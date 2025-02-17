# 1. Rust 编程语言
`Rust` 编程语言可帮助您编写更快、更可靠的软件。高级的人机工程学和低级的控制在编程语言设计中往往是不一致的；`Rust` 挑战了这种冲突。通过平衡强大的技术能力和出色的开发人员体验，`Rust` 为您提供了控制低级细节（例如内存使用）的选项，而无需传统上与此类控制相关的所有麻烦。
`Rust` 是一种高效的工具，可以在具有不同系统编程知识水平的大型开发人员团队之间进行协作。低级代码容易出现各种细微的错误，在大多数其他语言中，只有通过经验丰富的开发人员进行广泛的测试和仔细的代码审查才能发现这些错误。在 `Rust` 中，编译器通过拒绝编译带有这些难以捉摸的错误（包括并发错误）的代码来扮演看门人的角色。通过与编译器一起工作，团队可以将时间花在程序的逻辑上，而不是追踪错误。

`Rust` 还为系统编程世界带来了当代开发者工具：

* `Cargo` 是包含的依赖项管理器和构建工具，它使添加、编译和管理依赖项在整个 `Rust` 生态系统中变得轻松且一致。
* `Rustfmt` 确保开发人员之间的编码风格一致。
* `Rust` 语言服务器为代码完成和内联错误消息的集成开发环境 `(IDE)` 集成提供支持。
* 通过使用 `Rust` 生态系统中的这些和其他工具，开发人员可以在编写系统级代码时提高工作效率。

# 2. 安装 Rust 编译运行环境
## 2.1. 在 Linux 或 macOS 上安装
该命令会下载一个脚本并开始安装该 `rustup` 工具，该工具会安装最新的稳定版 `Rust`。系统可能会提示您输入密码。
```shell
imaginemiracle:~$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```
对 `curl` 这个工具的使用不清楚小伙伴可以通过笔者这篇博客了解，[《curl开源软件使用详解》](https://blog.csdn.net/qq_36393978/article/details/125189080)。(建议看完本文之后再去了解，不要打断学习一个内容的过程)
安装成功后会的输出会出现一行如下内容：
```shell
Rust is installed now. Great!
```
若是 **`Linux`** 系统的话通常需要安装 `gcc`、`g++`、`clang`、`build-essential(Ubuntu)`，但这些很有可能已经安装好了的，并且在安装完 `rustup` 工具后还需要更新环境变量才可以使用 `rustup`。
```shell
imaginemiracle:~$ source $HOME/.cargo/env
# 输入 ru 按 Tab 键可以输出及表示环境变量已更新
imaginemiracle:~$ ru
runcon           run-mailcap      runuser          rustc            rustfmt          rust-lldb        
runlevel         run-parts        run-with-aspell  rustdoc          rust-gdb         rustup 
```
若是 **`macOS`** 系统的话，则可以通过下面命令获取 `C` 编译器：
```shell
imaginemiracle:~$ xcode-select --install
```
**`Windows`** 用户则访问如下网址下载 `rustup-init.exe`（根据系统位数自主选择 `32bit` 或 `64bit`）。

[https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install)

下载完毕双击运行，便会自动弹出系统终端，同样当出现 `Rust is installed now. Great!`，则说明 `Rust` 安装完成。


## 2.2. 查看 Rust 发布的版本号
通过查看 `Rust` 的版本号，同时也可通过是否有输出检查是否正确的安装了 `Rust`。

`[注]：Windows 与 Linux 命令相同。`
```shell
#输出格式：rustc x.y.z (abcabcabc yyyy-mm-dd)
#描述信息：<版本号> (<提交哈希> <提交日期>)
imaginemiracle:rust$ rustc --version
rustc 1.61.0 (fe5b13d68 2022-05-18)
```
如果看到这个信息，说明已经成功安装了 `Rust`！

# 3. 更新和卸载
**(1)** **更新**
通过安装 `Rust` 的 `rustup`，可以很轻松的更新到最新版本。
```shell
imaginemiracle:rust$ rustup update
```
**(2)** **卸载**
同时也可以使用 `rustup` 随时卸载 `Rust`。

`[小玩笑]: 这么快就到卸载了？这就是传说中的《Rust语言从入门到放弃》2022最新版教程？`
```shell
imaginemiracle:rust$ rustup self uninstall
```
# 4. 查看本地文档
`Rust` 的安装还包括本地文档的副本，因此您可以离线阅读。运行 `rustup doc` 以在浏览器中打开本地文档。
```shell
imaginemiracle:rust$ rustup doc
```
任何时候标准库提供了一个类型或函数，而您不确定它的作用或如何使用它，请使用应用程序编程接口 `(API)` 文档找出答案！
