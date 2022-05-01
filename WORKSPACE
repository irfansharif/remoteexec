workspace(name = "remoteexec")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "5c4bd27429b1a307d51cd23d4677126aa6315fff608f0cd85c5bfb642a13b953",
    strip_prefix = "cockroachdb-rules_go-23b381c",
    urls = [
        "https://storage.googleapis.com/public-bazel-artifacts/bazel/cockroachdb-rules_go-v0.27.0-52-g23b381c.tar.gz",
    ],
)

# Load gazelle. This lets us auto-generate BUILD.bazel files throughout the
# repo.
http_archive(
    name = "bazel_gazelle",
    sha256 = "9fba095e4bebd8c6748154ca53c365862af47fa1651f7c0d25459e6ca5bb208f",
    strip_prefix = "bazelbuild-bazel-gazelle-3ea1d64",
    urls = [
        # v0.24.0
        "https://storage.googleapis.com/public-bazel-artifacts/bazel/bazelbuild-bazel-gazelle-v0.24.0-0-g3ea1d64.tar.gz",
    ],
)

http_archive(
    name = "io_buildbuddy_buildbuddy_toolchain",
    sha256 = "a2a5cccec251211e2221b1587af2ce43c36d32a42f5d881737db3b546a536510",
    strip_prefix = "buildbuddy-toolchain-829c8a574f706de5c96c54ca310f139f4acda7dd",
    urls = ["https://github.com/buildbuddy-io/buildbuddy-toolchain/archive/829c8a574f706de5c96c54ca310f139f4acda7dd.tar.gz"],
)

load("@io_buildbuddy_buildbuddy_toolchain//:deps.bzl", "buildbuddy_deps")

buildbuddy_deps()

load("@io_buildbuddy_buildbuddy_toolchain//:rules.bzl", "buildbuddy")

buildbuddy(name = "buildbuddy_toolchain")


load(
  "@io_bazel_rules_go//go:deps.bzl", 
  "go_rules_dependencies",
  "go_register_toolchains",
)

go_rules_dependencies()

go_register_toolchains(go_version = "1.18")

# Load gazelle dependencies.
load(
    "@bazel_gazelle//:deps.bzl",
    "gazelle_dependencies",
)

gazelle_dependencies()

