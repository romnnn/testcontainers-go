load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")
load("@bazel_gazelle//:def.bzl", "gazelle")

# gazelle:prefix github.com/romnnn/testcontainers-go
gazelle(name = "gazelle")

go_library(
    name = "go_default_library",
    srcs = [
        "compose.go",
        "container.go",
        "docker.go",
        "generic.go",
        "logconsumer.go",
        "network.go",
        "reaper.go",
        "testing.go",
    ],
    importpath = "github.com/romnnn/testcontainers-go",
    visibility = ["//visibility:public"],
    deps = [
        "//wait:go_default_library",
        "@com_github_cenkalti_backoff//:go_default_library",
        "@com_github_docker_docker//api/types:go_default_library",
        "@com_github_docker_docker//api/types/container:go_default_library",
        "@com_github_docker_docker//api/types/mount:go_default_library",
        "@com_github_docker_docker//api/types/network:go_default_library",
        "@com_github_docker_docker//client:go_default_library",
        "@com_github_docker_docker//errdefs:go_default_library",
        "@com_github_docker_docker//pkg/archive:go_default_library",
        "@com_github_docker_go_connections//nat:go_default_library",
        "@com_github_google_uuid//:go_default_library",
        "@com_github_pkg_errors//:go_default_library",
        "@in_gopkg_yaml_v2//:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "compose_test.go",
        "container_test.go",
        "docker_test.go",
        "logconsumer_test.go",
        "network_test.go",
        "testing_test.go",
    ],
    embed = [":go_default_library"],
    deps = [
        "//wait:go_default_library",
        "@com_github_docker_docker//api/types:go_default_library",
        "@com_github_docker_docker//api/types/filters:go_default_library",
        "@com_github_docker_docker//api/types/volume:go_default_library",
        "@com_github_docker_docker//client:go_default_library",
        "@com_github_docker_docker//errdefs:go_default_library",
        "@com_github_docker_go_connections//nat:go_default_library",
        "@com_github_go_redis_redis//:go_default_library",
        "@com_github_go_sql_driver_mysql//:go_default_library",
        "@com_github_google_uuid//:go_default_library",
        "@com_github_pkg_errors//:go_default_library",
        "@com_github_stretchr_testify//assert:go_default_library",
        "@tools_gotest//assert:go_default_library",
    ],
)
