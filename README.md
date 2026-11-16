# TermuxPP:Float

[![Build status](https://github.com/pschmitt/termuxpp-float/actions/workflows/github_action_build.yml/badge.svg?branch=main)](https://github.com/pschmitt/termuxpp-float/actions)

A TermuxPP companion app to show the terminal in a floating terminal window.

> **TermuxPP release channel:** New builds are published in the
> [TermuxPP monorepo](https://github.com/pschmitt/termuxpp/releases/tag/latest).
> This repository has no published releases. See the
> [self-update guide](https://github.com/pschmitt/termuxpp/blob/main/docs/en/self-update.md).
##



### Contents
- [Installation](#Installation)
- [Terminal and App Settings](#Terminal-and-App-Settings)
- [Debugging](#Debugging)
- [Worthy Of Note](#Worthy-Of-Note)
- [For Maintainers and Contributors](#For-Maintainers-and-Contributors)
- [Forking](#Forking)
##



### Installation

This fork currently tracks Termux:Float `v0.17.0`.

Install [TermuxPP](https://github.com/pschmitt/termuxpp-app) first, then install a matching TermuxPP:Float build from this repository's [GitHub Actions](https://github.com/pschmitt/termuxpp-float/actions). Both apps must use the same signing certificate. Stock Termux:Float and F-Droid builds are not compatible with this fork.

Action artifacts are produced for commits and pull requests and can be downloaded from each workflow run. They are debuggable and are only compatible with builds signed by the same certificate. Releases, when published, will attach APKs under their assets.

### Terminal and App Settings

TermuxPP:Float reads settings from `~/.config/termuxpp/termux.float.properties`, then falls back to `~/.config/termux/termux.float.properties` and the legacy `~/.termux/termux.float.properties` file. Currently, only the following properties are supported: `enforce-char-based-input`, `ctrl-space-workaround`, `bell-character`, `terminal-cursor-style`, `terminal-transcript-rows`, `back-key`, `default-working-directory`, `volume-keys`. Check [Terminal Settings](https://wiki.termux.com/wiki/Terminal_Settings) for more info. The `~/` is a shortcut for the TermuxPP home directory and can also be referred to by the `$HOME` shell environment variable.

You can create/edit it with a text editor in Termux. For example:

```
mkdir -p ~/.config/termuxpp
nano ~/.config/termuxpp/termux.float.properties
```

##



### Debugging

You can help debug problems by setting appropriate `logcat` `Log Level` in TermuxPP settings -> TermuxPP:Float -> Debugging -> Log Level. The `Log Level` defaults to `Normal` and log level `Verbose` currently logs additional information. Its best to revert log level to `Normal` after you have finished debugging since private data may otherwise be passed to `logcat` during normal operation and moreover, additional logging increases execution time.

Once log levels have been set, you can run the `logcat` command in `Termux` or `Termux:Float` app terminal to view the logs in realtime (`Ctrl+c` to stop) or use `logcat -d > logcat.txt` to take a dump of the log. You can also view the logs from a PC over `ADB`. For more information, check official android `logcat` guide [here](https://developer.android.com/studio/command-line/logcat).

##### Log Levels
- `Off` - Log nothing
- `Normal` - Start logging error, warn and info messages and stacktraces
- `Debug` - Start logging debug messages
- `Verbose` - Start logging verbose messages
##



## For Maintainers and Contributors

Check [For Maintainers and Contributors](https://github.com/pschmitt/termuxpp-app#for-maintainers-and-contributors) in the TermuxPP core README.
##



## Forking

Check [Forking](https://github.com/pschmitt/termuxpp-app#forking) in the TermuxPP core README for details.
##



[Termux]: https://termux.dev
