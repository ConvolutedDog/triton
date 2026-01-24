set(LLVM_TARGET_DEFINITIONS Passes.td)
mlir_tablegen(Passes.h.inc -gen-pass-decls -name TritonAMDGPU)
add_public_tablegen_target(TritonAMDGPUTransformsIncGen)

include(${PROJECT_SOURCE_DIR}/cmake/AddTableGenFormat.cmake)
add_mlir_tablegen_format(TritonAMDGPUTransformsIncGen)
