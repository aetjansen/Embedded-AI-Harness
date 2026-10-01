# The `music-buddy` branch

This branch is the bench software as it runs on the Music Buddy bench (espworkbench): the
upstream `main` plus our fixes that are not (yet) upstream. A fresh Pi installed from this
branch has all of them; the change requests behind them are in the music-buddy repository,
`testing/testbench-change-requests.md`.

| Fix | Change request | Upstream |
|---|---|---|
| Wi-Fi: rfkill unblock, Wi-Fi country at install, `password` alias, `sta_leave` no-op and restoring the AP's internet/DNS | CR-1, CR-2, CR-3, CR-11, CR-13 | PR #39 (open) |
| `serial_write`: short read timeout in the drain (5.7 s → 1.3 s per command) | CR-15 | not yet offered |
| `serial_write`: hold 0.2 s instead of 0.6 s (1.3 s → about 0.9 s per command) | CR-15 follow-up | not yet offered |

## Install or update the Pi from this branch

```
git clone -b music-buddy https://github.com/aetjansen/Embedded-AI-Harness.git
cd Embedded-AI-Harness/pi
sudo bash install.sh            # a new Pi
sudo bash install.sh --update   # an installed Pi: scripts only
```

Already cloned: `git pull` in that directory, then `sudo bash install.sh --update`.

## Keeping up with upstream

```
git fetch origin && git merge origin/main     # on the music-buddy branch
```
