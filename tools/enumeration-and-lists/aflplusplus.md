---
description: >-
  AFL+++: an open-source fuzz testing tool that uses advanced mutation
  algorithms, deep learning, and parallel fuzzing to quickly identify
  vulnerabilities in software.
---

# 🔎 aflplusplus

AFL+++, the advanced version of American Fuzzy Lop (AFL), is a powerful security tool for identifying vulnerabilities in software. It is an open-source software security testing tool that uses fuzz testing to find potential security flaws in code. AFL+++ was created to address the limitations of its predecessor, AFL, and provides an extensive set of features for better test coverage, faster feedback, and improved exploitability detection.

AFL+++ is a highly effective tool for identifying vulnerabilities in software. It works by inputting random data into an application, using various mutation techniques to modify the input data, and analyzing the results to determine if any vulnerabilities exist. AFL+++ provides advanced mutation algorithms, such as MOpt and QEMU mode, which optimize the input data to improve test coverage and reduce the time required for finding bugs.

One of the key features of AFL+++ is its ability to detect and prioritize exploitable bugs. This is done through a unique technique called "deep learning," which involves training the tool on real-world vulnerabilities to better identify them in new code. This helps developers to quickly identify high-risk vulnerabilities and prioritize their remediation efforts accordingly.

AFL+++ also provides a range of other advanced features, including coverage guidance, parallel fuzzing, and crash triage. Coverage guidance helps to ensure maximum code coverage by identifying areas that have not been tested and guiding the fuzzer to those areas. Parallel fuzzing allows multiple instances of AFL+++ to run simultaneously, reducing the time required for testing. Crash triage is a feature that helps to quickly identify the root cause of a crash and provide detailed information about the vulnerability.

Another key advantage of AFL+++ is its ease of use. It is designed to be user-friendly and easy to install, with comprehensive documentation and tutorials to guide users through the testing process. Additionally, AFL+++ supports a wide range of operating systems and architectures, making it a versatile tool for testing a variety of software applications.

In summary, AFL+++ is a powerful security testing tool that provides a range of advanced features for identifying and prioritizing vulnerabilities in software. With its advanced mutation algorithms, deep learning techniques, and range of other features, AFL+++ is an indispensable tool for software developers looking to improve the security of their applications.

### Packages and Binaries:

#### afl <a href="#afl" id="afl"></a>

This is a transitional package. It can safely be removed once afl++ is installed.

**Installed size:** `73 KB`\
**How to install:** `sudo apt install afl`

<details>

<summary>Dependencies:</summary>

* afl++

</details>

***

#### afl++ <a href="#afl-1" id="afl-1"></a>

American fuzzy lop is a fuzzer that employs compile-time instrumentation and genetic algorithms to automatically discover clean, interesting test cases that trigger new internal states in the targeted binary. This substantially improves the functional coverage for the fuzzed code. The compact synthesized corpora produced by the tool are also useful for seeding other, more labor- or resource-intensive testing regimes down the road.

afl++-fuzz is designed to be practical: it has modest performance overhead, uses a variety of highly effective fuzzing strategies, requires essentially no configuration, and seamlessly handles complex, real-world use cases - say, common image parsing or file compression libraries.

afl++ is a fork of the unmaintained afl.

**Installed size:** `2.29 MB`\
**How to install:** `sudo apt install afl++`

<details>

<summary>Dependencies:</summary>

* build-essential
* clang
* clang-14
* libc6
* libgcc-s1
* libpython3.11
* libstdc++6
* procps

</details>

**afl-analyze**

(unknown subject)

```
:~# afl-analyze -h
afl-analyze++4.04c by Michal Zalewski

afl-analyze [ options ] -- /path/to/target_app [ ... ]

Required parameters:
  -i file       - input test case to be analyzed by the tool

Execution control settings:
  -f file       - input file read by the tested program (stdin)
  -t msec       - timeout for each run (1000 ms)
  -m megs       - memory limit for child process (0 MB)
  -O            - use binary-only instrumentation (FRIDA mode)
  -Q            - use binary-only instrumentation (QEMU mode)
  -U            - use unicorn-based instrumentation (Unicorn mode)
  -W            - use qemu-based instrumentation with Wine (Wine mode)

Analysis settings:
  -e            - look for edge coverage only, ignore hit counts

For additional tips, please consult /usr/share/doc/afl/README.md.

Environment variables used:
TMPDIR: directory to use for temporary input files
ASAN_OPTIONS: custom settings for ASAN
              (must contain abort_on_error=1 and symbolize=0)
MSAN_OPTIONS: custom settings for MSAN
              (must contain exitcode=86 and symbolize=0)
AFL_ANALYZE_HEX: print file offsets in hexadecimal instead of decimal
AFL_MAP_SIZE: the shared memory size for that target. must be >= the size
              the target was compiled for
AFL_PRELOAD: LD_PRELOAD / DYLD_INSERT_LIBRARIES settings for target
AFL_SKIP_BIN_CHECK: skip checking the location of and the target
```

***

**afl-c++**

Afl-c++ (8) - afl-cc++4.04c by Michal Zalewski, Laszlo Szekeres, Marc Heuse afl-cc

