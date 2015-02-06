set(LLVM_TARGET_DEFINITIONS PJ32.td)

tablegen(LLVM PJ32GenRegisterInfo.inc -gen-register-info)
tablegen(LLVM PJ32GenInstrInfo.inc -gen-instr-info)
tablegen(LLVM PJ32GenDisassemblerTables.inc -gen-disassembler)
tablegen(LLVM PJ32GenCodeEmitter.inc -gen-emitter)
tablegen(LLVM PJ32GenMCCodeEmitter.inc -gen-emitter -mc-emitter)
tablegen(LLVM PJ32GenAsmWriter.inc -gen-asm-writer)
tablegen(LLVM PJ32GenDAGISel.inc -gen-dag-isel)
tablegen(LLVM PJ32GenFastISel.inc -gen-fast-isel)
tablegen(LLVM PJ32GenCallingConv.inc -gen-callingconv)
tablegen(LLVM PJ32GenSubtargetInfo.inc -gen-subtarget)
tablegen(LLVM PJ32GenAsmMatcher.inc -gen-asm-matcher)
tablegen(LLVM PJ32GenMCPseudoLowering.inc -gen-pseudo-lowering)
add_public_tablegen_target(PJ32CommonTableGen)

add_llvm_arget(PJ32CodeGen
	PJ32AsmPrinter.cpp
	PJ32CodeEmitter.cpp
	PJ32FastISel.cpp
	PJ32InstrInfo.cpp
	PJ32RegisterInfo.cpp
	)

add_subdirectory(AsmParser)
add_subdirectory(Disassembler)
add_subdirectory(InstPrinter)
add_subdirectory(MCTargetDesc)
add_subdirectory(TargetInfo)
