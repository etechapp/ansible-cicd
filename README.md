# CI-example
This repository will store code for the continuous integration using Jenkins and Ansible

# Run Sonar Scan

```
mvn sonar:sonar -Dsonar.projectKey=com.ansible -Dsonar.host.url=http://localhost:9000  -Dsonar.login=admin -Dsonar.password=admin

```
# T2.G2 - EtechApp
# Edit Files
Inventories > dev / prod > hosts > Insert IPs
Templates > index.html.j2 > Insert Browser Display
Jenkinsfile > edit url of repository

# Configure Webhook
On GitHub repo > Settings > webhook > URL: <JenkinsServerURL/github-webhook/ > Application JSON > Just Push > Save

# Create Job
Jenkins Dashboard > New Item > Name: t2.g2-ansible-jenkins > pipeline > ok

# Configure Job
GitHub webhook trigger > Definition: Pipeline script from SCM > SCM: Git > Repository URL: https://github.com/etechapp/ansible-cicd > Script path > Jenkinsfile > Apply and Save

# Run Build
After initialization, merge to main / production branch to build job
