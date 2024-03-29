---
layout: post
title: "Twinkle + FF Setup (Click To Call) using telify"
date: 2010-10-17T00:47:00+05:30
comments: false
categories:
 - twinkle
 - asterisk
---

On linux machine following settings needs to be done in order to get in browser calling enabled for phone numbers.

## Installation setup

1. Install twinkle setup (Create user profile) and get it working for outgoing and incoming calls
2. Install telify add-on (can be un-installed once completed with all settings)
3. Copy wrapper script `twinkle_tel`) click here to [download](http://github.com/sandipransing/twinkle_tel) and copy it to `/usr/bin` on user’s machine (make sure it has executable permissions)
4. In Firefox go to *preferences/applications*
5. Search for `tel` protocol and change value of tel protocol to */usr/bin/twinkle_tel*

## Usage/ Pre-requisites

HTML source code of phone number should look like as below

**1. Dialing source code**
```
<a title="phone number" class="telified" nr="9860648108" href="tel:9860648108">9860648108</a>
```

**2. Call disconnect source code**
```
<a title="disconnect call" class="telified" href="tel:disconnect">Disconnect</a>
```

<img src="{{ root_url }}/images/clicktocall.png" />
