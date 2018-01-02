---
title: Get your own Galaxy
layout: cloud.pug
splash: Within minutes. Configurable. Scalable. Without quotas.
why:
    Researchers' compute requirements vary widely over time and formerly required either buying and
    maintaining compute resources (with a lot of it idle), or reserving time and a
    fixed amount of compute resources on institutional clusters.
    <br />
    The cloud provides another option for this situation that can be cost-effective and efficient.
    Cloud infrastructures are elastic and dynamic. You only allocate resource when you need them, and
    you are able to dynamically scale up and down your allocated resources as your needs change over
    time. Furthermore, compute clouds are maintained by outside providers - you don't need to install
    your own hardware, or need to have access to a research compute cluster at your institution.
    <br />
    Available solutions allow you to create an installation of Galaxy on a cloud infrastructure
    provider within minutes, using a web interface or an API, and start using Galaxy right away.
    Once launched, the instance can be shared with colleagues or shut down during idle periods.
when:
    The following is a non-exhaustive list of scenarios when it is beneficial to use Galaxy on the cloud
when_reasons:
    - reason: Need to customize a Galaxy instance with tools or genome reference data
    - reason: Have run up against the quotas on a public server
    - reason: Do not want to spend time setting up a Galaxy instance
    - reason: Have variable or high requirements for compute or storage resources

solutions:  # Max 3
    - solution:
        name: Genomics Virtual Lab (GVL)
        url: /src/cloud/appliances/gvl/
        logo: http://abrpi.genome.edu.au/galaxy/static/images/gvl.png
        pitch: A suite of bioinformatics tools (Galaxy, Jupyter, RStudio, command line) available on multiple clouds.
    - solution:
        name: Globus Genomics
        url: http://www.globus.org/genomics
        logo: https://www.ci.uchicago.edu/sites/default/files/styles/large/public/globus_genomics_300x200.png?itok=TTDYl20v
        commercial: true
        pitch: Pre-defined best practice analytical pipelines with the familiar Galaxy interface available on AWS.
    - solution:
        name: Galaxy Enterprise Cloud
        url: https://www.galaxyinformatics.com/
        logo: /images/logos/galaxy-enterprise-logo-200.png
        commercial: true
        pitch: Fully managed and cloud-hosted Galaxy with various levels of SLAs, including data storage and management.
---
