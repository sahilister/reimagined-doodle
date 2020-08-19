---
title: "How I Installed Searx Using Yunohost"
date: 2020-08-19T01:22:38+05:30
tags: ["searx", "privacy", "selfhosting"]
---

I had an AWS account which offers 12 months of Amazon EC2 with 750 hours/month free on initial sign up. It's called free tier by Amazon and offers a t2.micro instance having 1vCPU, 1 GB RAM and 30 GB of storage. I would fire up an instance now and then for trying out various services and just play around with it.

I found about [YunoHost](https://yunohost.org/) while trying to install Matrix homeserver (Synapse). I was trying it through an [ansible playbook](https://github.com/spantaleev/matrix-docker-ansible-deploy) but failed to ssh into my instance using the playbook. I tried installing Synapse using YunoHost which too failed but I discovered various [applications](https://yunohost.org/#/apps) that can be installed on YunoHost.YunoHost installs on your Debian instance and give you a web interface to handle/install services. They explain it well [here](https://yunohost.org/#/whatsyunohost).You can try them on their website [here](https://yunohost.org/#/try). So amongst the list I was interested in Nextcloud and Searx. I dropped Nextcloud due to hardware limitations. I installed Searx and it's been my daily driver ever since. It works well and returns results in under 1.5 sec on best cases and under 5 sec in worst cases scenarios. The average first load time is 2.4 sec and average full load time is 3.4 sec for my personal instance. Not relaying on external search provider due to privacy concern does feel good (though Searx is a meta-search engine, but you know what I mean).

Lets me tell you how I installed it. 

### Basic Requirements

1. A server with root access.
2. Public IP for the server.
3. Debian 10 Buster.
4. (Optional) A domain. YunoHost provides _.nohost.me_, _.noho.st_ or _.ynh.fr_ subdomains if you don't have or want to use a personal one.

### Table of Content 

The installation process is divided into 5 step:

1. [Launch and configure instance](#launch-and-configure-instance)
2. [Install YunoHost](#install-yunohost)
3. [Configure DNS](#configure-dns)
4. [Configure YunoHost](#configure-yunohost)
5. [Install Searx](#install-searx)


### Installation

#### Launch and configure instance

- Launch instance with Debian 10 Buster (YunoHost is based on Debian and won't work on other distros).
- Update the system  

```bash
sudo apt update && sudo apt upgrade -y
```

- Check port forwarding and allow inbound traffic on port 80 (TCP, HTTP), 443 (TCP, HTTPS) and port 22 for SSH.
- Note you're public IP.


#### Install YunoHost

- Install YunoHost using following command 

```bash
curl https://install.yunohost.org | sudo bash
```
- On prompts, allow.


#### Configure DNS

- Get a dedicated domain (_example.com_) or subdomain (_subdomain.example.com_). If not available follow [this](https://yunohost.org/#/dns_nohost_me) to get YunoHost provided domains.
- In you're DNS panel, add a `A record` with Hostname = _example.com_, Destination IP = _11.22.33.44_ (server public IP) and for TTL, YunoHost recommends _3600_ but some DNS providers don't allow that, so choose the minimum your provider allows.
- Basic DNS configuration ends here. If you plan on to add mail and xmpp servers, look for their DNS configuration [here](https://yunohost.org/#/dns_config) (only the bold part).

_Note — Before proceeding further, wait for 10-15 min for DNS update to propagate, then check by using the `dig` command._


#### Configure YunoHost

- Visit _example.com/yunohost/admin_. It will throw certificate issues, accept and proceed (we'll install certificate in the following steps).
- Next follow the screen instructions and choose a strong password. This URL and password would be used to enter the admin panel of the server.
- Next click on `Domains` -> `example.com` -> `Let's Encrypt` to get a SSL certificate for the domain.


#### Install Searx

- Click `Applications` -> `Install` -> `Small Utilities` -> `Searx`-> `Install`.
- Configure the default URLs or add a special one using above Configure DNS section above and add that through `Domains` -> `Add domain`.
- Enjoy your own privacy respecting search engine.

_Notes — If you want the Searx for your own usage, change permissions in Users section._

Complete documentation and forum links can be found [here](https://yunohost.org/#/docs).
