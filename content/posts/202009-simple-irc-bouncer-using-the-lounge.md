---
title: "Simple IRC Bouncer using The Lounge"
date: 2020-09-11T03:16:28+05:30
tags: ["irc", "bouncer", "communication","the lounge"]
---

I use matrix services to communicate online and to bridge into IRC channels. So the other day, [Element](https://en.wikipedia.org/wiki/Element_(software)) was giving some trouble, and I was into a long conversation with someone on IRC. To access IRC, I found ["The Lounge"](https://thelounge.chat/) in my Yunohost instance directory. [Yunohost](https://yunohost.org/#/) is a Debian distribution one can say, which provides a Web GUI to manage and install application with a few clicks doing the heavy work for you with less to non server knowhow.

Coming back to IRC bouncer, this aforementioned steps can help you setup a free IRC bouncer (through [AWS EC2 free tier](https://aws.amazon.com/free/?all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc)). You can simply login into a web interface to access IRC. There not much to do other than getting YunoHost up and this can be completed in about 30-40 minutes.

### Installation

#### Install and configure Yunohost

- Follow steps 1-4 as mentioned in table of content [here](/2020/08/how-i-installed-searx-using-yunohost/). It links to my other post about Searx on Yunohost, so just referenced the same steps.
Otherwise, follow the official installation guide [here](https://yunohost.org/#/install_on_vps).

#### Install The Lounge

- On Yunohost web interface, do `Application` -> `Install` -> `Communication` -> `The Lounge` -> `Install`.


### Usage

- Add default user for Yunohost if not already done from `Users` menu on interface.
- Open "The Lounge" URL from `Application` section and login with default user created above.
- Login with your IRC credentials and start chatting.

_PS: The Lounge can be installed on Heroku also I believe but Heroku instances (free tier) go on sleep on 5 minutes of inactivity, so persistence can suffer. Feel free to correct me by firing a mail :) ._

_PSS: Other ways to install The Lounge can be found [here](https://thelounge.chat/docs/install-and-upgrade)._



