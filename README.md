<h1 align="center">Nano Processor </h1>
<p align="center"><i>Implementing a 4 bit nano processor </i></p>

<img src="assets/spaces_rEPCmpm8DJRtInZH7OOg_uploads_git-blob-207ad4ae1875dcad2914623f4e545e0f9ec6c664_pkuos.svg" alt="Awesome README Templates" />

## Overview

As part of the <b>CS1050 - Computer Organization and Digital Design</b> module,
This lab involves designing and developing a 4-bit processor capable of executing four specific instructions. By completing this lab, you will achieve the following objectives:

<ul>
    <li>Design and develop a 4-bit arithmetic unit that can add and subtract signed integers.</li>
    <li>Decode instructions to activate necessary components on the processor.</li>
    <li>Design and develop k-way b-bit multiplexers or tri-state busses.</li>
    <li>Verify the functionality of the processor through simulation and implementation on a development board.</li>
</ul>

## Components

<ul>
    <li><strong>4-bit Add/Subtract Unit</strong>
        <ul>
            <li>This unit should be capable of adding and subtracting numbers represented using 2’s complement.</li>
        </ul>
    </li>
    <li><strong>3-bit Adder</strong>
        <ul>
            <li>This unit is used to increment the Program Counter.</li>
        </ul>
    </li>
    <li><strong>3-bit Program Counter (PC)</strong>
        <ul>
            <li>The Program Counter needs to be reset to 0 when required. Build it using D Flip-Flops with a clear/reset input.</li>
        </ul>
    </li>
    <li><strong>k-way b-bit Multiplexers</strong>
        <ul>
            <li>A k-way b-bit multiplexer can take in k inputs, each with b bits, rather than a single bit. The output is a group of b bits. There are log<sub>2</sub> k control bits, and these control bits are used to select one of the k groups of b bits rather than a single bit.</li>
        </ul>
    </li>
    <li><strong>Register Bank</strong>
        <ul>
            <li>Contains 8, 4-bit registers (named R0 to R7).</li>
            <li>Hardcode value of R0 to all 0s.</li>
        </ul>
    </li>
    <li><strong>Program ROM</strong>
        <ul>
            <li>This stores our Assembly program.</li>
        </ul>
    </li>
    <li><strong>Buses</strong>
        <ul>
            <li>Used 3, 4, and 12-bit buses to connect components. This had greatly simplified our design rather than running so many wires around. We used labels such as D(3 downto 0), I(11 downto 0), M(3 downto 0), and R(3 downto 0).</li>
        </ul>
    </li>
    <li><strong>Instruction Decoder</strong>
        <ul>
            <li> The Instruction Decoder circuit is activating necessary components based on the instructions the user wish to execute</li>
        </ul>
    </li>
  
</ul>


The following table contains the list of functions the shell should support
alongside with a brief description of what they are supposed to do.

<img src="assets/Screenshot 2024-07-06 at 17.27.42.png" alt="Awesome README Templates" />

You can see in the following screenshots how my developed operating system works for those commands giving the system information of the machine. If you are also supposed to use this project, make sure to change the name in the **'init.c'** file.

<img src="assets/screenshot1 (1).jpeg" alt="Awesome README Templates" />
<img src="assets/screenshot2 (1).jpeg" alt="Awesome README Templates" />

## Step 2: Enable programs to interact with the OS via system calls.

The base code already supports loading and running user programs, but no I/O or interactivity is possible. In this step, I enabled programs to interact with the OS via system calls. For this part of the project, I primarily worked in the ]**userprog** directory, but the task required interacting with almost every other part of Pintos.

Previously, all the code ran as part of the operating system kernel, giving test code full access to privileged system parts. Running user programs changes this dynamic. This project dealt with the consequences of allowing more than one process to run simultaneously, each with a single thread. User programs operate under the illusion that they have the entire machine, so managing memory, scheduling, and other states correctly is crucial to maintain this illusion.

Unlike the previous part, where test code was compiled directly into the kernel requiring specific function interfaces, this step involved testing the OS by running user programs. 

You can see in the following screeshot how my developed os works for the in-built test cases.You can also check how extent your implementation supports for running user programs.

<img src="assets/Screenshot 1.jpeg" alt="Awesome README Templates" />

## Source Tree Overview

Let's take a look at what's inside. Here's the directory structure that you should see in **pintos/src**:

**"threads/"**

Source code for the base kernel,which modified in step 1


**"userprog/"**

Source code for the user program loader, which modified during step 2

**"vm/"**

An almost empty directory.

**"filesys/"**

Source code for a basic file system.

**"devices/"**

Source code for I/O device interfacing: keyboard, timer, disk, etc. Need to modify the timer implementation in step 1.

**"lib/"**

An implementation of a subset of the standard C library. The code in this directory is compiled into both the Pintos kernel. In both kernel code and user programs, headers in this directory can be included using the #include <...> notation. 

**"lib/kernel/"**

Parts of the C library that are included only in the Pintos kernel. This also includes implementations of some data types that you are free to use in your kernel code: bitmaps, doubly linked lists, and hash tables. In the kernel, headers in this directory can be included using the #include <...> notation.

**"lib/user/"**

Parts of the C library that are included only in Pintos user programs. In user programs, headers in this directory can be included using the #include <...> notation.

**"tests/"**

Tests for each project. You can modify this code if it helps you test your submission.

**"examples/"**

Example user programs for use.

**"misc/"**

**"utils/"**

# Contribute

Contributions are always welcome! Please create a PR to add Github Profile.

## :pencil: License

This project is licensed under [MIT](https://opensource.org/licenses/MIT) license.

## :man_astronaut: Show your support

Give a ⭐️ if this project helped you!
Example user programs for use.
