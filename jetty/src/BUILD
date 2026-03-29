clojure_sources(
    name="lib",
    resolve="pedestal",
    sources=["**/*.clj"],
    dependencies=[
        # Jetty ALPN not auto-inferred via Clojure :import
        "//3rdparty/jvm:jetty-alpn-server",
        "//3rdparty/jvm:jetty-server",
    ],
)
