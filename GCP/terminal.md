[Home](../sequence.md) - [GCP](./readme.md) - Third party terminal.

# Using a Third Party SSH / SCP client to connect to your VM

## Finding the SSH Client for You

You can connect to your instance via browser through the 
[instance listing page](https://console.cloud.google.com/compute/instances).
Alternatively, you can connect from a third party SSH client.
The third party clients may support other features such as integrated SCP and 
having built-in editors.
There are a large number
of SSH clients available for Windows and MAC.  For Windows machines,
there is a very good 
[list](https://www.htpcbeginner.com/best-ssh-clients-windows-putty-alternatives/2/),
and a similar [list for MACs](https://beebom.com/putty-for-mac-free-alternative-ssh-clients/).
What you select is a matter of taste.

## Setting up SSH keys

The only tricky part of using a third party SSH client is generating and using the SSH keys.
There are detailed [instructions](https://cloud.google.com/compute/docs/instances/connecting-to-instance)
on the GCP site.  But, these are a little confusing.  So, I have provided a 
short summary of the main steps.

First you need to generate a key on your local machine.  If you are on Windows,
you can do the following with `puttygen.exe`.  Similar programs are available on Mac or linux.
* Download [puttygen.exe](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html)
* Run `puttygen` and select "Generate"
* You will be asked to create some randomness.  After moving around your mouse, a key will be generated.
* Then fill out the following:
    * In "Key comment", put your username
    * In "passphrase", put a password of your choice
* Select "Save public key" and put the file somewhere, say "gcp_key.pub"
* Select "Save private key" and put the file somewhere, say "gcp_key.ppk"
* Keep the puttygen window open
On a MAC or Linux machine, you can use the command `ssh-keygen` from the terminal.  

Next, we open the Google Cloud Console.  In the Console on your browser, we will apply
the key information for all instances in the project.
* Got to Compute Engine -> Metadata
* Select the "SSH Keys" tab
* Select "Edit"
* Select "add item"
* Copy all the text in the puttygen window under the name
"Public key for pasting into OpenSSH authorized_key file".  Paste this text into the console window
where it says "Enter entire key data".  This will be a long string like
~~~
ssh-rsa AAAAB3N...2eGL86jtvPAtrNpH1KcP+LO+9Wx8RQ== <username>
~~~
It begins with `ssh-rsa` and ends with your username.  
* Select save

Finally, you need to provide your SSH or SCP client on your local machine with the `gcp_key.ppk` file.
This will depend on the SSH client.  


