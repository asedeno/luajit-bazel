load("@rules_foreign_cc//foreign_cc:configure.bzl", "configure_make")

configure_make(
    name = "luajit",
    configure_command = "build.py",
    lib_source = "@com_github_luajit_luajit//:all",
    out_include_dir = "include/luajit-2.1",
    out_static_libs = ["libluajit-5.1.a"],
    targets = [],
)
