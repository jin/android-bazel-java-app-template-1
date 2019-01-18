load("@rules_maven//:defs.bzl", "artifact")
load("//bazel/robolectric:android_all.bzl", "get_android_all_jars")
load("//:versions.bzl", "versions", "targetSdkVersion")

# ANDROID_ALL_JARS = [artifact(jar) for jar in get_android_all_jars(targetSdkVersion)]

java_library(
    name = "robolectric_and_android_all",
    data = [":robolectric-deps.properties"],
    visibility = ["//src/test:__subpackages__"],
    exports = [
        artifact("androidx.test.ext:junit"),
        artifact("org.robolectric:robolectric"),
        artifact("org.robolectric:android-all"),
    ],
)

filegroup(
    name = "android_all_jars",
    srcs = [
        artifact("org.robolectric:android-all"),
    ],
)

genrule(
    name = "gen_properties",
    srcs = [":android_all_jars"],
    outs = ["robolectric-deps.properties"],
    cmd = "$(location :gen_deps) $(locations :android_all_jars) > $@",
    tools = [":gen_deps"],
)

py_binary(
    name = "gen_deps",
    srcs = ["gen_deps.py"],
)
