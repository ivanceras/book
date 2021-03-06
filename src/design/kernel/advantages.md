Advantages of microkernels
==========================

Arguably, there are quite a lot advantages (and disadvantages too!) of microkernels. These will briefly be discussed here:

Modularity and customizability
------------------------------

Monolithic kernels are, well, monolithic. They do not allow as fine-grained control as microkernels. This is due to many essential components are "hard-coded" into the kernel, and thus requires modifications to the kernel itself.

Microkernels are very modular by nature. You can replace, reload, modify, change, and remove modules, on runtime, without even touching the kernel.

Modern monolithic kernels tries to solve this issue, using kernel modules, but do often still require the system to reboot.

Security
--------

Microkernels are undoubtedly _a lot_ more secure than monolithic kernels. The minimality principle of microkernels is a direct consequence of the principle of least privilege, according to which all components should have only the privileges absolutely needed to provide the needed functionality.

The vast majority of security-critical bugs in monolithic kernels stems from drivers running unrestricted in kernel mode, without any form of protection.

In other words: **drivers can do whatever, without restrictions, when running in ring 0**.

Less crashes
------------

Monolithic kernels are, when compared to microkernels, relatively crash-prone. Simple logic bugs can result in a crashed driver, which will, for a kernel space driver, crash the whole system.

In Linux, this is often seen by errors with drivers dereferencing bad pointers, ultimately resulting in kernel panics.

> TODO
