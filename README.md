# ORCAS

## Dataset

CVE vulnerabilities are selected from multiple projects, with each project containing a package of executable files named in the format: `CVEID_ProjectName_FunctionName_OptimizationOption_ObfuscationMethod`. If there is an `_arm` suffix, the package is for the ARM64 architecture; otherwise, it is for x86-64.

To facilitate the use of obfuscation options, [obfuscator-llvm](https://github.com/obfuscator-llvm/obfuscator) was used to build a total of 10 instances across two instruction set architectures: x86-64 and ARM64. The initial configuration for each project is as follows:

- **Obfuscation Options**:
  - Without obfuscation option.
  - Control Flow Flattening: `-mllvm -fla`.
  - Bogus Control Flow: `-mllvm -bcf`.
  - Instruction Substitution: `-mllvm -sub`.
  - All: Includes all three methods above, i.e., using `-mllvm -fla -mllvm -bcf -mllvm -sub`.
- **Compilation Optimization**:
  - `-O0` and `-O3`.
- **Function Inlining**:
  - To facilitate function extraction, all function inlining is disabled: `-fno-inline-functions`.


### [openjpeg](https://github.com/uclouvain/openjpeg)

- CVE-2017-14151 (afb308b9ccbe129608c9205cf3bb39bbefad90b9^)
- CVE-2017-14152 (4241ae6fbbf1de9658764a80944dc8108f2b4154^)
- CVE-2016-4796 (162f6199c0cd3ec1c6c6dc65e41b2faab92b2d91^)
- CVE-2017-12982 (baf0c1ad4572daa89caa3b12985bdd93530f0dd7^)
- CVE-2016-10504 (397f62c0a838e15d667ef50e27d5d011d2c79c04^)

### [libgit2](https://github.com/libgit2/libgit2)

- CVE-2018-8098（3207ddb0103543da8ad2139ec6539f590f9900c1^）
- CVE-2018-10888（9844d38bed10e9ff17174434b3421b227ae710f3^）
- CVE-2016-10130（b5c6a1b407b7f8b952bded2789593b68b1876211^）
