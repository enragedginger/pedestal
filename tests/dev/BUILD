# Dev utilities - the custom test runner is replaced by Pants' own test runner,
# but these are still useful for REPL development.
clojure_sources(
    name="dev",
    resolve="pedestal",
    sources=["**/*.clj"],
)

# Classpath resources under public/ - used by tests via ::service/resource-path "public"
resources(
    name="public-resources",
    sources=["public/**/*"],
)
