## System Requirements

| Operating System        | Windows 10, Windows Server 2012 R2 or later          |
| ----------------------- | -----------------------------------------------------|
| Microsoft .NET Framework | 4.8 &nbsp;&nbsp;<span style="color:blue">[Download](https://dotnet.microsoft.com/download/dotnet-framework/net48)</span>             |
| Windows PowerShell      | > 3.0                                                |
| Database                | Microsoft SQL Server 2012 or later				     |           
| Browser                 | Chrome, Mozilla Firefox, IE 11 and Microsoft Edge 	 |
| Microsoft Visio         | 2003/2007/2010                                       |

## Pre-requisites Setup
The following installers need to run for 64/32-bit Operating System.
1.	Azure AD auth for SQL server *(Required only if you use Azure AD authentication for SQL Azure)*

	<span style="color:blue">[Microsoft Active Directory Authentication Library for Microsoft SQL Server](https://www.microsoft.com/en-us/download/confirmation.aspx?id=48742)</span>

2.	SMO for x64 (64 bit)

	<span style="color:blue">[Shared Management Objects](https://cdn.apppoint.com/bizapp/smo/x64/SharedManagementObjects.msi)</span>

	<span style="color:blue">[Sql Dom](https://cdn.apppoint.com/bizapp/smo/x64/SqlDom.msi)</span>
	
	<span style="color:blue">[Sql CLR Types](https://cdn.apppoint.com/bizapp/smo/x64/SQLSysClrTypes.msi)</span>

3.	SMO for x86 (32 bit)

	<span style="color:blue">[Shared Management Objects](https://cdn.apppoint.com/bizapp/smo/x86SharedManagementObjects.msi)</span>

	<span style="color:blue">[Sql Dom](https://cdn.apppoint.com/bizapp/smo/x86/SqlDom.msi)</span>
	
	<span style="color:blue">[Sql CLR Types](https://cdn.apppoint.com/bizapp/smo/x86/SQLSysClrTypes.msi)</span>
	
4.	VC++ Redistributable installer for x64 and x86

	<span style="color:blue">[64 bit VC++ Runtime](https://cdn.apppoint.com/bizapp/vcredist/vcredist_x64.exe)</span>

	<span style="color:blue">[32 bit VC++ Runtime](https://cdn.apppoint.com/bizapp/vcredist/vcredist_x86.exe)</span>

### IIS Setup

IIS or Internet Information Server is the server used to host the .Net web applications. IIS is normally installed on a Windows Server. 
The IIS on windows 10 or server versions has to be set-up and enabled on your system.
1.	Open Windows Run prompt. Type "inetmgr" and enter. The IIS Manager window will open, if installed.
2.	If IIS Manager does not open, to enable it on your system, go to Control Panel >> Programs >> Programs and Features.
3.	In the left panel, select the Turn Windows features on or off.
 
![windowsfeature](/images/systeminstalls/windowsfeatureonoff.png)

4.	In the Turn Windows features on or off, select the checkbox *Internet Information Services Hostable Web Core* and click OK. 
5.  Enable *Internet Information Services*. Make sure the following items are enabled under this node.
6.  Expand the node and navigate to "World Wide Web Services* >> *Application Development Features*
7.  Check the features such as .NET Extensibility, ASP.NET 4.8, ISAPI Filters, Server-side Includes and WebSocket Protocol.
8.  Navigate to *Common HTTP Features* and enable feeatures such as Default Document, HTTP Errors, HTTP Redirection and Static Content.
9.  Navigate to *Performance Features* and enable features such as Dynamic Content Compression and Static Content Compression.
10. If you require Windows Integrated Authentication for the web site, it can be enabled in *Security* >> Windows Authentication. 
11.	The installation will take several minutes, once it is completed, click Close.
12.	To ensure that IIS is installed and working, type IIS in the Search bar near the Start button. You’ll see the Internet Information Services Manager, click Open. OR
13.	In the Command Prompt, type inetmgr. The IIS Manager window is open onscreen. 
14.	In the IIS Manager window, click Application Pools, and check if BizAPP Pool services is in the “Started” state.

### Required Installations

You can clone the repository and install the build using Git Commands OR the Desktop interface of BitBucket (Sourcetree) and GitHub (GitHub Desktop).

a)	Install **Git Bash**: Use the Git 2.21.0 version and above
b)	Install **SourceTree 3.3.8**or the latest version (Not a mandatory requirement) 

### Install Git Bash 

Git Bash is a source control management system for Windows. It allows users to type Git commands that make source code management easier through versioning and commit history. Git Bash is not a GUI software; it is a command-line prompt which provides a BASH emulation to run Git from the command line. You can use Git Bash to write and run commands on the terminal and update the build.

1.	Download the latest **Git for Windows Installers** from [git instal llink](https://gitforwindows.org/) 
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

The Git cheatsheet with basic commands is available in the link : https://education.github.com/git-cheat-sheet-education.pdf. 

### Install Sourcetree 

Sourcetree is a free Git GUI used for visual representation of repositories.It provides you with an interface that gives you the same capabilities you have with Git without the need to use the command line. It simplifies how you interact with your Git repositories so you can focus on coding.

1. Open the [sourcetreeinstalllink](https://www.sourcetreeapp.com/). The **Home page** of Sourcetree is open on screen.
2. Click the **Download Free** button, or Click **Download for Windows**. The software gets downloaded to your system.
3. Double-click or Run the **.exe** file. This begins the installation process, click **Install**.
4. In the **Agreement of Terms and Conditions** form, select the checkbox **I agree to the Atlassian Customer Agreement.** and click **Continue.**
5. You need an Atlassian account to use Sourcetree. When you get to this screen, click **Use an Existing account**, enter your account ID to open Sourcetree.
6. If you are creating a new account, select **Sign-in** and add your credentials. or You can signin using your **Google** or **Windows** account.
7. A one-time registration is required to start using your Bitbucket account and connect to your accounts in GitHub, GitBash. In the **Registration** window, select **Bitbucket.**
 
![bitbucketreg](/images/systeminstalls/bitbucket_register.png)

8. If Sourcetree is already installed, select the **Notification** flag and update it to the latest available version.

7. A **Confirm access to your account** window appears on screen. Select the **Read and modify your repositories and their pull requests to enable the Read/Write access** option.
 
![bitbucketaccess](/images/systeminstalls/bitbucket_grantaccess.png)

8. Select the **Grant Access** button. This completes the Registration Process.
 
![bitbucketcomplete](/images/systeminstalls/bitbucket_completeregister.png)

9. Click **Next** to proceed to the next step,**Installing the Tools**.
 
![sourceversioncontrol](/images/systeminstalls/sourcetree_versioncontrol.png)

10. The **Version control systems** gets downloaded to your system.
 
![sourcetreemercurial](/images/systeminstalls/sourcetree_mercurial.png)

11. The **installation of the tool** will be completed after the Mercurial files extraction. 
 
![sourcecompleteinstall](/images/systeminstalls/sourcetree_completeinstall.png)

12. On completing the installation, click **Next** to view the **Preferences** window.
13. Select the **Set the global author details for Git and Mercurial**. A **Load SSH key?** prompt window appears on screen.  
  
![addpreferences](/images/systeminstalls/sourcetree_prefernces.jpg)

14. You may see the **Load SSH Key?** dialog after installation. Click **No**, if you don't have one and want to use Sourcetree to create one.
 
![loadssh](/images/systeminstalls/loadssh.png)