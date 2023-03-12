---
description: >-
  "llvm-defaults" is a collection of tools and libraries that provide a complete
  development environment for LLVM-based projects on Debian systems.
---

# 📦 llvm-defaults

LLVM is a collection of modular and reusable compiler and toolchain technologies. llvm-defaults is a tool that simplifies the installation and management of LLVM packages on Debian-based Linux distributions. It provides a meta-package that depends on the appropriate version of LLVM and its associated libraries and tools. By using llvm-defaults, users can easily install and maintain LLVM packages, including Clang, a popular C++ compiler, and other development tools that rely on LLVM. The tool also ensures that the correct dependencies are installed and that upgrades are smooth and error-free. LLVM and llvm-defaults are widely used in the development of operating systems, programming languages, and other software that require efficient and reliable compilation and optimization.

### Packages and Binaries:

#### clang <a href="#clang" id="clang"></a>

Clang project is a C, C++, Objective C and Objective C++ front-end for the LLVM compiler. Its goal is to offer a replacement to the GNU Compiler Collection (GCC).

Clang implements all of the ISO C++ 1998, 11 and 14 standards and also provides most of the support of C++17.

This is a dependency package providing the default clang compiler.

**Installed size:** `19 KB`\
**How to install:** `sudo apt install clang`

<details>

<summary>Dependencies:</summary>

* clang-14

</details>

**asan\_symbolize**

```
:~# asan_symbolize -h
usage: asan_symbolize [-h] [-d] [-c CROSS_COMPILE] [-l LOGFILE]
                      [--force-system-symbolizer] [--log-dest LOG_DEST]
                      [--log-level {debug,info,warning,error,critical}]
                      [-p PLUGINS [PLUGINS ...]] [--module-map MODULE_MAP]
                      [--skip-uuid-validation] [-s SYSROOT]
                      [path_to_cut ...]

ASan symbolization script

positional arguments:
  path_to_cut           pattern to be cut from the result file path

options:
  -h, --help            show this help message and exit
  -d, --demangle        demangle function names
  -c CROSS_COMPILE      set prefix for binutils
  -l LOGFILE, --logfile LOGFILE
                        set log file name to parse, default is stdin
  --force-system-symbolizer
                        don't use llvm-symbolizer
  --log-dest LOG_DEST   Destination path for script logging (default stderr).
  --log-level {debug,info,warning,error,critical}
                        Log level for script (default: info).
  -p PLUGINS [PLUGINS ...], --plugins PLUGINS [PLUGINS ...]
                        Load plug-in
  --module-map MODULE_MAP
                        Path to text file containing module mapoutput. See
                        print_module_map ASan option.
  --skip-uuid-validation
                        Skips validating UUID of modules using otool.
  -s SYSROOT            set path to sysroot for sanitized binaries

Example of use:
  asan_symbolize.py -c "$HOME/opt/cross/bin/arm-linux-gnueabi-" -s "$HOME/SymbolFiles" < asan.log

PLUGINS

This script provides a way for external plug-ins to hook into the behaviour of
various parts of this script (see `--plugins`). This is useful for situations
where it is necessary to handle site-specific quirks (e.g. binaries with debug
symbols only accessible via a remote service) without having to modify the
script itself.
```

***

**clang**

The Clang C, C++, and Objective-C compiler

```
:~# clang --help
OVERVIEW: clang LLVM compiler

USAGE: clang [options] file...

OPTIONS:
  -###                    Print (but do not run) the commands to run for this compilation
  --amdgpu-arch-tool=<value>
                          Tool used for detecting AMD GPU arch in the system.
  --analyzer-output <value>
                          Static analyzer report output format (html|plist|plist-multi-file|plist-html|sarif|sarif-html|text).
  --analyze               Run the static analyzer
  -arcmt-migrate-emit-errors
                          Emit ARC errors even if the migrator can fix them
  -arcmt-migrate-report-output <value>
                          Output path for the plist report
  -B <prefix>             Search $prefix$file for executables, libraries, and data files. If $prefix is a directory, search $prefix/$file
  -b <arg>                Pass -b <arg> to the linker on AIX (only).
  -CC                     Include comments from within macros in preprocessed output
  -cl-denorms-are-zero    OpenCL only. Allow denormals to be flushed to zero.
  -cl-fast-relaxed-math   OpenCL only. Sets -cl-finite-math-only and -cl-unsafe-math-optimizations, and defines __FAST_RELAXED_MATH__.
  -cl-finite-math-only    OpenCL only. Allow floating-point optimizations that assume arguments and results are not NaNs or +-Inf.
  -cl-fp32-correctly-rounded-divide-sqrt
                          OpenCL only. Specify that single precision floating-point divide and sqrt used in the program source are correctly rounded.
  -cl-kernel-arg-info     OpenCL only. Generate kernel argument metadata.
  -cl-mad-enable          OpenCL only. Allow use of less precise MAD computations in the generated binary.
  -cl-no-signed-zeros     OpenCL only. Allow use of less precise no signed zeros computations in the generated binary.
  -cl-no-stdinc           OpenCL only. Disables all standard includes containing non-native compiler types and functions.
  -cl-opt-disable         OpenCL only. This option disables all optimizations. By default optimizations are enabled.
  -cl-single-precision-constant
                          OpenCL only. Treat double precision floating-point constant as single precision constant.
  -cl-std=<value>         OpenCL language standard to compile for.
  -cl-strict-aliasing     OpenCL only. This option is added for compatibility with OpenCL 1.0.
  -cl-uniform-work-group-size
                          OpenCL only. Defines that the global work-size be a multiple of the work-group size specified to clEnqueueNDRangeKernel
  -cl-unsafe-math-optimizations
                          OpenCL only. Allow unsafe floating-point optimizations.  Also implies -cl-no-signed-zeros and -cl-mad-enable.
  --config <value>        Specifies configuration file
  --cuda-compile-host-device
                          Compile CUDA code for both host and device (default).  Has no effect on non-CUDA compilations.
  --cuda-device-only      Compile CUDA code for device only
  --cuda-host-only        Compile CUDA code for host only.  Has no effect on non-CUDA compilations.
  --cuda-include-ptx=<value>
                          Include PTX for the following GPU architecture (e.g. sm_35) or 'all'. May be specified more than once.
  --cuda-noopt-device-debug
                          Enable device-side debug info generation. Disables ptxas optimizations.
  --cuda-path-ignore-env  Ignore environment variables to detect CUDA installation
  --cuda-path=<value>     CUDA installation path
  -cuid=<value>           An ID for compilation unit, which should be the same for the same compilation unit but different for different compilation units. It is used to externalize device-side static variables for single source offloading languages CUDA and HIP so that they can be accessed by the host code of the same compilation unit.
  -cxx-isystem <directory>
                          Add directory to the C++ SYSTEM include search path
  -C                      Include comments in preprocessed output
  -c                      Only run preprocess, compile, and assemble steps
  -dD                     Print macro definitions in -E mode in addition to normal output
  -dependency-dot <value> Filename to write DOT-formatted header dependencies to
  -dependency-file <value>
                          Filename (or -) to write dependency output to
  -dI                     Print include directives in -E mode in addition to normal output
  -dM                     Print macro definitions in -E mode instead of normal output
  -dsym-dir <dir>         Directory to output dSYM's (if any) to
  -D <macro>=<value>      Define <macro> to <value> (or 1 if <value> omitted)
  -emit-ast               Emit Clang AST files for source inputs
  -emit-interface-stubs   Generate Interface Stub Files.
  -emit-llvm              Use the LLVM representation for assembler and object files
  -emit-merged-ifs        Generate Interface Stub Files, emit merged text not binary.
  --emit-static-lib       Enable linker job to emit a static library.
  -enable-trivial-auto-var-init-zero-knowing-it-will-be-removed-from-clang
                          Trivial automatic variable initialization to zero is only here for benchmarks, it'll eventually be removed, and I'm OK with that because I'm only using it to benchmark
  --end-no-unused-arguments
                          Start emitting warnings for unused driver arguments
  -extract-api            Extract API information
  -E                      Only run the preprocessor
  -faapcs-bitfield-load   Follows the AAPCS standard that all volatile bit-field write generates at least one load. (ARM only).
  -faapcs-bitfield-width  Follow the AAPCS standard requirement stating that volatile bit-field width is dictated by the field container type. (ARM only).
  -faddrsig               Emit an address-significance table
  -falign-loops=<N>       N must be a power of two. Align loops to the boundary
  -faligned-allocation    Enable C++17 aligned allocation functions
  -fallow-editor-placeholders
                          Treat editor placeholders as valid source code
  -faltivec-src-compat=<value>
                          Source-level compatibility for Altivec vectors (for PowerPC targets). This includes results of vector comparison (scalar for 'xl', vector for 'gcc') as well as behavior when initializing with a scalar (splatting for 'xl', element zero only for 'gcc'). For 'mixed', the compatibility is as 'gcc' for 'vector bool/vector pixel' and as 'xl' for other types. Current default is 'mixed'.
  -fansi-escape-codes     Use ANSI escape codes for diagnostics
  -fapple-kext            Use Apple's kernel extensions ABI
  -fapple-link-rtlib      Force linking the clang builtins runtime library
  -fapple-pragma-pack     Enable Apple gcc-compatible #pragma pack handling
  -fapplication-extension Restrict code to those available for App Extensions
  -fapprox-func           Allow certain math function calls to be replaced with an approximately equivalent calculation
  -fasync-exceptions      Enable EH Asynchronous exceptions
  -fbasic-block-sections=<value>
                          Place each function's basic blocks in unique sections (ELF Only) : all | labels | none | list=<file>
  -fbinutils-version=<major.minor>
                          Produced object files can use all ELF features supported by this binutils version and newer. If -fno-integrated-as is specified, the generated assembly will consider GNU as support. 'none' means that all ELF features can be used, regardless of binutils support. Defaults to 2.26.
  -fblocks                Enable the 'blocks' language feature
  -fborland-extensions    Accept non-standard constructs supported by the Borland compiler
  -fbuild-session-file=<file>
                          Use the last modification time of <file> as the build session timestamp
  -fbuild-session-timestamp=<time since Epoch in seconds>
                          Time when the current build session started
  -fbuiltin-module-map    Load the clang builtins module map file.
  -fc++-abi=<value>       C++ ABI to use. This will override the target C++ ABI.
  -fcall-saved-x10        Make the x10 register call-saved (AArch64 only)
  -fcall-saved-x11        Make the x11 register call-saved (AArch64 only)
  -fcall-saved-x12        Make the x12 register call-saved (AArch64 only)
  -fcall-saved-x13        Make the x13 register call-saved (AArch64 only)
  -fcall-saved-x14        Make the x14 register call-saved (AArch64 only)
  -fcall-saved-x15        Make the x15 register call-saved (AArch64 only)
  -fcall-saved-x18        Make the x18 register call-saved (AArch64 only)
  -fcall-saved-x8         Make the x8 register call-saved (AArch64 only)
  -fcall-saved-x9         Make the x9 register call-saved (AArch64 only)
  -fcf-protection=<value> Instrument control-flow architecture protection. Options: return, branch, full, none.
  -fcf-protection         Enable cf-protection in 'full' mode
  -fchar8_t               Enable C++ builtin type char8_t
  -fclang-abi-compat=<version>
                          Attempt to match the ABI of Clang <version>
  -fcolor-diagnostics     Enable colors in diagnostics
  -fcomment-block-commands=<arg>
                          Treat each comma separated argument in <arg> as a documentation comment block command
  -fcommon                Place uninitialized global variables in a common block
  -fcomplete-member-pointers
                          Require member pointer base types to be complete if they would be significant under the Microsoft ABI
  -fconvergent-functions  Assume functions may be convergent
  -fcoroutines-ts         Enable support for the C++ Coroutines TS
  -fcoverage-compilation-dir=<value>
                          The compilation directory to embed in the coverage mapping.
  -fcoverage-mapping      Generate coverage mapping to enable code coverage analysis
  -fcoverage-prefix-map=<value>
                          remap file source paths in coverage mapping
  -fcrash-diagnostics-dir=<dir>
                          Put crash-report files in <dir>
  -fcs-profile-generate=<directory>
                          Generate instrumented code to collect context sensitive execution counts into <directory>/default.profraw (overridden by LLVM_PROFILE_FILE env var)
  -fcs-profile-generate   Generate instrumented code to collect context sensitive execution counts into default.profraw (overridden by LLVM_PROFILE_FILE env var)
  -fcuda-approx-transcendentals
                          Use approximate transcendental functions
  -fcuda-short-ptr        Use 32-bit pointers for accessing const/local/shared address spaces
  -fcxx-exceptions        Enable C++ exceptions
  -fcxx-modules           Enable modules for C++
  -fdata-sections         Place each data in its own section
  -fdebug-compilation-dir=<value>
                          The compilation directory to embed in the debug info
  -fdebug-default-version=<value>
                          Default DWARF version to use, if a -g option caused DWARF debug info to be produced
  -fdebug-info-for-profiling
                          Emit extra debug info to make sample profile more accurate
  -fdebug-macro           Emit macro debug information
  -fdebug-prefix-map=<value>
                          remap file source paths in debug info
  -fdebug-ranges-base-address
                          Use DWARF base address selection entries in .debug_ranges
  -fdebug-types-section   Place debug types in their own section (ELF Only)
  -fdeclspec              Allow __declspec as a keyword
  -fdelayed-template-parsing
                          Parse templated function definitions at the end of the translation unit
  -fdelete-null-pointer-checks
                          Treat usage of null pointers as undefined behavior (default)
  -fdiagnostics-absolute-paths
                          Print absolute paths in diagnostics
  -fdiagnostics-hotness-threshold=<value>
                          Prevent optimization remarks from being output if they do not have at least this profile count. Use 'auto' to apply the threshold from profile summary
  -fdiagnostics-parseable-fixits
                          Print fix-its in machine parseable form
  -fdiagnostics-print-source-range-info
                          Print source range spans in numeric form
  -fdiagnostics-show-hotness
                          Enable profile hotness information in diagnostic line
  -fdiagnostics-show-note-include-stack
                          Display include stacks for diagnostic notes
  -fdiagnostics-show-option
                          Print option name with mappable diagnostics
  -fdiagnostics-show-template-tree
                          Print a template comparison tree for differing templates
  -fdigraphs              Enable alternative token representations '<:', ':>', '<%', '%>', '%:', '%:%:' (default)
  -fdirect-access-external-data
                          Don't use GOT indirection to reference external data symbols
  -fdiscard-value-names   Discard value names in LLVM IR
  -fdollars-in-identifiers
                          Allow '$' in identifiers
  -fdouble-square-bracket-attributes
                          Enable '[[]]' attributes in all C and C++ language modes
  -fdwarf-exceptions      Use DWARF style exceptions
  -feliminate-unused-debug-types
                          Do not emit  debug info for defined but unused types
  -fembed-bitcode-marker  Embed placeholder LLVM IR data as a marker
  -fembed-bitcode=<option>
                          Embed LLVM bitcode (option: off, all, bitcode, marker)
  -fembed-bitcode         Embed LLVM IR bitcode as data
  -fembed-offload-object=<value>
                          Embed Offloading device-side binary into host object file as a section.
  -femit-all-decls        Emit all declarations, even if unused
  -femulated-tls          Use emutls functions to access thread_local variables
  -fenable-matrix         Enable matrix data type and related builtin functions
  -fexceptions            Enable support for exception handling
  -fexperimental-new-constant-interpreter
                          Enable the experimental new constant interpreter
  -fexperimental-relative-c++-abi-vtables
                          Use the experimental C++ class ABI for classes with virtual tables
  -fexperimental-strict-floating-point
                          Enables experimental strict floating point in LLVM.
  -fextend-arguments=<value>
                          Controls how scalar integer arguments are extended in calls to unprototyped and varargs functions
  -ffast-math             Allow aggressive, lossy floating-point optimizations
  -ffile-compilation-dir=<value>
                          The compilation directory to embed in the debug info and coverage mapping.
  -ffile-prefix-map=<value>
                          remap file source paths in debug info, predefined preprocessor macros and __builtin_FILE()
  -ffine-grained-bitfield-accesses
                          Use separate accesses for consecutive bitfield runs with legal widths and alignments.
  -ffinite-loops          Assume all loops are finite.
  -ffixed-a0              Reserve the a0 register (M68k only)
  -ffixed-a1              Reserve the a1 register (M68k only)
  -ffixed-a2              Reserve the a2 register (M68k only)
  -ffixed-a3              Reserve the a3 register (M68k only)
  -ffixed-a4              Reserve the a4 register (M68k only)
  -ffixed-a5              Reserve the a5 register (M68k only)
  -ffixed-a6              Reserve the a6 register (M68k only)
  -ffixed-d0              Reserve the d0 register (M68k only)
  -ffixed-d1              Reserve the d1 register (M68k only)
  -ffixed-d2              Reserve the d2 register (M68k only)
  -ffixed-d3              Reserve the d3 register (M68k only)
  -ffixed-d4              Reserve the d4 register (M68k only)
  -ffixed-d5              Reserve the d5 register (M68k only)
  -ffixed-d6              Reserve the d6 register (M68k only)
  -ffixed-d7              Reserve the d7 register (M68k only)
  -ffixed-point           Enable fixed point types
  -ffixed-r19             Reserve register r19 (Hexagon only)
  -ffixed-r9              Reserve the r9 register (ARM only)
  -ffixed-x10             Reserve the x10 register (AArch64/RISC-V only)
  -ffixed-x11             Reserve the x11 register (AArch64/RISC-V only)
  -ffixed-x12             Reserve the x12 register (AArch64/RISC-V only)
  -ffixed-x13             Reserve the x13 register (AArch64/RISC-V only)
  -ffixed-x14             Reserve the x14 register (AArch64/RISC-V only)
  -ffixed-x15             Reserve the x15 register (AArch64/RISC-V only)
  -ffixed-x16             Reserve the x16 register (AArch64/RISC-V only)
  -ffixed-x17             Reserve the x17 register (AArch64/RISC-V only)
  -ffixed-x18             Reserve the x18 register (AArch64/RISC-V only)
  -ffixed-x19             Reserve the x19 register (AArch64/RISC-V only)
  -ffixed-x1              Reserve the x1 register (AArch64/RISC-V only)
  -ffixed-x20             Reserve the x20 register (AArch64/RISC-V only)
  -ffixed-x21             Reserve the x21 register (AArch64/RISC-V only)
  -ffixed-x22             Reserve the x22 register (AArch64/RISC-V only)
  -ffixed-x23             Reserve the x23 register (AArch64/RISC-V only)
  -ffixed-x24             Reserve the x24 register (AArch64/RISC-V only)
  -ffixed-x25             Reserve the x25 register (AArch64/RISC-V only)
  -ffixed-x26             Reserve the x26 register (AArch64/RISC-V only)
  -ffixed-x27             Reserve the x27 register (AArch64/RISC-V only)
  -ffixed-x28             Reserve the x28 register (AArch64/RISC-V only)
  -ffixed-x29             Reserve the x29 register (AArch64/RISC-V only)
  -ffixed-x2              Reserve the x2 register (AArch64/RISC-V only)
  -ffixed-x30             Reserve the x30 register (AArch64/RISC-V only)
  -ffixed-x31             Reserve the x31 register (AArch64/RISC-V only)
  -ffixed-x3              Reserve the x3 register (AArch64/RISC-V only)
  -ffixed-x4              Reserve the x4 register (AArch64/RISC-V only)
  -ffixed-x5              Reserve the x5 register (AArch64/RISC-V only)
  -ffixed-x6              Reserve the x6 register (AArch64/RISC-V only)
  -ffixed-x7              Reserve the x7 register (AArch64/RISC-V only)
  -ffixed-x8              Reserve the x8 register (AArch64/RISC-V only)
  -ffixed-x9              Reserve the x9 register (AArch64/RISC-V only)
  -fforce-dwarf-frame     Always emit a debug frame section
  -fforce-emit-vtables    Emits more virtual tables to improve devirtualization
  -fforce-enable-int128   Enable support for int128_t type
  -ffp-contract=<value>   Form fused FP ops (e.g. FMAs): fast (fuses across statements disregarding pragmas) | on (only fuses in the same statement unless dictated by pragmas) | off (never fuses) | fast-honor-pragmas (fuses across statements unless diectated by pragmas). Default is 'fast' for CUDA, 'fast-honor-pragmas' for HIP, and 'on' otherwise.
  -ffp-exception-behavior=<value>
                          Specifies the exception behavior of floating-point operations.
  -ffp-model=<value>      Controls the semantics of floating-point calculations.
  -ffreestanding          Assert that the compilation takes place in a freestanding environment
  -ffuchsia-api-level=<value>
                          Set Fuchsia API level
  -ffunction-sections     Place each function in its own section
  -fglobal-isel           Enables the global instruction selector
  -fgnu-keywords          Allow GNU-extension keywords regardless of language standard
  -fgnu-runtime           Generate output compatible with the standard GNU Objective-C runtime
  -fgnu89-inline          Use the gnu89 inline semantics
  -fgnuc-version=<value>  Sets various macros to claim compatibility with the given GCC version (default is 4.2.1)
  -fgpu-allow-device-init Allow device side init function in HIP (experimental)
  -fgpu-defer-diag        Defer host/device related diagnostic messages for CUDA/HIP
  -fgpu-flush-denormals-to-zero
                          Flush denormal floating point values to zero in CUDA/HIP device mode.
  -fgpu-rdc               Generate relocatable device code, also known as separate compilation mode
  -fgpu-sanitize          Enable sanitizer for AMDGPU target
  -fhip-fp32-correctly-rounded-divide-sqrt
                          Specify that single precision floating-point divide and sqrt used in the program source are correctly rounded (HIP device compilation only)
  -fhip-new-launch-api    Use new kernel launching API for HIP
  -fignore-exceptions     Enable support for ignoring exception handling constructs
  -fimplicit-module-maps  Implicitly search the file system for module map files.
  -finline-functions      Inline suitable functions
  -finline-hint-functions Inline functions which are (explicitly or implicitly) marked inline
  -finput-charset=<value> Specify the default character set for source files
  -finstrument-function-entry-bare
                          Instrument function entry only, after inlining, without arguments to the instrumentation call
  -finstrument-functions-after-inlining
                          Like -finstrument-functions, but insert the calls after inlining
  -finstrument-functions  Generate calls to instrument function entry and exit
  -fintegrated-as         Enable the integrated assembler
  -fintegrated-cc1        Run cc1 in-process
  -fjump-tables           Use jump tables for lowering switches
  -fkeep-static-consts    Keep static const variables if unused
  -flax-vector-conversions=<value>
                          Enable implicit vector bit-casts
  -flegacy-pass-manager   Use the legacy pass manager in LLVM (deprecated, to be removed in a future release)
  -flto-jobs=<value>      Controls the backend parallelism of -flto=thin (default of 0 means the number of threads will be derived from the number of CPUs detected)
  -flto=auto              Enable LTO in 'full' mode
  -flto=jobserver         Enable LTO in 'full' mode
  -flto=<value>           Set LTO mode to either 'full' or 'thin'
  -flto                   Enable LTO in 'full' mode
  -fmacro-prefix-map=<value>
                          remap file source paths in predefined preprocessor macros and __builtin_FILE()
  -fmath-errno            Require math functions to indicate errors by setting errno
  -fmax-tokens=<value>    Max total number of preprocessed tokens for -Wmax-tokens.
  -fmax-type-align=<value>
                          Specify the maximum alignment to enforce on pointers lacking an explicit alignment
  -fmemory-profile=<directory>
                          Enable heap memory profiling and dump results into <directory>
  -fmemory-profile        Enable heap memory profiling
  -fmerge-all-constants   Allow merging of constants
  -fmessage-length=<value>
                          Format message diagnostics so that they fit within N columns
  -fminimize-whitespace   Minimize whitespace when emitting preprocessor output
  -fmodule-file=[<name>=]<file>
                          Specify the mapping of module name to precompiled module file, or load a module file if name is omitted.
  -fmodule-map-file=<file>
                          Load this module map file
  -fmodule-name=<name>    Specify the name of the module to build
  -fmodules-cache-path=<directory>
                          Specify the module cache path
  -fmodules-decluse       Require declaration of modules used within a module
  -fmodules-disable-diagnostic-validation
                          Disable validation of the diagnostic options when loading the module
  -fmodules-ignore-macro=<value>
                          Ignore the definition of the given macro when building and loading modules
  -fmodules-prune-after=<seconds>
                          Specify the interval (in seconds) after which a module file will be considered unused
  -fmodules-prune-interval=<seconds>
                          Specify the interval (in seconds) between attempts to prune the module cache
  -fmodules-search-all    Search even non-imported modules to resolve references
  -fmodules-strict-decluse
                          Like -fmodules-decluse but requires all headers to be in modules
  -fmodules-ts            Enable support for the C++ Modules TS
  -fmodules-user-build-path <directory>
                          Specify the module user build path
  -fmodules-validate-input-files-content
                          Validate PCM input files based on content if mtime differs
  -fmodules-validate-once-per-build-session
                          Don't verify input files for the modules if the module has been successfully validated or loaded during this build session
  -fmodules-validate-system-headers
                          Validate the system headers that a module depends on when loading the module
  -fmodules               Enable the 'modules' language feature
  -fms-compatibility-version=<value>
                          Dot-separated value representing the Microsoft compiler version number to report in _MSC_VER (0 = don't define it (default))
  -fms-compatibility      Enable full Microsoft Visual C++ compatibility
  -fms-extensions         Accept some non-standard constructs supported by the Microsoft compiler
  -fms-hotpatch           Ensure that all functions can be hotpatched at runtime
  -fmsc-version=<value>   Microsoft compiler version number to report in _MSC_VER (0 = don't define it (default))
  -fnew-alignment=<align> Specifies the largest alignment guaranteed by '::operator new(size_t)'
  -fnew-infallible        Enable treating throwing global C++ operator new as always returning valid memory (annotates with __attribute__((returns_nonnull)) and throw()). This is detectable in source.
  -fno-aapcs-bitfield-width
                          Do not follow the AAPCS standard requirement stating that volatile bit-field width is dictated by the field container type. (ARM only).
  -fno-access-control     Disable C++ access control
  -fno-addrsig            Don't emit an address-significance table
  -fno-assume-sane-operator-new
                          Don't assume that C++'s global operator new can't alias any pointer
  -fno-autolink           Disable generation of linker directives for automatic library linking
  -fno-builtin-<value>    Disable implicit builtin knowledge of a specific function
  -fno-builtin            Disable implicit builtin knowledge of functions
  -fno-c++-static-destructors
                          Disable C++ static destructor registration
  -fno-char8_t            Disable C++ builtin type char8_t
  -fno-color-diagnostics  Disable colors in diagnostics
  -fno-common             Compile common globals like normal definitions
  -fno-complete-member-pointers
                          Do not require member pointer base types to be complete if they would be significant under the Microsoft ABI
  -fno-constant-cfstrings Disable creation of CodeFoundation-type constant strings
  -fno-coverage-mapping   Disable code coverage analysis
  -fno-crash-diagnostics  Disable auto-generation of preprocessed source files and a script for reproduction during a clang crash
  -fno-cuda-approx-transcendentals
                          Don't use approximate transcendental functions
  -fno-cxx-modules        Disable modules for C++
  -fno-debug-macro        Do not emit macro debug information
  -fno-declspec           Disallow __declspec as a keyword
  -fno-delayed-template-parsing
                          Disable delayed template parsing
  -fno-delete-null-pointer-checks
                          Do not treat usage of null pointers as undefined behavior
  -fno-diagnostics-fixit-info
                          Do not include fixit information in diagnostics
  -fno-digraphs           Disallow alternative token representations '<:', ':>', '<%', '%>', '%:', '%:%:'
  -fno-direct-access-external-data
                          Use GOT indirection to reference external data symbols
  -fno-discard-value-names
                          Do not discard value names in LLVM IR
  -fno-dollars-in-identifiers
                          Disallow '$' in identifiers
  -fno-double-square-bracket-attributes
                          Disable '[[]]' attributes in all C and C++ language modes
  -fno-elide-constructors Disable C++ copy constructor elision
  -fno-elide-type         Do not elide types when printing diagnostics
  -fno-eliminate-unused-debug-types
                          Emit  debug info for defined but unused types
  -fno-exceptions         Disable support for exception handling
  -fno-experimental-relative-c++-abi-vtables
                          Do not use the experimental C++ class ABI for classes with virtual tables
  -fno-fine-grained-bitfield-accesses
                          Use large-integer access for consecutive bitfield runs.
  -fno-finite-loops       Do not assume that any loop is finite.
  -fno-fixed-point        Disable fixed point types
  -fno-force-enable-int128
                          Disable support for int128_t type
  -fno-global-isel        Disables the global instruction selector
  -fno-gnu-inline-asm     Disable GNU style inline asm
  -fno-gpu-allow-device-init
                          Don't allow device side init function in HIP (experimental)
  -fno-gpu-defer-diag     Don't defer host/device related diagnostic messages for CUDA/HIP
  -fno-hip-fp32-correctly-rounded-divide-sqrt
                          Don't specify that single precision floating-point divide and sqrt used in the program source are correctly rounded (HIP device compilation only)
  -fno-hip-new-launch-api Don't use new kernel launching API for HIP
  -fno-integrated-as      Disable the integrated assembler
  -fno-integrated-cc1     Spawn a separate process for each cc1
  -fno-jump-tables        Do not use jump tables for lowering switches
  -fno-keep-static-consts Don't keep static const variables if unused
  -fno-legacy-pass-manager
                          Use the new pass manager in LLVM
  -fno-lto                Disable LTO mode (default)
  -fno-memory-profile     Disable heap memory profiling
  -fno-merge-all-constants
                          Disallow merging of constants
  -fno-new-infallible     Disable treating throwing global C++ operator new as always returning valid memory (annotates with __attribute__((returns_nonnull)) and throw()). This is detectable in source.
  -fno-objc-infer-related-result-type
                          do not infer Objective-C related result type based on method family
  -fno-offload-lto        Disable LTO mode (default) for offload compilation
  -fno-openmp-extensions  Disable all Clang extensions for OpenMP directives and clauses
  -fno-operator-names     Do not treat C++ operator name keywords as synonyms for operators
  -fno-pch-codegen        Do not generate code for uses of this PCH that assumes an explicit object file will be built for the PCH
  -fno-pch-debuginfo      Do not generate debug info for types in an object file built from this PCH and do not generate them elsewhere
  -fno-plt                Use GOT indirection instead of PLT to make external function calls (x86 only)
  -fno-preserve-as-comments
                          Do not preserve comments in inline assembly
  -fno-profile-generate   Disable generation of profile instrumentation.
  -fno-profile-instr-generate
                          Disable generation of profile instrumentation.
  -fno-profile-instr-use  Disable using instrumentation data for profile-guided optimization
  -fno-pseudo-probe-for-profiling
                          Do not emit pseudo probes for sample profiling
  -fno-register-global-dtors-with-atexit
                          Don't use atexit or __cxa_atexit to register global destructors
  -fno-rtlib-add-rpath    Do not add -rpath with architecture-specific resource directory to the linker flags
  -fno-rtti-data          Disable generation of RTTI data
  -fno-rtti               Disable generation of rtti information
  -fno-sanitize-address-outline-instrumentation
                          Use default code inlining logic for the address sanitizer
  -fno-sanitize-address-poison-custom-array-cookie
                          Disable poisoning array cookies when using custom operator new[] in AddressSanitizer
  -fno-sanitize-address-use-after-scope
                          Disable use-after-scope detection in AddressSanitizer
  -fno-sanitize-address-use-odr-indicator
                          Disable ODR indicator globals
  -fno-sanitize-cfi-canonical-jump-tables
                          Do not make the jump table addresses canonical in the symbol table
  -fno-sanitize-cfi-cross-dso
                          Disable control flow integrity (CFI) checks for cross-DSO calls.
  -fno-sanitize-coverage=<value>
                          Disable features of coverage instrumentation for Sanitizers
  -fno-sanitize-hwaddress-experimental-aliasing
                          Disable aliasing mode in HWAddressSanitizer
  -fno-sanitize-ignorelist
                          Don't use ignorelist file for sanitizers
  -fno-sanitize-memory-param-retval
                          Disable detection of uninitialized parameters and return values
  -fno-sanitize-memory-track-origins
                          Disable origins tracking in MemorySanitizer
  -fno-sanitize-memory-use-after-dtor
                          Disable use-after-destroy detection in MemorySanitizer
  -fno-sanitize-recover=<value>
                          Disable recovery for specified sanitizers
  -fno-sanitize-stats     Disable sanitizer statistics gathering.
  -fno-sanitize-thread-atomics
                          Disable atomic operations instrumentation in ThreadSanitizer
  -fno-sanitize-thread-func-entry-exit
                          Disable function entry/exit instrumentation in ThreadSanitizer
  -fno-sanitize-thread-memory-access
                          Disable memory access instrumentation in ThreadSanitizer
  -fno-sanitize-trap=<value>
                          Disable trapping for specified sanitizers
  -fno-sanitize-trap      Disable trapping for all sanitizers
  -fno-short-wchar        Force wchar_t to be an unsigned int
  -fno-show-column        Do not include column number on diagnostics
  -fno-show-source-location
                          Do not include source location information with diagnostics
  -fno-signed-char        char is unsigned
  -fno-signed-zeros       Allow optimizations that ignore the sign of floating point zeros
  -fno-spell-checking     Disable spell-checking
  -fno-split-machine-functions
                          Disable late function splitting using profile information (x86 ELF)
  -fno-split-stack        Wouldn't use segmented stack
  -fno-stack-clash-protection
                          Disable stack clash protection
  -fno-stack-protector    Disable the use of stack protectors
  -fno-standalone-debug   Limit debug information produced to reduce size of debug binary
  -fno-strict-float-cast-overflow
                          Relax language rules and try to match the behavior of the target's native float-to-int conversion instructions
  -fno-strict-return      Don't treat control flow paths that fall off the end of a non-void function as unreachable
  -fno-sycl               Disables SYCL kernels compilation for device
  -fno-temp-file          Directly create compilation output files. This may lead to incorrect incremental builds if the compiler crashes
  -fno-threadsafe-statics Do not emit code to make initialization of local statics thread safe
  -fno-trigraphs          Do not process trigraph sequences
  -fno-unique-section-names
                          Don't use unique names for text and data sections
  -fno-unroll-loops       Turn off loop unroller
  -fno-use-cxa-atexit     Don't use __cxa_atexit for calling destructors
  -fno-use-init-array     Use .ctors/.dtors instead of .init_array/.fini_array
  -fno-visibility-inlines-hidden-static-local-var
                          Disables -fvisibility-inlines-hidden-static-local-var (this is the default on non-darwin targets)
  -fno-xray-function-index
                          Omit function index section at the expense of single-function patching performance
  -fno-zero-initialized-in-bss
                          Don't place zero initialized data in BSS
  -fobjc-arc-exceptions   Use EH-safe code when synthesizing retains and releases in -fobjc-arc
  -fobjc-arc              Synthesize retain and release calls for Objective-C pointers
  -fobjc-disable-direct-methods-for-testing
                          Ignore attribute objc_direct so that direct methods can be tested
  -fobjc-encode-cxx-class-template-spec
                          Fully encode c++ class template specialization
  -fobjc-exceptions       Enable Objective-C exceptions
  -fobjc-runtime=<value>  Specify the target Objective-C runtime kind and version
  -fobjc-weak             Enable ARC-style weak references in Objective-C
  -foffload-lto=<value>   Set LTO mode to either 'full' or 'thin' for offload compilation
  -foffload-lto           Enable LTO in 'full' mode for offload compilation
  -fopenmp-extensions     Enable all Clang extensions for OpenMP directives and clauses
  -fopenmp-implicit-rpath Set rpath on OpenMP executables
  -fopenmp-new-driver     Use the new driver for OpenMP offloading.
  -fopenmp-simd           Emit OpenMP code only for SIMD-based constructs.
  -fopenmp-target-debug   Enable debugging in the OpenMP offloading device RTL
  -fopenmp-target-new-runtime
                          Use the new bitcode library for OpenMP offloading
  -fopenmp-targets=<value>
                          Specify comma-separated list of triples OpenMP offloading targets to be supported
  -fopenmp-version=<value>
                          Set OpenMP version (e.g. 45 for OpenMP 4.5, 50 for OpenMP 5.0). Default value is 50.
  -fopenmp                Parse OpenMP pragmas and generate parallel code.
  -foptimization-record-file=<file>
                          Specify the output name of the file containing the optimization remarks. Implies -fsave-optimization-record. On Darwin platforms, this cannot be used with multiple -arch <arch> options.
  -foptimization-record-passes=<regex>
                          Only include passes which match a specified regular expression in the generated optimization record (by default, include all passes)
  -forder-file-instrumentation
                          Generate instrumented code to collect order file into default.profraw file (overridden by '=' form of option or LLVM_PROFILE_FILE env var)
  -fpack-struct=<value>   Specify the default maximum struct packing alignment
  -fpascal-strings        Recognize and construct Pascal-style string literals
  -fpass-plugin=<dsopath> Load pass plugin from a dynamic shared object file (only with new pass manager).
  -fpatchable-function-entry=<N,M>
                          Generate M NOPs before function entry and N-M NOPs after function entry
  -fpcc-struct-return     Override the default ABI to return all structs on the stack
  -fpch-codegen           Generate code for uses of this PCH that assumes an explicit object file will be built for the PCH
  -fpch-debuginfo         Generate debug info for types in an object file built from this PCH and do not generate them elsewhere
  -fpch-instantiate-templates
                          Instantiate templates already while building a PCH
  -fpch-validate-input-files-content
                          Validate PCH input files based on content if mtime differs
  -fplugin-arg-<name>-<arg>
                          Pass <arg> to plugin <name>
  -fplugin=<dsopath>      Load the named plugin (dynamic shared object)
  -fprebuilt-implicit-modules
                          Look up implicit modules in the prebuilt module path
  -fprebuilt-module-path=<directory>
                          Specify the prebuilt module path
  -fproc-stat-report=<value>
                          Save subprocess statistics to the given file
  -fproc-stat-report<value>
                          Print subprocess statistics
  -fprofile-exclude-files=<value>
                          Instrument only functions from files where names don't match all the regexes separated by a semi-colon
  -fprofile-filter-files=<value>
                          Instrument only functions from files where names match any regex separated by a semi-colon
  -fprofile-generate=<directory>
                          Generate instrumented code to collect execution counts into <directory>/default.profraw (overridden by LLVM_PROFILE_FILE env var)
  -fprofile-generate      Generate instrumented code to collect execution counts into default.profraw (overridden by LLVM_PROFILE_FILE env var)
  -fprofile-instr-generate=<file>
                          Generate instrumented code to collect execution counts into <file> (overridden by LLVM_PROFILE_FILE env var)
  -fprofile-instr-generate
                          Generate instrumented code to collect execution counts into default.profraw file (overridden by '=' form of option or LLVM_PROFILE_FILE env var)
  -fprofile-instr-use=<value>
                          Use instrumentation data for profile-guided optimization
  -fprofile-list=<value>  Filename defining the list of functions/files to instrument
  -fprofile-remapping-file=<file>
                          Use the remappings described in <file> to match the profile data against names in the program
  -fprofile-sample-accurate
                          Specifies that the sample profile is accurate
  -fprofile-sample-use=<value>
                          Enable sample-based profile guided optimizations
  -fprofile-update=<method>
                          Set update method of profile counters (atomic,prefer-atomic,single)
  -fprofile-use=<pathname>
                          Use instrumentation data for profile-guided optimization. If pathname is a directory, it reads from <pathname>/default.profdata. Otherwise, it reads from file <pathname>.
  -fprotect-parens        Determines whether the optimizer honors parentheses when floating-point expressions are evaluated
  -fpseudo-probe-for-profiling
                          Emit pseudo probes for sample profiling
  -freciprocal-math       Allow division operations to be reassociated
  -freg-struct-return     Override the default ABI to return small structs in registers
  -fregister-global-dtors-with-atexit
                          Use atexit or __cxa_atexit to register global destructors
  -frelaxed-template-template-args
                          Enable C++17 relaxed template template argument matching
  -freroll-loops          Turn on loop reroller
  -fropi                  Generate read-only position independent code (ARM only)
  -frtlib-add-rpath       Add -rpath with architecture-specific resource directory to the linker flags
  -frwpi                  Generate read-write position independent code (ARM only)
  -fsanitize-address-destructor=<value>
                          Set destructor type used in ASan instrumentation
  -fsanitize-address-field-padding=<value>
                          Level of field padding for AddressSanitizer
  -fsanitize-address-globals-dead-stripping
                          Enable linker dead stripping of globals in AddressSanitizer
  -fsanitize-address-outline-instrumentation
                          Always generate function calls for address sanitizer instrumentation
  -fsanitize-address-poison-custom-array-cookie
                          Enable poisoning array cookies when using custom operator new[] in AddressSanitizer
  -fsanitize-address-use-after-return=<mode>
                          Select the mode of detecting stack use-after-return in AddressSanitizer: never | runtime (default) | always
  -fsanitize-address-use-after-scope
                          Enable use-after-scope detection in AddressSanitizer
  -fsanitize-address-use-odr-indicator
                          Enable ODR indicator globals to avoid false ODR violation reports in partially sanitized programs at the cost of an increase in binary size
  -fsanitize-blacklist=<value>
                          Alias for -fsanitize-ignorelist=
  -fsanitize-cfi-canonical-jump-tables
                          Make the jump table addresses canonical in the symbol table
  -fsanitize-cfi-cross-dso
                          Enable control flow integrity (CFI) checks for cross-DSO calls.
  -fsanitize-cfi-icall-generalize-pointers
                          Generalize pointers in CFI indirect call type signature checks
  -fsanitize-coverage-allowlist=<value>
                          Restrict sanitizer coverage instrumentation exclusively to modules and functions that match the provided special case list, except the blocked ones
  -fsanitize-coverage-blacklist=<value>
                          Deprecated, use -fsanitize-coverage-ignorelist= instead
  -fsanitize-coverage-ignorelist=<value>
                          Disable sanitizer coverage instrumentation for modules and functions that match the provided special case list, even the allowed ones
  -fsanitize-coverage-whitelist=<value>
                          Deprecated, use -fsanitize-coverage-allowlist= instead
  -fsanitize-coverage=<value>
                          Specify the type of coverage instrumentation for Sanitizers
  -fsanitize-hwaddress-abi=<value>
                          Select the HWAddressSanitizer ABI to target (interceptor or platform, default interceptor). This option is currently unused.
  -fsanitize-hwaddress-experimental-aliasing
                          Enable aliasing mode in HWAddressSanitizer
  -fsanitize-ignorelist=<value>
                          Path to ignorelist file for sanitizers
  -fsanitize-memory-param-retval
                          Enable detection of uninitialized parameters and return values
  -fsanitize-memory-track-origins=<value>
                          Enable origins tracking in MemorySanitizer
  -fsanitize-memory-track-origins
                          Enable origins tracking in MemorySanitizer
  -fsanitize-memory-use-after-dtor
                          Enable use-after-destroy detection in MemorySanitizer
  -fsanitize-recover=<value>
                          Enable recovery for specified sanitizers
  -fsanitize-stats        Enable sanitizer statistics gathering.
  -fsanitize-system-blacklist=<value>
                          Alias for -fsanitize-system-ignorelist=
  -fsanitize-system-ignorelist=<value>
                          Path to system ignorelist file for sanitizers
  -fsanitize-thread-atomics
                          Enable atomic operations instrumentation in ThreadSanitizer (default)
  -fsanitize-thread-func-entry-exit
                          Enable function entry/exit instrumentation in ThreadSanitizer (default)
  -fsanitize-thread-memory-access
                          Enable memory access instrumentation in ThreadSanitizer (default)
  -fsanitize-trap=<value> Enable trapping for specified sanitizers
  -fsanitize-trap         Enable trapping for all sanitizers
  -fsanitize-undefined-strip-path-components=<number>
                          Strip (or keep only, if negative) a given number of path components when emitting check metadata.
  -fsanitize=<check>      Turn on runtime checks for various forms of undefined or suspicious behavior. See user manual for available checks
  -fsave-optimization-record=<format>
                          Generate an optimization record file in a specific format
  -fsave-optimization-record
                          Generate a YAML optimization record file
  -fseh-exceptions        Use SEH style exceptions
  -fshort-enums           Allocate to an enum type only as many bytes as it needs for the declared range of possible values
  -fshort-wchar           Force wchar_t to be a short unsigned int
  -fshow-overloads=<value>
                          Which overload candidates to show when overload resolution fails: best|all; defaults to all
  -fshow-skipped-includes Show skipped includes in -H output.
  -fsigned-char           char is signed
  -fsized-deallocation    Enable C++14 sized global deallocation functions
  -fsjlj-exceptions       Use SjLj style exceptions
  -fslp-vectorize         Enable the superword-level parallelism vectorization passes
  -fsplit-dwarf-inlining  Provide minimal debug info in the object/executable to facilitate online symbolication/stack traces in the absence of .dwo/.dwp files when using Split DWARF
  -fsplit-lto-unit        Enables splitting of the LTO unit
  -fsplit-machine-functions
                          Enable late function splitting using profile information (x86 ELF)
  -fsplit-stack           Use segmented stack
  -fstack-clash-protection
                          Enable stack clash protection
  -fstack-protector-all   Enable stack protectors for all functions
  -fstack-protector-strong
                          Enable stack protectors for some functions vulnerable to stack smashing. Compared to -fstack-protector, this uses a stronger heuristic that includes functions containing arrays of any size (and any type), as well as any calls to alloca or the taking of an address from a local variable
  -fstack-protector       Enable stack protectors for some functions vulnerable to stack smashing. This uses a loose heuristic which considers functions vulnerable if they contain a char (or 8bit integer) array or constant sized calls to alloca , which are of greater size than ssp-buffer-size (default: 8 bytes). All variable sized calls to alloca are considered vulnerable. A function with a stack protector has a guard value added to the stack frame that is checked on function exit. The guard value must be positioned in the stack frame such that a buffer overflow from a vulnerable variable will overwrite the guard value before overwriting the function's return address. The reference stack guard value is stored in a global variable.
  -fstack-size-section    Emit section containing metadata on function stack sizes
  -fstack-usage           Emit .su file containing information on function stack sizes
  -fstandalone-debug      Emit full debug info for all types used by the program
  -fstrict-enums          Enable optimizations based on the strict definition of an enum's value range
  -fstrict-float-cast-overflow
                          Assume that overflowing float-to-int casts are undefined (default)
  -fstrict-vtable-pointers
                          Enable optimizations based on the strict rules for overwriting polymorphic C++ objects
  -fswift-async-fp=<option>
                          Control emission of Swift async extended frame info (option: auto, always, never)
  -fsycl                  Enables SYCL kernels compilation for device
  -fsystem-module         Build this module as a system module. Only used with -emit-module
  -fthin-link-bitcode=<value>
                          Write minimized bitcode to <file> for the ThinLTO thin link only
  -fthinlto-index=<value> Perform ThinLTO importing using provided function summary index
  -ftime-report=<value>   (For new pass manager) "per-pass": one report for each pass; "per-pass-run": one report for each pass invocation
  -ftime-trace-granularity=<value>
                          Minimum time granularity (in microseconds) traced by time profiler
  -ftime-trace            Turn on time profiler. Generates JSON file based on output filename.
  -ftrap-function=<value> Issue call to specified function rather than a trap instruction
  -ftrapv-handler=<function name>
                          Specify the function to be called on overflow
  -ftrapv                 Trap on integer overflow
  -ftrigraphs             Process trigraph sequences
  -ftrivial-auto-var-init-stop-after=<value>
                          Stop initializing trivial automatic stack variables after the specified number of instances
  -ftrivial-auto-var-init=<value>
                          Initialize trivial automatic stack variables: uninitialized (default) | pattern
  -funique-basic-block-section-names
                          Use unique names for basic block sections (ELF Only)
  -funique-internal-linkage-names
                          Uniqueify Internal Linkage Symbol Names by appending the MD5 hash of the module path
  -funroll-loops          Turn on loop unroller
  -fuse-cuid=<value>      Method to generate ID's for compilation units for single source offloading languages CUDA and HIP: 'hash' (ID's generated by hashing file path and command line options) | 'random' (ID's generated as random numbers) | 'none' (disabled). Default is 'hash'. This option will be overridden by option '-cuid=[ID]' if it is specified.
  -fuse-line-directives   Use #line in preprocessed output
  -fvalidate-ast-input-files-content
                          Compute and store the hash of input files used to build an AST. Files with mismatching mtime's are considered valid if both contents is identical
  -fveclib=<value>        Use the given vector functions library
  -fvectorize             Enable the loop vectorization passes
  -fverbose-asm           Generate verbose assembly output
  -fvirtual-function-elimination
                          Enables dead virtual function elimination optimization. Requires -flto=full
  -fvisibility-dllexport=<value>
                          The visibility for dllexport definitions [-fvisibility-from-dllstorageclass]
  -fvisibility-externs-dllimport=<value>
                          The visibility for dllimport external declarations [-fvisibility-from-dllstorageclass]
  -fvisibility-externs-nodllstorageclass=<value>
                          The visibility for external declarations without an explicit DLL dllstorageclass [-fvisibility-from-dllstorageclass]
  -fvisibility-from-dllstorageclass
                          Set the visibility of symbols in the generated code from their DLL storage class
  -fvisibility-global-new-delete-hidden
                          Give global C++ operator new and delete declarations hidden visibility
  -fvisibility-inlines-hidden-static-local-var
                          When -fvisibility-inlines-hidden is enabled, static variables in inline C++ member functions will also be given hidden visibility by default
  -fvisibility-inlines-hidden
                          Give inline C++ member functions hidden visibility by default
  -fvisibility-ms-compat  Give global types 'default' visibility and global functions and variables 'hidden' visibility by default
  -fvisibility-nodllstorageclass=<value>
                          The visibility for defintiions without an explicit DLL export class [-fvisibility-from-dllstorageclass]
  -fvisibility=<value>    Set the default symbol visibility for all global declarations
  -fwasm-exceptions       Use WebAssembly style exceptions
  -fwhole-program-vtables Enables whole-program vtable optimization. Requires -flto
  -fwrapv                 Treat signed integer overflow as two's complement
  -fwritable-strings      Store string literals as writable data
  -fxl-pragma-pack        Enable IBM XL #pragma pack handling
  -fxray-always-emit-customevents
                          Always emit __xray_customevent(...) calls even if the containing function is not always instrumented
  -fxray-always-emit-typedevents
                          Always emit __xray_typedevent(...) calls even if the containing function is not always instrumented
  -fxray-always-instrument= <value>
                          DEPRECATED: Filename defining the whitelist for imbuing the 'always instrument' XRay attribute.
  -fxray-attr-list= <value>
                          Filename defining the list of functions/types for imbuing XRay attributes.
  -fxray-function-groups=<value>
                          Only instrument 1 of N groups
  -fxray-ignore-loops     Don't instrument functions with loops unless they also meet the minimum function size
  -fxray-instruction-threshold= <value>
                          Sets the minimum function size to instrument with XRay
  -fxray-instrumentation-bundle= <value>
                          Select which XRay instrumentation points to emit. Options: all, none, function-entry, function-exit, function, custom. Default is 'all'.  'function' includes both 'function-entry' and 'function-exit'.
  -fxray-instrument       Generate XRay instrumentation sleds on function entry and exit
  -fxray-link-deps        Tells clang to add the link dependencies for XRay.
  -fxray-modes= <value>   List of modes to link in by default into XRay instrumented binaries.
  -fxray-never-instrument= <value>
                          DEPRECATED: Filename defining the whitelist for imbuing the 'never instrument' XRay attribute.
  -fxray-selected-function-group=<value>
                          When using -fxray-function-groups, select which group of functions to instrument. Valid range is 0 to fxray-function-groups - 1
  -fzvector               Enable System z vector language extension
  -F <value>              Add directory to framework include search path
  --gcc-toolchain=<value> Search for GCC installation in the specified directory on targets which commonly use GCC. The directory usually contains 'lib{,32,64}/gcc{,-cross}/$triple' and 'include'. If specified, sysroot is skipped for GCC detection. Note: executables (e.g. ld) used by the compiler are not overridden by the selected GCC installation
  -gcodeview-ghash        Emit type record hashes in a .debug$H section
  -gcodeview              Generate CodeView debug information
  -gdwarf-2               Generate source-level debug information with dwarf version 2
  -gdwarf-3               Generate source-level debug information with dwarf version 3
  -gdwarf-4               Generate source-level debug information with dwarf version 4
  -gdwarf-5               Generate source-level debug information with dwarf version 5
  -gdwarf32               Enables DWARF32 format for ELF binaries, if debug information emission is enabled.
  -gdwarf64               Enables DWARF64 format for ELF binaries, if debug information emission is enabled.
  -gdwarf                 Generate source-level debug information with the default dwarf version
  -gembed-source          Embed source text in DWARF debug sections
  -gline-directives-only  Emit debug line info directives only
  -gline-tables-only      Emit debug line number tables only
  -gmodules               Generate debug info with external references to clang modules or precompiled headers
  -gno-embed-source       Restore the default behavior of not embedding source text in DWARF debug sections
  -gno-inline-line-tables Don't emit inline line tables.
  --gpu-bundle-output     Bundle output files of HIP device compilation
  --gpu-instrument-lib=<value>
                          Instrument device library for HIP, which is a LLVM bitcode containing __cyg_profile_func_enter and __cyg_profile_func_exit
  --gpu-max-threads-per-block=<value>
                          Default max threads per block for kernel launch bounds for HIP
  -gsplit-dwarf=<value>   Set DWARF fission mode to either 'split' or 'single'
  -gz=<value>             DWARF debug sections compression type
  -G <size>               Put objects of at most <size> bytes into small data section (MIPS / Hexagon)
  -g                      Generate source-level debug information
  --help-hidden           Display help for hidden options
  -help                   Display available options
  --hip-device-lib=<value>
                          HIP device library
  --hip-link              Link clang-offload-bundler bundles for HIP
  --hip-path=<value>      HIP runtime installation path, used for finding HIP version and adding HIP include path.
  --hip-version=<value>   HIP version in the format of major.minor.patch
  --hipspv-pass-plugin=<dsopath>
                          path to a pass plugin for HIP to SPIR-V passes.
  -H                      Show header includes and nesting depth
  -I-                     Restrict all prior -I flags to double-quoted inclusion and remove current directory from include path
  -ibuiltininc            Enable builtin #include directories even when -nostdinc is used before or after -ibuiltininc. Using -nobuiltininc after the option disables it
  -idirafter <value>      Add directory to AFTER include search path
  -iframeworkwithsysroot <directory>
                          Add directory to SYSTEM framework search path, absolute paths are relative to -isysroot
  -iframework <value>     Add directory to SYSTEM framework search path
  -imacros <file>         Include macros from file before parsing
  -include-pch <file>     Include precompiled header file
  -include <file>         Include file before parsing
  -index-header-map       Make the next included directory (-I or -F) an indexer header map
  -iprefix <dir>          Set the -iwithprefix/-iwithprefixbefore prefix
  -iquote <directory>     Add directory to QUOTE include search path
  -isysroot <dir>         Set the system root directory (usually /)
  -isystem-after <directory>
                          Add directory to end of the SYSTEM include search path
  -isystem <directory>    Add directory to SYSTEM include search path
  -ivfsoverlay <value>    Overlay the virtual filesystem described by file over the real file system
  -iwithprefixbefore <dir>
                          Set directory to include search path with prefix
  -iwithprefix <dir>      Set directory to SYSTEM include search path with prefix
  -iwithsysroot <directory>
                          Add directory to SYSTEM include search path, absolute paths are relative to -isysroot
  -I <dir>                Add directory to the end of the list of include search paths
  --libomptarget-amdgcn-bc-path=<value>
                          Path to libomptarget-amdgcn bitcode library
  --libomptarget-nvptx-bc-path=<value>
                          Path to libomptarget-nvptx bitcode library
  -L <dir>                Add directory to library search path
  -mabi=vec-default       Enable the default Altivec ABI on AIX (AIX only). Uses only volatile vector registers.
  -mabi=vec-extabi        Enable the extended Altivec ABI on AIX (AIX only). Uses volatile and nonvolatile vector registers
  -mabicalls              Enable SVR4-style position-independent code (Mips only)
  -maix-struct-return     Return all structs in memory (PPC32 only)
  -malign-branch-boundary=<value>
                          Specify the boundary's size to align branches
  -malign-branch=<value>  Specify types of branches to align
  -malign-double          Align doubles to two words in structs (x86 only)
  -mamdgpu-ieee           Sets the IEEE bit in the expected default floating point  mode register. Floating point opcodes that support exception flag gathering quiet and propagate signaling NaN inputs per IEEE 754-2008. This option changes the ABI. (AMDGPU only)
  -mbackchain             Link stack frames through backchain on System Z
  -mbranch-protection=<value>
                          Enforce targets of indirect branches and function returns
  -mbranches-within-32B-boundaries
                          Align selected branches (fused, jcc, jmp) within 32-byte boundary
  -mcmodel=medany         Equivalent to -mcmodel=medium, compatible with RISC-V gcc.
  -mcmodel=medlow         Equivalent to -mcmodel=small, compatible with RISC-V gcc.
  -mcmse                  Allow use of CMSE (Armv8-M Security Extensions)
  -mcode-object-v3        Legacy option to specify code object ABI V3 (AMDGPU only)
  -mcode-object-version=<version>
                          Specify code object ABI version. Defaults to 3. (AMDGPU only)
  -mcrc                   Allow use of CRC instructions (ARM/Mips only)
  -mcumode                Specify CU wavefront execution mode (AMDGPU only)
  -mdouble=<value>        Force double to be 32 bits or 64 bits
  -MD                     Write a depfile containing user and system headers
  -meabi <value>          Set EABI type, e.g. 4, 5 or gnu (default depends on triple)
  -membedded-data         Place constants in the .rodata section instead of the .sdata section even if they meet the -G <size> threshold (MIPS)
  -menable-experimental-extensions
                          Enable use of experimental RISC-V extensions.
  -menable-unsafe-fp-math Allow unsafe floating-point math optimizations which may decrease precision
  -mexec-model=<value>    Execution model (WebAssembly only)
  -mexecute-only          Disallow generation of data access to code sections (ARM only)
  -mextern-sdata          Assume that externally defined data is in the small data if it meets the -G <size> threshold (MIPS)
  -mfentry                Insert calls to fentry at function entry (x86/SystemZ only)
  -mfix-cmse-cve-2021-35465
                          Work around VLLDM erratum CVE-2021-35465 (ARM only)
  -mfix-cortex-a53-835769 Workaround Cortex-A53 erratum 835769 (AArch64 only)
  -mfp32                  Use 32-bit floating point registers (MIPS only)
  -mfp64                  Use 64-bit floating point registers (MIPS only)
  -MF <file>              Write depfile output from -MMD, -MD, -MM, or -M to <file>
  -mgeneral-regs-only     Generate code which only uses the general purpose registers (AArch64/x86 only)
  -mglobal-merge          Enable merging of globals
  -mgpopt                 Use GP relative accesses for symbols known to be in a small data section (MIPS)
  -MG                     Add missing headers to depfile
  -mharden-sls=<value>    Select straight-line speculation hardening scope
  -mhvx-ieee-fp           Enable Hexagon HVX IEEE floating-point
  -mhvx-length=<value>    Set Hexagon Vector Length
  -mhvx-qfloat            Enable Hexagon HVX QFloat instructions
  -mhvx=<value>           Enable Hexagon Vector eXtensions
  -mhvx                   Enable Hexagon Vector eXtensions
  -miamcu                 Use Intel MCU ABI
  -mibt-seal              Optimize fcf-protection=branch/full (requires LTO).
  -mignore-xcoff-visibility
                          Not emit the visibility attribute for asm in AIX OS or give all symbols 'unspecified' visibility in XCOFF object file
  --migrate               Run the migrator
  -mincremental-linker-compatible
                          (integrated-as) Emit an object file which can be used with an incremental linker
  -mindirect-jump=<value> Change indirect jump instructions to inhibit speculation
  -mios-version-min=<value>
                          Set iOS deployment target
  -MJ <value>             Write a compilation database entry per input
  -mllvm <value>          Additional arguments to forward to LLVM's option processing
  -mlocal-sdata           Extend the -G behaviour to object local data (MIPS)
  -mlong-calls            Generate branches with extended addressability, usually via indirect jumps.
  -mlong-double-128       Force long double to be 128 bits
  -mlong-double-64        Force long double to be 64 bits
  -mlong-double-80        Force long double to be 80 bits, padded to 128 bits for storage
  -mlvi-cfi               Enable only control-flow mitigations for Load Value Injection (LVI)
  -mlvi-hardening         Enable all mitigations for Load Value Injection (LVI)
  -mmacosx-version-min=<value>
                          Set Mac OS X deployment target
  -mmadd4                 Enable the generation of 4-operand madd.s, madd.d and related instructions.
  -mmark-bti-property     Add .note.gnu.property with BTI to assembly files (AArch64 only)
  -MMD                    Write a depfile containing user headers
  -mmemops                Enable generation of memop instructions
  -mms-bitfields          Set the default structure layout to be compatible with the Microsoft compiler standard
  -mmsa                   Enable MSA ASE (MIPS only)
  -mmt                    Enable MT ASE (MIPS only)
  -MM                     Like -MMD, but also implies -E and writes to stdout by default
  -mno-abicalls           Disable SVR4-style position-independent code (Mips only)
  -mno-bti-at-return-twice
                          Do not add a BTI instruction after a setjmp or other return-twice construct (Arm/AArch64 only)
  -mno-code-object-v3     Legacy option to specify code object ABI V2 (AMDGPU only)
  -mno-crc                Disallow use of CRC instructions (Mips only)
  -mno-cumode             Specify WGP wavefront execution mode (AMDGPU only)
  -mno-embedded-data      Do not place constants in the .rodata section instead of the .sdata if they meet the -G <size> threshold (MIPS)
  -mno-execute-only       Allow generation of data access to code sections (ARM only)
  -mno-extern-sdata       Do not assume that externally defined data is in the small data if it meets the -G <size> threshold (MIPS)
  -mno-fix-cmse-cve-2021-35465
                          Don't work around VLLDM erratum CVE-2021-35465 (ARM only)
  -mno-fix-cortex-a53-835769
                          Don't workaround Cortex-A53 erratum 835769 (AArch64 only)
  -mno-global-merge       Disable merging of globals
  -mno-gpopt              Do not use GP relative accesses for symbols known to be in a small data section (MIPS)
  -mno-hvx-ieee-fp        Disable Hexagon HVX IEEE floating-point
  -mno-hvx-qfloat         Disable Hexagon HVX QFloat instructions
  -mno-hvx                Disable Hexagon Vector eXtensions
  -mno-implicit-float     Don't generate implicit floating point instructions
  -mno-incremental-linker-compatible
                          (integrated-as) Emit an object file which cannot be used with an incremental linker
  -mno-local-sdata        Do not extend the -G behaviour to object local data (MIPS)
  -mno-long-calls         Restore the default behaviour of not generating long calls
  -mno-lvi-cfi            Disable control-flow mitigations for Load Value Injection (LVI)
  -mno-lvi-hardening      Disable mitigations for Load Value Injection (LVI)
  -mno-madd4              Disable the generation of 4-operand madd.s, madd.d and related instructions.
  -mno-memops             Disable generation of memop instructions
  -mno-movt               Disallow use of movt/movw pairs (ARM only)
  -mno-ms-bitfields       Do not set the default structure layout to be compatible with the Microsoft compiler standard
  -mno-msa                Disable MSA ASE (MIPS only)
  -mno-mt                 Disable MT ASE (MIPS only)
  -mno-neg-immediates     Disallow converting instructions with negative immediates to their negation or inversion.
  -mno-nvj                Disable generation of new-value jumps
  -mno-nvs                Disable generation of new-value stores
  -mno-outline-atomics    Don't generate local calls to out-of-line atomic operations
  -mno-outline            Disable function outlining (AArch64 only)
  -mno-packets            Disable generation of instruction packets
  -mno-relax              Disable linker relaxation
  -mno-restrict-it        Allow generation of deprecated IT blocks for ARMv8. It is off by default for ARMv8 Thumb mode
  -mno-save-restore       Disable using library calls for save and restore
  -mno-seses              Disable speculative execution side effect suppression (SESES)
  -mno-stack-arg-probe    Disable stack probes which are enabled by default
  -mno-tgsplit            Disable threadgroup split execution mode (AMDGPU only)
  -mno-tls-direct-seg-refs
                          Disable direct TLS access through segment registers
  -mno-unaligned-access   Force all memory accesses to be aligned (AArch32/AArch64 only)
  -mno-wavefrontsize64    Specify wavefront size 32 mode (AMDGPU only)
  -mnocrc                 Disallow use of CRC instructions (ARM only)
  -mnop-mcount            Generate mcount/__fentry__ calls as nops. To activate they need to be patched in.
  -mnvj                   Enable generation of new-value jumps
  -mnvs                   Enable generation of new-value stores
  -module-dependency-dir <value>
                          Directory to dump module dependencies to
  -module-file-info       Provide information about a particular module file
  -momit-leaf-frame-pointer
                          Omit frame pointer setup for leaf functions
  -moutline-atomics       Generate local calls to out-of-line atomic operations
  -moutline               Enable function outlining (AArch64 only)
  -mpacked-stack          Use packed stack layout (SystemZ only).
  -mpackets               Enable generation of instruction packets
  -mpad-max-prefix-size=<value>
                          Specify maximum number of prefixes to use for padding
  -mprefer-vector-width=<value>
                          Specifies preferred vector width for auto-vectorization. Defaults to 'none' which allows target specific decisions.
  -MP                     Create phony target for each dependency (other than main file)
  -mqdsp6-compat          Enable hexagon-qdsp6 backward compatibility
  -MQ <value>             Specify name of main file output to quote in depfile
  -mrecord-mcount         Generate a __mcount_loc section entry for each __fentry__ call.
  -mrelax-all             (integrated-as) Relax all machine instructions
  -mrelax                 Enable linker relaxation
  -mrestrict-it           Disallow generation of deprecated IT blocks for ARMv8. It is on by default for ARMv8 Thumb mode.
  -mrtd                   Make StdCall calling convention the default
  -msave-restore          Enable using library calls for save and restore
  -mseses                 Enable speculative execution side effect suppression (SESES). Includes LVI control flow integrity mitigations
  -msign-return-address=<value>
                          Select return address signing scope
  -mskip-rax-setup        Skip setting up RAX register when passing variable arguments (x86 only)
  -msmall-data-limit=<value>
                          Put global and static data smaller than the limit into a special section
  -msoft-float            Use software floating point
  -mstack-alignment=<value>
                          Set the stack alignment
  -mstack-arg-probe       Enable stack probes
  -mstack-probe-size=<value>
                          Set the stack probe size
  -mstack-protector-guard-offset=<value>
                          Use the given offset for addressing the stack-protector guard
  -mstack-protector-guard-reg=<value>
                          Use the given reg for addressing the stack-protector guard
  -mstack-protector-guard=<value>
                          Use the given guard (global, tls) for addressing the stack-protector guard
  -mstackrealign          Force realign the stack at entry to every function
  -msve-vector-bits=<value>
                          Specify the size in bits of an SVE vector register. Defaults to the vector length agnostic value of "scalable". (AArch64 only)
  -msvr4-struct-return    Return small structs in registers (PPC32 only)
  -mtargetos=<value>      Set the deployment target to be the specified OS and OS version
  -mtgsplit               Enable threadgroup split execution mode (AMDGPU only)
  -mthread-model <value>  The thread model to use, e.g. posix, single (posix by default)
  -mtls-direct-seg-refs   Enable direct TLS access through segment registers (default)
  -mtls-size=<value>      Specify bit size of immediate TLS offsets (AArch64 ELF only): 12 (for 4KB) | 24 (for 16MB, default) | 32 (for 4GB) | 48 (for 256TB, needs -mcmodel=large)
  -mtp=<value>            Thread pointer access method (AArch32/AArch64 only)
  -mtune=<value>          Only supported on X86 and RISC-V. Otherwise accepted for compatibility with GCC.
  -MT <value>             Specify name of main file output in depfile
  -munaligned-access      Allow memory accesses to be unaligned (AArch32/AArch64 only)
  -munsafe-fp-atomics     Enable unsafe floating point atomic instructions (AMDGPU only)
  -mvscale-max=<value>    Specify the vscale maximum. Defaults to the vector length agnostic value of "0". (AArch64 only)
  -mvscale-min=<value>    Specify the vscale minimum. Defaults to "1". (AArch64 only)
  -MV                     Use NMake/Jom format for the depfile
  -mwavefrontsize64       Specify wavefront size 64 mode (AMDGPU only)
  -M                      Like -MD, but also implies -E and writes to stdout by default
  --no-cuda-include-ptx=<value>
                          Do not include PTX for the following GPU architecture (e.g. sm_35) or 'all'. May be specified more than once.
  --no-cuda-version-check Don't error out if the detected version of the CUDA install is too low for the requested CUDA gpu architecture.
  --no-gpu-bundle-output  Do not bundle output files of HIP device compilation
  --no-offload-arch=<value>
                          Remove CUDA/HIP offloading device architecture (e.g. sm_35, gfx906) from the list of devices to compile for. 'all' resets the list to its default value.
  --no-system-header-prefix=<prefix>
                          Treat all #include paths starting with <prefix> as not including a system header.
  -nobuiltininc           Disable builtin #include directories
  -nogpuinc               Do not add include paths for CUDA/HIP and do not include the default CUDA/HIP wrapper headers
  -nogpulib               Do not link device library for CUDA/HIP device compilation
  -nohipwrapperinc        Do not include the default HIP wrapper headers and include paths
  -nostdinc++             Disable standard #include directories for the C++ standard library
  -ObjC++                 Treat source input files as Objective-C++ inputs
  -objcmt-allowlist-dir-path=<value>
                          Only modify files with a filename contained in the provided directory path
  -objcmt-atomic-property Make migration to 'atomic' properties
  -objcmt-migrate-all     Enable migration to modern ObjC
  -objcmt-migrate-annotation
                          Enable migration to property and method annotations
  -objcmt-migrate-designated-init
                          Enable migration to infer NS_DESIGNATED_INITIALIZER for initializer methods
  -objcmt-migrate-instancetype
                          Enable migration to infer instancetype for method result type
  -objcmt-migrate-literals
                          Enable migration to modern ObjC literals
  -objcmt-migrate-ns-macros
                          Enable migration to NS_ENUM/NS_OPTIONS macros
  -objcmt-migrate-property-dot-syntax
                          Enable migration of setter/getter messages to property-dot syntax
  -objcmt-migrate-property
                          Enable migration to modern ObjC property
  -objcmt-migrate-protocol-conformance
                          Enable migration to add protocol conformance on classes
  -objcmt-migrate-readonly-property
                          Enable migration to modern ObjC readonly property
  -objcmt-migrate-readwrite-property
                          Enable migration to modern ObjC readwrite property
  -objcmt-migrate-subscripting
                          Enable migration to modern ObjC subscripting
  -objcmt-ns-nonatomic-iosonly
                          Enable migration to use NS_NONATOMIC_IOSONLY macro for setting property's 'atomic' attribute
  -objcmt-returns-innerpointer-property
                          Enable migration to annotate property with NS_RETURNS_INNER_POINTER
  -objcmt-whitelist-dir-path=<value>
                          Alias for -objcmt-allowlist-dir-path
  -ObjC                   Treat source input files as Objective-C inputs
  -object-file-name=<file>
                          Set the output <file> for debug infos
  --offload-arch=<value>  CUDA offloading device architecture (e.g. sm_35), or HIP offloading target ID in the form of a device architecture followed by target ID features delimited by a colon. Each target ID feature is a pre-defined string followed by a plus or minus sign (e.g. gfx908:xnack+:sramecc-).  May be specified more than once.
  --offload=<value>       Specify comma-separated list of offloading target triples (CUDA and HIP only)
  -o <file>               Write output to <file>
  -pedantic               Warn on language extensions
  -pg                     Enable mcount instrumentation
  -pipe                   Use pipes between commands, when possible
  --precompile            Only precompile the input
  -print-effective-triple Print the effective target triple
  -print-file-name=<file> Print the full library path of <file>
  -print-ivar-layout      Enable Objective-C Ivar layout bitmap print trace
  -print-libgcc-file-name Print the library path for the currently used compiler runtime library ("libgcc.a" or "libclang_rt.builtins.*.a")
  -print-multiarch        Print the multiarch target triple
  -print-prog-name=<name> Print the full program path of <name>
  -print-resource-dir     Print the resource directory pathname
  -print-rocm-search-dirs Print the paths used for finding ROCm installation
  -print-runtime-dir      Print the directory pathname containing clangs runtime libraries
  -print-search-dirs      Print the paths used for finding libraries and programs
  -print-supported-cpus   Print supported cpu models for the given target (if target is not specified, it will print the supported cpus for the default target)
  -print-target-triple    Print the normalized target triple
  -print-targets          Print the registered targets
  -pthread                Support POSIX threads in generated code
  --ptxas-path=<value>    Path to ptxas (used for compiling CUDA code)
  -P                      Disable linemarker output in -E mode
  -Qn                     Do not emit metadata containing compiler name and version
  -Qunused-arguments      Don't emit warning for unused driver arguments
  -Qy                     Emit metadata containing compiler name and version
  -relocatable-pch        Whether to build a relocatable precompiled header
  -rewrite-legacy-objc    Rewrite Legacy Objective-C source to C++
  -rewrite-objc           Rewrite Objective-C source to C++
  --rocm-device-lib-path=<value>
                          ROCm device library path. Alternative to rocm-path.
  --rocm-path=<value>     ROCm installation path, used for finding and automatically linking required bitcode libraries.
  -Rpass-analysis=<value> Report transformation analysis from optimization passes whose name matches the given POSIX regular expression
  -Rpass-missed=<value>   Report missed transformations by optimization passes whose name matches the given POSIX regular expression
  -Rpass=<value>          Report transformations performed by optimization passes whose name matches the given POSIX regular expression
  -rtlib=<value>          Compiler runtime library to use
  -R<remark>              Enable the specified remark
  -save-stats=<value>     Save llvm statistics.
  -save-stats             Save llvm statistics.
  -save-temps=<value>     Save intermediate compilation results.
  -save-temps             Save intermediate compilation results
  -serialize-diagnostics <value>
                          Serialize compiler diagnostics to a file
  -shared-libsan          Dynamically link the sanitizer runtime
  --start-no-unused-arguments
                          Don't emit warnings about unused arguments for the following arguments
  -static-libsan          Statically link the sanitizer runtime
  -static-openmp          Use the static host OpenMP runtime while linking.
  -std=<value>            Language standard to compile for
  -stdlib++-isystem <directory>
                          Use directory as the C++ standard library include path
  -stdlib=<value>         C++ standard library to use
  -sycl-std=<value>       SYCL language standard to compile for.
  --system-header-prefix=<prefix>
                          Treat all #include paths starting with <prefix> as including a system header.
  -S                      Only run preprocess and compilation steps
  --target=<value>        Generate code for the given target
  -Tbss <addr>            Set starting address of BSS to <addr>
  -Tdata <addr>           Set starting address of DATA to <addr>
  -time                   Time individual commands
  -traditional-cpp        Enable some traditional CPP emulation
  -trigraphs              Process trigraph sequences
  -Ttext <addr>           Set starting address of TEXT to <addr>
  -T <script>             Specify <script> as linker script
  -undef                  undef all system defines
  -unwindlib=<value>      Unwind library to use
  -U <macro>              Undefine macro <macro>
  --verify-debug-info     Verify the binary representation of debug output
  -verify-pch             Load and verify that a pre-compiled header file is not stale
  --version               Print version information
  -v                      Show commands to run and use verbose output
  -Wa,<arg>               Pass the comma separated arguments in <arg> to the assembler
  -Wdeprecated            Enable warnings for deprecated constructs and define __DEPRECATED
  -Wl,<arg>               Pass the comma separated arguments in <arg> to the linker
  -working-directory <value>
                          Resolve file paths relative to the specified directory
  -Wp,<arg>               Pass the comma separated arguments in <arg> to the preprocessor
  -W<warning>             Enable the specified warning
  -w                      Suppress all warnings
  -Xanalyzer <arg>        Pass <arg> to the static analyzer
  -Xarch_device <arg>     Pass <arg> to the CUDA/HIP device compilation
  -Xarch_host <arg>       Pass <arg> to the CUDA/HIP host compilation
  -Xassembler <arg>       Pass <arg> to the assembler
  -Xclang <arg>           Pass <arg> to the clang compiler
  -Xcuda-fatbinary <arg>  Pass <arg> to fatbinary invocation
  -Xcuda-ptxas <arg>      Pass <arg> to the ptxas assembler
  -Xlinker <arg>          Pass <arg> to the linker
  -Xopenmp-target=<triple> <arg>
                          Pass <arg> to the target offloading toolchain identified by <triple>.
  -Xopenmp-target <arg>   Pass <arg> to the target offloading toolchain.
  -Xpreprocessor <arg>    Pass <arg> to the preprocessor
  -x <language>           Treat subsequent input files as having type <language>
  -z <arg>                Pass -z <arg> to the linker
```

***

**clang++**

```
:~# clang++ --help
OVERVIEW: clang LLVM compiler

USAGE: clang [options] file...

OPTIONS:
  -###                    Print (but do not run) the commands to run for this compilation
  --amdgpu-arch-tool=<value>
                          Tool used for detecting AMD GPU arch in the system.
  --analyzer-output <value>
                          Static analyzer report output format (html|plist|plist-multi-file|plist-html|sarif|sarif-html|text).
  --analyze               Run the static analyzer
  -arcmt-migrate-emit-errors
                          Emit ARC errors even if the migrator can fix them
  -arcmt-migrate-report-output <value>
                          Output path for the plist report
  -B <prefix>             Search $prefix$file for executables, libraries, and data files. If $prefix is a directory, search $prefix/$file
  -b <arg>                Pass -b <arg> to the linker on AIX (only).
  -CC                     Include comments from within macros in preprocessed output
  -cl-denorms-are-zero    OpenCL only. Allow denormals to be flushed to zero.
  -cl-fast-relaxed-math   OpenCL only. Sets -cl-finite-math-only and -cl-unsafe-math-optimizations, and defines __FAST_RELAXED_MATH__.
  -cl-finite-math-only    OpenCL only. Allow floating-point optimizations that assume arguments and results are not NaNs or +-Inf.
  -cl-fp32-correctly-rounded-divide-sqrt
                          OpenCL only. Specify that single precision floating-point divide and sqrt used in the program source are correctly rounded.
  -cl-kernel-arg-info     OpenCL only. Generate kernel argument metadata.
  -cl-mad-enable          OpenCL only. Allow use of less precise MAD computations in the generated binary.
  -cl-no-signed-zeros     OpenCL only. Allow use of less precise no signed zeros computations in the generated binary.
  -cl-no-stdinc           OpenCL only. Disables all standard includes containing non-native compiler types and functions.
  -cl-opt-disable         OpenCL only. This option disables all optimizations. By default optimizations are enabled.
  -cl-single-precision-constant
                          OpenCL only. Treat double precision floating-point constant as single precision constant.
  -cl-std=<value>         OpenCL language standard to compile for.
  -cl-strict-aliasing     OpenCL only. This option is added for compatibility with OpenCL 1.0.
  -cl-uniform-work-group-size
                          OpenCL only. Defines that the global work-size be a multiple of the work-group size specified to clEnqueueNDRangeKernel
  -cl-unsafe-math-optimizations
                          OpenCL only. Allow unsafe floating-point optimizations.  Also implies -cl-no-signed-zeros and -cl-mad-enable.
  --config <value>        Specifies configuration file
  --cuda-compile-host-device
                          Compile CUDA code for both host and device (default).  Has no effect on non-CUDA compilations.
  --cuda-device-only      Compile CUDA code for device only
  --cuda-host-only        Compile CUDA code for host only.  Has no effect on non-CUDA compilations.
  --cuda-include-ptx=<value>
                          Include PTX for the following GPU architecture (e.g. sm_35) or 'all'. May be specified more than once.
  --cuda-noopt-device-debug
                          Enable device-side debug info generation. Disables ptxas optimizations.
  --cuda-path-ignore-env  Ignore environment variables to detect CUDA installation
  --cuda-path=<value>     CUDA installation path
  -cuid=<value>           An ID for compilation unit, which should be the same for the same compilation unit but different for different compilation units. It is used to externalize device-side static variables for single source offloading languages CUDA and HIP so that they can be accessed by the host code of the same compilation unit.
  -cxx-isystem <directory>
                          Add directory to the C++ SYSTEM include search path
  -C                      Include comments in preprocessed output
  -c                      Only run preprocess, compile, and assemble steps
  -dD                     Print macro definitions in -E mode in addition to normal output
  -dependency-dot <value> Filename to write DOT-formatted header dependencies to
  -dependency-file <value>
                          Filename (or -) to write dependency output to
  -dI                     Print include directives in -E mode in addition to normal output
  -dM                     Print macro definitions in -E mode instead of normal output
  -dsym-dir <dir>         Directory to output dSYM's (if any) to
  -D <macro>=<value>      Define <macro> to <value> (or 1 if <value> omitted)
  -emit-ast               Emit Clang AST files for source inputs
  -emit-interface-stubs   Generate Interface Stub Files.
  -emit-llvm              Use the LLVM representation for assembler and object files
  -emit-merged-ifs        Generate Interface Stub Files, emit merged text not binary.
  --emit-static-lib       Enable linker job to emit a static library.
  -enable-trivial-auto-var-init-zero-knowing-it-will-be-removed-from-clang
                          Trivial automatic variable initialization to zero is only here for benchmarks, it'll eventually be removed, and I'm OK with that because I'm only using it to benchmark
  --end-no-unused-arguments
                          Start emitting warnings for unused driver arguments
  -extract-api            Extract API information
  -E                      Only run the preprocessor
  -faapcs-bitfield-load   Follows the AAPCS standard that all volatile bit-field write generates at least one load. (ARM only).
  -faapcs-bitfield-width  Follow the AAPCS standard requirement stating that volatile bit-field width is dictated by the field container type. (ARM only).
  -faddrsig               Emit an address-significance table
  -falign-loops=<N>       N must be a power of two. Align loops to the boundary
  -faligned-allocation    Enable C++17 aligned allocation functions
  -fallow-editor-placeholders
                          Treat editor placeholders as valid source code
  -faltivec-src-compat=<value>
                          Source-level compatibility for Altivec vectors (for PowerPC targets). This includes results of vector comparison (scalar for 'xl', vector for 'gcc') as well as behavior when initializing with a scalar (splatting for 'xl', element zero only for 'gcc'). For 'mixed', the compatibility is as 'gcc' for 'vector bool/vector pixel' and as 'xl' for other types. Current default is 'mixed'.
  -fansi-escape-codes     Use ANSI escape codes for diagnostics
  -fapple-kext            Use Apple's kernel extensions ABI
  -fapple-link-rtlib      Force linking the clang builtins runtime library
  -fapple-pragma-pack     Enable Apple gcc-compatible #pragma pack handling
  -fapplication-extension Restrict code to those available for App Extensions
  -fapprox-func           Allow certain math function calls to be replaced with an approximately equivalent calculation
  -fasync-exceptions      Enable EH Asynchronous exceptions
  -fbasic-block-sections=<value>
                          Place each function's basic blocks in unique sections (ELF Only) : all | labels | none | list=<file>
  -fbinutils-version=<major.minor>
                          Produced object files can use all ELF features supported by this binutils version and newer. If -fno-integrated-as is specified, the generated assembly will consider GNU as support. 'none' means that all ELF features can be used, regardless of binutils support. Defaults to 2.26.
  -fblocks                Enable the 'blocks' language feature
  -fborland-extensions    Accept non-standard constructs supported by the Borland compiler
  -fbuild-session-file=<file>
                          Use the last modification time of <file> as the build session timestamp
  -fbuild-session-timestamp=<time since Epoch in seconds>
                          Time when the current build session started
  -fbuiltin-module-map    Load the clang builtins module map file.
  -fc++-abi=<value>       C++ ABI to use. This will override the target C++ ABI.
  -fcall-saved-x10        Make the x10 register call-saved (AArch64 only)
  -fcall-saved-x11        Make the x11 register call-saved (AArch64 only)
  -fcall-saved-x12        Make the x12 register call-saved (AArch64 only)
  -fcall-saved-x13        Make the x13 register call-saved (AArch64 only)
  -fcall-saved-x14        Make the x14 register call-saved (AArch64 only)
  -fcall-saved-x15        Make the x15 register call-saved (AArch64 only)
  -fcall-saved-x18        Make the x18 register call-saved (AArch64 only)
  -fcall-saved-x8         Make the x8 register call-saved (AArch64 only)
  -fcall-saved-x9         Make the x9 register call-saved (AArch64 only)
  -fcf-protection=<value> Instrument control-flow architecture protection. Options: return, branch, full, none.
  -fcf-protection         Enable cf-protection in 'full' mode
  -fchar8_t               Enable C++ builtin type char8_t
  -fclang-abi-compat=<version>
                          Attempt to match the ABI of Clang <version>
  -fcolor-diagnostics     Enable colors in diagnostics
  -fcomment-block-commands=<arg>
                          Treat each comma separated argument in <arg> as a documentation comment block command
  -fcommon                Place uninitialized global variables in a common block
  -fcomplete-member-pointers
                          Require member pointer base types to be complete if they would be significant under the Microsoft ABI
  -fconvergent-functions  Assume functions may be convergent
  -fcoroutines-ts         Enable support for the C++ Coroutines TS
  -fcoverage-compilation-dir=<value>
                          The compilation directory to embed in the coverage mapping.
  -fcoverage-mapping      Generate coverage mapping to enable code coverage analysis
  -fcoverage-prefix-map=<value>
                          remap file source paths in coverage mapping
  -fcrash-diagnostics-dir=<dir>
                          Put crash-report files in <dir>
  -fcs-profile-generate=<directory>
                          Generate instrumented code to collect context sensitive execution counts into <directory>/default.profraw (overridden by LLVM_PROFILE_FILE env var)
  -fcs-profile-generate   Generate instrumented code to collect context sensitive execution counts into default.profraw (overridden by LLVM_PROFILE_FILE env var)
  -fcuda-approx-transcendentals
                          Use approximate transcendental functions
  -fcuda-short-ptr        Use 32-bit pointers for accessing const/local/shared address spaces
  -fcxx-exceptions        Enable C++ exceptions
  -fcxx-modules           Enable modules for C++
  -fdata-sections         Place each data in its own section
  -fdebug-compilation-dir=<value>
                          The compilation directory to embed in the debug info
  -fdebug-default-version=<value>
                          Default DWARF version to use, if a -g option caused DWARF debug info to be produced
  -fdebug-info-for-profiling
                          Emit extra debug info to make sample profile more accurate
  -fdebug-macro           Emit macro debug information
  -fdebug-prefix-map=<value>
                          remap file source paths in debug info
  -fdebug-ranges-base-address
                          Use DWARF base address selection entries in .debug_ranges
  -fdebug-types-section   Place debug types in their own section (ELF Only)
  -fdeclspec              Allow __declspec as a keyword
  -fdelayed-template-parsing
                          Parse templated function definitions at the end of the translation unit
  -fdelete-null-pointer-checks
                          Treat usage of null pointers as undefined behavior (default)
  -fdiagnostics-absolute-paths
                          Print absolute paths in diagnostics
  -fdiagnostics-hotness-threshold=<value>
                          Prevent optimization remarks from being output if they do not have at least this profile count. Use 'auto' to apply the threshold from profile summary
  -fdiagnostics-parseable-fixits
                          Print fix-its in machine parseable form
  -fdiagnostics-print-source-range-info
                          Print source range spans in numeric form
  -fdiagnostics-show-hotness
                          Enable profile hotness information in diagnostic line
  -fdiagnostics-show-note-include-stack
                          Display include stacks for diagnostic notes
  -fdiagnostics-show-option
                          Print option name with mappable diagnostics
  -fdiagnostics-show-template-tree
                          Print a template comparison tree for differing templates
  -fdigraphs              Enable alternative token representations '<:', ':>', '<%', '%>', '%:', '%:%:' (default)
  -fdirect-access-external-data
                          Don't use GOT indirection to reference external data symbols
  -fdiscard-value-names   Discard value names in LLVM IR
  -fdollars-in-identifiers
                          Allow '$' in identifiers
  -fdouble-square-bracket-attributes
                          Enable '[[]]' attributes in all C and C++ language modes
  -fdwarf-exceptions      Use DWARF style exceptions
  -feliminate-unused-debug-types
                          Do not emit  debug info for defined but unused types
  -fembed-bitcode-marker  Embed placeholder LLVM IR data as a marker
  -fembed-bitcode=<option>
                          Embed LLVM bitcode (option: off, all, bitcode, marker)
  -fembed-bitcode         Embed LLVM IR bitcode as data
  -fembed-offload-object=<value>
                          Embed Offloading device-side binary into host object file as a section.
  -femit-all-decls        Emit all declarations, even if unused
  -femulated-tls          Use emutls functions to access thread_local variables
  -fenable-matrix         Enable matrix data type and related builtin functions
  -fexceptions            Enable support for exception handling
  -fexperimental-new-constant-interpreter
                          Enable the experimental new constant interpreter
  -fexperimental-relative-c++-abi-vtables
                          Use the experimental C++ class ABI for classes with virtual tables
  -fexperimental-strict-floating-point
                          Enables experimental strict floating point in LLVM.
  -fextend-arguments=<value>
                          Controls how scalar integer arguments are extended in calls to unprototyped and varargs functions
  -ffast-math             Allow aggressive, lossy floating-point optimizations
  -ffile-compilation-dir=<value>
                          The compilation directory to embed in the debug info and coverage mapping.
  -ffile-prefix-map=<value>
                          remap file source paths in debug info, predefined preprocessor macros and __builtin_FILE()
  -ffine-grained-bitfield-accesses
                          Use separate accesses for consecutive bitfield runs with legal widths and alignments.
  -ffinite-loops          Assume all loops are finite.
  -ffixed-a0              Reserve the a0 register (M68k only)
  -ffixed-a1              Reserve the a1 register (M68k only)
  -ffixed-a2              Reserve the a2 register (M68k only)
  -ffixed-a3              Reserve the a3 register (M68k only)
  -ffixed-a4              Reserve the a4 register (M68k only)
  -ffixed-a5              Reserve the a5 register (M68k only)
  -ffixed-a6              Reserve the a6 register (M68k only)
  -ffixed-d0              Reserve the d0 register (M68k only)
  -ffixed-d1              Reserve the d1 register (M68k only)
  -ffixed-d2              Reserve the d2 register (M68k only)
  -ffixed-d3              Reserve the d3 register (M68k only)
  -ffixed-d4              Reserve the d4 register (M68k only)
  -ffixed-d5              Reserve the d5 register (M68k only)
  -ffixed-d6              Reserve the d6 register (M68k only)
  -ffixed-d7              Reserve the d7 register (M68k only)
  -ffixed-point           Enable fixed point types
  -ffixed-r19             Reserve register r19 (Hexagon only)
  -ffixed-r9              Reserve the r9 register (ARM only)
  -ffixed-x10             Reserve the x10 register (AArch64/RISC-V only)
  -ffixed-x11             Reserve the x11 register (AArch64/RISC-V only)
  -ffixed-x12             Reserve the x12 register (AArch64/RISC-V only)
  -ffixed-x13             Reserve the x13 register (AArch64/RISC-V only)
  -ffixed-x14             Reserve the x14 register (AArch64/RISC-V only)
  -ffixed-x15             Reserve the x15 register (AArch64/RISC-V only)
  -ffixed-x16             Reserve the x16 register (AArch64/RISC-V only)
  -ffixed-x17             Reserve the x17 register (AArch64/RISC-V only)
  -ffixed-x18             Reserve the x18 register (AArch64/RISC-V only)
  -ffixed-x19             Reserve the x19 register (AArch64/RISC-V only)
  -ffixed-x1              Reserve the x1 register (AArch64/RISC-V only)
  -ffixed-x20             Reserve the x20 register (AArch64/RISC-V only)
  -ffixed-x21             Reserve the x21 register (AArch64/RISC-V only)
  -ffixed-x22             Reserve the x22 register (AArch64/RISC-V only)
  -ffixed-x23             Reserve the x23 register (AArch64/RISC-V only)
  -ffixed-x24             Reserve the x24 register (AArch64/RISC-V only)
  -ffixed-x25             Reserve the x25 register (AArch64/RISC-V only)
  -ffixed-x26             Reserve the x26 register (AArch64/RISC-V only)
  -ffixed-x27             Reserve the x27 register (AArch64/RISC-V only)
  -ffixed-x28             Reserve the x28 register (AArch64/RISC-V only)
  -ffixed-x29             Reserve the x29 register (AArch64/RISC-V only)
  -ffixed-x2              Reserve the x2 register (AArch64/RISC-V only)
  -ffixed-x30             Reserve the x30 register (AArch64/RISC-V only)
  -ffixed-x31             Reserve the x31 register (AArch64/RISC-V only)
  -ffixed-x3              Reserve the x3 register (AArch64/RISC-V only)
  -ffixed-x4              Reserve the x4 register (AArch64/RISC-V only)
  -ffixed-x5              Reserve the x5 register (AArch64/RISC-V only)
  -ffixed-x6              Reserve the x6 register (AArch64/RISC-V only)
  -ffixed-x7              Reserve the x7 register (AArch64/RISC-V only)
  -ffixed-x8              Reserve the x8 register (AArch64/RISC-V only)
  -ffixed-x9              Reserve the x9 register (AArch64/RISC-V only)
  -fforce-dwarf-frame     Always emit a debug frame section
  -fforce-emit-vtables    Emits more virtual tables to improve devirtualization
  -fforce-enable-int128   Enable support for int128_t type
  -ffp-contract=<value>   Form fused FP ops (e.g. FMAs): fast (fuses across statements disregarding pragmas) | on (only fuses in the same statement unless dictated by pragmas) | off (never fuses) | fast-honor-pragmas (fuses across statements unless diectated by pragmas). Default is 'fast' for CUDA, 'fast-honor-pragmas' for HIP, and 'on' otherwise.
  -ffp-exception-behavior=<value>
                          Specifies the exception behavior of floating-point operations.
  -ffp-model=<value>      Controls the semantics of floating-point calculations.
  -ffreestanding          Assert that the compilation takes place in a freestanding environment
  -ffuchsia-api-level=<value>
                          Set Fuchsia API level
  -ffunction-sections     Place each function in its own section
  -fglobal-isel           Enables the global instruction selector
  -fgnu-keywords          Allow GNU-extension keywords regardless of language standard
  -fgnu-runtime           Generate output compatible with the standard GNU Objective-C runtime
  -fgnu89-inline          Use the gnu89 inline semantics
  -fgnuc-version=<value>  Sets various macros to claim compatibility with the given GCC version (default is 4.2.1)
  -fgpu-allow-device-init Allow device side init function in HIP (experimental)
  -fgpu-defer-diag        Defer host/device related diagnostic messages for CUDA/HIP
  -fgpu-flush-denormals-to-zero
                          Flush denormal floating point values to zero in CUDA/HIP device mode.
  -fgpu-rdc               Generate relocatable device code, also known as separate compilation mode
  -fgpu-sanitize          Enable sanitizer for AMDGPU target
  -fhip-fp32-correctly-rounded-divide-sqrt
                          Specify that single precision floating-point divide and sqrt used in the program source are correctly rounded (HIP device compilation only)
  -fhip-new-launch-api    Use new kernel launching API for HIP
  -fignore-exceptions     Enable support for ignoring exception handling constructs
  -fimplicit-module-maps  Implicitly search the file system for module map files.
  -finline-functions      Inline suitable functions
  -finline-hint-functions Inline functions which are (explicitly or implicitly) marked inline
  -finput-charset=<value> Specify the default character set for source files
  -finstrument-function-entry-bare
                          Instrument function entry only, after inlining, without arguments to the instrumentation call
  -finstrument-functions-after-inlining
                          Like -finstrument-functions, but insert the calls after inlining
  -finstrument-functions  Generate calls to instrument function entry and exit
  -fintegrated-as         Enable the integrated assembler
  -fintegrated-cc1        Run cc1 in-process
  -fjump-tables           Use jump tables for lowering switches
  -fkeep-static-consts    Keep static const variables if unused
  -flax-vector-conversions=<value>
                          Enable implicit vector bit-casts
  -flegacy-pass-manager   Use the legacy pass manager in LLVM (deprecated, to be removed in a future release)
  -flto-jobs=<value>      Controls the backend parallelism of -flto=thin (default of 0 means the number of threads will be derived from the number of CPUs detected)
  -flto=auto              Enable LTO in 'full' mode
  -flto=jobserver         Enable LTO in 'full' mode
  -flto=<value>           Set LTO mode to either 'full' or 'thin'
  -flto                   Enable LTO in 'full' mode
  -fmacro-prefix-map=<value>
                          remap file source paths in predefined preprocessor macros and __builtin_FILE()
  -fmath-errno            Require math functions to indicate errors by setting errno
  -fmax-tokens=<value>    Max total number of preprocessed tokens for -Wmax-tokens.
  -fmax-type-align=<value>
                          Specify the maximum alignment to enforce on pointers lacking an explicit alignment
  -fmemory-profile=<directory>
                          Enable heap memory profiling and dump results into <directory>
  -fmemory-profile        Enable heap memory profiling
  -fmerge-all-constants   Allow merging of constants
  -fmessage-length=<value>
                          Format message diagnostics so that they fit within N columns
  -fminimize-whitespace   Minimize whitespace when emitting preprocessor output
  -fmodule-file=[<name>=]<file>
                          Specify the mapping of module name to precompiled module file, or load a module file if name is omitted.
  -fmodule-map-file=<file>
                          Load this module map file
  -fmodule-name=<name>    Specify the name of the module to build
  -fmodules-cache-path=<directory>
                          Specify the module cache path
  -fmodules-decluse       Require declaration of modules used within a module
  -fmodules-disable-diagnostic-validation
                          Disable validation of the diagnostic options when loading the module
  -fmodules-ignore-macro=<value>
                          Ignore the definition of the given macro when building and loading modules
  -fmodules-prune-after=<seconds>
                          Specify the interval (in seconds) after which a module file will be considered unused
  -fmodules-prune-interval=<seconds>
                          Specify the interval (in seconds) between attempts to prune the module cache
  -fmodules-search-all    Search even non-imported modules to resolve references
  -fmodules-strict-decluse
                          Like -fmodules-decluse but requires all headers to be in modules
  -fmodules-ts            Enable support for the C++ Modules TS
  -fmodules-user-build-path <directory>
                          Specify the module user build path
  -fmodules-validate-input-files-content
                          Validate PCM input files based on content if mtime differs
  -fmodules-validate-once-per-build-session
                          Don't verify input files for the modules if the module has been successfully validated or loaded during this build session
  -fmodules-validate-system-headers
                          Validate the system headers that a module depends on when loading the module
  -fmodules               Enable the 'modules' language feature
  -fms-compatibility-version=<value>
                          Dot-separated value representing the Microsoft compiler version number to report in _MSC_VER (0 = don't define it (default))
  -fms-compatibility      Enable full Microsoft Visual C++ compatibility
  -fms-extensions         Accept some non-standard constructs supported by the Microsoft compiler
  -fms-hotpatch           Ensure that all functions can be hotpatched at runtime
  -fmsc-version=<value>   Microsoft compiler version number to report in _MSC_VER (0 = don't define it (default))
  -fnew-alignment=<align> Specifies the largest alignment guaranteed by '::operator new(size_t)'
  -fnew-infallible        Enable treating throwing global C++ operator new as always returning valid memory (annotates with __attribute__((returns_nonnull)) and throw()). This is detectable in source.
  -fno-aapcs-bitfield-width
                          Do not follow the AAPCS standard requirement stating that volatile bit-field width is dictated by the field container type. (ARM only).
  -fno-access-control     Disable C++ access control
  -fno-addrsig            Don't emit an address-significance table
  -fno-assume-sane-operator-new
                          Don't assume that C++'s global operator new can't alias any pointer
  -fno-autolink           Disable generation of linker directives for automatic library linking
  -fno-builtin-<value>    Disable implicit builtin knowledge of a specific function
  -fno-builtin            Disable implicit builtin knowledge of functions
  -fno-c++-static-destructors
                          Disable C++ static destructor registration
  -fno-char8_t            Disable C++ builtin type char8_t
  -fno-color-diagnostics  Disable colors in diagnostics
  -fno-common             Compile common globals like normal definitions
  -fno-complete-member-pointers
                          Do not require member pointer base types to be complete if they would be significant under the Microsoft ABI
  -fno-constant-cfstrings Disable creation of CodeFoundation-type constant strings
  -fno-coverage-mapping   Disable code coverage analysis
  -fno-crash-diagnostics  Disable auto-generation of preprocessed source files and a script for reproduction during a clang crash
  -fno-cuda-approx-transcendentals
                          Don't use approximate transcendental functions
  -fno-cxx-modules        Disable modules for C++
  -fno-debug-macro        Do not emit macro debug information
  -fno-declspec           Disallow __declspec as a keyword
  -fno-delayed-template-parsing
                          Disable delayed template parsing
  -fno-delete-null-pointer-checks
                          Do not treat usage of null pointers as undefined behavior
  -fno-diagnostics-fixit-info
                          Do not include fixit information in diagnostics
  -fno-digraphs           Disallow alternative token representations '<:', ':>', '<%', '%>', '%:', '%:%:'
  -fno-direct-access-external-data
                          Use GOT indirection to reference external data symbols
  -fno-discard-value-names
                          Do not discard value names in LLVM IR
  -fno-dollars-in-identifiers
                          Disallow '$' in identifiers
  -fno-double-square-bracket-attributes
                          Disable '[[]]' attributes in all C and C++ language modes
  -fno-elide-constructors Disable C++ copy constructor elision
  -fno-elide-type         Do not elide types when printing diagnostics
  -fno-eliminate-unused-debug-types
                          Emit  debug info for defined but unused types
  -fno-exceptions         Disable support for exception handling
  -fno-experimental-relative-c++-abi-vtables
                          Do not use the experimental C++ class ABI for classes with virtual tables
  -fno-fine-grained-bitfield-accesses
                          Use large-integer access for consecutive bitfield runs.
  -fno-finite-loops       Do not assume that any loop is finite.
  -fno-fixed-point        Disable fixed point types
  -fno-force-enable-int128
                          Disable support for int128_t type
  -fno-global-isel        Disables the global instruction selector
  -fno-gnu-inline-asm     Disable GNU style inline asm
  -fno-gpu-allow-device-init
                          Don't allow device side init function in HIP (experimental)
  -fno-gpu-defer-diag     Don't defer host/device related diagnostic messages for CUDA/HIP
  -fno-hip-fp32-correctly-rounded-divide-sqrt
                          Don't specify that single precision floating-point divide and sqrt used in the program source are correctly rounded (HIP device compilation only)
  -fno-hip-new-launch-api Don't use new kernel launching API for HIP
  -fno-integrated-as      Disable the integrated assembler
  -fno-integrated-cc1     Spawn a separate process for each cc1
  -fno-jump-tables        Do not use jump tables for lowering switches
  -fno-keep-static-consts Don't keep static const variables if unused
  -fno-legacy-pass-manager
                          Use the new pass manager in LLVM
  -fno-lto                Disable LTO mode (default)
  -fno-memory-profile     Disable heap memory profiling
  -fno-merge-all-constants
                          Disallow merging of constants
  -fno-new-infallible     Disable treating throwing global C++ operator new as always returning valid memory (annotates with __attribute__((returns_nonnull)) and throw()). This is detectable in source.
  -fno-objc-infer-related-result-type
                          do not infer Objective-C related result type based on method family
  -fno-offload-lto        Disable LTO mode (default) for offload compilation
  -fno-openmp-extensions  Disable all Clang extensions for OpenMP directives and clauses
  -fno-operator-names     Do not treat C++ operator name keywords as synonyms for operators
  -fno-pch-codegen        Do not generate code for uses of this PCH that assumes an explicit object file will be built for the PCH
  -fno-pch-debuginfo      Do not generate debug info for types in an object file built from this PCH and do not generate them elsewhere
  -fno-plt                Use GOT indirection instead of PLT to make external function calls (x86 only)
  -fno-preserve-as-comments
                          Do not preserve comments in inline assembly
  -fno-profile-generate   Disable generation of profile instrumentation.
  -fno-profile-instr-generate
                          Disable generation of profile instrumentation.
  -fno-profile-instr-use  Disable using instrumentation data for profile-guided optimization
  -fno-pseudo-probe-for-profiling
                          Do not emit pseudo probes for sample profiling
  -fno-register-global-dtors-with-atexit
                          Don't use atexit or __cxa_atexit to register global destructors
  -fno-rtlib-add-rpath    Do not add -rpath with architecture-specific resource directory to the linker flags
  -fno-rtti-data          Disable generation of RTTI data
  -fno-rtti               Disable generation of rtti information
  -fno-sanitize-address-outline-instrumentation
                          Use default code inlining logic for the address sanitizer
  -fno-sanitize-address-poison-custom-array-cookie
                          Disable poisoning array cookies when using custom operator new[] in AddressSanitizer
  -fno-sanitize-address-use-after-scope
                          Disable use-after-scope detection in AddressSanitizer
  -fno-sanitize-address-use-odr-indicator
                          Disable ODR indicator globals
  -fno-sanitize-cfi-canonical-jump-tables
                          Do not make the jump table addresses canonical in the symbol table
  -fno-sanitize-cfi-cross-dso
                          Disable control flow integrity (CFI) checks for cross-DSO calls.
  -fno-sanitize-coverage=<value>
                          Disable features of coverage instrumentation for Sanitizers
  -fno-sanitize-hwaddress-experimental-aliasing
                          Disable aliasing mode in HWAddressSanitizer
  -fno-sanitize-ignorelist
                          Don't use ignorelist file for sanitizers
  -fno-sanitize-memory-param-retval
                          Disable detection of uninitialized parameters and return values
  -fno-sanitize-memory-track-origins
                          Disable origins tracking in MemorySanitizer
  -fno-sanitize-memory-use-after-dtor
                          Disable use-after-destroy detection in MemorySanitizer
  -fno-sanitize-recover=<value>
                          Disable recovery for specified sanitizers
  -fno-sanitize-stats     Disable sanitizer statistics gathering.
  -fno-sanitize-thread-atomics
                          Disable atomic operations instrumentation in ThreadSanitizer
  -fno-sanitize-thread-func-entry-exit
                          Disable function entry/exit instrumentation in ThreadSanitizer
  -fno-sanitize-thread-memory-access
                          Disable memory access instrumentation in ThreadSanitizer
  -fno-sanitize-trap=<value>
                          Disable trapping for specified sanitizers
  -fno-sanitize-trap      Disable trapping for all sanitizers
  -fno-short-wchar        Force wchar_t to be an unsigned int
  -fno-show-column        Do not include column number on diagnostics
  -fno-show-source-location
                          Do not include source location information with diagnostics
  -fno-signed-char        char is unsigned
  -fno-signed-zeros       Allow optimizations that ignore the sign of floating point zeros
  -fno-spell-checking     Disable spell-checking
  -fno-split-machine-functions
                          Disable late function splitting using profile information (x86 ELF)
  -fno-split-stack        Wouldn't use segmented stack
  -fno-stack-clash-protection
                          Disable stack clash protection
  -fno-stack-protector    Disable the use of stack protectors
  -fno-standalone-debug   Limit debug information produced to reduce size of debug binary
  -fno-strict-float-cast-overflow
                          Relax language rules and try to match the behavior of the target's native float-to-int conversion instructions
  -fno-strict-return      Don't treat control flow paths that fall off the end of a non-void function as unreachable
  -fno-sycl               Disables SYCL kernels compilation for device
  -fno-temp-file          Directly create compilation output files. This may lead to incorrect incremental builds if the compiler crashes
  -fno-threadsafe-statics Do not emit code to make initialization of local statics thread safe
  -fno-trigraphs          Do not process trigraph sequences
  -fno-unique-section-names
                          Don't use unique names for text and data sections
  -fno-unroll-loops       Turn off loop unroller
  -fno-use-cxa-atexit     Don't use __cxa_atexit for calling destructors
  -fno-use-init-array     Use .ctors/.dtors instead of .init_array/.fini_array
  -fno-visibility-inlines-hidden-static-local-var
                          Disables -fvisibility-inlines-hidden-static-local-var (this is the default on non-darwin targets)
  -fno-xray-function-index
                          Omit function index section at the expense of single-function patching performance
  -fno-zero-initialized-in-bss
                          Don't place zero initialized data in BSS
  -fobjc-arc-exceptions   Use EH-safe code when synthesizing retains and releases in -fobjc-arc
  -fobjc-arc              Synthesize retain and release calls for Objective-C pointers
  -fobjc-disable-direct-methods-for-testing
                          Ignore attribute objc_direct so that direct methods can be tested
  -fobjc-encode-cxx-class-template-spec
                          Fully encode c++ class template specialization
  -fobjc-exceptions       Enable Objective-C exceptions
  -fobjc-runtime=<value>  Specify the target Objective-C runtime kind and version
  -fobjc-weak             Enable ARC-style weak references in Objective-C
  -foffload-lto=<value>   Set LTO mode to either 'full' or 'thin' for offload compilation
  -foffload-lto           Enable LTO in 'full' mode for offload compilation
  -fopenmp-extensions     Enable all Clang extensions for OpenMP directives and clauses
  -fopenmp-implicit-rpath Set rpath on OpenMP executables
  -fopenmp-new-driver     Use the new driver for OpenMP offloading.
  -fopenmp-simd           Emit OpenMP code only for SIMD-based constructs.
  -fopenmp-target-debug   Enable debugging in the OpenMP offloading device RTL
  -fopenmp-target-new-runtime
                          Use the new bitcode library for OpenMP offloading
  -fopenmp-targets=<value>
                          Specify comma-separated list of triples OpenMP offloading targets to be supported
  -fopenmp-version=<value>
                          Set OpenMP version (e.g. 45 for OpenMP 4.5, 50 for OpenMP 5.0). Default value is 50.
  -fopenmp                Parse OpenMP pragmas and generate parallel code.
  -foptimization-record-file=<file>
                          Specify the output name of the file containing the optimization remarks. Implies -fsave-optimization-record. On Darwin platforms, this cannot be used with multiple -arch <arch> options.
  -foptimization-record-passes=<regex>
                          Only include passes which match a specified regular expression in the generated optimization record (by default, include all passes)
  -forder-file-instrumentation
                          Generate instrumented code to collect order file into default.profraw file (overridden by '=' form of option or LLVM_PROFILE_FILE env var)
  -fpack-struct=<value>   Specify the default maximum struct packing alignment
  -fpascal-strings        Recognize and construct Pascal-style string literals
  -fpass-plugin=<dsopath> Load pass plugin from a dynamic shared object file (only with new pass manager).
  -fpatchable-function-entry=<N,M>
                          Generate M NOPs before function entry and N-M NOPs after function entry
  -fpcc-struct-return     Override the default ABI to return all structs on the stack
  -fpch-codegen           Generate code for uses of this PCH that assumes an explicit object file will be built for the PCH
  -fpch-debuginfo         Generate debug info for types in an object file built from this PCH and do not generate them elsewhere
  -fpch-instantiate-templates
                          Instantiate templates already while building a PCH
  -fpch-validate-input-files-content
                          Validate PCH input files based on content if mtime differs
  -fplugin-arg-<name>-<arg>
                          Pass <arg> to plugin <name>
  -fplugin=<dsopath>      Load the named plugin (dynamic shared object)
  -fprebuilt-implicit-modules
                          Look up implicit modules in the prebuilt module path
  -fprebuilt-module-path=<directory>
                          Specify the prebuilt module path
  -fproc-stat-report=<value>
                          Save subprocess statistics to the given file
  -fproc-stat-report<value>
                          Print subprocess statistics
  -fprofile-exclude-files=<value>
                          Instrument only functions from files where names don't match all the regexes separated by a semi-colon
  -fprofile-filter-files=<value>
                          Instrument only functions from files where names match any regex separated by a semi-colon
  -fprofile-generate=<directory>
                          Generate instrumented code to collect execution counts into <directory>/default.profraw (overridden by LLVM_PROFILE_FILE env var)
  -fprofile-generate      Generate instrumented code to collect execution counts into default.profraw (overridden by LLVM_PROFILE_FILE env var)
  -fprofile-instr-generate=<file>
                          Generate instrumented code to collect execution counts into <file> (overridden by LLVM_PROFILE_FILE env var)
  -fprofile-instr-generate
                          Generate instrumented code to collect execution counts into default.profraw file (overridden by '=' form of option or LLVM_PROFILE_FILE env var)
  -fprofile-instr-use=<value>
                          Use instrumentation data for profile-guided optimization
  -fprofile-list=<value>  Filename defining the list of functions/files to instrument
  -fprofile-remapping-file=<file>
                          Use the remappings described in <file> to match the profile data against names in the program
  -fprofile-sample-accurate
                          Specifies that the sample profile is accurate
  -fprofile-sample-use=<value>
                          Enable sample-based profile guided optimizations
  -fprofile-update=<method>
                          Set update method of profile counters (atomic,prefer-atomic,single)
  -fprofile-use=<pathname>
                          Use instrumentation data for profile-guided optimization. If pathname is a directory, it reads from <pathname>/default.profdata. Otherwise, it reads from file <pathname>.
  -fprotect-parens        Determines whether the optimizer honors parentheses when floating-point expressions are evaluated
  -fpseudo-probe-for-profiling
                          Emit pseudo probes for sample profiling
  -freciprocal-math       Allow division operations to be reassociated
  -freg-struct-return     Override the default ABI to return small structs in registers
  -fregister-global-dtors-with-atexit
                          Use atexit or __cxa_atexit to register global destructors
  -frelaxed-template-template-args
                          Enable C++17 relaxed template template argument matching
  -freroll-loops          Turn on loop reroller
  -fropi                  Generate read-only position independent code (ARM only)
  -frtlib-add-rpath       Add -rpath with architecture-specific resource directory to the linker flags
  -frwpi                  Generate read-write position independent code (ARM only)
  -fsanitize-address-destructor=<value>
                          Set destructor type used in ASan instrumentation
  -fsanitize-address-field-padding=<value>
                          Level of field padding for AddressSanitizer
  -fsanitize-address-globals-dead-stripping
                          Enable linker dead stripping of globals in AddressSanitizer
  -fsanitize-address-outline-instrumentation
                          Always generate function calls for address sanitizer instrumentation
  -fsanitize-address-poison-custom-array-cookie
                          Enable poisoning array cookies when using custom operator new[] in AddressSanitizer
  -fsanitize-address-use-after-return=<mode>
                          Select the mode of detecting stack use-after-return in AddressSanitizer: never | runtime (default) | always
  -fsanitize-address-use-after-scope
                          Enable use-after-scope detection in AddressSanitizer
  -fsanitize-address-use-odr-indicator
                          Enable ODR indicator globals to avoid false ODR violation reports in partially sanitized programs at the cost of an increase in binary size
  -fsanitize-blacklist=<value>
                          Alias for -fsanitize-ignorelist=
  -fsanitize-cfi-canonical-jump-tables
                          Make the jump table addresses canonical in the symbol table
  -fsanitize-cfi-cross-dso
                          Enable control flow integrity (CFI) checks for cross-DSO calls.
  -fsanitize-cfi-icall-generalize-pointers
                          Generalize pointers in CFI indirect call type signature checks
  -fsanitize-coverage-allowlist=<value>
                          Restrict sanitizer coverage instrumentation exclusively to modules and functions that match the provided special case list, except the blocked ones
  -fsanitize-coverage-blacklist=<value>
                          Deprecated, use -fsanitize-coverage-ignorelist= instead
  -fsanitize-coverage-ignorelist=<value>
                          Disable sanitizer coverage instrumentation for modules and functions that match the provided special case list, even the allowed ones
  -fsanitize-coverage-whitelist=<value>
                          Deprecated, use -fsanitize-coverage-allowlist= instead
  -fsanitize-coverage=<value>
                          Specify the type of coverage instrumentation for Sanitizers
  -fsanitize-hwaddress-abi=<value>
                          Select the HWAddressSanitizer ABI to target (interceptor or platform, default interceptor). This option is currently unused.
  -fsanitize-hwaddress-experimental-aliasing
                          Enable aliasing mode in HWAddressSanitizer
  -fsanitize-ignorelist=<value>
                          Path to ignorelist file for sanitizers
  -fsanitize-memory-param-retval
                          Enable detection of uninitialized parameters and return values
  -fsanitize-memory-track-origins=<value>
                          Enable origins tracking in MemorySanitizer
  -fsanitize-memory-track-origins
                          Enable origins tracking in MemorySanitizer
  -fsanitize-memory-use-after-dtor
                          Enable use-after-destroy detection in MemorySanitizer
  -fsanitize-recover=<value>
                          Enable recovery for specified sanitizers
  -fsanitize-stats        Enable sanitizer statistics gathering.
  -fsanitize-system-blacklist=<value>
                          Alias for -fsanitize-system-ignorelist=
  -fsanitize-system-ignorelist=<value>
                          Path to system ignorelist file for sanitizers
  -fsanitize-thread-atomics
                          Enable atomic operations instrumentation in ThreadSanitizer (default)
  -fsanitize-thread-func-entry-exit
                          Enable function entry/exit instrumentation in ThreadSanitizer (default)
  -fsanitize-thread-memory-access
                          Enable memory access instrumentation in ThreadSanitizer (default)
  -fsanitize-trap=<value> Enable trapping for specified sanitizers
  -fsanitize-trap         Enable trapping for all sanitizers
  -fsanitize-undefined-strip-path-components=<number>
                          Strip (or keep only, if negative) a given number of path components when emitting check metadata.
  -fsanitize=<check>      Turn on runtime checks for various forms of undefined or suspicious behavior. See user manual for available checks
  -fsave-optimization-record=<format>
                          Generate an optimization record file in a specific format
  -fsave-optimization-record
                          Generate a YAML optimization record file
  -fseh-exceptions        Use SEH style exceptions
  -fshort-enums           Allocate to an enum type only as many bytes as it needs for the declared range of possible values
  -fshort-wchar           Force wchar_t to be a short unsigned int
  -fshow-overloads=<value>
                          Which overload candidates to show when overload resolution fails: best|all; defaults to all
  -fshow-skipped-includes Show skipped includes in -H output.
  -fsigned-char           char is signed
  -fsized-deallocation    Enable C++14 sized global deallocation functions
  -fsjlj-exceptions       Use SjLj style exceptions
  -fslp-vectorize         Enable the superword-level parallelism vectorization passes
  -fsplit-dwarf-inlining  Provide minimal debug info in the object/executable to facilitate online symbolication/stack traces in the absence of .dwo/.dwp files when using Split DWARF
  -fsplit-lto-unit        Enables splitting of the LTO unit
  -fsplit-machine-functions
                          Enable late function splitting using profile information (x86 ELF)
  -fsplit-stack           Use segmented stack
  -fstack-clash-protection
                          Enable stack clash protection
  -fstack-protector-all   Enable stack protectors for all functions
  -fstack-protector-strong
                          Enable stack protectors for some functions vulnerable to stack smashing. Compared to -fstack-protector, this uses a stronger heuristic that includes functions containing arrays of any size (and any type), as well as any calls to alloca or the taking of an address from a local variable
  -fstack-protector       Enable stack protectors for some functions vulnerable to stack smashing. This uses a loose heuristic which considers functions vulnerable if they contain a char (or 8bit integer) array or constant sized calls to alloca , which are of greater size than ssp-buffer-size (default: 8 bytes). All variable sized calls to alloca are considered vulnerable. A function with a stack protector has a guard value added to the stack frame that is checked on function exit. The guard value must be positioned in the stack frame such that a buffer overflow from a vulnerable variable will overwrite the guard value before overwriting the function's return address. The reference stack guard value is stored in a global variable.
  -fstack-size-section    Emit section containing metadata on function stack sizes
  -fstack-usage           Emit .su file containing information on function stack sizes
  -fstandalone-debug      Emit full debug info for all types used by the program
  -fstrict-enums          Enable optimizations based on the strict definition of an enum's value range
  -fstrict-float-cast-overflow
                          Assume that overflowing float-to-int casts are undefined (default)
  -fstrict-vtable-pointers
                          Enable optimizations based on the strict rules for overwriting polymorphic C++ objects
  -fswift-async-fp=<option>
                          Control emission of Swift async extended frame info (option: auto, always, never)
  -fsycl                  Enables SYCL kernels compilation for device
  -fsystem-module         Build this module as a system module. Only used with -emit-module
  -fthin-link-bitcode=<value>
                          Write minimized bitcode to <file> for the ThinLTO thin link only
  -fthinlto-index=<value> Perform ThinLTO importing using provided function summary index
  -ftime-report=<value>   (For new pass manager) "per-pass": one report for each pass; "per-pass-run": one report for each pass invocation
  -ftime-trace-granularity=<value>
                          Minimum time granularity (in microseconds) traced by time profiler
  -ftime-trace            Turn on time profiler. Generates JSON file based on output filename.
  -ftrap-function=<value> Issue call to specified function rather than a trap instruction
  -ftrapv-handler=<function name>
                          Specify the function to be called on overflow
  -ftrapv                 Trap on integer overflow
  -ftrigraphs             Process trigraph sequences
  -ftrivial-auto-var-init-stop-after=<value>
                          Stop initializing trivial automatic stack variables after the specified number of instances
  -ftrivial-auto-var-init=<value>
                          Initialize trivial automatic stack variables: uninitialized (default) | pattern
  -funique-basic-block-section-names
                          Use unique names for basic block sections (ELF Only)
  -funique-internal-linkage-names
                          Uniqueify Internal Linkage Symbol Names by appending the MD5 hash of the module path
  -funroll-loops          Turn on loop unroller
  -fuse-cuid=<value>      Method to generate ID's for compilation units for single source offloading languages CUDA and HIP: 'hash' (ID's generated by hashing file path and command line options) | 'random' (ID's generated as random numbers) | 'none' (disabled). Default is 'hash'. This option will be overridden by option '-cuid=[ID]' if it is specified.
  -fuse-line-directives   Use #line in preprocessed output
  -fvalidate-ast-input-files-content
                          Compute and store the hash of input files used to build an AST. Files with mismatching mtime's are considered valid if both contents is identical
  -fveclib=<value>        Use the given vector functions library
  -fvectorize             Enable the loop vectorization passes
  -fverbose-asm           Generate verbose assembly output
  -fvirtual-function-elimination
                          Enables dead virtual function elimination optimization. Requires -flto=full
  -fvisibility-dllexport=<value>
                          The visibility for dllexport definitions [-fvisibility-from-dllstorageclass]
  -fvisibility-externs-dllimport=<value>
                          The visibility for dllimport external declarations [-fvisibility-from-dllstorageclass]
  -fvisibility-externs-nodllstorageclass=<value>
                          The visibility for external declarations without an explicit DLL dllstorageclass [-fvisibility-from-dllstorageclass]
  -fvisibility-from-dllstorageclass
                          Set the visibility of symbols in the generated code from their DLL storage class
  -fvisibility-global-new-delete-hidden
                          Give global C++ operator new and delete declarations hidden visibility
  -fvisibility-inlines-hidden-static-local-var
                          When -fvisibility-inlines-hidden is enabled, static variables in inline C++ member functions will also be given hidden visibility by default
  -fvisibility-inlines-hidden
                          Give inline C++ member functions hidden visibility by default
  -fvisibility-ms-compat  Give global types 'default' visibility and global functions and variables 'hidden' visibility by default
  -fvisibility-nodllstorageclass=<value>
                          The visibility for defintiions without an explicit DLL export class [-fvisibility-from-dllstorageclass]
  -fvisibility=<value>    Set the default symbol visibility for all global declarations
  -fwasm-exceptions       Use WebAssembly style exceptions
  -fwhole-program-vtables Enables whole-program vtable optimization. Requires -flto
  -fwrapv                 Treat signed integer overflow as two's complement
  -fwritable-strings      Store string literals as writable data
  -fxl-pragma-pack        Enable IBM XL #pragma pack handling
  -fxray-always-emit-customevents
                          Always emit __xray_customevent(...) calls even if the containing function is not always instrumented
  -fxray-always-emit-typedevents
                          Always emit __xray_typedevent(...) calls even if the containing function is not always instrumented
  -fxray-always-instrument= <value>
                          DEPRECATED: Filename defining the whitelist for imbuing the 'always instrument' XRay attribute.
  -fxray-attr-list= <value>
                          Filename defining the list of functions/types for imbuing XRay attributes.
  -fxray-function-groups=<value>
                          Only instrument 1 of N groups
  -fxray-ignore-loops     Don't instrument functions with loops unless they also meet the minimum function size
  -fxray-instruction-threshold= <value>
                          Sets the minimum function size to instrument with XRay
  -fxray-instrumentation-bundle= <value>
                          Select which XRay instrumentation points to emit. Options: all, none, function-entry, function-exit, function, custom. Default is 'all'.  'function' includes both 'function-entry' and 'function-exit'.
  -fxray-instrument       Generate XRay instrumentation sleds on function entry and exit
  -fxray-link-deps        Tells clang to add the link dependencies for XRay.
  -fxray-modes= <value>   List of modes to link in by default into XRay instrumented binaries.
  -fxray-never-instrument= <value>
                          DEPRECATED: Filename defining the whitelist for imbuing the 'never instrument' XRay attribute.
  -fxray-selected-function-group=<value>
                          When using -fxray-function-groups, select which group of functions to instrument. Valid range is 0 to fxray-function-groups - 1
  -fzvector               Enable System z vector language extension
  -F <value>              Add directory to framework include search path
  --gcc-toolchain=<value> Search for GCC installation in the specified directory on targets which commonly use GCC. The directory usually contains 'lib{,32,64}/gcc{,-cross}/$triple' and 'include'. If specified, sysroot is skipped for GCC detection. Note: executables (e.g. ld) used by the compiler are not overridden by the selected GCC installation
  -gcodeview-ghash        Emit type record hashes in a .debug$H section
  -gcodeview              Generate CodeView debug information
  -gdwarf-2               Generate source-level debug information with dwarf version 2
  -gdwarf-3               Generate source-level debug information with dwarf version 3
  -gdwarf-4               Generate source-level debug information with dwarf version 4
  -gdwarf-5               Generate source-level debug information with dwarf version 5
  -gdwarf32               Enables DWARF32 format for ELF binaries, if debug information emission is enabled.
  -gdwarf64               Enables DWARF64 format for ELF binaries, if debug information emission is enabled.
  -gdwarf                 Generate source-level debug information with the default dwarf version
  -gembed-source          Embed source text in DWARF debug sections
  -gline-directives-only  Emit debug line info directives only
  -gline-tables-only      Emit debug line number tables only
  -gmodules               Generate debug info with external references to clang modules or precompiled headers
  -gno-embed-source       Restore the default behavior of not embedding source text in DWARF debug sections
  -gno-inline-line-tables Don't emit inline line tables.
  --gpu-bundle-output     Bundle output files of HIP device compilation
  --gpu-instrument-lib=<value>
                          Instrument device library for HIP, which is a LLVM bitcode containing __cyg_profile_func_enter and __cyg_profile_func_exit
  --gpu-max-threads-per-block=<value>
                          Default max threads per block for kernel launch bounds for HIP
  -gsplit-dwarf=<value>   Set DWARF fission mode to either 'split' or 'single'
  -gz=<value>             DWARF debug sections compression type
  -G <size>               Put objects of at most <size> bytes into small data section (MIPS / Hexagon)
  -g                      Generate source-level debug information
  --help-hidden           Display help for hidden options
  -help                   Display available options
  --hip-device-lib=<value>
                          HIP device library
  --hip-link              Link clang-offload-bundler bundles for HIP
  --hip-path=<value>      HIP runtime installation path, used for finding HIP version and adding HIP include path.
  --hip-version=<value>   HIP version in the format of major.minor.patch
  --hipspv-pass-plugin=<dsopath>
                          path to a pass plugin for HIP to SPIR-V passes.
  -H                      Show header includes and nesting depth
  -I-                     Restrict all prior -I flags to double-quoted inclusion and remove current directory from include path
  -ibuiltininc            Enable builtin #include directories even when -nostdinc is used before or after -ibuiltininc. Using -nobuiltininc after the option disables it
  -idirafter <value>      Add directory to AFTER include search path
  -iframeworkwithsysroot <directory>
                          Add directory to SYSTEM framework search path, absolute paths are relative to -isysroot
  -iframework <value>     Add directory to SYSTEM framework search path
  -imacros <file>         Include macros from file before parsing
  -include-pch <file>     Include precompiled header file
  -include <file>         Include file before parsing
  -index-header-map       Make the next included directory (-I or -F) an indexer header map
  -iprefix <dir>          Set the -iwithprefix/-iwithprefixbefore prefix
  -iquote <directory>     Add directory to QUOTE include search path
  -isysroot <dir>         Set the system root directory (usually /)
  -isystem-after <directory>
                          Add directory to end of the SYSTEM include search path
  -isystem <directory>    Add directory to SYSTEM include search path
  -ivfsoverlay <value>    Overlay the virtual filesystem described by file over the real file system
  -iwithprefixbefore <dir>
                          Set directory to include search path with prefix
  -iwithprefix <dir>      Set directory to SYSTEM include search path with prefix
  -iwithsysroot <directory>
                          Add directory to SYSTEM include search path, absolute paths are relative to -isysroot
  -I <dir>                Add directory to the end of the list of include search paths
  --libomptarget-amdgcn-bc-path=<value>
                          Path to libomptarget-amdgcn bitcode library
  --libomptarget-nvptx-bc-path=<value>
                          Path to libomptarget-nvptx bitcode library
  -L <dir>                Add directory to library search path
  -mabi=vec-default       Enable the default Altivec ABI on AIX (AIX only). Uses only volatile vector registers.
  -mabi=vec-extabi        Enable the extended Altivec ABI on AIX (AIX only). Uses volatile and nonvolatile vector registers
  -mabicalls              Enable SVR4-style position-independent code (Mips only)
  -maix-struct-return     Return all structs in memory (PPC32 only)
  -malign-branch-boundary=<value>
                          Specify the boundary's size to align branches
  -malign-branch=<value>  Specify types of branches to align
  -malign-double          Align doubles to two words in structs (x86 only)
  -mamdgpu-ieee           Sets the IEEE bit in the expected default floating point  mode register. Floating point opcodes that support exception flag gathering quiet and propagate signaling NaN inputs per IEEE 754-2008. This option changes the ABI. (AMDGPU only)
  -mbackchain             Link stack frames through backchain on System Z
  -mbranch-protection=<value>
                          Enforce targets of indirect branches and function returns
  -mbranches-within-32B-boundaries
                          Align selected branches (fused, jcc, jmp) within 32-byte boundary
  -mcmodel=medany         Equivalent to -mcmodel=medium, compatible with RISC-V gcc.
  -mcmodel=medlow         Equivalent to -mcmodel=small, compatible with RISC-V gcc.
  -mcmse                  Allow use of CMSE (Armv8-M Security Extensions)
  -mcode-object-v3        Legacy option to specify code object ABI V3 (AMDGPU only)
  -mcode-object-version=<version>
                          Specify code object ABI version. Defaults to 3. (AMDGPU only)
  -mcrc                   Allow use of CRC instructions (ARM/Mips only)
  -mcumode                Specify CU wavefront execution mode (AMDGPU only)
  -mdouble=<value>        Force double to be 32 bits or 64 bits
  -MD                     Write a depfile containing user and system headers
  -meabi <value>          Set EABI type, e.g. 4, 5 or gnu (default depends on triple)
  -membedded-data         Place constants in the .rodata section instead of the .sdata section even if they meet the -G <size> threshold (MIPS)
  -menable-experimental-extensions
                          Enable use of experimental RISC-V extensions.
  -menable-unsafe-fp-math Allow unsafe floating-point math optimizations which may decrease precision
  -mexec-model=<value>    Execution model (WebAssembly only)
  -mexecute-only          Disallow generation of data access to code sections (ARM only)
  -mextern-sdata          Assume that externally defined data is in the small data if it meets the -G <size> threshold (MIPS)
  -mfentry                Insert calls to fentry at function entry (x86/SystemZ only)
  -mfix-cmse-cve-2021-35465
                          Work around VLLDM erratum CVE-2021-35465 (ARM only)
  -mfix-cortex-a53-835769 Workaround Cortex-A53 erratum 835769 (AArch64 only)
  -mfp32                  Use 32-bit floating point registers (MIPS only)
  -mfp64                  Use 64-bit floating point registers (MIPS only)
  -MF <file>              Write depfile output from -MMD, -MD, -MM, or -M to <file>
  -mgeneral-regs-only     Generate code which only uses the general purpose registers (AArch64/x86 only)
  -mglobal-merge          Enable merging of globals
  -mgpopt                 Use GP relative accesses for symbols known to be in a small data section (MIPS)
  -MG                     Add missing headers to depfile
  -mharden-sls=<value>    Select straight-line speculation hardening scope
  -mhvx-ieee-fp           Enable Hexagon HVX IEEE floating-point
  -mhvx-length=<value>    Set Hexagon Vector Length
  -mhvx-qfloat            Enable Hexagon HVX QFloat instructions
  -mhvx=<value>           Enable Hexagon Vector eXtensions
  -mhvx                   Enable Hexagon Vector eXtensions
  -miamcu                 Use Intel MCU ABI
  -mibt-seal              Optimize fcf-protection=branch/full (requires LTO).
  -mignore-xcoff-visibility
                          Not emit the visibility attribute for asm in AIX OS or give all symbols 'unspecified' visibility in XCOFF object file
  --migrate               Run the migrator
  -mincremental-linker-compatible
                          (integrated-as) Emit an object file which can be used with an incremental linker
  -mindirect-jump=<value> Change indirect jump instructions to inhibit speculation
  -mios-version-min=<value>
                          Set iOS deployment target
  -MJ <value>             Write a compilation database entry per input
  -mllvm <value>          Additional arguments to forward to LLVM's option processing
  -mlocal-sdata           Extend the -G behaviour to object local data (MIPS)
  -mlong-calls            Generate branches with extended addressability, usually via indirect jumps.
  -mlong-double-128       Force long double to be 128 bits
  -mlong-double-64        Force long double to be 64 bits
  -mlong-double-80        Force long double to be 80 bits, padded to 128 bits for storage
  -mlvi-cfi               Enable only control-flow mitigations for Load Value Injection (LVI)
  -mlvi-hardening         Enable all mitigations for Load Value Injection (LVI)
  -mmacosx-version-min=<value>
                          Set Mac OS X deployment target
  -mmadd4                 Enable the generation of 4-operand madd.s, madd.d and related instructions.
  -mmark-bti-property     Add .note.gnu.property with BTI to assembly files (AArch64 only)
  -MMD                    Write a depfile containing user headers
  -mmemops                Enable generation of memop instructions
  -mms-bitfields          Set the default structure layout to be compatible with the Microsoft compiler standard
  -mmsa                   Enable MSA ASE (MIPS only)
  -mmt                    Enable MT ASE (MIPS only)
  -MM                     Like -MMD, but also implies -E and writes to stdout by default
  -mno-abicalls           Disable SVR4-style position-independent code (Mips only)
  -mno-bti-at-return-twice
                          Do not add a BTI instruction after a setjmp or other return-twice construct (Arm/AArch64 only)
  -mno-code-object-v3     Legacy option to specify code object ABI V2 (AMDGPU only)
  -mno-crc                Disallow use of CRC instructions (Mips only)
  -mno-cumode             Specify WGP wavefront execution mode (AMDGPU only)
  -mno-embedded-data      Do not place constants in the .rodata section instead of the .sdata if they meet the -G <size> threshold (MIPS)
  -mno-execute-only       Allow generation of data access to code sections (ARM only)
  -mno-extern-sdata       Do not assume that externally defined data is in the small data if it meets the -G <size> threshold (MIPS)
  -mno-fix-cmse-cve-2021-35465
                          Don't work around VLLDM erratum CVE-2021-35465 (ARM only)
  -mno-fix-cortex-a53-835769
                          Don't workaround Cortex-A53 erratum 835769 (AArch64 only)
  -mno-global-merge       Disable merging of globals
  -mno-gpopt              Do not use GP relative accesses for symbols known to be in a small data section (MIPS)
  -mno-hvx-ieee-fp        Disable Hexagon HVX IEEE floating-point
  -mno-hvx-qfloat         Disable Hexagon HVX QFloat instructions
  -mno-hvx                Disable Hexagon Vector eXtensions
  -mno-implicit-float     Don't generate implicit floating point instructions
  -mno-incremental-linker-compatible
                          (integrated-as) Emit an object file which cannot be used with an incremental linker
  -mno-local-sdata        Do not extend the -G behaviour to object local data (MIPS)
  -mno-long-calls         Restore the default behaviour of not generating long calls
  -mno-lvi-cfi            Disable control-flow mitigations for Load Value Injection (LVI)
  -mno-lvi-hardening      Disable mitigations for Load Value Injection (LVI)
  -mno-madd4              Disable the generation of 4-operand madd.s, madd.d and related instructions.
  -mno-memops             Disable generation of memop instructions
  -mno-movt               Disallow use of movt/movw pairs (ARM only)
  -mno-ms-bitfields       Do not set the default structure layout to be compatible with the Microsoft compiler standard
  -mno-msa                Disable MSA ASE (MIPS only)
  -mno-mt                 Disable MT ASE (MIPS only)
  -mno-neg-immediates     Disallow converting instructions with negative immediates to their negation or inversion.
  -mno-nvj                Disable generation of new-value jumps
  -mno-nvs                Disable generation of new-value stores
  -mno-outline-atomics    Don't generate local calls to out-of-line atomic operations
  -mno-outline            Disable function outlining (AArch64 only)
  -mno-packets            Disable generation of instruction packets
  -mno-relax              Disable linker relaxation
  -mno-restrict-it        Allow generation of deprecated IT blocks for ARMv8. It is off by default for ARMv8 Thumb mode
  -mno-save-restore       Disable using library calls for save and restore
  -mno-seses              Disable speculative execution side effect suppression (SESES)
  -mno-stack-arg-probe    Disable stack probes which are enabled by default
  -mno-tgsplit            Disable threadgroup split execution mode (AMDGPU only)
  -mno-tls-direct-seg-refs
                          Disable direct TLS access through segment registers
  -mno-unaligned-access   Force all memory accesses to be aligned (AArch32/AArch64 only)
  -mno-wavefrontsize64    Specify wavefront size 32 mode (AMDGPU only)
  -mnocrc                 Disallow use of CRC instructions (ARM only)
  -mnop-mcount            Generate mcount/__fentry__ calls as nops. To activate they need to be patched in.
  -mnvj                   Enable generation of new-value jumps
  -mnvs                   Enable generation of new-value stores
  -module-dependency-dir <value>
                          Directory to dump module dependencies to
  -module-file-info       Provide information about a particular module file
  -momit-leaf-frame-pointer
                          Omit frame pointer setup for leaf functions
  -moutline-atomics       Generate local calls to out-of-line atomic operations
  -moutline               Enable function outlining (AArch64 only)
  -mpacked-stack          Use packed stack layout (SystemZ only).
  -mpackets               Enable generation of instruction packets
  -mpad-max-prefix-size=<value>
                          Specify maximum number of prefixes to use for padding
  -mprefer-vector-width=<value>
                          Specifies preferred vector width for auto-vectorization. Defaults to 'none' which allows target specific decisions.
  -MP                     Create phony target for each dependency (other than main file)
  -mqdsp6-compat          Enable hexagon-qdsp6 backward compatibility
  -MQ <value>             Specify name of main file output to quote in depfile
  -mrecord-mcount         Generate a __mcount_loc section entry for each __fentry__ call.
  -mrelax-all             (integrated-as) Relax all machine instructions
  -mrelax                 Enable linker relaxation
  -mrestrict-it           Disallow generation of deprecated IT blocks for ARMv8. It is on by default for ARMv8 Thumb mode.
  -mrtd                   Make StdCall calling convention the default
  -msave-restore          Enable using library calls for save and restore
  -mseses                 Enable speculative execution side effect suppression (SESES). Includes LVI control flow integrity mitigations
  -msign-return-address=<value>
                          Select return address signing scope
  -mskip-rax-setup        Skip setting up RAX register when passing variable arguments (x86 only)
  -msmall-data-limit=<value>
                          Put global and static data smaller than the limit into a special section
  -msoft-float            Use software floating point
  -mstack-alignment=<value>
                          Set the stack alignment
  -mstack-arg-probe       Enable stack probes
  -mstack-probe-size=<value>
                          Set the stack probe size
  -mstack-protector-guard-offset=<value>
                          Use the given offset for addressing the stack-protector guard
  -mstack-protector-guard-reg=<value>
                          Use the given reg for addressing the stack-protector guard
  -mstack-protector-guard=<value>
                          Use the given guard (global, tls) for addressing the stack-protector guard
  -mstackrealign          Force realign the stack at entry to every function
  -msve-vector-bits=<value>
                          Specify the size in bits of an SVE vector register. Defaults to the vector length agnostic value of "scalable". (AArch64 only)
  -msvr4-struct-return    Return small structs in registers (PPC32 only)
  -mtargetos=<value>      Set the deployment target to be the specified OS and OS version
  -mtgsplit               Enable threadgroup split execution mode (AMDGPU only)
  -mthread-model <value>  The thread model to use, e.g. posix, single (posix by default)
  -mtls-direct-seg-refs   Enable direct TLS access through segment registers (default)
  -mtls-size=<value>      Specify bit size of immediate TLS offsets (AArch64 ELF only): 12 (for 4KB) | 24 (for 16MB, default) | 32 (for 4GB) | 48 (for 256TB, needs -mcmodel=large)
  -mtp=<value>            Thread pointer access method (AArch32/AArch64 only)
  -mtune=<value>          Only supported on X86 and RISC-V. Otherwise accepted for compatibility with GCC.
  -MT <value>             Specify name of main file output in depfile
  -munaligned-access      Allow memory accesses to be unaligned (AArch32/AArch64 only)
  -munsafe-fp-atomics     Enable unsafe floating point atomic instructions (AMDGPU only)
  -mvscale-max=<value>    Specify the vscale maximum. Defaults to the vector length agnostic value of "0". (AArch64 only)
  -mvscale-min=<value>    Specify the vscale minimum. Defaults to "1". (AArch64 only)
  -MV                     Use NMake/Jom format for the depfile
  -mwavefrontsize64       Specify wavefront size 64 mode (AMDGPU only)
  -M                      Like -MD, but also implies -E and writes to stdout by default
  --no-cuda-include-ptx=<value>
                          Do not include PTX for the following GPU architecture (e.g. sm_35) or 'all'. May be specified more than once.
  --no-cuda-version-check Don't error out if the detected version of the CUDA install is too low for the requested CUDA gpu architecture.
  --no-gpu-bundle-output  Do not bundle output files of HIP device compilation
  --no-offload-arch=<value>
                          Remove CUDA/HIP offloading device architecture (e.g. sm_35, gfx906) from the list of devices to compile for. 'all' resets the list to its default value.
  --no-system-header-prefix=<prefix>
                          Treat all #include paths starting with <prefix> as not including a system header.
  -nobuiltininc           Disable builtin #include directories
  -nogpuinc               Do not add include paths for CUDA/HIP and do not include the default CUDA/HIP wrapper headers
  -nogpulib               Do not link device library for CUDA/HIP device compilation
  -nohipwrapperinc        Do not include the default HIP wrapper headers and include paths
  -nostdinc++             Disable standard #include directories for the C++ standard library
  -ObjC++                 Treat source input files as Objective-C++ inputs
  -objcmt-allowlist-dir-path=<value>
                          Only modify files with a filename contained in the provided directory path
  -objcmt-atomic-property Make migration to 'atomic' properties
  -objcmt-migrate-all     Enable migration to modern ObjC
  -objcmt-migrate-annotation
                          Enable migration to property and method annotations
  -objcmt-migrate-designated-init
                          Enable migration to infer NS_DESIGNATED_INITIALIZER for initializer methods
  -objcmt-migrate-instancetype
                          Enable migration to infer instancetype for method result type
  -objcmt-migrate-literals
                          Enable migration to modern ObjC literals
  -objcmt-migrate-ns-macros
                          Enable migration to NS_ENUM/NS_OPTIONS macros
  -objcmt-migrate-property-dot-syntax
                          Enable migration of setter/getter messages to property-dot syntax
  -objcmt-migrate-property
                          Enable migration to modern ObjC property
  -objcmt-migrate-protocol-conformance
                          Enable migration to add protocol conformance on classes
  -objcmt-migrate-readonly-property
                          Enable migration to modern ObjC readonly property
  -objcmt-migrate-readwrite-property
                          Enable migration to modern ObjC readwrite property
  -objcmt-migrate-subscripting
                          Enable migration to modern ObjC subscripting
  -objcmt-ns-nonatomic-iosonly
                          Enable migration to use NS_NONATOMIC_IOSONLY macro for setting property's 'atomic' attribute
  -objcmt-returns-innerpointer-property
                          Enable migration to annotate property with NS_RETURNS_INNER_POINTER
  -objcmt-whitelist-dir-path=<value>
                          Alias for -objcmt-allowlist-dir-path
  -ObjC                   Treat source input files as Objective-C inputs
  -object-file-name=<file>
                          Set the output <file> for debug infos
  --offload-arch=<value>  CUDA offloading device architecture (e.g. sm_35), or HIP offloading target ID in the form of a device architecture followed by target ID features delimited by a colon. Each target ID feature is a pre-defined string followed by a plus or minus sign (e.g. gfx908:xnack+:sramecc-).  May be specified more than once.
  --offload=<value>       Specify comma-separated list of offloading target triples (CUDA and HIP only)
  -o <file>               Write output to <file>
  -pedantic               Warn on language extensions
  -pg                     Enable mcount instrumentation
  -pipe                   Use pipes between commands, when possible
  --precompile            Only precompile the input
  -print-effective-triple Print the effective target triple
  -print-file-name=<file> Print the full library path of <file>
  -print-ivar-layout      Enable Objective-C Ivar layout bitmap print trace
  -print-libgcc-file-name Print the library path for the currently used compiler runtime library ("libgcc.a" or "libclang_rt.builtins.*.a")
  -print-multiarch        Print the multiarch target triple
  -print-prog-name=<name> Print the full program path of <name>
  -print-resource-dir     Print the resource directory pathname
  -print-rocm-search-dirs Print the paths used for finding ROCm installation
  -print-runtime-dir      Print the directory pathname containing clangs runtime libraries
  -print-search-dirs      Print the paths used for finding libraries and programs
  -print-supported-cpus   Print supported cpu models for the given target (if target is not specified, it will print the supported cpus for the default target)
  -print-target-triple    Print the normalized target triple
  -print-targets          Print the registered targets
  -pthread                Support POSIX threads in generated code
  --ptxas-path=<value>    Path to ptxas (used for compiling CUDA code)
  -P                      Disable linemarker output in -E mode
  -Qn                     Do not emit metadata containing compiler name and version
  -Qunused-arguments      Don't emit warning for unused driver arguments
  -Qy                     Emit metadata containing compiler name and version
  -relocatable-pch        Whether to build a relocatable precompiled header
  -rewrite-legacy-objc    Rewrite Legacy Objective-C source to C++
  -rewrite-objc           Rewrite Objective-C source to C++
  --rocm-device-lib-path=<value>
                          ROCm device library path. Alternative to rocm-path.
  --rocm-path=<value>     ROCm installation path, used for finding and automatically linking required bitcode libraries.
  -Rpass-analysis=<value> Report transformation analysis from optimization passes whose name matches the given POSIX regular expression
  -Rpass-missed=<value>   Report missed transformations by optimization passes whose name matches the given POSIX regular expression
  -Rpass=<value>          Report transformations performed by optimization passes whose name matches the given POSIX regular expression
  -rtlib=<value>          Compiler runtime library to use
  -R<remark>              Enable the specified remark
  -save-stats=<value>     Save llvm statistics.
  -save-stats             Save llvm statistics.
  -save-temps=<value>     Save intermediate compilation results.
  -save-temps             Save intermediate compilation results
  -serialize-diagnostics <value>
                          Serialize compiler diagnostics to a file
  -shared-libsan          Dynamically link the sanitizer runtime
  --start-no-unused-arguments
                          Don't emit warnings about unused arguments for the following arguments
  -static-libsan          Statically link the sanitizer runtime
  -static-openmp          Use the static host OpenMP runtime while linking.
  -std=<value>            Language standard to compile for
  -stdlib++-isystem <directory>
                          Use directory as the C++ standard library include path
  -stdlib=<value>         C++ standard library to use
  -sycl-std=<value>       SYCL language standard to compile for.
  --system-header-prefix=<prefix>
                          Treat all #include paths starting with <prefix> as including a system header.
  -S                      Only run preprocess and compilation steps
  --target=<value>        Generate code for the given target
  -Tbss <addr>            Set starting address of BSS to <addr>
  -Tdata <addr>           Set starting address of DATA to <addr>
  -time                   Time individual commands
  -traditional-cpp        Enable some traditional CPP emulation
  -trigraphs              Process trigraph sequences
  -Ttext <addr>           Set starting address of TEXT to <addr>
  -T <script>             Specify <script> as linker script
  -undef                  undef all system defines
  -unwindlib=<value>      Unwind library to use
  -U <macro>              Undefine macro <macro>
  --verify-debug-info     Verify the binary representation of debug output
  -verify-pch             Load and verify that a pre-compiled header file is not stale
  --version               Print version information
  -v                      Show commands to run and use verbose output
  -Wa,<arg>               Pass the comma separated arguments in <arg> to the assembler
  -Wdeprecated            Enable warnings for deprecated constructs and define __DEPRECATED
  -Wl,<arg>               Pass the comma separated arguments in <arg> to the linker
  -working-directory <value>
                          Resolve file paths relative to the specified directory
  -Wp,<arg>               Pass the comma separated arguments in <arg> to the preprocessor
  -W<warning>             Enable the specified warning
  -w                      Suppress all warnings
  -Xanalyzer <arg>        Pass <arg> to the static analyzer
  -Xarch_device <arg>     Pass <arg> to the CUDA/HIP device compilation
  -Xarch_host <arg>       Pass <arg> to the CUDA/HIP host compilation
  -Xassembler <arg>       Pass <arg> to the assembler
  -Xclang <arg>           Pass <arg> to the clang compiler
  -Xcuda-fatbinary <arg>  Pass <arg> to fatbinary invocation
  -Xcuda-ptxas <arg>      Pass <arg> to the ptxas assembler
  -Xlinker <arg>          Pass <arg> to the linker
  -Xopenmp-target=<triple> <arg>
                          Pass <arg> to the target offloading toolchain identified by <triple>.
  -Xopenmp-target <arg>   Pass <arg> to the target offloading toolchain.
  -Xpreprocessor <arg>    Pass <arg> to the preprocessor
  -x <language>           Treat subsequent input files as having type <language>
  -z <arg>                Pass -z <arg> to the linker
```

***

#### clang-format <a href="#clang-format" id="clang-format"></a>

Clang-format is both a library and a stand-alone tool with the goal of automatically reformatting C++ sources files according to configurable style guides. To do so, clang-format uses Clang’s Lexer to transform an input file into a token stream and then changes all the whitespace around those tokens. The goal is for clang-format to both serve both as a user tool (ideally with powerful IDE integrations) and part of other refactoring tools, e.g. to do a reformatting of all the lines changed during a renaming.

This is a dependency package providing the clang format tool.

**Installed size:** `28 KB`\
**How to install:** `sudo apt install clang-format`

<details>

<summary>Dependencies:</summary>

* clang-format-14

</details>

**clang-format**

Manual page for clang-format 14

```
:~# clang-format --help
OVERVIEW: A tool to format C/C++/Java/JavaScript/JSON/Objective-C/Protobuf/C# code.

If no arguments are specified, it formats the code from standard input
and writes the result to the standard output.
If <file>s are given, it reformats the files. If -i is specified
together with <file>s, the files are edited in-place. Otherwise, the
result is written to the standard output.

USAGE: clang-format [options] [<file> ...]

OPTIONS:

Clang-format options:

  --Werror                       - If set, changes formatting warnings to errors
  --Wno-error=<value>            - If set don't error out on the specified warning type.
    =unknown                     -   If set, unknown format options are only warned about.
                                     This can be used to enable formatting, even if the
                                     configuration contains unknown (newer) options.
                                     Use with caution, as this might lead to dramatically
                                     differing format depending on an option being
                                     supported or not.
  --assume-filename=<string>     - Override filename used to determine the language.
                                   When reading from stdin, clang-format assumes this
                                   filename to determine the language.
  --cursor=<uint>                - The position of the cursor when invoking
                                   clang-format from an editor integration
  --dry-run                      - If set, do not actually make the formatting changes
  --dump-config                  - Dump configuration options to stdout and exit.
                                   Can be used with -style option.
  --fallback-style=<string>      - The name of the predefined style used as a
                                   fallback in case clang-format is invoked with
                                   -style=file, but can not find the .clang-format
                                   file to use.
                                   Use -fallback-style=none to skip formatting.
  --ferror-limit=<uint>          - Set the maximum number of clang-format errors to emit before stopping (0 = no limit). Used only with --dry-run or -n
  --files=<string>               - Provide a list of files to run clang-format
  -i                             - Inplace edit <file>s, if specified.
  --length=<uint>                - Format a range of this length (in bytes).
                                   Multiple ranges can be formatted by specifying
                                   several -offset and -length pairs.
                                   When only a single -offset is specified without
                                   -length, clang-format will format up to the end
                                   of the file.
                                   Can only be used with one input file.
  --lines=<string>               - <start line>:<end line> - format a range of
                                   lines (both 1-based).
                                   Multiple ranges can be formatted by specifying
                                   several -lines arguments.
                                   Can't be used with -offset and -length.
                                   Can only be used with one input file.
  -n                             - Alias for --dry-run
  --offset=<uint>                - Format a range starting at this byte offset.
                                   Multiple ranges can be formatted by specifying
                                   several -offset and -length pairs.
                                   Can only be used with one input file.
  --output-replacements-xml      - Output replacements as XML.
  --qualifier-alignment=<string> - If set, overrides the qualifier alignment style determined by the QualifierAlignment style flag
  --sort-includes                - If set, overrides the include sorting behavior determined by the SortIncludes style flag
  --style=<string>               - Coding style, currently supports:
                                     LLVM, GNU, Google, Chromium, Microsoft, Mozilla, WebKit.
                                   Use -style=file to load style configuration from
                                   .clang-format file located in one of the parent
                                   directories of the source file (or current
                                   directory for stdin).
                                   Use -style=file:<format_file_path> to explicitly specifythe configuration file.
                                   Use -style="{key: value, ...}" to set specific
                                   parameters, e.g.:
                                     -style="{BasedOnStyle: llvm, IndentWidth: 8}"
  --verbose                      - If set, shows the list of processed files

Generic Options:

  --help                         - Display available options (--help-hidden for more)
  --help-list                    - Display list of available options (--help-list-hidden for more)
  --version                      - Display the version of this program
```

***

**clang-format-diff**

Manual page for clang-format-diff.py 14

```
:~# clang-format-diff -h
usage: clang-format-diff [-h] [-i] [-p NUM] [-regex PATTERN] [-iregex PATTERN]
                         [-sort-includes] [-v] [-style STYLE]
                         [-fallback-style FALLBACK_STYLE] [-binary BINARY]

This script reads input from a unified diff and reformats all the changed
lines. This is useful to reformat all the lines touched by a specific patch.
Example usage for git/svn users:

  git diff -U0 --no-color --relative HEAD^ | clang-format-diff.py -p1 -i
  svn diff --diff-cmd=diff -x-U0 | clang-format-diff.py -i

It should be noted that the filename contained in the diff is used unmodified
to determine the source file to update. Users calling this script directly
should be careful to ensure that the path in the diff is correct relative to the
current working directory.

options:
  -h, --help            show this help message and exit
  -i                    apply edits to files instead of displaying a diff
  -p NUM                strip the smallest prefix containing P slashes
  -regex PATTERN        custom pattern selecting file paths to reformat (case
                        sensitive, overrides -iregex)
  -iregex PATTERN       custom pattern selecting file paths to reformat (case
                        insensitive, overridden by -regex)
  -sort-includes        let clang-format sort include blocks
  -v, --verbose         be more verbose, ineffective without -i
  -style STYLE          formatting style to apply (LLVM, GNU, Google,
                        Chromium, Microsoft, Mozilla, WebKit)
  -fallback-style FALLBACK_STYLE
                        The name of the predefined style used as afallback in
                        case clang-format is invoked with-style=file, but can
                        not find the .clang-formatfile to use.
  -binary BINARY        location of binary to use for clang-format
```

***

**git-clang-format**

```
:~# git-clang-format -h
usage: git clang-format [OPTIONS] [<commit>] [<commit>|--staged] [--] [<file>...]

If zero or one commits are given, run clang-format on all lines that differ
between the working directory and <commit>, which defaults to HEAD.  Changes are
only applied to the working directory, or in the stage/index.

If two commits are given (requires --diff), run clang-format on all lines in the
second <commit> that differ from the first <commit>.

The following git-config settings set the default of the corresponding option:
  clangFormat.binary
  clangFormat.commit
  clangFormat.extensions
  clangFormat.style

positional arguments:
  <commit>              revision from which to compute the diff
  <file>...             if specified, only consider differences in these files

options:
  -h, --help            show this help message and exit
  --binary BINARY       path to clang-format
  --commit COMMIT       default commit to use if none is specified
  --diff                print a diff instead of applying the changes
  --diffstat            print a diffstat instead of applying the changes
  --extensions EXTENSIONS
                        comma-separated list of file extensions to format,
                        excluding the period and case-insensitive
  -f, --force           allow changes to unstaged files
  -p, --patch           select hunks interactively
  -q, --quiet           print less information
  --staged, --cached    format lines in the stage instead of the working dir
  --style STYLE         passed to clang-format
  -v, --verbose         print extra information
```

***

#### clang-tidy <a href="#clang-tidy" id="clang-tidy"></a>

Provide an extensible framework for diagnosing and fixing typical programming errors, like style violations, interface misuse, or bugs that can be deduced via static analysis. clang-tidy is modular and provides a convenient interface for writing new checks.

clang-tidy replaces clang-modernize

This is a dependency package providing the clang tidy tool.

**Installed size:** `20 KB`\
**How to install:** `sudo apt install clang-tidy`

<details>

<summary>Dependencies:</summary>

* clang-tidy-14

</details>

**clang-tidy**

Manual page for clang-tidy 14

```
:~# clang-tidy -h
USAGE: clang-tidy [options] <source0> [... <sourceN>]

OPTIONS:

Generic Options:

  --help                         - Display available options (--help-hidden for more)
  --help-list                    - Display list of available options (--help-list-hidden for more)
  --version                      - Display the version of this program

clang-tidy options:

  --checks=<string>              - 
                                   Comma-separated list of globs with optional '-'
                                   prefix. Globs are processed in order of
                                   appearance in the list. Globs without '-'
                                   prefix add checks with matching names to the
                                   set, globs with the '-' prefix remove checks
                                   with matching names from the set of enabled
                                   checks. This option's value is appended to the
                                   value of the 'Checks' option in .clang-tidy
                                   file, if any.
  --config=<string>              - 
                                   Specifies a configuration in YAML/JSON format:
                                     -config="{Checks: '*',
                                               CheckOptions: [{key: x,
                                                               value: y}]}"
                                   When the value is empty, clang-tidy will
                                   attempt to find a file named .clang-tidy for
                                   each source file in its parent directories.
  --config-file=<string>         - 
                                   Specify the path of .clang-tidy or custom config file:
                                    e.g. --config-file=/some/path/myTidyConfigFile
                                   This option internally works exactly the same way as
                                    --config option after reading specified config file.
                                   Use either --config-file or --config, not both.
  --dump-config                  - 
                                   Dumps configuration in the YAML format to
                                   stdout. This option can be used along with a
                                   file name (and '--' if the file is outside of a
                                   project with configured compilation database).
                                   The configuration used for this file will be
                                   printed.
                                   Use along with -checks=* to include
                                   configuration of all checks.
  --enable-check-profile         - 
                                   Enable per-check timing profiles, and print a
                                   report to stderr.
  --explain-config               - 
                                   For each enabled check explains, where it is
                                   enabled, i.e. in clang-tidy binary, command
                                   line or a specific configuration file.
  --export-fixes=<filename>      - 
                                   YAML file to store suggested fixes in. The
                                   stored fixes can be applied to the input source
                                   code with clang-apply-replacements.
  --extra-arg=<string>           - Additional argument to append to the compiler command line
  --extra-arg-before=<string>    - Additional argument to prepend to the compiler command line
  --fix                          - 
                                   Apply suggested fixes. Without -fix-errors
                                   clang-tidy will bail out if any compilation
                                   errors were found.
  --fix-errors                   - 
                                   Apply suggested fixes even if compilation
                                   errors were found. If compiler errors have
                                   attached fix-its, clang-tidy will apply them as
                                   well.
  --fix-notes                    - 
                                   If a warning has no fix, but a single fix can 
                                   be found through an associated diagnostic note, 
                                   apply the fix. 
                                   Specifying this flag will implicitly enable the 
                                   '--fix' flag.
  --format-style=<string>        - 
                                   Style for formatting code around applied fixes:
                                     - 'none' (default) turns off formatting
                                     - 'file' (literally 'file', not a placeholder)
                                       uses .clang-format file in the closest parent
                                       directory
                                     - '{ <json> }' specifies options inline, e.g.
                                       -format-style='{BasedOnStyle: llvm, IndentWidth: 8}'
                                     - 'llvm', 'google', 'webkit', 'mozilla'
                                   See clang-format documentation for the up-to-date
                                   information about formatting styles and options.
                                   This option overrides the 'FormatStyle` option in
                                   .clang-tidy file, if any.
  --header-filter=<string>       - 
                                   Regular expression matching the names of the
                                   headers to output diagnostics from. Diagnostics
                                   from the main file of each translation unit are
                                   always displayed.
                                   Can be used together with -line-filter.
                                   This option overrides the 'HeaderFilterRegex'
                                   option in .clang-tidy file, if any.
  --line-filter=<string>         - 
                                   List of files with line ranges to filter the
                                   warnings. Can be used together with
                                   -header-filter. The format of the list is a
                                   JSON array of objects:
                                     [
                                       {"name":"file1.cpp","lines":[[1,3],[5,7]]},
                                       {"name":"file2.h"}
                                     ]
  --list-checks                  - 
                                   List all enabled checks and exit. Use with
                                   -checks=* to list all available checks.
  --load=<pluginfilename>        - Load the specified plugin
  -p=<string>                    - Build path
  --quiet                        - 
                                   Run clang-tidy in quiet mode. This suppresses
                                   printing statistics about ignored warnings and
                                   warnings treated as errors if the respective
                                   options are specified.
  --store-check-profile=<prefix> - 
                                   By default reports are printed in tabulated
                                   format to stderr. When this option is passed,
                                   these per-TU profiles are instead stored as JSON.
  --system-headers               - Display the errors from system headers.
  --use-color                    - 
                                   Use colors in diagnostics. If not set, colors
                                   will be used if the terminal connected to
                                   standard output supports colors.
                                   This option overrides the 'UseColor' option in
                                   .clang-tidy file, if any.
  --vfsoverlay=<filename>        - 
                                   Overlay the virtual filesystem described by file
                                   over the real file system.
  --warnings-as-errors=<string>  - 
                                   Upgrades warnings to errors. Same format as
                                   '-checks'.
                                   This option's value is appended to the value of
                                   the 'WarningsAsErrors' option in .clang-tidy
                                   file, if any.

-p <build-path> is used to read a compile command database.

	For example, it can be a CMake build directory in which a file named
	compile_commands.json exists (use -DCMAKE_EXPORT_COMPILE_COMMANDS=ON
	CMake option to get this output). When no build path is specified,
	a search for compile_commands.json will be attempted through all
	parent paths of the first input file . See:
	https://clang.llvm.org/docs/HowToSetupToolingForLLVM.html for an
	example of setting up Clang Tooling on a source tree.

<source0> ... specify the paths of source files. These paths are
	looked up in the compile command database. If the path of a file is
	absolute, it needs to point into CMake's source tree. If the path is
	relative, the current working directory needs to be in the CMake
	source tree and the file must be in a subdirectory of the current
	working directory. "./" prefixes in the relative files will be
	automatically removed, but the rest of a relative path must be a
	suffix of a path in the compile command database.


Configuration files:
  clang-tidy attempts to read configuration for each source file from a
  .clang-tidy file located in the closest parent directory of the source
  file. If InheritParentConfig is true in a config file, the configuration file
  in the parent directory (if any exists) will be taken and current config file
  will be applied on top of the parent one. If any configuration options have
  a corresponding command-line option, command-line option takes precedence.
  The effective configuration can be inspected using -dump-config:

    $ clang-tidy -dump-config
    ---
    Checks:              '-*,some-check'
    WarningsAsErrors:    ''
    HeaderFilterRegex:   ''
    FormatStyle:         none
    InheritParentConfig: true
    User:                user
    CheckOptions:
      - key:             some-check.SomeOption
        value:           'some value'
    ...

```

***

**clang-tidy-diff**

```
:~# clang-tidy-diff -h
usage: clang-tidy-diff [-h] [-clang-tidy-binary PATH] [-p NUM]
                       [-regex PATTERN] [-iregex PATTERN] [-j J]
                       [-timeout TIMEOUT] [-fix] [-checks CHECKS] [-use-color]
                       [-path BUILD_PATH] [-export-fixes FILE]
                       [-extra-arg EXTRA_ARG]
                       [-extra-arg-before EXTRA_ARG_BEFORE] [-quiet]

Run clang-tidy against changed files, and output diagnostics only for modified
lines.

options:
  -h, --help            show this help message and exit
  -clang-tidy-binary PATH
                        path to clang-tidy binary
  -p NUM                strip the smallest prefix containing P slashes
  -regex PATTERN        custom pattern selecting file paths to check (case
                        sensitive, overrides -iregex)
  -iregex PATTERN       custom pattern selecting file paths to check (case
                        insensitive, overridden by -regex)
  -j J                  number of tidy instances to be run in parallel.
  -timeout TIMEOUT      timeout per each file in seconds.
  -fix                  apply suggested fixes
  -checks CHECKS        checks filter, when not specified, use clang-tidy
                        default
  -use-color            Use colors in output
  -path BUILD_PATH      Path used to read a compile command database.
  -export-fixes FILE    Create a yaml file to store suggested fixes in, which
                        can be applied with clang-apply-replacements.
  -extra-arg EXTRA_ARG  Additional argument to append to the compiler command
                        line.
  -extra-arg-before EXTRA_ARG_BEFORE
                        Additional argument to prepend to the compiler command
                        line.
  -quiet                Run clang-tidy in quiet mode
```

***

**run-clang-tidy**

```
:~# run-clang-tidy -h
usage: run-clang-tidy [-h] [-allow-enabling-alpha-checkers]
                      [-clang-tidy-binary PATH]
                      [-clang-apply-replacements-binary PATH] [-checks CHECKS]
                      [-config CONFIG] [-header-filter HEADER_FILTER]
                      [-line-filter LINE_FILTER] [-export-fixes filename]
                      [-j J] [-fix] [-format] [-style STYLE] [-p BUILD_PATH]
                      [-extra-arg EXTRA_ARG]
                      [-extra-arg-before EXTRA_ARG_BEFORE] [-quiet]
                      [files ...]

Runs clang-tidy over all files in a compilation database. Requires clang-tidy
and clang-apply-replacements in $PATH.

positional arguments:
  files                 files to be processed (regex on path)

options:
  -h, --help            show this help message and exit
  -allow-enabling-alpha-checkers
                        allow alpha checkers from clang-analyzer.
  -clang-tidy-binary PATH
                        path to clang-tidy binary
  -clang-apply-replacements-binary PATH
                        path to clang-apply-replacements binary
  -checks CHECKS        checks filter, when not specified, use clang-tidy
                        default
  -config CONFIG        Specifies a configuration in YAML/JSON format:
                        -config="{Checks: '*', CheckOptions: [{key: x, value:
                        y}]}" When the value is empty, clang-tidy will attempt
                        to find a file named .clang-tidy for each source file
                        in its parent directories.
  -header-filter HEADER_FILTER
                        regular expression matching the names of the headers
                        to output diagnostics from. Diagnostics from the main
                        file of each translation unit are always displayed.
  -line-filter LINE_FILTER
                        List of files with line ranges to filter thewarnings.
  -export-fixes filename
                        Create a yaml file to store suggested fixes in, which
                        can be applied with clang-apply-replacements.
  -j J                  number of tidy instances to be run in parallel.
  -fix                  apply fix-its
  -format               Reformat code after applying fixes
  -style STYLE          The style of reformat code after applying fixes
  -p BUILD_PATH         Path used to read a compile command database.
  -extra-arg EXTRA_ARG  Additional argument to append to the compiler command
                        line.
  -extra-arg-before EXTRA_ARG_BEFORE
                        Additional argument to prepend to the compiler command
                        line.
  -quiet                Run clang-tidy in quiet mode
```

***

#### clang-tools <a href="#clang-tools" id="clang-tools"></a>

Clang project is a C, C++, Objective C and Objective C++ front-end for the LLVM compiler. Its goal is to offer a replacement to the GNU Compiler Collection (GCC).

Clang implements all of the ISO C++ 1998, 11 and 14 standards and also provides most of the support of C++17.

This is a dependency package providing the clang tools package.

**Installed size:** `26 KB`\
**How to install:** `sudo apt install clang-tools`

<details>

<summary>Dependencies:</summary>

* clang-tools-14

</details>

**c-index-test**

```
:~# c-index-test -h
usage: c-index-test -code-completion-at=<site> <compiler arguments>
       c-index-test -code-completion-timing=<site> <compiler arguments>
       c-index-test -cursor-at=<site> <compiler arguments>
       c-index-test -evaluate-cursor-at=<site> <compiler arguments>
       c-index-test -get-macro-info-cursor-at=<site> <compiler arguments>
       c-index-test -file-refs-at=<site> <compiler arguments>
       c-index-test -file-includes-in=<filename> <compiler arguments>
       c-index-test -index-file [-check-prefix=<FileCheck prefix>] <compiler arguments>
       c-index-test -index-file-full [-check-prefix=<FileCheck prefix>] <compiler arguments>
       c-index-test -index-tu [-check-prefix=<FileCheck prefix>] <AST file>
       c-index-test -index-compile-db [-check-prefix=<FileCheck prefix>] <compilation database>
       c-index-test -test-file-scan <AST file> <source file> [FileCheck prefix]
       c-index-test -test-load-tu <AST file> <symbol filter> [FileCheck prefix]
       c-index-test -test-load-tu-usrs <AST file> <symbol filter> [FileCheck prefix]
       c-index-test -test-load-source <symbol filter> {<args>}*
       c-index-test -test-load-source-memory-usage <symbol filter> {<args>}*
       c-index-test -test-load-source-reparse <trials> <symbol filter>           {<args>}*
       c-index-test -test-load-source-usrs <symbol filter> {<args>}*
       c-index-test -test-load-source-usrs-memory-usage <symbol filter> {<args>}*
       c-index-test -test-annotate-tokens=<range> {<args>}*
       c-index-test -test-inclusion-stack-source {<args>}*
       c-index-test -test-inclusion-stack-tu <AST file>
       c-index-test -test-print-linkage-source {<args>}*
       c-index-test -test-print-visibility {<args>}*
       c-index-test -test-print-type {<args>}*
       c-index-test -test-print-type-size {<args>}*
       c-index-test -test-print-bitwidth {<args>}*
       c-index-test -test-print-target-info {<args>}*
       c-index-test -test-print-type-declaration {<args>}*
       c-index-test -print-usr [<CursorKind> {<args>}]*
       c-index-test -print-usr-file <file>
       c-index-test -write-pch <file> <compiler arguments>
       c-index-test -compilation-db [lookup <filename>] database
       c-index-test -print-build-session-timestamp
       c-index-test -read-diagnostics <file>

 <symbol filter> values:
   all - load all symbols, including those from PCH
   local - load all symbols except those in PCH
   category - only load ObjC categories (non-PCH)
   interface - only load ObjC interfaces (non-PCH)
   protocol - only load ObjC protocols (non-PCH)
   function - only load functions (non-PCH)
   typedef - only load typdefs (non-PCH)
   scan-function - scan function bodies (non-PCH)

```

***

**clang-apply-replacements**

Manual page for clang-apply-replacements 14

```
:~# clang-apply-replacements -h
USAGE: clang-apply-replacements [options] <Search Root Directory>

OPTIONS:

Formatting Options:

  --format                   - Enable formatting of code changed by applying replacements.
                               Use -style to choose formatting style.
  --style=<string>           - Coding style, currently supports:
                                 LLVM, GNU, Google, Chromium, Microsoft, Mozilla, WebKit.
                               Use -style=file to load style configuration from
                               .clang-format file located in one of the parent
                               directories of the source file (or current
                               directory for stdin).
                               Use -style=file:<format_file_path> to explicitly specifythe configuration file.
                               Use -style="{key: value, ...}" to set specific
                               parameters, e.g.:
                                 -style="{BasedOnStyle: llvm, IndentWidth: 8}"
  --style-config=<string>    - Path to a directory containing a .clang-format file
                               describing a formatting style to use for formatting
                               code when -style=file.

Generic Options:

  --help                     - Display available options (--help-hidden for more)
  --help-list                - Display list of available options (--help-list-hidden for more)
  --version                  - Display the version of this program

Replacement Options:

  --remove-change-desc-files - Remove the change description files regardless of successful
                               merging/replacing.
```

***

**clang-check**

Manual page for clang-check 14

```
:~# clang-check -h
USAGE: clang-check [options] <source0> [... <sourceN>]

OPTIONS:

Generic Options:

  --help                          - Display available options (--help-hidden for more)
  --help-list                     - Display list of available options (--help-list-hidden for more)
  --version                       - Display the version of this program

clang-check options:

  --analyze                       - Run static analysis engine
  --analyzer-output-path=<string> - Write output to <file>
  --ast-dump                      - Build ASTs and then debug dump them
  --ast-dump-filter=<string>      - Use with -ast-dump or -ast-print to dump/print only AST declaration nodes having a certain substring in a qualified name. Use -ast-list to list all filterable declaration node names.
  --ast-list                      - Build ASTs and print the list of declaration node qualified names
  --ast-print                     - Build ASTs and then pretty-print them
  --extra-arg=<string>            - Additional argument to append to the compiler command line
  --extra-arg-before=<string>     - Additional argument to prepend to the compiler command line
  --fix-what-you-can              - Apply fix-it advice even in the presence of unfixable errors
  --fixit                         - Apply fix-it advice to the input source
  -p=<string>                     - Build path
  --syntax-tree-dump              - dump the syntax tree
  --tokens-dump                   - dump the preprocessed tokens

-p <build-path> is used to read a compile command database.

	For example, it can be a CMake build directory in which a file named
	compile_commands.json exists (use -DCMAKE_EXPORT_COMPILE_COMMANDS=ON
	CMake option to get this output). When no build path is specified,
	a search for compile_commands.json will be attempted through all
	parent paths of the first input file . See:
	https://clang.llvm.org/docs/HowToSetupToolingForLLVM.html for an
	example of setting up Clang Tooling on a source tree.

<source0> ... specify the paths of source files. These paths are
	looked up in the compile command database. If the path of a file is
	absolute, it needs to point into CMake's source tree. If the path is
	relative, the current working directory needs to be in the CMake
	source tree and the file must be in a subdirectory of the current
	working directory. "./" prefixes in the relative files will be
	automatically removed, but the rest of a relative path must be a
	suffix of a path in the compile command database.

	For example, to run clang-check on all files in a subtree of the
	source tree, use:

	  find path/in/subtree -name '*.cpp'|xargs clang-check

	or using a specific build path:

	  find path/in/subtree -name '*.cpp'|xargs clang-check -p build/path

	Note, that path/in/subtree and current directory should follow the
	rules described above.

```

***

**clang-query**

Manual page for clang-query 14

```
:~# clang-query -h
USAGE: clang-query [options] <source0> [... <sourceN>]

OPTIONS:

Generic Options:

  --help                      - Display available options (--help-hidden for more)
  --help-list                 - Display list of available options (--help-list-hidden for more)
  --version                   - Display the version of this program

clang-query options:

  -c=<command>                - Specify command to run
  --extra-arg=<string>        - Additional argument to append to the compiler command line
  --extra-arg-before=<string> - Additional argument to prepend to the compiler command line
  -f=<file>                   - Read commands from file
  -p=<string>                 - Build path
  --preload=<file>            - Preload commands from file and start interactive mode
  --use-color                 - Use colors in detailed AST output. If not set, colors
                                will be used if the terminal connected to
                                standard output supports colors.

-p <build-path> is used to read a compile command database.

	For example, it can be a CMake build directory in which a file named
	compile_commands.json exists (use -DCMAKE_EXPORT_COMPILE_COMMANDS=ON
	CMake option to get this output). When no build path is specified,
	a search for compile_commands.json will be attempted through all
	parent paths of the first input file . See:
	https://clang.llvm.org/docs/HowToSetupToolingForLLVM.html for an
	example of setting up Clang Tooling on a source tree.

<source0> ... specify the paths of source files. These paths are
	looked up in the compile command database. If the path of a file is
	absolute, it needs to point into CMake's source tree. If the path is
	relative, the current working directory needs to be in the CMake
	source tree and the file must be in a subdirectory of the current
	working directory. "./" prefixes in the relative files will be
	automatically removed, but the rest of a relative path must be a
	suffix of a path in the compile command database.

```

***

**sancov**

Manual page for sancov 14

```
:~# sancov -h
OVERVIEW: Sanitizer Coverage Processing Tool (sancov)

  This tool can extract various coverage-related information from: 
  coverage-instrumented binary files, raw .sancov files and their symbolized .symcov version.
  Depending on chosen action the tool expects different input files:
    -print-coverage-pcs     - coverage-instrumented binary files
    -print-coverage         - .sancov files
    <other actions>         - .sancov files & corresponding binary files, .symcov files

USAGE: sancov [options] <action> <binary files...> <.sancov files...> <.symcov files...>

OPTIONS:

Color Options:

  --color                                            - Use colors in output (default=autodetect)

General options:

  --aarch64-neon-syntax=<value>                      - Choose style of NEON code to emit from AArch64 backend:
    =generic                                         -   Emit generic NEON assembly
    =apple                                           -   Emit Apple-style NEON assembly
  --aarch64-use-aa                                   - Enable the use of AA during codegen.
  --abort-on-max-devirt-iterations-reached           - Abort when the max iterations for devirtualization CGSCC repeat pass is reached
  --allow-ginsert-as-artifact                        - Allow G_INSERT to be considered an artifact. Hack around AMDGPU test infinite loops.
  --amdgpu-bypass-slow-div                           - Skip 64-bit divide for dynamic 32-bit values
  --amdgpu-disable-loop-alignment                    - Do not align and prefetch loops
  --amdgpu-disable-power-sched                       - Disable scheduling to minimize mAI power bursts
  --amdgpu-dpp-combine                               - Enable DPP combiner
  --amdgpu-dump-hsa-metadata                         - Dump AMDGPU HSA Metadata
  --amdgpu-enable-flat-scratch                       - Use flat scratch instructions
  --amdgpu-enable-merge-m0                           - Merge and hoist M0 initializations
  --amdgpu-promote-alloca-to-vector-limit=<uint>     - Maximum byte size to consider promote alloca to vector
  --amdgpu-sdwa-peephole                             - Enable SDWA peepholer
  --amdgpu-use-aa-in-codegen                         - Enable the use of AA during codegen.
  --amdgpu-verify-hsa-metadata                       - Verify AMDGPU HSA Metadata
  --amdgpu-vgpr-index-mode                           - Use GPR indexing mode instead of movrel for vector indexing
  --arm-add-build-attributes                         - 
  --arm-implicit-it=<value>                          - Allow conditional instructions outdside of an IT block
    =always                                          -   Accept in both ISAs, emit implicit ITs in Thumb
    =never                                           -   Warn in ARM, reject in Thumb
    =arm                                             -   Accept in ARM, reject in Thumb
    =thumb                                           -   Warn in ARM, emit implicit ITs in Thumb
  --asm-show-inst                                    - Emit internal instruction representation to assembly file
  --atomic-counter-update-promoted                   - Do counter update using atomic fetch add  for promoted counters only
  --atomic-first-counter                             - Use atomic fetch add for first counter in a function (usually the entry counter)
  --blacklist=<string>                               - Blacklist file (sanitizer blacklist format).
  --bounds-checking-single-trap                      - Use one trap block per function
  --cfg-hide-cold-paths=<number>                     - Hide blocks with relative frequency below the given value
  --cfg-hide-deoptimize-paths                        - 
  --cfg-hide-unreachable-paths                       - 
  --cost-kind=<value>                                - Target cost kind
    =throughput                                      -   Reciprocal throughput
    =latency                                         -   Instruction latency
    =code-size                                       -   Code size
    =size-latency                                    -   Code size and latency
  Action (required)
      --print                                           - Print coverage addresses
      --print-coverage-pcs                              - Print coverage instrumentation points addresses.
      --covered-functions                               - Print all covered funcions.
      --not-covered-functions                           - Print all not covered funcions.
      --print-coverage-stats                            - Print coverage statistics.
      --html-report                                     - REMOVED. Use -symbolize & coverage-report-server.py.
      --symbolize                                       - Produces a symbolized JSON report from binary report.
      --merge                                           - Merges reports.
  --debug-info-correlate                             - Use debug info to correlate profiles.
  --debugify-level=<value>                           - Kind of debug info to add
    =locations                                       -   Locations only
    =location+variables                              -   Locations and Variables
  --debugify-quiet                                   - Suppress verbose debugify output
  --demangle                                         - Print demangled function name.
  --disable-i2p-p2i-opt                              - Disables inttoptr/ptrtoint roundtrip optimization
  --disable-promote-alloca-to-lds                    - Disable promote alloca to LDS
  --disable-promote-alloca-to-vector                 - Disable promote alloca to vector
  --do-counter-promotion                             - Do counter register promotion
  --dot-cfg-mssa=<file name for generated dot file>  - file name for generated dot file
  --dwarf-version=<int>                              - Dwarf version
  --dwarf64                                          - Generate debugging info in the 64-bit DWARF format
  --emscripten-cxx-exceptions-allowed=<string>       - The list of function names in which Emscripten-style exception handling is enabled (see emscripten EMSCRIPTEN_CATCHING_ALLOWED options)
  --enable-cse-in-irtranslator                       - Should enable CSE in irtranslator
  --enable-cse-in-legalizer                          - Should enable CSE in Legalizer
  --enable-emscripten-cxx-exceptions                 - WebAssembly Emscripten-style exception handling
  --enable-emscripten-sjlj                           - WebAssembly Emscripten-style setjmp/longjmp handling
  --enable-gvn-hoist                                 - Enable the GVN hoisting pass (default = off)
  --enable-gvn-memdep                                - 
  --enable-gvn-sink                                  - Enable the GVN sinking pass (default = off)
  --enable-load-in-loop-pre                          - 
  --enable-load-pre                                  - 
  --enable-loop-simplifycfg-term-folding             - 
  --enable-name-compression                          - Enable name/filename string compression
  --enable-split-backedge-in-load-pre                - 
  --experimental-debug-variable-locations            - Use experimental new value-tracking variable locations
  --fatal-warnings                                   - Treat warnings as errors
  --fs-profile-debug-bw-threshold=<uint>             - Only show debug message if the source branch weight is greater  than this value.
  --fs-profile-debug-prob-diff-threshold=<uint>      - Only show debug message if the branch probility is greater than this value (in percentage).
  --generate-merged-base-profiles                    - When generating nested context-sensitive profiles, always generate extra base profile for function with all its context profiles merged into it.
  --gpsize=<uint>                                    - Global Pointer Addressing Size.  The default size is 8.
  --hash-based-counter-split                         - Rename counter variable of a comdat function based on cfg hash
  --hot-cold-split                                   - Enable hot-cold splitting pass
  --import-all-index                                 - Import all external functions in index.
  --incremental-linker-compatible                    - When used with filetype=obj, emit an object file which can be used with an incremental linker
  --instcombine-code-sinking                         - Enable code sinking
  --instcombine-guard-widening-window=<uint>         - How wide an instruction window to bypass looking for another guard
  --instcombine-max-iterations=<uint>                - Limit the maximum number of instruction combining iterations
  --instcombine-max-num-phis=<uint>                  - Maximum number phis to handle in intptr/ptrint folding
  --instcombine-maxarray-size=<uint>                 - Maximum array size considered when doing a combine
  --instcombine-negator-enabled                      - Should we attempt to sink negations?
  --instcombine-negator-max-depth=<uint>             - What is the maximal lookup depth when trying to check for viability of negation sinking.
  --instrprof-atomic-counter-update-all              - Make all profile counter updates atomic (for testing only)
  --internalize-public-api-file=<filename>           - A file containing list of symbol names to preserve
  --internalize-public-api-list=<list>               - A list of symbol names to preserve
  --iterative-counter-promotion                      - Allow counter promotion across the whole loop nest.
  --lto-embed-bitcode=<value>                        - Embed LLVM bitcode in object files produced by LTO
    =none                                            -   Do not embed
    =optimized                                       -   Embed after all optimization passes
    =post-merge-pre-opt                              -   Embed post merge, but before optimizations
  --lto-pass-remarks-filter=<regex>                  - Only record optimization remarks from passes whose names match the given regular expression
  --lto-pass-remarks-format=<format>                 - The format used for serializing remarks (default: YAML)
  --lto-pass-remarks-output=<filename>               - Output filename for pass remarks
  --matrix-default-layout=<value>                    - Sets the default matrix layout
    =column-major                                    -   Use column-major layout
    =row-major                                       -   Use row-major layout
  --max-counter-promotions=<int>                     - Max number of allowed counter promotions
  --max-counter-promotions-per-loop=<uint>           - Max number counter promotions per loop to avoid increasing register pressure too much
  --mc-relax-all                                     - When used with filetype=obj, relax all fixups in the emitted object file
  --mcabac                                           - tbd
  --merror-missing-parenthesis                       - Error for missing parenthesis around predicate registers
  --merror-noncontigious-register                    - Error for register names that aren't contigious
  --mhvx                                             - Enable Hexagon Vector eXtensions
  --mhvx=<value>                                     - Enable Hexagon Vector eXtensions
    =v60                                             -   Build for HVX v60
    =v62                                             -   Build for HVX v62
    =v65                                             -   Build for HVX v65
    =v66                                             -   Build for HVX v66
    =v67                                             -   Build for HVX v67
    =v68                                             -   Build for HVX v68
    =v69                                             -   Build for HVX v69
  --mips-compact-branches=<value>                    - MIPS Specific: Compact branch policy.
    =never                                           -   Do not use compact branches if possible.
    =optimal                                         -   Use compact branches where appropriate (default).
    =always                                          -   Always use compact branches if possible.
  --mips16-constant-islands                          - Enable mips16 constant islands.
  --mips16-hard-float                                - Enable mips16 hard float.
  --mir-strip-debugify-only                          - Should mir-strip-debug only strip debug info from debugified modules by default
  --mno-compound                                     - Disable looking for compound instructions for Hexagon
  --mno-fixup                                        - Disable fixing up resolved relocations for Hexagon
  --mno-ldc1-sdc1                                    - Expand double precision loads and stores to their single precision counterparts
  --mno-pairing                                      - Disable looking for duplex instructions for Hexagon
  --mwarn-missing-parenthesis                        - Warn for missing parenthesis around predicate registers
  --mwarn-noncontigious-register                     - Warn for register names that arent contigious
  --mwarn-sign-mismatch                              - Warn for mismatching a signed and unsigned value
  --no-deprecated-warn                               - Suppress all deprecated warnings
  --no-discriminators                                - Disable generation of discriminator information.
  --no-type-check                                    - Suppress type errors (Wasm)
  --no-warn                                          - Suppress all warnings
  --nvptx-sched4reg                                  - NVPTX Specific: schedule for register pressue
  --opaque-pointers                                  - Use opaque pointers
  --poison-checking-function-local                   - Check that returns are non-poison (for testing)
  --print-pipeline-passes                            - Print a '-passes' compatible string describing the pipeline (best-effort only).
  --r600-ir-structurize                              - Use StructurizeCFG IR pass
  --rdf-dump                                         - 
  --rdf-limit=<uint>                                 - 
  --runtime-counter-relocation                       - Enable relocating counters at runtime.
  --safepoint-ir-verifier-print-only                 - 
  --sample-profile-check-record-coverage=<N>         - Emit a warning if less than N% of records in the input profile are matched to the IR.
  --sample-profile-check-sample-coverage=<N>         - Emit a warning if less than N% of samples in the input profile are matched to the IR.
  --sample-profile-max-propagate-iterations=<uint>   - Maximum number of iterations to go through when propagating sample block/edge weights through the CFG.
  --skip-dead-files                                  - Do not list dead source files in reports.
  --skip-ret-exit-block                              - Suppress counter promotion if exit blocks contain ret.
  --speculative-counter-promotion-max-exiting=<uint> - The max number of exiting blocks of a loop to allow  speculative counter promotion
  --speculative-counter-promotion-to-loop            - When the option is false, if the target block is in a loop, the promotion will be disallowed unless the promoted counter  update can be further/iteratively promoted into an acyclic  region.
  --strip_path_prefix=<string>                       - Strip this prefix from file paths in reports.
  --summary-file=<string>                            - The summary file to use for function importing.
  --tail-predication=<value>                         - MVE tail-predication pass options
    =disabled                                        -   Don't tail-predicate loops
    =enabled-no-reductions                           -   Enable tail-predication, but not for reduction loops
    =enabled                                         -   Enable tail-predication, including reduction loops
    =force-enabled-no-reductions                     -   Enable tail-predication, but not for reduction loops, and force this which might be unsafe
    =force-enabled                                   -   Enable tail-predication, including reduction loops, and force this which might be unsafe
  --thinlto-assume-merged                            - Assume the input has already undergone ThinLTO function importing and the other pre-optimization pipeline changes.
  --threads=<int>                                    - 
  --verify-region-info                               - Verify region info (time consuming)
  --vp-counters-per-site=<number>                    - The average number of profile counters allocated per value profiling site.
  --vp-static-alloc                                  - Do static counter allocation for value profiler
  --wasm-enable-eh                                   - WebAssembly exception handling
  --wasm-enable-sjlj                                 - WebAssembly setjmp/longjmp handling
  --x86-align-branch=<string>                        - Specify types of branches to align (plus separated list of types):
                                                       jcc      indicates conditional jumps
                                                       fused    indicates fused conditional jumps
                                                       jmp      indicates direct unconditional jumps
                                                       call     indicates direct and indirect calls
                                                       ret      indicates rets
                                                       indirect indicates indirect unconditional jumps
  --x86-align-branch-boundary=<uint>                 - Control how the assembler should align branches with NOP. If the boundary's size is not 0, it should be a power of 2 and no less than 32. Branches will be aligned to prevent from being across or against the boundary of specified size. The default value 0 does not align branches.
  --x86-branches-within-32B-boundaries               - Align selected instructions to mitigate negative performance impact of Intel's micro code update for errata skx102.  May break assumptions about labels corresponding to particular instructions, and should be used with caution.
  --x86-pad-max-prefix-size=<uint>                   - Maximum number of prefixes to use for padding

Generic Options:

  --help                                             - Display available options (--help-hidden for more)
  --help-list                                        - Display list of available options (--help-list-hidden for more)
  --version                                          - Display the version of this program

Polly Options:
Configure the polly loop optimizer

  --polly                                            - Enable the polly optimizer (with -O1, -O2 or -O3)
  --polly-2nd-level-tiling                           - Enable a 2nd level loop of loop tiling
  --polly-ast-print-accesses                         - Print memory access functions
  --polly-context=<isl parameter set>                - Provide additional constraints on the context parameters
  --polly-dce-precise-steps=<int>                    - The number of precise steps between two approximating iterations. (A value of -1 schedules another approximation stage before the actual dead code elimination.
  --polly-delicm-max-ops=<int>                       - Maximum number of isl operations to invest for lifetime analysis; 0=no limit
  --polly-detect-full-functions                      - Allow the detection of full functions
  --polly-dump-after                                 - Dump module after Polly transformations into a file suffixed with "-after"
  --polly-dump-after-file=<string>                   - Dump module after Polly transformations to the given file
  --polly-dump-before                                - Dump module before Polly transformations into a file suffixed with "-before"
  --polly-dump-before-file=<string>                  - Dump module before Polly transformations to the given file
  --polly-enable-simplify                            - Simplify SCoP after optimizations
  --polly-ignore-func=<string>                       - Ignore functions that match a regex. Multiple regexes can be comma separated. Scop detection will ignore all functions that match ANY of the regexes provided.
  --polly-isl-arg=<argument>                         - Option passed to ISL
  --polly-on-isl-error-abort                         - Abort if an isl error is encountered
  --polly-only-func=<string>                         - Only run on functions that match a regex. Multiple regexes can be comma separated. Scop detection will run on all functions that match ANY of the regexes provided.
  --polly-only-region=<identifier>                   - Only run on certain regions (The provided identifier must appear in the name of the region's entry block
  --polly-only-scop-detection                        - Only run scop detection, but no other optimizations
  --polly-optimized-scops                            - Polly - Dump polyhedral description of Scops optimized with the isl scheduling optimizer and the set of post-scheduling transformations is applied on the schedule tree
  --polly-parallel                                   - Generate thread parallel code (isl codegen only)
  --polly-parallel-force                             - Force generation of thread parallel code ignoring any cost model
  --polly-pattern-matching-based-opts                - Perform optimizations based on pattern matching
  --polly-postopts                                   - Apply post-rescheduling optimizations such as tiling (requires -polly-reschedule)
  --polly-pragma-based-opts                          - Apply user-directed transformation from metadata
  --polly-pragma-ignore-depcheck                     - Skip the dependency check for pragma-based transformations
  --polly-process-unprofitable                       - Process scops that are unlikely to benefit from Polly optimizations.
  --polly-register-tiling                            - Enable register tiling
  --polly-report                                     - Print information about the activities of Polly
  --polly-reschedule                                 - Optimize SCoPs using ISL
  --polly-show                                       - Highlight the code regions that will be optimized in a (CFG BBs and LLVM-IR instructions)
  --polly-show-only                                  - Highlight the code regions that will be optimized in a (CFG only BBs)
  --polly-stmt-granularity=<value>                   - Algorithm to use for splitting basic blocks into multiple statements
    =bb                                              -   One statement per basic block
    =scalar-indep                                    -   Scalar independence heuristic
    =store                                           -   Store-level granularity
  --polly-target=<value>                             - The hardware to target
    =cpu                                             -   generate CPU code
  --polly-tiling                                     - Enable loop tiling
  --polly-vectorizer=<value>                         - Select the vectorization strategy
    =none                                            -   No Vectorization
    =polly                                           -   Polly internal vectorizer
    =stripmine                                       -   Strip-mine outer loops for the loop-vectorizer to trigger
```

***

**scan-build**

Clang static analyzer

```
:~# scan-build -h
USAGE: scan-build [options] <build command> [build options]

OPTIONS:

 -analyze-headers

   Also analyze functions in #included files.  By default, such functions
   are skipped unless they are called by functions within the main source file.

 --force-analyze-debug-code

   Tells analyzer to enable assertions in code even if they were disabled
   during compilation to enable more precise results.

 -o <output location>

   Specifies the output directory for analyzer reports. Subdirectories will be
   created as needed to represent separate "runs" of the analyzer. If this
   option is not specified, a directory is created in /tmp (TMPDIR on Mac OS X)
   to store the reports.

 -h
 --help

   Display this message.

 -k
 --keep-going

   Add a "keep on going" option to the specified build command. This option
   currently supports make and xcodebuild. This is a convenience option; one
   can specify this behavior directly using build options.

 --keep-cc

   Do not override CC and CXX make variables. Useful when running make in
   autoconf-based (and similar) projects where configure can add extra flags
   to those variables.

 --html-title [title]
 --html-title=[title]

   Specify the title used on generated HTML pages. If not specified, a default
   title will be used.

 --show-description

   Display the description of defects in the list

 -sarif

  By default the output of scan-build is a set of HTML files. This option
  outputs the results in SARIF format.
 
 -plist

   By default the output of scan-build is a set of HTML files. This option
   outputs the results as a set of .plist files.

 -plist-html

   By default the output of scan-build is a set of HTML files. This option
   outputs the results as a set of HTML and .plist files.

 --status-bugs

   By default, the exit status of scan-build is the same as the executed build
   command. Specifying this option causes the exit status of scan-build to be 1
   if it found potential bugs and the exit status of the build itself otherwise.

 --exclude <path>

   Do not run static analyzer against files found in this
   directory (You can specify this option multiple times).
   Could be useful when project contains 3rd party libraries.

 --use-cc [compiler path]
 --use-cc=[compiler path]

   scan-build analyzes a project by interposing a "fake compiler", which
   executes a real compiler for compilation and the static analyzer for analysis.
   Because of the current implementation of interposition, scan-build does not
   know what compiler your project normally uses.  Instead, it simply overrides
   the CC environment variable, and guesses your default compiler.

   In the future, this interposition mechanism to be improved, but if you need
   scan-build to use a specific compiler for *compilation* then you can use
   this option to specify a path to that compiler.

   If the given compiler is a cross compiler, you may also need to provide
   --analyzer-target option to properly analyze the source code because static
   analyzer runs as if the code is compiled for the host machine by default.

 --use-c++ [compiler path]
 --use-c++=[compiler path]

   This is the same as "--use-cc" but for C++ code.

 --analyzer-target [target triple name for analysis]
 --analyzer-target=[target triple name for analysis]

   This provides target triple information to clang static analyzer.
   It only changes the target for analysis but doesn't change the target of a
   real compiler given by --use-cc and --use-c++ options.

 -v

   Enable verbose output from scan-build. A second and third '-v' increases
   verbosity.

 -V
 --view

   View analysis results in a web browser when the build completes.

 --generate-index-only <output location>

   Do not perform the analysis, but only regenerate the index.html file
   from existing report.html files. Useful for making a custom Static Analyzer
   integration into a build system that isn't otherwise supported by scan-build.

ADVANCED OPTIONS:

 -no-failure-reports

   Do not create a 'failures' subdirectory that includes analyzer crash reports
   and preprocessed source files.

 -stats

   Generates visitation statistics for the project being analyzed.

 -maxloop <loop count>

   Specify the number of times a block can be visited before giving up.
   Default is 4. Increase for more comprehensive coverage at a cost of speed.

 -internal-stats

   Generate internal analyzer statistics.

 --use-analyzer [Xcode|path to clang]
 --use-analyzer=[Xcode|path to clang]

   scan-build uses the 'clang' executable relative to itself for static
   analysis. One can override this behavior with this option by using the
   'clang' packaged with Xcode (on OS X) or from the PATH.

 --keep-empty

   Don't remove the build results directory even if no issues were reported.

 --override-compiler
   Always resort to the ccc-analyzer even when better interposition methods
   are available.

 -analyzer-config <options>

   Provide options to pass through to the analyzer's -analyzer-config flag.
   Several options are separated with comma: 'key1=val1,key2=val2'

   Available options:
     * stable-report-filename=true or false (default)
       Switch the page naming to:
       report-<filename>-<function/method name>-<id>.html
       instead of report-XXXXXX.html

CONTROLLING CHECKERS:

 A default group of checkers are always run unless explicitly disabled.
 Checkers may be enabled/disabled using the following options:

 -enable-checker [checker name]
 -disable-checker [checker name]

LOADING CHECKERS:

 Loading external checkers using the clang plugin interface:

 -load-plugin [plugin library]

AVAILABLE CHECKERS:

 + core.CallAndMessage           Check for logical errors for function calls and Objective-C message expressions (e.g., uninitialized arguments, null function pointers)
 + core.DivideZero               Check for division by zero
 + core.NonNullParamChecker      Check for null pointers passed as arguments to a function whose arguments are references or marked with the 'nonnull' attribute
 + core.NullDereference          Check for dereferences of null pointers
 + core.StackAddressEscape       Check that addresses to stack memory do not escape the function
 + core.UndefinedBinaryOperatorResult
                                 Check for undefined results of binary operators
 + core.VLASize                  Check for declarations of VLA of undefined or zero size
 + core.uninitialized.ArraySubscript
                                 Check for uninitialized values used as array subscripts
 + core.uninitialized.Assign     Check for assigning uninitialized values
 + core.uninitialized.Branch     Check for uninitialized values used as branch conditions
 + core.uninitialized.CapturedBlockVariable
                                 Check for blocks that capture uninitialized values
 + core.uninitialized.UndefReturn Check for uninitialized values being returned to the caller
 + cplusplus.InnerPointer        Check for inner pointers of C++ containers used after re/deallocation
 + cplusplus.Move                Find use-after-move bugs in C++
 + cplusplus.NewDelete           Check for double-free and use-after-free problems. Traces memory managed by new/delete.
 + cplusplus.NewDeleteLeaks      Check for memory leaks. Traces memory managed by new/delete.
 + cplusplus.PlacementNew        Check if default placement new is provided with pointers to sufficient storage capacity
 + cplusplus.PureVirtualCall     Check pure virtual function calls during construction/destruction
 + cplusplus.StringChecker       Checks C++ std::string bugs
 + deadcode.DeadStores           Check for values stored to variables that are never read afterwards
   fuchsia.HandleChecker         A Checker that detect leaks related to Fuchsia handles
 + nullability.NullPassedToNonnull
                                 Warns when a null pointer is passed to a pointer which has a _Nonnull type.
 + nullability.NullReturnedFromNonnull
                                 Warns when a null pointer is returned from a function that has _Nonnull return type.
   nullability.NullableDereferenced
                                 Warns when a nullable pointer is dereferenced.
   nullability.NullablePassedToNonnull
                                 Warns when a nullable pointer is passed to a pointer which has a _Nonnull type.
   nullability.NullableReturnedFromNonnull
                                 Warns when a nullable pointer is returned from a function that has _Nonnull return type.
   optin.cplusplus.UninitializedObject
                                 Reports uninitialized fields after object construction
   optin.cplusplus.VirtualCall   Check virtual function calls during construction/destruction
   optin.mpi.MPI-Checker         Checks MPI code
   optin.osx.OSObjectCStyleCast  Checker for C-style casts of OSObjects
   optin.osx.cocoa.localizability.EmptyLocalizationContextChecker
                                 Check that NSLocalizedString macros include a comment for context
   optin.osx.cocoa.localizability.NonLocalizedStringChecker
                                 Warns about uses of non-localized NSStrings passed to UI methods expecting localized NSStrings
   optin.performance.GCDAntipattern
                                 Check for performance anti-patterns when using Grand Central Dispatch
   optin.performance.Padding     Check for excessively padded structs.
   optin.portability.UnixAPI     Finds implementation-defined behavior in UNIX/Posix functions
   osx.API                       Check for proper uses of various Apple APIs
   osx.MIG                       Find violations of the Mach Interface Generator calling convention
   osx.NumberObjectConversion    Check for erroneous conversions of objects representing numbers into numbers
   osx.OSObjectRetainCount       Check for leaks and improper reference count management for OSObject
   osx.ObjCProperty              Check for proper uses of Objective-C properties
   osx.SecKeychainAPI            Check for proper uses of Secure Keychain APIs
   osx.cocoa.AtSync              Check for nil pointers used as mutexes for @synchronized
   osx.cocoa.AutoreleaseWrite    Warn about potentially crashing writes to autoreleasing objects from different autoreleasing pools in Objective-C
   osx.cocoa.ClassRelease        Check for sending 'retain', 'release', or 'autorelease' directly to a Class
   osx.cocoa.Dealloc             Warn about Objective-C classes that lack a correct implementation of -dealloc
   osx.cocoa.IncompatibleMethodTypes
                                 Warn about Objective-C method signatures with type incompatibilities
   osx.cocoa.Loops               Improved modeling of loops using Cocoa collection types
   osx.cocoa.MissingSuperCall    Warn about Objective-C methods that lack a necessary call to super
   osx.cocoa.NSAutoreleasePool   Warn for suboptimal uses of NSAutoreleasePool in Objective-C GC mode
   osx.cocoa.NSError             Check usage of NSError** parameters
   osx.cocoa.NilArg              Check for prohibited nil arguments to ObjC method calls
   osx.cocoa.NonNilReturnValue   Model the APIs that are guaranteed to return a non-nil value
   osx.cocoa.ObjCGenerics        Check for type errors when using Objective-C generics
   osx.cocoa.RetainCount         Check for leaks and improper reference count management
   osx.cocoa.RunLoopAutoreleaseLeak
                                 Check for leaked memory in autorelease pools that will never be drained
   osx.cocoa.SelfInit            Check that 'self' is properly initialized inside an initializer method
   osx.cocoa.SuperDealloc        Warn about improper use of '[super dealloc]' in Objective-C
   osx.cocoa.UnusedIvars         Warn about private ivars that are never used
   osx.cocoa.VariadicMethodTypes Check for passing non-Objective-C types to variadic collection initialization methods that expect only Objective-C types
   osx.coreFoundation.CFError    Check usage of CFErrorRef* parameters
   osx.coreFoundation.CFNumber   Check for proper uses of CFNumber APIs
   osx.coreFoundation.CFRetainRelease
                                 Check for null arguments to CFRetain/CFRelease/CFMakeCollectable
   osx.coreFoundation.containers.OutOfBounds
                                 Checks for index out-of-bounds when using 'CFArray' API
   osx.coreFoundation.containers.PointerSizedValues
                                 Warns if 'CFArray', 'CFDictionary', 'CFSet' are created with non-pointer-size values
   security.FloatLoopCounter     Warn on using a floating point value as a loop counter (CERT: FLP30-C, FLP30-CPP)
   security.insecureAPI.DeprecatedOrUnsafeBufferHandling
                                 Warn on uses of unsecure or deprecated buffer manipulating functions
 + security.insecureAPI.UncheckedReturn
                                 Warn on uses of functions whose return values must be always checked
   security.insecureAPI.bcmp     Warn on uses of the 'bcmp' function
   security.insecureAPI.bcopy    Warn on uses of the 'bcopy' function
   security.insecureAPI.bzero    Warn on uses of the 'bzero' function
   security.insecureAPI.decodeValueOfObjCType
                                 Warn on uses of the '-decodeValueOfObjCType:at:' method
 + security.insecureAPI.getpw    Warn on uses of the 'getpw' function
 + security.insecureAPI.gets     Warn on uses of the 'gets' function
 + security.insecureAPI.mkstemp  Warn when 'mkstemp' is passed fewer than 6 X's in the format string
 + security.insecureAPI.mktemp   Warn on uses of the 'mktemp' function
   security.insecureAPI.rand     Warn on uses of the 'rand', 'random', and related functions
   security.insecureAPI.strcpy   Warn on uses of the 'strcpy' and 'strcat' functions
 + security.insecureAPI.vfork    Warn on uses of the 'vfork' function
 + unix.API                      Check calls to various UNIX/Posix functions
 + unix.Malloc                   Check for memory leaks, double free, and use-after-free problems. Traces memory managed by malloc()/free().
 + unix.MallocSizeof             Check for dubious malloc arguments involving sizeof
 + unix.MismatchedDeallocator    Check for mismatched deallocators.
 + unix.Vfork                    Check for proper usage of vfork
 + unix.cstring.BadSizeArg       Check the size argument passed into C string functions for common erroneous patterns
 + unix.cstring.NullArg          Check for null pointers being passed as arguments to C string functions
   valist.CopyToSelf             Check for va_lists which are copied onto itself.
   valist.Uninitialized          Check for usages of uninitialized (or already released) va_lists.
   valist.Unterminated           Check for va_lists which are not released by a va_end call.
   webkit.NoUncountedMemberChecker
                                 Check for no uncounted member variables.
   webkit.RefCntblBaseVirtualDtor Check for any ref-countable base class having virtual destructor.
   webkit.UncountedLambdaCapturesChecker
                                 Check uncounted lambda captures.

NOTE: "+" indicates that an analysis is enabled by default.

BUILD OPTIONS

 You can specify any build option acceptable to the build command.

EXAMPLE

 scan-build -o /tmp/myhtmldir make -j4

The above example causes analysis reports to be deposited into a subdirectory
of "/tmp/myhtmldir" and to run "make" with the "-j4" option. A different
subdirectory is created each time scan-build analyzes a project. The analyzer
should support most parallel builds, but not distributed builds.

```

***

**scan-view**

Manual page for scan-view 14

```
:~# scan-view -h
usage: scan-view [-h] [--host HOST] [--port PORT] [--debug] [--auto-reload]
                 [--no-browser] [--allow-all-hosts]
                 <results directory>

The clang static analyzer results viewer.

positional arguments:
  <results directory>

options:
  -h, --help           show this help message and exit
  --host HOST          Host interface to listen on. (default=127.0.0.1)
  --port PORT          Port to listen on. (default=8181)
  --debug              Print additional debugging information.
  --auto-reload        Automatically update module for each request.
  --no-browser         Don't open a webbrowser on startup.
  --allow-all-hosts    Allow connections from any host (access restricted to
                       "127.0.0.1" by default)
```

***

#### clangd <a href="#clangd" id="clangd"></a>

clangd understands your C++ code and adds smart features to your editor:

* code completion
* compile errors
* go-to-definition
* and more.

clangd is a language server that implements the Language Server Protocol; it can work with many editors through a plugin.

This is a dependency package providing clangd.

**Installed size:** `15 KB`\
**How to install:** `sudo apt install clangd`

<details>

<summary>Dependencies:</summary>

* clangd-14

</details>

**clangd**

Manual page for clangd 14

```
:~# clangd -h
OVERVIEW: clangd is a language server that provides IDE-like features to editors.

It should be used via an editor plugin rather than invoked directly. For more information, see:
	https://clangd.llvm.org/
	https://microsoft.github.io/language-server-protocol/

clangd accepts flags on the commandline, and in the CLANGD_FLAGS environment variable.

USAGE: clangd [options]

OPTIONS:

Generic Options:

  --help                          - Display available options (--help-hidden for more)
  --help-list                     - Display list of available options (--help-list-hidden for more)
  --version                       - Display the version of this program

clangd compilation flags options:

  --compile-commands-dir=<string> - Specify a path to look for compile_commands.json. If path is invalid, clangd will look in the current directory and parent paths of each source file
  --query-driver=<string>         - Comma separated list of globs for white-listing gcc-compatible drivers that are safe to execute. Drivers matching any of these globs will be used to extract system includes. e.g. /usr/bin/**/clang-*,/path/to/repo/**/g++-*

clangd feature options:

  --all-scopes-completion         - If set to true, code completion will include index symbols that are not defined in the scopes (e.g. namespaces) visible from the code completion point. Such completions can insert scope qualifiers
  --background-index              - Index project code in the background and persist index on disk.
  --clang-tidy                    - Enable clang-tidy diagnostics
  --completion-style=<value>      - Granularity of code completion suggestions
    =detailed                     -   One completion item for each semantically distinct completion, with full type information
    =bundled                      -   Similar completion items (e.g. function overloads) are combined. Type information shown where possible
  --fallback-style=<string>       - clang-format style to apply by default when no .clang-format file is found
  --function-arg-placeholders     - When disabled, completions contain only parentheses for function calls. When enabled, completions also contain placeholders for method parameters
  --header-insertion=<value>      - Add #include directives when accepting code completions
    =iwyu                         -   Include what you use. Insert the owning header for top-level symbols, unless the header is already directly included or the symbol is forward-declared
    =never                        -   Never insert #include directives as part of code completion
  --header-insertion-decorators   - Prepend a circular dot or space before the completion label, depending on whether an include line will be inserted or not
  --limit-references=<int>        - Limit the number of references returned by clangd. 0 means no limit (default=1000)
  --limit-results=<int>           - Limit the number of results returned by clangd. 0 means no limit (default=100)
  --project-root=<string>         - Path to the project root. Requires remote-index-address to be set.
  --remote-index-address=<string> - Address of the remote index server

clangd miscellaneous options:

  --check[=<string>]                - Parse one file in isolation instead of acting as a language server. Useful to investigate/reproduce crashes or configuration problems. With --check=<filename>, attempts to parse a particular file.
  --check-lines[=<string>]          - If specified, limits the range of tokens in -check file on which various features are tested. Example --check-lines=3-7 restricts testing to lines 3 to 7 (inclusive) or --check-lines=5 to restrict to one line. Default is testing entire file.
  --enable-config                 - Read user and project configuration from YAML files.
                                    Project config is from a .clangd file in the project directory.
                                    User config is from clangd/config.yaml in the following directories:
                                    	Windows: %USERPROFILE%\AppData\Local
                                    	Mac OS: ~/Library/Preferences/
                                    	Others: $XDG_CONFIG_HOME, usually ~/.config
                                    Configuration is documented at https://clangd.llvm.org/config.html
  -j=<uint>                       - Number of async workers used by clangd. Background index also uses this many workers.
  --malloc-trim                   - Release memory periodically via malloc_trim(3).
  --pch-storage=<value>           - Storing PCHs in memory increases memory usages, but may improve performance
    =disk                         -   store PCHs on disk
    =memory                       -   store PCHs in memory

clangd protocol and logging options:

  --log=<value>                   - Verbosity of log messages written to stderr
    =error                        -   Error messages only
    =info                         -   High level execution tracing
    =verbose                      -   Low level details
  --offset-encoding=<value>       - Force the offsetEncoding used for character positions. This bypasses negotiation via client capabilities
    =utf-8                        -   Offsets are in UTF-8 bytes
    =utf-16                       -   Offsets are in UTF-16 code units
    =utf-32                       -   Offsets are in unicode codepoints
  --path-mappings=<string>        - Translates between client paths (as seen by a remote editor) and server paths (where clangd sees files on disk). Comma separated list of '<client_path>=<server_path>' pairs, the first entry matching a given path is used. e.g. /home/project/incl=/opt/include,/home/project=/workarea/project
  --pretty                        - Pretty-print JSON output
```

***

#### libc++-dev <a href="#libc-dev" id="libc-dev"></a>

libc++ is another implementation of the C++ standard library

Features and Goals

* Correctness as defined by the C++ standards.
* Fast execution.
* Minimal memory use.
* Fast compile times.
* ABI compatibility with gcc’s libstdc++ for some low-level features such as exception objects, rtti and memory allocation.
* Extensive unit tests.

This is a dependency package providing the default LLVM C++ Standard library development files.

**Installed size:** `10 KB`\
**How to install:** `sudo apt install libc++-dev`

<details>

<summary>Dependencies:</summary>

* libc++-14-dev

</details>

***

#### libc++-dev-wasm32 <a href="#libc-dev-wasm32" id="libc-dev-wasm32"></a>

libc++ is another implementation of the C++ standard library

Features and Goals

* Correctness as defined by the C++ standards.
* Fast execution.
* Minimal memory use.
* Fast compile times.
* ABI compatibility with gcc’s libstdc++ for some low-level features such as exception objects, rtti and memory allocation.
* Extensive unit tests.

This is a dependency package providing the default 32-bit WebAssembly System Interface.

**Installed size:** `10 KB`\
**How to install:** `sudo apt install libc++-dev-wasm32`

<details>

<summary>Dependencies:</summary>

* libc++-14-dev-wasm32

</details>

***

#### libc++1 <a href="#libc1" id="libc1"></a>

libc++ is another implementation of the C++ standard library.

Features and Goals

* Correctness as defined by the C++ standards.
* Fast execution.
* Minimal memory use.
* Fast compile times.
* ABI compatibility with gcc’s libstdc++ for some low-level features such as exception objects, rtti and memory allocation.
* Extensive unit tests.

This is a dependency package providing the default LLVM C++ Standard library.

**Installed size:** `10 KB`\
**How to install:** `sudo apt install libc++1`

<details>

<summary>Dependencies:</summary>

* libc++1-14

</details>

***

#### libc++abi-dev <a href="#libcabi-dev" id="libcabi-dev"></a>

libc++abi is another implementation of low level support for a standard C++ library.

Features and Goals

* Correctness as defined by the C++ standards.
* Provide a portable sublayer to ease the porting of libc++

This is a dependency package providing low level support to dev LLVM C++ Standard library.

**Installed size:** `13 KB`\
**How to install:** `sudo apt install libc++abi-dev`

<details>

<summary>Dependencies:</summary>

* libc++abi-14-dev

</details>

***

#### libc++abi1 <a href="#libcabi1" id="libcabi1"></a>

libc++abi is another implementation of low level support for a standard C++ library.

Features and Goals

* Correctness as defined by the C++ standards.
* Provide a portable sublayer to ease the porting of libc++

This is a dependency package providing low level support to LLVM C++ Standard library.

**Installed size:** `10 KB`\
**How to install:** `sudo apt install libc++abi1`

<details>

<summary>Dependencies:</summary>

* libc++abi1-14

</details>

***

#### libclang-cpp-dev <a href="#libclang-cpp-dev" id="libclang-cpp-dev"></a>

Clang project is a C, C++, Objective C and Objective C++ front-end for the LLVM compiler. Its goal is to offer a replacement to the GNU Compiler Collection (GCC).

Clang implements all of the ISO C++ 1998, 11 and 14 standards and also provides most of the support of C++17.

This is a dependency package providing the default Clang C++ library.

**Installed size:** `10 KB`\
**How to install:** `sudo apt install libclang-cpp-dev`

<details>

<summary>Dependencies:</summary>

* libclang-cpp14-dev

</details>

***

#### libclang-dev <a href="#libclang-dev" id="libclang-dev"></a>

Clang project is a C, C++, Objective C and Objective C++ front-end for the LLVM compiler. Its goal is to offer a replacement to the GNU Compiler Collection (GCC).

Clang implements all of the ISO C++ 1998, 11 and 14 standards and also provides most of the support of C++17.

This is a dependency package providing the default libclang libraries and headers.

**Installed size:** `10 KB`\
**How to install:** `sudo apt install libclang-dev`

<details>

<summary>Dependencies:</summary>

* libclang-14-dev

</details>

***

#### libclang-rt-dev <a href="#libclang-rt-dev" id="libclang-rt-dev"></a>

This package provides various libraries:

* builtins - Simple libraries that provide implementation of the low-level target-specific hooks required by code generation and other runtime components.
* sanitizer runtimes - AddressSanitizer, ThreadSanitizer, UndefinedBehaviorSanitizer, MemorySanitizer, LeakSanitizer DataFlowSanitizer, etc
* profile - Library which is used to collect coverage information.

This is a dependency package providing the default compiler-rt libraries and headers.

**Installed size:** `10 KB`\
**How to install:** `sudo apt install libclang-rt-dev`

<details>

<summary>Dependencies:</summary>

* libclang-rt-14-dev

</details>

***

#### libclang-rt-dev-wasm32 <a href="#libclang-rt-dev-wasm32" id="libclang-rt-dev-wasm32"></a>

Provides the compiler-rt builtins for WebAssembly 32 bits

This is a dependency package providing the default libclang wasm32 library.

**Installed size:** `10 KB`\
**How to install:** `sudo apt install libclang-rt-dev-wasm32`

<details>

<summary>Dependencies:</summary>

* libclang-rt-14-dev-wasm32

</details>

***

#### libclang-rt-dev-wasm64 <a href="#libclang-rt-dev-wasm64" id="libclang-rt-dev-wasm64"></a>

Provides the compiler-rt builtins for WebAssembly 64 bits

This is a dependency package providing the default libclang wasm64 library.

**Installed size:** `10 KB`\
**How to install:** `sudo apt install libclang-rt-dev-wasm64`

<details>

<summary>Dependencies:</summary>

* libclang-rt-14-dev-wasm64

</details>

***

#### libclang1 <a href="#libclang1" id="libclang1"></a>

Clang project is a C, C++, Objective C and Objective C++ front-end for the LLVM compiler. Its goal is to offer a replacement to the GNU Compiler Collection (GCC).

Clang implements all of the ISO C++ 1998, 11 and 14 standards and also provides most of the support of C++17.

This is a dependency package providing the default clang libraries.

The C Interface to Clang provides a relatively small API that exposes facilities for parsing source code into an abstract syntax tree (AST), loading already-parsed ASTs, traversing the AST, associating physical source locations with elements within the AST, and other facilities that support Clang-based development tools.

**Installed size:** `10 KB`\
**How to install:** `sudo apt install libclang1`

<details>

<summary>Dependencies:</summary>

* libclang1-14

</details>

***

#### liblld-dev <a href="#liblld-dev" id="liblld-dev"></a>

LLD is a new, high-performance linker. It is built as a set of reusable components which highly leverage existing libraries in the larger LLVM Project.

This is a dependency package providing the default liblld-dev package.

**Installed size:** `12 KB`\
**How to install:** `sudo apt install liblld-dev`

<details>

<summary>Dependencies:</summary>

* liblld-14-dev

</details>

***

#### liblldb-dev <a href="#liblldb-dev" id="liblldb-dev"></a>

LLDB is a next generation, high-performance debugger. It is built as a set of reusable components which highly leverage existing libraries in the larger LLVM Project, such as the Clang expression parser and LLVM disassembler.

This package provides the header files to build extension over lldb.

**Installed size:** `14 KB`\
**How to install:** `sudo apt install liblldb-dev`

<details>

<summary>Dependencies:</summary>

* liblldb-14-dev

</details>

***

#### libllvm-ocaml-dev <a href="#libllvm-ocaml-dev" id="libllvm-ocaml-dev"></a>

The Low-Level Virtual Machine (LLVM) is a collection of libraries and tools that make it easy to build compilers, optimizers, Just-In-Time code generators, and many other compiler-related programs.

This is a dependency package providing the default bindings for OCaml.

**Installed size:** `15 KB`\
**How to install:** `sudo apt install libllvm-ocaml-dev`

<details>

<summary>Dependencies:</summary>

* libllvm-14-ocaml-dev
* llvm-runtime

</details>

***

#### libomp-dev <a href="#libomp-dev" id="libomp-dev"></a>

The runtime is the part of the OpenMP implementation that your code is linked against, and that manages the multiple threads in an OpenMP program while it is executing.

This is a dependency package providing the default LLVM OpenMP dev package.

**Installed size:** `10 KB`\
**How to install:** `sudo apt install libomp-dev`

<details>

<summary>Dependencies:</summary>

* libomp-14-dev

</details>

***

#### libomp5 <a href="#libomp5" id="libomp5"></a>

The runtime is the part of the OpenMP implementation that your code is linked against, and that manages the multiple threads in an OpenMP program while it is executing.

This is a dependency package providing the default LLVM OpenMP runtime.

**Installed size:** `10 KB`\
**How to install:** `sudo apt install libomp5`

<details>

<summary>Dependencies:</summary>

* libomp5-14

</details>

***

#### lld <a href="#lld" id="lld"></a>

LLD is a new, high-performance linker. It is built as a set of reusable components which highly leverage existing libraries in the larger LLVM Project.

This is a dependency package providing the lld linker.

**Installed size:** `19 KB`\
**How to install:** `sudo apt install lld`

<details>

<summary>Dependencies:</summary>

* lld-14

</details>

**ld.lld**

ELF linker from the LLVM project

```
:~# ld.lld --help
OVERVIEW: lld

USAGE: ld.lld [options] file...

OPTIONS:
  -(                      Alias for --start-group
  -)                      Alias for --end-group
  --allow-multiple-definition
                          Allow multiple definitions
  --allow-shlib-undefined Allow unresolved references in shared libraries (default when linking a shared library)
  --apply-dynamic-relocs  Apply link-time values for dynamic relocations
  --as-needed             Only set DT_NEEDED for shared libraries if used
  --auxiliary=<value>     Set DT_AUXILIARY field to the specified name
  --Bdynamic              Link against shared libraries (default)
  --Bno-symbolic          Don't bind default visibility defined symbols locally for -shared (default)
  --Bshareable            Alias for --shared
  --Bstatic               Do not link against shared libraries
  --Bsymbolic-functions   Bind default visibility defined function symbols locally for -shared
  --Bsymbolic-non-weak-functions
                          Bind default visibility defined STB_GLOBAL function symbols locally for -shared
  --Bsymbolic             Bind default visibility defined symbols locally for -shared
  --build-id=[fast,md5,sha1,uuid,0x<hexstring>]
                          Generate build ID note
  --build-id              Alias for --build-id=fast
  -b <value>              Alias for --format
  --call-graph-ordering-file=<value>
                          Layout sections to optimize the given callgraph
  --call-graph-profile-sort
                          Reorder sections with call graph profile (default)
  --call_shared           Alias for --Bdynamic
  --check-sections        Check section addresses for overlaps (default)
  --color-diagnostics=[auto,always,never]
                          Use colors in diagnostics (default: auto)
  --color-diagnostics     Alias for --color-diagnostics=always
  --compress-debug-sections=[none,zlib]
                          Compress DWARF debug sections
  --cref                  Output cross reference table. If -Map is specified, print to the map file
  --dc                    Alias for --define-common
  --define-common         Assign space to common symbols
  --defsym=<symbol>=<value>
                          Define a symbol alias
  --demangle              Demangle symbol names (default)
  --dependency-file=<file>
                          Write a dependency file
  --dependent-libraries   Process dependent library specifiers from input files (default)
  --disable-new-dtags     Disable new dynamic tags
  --discard-all           Delete all local symbols
  --discard-locals        Delete temporary local symbols
  --discard-none          Keep all symbols in the symbol table
  --dn                    Alias for --Bstatic
  --dp                    Alias for --define-common
  --dynamic-linker=<value>
                          Which dynamic linker to use
  --dynamic-list=<file>   Similar to --export-dynamic-symbol-list. When creating a shared object, this additionally implies -Bsymbolic but does not set DF_SYMBOLIC
  --dy                    Alias for --Bdynamic
  -d                      Alias for --define-common
  --EB                    Select the big-endian format in OUTPUT_FORMAT
  --eh-frame-hdr          Request creation of .eh_frame_hdr section and PT_GNU_EH_FRAME segment header
  --EL                    Select the little-endian format in OUTPUT_FORMAT
  --emit-relocs           Generate relocations in output
  --enable-new-dtags      Enable new dynamic tags (default)
  --end-group             Ignored for compatibility with GNU unless you pass --warn-backrefs
  --end-lib               End a grouping of objects that should be treated as if they were together in an archive
  --entry=<entry>         Name of entry point symbol
  --error-handling-script=<value>
                          Specify an error handling script
  --error-limit=<value>   Maximum number of errors to emit before stopping (0 = no limit)
  --error-unresolved-symbols
                          Report unresolved symbols as errors
  --exclude-libs=<value>  Exclude static libraries from automatic export
  --execute-only          Mark executable sections unreadable
  --export-dynamic-symbol-list=file
                          Read a list of dynamic symbol patterns. Apply --export-dynamic-symbol on each pattern
  --export-dynamic-symbol=glob
                          (executable) Put matched symbols in the dynamic symbol table. (shared object) References to matched non-local STV_DEFAULT symbols shouldn't be bound to definitions within the shared object. Does not imply -Bsymbolic.
  --export-dynamic        Put symbols in the dynamic symbol table
  -E                      Alias for --export-dynamic
  -e <value>              Alias for --entry
  --fatal-warnings        Treat warnings as errors
  --filter=<value>        Set DT_FILTER field to the specified name
  --fini=<symbol>         Specify a finalizer function
  --fix-cortex-a53-843419 Apply fixes for AArch64 Cortex-A53 erratum 843419
  --fix-cortex-a8         Apply fixes for ARM Cortex-A8 erratum 657417
  --format=[default,elf,binary]
                          Change the input format of the inputs following this option
  --fortran-common        Search archive members for definitions to override COMMON symbols (default)
  -F <value>              Alias for --filter
  -f <value>              Alias for --auxiliary
  --gc-sections           Enable garbage collection of unused sections
  --gdb-index             Generate .gdb_index section
  --gnu-unique            Enable STB_GNU_UNIQUE symbol binding (default)
  --hash-style=<value>    Specify hash style (sysv, gnu or both)
  --help                  Print option help
  -h <value>              Alias for --soname
  --icf=all               Enable identical code folding
  --icf=none              Disable identical code folding (default)
  --icf=safe              Enable safe identical code folding
  --ignore-data-address-equality
                          lld can break the address equality of data
  --ignore-function-address-equality
                          lld can break the address equality of functions
  --image-base=<value>    Set the base address
  --init=<symbol>         Specify an initializer function
  --just-symbols=<value>  Just link symbols
  --keep-unique=<value>   Do not fold this symbol during ICF
  --library-path=<value>  Add <dir> to the library search path
  --library-path <value>  Add <dir> to the library search path
  --library=<value>       Search for library <libname>
  --library <value>       Search for library <libname>
  --lto-aa-pipeline=<value>
                          AA pipeline to run during LTO. Used in conjunction with -lto-newpm-passes
  --lto-basic-block-sections=<value>
                          Enable basic block sections for LTO
  --lto-cs-profile-file=<value>
                          Context sensitive profile file path
  --lto-cs-profile-generate
                          Perform context sensitive PGO instrumentation
  --lto-debug-pass-manager
                          Debug new pass manager
  --lto-emit-asm          Emit assembly code
  --lto-legacy-pass-manager
                          Use the legacy pass manager in LLVM
  --lto-newpm-passes=<value>
                          Passes to run during LTO
  --lto-O<opt-level>      Optimization level for LTO
  --lto-partitions=<value>
                          Number of LTO codegen partitions
  --lto-pgo-warn-mismatch turn on warnings about profile cfg mismatch (default)>
  --lto-sample-profile=<value>
                          Sample profile file path
  --lto-unique-basic-block-section-names
                          Give unique names to every basic block section for LTO
  --lto-whole-program-visibility
                          Asserts that the LTO link has whole program visibility
  -L <dir>                Add <dir> to the library search path
  -l <libname>            Search for library <libname>
  --Map=<value>           Print a link map to the specified file
  --merge-exidx-entries   Enable merging .ARM.exidx entries (default)
  --mllvm=<value>         Additional arguments to forward to LLVM's option processing
  --mmap-output-file      Mmap the output file for writing (default)
  -M                      Alias for --print-map
  -m <value>              Set target emulation
  --nmagic                Do not page align sections, link against static libraries.
  --no-allow-multiple-definition
                          Do not allow multiple definitions (default)
  --no-allow-shlib-undefined
                          Do not allow unresolved references in shared libraries (default when linking an executable)
  --no-apply-dynamic-relocs
                          Do not apply link-time values for dynamic relocations (default)
  --no-as-needed          Always set DT_NEEDED for shared libraries (default)
  --no-call-graph-profile-sort
                          Do not reorder sections with call graph profile
  --no-check-sections     Do not check section addresses for overlaps
  --no-color-diagnostics  Alias for --color-diagnostics=never
  --no-define-common      Do not assign space to common symbols
  --no-demangle           Do not demangle symbol names
  --no-dependent-libraries
                          Ignore dependent library specifiers from input files
  --no-dynamic-linker     Inhibit output of .interp section
  --no-eh-frame-hdr       Do not create .eh_frame_hdr section
  --no-execute-only       Mark executable sections readable (default)
  --no-export-dynamic     Do not put symbols in the dynamic symbol table (default)
  --no-fatal-warnings     Do not treat warnings as errors (default)
  --no-fortran-common     Do not search archive members for definitions to override COMMON symbols
  --no-gc-sections        Disable garbage collection of unused sections (default)
  --no-gdb-index          Do not generate .gdb_index section (default)
  --no-gnu-unique         Disable STB_GNU_UNIQUE symbol binding
  --no-lto-legacy-pass-manager
                          Use the new pass manager in LLVM
  --no-lto-pgo-warn-mismatch
                          turn off warnings about profile cfg mismatch
  --no-lto-unique-basic-block-section-names
                          Do not give unique names to every basic block section for LTO (default)
  --no-lto-whole-program-visibility
                          Asserts that the LTO link does not have whole program visibility
  --no-merge-exidx-entries
                          Disable merging .ARM.exidx entries
  --no-mmap-output-file   Do not mmap the output file for writing
  --no-nmagic             Page align sections (default)
  --no-omagic             Do not set the text data sections to be writable, page align sections (default)
  --no-optimize-bb-jumps  Do not remove any direct jumps at the end to the next basic block (default)
  --no-pcrel-optimize     (PowerPC64) Disable PC-relative optimizations
  --no-pie                Do not create a position independent executable (default)
  --no-power10-stubs      Alias for --power10-stubs=no
  --no-print-gc-sections  Do not list removed unused sections (default)
  --no-print-icf-sections Do not list identical folded sections (default)
  --no-relax              Disable target-specific relaxations
  --no-rosegment          Do not put read-only non-executable sections in their own segment
  --no-toc-optimize       (PowerPC64) Disable TOC related optimizations
  --no-undefined-version  Report version scripts that refer undefined symbols
  --no-undefined          Report unresolved symbols even if the linker is creating a shared library
  --no-use-android-relr-tags
                          Use SHT_RELR / DT_RELR* tags (default)
  --no-warn-backrefs      Do not warn about backward symbol references to extract archive members (default)
  --no-warn-common        Do not warn about duplicate common symbols (default)
  --no-warn-ifunc-textrel Do not warn about using ifunc symbols with text relocations (default)
  --no-warn-symbol-ordering
                          Do not warn about problems with the symbol ordering file
  --no-whole-archive      Do not force load of all members in a static library (default)
  --noinhibit-exec        Retain the executable output file whenever it is still usable
  --non_shared            Alias for --Bstatic
  --nostdlib              Only search directories specified on the command line
  -N                      Alias for --omagic
  -n                      Alias for --nmagic
  --oformat=[elf,binary]  Specify the binary format for the output object file
  --omagic                Set the text and data sections to be readable and writable, do not page align sections, link against static libraries
  --opt-remarks-filename <value>
                          YAML output file for optimization remarks
  --opt-remarks-format <value>
                          The format used for serializing remarks (default: YAML)
  --opt-remarks-hotness-threshold=<value>
                          Minimum profile count required for an optimization remark to be output. Use 'auto' to apply the threshold from profile summary.
  --opt-remarks-passes <value>
                          Regex for the passes that need to be serialized to the output file
  --opt-remarks-with-hotness
                          Include hotness information in the optimization remarks file
  --optimize-bb-jumps     Remove direct jumps at the end to the next basic block
  --orphan-handling=<value>
                          Control how orphan sections are handled when linker script used
  --output=<value>        Alias for -o
  --output <value>        Alias for -o
  -O <value>              Optimize output file size
  -o <path>               Path to file to write output
  --pack-dyn-relocs=[none,android,relr,android+relr]
                          Pack dynamic relocations in the given format
  --pcrel-optimize        (PowerPC64) Enable PC-relative optimizations (default)
  --pic-executable        Alias for --pie
  --pic-veneer            Always generate position independent thunks (veneers)
  --pie                   Create a position independent executable
  --plugin-opt=-<value>   Specify an LLVM option for compatibility with LLVMgold.so
  --plugin-opt=cs-profile-generate
                          Alias for --lto-cs-profile-generate
  --plugin-opt=cs-profile-path=<value>
                          Alias for --lto-cs-profile-file
  --plugin-opt=debug-pass-manager
                          Alias for --lto-debug-pass-manager
  --plugin-opt=disable-verify
                          Alias for --disable-verify
  --plugin-opt=dwo_dir=<value>
                          Directory to store .dwo files when LTO and debug fission are used
  --plugin-opt=emit-asm   Alias for --lto-emit-asm
  --plugin-opt=jobs=<value>
                          Alias for --thinlto-jobs
  --plugin-opt=legacy-pass-manager
                          Alias for --no-legacy-pass-manager
  --plugin-opt=lto-partitions=<value>
                          Alias for --lto-partitions
  --plugin-opt=new-pass-manager
                          Alias for --no-lto-legacy-pass-manager
  --plugin-opt=obj-path=<value>
                          Alias for --lto-obj-path=
  --plugin-opt=opt-remarks-filename=<value>
                          Alias for --opt-remarks-filename
  --plugin-opt=opt-remarks-format=<value>
                          Alias for --opt-remarks-format
  --plugin-opt=opt-remarks-hotness-threshold=<value>
                          Alias for --opt-remarks-hotness-threshold
  --plugin-opt=opt-remarks-passes=<value>
                          Alias for --opt-remarks-passes
  --plugin-opt=opt-remarks-with-hotness
                          Alias for --opt-remarks-with_hotness
  --plugin-opt=O<value>   Alias for --lto-O
  --plugin-opt=sample-profile=<value>
                          Alias for --lto-sample-profile
  --plugin-opt=save-temps Alias for --save-temps
  --plugin-opt=thinlto-emit-imports-files
                          Alias for --thinlto-emit-imports-files
  --plugin-opt=thinlto-index-only=<value>
                          Alias for --thinlto-index-only=
  --plugin-opt=thinlto-index-only
                          Alias for --thinlto-index-only
  --plugin-opt=thinlto-object-suffix-replace=<value>
                          Alias for --thinlto-object-suffix-replace=
  --plugin-opt=thinlto-prefix-replace=<value>
                          Alias for --thinlto-prefix-replace=
  --plugin=<value>        Ignored for compatibility with GNU linkers
  --pop-state             Restore the states saved by --push-state
  --power10-stubs=<mode>  Whether to use Power10 instructions in call stubs for R_PPC64_REL24_NOTOC and TOC/NOTOC interworking (yes (default): use; no: don't use). "auto" is currently the same as "yes"
  --power10-stubs         Alias for --power10-stubs=auto
  --print-archive-stats=<value>
                          Write archive usage statistics to the specified file. Print the numbers of members and extracted members for each archive
  --print-gc-sections     List removed unused sections
  --print-icf-sections    List identical folded sections
  --print-map             Print a link map to the standard output
  --print-symbol-order=<value>
                          Print a symbol order specified by --call-graph-ordering-file into the specified file
  --push-state            Save the current state of --as-needed, -static and --whole-archive
  -q                      Alias for --emit-relocs
  --relax                 Enable target-specific relaxations if supported (default)
  --relocatable           Create relocatable object file
  --reproduce=<value>     Write tar file containing inputs and command to reproduce link
  --retain-symbols-file=<file>
                          Retain only the symbols listed in the file
  --rosegment             Put read-only non-executable sections in their own segment (default)
  --rpath=<value>         Add a DT_RUNPATH to the output
  --rsp-quoting=[posix,windows]
                          Quoting style for response files
  -R <value>              Alias for --rpath
  -r                      Alias for --relocatable
  --save-temps            Save intermediate LTO compilation results
  --script=<value>        Read linker script
  --section-start=<address>
                          Set address of section
  --shared                Build a shared object
  --shuffle-sections=<section-glob>=<seed>
                          Shuffle matched sections using the given seed before mapping them to the output sections. If -1, reverse the section order. If 0, use a random seed
  --soname=<value>        Set DT_SONAME
  --sort-section=<value>  Specifies sections sorting rule when linkerscript is used
  --split-stack-adjust-size=<value>
                          Specify adjustment to stack size when a split-stack function calls a non-split-stack function
  --start-group           Ignored for compatibility with GNU unless you pass --warn-backrefs
  --start-lib             Start a grouping of objects that should be treated as if they were together in an archive
  --static                Alias for --Bstatic
  --strip-all             Strip all symbols. Implies --strip-debug
  --strip-debug           Strip debugging information
  --symbol-ordering-file=<value>
                          Layout sections to place symbols in the order specified by symbol ordering file
  --sysroot=<value>       Set the system root
  -S                      Alias for --strip-debug
  -s                      Alias for --strip-all
  --target1-abs           Interpret R_ARM_TARGET1 as R_ARM_ABS32 (default)
  --target1-rel           Interpret R_ARM_TARGET1 as R_ARM_REL32
  --target2=<type>        Interpret R_ARM_TARGET2 as <type>, where <type> is one of rel, abs, or got-rel
  --Tbss=<value>          Same as --section-start with .bss as the sectionname
  --Tdata=<value>         Same as --section-start with .data as the sectionname
  --thinlto-cache-dir=<value>
                          Path to ThinLTO cached object file directory
  --thinlto-cache-policy=<value>
                          Pruning policy for the ThinLTO cache
  --thinlto-jobs=<value>  Number of ThinLTO jobs. Default to --threads=
  --thinlto-single-module=<value>
                          Specific a single module to compile in ThinLTO mode, for debugging only
  --threads=<value>       Number of threads. '1' disables multi-threading. By default all available hardware threads are used
  --time-trace-file=<value>
                          Specify time trace output file
  --time-trace-granularity=<value>
                          Minimum time granularity (in microseconds) traced by time profiler
  --time-trace            Record time trace
  --toc-optimize          (PowerPC64) Enable TOC related optimizations (default)
  --trace-symbol=<value>  Trace references to symbols
  --trace                 Print the names of the input files
  --Ttext=<value>         Same as --section-start with .text as the sectionname
  -T <value>              Alias for --script
  -t                      Alias for --trace
  --undefined-glob=<pattern>
                          Force undefined symbol during linking
  --undefined-version     Allow unused version in version script (default)
  --undefined=<symbol>    Force undefined symbol during linking
  --unique                Creates a separate output section for every orphan input section
  --unresolved-symbols=<value>
                          Determine how to handle unresolved symbols
  --use-android-relr-tags Use SHT_ANDROID_RELR / DT_ANDROID_RELR* tags instead of SHT_RELR / DT_RELR*
  -u <value>              Alias for --undefined
  --verbose               Verbose mode
  --version-script=<value>
                          Read a version script
  --version               Display the version number and exit
  --vs-diagnostics        Format diagnostics for Visual Studio compatibility
  -V                      Alias for --version
  -v                      Display the version number
  --warn-backrefs-exclude=<glob>
                          Glob describing an archive (or an object file within --start-lib) which should be ignored for --warn-backrefs.
  --warn-backrefs         Warn about backward symbol references to extract archive members
  --warn-common           Warn about duplicate common symbols
  --warn-ifunc-textrel    Warn about using ifunc symbols with text relocations
  --warn-symbol-ordering  Warn about problems with the symbol ordering file (default)
  --warn-unresolved-symbols
                          Report unresolved symbols as warnings
  --whole-archive         Force load of all members in a static library
  --why-extract=<value>   Print to a file about why archive members are extracted
  --wrap=<symbol>         Redirect symbol references to __wrap_symbol and __real_symbol references to symbol
  -X                      Alias for --discard-locals
  -x                      Alias for --discard-all
  -y <value>              Alias for --trace-symbol
  -z <option>             Linker option extensions

ld.lld: supported targets: elf
```

***

**lld**

ELF linker from the LLVM project

```
:~# man lld
LD.LLD(1)                 BSD General Commands Manual                LD.LLD(1)

NAME
     ld.lld -- ELF linker from the LLVM project

SYNOPSIS
     ld.lld [options] objfile ...

DESCRIPTION
     A linker takes one or more object, archive, and library files, and com-
     bines them into an output file (an executable, a shared library, or an-
     other object file).  It relocates code and data from the input files and
     resolves symbol references between them.

     ld.lld is a drop-in replacement for the GNU BFD and gold linkers.  It ac-
     cepts most of the same command line arguments and linker scripts as GNU
     linkers.

     ld.lld currently supports i386, x86-64, ARM, AArch64, PowerPC32, Pow-
     erPC64, MIPS32, MIPS64, RISC-V, AMDGPU, Hexagon and SPARC V9 targets.
     ld.lld acts as a Microsoft link.exe-compatible linker if invoked as
     lld-link and as macOS's ld if invoked as ld.ld64. All these targets are
     always supported however ld.lld was built, so you can always use ld.lld
     as a native linker as well as a cross linker.

OPTIONS
     Many options have both a single-letter and long form.  When using the
     long form options other than those beginning with the letter o may be
     specified using either one or two dashes preceding the option name.  Long
     options beginning with o require two dashes to avoid confusion with the
     -o path option.

     --allow-multiple-definition
             Do not error if a symbol is defined multiple times.  The first
             definition will be used.

     --allow-shlib-undefined
             Allow unresolved references in shared libraries.  This option is
             enabled by default when linking a shared library.

     --apply-dynamic-relocs
             Apply link-time values for dynamic relocations.

     --as-needed
             Only set DT_NEEDED for shared libraries if used.

     --auxiliary=value
             Set the DT_AUXILIARY field to the specified name.

     --Bdynamic, --dy
             Link against shared libraries.

     --Bstatic, --static, --dn
             Do not link against shared libraries.

     -Bno-symbolic
             Don't bind default visibility defined symbols locally for -shared
             (default).

     -Bsymbolic
             Bind default visibility defined symbols locally for -shared. Also
             set the DF_SYMBOLIC flag.

     -Bsymbolic-functions
             Bind default visibility defined function symbols locally for
             -shared.

     -Bsymbolic-non-weak-functions
             Bind default visibility defined STB_GLOBAL function symbols lo-
             cally for -shared.

     --build-id=value
             Generate a build ID note.  value may be one of fast, md5, sha1,
             tree, uuid, 0xhex-string, and none.  tree is an alias for sha1.
             Build-IDs of type fast, md5, sha1, and tree are calculated from
             the object contents.  fast is not intended to be cryptographi-
             cally secure.

     --build-id
             Synonym for --build-id=fast.

     --color-diagnostics=value
             Use colors in diagnostics.  value may be one of always, auto, and
             never.  auto enables color if and only if output is to a termi-
             nal.

     --color-diagnostics
             Alias for --color-diagnostics=auto.

     --compress-debug-sections=value
             Compress DWARF debug sections.  value may be none or zlib.  The
             default compression level is 1 (fastest) as the debug info usu-
             ally compresses well at that level, but if you want to compress
             it more, you can specify -O2 to set the compression level to 6.

     --cref  Output cross reference table. If -Map is specified, print to the
             map file.

     --define-common, -d
             Assign space to common symbols.

     --defsym=symbol=expression
             Define a symbol alias.  expression may be another symbol or a
             linker script expression.  For example, '--defsym=foo=bar' or
             '--defsym=foo=bar+0x100'.

     --demangle
             Demangle symbol names.

     --disable-new-dtags
             Disable new dynamic tags.

     --discard-all, -x
             Delete all local symbols.

     --discard-locals, -X
             Delete temporary local symbols.

     --discard-none
             Keep all symbols in the symbol table.

     --dynamic-linker=value
             Specify the dynamic linker to be used for a dynamically linked
             executable.  This is recorded in an ELF segment of type
             PT_INTERP.

     --dynamic-list=file
             Similar to --export-dynamic-symbol-list.  When creating a shared
             object, implies -Bsymbolic but does not set DF_SYMBOLIC

     --EB    Select the big-endian format in the OUTPUT_FORMAT command.

     --EL    Select the little-endian format in the OUTPUT_FORMAT command.

     --eh-frame-hdr
             Request creation of .eh_frame_hdr section and PT_GNU_EH_FRAME
             segment header.

     --emit-relocs, -q
             Generate relocations in the output.

     --enable-new-dtags
             Enable new dynamic tags.

     --end-lib
             End a grouping of objects that should be treated as if they were
             together in an archive.

     --entry=entry
             Name of entry point symbol.

     --error-limit=value
             Maximum number of errors to emit before stopping.  A value of
             zero indicates that there is no limit.

     --error-unresolved-symbols
             Report unresolved symbols as errors.

     --error-handing-script=script_path
             Call script script_path upon some error, with tag as first argu-
             ment, and an extra parameter as second argument. The script is
             expected to return 0 on success. Any other value is considered a
             generic error.  tag may be missing-lib followed by the name of
             the missing library.  undefined-symbol followed by the name of
             the undefined symbol.

     --execute-only
             Mark executable sections unreadable.  This option is currently
             only supported on AArch64.

     --exclude-libs=value
             Exclude static libraries from automatic export.

     --export-dynamic, -E
             Put symbols in the dynamic symbol table.

     --export-dynamic-symbol=glob
             (executable) Put matched non-local defined symbols to the dynamic
             symbol table.  (shared object) References to matched non-local
             STV_DEFAULT symbols shouldn't be bound to definitions within the
             shared object even if they would otherwise be due to -Bsymbolic ,
             -Bsymbolic-functions or --dynamic-list

     --export-dynamic-symbol-list=file
             Read a list of dynamic symbol patterns from file.  Apply
             --export-dynamic-symbol on each pattern.

     --fatal-warnings
             Treat warnings as errors.

     --filter=value, -F value
             Set the DT_FILTER field to the specified value.

     --fini=symbol
             Specify a finalizer function.

     --format=input-format, -b input-format
             Specify the format of the inputs following this option.
             input-format may be one of binary, elf, and default.  default is
             a synonym for elf.

     --gc-sections
             Enable garbage collection of unused sections.

     --gdb-index
             Generate .gdb_index section.

     --hash-style=value
             Specify hash style.  value may be sysv, gnu, or both.  both is
             the default.

     --help  Print a help message.

     --icf=all
             Enable identical code folding.

     --icf=safe
             Enable safe identical code folding.

     --icf=none
             Disable identical code folding.

     --ignore-data-address-equality
             Ignore address equality of data. C/C++ requires each data to have
             a unique address.  This option allows lld to do unsafe optimiza-
             tion that breaks the requirement: create copies of read-only data
             or merge two or more read-only data that happen to have the same
             value.

     --ignore-function-address-equality
             Ignore address equality of functions.  This option allows non-PIC
             calls to a function with non-default visibility in a shared ob-
             ject.  The function may have different addresses within the exe-
             cutable and within the shared object.

     --image-base=value
             Set the base address to value.

     --init=symbol
             Specify an initializer function.

     --keep-unique=symbol
             Do not fold symbol during ICF.

     -l libName, --library=libName
             Root name of library to use.

     -L dir, --library-path=dir
             Add a directory to the library search path.

     --lto-aa-pipeline=value
             AA pipeline to run during LTO.  Used in conjunction with
             --lto-newpm-passes.

     --lto-newpm-passes=value
             Passes to run during LTO.

     --lto-Oopt-level
             Optimization level for LTO.

     --lto-partitions=value
             Number of LTO codegen partitions.

     -m value
             Set target emulation.

     --Map=file, -M file
             Print a link map to file.

     --nmagic, -n
             Do not page align sections, link against static libraries.

     --no-allow-shlib-undefined
             Do not allow unresolved references in shared libraries.  This op-
             tion is enabled by default when linking an executable.

     --no-as-needed
             Always set DT_NEEDED for shared libraries.

     --no-color-diagnostics
             Do not use colors in diagnostics.

     --no-define-common
             Do not assign space to common symbols.

     --no-demangle
             Do not demangle symbol names.

     --no-dynamic-linker
             Inhibit output of an .interp section.

     --no-fortran-common
             Do not search archive members for definitions to override COMMON
             symbols.

     --no-gc-sections
             Disable garbage collection of unused sections.

     --no-gnu-unique
             Disable STB_GNU_UNIQUE symbol binding.

     --no-merge-exidx-entries
             Disable merging .ARM.exidx entries.

     --no-nmagic
             Page align sections.

     --no-omagic
             Do not set the text data sections to be writable, page align sec-
             tions.

     --no-relax
             Disable target-specific relaxations. For x86-64 this disables
             R_X86_64_GOTPCRELX and R_X86_64_REX_GOTPCRELX GOT optimization.

     --no-rosegment
             Do not put read-only non-executable sections in their own seg-
             ment.

     --no-undefined-version
             Report version scripts that refer undefined symbols.

     --no-undefined
             Report unresolved symbols even if the linker is creating a shared
             library.

     --no-warn-symbol-ordering
             Do not warn about problems with the symbol ordering file or call
             graph profile.

     --no-whole-archive
             Restores the default behavior of loading archive members.

     --no-pie, --no-pic-executable
             Do not create a position independent executable.

     --noinhibit-exec
             Retain the executable output file whenever it is still usable.

     --nostdlib
             Only search directories specified on the command line.

     -o path
             Write the output executable, library, or object to path.  If not
             specified, a.out is used as a default.

     -Ovalue
             Optimize output file size.  value may be:

             0   Disable string merging.
             1   Enable string merging.
             2   Enable string tail merging. If --compress-debug-sections is
                 given, compress debug sections at compression level 6 instead
                 of 1.

             -O1 is the default.

     --oformat=format
             Specify the format for the output object file.  The only sup-
             ported format is binary, which produces output with no ELF
             header.

     --omagic, -N
             Set the text and data sections to be readable and writable, do
             not page align sections, link against static libraries.

     --opt-remarks-filename file
             Write optimization remarks in YAML format to file.

     --opt-remarks-passes pass-regex
             Filter optimization remarks by only allowing the passes matching
             pass-regex.

     --opt-remarks-with-hotness
             Include hotness information in the optimization remarks file.

     --orphan-handling=mode
             Control how orphan sections are handled.  An orphan section is
             one not specifically mentioned in a linker script.  mode may be:

             place
                 Place orphan sections in suitable output sections.
             warn
                 Place orphan sections as for place and also report a warning.
             error
                 Place orphan sections as for place and also report an error.

             place is the default.

     --pack-dyn-relocs=format
             Pack dynamic relocations in the given format.  format may be:

             none
                 Do not pack.  Dynamic relocations are encoded in SHT_REL(A).
             android
                 Pack dynamic relocations in SHT_ANDROID_REL(A).
             relr
                 Pack relative relocations in SHT_RELR, and the rest of dy-
                 namic relocations in SHT_REL(A).
             android+relr
                 Pack relative relocations in SHT_RELR, and the rest of dy-
                 namic relocations in SHT_ANDROID_REL(A).

             none is the default.  If --use-android-relr-tags is specified,
             use SHT_ANDROID_RELR instead of SHT_RELR.

     --pic-veneer
             Always generate position independent thunks.

     --pie, --pic-executable
             Create a position independent executable.

     --power10-stubs=mode
             Whether to use Power10 instructions in call stubs for
             R_PPC64_REL24_NOTOC and TOC/NOTOC interworking.  mode may be:

             yes
                 (default) Use.
             auto
                 Currently the same as yes.
             no  Don't use.

     --print-gc-sections
             List removed unused sections.

     --print-icf-sections
             List identical folded sections.

     --print-map
             Print a link map to the standard output.

     --print-archive-stats=file
             Write archive usage statistics to the specified file.  Print the
             numbers of members and fetched members for each archive.

     --push-state
             Save the current state of --as-needed, --static, and
             --whole-archive.

     --pop-state
             Restore the states saved by --push-state.

     --relocatable, -r
             Create relocatable object file.

     --reproduce=path
             Write a tar file to path, containing all the input files needed
             to reproduce the link, a text file called response.txt containing
             the command line options and a text file called version.txt con-
             taining the output of ld.lld --version.  The archive when un-
             packed can be used to re-run the linker with the same options and
             input files.

     --retain-symbols-file=file
             Retain only the symbols listed in the file.

     --rpath=value, -R value
             Add a DT_RUNPATH to the output.

     --rsp-quoting=value
             Quoting style for response files.  The supported values are
             windows and posix.

     --script=file, -T file
             Read linker script from file.  If multiple linker scripts are
             given, they are processed as if they were concatenated in the or-
             der they appeared on the command line.

     --section-start=section=address
             Set address of section.

     --shared, --Bsharable
             Build a shared object.

     --shuffle-sections=seed
             Shuffle matched sections using the given seed before mapping them
             to the output sections.  If -1, reverse the section order. If 0,
             use a random seed.

     --soname=value, -h value
             Set DT_SONAME to value.

     --sort-common
             This option is ignored for GNU compatibility.

     --sort-section=value
             Specifies sections sorting rule when linkerscript is used.

     --start-lib
             Start a grouping of objects that should be treated as if they
             were together in an archive.

     --strip-all, -s
             Strip all symbols.  Implies --strip-debug.

     --strip-debug, -S
             Strip debugging information.

     --symbol-ordering-file=file
             Lay out sections in the order specified by file.

     --sysroot=value
             Set the system root.

     --target1-abs
             Interpret R_ARM_TARGET1 as R_ARM_ABS32.

     --target1-rel
             Interpret R_ARM_TARGET1 as R_ARM_REL32.

     --target2=type
             Interpret R_ARM_TARGET2 as type, where type is one of rel, abs,
             or got-rel.

     --Tbss=value
             Same as --section-start with .bss as the sectionname.

     --Tdata=value
             Same as --section-start with .data as the sectionname.

     --Ttext=value
             Same as --section-start with .text as the sectionname.

     --thinlto-cache-dir=value
             Path to ThinLTO cached object file directory.

     --thinlto-cache-policy=value
             Pruning policy for the ThinLTO cache.

     --thinlto-jobs=value
             Number of ThinLTO jobs.

     --threads=N
             Number of threads.  all (default) means all of concurrent threads
             supported.  1 disables multi-threading.

     --time-trace
             Record time trace.

     --time-trace-file=file
             Write time trace output to file.

     --time-trace-granularity=value
             Minimum time granularity (in microseconds) traced by time pro-
             filer.

     --trace
             Print the names of the input files.

     --trace-symbol=symbol, -y symbol
             Trace references to symbol.

     --undefined=symbol, -u symbol
             If symbol is not defined after symbol resolution, and there's a
             static library that contains an object file defining the symbol,
             load the member to include the object file in the output file.

     --undefined-glob=pattern
             Synonym for --undefined, except that it takes a glob pattern.  In
             a glob pattern, * matches zero or more characters, ?  matches any
             single character, and [...] matches the characters within brack-
             ets.  All symbols that match a given pattern are handled as if
             they were given as arguments of --undefined.

     --unique
             Creates a separate output section for every orphan input section.

     --unresolved-symbols=value
             Determine how to handle unresolved symbols.

     --use-android-relr-tags
             Use SHT_ANDROID_RELR / DT_ANDROID_RELR* tags instead of SHT_RELR
             / DT_RELR*.

     -v      Display the version number and proceed with linking if object
             files are specified.

     -V, --version
             Display the version number and exit.

     --verbose
             Verbose mode.

     --version-script=file
             Read version script from file.

     --warn-backrefs
             Warn about reverse or cyclic dependencies to or between static
             archives.  This can be used to ensure linker invocation remains
             compatible with traditional Unix-like linkers.

     --warn-backrefs-exclude=glob
             Glob describing an archive (or an object file within --start-lib)
             which should be ignored for --warn-backrefs

     --warn-common
             Warn about duplicate common symbols.

     --warn-ifunc-textrel
             Warn about using ifunc symbols in conjunction with text reloca-
             tions.  Older versions of glibc library (2.28 and earlier) has a
             bug that causes the segment that includes ifunc symbols to be
             marked as not executable when they are relocated.  As a result,
             although the program compiles and links successfully, it gives
             segmentation fault when the instruction pointer reaches an ifunc
             symbol.  Use -warn-ifunc-textrel to let lld give a warning, if
             the code may include ifunc symbols, may do text relocations and
             be linked with an older glibc version.  Otherwise, there is no
             need to use it, as the default value does not give a warning.
             This flag has been introduced in late 2018, has no counter part
             in ld and gold linkers, and may be removed in the future.

     --warn-unresolved-symbols
             Report unresolved symbols as warnings.

     --whole-archive
             Force load of all members in a static library.

     --why-extract=file
             Print to a file about why archive members are extracted.

     --wrap=symbol
             Redirect symbol references to __wrap_symbol and __real_symbol
             references to symbol.

     -z option
             Linker option extensions.

             dead-reloc-in-nonalloc=section_glob=value
                     Resolve a relocation in a matched non-SHF_ALLOC section
                     referencing a discarded symbol to value Accepts globs, in
                     the event of a section matching more than one option, the
                     last option takes precedence. An order of least specific
                     to most specific match is recommended.

             execstack
                     Make the main stack executable.  Stack permissions are
                     recorded in the PT_GNU_STACK segment.

             bti-report=[none|warning|error]
                     Specify how to report the missing GNU_PROP-
                     ERTY_AARCH64_FEATURE_1_BTI property.  none is the de-
                     fault, linker will not report the missing property other-
                     wise will be reported as a warning or an error.

             cet-report=[none|warning|error]
                     Specify how to report the missing GNU_PROPERTY_X86_FEA-
                     TURE_1_IBT or GNU_PROPERTY_X86_FEATURE_1_SHSTK proper-
                     ties.  none is the default, linker will not report the
                     missing property otherwise will be reported as a warning
                     or an error.

             force-bti
                     Force enable AArch64 BTI instruction in PLT, warn if In-
                     put ELF file does not have GNU_PROPERTY_AARCH64_FEA-
                     TURE_1_BTI property.

             force-ibt
                     Force enable Intel Indirect Branch Tracking in PLT, warn
                     if an input ELF file does not have GNU_PROPERTY_X86_FEA-
                     TURE_1_IBT property.

             global  Sets the DF_1_GLOBAL flag in the DYNAMIC section.  Dif-
                     ferent loaders can decide how to handle this flag on
                     their own.

             ifunc-noplt
                     Do not emit PLT entries for ifunc symbols.  Instead, emit
                     text relocations referencing the resolver.  This is an
                     experimental optimization and only suitable for stand-
                     alone environments where text relocations do not have the
                     usual drawbacks.  This option must be combined with the
                     -z notext option.

             initfirst
                     Sets the DF_1_INITFIRST flag to indicate the module
                     should be initialized first.

             interpose
                     Set the DF_1_INTERPOSE flag to indicate to the runtime
                     linker that the object is an interposer.  During symbol
                     resolution interposers are searched after the application
                     but before other dependencies.

             muldefs
                     Do not error if a symbol is defined multiple times.  The
                     first definition will be used.  This is a synonym for
                     --allow-multiple-definition.

             nocombreloc
                     Disable combining and sorting multiple relocation sec-
                     tions.

             nocopyreloc
                     Disable the creation of copy relocations.

             nodefaultlib
                     Set the DF_1_NODEFLIB flag to indicate that default li-
                     brary search paths should be ignored.

             nodelete
                     Set the DF_1_NODELETE flag to indicate that the object
                     cannot be unloaded from a process.

             nodlopen
                     Set the DF_1_NOOPEN flag to indicate that the object may
                     not be opened by dlopen(3).

             nognustack
                     Do not emit the PT_GNU_STACK segment.

             norelro
                     Do not indicate that portions of the object should be
                     mapped read-only after initial relocation processing.
                     The object will omit the PT_GNU_RELRO segment.

             notext  Allow relocations against read-only segments.  Sets the
                     DT_TEXTREL flag in the DYNAMIC section.

             now     Set the DF_BIND_NOW flag to indicate that the run-time
                     loader should perform all relocation processing as part
                     of object initialization.  By default relocations may be
                     performed on demand.

             origin  Set the DF_ORIGIN flag to indicate that the object re-
                     quires $ORIGIN processing.

             pac-plt
                     AArch64 only, use pointer authentication in PLT.

             rel     Use REL format for dynamic relocations.

             rela    Use RELA format for dynamic relocations.

             retpolineplt
                     Emit retpoline format PLT entries as a mitigation for
                     CVE-2017-5715.

             rodynamic
                     Make the .dynamic section read-only.  The DT_DEBUG tag
                     will not be emitted.

             separate-loadable-segments
             separate-code
             noseparate-code
                     Specify whether two adjacent PT_LOAD segments are allowed
                     to overlap in pages.  noseparate-code (default) allows
                     overlap.  separate-code allows overlap between two exe-
                     cutable segments, or two non-executable segments.
                     separate-loadable-segments disallows overlap.

             shstk   x86 only, use shadow stack.

             stack-size=size
                     Set the main thread's stack size to size.  The stack size
                     is recorded as the size of the size.  PT_GNU_STACK pro-
                     gram segment.

             start-stop-gc
                     Don't let __start_/__stop_ references retain the associ-
                     ated C identifier name sections (default).

             nostart-stop-gc
                     Let __start_/__stop_ references retain the associated C
                     identifier name sections.

             text    Do not allow relocations against read-only segments.
                     This is the default.

             wxneeded
                     Create a PT_OPENBSD_WXNEEDED segment.

IMPLEMENTATION NOTES
     ld.lld's handing of archive files (those with a .a file extension) is
     different from traditional linkers used on Unix-like systems.

     Traditional linkers maintain a set of undefined symbols during linking.
     The linker processes each file in the order in which it appears on the
     command line, until the set of undefined symbols becomes empty.  An ob-
     ject file is linked into the output object when it is encountered, with
     its undefined symbols added to the set.  Upon encountering an archive
     file a traditional linker searches the objects contained therein, and
     processes those that satisfy symbols in the unresolved set.

     Handling mutually dependent archives may be awkward when using a tradi-
     tional linker.  Archive files may have to be specified multiple times, or
     the special command line options --start-group and --end-group may be
     used to have the linker loop over the files in the group until no new
     symbols are added to the set.

     ld.lld records all symbols found in objects and archives as it iterates
     over command line arguments.  When ld.lld encounters an undefined symbol
     that can be resolved by an object file contained in a previously pro-
     cessed archive file, it immediately extracts and links it into the output
     object.

     With certain archive inputs ld.lld may produce different results compared
     to traditional linkers.  In practice, large bodies of third party soft-
     ware have been linked with ld.lld without material issues.

     The --warn-backrefs option may be used to identify a linker invocation
     that may be incompatible with traditional Unix-like linker behavior.

BSD                              May 12, 2019                              BSD
```

***

**lld-link**

***

**wasm-ld**

```
:~# wasm-ld --help
OVERVIEW: LLVM Linker

USAGE: wasm-ld [options] file...

OPTIONS:
  --allow-undefined-file=<value>
                         Allow symbols listed in <file> to be undefined in linked binary
  --allow-undefined      Allow undefined symbols in linked binary. This options is equivalent to --import-undefined and --unresolved-symbols=ignore-all
  --Bsymbolic            Bind defined symbols locally
  --check-features       Check feature compatibility of linked objects (default)
  --color-diagnostics=[auto,always,never]
                         Use colors in diagnostics (default: auto)
  --color-diagnostics    Alias for --color-diagnostics=always
  --compress-relocations Compress the relocation targets in the code section.
  --demangle             Demangle symbol names
  --emit-relocs          Generate relocations in output
  --entry <entry>        Name of entry point symbol
  --error-limit=<value>  Maximum number of errors to emit before stopping (0 = no limit)
  --error-unresolved-symbols
                         Report unresolved symbols as errors
  --experimental-pic     Enable Experimental PIC
  --export-all           Export all symbols (normally combined with --no-gc-sections)
  --export-dynamic       Put symbols in the dynamic symbol table
  --export-if-defined=<value>
                         Force a symbol to be exported, if it is defined in the input
  --export-table         Export function table to the environment
  --export=<value>       Force a symbol to be exported
  -E                     Alias for --export-dynamic
  --fatal-warnings       Treat warnings as errors
  --features=<value>     Comma-separated used features, inferred from input objects by default.
  --gc-sections          Enable garbage collection of unused sections
  --global-base=<value>  Where to start to place global data
  --growable-table       Remove maximum size from function table, allowing table to grow
  --help                 Print option help
  --import-memory        Import memory from the environment
  --import-table         Import function table from the environment
  --import-undefined     Turn undefined symbols into imports where possible
  --initial-memory=<value>
                         Initial size of the linear memory
  --lto-debug-pass-manager
                         Debug new pass manager
  --lto-legacy-pass-manager
                         Use legacy pass manager
  --lto-O<opt-level>     Optimization level for LTO
  --lto-partitions=<value>
                         Number of LTO codegen partitions
  -L <dir>               Add a directory to the library search path
  -l <libName>           Root name of library to use
  --Map=<value>          Print a link map to the specified file
  --max-memory=<value>   Maximum size of the linear memory
  --merge-data-segments  Enable merging data segments
  --mllvm <value>        Options to pass to LLVM
  -M                     Alias for --print-map
  -m <value>             Set target emulation
  --no-check-features    Ignore feature compatibility of linked objects
  --no-color-diagnostics Alias for --color-diagnostics=never
  --no-demangle          Do not demangle symbol names
  --no-entry             Do not output any entry point
  --no-export-dynamic    Do not put symbols in the dynamic symbol table (default)
  --no-gc-sections       Disable garbage collection of unused sections
  --no-lto-legacy-pass-manager
                         Use new pass manager
  --no-merge-data-segments
                         Disable merging data segments
  --no-pie               Do not create a position independent executable (default)
  --no-print-gc-sections Do not list removed unused sections
  --no-whole-archive     Do not force load of all members in a static library (default)
  -O <value>             Optimize output file size
  -o <path>              Path to file to write output
  --pie                  Create a position independent executable
  --print-gc-sections    List removed unused sections
  --print-map            Print a link map to the standard output
  --relocatable          Create relocatable object file
  --reproduce=<value>    Dump linker invocation and input files for debugging
  --rsp-quoting=[posix,windows]
                         Quoting style for response files
  --save-temps           Save intermediate LTO compilation results
  --shared-memory        Use shared linear memory
  --shared               Build a shared object
  --stack-first          Place stack at start of linear memory rather than after data
  --strip-all            Strip all symbols
  --strip-debug          Strip debugging information
  -S                     Alias for --strip-debug
  -s                     Alias for --strip-all
  --thinlto-cache-dir=<value>
                         Path to ThinLTO cached object file directory
  --thinlto-cache-policy=<value>
                         Pruning policy for the ThinLTO cache
  --thinlto-jobs=<value> Number of ThinLTO jobs. Default to --threads=
  --threads=<value>      Number of threads. '1' disables multi-threading. By default all available hardware threads are used
  --trace-symbol=<value> Trace references to symbols
  --trace                Print the names of the input files
  -t                     Alias for --trace
  --undefined=<value>    Force undefined symbol during linking
  --unresolved-symbols=<value>
                         Determine how to handle unresolved symbols
  --verbose              Verbose mode
  --version              Display the version number and exit
  -v                     Display the version number
  --warn-unresolved-symbols
                         Report unresolved symbols as warnings
  --whole-archive        Force load of all members in a static library
  --wrap=<symbol>=<symbol>
                         Use wrapper functions for symbol
  -y <value>             Alias for --trace-symbol
  -z <option>            Linker option extensions
```

***

#### lldb <a href="#lldb" id="lldb"></a>

LLDB is a next generation, high-performance debugger. It is built as a set of reusable components which highly leverage existing libraries in the larger LLVM Project, such as the Clang expression parser and LLVM disassembler.

This is a dependency package providing the default version of lldb.

**Installed size:** `17 KB`\
**How to install:** `sudo apt install lldb`

<details>

<summary>Dependencies:</summary>

* lldb-14

</details>

**lldb**

Manual page for lldb 14

```
:~# lldb -h
OVERVIEW: LLDB

USAGE: lldb [options]

ATTACHING:
  --attach-name <name> Tells the debugger to attach to a process with the given name.
  --attach-pid <pid>   Tells the debugger to attach to a process with the given pid.
  -n <value>           Alias for --attach-name
  -p <value>           Alias for --attach-pid
  --wait-for           Tells the debugger to wait for a process with the given pid or name to launch before attaching.
  -w                   Alias for --wait-for

COMMANDS:
  --batch              Tells the debugger to run the commands from -s, -S, -o & -O, and then quit.
  -b                   Alias for --batch
  -K <value>           Alias for --source-on-crash
  -k <value>           Alias for --one-line-on-crash
  --local-lldbinit     Allow the debugger to parse the .lldbinit files in the current working directory, unless --no-lldbinit is passed.
  --no-lldbinit        Do not automatically parse any '.lldbinit' files.
  --one-line-before-file <command>
                       Tells the debugger to execute this one-line lldb command before any file provided on the command line has been loaded.
  --one-line-on-crash <command>
                       When in batch mode, tells the debugger to run this one-line lldb command if the target crashes.
  --one-line <command> Tells the debugger to execute this one-line lldb command after any file provided on the command line has been loaded.
  -O <value>           Alias for --one-line-before-file
  -o <value>           Alias for --one-line
  -Q                   Alias for --source-quietly
  --source-before-file <file>
                       Tells the debugger to read in and execute the lldb commands in the given file, before any file has been loaded.
  --source-on-crash <file>
                       When in batch mode, tells the debugger to source this file of lldb commands if the target crashes.
  --source-quietly     Tells the debugger not to echo commands while sourcing files or one-line commands provided on the command line.
  --source <file>      Tells the debugger to read in and execute the lldb commands in the given file, after any file has been loaded.
  -S <value>           Alias for --source-before-file
  -s <value>           Alias for --source
  -x                   Alias for --no-lldbinit

OPTIONS:
  --arch <architecture> Tells the debugger to use the specified architecture when starting and running the program.
  -a <value>            Alias for --arch
  --capture-path <filename>
                        Tells the debugger to use the given filename for the reproducer.
  --capture             Tells the debugger to capture a reproducer.
  --core <filename>     Tells the debugger to use the full path to <filename> as the core file.
  -c <value>            Alias for --core
  --debug               Tells the debugger to print out extra information for debugging itself.
  -d                    Alias for --debug
  --editor              Tells the debugger to open source files using the host's "external editor" mechanism.
  -e                    Alias for --editor
  --file <filename>     Tells the debugger to use the file <filename> as the program to be debugged.
  -f <value>            Alias for --file
  --help                Prints out the usage information for the LLDB debugger.
  -h                    Alias for --help
  --no-use-colors       Do not use colors.
  --reproducer-generate-on-exit
                        Generate reproducer on exit.
  --version             Prints out the current version number of the LLDB debugger.
  -v                    Alias for --version
  -X                    Alias for --no-use-color

REPL:
  -r=<flags>     Alias for --repl=<flags>
  --repl-language <language>
                 Chooses the language for the REPL.
  --repl=<flags> Runs lldb in REPL mode with a stub process with the given flags.
  --repl         Runs lldb in REPL mode with a stub process.
  -R <value>     Alias for --repl-language
  -r             Alias for --repl

SCRIPTING:
  -l <value>    Alias for --script-language
  --print-script-interpreter-info
                Prints out a json dictionary with information about the scripting language interpreter.
  --python-path Prints out the path to the lldb.py file for this version of lldb.
  -P            Alias for --python-path
  --script-language <language>
                Tells the debugger to use the specified scripting language for user-defined scripts.

EXAMPLES:
  The debugger can be started in several modes.

  Passing an executable as a positional argument prepares lldb to debug the
  given executable. To disambiguate between arguments passed to lldb and
  arguments passed to the debugged executable, arguments starting with a - must
  be passed after --.

    lldb --arch x86_64 /path/to/program program argument -- --arch armv7

  For convenience, passing the executable after -- is also supported.

    lldb --arch x86_64 -- /path/to/program program argument --arch armv7

  Passing one of the attach options causes lldb to immediately attach to the
  given process.

    lldb -p <pid>
    lldb -n <process-name>

  Passing --repl starts lldb in REPL mode.

    lldb -r

  Passing --core causes lldb to debug the core file.

    lldb -c /path/to/core

  Command options can be combined with these modes and cause lldb to run the
  specified commands before or after events, like loading the file or crashing,
  in the order provided on the command line.

    lldb -O 'settings set stop-disassembly-count 20' -o 'run' -o 'bt'
    lldb -S /source/before/file -s /source/after/file
    lldb -K /source/before/crash -k /source/after/crash

  Note: In REPL mode no file is loaded, so commands specified to run after
  loading the file (via -o or -s) will be ignored.
```

***

**lldb-argdumper**

```
:~# lldb-argdumper -h
{"arguments":["-h"]}
```

***

**lldb-server**

```
:~# lldb-server -h
Usage:
  lldb-server v[ersion]
  lldb-server g[dbserver] [options]
  lldb-server p[latform] [options]
Invoke subcommand for additional help
```

***

#### llvm <a href="#llvm" id="llvm"></a>

The Low-Level Virtual Machine (LLVM) is a collection of libraries and tools that make it easy to build compilers, optimizers, Just-In-Time code generators, and many other compiler-related programs.

This is a dependency package providing the default llvm package.

**Installed size:** `109 KB`\
**How to install:** `sudo apt install llvm`

<details>

<summary>Dependencies:</summary>

* llvm-14
* llvm-runtime

</details>

**bugpoint**

Automatic test case reduction tool

```
:~# bugpoint -h
OVERVIEW: LLVM automatic testcase reducer. See
http://llvm.org/cmds/bugpoint.html for more information.

USAGE: bugpoint [options] --args <program arguments>... --tool-args <tool arguments>... --safe-tool-args <safe-tool arguments>... --gcc-tool-args <gcc-tool arguments>... --opt-args <opt arguments>... <input llvm ll/bc files>

OPTIONS:

Color Options:

  --color                                            - Use colors in output (default=autodetect)

General options:

  --O1                                               - Optimization level 1. Identical to 'opt -O1'
  --O2                                               - Optimization level 2. Identical to 'opt -O2'
  --O3                                               - Optimization level 3. Identical to 'opt -O3'
  --Os                                               - Like -O2 with extra optimizations for size. Similar to clang -Os
  --Oz                                               - Like -Os but reduces code size further. Similar to clang -Oz
  --Xlinker=<string>                                 - Additional arguments to pass to the linker
  --aarch64-neon-syntax=<value>                      - Choose style of NEON code to emit from AArch64 backend:
    =generic                                         -   Emit generic NEON assembly
    =apple                                           -   Emit Apple-style NEON assembly
  --aarch64-use-aa                                   - Enable the use of AA during codegen.
  --abort-on-max-devirt-iterations-reached           - Abort when the max iterations for devirtualization CGSCC repeat pass is reached
  --abs-tolerance=<number>                           - Absolute error tolerated
  --additional-so=<string>                           - Additional shared objects to load into executing programs
  --allow-ginsert-as-artifact                        - Allow G_INSERT to be considered an artifact. Hack around AMDGPU test infinite loops.
  --amdgpu-bypass-slow-div                           - Skip 64-bit divide for dynamic 32-bit values
  --amdgpu-disable-loop-alignment                    - Do not align and prefetch loops
  --amdgpu-disable-power-sched                       - Disable scheduling to minimize mAI power bursts
  --amdgpu-dpp-combine                               - Enable DPP combiner
  --amdgpu-dump-hsa-metadata                         - Dump AMDGPU HSA Metadata
  --amdgpu-enable-flat-scratch                       - Use flat scratch instructions
  --amdgpu-enable-merge-m0                           - Merge and hoist M0 initializations
  --amdgpu-promote-alloca-to-vector-limit=<uint>     - Maximum byte size to consider promote alloca to vector
  --amdgpu-sdwa-peephole                             - Enable SDWA peepholer
  --amdgpu-use-aa-in-codegen                         - Enable the use of AA during codegen.
  --amdgpu-verify-hsa-metadata                       - Verify AMDGPU HSA Metadata
  --amdgpu-vgpr-index-mode                           - Use GPR indexing mode instead of movrel for vector indexing
  --append-exit-code                                 - Append the exit code to the output so it gets diff'd too
  --args <string>...                                 - <program arguments>...
  --arm-add-build-attributes                         - 
  --arm-implicit-it=<value>                          - Allow conditional instructions outdside of an IT block
    =always                                          -   Accept in both ISAs, emit implicit ITs in Thumb
    =never                                           -   Warn in ARM, reject in Thumb
    =arm                                             -   Accept in ARM, reject in Thumb
    =thumb                                           -   Warn in ARM, emit implicit ITs in Thumb
  --asm-show-inst                                    - Emit internal instruction representation to assembly file
  --atomic-counter-update-promoted                   - Do counter update using atomic fetch add  for promoted counters only
  --atomic-first-counter                             - Use atomic fetch add for first counter in a function (usually the entry counter)
  --bounds-checking-single-trap                      - Use one trap block per function
  --cfg-hide-cold-paths=<number>                     - Hide blocks with relative frequency below the given value
  --cfg-hide-deoptimize-paths                        - 
  --cfg-hide-unreachable-paths                       - 
  --compile-command=<string>                         - Command to compile the bitcode (use with -compile-custom) (default: llc)
  --cost-kind=<value>                                - Target cost kind
    =throughput                                      -   Reciprocal throughput
    =latency                                         -   Instruction latency
    =code-size                                       -   Code size
    =size-latency                                    -   Code size and latency
  --debug-info-correlate                             - Use debug info to correlate profiles.
  --debugify-level=<value>                           - Kind of debug info to add
    =locations                                       -   Locations only
    =location+variables                              -   Locations and Variables
  --debugify-quiet                                   - Suppress verbose debugify output
  --disable-attribute-remove                         - Do not remove function attributes
  --disable-block-extraction                         - Don't extract blocks when searching for miscompilations
  --disable-dce                                      - Do not use the -dce pass to reduce testcases
  --disable-global-remove                            - Do not remove global variables
  --disable-i2p-p2i-opt                              - Disables inttoptr/ptrtoint roundtrip optimization
  --disable-loop-extraction                          - Don't extract loops when searching for miscompilations
  --disable-namedmd-remove                           - Do not remove global named metadata
  --disable-pass-list-reduction                      - Skip pass list reduction steps
  --disable-promote-alloca-to-lds                    - Disable promote alloca to LDS
  --disable-promote-alloca-to-vector                 - Disable promote alloca to vector
  --disable-simplifycfg                              - Do not use the -simplifycfg pass to reduce testcases
  --disable-strip-debug-types                        - Do not strip debug type info metadata
  --disable-strip-debuginfo                          - Do not strip debug info metadata
  --do-counter-promotion                             - Do counter register promotion
  --dot-cfg-mssa=<file name for generated dot file>  - file name for generated dot file
  --dwarf-version=<int>                              - Dwarf version
  --dwarf64                                          - Generate debugging info in the 64-bit DWARF format
  --emscripten-cxx-exceptions-allowed=<string>       - The list of function names in which Emscripten-style exception handling is enabled (see emscripten EMSCRIPTEN_CATCHING_ALLOWED options)
  --enable-cse-in-irtranslator                       - Should enable CSE in irtranslator
  --enable-cse-in-legalizer                          - Should enable CSE in Legalizer
  --enable-emscripten-cxx-exceptions                 - WebAssembly Emscripten-style exception handling
  --enable-emscripten-sjlj                           - WebAssembly Emscripten-style setjmp/longjmp handling
  --enable-gvn-hoist                                 - Enable the GVN hoisting pass (default = off)
  --enable-gvn-memdep                                - 
  --enable-gvn-sink                                  - Enable the GVN sinking pass (default = off)
  --enable-load-in-loop-pre                          - 
  --enable-load-pre                                  - 
  --enable-loop-simplifycfg-term-folding             - 
  --enable-name-compression                          - Enable name/filename string compression
  --enable-split-backedge-in-load-pre                - 
  --enable-valgrind                                  - Run optimizations through valgrind
  --exec-command=<string>                            - Command to execute the bitcode (use with -run-custom) (default: simulate)
  --experimental-debug-variable-locations            - Use experimental new value-tracking variable locations
  --fatal-warnings                                   - Treat warnings as errors
  --find-bugs                                        - Run many different optimization sequences on program to find bugs
  --fs-profile-debug-bw-threshold=<uint>             - Only show debug message if the source branch weight is greater  than this value.
  --fs-profile-debug-prob-diff-threshold=<uint>      - Only show debug message if the branch probility is greater than this value (in percentage).
  --gcc=<string>                                     - The gcc binary to use.
  --gcc-tool-args <string>...                        - <gcc-tool arguments>...
  --generate-merged-base-profiles                    - When generating nested context-sensitive profiles, always generate extra base profile for function with all its context profiles merged into it.
  --gpsize=<uint>                                    - Global Pointer Addressing Size.  The default size is 8.
  --hash-based-counter-split                         - Rename counter variable of a comdat function based on cfg hash
  --hot-cold-split                                   - Enable hot-cold splitting pass
  --import-all-index                                 - Import all external functions in index.
  --incremental-linker-compatible                    - When used with filetype=obj, emit an object file which can be used with an incremental linker
  --input=<string>                                   - Filename to pipe in as stdin (default: /dev/null)
  --instcombine-code-sinking                         - Enable code sinking
  --instcombine-guard-widening-window=<uint>         - How wide an instruction window to bypass looking for another guard
  --instcombine-max-iterations=<uint>                - Limit the maximum number of instruction combining iterations
  --instcombine-max-num-phis=<uint>                  - Maximum number phis to handle in intptr/ptrint folding
  --instcombine-maxarray-size=<uint>                 - Maximum array size considered when doing a combine
  --instcombine-negator-enabled                      - Should we attempt to sink negations?
  --instcombine-negator-max-depth=<uint>             - What is the maximal lookup depth when trying to check for viability of negation sinking.
  --instrprof-atomic-counter-update-all              - Make all profile counter updates atomic (for testing only)
  --internalize-public-api-file=<filename>           - A file containing list of symbol names to preserve
  --internalize-public-api-list=<list>               - A list of symbol names to preserve
  Passes available:
      --aa                                              - Function Alias Analysis Results
      --aa-eval                                         - Exhaustive Alias Analysis Precision Evaluator
      --adce                                            - Aggressive Dead Code Elimination
      --add-discriminators                              - Add DWARF path discriminators
      --aggressive-instcombine                          - Combine pattern based expressions
      --alignment-from-assumptions                      - Alignment from assumptions
      --always-inline                                   - Inliner for always_inline functions
      --annotation-remarks                              - Annotation Remarks
      --annotation2metadata                             - Annotation2Metadata
      --argpromotion                                    - Promote 'by reference' arguments to scalars
      --asan                                            - AddressSanitizer: detects use-after-free and out-of-bounds bugs.
      --asan-globals-md                                 - Read metadata to mark which globals should be instrumented when running ASan.
      --asan-module                                     - AddressSanitizer: detects use-after-free and out-of-bounds bugs.ModulePass
      --assume-builder                                  - Assume Builder
      --assume-simplify                                 - Assume Simplify
      --assumption-cache-tracker                        - Assumption Cache Tracker
      --attributor                                      - Deduce and propagate attributes
      --attributor-cgscc                                - Deduce and propagate attributes (CGSCC pass)
      --barrier                                         - A No-Op Barrier Pass
      --basic-aa                                        - Basic Alias Analysis (stateless AA impl)
      --basiccg                                         - CallGraph Construction
      --bdce                                            - Bit-Tracking Dead Code Elimination
      --block-freq                                      - Block Frequency Analysis
      --bounds-checking                                 - Run-time bounds checking
      --branch-prob                                     - Branch Probability Analysis
      --break-crit-edges                                - Break critical edges in CFG
      --called-value-propagation                        - Called Value Propagation
      --callsite-splitting                              - Call-site splitting
      --canon-freeze                                    - Canonicalize Freeze Instructions in Loops
      --canonicalize-aliases                            - Canonicalize aliases
      --cfl-anders-aa                                   - Inclusion-Based CFL Alias Analysis
      --cfl-steens-aa                                   - Unification-Based CFL Alias Analysis
      --cg-profile                                      - Call Graph Profile
      --check-debugify                                  - Check debug info from -debugify
      --check-debugify-function                         - Check debug info from -debugify-function
      --chr                                             - Reduce control height in the hot paths
      --consthoist                                      - Constant Hoisting
      --constmerge                                      - Merge Duplicate Global Constants
      --constraint-elimination                          - Constraint Elimination
      --correlated-propagation                          - Value Propagation
      --cost-model                                      - Cost Model Analysis
      --cross-dso-cfi                                   - Cross-DSO CFI
      --cycles                                          - Cycle Info Analysis
      --da                                              - Dependence Analysis
      --dce                                             - Dead Code Elimination
      --deadargelim                                     - Dead Argument Elimination
      --deadarghaX0r                                    - Dead Argument Hacking (BUGPOINT USE ONLY; DO NOT USE)
      --debugify                                        - Attach debug info to everything
      --debugify-function                               - Attach debug info to a function
      --delinearize                                     - Delinearization
      --demanded-bits                                   - Demanded bits analysis
      --dfa-jump-threading                              - DFA Jump Threading
      --dfsan                                           - DataFlowSanitizer: dynamic data flow analysis.
      --div-rem-pairs                                   - Hoist/decompose integer division and remainder
      --divergence                                      - Legacy Divergence Analysis
      --domfrontier                                     - Dominance Frontier Construction
      --domtree                                         - Dominator Tree Construction
      --dot-callgraph                                   - Print call graph to 'dot' file
      --dot-cfg                                         - Print CFG of function to 'dot' file
      --dot-cfg-only                                    - Print CFG of function to 'dot' file (with no function bodies)
      --dot-dom                                         - Print dominance tree of function to 'dot' file
      --dot-dom-only                                    - Print dominance tree of function to 'dot' file (with no function bodies)
      --dot-postdom                                     - Print postdominance tree of function to 'dot' file
      --dot-postdom-only                                - Print postdominance tree of function to 'dot' file (with no function bodies)
      --dot-regions                                     - Print regions of function to 'dot' file
      --dot-regions-only                                - Print regions of function to 'dot' file (with no function bodies)
      --dot-scops                                       - Polly - Print Scops of function
      --dot-scops-only                                  - Polly - Print Scops of function (with no function bodies)
      --dse                                             - Dead Store Elimination
      --early-cse                                       - Early CSE
      --early-cse-memssa                                - Early CSE w/ MemorySSA
      --ee-instrument                                   - Instrument function entry/exit with calls to e.g. mcount() (pre inlining)
      --elim-avail-extern                               - Eliminate Available Externally Globals
      --external-aa                                     - External Alias Analysis
      --extract-blocks                                  - Extract basic blocks from module
      --fix-irreducible                                 - Convert irreducible control-flow into natural loops
      --flattencfg                                      - Flatten the CFG
      --float2int                                       - Float to int
      --forceattrs                                      - Force set function attributes
      --function-attrs                                  - Deduce function attributes
      --function-import                                 - Summary Based Function Import
      --function-specialization                         - Propagate constant arguments by specializing the function
      --globaldce                                       - Dead Global Elimination
      --globalopt                                       - Global Variable Optimizer
      --globals-aa                                      - Globals Alias Analysis
      --globalsplit                                     - Global splitter
      --guard-widening                                  - Widen guards
      --gvn                                             - Global Value Numbering
      --gvn-hoist                                       - Early GVN Hoisting of Expressions
      --gvn-sink                                        - Early GVN sinking of Expressions
      --hotcoldsplit                                    - Hot Cold Splitting
      --hwasan                                          - HWAddressSanitizer: detect memory bugs using tagged addressing.
      --indvars                                         - Induction Variable Simplification
      --infer-address-spaces                            - Infer address spaces
      --inferattrs                                      - Infer set function attributes
      --inject-tli-mappings                             - Inject TLI Mappings
      --inline                                          - Function Integration/Inlining
      --insert-gcov-profiling                           - Insert instrumentation for GCOV profiling
      --instcombine                                     - Combine redundant instructions
      --instcount                                       - Counts the various types of Instructions
      --instnamer                                       - Assign names to anonymous instructions
      --instrorderfile                                  - Instrumentation for Order File
      --instrprof                                       - Frontend instrumentation-based coverage lowering.
      --instsimplify                                    - Remove redundant instructions
      --internalize                                     - Internalize Global Symbols
      --intervals                                       - Interval Partition Construction
      --ipsccp                                          - Interprocedural Sparse Conditional Constant Propagation
      --ir-similarity-identifier                        - ir-similarity-identifier
      --irce                                            - Inductive range check elimination
      --iroutliner                                      - IR Outliner
      --iv-users                                        - Induction Variable Users
      --jump-threading                                  - Jump Threading
      --lazy-block-freq                                 - Lazy Block Frequency Analysis
      --lazy-branch-prob                                - Lazy Branch Probability Analysis
      --lazy-value-info                                 - Lazy Value Information Analysis
      --lcssa                                           - Loop-Closed SSA Form Pass
      --lcssa-verification                              - LCSSA Verifier
      --libcalls-shrinkwrap                             - Conditionally eliminate dead library calls
      --licm                                            - Loop Invariant Code Motion
      --lint                                            - Statically lint-checks LLVM IR
      --load-store-vectorizer                           - Vectorize load and store instructions
      --loop-accesses                                   - Loop Access Analysis
      --loop-data-prefetch                              - Loop Data Prefetch
      --loop-deletion                                   - Delete dead loops
      --loop-distribute                                 - Loop Distribution
      --loop-extract                                    - Extract loops into new functions
      --loop-extract-single                             - Extract at most one loop into a new function
      --loop-flatten                                    - Flattens loops
      --loop-fusion                                     - Loop Fusion
      --loop-guard-widening                             - Widen guards (within a single loop, as a loop pass)
      --loop-idiom                                      - Recognize loop idioms
      --loop-instsimplify                               - Simplify instructions in loops
      --loop-interchange                                - Interchanges loops for cache reuse
      --loop-load-elim                                  - Loop Load Elimination
      --loop-predication                                - Loop predication
      --loop-reduce                                     - Loop Strength Reduction
      --loop-reroll                                     - Reroll loops
      --loop-rotate                                     - Rotate Loops
      --loop-simplify                                   - Canonicalize natural loops
      --loop-simplifycfg                                - Simplify loop CFG
      --loop-sink                                       - Loop Sink
      --loop-unroll                                     - Unroll loops
      --loop-unroll-and-jam                             - Unroll and Jam loops
      --loop-unswitch                                   - Unswitch loops
      --loop-vectorize                                  - Loop Vectorization
      --loop-versioning                                 - Loop Versioning
      --loop-versioning-licm                            - Loop Versioning For LICM
      --loops                                           - Natural Loop Information
      --lower-constant-intrinsics                       - Lower constant intrinsics
      --lower-expect                                    - Lower 'expect' Intrinsics
      --lower-guard-intrinsic                           - Lower the guard intrinsic to normal control flow
      --lower-matrix-intrinsics                         - Lower the matrix intrinsics
      --lower-matrix-intrinsics-minimal                 - Lower the matrix intrinsics (minimal)
      --lower-widenable-condition                       - Lower the widenable condition to default true value
      --loweratomic                                     - Lower atomic intrinsics to non-atomic form
      --lowerinvoke                                     - Lower invoke and unwind, for unwindless code generators
      --lowerswitch                                     - Lower SwitchInst's to branches
      --lowertypetests                                  - Lower type metadata
      --make-guards-explicit                            - Lower the guard intrinsic to explicit control flow form
      --mem2reg                                         - Promote Memory to Register
      --memcpyopt                                       - MemCpy Optimization
      --memdep                                          - Memory Dependence Analysis
      --memoryssa                                       - Memory SSA
      --memprof                                         - MemProfiler: profile memory allocations and accesses.
      --memprof-module                                  - MemProfiler: profile memory allocations and accesses.ModulePass
      --mergefunc                                       - Merge Functions
      --mergeicmps                                      - Merge contiguous icmps into a memcmp
      --mergereturn                                     - Unify function exit nodes
      --metarenamer                                     - Assign new names to everything
      --mldst-motion                                    - MergedLoadStoreMotion
      --module-debuginfo                                - Decodes module-level debug info
      --module-summary-analysis                         - Module Summary Analysis
      --module-summary-info                             - Module summary info
      --msan                                            - MemorySanitizer: detects uninitialized reads.
      --name-anon-globals                               - Provide a name to nameless globals
      --nary-reassociate                                - Nary reassociation
      --newgvn                                          - Global Value Numbering
      --objc-arc                                        - ObjC ARC optimization
      --objc-arc-aa                                     - ObjC-ARC-Based Alias Analysis
      --objc-arc-apelim                                 - ObjC ARC autorelease pool elimination
      --objc-arc-contract                               - ObjC ARC contraction
      --objc-arc-expand                                 - ObjC ARC expansion
      --openmp-opt-cgscc                                - OpenMP specific optimizations
      --opt-remark-emitter                              - Optimization Remark Emitter
      --pa-eval                                         - Evaluate ProvenanceAnalysis on all pairs
      --partial-inliner                                 - Partial Inliner
      --partially-inline-libcalls                       - Partially inline calls to library functions
      --pgo-icall-prom                                  - Use PGO instrumentation profile to promote indirect calls to direct calls.
      --pgo-instr-gen                                   - PGO instrumentation.
      --pgo-instr-use                                   - Read PGO instrumentation profile.
      --pgo-memop-opt                                   - Optimize memory intrinsic using its size value profile
      --phi-values                                      - Phi Values Analysis
      --place-backedge-safepoints-impl                  - Place Backedge Safepoints
      --place-safepoints                                - Place Safepoints
      --polly-ast                                       - Polly - Generate an AST from the SCoP (isl)
      --polly-canonicalize                              - Polly - Run canonicalization passes
      --polly-cleanup                                   - Polly - Cleanup after code generation
      --polly-codegen                                   - Polly - Create LLVM-IR from SCoPs
      --polly-dce                                       - Polly - Remove dead iterations
      --polly-delicm                                    - Polly - DeLICM/DePRE
      --polly-dependences                               - Polly - Calculate dependences
      --polly-detect                                    - Polly - Detect static control parts (SCoPs)
      --polly-dump-module                               - Polly - Dump Module
      --polly-export-jscop                              - Polly - Export Scops as JSON (Writes a .jscop file for each Scop)
      --polly-flatten-schedule                          - Polly - Flatten schedule
      --polly-function-dependences                      - Polly - Calculate dependences for all the SCoPs of a function
      --polly-function-scops                            - Polly - Create polyhedral description of all Scops of a function
      --polly-import-jscop                              - Polly - Import Scops from JSON (Reads a .jscop file for each Scop)
      --polly-mse                                       - Polly - Maximal static expansion of SCoP
      --polly-opt-isl                                   - Polly - Optimize schedule of SCoP
      --polly-optree                                    - Polly - Forward operand tree
      --polly-prepare                                   - Polly - Prepare code for polly
      --polly-prune-unprofitable                        - Polly - Prune unprofitable SCoPs
      --polly-scop-inliner                              - inline functions based on how much of the function is a scop.
      --polly-scops                                     - Polly - Create polyhedral description of Scops
      --polly-simplify                                  - Polly - Simplify
      --polyhedral-info                                 - Polly - Interface to polyhedral analysis engine
      --post-inline-ee-instrument                       - Instrument function entry/exit with calls to e.g. mcount() (post inlining)
      --postdomtree                                     - Post-Dominator Tree Construction
      --print-alias-sets                                - Alias Set Printer
      --print-callgraph                                 - Print a call graph
      --print-function                                  - Print function to stderr
      --print-lazy-value-info                           - Lazy Value Info Printer Pass
      --print-memdeps                                   - Print MemDeps of function
      --print-memderefs                                 - Memory Dereferenciblity of pointers in function
      --print-memoryssa                                 - Memory SSA Printer
      --print-module                                    - Print module to stderr
      --print-must-be-executed-contexts                 - print the must-be-executed-context for all instructions
      --print-mustexecute                               - Instructions which execute on loop entry
      --print-predicateinfo                             - PredicateInfo Printer
      --profile-summary-info                            - Profile summary info
      --prune-eh                                        - Remove unused exception handling info
      --reassociate                                     - Reassociate expressions
      --redundant-dbg-inst-elim                         - Redundant Dbg Instruction Elimination
      --reg2mem                                         - Demote all values to stack slots
      --regions                                         - Detect single entry single exit regions
      --rewrite-statepoints-for-gc                      - Make relocations explicit at statepoints
      --rpo-function-attrs                              - Deduce function attributes in RPO
      --sample-profile                                  - Sample Profile loader
      --sancov                                          - Pass for instrumenting coverage on functions
      --scalar-evolution                                - Scalar Evolution Analysis
      --scalarize-masked-mem-intrin                     - Scalarize unsupported masked memory intrinsics
      --scalarizer                                      - Scalarize vector operations
      --sccp                                            - Sparse Conditional Constant Propagation
      --scev-aa                                         - ScalarEvolution-based Alias Analysis
      --scoped-noalias-aa                               - Scoped NoAlias Alias Analysis
      --separate-const-offset-from-gep                  - Split GEPs to a variadic base and a constant offset for better CSE
      --simple-loop-unswitch                            - Simple unswitch loops
      --simplifycfg                                     - Simplify the CFG
      --sink                                            - Code sinking
      --slp-vectorizer                                  - SLP Vectorizer
      --slsr                                            - Straight line strength reduction
      --speculative-execution                           - Speculatively execute instructions
      --sroa                                            - Scalar Replacement Of Aggregates
      --stack-safety                                    - Stack Safety Analysis
      --stack-safety-local                              - Stack Safety Local Analysis
      --strip                                           - Strip all symbols from a module
      --strip-dead-debug-info                           - Strip debug info for unused symbols
      --strip-dead-prototypes                           - Strip Unused Function Prototypes
      --strip-debug-declare                             - Strip all llvm.dbg.declare intrinsics
      --strip-gc-relocates                              - Strip gc.relocates inserted through RewriteStatepointsForGC
      --strip-nondebug                                  - Strip all symbols, except dbg symbols, from a module
      --strip-nonlinetable-debuginfo                    - Strip all debug info except linetables
      --structurizecfg                                  - Structurize the CFG
      --tailcallelim                                    - Tail Call Elimination
      --targetlibinfo                                   - Target Library Information
      --tbaa                                            - Type-Based Alias Analysis
      --transform-warning                               - Warn about non-applied transformations
      --tsan                                            - ThreadSanitizer: detects data races.
      --tti                                             - Target Transform Information
      --unify-loop-exits                                - Fixup each natural loop to have a single exit block
      --vector-combine                                  - Optimize scalar/vector ops
      --verify                                          - Module Verifier
      --verify-safepoint-ir                             - Safepoint IR Verifier
      --view-callgraph                                  - View call graph
      --view-cfg                                        - View CFG of function
      --view-cfg-only                                   - View CFG of function (with no function bodies)
      --view-dom                                        - View dominance tree of function
      --view-dom-only                                   - View dominance tree of function (with no function bodies)
      --view-postdom                                    - View postdominance tree of function
      --view-postdom-only                               - View postdominance tree of function (with no function bodies)
      --view-regions                                    - View regions of function
      --view-regions-only                               - View regions of function (with no function bodies)
      --view-scops                                      - Polly - View Scops of function
      --view-scops-only                                 - Polly - View Scops of function (with no function bodies)
      --wholeprogramdevirt                              - Whole program devirtualization
  --iterative-counter-promotion                      - Allow counter promotion across the whole loop nest.
  --keep-main                                        - Force function reduction to keep main
  --load=<pluginfilename>                            - Load the specified plugin
  --lto-embed-bitcode=<value>                        - Embed LLVM bitcode in object files produced by LTO
    =none                                            -   Do not embed
    =optimized                                       -   Embed after all optimization passes
    =post-merge-pre-opt                              -   Embed post merge, but before optimizations
  --lto-pass-remarks-filter=<regex>                  - Only record optimization remarks from passes whose names match the given regular expression
  --lto-pass-remarks-format=<format>                 - The format used for serializing remarks (default: YAML)
  --lto-pass-remarks-output=<filename>               - Output filename for pass remarks
  --matrix-default-layout=<value>                    - Sets the default matrix layout
    =column-major                                    -   Use column-major layout
    =row-major                                       -   Use row-major layout
  --max-counter-promotions=<int>                     - Max number of allowed counter promotions
  --max-counter-promotions-per-loop=<uint>           - Max number counter promotions per loop to avoid increasing register pressure too much
  --mc-relax-all                                     - When used with filetype=obj, relax all fixups in the emitted object file
  --mcabac                                           - tbd
  --merror-missing-parenthesis                       - Error for missing parenthesis around predicate registers
  --merror-noncontigious-register                    - Error for register names that aren't contigious
  --mhvx                                             - Enable Hexagon Vector eXtensions
  --mhvx=<value>                                     - Enable Hexagon Vector eXtensions
    =v60                                             -   Build for HVX v60
    =v62                                             -   Build for HVX v62
    =v65                                             -   Build for HVX v65
    =v66                                             -   Build for HVX v66
    =v67                                             -   Build for HVX v67
    =v68                                             -   Build for HVX v68
    =v69                                             -   Build for HVX v69
  --mips-compact-branches=<value>                    - MIPS Specific: Compact branch policy.
    =never                                           -   Do not use compact branches if possible.
    =optimal                                         -   Use compact branches where appropriate (default).
    =always                                          -   Always use compact branches if possible.
  --mips16-constant-islands                          - Enable mips16 constant islands.
  --mips16-hard-float                                - Enable mips16 hard float.
  --mir-strip-debugify-only                          - Should mir-strip-debug only strip debug info from debugified modules by default
  --mlimit=<MBytes>                                  - Maximum amount of memory to use. 0 disables check. Defaults to 400MB (800MB under valgrind, 0 with sanitizers).
  --mno-compound                                     - Disable looking for compound instructions for Hexagon
  --mno-fixup                                        - Disable fixing up resolved relocations for Hexagon
  --mno-ldc1-sdc1                                    - Expand double precision loads and stores to their single precision counterparts
  --mno-pairing                                      - Disable looking for duplex instructions for Hexagon
  --mtriple=<string>                                 - Override target triple for module
  --mwarn-missing-parenthesis                        - Warn for missing parenthesis around predicate registers
  --mwarn-noncontigious-register                     - Warn for register names that arent contigious
  --mwarn-sign-mismatch                              - Warn for mismatching a signed and unsigned value
  --no-deprecated-warn                               - Suppress all deprecated warnings
  --no-discriminators                                - Disable generation of discriminator information.
  --no-type-check                                    - Suppress type errors (Wasm)
  --no-warn                                          - Suppress all warnings
  --nvptx-sched4reg                                  - NVPTX Specific: schedule for register pressue
  --opaque-pointers                                  - Use opaque pointers
  --opt-args <string>...                             - <opt arguments>...
  --opt-command=<string>                             - Path to opt. (default: search path for 'opt'.)
  --output=<string>                                  - Specify a reference program output (for miscompilation detection)
  --output-prefix=<string>                           - Prefix to use for outputs (default: 'bugpoint')
  --poison-checking-function-local                   - Check that returns are non-poison (for testing)
  --print-pipeline-passes                            - Print a '-passes' compatible string describing the pipeline (best-effort only).
  --r600-ir-structurize                              - Use StructurizeCFG IR pass
  --rdf-dump                                         - 
  --rdf-limit=<uint>                                 - 
  --rel-tolerance=<number>                           - Relative error tolerated
  --remote-client=<string>                           - Remote execution client (rsh/ssh)
  --remote-extra-options=<string>                    - Remote execution (rsh/ssh) extra options
  --remote-host=<string>                             - Remote execution (rsh/ssh) host
  --remote-port=<string>                             - Remote execution (rsh/ssh) port
  --remote-user=<string>                             - Remote execution (rsh/ssh) user id
  --replace-funcs-with-null                          - When stubbing functions, replace all uses will null
  Specify the "test" i.e. suspect back-end:
      --auto                                            - Use best guess
      --run-int                                         - Execute with the interpreter
      --run-jit                                         - Execute with JIT
      --run-llc                                         - Compile with LLC
      --run-llc-ia                                      - Compile with LLC with integrated assembler
      --compile-custom                                  - Use -compile-command to define a command to compile the bitcode. Useful to avoid linking.
      --run-custom                                      - Use -exec-command to define a command to execute the bitcode. Useful for cross-compilation.
  --runtime-counter-relocation                       - Enable relocating counters at runtime.
  --safe-path=<string>                               - Specify the path to the "safe" backend program
  Specify "safe" i.e. known-good backend:
      --safe-auto                                       - Use best guess
      --safe-run-llc                                    - Compile with LLC
      --safe-run-custom                                 - Use -exec-command to define a command to execute the bitcode. Useful for cross-compilation.
  --safe-tool-args <string>...                       - <safe-tool arguments>...
  --safepoint-ir-verifier-print-only                 - 
  --sample-profile-check-record-coverage=<N>         - Emit a warning if less than N% of records in the input profile are matched to the IR.
  --sample-profile-check-sample-coverage=<N>         - Emit a warning if less than N% of samples in the input profile are matched to the IR.
  --sample-profile-max-propagate-iterations=<uint>   - Maximum number of iterations to go through when propagating sample block/edge weights through the CFG.
  --save-temps                                       - Save temporary files
  --silence-passes                                   - Suppress output of running passes (both stdout and stderr)
  --skip-ret-exit-block                              - Suppress counter promotion if exit blocks contain ret.
  --speculative-counter-promotion-max-exiting=<uint> - The max number of exiting blocks of a loop to allow  speculative counter promotion
  --speculative-counter-promotion-to-loop            - When the option is false, if the target block is in a loop, the promotion will be disallowed unless the promoted counter  update can be further/iteratively promoted into an acyclic  region.
  --std-link-opts                                    - Include the standard link time optimizations
  --summary-file=<string>                            - The summary file to use for function importing.
  --tail-predication=<value>                         - MVE tail-predication pass options
    =disabled                                        -   Don't tail-predicate loops
    =enabled-no-reductions                           -   Enable tail-predication, but not for reduction loops
    =enabled                                         -   Enable tail-predication, including reduction loops
    =force-enabled-no-reductions                     -   Enable tail-predication, but not for reduction loops, and force this which might be unsafe
    =force-enabled                                   -   Enable tail-predication, including reduction loops, and force this which might be unsafe
  --thinlto-assume-merged                            - Assume the input has already undergone ThinLTO function importing and the other pre-optimization pipeline changes.
  --threads=<int>                                    - 
  --timeout=<seconds>                                - Number of seconds program is allowed to run before it is killed (default is 300s), 0 disables timeout
  --tool-args <string>...                            - <tool arguments>...
  --verbose-errors                                   - Print the output of crashing program
  --verify-region-info                               - Verify region info (time consuming)
  --vp-counters-per-site=<number>                    - The average number of profile counters allocated per value profiling site.
  --vp-static-alloc                                  - Do static counter allocation for value profiler
  --wasm-enable-eh                                   - WebAssembly exception handling
  --wasm-enable-sjlj                                 - WebAssembly setjmp/longjmp handling
  --x86-align-branch=<string>                        - Specify types of branches to align (plus separated list of types):
                                                       jcc      indicates conditional jumps
                                                       fused    indicates fused conditional jumps
                                                       jmp      indicates direct unconditional jumps
                                                       call     indicates direct and indirect calls
                                                       ret      indicates rets
                                                       indirect indicates indirect unconditional jumps
  --x86-align-branch-boundary=<uint>                 - Control how the assembler should align branches with NOP. If the boundary's size is not 0, it should be a power of 2 and no less than 32. Branches will be aligned to prevent from being across or against the boundary of specified size. The default value 0 does not align branches.
  --x86-branches-within-32B-boundaries               - Align selected instructions to mitigate negative performance impact of Intel's micro code update for errata skx102.  May break assumptions about labels corresponding to particular instructions, and should be used with caution.
  --x86-pad-max-prefix-size=<uint>                   - Maximum number of prefixes to use for padding

Generic Options:

  --help                                             - Display available options (--help-hidden for more)
  --help-list                                        - Display list of available options (--help-list-hidden for more)
  --version                                          - Display the version of this program

Polly Options:
Configure the polly loop optimizer

  --polly                                            - Enable the polly optimizer (with -O1, -O2 or -O3)
  --polly-2nd-level-tiling                           - Enable a 2nd level loop of loop tiling
  --polly-ast-print-accesses                         - Print memory access functions
  --polly-context=<isl parameter set>                - Provide additional constraints on the context parameters
  --polly-dce-precise-steps=<int>                    - The number of precise steps between two approximating iterations. (A value of -1 schedules another approximation stage before the actual dead code elimination.
  --polly-delicm-max-ops=<int>                       - Maximum number of isl operations to invest for lifetime analysis; 0=no limit
  --polly-detect-full-functions                      - Allow the detection of full functions
  --polly-dump-after                                 - Dump module after Polly transformations into a file suffixed with "-after"
  --polly-dump-after-file=<string>                   - Dump module after Polly transformations to the given file
  --polly-dump-before                                - Dump module before Polly transformations into a file suffixed with "-before"
  --polly-dump-before-file=<string>                  - Dump module before Polly transformations to the given file
  --polly-enable-simplify                            - Simplify SCoP after optimizations
  --polly-ignore-func=<string>                       - Ignore functions that match a regex. Multiple regexes can be comma separated. Scop detection will ignore all functions that match ANY of the regexes provided.
  --polly-isl-arg=<argument>                         - Option passed to ISL
  --polly-on-isl-error-abort                         - Abort if an isl error is encountered
  --polly-only-func=<string>                         - Only run on functions that match a regex. Multiple regexes can be comma separated. Scop detection will run on all functions that match ANY of the regexes provided.
  --polly-only-region=<identifier>                   - Only run on certain regions (The provided identifier must appear in the name of the region's entry block
  --polly-only-scop-detection                        - Only run scop detection, but no other optimizations
  --polly-optimized-scops                            - Polly - Dump polyhedral description of Scops optimized with the isl scheduling optimizer and the set of post-scheduling transformations is applied on the schedule tree
  --polly-parallel                                   - Generate thread parallel code (isl codegen only)
  --polly-parallel-force                             - Force generation of thread parallel code ignoring any cost model
  --polly-pattern-matching-based-opts                - Perform optimizations based on pattern matching
  --polly-postopts                                   - Apply post-rescheduling optimizations such as tiling (requires -polly-reschedule)
  --polly-pragma-based-opts                          - Apply user-directed transformation from metadata
  --polly-pragma-ignore-depcheck                     - Skip the dependency check for pragma-based transformations
  --polly-process-unprofitable                       - Process scops that are unlikely to benefit from Polly optimizations.
  --polly-register-tiling                            - Enable register tiling
  --polly-report                                     - Print information about the activities of Polly
  --polly-reschedule                                 - Optimize SCoPs using ISL
  --polly-show                                       - Highlight the code regions that will be optimized in a (CFG BBs and LLVM-IR instructions)
  --polly-show-only                                  - Highlight the code regions that will be optimized in a (CFG only BBs)
  --polly-stmt-granularity=<value>                   - Algorithm to use for splitting basic blocks into multiple statements
    =bb                                              -   One statement per basic block
    =scalar-indep                                    -   Scalar independence heuristic
    =store                                           -   Store-level granularity
  --polly-target=<value>                             - The hardware to target
    =cpu                                             -   generate CPU code
  --polly-tiling                                     - Enable loop tiling
  --polly-vectorizer=<value>                         - Select the vectorization strategy
    =none                                            -   No Vectorization
    =polly                                           -   Polly internal vectorizer
    =stripmine                                       -   Strip-mine outer loops for the loop-vectorizer to trigger
```

***

**dsymutil**

Manipulate archived DWARF debug symbol files

```
:~# dsymutil -h
OVERVIEW: manipulate archived DWARF debug symbol files.

dsymutil links the DWARF debug information found in the object files
for the executable <input file> by using debug symbols information
contained in its symbol table.


USAGE: dsymutil [options] <input files>

Dsymutil Options:
  --accelerator <accelerator type>
                          Specify the desired type of accelerator table. Valid options are 'Apple' (.apple_names, .apple_namespaces, .apple_types, .apple_objc), 'Dwarf' (.debug_names), 'Pub' (.debug_pubnames, .debug_pubtypes) and 'Default'
  --arch <arch>           Link DWARF debug information only for specified CPU architecturetypes. This option can be specified multiple times, once for eachdesired architecture. All CPU architectures will be linked bydefault.
  --dump-debug-map        Parse and dump the debug map to standard output. No DWARF link will take place.
  --flat                  Produce a flat dSYM file (not a bundle).
  -f                      Alias for --flat
  --gen-reproducer        Generate a reproducer consisting of the input object files.
  --help                  Prints this help output.
  -h                      Alias for --help
  -j <threads>            Alias for --num-threads
  --keep-function-for-static
                          Make a static variable keep the enclosing function even if it would have been omitted otherwise.
  --no-odr                Do not use ODR (One Definition Rule) for type uniquing.
  --no-output             Do the link in memory, but do not emit the result file.
  --no-swiftmodule-timestamp
                          Don't check timestamp for swiftmodule files.
  --num-threads <threads> Specifies the maximum number of simultaneous threads to use when linking multiple architectures.
  --object-prefix-map <prefix=remapped>
                          Remap object file paths (but no source paths) before processing.Use this for Clang objects where the module cache location wasremapped using -fdebug-prefix-map; to help dsymutilfind the Clang module cache.
  --oso-prepend-path <path>
                          Specify a directory to prepend to the paths of object files.
  --out <filename>        Alias for -o
  -o <filename>           Specify the output file. Defaults to <input file>.dwarf
  --papertrail            Embed warnings in the linked DWARF debug info.
  --remarks-output-format <format>
                          Specify the format to be used when serializing the linked remarks.
  --remarks-prepend-path <path>
                          Specify a directory to prepend to the paths of the external remark files.
  --statistics            Print statistics about the contribution of each object file to the linked debug info. This prints a table after linking with the object file name, the size of the debug info in the object file (in bytes) and the size contributed (in bytes) to the linked dSYM. The table is sorted by the output size listing the object files with the largest contribution first.
  --symbol-map <bcsymbolmap>
                          Updates the existing dSYMs inplace using symbol map specified.
  --symtab                Dumps the symbol table found in executable or object file(s) and exits.
  -S                      Output textual assembly instead of a binary dSYM companion file.
  -s                      Alias for --symtab
  --toolchain <toolchain> Embed toolchain information in dSYM bundle.
  --update                Updates existing dSYM files to contain the latest accelerator tables and other DWARF optimizations.
  --use-reproducer <path> Use the object files from the given reproducer path.
  -u                      Alias for --update
  --verbose               Enable verbose mode.
  --verify                Run the DWARF verifier on the linked DWARF debug info.
  --version               Prints the dsymutil version.
  -v                      Alias for --version
  -y                      Treat the input file is a YAML debug map rather than a binary.
```

***

**llc**

LLVM static compiler

```
:~# llc -h
OVERVIEW: llvm system compiler

USAGE: llc [options] <input bitcode>

OPTIONS:

Color Options:

  --color                                                               - Use colors in output (default=autodetect)

General options:

  -I=<string>                                                           - include search path
  -O=<char>                                                             - Optimization level. [-O0, -O1, -O2, or -O3] (default = '-O2')
  --aarch64-neon-syntax=<value>                                         - Choose style of NEON code to emit from AArch64 backend:
    =generic                                                            -   Emit generic NEON assembly
    =apple                                                              -   Emit Apple-style NEON assembly
  --aarch64-use-aa                                                      - Enable the use of AA during codegen.
  --abort-on-max-devirt-iterations-reached                              - Abort when the max iterations for devirtualization CGSCC repeat pass is reached
  --addrsig                                                             - Emit an address-significance table
  --align-loops=<uint>                                                  - Default alignment for loops
  --allow-ginsert-as-artifact                                           - Allow G_INSERT to be considered an artifact. Hack around AMDGPU test infinite loops.
  --amdgpu-bypass-slow-div                                              - Skip 64-bit divide for dynamic 32-bit values
  --amdgpu-disable-loop-alignment                                       - Do not align and prefetch loops
  --amdgpu-disable-power-sched                                          - Disable scheduling to minimize mAI power bursts
  --amdgpu-dpp-combine                                                  - Enable DPP combiner
  --amdgpu-dump-hsa-metadata                                            - Dump AMDGPU HSA Metadata
  --amdgpu-enable-flat-scratch                                          - Use flat scratch instructions
  --amdgpu-enable-merge-m0                                              - Merge and hoist M0 initializations
  --amdgpu-promote-alloca-to-vector-limit=<uint>                        - Maximum byte size to consider promote alloca to vector
  --amdgpu-sdwa-peephole                                                - Enable SDWA peepholer
  --amdgpu-use-aa-in-codegen                                            - Enable the use of AA during codegen.
  --amdgpu-verify-hsa-metadata                                          - Verify AMDGPU HSA Metadata
  --amdgpu-vgpr-index-mode                                              - Use GPR indexing mode instead of movrel for vector indexing
  --arm-add-build-attributes                                            - 
  --arm-implicit-it=<value>                                             - Allow conditional instructions outdside of an IT block
    =always                                                             -   Accept in both ISAs, emit implicit ITs in Thumb
    =never                                                              -   Warn in ARM, reject in Thumb
    =arm                                                                -   Accept in ARM, reject in Thumb
    =thumb                                                              -   Warn in ARM, emit implicit ITs in Thumb
  --asm-show-inst                                                       - Emit internal instruction representation to assembly file
  --asm-verbose                                                         - Add comments to directives.
  --atomic-counter-update-promoted                                      - Do counter update using atomic fetch add  for promoted counters only
  --atomic-first-counter                                                - Use atomic fetch add for first counter in a function (usually the entry counter)
  --basic-block-sections=<all | <function list (file)> | labels | none> - Emit basic blocks into separate sections
  --bounds-checking-single-trap                                         - Use one trap block per function
  --cfg-hide-cold-paths=<number>                                        - Hide blocks with relative frequency below the given value
  --cfg-hide-deoptimize-paths                                           - 
  --cfg-hide-unreachable-paths                                          - 
  --code-model=<value>                                                  - Choose code model
    =tiny                                                               -   Tiny code model
    =small                                                              -   Small code model
    =kernel                                                             -   Kernel code model
    =medium                                                             -   Medium code model
    =large                                                              -   Large code model
  --cost-kind=<value>                                                   - Target cost kind
    =throughput                                                         -   Reciprocal throughput
    =latency                                                            -   Instruction latency
    =code-size                                                          -   Code size
    =size-latency                                                       -   Code size and latency
  --data-sections                                                       - Emit data into separate sections
  --debug-entry-values                                                  - Enable debug info for the debug entry values.
  --debug-info-correlate                                                - Use debug info to correlate profiles.
  --debugger-tune=<value>                                               - Tune debug info for a particular debugger
    =gdb                                                                -   gdb
    =lldb                                                               -   lldb
    =dbx                                                                -   dbx
    =sce                                                                -   SCE targets (e.g. PS4)
  --debugify-level=<value>                                              - Kind of debug info to add
    =locations                                                          -   Locations only
    =location+variables                                                 -   Locations and Variables
  --debugify-quiet                                                      - Suppress verbose debugify output
  --denormal-fp-math=<value>                                            - Select which denormal numbers the code is permitted to require
    =ieee                                                               -   IEEE 754 denormal numbers
    =preserve-sign                                                      -   the sign of a  flushed-to-zero number is preserved in the sign of 0
    =positive-zero                                                      -   denormals are flushed to positive zero
  --denormal-fp-math-f32=<value>                                        - Select which denormal numbers the code is permitted to require for float
    =ieee                                                               -   IEEE 754 denormal numbers
    =preserve-sign                                                      -   the sign of a  flushed-to-zero number is preserved in the sign of 0
    =positive-zero                                                      -   denormals are flushed to positive zero
  --disable-i2p-p2i-opt                                                 - Disables inttoptr/ptrtoint roundtrip optimization
  --disable-promote-alloca-to-lds                                       - Disable promote alloca to LDS
  --disable-promote-alloca-to-vector                                    - Disable promote alloca to vector
  --disable-simplify-libcalls                                           - Disable simplify-libcalls
  --disable-tail-calls                                                  - Never emit tail calls
  --do-counter-promotion                                                - Do counter register promotion
  --dot-cfg-mssa=<file name for generated dot file>                     - file name for generated dot file
  --dwarf-version=<int>                                                 - Dwarf version
  --dwarf64                                                             - Generate debugging info in the 64-bit DWARF format
  --emit-call-site-info                                                 - Emit call site debug information, if debug information is enabled.
  --emscripten-cxx-exceptions-allowed=<string>                          - The list of function names in which Emscripten-style exception handling is enabled (see emscripten EMSCRIPTEN_CATCHING_ALLOWED options)
  --emulated-tls                                                        - Use emulated TLS model
  --enable-cse-in-irtranslator                                          - Should enable CSE in irtranslator
  --enable-cse-in-legalizer                                             - Should enable CSE in Legalizer
  --enable-emscripten-cxx-exceptions                                    - WebAssembly Emscripten-style exception handling
  --enable-emscripten-sjlj                                              - WebAssembly Emscripten-style setjmp/longjmp handling
  --enable-gvn-hoist                                                    - Enable the GVN hoisting pass (default = off)
  --enable-gvn-memdep                                                   - 
  --enable-gvn-sink                                                     - Enable the GVN sinking pass (default = off)
  --enable-load-in-loop-pre                                             - 
  --enable-load-pre                                                     - 
  --enable-loop-simplifycfg-term-folding                                - 
  --enable-name-compression                                             - Enable name/filename string compression
  --enable-no-infs-fp-math                                              - Enable FP math optimizations that assume no +-Infs
  --enable-no-nans-fp-math                                              - Enable FP math optimizations that assume no NaNs
  --enable-no-signed-zeros-fp-math                                      - Enable FP math optimizations that assume the sign of 0 is insignificant
  --enable-no-trapping-fp-math                                          - Enable setting the FP exceptions build attribute not to use exceptions
  --enable-split-backedge-in-load-pre                                   - 
  --enable-unsafe-fp-math                                               - Enable optimizations that may decrease FP precision
  --exception-model=<value>                                             - exception model
    =default                                                            -   default exception handling model
    =dwarf                                                              -   DWARF-like CFI based exception handling
    =sjlj                                                               -   SjLj exception handling
    =arm                                                                -   ARM EHABI exceptions
    =wineh                                                              -   Windows exception model
    =wasm                                                               -   WebAssembly exception handling
  --experimental-debug-variable-locations                               - Use experimental new value-tracking variable locations
  --fatal-warnings                                                      - Treat warnings as errors
  --filetype=<value>                                                    - Choose a file type (not all types are supported by all targets):
    =asm                                                                -   Emit an assembly ('.s') file
    =obj                                                                -   Emit a native object ('.o') file
    =null                                                               -   Emit nothing, for performance testing
  --float-abi=<value>                                                   - Choose float ABI type
    =default                                                            -   Target default float ABI type
    =soft                                                               -   Soft float ABI (implied by -soft-float)
    =hard                                                               -   Hard float ABI (uses FP registers)
  --force-dwarf-frame-section                                           - Always emit a debug frame section.
  --fp-contract=<value>                                                 - Enable aggressive formation of fused FP ops
    =fast                                                               -   Fuse FP ops whenever profitable
    =on                                                                 -   Only fuse 'blessed' FP ops.
    =off                                                                -   Only fuse FP ops when the result won't be affected.
  --frame-pointer=<value>                                               - Specify frame pointer elimination optimization
    =all                                                                -   Disable frame pointer elimination
    =non-leaf                                                           -   Disable frame pointer elimination for non-leaf frame
    =none                                                               -   Enable frame pointer elimination
  --fs-profile-debug-bw-threshold=<uint>                                - Only show debug message if the source branch weight is greater  than this value.
  --fs-profile-debug-prob-diff-threshold=<uint>                         - Only show debug message if the branch probility is greater than this value (in percentage).
  --function-sections                                                   - Emit functions into separate sections
  --generate-merged-base-profiles                                       - When generating nested context-sensitive profiles, always generate extra base profile for function with all its context profiles merged into it.
  --gpsize=<uint>                                                       - Global Pointer Addressing Size.  The default size is 8.
  --hash-based-counter-split                                            - Rename counter variable of a comdat function based on cfg hash
  --hot-cold-split                                                      - Enable hot-cold splitting pass
  --ignore-xcoff-visibility                                             - Not emit the visibility attribute for asm in AIX OS or give all symbols 'unspecified' visibility in XCOFF object file
  --import-all-index                                                    - Import all external functions in index.
  --incremental-linker-compatible                                       - When used with filetype=obj, emit an object file which can be used with an incremental linker
  --instcombine-code-sinking                                            - Enable code sinking
  --instcombine-guard-widening-window=<uint>                            - How wide an instruction window to bypass looking for another guard
  --instcombine-max-iterations=<uint>                                   - Limit the maximum number of instruction combining iterations
  --instcombine-max-num-phis=<uint>                                     - Maximum number phis to handle in intptr/ptrint folding
  --instcombine-maxarray-size=<uint>                                    - Maximum array size considered when doing a combine
  --instcombine-negator-enabled                                         - Should we attempt to sink negations?
  --instcombine-negator-max-depth=<uint>                                - What is the maximal lookup depth when trying to check for viability of negation sinking.
  --instrprof-atomic-counter-update-all                                 - Make all profile counter updates atomic (for testing only)
  --internalize-public-api-file=<filename>                              - A file containing list of symbol names to preserve
  --internalize-public-api-list=<list>                                  - A list of symbol names to preserve
  --iterative-counter-promotion                                         - Allow counter promotion across the whole loop nest.
  --load=<pluginfilename>                                               - Load the specified plugin
  --lto-embed-bitcode=<value>                                           - Embed LLVM bitcode in object files produced by LTO
    =none                                                               -   Do not embed
    =optimized                                                          -   Embed after all optimization passes
    =post-merge-pre-opt                                                 -   Embed post merge, but before optimizations
  --lto-pass-remarks-filter=<regex>                                     - Only record optimization remarks from passes whose names match the given regular expression
  --lto-pass-remarks-format=<format>                                    - The format used for serializing remarks (default: YAML)
  --lto-pass-remarks-output=<filename>                                  - Output filename for pass remarks
  --march=<string>                                                      - Architecture to generate code for (see --version)
  --matrix-default-layout=<value>                                       - Sets the default matrix layout
    =column-major                                                       -   Use column-major layout
    =row-major                                                          -   Use row-major layout
  --mattr=<a1,+a2,-a3,...>                                              - Target specific attributes (-mattr=help for details)
  --max-counter-promotions=<int>                                        - Max number of allowed counter promotions
  --max-counter-promotions-per-loop=<uint>                              - Max number counter promotions per loop to avoid increasing register pressure too much
  --mc-relax-all                                                        - When used with filetype=obj, relax all fixups in the emitted object file
  --mcabac                                                              - tbd
  --mcpu=<cpu-name>                                                     - Target a specific cpu type (-mcpu=help for details)
  --meabi=<value>                                                       - Set EABI type (default depends on triple):
    =default                                                            -   Triple default EABI version
    =4                                                                  -   EABI version 4
    =5                                                                  -   EABI version 5
    =gnu                                                                -   EABI GNU
  --merror-missing-parenthesis                                          - Error for missing parenthesis around predicate registers
  --merror-noncontigious-register                                       - Error for register names that aren't contigious
  --mhvx                                                                - Enable Hexagon Vector eXtensions
  --mhvx=<value>                                                        - Enable Hexagon Vector eXtensions
    =v60                                                                -   Build for HVX v60
    =v62                                                                -   Build for HVX v62
    =v65                                                                -   Build for HVX v65
    =v66                                                                -   Build for HVX v66
    =v67                                                                -   Build for HVX v67
    =v68                                                                -   Build for HVX v68
    =v69                                                                -   Build for HVX v69
  --mips-compact-branches=<value>                                       - MIPS Specific: Compact branch policy.
    =never                                                              -   Do not use compact branches if possible.
    =optimal                                                            -   Use compact branches where appropriate (default).
    =always                                                             -   Always use compact branches if possible.
  --mips16-constant-islands                                             - Enable mips16 constant islands.
  --mips16-hard-float                                                   - Enable mips16 hard float.
  --mir-strip-debugify-only                                             - Should mir-strip-debug only strip debug info from debugified modules by default
  --mno-compound                                                        - Disable looking for compound instructions for Hexagon
  --mno-fixup                                                           - Disable fixing up resolved relocations for Hexagon
  --mno-ldc1-sdc1                                                       - Expand double precision loads and stores to their single precision counterparts
  --mno-pairing                                                         - Disable looking for duplex instructions for Hexagon
  --mtriple=<string>                                                    - Override target triple for module
  --mwarn-missing-parenthesis                                           - Warn for missing parenthesis around predicate registers
  --mwarn-noncontigious-register                                        - Warn for register names that arent contigious
  --mwarn-sign-mismatch                                                 - Warn for mismatching a signed and unsigned value
  --no-deprecated-warn                                                  - Suppress all deprecated warnings
  --no-discriminators                                                   - Disable generation of discriminator information.
  --no-type-check                                                       - Suppress type errors (Wasm)
  --no-warn                                                             - Suppress all warnings
  --no-xray-index                                                       - Don't emit xray_fn_idx section
  --nozero-initialized-in-bss                                           - Don't place zero-initialized symbols into bss section
  --nvptx-sched4reg                                                     - NVPTX Specific: schedule for register pressue
  -o=<filename>                                                         - Output filename
  --opaque-pointers                                                     - Use opaque pointers
  --pass-remarks-filter=<regex>                                         - Only record optimization remarks from passes whose names match the given regular expression
  --pass-remarks-format=<format>                                        - The format used for serializing remarks (default: YAML)
  --pass-remarks-output=<filename>                                      - Output filename for pass remarks
  --poison-checking-function-local                                      - Check that returns are non-poison (for testing)
  --print-pipeline-passes                                               - Print a '-passes' compatible string describing the pipeline (best-effort only).
  --r600-ir-structurize                                                 - Use StructurizeCFG IR pass
  --rdf-dump                                                            - 
  --rdf-limit=<uint>                                                    - 
  --relax-elf-relocations                                               - Emit GOTPCRELX/REX_GOTPCRELX instead of GOTPCREL on x86-64 ELF
  --relocation-model=<value>                                            - Choose relocation model
    =static                                                             -   Non-relocatable code
    =pic                                                                -   Fully relocatable, position independent code
    =dynamic-no-pic                                                     -   Relocatable external references, non-relocatable code
    =ropi                                                               -   Code and read-only data relocatable, accessed PC-relative
    =rwpi                                                               -   Read-write data relocatable, accessed relative to static base
    =ropi-rwpi                                                          -   Combination of ropi and rwpi
  --run-pass=<pass-name>                                                - Run compiler only for specified passes (comma separated list)
  --runtime-counter-relocation                                          - Enable relocating counters at runtime.
  --safepoint-ir-verifier-print-only                                    - 
  --sample-profile-check-record-coverage=<N>                            - Emit a warning if less than N% of records in the input profile are matched to the IR.
  --sample-profile-check-sample-coverage=<N>                            - Emit a warning if less than N% of samples in the input profile are matched to the IR.
  --sample-profile-max-propagate-iterations=<uint>                      - Maximum number of iterations to go through when propagating sample block/edge weights through the CFG.
  --skip-ret-exit-block                                                 - Suppress counter promotion if exit blocks contain ret.
  --speculative-counter-promotion-max-exiting=<uint>                    - The max number of exiting blocks of a loop to allow  speculative counter promotion
  --speculative-counter-promotion-to-loop                               - When the option is false, if the target block is in a loop, the promotion will be disallowed unless the promoted counter  update can be further/iteratively promoted into an acyclic  region.
  --split-dwarf-file=<string>                                           - Specify the name of the .dwo file to encode in the DWARF output
  --split-dwarf-output=<filename>                                       - .dwo output filename
  --split-machine-functions                                             - Split out cold basic blocks from machine functions based on profile information
  --stack-size-section                                                  - Emit a section containing stack size metadata
  --stack-symbol-ordering                                               - Order local stack symbols.
  --stackrealign                                                        - Force align the stack to the minimum alignment
  --strict-dwarf                                                        - use strict dwarf
  --summary-file=<string>                                               - The summary file to use for function importing.
  --swift-async-fp=<value>                                              - Determine when the Swift async frame pointer should be set
    =auto                                                               -   Determine based on deployment target
    =always                                                             -   Always set the bit
    =never                                                              -   Never set the bit
  --tail-predication=<value>                                            - MVE tail-predication pass options
    =disabled                                                           -   Don't tail-predicate loops
    =enabled-no-reductions                                              -   Enable tail-predication, but not for reduction loops
    =enabled                                                            -   Enable tail-predication, including reduction loops
    =force-enabled-no-reductions                                        -   Enable tail-predication, but not for reduction loops, and force this which might be unsafe
    =force-enabled                                                      -   Enable tail-predication, including reduction loops, and force this which might be unsafe
  --tailcallopt                                                         - Turn fastcc calls into tail calls by (potentially) changing ABI.
  --thinlto-assume-merged                                               - Assume the input has already undergone ThinLTO function importing and the other pre-optimization pipeline changes.
  --thread-model=<value>                                                - Choose threading model
    =posix                                                              -   POSIX thread model
    =single                                                             -   Single thread model
  --threads=<int>                                                       - 
  --time-trace                                                          - Record time trace
  --time-trace-file=<filename>                                          - Specify time trace file destination
  --tls-size=<uint>                                                     - Bit size of immediate TLS offsets
  --unique-basic-block-section-names                                    - Give unique names to every basic block section
  --unique-section-names                                                - Give unique names to every section
  --use-ctors                                                           - Use .ctors instead of .init_array.
  --vec-extabi                                                          - Enable the AIX Extended Altivec ABI.
  --verify-region-info                                                  - Verify region info (time consuming)
  --vp-counters-per-site=<number>                                       - The average number of profile counters allocated per value profiling site.
  --vp-static-alloc                                                     - Do static counter allocation for value profiler
  --wasm-enable-eh                                                      - WebAssembly exception handling
  --wasm-enable-sjlj                                                    - WebAssembly setjmp/longjmp handling
  -x=<string>                                                           - Input language ('ir' or 'mir')
  --x86-align-branch=<string>                                           - Specify types of branches to align (plus separated list of types):
                                                                          jcc      indicates conditional jumps
                                                                          fused    indicates fused conditional jumps
                                                                          jmp      indicates direct unconditional jumps
                                                                          call     indicates direct and indirect calls
                                                                          ret      indicates rets
                                                                          indirect indicates indirect unconditional jumps
  --x86-align-branch-boundary=<uint>                                    - Control how the assembler should align branches with NOP. If the boundary's size is not 0, it should be a power of 2 and no less than 32. Branches will be aligned to prevent from being across or against the boundary of specified size. The default value 0 does not align branches.
  --x86-branches-within-32B-boundaries                                  - Align selected instructions to mitigate negative performance impact of Intel's micro code update for errata skx102.  May break assumptions about labels corresponding to particular instructions, and should be used with caution.
  --x86-pad-max-prefix-size=<uint>                                      - Maximum number of prefixes to use for padding
  --xcoff-traceback-table                                               - Emit the XCOFF traceback table

Generic Options:

  --help                                                                - Display available options (--help-hidden for more)
  --help-list                                                           - Display list of available options (--help-list-hidden for more)
  --version                                                             - Display the version of this program

Polly Options:
Configure the polly loop optimizer

  --polly                                                               - Enable the polly optimizer (with -O1, -O2 or -O3)
  --polly-2nd-level-tiling                                              - Enable a 2nd level loop of loop tiling
  --polly-ast-print-accesses                                            - Print memory access functions
  --polly-context=<isl parameter set>                                   - Provide additional constraints on the context parameters
  --polly-dce-precise-steps=<int>                                       - The number of precise steps between two approximating iterations. (A value of -1 schedules another approximation stage before the actual dead code elimination.
  --polly-delicm-max-ops=<int>                                          - Maximum number of isl operations to invest for lifetime analysis; 0=no limit
  --polly-detect-full-functions                                         - Allow the detection of full functions
  --polly-dump-after                                                    - Dump module after Polly transformations into a file suffixed with "-after"
  --polly-dump-after-file=<string>                                      - Dump module after Polly transformations to the given file
  --polly-dump-before                                                   - Dump module before Polly transformations into a file suffixed with "-before"
  --polly-dump-before-file=<string>                                     - Dump module before Polly transformations to the given file
  --polly-enable-simplify                                               - Simplify SCoP after optimizations
  --polly-ignore-func=<string>                                          - Ignore functions that match a regex. Multiple regexes can be comma separated. Scop detection will ignore all functions that match ANY of the regexes provided.
  --polly-isl-arg=<argument>                                            - Option passed to ISL
  --polly-on-isl-error-abort                                            - Abort if an isl error is encountered
  --polly-only-func=<string>                                            - Only run on functions that match a regex. Multiple regexes can be comma separated. Scop detection will run on all functions that match ANY of the regexes provided.
  --polly-only-region=<identifier>                                      - Only run on certain regions (The provided identifier must appear in the name of the region's entry block
  --polly-only-scop-detection                                           - Only run scop detection, but no other optimizations
  --polly-optimized-scops                                               - Polly - Dump polyhedral description of Scops optimized with the isl scheduling optimizer and the set of post-scheduling transformations is applied on the schedule tree
  --polly-parallel                                                      - Generate thread parallel code (isl codegen only)
  --polly-parallel-force                                                - Force generation of thread parallel code ignoring any cost model
  --polly-pattern-matching-based-opts                                   - Perform optimizations based on pattern matching
  --polly-postopts                                                      - Apply post-rescheduling optimizations such as tiling (requires -polly-reschedule)
  --polly-pragma-based-opts                                             - Apply user-directed transformation from metadata
  --polly-pragma-ignore-depcheck                                        - Skip the dependency check for pragma-based transformations
  --polly-process-unprofitable                                          - Process scops that are unlikely to benefit from Polly optimizations.
  --polly-register-tiling                                               - Enable register tiling
  --polly-report                                                        - Print information about the activities of Polly
  --polly-reschedule                                                    - Optimize SCoPs using ISL
  --polly-show                                                          - Highlight the code regions that will be optimized in a (CFG BBs and LLVM-IR instructions)
  --polly-show-only                                                     - Highlight the code regions that will be optimized in a (CFG only BBs)
  --polly-stmt-granularity=<value>                                      - Algorithm to use for splitting basic blocks into multiple statements
    =bb                                                                 -   One statement per basic block
    =scalar-indep                                                       -   Scalar independence heuristic
    =store                                                              -   Store-level granularity
  --polly-target=<value>                                                - The hardware to target
    =cpu                                                                -   generate CPU code
  --polly-tiling                                                        - Enable loop tiling
  --polly-vectorizer=<value>                                            - Select the vectorization strategy
    =none                                                               -   No Vectorization
    =polly                                                              -   Polly internal vectorizer
    =stripmine                                                          -   Strip-mine outer loops for the loop-vectorizer to trigger
```

***

**llvm-PerfectShuffle**

***

**llvm-addr2line**

A drop-in replacement for addr2line

```
:~# llvm-addr2line -h
OVERVIEW: llvm-addr2line

USAGE: llvm-addr2line [options] addresses...

OPTIONS:
  --addresses           Show address before line information
  --adjust-vma=<offset> Add specified offset to object file addresses
  -a                    Alias for --addresses
  --basenames           Strip directory names from paths
  -C                    Alias for --demangle
  --debug-file-directory=<dir>
                        Path to directory where to look for debug files
  -demangle=false       Alias for --no-demangle
  -demangle=true        Alias for --demangle
  --demangle            Demangle function names
  --dia                 Use the DIA library to access symbols (Windows only)
  --dwp=<file>          Path to DWP file to be use for any split CUs
  -e=<file>             Alias for --obj
  --exe=<file>          Alias for --obj
  --exe <file>          Alias for --obj
  -e <file>             Alias for --obj
  -f=<value>            Alias for --functions=
  --fallback-debug-path=<dir>
                        Fallback path for debug binaries
  --functions=<value>   Print function name for a given address
  --functions           Print function name for a given address
  -f                    Alias for --functions
  --help                Display this help
  --inlines             Print all inlined frames for a given address
  --inlining=false      Alias for --no-inlines
  --inlining=true       Alias for --inlines
  --inlining            Alias for --inlines
  -i                    Alias for --inlines
  --no-demangle         Don't demangle function names
  --no-inlines          Do not print inlined frames
  --no-untag-addresses  Remove memory tags from addresses before symbolization
  --obj=<file>          Path to object file to be symbolized (if not provided, object file should be specified for each input line)
  --output-style=style  Specify print style. Supported styles: LLVM, GNU, JSON
  --pretty-print        Make the output more human friendly
  --print-address       Alias for --addresses
  --print-source-context-lines=<value>
                        Print N lines of source file context
  -p                    Alias for --pretty-print
  --relative-address    Interpret addresses as addresses relative to the image base
  --relativenames       Strip the compilation directory from paths
  -s                    Alias for --basenames
  --verbose             Print verbose line info
  --version             Display the version
  -v                    Alias for --version

llvm-symbolizer Mach-O Specific Options:
  --default-arch=<value> Default architecture (for multi-arch objects)
  --dsym-hint=<dir>      Path to .dSYM bundles to search for debug info for the object files

Pass @FILE as argument to read options from FILE.
```

***

**llvm-ar**

LLVM archiver

```
:~# llvm-ar -h
OVERVIEW: LLVM Archiver

USAGE: llvm-ar [options] [-]<operation>[modifiers] [relpos] [count] <archive> [files]
       llvm-ar -M [<mri-script]

OPTIONS:
  --format              - archive format to create
    =default            -   default
    =gnu                -   gnu
    =darwin             -   darwin
    =bsd                -   bsd
  --plugin=<string>     - ignored for compatibility
  -h --help             - display this help and exit
  --rsp-quoting         - quoting style for response files
    =posix              -   posix
    =windows            -   windows
  --thin                - create a thin archive
  --version             - print the version and exit
  @<file>               - read options from <file>

OPERATIONS:
  d - delete [files] from the archive
  m - move [files] in the archive
  p - print contents of [files] found in the archive
  q - quick append [files] to the archive
  r - replace or insert [files] into the archive
  s - act as ranlib
  t - display list of files in archive
  x - extract [files] from the archive

MODIFIERS:
  [a] - put [files] after [relpos]
  [b] - put [files] before [relpos] (same as [i])
  [c] - do not warn if archive had to be created
  [D] - use zero for timestamps and uids/gids (default)
  [h] - display this help and exit
  [i] - put [files] before [relpos] (same as [b])
  [l] - ignored for compatibility
  [L] - add archive's contents
  [N] - use instance [count] of name
  [o] - preserve original dates
  [O] - display member offsets
  [P] - use full names when matching (implied for thin archives)
  [s] - create an archive index (cf. ranlib)
  [S] - do not build a symbol table
  [T] - deprecated, use --thin instead
  [u] - update only [files] newer than archive contents
  [U] - use actual timestamps and uids/gids
  [v] - be verbose about actions taken
  [V] - display the version and exit
```

***

**llvm-as**

LLVM assembler

```
:~# llvm-as -h
OVERVIEW: llvm .ll -> .bc assembler

USAGE: llvm-as [options] <input .llvm file>

OPTIONS:

Generic Options:

  --help                        - Display available options (--help-hidden for more)
  --help-list                   - Display list of available options (--help-list-hidden for more)
  --version                     - Display the version of this program

llvm-as Options:

  --data-layout=<layout-string> - data layout string to use
  --disable-output              - Disable output
  -f                            - Enable binary output on terminals
  --module-hash                 - Emit module hash
  -o=<filename>                 - Override output filename
```

***

**llvm-bcanalyzer**

LLVM bitcode analyzer

```
:~# llvm-bcanalyzer -h
OVERVIEW: llvm-bcanalyzer file analyzer

USAGE: llvm-bcanalyzer [options] <input bitcode>

OPTIONS:

BC Analyzer Options:

  --block-info=<string> - Use the BLOCK_INFO from the given file
  --check-hash=<string> - Check module hash using the argument as a string table
  --disable-histogram   - Do not print per-code histogram
  --dump                - Dump low level bitcode trace
  --dump-blockinfo      - Include BLOCKINFO details in low level dump
  --non-symbolic        - Emit numeric info in dump even if symbolic info is available
  --show-binary-blobs   - Print binary blobs using hex escapes

Color Options:

  --color               - Use colors in output (default=autodetect)

Generic Options:

  --help                - Display available options (--help-hidden for more)
  --help-list           - Display list of available options (--help-list-hidden for more)
  --version             - Display the version of this program
```

***

**llvm-c-test**

```
:~# llvm-c-test -h
llvm-c-test command

 Commands:
  * --module-dump
    Read bitcode from stdin - print disassembly

  * --lazy-module-dump
    Lazily read bitcode from stdin - print disassembly

  * --new-module-dump
    Read bitcode from stdin - print disassembly

  * --lazy-new-module-dump
    Lazily read bitcode from stdin - print disassembly

  * --module-list-functions
    Read bitcode from stdin - list summary of functions

  * --module-list-globals
    Read bitcode from stdin - list summary of globals

  * --targets-list
    List available targets

  * --object-list-sections
    Read object file from stdin - list sections

  * --object-list-symbols
    Read object file from stdin - list symbols (like nm)

  * --disassemble
    Read lines of triple, hex ascii machine code from stdin - print disassembly

  * --calc
    Read lines of name, rpn from stdin - print generated module

  * --echo
    Read bitcode file from stdin - print it back out

  * --test-diagnostic-handler
    Read bitcode file from stdin with a diagnostic handler set

  * --test-dibuilder
    Run tests for the DIBuilder C API - print generated module

```

***

**llvm-cat**

```
:~# llvm-cat -h
OVERVIEW: Module concatenation
USAGE: llvm-cat [options] <input  files>

OPTIONS:

Generic Options:

  --help        - Display available options (--help-hidden for more)
  --help-list   - Display list of available options (--help-list-hidden for more)
  --version     - Display the version of this program

llvm-cat Options:

  -b            - Whether to perform binary concatenation
  -o=<filename> - Output filename
```

***

**llvm-cfi-verify**

```
:~# llvm-cfi-verify -h
OVERVIEW: Identifies whether Control Flow Integrity protects all indirect control flow instructions in the provided object file, DSO or binary.
Note: Anything statically linked into the provided file *must* be compiled with '-g'. This can be relaxed through the '--ignore-dwarf' flag.
USAGE: llvm-cfi-verify [options] <input file> [ignorelist file]

OPTIONS:

CFI Verify Options:

  --blame-context=<uint>     - Print the blame context (if possible) for BAD instructions. This specifies the number of lines of context to include, where zero disables this feature.
  --blame-context-all=<uint> - Prints the blame context (if possible) for ALL instructions. This specifies the number of lines of context for non-BAD instructions (see --blame-context). If --blame-context is unspecified, it prints this number of contextual lines for BAD instructions as well.
  --print-graphs             - Print graphs around indirect CF instructions in DOT format.
  --summarize                - Print the summary only.

Color Options:

  --color                    - Use colors in output (default=autodetect)

Generic Options:

  --help                     - Display available options (--help-hidden for more)
  --help-list                - Display list of available options (--help-list-hidden for more)
  --version                  - Display the version of this program
```

***

**llvm-config**

Print LLVM compilation options

```
:~# llvm-config -h
usage: llvm-config <OPTION>... [<COMPONENT>...]

Get various configuration information needed to compile programs which use
LLVM.  Typically called from 'configure' scripts.  Examples:
  llvm-config --cxxflags
  llvm-config --ldflags
  llvm-config --libs engine bcreader scalaropts

Options:
  --version         Print LLVM version.
  --prefix          Print the installation prefix.
  --src-root        Print the source root LLVM was built from.
  --obj-root        Print the object root used to build LLVM.
  --bindir          Directory containing LLVM executables.
  --includedir      Directory containing LLVM headers.
  --libdir          Directory containing LLVM libraries.
  --cmakedir        Directory containing LLVM cmake modules.
  --cppflags        C preprocessor flags for files that include LLVM headers.
  --cflags          C compiler flags for files that include LLVM headers.
  --cxxflags        C++ compiler flags for files that include LLVM headers.
  --ldflags         Print Linker flags.
  --system-libs     System Libraries needed to link against LLVM components.
  --libs            Libraries needed to link against LLVM components.
  --libnames        Bare library names for in-tree builds.
  --libfiles        Fully qualified library filenames for makefile depends.
  --components      List of all possible components.
  --targets-built   List of all targets currently built.
  --host-target     Target triple used to configure LLVM.
  --build-mode      Print build mode of LLVM tree (e.g. Debug or Release).
  --assertion-mode  Print assertion mode of LLVM tree (ON or OFF).
  --build-system    Print the build system used to build LLVM (always cmake).
  --has-rtti        Print whether or not LLVM was built with rtti (YES or NO).
  --shared-mode     Print how the provided components can be collectively linked (`shared` or `static`).
  --link-shared     Link the components as shared libraries.
  --link-static     Link the component libraries statically.
  --ignore-libllvm  Ignore libLLVM and link component libraries instead.
Typical components:
  all               All LLVM libraries (default).
  engine            Either a native JIT or a bitcode interpreter.
```

***

**llvm-cov**

Emit coverage information

```
:~# llvm-cov -h
Usage: llvm-cov {export|gcov|report|show} [OPTION]...

Shows code coverage information.

Subcommands:
  export: Export instrprof file to structured format.
  gcov:   Work with the gcov format.
  report: Summarize instrprof style coverage information.
  show:   Annotate source files using instrprof style coverage.
```

***

**llvm-cvtres**

```
:~# llvm-cvtres -h
OVERVIEW: Resource Converter

USAGE: llvm-cvtres [options] file...

OPTIONS:
  /DEFINE:symbol     Not implemented
  /FOLDDUPS:         Not implemented
  /HELP              Display available options
  /MACHINE:{ARM|ARM64|EBC|IA64|X64|X86}
                     Machine architecture
  /NOLOGO            Not implemented
  /OUT:filename      Output file
  /READONLY          Not implemented
  /TIMESTAMP:<value> Timestamp for coff header, defaults to current time
  /VERBOSE           Use verbose output
```

***

**llvm-cxxdump**

```
:~# llvm-cxxdump -h
OVERVIEW: LLVM C++ ABI Data Dumper

USAGE: llvm-cxxdump [options] <input object files>

OPTIONS:

Color Options:

  --color     - Use colors in output (default=autodetect)

Generic Options:

  --help      - Display available options (--help-hidden for more)
  --help-list - Display list of available options (--help-list-hidden for more)
  --version   - Display the version of this program
```

***

**llvm-cxxfilt**

LLVM symbol name demangler

```
:~# llvm-cxxfilt -h
OVERVIEW: LLVM symbol undecoration tool

USAGE: llvm-cxxfilt [options] <mangled>

OPTIONS:
  -_                    Alias for --strip-underscore
  --format=<value>      Specify mangling format. Currently ignored because only 'gnu' is supported
  --help                Display this help
  -h                    Alias for --help
  --no-strip-underscore Don't strip the leading underscore
  -n                    Alias for --no-strip-underscore
  --strip-underscore    Strip the leading underscore
  -s                    Alias for --format
  -t                    Alias for --types
  --version             Display the version

Pass @FILE as argument to read options from FILE.
```

***

**llvm-diff**

LLVM structural ‘diff’

```
:~# llvm-diff -h
USAGE: llvm-diff [options] <first file> <second file> <globals to compare>

OPTIONS:

Color Options:

  --color     - Use colors in output (default=autodetect)

Generic Options:

  --help      - Display available options (--help-hidden for more)
  --help-list - Display list of available options (--help-list-hidden for more)
  --version   - Display the version of this program
```

***

**llvm-dis**

LLVM disassembler

```
:~# llvm-dis -h
OVERVIEW: llvm .bc -> .ll disassembler

USAGE: llvm-dis [options] [input bitcode]...

OPTIONS:

Color Options:

  --color                - Use colors in output (default=autodetect)

Disassembler Options:

  -f                     - Enable binary output on terminals
  --materialize-metadata - Load module without materializing metadata, then materialize only the metadata
  -o=<filename>          - Override output filename
  --show-annotations     - Add informational comments to the .ll file

Generic Options:

  --help                 - Display available options (--help-hidden for more)
  --help-list            - Display list of available options (--help-list-hidden for more)
  --version              - Display the version of this program
```

***

**llvm-dlltool**

```
:~# llvm-dlltool -h
OVERVIEW: llvm-dlltool

USAGE: llvm-dlltool [options] file...

OPTIONS:
  -D <value> Specify the input DLL Name
  -d <value> Input .def File
  -f <value> Assembler Flags
  -k         Kill @n Symbol from export
  -l <value> Generate an import lib
  -m <value> Set target machine
  -S <value> Assembler

TARGETS: i386, i386:x86-64, arm, arm64
```

***

**llvm-dwarfdump**

Manual page for llvm-dwarfdump 14

```
:~# llvm-dwarfdump -h
OVERVIEW: pretty-print DWARF debug information in object files and debug info archives.

USAGE: llvm-dwarfdump [options] <input object files or .dSYM bundles>

OPTIONS:

Color Options:

  --color                    - Use colors in output (default=autodetect)

Generic Options:

  --help                     - Display available options (--help-hidden for more)
  --help-list                - Display list of available options (--help-list-hidden for more)
  --version                  - Display the version of this program

Section-specific Dump Options:
These control which sections are dumped. Where applicable these parameters take an optional =<offset> argument to dump only the entry at the specified offset.

  -a                         - Alias for --all
  --all                      - Dump all debug info sections
  --apple-names              - Dump the .apple_names section
  --apple-namespaces         - Dump the .apple_namespaces section
  --apple-objc               - Dump the .apple_objc section
  --apple-types              - Dump the .apple_types section
  --debug-abbrev             - Dump the .debug_abbrev section
  --debug-addr               - Dump the .debug_addr section
  --debug-aranges            - Dump the .debug_aranges section
  --debug-cu-index           - Dump the .debug_cu_index section
  --debug-frame[=<offset>]     - Dump the .debug_frame section
  --debug-gnu-pubnames       - Dump the .debug_gnu_pubnames section
  --debug-gnu-pubtypes       - Dump the .debug_gnu_pubtypes section
  --debug-info[=<offset>]      - Dump the .debug_info section
  --debug-line[=<offset>]      - Dump the .debug_line section
  --debug-line-str           - Dump the .debug_line_str section
  --debug-loc[=<offset>]       - Dump the .debug_loc section
  --debug-loclists[=<offset>]  - Dump the .debug_loclists section
  --debug-macro              - Dump the .debug_macro section
  --debug-names              - Dump the .debug_names section
  --debug-pubnames           - Dump the .debug_pubnames section
  --debug-pubtypes           - Dump the .debug_pubtypes section
  --debug-ranges             - Dump the .debug_ranges section
  --debug-rnglists           - Dump the .debug_rnglists section
  --debug-str                - Dump the .debug_str section
  --debug-str-offsets        - Dump the .debug_str_offsets section
  --debug-tu-index           - Dump the .debug_tu_index section
  --debug-types[=<offset>]     - Dump the .debug_types section
  --eh-frame                 - Alias for --debug-frame
  --gdb-index                - Dump the .gdb_index section

Specific Options:

  -F                         - Alias for --show-form.
  --arch=<string>            - Dump debug information for the specified CPU architecture only. Architectures may be specified by name or by number. This option can be specified multiple times, once for each desired architecture.
  -c                         - Alias for --show-children.
  --diff                     - Emit diff-friendly output by omitting offsets and addresses.
  -f                         - Alias for --find.
  --find=<name>              - Search for the exact match for <name> in the accelerator tables and print the matching debug information entries. When no accelerator tables are available, the slower but more complete -name option can be used instead.
  -i                         - Alias for --ignore-case.
  --ignore-case              - Ignore case distinctions when using --name.
  --lookup=<address>         - Lookup <address> in the debug information and print out any available file, function, block and line table details.
  -n                         - Alias for --name
  --name=<pattern>           - Find and print all debug info entries whose name (DW_AT_name attribute) matches the exact text in <pattern>.  When used with the the -regex option <pattern> is interpreted as a regular expression.
  -o=<filename>              - Redirect output to the specified file.
  -p                         - Alias for --show-parents.
  --parent-recurse-depth=<N> - Only recurse to a depth of N when displaying parents of debug info entries.
  --quiet                    - Use with -verify to not emit to STDOUT.
  -r                         - Alias for --recurse-depth.
  --recurse-depth=<N>        - Only recurse to a depth of N when displaying children of debug info entries.
  --regex                    - Treat any <pattern> strings as regular expressions when searching with --name. If --ignore-case is also specified, the regular expression becomes case-insensitive.
  --show-children            - Show a debug info entry's children when selectively printing entries.
  --show-form                - Show DWARF form types after the DWARF attribute types.
  --show-parents             - Show a debug info entry's parents when selectively printing entries.
  --show-section-sizes       - Show the sizes of all debug sections, expressed in bytes.
  --statistics               - Emit JSON-formatted debug info quality metrics.
  --summarize-types          - Abbreviate the description of type unit entries.
  -u                         - Alias for --uuid.
  --uuid                     - Show the UUID for each architecture.
  -v                         - Alias for --verbose.
  --verbose                  - Print more low-level encoding details.
  --verify                   - Verify the DWARF debug info.
  -x                         - Alias for --regex

Pass @FILE as argument to read options from FILE.
```

***

**llvm-dwp**

```
:~# llvm-dwp -h
OVERVIEW: merge split dwarf (.dwo) files

USAGE: llvm-dwp [options] <input files>

OPTIONS:

Color Options:

  --color       - Use colors in output (default=autodetect)

Generic Options:

  --help        - Display available options (--help-hidden for more)
  --help-list   - Display list of available options (--help-list-hidden for more)
  --version     - Display the version of this program

Specific Options:

  -e=<filename> - Specify the executable/library files to get the list of *.dwo from
  -o=<filename> - Specify the output file.
```

***

**llvm-exegesis**

LLVM Machine Instruction Benchmark

```
:~# llvm-exegesis -h
USAGE: llvm-exegesis [options]

OPTIONS:

Color Options:

  --color                                            - Use colors in output (default=autodetect)

General options:

  --allow-ginsert-as-artifact                        - Allow G_INSERT to be considered an artifact. Hack around AMDGPU test infinite loops.
  --atomic-counter-update-promoted                   - Do counter update using atomic fetch add  for promoted counters only
  --atomic-first-counter                             - Use atomic fetch add for first counter in a function (usually the entry counter)
  --bounds-checking-single-trap                      - Use one trap block per function
  --debug-info-correlate                             - Use debug info to correlate profiles.
  --debugify-level=<value>                           - Kind of debug info to add
    =locations                                       -   Locations only
    =location+variables                              -   Locations and Variables
  --debugify-quiet                                   - Suppress verbose debugify output
  --disable-i2p-p2i-opt                              - Disables inttoptr/ptrtoint roundtrip optimization
  --do-counter-promotion                             - Do counter register promotion
  --dot-cfg-mssa=<file name for generated dot file>  - file name for generated dot file
  --enable-cse-in-irtranslator                       - Should enable CSE in irtranslator
  --enable-cse-in-legalizer                          - Should enable CSE in Legalizer
  --enable-name-compression                          - Enable name/filename string compression
  --experimental-debug-variable-locations            - Use experimental new value-tracking variable locations
  --fs-profile-debug-bw-threshold=<uint>             - Only show debug message if the source branch weight is greater  than this value.
  --fs-profile-debug-prob-diff-threshold=<uint>      - Only show debug message if the branch probility is greater than this value (in percentage).
  --generate-merged-base-profiles                    - When generating nested context-sensitive profiles, always generate extra base profile for function with all its context profiles merged into it.
  --hash-based-counter-split                         - Rename counter variable of a comdat function based on cfg hash
  --instrprof-atomic-counter-update-all              - Make all profile counter updates atomic (for testing only)
  --iterative-counter-promotion                      - Allow counter promotion across the whole loop nest.
  --max-counter-promotions=<int>                     - Max number of allowed counter promotions
  --max-counter-promotions-per-loop=<uint>           - Max number counter promotions per loop to avoid increasing register pressure too much
  --mir-strip-debugify-only                          - Should mir-strip-debug only strip debug info from debugified modules by default
  --opaque-pointers                                  - Use opaque pointers
  --runtime-counter-relocation                       - Enable relocating counters at runtime.
  --sample-profile-check-record-coverage=<N>         - Emit a warning if less than N% of records in the input profile are matched to the IR.
  --sample-profile-check-sample-coverage=<N>         - Emit a warning if less than N% of samples in the input profile are matched to the IR.
  --sample-profile-max-propagate-iterations=<uint>   - Maximum number of iterations to go through when propagating sample block/edge weights through the CFG.
  --skip-ret-exit-block                              - Suppress counter promotion if exit blocks contain ret.
  --speculative-counter-promotion-max-exiting=<uint> - The max number of exiting blocks of a loop to allow  speculative counter promotion
  --speculative-counter-promotion-to-loop            - When the option is false, if the target block is in a loop, the promotion will be disallowed unless the promoted counter  update can be further/iteratively promoted into an acyclic  region.
  --verify-region-info                               - Verify region info (time consuming)
  --vp-counters-per-site=<number>                    - The average number of profile counters allocated per value profiling site.
  --vp-static-alloc                                  - Do static counter allocation for value profiler
  --x86-align-branch=<string>                        - Specify types of branches to align (plus separated list of types):
                                                       jcc      indicates conditional jumps
                                                       fused    indicates fused conditional jumps
                                                       jmp      indicates direct unconditional jumps
                                                       call     indicates direct and indirect calls
                                                       ret      indicates rets
                                                       indirect indicates indirect unconditional jumps
  --x86-align-branch-boundary=<uint>                 - Control how the assembler should align branches with NOP. If the boundary's size is not 0, it should be a power of 2 and no less than 32. Branches will be aligned to prevent from being across or against the boundary of specified size. The default value 0 does not align branches.
  --x86-branches-within-32B-boundaries               - Align selected instructions to mitigate negative performance impact of Intel's micro code update for errata skx102.  May break assumptions about labels corresponding to particular instructions, and should be used with caution.
  --x86-pad-max-prefix-size=<uint>                   - Maximum number of prefixes to use for padding

Generic Options:

  --help                                             - Display available options (--help-hidden for more)
  --help-list                                        - Display list of available options (--help-list-hidden for more)
  --version                                          - Display the version of this program

llvm-exegesis analysis options:

  --analysis-clustering=<value>                      - the clustering algorithm to use
    =dbscan                                          -   use DBSCAN/OPTICS algorithm
    =naive                                           -   one cluster per opcode
  --analysis-clustering-epsilon=<number>             - epsilon for benchmark point clustering
  --analysis-clusters-output-file=<string>           - 
  --analysis-display-unstable-clusters               - if there is more than one benchmark for an opcode, said benchmarks may end up not being clustered into the same cluster if the measured performance characteristics are different. by default all such opcodes are filtered out. this flag will instead show only such unstable opcodes
  --analysis-inconsistencies-output-file=<string>    - 
  --analysis-inconsistency-epsilon=<number>          - epsilon for detection of when the cluster is different from the LLVM schedule profile values
  --analysis-numpoints=<uint>                        - minimum number of points in an analysis cluster (dbscan only)

llvm-exegesis benchmark options:

  --dump-object-to-disk                              - dumps the generated benchmark object to disk and prints a message to access it
  --ignore-invalid-sched-class                       - ignore instructions that do not define a sched class
  --loop-body-size=<uint>                            - when repeating the instruction snippet by looping over it, duplicate the snippet until the loop body contains at least this many instruction
  --max-configs-per-opcode=<uint>                    - allow to snippet generator to generate at most that many configs
  --num-repetitions=<uint>                           - number of time to repeat the asm snippet
  --opcode-index=<int>                               - opcode to measure, by index, or -1 to measure all opcodes
  --opcode-name=<string>                             - comma-separated list of opcodes to measure, by name
  --repetition-mode=<value>                          - how to repeat the instruction snippet
    =duplicate                                       -   Duplicate the snippet
    =loop                                            -   Loop over the snippet
    =min                                             -   All of the above and take the minimum of measurements
  --snippets-file=<string>                           - code snippets to measure

llvm-exegesis benchmark x86-options:

  --x86-lbr-sample-period=<uint>                     - The sample period (nbranches/sample), used for LBR sampling

llvm-exegesis options:

  --benchmarks-file=<string>                         - File to read (analysis mode) or write (latency/uops/inverse_throughput modes) benchmark results. “-” uses stdin/stdout.
  --mcpu=<string>                                    - cpu name to use for pfm counters, leave empty to autodetect
  --mode=<value>                                     - the mode to run
    =latency                                         -   Instruction Latency
    =inverse_throughput                              -   Instruction Inverse Throughput
    =uops                                            -   Uop Decomposition
    =analysis                                        -   Analysis
  --result-aggregation-mode=<value>                  - How to aggregate multi-values result
    =min                                             -   Keep min reading
    =max                                             -   Keep max reading
    =mean                                            -   Compute mean of all readings
    =min-variance                                    -   Keep readings set with min-variance
```

***

Extract a function from an LLVM module

```
:~# llvm-extract -h
OVERVIEW: llvm extractor

USAGE: llvm-extract [options] <input bitcode file>

OPTIONS:

Generic Options:

  --help                       - Display available options (--help-hidden for more)
  --help-list                  - Display list of available options (--help-list-hidden for more)
  --version                    - Display the version of this program

llvm-extract Options:

  --alias=<alias>              - Specify alias to extract
  --bb=<function:bb1[;bb2...]> - Specify <function, basic block1[;basic block2...]> pairs to extract.
                                 Each pair will create a function.
                                 If multiple basic blocks are specified in one pair,
                                 the first block in the sequence should dominate the rest.
                                 eg:
                                   --bb=f:bb1;bb2 will extract one function with both bb1 and bb2;
                                   --bb=f:bb1 --bb=f:bb2 will extract two functions, one with bb1, one with bb2.
  --delete                     - Delete specified Globals from Module
  -f                           - Enable binary output on terminals
  --func=<function>            - Specify function to extract
  --glob=<global>              - Specify global to extract
  --keep-const-init            - Keep initializers of constants
  -o=<filename>                - Specify output filename
  --ralias=<ralias>            - Specify alias(es) to extract using a regular expression
  --recursive                  - Recursively extract all called functions
  --rfunc=<rfunction>          - Specify function(s) to extract using a regular expression
  --rglob=<rglobal>            - Specify global(s) to extract using a regular expression
```

***

**llvm-lib**

LLVM lib.exe compatible library tool

```
:~# man llvm-lib
LLVM-LIB(1)                          LLVM                          LLVM-LIB(1)

NAME
       llvm-lib - LLVM lib.exe compatible library tool

SYNOPSIS
       llvm-lib  [/libpath:<path>]  [/out:<output>]  [/llvmlibthin]  [/ignore]
       [/machine] [/nologo] [files]

DESCRIPTION
       The llvm-lib command is intended to be a lib.exe compatible  tool.  See
       https://msdn.microsoft.com/en-us/library/7ykb2k5f  for  the general de-
       scription.

       llvm-lib has the following extensions:

       o Bitcode files in symbol tables.  llvm-lib includes symbols from  both
         bitcode files and regular object files in the symbol table.

       o Creating  thin  archives.  The /llvmlibthin option causes llvm-lib to
         create thin archive that contain only the symbol table and the header
         for  the  various  members. These files are much smaller, but are not
         compatible with link.exe (lld can handle them).

AUTHOR
       Maintained by the LLVM Team (https://llvm.org/).

COPYRIGHT
       2003-2023, LLVM Project

14                                2023-02-17                       LLVM-LIB(1)
```

***

**llvm-link**

LLVM bitcode linker

```
:~# llvm-link -h
OVERVIEW: llvm linker

USAGE: llvm-link [options] <input bitcode files>

OPTIONS:

Color Options:

  --color                       - Use colors in output (default=autodetect)

Generic Options:

  --help                        - Display available options (--help-hidden for more)
  --help-list                   - Display list of available options (--help-list-hidden for more)
  --version                     - Display the version of this program

Link Options:

  --disable-debug-info-type-map - Don't use a uniquing type map for debug info
  --disable-lazy-loading        - Disable lazy module loading
  -f                            - Enable binary output on terminals
  --import=<function:filename>  - Pair of function name and filename, where function should be imported from bitcode in filename
  --internalize                 - Internalize linked symbols
  -o=<filename>                 - Override output filename
  --only-needed                 - Link only needed symbols
  --override=<filename>         - input bitcode file which can override previously defined symbol(s)
  --summary-index=<filename>    - Module summary index filename
  --suppress-warnings           - Suppress all linking warnings
  -v                            - Print information about actions taken
```

***

**llvm-lto**

```
:~# llvm-lto -h
OVERVIEW: llvm LTO linker

USAGE: llvm-lto [options] <input bitcode files>

OPTIONS:

Color Options:

  --color                                 - Use colors in output (default=autodetect)

Generic Options:

  --help                                  - Display available options (--help-hidden for more)
  --help-list                             - Display list of available options (--help-list-hidden for more)
  --version                               - Display the version of this program

LTO Options:

  -O=<char>                               - Optimization level. [-O0, -O1, -O2, or -O3] (default = '-O2')
  --check-for-objc                        - Only check if the module has objective-C defined in it
  --disable-verify                        - Do not run the verifier during the optimization pipeline
  --dso-symbol=<string>                   - Symbol to put in the symtab in the resulting dso
  --exported-symbol=<string>              - List of symbols to export from the resulting object file
  -j=<uint>                               - Number of backend threads
  --list-dependent-libraries-only         - Instead of running LTO, list the dependent libraries in each IR file
  --list-symbols-only                     - Instead of running LTO, list the symbols in each IR file
  --lto-freestanding                      - Enable Freestanding (disable builtins / TLI) during LTO
  -o=<filename>                           - Override output filename
  --print-macho-cpu-only                  - Instead of running LTO, print the mach-o cpu in each IR file
  --restore-linkage                       - Restore original linkage of globals prior to CodeGen
  --save-linked-module                    - Write linked LTO module to file before optimize
  --save-merged-module                    - Write merged LTO module to file before CodeGen
  --set-merged-module                     - Use the first input module as the merged module
  --thinlto                               - Only write combined global index for ThinLTO backends
  --thinlto-action=<value>                - Perform a single ThinLTO stage:
    =thinlink                             -   ThinLink: produces the index by linking only the summaries.
    =distributedindexes                   -   Produces individual indexes for distributed backends.
    =emitimports                          -   Emit imports files for distributed backends.
    =promote                              -   Perform pre-import promotion (requires -thinlto-index).
    =import                               -   Perform both promotion and cross-module importing (requires -thinlto-index).
    =internalize                          -   Perform internalization driven by -exported-symbol (requires -thinlto-index).
    =optimize                             -   Perform ThinLTO optimizations.
    =codegen                              -   CodeGen (expected to match llc)
    =run                                  -   Perform ThinLTO end-to-end
  --thinlto-cache-dir=<string>            - Enable ThinLTO caching.
  --thinlto-cache-entry-expiration=<uint> - Set ThinLTO cache entry expiration time.
  --thinlto-cache-max-size-bytes=<ulong>  - Set ThinLTO cache pruning directory maximum size in bytes.
  --thinlto-cache-max-size-files=<int>    - Set ThinLTO cache pruning directory maximum number of files.
  --thinlto-cache-pruning-interval=<int>  - Set ThinLTO cache pruning interval.
  --thinlto-index=<string>                - Provide the index produced by a ThinLink, required to perform the promotion and/or importing.
  --thinlto-index-stats                   - Print statistic for the index in every input files
  --thinlto-module-id=<string>            - For the module ID for the file to process, useful to match what is in the index.
  --thinlto-prefix-replace=<string>       - Control where files for distributed backends are created. Expects 'oldprefix;newprefix' and if path prefix of output file is oldprefix it will be replaced with newprefix.
  --thinlto-save-objects=<string>         - Save ThinLTO generated object files using filenames created in the given directory.
  --thinlto-save-temps=<string>           - Save ThinLTO temp files using filenames created by adding suffixes to the given file path prefix.
  --use-diagnostic-handler                - Use a diagnostic handler to test the handler interface
```

***

**llvm-lto2**

```
:~# llvm-lto2 -h
Available subcommands: dump-symtab run
```

***

**llvm-mc**

Manual page for llvm-mc 14

```
:~# llvm-mc -h
OVERVIEW: llvm machine code playground

USAGE: llvm-mc [options] <input file>

OPTIONS:

Color Options:

  --color                                           - Use colors in output (default=autodetect)

Generic Options:

  --help                                            - Display available options (--help-hidden for more)
  --help-list                                       - Display list of available options (--help-list-hidden for more)
  --version                                         - Display the version of this program

MC Options:

  -I=<directory>                                    - Directory of include files
  -M=<string>                                       - Disassembler options
  --arch=<string>                                   - Target arch to assemble for, see -version for available targets
  Action to perform:
      --as-lex                                         - Lex tokens from a .s file
      --assemble                                       - Assemble a .s file (default)
      --disassemble                                    - Disassemble strings of hex bytes
      --mdis                                           - Marked up disassembly of strings of hex bytes
  --compress-debug-sections=<value>                 - Choose DWARF debug sections compression:
    =none                                           -   No compression
    =zlib                                           -   Use zlib compression
    =zlib-gnu                                       -   Use zlib-gnu compression (deprecated)
  --defsym=<string>                                 - Defines a symbol to be an integer constant
  --fdebug-compilation-dir=<string>                 - Specifies the debug info's compilation dir
  --fdebug-prefix-map=<= separated key-value pairs> - Map file source paths in debug info
  --filetype=<value>                                - Choose an output file type:
    =asm                                            -   Emit an assembly ('.s') file
    =null                                           -   Don't emit anything (for timing purposes)
    =obj                                            -   Emit a native object ('.o') file
  -g                                                - Generate dwarf debugging info for assembly source files
  --large-code-model                                - Create cfi directives that assume the code might be more than 2gb away
  --main-file-name=<string>                         - Specifies the name we should consider the input file
  --masm-hexfloats                                  - Enable MASM-style hex float initializers (3F800000r)
  --masm-integers                                   - Enable binary and hex masm integers (0b110 and 0ABCh)
  --mattr=<a1,+a2,-a3,...>                          - Target specific attributes (-mattr=help for details)
  --mcpu=<cpu-name>                                 - Target a specific cpu type (-mcpu=help for details)
  --motorola-integers                               - Enable binary and hex Motorola integers (%110 and $ABC)
  -n                                                - Don't assume assembly file starts in the text section
  --no-exec-stack                                   - File doesn't need an exec stack
  -o=<filename>                                     - Output filename
  --output-asm-variant=<uint>                       - Syntax variant to use for output printing
  --position-independent                            - Position independent
  --preserve-comments                               - Preserve Comments in outputted assembly
  --print-imm-hex                                   - Prefer hex format for immediate values
  --relax-relocations                               - Emit R_X86_64_GOTPCRELX instead of R_X86_64_GOTPCREL
  --save-temp-labels                                - Don't discard temporary labels
  --show-encoding                                   - Show instruction encodings
  --show-inst                                       - Show internal instruction representation
  --show-inst-operands                              - Show instructions operands as parsed
  --split-dwarf-file=<filename>                     - DWO output filename
  --triple=<string>                                 - Target triple to assemble for, see -version for available targets
```

***

**llvm-mca**

LLVM Machine Code Analyzer

```
:~# llvm-mca -h
OVERVIEW: llvm machine code performance analyzer.

USAGE: llvm-mca [options] <input file>

OPTIONS:

Generic Options:

  --help                           - Display available options (--help-hidden for more)
  --help-list                      - Display list of available options (--help-list-hidden for more)
  --version                        - Display the version of this program

Tool Options:

  --dispatch=<uint>                - Override the processor dispatch width
  --instruction-tables             - Print instruction tables
  --iterations=<uint>              - Number of iterations to run
  --json                           - Print the output in json format
  --lqueue=<uint>                  - Size of the load queue
  --march=<string>                 - Target architecture. See -version for available targets
  --mattr=<string>                 - Additional target features.
  --mcpu=<cpu-name>                - Target a specific cpu type (-mcpu=help for details)
  --mtriple=<string>               - Target triple. See -version for available targets
  --noalias                        - If set, assume that loads and stores do not alias
  -o=<filename>                    - Output filename
  --output-asm-variant=<int>       - Syntax variant to use for output printing
  --print-imm-hex                  - Prefer hex format when printing immediate values
  --register-file-size=<uint>      - Maximum number of physical registers which can be used for register mappings
  --squeue=<uint>                  - Size of the store queue

View Options:

  --all-stats                      - Print all hardware statistics
  --all-views                      - Print all views including hardware statistics
  --bottleneck-analysis            - Enable bottleneck analysis (disabled by default)
  --disable-cb                     - Disable custom behaviour (use the default class which does nothing).
  --dispatch-stats                 - Print dispatch statistics
  --instruction-info               - Print the instruction info view (enabled by default)
  --register-file-stats            - Print register file statistics
  --resource-pressure              - Print the resource pressure view (enabled by default)
  --retire-stats                   - Print retire control unit statistics
  --scheduler-stats                - Print scheduler statistics
  --show-barriers                  - Print memory barrier information in the instruction info view
  --show-encoding                  - Print encoding information in the instruction info view
  --timeline                       - Print the timeline view
  --timeline-max-cycles=<uint>     - Maximum number of cycles in the timeline view, or 0 for unlimited. Defaults to 80 cycles
  --timeline-max-iterations=<uint> - Maximum number of iterations to print in timeline view
```

***

```
:~# llvm-modextract -h
OVERVIEW: Module extractor
USAGE: llvm-modextract [options] <input bitcode>

OPTIONS:

Color Options:

  --color       - Use colors in output (default=autodetect)

Generic Options:

  --help        - Display available options (--help-hidden for more)
  --help-list   - Display list of available options (--help-list-hidden for more)
  --version     - Display the version of this program

Modextract Options:

  -b            - Whether to perform binary extraction
  -n=<index>    - Index of module to extract
  -o=<filename> - Output filename
```

***

**llvm-mt**

```
:~# llvm-mt -h
OVERVIEW: Manifest Tool

USAGE: llvm-mt [options] file...

OPTIONS:
  /canonicalize:         Not supported
  /category              Not supported
  /check_for_duplicates: Not supported
  /dll:dll               Not supported
  /hashupdate:file       Not supported
  /hashupdate            Not supported
  /identity:identity     Not supported
  /inputresource:file    Not supported
  /makecdfs:             Not supported
  /managedassemblyname:assembly
                         Not supported
  /manifest manifest     Used to specify each manifest that need to be processed
  /nodependency          Not supported
  /nologo                No effect as this tool never writes copyright data.  Included for parity
  /notify_update         Exit with a special exit code if the output file has changed
  /out:manifest          Name of the output manifest.  If this is skipped and only one manifest is being operated upon by the tool, that manifest is modified in place
  /outputresource:file   Not supported
  /outputresource        Not supported
  /replacements:file     Not supported
  /rgs:script            Not supported
  /tlb:file              Not supported
  /updateresource:file   Not supported
  /validate_file_hashes: Not supported
  /validate_manifest     Not supported
  /verbose               Not supported
```

***

**llvm-nm**

List LLVM bitcode and object file’s symbol table

```
:~# llvm-nm -h
OVERVIEW: LLVM symbol table dumper

USAGE: llvm-nm [options] <input object files>

OPTIONS:
  -A                Alias for --print-file-name
  -a                Alias for --debug-syms
  -B                Alias for --format=bsd
  -C                Alias for --demangle
  --debug-syms      Show all symbols, even debugger only
  --defined-only    Show only defined symbols
  --demangle        Demangle C++ symbol names
  --dynamic         Display dynamic symbols instead of normal symbols
  -D                Alias for --dynamic
  --extern-only     Show only external symbols
  --format=<format> Specify output format: bsd (default), posix, sysv, darwin, just-symbols
  -f <format>       Alias for --format
  -g                Alias for --extern-only
  --help            Display this help
  -h                Alias for --help
  -j                Alias for --format=just-symbols
  -m                Alias for --format=darwin
  --no-demangle     Don't demangle symbol names
  --no-llvm-bc      Disable LLVM bitcode reader
  --no-sort         Show symbols in order encountered
  --no-weak         Show only non-weak symbols
  --numeric-sort    Sort symbols by address
  -n                Alias for --numeric-sort
  -o                Alias for --print-file-name
  --portability     Alias for --format=posix
  --print-armap     Print the archive map
  --print-file-name Precede each symbol with the object file it came from
  --print-size      Show symbol size as well as address
  -P                Alias for --format=posix
  -p                Alias for --no-sort
  --quiet           Suppress 'no symbols' diagnostic
  --radix=<radix>   Radix (o/d/x) for printing symbol Values
  --reverse-sort    Sort in reverse order
  -r                Alias for --reverse-sort
  --size-sort       Sort symbols by size
  --special-syms    Do not filter special symbols from the output
  -S                Alias for --print-size
  -t <radix>        Alias for --radix
  --undefined-only  Show only undefined symbols
  -u                Alias for --undefined-only
  --version         Display the version
  -V                Alias for --version
  -v                Alias for --numeric-sort

llvm-nm Mach-O Specific Options:
  --add-dyldinfo    Add symbols from the dyldinfo not already in the symbol table
  --add-inlinedinfo Add symbols from the inlined libraries, TBD only
  --arch=<value>    architecture(s) from a Mach-O file to dump
  --dyldinfo-only   Show only symbols from the dyldinfo
  --no-dyldinfo     Don't add any symbols from the dyldinfo
  -s                Dump only symbols from this segment and section name
  -x                Print symbol entry in hex

Pass @FILE as argument to read options from FILE.
```

***

**llvm-objcopy**

Object copying and editing tool

```
:~# llvm-objcopy -h
OVERVIEW: llvm-objcopy tool

USAGE: llvm-objcopy [options] input [output]

OPTIONS:
  --add-gnu-debuglink=debug-file
                          Add a .gnu_debuglink for <debug-file>
  --add-section=section=file
                          Make a section named <section> with the contents of <file>.
  --add-symbol=name=[section:]value[,flags]
                          Add new symbol <name> to .symtab. Accepted flags: global, local, weak, default, hidden, protected, file, section, object, function, indirect-function. Accepted but ignored for compatibility: debug, constructor, warning, indirect, synthetic, unique-object, before.
  --adjust-start <value>  Alias for --change-start
  --allow-broken-links    Allow the tool to remove sections even if it would leave invalid section references. The appropriate sh_link fields will be set to zero.
  --binary-architecture=<value>
                          Ignored for compatibility
  -B <value>              Alias for --binary-architecture
  --change-start=incr     Add <incr> to the start address. Can be specified multiple times, all values will be applied cumulatively.
  --compress-debug-sections=[ zlib | zlib-gnu ]
                          Compress DWARF debug sections using specified style. Supported styles: 'zlib-gnu' and 'zlib'
  --decompress-debug-sections
                          Decompress DWARF debug sections.
  --disable-deterministic-archives
                          Disable deterministic mode when operating on archives (use real values for UIDs, GIDs, and timestamps).
  --discard-all           Remove all local symbols except file and section symbols. Also remove all debug sections
  --discard-locals        Remove compiler-generated local symbols, (e.g. symbols starting with .L)
  --dump-section=section=file
                          Dump contents of section named <section> into file <file>
  -D                      Alias for --enable-deterministic-archives
  --enable-deterministic-archives
                          Enable deterministic mode when operating on archives (use zero for UIDs, GIDs, and timestamps).
  --extract-dwo           Remove all sections that are not DWARF .dwo sections from file
  --extract-main-partition
                          Extract main partition from the input file
  --extract-partition=name
                          Extract named partition from input file
  -F <value>              Alias for --target
  --globalize-symbol=symbol
                          Mark <symbol> as global
  --globalize-symbols=filename
                          Reads a list of symbols from <filename> and marks them global.
  -G <value>              Alias for --keep-global-symbol
  -g                      Alias for --strip-debug
  --input-target=<value>  Format of the input file
  -I <value>              Alias for --input-target
  -j <value>              Alias for --only-section
  --keep-file-symbols     Do not remove file symbols
  --keep-global-symbol=symbol
                          Convert all symbols except <symbol> to local. May be repeated to convert all except a set of symbols to local.
  --keep-global-symbols=filename
                          Reads a list of symbols from <filename> and runs as if --keep-global-symbol=<symbol> is set for each one. <filename> contains one symbol per line and may contain comments beginning with '#'. Leading and trailing whitespace is stripped from each line. May be repeated to read symbols from many files.
  --keep-section=section  Keep <section>
  --keep-symbol=symbol    Do not remove symbol <symbol>
  --keep-symbols=filename Reads a list of symbols from <filename> and runs as if --keep-symbol=<symbol> is set for each one. <filename> contains one symbol per line and may contain comments beginning with '#'. Leading and trailing whitespace is stripped from each line. May be repeated to read symbols from many files.
  --keep-undefined        Do not remove undefined symbols
  -K <value>              Alias for --keep-symbol
  --localize-hidden       Mark all symbols that have hidden or internal visibility as local
  --localize-symbol=symbol
                          Mark <symbol> as local
  --localize-symbols=filename
                          Reads a list of symbols from <filename> and marks them local.
  -L <value>              Alias for --localize-symbol
  --new-symbol-visibility=<value>
                          Visibility of symbols generated for binary input or added with --add-symbol unless otherwise specified. The default value is 'default'.
  -N <value>              Alias for --strip-symbol
  --only-keep-debug       Produce a debug file as the output that only preserves contents of sections useful for debugging purposes
  --only-section=section  Remove all but <section>
  --output-target=<value> Format of the output file
  -O <value>              Alias for --output-target
  --prefix-alloc-sections=prefix
                          Add <prefix> to the start of every allocated section name
  --prefix-symbols=prefix Add <prefix> to the start of every symbol name
  --preserve-dates        Preserve access and modification timestamps
  -p                      Alias for --preserve-dates
  --redefine-sym=old=new  Change the name of a symbol old to new
  --redefine-syms=filename
                          Reads a list of symbol pairs from <filename> and runs as if --redefine-sym=<old>=<new> is set for each one. <filename> contains two symbols per line separated with whitespace and may contain comments beginning with '#'. Leading and trailing whitespace is stripped from each line. May be repeated to read symbols from many files.
  --regex                 Permit regular expressions in name comparison
  --remove-section=section
                          Remove <section>
  --rename-section=old=new[,flag1,...]
                          Renames a section from old to new, optionally with specified flags. Flags supported for GNU compatibility: alloc, load, noload, readonly, exclude, debug, code, data, rom, share, contents, merge, strings.
  -R <value>              Alias for --remove-section
  --set-section-alignment=section=align
                          Set alignment for a given section.
  --set-section-flags=section=flag1[,flag2,...]
                          Set section flags for a given section. Flags supported for GNU compatibility: alloc, load, noload, readonly, exclude, debug, code, data, rom, share, contents, merge, strings.
  --set-start=addr        Set the start address to <addr>. Overrides any previous --change-start or --adjust-start values.
  --split-dwo=dwo-file    Equivalent to extract-dwo on the input file to <dwo-file>, then strip-dwo on the input file
  --strip-all-gnu         Compatible with GNU's --strip-all
  --strip-all             Remove non-allocated sections outside segments. .gnu.warning* and .ARM.attribute sections are not removed
  --strip-debug           Remove all debug sections
  --strip-dwo             Remove all DWARF .dwo sections from file
  --strip-non-alloc       Remove all non-allocated sections outside segments
  --strip-sections        Remove all section headers and all sections not in segments
  --strip-symbol=symbol   Strip <symbol>
  --strip-symbols=filename
                          Reads a list of symbols from <filename> and removes them.
  --strip-unneeded-symbol=symbol
                          Remove symbol <symbol> if it is not needed by relocations
  --strip-unneeded-symbols=filename
                          Reads a list of symbols from <filename> and removes them if they are not needed by relocations
  --strip-unneeded        Remove all symbols not needed by relocations
  --subsystem=name[:version]
                          Set PE subsystem and version
  -S                      Alias for --strip-all
  --target=<value>        Format of the input and output file
  --update-section=name=file
                          Add section <name> with contents from a file <file>.
  -U                      Alias for --disable-deterministic-archives
  --version               Print the version and exit.
  -V                      Alias for --version
  --weaken-symbol=symbol  Mark <symbol> as weak
  --weaken-symbols=filename
                          Reads a list of symbols from <filename> and marks them weak.
  --weaken                Mark all global symbols as weak
  --wildcard              Allow wildcard syntax for symbol-related flags. Incompatible with --regex. Allows using '*' to match any number of characters, '?' to match any single character, '' to escape special characters, and '[]' to define character classes. Wildcards beginning with '!' will prevent a match, for example "-N '*' -N '!x'" will strip all symbols except for "x".
  -W <value>              Alias for --weaken-symbol
  -w                      Alias for --wildcard
  -X                      Alias for --discard-locals
  -x                      Alias for --discard-all

Pass @FILE as argument to read options from FILE.
```

***

**llvm-objdump**

Manual page for llvm-objdump 14

```
:~# llvm-objdump --help
OVERVIEW: llvm object file dumper

USAGE: llvm-objdump [options] <input object files>

OPTIONS:
  --adjust-vma=offset     Increase the displayed address by the specified offset
  --all-headers           Display all available header information, relocation entries and the symbol table
  --arch-name=<value>     Target arch to disassemble for, see --version for available targets
  --archive-headers       Display archive header information
  -a                      Alias for --archive-headers
  -C                      Alias for --demangle
  --debug-vars-indent=<value>
                          Distance to indent the source-level variable display, relative to the start of the disassembly
  --debug-vars=<value>    Print the locations (in registers or memory) of source-level variables alongside disassembly. Supported formats: ascii, unicode (default)
  --demangle              Demangle symbol names
  --disassemble-all       Disassemble all sections found in the input files
  --disassemble-symbols=<value>
                          List of symbols to disassemble. Accept demangled names when --demangle is specified, otherwise accept mangled names
  --disassemble-zeroes    Do not skip blocks of zeroes when disassembling
  --disassembler-options=options
                          Pass target specific disassembler options
  --disassemble           Disassemble all executable sections found in the input files
  --dwarf=<value>         Dump the specified DWARF debug sections. The only supported value is 'frames'
  --dynamic-reloc         Display the dynamic relocation entries in the file
  --dynamic-syms          Display the contents of the dynamic symbol table
  -D                      Alias for --disassemble-all
  -d                      Alias for --disassemble
  --fault-map-section     Display the content of the fault map section
  --file-headers          Display the contents of the overall file header
  --full-contents         Display the content of each section
  -f                      Alias for --file-headers
  --headers               Alias for --section-headers
  --help                  Display available options (--help-hidden for more)
  -h                      Alias for --section-headers
  -j <value>              Alias for --section
  --line-numbers          When disassembling, display source line numbers. Implies --disassemble
  -l                      Alias for --line-numbers
  --macho                 Use MachO specific object file parser
  --mattr=a1,+a2,-a3,...  Target specific attributes (--mattr=help for details)
  --mcpu=cpu-name         Target a specific cpu type (--mcpu=help for details)
  -M <value>              Alias for --disassembler-options=
  -m                      Alias for --macho
  --no-leading-addr       When disassembling, do not print leading addresses
  --no-print-imm-hex      Do not use hex format for immediate values (default)
  --no-show-raw-insn      When disassembling instructions, do not print the instruction bytes.
  --prefix-strip=prefix   Strip out initial directories from absolute paths. No effect without --prefix
  --prefix=prefix         Add prefix to absolute paths
  --print-imm-hex         Use hex format for immediate values
  --private-headers       Display format specific file headers
  -p                      Alias for --private-headers
  --raw-clang-ast         Dump the raw binary contents of the clang AST section
  --reloc                 Display the relocation entries in the file
  -R                      Alias for --dynamic-reloc
  -r                      Alias for --reloc
  --section-headers       Display summaries of the headers for each section.
  --section=<value>       Operate on the specified sections only. With --macho dump segment,section
  --show-lma              Display LMA column when dumping ELF section headers
  --source                When disassembling, display source interleaved with the disassembly. Implies --disassemble
  --start-address=address Set the start address for disassembling, printing relocations and printing symbols
  --stop-address=address  Set the stop address for disassembling, printing relocations and printing symbols
  --symbol-description    Add symbol description for disassembly. This option is for XCOFF files only.
  --symbolize-operands    Symbolize instruction operands when disassembling
  --syms                  Display the symbol table
  -S                      Alias for --source
  -s                      Alias for --full-contents
  --triple=<value>        Target triple to disassemble for, see --version for available targets
  -T                      Alias for --dynamic-syms
  -t                      Alias for --syms
  --unwind-info           Display unwind information
  -u                      Alias for --unwind-info
  --version               Display the version of this program
  -v                      Alias for --version
  --wide                  Ignored for compatibility with GNU objdump
  --x86-asm-syntax=att    Emit AT&T-style disassembly
  --x86-asm-syntax=intel  Emit Intel-style disassembly
  -x                      Alias for --all-headers
  -z                      Alias for --disassemble-zeroes

llvm-objdump MachO Specific Options:
  --arch=<value>         architecture(s) from a Mach-O file to dump
  --archive-member-offsets
                         Print the offset to each archive member for Mach-O archives (requires --macho and --archive-headers)
  --bind                 Display mach-o binding info
  --data-in-code         Print the data in code table for Mach-O objects (requires --macho)
  --dis-symname <value>  disassemble just this symbol's instructions (requires --macho)
  --dsym=<value>         Use .dSYM file for debug info
  --dylib-id             Print the shared library's id for the dylib Mach-O file (requires --macho)
  --dylibs-used          Print the shared libraries used for linked Mach-O files (requires --macho)
  --exports-trie         Display mach-o exported symbols
  --full-leading-addr    Print full leading address
  --function-starts      Print the function starts table for Mach-O objects (requires --macho)
  -g                     Print line information from debug info if available
  --indirect-symbols     Print indirect symbol table for Mach-O objects (requires --macho)
  --info-plist           Print the info plist section as strings for Mach-O objects (requires --macho)
  --lazy-bind            Display mach-o lazy binding info
  --link-opt-hints       Print the linker optimization hints for Mach-O objects (requires --macho)
  --no-leading-headers   Print no leading headers
  --no-symbolic-operands do not symbolic operands when disassembling (requires --macho)
  --non-verbose          Print the info for Mach-O objects in non-verbose or numeric form (requires --macho)
  --objc-meta-data       Print the Objective-C runtime meta data for Mach-O files (requires --macho)
  --private-header       Display only the first format specific file header
  --rebase               Display mach-o rebasing info
  --rpaths               Print the runtime search paths for the Mach-O file (requires --macho)
  --universal-headers    Print Mach-O universal headers (requires --macho)
  --weak-bind            Display mach-o weak binding info

Pass @FILE as argument to read options from FILE.
```

***

**llvm-opt-report**

```
:~# llvm-opt-report -h
OVERVIEW: A tool to generate an optimization report from YAML optimization record files.

USAGE: llvm-opt-report [options] <input>

OPTIONS:

Generic Options:

  --help            - Display available options (--help-hidden for more)
  --help-list       - Display list of available options (--help-list-hidden for more)
  --version         - Display the version of this program

llvm-opt-report options:

  --format=<string> - The format of the remarks.
  --no-demangle     - Don't demangle function names
  -o=<string>       - Output file
  -r=<string>       - Root for relative input paths
  -s                - Don't include vectorization factors, etc.
```

***

**llvm-pdbutil**

PDB File forensics and diagnostics

```
:~# llvm-pdbutil -h
OVERVIEW: LLVM PDB Dumper

USAGE: llvm-pdbutil [subcommand] [options]

SUBCOMMANDS:

  bytes    - Dump raw bytes from the PDB file
  diadump  - Dump debug information using a DIA-like API
  dump     - Dump MSF and CodeView debug info
  explain  - Explain the meaning of a file offset
  export   - Write binary data from a stream to a file
  merge    - Merge multiple PDBs into a single PDB
  pdb2yaml - Generate a detailed YAML description of a PDB File
  pretty   - Dump semantic information about types and symbols
  yaml2pdb - Generate a PDB file from a YAML description

  Type "llvm-pdbutil <subcommand> --help" to get more help on a specific subcommand

OPTIONS:

Generic Options:

  --help      - Display available options (--help-hidden for more)
  --help-list - Display list of available options (--help-list-hidden for more)
  --version   - Display the version of this program
```

***

**llvm-profdata**

Profile data tool

```
:~# llvm-profdata -h
OVERVIEW: LLVM profile data tools

USAGE: llvm-profdata <command> [args...]
USAGE: llvm-profdata <command> -help

See each individual command --help for more details.
Available commands: merge, show, overlap
```

***

**llvm-ranlib**

Manual page for llvm-ranlib 14

```
:~# llvm-ranlib -h
OVERVIEW: LLVM Ranlib (llvm-ranlib)

  This program generates an index to speed access to archives

USAGE: llvm-ranlib <archive-file>

OPTIONS:
  -h --help             - Display available options
  -v --version          - Display the version of this program
  -D                    - Use zero for timestamps and uids/gids (default)
  -U                    - Use actual timestamps and uids/gids
```

***

**llvm-rc**

```
:~# llvm-rc -h
OVERVIEW: Resource Converter

USAGE: rc [options] file...

OPTIONS:
  /?             Display this help and exit.
  /C <value>     Set the codepage used for input strings.
  /dry-run       Don't compile the input; only try to parse it.
  /D <value>     Define a symbol for the C preprocessor.
  /FO <value>    Change the output file location.
  /H             Display this help and exit.
  /I <value>     Add an include path.
  /LN <value>    Set the default language name.
  /L <value>     Set the default language identifier.
  /no-preprocess Don't try to preprocess the input file.
  /N             Null-terminate all strings in the string table.
  /U <value>     Undefine a symbol for the C preprocessor.
  /V             Be verbose.
  /X             Ignore 'include' variable.
  /Y             Suppress warnings on duplicate resource IDs.
```

***

**llvm-readelf**

GNU-style LLVM Object Reader

```
:~# llvm-readelf --help
OVERVIEW: LLVM Object Reader

USAGE: llvm-readelf [options] <input object files>

OPTIONS:
  --addrsig             Display address-significance table
  --all                 Equivalent to setting: --file-header, --program-headers, --section-headers, --symbols, --relocations, --dynamic-table, --notes, --version-info, --unwind, --section-groups and --histogram
  --arch-specific       Display architecture-specific information
  -A                    Alias for --arch-specific
  -a                    Alias for --all
  --bb-addr-map         Display the BB address map section
  --cg-profile          Display call graph profile section
  -C                    Alias for --demangle
  --demangle            Demangle symbol names
  --dependent-libraries Display the dependent libraries section
  --dt                  Alias for --dyn-syms
  --dyn-relocations     Display the dynamic relocation entries in the file
  --dyn-symbols         Alias for --dyn-syms
  --dyn-syms            Display the dynamic symbol table
  --dynamic             Alias for --dynamic-table
  --expand-relocs       Expand each shown relocation to multiple lines
  -e                    Alias for --headers
  --file-header         Display file header
  --headers             Equivalent to setting: --file-header, --program-headers, --section-headers
  --help                Display this help
  --hex-dump=<name or index>
                        Display the specified section(s) as hexadecimal bytes
  -h                    Alias for --file-header
  -l                    Alias for --program-headers
  --no-demangle         Do not demangle symbol names (default)
  -n                    Alias for --notes
  --pretty-print        Pretty print JSON output
  -p <name or index>    Alias for --string-dump
  --relocations         Alias for --relocs
  --relocs              Display the relocation entries in the file
  -r                    Alias for --relocs
  --sd                  Alias for --section-data
  --section-data        Display section data for each section shown. This option has no effect for GNU style output
  --section-details     Display the section details
  --section-headers     Display section headers
  --section-mapping     Display the section to segment mapping
  --section-relocations Display relocations for each section shown. This option has no effect for GNU style output
  --section-symbols     Display symbols for each section shown. This option has no effect for GNU style output
  --sections            Alias for --section-headers
  --sr                  Alias for --section-relocations
  --stack-sizes         Display contents of all stack sizes sections. This option has no effect for GNU style output
  --stackmap            Display contents of stackmap section
  --string-dump=<name or index>
                        Display the specified section(s) as a list of strings
  --string-table        Display the string table (only for XCOFF now)
  --st                  Alias for --section-symbols
  --symbols             Display the symbol table. Also display the dynamic symbol table when using GNU output style for ELF
  --syms                Alias for --symbols
  -S                    Alias for --section-headers
  -s                    Alias for --symbols
  -t                    Alias for --section-details
  --unwind              Display unwind information
  -u                    Alias for --unwind
  --version             Display the version
  --wide                Ignored for GNU readelf compatibility
  -W                    Ignored for GNU readelf compatibility
  -x <name or index>    Alias for --hex-dump

OPTIONS (ELF specific):
  --dynamic-table      Display the dynamic section table
  -d                   Alias for --dynamic-table
  --elf-linker-options Display the .linker-options section
  --elf-output-style=<value>
                       Specify ELF dump style: LLVM, GNU, JSON
  --gnu-hash-table     Display the GNU hash table for dynamic symbols
  -g                   Alias for --section-groups
  --hash-symbols       Display the dynamic symbols derived from the hash section
  --hash-table         Display .hash section
  --histogram          Display bucket list histogram for hash sections
  -I                   Alias for --histogram
  --needed-libs        Display the needed libraries
  --notes              Display notes
  --program-headers    Display program headers
  --raw-relr           Do not decode relocations in SHT_RELR section, display raw contents
  --section-groups     Display section groups
  --segments           Alias for --program-headers
  --version-info       Display version sections
  -V                   Alias for --version-info

OPTIONS (Mach-O specific):
  --macho-data-in-code   Display Data in Code command
  --macho-dysymtab       Display Dysymtab command
  --macho-indirect-symbols
                         Display indirect symbols
  --macho-linker-options Display linker options
  --macho-segment        Display Segment command
  --macho-version-min    Display version min command

OPTIONS (PE/COFF specific):
  --codeview-ghash        Enable global hashing for CodeView type stream de-duplication
  --codeview-merged-types Display the merged CodeView type stream
  --codeview-subsection-bytes
                          Dump raw contents of codeview debug sections and records
  --codeview              Display CodeView debug information
  --coff-basereloc        Display .reloc section
  --coff-debug-directory  Display debug directory
  --coff-directives       Display .drectve section
  --coff-exports          Display export table
  --coff-imports          Display import table
  --coff-load-config      Display load config
  --coff-resources        Display .rsrc section
  --coff-tls-directory    Display TLS directory

OPTIONS (XCOFF specific):
  --auxiliary-header display the auxiliary header

Pass @FILE as argument to read options from FILE.
```

***

**llvm-readobj**

LLVM Object Reader

```
:~# llvm-readobj --help
OVERVIEW: LLVM Object Reader

USAGE: llvm-readobj [options] <input object files>

OPTIONS:
  --addrsig             Display address-significance table
  --all                 Equivalent to setting: --file-header, --program-headers, --section-headers, --symbols, --relocations, --dynamic-table, --notes, --version-info, --unwind, --section-groups and --histogram
  --arch-specific       Display architecture-specific information
  -A                    Alias for --arch-specific
  -a                    Alias for --all
  --bb-addr-map         Display the BB address map section
  --cg-profile          Display call graph profile section
  -C                    Alias for --demangle
  --demangle            Demangle symbol names
  --dependent-libraries Display the dependent libraries section
  --dt                  Alias for --dyn-syms
  --dyn-relocations     Display the dynamic relocation entries in the file
  --dyn-symbols         Alias for --dyn-syms
  --dyn-syms            Display the dynamic symbol table
  --dynamic             Alias for --dynamic-table
  --expand-relocs       Expand each shown relocation to multiple lines
  -e                    Alias for --headers
  --file-header         Display file header
  --headers             Equivalent to setting: --file-header, --program-headers, --section-headers
  --help                Display this help
  --hex-dump=<name or index>
                        Display the specified section(s) as hexadecimal bytes
  -h                    Alias for --file-header
  -l                    Alias for --program-headers
  --no-demangle         Do not demangle symbol names (default)
  -n                    Alias for --notes
  --pretty-print        Pretty print JSON output
  -p <name or index>    Alias for --string-dump
  --relocations         Alias for --relocs
  --relocs              Display the relocation entries in the file
  -r                    Alias for --relocs
  --sd                  Alias for --section-data
  --section-data        Display section data for each section shown. This option has no effect for GNU style output
  --section-details     Display the section details
  --section-headers     Display section headers
  --section-mapping     Display the section to segment mapping
  --section-relocations Display relocations for each section shown. This option has no effect for GNU style output
  --section-symbols     Display symbols for each section shown. This option has no effect for GNU style output
  --sections            Alias for --section-headers
  --sr                  Alias for --section-relocations
  --stack-sizes         Display contents of all stack sizes sections. This option has no effect for GNU style output
  --stackmap            Display contents of stackmap section
  --string-dump=<name or index>
                        Display the specified section(s) as a list of strings
  --string-table        Display the string table (only for XCOFF now)
  --st                  Alias for --section-symbols
  --symbols             Display the symbol table. Also display the dynamic symbol table when using GNU output style for ELF
  --syms                Alias for --symbols
  -S                    Alias for --section-headers
  -s                    Alias for --symbols
  -t                    Alias for --section-details
  --unwind              Display unwind information
  -u                    Alias for --unwind
  --version             Display the version
  --wide                Ignored for GNU readelf compatibility
  -W                    Ignored for GNU readelf compatibility
  -x <name or index>    Alias for --hex-dump

OPTIONS (ELF specific):
  --dynamic-table      Display the dynamic section table
  -d                   Alias for --dynamic-table
  --elf-linker-options Display the .linker-options section
  --elf-output-style=<value>
                       Specify ELF dump style: LLVM, GNU, JSON
  --gnu-hash-table     Display the GNU hash table for dynamic symbols
  -g                   Alias for --section-groups
  --hash-symbols       Display the dynamic symbols derived from the hash section
  --hash-table         Display .hash section
  --histogram          Display bucket list histogram for hash sections
  -I                   Alias for --histogram
  --needed-libs        Display the needed libraries
  --notes              Display notes
  --program-headers    Display program headers
  --raw-relr           Do not decode relocations in SHT_RELR section, display raw contents
  --section-groups     Display section groups
  --segments           Alias for --program-headers
  --version-info       Display version sections
  -V                   Alias for --version-info

OPTIONS (Mach-O specific):
  --macho-data-in-code   Display Data in Code command
  --macho-dysymtab       Display Dysymtab command
  --macho-indirect-symbols
                         Display indirect symbols
  --macho-linker-options Display linker options
  --macho-segment        Display Segment command
  --macho-version-min    Display version min command

OPTIONS (PE/COFF specific):
  --codeview-ghash        Enable global hashing for CodeView type stream de-duplication
  --codeview-merged-types Display the merged CodeView type stream
  --codeview-subsection-bytes
                          Dump raw contents of codeview debug sections and records
  --codeview              Display CodeView debug information
  --coff-basereloc        Display .reloc section
  --coff-debug-directory  Display debug directory
  --coff-directives       Display .drectve section
  --coff-exports          Display export table
  --coff-imports          Display import table
  --coff-load-config      Display load config
  --coff-resources        Display .rsrc section
  --coff-tls-directory    Display TLS directory

OPTIONS (XCOFF specific):
  --auxiliary-header display the auxiliary header

Pass @FILE as argument to read options from FILE.
```

***

**llvm-reduce**

```
:~# llvm-reduce --help
OVERVIEW: LLVM automatic testcase reducer.

USAGE: llvm-reduce [options] <input llvm ll/bc file>

OPTIONS:

Color Options:

  --color                     - Use colors in output (default=autodetect)

Generic Options:

  --help                      - Display available options (--help-hidden for more)
  --help-list                 - Display list of available options (--help-list-hidden for more)
  --version                   - Display the version of this program

llvm-reduce options:

  --in-place                  - WARNING: This option will replace your input file with the reduced version!
  --max-pass-iterations=<int> - Maximum number of times to run the full set of delta passes (default=1)
  --mtriple=<string>          - Set the target triple
  --print-delta-passes        - Print list of delta passes, passable to --delta-passes as a comma separated list
  --test=<string>             - Name of the interesting-ness test to be run
  --test-arg=<string>         - Arguments passed onto the interesting-ness test
  -x=<value>                  - Input language ('ir' or 'mir')
    =ir
    =mir
```

***

**llvm-rtdyld**

Manual page for llvm-rtdyld 14

```
:~# llvm-rtdyld -h
OVERVIEW: llvm MC-JIT tool

USAGE: llvm-rtdyld [options] <input files> --args <program arguments>...

OPTIONS:

Color Options:

  --color               - Use colors in output (default=autodetect)

Generic Options:

  --help                - Display available options (--help-hidden for more)
  --help-list           - Display list of available options (--help-list-hidden for more)
  --version             - Display the version of this program

RTDyld Options:

  --args <string>...    - <program arguments>...
  --check=<string>      - File containing RuntimeDyld verifier checks.
  --dylib=<string>      - Add library.
  --entry=<string>      - Function to call as entry point.
  --mcpu=<cpu-name>     - Target a specific cpu type (-mcpu=help for details)
  --preallocate=<ulong> - Allocate memory upfront rather than on-demand
  --show-times          - Show times for llvm-rtdyld phases
  --triple=<string>     - Target triple for disassembler
  Action to perform:
      --execute            - Load, link, and execute the inputs.
      --printline          - Load, link, and print line information for each function.
      --printdebugline     - Load, link, and print line information for each function using the debug object
      --printobjline       - Like -printlineinfo but does not load the object first
      --verify             - Load, link and verify the resulting memory image.
```

***

**llvm-size**

Manual page for llvm-size 14

```
:~# llvm-size -h
OVERVIEW: LLVM object size dumper

USAGE: llvm-size [options] <input object files>

OPTIONS:
  -A               Alias for --format
  -B               Alias for --format
  --common         Print common symbols in the ELF file. When using Berkeley format, this is added to bss
  -d               Alias for --radix=10
  --format=<value> Specify output format
  --help           Display this help
  -h               Alias for --help
  -m               Alias for --format
  -o               Alias for --radix=8
  --radix=<value>  Print size in radix
  --totals         Print totals of all objects - Berkeley format only
  -t               Alias for --totals
  --version        Display the version
  -x               Alias for --radix=16

OPTIONS (Mach-O specific):
  --arch=<value> architecture(s) from a Mach-O file to dump
  -l             When format is darwin, use long format to include addresses and offsets

Pass @FILE as argument to read options from FILE.
```

***

**llvm-split**

```
:~# llvm-split -h
OVERVIEW: LLVM module splitter

USAGE: llvm-split [options] <input bitcode file>

OPTIONS:

Color Options:

  --color           - Use colors in output (default=autodetect)

Generic Options:

  --help            - Display available options (--help-hidden for more)
  --help-list       - Display list of available options (--help-list-hidden for more)
  --version         - Display the version of this program

Split Options:

  -j=<uint>         - Number of output files
  -o=<filename>     - Override output filename
  --preserve-locals - Split without externalizing locals
```

***

**llvm-stress**

Generate random .ll files

```
:~# llvm-stress -h
OVERVIEW: llvm codegen stress-tester

USAGE: llvm-stress [options]

OPTIONS:

Color Options:

  --color       - Use colors in output (default=autodetect)

Generic Options:

  --help        - Display available options (--help-hidden for more)
  --help-list   - Display list of available options (--help-list-hidden for more)
  --version     - Display the version of this program

Stress Options:

  -o=<filename> - Override output filename
  --seed=<uint> - Seed used for randomness
  --size=<uint> - The estimated size of the generated function (# of instrs)
```

***

**llvm-strings**

Print strings

```
:~# llvm-strings -h
OVERVIEW: llvm string dumper

USAGE: llvm-strings [options] <input object files>

OPTIONS:
  --all             Silently ignored. Present for GNU strings compatibility
  -a                Alias for --all
  --bytes=<value>   Print sequences of the specified length
  -f                Alias for --print-file-name
  --help            Display this help
  -h                Alias for --help
  -n <value>        Alias for --bytes
  --print-file-name Print the name of the file before each string
  --radix=<radix>   Print the offset within the file with the specified radix: o (octal), d (decimal), x (hexadecimal)
  -t <radix>        Alias for --radix
  --version         Display the version

Pass @FILE as argument to read options from FILE.
```

***

**llvm-strip**

Object stripping tool

```
ro:~# llvm-strip -h
OVERVIEW: llvm-strip tool

USAGE: llvm-strip [options] inputs...

OPTIONS:
  --allow-broken-links   Allow the tool to remove sections even if it would leave invalid section references. The appropriate sh_link fields will be set to zero.
  --disable-deterministic-archives
                         Disable deterministic mode when operating on archives (use real values for UIDs, GIDs, and timestamps).
  --discard-all          Remove all local symbols except file and section symbols. Also remove all debug sections
  --discard-locals       Remove compiler-generated local symbols, (e.g. symbols starting with .L)
  -D                     Alias for --enable-deterministic-archives
  -d                     Alias for --strip-debug
  --enable-deterministic-archives
                         Enable deterministic mode when operating on archives (use zero for UIDs, GIDs, and timestamps).
  -g                     Alias for --strip-debug
  --keep-file-symbols    Do not remove file symbols
  --keep-section=section Keep <section>
  --keep-symbol=symbol   Do not remove symbol <symbol>
  --keep-undefined       Do not remove undefined symbols
  -K <value>             Alias for --keep-symbol
  --no-strip-all         Disable --strip-all
  -N <value>             Alias for --strip-symbol
  --only-keep-debug      Produce a debug file as the output that only preserves contents of sections useful for debugging purposes
  -o <file>              Write output to <file>
  --preserve-dates       Preserve access and modification timestamps
  -p                     Alias for --preserve-dates
  --regex                Permit regular expressions in name comparison
  --remove-section=section
                         Remove <section>
  -R <value>             Alias for --remove-section
  --strip-all-gnu        Compatible with GNU's --strip-all
  --strip-all            Remove non-allocated sections outside segments. .gnu.warning* and .ARM.attribute sections are not removed
  --strip-debug          Remove all debug sections
  --strip-sections       Remove all section headers and all sections not in segments
  --strip-symbol=symbol  Strip <symbol>
  --strip-unneeded       Remove all symbols not needed by relocations
  -S                     Alias for --strip-debug
  -s                     Alias for --strip-all
  -T                     Remove Swift symbols
  -U                     Alias for --disable-deterministic-archives
  --version              Print the version and exit.
  -V                     Alias for --version
  --wildcard             Allow wildcard syntax for symbol-related flags. Incompatible with --regex. Allows using '*' to match any number of characters, '?' to match any single character, '' to escape special characters, and '[]' to define character classes. Wildcards beginning with '!' will prevent a match, for example "-N '*' -N '!x'" will strip all symbols except for "x".
  -w                     Alias for --wildcard
  -X                     Alias for --discard-locals
  -x                     Alias for --discard-all

Pass @FILE as argument to read options from FILE.
```

***

**llvm-symbolizer**

Convert addresses into source code locations

```
:~# llvm-symbolizer -h
OVERVIEW: llvm-symbolizer

USAGE: llvm-symbolizer [options] addresses...

OPTIONS:
  --addresses           Show address before line information
  --adjust-vma=<offset> Add specified offset to object file addresses
  -a                    Alias for --addresses
  --basenames           Strip directory names from paths
  -C                    Alias for --demangle
  --debug-file-directory=<dir>
                        Path to directory where to look for debug files
  -demangle=false       Alias for --no-demangle
  -demangle=true        Alias for --demangle
  --demangle            Demangle function names
  --dia                 Use the DIA library to access symbols (Windows only)
  --dwp=<file>          Path to DWP file to be use for any split CUs
  -e=<file>             Alias for --obj
  --exe=<file>          Alias for --obj
  --exe <file>          Alias for --obj
  -e <file>             Alias for --obj
  -f=<value>            Alias for --functions=
  --fallback-debug-path=<dir>
                        Fallback path for debug binaries
  --functions=<value>   Print function name for a given address
  --functions           Print function name for a given address
  -f                    Alias for --functions
  --help                Display this help
  --inlines             Print all inlined frames for a given address
  --inlining=false      Alias for --no-inlines
  --inlining=true       Alias for --inlines
  --inlining            Alias for --inlines
  -i                    Alias for --inlines
  --no-demangle         Don't demangle function names
  --no-inlines          Do not print inlined frames
  --no-untag-addresses  Remove memory tags from addresses before symbolization
  --obj=<file>          Path to object file to be symbolized (if not provided, object file should be specified for each input line)
  --output-style=style  Specify print style. Supported styles: LLVM, GNU, JSON
  --pretty-print        Make the output more human friendly
  --print-address       Alias for --addresses
  --print-source-context-lines=<value>
                        Print N lines of source file context
  -p                    Alias for --pretty-print
  --relative-address    Interpret addresses as addresses relative to the image base
  --relativenames       Strip the compilation directory from paths
  -s                    Alias for --basenames
  --verbose             Print verbose line info
  --version             Display the version
  -v                    Alias for --version

llvm-symbolizer Mach-O Specific Options:
  --default-arch=<value> Default architecture (for multi-arch objects)
  --dsym-hint=<dir>      Path to .dSYM bundles to search for debug info for the object files

Pass @FILE as argument to read options from FILE.
```

***

**llvm-tblgen**

Target Description to C++ Code for LLVM

```
:~# llvm-tblgen -h
USAGE: llvm-tblgen [options] <input file>

OPTIONS:

Color Options:

  --color                            - Use colors in output (default=autodetect)

General options:

  -D=<macro name>                    - Name of the macro to be defined
  -I=<directory>                     - Directory of include files
  -d=<filename>                      - Dependency filename
  Action to perform:
      --print-records                   - Print all records to stdout (default)
      --print-detailed-records          - Print full details of all records to stdout
      --null-backend                    - Do nothing after parsing (useful for timing)
      --dump-json                       - Dump all records as machine-readable JSON
      --gen-emitter                     - Generate machine code emitter
      --gen-code-beads                  - Generate machine code beads
      --gen-register-info               - Generate registers and register classes info
      --gen-instr-info                  - Generate instruction descriptions
      --gen-instr-docs                  - Generate instruction documentation
      --gen-callingconv                 - Generate calling convention descriptions
      --gen-asm-writer                  - Generate assembly writer
      --gen-disassembler                - Generate disassembler
      --gen-pseudo-lowering             - Generate pseudo instruction lowering
      --gen-compress-inst-emitter       - Generate RISCV compressed instructions.
      --gen-asm-matcher                 - Generate assembly instruction matcher
      --gen-dag-isel                    - Generate a DAG instruction selector
      --gen-dfa-packetizer              - Generate DFA Packetizer for VLIW targets
      --gen-fast-isel                   - Generate a "fast" instruction selector
      --gen-subtarget                   - Generate subtarget enumerations
      --gen-intrinsic-enums             - Generate intrinsic enums
      --gen-intrinsic-impl              - Generate intrinsic information
      --print-enums                     - Print enum values for a class
      --print-sets                      - Print expanded sets for testing DAG exprs
      --gen-opt-parser-defs             - Generate option definitions
      --gen-opt-rst                     - Generate option RST
      --gen-ctags                       - Generate ctags-compatible index
      --gen-attrs                       - Generate attributes
      --gen-searchable-tables           - Generate generic binary-searchable table
      --gen-global-isel                 - Generate GlobalISel selector
      --gen-global-isel-combiner        - Generate GlobalISel combiner
      --gen-x86-EVEX2VEX-tables         - Generate X86 EVEX to VEX compress tables
      --gen-x86-fold-tables             - Generate X86 fold tables
      --gen-register-bank               - Generate registers bank descriptions
      --gen-exegesis                    - Generate llvm-exegesis tables
      --gen-automata                    - Generate generic automata
      --gen-directive-decl              - Generate directive related declaration code (header file)
      --gen-directive-impl              - Generate directive related implementation code
  --no-warn-on-unused-template-args  - Disable unused template argument warnings.
  -o=<filename>                      - Output filename
  --time-phases                      - Time phases of parser and backend
  --write-if-changed                 - Only write output if it changed

Generic Options:

  --help                             - Display available options (--help-hidden for more)
  --help-list                        - Display list of available options (--help-list-hidden for more)
  --version                          - Display the version of this program

Options for -gen-asm-matcher:

  --match-prefix=<string>            - Only match instructions with the given prefix

Options for -gen-asm-parser:

  --asmparsernum=<uint>              - Make -gen-asm-parser emit assembly parser #N

Options for -gen-asm-writer:

  --asmwriternum=<uint>              - Make -gen-asm-writer emit assembly writer #N

Options for -gen-dag-isel:

  --instrument-coverage              - Generates tables to help identify patterns matched
  --omit-comments                    - Do not generate comments

Options for -gen-global-isel:

  --gisel-coverage-file=<string>     - Specify file to retrieve coverage information from
  --instrument-gisel-coverage        - Generate coverage instrumentation for GlobalISel
  --optimize-match-table             - Generate an optimized version of the match table
  --warn-on-skipped-patterns         - Explain why a pattern was skipped for inclusion in the GlobalISel selector

Options for -gen-global-isel-combiner:

  --combiners=<string>               - Emit the specified combiners
  --gicombiner-show-expansions       - Use C++ comments to indicate occurence of code expansion
  --gicombiner-stop-after-build      - Stop processing after building the match tree
  --gicombiner-stop-after-parse      - Stop processing after parsing rules and dump state

Options for -gen-intrinsic-enums:

  --intrinsic-prefix=<target prefix> - Generate intrinsics with this target prefix

Options for -gen-register-info:

  --register-info-debug              - Dump register information to help debugging

Options for -print-enums:

  --class=<class name>               - Print Enum list for this class
```

***

**llvm-undname**

```
:~# llvm-undname -h
OVERVIEW: llvm-undname

USAGE: llvm-undname [options] <input symbols>

OPTIONS:

Color Options:

  --color     - Use colors in output (default=autodetect)

Generic Options:

  --help      - Display available options (--help-hidden for more)
  --help-list - Display list of available options (--help-list-hidden for more)
  --version   - Display the version of this program
```

***

**llvm-xray**

```
:~# llvm-xray -h
OVERVIEW: XRay Tools

  This program consolidates multiple XRay trace processing tools for convenient access.

USAGE: llvm-xray [subcommand] [options]

SUBCOMMANDS:

  account    - Function call accounting
  convert    - Trace Format Conversion
  extract    - Extract instrumentation maps
  fdr-dump   - FDR Trace Dump
  graph      - Generate function-call graph
  graph-diff - Generate diff of function-call graphs
  stack      - Call stack accounting

  Type "llvm-xray <subcommand> --help" to get more help on a specific subcommand

OPTIONS:

Color Options:

  --color                                            - Use colors in output (default=autodetect)

General options:

  --aarch64-neon-syntax=<value>                      - Choose style of NEON code to emit from AArch64 backend:
    =generic                                         -   Emit generic NEON assembly
    =apple                                           -   Emit Apple-style NEON assembly
  --aarch64-use-aa                                   - Enable the use of AA during codegen.
  --abort-on-max-devirt-iterations-reached           - Abort when the max iterations for devirtualization CGSCC repeat pass is reached
  --allow-ginsert-as-artifact                        - Allow G_INSERT to be considered an artifact. Hack around AMDGPU test infinite loops.
  --amdgpu-bypass-slow-div                           - Skip 64-bit divide for dynamic 32-bit values
  --amdgpu-disable-loop-alignment                    - Do not align and prefetch loops
  --amdgpu-disable-power-sched                       - Disable scheduling to minimize mAI power bursts
  --amdgpu-dpp-combine                               - Enable DPP combiner
  --amdgpu-dump-hsa-metadata                         - Dump AMDGPU HSA Metadata
  --amdgpu-enable-flat-scratch                       - Use flat scratch instructions
  --amdgpu-enable-merge-m0                           - Merge and hoist M0 initializations
  --amdgpu-promote-alloca-to-vector-limit=<uint>     - Maximum byte size to consider promote alloca to vector
  --amdgpu-sdwa-peephole                             - Enable SDWA peepholer
  --amdgpu-use-aa-in-codegen                         - Enable the use of AA during codegen.
  --amdgpu-verify-hsa-metadata                       - Verify AMDGPU HSA Metadata
  --amdgpu-vgpr-index-mode                           - Use GPR indexing mode instead of movrel for vector indexing
  --arm-add-build-attributes                         - 
  --arm-implicit-it=<value>                          - Allow conditional instructions outdside of an IT block
    =always                                          -   Accept in both ISAs, emit implicit ITs in Thumb
    =never                                           -   Warn in ARM, reject in Thumb
    =arm                                             -   Accept in ARM, reject in Thumb
    =thumb                                           -   Warn in ARM, emit implicit ITs in Thumb
  --asm-show-inst                                    - Emit internal instruction representation to assembly file
  --atomic-counter-update-promoted                   - Do counter update using atomic fetch add  for promoted counters only
  --atomic-first-counter                             - Use atomic fetch add for first counter in a function (usually the entry counter)
  --bounds-checking-single-trap                      - Use one trap block per function
  --cfg-hide-cold-paths=<number>                     - Hide blocks with relative frequency below the given value
  --cfg-hide-deoptimize-paths                        - 
  --cfg-hide-unreachable-paths                       - 
  --cost-kind=<value>                                - Target cost kind
    =throughput                                      -   Reciprocal throughput
    =latency                                         -   Instruction latency
    =code-size                                       -   Code size
    =size-latency                                    -   Code size and latency
  --debug-info-correlate                             - Use debug info to correlate profiles.
  --debugify-level=<value>                           - Kind of debug info to add
    =locations                                       -   Locations only
    =location+variables                              -   Locations and Variables
  --debugify-quiet                                   - Suppress verbose debugify output
  --disable-i2p-p2i-opt                              - Disables inttoptr/ptrtoint roundtrip optimization
  --disable-promote-alloca-to-lds                    - Disable promote alloca to LDS
  --disable-promote-alloca-to-vector                 - Disable promote alloca to vector
  --do-counter-promotion                             - Do counter register promotion
  --dot-cfg-mssa=<file name for generated dot file>  - file name for generated dot file
  --dwarf-version=<int>                              - Dwarf version
  --dwarf64                                          - Generate debugging info in the 64-bit DWARF format
  --emscripten-cxx-exceptions-allowed=<string>       - The list of function names in which Emscripten-style exception handling is enabled (see emscripten EMSCRIPTEN_CATCHING_ALLOWED options)
  --enable-cse-in-irtranslator                       - Should enable CSE in irtranslator
  --enable-cse-in-legalizer                          - Should enable CSE in Legalizer
  --enable-emscripten-cxx-exceptions                 - WebAssembly Emscripten-style exception handling
  --enable-emscripten-sjlj                           - WebAssembly Emscripten-style setjmp/longjmp handling
  --enable-gvn-hoist                                 - Enable the GVN hoisting pass (default = off)
  --enable-gvn-memdep                                - 
  --enable-gvn-sink                                  - Enable the GVN sinking pass (default = off)
  --enable-load-in-loop-pre                          - 
  --enable-load-pre                                  - 
  --enable-loop-simplifycfg-term-folding             - 
  --enable-name-compression                          - Enable name/filename string compression
  --enable-split-backedge-in-load-pre                - 
  --experimental-debug-variable-locations            - Use experimental new value-tracking variable locations
  --fatal-warnings                                   - Treat warnings as errors
  --fs-profile-debug-bw-threshold=<uint>             - Only show debug message if the source branch weight is greater  than this value.
  --fs-profile-debug-prob-diff-threshold=<uint>      - Only show debug message if the branch probility is greater than this value (in percentage).
  --generate-merged-base-profiles                    - When generating nested context-sensitive profiles, always generate extra base profile for function with all its context profiles merged into it.
  --gpsize=<uint>                                    - Global Pointer Addressing Size.  The default size is 8.
  --hash-based-counter-split                         - Rename counter variable of a comdat function based on cfg hash
  --hot-cold-split                                   - Enable hot-cold splitting pass
  --import-all-index                                 - Import all external functions in index.
  --incremental-linker-compatible                    - When used with filetype=obj, emit an object file which can be used with an incremental linker
  --instcombine-code-sinking                         - Enable code sinking
  --instcombine-guard-widening-window=<uint>         - How wide an instruction window to bypass looking for another guard
  --instcombine-max-iterations=<uint>                - Limit the maximum number of instruction combining iterations
  --instcombine-max-num-phis=<uint>                  - Maximum number phis to handle in intptr/ptrint folding
  --instcombine-maxarray-size=<uint>                 - Maximum array size considered when doing a combine
  --instcombine-negator-enabled                      - Should we attempt to sink negations?
  --instcombine-negator-max-depth=<uint>             - What is the maximal lookup depth when trying to check for viability of negation sinking.
  --instrprof-atomic-counter-update-all              - Make all profile counter updates atomic (for testing only)
  --internalize-public-api-file=<filename>           - A file containing list of symbol names to preserve
  --internalize-public-api-list=<list>               - A list of symbol names to preserve
  --iterative-counter-promotion                      - Allow counter promotion across the whole loop nest.
  --lto-embed-bitcode=<value>                        - Embed LLVM bitcode in object files produced by LTO
    =none                                            -   Do not embed
    =optimized                                       -   Embed after all optimization passes
    =post-merge-pre-opt                              -   Embed post merge, but before optimizations
  --lto-pass-remarks-filter=<regex>                  - Only record optimization remarks from passes whose names match the given regular expression
  --lto-pass-remarks-format=<format>                 - The format used for serializing remarks (default: YAML)
  --lto-pass-remarks-output=<filename>               - Output filename for pass remarks
  --matrix-default-layout=<value>                    - Sets the default matrix layout
    =column-major                                    -   Use column-major layout
    =row-major                                       -   Use row-major layout
  --max-counter-promotions=<int>                     - Max number of allowed counter promotions
  --max-counter-promotions-per-loop=<uint>           - Max number counter promotions per loop to avoid increasing register pressure too much
  --mc-relax-all                                     - When used with filetype=obj, relax all fixups in the emitted object file
  --mcabac                                           - tbd
  --merror-missing-parenthesis                       - Error for missing parenthesis around predicate registers
  --merror-noncontigious-register                    - Error for register names that aren't contigious
  --mhvx                                             - Enable Hexagon Vector eXtensions
  --mhvx=<value>                                     - Enable Hexagon Vector eXtensions
    =v60                                             -   Build for HVX v60
    =v62                                             -   Build for HVX v62
    =v65                                             -   Build for HVX v65
    =v66                                             -   Build for HVX v66
    =v67                                             -   Build for HVX v67
    =v68                                             -   Build for HVX v68
    =v69                                             -   Build for HVX v69
  --mips-compact-branches=<value>                    - MIPS Specific: Compact branch policy.
    =never                                           -   Do not use compact branches if possible.
    =optimal                                         -   Use compact branches where appropriate (default).
    =always                                          -   Always use compact branches if possible.
  --mips16-constant-islands                          - Enable mips16 constant islands.
  --mips16-hard-float                                - Enable mips16 hard float.
  --mir-strip-debugify-only                          - Should mir-strip-debug only strip debug info from debugified modules by default
  --mno-compound                                     - Disable looking for compound instructions for Hexagon
  --mno-fixup                                        - Disable fixing up resolved relocations for Hexagon
  --mno-ldc1-sdc1                                    - Expand double precision loads and stores to their single precision counterparts
  --mno-pairing                                      - Disable looking for duplex instructions for Hexagon
  --mwarn-missing-parenthesis                        - Warn for missing parenthesis around predicate registers
  --mwarn-noncontigious-register                     - Warn for register names that arent contigious
  --mwarn-sign-mismatch                              - Warn for mismatching a signed and unsigned value
  --no-deprecated-warn                               - Suppress all deprecated warnings
  --no-discriminators                                - Disable generation of discriminator information.
  --no-type-check                                    - Suppress type errors (Wasm)
  --no-warn                                          - Suppress all warnings
  --nvptx-sched4reg                                  - NVPTX Specific: schedule for register pressue
  --opaque-pointers                                  - Use opaque pointers
  --poison-checking-function-local                   - Check that returns are non-poison (for testing)
  --print-pipeline-passes                            - Print a '-passes' compatible string describing the pipeline (best-effort only).
  --r600-ir-structurize                              - Use StructurizeCFG IR pass
  --rdf-dump                                         - 
  --rdf-limit=<uint>                                 - 
  --runtime-counter-relocation                       - Enable relocating counters at runtime.
  --safepoint-ir-verifier-print-only                 - 
  --sample-profile-check-record-coverage=<N>         - Emit a warning if less than N% of records in the input profile are matched to the IR.
  --sample-profile-check-sample-coverage=<N>         - Emit a warning if less than N% of samples in the input profile are matched to the IR.
  --sample-profile-max-propagate-iterations=<uint>   - Maximum number of iterations to go through when propagating sample block/edge weights through the CFG.
  --skip-ret-exit-block                              - Suppress counter promotion if exit blocks contain ret.
  --speculative-counter-promotion-max-exiting=<uint> - The max number of exiting blocks of a loop to allow  speculative counter promotion
  --speculative-counter-promotion-to-loop            - When the option is false, if the target block is in a loop, the promotion will be disallowed unless the promoted counter  update can be further/iteratively promoted into an acyclic  region.
  --summary-file=<string>                            - The summary file to use for function importing.
  --tail-predication=<value>                         - MVE tail-predication pass options
    =disabled                                        -   Don't tail-predicate loops
    =enabled-no-reductions                           -   Enable tail-predication, but not for reduction loops
    =enabled                                         -   Enable tail-predication, including reduction loops
    =force-enabled-no-reductions                     -   Enable tail-predication, but not for reduction loops, and force this which might be unsafe
    =force-enabled                                   -   Enable tail-predication, including reduction loops, and force this which might be unsafe
  --thinlto-assume-merged                            - Assume the input has already undergone ThinLTO function importing and the other pre-optimization pipeline changes.
  --threads=<int>                                    - 
  --verify-region-info                               - Verify region info (time consuming)
  --vp-counters-per-site=<number>                    - The average number of profile counters allocated per value profiling site.
  --vp-static-alloc                                  - Do static counter allocation for value profiler
  --wasm-enable-eh                                   - WebAssembly exception handling
  --wasm-enable-sjlj                                 - WebAssembly setjmp/longjmp handling
  --x86-align-branch=<string>                        - Specify types of branches to align (plus separated list of types):
                                                       jcc      indicates conditional jumps
                                                       fused    indicates fused conditional jumps
                                                       jmp      indicates direct unconditional jumps
                                                       call     indicates direct and indirect calls
                                                       ret      indicates rets
                                                       indirect indicates indirect unconditional jumps
  --x86-align-branch-boundary=<uint>                 - Control how the assembler should align branches with NOP. If the boundary's size is not 0, it should be a power of 2 and no less than 32. Branches will be aligned to prevent from being across or against the boundary of specified size. The default value 0 does not align branches.
  --x86-branches-within-32B-boundaries               - Align selected instructions to mitigate negative performance impact of Intel's micro code update for errata skx102.  May break assumptions about labels corresponding to particular instructions, and should be used with caution.
  --x86-pad-max-prefix-size=<uint>                   - Maximum number of prefixes to use for padding

Generic Options:

  --help                                             - Display available options (--help-hidden for more)
  --help-list                                        - Display list of available options (--help-list-hidden for more)
  --version                                          - Display the version of this program

Polly Options:
Configure the polly loop optimizer

  --polly                                            - Enable the polly optimizer (with -O1, -O2 or -O3)
  --polly-2nd-level-tiling                           - Enable a 2nd level loop of loop tiling
  --polly-ast-print-accesses                         - Print memory access functions
  --polly-context=<isl parameter set>                - Provide additional constraints on the context parameters
  --polly-dce-precise-steps=<int>                    - The number of precise steps between two approximating iterations. (A value of -1 schedules another approximation stage before the actual dead code elimination.
  --polly-delicm-max-ops=<int>                       - Maximum number of isl operations to invest for lifetime analysis; 0=no limit
  --polly-detect-full-functions                      - Allow the detection of full functions
  --polly-dump-after                                 - Dump module after Polly transformations into a file suffixed with "-after"
  --polly-dump-after-file=<string>                   - Dump module after Polly transformations to the given file
  --polly-dump-before                                - Dump module before Polly transformations into a file suffixed with "-before"
  --polly-dump-before-file=<string>                  - Dump module before Polly transformations to the given file
  --polly-enable-simplify                            - Simplify SCoP after optimizations
  --polly-ignore-func=<string>                       - Ignore functions that match a regex. Multiple regexes can be comma separated. Scop detection will ignore all functions that match ANY of the regexes provided.
  --polly-isl-arg=<argument>                         - Option passed to ISL
  --polly-on-isl-error-abort                         - Abort if an isl error is encountered
  --polly-only-func=<string>                         - Only run on functions that match a regex. Multiple regexes can be comma separated. Scop detection will run on all functions that match ANY of the regexes provided.
  --polly-only-region=<identifier>                   - Only run on certain regions (The provided identifier must appear in the name of the region's entry block
  --polly-only-scop-detection                        - Only run scop detection, but no other optimizations
  --polly-optimized-scops                            - Polly - Dump polyhedral description of Scops optimized with the isl scheduling optimizer and the set of post-scheduling transformations is applied on the schedule tree
  --polly-parallel                                   - Generate thread parallel code (isl codegen only)
  --polly-parallel-force                             - Force generation of thread parallel code ignoring any cost model
  --polly-pattern-matching-based-opts                - Perform optimizations based on pattern matching
  --polly-postopts                                   - Apply post-rescheduling optimizations such as tiling (requires -polly-reschedule)
  --polly-pragma-based-opts                          - Apply user-directed transformation from metadata
  --polly-pragma-ignore-depcheck                     - Skip the dependency check for pragma-based transformations
  --polly-process-unprofitable                       - Process scops that are unlikely to benefit from Polly optimizations.
  --polly-register-tiling                            - Enable register tiling
  --polly-report                                     - Print information about the activities of Polly
  --polly-reschedule                                 - Optimize SCoPs using ISL
  --polly-show                                       - Highlight the code regions that will be optimized in a (CFG BBs and LLVM-IR instructions)
  --polly-show-only                                  - Highlight the code regions that will be optimized in a (CFG only BBs)
  --polly-stmt-granularity=<value>                   - Algorithm to use for splitting basic blocks into multiple statements
    =bb                                              -   One statement per basic block
    =scalar-indep                                    -   Scalar independence heuristic
    =store                                           -   Store-level granularity
  --polly-target=<value>                             - The hardware to target
    =cpu                                             -   generate CPU code
  --polly-tiling                                     - Enable loop tiling
  --polly-vectorizer=<value>                         - Select the vectorization strategy
    =none                                            -   No Vectorization
    =polly                                           -   Polly internal vectorizer
    =stripmine                                       -   Strip-mine outer loops for the loop-vectorizer to trigger
```

***

**obj2yaml**

```
:~# obj2yaml -h
USAGE: obj2yaml [options] <input file>

OPTIONS:

Color Options:

  --color               - Use colors in output (default=autodetect)

General options:

  --disable-i2p-p2i-opt - Disables inttoptr/ptrtoint roundtrip optimization
  --opaque-pointers     - Use opaque pointers
  --raw-segment=<value> - Mach-O: dump the raw contents of the listed segments instead of parsing them:
    =data               -   __DATA
    =linkedit           -   __LINKEDIT

Generic Options:

  --help                - Display available options (--help-hidden for more)
  --help-list           - Display list of available options (--help-list-hidden for more)
  --version             - Display the version of this program
```

***

**opt**

LLVM optimizer

```
:~# opt -h
OVERVIEW: llvm .bc -> .bc modular optimizer and analysis printer

USAGE: opt [options] <input bitcode file>

OPTIONS:

Color Options:

  --color                                                               - Use colors in output (default=autodetect)

General options:

  --O0                                                                  - Optimization level 0. Similar to clang -O0. Use -passes='default<O0>' for the new PM
  --O1                                                                  - Optimization level 1. Similar to clang -O1. Use -passes='default<O1>' for the new PM
  --O2                                                                  - Optimization level 2. Similar to clang -O2. Use -passes='default<O2>' for the new PM
  --O3                                                                  - Optimization level 3. Similar to clang -O3. Use -passes='default<O3>' for the new PM
  --Os                                                                  - Like -O2 but size-conscious. Similar to clang -Os. Use -passes='default<Os>' for the new PM
  --Oz                                                                  - Like -O2 but optimize for code size above all else. Similar to clang -Oz. Use -passes='default<Oz>' for the new PM
  -S                                                                    - Write output as LLVM assembly
  --aarch64-neon-syntax=<value>                                         - Choose style of NEON code to emit from AArch64 backend:
    =generic                                                            -   Emit generic NEON assembly
    =apple                                                              -   Emit Apple-style NEON assembly
  --aarch64-use-aa                                                      - Enable the use of AA during codegen.
  --abort-on-max-devirt-iterations-reached                              - Abort when the max iterations for devirtualization CGSCC repeat pass is reached
  --addrsig                                                             - Emit an address-significance table
  --align-loops=<uint>                                                  - Default alignment for loops
  --allow-ginsert-as-artifact                                           - Allow G_INSERT to be considered an artifact. Hack around AMDGPU test infinite loops.
  --amdgpu-bypass-slow-div                                              - Skip 64-bit divide for dynamic 32-bit values
  --amdgpu-disable-loop-alignment                                       - Do not align and prefetch loops
  --amdgpu-disable-power-sched                                          - Disable scheduling to minimize mAI power bursts
  --amdgpu-dpp-combine                                                  - Enable DPP combiner
  --amdgpu-dump-hsa-metadata                                            - Dump AMDGPU HSA Metadata
  --amdgpu-enable-flat-scratch                                          - Use flat scratch instructions
  --amdgpu-enable-merge-m0                                              - Merge and hoist M0 initializations
  --amdgpu-promote-alloca-to-vector-limit=<uint>                        - Maximum byte size to consider promote alloca to vector
  --amdgpu-sdwa-peephole                                                - Enable SDWA peepholer
  --amdgpu-use-aa-in-codegen                                            - Enable the use of AA during codegen.
  --amdgpu-verify-hsa-metadata                                          - Verify AMDGPU HSA Metadata
  --amdgpu-vgpr-index-mode                                              - Use GPR indexing mode instead of movrel for vector indexing
  --analyze                                                             - Only perform analysis, no optimization. Legacy pass manager only.
  --arm-add-build-attributes                                            - 
  --arm-implicit-it=<value>                                             - Allow conditional instructions outdside of an IT block
    =always                                                             -   Accept in both ISAs, emit implicit ITs in Thumb
    =never                                                              -   Warn in ARM, reject in Thumb
    =arm                                                                -   Accept in ARM, reject in Thumb
    =thumb                                                              -   Warn in ARM, emit implicit ITs in Thumb
  --asm-show-inst                                                       - Emit internal instruction representation to assembly file
  --atomic-counter-update-promoted                                      - Do counter update using atomic fetch add  for promoted counters only
  --atomic-first-counter                                                - Use atomic fetch add for first counter in a function (usually the entry counter)
  --basic-block-sections=<all | <function list (file)> | labels | none> - Emit basic blocks into separate sections
  --bounds-checking-single-trap                                         - Use one trap block per function
  --cfg-hide-cold-paths=<number>                                        - Hide blocks with relative frequency below the given value
  --cfg-hide-deoptimize-paths                                           - 
  --cfg-hide-unreachable-paths                                          - 
  --code-model=<value>                                                  - Choose code model
    =tiny                                                               -   Tiny code model
    =small                                                              -   Small code model
    =kernel                                                             -   Kernel code model
    =medium                                                             -   Medium code model
    =large                                                              -   Large code model
  --codegen-opt-level=<uint>                                            - Override optimization level for codegen hooks, legacy PM only
  --cost-kind=<value>                                                   - Target cost kind
    =throughput                                                         -   Reciprocal throughput
    =latency                                                            -   Instruction latency
    =code-size                                                          -   Code size
    =size-latency                                                       -   Code size and latency
  --data-layout=<layout-string>                                         - data layout string to use
  --data-sections                                                       - Emit data into separate sections
  --debug-entry-values                                                  - Enable debug info for the debug entry values.
  --debug-info-correlate                                                - Use debug info to correlate profiles.
  --debugger-tune=<value>                                               - Tune debug info for a particular debugger
    =gdb                                                                -   gdb
    =lldb                                                               -   lldb
    =dbx                                                                -   dbx
    =sce                                                                -   SCE targets (e.g. PS4)
  --debugify-each                                                       - Start each pass with debugify and end it with check-debugify
  --debugify-export=<filename>                                          - Export per-pass debugify statistics to this file
  --debugify-level=<value>                                              - Kind of debug info to add
    =locations                                                          -   Locations only
    =location+variables                                                 -   Locations and Variables
  --debugify-quiet                                                      - Suppress verbose debugify output
  --denormal-fp-math=<value>                                            - Select which denormal numbers the code is permitted to require
    =ieee                                                               -   IEEE 754 denormal numbers
    =preserve-sign                                                      -   the sign of a  flushed-to-zero number is preserved in the sign of 0
    =positive-zero                                                      -   denormals are flushed to positive zero
  --denormal-fp-math-f32=<value>                                        - Select which denormal numbers the code is permitted to require for float
    =ieee                                                               -   IEEE 754 denormal numbers
    =preserve-sign                                                      -   the sign of a  flushed-to-zero number is preserved in the sign of 0
    =positive-zero                                                      -   denormals are flushed to positive zero
  --disable-builtin=<string>                                            - Disable specific target library builtin function
  --disable-debug-info-type-map                                         - Don't use a uniquing type map for debug info
  --disable-i2p-p2i-opt                                                 - Disables inttoptr/ptrtoint roundtrip optimization
  --disable-loop-unrolling                                              - Disable loop unrolling in all relevant passes
  --disable-promote-alloca-to-lds                                       - Disable promote alloca to LDS
  --disable-promote-alloca-to-vector                                    - Disable promote alloca to vector
  --disable-simplify-libcalls                                           - Disable simplify-libcalls
  --disable-tail-calls                                                  - Never emit tail calls
  --do-counter-promotion                                                - Do counter register promotion
  --dot-cfg-mssa=<file name for generated dot file>                     - file name for generated dot file
  --dwarf-version=<int>                                                 - Dwarf version
  --dwarf64                                                             - Generate debugging info in the 64-bit DWARF format
  --emit-call-site-info                                                 - Emit call site debug information, if debug information is enabled.
  --emscripten-cxx-exceptions-allowed=<string>                          - The list of function names in which Emscripten-style exception handling is enabled (see emscripten EMSCRIPTEN_CATCHING_ALLOWED options)
  --emulated-tls                                                        - Use emulated TLS model
  --enable-cse-in-irtranslator                                          - Should enable CSE in irtranslator
  --enable-cse-in-legalizer                                             - Should enable CSE in Legalizer
  --enable-debugify                                                     - Start the pipeline with debugify and end it with check-debugify
  --enable-emscripten-cxx-exceptions                                    - WebAssembly Emscripten-style exception handling
  --enable-emscripten-sjlj                                              - WebAssembly Emscripten-style setjmp/longjmp handling
  --enable-gvn-hoist                                                    - Enable the GVN hoisting pass (default = off)
  --enable-gvn-memdep                                                   - 
  --enable-gvn-sink                                                     - Enable the GVN sinking pass (default = off)
  --enable-load-in-loop-pre                                             - 
  --enable-load-pre                                                     - 
  --enable-loop-simplifycfg-term-folding                                - 
  --enable-name-compression                                             - Enable name/filename string compression
  --enable-new-pm                                                       - Enable the new pass manager, translating 'opt -foo' to 'opt -passes=foo'. This is strictly for the new PM migration, use '-passes=' when possible.
  --enable-no-infs-fp-math                                              - Enable FP math optimizations that assume no +-Infs
  --enable-no-nans-fp-math                                              - Enable FP math optimizations that assume no NaNs
  --enable-no-signed-zeros-fp-math                                      - Enable FP math optimizations that assume the sign of 0 is insignificant
  --enable-no-trapping-fp-math                                          - Enable setting the FP exceptions build attribute not to use exceptions
  --enable-split-backedge-in-load-pre                                   - 
  --enable-unsafe-fp-math                                               - Enable optimizations that may decrease FP precision
  --exception-model=<value>                                             - exception model
    =default                                                            -   default exception handling model
    =dwarf                                                              -   DWARF-like CFI based exception handling
    =sjlj                                                               -   SjLj exception handling
    =arm                                                                -   ARM EHABI exceptions
    =wineh                                                              -   Windows exception model
    =wasm                                                               -   WebAssembly exception handling
  --experimental-debug-variable-locations                               - Use experimental new value-tracking variable locations
  -f                                                                    - Enable binary output on terminals
  --fatal-warnings                                                      - Treat warnings as errors
  --filetype=<value>                                                    - Choose a file type (not all types are supported by all targets):
    =asm                                                                -   Emit an assembly ('.s') file
    =obj                                                                -   Emit a native object ('.o') file
    =null                                                               -   Emit nothing, for performance testing
  --float-abi=<value>                                                   - Choose float ABI type
    =default                                                            -   Target default float ABI type
    =soft                                                               -   Soft float ABI (implied by -soft-float)
    =hard                                                               -   Hard float ABI (uses FP registers)
  --force-dwarf-frame-section                                           - Always emit a debug frame section.
  --fp-contract=<value>                                                 - Enable aggressive formation of fused FP ops
    =fast                                                               -   Fuse FP ops whenever profitable
    =on                                                                 -   Only fuse 'blessed' FP ops.
    =off                                                                -   Only fuse FP ops when the result won't be affected.
  --frame-pointer=<value>                                               - Specify frame pointer elimination optimization
    =all                                                                -   Disable frame pointer elimination
    =non-leaf                                                           -   Disable frame pointer elimination for non-leaf frame
    =none                                                               -   Enable frame pointer elimination
  --fs-profile-debug-bw-threshold=<uint>                                - Only show debug message if the source branch weight is greater  than this value.
  --fs-profile-debug-prob-diff-threshold=<uint>                         - Only show debug message if the branch probility is greater than this value (in percentage).
  --function-sections                                                   - Emit functions into separate sections
  --generate-merged-base-profiles                                       - When generating nested context-sensitive profiles, always generate extra base profile for function with all its context profiles merged into it.
  --gpsize=<uint>                                                       - Global Pointer Addressing Size.  The default size is 8.
  --hash-based-counter-split                                            - Rename counter variable of a comdat function based on cfg hash
  --hot-cold-split                                                      - Enable hot-cold splitting pass
  --ignore-xcoff-visibility                                             - Not emit the visibility attribute for asm in AIX OS or give all symbols 'unspecified' visibility in XCOFF object file
  --import-all-index                                                    - Import all external functions in index.
  --incremental-linker-compatible                                       - When used with filetype=obj, emit an object file which can be used with an incremental linker
  --instcombine-code-sinking                                            - Enable code sinking
  --instcombine-guard-widening-window=<uint>                            - How wide an instruction window to bypass looking for another guard
  --instcombine-max-iterations=<uint>                                   - Limit the maximum number of instruction combining iterations
  --instcombine-max-num-phis=<uint>                                     - Maximum number phis to handle in intptr/ptrint folding
  --instcombine-maxarray-size=<uint>                                    - Maximum array size considered when doing a combine
  --instcombine-negator-enabled                                         - Should we attempt to sink negations?
  --instcombine-negator-max-depth=<uint>                                - What is the maximal lookup depth when trying to check for viability of negation sinking.
  --instrprof-atomic-counter-update-all                                 - Make all profile counter updates atomic (for testing only)
  --internalize-public-api-file=<filename>                              - A file containing list of symbol names to preserve
  --internalize-public-api-list=<list>                                  - A list of symbol names to preserve
  --iterative-counter-promotion                                         - Allow counter promotion across the whole loop nest.
  --load=<pluginfilename>                                               - Load the specified plugin
  --load-pass-plugin=<string>                                           - Load passes from plugin library
  --lto-embed-bitcode=<value>                                           - Embed LLVM bitcode in object files produced by LTO
    =none                                                               -   Do not embed
    =optimized                                                          -   Embed after all optimization passes
    =post-merge-pre-opt                                                 -   Embed post merge, but before optimizations
  --lto-pass-remarks-filter=<regex>                                     - Only record optimization remarks from passes whose names match the given regular expression
  --lto-pass-remarks-format=<format>                                    - The format used for serializing remarks (default: YAML)
  --lto-pass-remarks-output=<filename>                                  - Output filename for pass remarks
  --march=<string>                                                      - Architecture to generate code for (see --version)
  --matrix-default-layout=<value>                                       - Sets the default matrix layout
    =column-major                                                       -   Use column-major layout
    =row-major                                                          -   Use row-major layout
  --mattr=<a1,+a2,-a3,...>                                              - Target specific attributes (-mattr=help for details)
  --max-counter-promotions=<int>                                        - Max number of allowed counter promotions
  --max-counter-promotions-per-loop=<uint>                              - Max number counter promotions per loop to avoid increasing register pressure too much
  --mc-relax-all                                                        - When used with filetype=obj, relax all fixups in the emitted object file
  --mcabac                                                              - tbd
  --mcpu=<cpu-name>                                                     - Target a specific cpu type (-mcpu=help for details)
  --meabi=<value>                                                       - Set EABI type (default depends on triple):
    =default                                                            -   Triple default EABI version
    =4                                                                  -   EABI version 4
    =5                                                                  -   EABI version 5
    =gnu                                                                -   EABI GNU
  --merror-missing-parenthesis                                          - Error for missing parenthesis around predicate registers
  --merror-noncontigious-register                                       - Error for register names that aren't contigious
  --mhvx                                                                - Enable Hexagon Vector eXtensions
  --mhvx=<value>                                                        - Enable Hexagon Vector eXtensions
    =v60                                                                -   Build for HVX v60
    =v62                                                                -   Build for HVX v62
    =v65                                                                -   Build for HVX v65
    =v66                                                                -   Build for HVX v66
    =v67                                                                -   Build for HVX v67
    =v68                                                                -   Build for HVX v68
    =v69                                                                -   Build for HVX v69
  --mips-compact-branches=<value>                                       - MIPS Specific: Compact branch policy.
    =never                                                              -   Do not use compact branches if possible.
    =optimal                                                            -   Use compact branches where appropriate (default).
    =always                                                             -   Always use compact branches if possible.
  --mips16-constant-islands                                             - Enable mips16 constant islands.
  --mips16-hard-float                                                   - Enable mips16 hard float.
  --mir-strip-debugify-only                                             - Should mir-strip-debug only strip debug info from debugified modules by default
  --mno-compound                                                        - Disable looking for compound instructions for Hexagon
  --mno-fixup                                                           - Disable fixing up resolved relocations for Hexagon
  --mno-ldc1-sdc1                                                       - Expand double precision loads and stores to their single precision counterparts
  --mno-pairing                                                         - Disable looking for duplex instructions for Hexagon
  --module-hash                                                         - Emit module hash
  --module-summary                                                      - Emit module summary index
  --mtriple=<string>                                                    - Override target triple for module
  --mwarn-missing-parenthesis                                           - Warn for missing parenthesis around predicate registers
  --mwarn-noncontigious-register                                        - Warn for register names that arent contigious
  --mwarn-sign-mismatch                                                 - Warn for mismatching a signed and unsigned value
  --no-deprecated-warn                                                  - Suppress all deprecated warnings
  --no-discriminators                                                   - Disable generation of discriminator information.
  --no-type-check                                                       - Suppress type errors (Wasm)
  --no-warn                                                             - Suppress all warnings
  --no-xray-index                                                       - Don't emit xray_fn_idx section
  --nozero-initialized-in-bss                                           - Don't place zero-initialized symbols into bss section
  --nvptx-sched4reg                                                     - NVPTX Specific: schedule for register pressue
  -o=<filename>                                                         - Override output filename
  --opaque-pointers                                                     - Use opaque pointers
  --pass-remarks-filter=<regex>                                         - Only record optimization remarks from passes whose names match the given regular expression
  --pass-remarks-format=<format>                                        - The format used for serializing remarks (default: YAML)
  --pass-remarks-output=<filename>                                      - Output filename for pass remarks
  --passes=<string>                                                     - A textual description of the pass pipeline. To have analysis passes available before a certain pass, add 'require<foo-analysis>'.
  --poison-checking-function-local                                      - Check that returns are non-poison (for testing)
  --print-breakpoints-for-testing                                       - Print select breakpoints location for testing
  --print-passes                                                        - Print available passes that can be specified in -passes=foo and exit
  --print-pipeline-passes                                               - Print a '-passes' compatible string describing the pipeline (best-effort only).
  --r600-ir-structurize                                                 - Use StructurizeCFG IR pass
  --rdf-dump                                                            - 
  --rdf-limit=<uint>                                                    - 
  --relax-elf-relocations                                               - Emit GOTPCRELX/REX_GOTPCRELX instead of GOTPCREL on x86-64 ELF
  --relocation-model=<value>                                            - Choose relocation model
    =static                                                             -   Non-relocatable code
    =pic                                                                -   Fully relocatable, position independent code
    =dynamic-no-pic                                                     -   Relocatable external references, non-relocatable code
    =ropi                                                               -   Code and read-only data relocatable, accessed PC-relative
    =rwpi                                                               -   Read-write data relocatable, accessed relative to static base
    =ropi-rwpi                                                          -   Combination of ropi and rwpi
  --runtime-counter-relocation                                          - Enable relocating counters at runtime.
  --safepoint-ir-verifier-print-only                                    - 
  --sample-profile-check-record-coverage=<N>                            - Emit a warning if less than N% of records in the input profile are matched to the IR.
  --sample-profile-check-sample-coverage=<N>                            - Emit a warning if less than N% of samples in the input profile are matched to the IR.
  --sample-profile-max-propagate-iterations=<uint>                      - Maximum number of iterations to go through when propagating sample block/edge weights through the CFG.
  Optimizations available (use '-passes=' for the new pass manager)
      --aa                                                                 - Function Alias Analysis Results
      --aa-eval                                                            - Exhaustive Alias Analysis Precision Evaluator
      --aarch64-O0-prelegalizer-combiner                                   - Combine AArch64 machine instrs before legalization
      --aarch64-a57-fp-load-balancing                                      - AArch64 A57 FP Load-Balancing
      --aarch64-branch-targets                                             - AArch64 Branch Targets
      --aarch64-ccmp                                                       - AArch64 CCMP Pass
      --aarch64-collect-loh                                                - AArch64 Collect Linker Optimization Hint (LOH)
      --aarch64-condopt                                                    - AArch64 CondOpt Pass
      --aarch64-copyelim                                                   - AArch64 redundant copy elimination pass
      --aarch64-dead-defs                                                  - AArch64 Dead register definitions
      --aarch64-expand-pseudo                                              - AArch64 pseudo instruction expansion pass
      --aarch64-falkor-hwpf-fix                                            - Falkor HW Prefetch Fix
      --aarch64-falkor-hwpf-fix-late                                       - Falkor HW Prefetch Fix Late Phase
      --aarch64-fix-cortex-a53-835769-pass                                 - AArch64 fix for A53 erratum 835769
      --aarch64-jump-tables                                                - AArch64 compress jump tables pass
      --aarch64-ldst-opt                                                   - AArch64 load / store optimization pass
      --aarch64-local-dynamic-tls-cleanup                                  - AArch64 Local Dynamic TLS Access Clean-up
      --aarch64-lower-homogeneous-prolog-epilog                            - AArch64 homogeneous prolog/epilog lowering pass
      --aarch64-mi-peephole-opt                                            - AArch64 MI Peephole Optimization
      --aarch64-post-select-optimize                                       - Optimize AArch64 selected instructions
      --aarch64-postlegalizer-combiner                                     - Combine AArch64 MachineInstrs after legalization
      --aarch64-postlegalizer-lowering                                     - Lower AArch64 MachineInstrs after legalization
      --aarch64-prelegalizer-combiner                                      - Combine AArch64 machine instrs before legalization
      --aarch64-promote-const                                              - AArch64 Promote Constant Pass
      --aarch64-simd-scalar                                                - AdvSIMD Scalar Operation Optimization
      --aarch64-simdinstr-opt                                              - AArch64 SIMD instructions optimization pass
      --aarch64-sls-hardening                                              - AArch64 sls hardening pass
      --aarch64-speculation-hardening                                      - AArch64 speculation hardening pass
      --aarch64-stack-tagging                                              - AArch64 Stack Tagging
      --aarch64-stack-tagging-pre-ra                                       - AArch64 Stack Tagging PreRA Pass
      --aarch64-stp-suppress                                               - AArch64 Store Pair Suppression
      --aarch64-sve-intrinsic-opts                                         - SVE intrinsics optimizations
      --adce                                                               - Aggressive Dead Code Elimination
      --add-discriminators                                                 - Add DWARF path discriminators
      --aggressive-instcombine                                             - Combine pattern based expressions
      --alignment-from-assumptions                                         - Alignment from assumptions
      --alloca-hoisting                                                    - Hoisting alloca instructions in non-entry blocks to the entry block
      --always-inline                                                      - Inliner for always_inline functions
      --amdgpu-aa                                                          - AMDGPU Address space based Alias Analysis
      --amdgpu-aa-wrapper                                                  - AMDGPU Address space based Alias Analysis Wrapper
      --amdgpu-always-inline                                               - AMDGPU Inline All Functions
      --amdgpu-annotate-kernel-features                                    - Add AMDGPU function attributes
      --amdgpu-annotate-uniform                                            - Add AMDGPU uniform metadata
      --amdgpu-argument-reg-usage-info                                     - Argument Register Usage Information Storage
      --amdgpu-atomic-optimizer                                            - AMDGPU atomic optimizations
      --amdgpu-attributor                                                  - AMDGPU Attributor
      --amdgpu-codegenprepare                                              - AMDGPU IR optimizations
      --amdgpu-fix-function-bitcasts                                       - Fix function bitcasts for AMDGPU
      --amdgpu-isel                                                        - AMDGPU DAG->DAG Pattern Instruction Selection
      --amdgpu-late-codegenprepare                                         - AMDGPU IR late optimizations
      --amdgpu-lower-ctor-dtor                                             - Lower ctors and dtors for AMDGPU
      --amdgpu-lower-enqueued-block                                        - Lower OpenCL enqueued blocks
      --amdgpu-lower-intrinsics                                            - Lower intrinsics
      --amdgpu-lower-kernel-arguments                                      - AMDGPU Lower Kernel Arguments
      --amdgpu-lower-kernel-attributes                                     - AMDGPU Kernel Attributes
      --amdgpu-lower-module-lds                                            - Lower uses of LDS variables from non-kernel functions
      --amdgpu-nsa-reassign                                                - GCN NSA Reassign
      --amdgpu-perf-hint                                                   - Analysis if a function is memory bound
      --amdgpu-postlegalizer-combiner                                      - Combine AMDGPU machine instrs after legalization
      --amdgpu-pre-ra-optimizations                                        - Pre-RA optimizations
      --amdgpu-prelegalizer-combiner                                       - Combine AMDGPU machine instrs before legalization
      --amdgpu-printf-runtime-binding                                      - AMDGPU Printf lowering
      --amdgpu-promote-alloca                                              - AMDGPU promote alloca to vector or LDS
      --amdgpu-promote-alloca-to-vector                                    - AMDGPU promote alloca to vector
      --amdgpu-promote-kernel-arguments                                    - AMDGPU Promote Kernel Arguments
      --amdgpu-propagate-attributes-early                                  - Early propagate attributes from kernels to functions
      --amdgpu-propagate-attributes-late                                   - Late propagate attributes from kernels to functions
      --amdgpu-regbank-combiner                                            - Combine AMDGPU machine instrs after regbankselect
      --amdgpu-replace-lds-use-with-pointer                                - Replace within non-kernel function use of LDS with pointer
      --amdgpu-resource-usage                                              - Function register usage analysis
      --amdgpu-rewrite-out-arguments                                       - AMDGPU Rewrite Out Arguments
      --amdgpu-simplifylib                                                 - Simplify well-known AMD library calls
      --amdgpu-unify-divergent-exit-nodes                                  - Unify divergent function exit nodes
      --amdgpu-unify-metadata                                              - Unify multiple OpenCL metadata due to linking
      --amdgpu-usenative                                                   - Replace builtin math calls with that native versions.
      --amode-opt                                                          - Optimize addressing mode
      --annotation-remarks                                                 - Annotation Remarks
      --annotation2metadata                                                - Annotation2Metadata
      --argpromotion                                                       - Promote 'by reference' arguments to scalars
      --arm-block-placement                                                - ARM block placement
      --arm-branch-targets                                                 - ARM Branch Targets
      --arm-cp-islands                                                     - ARM constant island placement and branch shortening pass
      --arm-execution-domain-fix                                           - ARM Execution Domain Fix
      --arm-ldst-opt                                                       - ARM load / store optimization pass
      --arm-low-overhead-loops                                             - ARM Low Overhead Loops pass
      --arm-mve-gather-scatter-lowering                                    - MVE gather/scattering lowering pass
      --arm-mve-vpt                                                        - ARM MVE VPT block pass
      --arm-mve-vpt-opts                                                   - ARM MVE TailPred and VPT Optimisations pass
      --arm-parallel-dsp                                                   - Transform functions to use DSP intrinsics
      --arm-prera-ldst-opt                                                 - ARM pre- register allocation load / store optimization pass
      --arm-pseudo                                                         - ARM pseudo instruction expansion pass
      --arm-sls-hardening                                                  - ARM sls hardening pass
      --asan                                                               - AddressSanitizer: detects use-after-free and out-of-bounds bugs.
      --asan-globals-md                                                    - Read metadata to mark which globals should be instrumented when running ASan.
      --asan-module                                                        - AddressSanitizer: detects use-after-free and out-of-bounds bugs.ModulePass
      --assume-builder                                                     - Assume Builder
      --assume-simplify                                                    - Assume Simplify
      --assumption-cache-tracker                                           - Assumption Cache Tracker
      --atomic-expand                                                      - Expand Atomic instructions
      --attributor                                                         - Deduce and propagate attributes
      --attributor-cgscc                                                   - Deduce and propagate attributes (CGSCC pass)
      --avr-expand-pseudo                                                  - AVR pseudo instruction expansion pass
      --avr-relax-mem                                                      - AVR memory operation relaxation pass
      --avr-shift-expand                                                   - AVR Shift Expansion
      --barrier                                                            - A No-Op Barrier Pass
      --basic-aa                                                           - Basic Alias Analysis (stateless AA impl)
      --basiccg                                                            - CallGraph Construction
      --bdce                                                               - Bit-Tracking Dead Code Elimination
      --block-freq                                                         - Block Frequency Analysis
      --bounds-checking                                                    - Run-time bounds checking
      --bpf-abstract-member-access                                         - BPF Abstract Member Access
      --bpf-adjust-opt                                                     - BPF Adjust Optimization
      --bpf-check-and-opt-ir                                               - BPF Check And Adjust IR
      --bpf-ir-peephole                                                    - BPF IR Peephole
      --bpf-mi-trunc-elim                                                  - BPF MachineSSA Peephole Optimization For TRUNC Eliminate
      --bpf-mi-zext-elim                                                   - BPF MachineSSA Peephole Optimization For ZEXT Eliminate
      --bpf-preserve-di-type                                               - BPF Preserve Debuginfo Type
      --branch-prob                                                        - Branch Probability Analysis
      --break-crit-edges                                                   - Break critical edges in CFG
      --called-value-propagation                                           - Called Value Propagation
      --callsite-splitting                                                 - Call-site splitting
      --canon-freeze                                                       - Canonicalize Freeze Instructions in Loops
      --canonicalize-aliases                                               - Canonicalize aliases
      --cfl-anders-aa                                                      - Inclusion-Based CFL Alias Analysis
      --cfl-steens-aa                                                      - Unification-Based CFL Alias Analysis
      --cg-profile                                                         - Call Graph Profile
      --check-debugify                                                     - Check debug info from -debugify
      --check-debugify-function                                            - Check debug info from -debugify-function
      --chr                                                                - Reduce control height in the hot paths
      --codegenprepare                                                     - Optimize for code generation
      --consthoist                                                         - Constant Hoisting
      --constmerge                                                         - Merge Duplicate Global Constants
      --constraint-elimination                                             - Constraint Elimination
      --coro-cleanup                                                       - Lower all coroutine related intrinsics
      --coro-early                                                         - Lower early coroutine intrinsics
      --coro-elide                                                         - Coroutine frame allocation elision and indirect calls replacement
      --coro-split                                                         - Split coroutine into a set of functions driving its state machine
      --correlated-propagation                                             - Value Propagation
      --cost-model                                                         - Cost Model Analysis
      --cross-dso-cfi                                                      - Cross-DSO CFI
      --cseinfo                                                            - Analysis containing CSE Info
      --cycles                                                             - Cycle Info Analysis
      --da                                                                 - Dependence Analysis
      --dce                                                                - Dead Code Elimination
      --deadargelim                                                        - Dead Argument Elimination
      --deadarghaX0r                                                       - Dead Argument Hacking (BUGPOINT USE ONLY; DO NOT USE)
      --debugify                                                           - Attach debug info to everything
      --debugify-function                                                  - Attach debug info to a function
      --delinearize                                                        - Delinearization
      --demanded-bits                                                      - Demanded bits analysis
      --dfa-jump-threading                                                 - DFA Jump Threading
      --dfsan                                                              - DataFlowSanitizer: dynamic data flow analysis.
      --div-rem-pairs                                                      - Hoist/decompose integer division and remainder
      --divergence                                                         - Legacy Divergence Analysis
      --domfrontier                                                        - Dominance Frontier Construction
      --domtree                                                            - Dominator Tree Construction
      --dot-callgraph                                                      - Print call graph to 'dot' file
      --dot-cfg                                                            - Print CFG of function to 'dot' file
      --dot-cfg-only                                                       - Print CFG of function to 'dot' file (with no function bodies)
      --dot-dom                                                            - Print dominance tree of function to 'dot' file
      --dot-dom-only                                                       - Print dominance tree of function to 'dot' file (with no function bodies)
      --dot-postdom                                                        - Print postdominance tree of function to 'dot' file
      --dot-postdom-only                                                   - Print postdominance tree of function to 'dot' file (with no function bodies)
      --dot-regions                                                        - Print regions of function to 'dot' file
      --dot-regions-only                                                   - Print regions of function to 'dot' file (with no function bodies)
      --dot-scops                                                          - Polly - Print Scops of function
      --dot-scops-only                                                     - Polly - Print Scops of function (with no function bodies)
      --dse                                                                - Dead Store Elimination
      --dwarfehprepare                                                     - Prepare DWARF exceptions
      --early-cse                                                          - Early CSE
      --early-cse-memssa                                                   - Early CSE w/ MemorySSA
      --edge-bundles                                                       - Bundle Machine CFG Edges
      --ee-instrument                                                      - Instrument function entry/exit with calls to e.g. mcount() (pre inlining)
      --elim-avail-extern                                                  - Eliminate Available Externally Globals
      --expand-reductions                                                  - Expand reduction intrinsics
      --expandmemcmp                                                       - Expand memcmp() to load/stores
      --expandvp                                                           - Expand vector predication intrinsics
      --external-aa                                                        - External Alias Analysis
      --extract-blocks                                                     - Extract basic blocks from module
      --fasttileconfig                                                     - Fast Tile Register Configure
      --fix-irreducible                                                    - Convert irreducible control-flow into natural loops
      --flattencfg                                                         - Flatten the CFG
      --float2int                                                          - Float to int
      --forceattrs                                                         - Force set function attributes
      --function-attrs                                                     - Deduce function attributes
      --function-import                                                    - Summary Based Function Import
      --function-specialization                                            - Propagate constant arguments by specializing the function
      --gcn-dpp-combine                                                    - GCN DPP Combine
      --generic-to-nvvm                                                    - Ensure that the global variables are in the global address space
      --gisel-known-bits                                                   - Analysis for ComputingKnownBits
      --global-merge                                                       - Merge global variables
      --globaldce                                                          - Dead Global Elimination
      --globalopt                                                          - Global Variable Optimizer
      --globals-aa                                                         - Globals Alias Analysis
      --globalsplit                                                        - Global splitter
      --guard-widening                                                     - Widen guards
      --gvn                                                                - Global Value Numbering
      --gvn-hoist                                                          - Early GVN Hoisting of Expressions
      --gvn-sink                                                           - Early GVN sinking of Expressions
      --hardware-loops                                                     - Hardware Loop Insertion
      --hexagon-bit-simplify                                               - Hexagon bit simplification
      --hexagon-cext-opt                                                   - Hexagon constant-extender optimization
      --hexagon-constp                                                     - Hexagon Constant Propagation
      --hexagon-copy-combine                                               - Hexagon Copy-To-Combine Pass
      --hexagon-early-if                                                   - Hexagon early if conversion
      --hexagon-gen-mux                                                    - Hexagon generate mux instructions
      --hexagon-loop-idiom                                                 - Recognize Hexagon-specific loop idioms
      --hexagon-nvj                                                        - Hexagon NewValueJump
      --hexagon-packetizer                                                 - Hexagon Packetizer
      --hexagon-rdf-opt                                                    - Hexagon RDF optimizations
      --hexagon-split-double                                               - Hexagon Split Double Registers
      --hexagon-vc                                                         - Hexagon Vector Combine
      --hexagon-vextract                                                   - Hexagon optimize vextract
      --hexagon-vlcr                                                       - Hexagon-specific predictive commoning for HVX vectors
      --hotcoldsplit                                                       - Hot Cold Splitting
      --hwasan                                                             - HWAddressSanitizer: detect memory bugs using tagged addressing.
      --hwloops                                                            - Hexagon Hardware Loops
      --indirectbr-expand                                                  - Expand indirectbr instructions
      --indvars                                                            - Induction Variable Simplification
      --infer-address-spaces                                               - Infer address spaces
      --inferattrs                                                         - Infer set function attributes
      --inject-tli-mappings                                                - Inject TLI Mappings
      --inline                                                             - Function Integration/Inlining
      --insert-gcov-profiling                                              - Insert instrumentation for GCOV profiling
      --instcombine                                                        - Combine redundant instructions
      --instcount                                                          - Counts the various types of Instructions
      --instnamer                                                          - Assign names to anonymous instructions
      --instrorderfile                                                     - Instrumentation for Order File
      --instrprof                                                          - Frontend instrumentation-based coverage lowering.
      --instruction-select                                                 - Select target instructions out of generic instructions
      --instsimplify                                                       - Remove redundant instructions
      --interleaved-access                                                 - Lower interleaved memory accesses to target specific intrinsics
      --interleaved-load-combine                                           - Combine interleaved loads into wide loads and shufflevector instructions
      --internalize                                                        - Internalize Global Symbols
      --intervals                                                          - Interval Partition Construction
      --ipsccp                                                             - Interprocedural Sparse Conditional Constant Propagation
      --ir-similarity-identifier                                           - ir-similarity-identifier
      --irce                                                               - Inductive range check elimination
      --iroutliner                                                         - IR Outliner
      --irtranslator                                                       - IRTranslator LLVM IR -> MI
      --iv-users                                                           - Induction Variable Users
      --jump-threading                                                     - Jump Threading
      --lazy-block-freq                                                    - Lazy Block Frequency Analysis
      --lazy-branch-prob                                                   - Lazy Branch Probability Analysis
      --lazy-value-info                                                    - Lazy Value Information Analysis
      --lcssa                                                              - Loop-Closed SSA Form Pass
      --lcssa-verification                                                 - LCSSA Verifier
      --legalizer                                                          - Legalize the Machine IR a function's Machine IR
      --libcalls-shrinkwrap                                                - Conditionally eliminate dead library calls
      --licm                                                               - Loop Invariant Code Motion
      --lint                                                               - Statically lint-checks LLVM IR
      --liveintervals                                                      - Live Interval Analysis
      --liveregmatrix                                                      - Live Register Matrix
      --livevars                                                           - Live Variable Analysis
      --load-store-vectorizer                                              - Vectorize load and store instructions
      --loadstore-opt                                                      - Generic memory optimizations
      --localizer                                                          - Move/duplicate certain instructions close to their use
      --loop-accesses                                                      - Loop Access Analysis
      --loop-data-prefetch                                                 - Loop Data Prefetch
      --loop-deletion                                                      - Delete dead loops
      --loop-distribute                                                    - Loop Distribution
      --loop-extract                                                       - Extract loops into new functions
      --loop-extract-single                                                - Extract at most one loop into a new function
      --loop-flatten                                                       - Flattens loops
      --loop-fusion                                                        - Loop Fusion
      --loop-guard-widening                                                - Widen guards (within a single loop, as a loop pass)
      --loop-idiom                                                         - Recognize loop idioms
      --loop-instsimplify                                                  - Simplify instructions in loops
      --loop-interchange                                                   - Interchanges loops for cache reuse
      --loop-load-elim                                                     - Loop Load Elimination
      --loop-predication                                                   - Loop predication
      --loop-reduce                                                        - Loop Strength Reduction
      --loop-reroll                                                        - Reroll loops
      --loop-rotate                                                        - Rotate Loops
      --loop-simplify                                                      - Canonicalize natural loops
      --loop-simplifycfg                                                   - Simplify loop CFG
      --loop-sink                                                          - Loop Sink
      --loop-unroll                                                        - Unroll loops
      --loop-unroll-and-jam                                                - Unroll and Jam loops
      --loop-unswitch                                                      - Unswitch loops
      --loop-vectorize                                                     - Loop Vectorization
      --loop-versioning                                                    - Loop Versioning
      --loop-versioning-licm                                               - Loop Versioning For LICM
      --loops                                                              - Natural Loop Information
      --lower-amx-intrinsics                                               - Lower AMX intrinsics
      --lower-amx-type                                                     - Lower AMX type for load/store
      --lower-constant-intrinsics                                          - Lower constant intrinsics
      --lower-expect                                                       - Lower 'expect' Intrinsics
      --lower-guard-intrinsic                                              - Lower the guard intrinsic to normal control flow
      --lower-matrix-intrinsics                                            - Lower the matrix intrinsics
      --lower-matrix-intrinsics-minimal                                    - Lower the matrix intrinsics (minimal)
      --lower-widenable-condition                                          - Lower the widenable condition to default true value
      --loweratomic                                                        - Lower atomic intrinsics to non-atomic form
      --lowerinvoke                                                        - Lower invoke and unwind, for unwindless code generators
      --lowerswitch                                                        - Lower SwitchInst's to branches
      --lowertilecopy                                                      - Tile Copy Lowering
      --lowertypetests                                                     - Lower type metadata
      --machine-block-freq                                                 - Machine Block Frequency Analysis
      --machine-branch-prob                                                - Machine Branch Probability Analysis
      --machine-domfrontier                                                - Machine Dominance Frontier Construction
      --machine-loops                                                      - Machine Natural Loop Construction
      --machine-trace-metrics                                              - Machine Trace Metrics
      --machinedomtree                                                     - MachineDominator Tree Construction
      --machinepostdomtree                                                 - MachinePostDominator Tree Construction
      --make-guards-explicit                                               - Lower the guard intrinsic to explicit control flow form
      --mem2reg                                                            - Promote Memory to Register
      --memcpyopt                                                          - MemCpy Optimization
      --memdep                                                             - Memory Dependence Analysis
      --memoryssa                                                          - Memory SSA
      --memprof                                                            - MemProfiler: profile memory allocations and accesses.
      --memprof-module                                                     - MemProfiler: profile memory allocations and accesses.ModulePass
      --mergefunc                                                          - Merge Functions
      --mergeicmps                                                         - Merge contiguous icmps into a memcmp
      --mergereturn                                                        - Unify function exit nodes
      --metarenamer                                                        - Assign new names to everything
      --micromips-reduce-size                                              - MicroMips instruction size reduce pass
      --mips-branch-expansion                                              - Expand out of range branch instructions and fix forbidden slot hazards
      --mips-delay-slot-filler                                             - Fill delay slot for MIPS
      --mips-prelegalizer-combiner                                         - Combine Mips machine instrs before legalization
      --mips-vr4300-mulmul-fix                                             - Mips VR4300 mulmul bugfix
      --mldst-motion                                                       - MergedLoadStoreMotion
      --module-debuginfo                                                   - Decodes module-level debug info
      --module-summary-analysis                                            - Module Summary Analysis
      --module-summary-info                                                - Module summary info
      --msan                                                               - MemorySanitizer: detects uninitialized reads.
      --mve-laneinterleave                                                 - MVE lane interleaving
      --mve-tail-predication                                               - Transform predicated vector loops to use MVE tail predication
      --name-anon-globals                                                  - Provide a name to nameless globals
      --nary-reassociate                                                   - Nary reassociation
      --newgvn                                                             - Global Value Numbering
      --nvptx-assign-valid-global-names                                    - Assign valid PTX names to globals
      --nvptx-atomic-lower                                                 - Lower atomics of local memory to simple load/stores
      --nvptx-lower-aggr-copies                                            - Lower aggregate copies, and llvm.mem* intrinsics into loops
      --nvptx-lower-alloca                                                 - Lower Alloca
      --nvptx-lower-args                                                   - Lower arguments (NVPTX)
      --nvptx-proxyreg-erasure                                             - NVPTX ProxyReg Erasure
      --nvvm-intr-range                                                    - Add !range metadata to NVVM intrinsics.
      --nvvm-reflect                                                       - Replace occurrences of __nvvm_reflect() calls with 0/1
      --objc-arc                                                           - ObjC ARC optimization
      --objc-arc-aa                                                        - ObjC-ARC-Based Alias Analysis
      --objc-arc-apelim                                                    - ObjC ARC autorelease pool elimination
      --objc-arc-contract                                                  - ObjC ARC contraction
      --objc-arc-expand                                                    - ObjC ARC expansion
      --openmp-opt-cgscc                                                   - OpenMP specific optimizations
      --opt-remark-emitter                                                 - Optimization Remark Emitter
      --pa-eval                                                            - Evaluate ProvenanceAnalysis on all pairs
      --packets                                                            - R600 Packetizer
      --partial-inliner                                                    - Partial Inliner
      --partially-inline-libcalls                                          - Partially inline calls to library functions
      --pgo-icall-prom                                                     - Use PGO instrumentation profile to promote indirect calls to direct calls.
      --pgo-instr-gen                                                      - PGO instrumentation.
      --pgo-instr-use                                                      - Read PGO instrumentation profile.
      --pgo-memop-opt                                                      - Optimize memory intrinsic using its size value profile
      --phi-values                                                         - Phi Values Analysis
      --place-backedge-safepoints-impl                                     - Place Backedge Safepoints
      --place-safepoints                                                   - Place Safepoints
      --polly-ast                                                          - Polly - Generate an AST from the SCoP (isl)
      --polly-canonicalize                                                 - Polly - Run canonicalization passes
      --polly-cleanup                                                      - Polly - Cleanup after code generation
      --polly-codegen                                                      - Polly - Create LLVM-IR from SCoPs
      --polly-dce                                                          - Polly - Remove dead iterations
      --polly-delicm                                                       - Polly - DeLICM/DePRE
      --polly-dependences                                                  - Polly - Calculate dependences
      --polly-detect                                                       - Polly - Detect static control parts (SCoPs)
      --polly-dump-module                                                  - Polly - Dump Module
      --polly-export-jscop                                                 - Polly - Export Scops as JSON (Writes a .jscop file for each Scop)
      --polly-flatten-schedule                                             - Polly - Flatten schedule
      --polly-function-dependences                                         - Polly - Calculate dependences for all the SCoPs of a function
      --polly-function-scops                                               - Polly - Create polyhedral description of all Scops of a function
      --polly-import-jscop                                                 - Polly - Import Scops from JSON (Reads a .jscop file for each Scop)
      --polly-mse                                                          - Polly - Maximal static expansion of SCoP
      --polly-opt-isl                                                      - Polly - Optimize schedule of SCoP
      --polly-optree                                                       - Polly - Forward operand tree
      --polly-prepare                                                      - Polly - Prepare code for polly
      --polly-prune-unprofitable                                           - Polly - Prune unprofitable SCoPs
      --polly-scop-inliner                                                 - inline functions based on how much of the function is a scop.
      --polly-scops                                                        - Polly - Create polyhedral description of Scops
      --polly-simplify                                                     - Polly - Simplify
      --polyhedral-info                                                    - Polly - Interface to polyhedral analysis engine
      --post-inline-ee-instrument                                          - Instrument function entry/exit with calls to e.g. mcount() (post inlining)
      --postdomtree                                                        - Post-Dominator Tree Construction
      --ppc-atomic-expand                                                  - PowerPC Expand Atomic
      --ppc-bool-ret-to-int                                                - Convert i1 constants to i32/i64 if they are returned
      --ppc-branch-coalescing                                              - Branch Coalescing
      --ppc-branch-select                                                  - PowerPC Branch Selector
      --ppc-early-ret                                                      - PowerPC Early-Return Creation
      --ppc-expand-isel                                                    - PowerPC Expand ISEL Generation
      --ppc-loop-instr-form-prep                                           - Prepare loop for ppc preferred instruction forms
      --ppc-lower-massv-entries                                            - Lower MASSV entries
      --ppc-mi-peepholes                                                   - PowerPC MI Peephole Optimization
      --ppc-pre-emit-peephole                                              - PowerPC Pre-Emit Peephole
      --ppc-reduce-cr-ops                                                  - PowerPC Reduce CR logical Operation
      --ppc-tls-dynamic-call                                               - PowerPC TLS Dynamic Call Fixup
      --ppc-toc-reg-deps                                                   - PowerPC TOC Register Dependencies
      --ppc-vsx-copy                                                       - PowerPC VSX Copy Legalization
      --ppc-vsx-fma-mutate                                                 - PowerPC VSX FMA Mutation
      --ppc-vsx-swaps                                                      - PowerPC VSX Swap Removal
      --pre-amx-config                                                     - Pre AMX Tile Config
      --pre-isel-intrinsic-lowering                                        - Pre-ISel Intrinsic Lowering
      --print-alias-sets                                                   - Alias Set Printer
      --print-callgraph                                                    - Print a call graph
      --print-callgraph-sccs                                               - Print SCCs of the Call Graph
      --print-cfg-sccs                                                     - Print SCCs of each function CFG
      --print-dom-info                                                     - Dominator Info Printer
      --print-externalfnconstants                                          - Print external fn callsites passed constants
      --print-function                                                     - Print function to stderr
      --print-lazy-value-info                                              - Lazy Value Info Printer Pass
      --print-memdeps                                                      - Print MemDeps of function
      --print-memderefs                                                    - Memory Dereferenciblity of pointers in function
      --print-memoryssa                                                    - Memory SSA Printer
      --print-module                                                       - Print module to stderr
      --print-must-be-executed-contexts                                    - print the must-be-executed-context for all instructions
      --print-mustexecute                                                  - Instructions which execute on loop entry
      --print-predicateinfo                                                - PredicateInfo Printer
      --profile-summary-info                                               - Profile summary info
      --prune-eh                                                           - Remove unused exception handling info
      --pseudo-probe-inserter                                              - Insert pseudo probe annotations for value profiling
      --r600-expand-special-instrs                                         - R600ExpandSpecialInstrs
      --r600cf                                                             - R600 Control Flow Finalizer
      --r600mergeclause                                                    - R600 Clause Merge
      --reaching-deps-analysis                                             - ReachingDefAnalysis
      --reassociate                                                        - Reassociate expressions
      --redundant-dbg-inst-elim                                            - Redundant Dbg Instruction Elimination
      --reg2mem                                                            - Demote all values to stack slots
      --regbankselect                                                      - Assign register bank of generic virtual registers
      --regions                                                            - Detect single entry single exit regions
      --replace-with-veclib                                                - Replace intrinsics with calls to vector library
      --rewrite-statepoints-for-gc                                         - Make relocations explicit at statepoints
      --rewrite-symbols                                                    - Rewrite Symbols
      --riscv-expand-pseudo                                                - RISCV pseudo instruction expansion pass
      --riscv-gather-scatter-lowering                                      - RISCV gather/scatter lowering pass
      --riscv-insert-vsetvli                                               - RISCV Insert VSETVLI pass
      --riscv-merge-base-offset                                            - RISCV Merge Base Offset
      --riscv-sextw-removal                                                - RISCV sext.w Removal
      --rpo-function-attrs                                                 - Deduce function attributes in RPO
      --safe-stack                                                         - Safe Stack instrumentation pass
      --sample-profile                                                     - Sample Profile loader
      --sancov                                                             - Pass for instrumenting coverage on functions
      --scalar-evolution                                                   - Scalar Evolution Analysis
      --scalarize-masked-mem-intrin                                        - Scalarize unsupported masked memory intrinsics
      --scalarizer                                                         - Scalarize vector operations
      --sccp                                                               - Sparse Conditional Constant Propagation
      --scev-aa                                                            - ScalarEvolution-based Alias Analysis
      --scoped-noalias-aa                                                  - Scoped NoAlias Alias Analysis
      --separate-const-offset-from-gep                                     - Split GEPs to a variadic base and a constant offset for better CSE
      --si-annotate-control-flow                                           - Annotate SI Control Flow
      --si-fix-sgpr-copies                                                 - SI Fix SGPR copies
      --si-fix-vgpr-copies                                                 - SI Fix VGPR copies
      --si-fold-operands                                                   - SI Fold Operands
      --si-form-memory-clauses                                             - SI Form memory clauses
      --si-i1-copies                                                       - SI Lower i1 Copies
      --si-insert-hard-clauses                                             - SI Insert Hard Clauses
      --si-insert-waitcnts                                                 - SI Insert Waitcnts
      --si-late-branch-lowering                                            - SI insert s_cbranch_execz instructions
      --si-load-store-opt                                                  - SI Load Store Optimizer
      --si-lower-control-flow                                              - SI lower control flow
      --si-lower-sgpr-spills                                               - SI lower SGPR spill instructions
      --si-memory-legalizer                                                - SI Memory Legalizer
      --si-mode-register                                                   - Insert required mode register values
      --si-opt-vgpr-liverange                                              - SI Optimize VGPR LiveRange
      --si-optimize-exec-masking                                           - SI optimize exec mask operations
      --si-optimize-exec-masking-pre-ra                                    - SI optimize exec mask operations pre-RA
      --si-peephole-sdwa                                                   - SI Peephole SDWA
      --si-post-ra-bundler                                                 - SI post-RA bundler
      --si-pre-allocate-wwm-regs                                           - SI Pre-allocate WWM Registers
      --si-pre-emit-peephole                                               - SI peephole optimizations
      --si-shrink-instructions                                             - SI Shrink Instructions
      --si-wqm                                                             - SI Whole Quad Mode
      --simple-loop-unswitch                                               - Simple unswitch loops
      --simplifycfg                                                        - Simplify the CFG
      --sink                                                               - Code sinking
      --sjljehprepare                                                      - Prepare SjLj exceptions
      --slotindexes                                                        - Slot index numbering
      --slp-vectorizer                                                     - SLP Vectorizer
      --slsr                                                               - Straight line strength reduction
      --speculative-execution                                              - Speculatively execute instructions
      --sroa                                                               - Scalar Replacement Of Aggregates
      --stack-protector                                                    - Insert stack protectors
      --stack-safety                                                       - Stack Safety Analysis
      --stack-safety-local                                                 - Stack Safety Local Analysis
      --strip                                                              - Strip all symbols from a module
      --strip-dead-debug-info                                              - Strip debug info for unused symbols
      --strip-dead-prototypes                                              - Strip Unused Function Prototypes
      --strip-debug-declare                                                - Strip all llvm.dbg.declare intrinsics
      --strip-gc-relocates                                                 - Strip gc.relocates inserted through RewriteStatepointsForGC
      --strip-nondebug                                                     - Strip all symbols, except dbg symbols, from a module
      --strip-nonlinetable-debuginfo                                       - Strip all debug info except linetables
      --structurizecfg                                                     - Structurize the CFG
      --systemz-elim-compare                                               - SystemZ Comparison Elimination
      --systemz-ld-cleanup                                                 - SystemZ Local Dynamic TLS Access Clean-up
      --systemz-long-branch                                                - SystemZ Long Branch
      --systemz-post-rewrite                                               - SystemZ Post Rewrite pass
      --systemz-shorten-inst                                               - SystemZ Instruction Shortening
      --systemz-tdc                                                        - SystemZ Test Data Class optimization
      --tailcallelim                                                       - Tail Call Elimination
      --targetlibinfo                                                      - Target Library Information
      --targetpassconfig                                                   - Target Pass Configuration
      --tbaa                                                               - Type-Based Alias Analysis
      --thumb2-reduce-size                                                 - Thumb2 instruction size reduce pass
      --tileconfig                                                         - Tile Register Configure
      --transform-warning                                                  - Warn about non-applied transformations
      --tsan                                                               - ThreadSanitizer: detects data races.
      --tti                                                                - Target Transform Information
      --type-promotion                                                     - Type Promotion
      --unify-loop-exits                                                   - Fixup each natural loop to have a single exit block
      --unreachable-mbb-elimination                                        - Remove unreachable machine basic blocks
      --unreachableblockelim                                               - Remove unreachable blocks from the CFG
      --vec-merger                                                         - R600 Vector Reg Merger
      --vector-combine                                                     - Optimize scalar/vector ops
      --verify                                                             - Module Verifier
      --verify-safepoint-ir                                                - Safepoint IR Verifier
      --view-callgraph                                                     - View call graph
      --view-cfg                                                           - View CFG of function
      --view-cfg-only                                                      - View CFG of function (with no function bodies)
      --view-dom                                                           - View dominance tree of function
      --view-dom-only                                                      - View dominance tree of function (with no function bodies)
      --view-postdom                                                       - View postdominance tree of function
      --view-postdom-only                                                  - View postdominance tree of function (with no function bodies)
      --view-regions                                                       - View regions of function
      --view-regions-only                                                  - View regions of function (with no function bodies)
      --view-scops                                                         - Polly - View Scops of function
      --view-scops-only                                                    - Polly - View Scops of function (with no function bodies)
      --virtregmap                                                         - Virtual Register Map
      --wasm-add-missing-prototypes                                        - Add prototypes to prototypes-less functions
      --wasm-argument-move                                                 - Move ARGUMENT instructions for WebAssembly
      --wasm-cfg-sort                                                      - Reorders blocks in topological order
      --wasm-cfg-stackify                                                  - Insert BLOCK/LOOP/TRY markers for WebAssembly scopes
      --wasm-debug-fixup                                                   - Ensures debug_value's that have been stackified become stack relative
      --wasm-exception-info                                                - WebAssembly Exception Information
      --wasm-explicit-locals                                               - Convert registers to WebAssembly locals
      --wasm-fix-function-bitcasts                                         - Fix mismatching bitcasts for WebAssembly
      --wasm-fix-irreducible-control-flow                                  - Removes irreducible control flow
      --wasm-late-eh-prepare                                               - WebAssembly Late Exception Preparation
      --wasm-lower-br_unless                                               - Lowers br_unless into inverted br_if
      --wasm-lower-em-ehsjlj                                               - WebAssembly Lower Emscripten Exceptions / Setjmp / Longjmp
      --wasm-lower-global-dtors                                            - Lower @llvm.global_dtors for WebAssembly
      --wasm-mclower-prepass                                               - Collects information ahead of time for MC lowering
      --wasm-mem-intrinsic-results                                         - Optimize memory intrinsic result values for WebAssembly
      --wasm-nullify-dbg-value-lists                                       - WebAssembly Nullify DBG_VALUE_LISTs
      --wasm-optimize-live-intervals                                       - Optimize LiveIntervals for WebAssembly
      --wasm-optimize-returned                                             - Optimize calls with "returned" attributes for WebAssembly
      --wasm-peephole                                                      - WebAssembly peephole optimizations
      --wasm-prepare-for-live-intervals                                    - Fix up code for LiveIntervals
      --wasm-reg-coloring                                                  - Minimize number of registers used
      --wasm-reg-numbering                                                 - Assigns WebAssembly register numbers for virtual registers
      --wasm-reg-stackify                                                  - Reorder instructions to use the WebAssembly value stack
      --wasm-replace-phys-regs                                             - Replace physical registers with virtual registers
      --wasm-set-p2align-operands                                          - Set the p2align operands for WebAssembly loads and stores
      --wasmehprepare                                                      - Prepare WebAssembly exceptions
      --wholeprogramdevirt                                                 - Whole program devirtualization
      --winehprepare                                                       - Prepare Windows exceptions
      --write-bitcode                                                      - Write Bitcode
      --x86-avoid-SFB                                                      - Machine code sinking
      --x86-avoid-trailing-call                                            - X86 avoid trailing call pass
      --x86-cf-opt                                                         - X86 Call Frame Optimization
      --x86-cmov-conversion                                                - X86 cmov Conversion
      --x86-codegen                                                        - X86 FP Stackifier
      --x86-domain-reassignment                                            - X86 Domain Reassignment Pass
      --x86-evex-to-vex-compress                                           - Compressing EVEX instrs to VEX encoding when possible
      --x86-execution-domain-fix                                           - X86 Execution Domain Fix
      --x86-fixup-LEAs                                                     - X86 LEA Fixup
      --x86-fixup-bw-insts                                                 - X86 Byte/Word Instruction Fixup
      --x86-fixup-setcc                                                    - x86-fixup-setcc
      --x86-flags-copy-lowering                                            - X86 EFLAGS copy lowering
      --x86-lvi-load                                                       - X86 LVI load hardening
      --x86-lvi-ret                                                        - X86 LVI ret hardener
      --x86-optimize-LEAs                                                  - X86 optimize LEA pass
      --x86-partial-reduction                                              - X86 Partial Reduction
      --x86-pseudo                                                         - X86 pseudo instruction expansion pass
      --x86-seses                                                          - X86 Speculative Execution Side Effect Suppression
      --x86-slh                                                            - X86 speculative load hardener
      --x86-winehstate                                                     - Insert stores for EH state numbers
  --skip-ret-exit-block                                                 - Suppress counter promotion if exit blocks contain ret.
  --speculative-counter-promotion-max-exiting=<uint>                    - The max number of exiting blocks of a loop to allow  speculative counter promotion
  --speculative-counter-promotion-to-loop                               - When the option is false, if the target block is in a loop, the promotion will be disallowed unless the promoted counter  update can be further/iteratively promoted into an acyclic  region.
  --split-machine-functions                                             - Split out cold basic blocks from machine functions based on profile information
  --stack-size-section                                                  - Emit a section containing stack size metadata
  --stack-symbol-ordering                                               - Order local stack symbols.
  --stackrealign                                                        - Force align the stack to the minimum alignment
  --strict-dwarf                                                        - use strict dwarf
  --strip-debug                                                         - Strip debugger symbol info from translation unit
  --strip-named-metadata                                                - Strip module-level named metadata
  --summary-file=<string>                                               - The summary file to use for function importing.
  --swift-async-fp=<value>                                              - Determine when the Swift async frame pointer should be set
    =auto                                                               -   Determine based on deployment target
    =always                                                             -   Always set the bit
    =never                                                              -   Never set the bit
  --tail-predication=<value>                                            - MVE tail-predication pass options
    =disabled                                                           -   Don't tail-predicate loops
    =enabled-no-reductions                                              -   Enable tail-predication, but not for reduction loops
    =enabled                                                            -   Enable tail-predication, including reduction loops
    =force-enabled-no-reductions                                        -   Enable tail-predication, but not for reduction loops, and force this which might be unsafe
    =force-enabled                                                      -   Enable tail-predication, including reduction loops, and force this which might be unsafe
  --tailcallopt                                                         - Turn fastcc calls into tail calls by (potentially) changing ABI.
  --thin-link-bitcode-file=<filename>                                   - A file in which to write minimized bitcode for the thin link only
  --thinlto-assume-merged                                               - Assume the input has already undergone ThinLTO function importing and the other pre-optimization pipeline changes.
  --thinlto-bc                                                          - Write output as ThinLTO-ready bitcode
  --thinlto-split-lto-unit                                              - Enable splitting of a ThinLTO LTOUnit
  --thread-model=<value>                                                - Choose threading model
    =posix                                                              -   POSIX thread model
    =single                                                             -   Single thread model
  --threads=<int>                                                       - 
  --time-trace                                                          - Record time trace
  --time-trace-file=<filename>                                          - Specify time trace file destination
  --tls-size=<uint>                                                     - Bit size of immediate TLS offsets
  --unique-basic-block-section-names                                    - Give unique names to every basic block section
  --unique-section-names                                                - Give unique names to every section
  --use-ctors                                                           - Use .ctors instead of .init_array.
  --vec-extabi                                                          - Enable the AIX Extended Altivec ABI.
  --verify-debuginfo-preserve                                           - Start the pipeline with collecting and end it with checking of debug info preservation.
  --verify-di-preserve-export=<filename>                                - Export debug info preservation failures into specified (JSON) file (should be abs path as we use append mode to insert new JSON objects)
  --verify-each                                                         - Verify after each transform
  --verify-each-debuginfo-preserve                                      - Start each pass with collecting and end it with checking of debug info preservation.
  --verify-region-info                                                  - Verify region info (time consuming)
  --vp-counters-per-site=<number>                                       - The average number of profile counters allocated per value profiling site.
  --vp-static-alloc                                                     - Do static counter allocation for value profiler
  --wasm-enable-eh                                                      - WebAssembly exception handling
  --wasm-enable-sjlj                                                    - WebAssembly setjmp/longjmp handling
  --x86-align-branch=<string>                                           - Specify types of branches to align (plus separated list of types):
                                                                          jcc      indicates conditional jumps
                                                                          fused    indicates fused conditional jumps
                                                                          jmp      indicates direct unconditional jumps
                                                                          call     indicates direct and indirect calls
                                                                          ret      indicates rets
                                                                          indirect indicates indirect unconditional jumps
  --x86-align-branch-boundary=<uint>                                    - Control how the assembler should align branches with NOP. If the boundary's size is not 0, it should be a power of 2 and no less than 32. Branches will be aligned to prevent from being across or against the boundary of specified size. The default value 0 does not align branches.
  --x86-branches-within-32B-boundaries                                  - Align selected instructions to mitigate negative performance impact of Intel's micro code update for errata skx102.  May break assumptions about labels corresponding to particular instructions, and should be used with caution.
  --x86-pad-max-prefix-size=<uint>                                      - Maximum number of prefixes to use for padding
  --xcoff-traceback-table                                               - Emit the XCOFF traceback table

Generic Options:

  --help                                                                - Display available options (--help-hidden for more)
  --help-list                                                           - Display list of available options (--help-list-hidden for more)
  --version                                                             - Display the version of this program

Polly Options:
Configure the polly loop optimizer

  --polly                                                               - Enable the polly optimizer (with -O1, -O2 or -O3)
  --polly-2nd-level-tiling                                              - Enable a 2nd level loop of loop tiling
  --polly-ast-print-accesses                                            - Print memory access functions
  --polly-context=<isl parameter set>                                   - Provide additional constraints on the context parameters
  --polly-dce-precise-steps=<int>                                       - The number of precise steps between two approximating iterations. (A value of -1 schedules another approximation stage before the actual dead code elimination.
  --polly-delicm-max-ops=<int>                                          - Maximum number of isl operations to invest for lifetime analysis; 0=no limit
  --polly-detect-full-functions                                         - Allow the detection of full functions
  --polly-dump-after                                                    - Dump module after Polly transformations into a file suffixed with "-after"
  --polly-dump-after-file=<string>                                      - Dump module after Polly transformations to the given file
  --polly-dump-before                                                   - Dump module before Polly transformations into a file suffixed with "-before"
  --polly-dump-before-file=<string>                                     - Dump module before Polly transformations to the given file
  --polly-enable-simplify                                               - Simplify SCoP after optimizations
  --polly-ignore-func=<string>                                          - Ignore functions that match a regex. Multiple regexes can be comma separated. Scop detection will ignore all functions that match ANY of the regexes provided.
  --polly-isl-arg=<argument>                                            - Option passed to ISL
  --polly-on-isl-error-abort                                            - Abort if an isl error is encountered
  --polly-only-func=<string>                                            - Only run on functions that match a regex. Multiple regexes can be comma separated. Scop detection will run on all functions that match ANY of the regexes provided.
  --polly-only-region=<identifier>                                      - Only run on certain regions (The provided identifier must appear in the name of the region's entry block
  --polly-only-scop-detection                                           - Only run scop detection, but no other optimizations
  --polly-optimized-scops                                               - Polly - Dump polyhedral description of Scops optimized with the isl scheduling optimizer and the set of post-scheduling transformations is applied on the schedule tree
  --polly-parallel                                                      - Generate thread parallel code (isl codegen only)
  --polly-parallel-force                                                - Force generation of thread parallel code ignoring any cost model
  --polly-pattern-matching-based-opts                                   - Perform optimizations based on pattern matching
  --polly-postopts                                                      - Apply post-rescheduling optimizations such as tiling (requires -polly-reschedule)
  --polly-pragma-based-opts                                             - Apply user-directed transformation from metadata
  --polly-pragma-ignore-depcheck                                        - Skip the dependency check for pragma-based transformations
  --polly-process-unprofitable                                          - Process scops that are unlikely to benefit from Polly optimizations.
  --polly-register-tiling                                               - Enable register tiling
  --polly-report                                                        - Print information about the activities of Polly
  --polly-reschedule                                                    - Optimize SCoPs using ISL
  --polly-show                                                          - Highlight the code regions that will be optimized in a (CFG BBs and LLVM-IR instructions)
  --polly-show-only                                                     - Highlight the code regions that will be optimized in a (CFG only BBs)
  --polly-stmt-granularity=<value>                                      - Algorithm to use for splitting basic blocks into multiple statements
    =bb                                                                 -   One statement per basic block
    =scalar-indep                                                       -   Scalar independence heuristic
    =store                                                              -   Store-level granularity
  --polly-target=<value>                                                - The hardware to target
    =cpu                                                                -   generate CPU code
  --polly-tiling                                                        - Enable loop tiling
  --polly-vectorizer=<value>                                            - Select the vectorization strategy
    =none                                                               -   No Vectorization
    =polly                                                              -   Polly internal vectorizer
    =stripmine                                                          -   Strip-mine outer loops for the loop-vectorizer to trigger
```

***

**sanstats**

```
:~# sanstats -h
OVERVIEW: Sanitizer Statistics Processing Tool
USAGE: sanstats [options] <filename>

OPTIONS:

Color Options:

  --color                                            - Use colors in output (default=autodetect)

General options:

  --aarch64-neon-syntax=<value>                      - Choose style of NEON code to emit from AArch64 backend:
    =generic                                         -   Emit generic NEON assembly
    =apple                                           -   Emit Apple-style NEON assembly
  --aarch64-use-aa                                   - Enable the use of AA during codegen.
  --abort-on-max-devirt-iterations-reached           - Abort when the max iterations for devirtualization CGSCC repeat pass is reached
  --allow-ginsert-as-artifact                        - Allow G_INSERT to be considered an artifact. Hack around AMDGPU test infinite loops.
  --amdgpu-bypass-slow-div                           - Skip 64-bit divide for dynamic 32-bit values
  --amdgpu-disable-loop-alignment                    - Do not align and prefetch loops
  --amdgpu-disable-power-sched                       - Disable scheduling to minimize mAI power bursts
  --amdgpu-dpp-combine                               - Enable DPP combiner
  --amdgpu-dump-hsa-metadata                         - Dump AMDGPU HSA Metadata
  --amdgpu-enable-flat-scratch                       - Use flat scratch instructions
  --amdgpu-enable-merge-m0                           - Merge and hoist M0 initializations
  --amdgpu-promote-alloca-to-vector-limit=<uint>     - Maximum byte size to consider promote alloca to vector
  --amdgpu-sdwa-peephole                             - Enable SDWA peepholer
  --amdgpu-use-aa-in-codegen                         - Enable the use of AA during codegen.
  --amdgpu-verify-hsa-metadata                       - Verify AMDGPU HSA Metadata
  --amdgpu-vgpr-index-mode                           - Use GPR indexing mode instead of movrel for vector indexing
  --arm-add-build-attributes                         - 
  --arm-implicit-it=<value>                          - Allow conditional instructions outdside of an IT block
    =always                                          -   Accept in both ISAs, emit implicit ITs in Thumb
    =never                                           -   Warn in ARM, reject in Thumb
    =arm                                             -   Accept in ARM, reject in Thumb
    =thumb                                           -   Warn in ARM, emit implicit ITs in Thumb
  --asm-show-inst                                    - Emit internal instruction representation to assembly file
  --atomic-counter-update-promoted                   - Do counter update using atomic fetch add  for promoted counters only
  --atomic-first-counter                             - Use atomic fetch add for first counter in a function (usually the entry counter)
  --bounds-checking-single-trap                      - Use one trap block per function
  --cfg-hide-cold-paths=<number>                     - Hide blocks with relative frequency below the given value
  --cfg-hide-deoptimize-paths                        - 
  --cfg-hide-unreachable-paths                       - 
  --cost-kind=<value>                                - Target cost kind
    =throughput                                      -   Reciprocal throughput
    =latency                                         -   Instruction latency
    =code-size                                       -   Code size
    =size-latency                                    -   Code size and latency
  --debug-info-correlate                             - Use debug info to correlate profiles.
  --debugify-level=<value>                           - Kind of debug info to add
    =locations                                       -   Locations only
    =location+variables                              -   Locations and Variables
  --debugify-quiet                                   - Suppress verbose debugify output
  --demangle                                         - Print demangled function name.
  --disable-i2p-p2i-opt                              - Disables inttoptr/ptrtoint roundtrip optimization
  --disable-promote-alloca-to-lds                    - Disable promote alloca to LDS
  --disable-promote-alloca-to-vector                 - Disable promote alloca to vector
  --do-counter-promotion                             - Do counter register promotion
  --dot-cfg-mssa=<file name for generated dot file>  - file name for generated dot file
  --dwarf-version=<int>                              - Dwarf version
  --dwarf64                                          - Generate debugging info in the 64-bit DWARF format
  --emscripten-cxx-exceptions-allowed=<string>       - The list of function names in which Emscripten-style exception handling is enabled (see emscripten EMSCRIPTEN_CATCHING_ALLOWED options)
  --enable-cse-in-irtranslator                       - Should enable CSE in irtranslator
  --enable-cse-in-legalizer                          - Should enable CSE in Legalizer
  --enable-emscripten-cxx-exceptions                 - WebAssembly Emscripten-style exception handling
  --enable-emscripten-sjlj                           - WebAssembly Emscripten-style setjmp/longjmp handling
  --enable-gvn-hoist                                 - Enable the GVN hoisting pass (default = off)
  --enable-gvn-memdep                                - 
  --enable-gvn-sink                                  - Enable the GVN sinking pass (default = off)
  --enable-load-in-loop-pre                          - 
  --enable-load-pre                                  - 
  --enable-loop-simplifycfg-term-folding             - 
  --enable-name-compression                          - Enable name/filename string compression
  --enable-split-backedge-in-load-pre                - 
  --experimental-debug-variable-locations            - Use experimental new value-tracking variable locations
  --fatal-warnings                                   - Treat warnings as errors
  --fs-profile-debug-bw-threshold=<uint>             - Only show debug message if the source branch weight is greater  than this value.
  --fs-profile-debug-prob-diff-threshold=<uint>      - Only show debug message if the branch probility is greater than this value (in percentage).
  --generate-merged-base-profiles                    - When generating nested context-sensitive profiles, always generate extra base profile for function with all its context profiles merged into it.
  --gpsize=<uint>                                    - Global Pointer Addressing Size.  The default size is 8.
  --hash-based-counter-split                         - Rename counter variable of a comdat function based on cfg hash
  --hot-cold-split                                   - Enable hot-cold splitting pass
  --import-all-index                                 - Import all external functions in index.
  --incremental-linker-compatible                    - When used with filetype=obj, emit an object file which can be used with an incremental linker
  --instcombine-code-sinking                         - Enable code sinking
  --instcombine-guard-widening-window=<uint>         - How wide an instruction window to bypass looking for another guard
  --instcombine-max-iterations=<uint>                - Limit the maximum number of instruction combining iterations
  --instcombine-max-num-phis=<uint>                  - Maximum number phis to handle in intptr/ptrint folding
  --instcombine-maxarray-size=<uint>                 - Maximum array size considered when doing a combine
  --instcombine-negator-enabled                      - Should we attempt to sink negations?
  --instcombine-negator-max-depth=<uint>             - What is the maximal lookup depth when trying to check for viability of negation sinking.
  --instrprof-atomic-counter-update-all              - Make all profile counter updates atomic (for testing only)
  --internalize-public-api-file=<filename>           - A file containing list of symbol names to preserve
  --internalize-public-api-list=<list>               - A list of symbol names to preserve
  --iterative-counter-promotion                      - Allow counter promotion across the whole loop nest.
  --lto-embed-bitcode=<value>                        - Embed LLVM bitcode in object files produced by LTO
    =none                                            -   Do not embed
    =optimized                                       -   Embed after all optimization passes
    =post-merge-pre-opt                              -   Embed post merge, but before optimizations
  --lto-pass-remarks-filter=<regex>                  - Only record optimization remarks from passes whose names match the given regular expression
  --lto-pass-remarks-format=<format>                 - The format used for serializing remarks (default: YAML)
  --lto-pass-remarks-output=<filename>               - Output filename for pass remarks
  --matrix-default-layout=<value>                    - Sets the default matrix layout
    =column-major                                    -   Use column-major layout
    =row-major                                       -   Use row-major layout
  --max-counter-promotions=<int>                     - Max number of allowed counter promotions
  --max-counter-promotions-per-loop=<uint>           - Max number counter promotions per loop to avoid increasing register pressure too much
  --mc-relax-all                                     - When used with filetype=obj, relax all fixups in the emitted object file
  --mcabac                                           - tbd
  --merror-missing-parenthesis                       - Error for missing parenthesis around predicate registers
  --merror-noncontigious-register                    - Error for register names that aren't contigious
  --mhvx                                             - Enable Hexagon Vector eXtensions
  --mhvx=<value>                                     - Enable Hexagon Vector eXtensions
    =v60                                             -   Build for HVX v60
    =v62                                             -   Build for HVX v62
    =v65                                             -   Build for HVX v65
    =v66                                             -   Build for HVX v66
    =v67                                             -   Build for HVX v67
    =v68                                             -   Build for HVX v68
    =v69                                             -   Build for HVX v69
  --mips-compact-branches=<value>                    - MIPS Specific: Compact branch policy.
    =never                                           -   Do not use compact branches if possible.
    =optimal                                         -   Use compact branches where appropriate (default).
    =always                                          -   Always use compact branches if possible.
  --mips16-constant-islands                          - Enable mips16 constant islands.
  --mips16-hard-float                                - Enable mips16 hard float.
  --mir-strip-debugify-only                          - Should mir-strip-debug only strip debug info from debugified modules by default
  --mno-compound                                     - Disable looking for compound instructions for Hexagon
  --mno-fixup                                        - Disable fixing up resolved relocations for Hexagon
  --mno-ldc1-sdc1                                    - Expand double precision loads and stores to their single precision counterparts
  --mno-pairing                                      - Disable looking for duplex instructions for Hexagon
  --mwarn-missing-parenthesis                        - Warn for missing parenthesis around predicate registers
  --mwarn-noncontigious-register                     - Warn for register names that arent contigious
  --mwarn-sign-mismatch                              - Warn for mismatching a signed and unsigned value
  --no-deprecated-warn                               - Suppress all deprecated warnings
  --no-discriminators                                - Disable generation of discriminator information.
  --no-type-check                                    - Suppress type errors (Wasm)
  --no-warn                                          - Suppress all warnings
  --nvptx-sched4reg                                  - NVPTX Specific: schedule for register pressue
  --opaque-pointers                                  - Use opaque pointers
  --poison-checking-function-local                   - Check that returns are non-poison (for testing)
  --print-pipeline-passes                            - Print a '-passes' compatible string describing the pipeline (best-effort only).
  --r600-ir-structurize                              - Use StructurizeCFG IR pass
  --rdf-dump                                         - 
  --rdf-limit=<uint>                                 - 
  --runtime-counter-relocation                       - Enable relocating counters at runtime.
  --safepoint-ir-verifier-print-only                 - 
  --sample-profile-check-record-coverage=<N>         - Emit a warning if less than N% of records in the input profile are matched to the IR.
  --sample-profile-check-sample-coverage=<N>         - Emit a warning if less than N% of samples in the input profile are matched to the IR.
  --sample-profile-max-propagate-iterations=<uint>   - Maximum number of iterations to go through when propagating sample block/edge weights through the CFG.
  --skip-ret-exit-block                              - Suppress counter promotion if exit blocks contain ret.
  --speculative-counter-promotion-max-exiting=<uint> - The max number of exiting blocks of a loop to allow  speculative counter promotion
  --speculative-counter-promotion-to-loop            - When the option is false, if the target block is in a loop, the promotion will be disallowed unless the promoted counter  update can be further/iteratively promoted into an acyclic  region.
  --summary-file=<string>                            - The summary file to use for function importing.
  --tail-predication=<value>                         - MVE tail-predication pass options
    =disabled                                        -   Don't tail-predicate loops
    =enabled-no-reductions                           -   Enable tail-predication, but not for reduction loops
    =enabled                                         -   Enable tail-predication, including reduction loops
    =force-enabled-no-reductions                     -   Enable tail-predication, but not for reduction loops, and force this which might be unsafe
    =force-enabled                                   -   Enable tail-predication, including reduction loops, and force this which might be unsafe
  --thinlto-assume-merged                            - Assume the input has already undergone ThinLTO function importing and the other pre-optimization pipeline changes.
  --threads=<int>                                    - 
  --verify-region-info                               - Verify region info (time consuming)
  --vp-counters-per-site=<number>                    - The average number of profile counters allocated per value profiling site.
  --vp-static-alloc                                  - Do static counter allocation for value profiler
  --wasm-enable-eh                                   - WebAssembly exception handling
  --wasm-enable-sjlj                                 - WebAssembly setjmp/longjmp handling
  --x86-align-branch=<string>                        - Specify types of branches to align (plus separated list of types):
                                                       jcc      indicates conditional jumps
                                                       fused    indicates fused conditional jumps
                                                       jmp      indicates direct unconditional jumps
                                                       call     indicates direct and indirect calls
                                                       ret      indicates rets
                                                       indirect indicates indirect unconditional jumps
  --x86-align-branch-boundary=<uint>                 - Control how the assembler should align branches with NOP. If the boundary's size is not 0, it should be a power of 2 and no less than 32. Branches will be aligned to prevent from being across or against the boundary of specified size. The default value 0 does not align branches.
  --x86-branches-within-32B-boundaries               - Align selected instructions to mitigate negative performance impact of Intel's micro code update for errata skx102.  May break assumptions about labels corresponding to particular instructions, and should be used with caution.
  --x86-pad-max-prefix-size=<uint>                   - Maximum number of prefixes to use for padding

Generic Options:

  --help                                             - Display available options (--help-hidden for more)
  --help-list                                        - Display list of available options (--help-list-hidden for more)
  --version                                          - Display the version of this program

Polly Options:
Configure the polly loop optimizer

  --polly                                            - Enable the polly optimizer (with -O1, -O2 or -O3)
  --polly-2nd-level-tiling                           - Enable a 2nd level loop of loop tiling
  --polly-ast-print-accesses                         - Print memory access functions
  --polly-context=<isl parameter set>                - Provide additional constraints on the context parameters
  --polly-dce-precise-steps=<int>                    - The number of precise steps between two approximating iterations. (A value of -1 schedules another approximation stage before the actual dead code elimination.
  --polly-delicm-max-ops=<int>                       - Maximum number of isl operations to invest for lifetime analysis; 0=no limit
  --polly-detect-full-functions                      - Allow the detection of full functions
  --polly-dump-after                                 - Dump module after Polly transformations into a file suffixed with "-after"
  --polly-dump-after-file=<string>                   - Dump module after Polly transformations to the given file
  --polly-dump-before                                - Dump module before Polly transformations into a file suffixed with "-before"
  --polly-dump-before-file=<string>                  - Dump module before Polly transformations to the given file
  --polly-enable-simplify                            - Simplify SCoP after optimizations
  --polly-ignore-func=<string>                       - Ignore functions that match a regex. Multiple regexes can be comma separated. Scop detection will ignore all functions that match ANY of the regexes provided.
  --polly-isl-arg=<argument>                         - Option passed to ISL
  --polly-on-isl-error-abort                         - Abort if an isl error is encountered
  --polly-only-func=<string>                         - Only run on functions that match a regex. Multiple regexes can be comma separated. Scop detection will run on all functions that match ANY of the regexes provided.
  --polly-only-region=<identifier>                   - Only run on certain regions (The provided identifier must appear in the name of the region's entry block
  --polly-only-scop-detection                        - Only run scop detection, but no other optimizations
  --polly-optimized-scops                            - Polly - Dump polyhedral description of Scops optimized with the isl scheduling optimizer and the set of post-scheduling transformations is applied on the schedule tree
  --polly-parallel                                   - Generate thread parallel code (isl codegen only)
  --polly-parallel-force                             - Force generation of thread parallel code ignoring any cost model
  --polly-pattern-matching-based-opts                - Perform optimizations based on pattern matching
  --polly-postopts                                   - Apply post-rescheduling optimizations such as tiling (requires -polly-reschedule)
  --polly-pragma-based-opts                          - Apply user-directed transformation from metadata
  --polly-pragma-ignore-depcheck                     - Skip the dependency check for pragma-based transformations
  --polly-process-unprofitable                       - Process scops that are unlikely to benefit from Polly optimizations.
  --polly-register-tiling                            - Enable register tiling
  --polly-report                                     - Print information about the activities of Polly
  --polly-reschedule                                 - Optimize SCoPs using ISL
  --polly-show                                       - Highlight the code regions that will be optimized in a (CFG BBs and LLVM-IR instructions)
  --polly-show-only                                  - Highlight the code regions that will be optimized in a (CFG only BBs)
  --polly-stmt-granularity=<value>                   - Algorithm to use for splitting basic blocks into multiple statements
    =bb                                              -   One statement per basic block
    =scalar-indep                                    -   Scalar independence heuristic
    =store                                           -   Store-level granularity
  --polly-target=<value>                             - The hardware to target
    =cpu                                             -   generate CPU code
  --polly-tiling                                     - Enable loop tiling
  --polly-vectorizer=<value>                         - Select the vectorization strategy
    =none                                            -   No Vectorization
    =polly                                           -   Polly internal vectorizer
    =stripmine                                       -   Strip-mine outer loops for the loop-vectorizer to trigger
```

***

**verify-uselistorder**

```
:~# verify-uselistorder -h
OVERVIEW: llvm tool to verify use-list order

USAGE: verify-uselistorder [options] <input bitcode file>

OPTIONS:

Color Options:

  --color                                            - Use colors in output (default=autodetect)

General options:

  --aarch64-neon-syntax=<value>                      - Choose style of NEON code to emit from AArch64 backend:
    =generic                                         -   Emit generic NEON assembly
    =apple                                           -   Emit Apple-style NEON assembly
  --aarch64-use-aa                                   - Enable the use of AA during codegen.
  --abort-on-max-devirt-iterations-reached           - Abort when the max iterations for devirtualization CGSCC repeat pass is reached
  --allow-ginsert-as-artifact                        - Allow G_INSERT to be considered an artifact. Hack around AMDGPU test infinite loops.
  --amdgpu-bypass-slow-div                           - Skip 64-bit divide for dynamic 32-bit values
  --amdgpu-disable-loop-alignment                    - Do not align and prefetch loops
  --amdgpu-disable-power-sched                       - Disable scheduling to minimize mAI power bursts
  --amdgpu-dpp-combine                               - Enable DPP combiner
  --amdgpu-dump-hsa-metadata                         - Dump AMDGPU HSA Metadata
  --amdgpu-enable-flat-scratch                       - Use flat scratch instructions
  --amdgpu-enable-merge-m0                           - Merge and hoist M0 initializations
  --amdgpu-promote-alloca-to-vector-limit=<uint>     - Maximum byte size to consider promote alloca to vector
  --amdgpu-sdwa-peephole                             - Enable SDWA peepholer
  --amdgpu-use-aa-in-codegen                         - Enable the use of AA during codegen.
  --amdgpu-verify-hsa-metadata                       - Verify AMDGPU HSA Metadata
  --amdgpu-vgpr-index-mode                           - Use GPR indexing mode instead of movrel for vector indexing
  --arm-add-build-attributes                         - 
  --arm-implicit-it=<value>                          - Allow conditional instructions outdside of an IT block
    =always                                          -   Accept in both ISAs, emit implicit ITs in Thumb
    =never                                           -   Warn in ARM, reject in Thumb
    =arm                                             -   Accept in ARM, reject in Thumb
    =thumb                                           -   Warn in ARM, emit implicit ITs in Thumb
  --asm-show-inst                                    - Emit internal instruction representation to assembly file
  --atomic-counter-update-promoted                   - Do counter update using atomic fetch add  for promoted counters only
  --atomic-first-counter                             - Use atomic fetch add for first counter in a function (usually the entry counter)
  --bounds-checking-single-trap                      - Use one trap block per function
  --cfg-hide-cold-paths=<number>                     - Hide blocks with relative frequency below the given value
  --cfg-hide-deoptimize-paths                        - 
  --cfg-hide-unreachable-paths                       - 
  --cost-kind=<value>                                - Target cost kind
    =throughput                                      -   Reciprocal throughput
    =latency                                         -   Instruction latency
    =code-size                                       -   Code size
    =size-latency                                    -   Code size and latency
  --debug-info-correlate                             - Use debug info to correlate profiles.
  --debugify-level=<value>                           - Kind of debug info to add
    =locations                                       -   Locations only
    =location+variables                              -   Locations and Variables
  --debugify-quiet                                   - Suppress verbose debugify output
  --disable-i2p-p2i-opt                              - Disables inttoptr/ptrtoint roundtrip optimization
  --disable-promote-alloca-to-lds                    - Disable promote alloca to LDS
  --disable-promote-alloca-to-vector                 - Disable promote alloca to vector
  --do-counter-promotion                             - Do counter register promotion
  --dot-cfg-mssa=<file name for generated dot file>  - file name for generated dot file
  --dwarf-version=<int>                              - Dwarf version
  --dwarf64                                          - Generate debugging info in the 64-bit DWARF format
  --emscripten-cxx-exceptions-allowed=<string>       - The list of function names in which Emscripten-style exception handling is enabled (see emscripten EMSCRIPTEN_CATCHING_ALLOWED options)
  --enable-cse-in-irtranslator                       - Should enable CSE in irtranslator
  --enable-cse-in-legalizer                          - Should enable CSE in Legalizer
  --enable-emscripten-cxx-exceptions                 - WebAssembly Emscripten-style exception handling
  --enable-emscripten-sjlj                           - WebAssembly Emscripten-style setjmp/longjmp handling
  --enable-gvn-hoist                                 - Enable the GVN hoisting pass (default = off)
  --enable-gvn-memdep                                - 
  --enable-gvn-sink                                  - Enable the GVN sinking pass (default = off)
  --enable-load-in-loop-pre                          - 
  --enable-load-pre                                  - 
  --enable-loop-simplifycfg-term-folding             - 
  --enable-name-compression                          - Enable name/filename string compression
  --enable-split-backedge-in-load-pre                - 
  --experimental-debug-variable-locations            - Use experimental new value-tracking variable locations
  --fatal-warnings                                   - Treat warnings as errors
  --fs-profile-debug-bw-threshold=<uint>             - Only show debug message if the source branch weight is greater  than this value.
  --fs-profile-debug-prob-diff-threshold=<uint>      - Only show debug message if the branch probility is greater than this value (in percentage).
  --generate-merged-base-profiles                    - When generating nested context-sensitive profiles, always generate extra base profile for function with all its context profiles merged into it.
  --gpsize=<uint>                                    - Global Pointer Addressing Size.  The default size is 8.
  --hash-based-counter-split                         - Rename counter variable of a comdat function based on cfg hash
  --hot-cold-split                                   - Enable hot-cold splitting pass
  --import-all-index                                 - Import all external functions in index.
  --incremental-linker-compatible                    - When used with filetype=obj, emit an object file which can be used with an incremental linker
  --instcombine-code-sinking                         - Enable code sinking
  --instcombine-guard-widening-window=<uint>         - How wide an instruction window to bypass looking for another guard
  --instcombine-max-iterations=<uint>                - Limit the maximum number of instruction combining iterations
  --instcombine-max-num-phis=<uint>                  - Maximum number phis to handle in intptr/ptrint folding
  --instcombine-maxarray-size=<uint>                 - Maximum array size considered when doing a combine
  --instcombine-negator-enabled                      - Should we attempt to sink negations?
  --instcombine-negator-max-depth=<uint>             - What is the maximal lookup depth when trying to check for viability of negation sinking.
  --instrprof-atomic-counter-update-all              - Make all profile counter updates atomic (for testing only)
  --internalize-public-api-file=<filename>           - A file containing list of symbol names to preserve
  --internalize-public-api-list=<list>               - A list of symbol names to preserve
  --iterative-counter-promotion                      - Allow counter promotion across the whole loop nest.
  --lto-embed-bitcode=<value>                        - Embed LLVM bitcode in object files produced by LTO
    =none                                            -   Do not embed
    =optimized                                       -   Embed after all optimization passes
    =post-merge-pre-opt                              -   Embed post merge, but before optimizations
  --lto-pass-remarks-filter=<regex>                  - Only record optimization remarks from passes whose names match the given regular expression
  --lto-pass-remarks-format=<format>                 - The format used for serializing remarks (default: YAML)
  --lto-pass-remarks-output=<filename>               - Output filename for pass remarks
  --matrix-default-layout=<value>                    - Sets the default matrix layout
    =column-major                                    -   Use column-major layout
    =row-major                                       -   Use row-major layout
  --max-counter-promotions=<int>                     - Max number of allowed counter promotions
  --max-counter-promotions-per-loop=<uint>           - Max number counter promotions per loop to avoid increasing register pressure too much
  --mc-relax-all                                     - When used with filetype=obj, relax all fixups in the emitted object file
  --mcabac                                           - tbd
  --merror-missing-parenthesis                       - Error for missing parenthesis around predicate registers
  --merror-noncontigious-register                    - Error for register names that aren't contigious
  --mhvx                                             - Enable Hexagon Vector eXtensions
  --mhvx=<value>                                     - Enable Hexagon Vector eXtensions
    =v60                                             -   Build for HVX v60
    =v62                                             -   Build for HVX v62
    =v65                                             -   Build for HVX v65
    =v66                                             -   Build for HVX v66
    =v67                                             -   Build for HVX v67
    =v68                                             -   Build for HVX v68
    =v69                                             -   Build for HVX v69
  --mips-compact-branches=<value>                    - MIPS Specific: Compact branch policy.
    =never                                           -   Do not use compact branches if possible.
    =optimal                                         -   Use compact branches where appropriate (default).
    =always                                          -   Always use compact branches if possible.
  --mips16-constant-islands                          - Enable mips16 constant islands.
  --mips16-hard-float                                - Enable mips16 hard float.
  --mir-strip-debugify-only                          - Should mir-strip-debug only strip debug info from debugified modules by default
  --mno-compound                                     - Disable looking for compound instructions for Hexagon
  --mno-fixup                                        - Disable fixing up resolved relocations for Hexagon
  --mno-ldc1-sdc1                                    - Expand double precision loads and stores to their single precision counterparts
  --mno-pairing                                      - Disable looking for duplex instructions for Hexagon
  --mwarn-missing-parenthesis                        - Warn for missing parenthesis around predicate registers
  --mwarn-noncontigious-register                     - Warn for register names that arent contigious
  --mwarn-sign-mismatch                              - Warn for mismatching a signed and unsigned value
  --no-deprecated-warn                               - Suppress all deprecated warnings
  --no-discriminators                                - Disable generation of discriminator information.
  --no-type-check                                    - Suppress type errors (Wasm)
  --no-warn                                          - Suppress all warnings
  --num-shuffles=<uint>                              - Number of times to shuffle and verify use-lists
  --nvptx-sched4reg                                  - NVPTX Specific: schedule for register pressue
  --opaque-pointers                                  - Use opaque pointers
  --poison-checking-function-local                   - Check that returns are non-poison (for testing)
  --print-pipeline-passes                            - Print a '-passes' compatible string describing the pipeline (best-effort only).
  --r600-ir-structurize                              - Use StructurizeCFG IR pass
  --rdf-dump                                         - 
  --rdf-limit=<uint>                                 - 
  --runtime-counter-relocation                       - Enable relocating counters at runtime.
  --safepoint-ir-verifier-print-only                 - 
  --sample-profile-check-record-coverage=<N>         - Emit a warning if less than N% of records in the input profile are matched to the IR.
  --sample-profile-check-sample-coverage=<N>         - Emit a warning if less than N% of samples in the input profile are matched to the IR.
  --sample-profile-max-propagate-iterations=<uint>   - Maximum number of iterations to go through when propagating sample block/edge weights through the CFG.
  --save-temps                                       - Save temp files
  --skip-ret-exit-block                              - Suppress counter promotion if exit blocks contain ret.
  --speculative-counter-promotion-max-exiting=<uint> - The max number of exiting blocks of a loop to allow  speculative counter promotion
  --speculative-counter-promotion-to-loop            - When the option is false, if the target block is in a loop, the promotion will be disallowed unless the promoted counter  update can be further/iteratively promoted into an acyclic  region.
  --summary-file=<string>                            - The summary file to use for function importing.
  --tail-predication=<value>                         - MVE tail-predication pass options
    =disabled                                        -   Don't tail-predicate loops
    =enabled-no-reductions                           -   Enable tail-predication, but not for reduction loops
    =enabled                                         -   Enable tail-predication, including reduction loops
    =force-enabled-no-reductions                     -   Enable tail-predication, but not for reduction loops, and force this which might be unsafe
    =force-enabled                                   -   Enable tail-predication, including reduction loops, and force this which might be unsafe
  --thinlto-assume-merged                            - Assume the input has already undergone ThinLTO function importing and the other pre-optimization pipeline changes.
  --threads=<int>                                    - 
  --verify-region-info                               - Verify region info (time consuming)
  --vp-counters-per-site=<number>                    - The average number of profile counters allocated per value profiling site.
  --vp-static-alloc                                  - Do static counter allocation for value profiler
  --wasm-enable-eh                                   - WebAssembly exception handling
  --wasm-enable-sjlj                                 - WebAssembly setjmp/longjmp handling
  --x86-align-branch=<string>                        - Specify types of branches to align (plus separated list of types):
                                                       jcc      indicates conditional jumps
                                                       fused    indicates fused conditional jumps
                                                       jmp      indicates direct unconditional jumps
                                                       call     indicates direct and indirect calls
                                                       ret      indicates rets
                                                       indirect indicates indirect unconditional jumps
  --x86-align-branch-boundary=<uint>                 - Control how the assembler should align branches with NOP. If the boundary's size is not 0, it should be a power of 2 and no less than 32. Branches will be aligned to prevent from being across or against the boundary of specified size. The default value 0 does not align branches.
  --x86-branches-within-32B-boundaries               - Align selected instructions to mitigate negative performance impact of Intel's micro code update for errata skx102.  May break assumptions about labels corresponding to particular instructions, and should be used with caution.
  --x86-pad-max-prefix-size=<uint>                   - Maximum number of prefixes to use for padding

Generic Options:

  --help                                             - Display available options (--help-hidden for more)
  --help-list                                        - Display list of available options (--help-list-hidden for more)
  --version                                          - Display the version of this program

Polly Options:
Configure the polly loop optimizer

  --polly                                            - Enable the polly optimizer (with -O1, -O2 or -O3)
  --polly-2nd-level-tiling                           - Enable a 2nd level loop of loop tiling
  --polly-ast-print-accesses                         - Print memory access functions
  --polly-context=<isl parameter set>                - Provide additional constraints on the context parameters
  --polly-dce-precise-steps=<int>                    - The number of precise steps between two approximating iterations. (A value of -1 schedules another approximation stage before the actual dead code elimination.
  --polly-delicm-max-ops=<int>                       - Maximum number of isl operations to invest for lifetime analysis; 0=no limit
  --polly-detect-full-functions                      - Allow the detection of full functions
  --polly-dump-after                                 - Dump module after Polly transformations into a file suffixed with "-after"
  --polly-dump-after-file=<string>                   - Dump module after Polly transformations to the given file
  --polly-dump-before                                - Dump module before Polly transformations into a file suffixed with "-before"
  --polly-dump-before-file=<string>                  - Dump module before Polly transformations to the given file
  --polly-enable-simplify                            - Simplify SCoP after optimizations
  --polly-ignore-func=<string>                       - Ignore functions that match a regex. Multiple regexes can be comma separated. Scop detection will ignore all functions that match ANY of the regexes provided.
  --polly-isl-arg=<argument>                         - Option passed to ISL
  --polly-on-isl-error-abort                         - Abort if an isl error is encountered
  --polly-only-func=<string>                         - Only run on functions that match a regex. Multiple regexes can be comma separated. Scop detection will run on all functions that match ANY of the regexes provided.
  --polly-only-region=<identifier>                   - Only run on certain regions (The provided identifier must appear in the name of the region's entry block
  --polly-only-scop-detection                        - Only run scop detection, but no other optimizations
  --polly-optimized-scops                            - Polly - Dump polyhedral description of Scops optimized with the isl scheduling optimizer and the set of post-scheduling transformations is applied on the schedule tree
  --polly-parallel                                   - Generate thread parallel code (isl codegen only)
  --polly-parallel-force                             - Force generation of thread parallel code ignoring any cost model
  --polly-pattern-matching-based-opts                - Perform optimizations based on pattern matching
  --polly-postopts                                   - Apply post-rescheduling optimizations such as tiling (requires -polly-reschedule)
  --polly-pragma-based-opts                          - Apply user-directed transformation from metadata
  --polly-pragma-ignore-depcheck                     - Skip the dependency check for pragma-based transformations
  --polly-process-unprofitable                       - Process scops that are unlikely to benefit from Polly optimizations.
  --polly-register-tiling                            - Enable register tiling
  --polly-report                                     - Print information about the activities of Polly
  --polly-reschedule                                 - Optimize SCoPs using ISL
  --polly-show                                       - Highlight the code regions that will be optimized in a (CFG BBs and LLVM-IR instructions)
  --polly-show-only                                  - Highlight the code regions that will be optimized in a (CFG only BBs)
  --polly-stmt-granularity=<value>                   - Algorithm to use for splitting basic blocks into multiple statements
    =bb                                              -   One statement per basic block
    =scalar-indep                                    -   Scalar independence heuristic
    =store                                           -   Store-level granularity
  --polly-target=<value>                             - The hardware to target
    =cpu                                             -   generate CPU code
  --polly-tiling                                     - Enable loop tiling
  --polly-vectorizer=<value>                         - Select the vectorization strategy
    =none                                            -   No Vectorization
    =polly                                           -   Polly internal vectorizer
    =stripmine                                       -   Strip-mine outer loops for the loop-vectorizer to trigger
```

***

**yaml2obj**

```
:~# yaml2obj -h
OVERVIEW: Create an object file from a YAML description
USAGE: yaml2obj [options] <input file>

OPTIONS:

Generic Options:

  --help             - Display available options (--help-hidden for more)
  --help-list        - Display list of available options (--help-list-hidden for more)
  --version          - Display the version of this program

yaml2obj Options:

  -D=<string>        - Defined the specified macros to their specified definition. The syntax is <macro>=<definition>
  --docnum=<uint>    - Read specified document from input (default = 1)
  --max-size=<ulong> - Sets the maximum allowed output size (0 means no limit) [ELF only]
  -o=<filename>      - Output filename
```

***

#### llvm-dev <a href="#llvm-dev" id="llvm-dev"></a>

The Low-Level Virtual Machine (LLVM) is a collection of libraries and tools that make it easy to build compilers, optimizers, Just-In-Time code generators, and many other compiler-related programs.

This is a dependency package providing the default libraries and headers.

**Installed size:** `25 KB`\
**How to install:** `sudo apt install llvm-dev`

<details>

<summary>Dependencies:</summary>

* llvm
* llvm-14-dev
* llvm-runtime

</details>

***

#### llvm-runtime <a href="#llvm-runtime" id="llvm-runtime"></a>

The Low-Level Virtual Machine (LLVM) is a collection of libraries and tools that make it easy to build compilers, optimizers, Just-In-Time code generators, and many other compiler-related programs.

This is a dependency package providing the default bytecode interpreter.

**Installed size:** `15 KB`\
**How to install:** `sudo apt install llvm-runtime`

<details>

<summary>Dependencies:</summary>

* llvm-14-runtime

</details>

**lli**

Manual page for lli 14

```
:~# lli -h
OVERVIEW: llvm interpreter & dynamic compiler

USAGE: lli [options] <input bitcode> <program arguments>...

OPTIONS:

Color Options:

  --color                                                               - Use colors in output (default=autodetect)

General options:

  -O=<char>                                                             - Optimization level. [-O0, -O1, -O2, or -O3] (default = '-O2')
  --aarch64-neon-syntax=<value>                                         - Choose style of NEON code to emit from AArch64 backend:
    =generic                                                            -   Emit generic NEON assembly
    =apple                                                              -   Emit Apple-style NEON assembly
  --aarch64-use-aa                                                      - Enable the use of AA during codegen.
  --abort-on-max-devirt-iterations-reached                              - Abort when the max iterations for devirtualization CGSCC repeat pass is reached
  --addrsig                                                             - Emit an address-significance table
  --align-loops=<uint>                                                  - Default alignment for loops
  --allow-ginsert-as-artifact                                           - Allow G_INSERT to be considered an artifact. Hack around AMDGPU test infinite loops.
  --amdgpu-bypass-slow-div                                              - Skip 64-bit divide for dynamic 32-bit values
  --amdgpu-disable-loop-alignment                                       - Do not align and prefetch loops
  --amdgpu-disable-power-sched                                          - Disable scheduling to minimize mAI power bursts
  --amdgpu-dpp-combine                                                  - Enable DPP combiner
  --amdgpu-dump-hsa-metadata                                            - Dump AMDGPU HSA Metadata
  --amdgpu-enable-flat-scratch                                          - Use flat scratch instructions
  --amdgpu-enable-merge-m0                                              - Merge and hoist M0 initializations
  --amdgpu-promote-alloca-to-vector-limit=<uint>                        - Maximum byte size to consider promote alloca to vector
  --amdgpu-sdwa-peephole                                                - Enable SDWA peepholer
  --amdgpu-use-aa-in-codegen                                            - Enable the use of AA during codegen.
  --amdgpu-verify-hsa-metadata                                          - Verify AMDGPU HSA Metadata
  --amdgpu-vgpr-index-mode                                              - Use GPR indexing mode instead of movrel for vector indexing
  --arm-add-build-attributes                                            - 
  --arm-implicit-it=<value>                                             - Allow conditional instructions outdside of an IT block
    =always                                                             -   Accept in both ISAs, emit implicit ITs in Thumb
    =never                                                              -   Warn in ARM, reject in Thumb
    =arm                                                                -   Accept in ARM, reject in Thumb
    =thumb                                                              -   Warn in ARM, emit implicit ITs in Thumb
  --asm-show-inst                                                       - Emit internal instruction representation to assembly file
  --atomic-counter-update-promoted                                      - Do counter update using atomic fetch add  for promoted counters only
  --atomic-first-counter                                                - Use atomic fetch add for first counter in a function (usually the entry counter)
  --basic-block-sections=<all | <function list (file)> | labels | none> - Emit basic blocks into separate sections
  --bounds-checking-single-trap                                         - Use one trap block per function
  --cfg-hide-cold-paths=<number>                                        - Hide blocks with relative frequency below the given value
  --cfg-hide-deoptimize-paths                                           - 
  --cfg-hide-unreachable-paths                                          - 
  --code-model=<value>                                                  - Choose code model
    =tiny                                                               -   Tiny code model
    =small                                                              -   Small code model
    =kernel                                                             -   Kernel code model
    =medium                                                             -   Medium code model
    =large                                                              -   Large code model
  --compile-threads=<uint>                                              - Choose the number of compile threads (jit-kind=orc-lazy only)
  --cost-kind=<value>                                                   - Target cost kind
    =throughput                                                         -   Reciprocal throughput
    =latency                                                            -   Instruction latency
    =code-size                                                          -   Code size
    =size-latency                                                       -   Code size and latency
  --data-sections                                                       - Emit data into separate sections
  --debug-entry-values                                                  - Enable debug info for the debug entry values.
  --debug-info-correlate                                                - Use debug info to correlate profiles.
  --debugger-tune=<value>                                               - Tune debug info for a particular debugger
    =gdb                                                                -   gdb
    =lldb                                                               -   lldb
    =dbx                                                                -   dbx
    =sce                                                                -   SCE targets (e.g. PS4)
  --debugify-level=<value>                                              - Kind of debug info to add
    =locations                                                          -   Locations only
    =location+variables                                                 -   Locations and Variables
  --debugify-quiet                                                      - Suppress verbose debugify output
  --denormal-fp-math=<value>                                            - Select which denormal numbers the code is permitted to require
    =ieee                                                               -   IEEE 754 denormal numbers
    =preserve-sign                                                      -   the sign of a  flushed-to-zero number is preserved in the sign of 0
    =positive-zero                                                      -   denormals are flushed to positive zero
  --denormal-fp-math-f32=<value>                                        - Select which denormal numbers the code is permitted to require for float
    =ieee                                                               -   IEEE 754 denormal numbers
    =preserve-sign                                                      -   the sign of a  flushed-to-zero number is preserved in the sign of 0
    =positive-zero                                                      -   denormals are flushed to positive zero
  --disable-i2p-p2i-opt                                                 - Disables inttoptr/ptrtoint roundtrip optimization
  --disable-lazy-compilation                                            - Disable JIT lazy compilation
  --disable-promote-alloca-to-lds                                       - Disable promote alloca to LDS
  --disable-promote-alloca-to-vector                                    - Disable promote alloca to vector
  --disable-tail-calls                                                  - Never emit tail calls
  --dlopen=<string>                                                     - Dynamic libraries to load before linking
  --do-counter-promotion                                                - Do counter register promotion
  --dot-cfg-mssa=<file name for generated dot file>                     - file name for generated dot file
  --dwarf-version=<int>                                                 - Dwarf version
  --dwarf64                                                             - Generate debugging info in the 64-bit DWARF format
  --emit-call-site-info                                                 - Emit call site debug information, if debug information is enabled.
  --emscripten-cxx-exceptions-allowed=<string>                          - The list of function names in which Emscripten-style exception handling is enabled (see emscripten EMSCRIPTEN_CATCHING_ALLOWED options)
  --emulated-tls                                                        - Use emulated TLS model
  --enable-cache-manager                                                - Use cache manager to save/load modules
  --enable-cse-in-irtranslator                                          - Should enable CSE in irtranslator
  --enable-cse-in-legalizer                                             - Should enable CSE in Legalizer
  --enable-emscripten-cxx-exceptions                                    - WebAssembly Emscripten-style exception handling
  --enable-emscripten-sjlj                                              - WebAssembly Emscripten-style setjmp/longjmp handling
  --enable-gvn-hoist                                                    - Enable the GVN hoisting pass (default = off)
  --enable-gvn-memdep                                                   - 
  --enable-gvn-sink                                                     - Enable the GVN sinking pass (default = off)
  --enable-load-in-loop-pre                                             - 
  --enable-load-pre                                                     - 
  --enable-loop-simplifycfg-term-folding                                - 
  --enable-name-compression                                             - Enable name/filename string compression
  --enable-no-infs-fp-math                                              - Enable FP math optimizations that assume no +-Infs
  --enable-no-nans-fp-math                                              - Enable FP math optimizations that assume no NaNs
  --enable-no-signed-zeros-fp-math                                      - Enable FP math optimizations that assume the sign of 0 is insignificant
  --enable-no-trapping-fp-math                                          - Enable setting the FP exceptions build attribute not to use exceptions
  --enable-split-backedge-in-load-pre                                   - 
  --enable-unsafe-fp-math                                               - Enable optimizations that may decrease FP precision
  --entry-function=<function>                                           - Specify the entry function (default = 'main') of the executable
  --exception-model=<value>                                             - exception model
    =default                                                            -   default exception handling model
    =dwarf                                                              -   DWARF-like CFI based exception handling
    =sjlj                                                               -   SjLj exception handling
    =arm                                                                -   ARM EHABI exceptions
    =wineh                                                              -   Windows exception model
    =wasm                                                               -   WebAssembly exception handling
  --experimental-debug-variable-locations                               - Use experimental new value-tracking variable locations
  --extra-archive=<input archive>                                       - Extra archive files to be loaded
  --extra-module=<input bitcode>                                        - Extra modules to be loaded
  --extra-object=<input object>                                         - Extra object files to be loaded
  --fake-argv0=<executable>                                             - Override the 'argv[0]' value passed into the executing program
  --fatal-warnings                                                      - Treat warnings as errors
  --filetype=<value>                                                    - Choose a file type (not all types are supported by all targets):
    =asm                                                                -   Emit an assembly ('.s') file
    =obj                                                                -   Emit a native object ('.o') file
    =null                                                               -   Emit nothing, for performance testing
  --float-abi=<value>                                                   - Choose float ABI type
    =default                                                            -   Target default float ABI type
    =soft                                                               -   Soft float ABI (implied by -soft-float)
    =hard                                                               -   Hard float ABI (uses FP registers)
  --force-dwarf-frame-section                                           - Always emit a debug frame section.
  --force-interpreter                                                   - Force interpretation: disable JIT
  --fp-contract=<value>                                                 - Enable aggressive formation of fused FP ops
    =fast                                                               -   Fuse FP ops whenever profitable
    =on                                                                 -   Only fuse 'blessed' FP ops.
    =off                                                                -   Only fuse FP ops when the result won't be affected.
  --frame-pointer=<value>                                               - Specify frame pointer elimination optimization
    =all                                                                -   Disable frame pointer elimination
    =non-leaf                                                           -   Disable frame pointer elimination for non-leaf frame
    =none                                                               -   Enable frame pointer elimination
  --fs-profile-debug-bw-threshold=<uint>                                - Only show debug message if the source branch weight is greater  than this value.
  --fs-profile-debug-prob-diff-threshold=<uint>                         - Only show debug message if the branch probility is greater than this value (in percentage).
  --function-sections                                                   - Emit functions into separate sections
  --generate-merged-base-profiles                                       - When generating nested context-sensitive profiles, always generate extra base profile for function with all its context profiles merged into it.
  --gpsize=<uint>                                                       - Global Pointer Addressing Size.  The default size is 8.
  --hash-based-counter-split                                            - Rename counter variable of a comdat function based on cfg hash
  --hot-cold-split                                                      - Enable hot-cold splitting pass
  --ignore-xcoff-visibility                                             - Not emit the visibility attribute for asm in AIX OS or give all symbols 'unspecified' visibility in XCOFF object file
  --import-all-index                                                    - Import all external functions in index.
  --incremental-linker-compatible                                       - When used with filetype=obj, emit an object file which can be used with an incremental linker
  --instcombine-code-sinking                                            - Enable code sinking
  --instcombine-guard-widening-window=<uint>                            - How wide an instruction window to bypass looking for another guard
  --instcombine-max-iterations=<uint>                                   - Limit the maximum number of instruction combining iterations
  --instcombine-max-num-phis=<uint>                                     - Maximum number phis to handle in intptr/ptrint folding
  --instcombine-maxarray-size=<uint>                                    - Maximum array size considered when doing a combine
  --instcombine-negator-enabled                                         - Should we attempt to sink negations?
  --instcombine-negator-max-depth=<uint>                                - What is the maximal lookup depth when trying to check for viability of negation sinking.
  --instrprof-atomic-counter-update-all                                 - Make all profile counter updates atomic (for testing only)
  --internalize-public-api-file=<filename>                              - A file containing list of symbol names to preserve
  --internalize-public-api-list=<list>                                  - A list of symbol names to preserve
  --iterative-counter-promotion                                         - Allow counter promotion across the whole loop nest.
  --jd=<string>                                                         - Specifies the JITDylib to be used for any subsequent -extra-module arguments.
  --jit-kind=<value>                                                    - Choose underlying JIT kind.
    =mcjit                                                              -   MCJIT
    =orc                                                                -   Orc JIT
    =orc-lazy                                                           -   Orc-based lazy JIT.
  --jit-linker=<value>                                                  - Choose the dynamic linker/loader.
    =default                                                            -   Default for platform and JIT-kind
    =rtdyld                                                             -   RuntimeDyld
    =jitlink                                                            -   Orc-specific linker
  --load=<pluginfilename>                                               - Load the specified plugin
  --lto-embed-bitcode=<value>                                           - Embed LLVM bitcode in object files produced by LTO
    =none                                                               -   Do not embed
    =optimized                                                          -   Embed after all optimization passes
    =post-merge-pre-opt                                                 -   Embed post merge, but before optimizations
  --lto-pass-remarks-filter=<regex>                                     - Only record optimization remarks from passes whose names match the given regular expression
  --lto-pass-remarks-format=<format>                                    - The format used for serializing remarks (default: YAML)
  --lto-pass-remarks-output=<filename>                                  - Output filename for pass remarks
  --march=<string>                                                      - Architecture to generate code for (see --version)
  --matrix-default-layout=<value>                                       - Sets the default matrix layout
    =column-major                                                       -   Use column-major layout
    =row-major                                                          -   Use row-major layout
  --mattr=<a1,+a2,-a3,...>                                              - Target specific attributes (-mattr=help for details)
  --max-counter-promotions=<int>                                        - Max number of allowed counter promotions
  --max-counter-promotions-per-loop=<uint>                              - Max number counter promotions per loop to avoid increasing register pressure too much
  --mc-relax-all                                                        - When used with filetype=obj, relax all fixups in the emitted object file
  --mcabac                                                              - tbd
  --mcjit-remote-process=<filename>                                     - Specify the filename of the process to launch for remote MCJIT execution.  If none is specified,
                                                                          	remote execution will be simulated in-process.
  --mcpu=<cpu-name>                                                     - Target a specific cpu type (-mcpu=help for details)
  --meabi=<value>                                                       - Set EABI type (default depends on triple):
    =default                                                            -   Triple default EABI version
    =4                                                                  -   EABI version 4
    =5                                                                  -   EABI version 5
    =gnu                                                                -   EABI GNU
  --merror-missing-parenthesis                                          - Error for missing parenthesis around predicate registers
  --merror-noncontigious-register                                       - Error for register names that aren't contigious
  --mhvx                                                                - Enable Hexagon Vector eXtensions
  --mhvx=<value>                                                        - Enable Hexagon Vector eXtensions
    =v60                                                                -   Build for HVX v60
    =v62                                                                -   Build for HVX v62
    =v65                                                                -   Build for HVX v65
    =v66                                                                -   Build for HVX v66
    =v67                                                                -   Build for HVX v67
    =v68                                                                -   Build for HVX v68
    =v69                                                                -   Build for HVX v69
  --mips-compact-branches=<value>                                       - MIPS Specific: Compact branch policy.
    =never                                                              -   Do not use compact branches if possible.
    =optimal                                                            -   Use compact branches where appropriate (default).
    =always                                                             -   Always use compact branches if possible.
  --mips16-constant-islands                                             - Enable mips16 constant islands.
  --mips16-hard-float                                                   - Enable mips16 hard float.
  --mir-strip-debugify-only                                             - Should mir-strip-debug only strip debug info from debugified modules by default
  --mno-compound                                                        - Disable looking for compound instructions for Hexagon
  --mno-fixup                                                           - Disable fixing up resolved relocations for Hexagon
  --mno-ldc1-sdc1                                                       - Expand double precision loads and stores to their single precision counterparts
  --mno-pairing                                                         - Disable looking for duplex instructions for Hexagon
  --mtriple=<string>                                                    - Override target triple for module
  --mwarn-missing-parenthesis                                           - Warn for missing parenthesis around predicate registers
  --mwarn-noncontigious-register                                        - Warn for register names that arent contigious
  --mwarn-sign-mismatch                                                 - Warn for mismatching a signed and unsigned value
  --no-deprecated-warn                                                  - Suppress all deprecated warnings
  --no-discriminators                                                   - Disable generation of discriminator information.
  --no-process-syms                                                     - Do not resolve lli process symbols in JIT'd code
  --no-type-check                                                       - Suppress type errors (Wasm)
  --no-warn                                                             - Suppress all warnings
  --no-xray-index                                                       - Don't emit xray_fn_idx section
  --nozero-initialized-in-bss                                           - Don't place zero-initialized symbols into bss section
  --nvptx-sched4reg                                                     - NVPTX Specific: schedule for register pressue
  --object-cache-dir=<string>                                           - Directory to store cached object files (must be user writable)
  --opaque-pointers                                                     - Use opaque pointers
  --per-module-lazy                                                     - Performs lazy compilation on whole module boundaries rather than individual functions
  --poison-checking-function-local                                      - Check that returns are non-poison (for testing)
  --print-pipeline-passes                                               - Print a '-passes' compatible string describing the pipeline (best-effort only).
  --r600-ir-structurize                                                 - Use StructurizeCFG IR pass
  --rdf-dump                                                            - 
  --rdf-limit=<uint>                                                    - 
  --relax-elf-relocations                                               - Emit GOTPCRELX/REX_GOTPCRELX instead of GOTPCREL on x86-64 ELF
  --relocation-model=<value>                                            - Choose relocation model
    =static                                                             -   Non-relocatable code
    =pic                                                                -   Fully relocatable, position independent code
    =dynamic-no-pic                                                     -   Relocatable external references, non-relocatable code
    =ropi                                                               -   Code and read-only data relocatable, accessed PC-relative
    =rwpi                                                               -   Read-write data relocatable, accessed relative to static base
    =ropi-rwpi                                                          -   Combination of ropi and rwpi
  --remote-mcjit                                                        - Execute MCJIT'ed code in a separate process.
  --runtime-counter-relocation                                          - Enable relocating counters at runtime.
  --safepoint-ir-verifier-print-only                                    - 
  --sample-profile-check-record-coverage=<N>                            - Emit a warning if less than N% of records in the input profile are matched to the IR.
  --sample-profile-check-sample-coverage=<N>                            - Emit a warning if less than N% of samples in the input profile are matched to the IR.
  --sample-profile-max-propagate-iterations=<uint>                      - Maximum number of iterations to go through when propagating sample block/edge weights through the CFG.
  --skip-ret-exit-block                                                 - Suppress counter promotion if exit blocks contain ret.
  --soft-float                                                          - Generate software floating point library calls
  --speculative-counter-promotion-max-exiting=<uint>                    - The max number of exiting blocks of a loop to allow  speculative counter promotion
  --speculative-counter-promotion-to-loop                               - When the option is false, if the target block is in a loop, the promotion will be disallowed unless the promoted counter  update can be further/iteratively promoted into an acyclic  region.
  --split-machine-functions                                             - Split out cold basic blocks from machine functions based on profile information
  --stack-size-section                                                  - Emit a section containing stack size metadata
  --stack-symbol-ordering                                               - Order local stack symbols.
  --stackrealign                                                        - Force align the stack to the minimum alignment
  --strict-dwarf                                                        - use strict dwarf
  --summary-file=<string>                                               - The summary file to use for function importing.
  --swift-async-fp=<value>                                              - Determine when the Swift async frame pointer should be set
    =auto                                                               -   Determine based on deployment target
    =always                                                             -   Always set the bit
    =never                                                              -   Never set the bit
  --tail-predication=<value>                                            - MVE tail-predication pass options
    =disabled                                                           -   Don't tail-predicate loops
    =enabled-no-reductions                                              -   Enable tail-predication, but not for reduction loops
    =enabled                                                            -   Enable tail-predication, including reduction loops
    =force-enabled-no-reductions                                        -   Enable tail-predication, but not for reduction loops, and force this which might be unsafe
    =force-enabled                                                      -   Enable tail-predication, including reduction loops, and force this which might be unsafe
  --tailcallopt                                                         - Turn fastcc calls into tail calls by (potentially) changing ABI.
  --thinlto-assume-merged                                               - Assume the input has already undergone ThinLTO function importing and the other pre-optimization pipeline changes.
  --thread-entry=<string>                                               - calls the given entry-point on a new thread (jit-kind=orc-lazy only)
  --thread-model=<value>                                                - Choose threading model
    =posix                                                              -   POSIX thread model
    =single                                                             -   Single thread model
  --threads=<int>                                                       - 
  --tls-size=<uint>                                                     - Bit size of immediate TLS offsets
  --unique-basic-block-section-names                                    - Give unique names to every basic block section
  --unique-section-names                                                - Give unique names to every section
  --use-ctors                                                           - Use .ctors instead of .init_array.
  --vec-extabi                                                          - Enable the AIX Extended Altivec ABI.
  --verify-region-info                                                  - Verify region info (time consuming)
  --vp-counters-per-site=<number>                                       - The average number of profile counters allocated per value profiling site.
  --vp-static-alloc                                                     - Do static counter allocation for value profiler
  --wasm-enable-eh                                                      - WebAssembly exception handling
  --wasm-enable-sjlj                                                    - WebAssembly setjmp/longjmp handling
  --x86-align-branch=<string>                                           - Specify types of branches to align (plus separated list of types):
                                                                          jcc      indicates conditional jumps
                                                                          fused    indicates fused conditional jumps
                                                                          jmp      indicates direct unconditional jumps
                                                                          call     indicates direct and indirect calls
                                                                          ret      indicates rets
                                                                          indirect indicates indirect unconditional jumps
  --x86-align-branch-boundary=<uint>                                    - Control how the assembler should align branches with NOP. If the boundary's size is not 0, it should be a power of 2 and no less than 32. Branches will be aligned to prevent from being across or against the boundary of specified size. The default value 0 does not align branches.
  --x86-branches-within-32B-boundaries                                  - Align selected instructions to mitigate negative performance impact of Intel's micro code update for errata skx102.  May break assumptions about labels corresponding to particular instructions, and should be used with caution.
  --x86-pad-max-prefix-size=<uint>                                      - Maximum number of prefixes to use for padding
  --xcoff-traceback-table                                               - Emit the XCOFF traceback table

Generic Options:

  --help                                                                - Display available options (--help-hidden for more)
  --help-list                                                           - Display list of available options (--help-list-hidden for more)
  --version                                                             - Display the version of this program

Polly Options:
Configure the polly loop optimizer

  --polly                                                               - Enable the polly optimizer (with -O1, -O2 or -O3)
  --polly-2nd-level-tiling                                              - Enable a 2nd level loop of loop tiling
  --polly-ast-print-accesses                                            - Print memory access functions
  --polly-context=<isl parameter set>                                   - Provide additional constraints on the context parameters
  --polly-dce-precise-steps=<int>                                       - The number of precise steps between two approximating iterations. (A value of -1 schedules another approximation stage before the actual dead code elimination.
  --polly-delicm-max-ops=<int>                                          - Maximum number of isl operations to invest for lifetime analysis; 0=no limit
  --polly-detect-full-functions                                         - Allow the detection of full functions
  --polly-dump-after                                                    - Dump module after Polly transformations into a file suffixed with "-after"
  --polly-dump-after-file=<string>                                      - Dump module after Polly transformations to the given file
  --polly-dump-before                                                   - Dump module before Polly transformations into a file suffixed with "-before"
  --polly-dump-before-file=<string>                                     - Dump module before Polly transformations to the given file
  --polly-enable-simplify                                               - Simplify SCoP after optimizations
  --polly-ignore-func=<string>                                          - Ignore functions that match a regex. Multiple regexes can be comma separated. Scop detection will ignore all functions that match ANY of the regexes provided.
  --polly-isl-arg=<argument>                                            - Option passed to ISL
  --polly-on-isl-error-abort                                            - Abort if an isl error is encountered
  --polly-only-func=<string>                                            - Only run on functions that match a regex. Multiple regexes can be comma separated. Scop detection will run on all functions that match ANY of the regexes provided.
  --polly-only-region=<identifier>                                      - Only run on certain regions (The provided identifier must appear in the name of the region's entry block
  --polly-only-scop-detection                                           - Only run scop detection, but no other optimizations
  --polly-optimized-scops                                               - Polly - Dump polyhedral description of Scops optimized with the isl scheduling optimizer and the set of post-scheduling transformations is applied on the schedule tree
  --polly-parallel                                                      - Generate thread parallel code (isl codegen only)
  --polly-parallel-force                                                - Force generation of thread parallel code ignoring any cost model
  --polly-pattern-matching-based-opts                                   - Perform optimizations based on pattern matching
  --polly-postopts                                                      - Apply post-rescheduling optimizations such as tiling (requires -polly-reschedule)
  --polly-pragma-based-opts                                             - Apply user-directed transformation from metadata
  --polly-pragma-ignore-depcheck                                        - Skip the dependency check for pragma-based transformations
  --polly-process-unprofitable                                          - Process scops that are unlikely to benefit from Polly optimizations.
  --polly-register-tiling                                               - Enable register tiling
  --polly-report                                                        - Print information about the activities of Polly
  --polly-reschedule                                                    - Optimize SCoPs using ISL
  --polly-show                                                          - Highlight the code regions that will be optimized in a (CFG BBs and LLVM-IR instructions)
  --polly-show-only                                                     - Highlight the code regions that will be optimized in a (CFG only BBs)
  --polly-stmt-granularity=<value>                                      - Algorithm to use for splitting basic blocks into multiple statements
    =bb                                                                 -   One statement per basic block
    =scalar-indep                                                       -   Scalar independence heuristic
    =store                                                              -   Store-level granularity
  --polly-target=<value>                                                - The hardware to target
    =cpu                                                                -   generate CPU code
  --polly-tiling                                                        - Enable loop tiling
  --polly-vectorizer=<value>                                            - Select the vectorization strategy
    =none                                                               -   No Vectorization
    =polly                                                              -   Polly internal vectorizer
    =stripmine                                                          -   Strip-mine outer loops for the loop-vectorizer to trigger
```

***

#### python3-clang <a href="#python3-clang" id="python3-clang"></a>

Clang project is a C, C++, Objective C and Objective C++ front-end based on the LLVM compiler. Its goal is to offer a replacement to the GNU Compiler Collection (GCC).

Clang implements all of the ISO C++ 1998, 11 and 14 standards and also provides most of the support of C++17.

This is a dependency package providing the Python binding to Clang.

**Installed size:** `13 KB`\
**How to install:** `sudo apt install python3-clang`

<details>

<summary>Dependencies:</summary>

* python3-clang-14

</details>

***

#### python3-lldb <a href="#python3-lldb" id="python3-lldb"></a>

LLDB is a next generation, high-performance debugger. It is built as a set of reusable components which highly leverage existing libraries in the larger LLVM Project, such as the Clang expression parser and LLVM disassembler.

This is a dependency package providing the Python binding to lldb.

**Installed size:** `13 KB`\
**How to install:** `sudo apt install python3-lldb`

<details>

<summary>Dependencies:</summary>

* python3-lldb-14

</details>

***

Updated on: 2023-Mar-08\


***
