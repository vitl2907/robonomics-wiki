---
title: Lesson 1. Robot Services
contributors: [LoSk-p]
translated: true
---

In the first lesson you will learn how to use Spot services and control Spot's body position.

## Requirements

* Yggdrasil (installation instructions [here](https://yggdrasil-network.github.io/installation.html))

## Connection

To control Spot you need to connect to Spot Core. Go to this [link](https://[200:c32a:e1ac:1da2:15ed:626f:c1e0:36ed]:21443) and log in with your username and password (you can do that only with working yggdrasil). 

![log_in](../images/spot/less1-login.jpg)

Then go to `terminal` tab. There you can use python spot-sdk to control Spot.

![terminal](../images/spot/less1-terminal.png)

Also you can see what robot do in real time [stream](http://[200:b99e:a736:e3bf:744c:6acb:ec11:9dc]:8081/0/stream).

## Documentation

Read [Understanding Spot Programming](https://dev.bostondynamics.com/docs/python/understanding_spot_programming) page in spot-sdk documentation and follow the steps.

For Spot authentication use the same username and password as for Core. Spot address is `192.168.50.3`.

> Use `python3` instead of `python`

> In [Taking ownership of Spot (Leases)](https://dev.bostondynamics.com/docs/python/understanding_spot_programming#taking-ownership-of-spot-leases) section use `lease = lease_client.acquire()` before `lease_keep_alive = bosdyn.client.lease.LeaseKeepAlive(lease_client)`

You can find more detailed information for this lesson in [Base Services](https://dev.bostondynamics.com/docs/concepts/base_services), [Geometry and Frames](https://dev.bostondynamics.com/docs/concepts/geometry_and_frames), [Robot Services](https://dev.bostondynamics.com/docs/concepts/robot_services) and [E-Stop](https://dev.bostondynamics.com/docs/concepts/estop_service) sections of spot-sdk documentation.

## Task

In the first lesson you need to change Spot's body position to make him write your initials by his head. 