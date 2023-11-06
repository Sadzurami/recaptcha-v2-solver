# ReCaptcha V2 Solver

# NOT SUPPORTED ANYMORE

Cheapest and highest quality ReCaptcha V2 / Enterprise solver.

![](./tests-screen.jpg)

## Please ignore this app, if

- you do not need it
- you are satisfied with the results of the service
- you are happy with the results of a similar service
- you think this application is more expensive than other services or similar ones
- you don't understand why you should use this service if you can send tasks directly to a service

## Features

### Working with API

You interact with the application through the REST API and receive a captcha token as a solution.
For security, you need to specify the access keys to the application.
You choose them yourself and use them in your applications as api keys.

You can add them singly, from a file or from a link.

### Support for the Enterprise version of the captcha

Works for any sites with captchas of this type.

Supports additional parameters passed to the captcha.

### Unlimited free solutions\*

To solve the captcha requires neural network of object detection.

The application does not contain similar modules, but is able to work with off-the-shelf solutions:

-   [Captcha Guru](https://captcha.guru/ru/reg/?ref=100230) (paid).
-   [Capmonster](http://zennolab.com/ru/products/capmonster/capmonster-lite-samples/pid/30bdfb93-7f1d-4cb8-94b6-16ed37b31dd6) (paid)
-   Public Server (free).

The "Public Server" mode is free. This is a shared public server, which sends all the pictures to detect objects from all owners of the application. Suitable for everyone who do not plan to work with large amounts of captchas.

\*There are restrictions on the number of requests to the server per second.

\*Availability of the public server is not guaranteed.

### Solutions quality

Score 0.9 on 90% of tokens (captcha solutions) of the enterprise version of the captcha.

Guaranteed as long as conditions are met:

-   Good mobile or rededent proxies of any country, except RU. Server or any ip from RF cannot guarantee high score.
-   IP change is obligatory after each decision
-   Reuse IP no more than 3 times in 2 hours.

Cookies and additional data are not required for quality solutions.

[Proxies tier list](#proxies-tier-list).

### Speed of solutions

Less than 15 seconds for one solution of captcha.

Not guaranteed, but may be subject to conditions:

-   Proxies are fast enough
-   IPs of high quality (see point "Quality of solutions")

### Low traffic consumption

From 100 Kb for one solution of captchas.
Guaranteed under the following conditions:

-   IP quality (see point "Quality of solutions").

### Change of IP by link.

It can be useful when working with proxies having rotation by the link.

### Emulation of API of popular services

Supported:

- RuCaptcha
- 2Captcha
- Anticaptcha

If you write queries from scratch, follow instructions from [here](https://anti-captcha.com/apidoc) or [here](https://2captcha.com/2captcha-api), then change the host of the link to your own.
For example: the application runs locally (127.0.0.1) on port 5555, in this case change the link like this:

**For RuCaptcha/2Captcha API**:

- http://rucaptcha.com/in.php --> http://127.0.0.1:5555/in.php
- http://rucaptcha.com/res.php --> http://127.0.0.1:5555/res.php

**For Anticaptcha API**:

- https://api.anti-captcha.com/createTask --> http://127.0.0.1:5555/createTask
- https://api.anti-captcha.com/getTaskResult --> http://127.0.0.1:5555/getTaskResult

If you use ready-made solutions and there is no possibility to change the link, you can add a rule to the hosts file.

To do this:

- Run the application on port 80
- Open as administrator the file c:{windows\system32\drivers\etc\hosts
- Add the following lines to the very end
- `127.0.0.1 rucaptcha.com`
- `127.0.0.1 anti-captcha.com`
- Save this file

## Proxies tier list

**Mobile or Resident IPv4/IPv6**
- Best choice. Suitable for any captcha.
- Get maximum trust from captcha provider.
- On one IP it is possible to solve 3 enterprise type CAPTCHA for 2 hours, receiving the maximum score 0.9. If to solve more - score will start to fall and will be restored in 48 hours.
- Often slow and expensive, which may adversely affect when used with conventional v2 captcha.

**Hostings IPv4**
- Trust from captcha provider is limited.
- It is impossible to get the maximum score on the enterprise version of the captcha. Under ideal conditions, the best score will be 0.7, more realistically - 0.3.
- Fast. Good option for usual v2 captchas.

**Hostings IPv6**
- Trust from captcha provider is minimal.
- Not suitable for enterprise captcha. Maximum score is 0.1.
- IPs often get banned, so it is best to use many of them from different subnets.
- The cheapest option for regular v2 captchas.
- You can raise 15000 (or more) proxies by yourself using my free [script] (https://github.com/Sadzurami/tunnelbroker-proxies). And it will cost [4$ per month](https://hetzner.cloud/?ref=u773sH3Kq8gw). It is better to raise several of them, so that there are different subnets.

**A few words about rotation**

It's best to use rotation by link.
The app knows how to change the IP by link, if you provide a link along with a proxy, with a `|` separator.
For example: `http://log:pass@1.2.3.4:8080|http://changeip.com`

Rotation by time is better not to use, especially for the enterprise version of the captcha. At the moment of IP change captcha loses connection and resets current task.

Rotation on each request also does not make sense when solving captchas.

**A few words about proxy services**

Even if you use mobile or resedent proxies, there is no guarantee that you will receive the maximum trust from the captcha.
Certain subnets may be blacklisted by the captcha provider.
You should check several different services and countries, and if possible exclude RU IP's, as they have a maximum score of 0.7.

## Other


Free for a limited time.

`There is no technical support for setup or anything else.`

The application is delivered "as is" and if you are not happy with the use - ignore app.
