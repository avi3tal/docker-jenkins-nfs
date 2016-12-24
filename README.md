# jenkins-nfs

This Docker container runs Jenkins and mount a NFS or EFS (AWS Elastic File System) as JENKINS_HOME directory.

When the docker image runs the following environment variables are mandatory:

    MOUNT_VOLUME=fs-xxxxxxx.efs.eu-west-1.amazonaws.com:/

    MOUNT_TYPE=nfs4

    MOUNT_OPTIONS=nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2 fs-d514ed1c.efs.eu-west-1.amazonaws.com:/

Docker image must be privileged

    docker build -t jenkins-nfs .

    docker run --name jenkins-nfs --privileged -e MOUNT_VOLUME=fs-x... MOUNT_TYPE=nfs4 MOUNT_OPTIONS=nfs... jenkins-nfs


