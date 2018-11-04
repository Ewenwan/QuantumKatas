# Introduction

    据外媒报道，微软近日推出了一套先进的量子编程解决方案，让编程人员可以更好地学习量子计算及其相关的 Q# 编程语言。

    量子计算是一项有望彻底改变科技行业的事情，与当前的“传统”计算机相比，新机器将拥有强达数倍的性能，

    能够轻松攻克此前从未揭开的难题、让当前的各种加密手段瞬间化为无形。

    微软量子团队表示，Katas 是一款非常优秀的编程语言学习工具，主要依赖于几个简单的学习原则：
    主动学习，增量复杂性和反馈。

    Quantum Katas 的一系列教程可以自定义进度，旨在同时教授量子计算和 Q# 编程元素。
    从基础到具有一定挑战性，Katas 提供了一系列关于量子计算主题的任务。
    每项任务都需要填写代码，从开始的只有一行代码，到后面可能需要填写一大片代码。

    到目前为止，该项目主要涵盖以下主题：

      1. 基本量子计算门（Basic quantum computing gates）：
                 专注于量子计算中使用的主要单量子比特和多量子比特门的任务。

      2. 叠加（Superposition）： 专注于在一个或多个量子比特上准备某个叠加状态的任务。

      3. 测量（Measurements）：专注于使用测量来区分量子态的任务。

      4. Deutsch–Jozsa 算法（Deutsch–Jozsa algorithm）：专注于编写实现经典函数的量子的任务，
         以及 Bernstein-Vazirani 和 Deutsch-Jozsa 算法。


The Quantum Katas are a series of self-paced tutorials aimed at teaching you elements of quantum computing and Q# programming at the same time.

Each kata covers one topic.
Currently covered topics are:

* **[Basic quantum computing gates](./BasicGates/)**.
  This kata focuses on main single-qubit and multi-qubit gates used in quantum computing.
* **[Superposition](./Superposition/)**.
  The tasks focus on preparing a certain superposition state on one or multiple qubits.
* **[Measurements](./Measurements/)**.
  The tasks focus on distinguishing quantum states using measurements.
* **[Joint measurements](./JointMeasurements/)**.
  The tasks focus on using joint (parity) measurements for distinguishing quantum states and performing gates.
* **[Teleportation](./Teleportation/)**.
  This kata walks you through the standard teleportation protocol and several variations.
* **[Superdense coding](./SuperdenseCoding/)**.
  This kata walks you through the superdense coding protocol.
* **[Deutsch–Jozsa algorithm](./DeutschJozsaAlgorithm/)**.
  This kata starts with writing quantum oracles which implement classical functions, and continues to introduce the Bernstein–Vazirani and Deutsch–Jozsa algorithms.
