workspace(
    name = "repro",
    managed_directories = {"@npm": ["node_modules"]},
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_nodejs",
    sha256 = "da72ea53fa1cb8ab5ef7781ba06b97259b7d579a431ce480476266bc81bdf21d",
    urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/0.36.2/rules_nodejs-0.36.2.tar.gz"],
)



load("@build_bazel_rules_nodejs//:defs.bzl", "node_repositories", "yarn_install")

node_repositories(
    package_json = ["//:package.json"],
)

yarn_install(
    name = "npm",
    package_json = "//:package.json",
    yarn_lock = "//:yarn.lock",
)

load("@npm//:install_bazel_dependencies.bzl", "install_bazel_dependencies")

install_bazel_dependencies()
