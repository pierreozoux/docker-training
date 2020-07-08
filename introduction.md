# Docker

### Pierre Ozoux

25 Juin 2020



# Objectives of the session

 - terminology
 - problem solved by docker
 - understand containers
 - know how to build a docker image
 - manage volumes and networks
 - be capable to compose applications


# Program

 - installation
 - basics
 - runtime
 - image
 - networks
 - volumes
 - builder
 - advanced
 - compose
 - wrapup


# Methodology

 - presentation
 - hands on
 - exercises


# meta

```
git clone --recurse-submodules https://github.com/pierreozoux/docker-training
```



# A Brief history of the cloud 


## Xen (2003) 
## KVM (2007)


## Amazon Web Services 2006

![AWS logo](/images/AmazonWebservices_Logo.svg)


## IaaS

Infrastructure as a Service

(Amazon, OVH, Gandi)


## PaaS

Platform as a Service

(EngineYard, Heroku)


## SaaS

Software as a Service

(basecamp, gmail, impots.gouv.fr)



# What is DevOps?


## SysAdmin way:

Quand je fais un "ifconfig eth0 down" en SSH sur un serveur distant.

![sysadmin](/images/sysadmin.gif)

[source: lesjoiesdusysadmin.tumblr.com](http://lesjoiesdusysadmin.tumblr.com/post/83722079163/quand-je-fais-un-ifconfig-eth0-down-en-ssh-sur)


## DevOps way:

Unnecessary automation!

![devops](/images/devops.gif)

[source: devopsreactions.tumblr.com](http://devopsreactions.tumblr.com/post/117760555890/unnecessary-automation)


## Dev and Ops

CI/CD

Note:
You manage your Infrastructure like you manage your code.
Feature request, bug tracking, Continuous deployment


## SRE

Infrastructure as Code



# [12 Factor App](https://12factor.net/)

Developed by Heroku


## I. Codebase

One codebase tracked in revision control, many deploys


## II. Dependencies

Explicitly declare and isolate dependencies

Note:
dependency declaration: Gemfile
dependency isolation: bundle


## III. Config

Store config in the environment

Note:
An app's config is everything that is likely to vary between deploys (staging, production, developer environments, etc). This includes:
 - Resource handles to the database, Memcached, and other backing services
 - Credentials to external services such as Amazon S3 or Twitter
 - Per-deploy values such as the canonical hostname for the deploy
environment variables


## IV. Backing Services

Treat backing services as attached resources

Note:
email, db, twitter


## V. Build, release, run

Strictly separate build and run stages

Note:
build stage
release stage
run stage


## VI. Processes

Execute the app as one or more stateless processes

Note:
Twelve-factor processes are stateless and share-nothing. Any data that needs to persist must be stored in a stateful backing service, typically a database.


## VII. Port binding

Export services via port binding

Note:
The contract with the execution environment is binding to a port to serve requests.
Note also that the port-binding approach means that one app can become the backing service for another app.


## VIII. Concurrency

Scale out via the process model

Note:
Twelve-factor app processes should never daemonize or write PID files.


## IX. Disposability

Maximize robustness with fast startup and graceful shutdown

Note:
The twelve-factor app's processes are disposable, meaning they can be started or stopped at a moment's notice. This facilitates fast elastic scaling, rapid deployment of code or config changes, and robustness of production deploys.


## X. Dev/prod parity

Keep development, staging, and production as similar as possible

Note:
The twelve-factor app is designed for continuous deployment by keeping the gap between development and production small.


## XI. Logs

Treat logs as event streams

Note:
A twelve-factor app never concerns itself with routing or storage of its output stream. It should not attempt to write to or manage logfiles.


## XII. Admin processes

Run admin/management tasks as one-off processes



# Docker


## Containers?

 - BSD Jail
 - Solaris Zones
 - Linux containers (contributed by Google 2008)
  - LXC / OpenVZ
  - docker/rkt/nspawn


## Docker is:

- An open source tool that places a layer on top of Linux containers (cgroups and namespaces) to make it simple to package and ship complex apps
- A tool for creating a layered filesystem; each layer is versioned and can be shared across running instances, making for much more lightweight deployments
- A company behind the project, as well as a site called the "Docker Hub" for sharing containers - Docker

from [docker-jumpstart](https://github.com/odewahn/docker-jumpstart)


## Docker isn't:

 - A virtual machine. Unlike a true VM, a docker container does not also require a host OS, meaning it's much slimmer than a real VM
 - An infrastructure automation tool, like Puppet or Chef. Like those other tools, Docker is a major player in the DevOps space, but its focus is around running apps in a container environment, as opposed to representing a machine state.

from [docker-jumpstart](https://github.com/odewahn/docker-jumpstart)


## VM

![VM](/images/VM.png)


## Docker/Container

![Docker](/images/docker.png)



## The challenge

![challenge](/docker-img/the-challenge.png)


## The matrix from hell

![matrixhell](/docker-img/the-matrix-from-hell.png)


## Cargo transport pre 1960

![cargo](/docker-img/cargo.png)


## Also a matrix from hell!

![also](/docker-img/also.png)


## Solution: Intermodal shipping container

![solution](/docker-img/solution.png)


## Docker is a container system for code

![docker](/docker-img/shipping.png)


## Docker eliminated the matrix from hell

![eliminates](/docker-img/eliminates.png)


## Separation of concerns

![separation](/docker-img/separation.png)
