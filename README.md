# wd
A filesystem watchdog.

```bash
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
## Download
* [Windows 10 X64](https://github.com/GiovaLomba/wd/raw/master/wd.exe)

## Powered by:
[Python](https://www.python.org/)

[Watchdog](https://github.com/gorakhargosh/watchdog)

[PyInstaller](https://www.pyinstaller.org/)