```
:~# afl-c++ --help
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

**afl-cc**

Afl-cc++4.04c by Michal Zalewski, Laszlo Szekeres, Marc Heuse afl-cc

```
:~# afl-cc --help
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

**afl-clang**

```
:~# afl-clang --help
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

**afl-clang++**

```
:~# afl-clang++ --help
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

**afl-clang-fast**

Afl-cc++4.04c by Michal Zalewski, Laszlo Szekeres, Marc Heuse afl-cc

```
:~# afl-clang-fast --help
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

**afl-clang-fast++**

Afl-clang-fast++ (8) - afl-cc++4.04c by Michal Zalewski, Laszlo Szekeres, Marc Heuse afl-cc

```
:~# afl-clang-fast++ --help
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

**afl-clang-lto**

Afl-cc++4.04c by Michal Zalewski, Laszlo Szekeres, Marc Heuse afl-cc

```
:~# afl-clang-lto --help
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

**afl-clang-lto++**

Afl-clang-lto++ (8) - afl-cc++4.04c by Michal Zalewski, Laszlo Szekeres, Marc Heuse afl-cc

```
:~# afl-clang-lto++ --help
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

**afl-cmin**

(unknown subject)

```
:~# afl-cmin -h
corpus minimization tool for afl++ (awk version)

afl-cmin [ options ] -- /path/to/target_app [ ... ]

Required parameters:
  -i dir        - input directory with starting corpus
  -o dir        - output directory for minimized files

Execution control settings:
  -f file       - location read by the fuzzed program (stdin)
  -m megs       - memory limit for child process ( MB)
  -t msec       - run time limit for child process (default: none)
  -O            - use binary-only instrumentation (FRIDA mode)
  -Q            - use binary-only instrumentation (QEMU mode)
  -U            - use unicorn-based instrumentation (unicorn mode)

Minimization settings:
  -A            - allow crashes and timeouts (not recommended)
  -C            - keep crashing inputs, reject everything else
  -e            - solve for edge coverage only, ignore hit counts

For additional tips, please consult README.md

Environment variables used:
AFL_ALLOW_TMP: allow unsafe use of input/output directories under {/var}/tmp
AFL_CRASH_EXITCODE: optional child exit code to be interpreted as crash
AFL_FORKSRV_INIT_TMOUT: time the fuzzer waits for the forkserver to come up
AFL_KEEP_TRACES: leave the temporary <out_dir>/.traces directory
AFL_KILL_SIGNAL: Signal delivered to child processes on timeout (default: SIGKILL)
AFL_NO_FORKSRV: run target via execve instead of using the forkserver
AFL_CMIN_ALLOW_ANY: write tuples for crashing inputs also
AFL_PATH: path for the afl-showmap binary if not found anywhere in PATH
AFL_PRINT_FILENAMES: If set, the filename currently processed will be printed to stdout
AFL_SKIP_BIN_CHECK: skip afl instrumentation checks for target binary

```

***

**afl-cmin.bash**

(unknown subject)

```
:~# afl-cmin.bash -h
Usage: /usr/bin/afl-cmin.bash [ options ] -- /path/to/target_app [ ... ]

Required parameters:

  -i dir        - input directory with the starting corpus
  -o dir        - output directory for minimized files

Execution control settings:

  -f file       - location read by the fuzzed program (stdin)
  -m megs       - memory limit for child process (none MB)
  -t msec       - run time limit for child process (none)
  -O            - use binary-only instrumentation (FRIDA mode)
  -Q            - use binary-only instrumentation (QEMU mode)
  -U            - use unicorn-based instrumentation (Unicorn mode)
  
Minimization settings:

  -A            - allow crashing and timeout inputs
  -C            - keep crashing inputs, reject everything else
  -e            - solve for edge coverage only, ignore hit counts

For additional tips, please consult README.md.

Environment variables used:
AFL_KEEP_TRACES: leave the temporary <out_dir>\.traces directory
AFL_NO_FORKSRV: run target via execve instead of using the forkserver
AFL_PATH: last resort location to find the afl-showmap binary
AFL_SKIP_BIN_CHECK: skip check for target binary
```

***

**afl-fuzz**

(unknown subject)

