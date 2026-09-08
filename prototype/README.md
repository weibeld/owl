# Owl Prototype Script

A shell script for rudimentary management of Owl notes (no RAG or agent support).

## Setup

### Config file

`~/.config/owl/config.ini`:

```ini
dir=/Users/dw/repos/weibeld/owl-data
```

> Note: the config file uses the INI format, and `dir` specifies the local directory in which the Owl notes are stored.

### PATH

```bash
ln -s /Users/dw/repos/weibeld/owl/prototype/owl ~/.local/bin/owl
```
