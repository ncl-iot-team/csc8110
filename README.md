# CSC8110: Cloud Computing - Docker Platform
This repository contain essential materials and references for the practicals of CSC8110 Cloud computing module. Please read https://docs.docker.com/engine/docker-overview/ before doing the exercises.
## Installation
### Windows
Please refer https://docs.docker.com/docker-for-windows/install/
### Mac
Please refer https://docs.docker.com/docker-for-mac/install/
### Ubuntu
Please refer https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/
### Virtual Machine Pre-Installed with Docker
Download Virtual Box Image: https://s3.eu-west-2.amazonaws.com/ncl-share/DockerDevBox.ova

Login Password: 'password'
## Exercise: Basics
Please refer https://docs.docker.com/get-started/  and perform all the tasks under Getting started with Docker section in the documentation
## Docker Engine SDK and API
Docker provides an API for interacting with the Docker daemon (called the Docker Engine API), as well as SDKs for Go and Python. There are unofficial libraries for other programming languages. If you choose to use use Java as your programming language, you may use https://github.com/spotify/docker-client. Unofficial libraries doesn't come with all the features. Some provides control over basic docker engine features only.

The SDKs allow you to build and scale Docker apps and solutions quickly and easily. If Go or Python won’t work for you, you can use the Docker Engine API directly or any other language third party SDKs for 

The Docker Engine API is a RESTful API accessed by an HTTP client such as wget or curl, or the HTTP library which is part of most modern programming languages.

## cAdvisor Remote REST API Reference
1. Pattern of API endpoint
    http://&lt;hostname&gt;:&lt;port&gt;/api/&lt;version&gt;/&lt;request&gt;
    
    The current version of the API is v1.3 and there is a beta release of the v2.0 API
    
    Supported request types: &quot;containers,docker,events,machine,subcontainers&quot;
    
    Example http://localhost:8888/api/v1.3/containers
    The result is returned in JSON format.
2. To get information of all subcontainers http://localhost:8888/api/v1.3/subcontainers/
3. To get information of a specific subcontainer http://localhost:8888/api/v1.3/subcontainers/&lt;subcontainername&gt;

### Example 1. To get information of all subcontainers within docker container
    http://localhost:8888/api/v1.3/subcontainers/docker
### Example 2. To get information of a container within docker container
    http://localhost:8888/api/v1.3/subcontainers/docker/497cec18b8114c2ecdda1efb87f7795c594d7b431a59d5c775390426093b9631
    Containers’ name are available from the endpoint
    http://localhost:8888/api/v1.3/subcontainers or
    http://localhost:8888/api/v1.3/subcontainers/docker

Reference
https://github.com/google/cadvisor/blob/master/docs/api.md

## FAQ

