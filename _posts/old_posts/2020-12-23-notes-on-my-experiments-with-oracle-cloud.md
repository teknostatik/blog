---
title: "Notes on my experiments with Oracle Cloud"
date: "2020-12-23"
categories: 
  - "linux"
  - "oracle"
---

This Christmas I set up two small VMs in Oracle's cloud; one running Oracle Linux 8 (which I'm trying to learn at the moment), and one running Ubuntu (with my standard VM/container build). I've written these notes largely for me, but maybe someone else might find them useful too.

## Registering for Oracle Cloud

To sign up for Oracle Cloud go to [https://www.oracle.com/cloud/free/](https://www.oracle.com/cloud/free/).

You'll need a credit card, but it won't be charged providing you only use things marked as _always free_. This gets you two VMs, with 1 GB of RAM each and 100 GB of storage. That's more than enough for what I need to do here so it's all good. You also get signed up for a trial which allows you to build much bigger machines and access more services. I've not tried this out yet, but it's possible to go all the way up to VMs with 64 GB of RAM or bare metal machines with a lot more (which is basically what I want to build at home at some point soon).

See [here](https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier.htm) for exactly what the free tier gets you.

## Using Oracle Cloud

To build VMs and generally interact with the service log in at [Oracle Cloud](https://console.uk-london-1.oraclecloud.com/). The first time you create a VM you'll be asked to generate an SSH key (or provide one). Download the private key and save it somewhere, and then `chmod` it to `500` (otherwise it won't let you log in). The key can be used for more than one VM, so you should only need to go through this process once.

You can see all your instances at [https://console.uk-london-1.oraclecloud.com/compute/instances](https://console.uk-london-1.oraclecloud.com/compute/instances) - This works for anything in the London data centre but would need to be amended for other data centres.

## Logging in to a VM

To log in open up a terminal and SSH to the VM. The syntax is:

`ssh -i /path/to/key/ username@ip_address`

Where `/path/to/key/` is the location you saved your private key. Username and IP address will be in the _Instance Access_ section of the _Instance Details_ for the specific VM.

Full instructions are available on the [Oracle Cloud website](https://docs.oracle.com/en/cloud/paas/api-platform-cloud-um/apfad/accessing-vm-secure-shell-ssh.html#GUID-960BEB0F-4B2A-4974-9671-61478B702223).

## First thoughts

The Ubuntu VM was indistinguishable from what I'm used to, and all my usual software and scripts worked fine. I'm less familiar with Oracle Linux, but installing and updating software works as expected so I have no reason to believe that the experience will be that different from a locally installed server. I still don't find Oracle Linux anywhere near as easy to use as Ubuntu, but I suspect that's as much down to 15 years less experience as anything else.
