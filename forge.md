#### Forge Error saying 'could not pull from remote repository'

This means that the ssh-key for forge has not been registered in bitbucket. 

1. Ssh into forge terminal.
2. type cat ~/.ssh/id_rsa.pub
3. Copy the ssh key in the terminal
4. Go to bitbucket, click 'Settings' under the project
5. Click 'Access keys'
6. Click 'Add key'
7. Add the copied ssh key there and also give a name

If bitbucket says 'the key has been used by another user':

1. Create a new ssh key for forge by typing 'ssh-keygen' in forge terminal
2. Press enter for all prompts
3. Type cat ~/.ssh/id_rsa.pub
4. Copy this new ssh key and paste it in bitbucket as mentioned above
5. You should be good after this.


#### Forge/Laravel error 'could not load dynamic library ../mysql.so'
1. For Ubuntu 16.04, go to /etc/php/7.0/cli/php.ini
2. Uncomment (by placing a semicolon in frong) the lines which load those libraries
