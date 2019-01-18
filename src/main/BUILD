load("@rules_maven//:defs.bzl", "artifact")
load("//:versions.bzl", "versions", "targetSdkVersion")
load("@tools_android//tools/crashlytics:defs.bzl", "crashlytics_android_library")

crashlytics_android_library(
    name = "crashlytics_lib",
    package_name = "burrows.apps.example.template",
    build_id = "9dfea8fe-4d75-48a7-ba28-4ddb7fe74780",
    google_services_json = "google-services.json",
)

android_library(
    name = "template_app_lib",
    srcs = glob(["java/**/*.java"]),
    custom_package = "burrows.apps.example.template",
    manifest = "java/AndroidManifest.xml",
    resource_files = glob(["res/**/*"]),
    visibility = ["//src:__subpackages__"],
    deps = [
        ":crashlytics_lib",
        ":external_deps",
    ],
)

android_binary(
    name = "template_app",
    custom_package = "burrows.apps.example.template",
    manifest = "AndroidManifest.xml",
    manifest_values = {
        "targetSdkVersion": str(targetSdkVersion),
    },
    visibility = ["//src/androidTest:__subpackages__"],
    deps = [
        "//src/main:template_app_lib",
    ],
)

android_library(
    name = "external_deps",
    exports = [
        artifact("com.google.android.material:material"),
        artifact("com.google.android.gms:play-services-ads"),
        artifact("com.google.android.gms:play-services-ads-lite"),
        artifact("com.google.android.gms:play-services-basement"),
        artifact("com.google.android.gms:play-services-base"),
        artifact("androidx.annotation:annotation"),
        artifact("androidx.cardview:cardview"),
        artifact("androidx.appcompat:appcompat"),
        artifact("androidx.recyclerview:recyclerview"),
        artifact("androidx.fragment:fragment"),
        artifact("com.crashlytics.sdk.android:crashlytics"),
        artifact("io.fabric.sdk.android:fabric"),
    ],
)