```
:~# afl-fuzz --help
afl-fuzz++4.04c based on afl by Michal Zalewski and a large online community

afl-fuzz [ options ] -- /path/to/fuzzed_app [ ... ]

Required parameters:
  -i dir        - input directory with test cases
  -o dir        - output directory for fuzzer findings

Execution control settings:
  -p schedule   - power schedules compute a seed's performance score:
                  fast(default), explore, exploit, seek, rare, mmopt, coe, lin
                  quad -- see docs/FAQ.md for more information
  -f file       - location read by the fuzzed program (default: stdin or @@)
  -t msec       - timeout for each run (auto-scaled, default 1000 ms). Add a '+'
                  to auto-calculate the timeout, the value being the maximum.
  -m megs       - memory limit for child process (0 MB, 0 = no limit [default])
  -O            - use binary-only instrumentation (FRIDA mode)
  -Q            - use binary-only instrumentation (QEMU mode)
  -U            - use unicorn-based instrumentation (Unicorn mode)
  -W            - use qemu-based instrumentation with Wine (Wine mode)
  -X            - use VM fuzzing (NYX mode - standalone mode)
  -Y            - use VM fuzzing (NYX mode - multiple instances mode)

Mutator settings:
  -g minlength  - set min length of generated fuzz input (default: 1)
  -G maxlength  - set max length of generated fuzz input (default: 1048576)
  -D            - enable deterministic fuzzing (once per queue entry)
  -L minutes    - use MOpt(imize) mode and set the time limit for entering the
                  pacemaker mode (minutes of no new finds). 0 = immediately,
                  -1 = immediately and together with normal mutation.
                  See docs/README.MOpt.md
  -c program    - enable CmpLog by specifying a binary compiled for it.
                  if using QEMU/FRIDA or the fuzzing target is compiled
                  for CmpLog then just use -c 0.
  -l cmplog_opts - CmpLog configuration values (e.g. "2AT"):
                  1=small files, 2=larger files (default), 3=all files,
                  A=arithmetic solving, T=transformational solving.

Fuzzing behavior settings:
  -Z            - sequential queue selection instead of weighted random
  -N            - do not unlink the fuzzing input file (for devices etc.)
  -n            - fuzz without instrumentation (non-instrumented mode)
  -x dict_file  - fuzzer dictionary (see README.md, specify up to 4 times)

Test settings:
  -s seed       - use a fixed seed for the RNG
  -V seconds    - fuzz for a specified time then terminate
  -E execs      - fuzz for an approx. no. of total executions then terminate
                  Note: not precise and can have several more executions.

Other stuff:
  -M/-S id      - distributed mode (-M sets -Z and disables trimming)
                  see docs/fuzzing_in_depth.md#c-using-multiple-cores
                  for effective recommendations for parallel fuzzing.
  -F path       - sync to a foreign fuzzer queue directory (requires -M, can
                  be specified up to 32 times)
  -T text       - text banner to show on the screen
  -I command    - execute this command/script when a new crash is found
  -C            - crash exploration mode (the peruvian rabbit thing)
  -b cpu_id     - bind the fuzzing process to the specified CPU core (0-...)
  -e ext        - file extension for the fuzz test input file (if needed)

Environment variables used:
LD_BIND_LAZY: do not set LD_BIND_NOW env var for target
ASAN_OPTIONS: custom settings for ASAN
              (must contain abort_on_error=1 and symbolize=0)
MSAN_OPTIONS: custom settings for MSAN
              (must contain exitcode=86 and symbolize=0)
AFL_AUTORESUME: resume fuzzing if directory specified by -o already exists
AFL_BENCH_JUST_ONE: run the target just once
AFL_BENCH_UNTIL_CRASH: exit soon when the first crashing input has been found
AFL_CMPLOG_ONLY_NEW: do not run cmplog on initial testcases (good for resumes!)
AFL_CRASH_EXITCODE: optional child exit code to be interpreted as crash
AFL_CUSTOM_MUTATOR_LIBRARY: lib with afl_custom_fuzz() to mutate inputs
AFL_CUSTOM_MUTATOR_ONLY: avoid AFL++'s internal mutators
AFL_CYCLE_SCHEDULES: after completing a cycle, switch to a different -p schedule
AFL_DEBUG: extra debugging output for Python mode trimming
AFL_DEBUG_CHILD: do not suppress stdout/stderr from target
AFL_DISABLE_TRIM: disable the trimming of test cases
AFL_DUMB_FORKSRV: use fork server without feedback from target
AFL_EXIT_WHEN_DONE: exit when all inputs are run and no new finds are found
AFL_EXIT_ON_TIME: exit when no new coverage finds are made within the specified time period
AFL_EXPAND_HAVOC_NOW: immediately enable expand havoc mode (default: after 60 minutes and a cycle without finds)
AFL_FAST_CAL: limit the calibration stage to three cycles for speedup
AFL_FORCE_UI: force showing the status screen (for virtual consoles)
AFL_FORKSRV_INIT_TMOUT: time spent waiting for forkserver during startup (in milliseconds)
AFL_HANG_TMOUT: override timeout value (in milliseconds)
AFL_I_DONT_CARE_ABOUT_MISSING_CRASHES: don't warn about core dump handlers
AFL_IGNORE_UNKNOWN_ENVS: don't warn on unknown env vars
AFL_IGNORE_PROBLEMS: do not abort fuzzing if an incorrect setup is detected during a run
AFL_IMPORT_FIRST: sync and import test cases from other fuzzer instances first
AFL_INPUT_LEN_MIN/AFL_INPUT_LEN_MAX: like -g/-G set min/max fuzz length produced
AFL_PIZZA_MODE: 1 - enforce pizza mode, 0 - disable for April 1st
AFL_KILL_SIGNAL: Signal ID delivered to child processes on timeout, etc. (default: SIGKILL)
AFL_MAP_SIZE: the shared memory size for that target. must be >= the size
              the target was compiled for
AFL_MAX_DET_EXTRAS: if more entries are in the dictionary list than this value
                    then they are randomly selected instead all of them being
                    used. Defaults to 200.
AFL_NO_AFFINITY: do not check for an unused cpu core to use for fuzzing
AFL_TRY_AFFINITY: try to bind to an unused core, but don't fail if unsuccessful
AFL_NO_ARITH: skip arithmetic mutations in deterministic stage
AFL_NO_AUTODICT: do not load an offered auto dictionary compiled into a target
AFL_NO_CPU_RED: avoid red color for showing very high cpu usage
AFL_NO_FORKSRV: run target via execve instead of using the forkserver
AFL_NO_SNAPSHOT: do not use the snapshot feature (if the snapshot lkm is loaded)
AFL_NO_STARTUP_CALIBRATION: no initial seed calibration, start fuzzing at once
AFL_NO_UI: switch status screen off
AFL_PATH: path to AFL support binaries
AFL_PYTHON_MODULE: mutate and trim inputs with the specified Python module
AFL_QUIET: suppress forkserver status messages
AFL_PRELOAD: LD_PRELOAD / DYLD_INSERT_LIBRARIES settings for target
AFL_TARGET_ENV: pass extra environment variables to target
AFL_SHUFFLE_QUEUE: reorder the input queue randomly on startup
AFL_SKIP_BIN_CHECK: skip afl compatibility checks, also disables auto map size
AFL_SKIP_CPUFREQ: do not warn about variable cpu clocking
AFL_STATSD: enables StatsD metrics collection
AFL_STATSD_HOST: change default statsd host (default 127.0.0.1)
AFL_STATSD_PORT: change default statsd port (default: 8125)
AFL_STATSD_TAGS_FLAVOR: set statsd tags format (default: disable tags)
                        Supported formats are: 'dogstatsd', 'librato',
                        'signalfx' and 'influxdb'
AFL_SYNC_TIME: sync time between fuzzing instances (in minutes)
AFL_NO_CRASH_README: do not create a README in the crashes directory
AFL_TESTCACHE_SIZE: use a cache for testcases, improves performance (in MB)
AFL_TMPDIR: directory to use for input file generation (ramdisk recommended)
AFL_EARLY_FORKSERVER: force an early forkserver in an afl-clang-fast/
                      afl-clang-lto/afl-gcc-fast target
AFL_PERSISTENT: enforce persistent mode (if __AFL_LOOP is in a shared lib
AFL_DEFER_FORKSRV: enforced deferred forkserver (__AFL_INIT is in a .so

Compiled with Python 3.11.1 module support, see docs/custom_mutator.md
Compiled without AFL_PERSISTENT_RECORD support.
Compiled with shmat support.
For additional help please consult /usr/share/doc/afl/README.md :)

```

