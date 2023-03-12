# Optimizing JS with Cinnamon

## Cinnamon Javascript Optimization Techniques

This is a temporary chapter about Javascript optimization techniques in Cinnamon. It will be part of the dev guide when the Cinnamon design is described and the content of this section will then fit into the right place.

### Notes

Some of these optimization techniques don’t make sense to us and we cannot explain them all, but they were tested methodically.

Jason is the only one in the team to see an impact from them. He’s running a slow CPU with multi-monitors and a low-latency kernel with NVIDIA drivers. These were tested on Cinnamon 4.0. Performance boosts are witnessed in terms of input lag when moving windows and selecting text in Visual Studio Code.

These changes were tested in windowManager.js, an area of Cinnamon which is run constantly and which is prominent within the single execution thread.

### Reducing the overal number of gsettings signal listeners

Here’s an example: [https://github.com/linuxmint/Cinnamon/commit/47bef00856e3b1f5a1e1a19e829dec498376d033](https://github.com/linuxmint/Cinnamon/commit/47bef00856e3b1f5a1e1a19e829dec498376d033)

Reducing the number of listeners has a significant positive impact on performance.

### Using declared functions in signal listeners

We found out that using:

```
settings.connect('changed::property', (s, k) => { this.property = s.get_int(k); });
```

was slower than:

```
settings.connect('changed::property', (s, k) => this.setProperty(s, k));
```

i.e. declaring a function and referring to that function within the callback was faster than using an anonymous block of instructions in the callback.

The impact was significant.

### Factorizing callbacks

```
settings.connect('changed::int_property1', (s, k) => this.setProperty1(s, k));
settings.connect('changed::string_property2', (s, k) => this.setProperty2(s, k));
```

was slower than:

```
settings.connect('changed::int_property1', (s, k) => this.setProperty(s, k, 'int'));
settings.connect('changed::string_property2', (s, k) => this.setProperty(s, k, 'string'));
```

It makes `setProperty()` slower of course, although that’s usually not critical, but it makes the overal project faster.

The impact wasn’t as significant and this optimization is probably only suited to critical paths such as windowmanager.js.

### Grouping properties in smaller objects

Using `this.smallobject.property` is faster than `this.property`.

The idea is to avoid adding properties to large objects such as Main.wm.

So instead of using:

`Main.wm.desktop_effects_enabled`, we use `Main.wm.settings.desktop_effects_enabled`.

The impact is positive but subtle and this optimization is probably only suited to critical paths such as windowmanager.js.

### Using hashmaps vs properties

Using `this.smallobject['property']` is faster than `this.smallobject.property`.

The idea is confirmed by [https://jsperf.com/dot-notation-vs-square-bracket-notation](https://jsperf.com/dot-notation-vs-square-bracket-notation).

So instead of using:

`Main.wm.desktop_effects_enabled`, we use `Main.wm.settings['desktop_effects_enabled']`.

The impact is positive but subtle and this optimization is probably only suited to critical paths such as windowmanager.js.
