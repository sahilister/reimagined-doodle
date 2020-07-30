---
title: "Firefox Monitor"
date: 2020-07-20T15:44:54+05:30
tags: ["privacy", "firefox", "monitor", "breach"]
---

I have always preferred Firefox due to their approach to privacy as well as providing a viable alternative to Google backed Chromium/Chrome. Recently I also started using Thunderbird for Gmail (slowly trying to switch to ProtonMail). I couldn’t figure out why Gmail on Firefox for Linux with my extensions make the Gmail web client crawl.

Coming to [Firefox Monitor](https://monitor.firefox.com/). It's an online service to see if an account has been part of any public data breach. It sends out email alerts with name of service breach as well as data assumed compromised with the service. The service is free and you can learn more about data breaches and how Firefox Monitor helps [here](https://support.mozilla.org/en-US/kb/firefox-monitor-faq).

#### My Experience

Today i received a breach [alert](https://monitor.firefox.com/breach-details/Wattpad) for Wattpad. [Wattpad](https://www.wattpad.com) is a website for readers and writers to publish new user-generated stories in different genres. The breach exposed almost 270 million records including names, usernames, email, IP address, genders, date of birth and passwords as bcrypt hashes.[^1]
[^1]: "Have I Been Pwned: Pwned websites". [_haveibeenpwned.com_](https://haveibeenpwned.com/PwnedWebsites#Wattpad).

Bear in mind, Wattpad didn't contact me or anyone to inform about the data compromised. No public disclosure was done to inform users to change their credentials. Companies tend to hide these kinds of breaches for PR purposes but it leads to privacy and security concerns. This is also an added benefit of using Firefox Monitor.

_Side note — Check_ [_have i been pwned?_](https://haveibeenpwned.com/)_. Instantly check your account for any compromises. Firefox Monitor works with it to provide alerts._ 

As for Wattpad, I don't use the service anymore so I contacted customer service for data deletion request. The procedure is as follows:

- Email _privacy@wattpad.com_ with subject line: `Permanent Account Deletion` with the email address linked to Wattpad account.
- An automated confirmation mail with usual warning will arrive about losing libraries, reading lists, messages, comments and personal written works. Reply to this mail with an agreement to deletion as well as your username to proceed.
- Done.


_PS: Firefox shows dialog box with breach alerts with info if you visit such site._
