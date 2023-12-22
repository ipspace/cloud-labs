# Secure Your Virtual Network Infrastructure

In the last hands-on exercises, you [created a virtual network](EX2-Infrastructure-as-Code.md), a [private and a public subnet](EX4-Deploy-Virtual-Network.md), and [deployed several virtual machines](EX3-Deploy-Web-Server.md). Now, it's time to secure your deployment.

!!! Tip
    You're highly encouraged to continue working on a challenge relevant to an actual problem you're facing, as long as it includes most of the components you're expected to use and is simple enough to be completed in a reasonable amount of time.

## Traffic Filters

Using appropriate mechanisms offered by the public cloud environment you chose, apply traffic filters that will limit the traffic according to these rules:

* Anyone can connect to the Web server over HTTP and HTTPS;
* Specified IP addresses can connect to the SSH jump host over SSH;
* SSH jump host can connect to any VM within your virtual network over SSH;
* Web server(s) can connect to database server(s) over HTTP and MySQL (or any other similar service)
* Database server(s) can communicate over HTTP and MySQL

## Identity and Access Management

Create multiple users within your account (or subscription):

* A user with read-only access - when using those credentials, you should be able to see the networking and compute resources but not modify them.
* A user that can modify the storage bucket you created in the [third exercise](EX3-Deploy-Web-Server.md) but not anything else (optional)
* A user that can view networking resources and modify compute resources. Split your deployment procedure into two parts, and deploy networking and compute resources using two separate users (optional)

## Application firewall (optional)

Add a web application firewall in front of your web server and block any attempts to access /admin or /login URLs.

## Session logging (optional)

Log all sessions to and from the SSH jump host.
