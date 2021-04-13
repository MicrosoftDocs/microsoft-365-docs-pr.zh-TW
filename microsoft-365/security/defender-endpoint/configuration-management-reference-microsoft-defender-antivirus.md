---
title: 在您的企業中管理 Windows Defender
description: 瞭解如何使用群組原則、Configuration Manager、PowerShell、WMI、Intune 和命令列來管理 Microsoft Defender AV
keywords: 群組原則，gpo，config manager，sccm，scep，powershell，wmi，intune，defender，防毒程式，反惡意軟體，安全性，保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ad3e8d2fb61eb5a2a350d061f926dd7bff8ae109
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690125"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a><span data-ttu-id="52eb9-104">管理企業中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="52eb9-104">Manage Microsoft Defender Antivirus in your business</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="52eb9-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="52eb9-105">**Applies to:**</span></span>

- [<span data-ttu-id="52eb9-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="52eb9-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="52eb9-107">您可以使用下列工具來管理及設定 Microsoft Defender 防毒程式：</span><span class="sxs-lookup"><span data-stu-id="52eb9-107">You can manage and configure Microsoft Defender Antivirus with the following tools:</span></span>

- <span data-ttu-id="52eb9-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (現在是 Microsoft 端點管理員的一部分) </span><span class="sxs-lookup"><span data-stu-id="52eb9-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (now part of Microsoft Endpoint Manager)</span></span>
- <span data-ttu-id="52eb9-109">[Microsoft 端點 Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) 現在 (Microsoft 端點管理員的一部分) </span><span class="sxs-lookup"><span data-stu-id="52eb9-109">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (now part of Microsoft Endpoint Manager)</span></span>
- [<span data-ttu-id="52eb9-110">群組原則</span><span class="sxs-lookup"><span data-stu-id="52eb9-110">Group Policy</span></span>](./use-group-policy-microsoft-defender-antivirus.md)
- [<span data-ttu-id="52eb9-111">PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="52eb9-111">PowerShell cmdlets</span></span>](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="52eb9-112">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="52eb9-112">Windows Management Instrumentation (WMI)</span></span>](./use-wmi-microsoft-defender-antivirus.md)
- <span data-ttu-id="52eb9-113">[Microsoft 惡意程式碼保護命令列公用程式](./command-line-arguments-microsoft-defender-antivirus.md) (稱為 *mpcmdrun.exe* 公用程式</span><span class="sxs-lookup"><span data-stu-id="52eb9-113">The [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (referred to as the *mpcmdrun.exe* utility</span></span>

<span data-ttu-id="52eb9-114">下列文章提供使用這些工具來管理及設定 Microsoft Defender 防毒程式的進一步資訊、連結及資源。</span><span class="sxs-lookup"><span data-stu-id="52eb9-114">The following articles provide further information, links, and resources for using these tools to manage and configure Microsoft Defender Antivirus.</span></span>

| <span data-ttu-id="52eb9-115">文章</span><span class="sxs-lookup"><span data-stu-id="52eb9-115">Article</span></span> | <span data-ttu-id="52eb9-116">描述</span><span class="sxs-lookup"><span data-stu-id="52eb9-116">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="52eb9-117">使用 Microsoft Intune 和 Microsoft Endpoint Configuration Manager 管理 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="52eb9-117">Manage Microsoft Defender Antivirus with Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>](use-intune-config-manager-microsoft-defender-antivirus.md)|<span data-ttu-id="52eb9-118">使用 Intune 及 Configuration Manager 來部署、管理、報告和設定 Microsoft Defender 防毒程式的資訊</span><span class="sxs-lookup"><span data-stu-id="52eb9-118">Information about using Intune and Configuration Manager to deploy, manage, report, and configure Microsoft Defender Antivirus</span></span> |
|[<span data-ttu-id="52eb9-119">使用群組原則設定來管理 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="52eb9-119">Manage Microsoft Defender Antivirus with Group Policy settings</span></span>](use-group-policy-microsoft-defender-antivirus.md)|<span data-ttu-id="52eb9-120">位於 ADMX 範本中的所有群組原則設定清單</span><span class="sxs-lookup"><span data-stu-id="52eb9-120">List of all Group Policy settings located in ADMX templates</span></span> |
|[<span data-ttu-id="52eb9-121">使用 PowerShell Cmdlet 來管理 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="52eb9-121">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)|<span data-ttu-id="52eb9-122">使用 PowerShell Cmdlet 來管理 Microsoft Defender 防毒程式的指示，外加所有 Cmdlet 及允許參數的檔連結</span><span class="sxs-lookup"><span data-stu-id="52eb9-122">Instructions for using PowerShell cmdlets to manage Microsoft Defender Antivirus, plus links to documentation for all cmdlets and allowed parameters</span></span> |
|[<span data-ttu-id="52eb9-123">使用 Windows Management Instrumentation (WMI) 管理 Microsoft Defender 防毒程式 </span><span class="sxs-lookup"><span data-stu-id="52eb9-123">Manage Microsoft Defender Antivirus with Windows Management Instrumentation (WMI)</span></span>](use-wmi-microsoft-defender-antivirus.md)| <span data-ttu-id="52eb9-124">使用 WMI 來管理 Microsoft Defender 防毒程式的指示，加上 WMIv2 APIs (檔的連結，包括所有的類別、方法及屬性) </span><span class="sxs-lookup"><span data-stu-id="52eb9-124">Instructions for using WMI to manage Microsoft Defender Antivirus, plus links to documentation for the WMIv2 APIs (including all classes, methods, and properties)</span></span> |
|[<span data-ttu-id="52eb9-125">使用 mpcmdrun.exe 命令列工具管理 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="52eb9-125">Manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>](command-line-arguments-microsoft-defender-antivirus.md)|<span data-ttu-id="52eb9-126">使用專用命令列工具來管理及使用 Microsoft Defender 防毒程式的指示</span><span class="sxs-lookup"><span data-stu-id="52eb9-126">Instructions on using the dedicated command-line tool to manage and use Microsoft Defender Antivirus</span></span> |