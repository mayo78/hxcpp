# hxcpp (Nintendo Switch support)

This fork of hxcpp (Based on commit ``1618253``) has all the modifications needed to compile Haxe for the Nintendo Switch.
[Code taken from an old fork of hxcpp for the Nintendo Switch](https://github.com/retronx-team/switch-hxcpp) along with more changes in some parts of hxcpp to achieve a successful compilation for the console.

To use this, check out [HaxeNXCompiler](https://github.com/Slushi-Github/HaxeNXCompiler) or [Lime-NX](https://github.com/Slushi-Github/lime-nx).

**Please note that not everything provided by HXCPP has been tested on this experimental target.**

## Current known issues
- Socket partially supported, but not fully functional I think. IPV6 stuff and ``_hx_std_host_local`` in ``src/hx/libs/std/Socket.cpp`` (perhaps related to ``sys.net.Host.localhost``?) are not supported.
 * maybe similar issue with SQLite

- CFFI requires an implementation for this target.

- **(CRITICAL)** There appears to be a problem when the program ends that prevents it from releasing all the memory correctly, causing a crash.

## Important Changes

``sys.io.Process`` has been limited in this target, not due to compilation issues, but rather due to logic issues.

# Special Thanks

- [RetroNX Team](https://github.com/retronx-team) for the original work for use hxcpp on the Nintendo Switch.

- CRobes (On Discord) for helping me by telling me that I had to modify ``_hx_ssl_cert_load_defaults`` in ``src/hx/libs/ssl/SSL.cpp`` to support things like HTTPS requests in this target.