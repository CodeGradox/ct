# ct

Open, or reopen, a tmux session running Claude Code for the current folder.
Remembers the session name per folder, so a bare `ct` gets you back in.

## Usage

```sh
ct          # reuse this folder's saved name (asks the first time)
ct <name>   # use <name> and remember it for this folder
```

- Inside tmux, it switches to the session instead of nesting.
- If the session is gone (Claude exited, server rebooted), it starts a new one.
- `.` and `:` in names become `_`; tmux reads them as separators.

## Install

```sh
curl -fsSL https://raw.githubusercontent.com/CodeGradox/ct/main/ct -o ~/.local/bin/ct
chmod +x ~/.local/bin/ct
```

`~/.local/bin` must be on your `PATH`. Needs `tmux` and `claude`.

## Storage

Names are saved in `$XDG_STATE_HOME/ct/sessions`, or `~/.local/state/ct/sessions` when it's unset.
One `folder<TAB>name` line per folder.
