set(MLIR_BINARY_DIR ${CMAKE_BINARY_DIR})

set(LLVM_TARGET_DEFINITIONS TritonNvidiaGPUOps.td)
mlir_tablegen(Dialect.h.inc -gen-dialect-decls -dialect=ttng)
mlir_tablegen(Dialect.cpp.inc -gen-dialect-defs -dialect=ttng)
mlir_tablegen(Ops.h.inc -gen-op-decls)
mlir_tablegen(Ops.cpp.inc -gen-op-defs)
add_mlir_doc(TritonNvidiaGPUDialect TritonNvidiaGPUDialect dialects/ -gen-dialect-doc -dialect=ttng)
add_mlir_doc(TritonNvidiaGPUOps TritonNvidiaGPUOps dialects/ -gen-op-doc -dialect=ttng)
add_public_tablegen_target(TritonNvidiaGPUTableGen)

include(${PROJECT_SOURCE_DIR}/cmake/AddTableGenFormat.cmake)
add_mlir_tablegen_format(TritonNvidiaGPUTableGen)

set(LLVM_TARGET_DEFINITIONS TritonNvidiaGPUTypes.td)
mlir_tablegen(Types.h.inc -gen-typedef-decls)
mlir_tablegen(Types.cpp.inc -gen-typedef-defs)
add_public_tablegen_target(TritonNvidiaGPUTypesIncGen)

include(${PROJECT_SOURCE_DIR}/cmake/AddTableGenFormat.cmake)
add_mlir_tablegen_format(TritonNvidiaGPUTypesIncGen)

set(LLVM_TARGET_DEFINITIONS TritonNvidiaGPUAttrDefs.td)
mlir_tablegen(TritonNvidiaGPUAttrDefs.h.inc -gen-attrdef-decls)
mlir_tablegen(TritonNvidiaGPUAttrDefs.cpp.inc -gen-attrdef-defs)
mlir_tablegen(OpsEnums.h.inc -gen-enum-decls)
mlir_tablegen(OpsEnums.cpp.inc -gen-enum-defs)
add_public_tablegen_target(TritonNvidiaGPUAttrDefsIncGen)

include(${PROJECT_SOURCE_DIR}/cmake/AddTableGenFormat.cmake)
add_mlir_tablegen_format(TritonNvidiaGPUAttrDefsIncGen)

set(LLVM_TARGET_DEFINITIONS TritonNvidiaGPUOpInterfaces.td)
mlir_tablegen(TritonNvidiaGPUOpInterfaces.h.inc -gen-op-interface-decls)
mlir_tablegen(TritonNvidiaGPUOpInterfaces.cpp.inc -gen-op-interface-defs)
add_public_tablegen_target(TritonNvidiaGPUOpInterfacesIncGen)

include(${PROJECT_SOURCE_DIR}/cmake/AddTableGenFormat.cmake)
add_mlir_tablegen_format(TritonNvidiaGPUOpInterfacesIncGen)
