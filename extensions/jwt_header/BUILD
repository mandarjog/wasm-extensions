licenses(["notice"])  # Apache 2
load("@proxy_wasm_cpp_sdk//bazel/wasm:wasm.bzl", "wasm_cc_binary")

wasm_cc_binary(
    name = "jwt_header.wasm",
    srcs = [
        "config.cc",
        "plugin.cc",
        "@io_istio_proxy//extensions/common/wasm:base64.h",
    ],
    hdrs = [
        "plugin.h",
    ],
    visibility = ["//visibility:public"],
    deps = [
        ":config_cc_proto",
        "@com_google_absl//absl/strings",
        "@com_google_absl//absl/time",
        "@io_istio_proxy//extensions/common/wasm:json_util",
        "@proxy_wasm_cpp_sdk//:proxy_wasm_intrinsics",
    ],
)

cc_proto_library(
    name = "config_cc_proto",
    visibility = ["//visibility:public"],
    deps = ["config_proto"],
)

proto_library(
    name = "config_proto",
    srcs = ["config.proto"],
)

