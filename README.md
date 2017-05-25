### Overview
For most projects under version control (Git). All workflows operation following the Git workflow. More can be found about this process here. Each developer or any active contributor will typically work on their own branch. Along with that, there are 3 operational deployment branches (dev, staging, master) with master being the production or live branch. A typical deployment is as follows

#### Scenario | Predeployment
1. Say three devs, you (yourbranch) and two others(devA, devB), are working on a project
2. git checkout devA(devA’s branch on your computer, assuming you have it)
3. If you don’t have it create it and checkout(git branch devA and then git checkout devA)
4. Pull devA branch (git pull origin devA)
5. Merge devA’s branch into your own. On your branch, run git merge devA 
6. Ensure you have no conflicts and move on to the next developers branch
7. git checkout devB (devB’s branch)
8. If you don’t have devB branch create one as for devA above and checkout (git branch devB and then git checkout devB)
9. Pull devB branch(git pull origin devB)
10. Move back to your working branch git checkout yourbranch
11. Merge devB’s branch into your own git merge devB
12. RESOLVE ALL CONFLICTS AT THIS STAGE - VERY IMPORTANT
13. git checkout dev
14. git pull origin dev
15. Merge your working branch into dev (git merge yourbranch)
16. Push merged dev branch (git push origin dev)
17. All branches should be synced at this point and testing by the merger should happen before any next steps are taken.

#### Scenario | Dev -> Staging Deployment
16. On mergers machine, git checkout staging
17. git merge dev, Resolve any conflicts if any
18. git push origin staging
19. SSH onto the staging server and move into the working directory for that project
    Note: some projects differ from one another, so it may be best to identify this workflow on a per-project basis
20. Cd to ‘default’ directory
21. git pull origin staging
22. Staging should now be launched. It is typical that you may need to run a composer update on push, but that it usual on a per-deployment basis. 


#### Scenario | Staging -> Master Deployment

23. On mergers machine, git checkout master
24. git merge dev or staging. Either or does not matter as they should be the EXACT same at this point
25. SSH to Production server
26. Cd to ‘default’ directory
27. git pull origin master
    a) For SAR, their production environment is managed through a continuous deployment tool called Envoyer.
    b) The credentials for this service are in our lastpass account
    c)Once logged in, go to the Sons Of The American Revolution project and click the deploy button. Typical deployment for this site is roughly 93 seconds.
    
    
#### Installing sec panel
sudo apt-get update


sudo apt-get install secpanel


Host should be 'forge'
User is the ip address
Identity - click the browse button and select ~/.ssh/id_rsa

Leave ipv4 and ssh2 radio button checked

Go to the button with 'Lock' icon
Select Add identity
Select ~/.ssh/id_rsa.pub

Click 'Launch Agent'

Set up your ssh key in Laravel Forge
Make sure that your ssh keys are named differently, even though they may be the sam
To get your ssh key open your terminal and type cat ~/.ssh/id_rsa.pub
Copy the output and paste inside Forge

In your secpanel select the branch and then click Connect
A new terminal will open up once you are logged in



