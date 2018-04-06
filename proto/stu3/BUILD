package(default_visibility = ["//visibility:public"])

licenses(["notice"])

load("@io_bazel_rules_go//proto:def.bzl", "go_proto_library")

proto_library(
    name = "datatypes",
    srcs = [
        "annotations.proto",
        "codes.proto",
        "datatypes.proto",
    ],
    deps = [
        "@com_google_protobuf//:descriptor_proto",
    ],
)

java_proto_library(
    name = "datatypes_java_proto",
    strict_deps = 0,
    deps = [":datatypes"],
)

go_proto_library(
    name = "descriptor_go_proto",
    importpath = "github.com/golang/protobuf/protoc-gen-go/descriptor",
    proto = "@com_google_protobuf//:descriptor_proto",
)

go_proto_library(
    name = "datatypes_go_proto",
    proto = ":datatypes",
    importpath = "github.com/google/fhir/proto/stu3/datatypes",
    deps = ["descriptor_go_proto"],
)

proto_library(
    name = "resources_proto",
    srcs = [
        "resources.proto",
    ],
    deps = [
        ":datatypes",
    ],
)

java_proto_library(
    name = "resources_java_proto",
    strict_deps = 0,
    deps = [":resources_proto"],
)

go_proto_library(
    name = "resources_go_proto",
    proto = ":resources_proto",
    importpath = "github.com/google/fhir/proto/stu3/resources",
    deps = [":datatypes_go_proto"],
)

proto_library(
    name = "extensions",
    srcs = [
        "base64_separator_stride.proto",
        "elementdefinition_binding_name.proto",
        "primitive_has_no_value.proto",
        "structuredefinition_explicit_type_name.proto",
    ],
    deps = [
        ":datatypes",
    ],
)

java_proto_library(
    name = "extensions_java_proto",
    strict_deps = 0,
    deps = [":extensions"],
)

go_proto_library(
    name = "extensions_go_proto",
    proto = ":extensions",
    importpath = "github.com/google/fhir/proto/stu3/extensions",
    deps = [":datatypes_go_proto"],
)

# We also make the .proto files readable for testing.
filegroup(
    name = "testdata",
    srcs = glob([
        "*.proto",
    ]),
)
