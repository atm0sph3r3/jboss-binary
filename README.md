# Creating a Docker image and pushing to OS registry
1. Create a Docker file (Dockerfile in repo)
2. Tag the Docker image 
```
docker tag <image> <ip:port/namespace/image-name>
```
3. Get the OS user token
```
oc whoami -t
```
4. Login to the remote Docker registry
```
docker login -u <username> -e <any email> -p <token from above> <docker registry ip:port>
```
5. Create a new image stream to match the uploaded image
```
oc create -f imagestream.json -n openshift
```
6. Push the image to the Docker registry
```
docker push <tagged image>
```
