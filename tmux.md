Terminal multiplexer
===
| | New session                                              | Interactive | Visually
|-|-|-|-|
| Horizontal | tmux new-session\\; splitw -h                 | <> %        | \\| \\| \\|
|            | tmux new\\; splitw -h\\; splitw -h\\; select-layout even-horizontal        | \\| \\| \\| \\|
| Vertical   | tmux new';' splitw -v                         | <> "        | &Xi;
