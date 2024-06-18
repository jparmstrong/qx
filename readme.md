# qx - kdb/q remote prompt

This experimental script provides the ability to connect to a remote kdb/q session as if you were accessing it locally. When paired with `fzf`, it provides a seamless way of managing your production estate.

## Installation

Prerequisites:
- kdb+/q (obviously)
- fzf

Add the following to your `~/.bashrc`:

```
export QXHOME=/home/jp/code/qx # update to root of your project
alias qx="cat $QXHOME/qservers.txt | fzf --with-nth=1 | xargs -n2 -o rlwrap q $QXHOME/x.k -conn"
```

Copy `qservers.txt.skeleton` to `qservers.txt`. Update it with the servers you want listed when running `qx`.

## Usage

Run `qx` and select a server from the list.

To execute against the server run, `x)command` or `.x.e "command"`
