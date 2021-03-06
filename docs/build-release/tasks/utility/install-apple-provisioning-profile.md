---
title: Install Apple Provisioning Profile
description: Install an Apple provisioning profile required to build on a macOS agent in VSTS and Team Foundation Server TFS
ms.prod: vs-devops-alm
ms.technology: vs-devops-build
ms.assetid: 0f9f66ca-250e-40fd-9678-309bcd439d5e
ms.manager: douge
ms.author: alewis
ms.reviewer: dastahel
ms.date: 11/14/2017
---
[//]: # (monikerRange: '>= tfs-2018')

# Utility: Install Apple Provisioning Profile

**VSTS** | **TFS 2018**

![](../build/_img/xcode.png) Install an Apple provisioning profile required to build on a macOS agent

You can use this task to install provisioning profiles needed to build iOS Apps, Apple WatchKit Apps and App Extensions.

You can install an Apple provisioning profile that is:
- Stored as a [secure file](../../concepts/library/secure-files.md) on the server. 
- (**VSTS**) Committed to the source repository or copied to a local path on the macOS agent. We recommend encrypting the provisioning profiles if you are committing them to the source repository. The **Decrypt File** task can be used to decrypt them during a build or release.

## Demands

xcode

## Arguments

| Argument | Description |
| -------- | ----------- |
| Provisioning Profile Location (**VSTS**) | Select the location of the provisioning profile to install. The provisioning profile can be uploaded to **Secure Files** or stored in your source repository or a local path on the agent. |
| Provisioning Profile | Select the provisioning profile that was uploaded to **Secure Files** to install on the macOS agent (or) Select the provisioning profile from the source repository or specify the local path to a provisioning profile on the macOS agent.|
| Remove Profile After Build | Select to specify that the provisioning profile should be removed from the agent after the build or release is complete. |

[//]: # (::: moniker range="vsts")

## YAML snippet

(VSTS-only)

```YAML
- task: InstallAppleProvisioningProfile@1
  inputs:
#   provisioningProfileLocation: secureFiles # secureFiles (default), sourceRepository
    provProfileSecureFile:
    provProfileSourceRepository:
#   removeProfile: True
```

[//]: # (::: moniker-end)
