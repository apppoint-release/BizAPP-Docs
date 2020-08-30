To install BizAPP build on your system

1. On your Desktop, click **Start** and open **Windows Powershell** and **Run as Administrator**. 
2. or type **Powershell** at the Command Prompt. The PS C:\Windows\system32\ appears at the prompt.
3. To verify the execution policy setting, run the command

```
Get-Execution Policy 
```
4. If execution is restricted, then change the execution policy to allow execution of scripts.

```
Set-executionpolicy remotesigned
```
or
```
Set-executionpolicy unrestricted
```

5.	From the Command prompt, point to your local repository folder, for instance, E:/Localrepo/DeveRelease
6.	Run the build installation command  

```
.\Install.ps1  
```
![install](/images/installbizapp/install_ps1.png)

7.	Add storage path to store temporary files, for e.g., E:\Temp
8.	To set start-up services and IIS, run as domain User Account and then enter the inputs upon prompt. 
9.	System prompts user **Do you want to set up services to your user account (Y/N)?**. Type **Y** if you want to your domain account, else **N**.

![install_services](/images/installbizapp/install_services.png)

10.	Enter your **UserName, EmailID** and **Password** (System Password) for authentication. 
11.	System prompts user **Do you want to set up services to your user account (Y/N)?**. Type **Y** if you want to your domain account, else **N**.

![install_redis](/images/installbizapp/install_redis.png)

12.	System prompts: **Do you want to NGen assemblies? (Y/N)?**. Type **Y** if you are doing server deployments, else **N**.  This will take a few minutes to complete.

>NOTE : It is not mandatory for user to NGen assemblies. 

![install_ngen](/images/installbizapp/install_ngen.png)

After BizAPP is installed, configurations are done for BizAPP services to work.

## BizAPP Services

When modeler is installed for the first-time, the services will be automatically installed. If system has builds (older builds) then those services could be currently running. The old   
of BizAPP services of the previous build need to be removed. 

### Delete Services - Previous Build

The services of previous build (that is un-installed) need to be removed.

1.	Open the **Windows Command prompt >> Run as Administrator**.
2.	In C:\Windows\System32>sc delete <name of the old service> for e.g., sc delete BizAPP-Dev Hosting Agent 
3.	Press **Enter**. Then, sc delete service Success appears on screen.
4.  Replace {name} with "Product" for public customer release and "Dev" for dev release builds before running the below commands.

```
sc delete BizAPP-{name}-RegistryService
sc delete BizAPP-{name}-Bootstrap
sc delete BizAPP-{name}-HostingAgent
sc delete BizAPP-{name}-LicenseService
sc delete bizapp-{name}-backplane-1
sc delete bizapp-{name}-backplane-2
sc delete BizAPP-{name}-SessionStateManager
sc delete BizAPP-{name}-AutoUpdater
```

## Configure Local Repository files

Check the configurations required for files within the folders of your system.

**a. Configure SolutionConfigs/<Config_RecruitMgnt.xml>**

Administrator should provide user DB connection string that has to be added to it. 

1.	Open the local **SolutionConfigs** repository, if you have access to it. For Instance, E:\LocalSolutionConfigs
2.	Open the dev configs/<respective solution config file>, for instance, dev configs/Config_RecruitMgmt.xml in Notepad++.  
3.	Check if **Enterprise Name** and the **Database name** in the given connection string under **<respective_Solution_name>_UserDatabase>** is configured for you.
5.	Copy the path of the solution configuration file. For instance,E:\LocalSolutionConfigs\solutionconfigs\dev configs

**b. Configure - /DevRelease/BizAPP/BizAPP.Runtime.Registry.Host.exe.config**

To set the path of the license server and the service config file:

1.	In the local Build repository, point to BizAPP Folder, for instance, E:\Localrepo\devrelease\BizAPP
2.	Open the file **BizAPP.Runtime.Registry.Host.exe.config** in NotePad++
3.	In the appsettings sections, add path to the license as 

```
<add key="licenseserver" value="13.71.71.190:13333" />
```

4. The service config file has to point to where your config file is stored as 

```
<add key="serviceconfigfile" value="E:\LocalSolutionConfigs\solutionconfigs\Config_Recruit.xml" />
```

5. Enable the trace logs and file logs to **true** to view and generate the error report.

```
<rules>
	<logger name="BizAPP*" minlevel="Debug" writeTo="tracelog" enabled="True" />
	<logger name="BizAPP*" minlevel="Debug" writeTo="filelog" enabled="false" />
</rules>
```

**c. Create a shortcut - /Devrelease/BizAPP/BizAPPModeler.exe**

1.  Create a shortcut for BizAPP and start BizAPP from the desktop, if a shortcut is not created or pinned already to the taskbar.
2.	In the local build repository,  and point to BizAPP folder, For instance, E:\Localrepo\devrelease\BizAPP
3.	Right-click on **BizAPP.Modeler.exe** file.
4.	Select **Send To Desktop** and click **Create Shortcut** or Click **Pin to Taskbar**. 

Now, all the BizAPP configurations are completed. The BizAPP icon will appear on your desktop or will appear as pinned to your taskbar.

## Updating BizAPP Build

You can update the build by pulling the latest changes from the master repository of the build. Build can updated by using

* Git Commands 
* Sourcetree 
* GitHub Desktop

Before updating the new build, ensure all BizAPP services are in stopped state.

1. Open **services.msc** from windows run prompt.
2. Navigate to BizAPP-{name}-Bootstrap.
3. To stop services using command line, open **Command Prompt** from windows run prompt. Use the below command.

```
sc stop BizAPP-{name}-Bootstrap
```
>Replace {name} with "Product" for public customer release and "Dev" for dev release builds before running the below commands.

### Using Git Commands

If you have git bash installed, then you can update the build from the command prompt.

To pull new changes from master
 
1. Open the **Command prompt >> Run as Administrator**.
2. Open the folder (where your local repository is stored). For Instance, E:/LocalRepo/DeveRelease.
3. To view changes for the "master" branch from the "origin" of the remote repository before deciding to merge them into your repo. 
```
Git fetch origin
```
4. To fetch all the changes from the remote’s master branch and merge it to your local repository, use
```
Git pull origin master
```
5. If you encounter any errors such as files will be overwritten by the merge and aborted, then use the below command.
```
Git reset --hard origin/master
```

### Using Sourcetree

You can update the build from SourceTree. 

1. In **SourceTree** window, open the repository tab that points to the build repository.
2. On the menu bar, click **Pull** and Click **OK**. It will pull all the remote changes to your local repository. All the new changes will be available in the local repository.

### Starting services

After successful build update, services need to be restarted. It can be done using
* Services User Interface (services.msc)
* Command Prompt

1. Open **services.msc** from windows run prompt.
2. Navigate to BizAPP-{name}-Bootstrap and right click on Start.
3. To start services using command line, open **Command Prompt** from windows run prompt and run the below command.

```
sc start BizAPP-{name}-Bootstrap
```
>Replace {name} with "Product" for public customer release and "Dev" for dev release builds before running the below commands.