# Login into an AWS Instance and Launching Jupyter Notebook

## SSH into an Instance

If you are working on a Mac running OS X or a computer running Linux, login into your instance requires some shell commands. First, navigate to the directory were your copy of the key pair attached to the instance resides and change the permissions on the file.

<code>chmod 400 <AWS_key_name>.pem</code>

Then, SSH into the instance using its public DNS name. Here the instance is running Ubuntu so the username is ubuntu.

<code>ssh -i "<AWS_key_name>.pem" ubuntu@<public_DNS_name_prefix>.amazonaws.com</code>
  
## Connecting to an Instance with PuTTY

If you are working on a Windows computer download and install the SSH client called PuTTY.

https://www.putty.org

### Converting AWS Key

Next, you must convert the \*.pem key file associaed with your instance into a \*.ppk formate that PuTTY understands using PuTTYgen, a tool installed with PuTTY. Open PuTTYgen and select RSA as the type of key to generate. Then select load and navigate to your \*.pem file. You might have to change the file extension filter to show files with all extensions. Open your \*.pem file and save it as a \*.ppk file dismissing warnings about saving the key without a passphrase (or add a passphrase if you like but this makes the login process more cumbersome).

### Setting up PuTTY

With your converted key in hand, open PuTTY and open the Category > Sessions window. Enter your username and the instance's DNS name in the hosts box like follows. Here the instance is running Ubuntu so the username is ubuntu.

<code>ubuntu@<public_DNS_name_prefix>.amazonaws.com</code>

Select the radio button for <code>SSH</code> under <code>Connection type:</code> and ensure that the <code>Port</code> is set to 22. Navigate to the Category > Connection > SSH > Auth window and use the browse button under <code>Private key file for authorization</code> to find your \*.ppk file created above. 

Navigate to the Category > Connection > SSH > Tunnels window and set up port forwarding on port 8888 to allow Jupyter Notebook connections. In the <code>Source port</code> box enter 8888 and in the <code>Destination</code> box enter 127.0.0.1:8888 then click the <code>Add</code> button. 

To save the configuration for future use navigate back to Category > Sessions and enter a name in teh <code>Saved Sessions</coe> box and then click the <code>Save</code> button. When returning to PuTTY later you can select this saved session and <code>Load</code> it. Click the <code>Open</code> button to launch a connection with the instance. 
 