***

**afl-g++**

```
:~# afl-g++ --help
Usage: g++ [options] file...
Options:
  -pass-exit-codes         Exit with highest error code from a phase.
  --help                   Display this information.
  --target-help            Display target specific command line options (including assembler and linker options).
  --help={common|optimizers|params|target|warnings|[^]{joined|separate|undocumented}}[,...].
                           Display specific types of command line options.
  (Use '-v --help' to display command line options of sub-processes).
  --version                Display compiler version information.
  -dumpspecs               Display all of the built in spec strings.
  -dumpversion             Display the version of the compiler.
  -dumpmachine             Display the compiler's target processor.
  -foffload=<targets>      Specify offloading targets.
  -print-search-dirs       Display the directories in the compiler's search path.
  -print-libgcc-file-name  Display the name of the compiler's companion library.
  -print-file-name=<lib>   Display the full path to library <lib>.
  -print-prog-name=<prog>  Display the full path to compiler component <prog>.
  -print-multiarch         Display the target's normalized GNU triplet, used as
                           a component in the library path.
  -print-multi-directory   Display the root directory for versions of libgcc.
  -print-multi-lib         Display the mapping between command line options and
                           multiple library search directories.
  -print-multi-os-directory Display the relative path to OS libraries.
  -print-sysroot           Display the target libraries directory.
  -print-sysroot-headers-suffix Display the sysroot suffix used to find headers.
  -Wa,<options>            Pass comma-separated <options> on to the assembler.
  -Wp,<options>            Pass comma-separated <options> on to the preprocessor.
  -Wl,<options>            Pass comma-separated <options> on to the linker.
  -Xassembler <arg>        Pass <arg> on to the assembler.
  -Xpreprocessor <arg>     Pass <arg> on to the preprocessor.
  -Xlinker <arg>           Pass <arg> on to the linker.
  -save-temps              Do not delete intermediate files.
  -save-temps=<arg>        Do not delete intermediate files.
  -no-canonical-prefixes   Do not canonicalize paths when building relative
                           prefixes to other gcc components.
  -pipe                    Use pipes rather than intermediate files.
  -time                    Time the execution of each subprocess.
  -specs=<file>            Override built-in specs with the contents of <file>.
  -std=<standard>          Assume that the input sources are for <standard>.
  --sysroot=<directory>    Use <directory> as the root directory for headers
                           and libraries.
  -B <directory>           Add <directory> to the compiler's search paths.
  -v                       Display the programs invoked by the compiler.
  -###                     Like -v but options quoted and commands not executed.
  -E                       Preprocess only; do not compile, assemble or link.
  -S                       Compile only; do not assemble or link.
  -c                       Compile and assemble, but do not link.
  -o <file>                Place the output into <file>.
  -pie                     Create a dynamically linked position independent
                           executable.
  -shared                  Create a shared library.
  -x <language>            Specify the language of the following input files.
                           Permissible languages include: c c++ assembler none
                           'none' means revert to the default behavior of
                           guessing the language based on the file's extension.

Options starting with -g, -f, -m, -O, -W, or --param are automatically
 passed on to the various sub-processes invoked by g++.  In order to pass
 other options on to these processes the -W<letter> options must be used.

For bug reporting instructions, please see:
<file:///usr/share/doc/gcc-12/README.Bugs>.
```

