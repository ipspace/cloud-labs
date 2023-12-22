# Deploy a Cloud-Based Web Server

In the third hands-on exercise, you'll deploy a single virtual machine running a web server. You could use a Windows or a Linux virtual machine; I recommend creating an Ubuntu VM.

Use the infrastructure-as-code tool you selected in the [previous exercise](EX2-Infrastructure-as-Code.md) to create the infrastructure and (optionally) provision the server.

!!! Tip
    You're highly encouraged to create some other combination of compute and storage infrastructure, in particular, if you can solve an actual problem you're facing... just keep it simple enough that you'll be able to complete it in a reasonable amount of time - there will be plenty of opportunities for more complex work.

## When Using AWS

* Create an SSH key pair.
* Deploy a virtual machine in the default VPC
* Create a public S3 bucket. Upload a picture (JPG or PNG file) of your choice into that bucket.
* Turn the S3 bucket into a static website.

**Notes:**

* You could use an automation tool module to find the VM image (AMI) ID or cheat and find it through GUI (start deploying a VM through GUI and write down the AMI ID).

## When Using Azure

* Deploy a virtual machine with a minimal set of options. Networking objects will be created automatically.
* Create an Azure storage account. Upload a picture of your choice.
* Turn the storage account into a static website.

**Notes:**

* While you could use any automation tool to get the job done, you probably won't need more than a simple **bash** script.

## Complete the Deployment

* Install and enable a web server (Apache or Nginx if you use Linux) on your VM.
* Add a static web page that references the picture in your cloud storage
* (Optional) Use server-side include to add **ifconfig** printout to the web page. You will need this (or similar) functionality when deploying web servers in multiple availability zones.

Try to use an automation tool to provision the web server, and if at all possible, use the dynamic inventory features of your tool to fetch the VM details from your cloud orchestration system.

## Wrap Up

To complete the exercise, commit your work and a short description of what you did (preferably in Markdown format) to your Git repository and push the changes to your hosted repository.
