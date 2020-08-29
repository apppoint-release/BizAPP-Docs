## Install Sourcetree (Optional)

Sourcetree is a free Git GUI used for visual representation of repositories.It provides you with an interface that gives you the same capabilities you have with Git without the need to use the command line. It simplifies how you interact with your Git repositories so you can focus on coding.

1. Open the [link](https://www.sourcetreeapp.com/). The **Home page** of Sourcetree is open on screen.
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

In this section, you will learn to setup BizAPP and its environment for internal users and developers.


## Accessing Bitbucket Repositories
The BizAPP Dev build repository **DevRelease** is available in Bitbucket [link](https://bitbucket.org/apppoint/devrelease/src/master/). This document assumes that you have necessary permissions to access the repository.

>**Note:** On your avatar, check if you have permissions to (Read access) to the BizAPP Build repository. This is required to pull latest updates from the build. 
Otherwise, request administrator for access.

### SSH Authentication

SSH authentication is required for repositories that are private. When you set up SSH, you create a key pair that contains a private key (saved to your local computer) and a public key (uploaded to Bitbucket). Bitbucket uses the key pair to authenticate anything the associated account can access.  To access repositories in BitBucket that are Private, the following settings are required.
a)	The owner of the repository has to provide a Read, Write access. 
b)	An SSH authentication is required for your BitBucket account.
NOTE:  For more details, refer -->https://confluence.atlassian.com/bitbucket/set-up-an-ssh-key-728138079.html
You can generate public and private SSH keys for authentication
1.	Using SourceTree OR
2.	Using Git in Windows.

#### Generating SSH - Using SourceTree 
The SSH key authentication in Bitbucket is done using the puttykey generator. PuTTYgen is used to generate public or private key pair for SSH. It can create various public-key cryptosystems RSA, DSA, ECDSA and EdDSA keys and focuses primarily on secure data transmission and digital signatures.
When you create an SSH key with Sourcetree, you can save the public and private key wherever you want locally. You can save them under SSH directory, and refer to your SSH keys whenever you need them.
To generate SSH key using SourceTree.
1. Download **PuTTYGen for windows** from the link: https://www.puttygen.com/ 
2. Install **PuTTYgen** on your system.
3. Open **SourceTree to view your local repository.
4. Go to **Tools >>Create or Import SSH Keys** to open the **PuTTY Key Generator** window.
 
Figure 1: PuTTY Key Generator
5. From the **Key** menu, select **SSH-1 (RSA)** and click **Generate**.
6. As the SSH key generates, hover your mouse over the blank area in the dialog. It may take a minute or two. 
7. When SSH key generation is complete, you see the public key and a few other fields. 
 
Figure 2: SSH Keys Public and Private
7.	Create a folder .ssh under C:\Users\<yourname> and click Save public key and name the file with the .pub file extension, and click **Save**.
8.	Click **Save private key**, copy keyfile to the .ssh directory which is under C:\Users\<yourname>

#### Generating SSH - Using Git in Windows 
If you are unable to generate the keys using SourceTree, then use the alternate method as given below. 
1.	Open **Windows Powershell Admin** on your system and type in the command as below.
> PS C:\Users\you>ssh-keygen
2.	This initiates the process of generating public and private rsa key pair as below. Provide a file name, say id_rsa and press **Enter**. 
 
Figure 3: Prompt-Windows Power-Shell
3.	Generating public/private rsa key pair:
    Enter file in which you want to save the key (c:\Users\you/.ssh/id_rsa):  .ssh
4.	The system prompts you to enter and re-enter a passphrase as mentioned below.
	Enter passphrase (empty for no passphrase):
	Enter same passphrase again:
5.	Now, system prompts for the following information. 
	Your identification has been saved in C:\Users\you/.ssh/id_rsa.
	Your public key has been saved in C:\Users\you/.ssh/id_rsa.pub.
	The key fingerprint is:
	SHA256:fsCqtKCmShvReXHvSoCQ0evVKHUIYBkDY/NJgDrWULQ <you>@apppoint.com
	The key's randomart image is:
	
