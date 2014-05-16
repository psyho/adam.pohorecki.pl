---
layout: post
title: "How to Install PS3 Media Server on Ubuntu 14.04 Trusty Tahr"
date: 2014-05-16 15:06
comments: true
categories: [Ubuntu, How-To]
---

At the moment I'm writing this, the official Ubuntu guide to installing PS3 Media Server suggests doing the following:

```bash Installation Procedure
sudo add-apt-repository ppa:happy-neko/ps3mediaserver
sudo apt-get update
sudo apt-get install ps3mediaserver
```

Unfortunately, the second step of this process fails, because the happy-neko/ps3mediaserver repository does not have the packages for trusty yet. Luckily, we can still use the packages for raring:

```bash Installation Procedure, Updated
sudo add-apt-repository ppa:happy-neko/ps3mediaserver
sudo sed -i s/trusty/raring/ /etc/apt/sources.list.d/happy-neko-ps3mediaserver-trusty.list
sudo apt-get update
sudo apt-get install ps3mediaserver
```

Et voilà! PS3 Media Server is installed.
