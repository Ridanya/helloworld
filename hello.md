<h3>container</h3>- <p>the one where you put your workload and run it in a server. it is very portable .it  contains code with all its dependencies.
any application with its dependencies can be bundled up into a single image and then can be distributed.
anyone can download the image and deploy with their infrastruture with minimal setup</p>

<h3>Image</h3>-A package containing info to create a container.

<h3>dockerfile</h3>-text file with instructions 

<p>dockerfile >build a docker image > create a docker container</p>

<ul>
<li>A container registry is a  repository where container images are stored, managed, and distributed.</li>

<li>A container registry allows users to store and share container images with others in a controlled and secure way. Users can push container images to a registry and then pull them when needed to deploy applications on different platforms or environments.</li>
<ul>

<h2>quay</h2>

<p>Red Hat Quay is a container registry solution that enables users to store, manage, and deploy container images. </p>
<dl>
<dt>some command used to build and push images to registry</dt>

<dd>build -t hello .
 to build a image named hello with the instructions given from the dockerfile.</dd>

<dd>run -it hello 
to run the image</dd>
</dl>
**before pushing the image to registry ,tag the image using tag** 
 'tag hello registry.ford.com/rkathir3/hello     ---cdsid/imagename'
**then push the image using push** 
 'push registry.ford.com/rkathir3/hello'

<h3>podman images</h3>
  <p>to list the images available</p>

*you need to do podman login before pushing image*
*go to registry.ford.com after login at top you will find account settings click on that and then click on generate encrypted passsowrd provide lap password . *