---
title: Global Galaxy
---

Galaxy Project is not a single instance or a software component. It is a collection of software components that are used to deploy Galaxy instances, develop tools, and to facilitate dissemination and training. All of these components are developed and maintained by a vibrant international community, which includes biologists, tool developers, system engineers and administrators as well as educators. 

# Services

## Global instances

-------

The main, highly visible part of Galaxy infrastructure is a worldwide network of Galaxy instances with three primary sites in Europe, US, and Australia. European site, based in Germany, is closely aligned with a number of partner sites in other EU countries including France, Belgium, and the Netherlands. In addition to these main sites, that tightly coordinate and synchronize their toolset and reference datasets, there are over [125](https://galaxyproject.org/use/) smaller, often domain-specific instances located in a number of academic institutions. Galaxy project does not track installations of its software components and there is also a large number of closed, institutional instances that are not included in the above count. 


<div class="card mb-3">
  <iframe src="https://www.google.com/maps/d/embed?mid=1NwAFFOTAG8pcWw5naQ1j10uMHstibHAh" width="800" height="480" frameborder="0" style="border:0"></iframe>
  <div class="card-body">
    <p class="card-text">Main Galaxy instances worldwide.
    </p>
    <a href="http://usegalaxy.eu" class="btn btn-primary btn-sm">usegalaxy.eu</a>
    <a href="http://usegalaxy.org" class="btn btn-primary btn-sm">usegalaxy.org</a>
    <a href="http://usegalaxy.org.au" class="btn btn-primary btn-sm">usegalaxy.org.au</a>
  </div>
</div>

## Galaxy Training Network

-------

Success of the project depends on our ability to train new users, tool developers, and IT professionals on how to use, customize, and deploy Galaxy.  To solve this goal we have initiated a comprehensive Galaxy Training initiative (https://training.galaxyproject.org; (Batut et al. 2018)). This community driven effort aims at providing training materials covering various aspects of the project ranging from basic usage to very specific data analysis scenarious. This effort also includes topics related to development of tools for Galaxy, deployment of Galaxy  instances and, importantly, “train the trainers” program detailing the process of designing new Galaxy tutorials. 

## Galaxy toolshed

-------

ToolShed works as a global App Store for analysis tools that can be installed into any Galaxy system. Every Galaxy system is configured to fetch tools from the ToolShed. In addition, tool developers has the ability to instantiate private ToolSheds specific to their groups or institutions.    

## Common reference data

------

The Galaxy Project deploys a multitude of components to CVMFS, including reference data, tool dependencies (the software packages that underlie the tools Galaxy presents), and the Galaxy software itself. Deploying Galaxy across heterogeneous computing resources requires that these objects remain synchronized, which CVMFS provides. CVMFS allows compute nodes on bare metal, in the cloud, and even the Galaxy server itself to see a unified and consistent view of all of the components. Its replication system ensures that multiple copies of the components exist on geographically dispersed systems, and allows them to be reused by Galaxy community members.

## Container service for analysis tools

------

As Galaxy is moving towards a fully containerized solution (see section X) where every tool runs inside its own Singularity container we provide a CVMFS-based repository for Singularity containers containing all BioConda packages. This repository currently contains over 30,000 Singularity containers representing all BioConda tools built on various versions of Python. When a Galaxy instance anywhere is the world needs to run an analysis it fetches a container containing the appropriate tool from the container service repository and uses it to execute the job. 

# Components

## Galaxy Code Base | https://github.com/galaxyproject/galaxy

------

The main code base of the Galaxy project. The main repository of main Galaxy components including server and client components. There have been over 42,000 code commits to this repository and 5,500 pull request from over 200 contributors. 

## Intergalactic Utilities Commision (IUC) | https://github.com/galaxyproject/tools-iuc

------

A repository containing wrappers for Galaxy tool approved by IUC.  The IUC was established in 2012 to enable the pervasive use of the main Galaxy Tool Shed by ensuring the repositories available include contents that are functionally correct and optimized for installation into local Galaxies. When appropriate, the group provides guidance to Galaxy tool developers so that they can improve the quality of their repositories.

## Planemo | https://github.com/galaxyproject/planemo

------

Planemo is a framework for the development of tools for the Galaxy system. A de facto SDK for adding analysis to the Galaxy framework Planemo allows tool developers to create expendable Galaxy instances specifically for adding  new tools. Planemo can be used as part of a Galaxy tool development virtual appliance which comes pre-configured with Planemo, Galaxy, Docker, Conda, a local Tool Shed, linuxbrew, Komodo and Atom editors.

## Pulsar | https://github.com/galaxyproject/pulsar

-------

Pulsar is deployed as a service on remote compute resources where Galaxy is not able to remotely interface with the resource’s cluster scheduler and/or Galaxy and the resource do not share a common filesystem. Where Galaxy was initially developed as an application for a single server, and later a single data center, Pulsar allows Galaxy to operate on a global scale. Pulsar is responsible for fetching input datasets from Galaxy, resolving binary and reference data dependencies of the tool to be executed, writing the script for submission to the remote cluster scheduler, submitting and monitoring job progress, collecting the job outputs, and sending them back to Galaxy;

## Ephemeris | https://github.com/galaxyproject/ephemeris

--------

Ephemeris is a Python library and set of scripts for managing the bootstrapping of Galaxy plugins - tools, index data, and workflows.


## CloudMan | https://github.com/galaxyproject/cloudman

-------

CloudMan is a cloud manager that orchestrates all of the steps required to provision a complete compute cluster environment on a cloud infrastructure; subsequently, it allows one to manage the cluster, all through a web browser. Although CloudMan can be used in any domain and for any purpose that calls for a compute cluster, it is primarily used in the context of Galaxy Cloud and CloudBioLinux and, along with the infrastructure, ensures a complete Next Generation Sequencing (NGS) analysis toolkit is instantly available. CloudMan is currently available on the AWS EC2 cloud.

# Communities
A vibrant community of contributors is the reason this project exists. The Galaxy team alone cannot possibly maintain enough servers, wrap enough tools, teach enough workshops, implement all needed features, or answer every question on its own. This is why community is vital to our core mission - enabling reproducible research in life sciences and beyond. Members within the Galaxy community are located all around the world and often form subgroups that differ in size (small versus large) and degree of privacy (public versus private).

## Galaxy Community Conferences

-------

In 2010 National Science Foundation has initiated yearly gathering of Galaxy users and developers by providing the project with a grant supplement. Since then this gathering grew into an annual event known as the Galaxy Community Conference (GCC). GCC alternates between US and Europe and provides a forum for sharing knowledge and building collaborations. 

## Tool Development Community

-------

Overseen by IUC this community is responsible for all tool development and deployment at a variety of Galaxy instances around the world.

## Conda and BioConda

-------

Conda is an open source package management system that is heavily used by Galaxy to manage tool dependencies and installations. Bioconda is a specific channel for Conda that distributes popular bioinformatics software, many of which have been wrapped by the Galaxy community.

## Galaxy Training Framework

------
The Galaxy Training Network (GTN) is a network of people that present Galaxy and Galaxy-based training around the world. Members of the GTN are also responsible for generating, curating, and maintaining a large repository of Galaxy training materials. 

## Galaxy Admins

------
GalaxyAdmins is a discussion group for Galaxy community members who are responsible for running and maintaining large Galaxy installations. It has conference calls and gatherings at various Galaxy-related events.
