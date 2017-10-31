# Setting up a GPU Instance on GCP

Google Cloud Platform (GCP) has powerful instances with
[GPU support](https://cloud.google.com/gpu/).  Using these instances
can dramatically speed up training of deep networks
and are essential for large-scale
problems.  We will not need to use a GPU for any exercises in this class,
but you may wish to consider them for your project, particularly if you
are training a deep network with a large number of parameters.
The per hour costs of GPU instances are much more expensive than
regular CPU instancess, so you want to make sure you turn off the instances
you are not using.  

We walk you through a step-by-step guide in creating a GPU instance
on GCP with Tensorflow.

## Requesting GPU quota
To use a GPU on GCP, you will need to first request GPU access.
1.  Go to the [IAM & admin page](https://console.cloud.google.com/projectselector/iam-admin)
2.  Select the project you are using or create a new one.
3.  Select "Quotas" on the left menu.
4.  Scroll down the list and you will find an entry "Google Compute Engine API"
    for the zone that is best for you.  You want to select one NVIDIA K80 GPUs.
5.  After you have selected the item, select "Edit Quotas" at the top of the page.
    You will be prompted to answer some questions on why you need the GPUs.
    Request at least one more GPU.
6.  You should hear from them quite fast (sometimes even within the same day!) 

## Creating the VM with a GPU
1.	Open up the google developer console page: [Google API Console](https://console.developers.google.com/)
2.	Create new project by clicking on the "Project" drop-down. Provide a name and select the billing account.
3.	Navigate to the [Compute Engine page](https://console.cloud.google.com/compute) and select "Create Instance"
4.	Provide a name for your new instance and setup the following properties:
    *	Zone: Not all zones support GPUs, so you will need to select one that does.  
        For example, the zone `us-east1=d` supports GPUs.
    *	Machine type:   Select `Customize` so that more options appear.  Then select:
        * Select 2 vCPUs or more
        * Select 12 GB or more
        * Select 1 or more NVIDIA Tesla K80 GPUs
    * Look at the price on the right.  It should be around 79 cents per hour.  
      So be very careful with using these machines!
    *	Boot disk: Ubuntu 16.04 LTS with 30 GB boot disk space
    *	Firewall: Allow HTTP/HTTPS traffic checked.
    *   Hit "Create".  The VM will then take a short time to be created and will then appear in the list of VM
        instances.        
5.  Optionally, reserve a Static IP Address
    *	Navigate to the [Google Cloud Networking page](https://console.cloud.google.com/networking/addresses/list)
    *   Change the IP type of your VM instance to static.
    *   If you don't reserve a static IP address, you will have to enter the
        dynamic IP address each time.
        

## Install the Nvidia Driver

First, perform steps 1 and 2 of the Nvidia driver installation instructions
on the 
[NVIDIA webpage](https://www.nvidia.com/en-us/data-center/gpu-accelerated-applications/tensorflow/).

* In step 2, when downloading the Nvidia driver,
  you will need to use the Toolkit 8.0, not 9.0.
  This is a legacy release, so you will need to go to
  [Nvidia archive page](https://developer.nvidia.com/cuda-toolkit-archive).
  At the current time, Tensorflow is not compatible with Toolkit 9.0.
* Select CUDA Toolkit 8.0 - GA2
    * Select architecture: x86_64
    * Ubuntu 16.04, deb (local)
* The file is large (1.8 GB) and can take a long time to download.  

## Install cuDNN
Next follow Steps 3 and 4 of 
the 
[NVIDIA installation webpage](https://www.nvidia.com/en-us/data-center/gpu-accelerated-applications/tensorflow/).

* Select cuDNN for CUDA 8.0 v6.0 (There are more recent releases,
  but I am not sure if they work with Tensorflow)

## Install Tensorflow with Anaconda

  
## Install Tensorflow0

For GPU support, it is easier to use pip3 instead of Anaconda.
I am still seeing if you can install over Anaconda.
* First install python3:
~~~bash
>> sudo apt-get install python3-pip python3-dev
~~~

* Next install Tensorflow.
Since the above installation does not come with the package setuptools, you
will need to install tensorflow from the binary:
~~~bash
>> sudo pip3 install --upgrade https://storage.googleapis.com/tensorflow/linux/gpu/te
nsorflow_gpu-1.3.0-cp35-cp35m-linux_x86_64.whl
~~~
More details are in the [Tensorflow page](https://www.tensorflow.org/install/install_linux).


## Jupyter Notebook

* Since you used `pip3` installation above, and not Anaconda,
you will need to install jupyter notebook and the other common python
packages manually:
~~~bash
>> pip3 install --upgrade pip
>> pip3 install jupyter pandas matplotlib sklearn
~~~
See the [Jupyter installation page](http://jupyter.readthedocs.io/en/latest/install.html)
for more details.
* Follow the instructions in [Creating a VM instance](./getting_started.md)
to "Modify Jupyter notebook for external access" and
"open up the firewall to allow outside traffic".

