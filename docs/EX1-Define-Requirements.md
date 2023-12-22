# Define the Requirements

You were asked to participate in a project to deploy a new solution in a public cloud of your choice. This hands-on assignment is the first step in that process.

Use one of your existing projects, or something one of your customers is working on, or one of the sample projects described at the bottom of this document and document the requirements:

* What services should the public cloud deployment offer to the customers?
* How will the users consume those services? Will they use Internet access, or will you have to provide a more dedicated connectivity solution?
* Identify the data needed by the solution you're deploying. What data is shared with other applications? Where will the data reside?
* What are the security requirements of your application?
* What are the high availability requirements?
* Do you have to provide connectivity to your on-premises data center? If so, how will you implement it?
* Do you have to implement connectivity to other (customer) sites? If so, how will you implement it?

## Prepare the Solution Repository

You'll use Git throughout the course to manage the documentation, infrastructure-as-code definition files, and scripts you'll use to deploy your public cloud infrastructure.

Prepare your Git and GitHub environment:

* Install Git on your workstation;
* Create a GitHub account;
* Create a new repository on GitHub;
* Create a local copy of that repository (GitHub has pretty
  good step-by-step tutorials);

!!! Tip
    You can use any other Git-based repository service like GitLab or BitBucket. Your repository can be private if you don't feel comfortable making it public.

## Sample Projects

If you have no idea what project to work on, try one of these:

* **Web site**: Deploy a simple website (we'll give you all the
  instructions needed to deploy it) with a back-end database running on a database server. Figure out the connectivity requirements for website admins (working for your organization) and end users, depending on whether you'd be deploying a public or internal website.
* **Data archive**: You'll use public cloud infrastructure to archive data from your organization.
