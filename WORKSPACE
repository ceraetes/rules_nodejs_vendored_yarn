# Copyright 2019 The Bazel Authors. All rights reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_nodejs",
    sha256 = "aa0b0a71afd4e1f203b7092c3284a6606a5bfac77e0bd31f071b37bcac0f7cf3",
    urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/2.0.0-rc.1/rules_nodejs-2.0.0-rc.1.tar.gz"],
)

http_archive(
    name = "vendored_node_10_12_0",
    build_file_content = """exports_files(["node-v10.12.0-win-x64/bin/node"])""",
    # sha256 = "4eba2e9a6db95745b769915d58e57df6ca6724ec1f023f76556fce30ceca2367",
    urls = ["https://nodejs.org/dist/v10.12.0/node-v10.12.0-win-x64.zip"],
)

http_archive(
    name = "vendored_yarn_1_10_0",
    build_file_content = """exports_files(["vendored_yarn_1_10_0/yarn-v1.10.0/bin/yarn.js"])""",
    urls = ["https://github.com/yarnpkg/yarn/releases/download/v1.10.0/yarn-v1.10.0.tar.gz"],
)

load("@build_bazel_rules_nodejs//:index.bzl", "node_repositories", "yarn_install")

node_repositories(
    node_version = "10.12.0",
    vendored_node = "@vendored_node_10_12_0//:node-v10.12.0-win-x64",
    vendored_yarn = "@vendored_yarn_1_10_0//:yarn-v1.10.0",
  package_json = ["//:package.json"]
)
