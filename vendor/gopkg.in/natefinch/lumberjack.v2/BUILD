load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "chown.go",
        "lumberjack.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "chown_linux.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "gopkg.in/natefinch/lumberjack.v2",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "lumberjack_test.go",
        "testing_test.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "linux_test.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "gopkg.in/natefinch/lumberjack.v2",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/BurntSushi/toml:go_default_library",
        "//vendor/gopkg.in/yaml.v1:go_default_library",
    ],
)

go_test(
    name = "go_default_xtest",
    srcs = [
        "example_test.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "rotate_test.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "gopkg.in/natefinch/lumberjack.v2_test",
    deps = [
        ":go_default_library",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/github.com/natefinch/lumberjack:go_default_library",
        ],
        "//conditions:default": [],
    }),
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