***

**afl-g++-fast**

Afl-g++-fast (8) - afl-cc++4.04c by Michal Zalewski, Laszlo Szekeres, Marc Heuse afl-cc

```
:~# afl-g++-fast --help
Usage: g++ [options] file...
Options:
  -pass-exit-codes         Exit with highest error code from a phase.
  --help                   Display this information.
  --target-help            Display target specific command line options (including assembler and linker options).
  --help={common|optimizers|params|target|warnings|[^]{joined|separate|undocumented}}[,...].
                           Display specific types of command line options.
  (Use '-v --help' to display command line options of sub-processes).
  --version                Display compiler version information.
  -dumpspecs               Display all of the built in spec strings.
  -dumpversion             Display the version of the compiler.
  -dumpmachine             Display the compiler's target processor.
  -foffload=<targets>      Specify offloading targets.
  -print-search-dirs       Display the directories in the compiler's search path.
  -print-libgcc-file-name  Display the name of the compiler's companion library.
  -print-file-name=<lib>   Display the full path to library <lib>.
  -print-prog-name=<prog>  Display the full path to compiler component <prog>.
  -print-multiarch         Display the target's normalized GNU triplet, used as
                           a component in the library path.
  -print-multi-directory   Display the root directory for versions of libgcc.
  -print-multi-lib         Display the mapping between command line options and
                           multiple library search directories.
  -print-multi-os-directory Display the relative path to OS libraries.
  -print-sysroot           Display the target libraries directory.
  -print-sysroot-headers-suffix Display the sysroot suffix used to find headers.
  -Wa,<options>            Pass comma-separated <options> on to the assembler.
  -Wp,<options>            Pass comma-separated <options> on to the preprocessor.
  -Wl,<options>            Pass comma-separated <options> on to the linker.
  -Xassembler <arg>        Pass <arg> on to the assembler.
  -Xpreprocessor <arg>     Pass <arg> on to the preprocessor.
  -Xlinker <arg>           Pass <arg> on to the linker.
  -save-temps              Do not delete intermediate files.
  -save-temps=<arg>        Do not delete intermediate files.
  -no-canonical-prefixes   Do not canonicalize paths when building relative
                           prefixes to other gcc components.
  -pipe                    Use pipes rather than intermediate files.
  -time                    Time the execution of each subprocess.
  -specs=<file>            Override built-in specs with the contents of <file>.
  -std=<standard>          Assume that the input sources are for <standard>.
  --sysroot=<directory>    Use <directory> as the root directory for headers
                           and libraries.
  -B <directory>           Add <directory> to the compiler's search paths.
  -v                       Display the programs invoked by the compiler.
  -###                     Like -v but options quoted and commands not executed.
  -E                       Preprocess only; do not compile, assemble or link.
  -S                       Compile only; do not assemble or link.
  -c                       Compile and assemble, but do not link.
  -o <file>                Place the output into <file>.
  -pie                     Create a dynamically linked position independent
                           executable.
  -shared                  Create a shared library.
  -x <language>            Specify the language of the following input files.
                           Permissible languages include: c c++ assembler none
                           'none' means revert to the default behavior of
                           guessing the language based on the file's extension.

Options starting with -g, -f, -m, -O, -W, or --param are automatically
 passed on to the various sub-processes invoked by g++.  In order to pass
 other options on to these processes the -W<letter> options must be used.

For bug reporting instructions, please see:
<file:///usr/share/doc/gcc-12/README.Bugs>.
```

***

**afl-gcc**

