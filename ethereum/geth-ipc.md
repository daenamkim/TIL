# geth.ipc


If geth.ipc's location length reaches and exceeds 108, then geth will be terminated.

## References

- [Fatal: Error starting protocol stack: listen unix <PATH_TO_DATADIR>/geth.ipc: bind: invalid argument](https://github.com/ethereum/go-ethereum/issues/16342)
- [Why is socket path length limited to a hundred chars?](https://unix.stackexchange.com/questions/367008/why-is-socket-path-length-limited-to-a-hundred-chars/367012#367012)
