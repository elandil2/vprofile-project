# DevOps-local

This project involves provisioning virtual machines (VMs) and configuring them for different services, such as databases, web servers, and message brokers, for development and testing purposes. Let's break down the steps and provide an explanation:

Prerequisites:

Oracle VM Virtualbox: This is a virtualization platform used to run virtual machines.

Vagrant: Vagrant is a tool for managing virtual machine environments using a simple configuration file.

Vagrant Plugins: The 'vagrant-hostmanager' plugin is required and should be installed using the 'vagrant plugin install' command.

Git Bash or Equivalent Editor: You'll need a terminal or text editor for executing commands and editing files.

VM Setup:

Clone Source Code: Clone the project's source code repository.

Change Directory: Navigate into the cloned repository.

Switch to Main Branch: Ensure you are on the main branch of the project.

Navigate to Vagrant Directory: Change to the 'vagrant/Manual_provisioning' directory.

Bring Up VMs: Use 'vagrant up' to start the virtual machines. Note that this step might take a while.

Provisioning:

The provisioning section explains how to set up various services on the VMs. These services include:

MySQL Setup: This section explains how to set up a MySQL database, including securing it and creating a database with a user.

Memcache Setup: Instructions for installing and configuring Memcache, a distributed caching system.

RabbitMQ Setup: Details for setting up RabbitMQ, a message broker.

Tomcat Setup: Instructions for installing and configuring Apache Tomcat, a web server for Java applications.

Nginx Setup: Details for installing and configuring the Nginx web server, including setting up a reverse proxy to the Tomcat server.

Each section provides commands and explanations on what needs to be done on the respective VM.

Code Build & Deploy:

The 'CODE BUILD & DEPLOY' section focuses on building and deploying the application:

Download Source Code: Clone the project's source code repository again on the 'app01' VM.

Update Configuration: Edit the application properties file to configure backend server details.

Build Code: Use 'mvn install' to build the code.

Deploy Artifact: Deploy the application to the Tomcat server by copying the WAR file to the Tomcat webapps directory.

Nginx Setup (Web Server):

The final section deals with setting up Nginx as a reverse proxy server to route traffic to the Tomcat server:

Login to the Nginx VM: Access the Nginx VM.

Install Nginx: Install Nginx on the VM.

Create Nginx Configuration: Create an Nginx configuration file to route requests to the Tomcat server.

Remove Default Nginx Configuration: Remove the default Nginx configuration.

Create Link: Create a symbolic link to activate the new website configuration.

Restart Nginx: Restart the Nginx server to apply the new configuration.

These steps help configure Nginx to act as a reverse proxy for your Java application running on the Tomcat server.

Overall, this set of instructions guides you through creating a development environment with multiple VMs, configuring various services, and setting up a web server to deploy and test a Java application. Be sure to follow these steps carefully to set up your environment successfully.
------------------------------------------------------------------------------------------------------------------
Automated version : 
# VPROFILE DevOps Project

This DevOps project automates the setup of a development environment using Vagrant and related tools. It provisions virtual machines (VMs) and configures various services for development and testing purposes. This README provides an overview of the project structure and usage.

## Prerequisites

Before getting started, ensure you have the following prerequisites installed on your host system:

- Oracle VM Virtualbox
- Vagrant
- Vagrant plugins (vagrant-hostmanager)
- Git Bash or an equivalent editor

## Project Structure

The repository contains the following components:

- `backend.sh`: Shell script for setting up backend components (Memcache, RabbitMQ, MySQL).
- `memcache.sh`: Shell script for Memcached setup.
- `mysql.sh`: Shell script for MySQL setup.
- `nginx.sh`: Shell script for Nginx setup as a reverse proxy.
- `rabbitmq.sh`: Shell script for RabbitMQ setup.
- `tomcat_ubuntu.sh`: Shell script for Tomcat setup on Ubuntu.
- `tomcat.sh`: Shell script for Tomcat setup on CentOS.
- `Vagrantfile`: Vagrant configuration file defining VMs and provisioning scripts.

## Usage

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/yourusername/vprofile-devops.git
   cd vprofile-devops
Make sure you have Vagrant and VirtualBox installed.

Run the following command to create and provision the VMs:

bash
Copy code
vagrant up
Note: This may take some time as it sets up all the VMs and services.

Access your services using the following URLs:

Nginx (web01 VM): http://192.168.56.11
Tomcat (app01 VM): http://192.168.56.12:8080
MySQL (db01 VM): 192.168.56.15
Memcache (mc01 VM): 192.168.56.14
RabbitMQ (rmq01 VM): 192.168.56.16
You can customize configurations and deploy your application as needed.

Contributing
If you'd like to contribute to this project, please fork the repository, make your changes, and submit a pull request. We welcome contributions!
