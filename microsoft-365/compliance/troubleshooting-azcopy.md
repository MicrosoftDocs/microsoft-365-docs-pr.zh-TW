---
title: 在高级电子数据展示中排除 AzCopy 的故障
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 8033ad24d4e2fd742d5e66f75f6bca77d4796d1d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077455"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>在高级电子数据展示中排除 AzCopy 的故障

在高级电子数据展示中加载非 Office 365 数据或文档以进行错误修正时，用户界面会提供 Azure AzCopy 命令，该命令包含参数，其中包含要上载的文件的存储位置和 Azure 存储文件将上载到的位置。 要上载文档，请复制此命令，然后在本地计算机上的命令提示符中运行它。  以下屏幕截图显示了 AzCopy 命令的示例：

![上传非 Office 365 文件](media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

通常，在运行它时，提供的命令可以正常工作。 但是，在某些情况下，显示的命令可能无法成功运行。 以下是一些可能的原因。

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>支持的 AzCopy 版本未安装在本地计算机上

此时，您必须使用 AzCopy v8.1 在高级电子数据展示中加载非 Office 365 数据。 如果不使用 AzCopy v8.1，则显示在上一个屏幕截图**中显示的"上传文件"** 页上的 AzCopy 命令将返回错误。 要安装此版本，请参阅[在 Windows 上使用 AzCopy v8.1 传输数据。](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy 未安装在本地计算机上，或者未安装在默认位置

如果未安装 AzCopy 或安装在默认安装位置以外的位置（即`%ProgramFiles(x86)%`），则在运行 AzCopy 命令时可能会收到以下错误：

    The system cannot find the path specified.

如果本地计算机上未安装 AzCopy，则可以[在此处](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)安装 。 请确保将其安装在默认位置。

如果安装了 AzCopy，但它安装在与默认位置不同的位置，则可以复制该命令，将其粘贴到文本文件，然后将路径更改为安装 AzCopy 的位置。 例如，如果 Azcopy 位于`%ProgramFiles%`中，则可以将命令的第一部分从`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe`更改为`%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`。 进行此更改后，请从文本文件复制它，然后运行命令提示符。

> [!TIP]
> 如果 AzCopy 安装在默认安装位置的其他位置，请考虑卸载它，然后在默认位置重新安装它。 这将有助于防止将来出现此问题。
