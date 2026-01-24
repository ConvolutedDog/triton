set(LLVM_TARGET_DEFINITIONS Passes.td)
mlir_tablegen(Passes.h.inc -gen-pass-decls --name ProtonGPUToLLVM)
add_public_tablegen_target(ProtonGPUConversionPassIncGen)

add_subdirectory(ProtonNvidiaGPUToLLVM)
add_subdirectory(ProtonAMDGPUToLLVM)

include(${PROJECT_SOURCE_DIR}/cmake/AddTableGenFormat.cmake)
add_mlir_tablegen_format(ProtonGPUConversionPassIncGen)
