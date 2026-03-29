files(
    name="test-files-raw",
    sources=["**/*", "!BUILD"],
)

# Tests reference files via (io/file "file-root/sub/index.html").
# relocated_files strips the "tests/" prefix so files appear at "file-root/..." in the sandbox.
relocated_files(
    name="test-files",
    files_targets=[":test-files-raw"],
    src="tests",
    dest="",
)
