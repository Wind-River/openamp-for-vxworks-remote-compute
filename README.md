OpenAMP for VxWorks® Remote Compute

---

# Overview
**Wind River®** core operating technologies, **VxWorks®** and **Wind River Linux** leverage Symmetric Multi Processing on multicore processors, and **Wind River Helix™ Virtualization Platform** 
 runs a supervised AMP configuration, managing and separating operating systems across these cores in a flexible way.  On the ARM® architecture, these systems typically run on the main processor clusters and leverage Application Processor Units (APUs) such as the ARM Cortex®-A53.  As systems become increasingly more complex, and require a higher level of often specialized compute, many systems contain other Remote Processor Units (RPUs) such as the ARM Cortex-R5, that can be used for compute offload by applications running on the APUs.  There are two protocols built into **Linux** that can be used to exploit these types of remote applications.  
* **Remoteproc** - technology that allows a master application to load and manage the life cycle of remote software running on the RPU cores (an unsupervised AMP configuration).
* **RPMsg/Virtio** - a lightweight communications stack between the master and remote that runs over shared memory.

Both the master and the remote software must implement these protocols.
The **VxWorks** Real Time Operating System is a perfect fit for remote compute or running as a master but does not ship with these protocols.

The [**OpenAMP**](https://github.com/OpenAMP) project extends these protocols to other systems including RTOSes such as **VxWorks**.

The **OpenAMP for VxWorks Remote Compute** project contains software and instructions for showcasing applications that are initated from one of the three **Wind River** core technologies running on an ARM Cortex-A53 that leverage **VxWorks** running on an ARM Cortex®-R5. Each of the masters,  **VxWorks OpenAMP**, **Wind River® Linux**, or a **Wind River Linux** guest managed by **Helix Virtualization Platform**; hosts and manages a **VxWorks OpenAMP** remote, that is loaded from a file system accessible by the master. A simple application is used to demonstrate **Remoteproc** and **RPMsg/VirtIO** between master and remote. In all demos, the target hardware is a **Xilinx® Zynq® UltraScale+™ MPSoC ZCU102** reference platform. 

The following table has links to the demo documentation and highlights the technology used in each use-case:  

Demo | VxWorks 7 SR0620 | VxWorks Zcu102 IPI driver | VxWorks openamp layer | Wind River Linux LTS 18 | wr-vxworks7-openamp-demo-for-xilinx-zcu102 layer | Helix Virtualization Platform SR0620 and wr-vxvirt-arm64 layer | BOOT.BIN  
:---: |:---:|:---:|:---:|:---:|:---:|:---:|:---:
[**VxWorks OpenAMP** master and **VxWorks OpenAMP** Remote](https://github.com/Wind-River/vxworks7-openamp-layer-for-zcu102) | [Required](https://www.windriver.com/products/vxworks/) | [Here](https://github.com/Wind-River/vxworks7-ipi-driver-for-zcu102) | [Here](https://github.com/Wind-River/vxworks7-openamp-layer-for-zcu102) | | | | [2018.1 (Tested)](https://xilinx-wiki.atlassian.net/wiki/spaces/A/pages/18841902/2018.1+u-boot+release+notes#id-2018.1u-bootreleasenotes-Features)  
[**Wind River Linux** master and **VxWorks OpenAMP** remote](https://github.com/Wind-River/wr-vxworks7-openamp-demo-for-zcu102) | [Required](https://www.windriver.com/products/vxworks/) | [Here](https://github.com/Wind-River/vxworks7-ipi-driver-for-zcu102) | [Here](https://github.com/Wind-River/vxworks7-openamp-layer-for-zcu102) | [Required](https://www.windriver.com/products/linux/) | [Here](https://github.com/Wind-River/wr-vxworks7-openamp-demo-for-zcu102) | | [2018.1 (Tested)](https://xilinx-wiki.atlassian.net/wiki/spaces/A/pages/18841902/2018.1+u-boot+release+notes#id-2018.1u-bootreleasenotes-Features)  
[**Wind River Linux Helix Virtualization Platform** guest master and **VxWorks OpenAMP** remote](https://github.com/Wind-River/wr-vxworks7-openamp-demo-for-zcu102) | [Required](https://www.windriver.com/products/vxworks/) | [Here](https://github.com/Wind-River/vxworks7-ipi-driver-for-zcu102) | [Here](https://github.com/Wind-River/vxworks7-openamp-layer-for-zcu102) | [Required](https://www.windriver.com/products/linux/) | [Here](https://github.com/Wind-River/wr-vxworks7-openamp-demo-for-zcu102) | [Required](https://www.windriver.com/products/helix-platform/) | Custom (Please contact Wind River)


# Project License
This top level project contains no sources.
Text license notices can be found in the LICENSE_NOTICES.txt file in each 
project top level directory. Different files may be under different licenses.
Each source file should include a license notice that designates the licensing
 terms for the respective file.


# Legal Notices

All product names, logos, and brands are property of their respective owners. All company, 
product and service names used in this software are for identification purposes only. 
Wind River and VxWorks are registered trademarks of Wind River Systems, Inc.  Xilinx,
UltraScale,  Zynq, are trademarks of Xilinx in the United States and other countries.
Arm and Cortex are registered trademarks of Arm Limited (or its subsidiaries) in the US 
and/or elsewhere. 

Disclaimer of Warranty / No Support: Wind River does not provide support 
and maintenance services for this software, under Wind River's standard 
Software Support and Maintenance Agreement or otherwise. Unless required 
by applicable law, Wind River provides the software (and each contributor 
provides its contribution) on an "AS IS" BASIS, WITHOUT WARRANTIES OF ANY 
KIND, either express or implied, including, without limitation, any warranties 
of TITLE, NONINFRINGEMENT, MERCHANTABILITY, or FITNESS FOR A PARTICULAR 
PURPOSE. You are solely responsible for determining the appropriateness of 
using or redistributing the software and assume any risks associated with 
your exercise of permissions under the license.
