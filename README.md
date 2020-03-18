# is it just me, or is this a bug report?

_entr doesn't seem to receive or act on file events when run by parallel_

Prereqs:
- [parallel](https://www.gnu.org/software/parallel/)
- entr

Reproduce the issue:
- `$ ./repro` to run parallel with some entr commands
- `$ echo "asdf" > watch_me`
- Should trigger entr as used in cmds.txt, but does not (beyond the startup event).

The second command in cmds.txt writes to a file instead of stdout just to convince us that the problem is not with `parallel` buffering output.
