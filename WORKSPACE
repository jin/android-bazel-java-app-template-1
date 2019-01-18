android_sdk_repository(
    name = "androidsdk",
    path = "/usr/local/google/home/jingwen/sdk",
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

RULES_MAVEN_COMMIT = "0.1.2"

http_archive(
    name = "rules_maven",
    strip_prefix = "rules_maven-%s" % RULES_MAVEN_COMMIT,
    url = "https://github.com/jin/rules_maven/archive/%s.zip" % RULES_MAVEN_COMMIT,
)

load("@rules_maven//:defs.bzl", "maven_install")
load("//:versions.bzl", "versions")

TEST_DEPS = [
    "androidx.test.espresso:espresso-core:" + versions["espresso"],
    "androidx.test.ext:junit:" + versions["androidx.test"]["ext"]["junit"],
    "androidx.test:rules:" + versions["androidx.test"]["rules"],
    "androidx.test:runner:" + versions["androidx.test"]["runner"],
    "junit:junit:" + versions["junit"],
    "org.assertj:assertj-core:" + versions["assertj"],
    "org.easymock:easymock:" + versions["easymock"],
    "org.powermock:powermock-api-easymock:" + versions["powermock"],
    "org.powermock:powermock-core:" + versions["powermock"],
    "org.powermock:powermock-module-junit4:" + versions["powermock"],
    "org.robolectric:robolectric:" + versions["robolectric"],
    "org.robolectric:android-all:8.1.0-robolectric-4611349",
]

maven_install(
    artifacts = [
        "com.google.android.material:material:" + versions["material"],
        "androidx.cardview:cardview:" + versions["cardview"],
        "com.google.android.gms:play-services-ads:" + versions["gps"],
        "com.google.android.gms:play-services-basement:" + versions["gps"],
        "com.google.android.gms:play-services-base:" + versions["gps"],
        "androidx.annotation:annotation:" + versions["annotation"],
        "com.crashlytics.sdk.android:crashlytics:" + versions["crashlytics"],
        "com.google.firebase:firebase-core:" + versions["firebase"],
        "com.google.gms:google-services:" + versions["google-services"],
        "io.fabric.sdk.android:fabric:1.4.7",
    ] + TEST_DEPS,
    repositories = [
        "https://maven.fabric.io/public",
        "https://bintray.com/bintray/jcenter",
        "https://maven.google.com",
        "https://repo1.maven.org/maven2",
    ],
)

ATS_COMMIT = "964da25c7af91b2208505b81409e03b0313f328c"

http_archive(
    name = "android_test_support",
    sha256 = "d00b880d3302535ef370d82c12aa3e92f5feef0fb1449f92f55cdd776e8cde69",
    strip_prefix = "android-test-%s" % ATS_COMMIT,
    urls = ["https://github.com/jin/android-test/archive/%s.tar.gz" % ATS_COMMIT],
)

load("@android_test_support//:repo.bzl", "android_test_repositories")

android_test_repositories()

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Google Maven Repository
GMAVEN_TAG = "20181212-2"

http_archive(
    name = "gmaven_rules",
    strip_prefix = "gmaven_rules-%s" % GMAVEN_TAG,
    url = "https://github.com/bazelbuild/gmaven_rules/archive/%s.tar.gz" % GMAVEN_TAG,
)

load("@gmaven_rules//:gmaven.bzl", "gmaven_rules")

gmaven_rules()

TOOLS_ANDROID_VERSION = "0.1"

# http_archive(
#     name = "tools_android",
#     strip_prefix = "tools_android-" + TOOLS_ANDROID_VERSION,
#     url = "https://github.com/bazelbuild/tools_android/archive/%s.tar.gz" % TOOLS_ANDROID_VERSION,
# )

local_repository(
    name = "tools_android",
    path = "/usr/local/google/home/jingwen/code/tools_android",
)

load("@tools_android//tools/googleservices:defs.bzl", "google_services_workspace_dependencies")

google_services_workspace_dependencies()
