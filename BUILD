// Zero-mq
[
  { "config": {
    "component": "zeromq",
    "licenses": [ "http://opensource.org/licenses/gpl-3.0.html" ]
  } },

  { "autoconf": {
    "name": "zmq_gen",
    "postinstall": "cp cppzmq/*.hpp $GEN_DIR/include; mv $GEN_DIR/include $GEN_DIR/zeromq",
    "outs": [ "$GEN_DIR/zeromq/zmq.h",
              "$GEN_DIR/zeromq/zmq.hpp",
              "$GEN_DIR/zeromq/zmq_utils.h",
              "$GEN_DIR/lib/libzmq.a"
    ],
    "input_files": [ "Makefile", "cppzmq/*.hpp", "src/*.cpp", "src/*.hpp" ]
  } },

  { "cc_library": {
    "name": "zeromq",
    "cc_headers": [ "$GEN_DIR/zeromq/zmq.h",
                    "$GEN_DIR/zeromq/zmq.hpp",
                    "$GEN_DIR/zeromq/zmq_utils.h"
    ],
    "cc_objects": [ "$GEN_DIR/lib/libzmq.a" ],
    "dependencies": [ ":zmq_gen" ],
    "cc_include_dirs": [ "$GEN_DIR" ],
    "strict_file_mode": false
  } }
]