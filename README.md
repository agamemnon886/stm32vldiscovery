# stm32vldiscovery

## How to quick start programming on STM32VLDiscorevy on Linux.

1. Download [Atollic TrueStudio for Linux](https://atollic.com/resources/download/linux/)
1. In my case it was *Atollic_TrueSTUDIO_for_ARM_linux_x86_64_v8.1.0_20171023-2304.tar.gz*
1. After downloading completed unpack the tarball and start installation:

```
$ tar zxvf Atollic_TrueSTUDIO_for_ARM_linux_x86_64_v8.1.0_20171023-2304.tar.gz 
Atollic_TrueSTUDIO_for_ARM_8.1.0_installer/
Atollic_TrueSTUDIO_for_ARM_8.1.0_installer/install.sh
Atollic_TrueSTUDIO_for_ARM_8.1.0_installer/install.data
Atollic_TrueSTUDIO_for_ARM_8.1.0_installer/license.txt
$ cd Atollic_TrueSTUDIO_for_ARM_8.1.0_installer/
Atollic_TrueSTUDIO_for_ARM_8.1.0_installer$ sudo ./install.sh
```

4. I answered "yes" for all questions.
1. After installation completed find **Atollic TrueSTUDIO for ARM 8.1.0** icon in *Main Menu* and click on it.
1. Go to *"File->New->C Project"*.
1. In the appeared dialog window type project name in field *"Project name"*.
1. In the *"Project type"* select *"Executable->Embedded C Project"* and press *"Next"* button.
1. In the appeared dialog in field *"Target"* type *"stm32vl_discovery"*, select it and press *"Next"* button.
1. In the *"Select software settings"* dialog press *"Next"* button.
1. In the *"Select hardware debug settings"* dialog select *"ST-LINK"* and press *"Next"* button.
1. In the *"Select platforms and configurations you wish to deploy on"* dialog tick *"Debug"* and *"Release"* and press *"Finish"*.
1. Now you can see your project tree on the left side in the window *"Project Explorer"*.
1. I could not debug using Atolic debugger. When I press *"Run->Debug"* I got the following error message:

```
Atollic TrueSTUDIO gdbserver for ST-Link. Version 4.1.0 (LINUX64 2017-10-13 11:55:35 15425)
Copyright 2010-2017, Atollic AB. 


Starting server with the following options: 
        Persistant Mode            : Disabled 
        LogFile Name               : debug_log.txt
        Logging Level              : 1
        Listen Port Number         : 61235
        Status Refresh Delay       : 15s
        Verbose Mode               : Disabled 
        SWD Debug                  : Enabled 

	 Error in opening Log File debug_log.txt
	 Logging is disabled
Target unknown error 0

Error in initializing ST-Link device.
Reason: Unknown. Please check power and cabling to target.
```

15. It may be happened because I already had the installed st-link from [www.st.com](www.st.com) . Anyway let's use the installed st-link.
1. Go to *"Run->Debug Configurations"*.
1. Select *"Configure Workspace Settings"* in *"Main"* tab.
1. In the appeared dialog window on the left side select *"Run/Debug->Embedded C/C++ Application->Debug Hardware->ST-link GDB Server"*.
1. On the right side in *"Server"* type path to st-util. For me it was */usr/local/bin/st-util* . After that press *"Apply"* and *"OK"*.
1. In the "Debug Configurations" dialog press *"Debug"* to start debugging.


## How to create FreeRTOS project on STM32VLDiscorevy on Linux.

1. Go to *"File->New->Download new example project from TrueSTORE"*.
1. Type *stm32vl* and select *"STM32VL_Discovery_FreeRTOS_Simple_Demo"*.
1. Press *"Finish"* button.



