set(LLVM_TARGET_DEFINITIONS Passes.td)
mlir_tablegen(Passes.h.inc -gen-pass-decls -name TritonNvidiaGPU)
add_public_tablegen_target(TritonNvidiaGPUTransformsIncGen)

include(${PROJECT_SOURCE_DIR}/cmake/AddTableGenFormat.cmake)
add_mlir_tablegen_format(TritonNvidiaGPUTransformsIncGen)
