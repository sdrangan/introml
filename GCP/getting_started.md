# Setting up a CPU and GPU Instances on GCP

This note provides a step by step guide on setting up a 
[Google Cloud Platform (GCP)](https://cloud.google.com) 
virtual machine (VM) instance with most of the 
tools necessary for this class.  GCP has made the process considerably
easier by using pre-built images with all the necessary software installed.

The note will cover creating both CPU and GPU isntances.\
Although most labs in this class can be performed
with a CPU instance, a GPU instance is highly recommended for the deep learning lab.
You may also wish to consider using GPUs for your project, particularly if you
are training a deep network with a large number of parameters.
Using these instances
can dramatically speed up training of deep networks
and are essential for large-scale
problems.  
Note that the per hour costs of GPU instances are much more expensive than
regular CPU instancess, so you want to make sure you turn off the instances
you are not using.  

## Requesting GPU quota
To use a GPU on GCP, you will need to first request GPU access.  For CPU instances,
you can skip this step.
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

## Creating the VM from a Google instance
The fastest way to get up and running is to use a pre-built image with all
the software installed.  The steps are as follows:
1.  Go to the [Google Deep Learning VM webpage](https://console.cloud.google.com/marketplace/details/click-to-deploy-images/deeplearning).
    Select "Launch on Compute Engine".  Select the project you want the VM associated with.    
2.  Select the parameters:
    * Deployment name:  Give this any name, say "tensorflow-gpu" or "tensorflow-cpu".
    * Zone:  If you are using a GPU,  you must select the same zone where you have the quota, say "us-east1-b".  Not all
    zones have GPUs.
    * Machine type:  2 vCPUs with 13 GB memory  
    * Check "Enable access to Jupyter Lab via URL"
    * Set Boot disk to 30 GB
    
    In addition, for GPU instances, select:
    * GPUs:  1 NVIDIA Tesla P100 
    * Check Install NVIDIA GPU driver
3.  Look at the price on the right.  It should be around 1.29 cents per hour
    in the us-east1-b zone for GPU instances.  So be very careful with using these machines!*	
4.  Select "Deploy".      The VM will now take several minutes to deploy.
5.  Optionally, reserve a Static IP Address
    *	Navigate to the [Google Cloud Networking page](https://console.cloud.google.com/networking/addresses/list)
    *   Change the IP type of your VM instance to static.
    *   If you don't reserve a static IP address, you will have to enter the
        dynamic IP address each time.
        


## Connect to your VM Instance

You can connect to your instance via browser through the 
[instance listing page](https://console.cloud.google.com/compute/instances).
Alternatively, you can connect from a third party SSH client which may have
more features.  We provide [instructions for using third party clients](./terminal.md).
        

## Modify Jupyter installation for external access

The Google VM instances come with Tensorflow and jupyter notebook pre-installed.
We just have to re-configure them for external access.
1.  SSH into the VM
2.  [Optional] For security, you can add a password for access to Jupyter Notebook.
But, if you do not use this, the system will automatically use a token.  If you prefer
a password, generate a `sha1` hashed password:
```bash
    python3
    >>> from notebook.auth import passwd
    >>> passwd()
```

This will prompt you to enter a password and then will produce a long string like
`'sha1:e079...'`  Once this is diplayed, type `exit` to exit the `python` shell.

3.  Modify jupyter config file.  You can use any text editor.  The code below
assumes you use  `vi`, but you can use any editor of your choice like `nano`.
```bash
   jupyter notebook --generate-config
   vi .jupyter/jupyter_notebook_config.py
```
4.  You will now be viewing the `jupyter config` file.
Uncomment and modify existing lines, or add these new ones:
    * `c.NotebookApp.ip = '0.0.0.0'`
    * `c.NotebookApp.port = 8888 # or some other custom port`
    * `c.NotebookApp.password = u'sha1:sdasd...' # sha1 hash generated from previous step`
    * `c.NotebookApp.open_browser = False`
    
5. Start the jupyter notebook server as a background process:
```bash
    jupyter notebook &
```
The jupyter notebook will remain active as long as the SSH remains open.
Alternatively, in the previous step you can use `nohup jupyter notebook&`
and then jupyter notebook will remain open even if you close the SSH session.

## Open up the Firewall to Allow Outside Traffic
We need to modify the network settings to open up external access.

1.	Navigate to the Networking page on the Google Cloud console.
2.	Create a new firewall rule:
    * Source filter: Allow from any source.
    * Allowed protocols and ports: `tcp:80, 8888` (or whatever custom port you used before)
    * Targets: All instances in the network. If you specify a target tag, your VM instance must have a matching network tag or the firewall rule will not apply.
3.	You should now be able to access the remote jupyter notebook GUI through your local browser.
Just type your instance's external IP as the URL: `[IP_ADDRESS]:[PORT#]`
