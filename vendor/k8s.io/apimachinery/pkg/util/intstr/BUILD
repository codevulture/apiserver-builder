load("@io_bazel_rules_go//proto:def.bzl", "go_proto_library")
load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "generated.pb.go",
        "intstr.go",
    ],
    importpath = "k8s.io/apimachinery/pkg/util/intstr",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/go-openapi/spec:go_default_library",
        "//vendor/github.com/gogo/protobuf/proto:go_default_library",
        "//vendor/github.com/golang/glog:go_default_library",
        "//vendor/github.com/google/gofuzz:go_default_library",
        "//vendor/k8s.io/kube-openapi/pkg/common:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["intstr_test.go"],
    importpath = "k8s.io/apimachinery/pkg/util/intstr",
    library = ":go_default_library",
    deps = ["//vendor/github.com/ghodss/yaml:go_default_library"],
)

proto_library(
    name = "intstr_proto",
    srcs = ["generated.proto"],
    visibility = ["//visibility:public"],
)

go_proto_library(
    name = "intstr_go_proto",
    importpath = "k8s.io/apimachinery/pkg/util/intstr",
    proto = ":intstr_proto",
    visibility = ["//visibility:public"],
)
