# Introduction to CISCO IOS

The Cisco Internetwork Operating System (**Cisco IOS**) is a generic term for the collection of network operating systems used by Cisco networking devices.

> The OS on home routers is usually called **firmware**. The most common method for configuring a home router is by using a web browser-based GUI.

## Operating Systems

Let's talk about OSs before jumping into OSs in CISCO.

![architecture_of_a_operating_system.jpg](../img/architecture_of_a_operating_system.jpg)

### Hardware

The hardware consists of the memory, CPU, arithmetic-logic unit, various bulk storage devices, I/O, peripheral devices and other **physical devices**.

### Kernel

The kernel is the central component of most computer operating systems; it is a **bridge** between applications and the actual data processing done at the hardware level.

The kernel's responsibilities include:
- Managing the system's resources (the communication between hardware and software components).
- Provide the lowest-level abstraction layer for the resources (especially processors and I/O devices) that application software must control to perform its function.
- It typically makes these facilities available to application processes through inter-process communication mechanisms and system calls.

### Shell

A shell is a **piece of software that provides an interface for users** to an operating system which provides access to the services of a kernel. The name shell originates from shells being an outer layer of interface between the user and the innards of the operating system (the kernel). 

Operating system shells generally fall into one of two categories:

- **Command-line interface (CLI)**: Provides an environment (usually a black window with white text) to write commands to perform a certain CLI system task.
- **Graphical user interface (GUI)**: It uses computer graphics. One can click on the icon; drag the object with the help of a mouse. There is no need to remembering commands in this. 

In either category the primary purpose of the shell is to invoke or "launch" another program; however, shells frequently have additional capabilities such as viewing the contents of directories.

### Operating System vs Kernel

The **kernel is part of the operating system** and closer to the hardware it provides low level services like:

- Device driver
- Process management
- Memory management
- System calls

An operating system also includes applications like the user interface (shell, gui, tools, and services).

## Terminal emulators

A terminal emulator is a a computer application that emulates or behaves like a hardware terminal composed of at least a keyboard and monitor.

Terminal emulators use the same protocol use by TTY machines (teletype machines) to establish a session with the operating system. TTY machines were dedicated keyword and monitor used to connect enterprise servers or mainframes.

Common terminal emulators are:
- Putty
- Tera Term
- OS X terminal
- SecureCRT


## CISCO IOS

Cisco networking devices run particular versions of the Cisco IOS. The IOS version is dependent on the type of device being used and the required features. While all devices come with a default IOS and feature set, it is possible to upgrade the IOS version or feature set to obtain additional capabilities.

### Access methods

There are several ways to access the CLI environment and configure the device.

- Remote options:
    - **Telnet**: Used for remote management **without a securely encrypted connection, data is sent in plaintext**.
    - **SSH**: Used for remote management, this method provides password encrypted authentication and transport of session data, this keeps the user ID, pass, and details of the management session private.
- Out of band:
    - **Console**: Used for an initial configuration and maintenance purposes only **(out-of-band access**), by connecting a special cable (rollover or console cable) to the console port.
    - **AUX port**: a legacy auxiliary port that was used to establish a CLI session remotely using a modem (**out-of-band**).

### Cisco IOS command modes of operation

As a security feature, the Cisco IOS software separates **management access**

- **User Exec** Mode: Allows access to only a limited number of basic monitoring commands, it is a view-only mode.  prompt: `hostName>`
- **Privileged Exec** Mode: Allows access to all the commands and features. To access this mode you need to type the `enable` command in the User exec Mode. prompt:

```
hostName>enable
hostName#    <-- the # symbol says we are in the privileged mode
```

- To configure the device, the user must enter Global Configuration Mode (**Global Config Mode**). To access this mode you need to type the *configure terminal* command in the Privileged exec Mode. prompt:` hostName(config)#`
    - From this mode you can enter to different sub-configuration modes:
        - **Interface Configuration Mode**:  Used to configure a switch port or router network interface. default prompt: `hostName(config-if)#`.
        - **Line Configuration Mode**: Used to configure console, SSH, Telnet, or AUX access. default prompt: `hostName(config-line)#`

### Navigate between IOS modes

- Press **exit** to return to the previous command mode.
- **end** or **ctrl+z** to return to the privileged exec mode from any other mode.
- **enable** from the user exec mode to enter to the privileged exec mode.
- **disable** from the privileged exec mode to return to the user exec mode.

### IOS command structure

Structure:

    prompt    command    keyword/argument

- **prompt**: the set of characters that define the mode (device name+symbol).
- **Keyword**: a specific parameter defined in the operating system.
- **Argument**: not predefined; a value or variable defined by the user.

Examples:

`Switch>show ip protocols`

`Switch>ping 192.168.10.5`

In these examples:

- show, ping are commands
- ip is a keyword
- 192.168.10.5 is an argument

### IOS command syntax

When reading the documentation you will see the following syntax to describe the usage of a command:

- **Boldface**: Commands and keywords
- *Italics*: arguments
- `[an optional element]`
- `{a required element}`
- `[x {y | z}]` a required choice within an optional element

### IOS help features

- **Context-Sensitive Help**:
    - Enables you to quickly find which commands are available in each command mode
    - Which commands start with specific characters or group of characters
    - Which arguments and keywords are available to particular commands

To access context-sensitive help, simply enter a question mark, **?**, at the CLI. 

- **Command Syntax Check**:
    - It verifies that a valid command was entered by the user, and it will provide feedback describing what is wrong with the command. 

### Hotkeys

- **CLI Line Editing**:
    - **tab**: completes a partial command entry
    - **backspace**: erases the character to the left of the cursor
    - **Ctrl+D**: erases the character right to the cursor
    - **Ctr+E**: Moves the cursor to the end of the command line
    - **Ctr+A**: Moves the cursor to the beginning of line
- **At the "----More----" prompt**:
    - **Enter key**: Display the next line
    - **Space bar**: Display the next screen
    - **Any key**: Ends the display string, returning to privileged exec
- **Break keys**:
    - **Ctrl+C**: Ends the configuration mode and returns to the privileged exec mode. When in setup mode, aborts back to the command prompt
    - **Ctrl+Shift+6**: All-purpose break sequence. use to abort DNS lookups, traceroutes, pings, etc.
    - **Ctrl+Z**=end


## External resources

1. [http://cis2.oc.ctc.edu/oc_apps/Westlund/xbook/xbook.php?unit=04&proc=page&numb=1](http://cis2.oc.ctc.edu/oc_apps/Westlund/xbook/xbook.php?unit=04&proc=page&numb=1)
2. [http://zseries.marist.edu/enterprisesystemseducation/zinsights/ECI%20No.%208%203270%20TE%20V2b.pdf](http://zseries.marist.edu/enterprisesystemseducation/zinsights/ECI%20No.%208%203270%20TE%20V2b.pdf)