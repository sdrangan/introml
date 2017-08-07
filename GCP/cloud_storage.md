[Home](../sequence.md) - [GCP](./readme.md) - Cloud storage.

# Using Google Cloud Storage

[Google cloud storage](https://cloud.google.com/storage/) provides
a flexible and low cost storage option for virtual machines.
Using Google cloud storage will allow you to maintain files
in a common location that can be accessed from all your machine.  You 
may also transfer data into and out of the cloud storage 
to your personal machine.  Importantly, cloud storage is elastic in that
it can be scaled to your needs.  

In this file, we describe how to:
* Create a bucket in Google cloud storage
* Connect your VM instance to the bucket.

## Create the bucket

A [bucket](https://cloud.google.com/storage/docs/key-terms#buckets)
is the basic container in Google Cloud storage.  We first need
to create the bucket.

1. Log in to the Cloud Developers Console, and go to Storage->Storage.
2. This will prompt you to “Create” a new bucket
    * For the name, I selected “introml-bucket”
    * Select “Regional”
    * Make sure region matches the region for your VM instance
3. Optionally, you create “folders” within the bucket and load data into the bucket. 

## Enable Storage Access in your VM

By default, VMs are generally created with read only access to 
Google cloud storage. To enable full access, you will need to modify
the properties of your VM as follows:

1.	Go to Compute Engine -> VM instances.  A list of your VMs should appear
2.	Click on the name of the VM that you wish to mount the bucket in.  This will take you to a page “VM instance details”.  The VM you are interested in should not be running.
3.	Select “Edit” from the top menu
4.	Under “Cloud API access scopes” select “Select Access for each API”.  Within that menu select Full for Storage.
5.	Hit Save.
6.	Return to the main VM page

## Mount the Bucket in your VM

Finally, we need to mount the bucket in your VM with the tool [gcs-fuse.](https://cloud.google.com/storage/docs/gcs-fuse).

1.	Start the VM and SSH into the VM
2.	Follow the instructions on the [gcs-fuse page](https://cloud.google.com/storage/docs/gcs-fuse) 
for setting up gcs-fuse on your VM.

You should now be able to see the bucket files.


