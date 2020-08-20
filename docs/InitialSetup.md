---
id: doc2
title: Initial Setup
sidebar_label: Initial setup
---
[Install_Services](/images/installservices.png)
This document outlines the steps for *Initial Setup* 

## INITIAL SETUP 
The system should be set-up with required installations, pre-requisite software’s and made ready to install the Modeler.

### System Requirements

| Operating System        | Windows 10                                           |
| ----------------------- | -----------------------------------------------------|
| Microsoft.Net Framework | Download the .NET 4.8 Frame Work RunTime             |
|                         | https://dotnet.microsoft.com/downloadWindows 10      |
| Windows PowerShell      | 3.0                                                  |
| Database                | Microsoft SQL Server 2016 Standard/Enterprise edition|
|                         | Microsoft SQL Server Express 2008, 2012 edition.     |           
| Browser                 | Chrome, Mozilla Firefox, IE 10/11, Microsoft Edge 11 |
| Microsoft Visio         | 2003/2007/latest.                                    |
| Notepad/Notepad++       | Install the latest version.                          |



## Pre-requisite Setup
The following installers need to run for 64/32-bit Operating System.
1.	Azure AD auth for SQL server
***
https://www.microsoft.com/en-us/download/confirmation.aspx?id=48742
***
2.	SMO for x64 (64 bit)
***
https://cdn.apppoint.com/bizapp/smo/x64/SharedManagementObjects.msi
https://cdn.apppoint.com/bizapp/smo/x64/SqlDom.msi
https://cdn.apppoint.com/bizapp/smo/x64/SQLSysClrTypes.msi
***
3.	SMO for x86 (32 bit)
***
https://cdn.apppoint.com/bizapp/smo/x86/SharedManagementObjects.msi
https://cdn.apppoint.com/bizapp/smo/x86/SqlDom.msi
https://cdn.apppoint.com/bizapp/smo/x86/SQLSysClrTypes.msi
***
4.	VC++ Redistributable installer for x64 and x86
***
https://cdn.apppoint.com/bizapp/vcredist/vcredist_x64.exe
https://cdn.apppoint.com/bizapp/vcredist/vcredist_x86.exe
***

### IIS Setup

IIS or Internet Information Server is the server used to host the .Net web applications. IIS is normally installed on a Windows Server. The IIS on windows 10 has to be set-up and enabled on your system.
1.	On the Command prompt, run inetmgr. The IIS Manager window is available on screen.
2.	If IIS Manager does not open then to enable it on your system, open the Command prompt, go to Control Panel>>Programs>>Programs and Features.
3.	In the left panel, select the Turn Windows features on or off.
 
! Figure 1: Turn on Windows Features On/Off

4.	In the Turn Windows features on or off, select the checkbox “Internet Information Services Hostable Web Core” and click OK. 
5.	The installation will take several minutes, once it is completed, click Close.
6.	To ensure that IIS is installed and working, type IIS in the Search bar near the Start button. You’ll see the Internet Information Services Manager, click Open. OR
7.	In the Command Prompt, type inetmgr. The IIS Manager window is open onscreen. 
8.	In the IIS Manager window, click Application Pools, and check if BizAPP Pool services is in the “Started” state.

:::NOTE:  The current password of the user has to be added in the BizAPP Pool>>Advanced Settings>>Identity property >>Custom Account>>Set Credentials window. 
 
! Figure 2: IIS Manager: Application Pools

9.	Click Default Website, in the right pane, click Browse *:80 (http). The web browser will be redirected to http://localhost OR
10.	Open Sites, Default Web Sites, go to Action section, and click Basic Settings.  
11.	In the Edit Site window, check if Physical path is pointing to BizAPP\Web-client. 

:::NOTE:  You can check if localhost is set, click Connect as and Test Settings. 
 
! Figure 3: Setting the Default Web-client

12.	Click Ok and close the window.

### Required Installations

You can clone the repository and install the build using Git Commands OR the desktop interface of BitBucket (Sourcetree) and GitHUB (GitHub Desktop).

a)	Install Git Bash: Use the Git 2.21.0 version and above
b)	Install SourceTree 3.3.8 or the latest version (Not a mandatory requirement) 

### Install Git Bash 

Git Bash is a source control management system for Windows. It allows users to type Git commands that make source code management easier through versioning and commit history. Git Bash is not a GUI software; it is a command-line prompt which provides a BASH emulation to run Git from the command line. You can use Git Bash to write and run commands on the terminal and update the build.

