load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "adapter.go",
        "attachment.go",
        "container.go",
        "controller.go",
        "errors.go",
        "executor.go",
        "validate.go",
    ],
    importpath = "github.com/docker/docker/daemon/cluster/executor/container",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/docker/distribution/reference:go_default_library",
        "//vendor/github.com/docker/docker/api/types:go_default_library",
        "//vendor/github.com/docker/docker/api/types/backend:go_default_library",
        "//vendor/github.com/docker/docker/api/types/container:go_default_library",
        "//vendor/github.com/docker/docker/api/types/events:go_default_library",
        "//vendor/github.com/docker/docker/api/types/filters:go_default_library",
        "//vendor/github.com/docker/docker/api/types/mount:go_default_library",
        "//vendor/github.com/docker/docker/api/types/network:go_default_library",
        "//vendor/github.com/docker/docker/api/types/swarm:go_default_library",
        "//vendor/github.com/docker/docker/api/types/volume:go_default_library",
        "//vendor/github.com/docker/docker/container:go_default_library",
        "//vendor/github.com/docker/docker/daemon/cluster/controllers/plugin:go_default_library",
        "//vendor/github.com/docker/docker/daemon/cluster/convert:go_default_library",
        "//vendor/github.com/docker/docker/daemon/cluster/executor:go_default_library",
        "//vendor/github.com/docker/docker/daemon/cluster/provider:go_default_library",
        "//vendor/github.com/docker/docker/pkg/system:go_default_library",
        "//vendor/github.com/docker/go-connections/nat:go_default_library",
        "//vendor/github.com/docker/libnetwork:go_default_library",
        "//vendor/github.com/docker/libnetwork/datastore:go_default_library",
        "//vendor/github.com/docker/libnetwork/types:go_default_library",
        "//vendor/github.com/docker/swarmkit/agent:go_default_library",
        "//vendor/github.com/docker/swarmkit/agent/exec:go_default_library",
        "//vendor/github.com/docker/swarmkit/api:go_default_library",
        "//vendor/github.com/docker/swarmkit/api/genericresource:go_default_library",
        "//vendor/github.com/docker/swarmkit/api/naming:go_default_library",
        "//vendor/github.com/docker/swarmkit/log:go_default_library",
        "//vendor/github.com/docker/swarmkit/template:go_default_library",
        "//vendor/github.com/gogo/protobuf/types:go_default_library",
        "//vendor/github.com/opencontainers/go-digest:go_default_library",
        "//vendor/github.com/pkg/errors:go_default_library",
        "//vendor/github.com/sirupsen/logrus:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
        "//vendor/golang.org/x/time/rate:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "health_test.go",
        "validate_test.go",
        "validate_unix_test.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "validate_windows_test.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/docker/docker/daemon/cluster/executor/container",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/docker/docker/api/types/container:go_default_library",
        "//vendor/github.com/docker/docker/container:go_default_library",
        "//vendor/github.com/docker/docker/daemon:go_default_library",
        "//vendor/github.com/docker/docker/daemon/events:go_default_library",
        "//vendor/github.com/docker/docker/pkg/stringid:go_default_library",
        "//vendor/github.com/docker/swarmkit/api:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
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
