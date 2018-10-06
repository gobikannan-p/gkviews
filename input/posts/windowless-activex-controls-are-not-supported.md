Title: Windowless ActiveX controls are not supported
Published: 05/25/2017
Category: General
Tags: General
---

In windows 7 environment you may receive “Unable to get window handle, Windowless ActiveX controls are not supported..” exception, when you display a child form that contains ActiveX user controls. The user control may be a third party control. To avoid this exception you may disable DEP (Data Execution Prevention) for your ActiveX control.

DEP (Data Execution Prevention) is a security feature from windows 7 operating system to prevent damage your system from viruses and other security threats. If your user control access memory in an incorrect way, the DEP will close the program.

If you trust the user control which you integrated in the application, you may disable the DEP for that program in following way.

Go to Control Panel -> System and Security -> System

You will get a list of options in the left side of the window.

[comment]: # (![DEP 1](http://www.gkviews.com/wp-content/uploads/DEP_1.png)

Click on the “Advanced system settings” link, you will get System properties window.

In that System properties window, switch to Advanced tab and click on the settings button under the Performance section, you will get Performance Options window.

[comment]: # (![DEP 2](http://www.gkviews.com/wp-content/uploads/DEP_2.png)

Switch to Data Execution Prevention tab and select “Turn on DEP for all programs and services except those I select:” option.

[comment]: # (![DEP 3](http://www.gkviews.com/wp-content/uploads/DEP_3.png)

Now the “Add…” button is enabled, then you can add the specific program which you want to disable the DEP.

This changes will apply only after you restart the system.

[comment]: # (![DEP 4](http://www.gkviews.com/wp-content/uploads/DEP_4.png)

If you want to disable the DEP completely using the command prompt you need to do the following steps.

Select Start Menu -> All Programs -> Accessories.

You will see the Command Prompt under Accessories. Right click on the Command Prompt and select “Run as administrator”.

Enter the following command and execute it to disable DEP completely.

```cmd
bcdedit.exe /set {current} nx AlwaysOff
```

If you want to enable DEP, you need to execute the following command.

```cmd
bcdedit.exe /set {current} nx AlwaysOn
```

These changes will be affected after you restart the computer.

By default DEP is turned on in windows 7.