// Zero-mq
[
  { "config": {
    "component": "zeromq",
    "component_root": "$GEN_DIR/include"
  } },

  { "autoconf": {
    "name": "zmq_gen",
    "postinstall": "cp cppzmq/*.hpp $GEN_DIR/include",
    "outs": [ "$GEN_DIR/include/zmq.h",
              "$GEN_DIR/include/zmq.hpp",
              "$GEN_DIR/include/zmq_utils.h",
              "$GEN_DIR/lib/libzmq.a"
    ],
    "input_files": [ "Makefile", "cppzmq/*.hpp", "src/*.cpp", "src/*.hpp" ]
  } },

  { "cc_library": {
    "name": "zeromq",
    "cc_headers": [ "$GEN_DIR/include/zmq.h",
                    "$GEN_DIR/include/zmq.hpp",
                    "$GEN_DIR/include/zmq_utils.h"
    ],
    "cc_objects": [ "$GEN_DIR/lib/libzmq.a" ],
    "dependencies": [ ":zmq_gen" ],
    "strict_file_mode": false
  } }
]