This repo is an offshoot from my rustOS project. It has its own repo to seperate the step of creating a freesanding binary and minimal Kernel in Rust.


Simple guideline:
create bootimage with bootimage tool:
- install bootimage tool: cargo install bootimage
- run bootimage tool (execute in project dir): cargo bootimage

use the created bootimage with qemu: qemu-system-x86_64 -drive format=raw,file=target/x86_64-simpleRustKerneltt/debug/bootimage-simpleRustKernel.bin
OR
let the bootloader tool config in the cargo config.toml handle it with:
```
[target.'cfg(target_os = "none")']
runner = "bootimage runner"
```
(qemu should be started with "cargo run" with this setup

After running, qemu should display a simple "Hello world" from the bootimage
![image](https://github.com/raffifasaro/simpleRustKernel/assets/134242785/5dd570ee-647f-4b94-834e-48f898bfc53c)
