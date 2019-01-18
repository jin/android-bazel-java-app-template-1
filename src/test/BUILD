load("@rules_maven//:defs.bzl", "artifact")
load("//:versions.bzl", "versions", "targetSdkVersion")

android_local_test(
    name = "main_activity_test",
    srcs = ["java/burrows/apps/example/template/activity/MainActivityTest.java"],
    manifest = "AndroidManifest.xml",
    manifest_values = {
        "targetSdkVersion": str(targetSdkVersion),
    },
    test_class = "burrows.apps.example.template.activity.MainActivityTest",
    deps = [
        "//bazel/robolectric:robolectric_and_android_all",
        "//src/main:template_app_lib",
        artifact("org.assertj:assertj-core:" + versions["assertj"]),
        artifact("org.robolectric.shadows:framework:" + versions["robolectric"]),
    ],
)

android_local_test(
    name = "ads_util_test",
    srcs = ["java/burrows/apps/example/template/util/AdUtilsTest.java"],
    aapt_version = "aapt2",
    manifest = "AndroidManifest.xml",
    manifest_values = {
        "targetSdkVersion": str(targetSdkVersion),
    },
    test_class = "burrows.apps.example.template.util.AdUtilsTest",
    deps = [
        "//bazel/robolectric:robolectric_and_android_all",
        "//src/main:template_app_lib",
        artifact("org.hamcrest:hamcrest-library:1.3"),
        artifact("com.google.android.gms:play-services-ads-lite:" + versions["gps"]),
    ],
)

android_local_test(
    name = "play_services_utils_test",
    srcs = ["java/burrows/apps/example/template/util/PlayServicesUtilsTest.java"],
    manifest = "AndroidManifest.xml",
    manifest_values = {
        "targetSdkVersion": str(targetSdkVersion),
    },
    test_class = "burrows.apps.example.template.util.PlayServicesUtilsTest",
    deps = [
        "//bazel/robolectric:robolectric_and_android_all",
        "//src/main:template_app_lib",
        artifact("androidx.annotation:annotation"),
        artifact("org.hamcrest:hamcrest-library"),
        artifact("org.easymock:easymock"),
        artifact("com.google.android.gms:play-services-basement"),
        artifact("com.google.android.gms:play-services-base"),
        artifact("org.powermock:powermock-api-easymock"),
        artifact("org.powermock:powermock-api-support"),
        artifact("org.powermock:powermock-core"),
        artifact("org.powermock:powermock-module-junit4"),
    ],
)
