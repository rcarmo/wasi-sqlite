# wasi-sqlite

This is a quick hack to see if I can get `sqlite` to build as a CLI application for [a-Shell](https://github.com/holzschu/a-shell) using [wasi-sdk](https://github.com/holzschu/wasi-sdk).

Based on `sqlite-amalgamation-3390200` and [wapm-sqlite](https://github.com/wapm-packages/sqlite), using the `__wasi__` symbol to tweak some `#ifdefs` that are not covered by `config.h`.
