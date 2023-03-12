# Localization

[Linux Mint Translation Guide](broken-reference)

Note

This chapter explains how translations work. It is useful for getting a better understanding of the workflow and the technology but it isn’t required in order to start translating Linux Mint. If you want to skip it, you can go straight to the next chapter.

Software applications and user interfaces are designed in English.

The Linux Mint developers use a library and a set of tools called Gettext to localize them.

If you look at source code, you’ll often see an underscore function wrapping English words and sentences. For instance `_("Yes")` instead of `"Yes"`. This underscore refers to Gettext and indicates that the string `"Yes"` is localized.

Here’s an example in Python. The code below creates two buttons. They’re both labeled `Yes`, but button2 is localized whereas button1 isn’t.

```
button1 = Gtk.Button()
button2 = Gtk.Button()
button1.set_label("Yes")
button2.set_label(_("Yes"))
```

At runtime, button2 will be properly translated, whereas button1 will always show in English.

If you run this code in French, you’ll see a `Yes` button, and a `Oui` button. If you run it in Spanish, you’ll see a `Yes` button, and a `Sí` button.

Of course, for this to work, French and Spanish translations for `Yes` have to be available. If they aren’t, the second button will show in English.

### POT Templates[¶](broken-reference)

For each project, the Linux Mint developers extract all the English words and sentences and put everything that has to be translated into a `.pot` file called the `PO template`.

They then upload that file to Launchpad, where translators can translate the words and sentences into their own languages.

### PO files[¶](broken-reference)

The Linux Mint development team then downloads all the translations from Launchpad and packages them into the operating system.

The translations consist of `.po` files that are compiled and installed as `.mo` files on the filesystem, usually in `/usr/share/locale`.

They are packaged in their relevant applications, or sometimes in translation packages such as `mint-translations` (for the Mint tools) or `cinnamon-l10n` (for Cinnamon).
