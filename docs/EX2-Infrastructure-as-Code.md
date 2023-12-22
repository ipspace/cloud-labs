# Simple Infrastructure-as-Code Setup

In the second hands-on exercise, you'll:

* Select your public cloud provider,
* Create a public cloud account,
* Prepare your infrastructure-as-code environment.

## Selecting the Public Cloud Provider

You can select any public cloud provider of your choice as long as they provide interesting enough networking features, including:

* Private per-tenant networks and subnets;
* Per-tenant private addressing and NAT between tenant addresses and
  public IPv4 addresses;
* Security groups and stateful filters in front of VM interfaces;
* Multiple availability zones and regions;
* Optional: IPv6 connectivity;

AWS, Azure, Google Cloud, and Oracle Cloud Infrastructure (OCI) meet all these requirements. We have in-depth materials covering [AWS](https://my.ipspace.net/bin/list?id=AWSNET) and [Azure](https://my.ipspace.net/bin/list?id=AzureNet); your job might be a bit easier if you select one of these two, but please feel free to work with whatever public cloud provider makes the most sense for you.

Before you can get any work done, you'll need an account with the selected public cloud provider. AWS and OCI provide a long-term free tier (if you consume only a few resources), and Azure has time-limited free trials. You'll have to provide credit card details, but if you're at least a bit careful and shut down the resources after you're done with hands-on exercises, you won't get charged much (my Azure bills were around $1).

## Selecting the Infrastructure-as-Code Tool

You can work with any tool (free or commercial, open- or closed-source), or you could hack together a solution in Bash, Python, or any other programming language of your choice as long as the solution supports infrastructure-as-code concepts and meets a few additional requirements:

* You can describe the target infrastructure in machine- and human-readable
  definition files that can be tracked as text files with Git;
* The tool supports _idempotent_ deployments: you can execute the deploy process
  multiple times with no changes in the target infrastructure if the state of the
  infrastructure already matches your desired state;
* The tool supports adds, removals, and changes.

!!! Tip
    Implementing the last requirement with a home-brewed solution is complex. For example, my Bash scripts support idempotent infrastructure creation but not changes or removals.

**Ansible** and **Terraform** meet all the requirements (although resource removal tends to get clumsy with Ansible). Terraform is usually a better fit, but you won't find any training materials on ipSpace.net. We described **Ansible** core functionality extensively in the past and added cloud-specific material for AWS and Azure.

You can also use cloud-specific tools like AWS CloudFormation or Azure Resource Manager.

## Your First Infrastructure-as-Code Deployment

After creating an account with a public cloud provider and selecting the IaC tool, create a single public cloud resource using the infrastructure-as-code tool of your choice.

You could do something as simple as creating a tenant network (VPC/Vnet) with RFC 1918 prefix, or you could deploy a virtual machine. After you manage to create the selected public cloud resource, change the definition file to rename it, change its parameters, or remove it.

Finally, commit the definition file and a short description of your work (preferably in Markdown format) to your Git repository, and push the changes to your hosted repository.

!!! Warning
    Always store your public cloud credentials (account ID, secret keys, passwords) outside of Git repositories.
