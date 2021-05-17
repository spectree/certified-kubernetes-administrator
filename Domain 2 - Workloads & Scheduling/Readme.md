# Domain - Workloads & Scheduling

The code mentioned in this document are used in the Certified Kubernetes Administrator 2020 course.

https://www.udemy.com/course/certified-kubernetes-administrator/?couponCode=CKA-SEP-20


# Video-Document Mapper

| Sr No | yaml  | Setup | Comments |
| ------ | ------ | ------ |------ |
| 1 | [Implementing Labels and Selectors][PlDa] |             |            |
| 2 | [Creating our first ReplicaSet][PlDb] |             |             |
| 3 | [Creating our first deployment][PlDc]|             |             |
| 4 | [Understanding Liveness Probe][PlDd] |             |             |
| 5 | [Understanding Readiness Probe][PlDe] |             |             |
| 6 | [Creating first Job in Kubernetes][PlDf] |             |             |
| 7 | [CronJobs][PlDg] |             |             |
| 8 | [Generating Deployment Manifests via CLI][PlDh] |             |             |
| 9 | [Understanding DaemonSets][PlDi] | [Prep Commands][PlDp]           | [Assigning Popds to Nodes][PlDh] <br/> [Assigning Popds to Nodes-2][PlDq] <br/> [fluent bit daemonset exaple][PlDq1]      |
| 10 | [Overview of NodeSelector][PlDj] |             |[Assigning Popds to Nodes][PlDh]            |
| 11 | [Understanding Node Affinity][PlDk] |             |[Assigning Popds to Nodes][PlDh]             |
| 12 | [Pod Affinity and Pod Anti-Affinity][PlDl] |  Require multi node cluster           |             |
| 13 | [Resource Limits][PlDm] | kubectrl describe node node-name            |             |
| 14 | [Scheduling Pods without a Scheduler][PlDn] | [Find statid pods in node][PlDr1]<br/>  [Static pods-1][PlDr2]<br/>  [Static pods-2][PlDr3]       | aka static pods. Statics can be installed without k8s controle plane. <br/> It is installed using kubelet agent. <br/> <br/> Place the k8s pod yaml file in /etc/kubernetes/manifests directory (default path kubelet found  running command :  systemctl status kubelet) <br/> of kubelet node.  <br/>Kubelet periodcally scan this directory and will create the pod.  <br/> Static pod cannot be deleted usng command "kubectl delete pod" (that is by requesting it to kube-apiserver)|
| 15 | [Taints and Toleration][PlDs] | [a. k8s-taints-tolerations-affinities][PlDs1]  <br/> [b. taints_tolerations][PlDs2]       | A taint allows a node to refuse pod to be scheduled  <br/> unless that pod has matching toleration            |
| 16 | [Multi-Container POD Design Patterns][PlDt] |             |             |
| 17 | [Pod Design Pattern Adaptor/Proxy Pattern][PlDt1] |   [Logging Example][PlDt2]  <br/> [Logging Architecture][PlDt3]       |             |


   [PlDa]: <https://github.com/zealvora/certified-kubernetes-administrator/blob/master/Domain%202%20-%20Workloads%20%26%20Scheduling/labels.yaml>
   [PlDb]: <https://github.com/zealvora/certified-kubernetes-administrator/blob/master/Domain%202%20-%20Workloads%20%26%20Scheduling/replicaset.yaml>
   [PlDc]: <https://github.com/zealvora/certified-kubernetes-administrator/blob/master/Domain%202%20-%20Workloads%20%26%20Scheduling/deployment.yaml>
  [PlDd]: <https://github.com/zealvora/certified-kubernetes-administrator/blob/master/Domain%202%20-%20Workloads%20%26%20Scheduling/livenessprobe.yaml>
   [PlDe]: <https://github.com/zealvora/certified-kubernetes-administrator/blob/master/Domain%202%20-%20Workloads%20%26%20Scheduling/readinessprobe.yaml>
   [PlDf]: <https://github.com/zealvora/certified-kubernetes-administrator/blob/master/Domain%202%20-%20Workloads%20%26%20Scheduling/jobs.yaml>
   [PlDg]: <https://github.com/zealvora/certified-kubernetes-administrator/blob/master/Domain%202%20-%20Workloads%20%26%20Scheduling/cronjob.yaml>
[PlDh]: <https://github.com/zealvora/certified-kubernetes-administrator/blob/master/Domain%202%20-%20Workloads%20%26%20Scheduling/manifest-cli.md>
[PlDi]: <https://github.com/zealvora/certified-kubernetes-administrator/blob/master/Domain%202%20-%20Workloads%20%26%20Scheduling/daemonset.yaml>
[PlDj]: <https://github.com/zealvora/certified-kubernetes-administrator/blob/master/Domain%202%20-%20Workloads%20%26%20Scheduling/nodeSelector.yaml>
[PlDk]: <https://github.com/zealvora/certified-kubernetes-administrator/blob/master/Domain%202%20-%20Workloads%20%26%20Scheduling/node-affinity-combined.md>
[PlDl]: <https://github.com/zealvora/certified-kubernetes-administrator/blob/master/Domain%202%20-%20Workloads%20%26%20Scheduling/podaffinity-required.yaml>
[PlDm]: <https://github.com/zealvora/certified-kubernetes-administrator/blob/master/Domain%202%20-%20Workloads%20%26%20Scheduling/requests-limits.yaml>
[PlDn]: <https://github.com/zealvora/certified-kubernetes-administrator/blob/master/Domain%202%20-%20Workloads%20%26%20Scheduling/pod-without-scheduler.md>

[PlDo]: <https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node/#:~:text=Run%20kubectl%20get%20nodes%20to,the%20node%20you've%20chosen>
[PlDp]: <https://github.com/spectree/certified-kubernetes-administrator/blob/master/Command_Setup_Commands.md>
[PlDq]: <https://medium.com/kubernetes-tutorials/learn-how-to-assign-pods-to-nodes-in-kubernetes-using-nodeselector-and-affinity-features-e62c437f3cf8>
[PlDq1]: <https://github.com/fluent/fluentd-kubernetes-daemonset/blob/master/fluentd-daemonset-elasticsearch-rbac.yaml>  

[PlDr1]: <https://stackoverflow.com/questions/65657808/how-to-identify-static-pods-via-kubectl-command>
[PlDr2]: <https://blog.mayadata.io/openebs/static-pods-in-kubernetes>
[PlDr3]:<https://kubernetes.io/docs/tasks/configure-pod-container/static-pod/>

[PlDs1]: <https://banzaicloud.com/blog/k8s-taints-tolerations-affinities/>
[PlDs2]: <https://docs.openshift.com/container-platform/3.6/admin_guide/scheduling/taints_tolerations.html>

[PlDt]:  <https://rx-m.com/ckad-online-training/ckad-online-training-module-2/#ckadmod2-multicontainerpods>
[PlDt1]: <https://github.com/spectree/certified-kubernetes-administrator/blob/master/Domain%202%20-%20Workloads%20%26%20Scheduling/adapter.yaml>
[PlDt2]: <https://medium.com/kubernetes-tutorials/cluster-level-logging-in-kubernetes-with-fluentd-e59aa2b6093a>
[PlDt3]: <https://kubernetes.io/docs/concepts/cluster-administration/logging/>
