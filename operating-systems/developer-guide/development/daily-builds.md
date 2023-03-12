# Daily Builds

## Daily Builds

If you want to keep up to date with the latest git changes, you don’t need to rebuild everything all the time, you can use the Daily Builds PPA instead.

Important

The Daily Builds PPA contains daily builds of the very latest changes pushed by the developers on github. By using this PPA you’ll upgrade from stable to unstable versions which might introduce regressions or not work at all.

### Adding the PPA

To add the PPA to your computer, open a terminal and type:

```
sudo add-apt-repository ppa:linuxmint-daily-build-team/daily-builds
sudo apt-get update
```

### Upgrading software to unstable versions

Use the _Update Manager_ to upgrade your software to unstable versions.

### Reporting bugs

If you notice a regression, you can report it on the [Alpha Testing Github project](https://github.com/linuxmint/alpha-testing).

Make sure to read the disclaimers and information provided by this project before reporting issues. This project is only about regressions which appeared after the latest stable version of projects, not issues which already existed before then.

### Downgrading back to stable

To go back to stable versions, either restore a Timeshift snapshot, or remove the PPA, update the APT cache and use the _Maintenance -> Downgrade foreign packages_ section of the _Software Sources_ tool.
