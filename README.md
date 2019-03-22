# Orchestrator Demo

I have utilized Bitbucket pipelines, a Heroku App and small python script to demonstrate a deployable package with automation, failure collection, notification and build retries.

The following accounts have been created for the purpose of this demo.

Bitbucket Cred.
alextestemail1000@gmail.com
6JHFm2z6$vHk

Heroku Cred.
alextestemail1000@gmail.com
ZtZD8!rgC3dv


### Bitbucket Demo

Automation jobs are run by one of two ways, but triggering a commit or manually running the job. Currently, the deployment job is set for hourly.

To manually run a a job (fastest way to demo)
1. on left pane, click "Pipelines" 
2. in center of screen click on any job
3. to left of out window click "Rerun"

- build steps will proceed with the mathfunction.py performing a calculation and then pushing that change to a heroku app
- each build step is viewable by click on the build step it will drop down with the operations listed

To automatically run a job without having to clone the entire repository
1. on left pane, click "Source"
2. in center of code editor click "mathfunction.py"
3. on top-right corner of window click "edit"
4. delete or add a line of incorrect code
5. on bottom-right corner of code editor click the blue "Commit" button
6. add a message such as "this will demonstrate a build failure"
7. click the blue "Commit" button
8. on left pane, click "Pipelines" 
9. in center of screen click you will see your commit message with a job running
10. you will see the output failure 

The python function has already been deployed to Heroku, can the build pipeline can be viewed by logging in with the given credentials. 


### Notifications/Alerting
Notifications are automatically setup for failures, this is configued via the users in the project. An example of a notification of an email subject line is

"[Bitbucket] Pipeline for master failed on 6d919a4 (alextest1000/bitbucket-clearmetal-demo)"
With additional information on the user who committed files and what files may be failing


### Design Choices:
I was hoping to work with AWS/SaltStack/Ansible a technology that Clearmetal uses in its automation stack. Unfortunately, on a consumer level most of these technologies are not very friendly requiring business emails or consultations with sales reps before even accessing a trial. I intially started with AWS building clusters, ELBs and creating instances which I was intending to run Docker on. AWS documentation is awful and with the time given I switched gears to work with Google Cloud Products (GCP) getting access to similar tools as AWS but with phenomenal documentation. With time running out I decided to using Bitbucket being the most popular free option with its suite of tools and features to automate and deploy code. Bitbucket Pipelines uses a .yaml file to specify what kind of services should be ran. I created a simple python function to multiply numbers and deploy that as an app Heroku. Other tools such as Ansible and AWS can be integrated with Bitbucket pipelines making it highly scalable which I intend on looking into. AWS has a very steep learning curve, while I made significant progress with the time given I could not deliver a solution with that platform. Given more time I intended on dockerizing a python app across multiple instances using CloudWatch to monitor real time data. With time gone I wanted a deliverable solution that addressed all the necessary features for this challenge and Bitbucket was the winner.




