load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "main.go",
        "test.go",
    ],
    importpath = "golang.org/x/tools/cmd/cover/testdata",
    visibility = ["//visibility:private"],
)

go_binary(
    name = "testdata",
    importpath = "golang.org/x/tools/cmd/cover/testdata",
    library = ":go_default_library",
    visibility = ["//visibility:public"],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
