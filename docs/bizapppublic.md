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

### Creating an Empty Repository

The modeler repositories are stored in Bitbucket server on cloud. This repository may be public or private. The owner of the repository or the Administrator has to provide access to (read/write) the respective solution repository. User has to create an authentication in BitBucket by signing in with his personal google account or windows account. When user starts the modeler, the solution repository will get downloaded or cloned in to the folder on his system. 

To sign-in to bitbucket (using your personal account):
1.	Open the [link] (https://id.atlassian.com/login), click **Login**.
![bitbucketlogin](/images/bizapppublic/bitbucketlogin.png)
2.	Enter your Email ID and Password and click **Login**. The **Bitbucket Dashboard** is open on screen.
![createrepository](/images/bizapppublic/createrepository.png) 
3.	Click **Create Repository**. A Create a new repository form will appear on screen
![createnewrepo](/images/bizapppublic/createnewrepo.png) 
4.	Enter a name to the solution repository in the Repository name text box. For instance, in Recruit Management solution, the recruit_m_<your_name> can be created. 
5.	In the **Access level** text box, select **This is a private repository** checkbox to set the repository as **Private**. 
6.	If repository has an open source code, then it can be set as **Public**. 
7.	Since you are creating an empty repository, you can disable the generation of README file for the repository. In the **Include a README?** combo box, select the option **No** from the drop-down. 
8.	Forking need not be configured if your changes are a part of the main project repository. To create branch starting with either the head/trunk or an existing branch, select No Forks from the drop-down of the Forking combo box. 

>NOTE: If you want to work on a completely separate copy of the project, you can consider creating a 'fork'. Forking is a way for you to clone a repository at a specific point, and to modify it from there. Refer to the link : https://confluence.atlassian.com/bitbucket/forking-a-repository-221449527.html
9.	Click Create Repository. A new repository (git repository) is created under your Bitbucket account. The path is set as git.bitbucket.org/<User_name>/<Name of the Repository>.git
 
This is an empty solution repository that is created in bitbucket. 

### Solution Configuration File

The solution config file is Config.<solution_name>.xml file. Depending on the application you will be creating or working on, the System Administrator will provide access to the config file. 
The solution configuration file path has to be added in to the file /BizAPP/BizAPP.Runtime.Registry.Host.exe.config of your local repository.

For more details, refer to the link, [Configuring Files in the Repository](https://docs.apppoint.com/Modeler/index.html#!configuringfilesintherepositorylocal.htm)