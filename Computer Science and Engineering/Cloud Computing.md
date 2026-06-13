## Tools
### Docker and Kuberenetes
I want to build a mental model of docker/ kubernetes and dev-ops in general

Our fundamental aim is to be able to provide a deterministic/uniform working of our apps across different platforms. For that we need to be able to develop and test these on such environments.

We started of with virtual machines, where we had a software - hypervisor that built upon the host machine's hardware and containerised everything up from the OS level. This works good but we consume a lot of compute resources and time during the development process

Next we have docker. Docker builds images/containers on top of the existing OS, sharing the native OS(kernel) instead of the hardware itself. This helps us have smaller images, quicker development times at the same time meeting the fundamental requirement of a uniform/deterministic working of our software

docker ultimately runs on linux kernels. it directly talks to the kernel when run on linux and it runs on VMs on other OSs - WSL on windows and hyperkit on mac

To maintain our application now, we run it on a docker container and monitor the health of the service, the incoming connections(security), the safety of the physical hardware, provisioning new resources when our app is consuming most of the allocated resources, and so on. But we generally have multiple services in our application suite. We cannot individually monitor and maintain them at a granular detail. we have kuberenetes for this exact reason. but before that, we look into docker-comnpose

docker-compose uses docker compose files to provision resources and maintain multiple services with the required architecture on a single machine. it solves a few of the problems discussed above. but it fails to answer - what if one of the container dies down, or what is the machine dies? kuberenetes answers this

kubernetes is an orchestrator. it maintains the services, provisions new resources, gives us a macro level view of the resources that are being run. all it needs is docker images and specific instructions about how each of our app is expected to work. kuberenetes does not use docker files. it directly uses docker images(local or from the registry). 

kuberenetes has worker nodes and pods. everything is managed by a set of processes called the master plane. the most important part being the API server and etcd - a db that maintains the state of everything

kuberenetes depends on manifests(usually .yaml files) that instruct kuberenetes about the state of my services. eg.: i want 3 instances of my services with 2 gb of RAM each and with a load balancer in the front.