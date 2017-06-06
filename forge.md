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
2. Uncomment (by placing a semicolon in front) the lines which load those libraries

### If you get a 500 error
1. Go to the forge terminal
2. Do composer install
3. Do php artisan migrate
4. Check your .env file in forge for database login credentials.
5. Check /var/log/nginx/error.log for any error
6. Make sure the nginx file has  fastcgi_pass unix:/run/php/php7.0-fpm.sock 
7. If it was php5.0-sock, change it to php7.0.sock
8. For laravel project make sure you have done sudo chmod 777 -R for database/, bootstrap/, and storage/ directories
9. Make sure your folder under root in nginx file points to the proper public/ directory for laravel
