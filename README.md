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
Move back to your working branch git checkout yourbranch
Merge devB’s branch into your own git merge devB
RESOLVE ALL CONFLICTS AT THIS STAGE - VERY IMPORTANT
git checkout dev
git pull origin dev
Merge your working branch into dev (git merge yourbranch)
Push merged dev branch (git push origin dev)
All branches should be synced at this point and testing by the merger should happen before any next steps are taken.
