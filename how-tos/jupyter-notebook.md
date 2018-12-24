### Installing and Running Jupyter Notebook

It is possible that Jupyter Notebook is not installed by default on the AWS DLAMI image. Installation is easy. Once you SSH into the instance using a terminal or PuTTY install it for both python2 and python3 with the following commands:

<code>pip install ipykernel jupyter notebook</code>
<code>pip3 install ipykernel jupyter notebook</code>

The <code>ipykernel</code> package allows you to change between python2 and python3 kernels inside of jupyter notebook. To launch Jupyter Notebook type the following:

<code>jupyter notebook</code>

A URL with a token string will be displayed in the terminal. Copy (simply highlighting achieves this) and paste this URL and token into a browser window. If port forwarding is set up correctly (instruction for doing this in PuTTY are given in <code>PuTTY-login.md</code>) Jupyter Notebook running on the remote instance will load in your browser. 
