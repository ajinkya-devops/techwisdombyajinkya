---
layout: post
title: "An Introduction to Vagrant"
date: 2017-05-14 10:10:55
initpath: 'assets/img/Post_Images/2017-05-14-an-introduction-to-vagrant/3.png'
image: '../assets/img/Post_Images/2017-05-14-an-introduction-to-vagrant/3.png'
description: Introduction to Vagrant
category: 'devops'
tags:
- Vagrant
- VMs
twitter_text:
introduction:
---
<p align="justify">As we all know, <code>Virtual Machines(VMs)</code> are very popular among the entire IT world. Reason being: their capability of emulating an entire computing system. Virtual Machines gained popularity because of certain aspects of them which are listed below:</p>

<ul> 
<li>To try new Operating Systems (Major reason)</li>
<li>To create virtualized testing environments</li>
<li>Set up an office quickly (Literally!)</li>
<li>Build learning environments</li>
</ul>
 
<p align="justify">All of you must have heard & probably would already have had an experience of working on one of the two undisputed leaders of Virtualization Environments: <code>VMware</code> & <code>Virtualbox</code>.
 
<p align="justify">If you have ever tried to create virtual machines used for testing through a GUI; be it in the VMware or Virtualbox, you will know that it can be a pain, and it is a very manual process. I have found that there is a tendency to leave testing machines around for a long time without rebuilding them. 

<p align="justify">Before Vagrant there is a resistance to creating clean environments, because there is an extra labour cost associated with making this happen, it just a very manual process via a GUI. Vagrant can eliminate much of extra labour so lets go take a look at how that works. 


### What is Vagrant?

<p align="justify"><b>Vagrant is a tool for building and distributing development and testing environments.</b> It acts as a type of wrapper around virtualization software, which greatly speeds up many of the tasks associated with setting up, tearing down, and sharing virtual machines. </p>

<p align="justify">Development environments managed by Vagrant can run on: </p>

<ul>
<li>Local virtualization platforms like VMware/Virtualbox</li>
<li>In the cloud, via AWS/Openstack</li>
<li>In Containers such as Docker</li>
</ul>
 
<p align="justify">Okay so that's enough of introduction to Vagrant. Now we will cover prerequisites and overview of setup that you need to do before you can get going on your own.</p>
 

### Prerequisites
 
<p align="justify">As I mentioned earlier in the post, Vagrant acts as wrapper around virtualization software, so for Vagrant to work, you need to have some type of virtualization software setup.</p>

<p align="justify">The easiest way is to install VirtualBox, because it is free, supports all major operating systems, and it works great with Vagrant.</p>

<ul>
<li>Download Virtualbox binaries from HERE according to your platform.</li>

<li>Install Virtualbox</li>
</ul>

 
### Install Vagrant
<ul>
<li>You can download Vagrant from HERE</li> 

<li>Install Vagrant according to the installation guide from HERE</li>
</ul>


### Verifying the Installation
<ul>
<li>Verify that Vagrant is installed correctly by opening Command Prompt & typing "vagrant -v"</li>

<li>Also, If you run the vagrant command without any arguments, you will get the default help output, which displays available command options.</li>
</ul>

![placeholder](<../assets/img/Post_Images/2017-05-14-an-introduction-to-vagrant/1.png> "Vagrant")


### Check the list of available Vagrant boxes

<ul>
<li>You can check all the available boxes (OS flavours) from HERE</li>
</ul>

![placeholder](<../assets/img/Post_Images/2017-05-14-an-introduction-to-vagrant/2.png> "Vagrant")

### Running Vagrant Box

```shell
    $vagrant init hashicorp/precise64
    $vagrant up
```

<ul>
<li>After running the above two commands, you will have a fully running virtual machine in VirtualBox running Ubuntu 12.04 LTS 64-bit.</li>

<li>You can SSH into this machine with vagrant ssh, and when you are done playing around, you can terminate the virtual machine with vagrant destroy.</li>
</ul>
 
#### Notes 

<ul>
<li>A Vagrant environment can be a single Vagrant virtual machine, or a collection of virtual machines. So, an environment will describe what boxes, or virtual machines to boot, along with all of the associated settings, through a configuration file called a Vagrantfile.</li>

<li>I will write a separate blog post on Vagrantfiles & working around them to create multiple virtual environments at a time & playing around them.</li>
</ul>


<p align="justify"><code>Do let me know your questions, suggestions or reviews in the comments section below.</code></p>