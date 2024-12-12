Assuming `bazel` is actually `bazelisk`:

Run `bazel test //make_simple:*` and note that it succeeds.

Run `bazel test //make_wildcard:*` and note that it fails.

Change `.bazelversion` to read `6.5.0` and try again. Both now work.
