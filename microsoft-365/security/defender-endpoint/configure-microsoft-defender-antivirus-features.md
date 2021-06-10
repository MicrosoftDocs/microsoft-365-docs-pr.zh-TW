---
title: 設定 Microsoft Defender 防毒軟體功能
description: 您可以使用 Intune、Microsoft Endpoint Configuration Manager、群組原則和 PowerShell 設定 Microsoft Defender 防毒軟體功能。
keywords: Microsoft Defender 防毒軟體，反惡意程式碼，安全性，Defender，configure，configuration，Config Manager，Microsoft Endpoint Configuration Manager，SCCM，Intune，MDM，mobile 裝置管理，GP，群組原則，PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6ef9a2c34a88d7c9f5506c681088db9dc84cb0cc
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789024"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="a90c5-104">設定 Microsoft Defender 防毒軟體功能</span><span class="sxs-lookup"><span data-stu-id="a90c5-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a90c5-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a90c5-105">**Applies to:**</span></span>

- [<span data-ttu-id="a90c5-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a90c5-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a90c5-107">您可以使用一些工具設定 Microsoft Defender 防毒軟體，例如：</span><span class="sxs-lookup"><span data-stu-id="a90c5-107">You can configure Microsoft Defender Antivirus with a number of tools, such as:</span></span>

- <span data-ttu-id="a90c5-108">包含 Microsoft Intune 和 Microsoft Endpoint Configuration Manager 的 Microsoft 端點管理員 () </span><span class="sxs-lookup"><span data-stu-id="a90c5-108">Microsoft Endpoint Manager (which includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
- <span data-ttu-id="a90c5-109">群組原則</span><span class="sxs-lookup"><span data-stu-id="a90c5-109">Group Policy</span></span>
- <span data-ttu-id="a90c5-110">PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a90c5-110">PowerShell cmdlets</span></span>
- <span data-ttu-id="a90c5-111">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="a90c5-111">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="a90c5-112">您可以設定下列廣泛的功能類別：</span><span class="sxs-lookup"><span data-stu-id="a90c5-112">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="a90c5-113">雲端提供的保護。</span><span class="sxs-lookup"><span data-stu-id="a90c5-113">Cloud-delivered protection.</span></span> <span data-ttu-id="a90c5-114">請參閱[雲端提供的保護和 Microsoft Defender 防毒軟體](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a90c5-114">See [Cloud-delivered protection and Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span></span>
 
- <span data-ttu-id="a90c5-115">Always on 即時保護，包含行為、啟發式和機器學習型保護。</span><span class="sxs-lookup"><span data-stu-id="a90c5-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection.</span></span> <span data-ttu-id="a90c5-116">請參閱 [設定行為、啟發式和即時保護](configure-protection-features-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="a90c5-116">See [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).</span></span>

- <span data-ttu-id="a90c5-117">使用者如何與個別端點上的用戶端互動。</span><span class="sxs-lookup"><span data-stu-id="a90c5-117">How end users interact with the client on individual endpoints.</span></span> <span data-ttu-id="a90c5-118">請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="a90c5-118">See the following resources:</span></span>
   
   - [<span data-ttu-id="a90c5-119">防止使用者看到或與 Microsoft Defender 防毒軟體使用者介面互動</span><span class="sxs-lookup"><span data-stu-id="a90c5-119">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md)

   - [<span data-ttu-id="a90c5-120">防止或允許使用者本機修改 Microsoft Defender 防毒軟體原則設定</span><span class="sxs-lookup"><span data-stu-id="a90c5-120">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) 

> [!TIP]
> <span data-ttu-id="a90c5-121">請參閱 [管理及設定工具的參考主題](configuration-management-reference-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="a90c5-121">Review [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md).</span></span>