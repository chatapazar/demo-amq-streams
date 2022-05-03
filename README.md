Step to Demo
- login


oc apply -f cluster.yaml
oc apply -f topic.yaml

oc apply -f producer.yaml
oc apply -f consumer.yaml
oc apply -f consumer2.yaml
oc apply -f consumer3.yaml
oc apply -f consumer4.yaml
oc apply -f consumer5.yaml
oc logs -n amq-streams -f $(oc get pods -l app=hello-world-producer -o name)
oc logs -n amq-streams -f $(oc get pods -l app=hello-world-consumer -o name)
oc delete pods my-cluster-kafka-0 --grace-period=0
oc delete kt my-topic


producer/consumer source code
https://github.com/strimzi/client-examples

# .NET on Kubernetes

![](images/logo.png)


## Table of Contents
- [.NET for Cloud-Native](dotnetcloudnative.md)
  - Deploy .NET Core from Developer Console with S2I
  - Deploy .NET Core from Dockerfile with S2I
  - Deploy .NET Core from oc command with S2I
  - .NET User Workload Monitoring](#net-user-workload-monitoring)
  - .NET with Openshift Pipeline (Tekton)
  - .NET with OpenShift Service Mesh
  - .NET with OpenShift Serverless
  - .NET with OpenShift GitOps
- [.NET Core on OpenShift](dotnetcore.md)
  - Deploy with S2I on OpenShift Developer Console
    - from Git
    - from Dockerfile 
  - Deploy with oc command
  - Deploy with odo command
  - Openshift pipelines Support (tekton)
- [.NET Framework on OpenShift](dotnetframework.md)
  - Build .NET Framework Windows Container
  - Deploy .NET Framework Windows Container on OpenShift Windows Container Node
  - Build .NET Framework Windows Container with Docker