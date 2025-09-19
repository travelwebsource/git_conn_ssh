 *** Setup local machine to connect git through SSH keypairs ***

1. create a .ssh directory ---> and give permission ---> chmod 700 .ssh
2. cd into the directory on your terminal --> generate ssh keypairs
    ---> `ssh keygen -t 4096 -C "<company-email>"`
3. Do a `ls` to check the created files on macOS -->  id_whatever id_whatever.pub 
4. We need to start ssh-agent ---> `eval "$(ssh-agent -s)"` --> (Make sure to cd in .ssh and then run this command)
    ---> This will start a Agent and you will be able see Agent pid 2637 (Process id)
    ===> Which will run in the background
    ---> `ssh-add id_whatever` ( adding ssh key agent ) Enter  
5. Once we have created the ssh keys on local machine --> sign into github.com acct
    
6. Click Profile ---> Settings ---> SSH and GPG keys ---> New SSH key
    ---> Give a name, Select how Key Tyep : Authentication / Sign in
    ---> Copy the .pub key from your local machine
    ---> To copy: `cat id_rsa.pub` ---> then copy the ssh
    ---> In git Key textarea paste it.
    ---> Click Add SSH key
7. goto terminal ---> `ssh -T git@github.com (This will test if our connection is successful)
    ---> You will see the following msg:
    ( Warning: Permanently added the ECDSA host key for IP address '<Address>' to the list of known hosts.
        Hi travelwebsource! You've successfully authenticated, but GitHub does not provide shell access. )
 ---> Connection successful       

7. Done lets test it.

Test it : Open a existing Repo or create a test-repo on your git acct ( not a good practice)
--> Assuming we have a repo lets now clone it.

8. Lets click on a repo which already exist test-repo ---> click <Code > green btn 
    ---> Must select SSH ( Not HTTP Or Other one)
    ---> copy the url which will start with git.....
    ---> Open Terminal ---> `git clone git@github.com:travelwebsource/git_conn_ssh.git` Enter

    Now it will download the complete repo to your local machine 
    We don't have to use password or username to autheticate to sign in`
