---
layout: post
title: "Graphite: Monitor almost everything"
date: 2017-06-25 06:57:20
initpath: 'assets/img/Post_Images/2017-06-25-graphite:-monitor-almost-everything/1.png'
image: '../assets/img/Post_Images/2017-06-25-graphite:-monitor-almost-everything/1.png'
description: Introduction to Graphite.
category: 'devops'
tags:
- Monitoring
- Graphing
twitter_text:
introduction:
---
### Introduction

<p align="justify"><code>Graphite</code> is a graphing library made up of several components that can be used to render visual representations of your data over time and can show you statistics/metrics about that data.</p>

### Why do we collect data statistics & metrics?

<p align="justify">There are plenty of reasons why collecting stats about your servers, applications, and traffic is a good idea.</p>

<ul>
<li><p align="justify">Collecting and organizing data can give you confidence in your decisions about scaling, troubleshooting, and tracking down pain-points in your configurations. </p></li>

<li><p align="justify">The more data we have, the more likely we will be able to understand what is happening at any given moment. </p></li>

<li><p align="justify">
Most logging systems today are unable to correlate data from various applications and are also unable to represent it efficiently. </p></li>
</ul>

### Graphite

<p align="justify">Graphite is an enterprise-ready monitoring tool that runs equally well on cheap hardware or Cloud infrastructure.</p>

<p align="justify">Teams use Graphite to track the performance of their websites, applications, business services, and networked servers.</p>

<p align="justify">It marked the start of a new generation of monitoring tools, making it easier than ever to store, retrieve, share, and visualize time-series data.</p>

<p align="justify">Apart from that, it does following things as well! (According to Graphite folks, not me!)</p>

![placeholder](../assets/img/Post_Images/2017-06-25-graphite:-monitor-almost-everything/2.png "Graphite")

### Architecture 

Graphite consists of `three` software components:

![placeholder](../assets/img/Post_Images/2017-06-25-graphite:-monitor-almost-everything/3.png "Graphite") 

<ol type="1">
<li><p align="justify">
<code>carbon</code> - a high-performance service that listens for time-series data</p></li>

<li><p align="justify">
<code>whisper</code> - a simple database library for storing time-series data</p></li>

<li><p align="justify">
<code>graphite-web</code> - Graphite's user interface & API for rendering graphs and dashboards</p></li>
</ol>

<p align="justify">Metrics get fed into the stack via the Carbon service, which writes the data out to Whisper databases for long-term storage. Users interact with the Graphite web UI or API, which in turn queries Carbon and Whisper for the data needed to construct the requested graphs.</p>

### Installation

<p align="justify">You can read about Graphite installation using <code>Synthesize Script</code> in detail from <a href="http://graphiteapp.org/quick-start-guides/synthesize.html">HERE</a>.</p>

<p align="justify">Synthesize is a fully automated installation and configuration script for the Graphite stack.</p>

### Getting Matrics in Graphite

<p align="justify">There is a detailed explanation of how to get your own metrics into Graphite <a href="http://graphiteapp.org/quick-start-guides/feeding-metrics.html">HERE</a>.</p>

<p align="justify">Also, you can find a lot of detailed information about the same on <a href="http://graphite.readthedocs.io/en/latest/overview.html">Graphite Docs</a></p>

 
`Here's how the Graphite Web UI looks on my machine!`

![placeholder](../assets/img/Post_Images/2017-06-25-graphite:-monitor-almost-everything/4.png "Graphite")
![placeholder](../assets/img/Post_Images/2017-06-25-graphite:-monitor-almost-everything/5.png "Graphite")
![placeholder](../assets/img/Post_Images/2017-06-25-graphite:-monitor-almost-everything/6.png "Graphite")


<p align="justify">I will be uploading my tutorial on the same very soon. Till then you can get the know-how of getting data; or to be more specific, getting Matrics into the Graphite Stack from the above-mentioned links.</p>