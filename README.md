# x86 Encoding Data (Intel)
This repository contains a machine-readable (CSV) representation of the instruction encoding tables contained in [Intel® 64 and IA-32 architectures software developer's manual volume 2](https://software.intel.com/en-us/articles/intel-sdm).

# Format
Instructions are represented as rows in a UTF-8 encoded CSV file.

Columns correspond to the fields in the Intel instruction set reference. See "3.1 INTERPRETING THE INSTRUCTION REFERENCE PAGES" in the reference manual for a detailed description. Columns are as follows:

1. __Instruction__: Describes the accepted operands and instruction semantics. Corresponds to the instruction column in the Intel instruction set reference.
2. __Opcode__: The byte-wise encoding of the instruction. Corresponds to the opcode column in the Intel instruction set reference.
3. __64-bit Mode Support__: Indicates whether the encoding is valid in 64-bit mode. Corresponds to either the first value in the "64/32 -bit Mode Support" or the the "64-bit Mode" column in the Intel instruction set reference.
4. __32-bit/Legacy Support__: Indicates whether the encoding is valid in 32 and 16-bit mode. Corresponds to either the second value in the "64/32 -bit Mode Support" or the the "Compat/Leg Mode" column in the Intel instruction set reference.
5. __Feature Flags__: CPUID feature flags required for the instruction. Corresponds to the "CPUID Feature Flag" field in the Intel instruction set reference.
6. __Operand 1__: The encoding of the first operand.
7. __Operand 2__: The encoding of the second operand.
8. __Operand 3__: The encoding of the third operand.
9. __Operand 4__: The encoding of the fourth operand.
10. __Tuple Type__: The tuple type used for compressed displacement encoding.

# A Note on Excel Compatability
The csv document is encoded using UTF-8. Excel does not properly detect this, and as such does not display certain symbols correctly. Adding byte-order marks fixes this, but were excluded for easier machine parsing.