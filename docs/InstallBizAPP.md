# Installing BizAPP

To install Bizapp build (Devrelease) on your system:

1. On your Desktop, click **Start** and open **Windows Powershell** and **Run as Administrator**. 
2. Type **Powershell** at the Command Prompt. The PS C:\Windows\system32\ appears at the prompt.
3. To verify the execution policy setting, run the command -

```
Get-Execution Policy 
```
4. If execution is restricted, then you have to set the execution policy.

```
Set-executionpolicy remotesigned
```
5.	From the Command prompt, point to your local repository folder, Say E:/Localrepo/DeveRelease
6.	Run the build installation command:  

```
.\Install.ps1  
```

![install](/images/install_ps1.png)

7.	Add storage path to store temporary files, for e.g., E:\Temp
8.	To set start-up services and IIS, run as domain User Account and then enter the inputs upon prompt. 
9.	System prompts user **Do you want to set up services to your user account (Y/N)?**  Type **Y**.

![install_services](/images/install_services.pn)

10.	Enter your **UserName, EmailID** and **Password**(System Password) for authentication. 
11.	System prompts user - **Do you require local redis services (Y/N)**. Type **Y**.

![install_redis](/images/install_redis.png)

12.	System prompts - **If user wants Ngen assemblies? (Y/N)?**. Type **Y**.  All the New-Gen services will be installed.

:::NOTE
	It is not mandatory for user to install the Ngen assemblies. 
:::

![install_ngen](/images/install_ngen.png)

Now, BizAPP build (Devrelease)is installed.The Modeler will be available after all the BizAPP services on your system are started.

## Starting BizAPP Services

When the modeler is installed for the first-time, the services will be automatically created during build installation.If services of the previous build 
are currently running then those services have to be manually deleted. 

### Deleting Services of Previous build

The services of previous build (that is un-installed) has to be removed.

1.	Open the **Windows Command prompt>> Run as Administrator**.
2.	In C:\Windows\System32>sc delete <name of the old service> for e.g., sc delete BizAPP-Dev Hosting Agent 
3.	Press **Enter**. Then, [sc] DeleteService Success appears on screen.

### Starting Services of New build

To create new services for the current build installed:

1.	Open the **Command Prompt>>Run as Administrator**.  
2.	Point to the **DevRelease build**, for instance E:/Localrepo/devrelease> 
3.	Type the following command within the devrelease folder.

```
Powershell –f <path of the devrelease folder>\Install.ps1
```
4. For instance: E:\Localrepo\devrelease>powershell –f   E:\Localrepo\devrelease\Install.ps1
5. System prompts **Do you want to setup services/IIS to use another user account? (Y/N)**:  Type **Y**.
6. Enter **Username**: <enter your company/personal account>
7. Enter **Password**: <type in windows login password>
8. The services for **BizAPP–Dev–Registry Service** will be created. Then, the IIS AppPool and site is created.
9. System prompts **Do you want Ngen assemblies? (Y/N)**:  Type **Y**. All the Ngen services will get installed. 
10. Open the Command prompt and enter **Services.msc**.
11. Check, if the following BizAPP services are available. 

```
BizAPP Registry 
BizAPP BootStrap Services
BizApp-Dev-Hosting Agent
BizAPP registry
BizApp-Dev-LicenseService
bizapp-dev-backplane-1
bizapp-dev-backplane-2 
```
12.	Right-click on each of service, and Select **Start**. 

## Configuring Files in the Repository (Local)

Below are the configurations required for files within the folders of your system.

**A. Configuring the Config_RecruitMgnt.xml**

You have to configure the respective solution configuration file to point to the local build repository. Administrator will provide the current user DB connection string that has to be added to it. 

1.	In your system, open the **SolutionConfigs** repo that is cloned locally. For Instance, E:\LocalSolutionConfigs
2.	Open the folder Dev Config to view all the list of all the solution configuration files.  
3.	Select and open the respective solution config file, for instance, Config_RecruitMgmt.xml in Notepad++ 
4.	Check if **Enterprise Name** and the **Database name** in the given connection string under **<Solution_name_UserDatabase>** is configured for you.
5.	Copy the path of the solution configuration file. For instance:  E:\LocalSolutionConfigs\solutionconfigs\dev configs

