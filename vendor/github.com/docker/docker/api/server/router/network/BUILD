load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "backend.go",
        "filter.go",
        "network.go",
        "network_routes.go",
    ],
    importpath = "github.com/docker/docker/api/server/router/network",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/docker/docker/api/errors:go_default_library",
        "//vendor/github.com/docker/docker/api/server/httputils:go_default_library",
        "//vendor/github.com/docker/docker/api/server/router:go_default_library",
        "//vendor/github.com/docker/docker/api/types:go_default_library",
        "//vendor/github.com/docker/docker/api/types/filters:go_default_library",
        "//vendor/github.com/docker/docker/api/types/network:go_default_library",
        "//vendor/github.com/docker/docker/api/types/versions:go_default_library",
        "//vendor/github.com/docker/docker/daemon/cluster:go_default_library",
        "//vendor/github.com/docker/docker/runconfig:go_default_library",
        "//vendor/github.com/docker/libnetwork:go_default_library",
        "//vendor/github.com/docker/libnetwork/networkdb:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["filter_test.go"],
    importpath = "github.com/docker/docker/api/server/router/network",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/docker/docker/api/types:go_default_library",
        "//vendor/github.com/docker/docker/api/types/filters:go_default_library",
    ],
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
