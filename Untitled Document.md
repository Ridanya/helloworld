#### Container 
The one where you put your workload and run it in a server. 
It is very portable .
It  contains code with all its dependencies.
Any application with its dependencies can be bundled up into a single image and then can be distributed.
Anyone can download the image and deploy with their infrastruture with minimal setup<

#### Image
A package containing info to create a container.
#### Dockerfile
Text file with instructions 
*dockerfile >build a docker image > create a docker container*

- A container registry is a  repository where container images are stored, managed, and distributed.

- A container registry allows users to store and share container images with others in a controlled and secure way. Users can push container images to a registry and then pull them when needed to deploy applications on different platforms or environments.


### Quay

Red Hat Quay is a container registry solution that enables users to store, manage, and deploy container images. 

Some command used to build and push images to registry

: **build -t hello**
   to build a image named hello with the instructions given from the dockerfile.</dd>

: **run -it hello** 
to run the image</dd>

**before pushing the image to registry ,tag the image using tag** 
 'tag hello registry.ford.com/rkathir3/hello     ---cdsid/imagename'
**then push the image using push** 
 'push registry.ford.com/rkathir3/hello'

#### Podman images
  To list the images available

*you need to do podman login before pushing image*
*go to registry.ford.com after login at top you will find account settings click on that and then click on generate encrypted passsowrd provide lap password . *