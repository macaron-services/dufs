# Macaron Service: Dufs

```bash
macaron install https://github.com/macaron-services/dufs
```

The service exposes the current user's home directory through
[dufs](https://github.com/sigoden/dufs), with upload, download, edit, search,
archive, and delete operations enabled. Macaron chooses the listening port and
dufs binds to all network interfaces so the service is reachable through the
Macaron Tailscale environment.

To serve a different directory, set `DUFS_SERVE_PATH` before starting Macaron:

```bash
DUFS_SERVE_PATH="$HOME/Downloads" macaron start
```

The service does not add application-level authentication. Only run it in a
trusted network environment, and choose a restricted `DUFS_SERVE_PATH` when
you do not want to expose the entire home directory.
