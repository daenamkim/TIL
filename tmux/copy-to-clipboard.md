# Copy to Clipboard

For the latest version(2.9a) tmux, clipboard setting is different from the formal way like [here](https://ktrysmt.github.io/blog/hook-up-clipboard-and-tmux-buffer-on-windows-and-osx/) at least in macOS.

Install a tool

```sh
$ brew install reattach-to-user-namespace
```

Setup config

```sh
$ vi .tmux.conf
```

Add lines below

```conf
setw -g mode-keys vi
bind-key -T copy-mode-vi MouseDragEnd1Pane send-keys -X copy-pipe-and-cancel "reattach-to-user-namespace pbcopy"

unbind -T copy-mode-vi Enter
bind-key -T copy-mode-vi Enter send-keys -X copy-pipe-and-cancel "reattach-to-user-namespace pbcop
```

[Reference](https://qiita.com/kai_kou/items/900108081c65930e9d9c)
