# wasi-sqlite

This is a quick hack to get `sqlite` to build as a CLI application for [a-Shell](https://github.com/holzschu/a-shell) using [wasi-sdk](https://github.com/holzschu/wasi-sdk).

Based on `sqlite-amalgamation-3390200` and inspired by [wapm-sqlite](https://github.com/wapm-packages/sqlite), using the `__wasi__` symbol to tweak some `#ifdefs` that are not covered by `config.h`.

Many thanks to `@holzschu` for guidance in getting this working and figuring out the right hacks to get the UNIX VFS to work.

## Known Issues

Working with moderate (100MB+) databases might fail via the `sqlite3` prompt, but doing

```
echo "<command or query>" | sqlite3 foo.db
```

...might be a good workaround (at least to do "VACUUM;" and other memory-intensive operations)

