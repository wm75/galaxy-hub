---
autotoc: true
---

[![ToolShed](/src/images/logos/ToolShed.jpg)](http://toolshed.g2.bx.psu.edu)


# A single tool or a suite of tools per repository?

Many tool developers in the Galaxy community question the best way to organize tools in their Tool Shed repositories. Some groups have developed a large number of tools to allow their labs to perform analyses in Galaxy and took the approach of including all related tools in a single repository in the Tool Shed. Others have chosen to restrict each repository to include a single tool. What is the "best practice"? With the use of repository relationships a single tool per repository is the best approach.

## The benefits of a single tool per repository

* Restricting a repository to include a single tool provides more flexibility to Galaxy administrators to install only those specific tools in which their users have interest. Sometimes installing a suite of tools in order to get only one or two of them is not optimal.

* Some time in the future, Galaxy workflows may provide the ability to search for tools defined in the workflow that are not available in the Galaxy instance. Ideally, the Galaxy administrator will be able to locate and install only the precise list of missing tools in order to enable the workflow to run. For example, assume a user imported a workflow into their local Galaxy instance that was developed by someone else in a different Galaxy instance. The Galaxy workflow UI may provide a feature that searches available Tool Sheds for the tools required by the imported workflow that are not available in the Galaxy instance. Restricting repository contents to single tools would enable installation of only those missing tools required by the workflow.

* Tool Shed repositories that include tools have certain mercurial change set revisions that are installable into a local Galaxy instance. These revisions are defined by the versions of the tools included in the repository. Repositories that are restricted to contain a single tool will ensure that a new revision installation will be required only when that tool version changes. Repositories that include multiple tools require a new installation revision when the version of any one of the tools changes, possibly resulting in multiple versions of the same tool installed into a single Galaxy instance. Of course, Galaxy will load only a single instance of a tool version into the tool panel, but the tool and related files will still be installed on disk multiple times.

* If tools are not intended to provide meaningful analyses on their own, but are designed to function with other tools, restricting a repository to a single tool will require a Galaxy administrator to install multiple repositories in order to provide all necessary tools to their users. However, the Tool Shed provides a feature that we call **simple repository dependencies** that streamline this process. Repositories in the Tool Shed can contain a file named **repository_dependencies.xml** that define dependency relationships between repositories. For example, the current **emboss_datatypes** repository in the main Galaxy Tool Shed is defined as a required repository for the current **emboss_5** repository in the same Tool Shed via the inclusion of the file named **repository_dependencies.xml** in the **emboss_5** repository. So when the **emboss_5** repository is installed into Galaxy, the **emboss_datatypes** repository will be automatically installed along with it if the Galaxy administrator elects to do so.

* In some cases multiple tools are not intended to provide meaningful analyses on their own, but are designed to function with other tools in the suite. In these cases, it makes sense for all tools to be installed into a Galaxy instance, and thus, the tools may all be included in a single repository. In these cases, the Tool Shed provides the ability to define a suite of repositories that will be installed by installing the single repository that contains only one file named **repository_dependencies.xml** which defines multiple separate repositories that should be installed. Each of these repositories could contain a single tool, allowing a Galaxy administrator to install each tool separately. If the administrator chooses to install the "tool suite" repository, each separate repository would be automatically installed, providing the entire suite of tools with the single installation. This feature eliminates the benefits of including a suite of tools in a single repository.

# Related pages

* [Tool Shed features for Galaxy tools](/src/toolshed-tool-features/index.md) - the primary intent of the Tool Shed is for sharing Galaxy tools, workflows, and other useful Galaxy utilities. Galaxy tools are generally developed within a local Galaxy environment, proven to be functionally correct within that environment, and then uploaded to a Tool Shed for sharing. With a couple of exceptions, tool features are defined within the Galaxy framework and have nothing to do with the Tool Shed. This document describes those exceptions.

* [Including installation information or 3rd-party tool dependency licensing information in your repository](/src/toolshed-readme-files/index.md) - this document provides the details for a simple feature of the Tool Shed that enables displaying the license information (or possibly other kinds of information) for tools included in a repository.

* [Tool Shed features for Galaxy datatypes](/src/toolshed-datatypes-features/index.md) - this document provides information for how to include your proprietary Galaxy datatypes (upon which your Galaxy tools depend) in a repository in the Tool Shed.

* [Defining repository dependencies](/src/defining-repository-dependencies/index.md) - this document provides information about how to define dependencies for a repository on any number of additional, separate repositories.

* [Including functional test for your tools](/src/testing-installed-tools/index.md) - this document provides details for including input and output datasets in your repository for functional tests defined in tool config files included in the repository.

* [Enabling workflow sharing](/src/toolshed-workflow-sharing/index.md) - this document describes how the Tool Shed enables sharing Galaxy workflows.
