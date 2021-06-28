---
title: Lesson 1. Robot Services
contributors: [LoSk-p]
translated: true
---

In the first lesson you will learn how to use Spot services and control Spot's body position.

## Requirements

* Yggdrasil (installation instructions [here](https://yggdrasil-network.github.io/installation.html))

> For MacOS install .pkg file from the latest [release](https://github.com/yggdrasil-network/yggdrasil-go/releases)

## Updating the peers

You need to add a list of peers so that you will be able to connect to Spot. For that, edit the file with this command:

sudo nano /etc/yggdrasil.conf

In the file that you opened add the following text:

Peers:
  [
    tcp://95.79.25.190:50001
    tcp://[2a00:b700:2::6:69]:1333
    tcp://n2o.ddns.net:22632
    tcp://ygg.tomasgl.ru:61933
    tcp://37.139.18.100:59243
    tcp://1.ams.nl.y.fftlt.net:21285
    tcp://1.msk.ru.y.fftlt.net:21285
    tcp://1.tlt.ru.y.fftlt.net:21285
    tcp://ygg.loskiq.com:17313
    tcp://88.201.129.205:8777
    tcp://[2a05:3580:d900:1b13:e2d5:5eff:fed8:8b86]:8777
    tls://88.201.129.205:8778
    tls://[2a05:3580:d900:1b13:e2d5:5eff:fed8:8b86]:8778
    tcp://194.177.21.156:5066
    tcp://46.151.26.194:60575
  ]

Then restart Yggdrasil using this command:
systemctl restart yggdrasil

## Connection

To control Spot you need to connect to Spot Core. Go to this link (https://[200:c32a:e1ac:1da2:15ed:626f:c1e0:36ed]:21443) and log in with your username and password (you can do that only with working yggdrasil). 

![log_in](../images/spot/less1-login.jpg)

Then go to `terminal` tab. There you can use python spot-sdk to control Spot.

![terminal](../images/spot/less1-terminal.png)

Also you can see what the robot is doing in real-time livestream (http://[200:b99e:a736:e3bf:744c:6acb:ec11:9dc]:8081/0/stream).

## Documentation

Read [Understanding Spot Programming](https://dev.bostondynamics.com/docs/python/understanding_spot_programming) page in spot-sdk documentation and follow the steps.

For Spot authentication use the same username and password as for Core. Spot address is `192.168.50.3`.

> Use `python3` instead of `python`

> In [Taking ownership of Spot (Leases)](https://dev.bostondynamics.com/docs/python/understanding_spot_programming#taking-ownership-of-spot-leases) section use `lease = lease_client.acquire()` before `lease_keep_alive = bosdyn.client.lease.LeaseKeepAlive(lease_client)`

You can find more detailed information for this lesson in [Base Services](https://dev.bostondynamics.com/docs/concepts/base_services), [Geometry and Frames](https://dev.bostondynamics.com/docs/concepts/geometry_and_frames), [Robot Services](https://dev.bostondynamics.com/docs/concepts/robot_services) and [E-Stop](https://dev.bostondynamics.com/docs/concepts/estop_service) sections of spot-sdk documentation.

## Task

In the first lesson you need to change Spot's body position to make it trace your initials with it's face. For that, you will have to experiment with different body positions. The range of Pitch, Yaw and Roll is from -0.5 to 0.5
