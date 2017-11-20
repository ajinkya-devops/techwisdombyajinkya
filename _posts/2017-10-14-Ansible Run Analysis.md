---
layout: post
title: "Ansible Run Analysis"
date: 2017-10-14 12:26:40
initpath: 'assets/img/Post_Images/2017-09-14-Ansible Run Analysis/ara-with-icon.png'
image: '../assets/img/Post_Images/2017-09-14-Ansible Run Analysis/ara-with-icon.png'
description: Analysing Ansible Runs with ARA tool.
category: 'devops'
tags:
- Ansible
- ConfigMgmt
twitter_text: Analysing Ansible Runs with ARA tool.
introduction: Analysing Ansible Runs with ARA tool.
---
<p align="justify"><a href="https://www.ansible.com/">Ansible</a> can be used for a lot of things and it’s grown pretty popular for managing servers and their configuration. Today, Ansible is heavily used to deploy or test through Continuous Integration (CI). </p>

<p align="justify">In the world of automated continuous integration, it’s not uncommon to have hundreds, if not thousands of jobs running every day for testing, building, compiling, deploying and so on. </p>

### Problem

<p align="justify">Well, you cannot call it as a "Problem!",  but Ansible runs generate quite a large amount of console data. And yes, it continues to grow with each <b>flag</b> (Remember <b>-v</b> & <b>-vvv?</b>) that you add to the run! </p> 

<p align="justify">Keeping up with such a large amount of Ansible runs and their outcome, not just in the context of CI, is challenging. </p>

<p align="justify">Due to this mess, one tends to feel the need of something, that will present this verbose output in a way which is easily readable, graphical, tabular & more representative of the job status and debug information. </p>

> That `something` is ARA.

### Ansible Run Analysis (ARA) Tool

<p align="justify"><code>ARA</code> records <code>Ansible</code> playbook runs and makes the recorded data available and intuitive for users and systems. ARA organizes recorded playbook data in a way to make it intuitive for you to search and find what you’re interested in as fast and as easily as possible. </p>

![placeholder](../assets/img/Post_Images/2017-09-14-Ansible Run Analysis/ara1.png "ARA Tool UI")

<p align="justify">It provides summaries of task results per host or per playbook. </p>

![placeholder](../assets/img/Post_Images/2017-09-14-Ansible Run Analysis/ara2.png "ARA Tool UI")

<p align="justify">It allows you to filter task results by playbook, play, host, task or by the status of the task. </p>

![placeholder](../assets/img/Post_Images/2017-09-14-Ansible Run Analysis/ara3.png "ARA Tool UI")

<p align="justify">With ARA, you’re able to easily drill down from the summary view for the results you’re interested in, whether it’s a particular host or a specific task. </p>

![placeholder](../assets/img/Post_Images/2017-09-14-Ansible Run Analysis/ara4.png "ARA Tool UI")

<p align="justify">Beyond browsing a single ansible-playbook run, ARA supports recording and viewing multiple runs in the same database. </p>

![placeholder](../assets/img/Post_Images/2017-09-14-Ansible Run Analysis/ara5.png "ARA Tool UI")

### Installation

<p align="justify">There are 2 ways in which you can install ARA in your system. </p>
<ol>
<li>Using **Ansible Role** hosted on my <a href="https://github.com/AjinkyaBapat/Ansible-Run-Analyser">GitHub Account </a></li>

* Clone the repo & do:

````yaml
  ansible-playbook Playbook.yml
````
* If Playbook run is successful, you will get:

````yaml
  TASK [ara : Display ara UI URL] ************************
  ok: [localhost] => {}
    "msg": "Access playbook records at http://YOUR_IP:9191" 

````
* **Note**: It picks the IP address from ***ansible_default_ipv4*** fact gathered by *Ansible*. If there is no such fact gathered, replace it with your IP in `main.yml` file present in `roles/ara/tasks/` folder.

<li>ARA is an open source project available on <a href="https://github.com/dmsimard/ara">Github</a> under the Apache v2 license. Installation instructions are present under **Quickstart chapter**. </li>

<p align="justify">The <a href="http://ara.readthedocs.io/en/latest/">Documentation</a> and <a href="http://ara.readthedocs.io/en/latest/faq.html">frequently asked questions</a> are available on <code>readthedocs.io</code>. </p>

-----
### Conclusion

<p align="justify">Ever since I came across this tool, it's been a useful resource for me to get more out of `Ansible` run logs and outputs. I would highly recommend it for all `Ansible Ninjas!` out there. </p>

<p align="justify">Feel free to share this with others and do let me know your experience of using ARA. </p>