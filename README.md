<p align="center">
  <a href="https://himitsushell.com/" target="blank"><img src="https://avatars.githubusercontent.com/u/264618628?s=200&v=4" width="120" alt="HimitsuShell Logo" /></a>
</p>
<p align="center">
  <img src="https://img.shields.io/badge/Docker-Ready-2496ED?logo=docker&logoColor=white" alt="Docker Ready" />
  <img src="https://img.shields.io/badge/License-Commercial-6e7781" alt="Commercial License" />
  <a href="https://github.com/HimitsuShell/Himitsu/releases">
    <img src="https://img.shields.io/github/v/release/HimitsuShell/Himitsu?color=2da44e" alt="Latest Release" />
  </a>
</p>

## HimitsuShell
<img src="assets/demo.gif" width="300">

[HimitsuShell](https://himitsushell.com) compiles shell scripts into obfuscated binaries to protect source code from disclosure.

## Features
#### Advanced Obfuscation Techniques
<img src="assets/features_obfuscation.png" width="250">

Features instruction substitution, indirect calls, indirect branches, basic block splitting, and bogus control flow.

#### OS-Level Logging & Hooking Protection
<img src="assets/features_os.png" width="250">

Embeds its own shell interpreter, eliminating reliance on the system shell and reducing exposure to OS-level logging and hooking. (e.g., auditd).

#### String & Constant Encryption
<img src="assets/features_encryption.png" width="250">

All strings and constants in the binary are encrypted, making static analysis more difficult (e.g., IDA, Ghidra).

#### Debugger Detection
<img src="assets/features_debugger.png" width="250">

Continuously detects debuggers during execution, making dynamic analysis more difficult (e.g., gdb, ptrace, strace).

## Guide
### System Requirements
  - **CPU:** AMD x86_64, 2.5 GHz or higher (6 cores / 12 threads recommended)
  - **Memory:** 16 GB RAM
  - **Storage:** 10 GB available SSD/NVMe space

### Usage
```shell
# 1. Load the Docker Image
docker load -i himitsu_core_v1.1.2.tar.gz

# 2. Start the Container
docker run --name himitsu_core -d -it himitsu_core:v1.1.2

# 3. Upload Your Shell Script (The filename must be "launcher.sh")
docker cp launcher.sh himitsu_core:/var/work/

# 4. Build the Protected Binary (10–20 min)
docker exec himitsu_core /var/work/compile.sh

# 5. Download the Generated Binary
docker cp himitsu_core:/var/work/safeLauncher .
```

## About This Repository

HimitsuShell is a commercial software product.

This repository does not contain the HimitsuShell source code.

It serves as the official community hub for:

- Discussions
- Bug reports
- Feature requests

## Research & Security Analysis
- [Shell Script-to-Binary Tools: shc vs. HimitsuShell](https://medium.com/@y37653/shell-script-to-binary-tools-shc-vs-himitsushell-31baed264c6f)
- [shc Security Analysis: Structural Limitations of a Shell Script Compiler](https://medium.com/@y37653/how-to-hack-shc-shell-script-protection-tool-bd958126ea66)
- [ssc Security Analysis: Structural Limitations of a Shell Script Compiler](https://medium.com/@y37653/how-to-hack-ssc-shell-script-protection-tool-90a34b13c802)

## Discussions

We welcome questions, feedback, bug reports, feature requests, and use cases related to HimitsuShell. Feel free to start a discussion and share your thoughts.

## Contact
hjyun@mushsw.com
