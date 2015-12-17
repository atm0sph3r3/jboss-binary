## Creating a Docker image and pushing to OS registry
1. Create a Docker file (Dockerfile in repo)
2. Tag the Docker image 

        docker tag <image> <ip:port/namespace/image-name>
3. Get the OS user token

        oc whoami -t
4. Login to the remote Docker registry
       
        docker login -u <username> -e <any email> -p <token from above> <docker registry ip:port>
5. Create a new image stream to match the uploaded image

        oc create -f imagestream.json -n openshift
6. Push the image to the Docker registry

        docker push <tagged image>

## Creating the new app
1. Create the project

        oc new-project <project name> [--display-name=<display name>]
2. Create a new app based on image from OS registry

        oc new-app <image name>~<github repo> --strategy=source
Note that this is assuming that the build will be completed using .sti/bin/assemble and .sti/environment files.
        
        
