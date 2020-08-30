## System Requirements

| Operating System        | Windows 10, Windows Server 2012 R2 or later          |
| ----------------------- | -----------------------------------------------------|
| Microsoft .NET Framework | 4.8 &nbsp;&nbsp;[Download](https://dotnet.microsoft.com/download/dotnet-framework/net48)             |
| Windows PowerShell      | > 3.0                                                |
| Database                | Microsoft SQL Server 2012 or later				     |           
| Browser                 | Chrome, Mozilla Firefox, IE 11 and Microsoft Edge 	 |
| Microsoft Visio         | 2003/2007/2010                                       |

## Pre-requisites Setup
The following installers need to run for 64/32-bit Operating System.
1.	Azure AD auth for SQL server *(Required only if you use Azure AD authentication for SQL Azure)*

	[Microsoft Active Directory Authentication Library for Microsoft SQL Server](https://www.microsoft.com/en-us/download/confirmation.aspx?id=48742)

2.	SMO for x64 (64 bit)

	[Shared Management Objects](https://cdn.apppoint.com/bizapp/smo/x64/SharedManagementObjects.msi)

	[Sql Dom](https://cdn.apppoint.com/bizapp/smo/x64/SqlDom.msi)
	
	[Sql CLR Types](https://cdn.apppoint.com/bizapp/smo/x64/SQLSysClrTypes.msi)

3.	SMO for x86 (32 bit)

	[Shared Management Objects](https://cdn.apppoint.com/bizapp/smo/x86SharedManagementObjects.msi)

	[Sql Dom](https://cdn.apppoint.com/bizapp/smo/x86/SqlDom.msi)
	
	[Sql CLR Types](https://cdn.apppoint.com/bizapp/smo/x86/SQLSysClrTypes.msi)
	
4.	VC++ Redistributable installer for x64 and x86

	[64 bit VC++ Runtime](https://cdn.apppoint.com/bizapp/vcredist/vcredist_x64.exe)

	[32 bit VC++ Runtime](https://cdn.apppoint.com/bizapp/vcredist/vcredist_x86.exe)

### IIS Setup

IIS or Internet Information Server is the server used to host the .Net web applications. IIS is normally installed on a Windows Server. 
The IIS on windows 10 or server versions has to be set-up and enabled on your system.
1.	Open **Windows** Run prompt. Type **inetmgr** and enter. The **IIS Manager** window will open, if installed.
2.	If IIS Manager does not open, to enable it on your system, go to **Control Panel >> Programs >> Programs and Features**.
3.	In the left panel, select the **Turn Windows features on or off**.
4.	In the Turn Windows features on or off, select the checkbox *Internet Information Services Hostable Web Core* and click OK. 
5.  Enable *Internet Information Services*. Make sure the following items are enabled under this node.
![windowsfeature](/images/systeminstalls/windowsfeatureonoff.png)
6.  Expand the node and navigate to *World Wide Web Services* >> *Application Development Features*
7.  Enable features such as *.NET Extensibility, ASP.NET 4.8, ISAPI Filters, Server-side Includes and WebSocket Protocol*.
8.  Navigate to *Common HTTP Features* and enable features such as *Default Document, HTTP Errors, HTTP Redirection and Static Content*.
9.  Navigate to *Performance Features* and enable features such as *Dynamic Content Compression and Static Content Compression*.
10. If you require Windows Integrated Authentication for the web site, it can be enabled in *Security* >> *Windows Authentication*. 
11.	The installation will take several minutes, once it is completed, click Close.
12.	To ensure that IIS is installed and working, type IIS in the Search bar near the Start button. You’ll see the Internet Information Services Manager, click Open.
13.	Alternately, in the Run Prompt, type inetmgr. The IIS Manager window opens when successfully installed.

## Installation Roles

There are multiple ways to install the software for BizAPP Platform. If you are evaluating BizAPP Platform or going through the process of Self training, other software requirements is optional.
This not only makes further installation steps optimal, but also enables the users quickly to get started with the Platform.

* [Self training or Evaluation](#self-training-or-evaluation)
* [Regular development using the Platform](#regular-development-using-the-platform)

### Self training or Evaluation

Self training or evaluation typically does not require using Git tools to install the software from the public Git repository. Instead it can be downloaded from the site and 
manually installed.

To download the build repository as zip file, navigate to the [link](https://github.com/apppoint-release/BizAPP-Public) in any browser
and click on *Code >> Download ZIP*.

![bitbucketreg](/images/bizapppublic/DownloadRepoZip.png)

Refer to [Installing BizAPP](installbizapp.md) for further instructions.

### Regular development using the Platform

Development activities require Git tools to be installed on the machine to receive future updates on the Platform. 
You can either clone the repository and setup build using Git Commands or the Desktop interface of BitBucket (Sourcetree)/GitHub (GitHub Desktop).

#### Install Git Bash 

Git Bash is a source control management system for Windows. It allows users to type Git commands that make source code management easier through versioning and commit history. 
Git Bash is not a GUI software; it is a command-line prompt which provides a BASH emulation to run Git from the command line. 
You can use Git Bash to write and run commands on the terminal and update the build.

1.	Download the latest **Git for Windows Installers** from [link](https://gitforwindows.org/) 
2.	Double-click on the **.exe file** to open and execute Git Bash. A **Git Setup Wizard** appears on screen.
3.	In the Select Destination location, click **Browse**, select the destination location where you want to install Git, and click **Next**.

![gitdestination](/images/systeminstalls/gitsetup_destination.png)

4.	In the **Select Components window,** leave all the default options checked. Check other additional components you want to install and click **Next**.

![gitcomponents](/images/systeminstalls/gitsetup_components.png)
 
5.	In the **Choosing the default editor used by Git**, select the **Use NotePad++ as Git’s default editor** from the drop-down and click **Next**. 

![giteditor](/images/systeminstalls/gitsetup_defaulteditor.png)

6.	In the **Adjusting your PATH environment**, keep the default **Use Git from the command line and also from 3rd-party software** as shown below. This option will allow you to use Git from either Git Bash or the Windows Command Prompt. Click **Next**.
 
 ![gitenvironment](/images/systeminstalls/gitsetup_environment.png)

7.	In **Choosing HTTPS transport backend**, leave the default **Use the OpenSSL library** selected and click **Next**. 

![githttpsbackend](/images/systeminstalls/gitsetup_httpsbackend.png)
 
8.	In the **Configuring the line ending conversions window**, Select **Checkout Windows-style**, commit Unix-style line endings unless you need other line endings for your work.

![gitlinendings](/images/systeminstalls/gitsetup_lineendings.png)
 
9.	In the **Configuring the terminal emulator to use with Git Bash window**, Select **Use MinTTY (the default terminal of MSYS2)**.

![gitterminalemulator](/images/systeminstalls/gitsetup_terminalemulator.png)
 
10.	On the **Configuring extra options window** leave the default options checked unless you need the symbolic links, Click **Install** button.

![gitextraoptions](/images/systeminstalls/gitsetup_extraoptions.png)
 
11.	Once completed, you can check the option to **Launch Git Bash** if you want to open a Bash command line or, if you selected the Windows command line, run Git from the Windows command line.
 
 ![gitinstall](/images/systeminstalls/gitsetup_install.png)
 
 ![gitcompletewizard](/images/systeminstalls/gitsetup_completewizard.png)
  
12.	Click **Finish** to complete the installation. 

![gitcommandinterface](/images/systeminstalls/gitcommandinterface.png)

13.	Run the git commands to initialize, configure Git username and Email.  

The Git cheatsheet with basic commands is available in the [link](https://education.github.com/git-cheat-sheet-education.pdf). 

#### Install GitHub Desktop (Optional)

GitHub Desktop is a tool that allows you to interact with GitHub from the desktop. With this new application, you can work easier without having to depend on your browser. 

1. Open the [link](https://desktop.github.com/). Click the **Download for Windows (64Bit)** button.
2. After successful download, Run the **GitHubDesktopSetup.exe** file. This begins the installation process.
3. GitHub Desktop opens automatically after installation. It prompts for Sign in steps. Click on **Skip this step**.
4. In **Configure Git** page, fill in the *Name* and *Email* fields and click on **Continue**.

![githubconfigure](/images/github/configure.png)

5. Refer to [Release Build Public](bizapppublic.md) for further instructions on cloning the repository.