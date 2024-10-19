# ORCAS

## Dataset

从若干项目中抽取CVE漏洞，每一个项目下都有以`CVEID_项目名称_函数名_优化选项_混淆方式`方式命名的可执行文件的工程包。

每个项目的初定配置如下：

- 混淆选项
  - 控制流平坦化（Control Flow Flattening）：`-mllvm -fla`
  - 虚假控制流(Bogus Control Flow)：`-mllvm -bcf`
  - 指令替换(Instruction Substitution)：`-mllvm -sub`
  - 全部：包括上述3种方式。
- 编译优化
  - `-O3`
- 函数内联
  - 为了方便抽取函数，规定取消所有的函数内联：`-fno-inline-functions`。

### openjpeg

- CVE-2017-14151
- CVE-2017-14152
