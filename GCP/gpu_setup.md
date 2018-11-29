# Setting up a GPU Instance on GCP

Google Cloud Platform (GCP) has powerful instances with
[GPU support](https://cloud.google.com/gpu/).  Using these instances
can dramatically speed up training of deep networks
and are essential for large-scale
problems.  All the exercises in this class can be done without a GPU.
However, for the lab in deep learning, you can use one to get better results
with less computation time.  
You may also wish to consider using GPUs for your project, particularly if you
are training a deep network with a large number of parameters.

Note that the per hour costs of GPU instances are much more expensive than
regular CPU instancess, so you want to make sure you turn off the instances
you are not using.  

We walk you through a step-by-step guide in creating a GPU instance
on GCP with Tensorflow.

## Requesting GPU quota
To use a GPU on GCP, you will need to first request GPU access.
1.  Go to the [IAM & admin page](https://console.cloud.google.com/projectselector/iam-admin)
2.  Select the project you are using or create a new one.
3.  Select "Quotas" on the left menu.
4.  There are a large number of quotas that can be edited.  To find
    the correct quota, select on the top of the page:
    *   Service:  "Compute Engine API"
    *   Metric:  "NVIDIA P100 GPUs"
5.  You will now see a list of metrics, one for each zone. Select the zone that is
    best for you.  NYU students should select "us-east1".  
6.  After you have selected the item, select "Edit Quotas" at the top of the page.
    You will be prompted to answer some questions on why you need the GPUs.
    Request at least one more GPU.
7.  You should hear from them quite fast (sometimes even within the same day!) 

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
        * Select 1 or more NVIDIA P100 GPUs
    * Look at the price on the right.  It should be around 1.20 cents per hour.  
      So be very careful with using these machines!
    *	Boot disk: Ubuntu 16.04 LTS with 30 GB boot disk space.   Do not use later versions of Ubuntu,
        as the Nvidia drivers are not always available.
    *	Firewall: Allow HTTP/HTTPS traffic checked.
    *   Hit "Create".  The VM will then take a short time to be created and will then appear in the list of VM
        instances.        
5.  Optionally, reserve a Static IP Address
    *	Navigate to the [Google Cloud Networking page](https://console.cloud.google.com/networking/addresses/list)
    *   Change the IP type of your VM instance to static.
    *   If you don't reserve a static IP address, you will have to enter the
        dynamic IP address each time.
        

## Install the Nvidia Driver

Most of the instructions are now available on
[Tensorflow installation page](https://www.tensorflow.org/install/install_linux).
This note will cover some of the details they don't say.

First, we install CUDA Toolkit 9.0 following the instructions on the 
[NVIDIA webpage](https://docs.nvidia.com/cuda/cuda-installation-guide-linux/).

* In step 2.6, when downloading the Nvidia driver,
  you will need to use the Toolkit 9.0, not 9.2.
  This is a legacy release, so you will need to go to
  [Nvidia archive page](https://developer.nvidia.com/cuda-toolkit-archive).
  At the current time, Tensorflow is not compatible with versions later that 9.0.
* Select CUDA Toolkit 9.0
    * Select architecture: x86_64
    * Ubuntu 16.04
    * Installer type:  deb (local)
* The file is large (1.2 GB) and can take a long time to download.  

## Install cuDNN

Follow the instructions on [NVIDIA cuDNN installation page](https://docs.nvidia.com/deeplearning/sdk/cudnn-install/).

* In Step 2.2, when you download select "cuDNN v7.1.4 for CUDA 9.0",
    * You will need to get all three files: 
    "Runtime library", "Developer library" and "Code Samples for Ubuntu16.04 (Deb)".

  
## Install Tensorflow

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

