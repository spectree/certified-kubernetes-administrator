## Take help from kubectl command directly as below
- kubectl run --help
- kubectl expose --help


## Examples
### Start a single instance of nginx.
kubectl run nginx --image=nginx

###  Start a replicated instance of nginx.
kubectl run nginx --image=nginx --replicas=5

###  Dry run. Print the corresponding API objects without creating them.
kubectl run nginx --image=nginx --dry-run

###  Start a single instance of nginx and and let the container expose port 5701
kubectl run nginx --image=nginx --port=5701

###  Start a single instance of busybox and keep it in the foreground, don't restart it if it exits.
kubectl run -i --tty busybox --image=busybox --restart=Never

###  Start the nginx container using the default command, but use custom arguments (arg1 .. argN) for that command.
kubectl run nginx --image=nginx -- <arg1> <arg2> ... <argN>


###  Start the nginx container using a different command and custom arguments.
kubectl run nginx --image=nginx --command -- <cmd> <arg1> ... <argN

###  Start the perl container to compute π to 2000 places and print it out.
kubectl run pi --image=perl --restart=OnFailure -- perl -Mbignum=bpi -wle 'print bpi(2000)'

###  Start a single instance of hazelcast and set environment variables "DNS_DOMAIN=cluster" and "POD_NAMESPACE=default" in the container.
kubectl run hazelcast --image=hazelcast --env="DNS_DOMAIN=cluster" --env="POD_NAMESPACE=default"