1.	Download the latest Git for Windows Installers from the link – https://gitforwindows.org/ 
2.	Double-click on the .exe file to open and execute Git Bash. A Git Setup Wizard appears on screen.
3.	To install Git in the folder, click Browse, select the destination location, and click Next.

! Figure 4: Git Setup-Select Destination
4.	In the Select Components window, leave all the default options checked. Check other additional components you want to install and click Next.
 
!Figure 5: Git Setup- Select Components
5.	In the Choosing the default editor used by Git, select the Use NotePad++ as Git’s default editor from the drop-down and click Next. 
 
!Figure 6: Git Setup-Default Editor
6.	In the Adjusting your PATH environment, keep the default Use Git from the command line and also from 3rd-party software as shown below. This option will allow you to use Git from either Git Bash or the Windows Command Prompt. Click Next.
 
!Figure 7: Git Setup-Path Environment
7.	In Choosing HTTPS transport backend, leave the default “Use the OpenSSL library” selected and click Next. 
 
!Figure 8: Git Setup: Configure Https Transport backend
8.	In the Configuring the line ending conversions window, Select Checkout Windows-style, commit Unix-style line endings unless you need other line endings for your work.
 
Figure 9: Git Setup: Configure Line ending conversions
9.	In the Configuring the terminal emulator to use with Git Bash window, Select Use MinTTY (the default terminal of MSYS2).
 
!Figure 10: Git Setup: Configure emulator to use Git Bash
10.	On the Configuring extra options window leave the default options checked unless you need the symbolic links, Click Install button.
 
!Figure 11: Git set up-Configure Extra Options
11.	Once completed, you can check the option to Launch Git Bash if you want to open a Bash command line or, if you selected the Windows command line, run Git from the Windows command line.
 
!Figure 12: Git Setup Install
.  
!Figure 13: Git Setup - Complete Wizard
12.	Click Finish to complete the installation. 
 
!Figure 14: Git - Command Interface
13.	Run the git commands to initialize, configure Git username and Email.  

The Git cheat sheet with basic commands is available in the link : https://education.github.com/git-cheat-sheet-education.pdf. 

### Install Sourcetree 

Sourcetree is a free Git GUI used for visual representation of repositories. It provides you with an interface that gives you the same capabilities you have with Git without the need to use the command line. It simplifies how you interact with your Git repositories so you can focus on coding.
1.    Open the link -  https://www.sourcetreeapp.com/. The Home page of Sourcetree is open on screen.
2.    Click the Download Free button, or Click Download for Windows. The software gets downloaded to your system.
3.    Double-click or Run the .exe file. This begins the installation process, click Install.
4.    In the Agreement of Terms and Conditions form, select the checkbox “I agree to the Atlassian Customer Agreement” and click Continue.
5.    You need an Atlassian account to use Sourcetree. When you get to this screen, click Use an Existing account, enter your account ID to open Sourcetree.

:::NOTE: If you are creating a new account, select Sign-in and create a new account in BitBucket. You can sign in using your Google or Windows account.

6.    A one-time registration is required to start using your Bitbucket account and connect to your accounts in GitHub, GitBash. In the Registration window, select Bitbucket.
 
!Figure 15: BitBucket - Registration

:::NOTE:  If Sourcetree is already installed, select the Notification flag and update it to the latest available version.
7.    A Confirm access to your account window appears on screen. Select the Read and modify your repositories and their pull requests to enable the Read/Write access.
 
!Figure 16: Grant Access
8.    Select the Grant Access button. This completes the Registration Process.
 
!Figure 17: Complete Registration
9.    Click Next to proceed to the next step, Installing the Tools.
 
!Figure 18: Download Version Control
10.  Version control systems gets downloaded to your system.
 
!Figure 19: Extraction of Mercurial
11.  The installation of the tool will be done after the Extraction of Mercurial files is completed.
 
!Figure 20: Complete Installation
12.  On completing the installation, click Next to view the Preferences window.
13.  Select the Set the global author details for Git and Mercurial. A “Load SSH key?” prompt window appears on screen.  
 
! Figure 21: Add Preferences

14.  You may see the Load SSH Key? dialog after installation. Click No, if you don't have one and want to use Sourcetree to create one.
 
! Figure 22: Load SSH






