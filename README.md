# PROJECT
Jenkins+Docker+Github integration
Project Summary

JOB#1
If Developer push to dev branch then Jenkins will fetch from dev and deploy on dev-docker environment.

JOB#2
If Developer push to master branch then Jenkins will fetch from master and deploy on master-docke environment.
both dev-docker and master-docker environment are on different docker containers.

JOB#3
Jenkins will check (test) for the website running in dev-docker environment. If it is running fine then Jenkins will merge the dev branch to master branch


In this project we going to build a complete pipeline from developrs commit to testing and deployment.

Tools and Technologyies used:
1. Git and Github
2. Docker
3. Jenkins
4. RHEL-8 OS in VM
5. Base OS:Windows 10

<H3>First setup environment in RHEL-8 </H3>
<pre>
# setenforce 0
# systemctl stop firewalld
# systemctl start docker
# systemctl start httpd
# systemctl start jenkins
<pre>
Docker image required : Httpd
Docker containers required: 
1. devoshw : for testing purpose used by dev branch
2. masteroshw : for production purpose used by master branch

To automate the git push we need to create a hook:
cat >> .git/hooks/post-commit
#!/bin/bash
git push

![git](https://github.com/rohitm17/LW-HomeWork/blob/master/Screenshots/git.png)
![github](https://github.com/rohitm17/LW-HomeWork/blob/master/Screenshots/github.png)
JOB1:dev-job
![img1](https://github.com/rohitm17/LW-HomeWork/blob/master/Screenshots/Screenshot_2020-05-07%20dev-job%20Config%20%5BJenkins%5D.png)
JOB2: master-job
![img2](https://github.com/rohitm17/LW-HomeWork/blob/master/Screenshots/Screenshot_2020-05-07%20master-job%20Config%20%5BJenkins%5D.png)
JOB3: merge-job
![img3](https://github.com/rohitm17/LW-HomeWork/blob/master/Screenshots/Screenshot_2020-05-07%20merge-job%20Config%20%5BJenkins%5D.png)




