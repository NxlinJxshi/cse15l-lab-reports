# Week 2 Lab Report

## Installing VScode

1) First install [Visual Studio Code](https://code.visualstudio.com/). Setting this up is easy as its a straightforward process and all instructions are provided while setting up.

![VSCode]<img width="1433" alt="Screen Shot 2022-06-06 at 6 37 40 PM" src="https://user-images.githubusercontent.com/103763994/172277115-1def92c7-47b0-4983-a75b-aa611f1454be.png">

## Remotely Connecting

2) Then install a program called [OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse), look up your CSE15L account email [here](https://sdacs.ucsd.edu/~icc/index.php) and reset your password.

Open the terminal in VS Code and type the following, but replace the aeg with your course specific username:

```ssh cs15lsp22aeg@ieng6.ucsd.edu```
You will get the message below. Type yes.
> The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.\
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.\
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
After entering your password you should see a window similar to the one below
![Remotely Connecting]<img width="718" alt="Screen Shot 2022-06-06 at 6 39 21 PM" src="https://user-images.githubusercontent.com/103763994/172277362-488ee22e-b507-455d-8c72-42630e6beb4e.png">

## Trying Some Commands
3) Try running the commands ```cd ```, ``` ls``` , ```pwd```, ```mkdir```, and ```cp```
![Trying Some Commands]<img width="293" alt="Screen Shot 2022-06-06 at 6 47 29 PM" src="https://user-images.githubusercontent.com/103763994/172278255-c8d0d277-aee7-4c30-b923-488958fca388.png">

## Moving Files with scp
4) We will now copy files over ssh wich scp. Create a file on your computer called WhereAmI.java and put the following contents into it: 
```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```
Then, in the terminal from the directory where you made this file, run this command, using your username:
```scp WhereAmI.java cs15lsp22aeg@ieng6.ucsd.edu:~/```
You should see something similar to the image below
![Moving Files with scp]<img width="478" alt="Screen Shot 2022-06-06 at 7 04 18 PM" src="https://user-images.githubusercontent.com/103763994/172280072-44b1ad7b-8097-43b7-bc2b-d3dda6f58e05.png">

## Setting an SSH Key
5) Using ssh keys we will not have to repeately input our password. The following command will create a public key and a private key which will be used to log in instead of a password
Type the following
> ssh-keygen
You can leave the prompts empty and then your terminal should look similar to the image below
![Screenshot 2022-01-15 021342]<img width="720" alt="Screen Shot 2022-06-06 at 7 06 45 PM" src="https://user-images.githubusercontent.com/103763994/172280837-6ca02317-2ae5-42be-9e45-3ce443a599ca.png">

Now run the following command
```
$ ssh cs15lsp22zz@ieng6.ucsd.edu
<Enter Password>
# now on server
$ mkdir .ssh
$ <logout>
```
Run the following command put replace the destination of the key with the one provided in your terminal above (destination of the key)
```
scp /Users/joe/.ssh/id_rsa.pub cs15lsp22@ieng6.ucsd.edu:~/.ssh/authorized_keys
```
![Screenshot 2022-01-15 021908]
As you can see below, I was logged into my account without inputting my password
![Screenshot 2022-01-15 021949]<img width="1298" alt="Screen Shot 2022-06-06 at 7 23 51 PM" src="https://user-images.githubusercontent.com/103763994/172282401-42572692-0e1c-40e7-a035-7554b1286b14.png">


## Optimizing Remote Running
6) You can now use all the command you have learned and more for smooth running of programs, such as writing a command in quotes at the end of an ssh command. 
```
scp WhereAmI.java cs15lsp22awz@ieng6.ucsd.edu:~/
ssh cs15lsp22awz@ieng6.ucsd.edu "javac WhereAmI.java; java WhereAmI"

```