```
:~# afl-gcc --help
Usage: gcc [options] file...
Options:
  -pass-exit-codes         Exit with highest error code from a phase.
  --help                   Display this information.
  --target-help            Display target specific command line options (including assembler and linker options).
  --help={common|optimizers|params|target|warnings|[^]{joined|separate|undocumented}}[,...].
                           Display specific types of command line options.
  (Use '-v --help' to display command line options of sub-processes).
  --version                Display compiler version information.
  -dumpspecs               Display all of the built in spec strings.
  -dumpversion             Display the version of the compiler.
  -dumpmachine             Display the compiler's target processor.
  -foffload=<targets>      Specify offloading targets.
  -print-search-dirs       Display the directories in the compiler's search path.
  -print-libgcc-file-name  Display the name of the compiler's companion library.
  -print-file-name=<lib>   Display the full path to library <lib>.
  -print-prog-name=<prog>  Display the full path to compiler component <prog>.
  -print-multiarch         Display the target's normalized GNU triplet, used as
                           a component in the library path.
  -print-multi-directory   Display the root directory for versions of libgcc.
  -print-multi-lib         Display the mapping between command line options and
                           multiple library search directories.
  -print-multi-os-directory Display the relative path to OS libraries.
  -print-sysroot           Display the target libraries directory.
  -print-sysroot-headers-suffix Display the sysroot suffix used to find headers.
  -Wa,<options>            Pass comma-separated <options> on to the assembler.
  -Wp,<options>            Pass comma-separated <options> on to the preprocessor.
  -Wl,<options>            Pass comma-separated <options> on to the linker.
  -Xassembler <arg>        Pass <arg> on to the assembler.
  -Xpreprocessor <arg>     Pass <arg> on to the preprocessor.
  -Xlinker <arg>           Pass <arg> on to the linker.
  -save-temps              Do not delete intermediate files.
  -save-temps=<arg>        Do not delete intermediate files.
  -no-canonical-prefixes   Do not canonicalize paths when building relative
                           prefixes to other gcc components.
  -pipe                    Use pipes rather than intermediate files.
  -time                    Time the execution of each subprocess.
  -specs=<file>            Override built-in specs with the contents of <file>.
  -std=<standard>          Assume that the input sources are for <standard>.
  --sysroot=<directory>    Use <directory> as the root directory for headers
                           and libraries.
  -B <directory>           Add <directory> to the compiler's search paths.
  -v                       Display the programs invoked by the compiler.
  -###                     Like -v but options quoted and commands not executed.
  -E                       Preprocess only; do not compile, assemble or link.
  -S                       Compile only; do not assemble or link.
  -c                       Compile and assemble, but do not link.
  -o <file>                Place the output into <file>.
  -pie                     Create a dynamically linked position independent
                           executable.
  -shared                  Create a shared library.
  -x <language>            Specify the language of the following input files.
                           Permissible languages include: c c++ assembler none
                           'none' means revert to the default behavior of
                           guessing the language based on the file's extension.

Options starting with -g, -f, -m, -O, -W, or --param are automatically
 passed on to the various sub-processes invoked by gcc.  In order to pass
 other options on to these processes the -W<letter> options must be used.

For bug reporting instructions, please see:
<file:///usr/share/doc/gcc-12/README.Bugs>.
```

***

**afl-gcc-fast**

Afl-cc++4.04c by Michal Zalewski, Laszlo Szekeres, Marc Heuse afl-cc

```
:~# afl-gcc-fast --help
Usage: gcc [options] file...
Options:
  -pass-exit-codes         Exit with highest error code from a phase.
  --help                   Display this information.
  --target-help            Display target specific command line options (including assembler and linker options).
  --help={common|optimizers|params|target|warnings|[^]{joined|separate|undocumented}}[,...].
                           Display specific types of command line options.
  (Use '-v --help' to display command line options of sub-processes).
  --version                Display compiler version information.
  -dumpspecs               Display all of the built in spec strings.
  -dumpversion             Display the version of the compiler.
  -dumpmachine             Display the compiler's target processor.
  -foffload=<targets>      Specify offloading targets.
  -print-search-dirs       Display the directories in the compiler's search path.
  -print-libgcc-file-name  Display the name of the compiler's companion library.
  -print-file-name=<lib>   Display the full path to library <lib>.
  -print-prog-name=<prog>  Display the full path to compiler component <prog>.
  -print-multiarch         Display the target's normalized GNU triplet, used as
                           a component in the library path.
  -print-multi-directory   Display the root directory for versions of libgcc.
  -print-multi-lib         Display the mapping between command line options and
                           multiple library search directories.
  -print-multi-os-directory Display the relative path to OS libraries.
  -print-sysroot           Display the target libraries directory.
  -print-sysroot-headers-suffix Display the sysroot suffix used to find headers.
  -Wa,<options>            Pass comma-separated <options> on to the assembler.
  -Wp,<options>            Pass comma-separated <options> on to the preprocessor.
  -Wl,<options>            Pass comma-separated <options> on to the linker.
  -Xassembler <arg>        Pass <arg> on to the assembler.
  -Xpreprocessor <arg>     Pass <arg> on to the preprocessor.
  -Xlinker <arg>           Pass <arg> on to the linker.
  -save-temps              Do not delete intermediate files.
  -save-temps=<arg>        Do not delete intermediate files.
  -no-canonical-prefixes   Do not canonicalize paths when building relative
                           prefixes to other gcc components.
  -pipe                    Use pipes rather than intermediate files.
  -time                    Time the execution of each subprocess.
  -specs=<file>            Override built-in specs with the contents of <file>.
  -std=<standard>          Assume that the input sources are for <standard>.
  --sysroot=<directory>    Use <directory> as the root directory for headers
                           and libraries.
  -B <directory>           Add <directory> to the compiler's search paths.
  -v                       Display the programs invoked by the compiler.
  -###                     Like -v but options quoted and commands not executed.
  -E                       Preprocess only; do not compile, assemble or link.
  -S                       Compile only; do not assemble or link.
  -c                       Compile and assemble, but do not link.
  -o <file>                Place the output into <file>.
  -pie                     Create a dynamically linked position independent
                           executable.
  -shared                  Create a shared library.
  -x <language>            Specify the language of the following input files.
                           Permissible languages include: c c++ assembler none
                           'none' means revert to the default behavior of
                           guessing the language based on the file's extension.

Options starting with -g, -f, -m, -O, -W, or --param are automatically
 passed on to the various sub-processes invoked by gcc.  In order to pass
 other options on to these processes the -W<letter> options must be used.

For bug reporting instructions, please see:
<file:///usr/share/doc/gcc-12/README.Bugs>.
```

