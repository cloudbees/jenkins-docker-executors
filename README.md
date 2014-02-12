# Run Jenkins builds that use docker

This is a docker image that contains Jenkins, and has the ability to run docker, itself, inside docker!
(crazy, I know).

    
    docker run -p 8080:8080 -privileged michaelneale/jenkins-docker-executors


This will download, and then run Jenkins in a docker container - on port 8080. 

You can see your docker conatiner running with:

    docker ps

If you with to use a volume outside to store your workspace, you can with bind mounting and setting the JENKINS_HOME directory. 

If you wish to use docker in a build - you can. You can just use the `docker` command from a freestyle build, it will work just like expect it would. Don't do anything crazy like try to run this thing itself inside docker, as then you end up in an inception like world and ultimate in limbo. http://inception.davepedu.com/ ;)

This works via the exellent work covered here https://github.com/jpetazzo/dind


