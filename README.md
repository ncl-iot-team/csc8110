# CSC8110: Cloud Computing - Docker Platform
This repository contains essential materials and references for the practicals of CSC8110 Cloud computing module. Please read https://docs.docker.com/engine/docker-overview/ before doing the exercises.
## Installation
### Virtual Machine Pre-Installed with Docker (Recommended)
Docker environment run seamlessly in Linux. It is recommended using the provided Virtual Machine Linux Image. Download Virtual Box Image: https://goo.gl/qDNi1Z

If you have already installed Docker for Windows, existing installation and related feature (Hyper-V) may create conflicts while running a VM image. Please disable Hyper-V and restart windows before running VirtualBox


![Disable HyperV Step 1](disableHyper-V-1.png?raw=true "Search for 'Turn Windows Features on or off'")
![Disable HyperV Step 2](disableHyper-V-2.png?raw=true "Disable Hyper-V")


### Windows
Please refer https://docs.docker.com/docker-for-windows/install/
### Mac
Please refer https://docs.docker.com/docker-for-mac/install/
### Ubuntu
Please refer https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/

Login Password: 'password'
## Exercise: Basics
Please refer https://docs.docker.com/get-started/  and perform all the tasks up to "Part 3: Services" under Getting started with Docker section in the documentation
## Docker Engine SDK and API
Docker provides an API for interacting with the Docker daemon (called the Docker Engine API), as well as SDKs for Go and Python. There are unofficial libraries for other programming languages. If you choose to use Java as your programming language, you may use https://github.com/spotify/docker-client. Unofficial libraries don't come with all the features. Some provide control over basic docker engine features only.

The SDKs allow you to build and scale Docker apps and solutions quickly and easily. If Go or Python won’t work for you, you can use the Docker Engine API directly or any other language third-party SDKs for 

The Docker Engine API is a RESTful API accessed by an HTTP client such as wget or curl, or the HTTP library which is part of most modern programming languages.

Refer https://docs.docker.com/develop/sdk/

Python SDK Reference : https://docker-py.readthedocs.io/en/stable/

## cAdvisor Remote REST API Reference
1. Pattern of API endpoint
    http://&lt;hostname&gt;:&lt;port&gt;/api/&lt;version&gt;/&lt;request&gt;
    
    The current version of the API is v1.3 and there is a beta release of the v2.0 API
    
    Supported request types: &quot;containers,docker,events,machine,subcontainers&quot;
    
    Example http://localhost:8888/api/v1.3/containers
    The result is returned in JSON format.
2. To get information of all sub containers http://localhost:8888/api/v1.3/subcontainers/
3. To get information of a specific sub container http://localhost:8888/api/v1.3/subcontainers/&lt;subcontainername&gt;

### Example 1. To get information of all sub-containers within docker container
    http://localhost:8888/api/v1.3/subcontainers/docker
### Example 2. To get information of a container within docker container
    http://localhost:8888/api/v1.3/subcontainers/docker/497cec18b8114c2ecdda1efb87f7795c594d7b431a59d5c775390426093b9631
    Containers’ name are available from the endpoint
    http://localhost:8888/api/v1.3/subcontainers or
    http://localhost:8888/api/v1.3/subcontainers/docker

Reference
https://github.com/google/cadvisor/blob/master/docs/api.md

## Docker Swarm Visualizer
Refer: https://github.com/dockersamples/docker-swarm-visualizer

Also Refer the docker-compose.yml file in https://docs.docker.com/get-started/part5/#add-a-new-service-and-redeploy 

## FAQ
1. **Tips for Task 1 - Pull the webapplication image and test**

    It is a basic docker job which has to be performed using following methods
    1. Command line (Refer https://docs.docker.com/get-started/part2/#run-the-app)
    1. SDK or API (Refer https://docs.docker.com/develop/sdk/examples/ )
        
    You may use any programming language which has a compatible Docker SDK or call RESTful API from the program.
    
2. **Tips for Task 2 - Deploy a multi-service application in a Docker environment**

    Please make sure you practised the [exercise](https://github.com/nclcloudcomputing/csc8110-2017-18#exercise-basics)     given on the top of this page. Firstly perform the task in command line using docker-client as described in the practise docs. Then find the corresponding interfaces in SDK or API to do it programmatically.

3. **Tips for Task 3 - Load Generator**

    You may use any programming language to make this program. If you want to build it as a shell program, you may use a tool called 'curl' (Refer https://curl.haxx.se/docs/manpage.html). Most of the programming languages come with a native HTTP client library or you can use any third party libraries, which could enable it to call HTTP endpoints.

4. **Tips for Task 4: Add a docker monitoring tool**

    Refer https://github.com/google/cadvisor

5. **Task 5: Insert benchmark result into database**

    Use [cAdvisor API](https://github.com/nclcloudcomputing/csc8110-2017-18#cadvisor-remote-rest-api-reference) to retrive the monitoring information.

    Insert this data into mongoDB instance created in Task 2.
    
    Refer https://docs.mongodb.com/getting-started/shell/#available-editions to understand how to use mongoDB driver in different programming languages.
