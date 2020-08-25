## Remote Build Repository
The release build BizAPP–Public is a public repository in Github which can be accessed by any user using the given URL. This remote repository does not require user to sign-in and create any authentication. It can be cloned directly to create a local copy in your system. 

__To access and clone the release build-BizAPP-Public__
1.	In any browser, open the link: <span style="color:blue">[Download BizAPP-Public]( https://github.com/apppoint-release/BizAPP-Public)</span>  
2.	All the source files of **BizAPP-Public** will be listed in GitHub. 
 
 ![githubbizappsource](/images/bizapppublic/githubbizappsource.png) 

3.	Navigate to **Code**, click on the drop-down arrow to view the **Clone with HTTPS** window. 
4.	Copy the **HTTPs URL** of the repository.
5.	Open **Sourcetree**(that is installed on your system) and click **File >> Clone/New**.
6.	Select **Clone** tab and paste the **HTTPs URL** into the **Source** text box. 
  
![clonesourcetree](/images/bizapppublic/clonesourcetree.png)

7.	Add **Destination path** of your local repository. For instance, E:\GIT\BizAPP-Public
8.	Click **Clone**. The cloning will be in progress state. Wait for a few minutes until the process is completed. 
9.	Click **Show Full Output** to view if any errors are encountered. 
 
 ![cloneinprogress](/images/bizapppublic/cloneinprogress.png)

10.	If cloning is successfully completed, then all the files from the remote repository will be copied to your local repository.  

![localreposourcetree](/images/bizapppublic/localreposourcetree.png)

11.	Open the **local folder** to check if all the files are listed under it.

## Creating an Empty Repository

The modeler repositories are stored in Bitbucket server on cloud. The owner of the repository or the Administrator has to provide user access to the respective modeler repository.
User has to create an authentication in BitBucket by signing in with his personal google account or windows account. When user starts the modeler, the respective modeler repository will get created or downloaded into the folder on his system. 
__To sign-in to bitbucket (using your personal account)__:

1. Open <span style="color:blue">[Bitbucket]( https://id.atlassian.com/login)</span> and click **Login**.

![bitbucketlogin](/images/bizapppublic/bitbucketlogin.png)

2. Enter your **Email ID** and **Password** and click **Login**. The **Bitbucket Dashboard** is open on screen.

![bitbucketdashboard](/images/bizapppublic/bitbucketdashboard.png)

3. Click **Create Repository**. A **Create a new repository** form will appear on screen.

![createnewrepo](/images/bizapppublic/createnewrepo.png)

4.	Enter a name to the solution repository in the **Repository name** text box. For instance, in Recruit Management application, the recruit_m_<your_name> can be created. 
5.	In the **Access Level** text box, select the **This is a private repository** checkbox to set the repository as **Private**. 
6.	If repository has an open source code, then it can be set as **Public**. 
7.	Since you are creating an empty repository, you can disable the generation of **README** file for the repository. In the **Include a README?** combo box, select the option **No** from the drop-down. 
8.	Forking need not be configured if your changes are a part of the main project repository. To create branch starting with either the head/trunk or an existing branch, select **No Forks** from the drop-down of the **Forking** combo box. 
9.	Click **Create Repository**. A new repository (git repository) is created under your Bitbucket account. The path is set as git.bitbucket.org/<User_name>/<Name of the Repository>.git
 
![createemptyrepo](/images/bizapppublic/createemptyrepo.png)
 
This is an empty solution repository that is created in bitbucket. 

### Solution Configuration File
The owner of the Solution Configuration repository or the Administrator will provide access to the respective solution configuration file. The path of this file has to be configured to a config file within the build repository. For more details, refer to: <span style="color:blue">[Configuring Files](]</span>
