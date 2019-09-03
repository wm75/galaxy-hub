---
title: "About Galaxy: Software"
---

Galaxy is a coordinated suite of software components.  At its core is the **Galaxy server**, the software that powers Galaxy instances and provides a graphical user interface. Other software components and services surround that core and support it.

Here's the big picture of software in the Galaxy ecosystem.

|  | API | Server Deployment | Authentication & Authorization | Cloud | Distributed Compute | Distributed Storage | Tools |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Galaxy Server | X | X | X | X | X | X | X |
| BioBlend        |  X |    |   | X  |   |   |   |
| Blend4PHP     |  X |    |   |   |   |   |   |
| Cargo Port      |   |  X  |   |   |   |   |   |
| CloudAuthZ   |   |  X  | X  | X  |   |   |   |
| CloudLaunch |   |  X  | X  | X  |   |   |   |
| CloudMan      |   |  X  |     | X  |   |   |   |
| Ephemeris     |   |  X  |   |   |   |   |  X |
| ObjectStore    |   |  X  |   | X  |   | X  |   |
| Planemo        |   |  X  |   |   |   |   | X  |
| Pulsar            |   | X   |   | X  |   |   |   |
| StarForge      |   |  X  |   |   |   |   | X  |
| ToolShed      |   |  X  |   |   |   |   |  X |

All Galaxy software is open source.

## Galaxy Server

Galaxy server code supports running tools and pipelines to integrate, analyze, and visualize data. The server also coordinates authentication, manages users, tracks every step of every analysis, and supports sharing and publishing of analyses and reusable workflows.

## Programmatic Access to Galaxy: BioBlend and Blend4PHP

## Tool Support: ToolShed, Planemo, Ephemeris, and Cargo Port

## Cloud and Distributed Resources: CloudLaunch, CloudMan, ObjectStore and Pulsar

## Deployment Support: Everything


