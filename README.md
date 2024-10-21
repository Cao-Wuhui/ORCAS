# ORCAS

## Dataset

从若干项目中抽取CVE漏洞，每一个项目下都有以`CVEID_项目名称_函数名_优化选项_混淆方式`方式命名的可执行文件的工程包。

为方便使用混淆选项，使用[obfuscator-llvm](https://github.com/obfuscator-llvm/obfuscator)构建x86_64和aarch64 2种指令集架构共计10个实例，每个项目的初定配置如下：

- 混淆选项
  - 控制流平坦化（Control Flow Flattening）：`-mllvm -fla`
  - 虚假控制流（Bogus Control Flow）：`-mllvm -bcf`
  - 指令替换（Instruction Substitution）：`-mllvm -sub`
  - 全部：包括上述3种方式，即`-mllvm -fla -mllvm -bcf -mllvm -sub`
- 编译优化
  - `-O3`
- 函数内联
  - 为了方便抽取函数，规定取消所有的函数内联：`-fno-inline-functions`。

### [openjpeg](https://github.com/uclouvain/openjpeg)

- CVE-2017-14151 (afb308b9ccbe129608c9205cf3bb39bbefad90b9^)
- CVE-2017-14152 (4241ae6fbbf1de9658764a80944dc8108f2b4154^)
- CVE-2016-4796 (162f6199c0cd3ec1c6c6dc65e41b2faab92b2d91^)

### openssl （TODO）

