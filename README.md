# Linux Server/Service Management
How to host/manage server on Linux

This repository demonstrates how to manage a server/service on Linux using Vagrant, both manually and with provisioning.

## Overview

Managing a server on Linux involves setting up and configuring various services. In this repository, we will show you how to manually set up an HTTP server on Linux and how to automate the setup process using Vagrant's provisioning capabilities.

## Contents

- [Manual Setup](#manual-setup)
- [Provisioning with Vagrant](#provisioning-with-vagrant)

## Manual Setup

Follow these steps to manually set up an HTTP server on CentOS.

### Step 1: Install Necessary Packages

First, install the required packages using `yum`:

```bash
yum install httpd wget unzip vim -y
```

### Step 2: Start and Enable HTTPD

```bash
systemctl start httpd
systemctl enable httpd
```

### Step 3: Download and Deploy the Website

Create a temporary directory, download the website template, and deploy it to the HTTP server:

```bash
mkdir -p /tmp/finance
cd /tmp/finance
wget https://www.tooplate.com/zip-templates/2135_mini_finance.zip
unzip -o 2135_mini_finance.zip
cp -r 2135_mini_finance/* /var/www/html/
systemctl restart httpd
cd /tmp/
rm -rf /tmp/finance
```

This will download a sample website template, unzip it, and copy the contents to the web server's root directory. Finally, the HTTPD service is restarted to apply the changes.

## Provisioning with Vagrant

Provisioning is the process of setting up the software and configuration on a virtual machine automatically. Vagrant allows you to automate the provisioning of your virtual machines using shell scripts, configuration management tools, and more.

In this section, we demonstrate how to use Vagrant to automatically provision a CentOS server with the same setup as described in the manual steps.

### Step 1: Clone this repository


