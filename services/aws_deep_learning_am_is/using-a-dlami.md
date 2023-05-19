---
id: Using a DLAMI
title: Using a DLAMI
created: 1683841041000
updated: 1683841041000
---
# Using a DLAMI

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-deep-learning-amis.git)
{% endhint %}

## Conda DLAMI

- **Note**  
We no longer include the CNTK, Caffe, Caffe2, Theano, Chainer, and Keras Conda environments in the AWS Deep Learning AMI starting with the v28 release\. Previous releases of the AWS Deep Learning AMI that contain these environments will continue to be available\. However, we will only provide updates to these environments if there are security fixes published by the open source community for these frameworks\.
- **Note**  
When you launch your first Conda environment, please be patient while it loads\. The Deep Learning AMI with Conda automatically installs the most optimized version of the framework for your EC2 instance upon the framework's first activation\. You should not expect subsequent delays\.


## Jupyter Notebooks

- **Important**  
To run the Jupyter notebook tutorials installed on the DLAMI, you will need to [Set up a Jupyter Notebook Server](setup-jupyter.md)\.
- **Note**  
Many tutorials require additional Python modules that may not be set up on your DLAMI\. If you get an error like `"xyz module not found"`, log in to the DLAMI, activate the environment as described above, then install the necessary modules\.
- **Tip**  
Deep learning tutorials and examples often rely on one or more GPUs\. If your instance type doesn't have a GPU, you may need to change some of the example's code to get it to run\.
- **Tip**  
If you're concerned about which version of CUDA is active, one way to see it is in the MOTD when you first log in to the DLAMI\.
- **Tip**  
Switching between frameworks can be fun and educational, however you can run out of memory\. If you start running into errors, look at the terminal window that has the Jupyter server running\. There are helpful messages and error logging here, and you may see an out\-of\-memory error\. To fix this, you can go to the home page of your Jupyter server, click the **Running** tab, then click **Shutdown** for each of the tutorials that are probably still running in the background and eating up all of your memory\.

