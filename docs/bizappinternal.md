
In this section, you will learn to setup BizAPP and its environment for internal users and developers.


## Accessing Bitbucket Repositories
The BizAPP Dev build repository Dev release is available in Bitbucket in the link provided below.
https://bitbucket.org/apppoint/devrelease/src/master/

### Signing into Bitbucket
Bitbucket is a system for hosting version control repositories. Before, you use Bitbucket, you have to create an account. You can use the standard sign up or you can create one through Open ID (using an existing Google or Yahoo account). 
To use the standard Bitbucket sign-up:  
1.	In any Browser, open the link  https://bitbucket.org
2.	Select Sign-Up for an account. A Create your account for new Sign-up window appears on screen.
3.	Enter a unique User Name (it can contain numbers, letters, and underscore characters up to 30). Bitbucket appends this username to the URL for all the repositories you create.
4.	Provide an Email address that is unique across the Bitbucket site. The system will send you a confirmation email.
5.	Type in a Password and ensure that your password is sufficiently complex and meets the security standards. 

A new account is created in Bitbucket. You can use this Email ID to login into Bitbucket to view remote repositories.

NOTE: On your avatar, check if you have permissions to (Read/Write access) to the BizAPP Build repository. This is required to pull latest updates from the build. Otherwise, permission has to be given by the Owner of the remote repository.

###SSH Authentication

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


