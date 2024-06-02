cc_library(
    name = "factorial",
    srcs = ["factorial.cc"],
    hdrs = ["factorial.hh"],
    defines = [
        "DOCTEST_CONFIG_SUPER_FAST_ASSERTS",
    ],
    deps = ["@doctest//doctest"],
    alwayslink = True,
)

cc_test(
    name = "factorial-test",
    deps = [
        ":factorial",
        "@doctest//doctest:main",
    ],
)
