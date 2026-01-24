set(LLVM_TARGET_DEFINITIONS Passes.td)
mlir_tablegen(Passes.h.inc -gen-pass-decls --name ProtonToProtonGPU)
add_public_tablegen_target(ProtonToProtonGPUIncGen)

include(${PROJECT_SOURCE_DIR}/cmake/AddTableGenFormat.cmake)
add_mlir_tablegen_format(ProtonToProtonGPUIncGen)
