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
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="4f058-102">在高级电子数据展示中排除 AzCopy 的故障</span><span class="sxs-lookup"><span data-stu-id="4f058-102">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="4f058-103">在高级电子数据展示中加载非 Office 365 数据或文档以进行错误修正时，用户界面会提供 Azure AzCopy 命令，该命令包含参数，其中包含要上载的文件的存储位置和 Azure 存储文件将上载到的位置。</span><span class="sxs-lookup"><span data-stu-id="4f058-103">When loading non-Office 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="4f058-104">要上载文档，请复制此命令，然后在本地计算机上的命令提示符中运行它。</span><span class="sxs-lookup"><span data-stu-id="4f058-104">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="4f058-105">以下屏幕截图显示了 AzCopy 命令的示例：</span><span class="sxs-lookup"><span data-stu-id="4f058-105">The follow screenshot shows an example of an AzCopy command:</span></span>

![上传非 Office 365 文件](media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="4f058-107">通常，在运行它时，提供的命令可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="4f058-107">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="4f058-108">但是，在某些情况下，显示的命令可能无法成功运行。</span><span class="sxs-lookup"><span data-stu-id="4f058-108">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="4f058-109">以下是一些可能的原因。</span><span class="sxs-lookup"><span data-stu-id="4f058-109">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="4f058-110">支持的 AzCopy 版本未安装在本地计算机上</span><span class="sxs-lookup"><span data-stu-id="4f058-110">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="4f058-111">此时，您必须使用 AzCopy v8.1 在高级电子数据展示中加载非 Office 365 数据。</span><span class="sxs-lookup"><span data-stu-id="4f058-111">At this time, you must use AzCopy v8.1 to load non-Office 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="4f058-112">如果不使用 AzCopy v8.1，则显示在上一个屏幕截图**中显示的"上传文件"** 页上的 AzCopy 命令将返回错误。</span><span class="sxs-lookup"><span data-stu-id="4f058-112">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="4f058-113">要安装此版本，请参阅[在 Windows 上使用 AzCopy v8.1 传输数据。](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)</span><span class="sxs-lookup"><span data-stu-id="4f058-113">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="4f058-114">AzCopy 未安装在本地计算机上，或者未安装在默认位置</span><span class="sxs-lookup"><span data-stu-id="4f058-114">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="4f058-115">如果未安装 AzCopy 或安装在默认安装位置以外的位置（即`%ProgramFiles(x86)%`），则在运行 AzCopy 命令时可能会收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="4f058-115">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

    The system cannot find the path specified.

<span data-ttu-id="4f058-116">如果本地计算机上未安装 AzCopy，则可以[在此处](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)安装 。</span><span class="sxs-lookup"><span data-stu-id="4f058-116">If AzCopy isn't installed on the local computer, you can install from [here](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="4f058-117">请确保将其安装在默认位置。</span><span class="sxs-lookup"><span data-stu-id="4f058-117">Be sure to install it in the default location.</span></span>

<span data-ttu-id="4f058-118">如果安装了 AzCopy，但它安装在与默认位置不同的位置，则可以复制该命令，将其粘贴到文本文件，然后将路径更改为安装 AzCopy 的位置。</span><span class="sxs-lookup"><span data-stu-id="4f058-118">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="4f058-119">例如，如果 Azcopy 位于`%ProgramFiles%`中，则可以将命令的第一部分从`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe`更改为`%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`。</span><span class="sxs-lookup"><span data-stu-id="4f058-119">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="4f058-120">进行此更改后，请从文本文件复制它，然后运行命令提示符。</span><span class="sxs-lookup"><span data-stu-id="4f058-120">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="4f058-121">如果 AzCopy 安装在默认安装位置的其他位置，请考虑卸载它，然后在默认位置重新安装它。</span><span class="sxs-lookup"><span data-stu-id="4f058-121">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="4f058-122">这将有助于防止将来出现此问题。</span><span class="sxs-lookup"><span data-stu-id="4f058-122">This will help prevent this issue in the future.</span></span>
