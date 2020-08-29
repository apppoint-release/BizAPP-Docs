The release build, BizAPP-Public is a repository in GitHub that does not require user to sign-up and create an account for authentication.  

To access the repository, open the [link](https://github.com/apppoint-release/BizAPP-Public) in any browser. All the source files of BizAPP Dev-Public will be listed in the page. 

## Cloning the Public Repository
You can clone the remote public repository from GitHub Desktop, using HTTPS Url to create a local copy of the build files to your system.

1. To clone the build repository, navigate to the [link](https://github.com/apppoint-release/BizAPP-Public) in any browser and click on *Code >> Copy HTTPS Clone Url*.

![githubbizappsource](/images/bizapppublic/githubbizappsource.png)

2. In **GitHub Desktop**, click **Clone a repository from the internet...**.
3. This opens **Clone a repository** popup, navigate to **URL** tab page.
4. Paste the url copied from the browser in the step 5.
5. Change the **Local path** to any folder in your local machine. Click **Clone** button. New folder **BizAPP-Public** will be created.

![githubconfigure](/images/github/clonerepo.png)

6. It will show the clone status as shown in the image below.

![githubconfigure](/images/github/status.png)

7. If cloning is successfully completed, then all the files from the remote repository will be copied to your local repository. You can open the folder and check if BizAPP files are listed.
8. Refer to [Installing BizAPP](InstallBizAPP.md) for further install instructions.
 
>Note: If there is any new updates to the build, it can be pulled.

### Solution Configuration File

The solution config file is Config.<solution_name>.xml file. Depending on the application you will be creating or working on, the System Administrator will provide access to the config file. 
The solution configuration file path has to be added in to the file /BizAPP/BizAPP.Runtime.Registry.Host.exe.config of your local repository.

For more details, refer to the link, [Configuring Files in the Repository](https://docs.apppoint.com/Modeler/index.html#!configuringfilesintherepositorylocal.htm)