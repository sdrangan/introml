[Home](../sequence.md) - [GCP](./readme.md) - Getting started.

# Creating a GCP Instance with Python and Jupyter Notebook 

This note provides a step by step guide on setting up a 
[Google Cloud Platform (GCP)](https://cloud.google.com) 
virtual machine (VM) instance with most of the 
tools necessary for this class.  

Before starting you will need to create a GCP account, and 
a GCP project with billing enabled.  You may also redeem the GCP coupon 
provided by the professor.  Instructions on getting started in GCP
can be found [here](https://cloud.google.com/getting-started/).

## Creating the VM
1.	Open up the google developer console page: [Google API Console](https://console.developers.google.com/)
2.	Create new project by clicking on the "Project" drop-down. Provide a name and select the billing account.
3.	Navigate to the [Compute Engine page](https://console.cloud.google.com/compute) and select "Create Instance"
4.	Provide a name for your new instance and setup the following properties:
    *	Zone: one of the us-east options
    *	Machine type: minimize the specs for a lower rate.
    *	Boot disk: Ubuntu 16.04 LTS
    *	Firewall: Allow HTTP/HTTPS traffic checked.
    *   Hit "Create".  The VM will then take a short time to be created and will then appear in the list of VM
        instances.
5.  Reserve a Static IP Address
    *	Navigate to the [Google Cloud Networking page](https://console.cloud.google.com/networking/addresses/list)
    *   Change the IP type of your VM instance to static.


## Connect to your VM Instance

You can connect to your instance via browser through the 
[instance listing page](https://console.cloud.google.com/compute/instances).
Alternatively, you can connect from a third party SSH client which may have
more features.  We provide [instructions for using third party clients](./terminal.md).



## Jupyter Notebook Setup with Anaconda

In this class, we will use Python 3.  So, make sure you get the correct version.

1. SSH to the VM (see above)
2. Create a directory in your VM, say `~/Downloads`
3. Get the latest conda package: 
~~~bash
    wget  https://repo.continuum.io/archive/Anaconda3-4.4.0-Linux-x86_64.sh
~~~    
4. Run the script:  `bash ~/Downloads/Anaconda3-4.4.0-Linux-x86_64.sh`.
5. Follow instructions [https://www.continuum.io/downloads](https://www.continuum.io/downloads).
6. Close and re-open SSH
7. Update `conda`:
~~~bash
    conda update conda
    conda update anaconda
~~~    

## Jupyter Notebook with Pip
If you install Anaconda in the previous step, you can skip this step.  
But, if you wish to install with `pip3` instead of `anaconda`, do the following:
1.  Connect to your VM instance using SSH
2.  Install python 3 stuff:
~~~bash
    sudo apt install python3-pip
    pip3 install jupyter pandas numpy matplotlib
~~~

## Modify Jupyter installation for external access

Some of the commands below will need to be changed if you used `pip3` instead of 
`anaconda`.
1.  SSH into the VM
2.  [Optional] For security, you can add a password for access to Jupyter Notebook.
But, if you do not use this, the system will automatically use a token.  If you prefer
a password, generate a `sha1` hashed password:
~~~bash
    python3
    >>> from notebook.auth import passwd
    >>> passwd()
~~~
This will prompt you to enter a password and then will produce a long string like
`'sha1:e079...'`  Once this is diplayed, type `exit` to exit the `python` shell.

3.  Modify jupyter config file.  You can use any text editor.  The code below
assumes you use  `vi`, but you can use any editor of your choice like `nano`.
~~~bash
   jupyter notebook --generate-config
   vi .jupyter/jupyter_notebook_config.py
~~~
4.  You will now be viewing the `jupyter config` file.
Uncomment and modify existing lines, or add these new ones:
    * `c.NotebookApp.ip = '0.0.0.0'`
    * `c.NotebookApp.port = 8888 # or some other custom port`
    * `c.NotebookApp.password = u'sha1:sdasd...' # sha1 hash generated from previous step`
    * `c.NotebookApp.open_browser = False`
    
5. Start the jupyter notebook server as a background process:
~~~bash
    jupyter notebook &
~~~
The jupyter notebook will remain active as long as the SSH remains open.
Alternatively, in the previous step you can use `nohup jupyter notebook&`
and then jupyter notebook will remain open even if you close the SSH session.

## Open up the Firewall to Allow Outside Traffic
We need to modify the network settings to open up external access.

1.	Navigate to the Networking page on the Google Cloud console.
2.	Create a new firewall rule:
    * Source filter: Allow from any source.
    * Allowed protocols and ports: `tcp:80, 8888` (or whatever custom port you used before)
3.	You should now be able to access the remote jupyter notebook GUI through your local browser.
Just type your instance's external IP as the URL: `[IP_ADDRESS]:[PORT#]`

