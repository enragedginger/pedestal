# Third-party dependencies for all Pedestal modules.
# Extracted from module deps.edn files.

# === Core Clojure ===

jvm_artifact(
    name="clojure",
    group="org.clojure",
    artifact="clojure",
    version="1.12.4",
    resolve="pedestal",
)

jvm_artifact(
    name="core-async",
    group="org.clojure",
    artifact="core.async",
    version="1.8.741",
    resolve="pedestal",
)

jvm_artifact(
    name="core-match",
    group="org.clojure",
    artifact="core.match",
    version="1.1.1",
    resolve="pedestal",
    exclusions=[
        jvm_exclude(group="org.clojure", artifact="clojurescript"),
    ],
)

jvm_artifact(
    name="tools-reader",
    group="org.clojure",
    artifact="tools.reader",
    version="1.6.0",
    resolve="pedestal",
)

# === Utility Libraries ===

jvm_artifact(
    name="pretty",
    group="org.clj-commons",
    artifact="pretty",
    version="3.6.8",
    resolve="pedestal",
)

jvm_artifact(
    name="medley",
    group="medley",
    artifact="medley",
    version="1.4.0",
    resolve="pedestal",
)

# === Logging ===

jvm_artifact(
    name="slf4j-api",
    group="org.slf4j",
    artifact="slf4j-api",
    version="2.0.17",
    resolve="pedestal",
)

jvm_artifact(
    name="logback-classic",
    group="ch.qos.logback",
    artifact="logback-classic",
    version="1.5.32",
    resolve="pedestal",
)

# === Telemetry ===

jvm_artifact(
    name="opentelemetry-api",
    group="io.opentelemetry",
    artifact="opentelemetry-api",
    version="1.59.0",
    resolve="pedestal",
)

# === Service Layer ===

jvm_artifact(
    name="ring-core",
    group="ring",
    artifact="ring-core",
    version="1.15.3",
    resolve="pedestal",
)

jvm_artifact(
    name="charred",
    group="com.cnuernber",
    artifact="charred",
    version="1.038",
    resolve="pedestal",
)

jvm_artifact(
    name="transit-clj",
    group="com.cognitect",
    artifact="transit-clj",
    version="1.1.347",
    resolve="pedestal",
)

jvm_artifact(
    name="commons-codec",
    group="commons-codec",
    artifact="commons-codec",
    version="1.21.0",
    resolve="pedestal",
)

jvm_artifact(
    name="crypto-random",
    group="crypto-random",
    artifact="crypto-random",
    version="1.2.1",
    resolve="pedestal",
)

jvm_artifact(
    name="crypto-equality",
    group="crypto-equality",
    artifact="crypto-equality",
    version="1.0.1",
    resolve="pedestal",
)

# === Jakarta APIs (for servlet Java compilation) ===

jvm_artifact(
    name="jakarta-servlet-api",
    group="jakarta.servlet",
    artifact="jakarta.servlet-api",
    version="6.1.0",
    resolve="pedestal",
)

jvm_artifact(
    name="jakarta-websocket-api",
    group="jakarta.websocket",
    artifact="jakarta.websocket-api",
    version="2.2.0",
    resolve="pedestal",
)

jvm_artifact(
    name="jakarta-websocket-client-api",
    group="jakarta.websocket",
    artifact="jakarta.websocket-client-api",
    version="2.2.0",
    resolve="pedestal",
)

# === Jetty 12 ===

jvm_artifact(
    name="jetty-server",
    group="org.eclipse.jetty",
    artifact="jetty-server",
    version="12.0.32",
    resolve="pedestal",
)

jvm_artifact(
    name="jetty-http2-server",
    group="org.eclipse.jetty.http2",
    artifact="jetty-http2-server",
    version="12.0.32",
    resolve="pedestal",
)

jvm_artifact(
    name="jetty-ee10-servlet",
    group="org.eclipse.jetty.ee10",
    artifact="jetty-ee10-servlet",
    version="12.0.32",
    resolve="pedestal",
)

jvm_artifact(
    name="jetty-alpn-server",
    group="org.eclipse.jetty",
    artifact="jetty-alpn-server",
    version="12.0.32",
    resolve="pedestal",
)

jvm_artifact(
    name="jetty-ee10-websocket-jakarta-server",
    group="org.eclipse.jetty.ee10.websocket",
    artifact="jetty-ee10-websocket-jakarta-server",
    version="12.0.32",
    resolve="pedestal",
)

# === Http-Kit ===

jvm_artifact(
    name="http-kit",
    group="http-kit",
    artifact="http-kit",
    version="2.8.1",
    resolve="pedestal",
)

# === Test Dependencies ===

jvm_artifact(
    name="matcher-combinators",
    group="nubank",
    artifact="matcher-combinators",
    version="3.10.0",
    resolve="pedestal",
)

jvm_artifact(
    name="mockfn",
    group="nubank",
    artifact="mockfn",
    version="0.7.0",
    resolve="pedestal",
)

jvm_artifact(
    name="expound",
    group="expound",
    artifact="expound",
    version="0.9.0",
    resolve="pedestal",
)

jvm_artifact(
    name="clj-http",
    group="clj-http",
    artifact="clj-http",
    version="3.13.1",
    resolve="pedestal",
)

jvm_artifact(
    name="hato",
    group="hato",
    artifact="hato",
    version="1.0.0",
    resolve="pedestal",
)

jvm_artifact(
    name="component",
    group="com.stuartsierra",
    artifact="component",
    version="1.2.0",
    resolve="pedestal",
)

jvm_artifact(
    name="trace",
    group="io.github.hlship",
    artifact="trace",
    version="1.4",
    resolve="pedestal",
)

jvm_artifact(
    name="test-reporting",
    group="com.walmartlabs",
    artifact="test-reporting",
    version="1.2",
    resolve="pedestal",
)

jvm_artifact(
    name="clj-async-profiler",
    group="com.clojure-goes-fast",
    artifact="clj-async-profiler",
    version="1.7.0",
    resolve="pedestal",
)

jvm_artifact(
    name="sse-handler",
    group="cloud.prefab",
    artifact="sse-handler",
    version="1.0.1",
    resolve="pedestal",
)

jvm_artifact(
    name="clj-reload",
    group="io.github.tonsky",
    artifact="clj-reload",
    version="1.0.0",
    resolve="pedestal",
)

jvm_artifact(
    name="criterium",
    group="criterium",
    artifact="criterium",
    version="0.4.6",
    resolve="pedestal",
)

# Note: The deprecated jetty-servlets test (jetty-util-test) uses Jetty 11.
# Included for completeness but this test may be dropped.
jvm_artifact(
    name="jetty-servlets",
    group="org.eclipse.jetty",
    artifact="jetty-servlets",
    version="11.0.26",
    resolve="pedestal",
)
