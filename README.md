1)

./vcpkg create pb https://codeload.github.com/protocolbuffers/protobuf/zip/v21.12 pb21.12.zip


2) port/pb/pb.json


vcpkg_download_distfile(ARCHIVE
    URLS "https://codeload.github.com/protocolbuffers/protobuf/zip/v21.12"
    FILENAME "pb21.12.zip"
    SHA512 838b71b385eb8efdec7f3b67dd2809ff7eda4b773333f648d325a65451839a90f21eb05219d100f2d5139d47738488b3f0060c3499c3a5f24e563b69d90dd726
)

vcpkg_extract_source_archive_ex(
    OUT_SOURCE_PATH SOURCE_PATH
    ARCHIVE ${ARCHIVE}
    # (Optional) A friendly name to use instead of the filename of the archive (e.g.: a version number or tag).
    # REF 1.0.0
    # (Optional) Read the docs for how to generate patches at:
    # https://github.com/Microsoft/vcpkg/blob/master/docs/examples/patching.md
    PATCHES
        fix-static-build.patch
)