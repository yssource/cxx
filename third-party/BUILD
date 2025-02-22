load(
    "//tools/bazel:third_party.bzl",
    cargo_build_script = "third_party_cargo_build_script",
    glob = "third_party_glob",
    rust_library = "third_party_rust_library",
)

rust_library(
    name = "bitflags",
    srcs = glob(["vendor/bitflags-1.3.2/src/**"]),
    edition = "2018",
)

rust_library(
    name = "cc",
    srcs = glob(["vendor/cc-1.0.73/src/**"]),
    edition = "2018",
    visibility = ["//visibility:public"],
)

rust_library(
    name = "clap",
    srcs = glob(["vendor/clap-3.1.18/src/**"]),
    crate_features = ["std"],
    edition = "2018",
    visibility = ["//visibility:public"],
    deps = [
        ":bitflags",
        ":clap_lex",
        ":indexmap",
        ":textwrap",
    ],
)

rust_library(
    name = "clap_lex",
    srcs = glob(["vendor/clap_lex-0.2.0/src/**"]),
    edition = "2018",
    deps = [
        ":os_str_bytes",
    ],
)

rust_library(
    name = "codespan-reporting",
    srcs = glob(["vendor/codespan-reporting-0.11.1/src/**"]),
    edition = "2018",
    visibility = ["//visibility:public"],
    deps = [
        ":termcolor",
        ":unicode-width",
    ],
)

rust_library(
    name = "hashbrown",
    srcs = glob(["vendor/hashbrown-0.11.2/src/**"]),
    crate_features = ["raw"],
    edition = "2018",
)

rust_library(
    name = "indexmap",
    srcs = glob(["vendor/indexmap-1.8.1/src/**"]),
    crate_features = ["std"],
    edition = "2018",
    rustc_flags = ["--cfg=has_std"],
    deps = [":hashbrown"],
)

rust_library(
    name = "once_cell",
    srcs = glob(["vendor/once_cell-1.10.0/src/**"]),
    crate_features = [
        "alloc",
        "std",
    ],
    edition = "2018",
    visibility = ["//visibility:public"],
)

rust_library(
    name = "os_str_bytes",
    srcs = glob(["vendor/os_str_bytes-6.0.1/src/**"]),
    crate_features = [
        "raw_os_str",
    ],
    edition = "2018",
)

rust_library(
    name = "proc-macro2",
    srcs = glob(["vendor/proc-macro2-1.0.39/src/**"]),
    crate_features = [
        "proc-macro",
        "span-locations",
    ],
    edition = "2018",
    visibility = ["//visibility:public"],
    deps = [
        ":proc-macro2@build",
        ":unicode-ident",
    ],
)

cargo_build_script(
    name = "proc-macro2@build",
    srcs = ["vendor/proc-macro2-1.0.39/build.rs"],
    crate_features = [
        "proc-macro",
        "span-locations",
    ],
    crate_name = "build",
    edition = "2018",
)

rust_library(
    name = "quote",
    srcs = glob(["vendor/quote-1.0.18/src/**"]),
    crate_features = ["proc-macro"],
    edition = "2018",
    visibility = ["//visibility:public"],
    deps = [":proc-macro2"],
)

rust_library(
    name = "scratch",
    srcs = glob(["vendor/scratch-1.0.1/src/**"]),
    edition = "2018",
    rustc_env = {"OUT_DIR": ""},
    visibility = ["//visibility:public"],
)

rust_library(
    name = "syn",
    srcs = glob(["vendor/syn-1.0.95/src/**"]),
    crate_features = [
        "clone-impls",
        "derive",
        "full",
        "parsing",
        "printing",
        "proc-macro",
    ],
    edition = "2018",
    visibility = ["//visibility:public"],
    deps = [
        ":proc-macro2",
        ":quote",
        ":syn@build",
        ":unicode-ident",
    ],
)

cargo_build_script(
    name = "syn@build",
    srcs = ["vendor/syn-1.0.95/build.rs"],
    crate_features = [
        "clone-impls",
        "derive",
        "full",
        "parsing",
        "printing",
        "proc-macro",
    ],
    crate_name = "build",
    edition = "2018",
)

rust_library(
    name = "termcolor",
    srcs = glob(["vendor/termcolor-1.1.3/src/**"]),
    edition = "2018",
)

rust_library(
    name = "textwrap",
    srcs = glob(["vendor/textwrap-0.15.0/src/**"]),
    edition = "2018",
    deps = [":unicode-width"],
)

rust_library(
    name = "unicode-ident",
    srcs = glob(["vendor/unicode-ident-1.0.0/src/**"]),
    edition = "2018",
)

rust_library(
    name = "unicode-width",
    srcs = glob(["vendor/unicode-width-0.1.9/src/**"]),
    edition = "2018",
)
