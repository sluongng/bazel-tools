workspace(name = "com_github_atlassian_bazel_tools")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "a8d6b1b354d371a646d2f7927319974e0f9e52f73a2452d2b3877118169eb6bb",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_go/releases/download/v0.23.3/rules_go-v0.23.3.tar.gz",
        "https://github.com/bazelbuild/rules_go/releases/download/v0.23.3/rules_go-v0.23.3.tar.gz",
    ],
)

http_archive(
    name = "bazel_gazelle",
    sha256 = "d8c45ee70ec39a57e7a05e5027c32b1576cc7f16d9dd37135b0eddde45cf1b10",
    urls = [
        "https://storage.googleapis.com/bazel-mirror/github.com/bazelbuild/bazel-gazelle/releases/download/v0.20.0/bazel-gazelle-v0.20.0.tar.gz",
        "https://github.com/bazelbuild/bazel-gazelle/releases/download/v0.20.0/bazel-gazelle-v0.20.0.tar.gz",
    ],
)

git_repository(
    name = "com_github_bazelbuild_buildtools",
    commit = "22e56e7356b839fca53d4d20aff02e1a0dce32ae",  #v2.2.1
    remote = "https://github.com/bazelbuild/buildtools.git",
    shallow_since = "1583879293 +0100",
)

git_repository(
    name = "com_google_protobuf",
    commit = "d0bfd5221182da1a7cc280f3337b5e41a89539cf",  #v3.11.4
    remote = "https://github.com/protocolbuffers/protobuf.git",
    shallow_since = "1581711200 -0800",
)

load("@io_bazel_rules_go//go:deps.bzl", "go_register_toolchains", "go_rules_dependencies")
load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies")
load("@com_github_bazelbuild_buildtools//buildifier:deps.bzl", "buildifier_dependencies")
load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")
load("//gotemplate:deps.bzl", "gotemplate_dependencies")

go_rules_dependencies()

go_register_toolchains()

gazelle_dependencies()

buildifier_dependencies()

gotemplate_dependencies()

protobuf_deps()
