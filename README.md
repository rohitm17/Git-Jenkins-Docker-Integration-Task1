# LW-HomeWork
Jenkins+Docker+Github integration
Home Work Summary

JOB#1
If Developer push to dev branch then Jenkins will fetch from dev and deploy on dev-docker environment.

JOB#2
If Developer push to master branch then Jenkins will fetch from master and deploy on master-docke environment.
both dev-docker and master-docker environment are on different docker containers.

JOB#3
Jenkins will check (test) for the website running in dev-docker environment. If it is running fine then Jenkins will merge the dev branch to master branch