**B. Configurations in File BizAPP.Runtime.Registry.Host.exe.config**

To set the path of the license server and the service config file:

1.	In the local Build repository, point to BizAPP Folder, for instance, E:\Localrepo\devrelease\BizAPP
2.	Open the file **BizAPP.Runtime.Registry.Host.exe.config** in NotePad++


3.	In the appsettings sections, add path to the license as 
***
   <add key="licenseserver" value="13.71.71.190:13333" />`

   <add key="licenseserver" value="13.71.71.190:13333" />
***

4. The service config file has to point to where your config file is stored as 

***
 <add key="serviceconfigfile" value="E:\LocalSolutionConfigs\solutionconfigs\Config_Recruit.xml" />
***
5. Enable the trace logs and file logs to “true” to view and generate the error report.

***
<rules>
<logger name="BizAPP*" minlevel="Debug" writeTo="tracelog" enabled="True" />
<logger name="BizAPP*" minlevel="Debug" writeTo="filelog" enabled="True" />
</rules>
***

Now, all the BizAPP configurations are completed. 

## BizAPP – Shortcut  
 
You can easily open and start BizAPP from the desktop, if a shortcut is created or pinned to the taskbar.

1.	Open the local build repository and point to BizAPP folder, For instance, E:\Localrepo\devrelease\BizAPP
2.	Right-click on **BizAPPModeler.exe** file.
3.	Select **Send To Desktop** and click **Create Shortcut** or Click **Pin to Taskbar**. 

The BizAPP icon will appear on your desktop or will appear as pinned to your taskbar.

## Updating BizAPP Build

You can update the build by pulling the latest changes from the master repository of the modeler.

a.	Using GIT Commands OR 
b.	Using SourceTree.

Before updating the new build, you have to stop all the BizAPP services.

1.	On the **Command prompt**, run **services.msc**
2.	In the **Application Configuration window**, right-click on the **BizAPP parameters** and stop all the services, 
```
BizApp-Dev-Hosting Agent
BizApp-Dev-LicenseService
BizApp-Dev-Registry
bizapp-dev-backplane-1
bizapp-dev-backplane-2
```

### Using Git Commands  

If you have git bash installed, or your repo is git initialized before LFS is installed, then you can update the build from the command prompt.

To get new changes from Master:
 
1. Open the **Command prompt>>Run as Administrator.**
2. Open the folder (where your local repository is stored). For Instance, E:/LocalRepo/DeveRelease
3. At the Command Prompt run the following commands. 
```
Git lfs install
git lfs pull 
```
4. If you see any errors related to smudged files, then run the following commands in the repo.
```
git lfs install --skip-smudge 
git lfs pull 
git lfs install --force
```
The above commands will re-initialize smudged files from the remote repository. 

5. To view changes for the "master" branch from the "origin" of the remote repo before deciding to merge them into your repo. 
```
Git fetch origin
```
6. To fetch all the changes from the remote’s master branch and merge it to your local repo, use:
```
Git reset --hard origin/master Or
Git pull origin master
```

:::NOTE

 For BizAPP files that are configured locally you may get the following error.  
:::

### Using Sourcetree

You can update the build from SourceTree. 

1.	In the **SourceTree** window, open the repository tab that points to the build repository.
2.	On the menu bar, click **Pull** and Click **OK**. It will pull all the remote changes to your local repository. All the new changes will be available in the local repository.   
4.	Open the **BizAPP folder** from your local repository. 
5.	Configure **BizAPP.Runtime.Registry.Host.exe.config**& **Config.config file**. Refer to: Configuring Files in Local Host for more details.
6.	Re-start all the**BizAPP services** from the **Task Manager** OR On the **Command Prompt**, type **Services.msc**.
7.	Scroll-down to **BizAPP services**, right-click on a service and click **Start**. 

Now, all the new changes will be available in your local repository as un-committed changes.

