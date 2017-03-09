package(default_visibility = ["//visibility:public"])

COPTS = [
    "-DSQLCIPHER_CRYPTO_OPENSSL",
    "-DSQLITE_HAS_CODEC",
    "-DSQLITE_OMIT_LOAD_EXTENSION",
    "-DSQLITE_OS_UNIX=1",
    "-DSQLITE_TEMP_STORE=3",
    "-D_HAVE_SQLITE_CONFIG_H",
]

cc_binary(
    name = "sqlcipher",
    srcs = ["shell.c"],
    deps = [":sqlcipher_lib"],
    copts = COPTS,
)

cc_library(
    name = "sqlcipher_lib",
    srcs = [
        "sqlite3.c",
        "config.h",
    ],
    hdrs = [
        "sqlite3.h",
        "sqlite3ext.h",
    ],
    copts = COPTS,
    deps = [
        "@boringssl//:crypto",
    ],
)
