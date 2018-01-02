---
title: CloudLaunch
---

CloudLaunch is a web application and an API that allows composite virtual
machines (i.e., appliances) to be launched on a range of cloud provider
infrastructures. CloudLaunch handles cloud provider credentials management,
the launching process, and subsequent monitoring of the deployed appliances.

## Appliances
The following is a (non-exhaustive) list of appliances available via
CloudLaunch. Many flavors offer overlapping functionality but are individually
tailored for a specific use case, as detailed in their respective descriptions.
 * [Genomics Virtual Lab](https://www.gvl.org.au/): the default and recommended
   appliance for using Galaxy on the cloud. It offers dynamic scaling
   capabilities and other application and infrastructure management features.
 * [Galaxy Docker flavors](/src/cloud/docker-flavors/index.md): Galaxy
   instances tailored for a specific type of analysis. Note that these machines
   do not offer ability to save the data after they are shut down.
 * [Galaxy Standalone](/src/cloud/jetstream/allocation/#using-api-credentials-for-cloudlaunch):
   Similar to the Docker flavors but uses a virtual machine instead of Docker
   containers to run Galaxy. This appliance is available only on the NSF
   Jetstream cloud.
