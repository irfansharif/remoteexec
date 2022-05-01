load("@bazel_gazelle//:def.bzl", "gazelle")
load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library")

# gazelle:prefix github.com/irfansharif/remoteexec
gazelle(name = "gazelle")

go_binary(
    name = "remoteexec",
    embed = [":main_lib"],
    visibility = ["//visibility:public"],
)

go_library(
    name = "main_lib",
    srcs = ["main.go"],
    importpath = "github.com/irfansharif/remoteexec",
    visibility = ["//visibility:private"],
)
