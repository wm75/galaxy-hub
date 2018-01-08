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

## API

CloudLaunch provides a full featured REST API that can be used to
programmatically create and manipulate cloud appliances. You don't have to use
the API; the CloudLaunch web application provides all of the same functionality
in an easy to use interface. But if you have the need to automate the deployment
and monitoring of cloud applications the API is there to help.

There are several different ways in which you can interact with the REST API and
these are covered below.

### Interactive REST API browser

CloudLaunch provides an [interactive REST API
browser](https://launch.usegalaxy.org/cloudlaunch/api/v1/). This is a good way
to browse around and discover what the API can provide. For example, by
navigating to
[https://launch.usegalaxy.org/cloudlaunch/api/v1/infrastructure/clouds/](/cloudlaunch/api/v1/infrastructure/clouds/)
you can see a list of available clouds. For each cloud there is a link to the
*compute*, *storage*, *networking*, and *security* resources available on that
cloud.

Note: some parts of the REST API browser require authentication so it's best to
[login to CloudLaunch first](https://launch.usegalaxy.org/login).

### Getting an API token

To interact with the API programmatically you'll need to first obtain an API
token.

1. First, [login to CloudLaunch](https://launch.usegalaxy.org/login). You can
login with several OpenID Connect providers here.
2. Go to the
[api-token-auth](https://launch.usegalaxy.org/cloudlaunch/api/v1/auth/api-token-auth/).
The response should look something like:
    ```
    {"token":"b38faadf2ef6d59ce46711ed73e99d6..."}
    ```
    Although obviously you'll see a different token. You'll need this token for the following API interaction methods.


### Using cURL

### Using coreapi

### Using cloudlaunch-cli

