workspace(name = "luajit-bazel-test")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
http_archive(
    name = "bazel_features",
    sha256 = "9c7f9a4c997cbf0eb93572b68b0ff0bb9822004633101a16d89499e814190323",
    strip_prefix = "bazel_features-1.22.0",
    url = "https://github.com/bazel-contrib/bazel_features/releases/download/v1.22.0/bazel_features-v1.22.0.tar.gz",
)
load("@bazel_features//:deps.bzl", "bazel_features_deps")
bazel_features_deps()

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
http_archive(
    name = "rules_foreign_cc",
    sha256 = "8e5605dc2d16a4229cb8fbe398514b10528553ed4f5f7737b663fdd92f48e1c2",
    strip_prefix = "rules_foreign_cc-0.13.0",
    url = "https://github.com/bazel-contrib/rules_foreign_cc/releases/download/0.13.0/rules_foreign_cc-0.13.0.tar.gz",
)

load("@rules_foreign_cc//foreign_cc:repositories.bzl", "rules_foreign_cc_dependencies")

# This sets up some common toolchains for building targets. For more details, please see
# https://bazelbuild.github.io/rules_foreign_cc/0.13.0/flatten.html#rules_foreign_cc_dependencies
rules_foreign_cc_dependencies()

http_archive(
    name = "com_github_luajit_luajit",
    build_file_content = 'filegroup(name = "all", srcs = glob(["**"], exclude=[]), visibility = ["//visibility:public"])',
    patches = ["//:luajit.patch"],
    patch_args = ["-p1"],
    patch_cmds = ["chmod u+x build.py"],
    sha256 = "e91acbe181cf6ffa3ef15870b8e620131002240ba24c5c779fd0131db021517f",
    strip_prefix = "LuaJIT-19878ec05c239ccaf5f3d17af27670a963e25b8b",
    url = "https://github.com/LuaJIT/LuaJIT/archive/19878ec05c239ccaf5f3d17af27670a963e25b8b.tar.gz",
)