***

**afl-gotcpu**

(unknown subject)

```
:~# afl-gotcpu -h
afl-gotcpu++4.04c by Michal Zalewski

afl-gotcpu 

afl-gotcpu does not have command line options
afl-gotcpu prints out which CPUs are available
```

***

**afl-ld-lto**

```
:~# afl-ld-lto --help
OVERVIEW: lld

USAGE: /usr/lib/llvm-14/bin/ld.lld [options] file...

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

/usr/lib/llvm-14/bin/ld.lld: supported targets: elf
```

***

**afl-lto**

Afl-cc++4.04c by Michal Zalewski, Laszlo Szekeres, Marc Heuse afl-cc

```
:~# afl-lto --help
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

**afl-lto++**

Afl-lto++ (8) - afl-cc++4.04c by Michal Zalewski, Laszlo Szekeres, Marc Heuse afl-cc

```
:~# afl-lto++ --help
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

**afl-network-client**

```
:~# afl-network-client -h
Syntax: afl-network-client host port [max-input-size]

Requires host and port of the remote afl-proxy-server instance.
IPv4 and IPv6 are supported, also binding to an interface with "%"
The max-input-size default is 65536.
The default map size is 65536 and can be changed with setting AFL_MAP_SIZE.
```

***

**afl-network-server**

```
:~# afl-network-server -h

afl-network-server [ options ] -- /path/to/target_app [ ... ]

Required parameters:
  -i port       - the port to listen for the client to connect to

Execution control settings:
  -f file       - input file read by the tested program (stdin)
  -t msec       - timeout for each run (1000 ms)
  -m megs       - memory limit for child process (0 MB)
  -Q            - use binary-only instrumentation (QEMU mode)
  -U            - use unicorn-based instrumentation (Unicorn mode)
  -W            - use qemu-based instrumentation with Wine (Wine mode)

Environment variables used:
TMPDIR: directory to use for temporary input files
ASAN_OPTIONS: custom settings for ASAN
              (must contain abort_on_error=1 and symbolize=0)
MSAN_OPTIONS: custom settings for MSAN
              (must contain exitcode=86 and symbolize=0)
AFL_MAP_SIZE: the shared memory size for that target. must be >= the size
              the target was compiled for
AFL_PRELOAD:  LD_PRELOAD / DYLD_INSERT_LIBRARIES settings for target
```

***

**afl-persistent-config**

(unknown subject)

```
:~# afl-persistent-config -h
afl-persistent-config

/usr/bin/afl-persistent-config

afl-persistent-config has no command line options

afl-persistent-config permanently reconfigures the system to a high performance fuzzing state.
WARNING: this reduces the security of the system!

Note that there is also afl-system-config which sets additional runtime
configuration options.
```

***

**afl-plot**

(unknown subject)

```
:~# afl-plot -h
/usr/bin/afl-plot [ -g | --graphical ] afl_state_dir graph_output_dir

This program generates gnuplot images from afl-fuzz output data.

Usage:

    afl_state_dir       should point to an existing state directory for any
                        active or stopped instance of afl-fuzz
    graph_output_dir    should point to an empty directory where this
                        tool can write the resulting plots to
    -g, --graphical     (optional) display the plots in a graphical window
                        (you should have built afl-plot-ui to use this option)

The program will put index.html and three PNG images in the output directory;
you should be able to view it with any web browser of your choice.
```

***

**afl-showmap**

(unknown subject)

```
:~# afl-showmap -h
afl-showmap++4.04c by Michal Zalewski

afl-showmap [ options ] -- /path/to/target_app [ ... ]

Required parameters:
  -o file    - file to write the trace data to

Execution control settings:
  -t msec    - timeout for each run (none)
  -m megs    - memory limit for child process (0 MB)
  -O         - use binary-only instrumentation (FRIDA mode)
  -Q         - use binary-only instrumentation (QEMU mode)
  -U         - use Unicorn-based instrumentation (Unicorn mode)
  -W         - use qemu-based instrumentation with Wine (Wine mode)
               (Not necessary, here for consistency with other afl-* tools)

Other settings:
  -i dir     - process all files below this directory, must be combined with -o.
               With -C, -o is a file, without -C it must be a directory
               and each bitmap will be written there individually.
  -C         - collect coverage, writes all edges to -o and gives a summary
               Must be combined with -i.
  -q         - sink program's output and don't show messages
  -e         - show edge coverage only, ignore hit counts
  -r         - show real tuple values instead of AFL filter values
  -s         - do not classify the map
  -c         - allow core dumps

This tool displays raw tuple data captured by AFL instrumentation.
For additional help, consult /usr/share/doc/afl/README.md.

Environment variables used:
LD_BIND_LAZY: do not set LD_BIND_NOW env var for target
AFL_CMIN_CRASHES_ONLY: (cmin_mode) only write tuples for crashing inputs
AFL_CMIN_ALLOW_ANY: (cmin_mode) write tuples for crashing inputs also
AFL_CRASH_EXITCODE: optional child exit code to be interpreted as crash
AFL_DEBUG: enable extra developer output
AFL_FORKSRV_INIT_TMOUT: time spent waiting for forkserver during startup (in milliseconds)
AFL_KILL_SIGNAL: Signal ID delivered to child processes on timeout, etc. (default: SIGKILL)
AFL_MAP_SIZE: the shared memory size for that target. must be >= the size the target was compiled for
AFL_PRELOAD: LD_PRELOAD / DYLD_INSERT_LIBRARIES settings for target
AFL_PRINT_FILENAMES: If set, the filename currently processed will be printed to stdout
AFL_QUIET: do not print extra informational output
AFL_NO_FORKSRV: run target via execve instead of using the forkserver
```

