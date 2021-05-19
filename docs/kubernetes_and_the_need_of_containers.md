# Kubernetes and the Need for Containers  

Before starting this ramp-up we recommend to learn before the concept of containers, since kubernetes is a tool that helps you to orchestrate containers and for understanding kubernetes and performing the challenges that this ramp-up propose you'll need to know what containers are, why we use them and how they work. The next reading briefly overviews the topic.  

A container is a mini-virtual machine. It is small, as it does not have device drivers and all the other components of a regular virtual machine. Docker is by far the most popular container and it is written in Linux. Microsoft also has added containers to Windows as well, because they have become so popular.

The best way to illustrate why this is useful and important is to give an example.

Suppose you want to install the nginx web server on a Linux server. You have several ways to do that. First, you could install it directly on the physical server’s OS. But most people use virtual machines now, so you would probably install it there.

But setting up a virtual machine requires some administrative effort and cost as well. And machines will be underutilized if you just dedicate it for just one task, which is how people typically use VMs. It would be better to load that one machine up with nginx, messaging software, a DNS server, etc.

The people who invented containers thought through these issues and reasoned that since nginx or any other application just needs some bare minimum operating system to run, then why not make a stripped down version of an OS, put nginx inside, and run that. Then you have a self-contained, machine-agnostic unit that can be installed anywhere.

Now containers are so popular than they threaten to make VMs obsolete, is what some people say.

Docker Hub

But making the container small is not the only advantage. The container can be deployed just like a VM template, meaning an application that is ready to go that requires little or no configuration.

There are thousands of preconfigured Docker images at the Dockerhub public repository. There, people have taken the time to assemble opensource software configurations that might take someone else hours or days to put together. People benefit from that because they can install nginx or even far more complicated items simply by downloading them from there.

For example, this one line command will down, install, and start Apache Spark with Jupyter notebooks (iPython):

docker run -d -p 8888:8888 jupyter/all-spark-notebook

As you can see it is running on port 8888. So you could install something else on another port or even install a second instance of Spark and Jupyter.

On the Need for Orchestration

Now, there is an inherent problem with containers, just like there is with virtual machines. That is the need to keep track of them. When public cloud companies bill you for CPU time or storage then you need to make sure you do not have any orphaned machines spinning out there doing nothing. Plus there is the need to automatically spin up more when a machine needs more memory, CPU, or storage, as well as shut them down when the load lightens.

Orchestration tackles these problems. This is where Kubernetes comes in.

