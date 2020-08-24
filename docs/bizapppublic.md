The release build, BizAPP-Public is a repository in GitHub that does not require user to sign-up and create an account for authentication.  

To access the repository, open the link: https://github.com/apppoint-release/BizAPP-Public in any browser. All the source files of BizAPP Dev-Public will be listed in GitHub. 

![githubbizappsource](/images/bizapppublic/githubbizappsource.png)
 
## Cloning the Public Repository
You can clone the remote public repository from Sourcetree, using Https to create a local copy of the source files into your system.

1.	In the **BizAPP Dev-Public repository**, navigate to **Code**.
2.  Click on the drop-down arrow to view the **Clone with HTTPS window**.
3.	Copy the **HTTPs URL of the repository**.
4.	Open **Sourcetree**(that is installed on your system). Click **File>>Clone/New**.
5.	Select **Clone** tab and paste the HTTPs URL in to the **Source** text box. 

![clonesourcetree](/images/bizapppublic/clonesourcetree.png)

6.	Add **Destination path** of your local repository. For instance, E:\GIT\BizAPP-Public
7.	Click **Clone**. The cloning will be in progress state. Wait for a few minutes until the process is completed. 
8.	Click **Show Full Output** to view if any errors are encountered. 

![cloneinprogress](/images/bizapppublic/cloneinprogress.png)
 
9.	If cloning is successfully completed, then all the files from the remote repository will be copied to your local repository. You can open the folder and check if BizAPP files are listed.
 
![localreposourcetree](/images/bizapppublic/localreposourcetree.png)

Figure 4: Local repository in Sourcetree

>Note: If there are any new updates in the build then this will be indicated on the **Pull**. Please update the build and then clone the repository. For more details, refer to Updating the Build.

### Solution Configuration File

The solution config file is Config.<solution_name>.xml file. Depending on the application you will be creating or working on, the System Administrator will provide access to the config file. 
The solution configuration file path has to be added in to the file /BizAPP/BizAPP.Runtime.Registry.Host.exe.config of your local repository.

For more details, refer to the link, [Configuring Files in the Repository](https://docs.apppoint.com/Modeler/index.html#!configuringfilesintherepositorylocal.htm)


