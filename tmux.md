tmux: Terminal multiplexer
===
| | New session                                                                    | Interactive | Visually |
|-|-|-|-|
| Horizontal | **tmux** new-session\\; splitw -h                                   | <> %           | \\| \\| \\| |
|            | tmux new\\; splitw -h\\; splitw -h\\; select-layout even-horizontal | <> : select... | \\| \\| \\| \\|
| Vertical   | tmux new';' splitw -v                                               | <> "           | &Xi; |

| | Interactive                                                                    |                |
|-|-|-|
| Pane layout change                                                               | <> Space |

| | Interactive command mode                                                       | <> : |
|-|-|-|
| select-layout                                                                    | |
| select-pane                                                                      | |
| select-window                                                                    | |
