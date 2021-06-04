---
layout: article
title: Using Containers on Linux
description: >
   How to setup and use LXC/LXD
keywords:
  - Support
  - Pop
  - Ubuntu
  - LXC
  - LXD
image: http://support.system76.com/images/system76.png
hidden: false
section: software-applications

---

# Using Containers on Linux

Sometimes an older version of a library or libraries for an application is needed for development. It is faster and easier to use LXC/LXD to setup a Container of that release and work in that Container.

### Software

First open a terminal like so:

Pop!_OS : <kbd><span class="fl-pop-key"></span></kbd> + <kbd>T</kbd>

Ubuntu : <kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>T</kbd>

Install the software with this command in the terminal.

```bash
sudo apt install lxd lxd-client
```

### Setup

Tell LXD what storage and network is needed with this command:

```bash
sudo lxd init
```

### Create a container

Now create our first container with this command:

```bash
lxc launch ubuntu:16.04 first
```

This will create a container based on Ubuntu 16.04 with the name 'first'.

List and confirm that the container was created with this command:

```bash
lxc list
```

The container can be stopped with this command:

```bash
lxc stop first
```

Or the container can be deleted:

```bash
lxc delete first
```

### Enter the container

Enter the container with this command:

```bash
lxc exec first -- /bin/bash
```

Or just one command can be issued without entering the container:

```bash
lxc exec first -- apt update
```

### Sharing files

For pushing a file to the container:

```bash
lxc file push filename first/tmp/
```

For pulling a file from the container:

```bash
lxc file pull first/tmp/filename .
```

---

- Document Version: 1.0.0
- Date: (Jun 12, 2018)
- Author: Aaron Honeycutt
- Contributing Editor(s): Jonathan Barda, Nathaniel