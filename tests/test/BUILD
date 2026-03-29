# Test helper/utility files - NOT tests, but needed on the test classpath.
clojure_sources(
    name="test-support",
    resolve="pedestal",
    sources=[
        "io/pedestal/test_common.clj",
        "io/pedestal/async_events.clj",
        "user.clj",
    ],
    dependencies=[
        # Dynamic requires in test_common.clj instrument-specs-fixture
        "//servlet/src:lib",
        "//jetty/src:lib",
        "//http-kit/src:lib",
    ],
)

# Actual test files.
# Uses **/*_test.clj which captures all tests (including test_test.clj)
# but naturally excludes test_common.clj (doesn't end with _test).
clojure_tests(
    name="tests",
    resolve="pedestal",
    sources=["**/*_test.clj"],
    dependencies=[
        # Dynamic dependencies resolved at runtime via read-config :default-value.
        # Pants can't infer these from :require forms.
        "//service/src:lib",
        "//telemetry/src:lib",
        # Test data files referenced via (io/file "file-root/...")
        "tests/file-root:test-files",
        # Test data files inside tests/test/ referenced via filesystem paths like
        # "test/io/pedestal/http/keystore.jks" and "test/io/pedestal/public/..."
        ":test-data-files",
        # Jetty DoSFilter used by jetty_util_test
        "//3rdparty/jvm:jetty-servlets",
        # Classpath resources in tests/dev/public/ (test.html, test.js, test.txt)
        "//tests/dev:public-resources",
        # Classpath resources for io/pedestal/public/ (used by resource-serving tests)
        ":test-classpath-resources",
    ],
)

# Non-source test data files (keystore, HTML, etc.) referenced via filesystem paths.
# Tests expect these at "test/io/pedestal/..." (tests/ prefix stripped, test/ prefix kept).
files(
    name="test-data-raw",
    sources=[
        "io/pedestal/http/keystore.jks",
        "io/pedestal/public/**/*",
    ],
)

relocated_files(
    name="test-data-files",
    files_targets=[":test-data-raw"],
    src="tests/test",
    dest="test",
)

# Same public/ files as classpath resources for tests using ::service/resource-root.
# Source root tests/test/ is stripped, so these appear at io/pedestal/public/... on classpath.
resources(
    name="test-classpath-resources",
    sources=["io/pedestal/public/**/*"],
)