***

**afl-system-config**

(unknown subject)

```
:~# afl-system-config -h
afl-system-config by Marc Heuse <>

/usr/bin/afl-system-config

afl-system-config has no command line options

afl-system-config reconfigures the system to a high performance fuzzing state.
WARNING: this reduces the security of the system!

Note that there is also afl-persistent-config which sets additional permanent
configuration options.
```

***

**afl-tmin**

(unknown subject)

```
:~# afl-tmin -h
afl-tmin++4.04c by Michal Zalewski

afl-tmin [ options ] -- /path/to/target_app [ ... ]

Required parameters:
  -i file       - input test case to be shrunk by the tool
  -o file       - final output location for the minimized data

Execution control settings:
  -f file       - input file read by the tested program (stdin)
  -t msec       - timeout for each run (1000 ms)
  -m megs       - memory limit for child process (0 MB)
  -O            - use binary-only instrumentation (FRIDA mode)
  -Q            - use binary-only instrumentation (QEMU mode)
  -U            - use unicorn-based instrumentation (Unicorn mode)
  -W            - use qemu-based instrumentation with Wine (Wine mode)
                  (Not necessary, here for consistency with other afl-* tools)

Minimization settings:
  -e            - solve for edge coverage only, ignore hit counts
  -x            - treat non-zero exit codes as crashes

  -H            - minimize a hang (hang mode)
For additional tips, please consult /usr/share/doc/afl/README.md.

Environment variables used:
AFL_CRASH_EXITCODE: optional child exit code to be interpreted as crash
AFL_FORKSRV_INIT_TMOUT: time spent waiting for forkserver during startup (in milliseconds)
AFL_KILL_SIGNAL: Signal ID delivered to child processes on timeout, etc. (default: SIGKILL)
AFL_MAP_SIZE: the shared memory size for that target. must be >= the size
              the target was compiled for
AFL_PRELOAD:  LD_PRELOAD / DYLD_INSERT_LIBRARIES settings for target
AFL_TMIN_EXACT: require execution paths to match for crashing inputs
AFL_NO_FORKSRV: run target via execve instead of using the forkserver
ASAN_OPTIONS: custom settings for ASAN
              (must contain abort_on_error=1 and symbolize=0)
MSAN_OPTIONS: custom settings for MSAN
              (must contain exitcode=86 and symbolize=0)
TMPDIR: directory to use for temporary input files
```

***

**afl-whatsup**

(unknown subject)

```
:~# afl-whatsup -h
/usr/bin/afl-whatsup status check tool for afl-fuzz by Michal Zalewski

Usage: /usr/bin/afl-whatsup [-s] [-d] afl_output_directory

Options:
  -s  -  skip details and output summary results only
  -d  -  include dead fuzzer stats

```

***

#### afl++-clang <a href="#afl-clang-2" id="afl-clang-2"></a>

This is a transitional package. It can safely be removed once afl++ is installed.

**Installed size:** `73 KB`\
**How to install:** `sudo apt install afl++-clang`

<details>

<summary>Dependencies:</summary>

* afl++

</details>

***

#### afl++-doc <a href="#afl-doc" id="afl-doc"></a>

American fuzzy lop is a fuzzer that employs compile-time instrumentation and genetic algorithms to automatically discover clean, interesting test cases that trigger new internal states in the targeted binary.

This package provides the documentation, a collection of special crafted test cases, vulnerability samples and experimental stuff.

**Installed size:** `440 KB`\
**How to install:** `sudo apt install afl++-doc`

***

#### afl-clang <a href="#afl-clang-3" id="afl-clang-3"></a>

This is a transitional package. It can safely be removed once afl++-clang is installed.

**Installed size:** `73 KB`\
**How to install:** `sudo apt install afl-clang`

<details>

<summary>Dependencies:</summary>

* afl++-clang

</details>

***

#### afl-doc <a href="#afl-doc-1" id="afl-doc-1"></a>

This is a transitional package. It can safely be removed once afl++-doc is installed.

**Installed size:** `73 KB`\
**How to install:** `sudo apt install afl-doc`

<details>

<summary>Dependencies:</summary>

* afl++-doc

</details>

***

Updated on: 2023-Mar-08\


***