+---[RSA 2048]----+
|=XO=. .          |
|++B.oo .         |
|.ooEo.+.         |
|o.o+oooo.        |
|.o.+oo  S.       |
|  ... .o..       |
| o. . .....      |
|.ooo o. ..       |
|B.  o  .         |
+----[SHA256]-----+
6.	Now, ssh key has been initialized. It has to be initiated. To initiate the ssh key, enter the following command. 
C:\Users\you>start-ssh-agent
Found ssh-agent at 6776
Failed to find ssh-agent socket
Starting ssh-agent:  done
Identity added: /c/Users/you/.ssh/id_rsa (/c/Users/you/.ssh/id_rsa)
C:\Users\you\.ssh>ssh -T git@bitbucket.org
logged in as <user_name>
You can use git or hg to connect to Bitbucket. Shell access is disabled.

#### Installing your Private key on Pageant
SourceTree comes with an SSH authentication agent called Pageant. Load your private key into Pageant to automatically authenticate so that you don't need to enter your passphrase.
SSH authentication can be done using
1.	Pageant (PuTTY Authentication Agent)
2.	Launch SSH key from SourceTree

NOTE: If SSH key is not authenticated, you will not be able to push or pull changes to or from local to remote repository in to BitBucket.

#### Authenticate SSH Key
You can authenticate SSH using Pegeant PuTTY or using Sourcetree

#### PuTTY Authentication Agent
1.	Double-click the **Pageant (PuTTY Authentication Agent)** icon in your system tray. 
  
Figure 4: PuTTY Gen - Add Key
`
2.	A blank **Pageant (Putty Authentication Agent)** editor is available. 
3.	Navigate to the private key file you saved in C:\Users\<YouName>\.ssh and click copy. 
4.	Paste the **Private.ppk** file in to the **Pageant Key list** editor, click **Add Key** and **Close**. 
 
Figure 5: Adding SSH Key

Now, the SSH Key will be launched for your local repository. 

::: NOTE
Every time you close and open your local repository in Sourcetree that keeps track of your local files, you should authenticate SSH key. 
:::

##### Using SourceTree
Every time a Sourcetree is opened, the SSH key that is already generated has to be launched. Otherwise, when user tries to update (pull from remote) new changes, a pop-up window prompts user to generate SSH keys.  
To launch Sourcetree, on the menu bar, go to Tools and click Launch SSH Key. 
####### Adding Public key to Bitbucket Settings
To add the SSH key to your account in to Bitbucket:
1.	Open your account in Bitbucket.
2.	Choose Bitbucket settings from your avatar in the lower left. The Account Settings page opens.
3.	Click **SSH keys**. If you've already added keys, you'll see them on this page. 
4.	Click **Add key**. Enter a Label for your new key, for example, Default public key. Paste the copied public key into the SSH Key field.
 
Figure 6: Add Key BitBucket
5.	Click **Save**. An Email notification is sends your account to confirm the addition of the key.
6.	Edit an SSH key. After you add a key, you can edit the key’s label but not the key itself. 

If you are using your key for a build system, it is a good idea to confirm the key is working correctly from the service or build server. For example, you can test it by manually cloning the repository using SSH, just as you would normally clone a repository.

#### Dev Release Build
The Dev release build is tested and update frequently for bug fixes, new features and improvements. The build has versions to identify the new build updates. Release notes are documented for every build update to determine the bug fixes and improvements.
The latest updates in source files of BizAPP Dev are available in the DevRelease repository in Bitbucket   
https://bitbucket.org/apppoint/devrelease/src/master/

#### Customer Release Builds
The final build of the software is generally handed to the Customers as release builds. But, if client agrees on certain features in the first release of the software. Other features/improvements/requirements as well as bug fixes are done on the Dev release build and given to the client as patch updates. Generally, Customer release builds are updated quarterly and patch updates are done on need basis.

#### Enabling Azure AD auth support SQL server 
User access to the development assets of user DB and resources in cloud can be enabled using Azure AD (Office 365 credentials). This is required as modeler publish will connect to cloud SQL server database. Also, the local host of IIS client and background services will require to be connected to cloud database. This is a one-time set-up required to enable your dev set-up for new changes introduced in the build.

To map your office 365 credentials in Credential Manager tool:
1.	Open **Credential Manager** from the **Start >>Search window** of your desktop.
2.	Navigate to **Generic Credentials** tab and click **Add a generic credential**.
3.	In the **Add a generic Credential dialog**, provide the Internet or network address name as **BizAPPClient**.
4.	Add your Office 365 credentials in the User name and Password text boxes as shown below.
5.	Click **OK**. The new entry will appear in the **Windows Credentials list**. 
6.	Restart all your registry, services and clients including IIS.


