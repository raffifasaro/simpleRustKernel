This repo is an offshoot from my rustOS project. It has its own repo to seperate the step of creating a freesanding binary and minimal Kernel in Rust. <br>
Our minimal kernel is able to initialize the necessary hardware components, set up a basic execution environment, and write "Hello, World!" directly to the VGA buffer, thereby displaying the message on the screen :D

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

After running, qemu should display a simple "Hello World" from the bootimage
![image](https://github.com/raffifasaro/simpleRustKernel/assets/134242785/5dd570ee-647f-4b94-834e-48f898bfc53c)

Disclaimer:<br>
There are a lot of comments because I use this project myself to get more familiar with the Rust programming language, especially in low level use cases :)
