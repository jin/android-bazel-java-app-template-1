load("@rules_maven//:defs.bzl", "artifact")
load("//:versions.bzl", "versions", "targetSdkVersion")

android_instrumentation_test(
    name = "main_activity_test",
    tags = ["manual"],  # Linux only, so this excludes it from //...
    target_device = "@android_test_support//tools/android/emulated_devices/generic_phone:android_23_x86_qemu2",
    test_app = ":template_test_app",
)

android_binary(
    name = "template_test_app",
    srcs = ["java/burrows/apps/example/template/instrumentation/MainActivityTest.java"],
    custom_package = "burrows.apps.example.template.instrumentation",
    instruments = "//src/main:template_app",
    manifest = "AndroidManifest.xml",
    manifest_values = {
        "targetSdkVersion": str(targetSdkVersion),
    },
    deps = [
        artifact("androidx.test:runner"),
        artifact("androidx.test:rules"),
        artifact("androidx.annotation:annotation"),
        artifact("androidx.test.espresso:espresso-core"),
        artifact("androidx.test.ext:junit"),
        artifact("junit:junit"),
        "//src/main:template_app_lib",
    ],
)
