

# WD [![HitCount](http://hits.dwyl.io/GiovaLomba/wd.svg?style=plastic)](http://hits.dwyl.io/GiovaLomba/wd)
A filesystem WatchDog. It watches events on files and directories on a given portion of a filesystem. Events can happen on files or directories; everything which isn't a directory is considered as a file (alias and/or link too). Recordered events are classified as follows:

- __Created__: a new item has been created in the watched portion of the filesystem.
- __Moved__: an item has been moved from or to a watched portion of the filesystem.
- __Modified__: an item in the watched portion of the filesystem has been edited.
- __Deleted__: an item in the watched portion of the filesystem has been removed.

## How does it works?

```
(c) 2019 Giovanni Lombardo mailto://g.lombardo@protonmail.com
wd.exe version 1.0.0

usage: wd.exe [-h] [-i IGNORED [IGNORED ...]] [-g] [-p] [-ci CI] [-ls LS]
              [-ln LN]
              location log

It records events on a given portion of filesystem.

positional arguments:
  location              The portion of the filesystem to watch.
  log                   The log file that will contain event entries.

optional arguments:
  -h, --help            show this help message and exit
  -i IGNORED [IGNORED ...], --ignored IGNORED [IGNORED ...]
                        Pattern of items to ignore.
  -g, --git             When given it performs commit on the log folder.
  -p, --push            When given it performs pushes on the log folder.
  -ci CI, --commit-interval CI
                        When given it defines after how much time commits to
                        logs are performed; defaults to 60 (seconds).
  -ls LS, --log-size LS
                        When given defines the maximum size of each log file;
                        defaults to 30 (MB).
  -ln LN, --log-number LN
                        When given defines the maximum number of log files of
                        the given size; defaults to 10.
```
## Note
When the specified log file is actually stored into the watched portion of the filesystem every change to it will be reported as an event in the log file, thus generating a huge number of unuseful events. In such cases, to avoid this circumstance `wd` should be executed with the `-i` option with at least one (regex) pattern matching the name of the log file. Take a look at the following example:

```bash
wd.exe C:\ C:\Users\Jhon\Logs\wd.log -i "wd\.log$"
                                     -------------
```

The dot (`.`) in the regexp language has special meaning, so it must be escaped in order for it to be matched literally. The dollar sign (`-$`) at the end of the regex means that the matching string must end there.

## Download
* [Windows 10 X64](https://github.com/GiovaLomba/wd/raw/master/wd.exe)

## Contributing [![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=plastic)](https://github.com/GiovaLomba/wd/issues)

## Powered by
![Python](https://www.python.org/static/img/python-logo.png "Python")

<!---
[Python](https://www.python.org/)

[Watchdog](https://github.com/gorakhargosh/watchdog)

[PyInstaller](https://www.pyinstaller.org/)
-->
