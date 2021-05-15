## Deployment Configuration

While performing a rolling update, there are two important configurations to know.

a. maxUnavailable=0 and maxSurge=20%  << Full Capacity is maintained.

b. maxUnavailable=10% and maxSurge=0   << Update with no extra capacity. In-place updates.

If you want fast rollout, make use of maxSurge.

If there might be a resource quota in place and partial unavailability is acceptable, maxUnavailable can be used.


## Restart Policies

By default, Docker containers will not start when they exit or when docker daemon is restarted.

Docker provides restart policies to control whether your containers start automatically when they exit, or when Docker restarts.

We can specify the restart policy (in dokcer run commands args) by using the --restart flag with dokcer run command.


a. no : default, don;t automatically restart the cotainer
b. on-failure : restart the container if it exits due to an error, which manifest as a non-zero exit code.  
c. unless-stopped : restart the cotnainer uless if it is stopped or Docker daemon itself stopped oe restarted.
d. always. : Always restart the cotnainer if it stopped


Example : docker container run --d --restart unless-stoppd nginx.  && systemctl restart docker 






