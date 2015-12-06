#!help

#What you can get from this file.

    1. how to generate the rsa password for github.
    2. how to add the rsa to github.
    3. how to test whether it works.


1. create the key if needed.
   ~/.ssh/

   $ ssh-keygen -t rsa -C "your_email@example.com"
   :Creates a new ssh key using the provided email
    Generating public/private rsa key pair.
    Enter file in which to save the key (/your_home_path/.ssh/id_rsa): "input the location."
        eg: ~/.ssh/xx/id_rsa_xx
    Enter passphrase (empty for no passphrase): "input the password."
        eg: xx  you can press the Enter button directly.

   #result:
   Your identification has been saved in /your_home_path/.ssh/xx/id_rsa_xx.
   Your public key has been saved in /your_home_path/.ssh/xx/id_rsa_xx.pub.
   The key fingerprint is:
   01:0f:f4:3b:ca:85:d6:17:a1:7d:f0:68:9d:f0:a2:db your_email@example.com
   
2. execute cmd to add the key into ssh-agetn bellow.

   $ eval "$(ssh-agent -s)"
   # Agent pid 59566
   $ ssh-add ~/.ssh/id_rsa


3. open the file ~/.ssh/id_rsa.pub and copy the content to github list of ssh-key. (project -> Settings -> deploy keys)

4. use bellow cmd to test.

   $ ssh -T git@github.com

   #result:
    The authenticity of host 'github.com (207.97.227.239)' cannt be established.
    RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
    Are you sure you want to continue connecting (yes/no)? "input yes here."

   #sucess:
   Hi username! You have successfully authenticated, but GitHub does not provide shell access.
