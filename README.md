# Docker setup
NGINX running as webserver with non root privilege in a docker container that serves a simple page containing the container's hostname, IP address and port.

## Prerequisites

1. Install Docker using the necessary package for your OS:
   
   ```https://docs.docker.com/get-docker/```

2. Clone demo repo
   
   ```git clone git@github.com:supernova-github/docker-demo.git```

## Steps to create Docker image and running it on local

1. Build docker image using the following command -
   
   ```docker build -t abhishekjaindevops/docker-demo .```

2. Once image is built we can use the below command to check it -
   
   ```docker images```

3. We can push this image to Dockerhub, inorder to do that we need to first login to Dockerhub using the following -
   
   ```docker login```

   Then run push command 
    
   ```docker push abhishekjaindevops/docker-demo```

4. Now in order to run the docker container on local we need to run the following -
    
   ```docker run -p 8080:8080 -d abhishekjaindevops/docker-demo```

   To start a container in detached mode, we use ```-d```

   To expose a container’s internal we start the container with the ```-p``` flag

5. Now we can use the ps command to see the running containers
   
   ```docker ps```

   if we want to see all containers(including exited) we can use ```-a``` flag

   It will show the results like this

   ```CONTAINER ID   IMAGE                            COMMAND                  CREATED      STATUS      PORTS                            NAMES
   aedd4e97850e   abhishekjaindevops/docker-demo   "/docker-entrypoint.…"   6 days ago   Up 6 days   80/tcp, 0.0.0.0:8080->8080/tcp   dreamy_mayer```

6. Now we can get the ip and port on which container is running and open the in a browser.

<img width="1477" alt="Screenshot 2022-07-18 at 1 07 40 PM" src="https://user-images.githubusercontent.com/102737937/179466618-9c35d404-206f-4273-bab1-693b85c3f2b1.png">
7. connect to the cluster by running command : kubectl confog use-context k3d-cluster
8. cd deploy/chart 
9. helm install nodeserver . -n <namespace>


   
