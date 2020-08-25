The repository in BitBucket or GitHub are remote repositories (either public or private) that can be cloned to create a local copy on your system. 
Cloning repositories can be done:
 + Using SSH or
 + Using Https (where no authentication of user is required)
 
Cloning can be done using either 
+ SourceTree OR 
+ BitBucket/GitHub

### Cloning from BitBucket/GitHub

If your account in GitHub or BitBucket has been authenticated (or given access), then the remote repositories will be listed in Sourcetree. 
__To clone remote repositories from BitBucket or from Sourcetree__:
1.	Click on the [Release_Build] Open the repository in BitBucket (using the link provided) and click **Clone**. 
2.	In the **Clone this repository** window, select **HTTPS** and copy the url OR click **Clone in Sourcetree**. 
 
 ![cloneinbitbucket](/images/clonerepo/clonebitbucket.png)

### Cloning from Sourcetree
In Sourcetree, user can view remote repositories of BitBucket/GitHub that are set as **Public** or **Private** and for which user is given access. 


+ **SSH Authentication**:
1. On the **Taskbar**, click and open **PuTTYGen Authentication Agent**.
2. Click **Add Key**, select a **Privatekey** from the **.ssh** folder to add the **PrivateKey**. 
3. In **Sourcetree**, go to **Tools >> Launch SSH Agent** to launch SSH key for authentication.

+ To clone the repository:
1. Select **File > >Clone/New**, and Click **Remote**. **Sourcetree** opens in a new window. 
2. The **Remote** tab lists all the remote repositories available for the current user. Select a **Repository**, for instance DevRelease and click **Clone**. 

![cloneinsourcetree](/images/clonerepo/clonesourcetree.png)
 
3.  The **Clone** tab (with clone repository path) is available. OR If cloning is done from Bitbucket, copy-paste the clone path into the text box specified to add the **Source path**. 
4.	Add **Destination** path of your local repository, for instance E:\LocaRepo\DeveRelease and click **Clone**. Cloning will be allowed only if it is git repository.

![clonerepolocal](/images/clonerepo/clonerepolocally.png)

5.	Cloning will be in progress state, wait for a few minutes until the process is completed. 
6.	Click **Show Full Output** to view if any errors are encountered. 
  
![cloneinprogress](/images/clonerepo/cloneinprogress.png)

7. If cloning is successfully completed, then all the files from the remote repository will be copied to your local repository. 
8. A prompt window appears to confirm if you want to **install Git LFS**. If you are cloning a **BitBucket Repository**, click **No**.

The Release build of BizAPP-Internal is cloned locally. Open the folder to check if all the BizAPP related files are available or listed. 

## Cloning Solution Configuration Repository

All the solution configuration files are stored in this repository. To get access to the respective solution config file, user will clone the repository to his system. 

__To access and clone the solution configuration repository__:

1. In your system, create a directory, say LocalSolutionConfigs in C or E drive.
2. Open the **solution configuration repo**, click <span style="color:blue">[[solution Configurations](https://bitbucket.org/apppoint/solutionconfigs/src/master/)</span> 
3. Clone the solution repository to the local folder on your system, either from BitBucket or Sourcetree. 
 
 ![clonesolutionconfig](/images/clonerepo/clonesolutionconfigs.png)

4. Open **Sourcetree** that is installed on your system, Click **File Clone/New**.
5. In the **Clone** tab, paste the **https** path of the source files to be cloned. 
6. In the **Destination** path, enter the path of the local directory where all the solution configurations will be cloned.
7. Click **Clone**. If cloning is successfully completed then all the files from the remote repository will be copied to your local repository. 
8. Open the local solution configuration repository and check if all the configuration files are listed under the **Dev Config** folder.