* **[Simon's algorithm](./SimonsAlgorithm/)**.
  This kata introduces Simon's algorithm.
* **[Grover's algorithm](./GroversAlgorithm/)**.
  This kata introduces Grover's search algorithm and writing quantum oracles to be used with it.
* **[Bit-flip error correcting code](./QEC_BitFlipCode/)**.
  This kata introduces a 3-qubit error correcting code for protecting against bit-flip errors.

Each kata is a separate project which includes:

* A sequence of tasks on the topic progressing from trivial to challenging.
  Each task requires you to fill in some code; the first task might require just one line, and the last one might require a sizable fragment of code.
* A testing framework that sets up, runs and validates your solutions.
  Each task is covered by a [*unit test*](https://docs.microsoft.com/en-us/visualstudio/test/getting-started-with-unit-testing) which initially fails; once the test passes, you can move on to the next task!
* Pointers to reference materials you might need to solve the tasks, both on quantum computing and on Q#.
* Reference solutions, for when all else fails.

# Installing and Getting Started #

To get started with the Quantum Katas, you'll first need to install the [Quantum Development Kit](https://docs.microsoft.com/quantum), available for Windows 10, macOS, and for Linux.
Please see the [install guide for the Quantum Development Kit](https://docs.microsoft.com/en-us/quantum/quantum-installconfig) if you do not already have the Quantum Development Kit installed.

A quick reference sheet for Q# programming language is available [here](./quickref/qsharp-quick-reference.pdf).

### Downloading the Quantum Katas ###

If you have Git installed, go on and clone the Microsoft/QuantumKatas repository.
From your favorite command line:

```bash
$ git clone https://github.com/Microsoft/QuantumKatas.git
```

> **TIP**: Both Visual Studio 2017 and Visual Studio Code make it easy to clone repositories from within your development environment.
> See the [Visual Studio 2017](https://docs.microsoft.com/en-us/vsts/git/tutorial/clone?view=vsts&tabs=visual-studio#clone-from-another-git-provider) and [Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol#_cloning-a-repository) documentation for details.

Alternatively, if you don't have Git installed, you can manually download a standalone copy of the katas from https://github.com/Microsoft/QuantumKatas/archive/master.zip.

### Opening a Tutorial ###

Each individual kata is placed in its own directory as a self-contained Q# solution and project pair.
For instance, the **BasicGates** kata is laid out as below.

```
QuantumKatas/
  BasicGates/
    README.md                  # Instructions specific to this kata.
    .vscode/                   # Metadata used by Visual Studio Code.
    BasicGates.sln             # Visual Studio 2017 solution file.
    BasicGates.csproj          # Project file used to build both classical and quantum code.

    Tasks.qs                   # Q# source code that you will fill as you solve each task.
    Tests.qs                   # Q# tests that verify your solutions.
    TestSuiteRunner.cs         # C# source code used to run the Q# tests.
    ReferenceImplementation.qs # Q# source code containing solutions to the tasks.
```

To open the **BasicGates** kata in Visual Studio 2017, open the `QuantumKatas/BasicGates/BasicGates.sln` solution file.

To open the **BasicGates** kata in Visual Studio Code, open the `QuantumKatas/BasicGates/` folder.
Press Ctrl + Shift + P (or ⌘ + Shift + P on macOS) to open the Command Palette. Type "Open Folder" on Windows 10 or Linux or "Open" on macOS.

> **TIP**: Almost all commands available in Visual Studio Code can be found in the Command Palette.
> If you ever get stuck, press Ctrl + Shift + P (or ⌘ + Shift + P on macOS) and type some letters to search through all available commands.

> **TIP**: You can also launch Visual Studio Code from the command line if you prefer:
> ```bash
> $ code QuantumKatas/BasicGates/
> ```

### Running Kata Tests ###

Once you have a kata open, it's time to run the tests using the instructions below.
Initially all tests will fail; do not panic!
Open the `Tasks.qs` file and start filling in the code to complete the tasks. Each task is covered by a unit test; once you fill in the correct code for a task, rebuild the project and re-run the tests, and the corresponding unit test will pass.

#### Visual Studio 2017

1. Build solution.
2. Open Test Explorer (found in `Test` > `Windows` menu) and select "Run All" to run all unit tests at once.
3. Work on the tasks in the `Tasks.qs` file.
4. To test your code changes for a task, rebuild solution and re-run all unit tests using "Run All" or the unit test which covers that task by right-clicking on that test and selecting "Run Selected Tests".

#### Visual Studio Code

1. Press Ctrl + \` (or ⌘ + \` on macOS) to open the integrated terminal.
   The terminal should already start in the kata directory, but if not, use `cd` to navigate to the folder containing the `*.csproj` file for the kata.
2. Run `dotnet test` in the integrated terminal.
   This should automatically build the kata project and run all unit tests; initially, all unit tests should fail.
3. Work on the tasks in the `Tasks.qs` file.
4. To test your code changes for a task, run `dotnet test` again.

For convenience, we also provide a `tasks.json` configuration for each kata that allows Visual Studio Code to run the build and test steps from the Command Palette.
Press Ctrl + Shift + P (or ⌘ + Shift + P on macOS) to open the Palette and type "Run Build Task" or "Run Test Task," then press Enter.

# Contributing

This project welcomes contributions and suggestions.  For details, see [How Can I Contribute?](.github/CONTRIBUTING.md)

# Code of Conduct

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
