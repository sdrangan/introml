[Home](../sequence.md) - [GCP](./readme.md) - Using docker

# Using GCP with Docker 

Instead of creating a VM and installing all the requisite software
manually, you can run all the software in this class on a pre-configured
[Docker](https://docs.docker.com) image.  This may simplify the process of
getting started at the cost of not being able to customize your software.

The Docker website has an excellent
[tutorial](https://docs.docker.com/get-started/).  For this class, we will use
one of Google's pre-made Docker images that includes installations of python
and Tensorflow.  We create a Docker container from this image on your VM
and then run the software on top of that container.

* Create a VM using following the instructions in the [GCP set-up page](./getting_started.md).
The only change is that instead of using the `Ubuntu 16.04 LTS` boot disk, select the
one with a name like `Container-Optimized OS 60-9592.82.0 stable`.  
This is a special boot disk that Google has created with Docker installed.

* SSH into the VM
* When using `docker`, we need to create a
[Docker volume](https://docs.docker.com/engine/admin/volumes/volumes/) and *bind mount*
the volume to the host VM.  In this way, we will be able to share files between
the Docker container and the host VM.  As a first step, we create a directory in the host VM
that will be bind mounted.  In this example, we will create a directory
~~~
   mkdir ~/dockermnt
~~~
* Any files that we want the Docker container to access can then be copied to 
the directory created in the previous step.  For example,
to use the instructional files in this repo:
~~~
   cd ~/dockermnt
   git clone https://github.com/sdrangan/introml.git
~~~
* Next, the following command will download the docker image, create the container
in the VM and run the pre-defined jupyter notebook application:
~~~
    docker run -it -v ~/dockermnt:/notebooks -p 8888:8888 gcr.io/tensorflow/tensorflow:latest-py3
~~~
Here, the `-v` option mounts the `/notebooks` volume in the Docker container to the
`dockermnt` directory in the host VM.  The `-p` option binds the ports so that
you can use Jupyter notebook.  Finally the image `gcr.io/...` is the name of 
the Google image that includes Python 3 and Tensorflow.
The first time you run this command, it will download a number of files 
which may take a few minutes.
* Once the `docker run` has downloaded the files you will get a message like:
~~~
 
    Copy/paste this URL into your browser when you connect for the first time,
    to login with a token:
        http://localhost:8888/?token=ec6e86341844dc7b9e24efb123a1a183fdc8fa009f281614
~~~
In your local machine's browser, enter the URL `[IP]:8888` where `[IP]` is the
VM's external IP address.  The external IP address is listed on the Google console 
image page.You will then be prompted for a token.  Enter the value
from the message in the previous step, `ec6...14`.

* You should now see the Jupyter notebook open in your browser with access to all the files
in the directory `dockermnt`.



