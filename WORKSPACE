workspace(name = "com_google_fhir")

# proto_library, cc_proto_library, and java_proto_library rules implicitly
# depend on @com_google_protobuf for protoc and proto runtimes.
# This statement defines the @com_google_protobuf repo.
http_archive(
    name = "com_google_protobuf",
    sha256 = "cef7f1b5a7c5fba672bec2a319246e8feba471f04dcebfe362d55930ee7c1c30",
    strip_prefix = "protobuf-3.5.0",
    urls = ["https://github.com/google/protobuf/archive/v3.5.0.zip"],
)

http_archive(
    name = "io_bazel_rules_go",
    url = "https://github.com/bazelbuild/rules_go/releases/download/0.10.3/rules_go-0.10.3.tar.gz",
    sha256 = "feba3278c13cde8d67e341a837f69a029f698d7a27ddbb2a202be7a10b22142a",
)
load("@io_bazel_rules_go//go:def.bzl", "go_rules_dependencies", "go_register_toolchains")
go_rules_dependencies()
go_register_toolchains()

maven_jar(
    name = "guava_maven",
    artifact = "com.google.guava:guava:24.1-jre",
    sha1 = "96c528475465aeb22cce60605d230a7e67cebd7b",
)

bind(
    name = "guava",
    actual = "@guava_maven//jar",
)

maven_jar(
    name = "gson_maven",
    artifact = "com.google.code.gson:gson:2.8.2",
    sha1 = "3edcfe49d2c6053a70a2a47e4e1c2f94998a49cf",
)

bind(
    name = "gson",
    actual = "@gson_maven//jar",
)

maven_jar(
    name = "jcommander_maven",
    artifact = "com.beust:jcommander:1.72",
    sha1 = "6375e521c1e11d6563d4f25a07ce124ccf8cd171",
)

bind(
    name = "jcommander",
    actual = "@jcommander_maven//jar",
)

maven_jar(
    name = "junit_maven",
    artifact = "junit:junit:4.12",
    sha1 = "2973d150c0dc1fefe998f834810d68f278ea58ec",
)

bind(
    name = "junit",
    actual = "@junit_maven//jar",
)

maven_jar(
    name = "truth_maven",
    artifact = "com.google.truth:truth:0.40",
    sha1 = "0d74e716afec045cc4a178dbbfde2a8314ae5574",
)

bind(
    name = "truth",
    actual = "@truth_maven//jar",
)
