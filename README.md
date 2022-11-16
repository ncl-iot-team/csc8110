# CSC8110/CSC8634 Cloud Computing – Assessment 1

This repository contains essential materials and references for the practicals of CSC8110 Cloud Computing module. Please read https://docs.docker.com/engine/docker-overview/ before doing the exercises.

## Pre-Requisites

1. SSH client (Remote command line) and/or [X2go client](https://wiki.x2go.org/doku.php) (Remote GUI)

2. Access Azure lab
    * Go to [Azure lab](https://labs.azure.com/), login with your student account
    * Turn on the virual machine. Set the password if requested
    * Click the icon next to the VM power button

3. Setup remote connection (Choose either one)
    * A. Remote connection via SSH
      * You can use any SSH clients. E.g. WSL, Putty, etc.
      * Copy the SSH command. This is different per account
      * Copy this to your terminal and you will access the VM
      * ![image](https://user-images.githubusercontent.com/7325740/193309309-facb4716-14e6-4130-ad97-fe5ac3c4b396.png)
    * B. Remote connenction via X2Go
      * Do the same step as 3A
      * Open X2go and create a new session
      * Fill out the information as required
      * In the session type, choose MATE
      * Login with the username "student" and the password that you have set
      * ![image](https://user-images.githubusercontent.com/7325740/193328954-7f08ab1a-9dbf-4543-a2d0-a4fd70b535a2.png)

4. Explanation References
   * Container Introduction <https://www.youtube.com/watch?v=EnJ7qX9fkcU>

## Task 1: Deploy a web application component in Docker Environment

1. Tutorial Video

	Task1 Cloud Computing Coursework https://bit.ly/3nR14sy

2. Additional Hints

	It is a basic docker job which has to be performed using Command line (Refer https://docs.docker.com/get-started/part2/#run-the-app)

## Task 2: Deploy a complex web application stack in Docker Environment

1. Tutorial Video

	Task2 Introduction to Docker Swarm https://bit.ly/3lBvuwh
2. Explanation References
	* Docker Swarm Intro 
		
		https://www.youtube.com/watch?v=Tm0Q5zr3FL4
		Refer https://docs.docker.com/engine/swarm/ for basic concepts
	* Docker Engine SDK and API

		Docker provides an API for interacting with the Docker daemon (called the Docker Engine API), as well as SDKs for Go and Python. There are unofficial libraries for other programming languages. If you choose to use Java as your programming language, you may use https://github.com/spotify/docker-client. Unofficial libraries don't come with all the features. Some provide control over basic docker engine features only.

		The SDKs allow you to build and scale Docker apps and solutions quickly and easily. If Go or Python won’t work for you, you can use the Docker Engine API directly.

		The Docker Engine API is a RESTful API accessed by an HTTP client such as wget or curl, or the HTTP library which is part of most modern programming languages.

		Refer https://docs.docker.com/develop/sdk/

		Python SDK Reference : https://docker-py.readthedocs.io/en/stable/
	
	* Mongo Database
		* Official Website
		https://www.mongodb.com
		* Docker QuickStart
		https://hub.docker.com/_/mongo

	* Google cAdvisor Remote REST API Reference
		* Pattern of API endpoint
			```
			http://<hostname>:<port>/api/<version>/<request>
			```
		
			The current version of the API is v1.3 and there is a beta release of the v2.0 API
		
    		Supported request types: &quot;containers,docker,events,machine,subcontainers&quot;
		
    		Example: 
			```
			http://localhost:8888/api/v1.3/containers
			```
    	
			The result is returned in JSON format.
		
		* To get information of all sub containers 
		
			```
			http://localhost:8888/api/v1.3/subcontainers/
			```
		
		* To get information of a specific sub container 
		
			```
			http://localhost:8888/api/v1.3/subcontainers/<subcontainername>
			```
		
			Refer https://github.com/google/cadvisor/blob/master/docs/api.md

	* Docker Swarm Visualizer

		Refer: https://github.com/dockersamples/docker-swarm-visualizer

3. Additional Hints

	Refer the docker-compose.yml file in https://docs.docker.com/get-started/part5/#add-a-new-service-and-redeploy 

## Task 3: Build your own Docker image and push it to the Docker Hub

1. Tutorial Video

	Task3 Docker Build Toturial <https://bit.ly/3CEas6E>

2. Additional Hints
	
	You can download the source code of the provided Java program in this link https://github.com/ncl-iot-team/cadvisor-scraper

	Before you push the new built docker image to the remote Docker Hub repository, please don't forget to login with your Docker Hub account in command link interface, and tag your built image with "&lt;your username&gt;/&lt;image name&gt;". 

## Task 4: Fully deploy and run the complex web application stack and undertake performance benchmarking activities

1. Tutorial Video

	Task4 Introduction to cAdvisor https://bit.ly/3x47sR3

2. Additional Hints

	When you plan to verify the container statistics recorded in the MongoDB instance, you can try to deploy a mongodb express service, refer https://github.com/mongo-express/mongo-express which can be deployed in Docker environment, ref https://hub.docker.com/_/mongo-express/
	
## Task 5: Deploy Kubernetes using Terraform and deploy a microservice

1. Enable Azure for student subscription

	Go to https://azure.microsoft.com/en-us/free/students/ and login with your school account
	
	You will need to provide a phone number and an address
	
	⚠⚠⚠Warning: This adds $100 USD in your account for your coursework. Do not use it all as we cannot give you extra!⚠⚠⚠

2. Cleaning up after finishing your work

	⚠⚠⚠Make sure you clean up any resources you have created when you are not working on your assigment!⚠⚠⚠
	
	![image](https://user-images.githubusercontent.com/7325740/202251275-12707144-8293-4420-b74f-44ececd3cb03.png)

	When deleting resources, ensure the check box for Azure for students is checked
	
	You can delete most resources with `terraform destroy`. Afterwards, go to "All resources" in your Azure portal and ensure there's nothing there
	
	![image](https://user-images.githubusercontent.com/7325740/202251584-be3a98a9-41ac-422e-a13a-ce0cd38290bc.png)
	
	![image](https://user-images.githubusercontent.com/7325740/202251643-c93d3685-42cd-4e26-900a-b0f6b75e6a4d.png)
	
	Delete any resource groups you may have in your account.
	
3. Additional hints

	You will need 3 tools for this task
	
	* Azure CLI https://docs.microsoft.com/en-us/cli/azure/install-azure-cli
	* kubectl https://kubernetes.io/docs/tasks/tools/install-kubectl/
	* terraform CLI https://www.terraform.io/downloads.html

	When you are creating the service principal for terraform, if you are having problems relating to idenfiferUrls not being verified, name your principal with a prefix `api://`
