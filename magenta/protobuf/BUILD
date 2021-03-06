# Copyright 2016 Google Inc. All Rights Reserved.
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

# Description:
# Magenta protocol buffers.

package(
    default_visibility = ["//magenta:__subpackages__"],
    features = ["-layering_check"],
)

load("@protobuf//:protobuf.bzl", "cc_proto_library")
load("@protobuf//:protobuf.bzl", "py_proto_library")

# Magenta public API.
py_library(
    name = "protobuf",
    deps = [
        ":generator_py_pb2",
        ":music_py_pb2",
    ],
)

py_proto_library(
    name = "music_py_pb2",
    srcs = ["music.proto"],
    default_runtime = "@protobuf//:protobuf_python",
    protoc = "@protobuf//:protoc",
    srcs_version = "PY2AND3",
)

cc_proto_library(
    name = "music_proto",
    srcs = ["music.proto"],
    default_runtime = "@protobuf//:protobuf",
    protoc = "@protobuf//:protoc",
)

py_proto_library(
    name = "generator_py_pb2",
    srcs = ["generator.proto"],
    default_runtime = "@protobuf//:protobuf_python",
    protoc = "@protobuf//:protoc",
    srcs_version = "PY2AND3",
    deps = [":music_py_pb2"],
)

cc_proto_library(
    name = "generator_proto",
    srcs = ["generator.proto"],
    default_runtime = "@protobuf//:protobuf",
    protoc = "@protobuf//:protoc",
    deps = [":music_proto"],
)
