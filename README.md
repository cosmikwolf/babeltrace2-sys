# babeltrace2-sys &emsp; [![crates.io]](https://crates.io/crates/babeltrace2-sys)

Rust sys crate for [babeltrace2](https://github.com/efficios/babeltrace)

## Building with System-Installed Babeltrace

By default, this crate builds and links against a bundled version of Babeltrace. If you have Babeltrace 2.x already installed on your system, you can use it instead by setting the `BABELTRACE_USE_SYSTEM` environment variable:

```bash
BABELTRACE_USE_SYSTEM=1 cargo build
```

This requires:
- Babeltrace 2.x (>= 2.0.0) to be installed on your system
- Development headers for Babeltrace
- pkg-config to be available

If the system-installed Babeltrace cannot be found, the build will automatically fall back to the bundled version with a warning message.

To explicitly disable using the system Babeltrace (which is the default behavior):

```bash
BABELTRACE_USE_SYSTEM=0 cargo build
```

### Dependencies

When using the system-installed Babeltrace, the crate will dynamically link against:
- babeltrace2
- babeltrace2-ctf-writer
- glib-2.0
- gmodule-2.0
- libpcre

When building from the bundled source, these dependencies will be statically linked.

[crates.io]: https://img.shields.io/crates/v/babeltrace2-sys.svg
