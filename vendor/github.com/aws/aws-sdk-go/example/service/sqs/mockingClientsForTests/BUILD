load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["ifaceExample.go"],
    importpath = "github.com/aws/aws-sdk-go/example/service/sqs/mockingClientsForTests",
    visibility = ["//visibility:private"],
    deps = [
        "//vendor/github.com/aws/aws-sdk-go/aws:go_default_library",
        "//vendor/github.com/aws/aws-sdk-go/aws/session:go_default_library",
        "//vendor/github.com/aws/aws-sdk-go/service/sqs:go_default_library",
        "//vendor/github.com/aws/aws-sdk-go/service/sqs/sqsiface:go_default_library",
    ],
)

go_binary(
    name = "mockingClientsForTests",
    importpath = "github.com/aws/aws-sdk-go/example/service/sqs/mockingClientsForTests",
    library = ":go_default_library",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = ["ifaceExample_test.go"],
    importpath = "github.com/aws/aws-sdk-go/example/service/sqs/mockingClientsForTests",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/aws/aws-sdk-go/aws:go_default_library",
        "//vendor/github.com/aws/aws-sdk-go/service/sqs:go_default_library",
        "//vendor/github.com/aws/aws-sdk-go/service/sqs/sqsiface:go_default_library",
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
