load("//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "construct.go",
        "doc.go",
        "generator.go",
        "resolve.go",
        "resolve_external.go",
        "resolve_structured.go",
    ],
    visibility = ["//visibility:public"],
    deps = [
        "@io_bazel_buildifier//core:go_default_library",
        "@org_golang_x_tools//go/vcs:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "resolve_external_test.go",
        "resolve_structured_test.go",
        "resolve_test.go",
    ],
    library = ":go_default_library",
)

go_test(
    name = "go_default_xtest",
    srcs = ["generator_test.go"],
    data = glob(["testdata/**/*"]),
    deps = [
        "@io_bazel_buildifier//core:go_default_library",
        ":go_default_library",
        "//go/tools/gazelle/testdata:go_default_library",
    ],
)
