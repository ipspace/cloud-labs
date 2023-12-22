# Deploy a Virtual Network Infrastructure

In the [previous hands-on exercise](EX3-Deploy-Web-Server.md), you deployed a virtual machine into a default VPC (AWS)
or used auto-created networking objects to simplify your deployment (Azure). In this exercise, you'll create a full-blown custom networking infrastructure using the infrastructure-as-code tool of your choice.

!!! Tip
    You're highly encouraged to create networking infrastructure relevant to an actual problem you're facing, as long as it includes most of the components you're expected to use and is simple enough to be completed in a reasonable amount of time.

## When Using AWS

* Create a VPC and two subnets (public and private).
* Create an Internet Gateway and associate it with the VPC
* Create a route table for the public subnet and add a default route pointing to the Internet gateway
* Adjust the default security group to allow HTTP, HTTPS, and SSH access to all virtual machines. Use GUI if necessary.

**Optional:**

* Create an elastic IP address and an elastic network interface.

## When Using Azure

* Create a VNet and two subnets (public and private).
* Create a route table that prevents Internet access from virtual machines in the private subnet
* Use **open_ports** parameter of **azure\_rm\_virtualmachine** Ansible module (or equivalent CLI/Terraform parameter) to enable HTTP, HTTPS, and SSH access to all VM instances

**Optional:**

* Create public IP addresses and VM NICs for virtual machines in the public subnet

## Complete the deployment

* Deploy a web server in the public subnet (use the tools you created in the previous exercise to deploy it).
* Deploy an SSH jump host in the public subnet.
* Deploy another VM instance in the private subnet.

## Connectivity tests

**Verify that:**

* You can open an SSH session to the web server and jump host from the Internet;
* You can download a web page from the web server;
* Jump host can open an SSH session to a VM instance in the private subnet;
* The VM instance in the private subnet cannot reach destinations outside of your virtual network.

**Optional:**

* Write an automated test suite (for example, an Ansible playbook).

!!! Tip
    If you use Ansible, use **delegate_to** or SSH proxy functionality to access VM instances through the jump host.

## Wrap Up

To complete the exercise, commit your work and a short description of what you did (preferably in Markdown format) to your Git repository and push the changes to your hosted repository.
