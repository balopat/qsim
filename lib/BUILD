package(default_visibility = ["//visibility:public"])

##### Aggregate libraries #####

# Full qsim library
cc_library(
    name = "qsim_lib",
    hdrs = [
        "bitstring.h",
        "circuit_qsim_parser.h",
        "circuit.h",
        "formux.h",
        "fuser_basic.h",
        "fuser.h",
        "gate.h",
        "gate_appl.h",
        "gates_cirq.h",
        "gates_qsim.h",
        "hybrid.h",
        "io_file.h",
        "io.h",
        "matrix.h",
        "parfor.h",
        "run_qsim.h",
        "run_qsimh.h",
        "seqfor.h",
        "simmux.h",
        "simulator_avx.h",
        "simulator_basic.h",
        "simulator_sse.h",
        "statespace_avx.h",
        "statespace_basic.h",
        "statespace_sse.h",
        "statespace.h",
        "umux.h",
        "unitaryspace.h",
        "unitaryspace_basic.h",
        "unitary_calculator_basic.h",
        "util.h",
    ],
)

# Library to run qsim with qsim circuit parser and parallel `for`
cc_library(
    name = "run_qsim_lib",
    hdrs = [
        "circuit.h",
        "circuit_qsim_parser.h",
        "formux.h",
        "fuser.h",
        "fuser_basic.h",
        "gate.h",
        "gate_appl.h",
        "gates_qsim.h",
        "io.h",
        "io_file.h",
        "matrix.h",
        "parfor.h",
        "run_qsim.h",
        "seqfor.h",
        "simmux.h",
        "simulator_avx.h",
        "simulator_basic.h",
        "simulator_sse.h",
        "statespace.h",
        "statespace_avx.h",
        "statespace_basic.h",
        "statespace_sse.h",
        "umux.h",
        "unitaryspace.h",
        "unitaryspace_basic.h",
        "unitary_calculator_basic.h",
        "util.h",
    ],
)

# Library to run qsimh with qsim circuit parser and parallel `for`
cc_library(
    name = "run_qsimh_lib",
    hdrs = [
        "circuit.h",
        "circuit_qsim_parser.h",
        "formux.h",
        "fuser.h",
        "fuser_basic.h",
        "gate.h",
        "gate_appl.h",
        "gates_qsim.h",
        "hybrid.h",
        "io.h",
        "io_file.h",
        "matrix.h",
        "parfor.h",
        "run_qsimh.h",
        "seqfor.h",
        "simmux.h",
        "simulator_avx.h",
        "simulator_basic.h",
        "simulator_sse.h",
        "statespace.h",
        "statespace_avx.h",
        "statespace_basic.h",
        "statespace_sse.h",
        "util.h",
    ],
)

##### Basic libraries #####

### Utility libraries ###

# Bitstring parser
cc_library(
    name = "bitstring",
    hdrs = ["bitstring.h"],
)

cc_library(
    name = "matrix",
    hdrs = ["matrix.h"],
)

cc_library(
    name = "util",
    hdrs = ["util.h"],
)

### Input/output libraries ###

cc_library(
    name = "io",
    hdrs = ["io.h"],
)

cc_library(
    name = "io_file",
    hdrs = ["io_file.h"],
    deps = [":io"],
)

### Parallel and sequential `for` libraries ###

# OpenMP-based parallelization
cc_library(
    name = "parfor",
    hdrs = ["parfor.h"],
    copts = ["-fopenmp"],
)

cc_library(
    name = "seqfor",
    hdrs = ["seqfor.h"],
)

# Both parallelism control paths with multiplexer
cc_library(
    name = "formux",
    hdrs = ["formux.h"],
    deps = [
        ":parfor",
        ":seqfor",
    ],
)

### Gate libraries ###

cc_library(
    name = "gate",
    hdrs = ["gate.h"],
    deps = [":matrix"],
)

cc_library(
    name = "gate_appl",
    hdrs = ["gate_appl.h"],
    deps = [":matrix"],
)

cc_library(
    name = "gates_cirq",
    hdrs = ["gates_cirq.h"],
    deps = [":gate"],
)

cc_library(
    name = "gates_qsim",
    hdrs = ["gates_qsim.h"],
    deps = [":gate"],
)

### Circuit libraries ###

cc_library(
    name = "circuit",
    hdrs = ["circuit.h"],
)

# qsim circuit parser
cc_library(
    name = "circuit_qsim_parser",
    hdrs = ["circuit_qsim_parser.h"],
    deps = [
        ":circuit",
        ":gates_qsim",
    ],
)

### Fuser libraries ###

cc_library(
    name = "fuser",
    hdrs = ["fuser.h"],
)

cc_library(
    name = "fuser_basic",
    hdrs = ["fuser_basic.h"],
    deps = [
        ":fuser",
        ":gate",
    ],
)

### Helper libraries to run qsim and qsimh ###

cc_library(
    name = "run_qsim",
    hdrs = ["run_qsim.h"],
    deps = [
        ":gate",
        ":gate_appl",
        ":util",
    ],
)

cc_library(
    name = "run_qsimh",
    hdrs = ["run_qsimh.h"],
    deps = [
        ":hybrid",
        ":util",
    ],
)

### Statespace libraries ###

cc_library(
    name = "statespace",
    hdrs = ["statespace.h"],
    deps = [":util"],
)

cc_library(
    name = "statespace_avx",
    hdrs = ["statespace_avx.h"],
    deps = [
        ":statespace",
        ":util",
    ],
)

cc_library(
    name = "statespace_basic",
    hdrs = ["statespace_basic.h"],
    deps = [
        ":statespace",
        ":util",
    ],
)

cc_library(
    name = "statespace_sse",
    hdrs = ["statespace_sse.h"],
    deps = [
        ":statespace",
        ":util",
    ],
)

### Simulator libraries ###

cc_library(
    name = "simulator_avx",
    hdrs = ["simulator_avx.h"],
    deps = [":statespace_avx"],
)

cc_library(
    name = "simulator_basic",
    hdrs = ["simulator_basic.h"],
    deps = [":statespace_basic"],
)

cc_library(
    name = "simulator_sse",
    hdrs = ["simulator_sse.h"],
    deps = [":statespace_sse"],
)

# All three state-vector simulators with multiplexer
cc_library(
    name = "simulator",
    hdrs = ["simmux.h"],
    deps = [
        ":simulator_avx",
        ":simulator_basic",
        ":simulator_sse",
    ],
)

# Hybrid simulator
cc_library(
    name = "hybrid",
    hdrs = ["hybrid.h"],
    deps = [
        ":gate",
        ":gate_appl",
    ],
)

### UnitarySpace libraries ###

cc_library(
    name = "unitaryspace",
    hdrs = ["unitaryspace.h"],
    deps = [":util"],
)

cc_library(
    name = "unitaryspace_basic",
    hdrs = ["unitaryspace_basic.h"],
    deps = [":unitaryspace"],
)

### Unitary calculator libraries ###

cc_library(
    name = "unitary_calculator_basic",
    hdrs = ["unitary_calculator_basic.h"],
    deps = [":unitaryspace_basic"],
)

### Unitary mux header ###

cc_library(
    name = "umux",
    hdrs = ["umux.h"],
    deps = [":unitary_calculator_basic"]
)
