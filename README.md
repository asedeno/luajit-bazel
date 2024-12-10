Assuming `bazel` is actually `bazelisk`:

Run `bazel build :luajit` and note that it fails.

Change `.bazelversion` to read `6.5.0` and try again. It works.

Dig into the build logs when running with 7.4.1 and find that inside
of LuaJIT, `make -C src` causes make to segfault. No idea why.
