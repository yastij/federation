load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "common.go",
        "coverage.go",
        "go1_1.go",
        "go1_2.go",
        "index.go",
        "language.go",
        "lookup.go",
        "match.go",
        "parse.go",
        "tables.go",
        "tags.go",
    ],
    importpath = "golang.org/x/text/language",
    visibility = ["//visibility:public"],
    deps = ["//vendor/golang.org/x/text/internal/tag:go_default_library"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "coverage_test.go",
        "data_test.go",
        "language_test.go",
        "lookup_test.go",
        "match_test.go",
        "parse_test.go",
    ],
    data = glob(["testdata/**"]),
    importpath = "golang.org/x/text/language",
    library = ":go_default_library",
    deps = [
        "//vendor/golang.org/x/text/internal/tag:go_default_library",
        "//vendor/golang.org/x/text/internal/testtext:go_default_library",
        "//vendor/golang.org/x/text/internal/ucd:go_default_library",
    ],
)

go_test(
    name = "go_default_xtest",
    srcs = [
        "examples_test.go",
        "httpexample_test.go",
    ],
    data = glob(["testdata/**"]),
    importpath = "golang.org/x/text/language_test",
    deps = [":go_default_library"],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [
        ":package-srcs",
        "//vendor/golang.org/x/text/language/display:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
