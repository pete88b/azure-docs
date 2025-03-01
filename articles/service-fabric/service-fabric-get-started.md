---
title: Set up a Windows development environment
description: Install the runtime, SDK, and tools and create a local development cluster. After completing this setup, you will be ready to build applications on Windows.
ms.topic: how-to
ms.author: tomcassidy
author: tomvcassidy
ms.service: service-fabric
services: service-fabric
ms.date: 07/14/2022
---

# Prepare your development environment on Windows

> [!div class="op_single_selector"]
> * [Windows](service-fabric-get-started.md) 
> * [Linux](service-fabric-get-started-linux.md)
> * [Mac OS X](service-fabric-get-started-mac.md)
>
>

To build and run [Azure Service Fabric applications][1] on your Windows development machine, install the Service Fabric runtime, SDK, and tools. You also need to [enable execution of the Windows PowerShell scripts](#enable-powershell-script-execution) included in the SDK.

## Prerequisites

Ensure you are using a supported [Windows version](service-fabric-versions.md#supported-windows-versions-and-support-end-date).

## Install the SDK and tools

Web Platform Installer (WebPI) is the recommended way to install the SDK and tools. If you receive runtime errors using WebPI, you can also find direct links to the installers in the release notes for a specific Service Fabric release. The release notes can be found in the various release announcements on the [Service Fabric team blog](https://techcommunity.microsoft.com/t5/azure-service-fabric/bg-p/Service-Fabric).

WebPI may already be installed on your computer. Search for it by using the Windows key. If it's not present, you can [download it here](https://www.microsoft.com/web/downloads/platform.aspx). **NB** The page mentions that the tool will be retired fairly soon (July 1, 2022), so you may need to look for alternative ways to install this after that date. Stay tuned!

> [!NOTE]
> Local Service Fabric development cluster upgrades are not supported.

### To use Visual Studio 2017 or 2019

The Service Fabric Tools are part of the Azure Development workload in Visual Studio 2019 and 2017. Enable this workload as part of your Visual Studio installation.
In addition, you need to install the Microsoft Azure Service Fabric SDK and runtime using Web Platform Installer.

* [Install the Microsoft Azure Service Fabric SDK][core-sdk]

### SDK installation only

If you only need the SDK, you can install this package:

* [Install the Microsoft Azure Service Fabric SDK][core-sdk]

The current versions are:

* Service Fabric SDK and Tools 6.0.1048
* Service Fabric runtime 9.0.1048

For a list of supported versions, see [Service Fabric versions](service-fabric-versions.md)

> [!NOTE]
> Single machine clusters (OneBox) are not supported for Application or Cluster upgrades; delete the OneBox cluster and recreate it if you need to perform a Cluster upgrade, or have any issues performing an Application upgrade. 

## Enable PowerShell script execution

Service Fabric uses Windows PowerShell scripts for creating a local development cluster and for deploying applications from Visual Studio. By default, Windows blocks these scripts from running. To enable them, you must modify your PowerShell execution policy. Open PowerShell as an administrator and enter the following command:

```powershell
Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Force -Scope CurrentUser
```

## Install Docker (optional)

[Service Fabric is a container orchestrator](service-fabric-containers-overview.md) for deploying microservices across a cluster of machines. To run Windows container applications on your local development cluster, you must first install Docker for Windows. Get [Docker CE for Windows (stable)](https://store.docker.com/editions/community/docker-ce-desktop-windows?tab=description). After installing and starting Docker, right-click on the tray icon and select **Switch to Windows containers**. This step is required to run Docker images based on Windows.

## Next steps

Now that you've finished setting up your development environment, start building and running apps.

* [Learn how to create, deploy, and manage applications](service-fabric-tutorial-create-dotnet-app.md)
* [Learn about the programming models: Reliable Services and Reliable Actors](service-fabric-choose-framework.md)
* [Check out the Service Fabric code samples on GitHub](/samples/browse/?products=azure)
* [Visualize your cluster by using Service Fabric Explorer](service-fabric-visualizing-your-cluster.md)
* [Prepare a Linux development environment on Windows](service-fabric-local-linux-cluster-windows.md)
* Learn about [Service Fabric support options](service-fabric-support.md)

[1]: https://azure.microsoft.com/campaigns/service-fabric/ "Service Fabric campaign page"
[2]: https://go.microsoft.com/fwlink/?LinkId=517106 "VS RC"
[full-bundle-vs2015]:https://www.microsoft.com/web/handlers/webpi.ashx?command=getinstallerredirect&appid=MicrosoftAzure-ServiceFabric-VS2015 "VS 2015 WebPI link"
[full-bundle-dev15]:https://www.microsoft.com/web/handlers/webpi.ashx?command=getinstallerredirect&appid=MicrosoftAzure-ServiceFabric-Dev15 "Dev15 WebPI link"
[core-sdk]:https://www.microsoft.com/web/handlers/webpi.ashx?command=getinstallerredirect&appid=MicrosoftAzure-ServiceFabric-CoreSDK "Core SDK WebPI link"
[powershell5-download]:https://www.microsoft.com/download/details.aspx?id=54616
