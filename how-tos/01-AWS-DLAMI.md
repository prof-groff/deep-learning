# Deep Learning in the Cloud - Part 1

## AWS DLAMI (Deep Learning Amazon Machine Image) - Set Up Instructions

### 1) Create an AWS Account

Go to https://aws.amazon.com to sign up. This account can be linked with an existing Amazon account.

### 2) Optional: Join AWS Educate

Go to https://aws.amazon.com/education/awseducate to sign up for an educator account to earn free credits to apply to your AWS account. During the application process you must specify a class you plan to use AWS in. If you don’t have a specific class in mind, then pick a class for which you could explore the use of AWS. Once your application is approved you will get an email with a promo code that you can enter into your AWS billing console for a $40 credit. Note that the email address you use to sign up for AWS Educate must be your official school email address, but you can use a different email address with AWS. 

### 3) Request Use of a GPU

Log into Amazon Web Services at https://aws.amazon.com and navigate to Services > Compute > EC2 > Limits and request an increase in instance limits to allow you to use an instance with a GPU attached to it. Two recommended instance classes are g3.4xlarge (currently $1.1/hr) or p3.2xlarge (much more powerful GPU but $3/hr). It may take a day for your request to be approved.

### 4) Create a New Instance

Log into AWS at https://aws.amazon.com and navigate to Services > Compute > EC2 and click on the Launch Instance button. Select the AMS Marketplace option and search for Deep Learning AMI (or DLAMI). Select one of the precompiled images, which include common deep learning toolset such as NVIDIA CUDA, cuDNN, python, TensorFlow, Keras, etc. I use the Deep Learning AMI (Ubuntu) image. As you progress through the image creation process there are many options. The defaults are mostly okay. But, when you are selecting the instance type make sure to select the type requested above. Also, if you plan to use Jupyter Notebook with your instance you will need to add the following networking rule to make this possible:

type: Custom TCP Rule
protocol: TCP
port range: 8888
source: Anywhere 0.0.0.0/0, ::/0

When you launch your instance you will be instructed to either launch the instance with an existing key pair or to create a new key pair if you do not already have one. This key pair is necessary to allow you to SSH into your instance once it is running. Don't lose your copy. Once your instance is created you can start and stop it at Services > Computer > EC2 > Instances. Make sure you stop the instance when it is not in use or you will continue to be billed for its resource consumption. 

