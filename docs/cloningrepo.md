The repository in BitBucket is a remote repository which is configured as private. Both Public and Private repositories can be cloned to create a local copy on your system. 
Cloning a repository syncs it to your local machine. Both the locations have to be synchronized to add, edit files and then push and pull updates. 
Public repositories can be cloned using HTTPS where no authentication mechanism is required. 

From Source tree, you can view all the remote repositories of BitBucket that are set as “Public” or “Private” and for which Read/Write access is given. Cloning can be done using either SourceTree OR BitBucket/GitHub

## Cloning Build - BitBucket
If your account in  BitBucket has been authenticated (or given access), then the remote repositories will be listed in Sourcetree.

To clone remote repositories from BitBucket or from Sourcetree:
1.	Open the repository in BitBucket (using the link provided) and click **Clone**. 
2.	In the **Clone this repository** window, select **HTTPS** and click **Clone in Sourcetree**.
 
 ![cloneinbitbucket](/images/clonerepo/clonebitbucket.png)

3.	Open Sourcetree.  Select **File >> Clone**, and Click Remote.  The Sourcetree opens in a new window. 

### Cloning from Sourcetree
The Remote tab shows list of all the remote repositories available for the current user. 
1.	Select the **Repository**, for instance DevRelease and click **Clone**. 

![cloneinsourcetree](/images/clonerepo/clonesourcetree.png)
 
2.	Select the repository, for instance, the DevRelease build from the list and click **Clone**. The **Clone** tab (with clone repository path) is available.
3.	If cloning is done from Bitbucket, copy-paste the clone path into the text box specified to add the Source path.
4.	Add **Destination path** of your local repository, for instance F:\LocaRepo\DeveRelease and click Clone.
5.	If you are unable to clone, then scroll-down to the Taskbar, click and open PuTTYGen Authentication Agent and add the PrivateKey.
6.	In Sourcetree, go to **Tools>>Launch SSH Agent** to launch SSH key for authentication.
 
![clonerepolocal](/images/clonerepo/clonerepolocally.png)

7.	Cloning will be in progress state, wait for a few minutes until the process is completed. 
8.	Click **Show Full Output** to view if any errors are encountered. 
  
![cloneinprogress](/images/clonerepo/cloneinprogress.png)

9.	If cloning is successfully completed then all the files from the remote repository will be copied to your local repository. 
10.	You can open the folder and check if all the BizAPP related files are available or listed.
11.	A prompt window appears to confirm if you want to install Git LFS. If you are cloning a BitBucket Repository, click **No**.

Now, BizAPP build is cloned locally on to your system. You can proceed further to [Installing BizAPP](InstallBizAPP.md)on your system.

## Cloning Solution Configuration Repository
If your account has access to view the repository,then you can clone it to a local folder on your system.

To access and clone the repository:
1.	In your system, create a directory, for in LocalSolutionConfigs in C or E drive.
2.	Open the solution configuration repo using the link:
https://bitbucket.org/apppoint/solutionconfigs/src/master/
3.	Clone the solution repository to the local folder on your system, either from BitBucket or Sourcetree. 
 
 ![clonesolutionconfig](/images/clonerepo/clonesolutionconfigs.png)

4.	Open **Sourcetree** that is installed on your system, open **File Clone/New**.
5.	In the **Clone** tab, paste the https path of the source files to be cloned. For instance, the path mentioned above.
6.	In the **Destination path**, enter the path of the local directory where all the solution configurations will be cloned.
7.	Click **Clone**. If cloning is successfully completed, then all the files from the remote repository will be copied to your local repository. 

You can open the folder and check if all the BizAPP related files are available and listed.

