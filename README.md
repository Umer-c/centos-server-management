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
