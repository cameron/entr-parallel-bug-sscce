# bug report

_entr doesn't seem to receive or act on file events when run by parallel_

Reproduce the issue:
- `$ parallel --line-buffered < cmds.txt`
- `$ echo "asdf" > watch_me`
- Should trigger entr as used in cmds.txt, but does not.

The second command in cmds.txt writes to a file instead of stdout just to convince us that the problem is not with `parallel` buffering output.
