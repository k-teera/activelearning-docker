# Lab 1 - Create image and push to github #
## Prerequisites ##
* Github Codespace
* Dockerfile
### Step 1.Create Personal Access Token ###
* Login to Github then click on Picture profile and navigate to Settings  
  ![lab1-1](https://github.com/k-teera/activelearning-docker/blob/main/images/lab1-1.png "lab1-1")  
* On the right menu, scroll down and select Developer Settings  
  ![lab1-2](https://github.com/k-teera/activelearning-docker/blob/main/images/lab1-2.png "lab1-2")  
* Click on Personal access tokens > Tokens (classic)  
  ![lab1-3](https://github.com/k-teera/activelearning-docker/blob/main/images/lab1-3.png "lab1-3")  
* Generate new token (classic)  
  ![lab1-4](https://github.com/k-teera/activelearning-docker/blob/main/images/lab1-4.png "lab1-4")  
* Set Permission  
  ![lab1-5](https://github.com/k-teera/activelearning-docker/blob/main/images/lab1-5.png "lab1-5")  
* Personal access tokens  
  ![lab1-6](https://github.com/k-teera/activelearning-docker/blob/main/images/lab1-6.png "lab1-6")  

### Step 2.Create Image ###
* Create repository dockerimage-ghcr with readme file  
  ![lab1-7](https://github.com/k-teera/activelearning-docker/blob/main/images/lab1-7.png "lab1-7")  
* Create Codespace and open with VS Code on local  
  ![lab1-8](https://github.com/k-teera/activelearning-docker/blob/main/images/lab1-8.png "lab1-8")  
* Create entrypoint.sh  
```
#!/bin/sh  
echo "Hello from Entrypoint!"  
```  
* Create Dockerfile
```
# Use the officeial image as a base image
FROM alpine:latest

RUN apk add --no-cache bash

# Set the working directory inside the container
WORKDIR /app

# Copy the shell script into the container
COPY entrypoint.sh .

# Make the sheel script executable
RUN chmod +x entrypoint.sh

# Set the shell script as the entry point
ENTRYPOINT [ "/app/entrypoint.sh" ]
```
