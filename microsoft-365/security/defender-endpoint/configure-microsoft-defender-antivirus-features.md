---
title: 設定 Microsoft Defender 防病毒功能
description: 您可以使用 Intune、Microsoft Endpoint Configuration 管理員、群組原則和 PowerShell 來設定 Microsoft Defender 防病毒功能。
keywords: Microsoft Defender 防毒程式，反惡意程式碼，安全性，Defender，configure，configuration，Config Manager，Microsoft Endpoint Configuration Manager，SCCM，Intune，MDM，mobile 裝置管理，GP，群組原則，PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8503bb5bdd6337ec60390ef1d8e59f6f506fbce2
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765164"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="e3586-104">設定 Microsoft Defender 防病毒功能</span><span class="sxs-lookup"><span data-stu-id="e3586-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e3586-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e3586-105">**Applies to:**</span></span>

- [<span data-ttu-id="e3586-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e3586-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e3586-107">您可以設定 Microsoft Defender 防毒程式的一些工具，包括：</span><span class="sxs-lookup"><span data-stu-id="e3586-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="e3586-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e3586-108">Microsoft Intune</span></span>
- <span data-ttu-id="e3586-109">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e3586-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="e3586-110">群組原則</span><span class="sxs-lookup"><span data-stu-id="e3586-110">Group Policy</span></span>
- <span data-ttu-id="e3586-111">PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e3586-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="e3586-112">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="e3586-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="e3586-113">您可以設定下列廣泛的功能類別：</span><span class="sxs-lookup"><span data-stu-id="e3586-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="e3586-114">雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="e3586-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="e3586-115">Always on 即時保護，包含行為、啟發式和機器學習型保護</span><span class="sxs-lookup"><span data-stu-id="e3586-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="e3586-116">使用者如何與個別端點上的用戶端互動</span><span class="sxs-lookup"><span data-stu-id="e3586-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="e3586-117">下列文章說明在設定 Microsoft Defender 防病毒時，如何執行主要工作。</span><span class="sxs-lookup"><span data-stu-id="e3586-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="e3586-118">每篇文章都包含適用的設定工具 (或工具) 的指示。</span><span class="sxs-lookup"><span data-stu-id="e3586-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="e3586-119">文章</span><span class="sxs-lookup"><span data-stu-id="e3586-119">Article</span></span>  |<span data-ttu-id="e3586-120">描述</span><span class="sxs-lookup"><span data-stu-id="e3586-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="e3586-121">使用 Microsoft 雲端所提供的 Microsoft Defender 防防毒保護</span><span class="sxs-lookup"><span data-stu-id="e3586-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="e3586-122">使用雲端提供的保護，以進行高級、快速、可靠的防病毒偵測。</span><span class="sxs-lookup"><span data-stu-id="e3586-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="e3586-123">設定行為、啟發式和即時保護</span><span class="sxs-lookup"><span data-stu-id="e3586-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="e3586-124">啟用行為基礎、啟發式和即時防防毒保護。</span><span class="sxs-lookup"><span data-stu-id="e3586-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="e3586-125">使用 Microsoft Defender 防毒軟體設定使用者互動</span><span class="sxs-lookup"><span data-stu-id="e3586-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="e3586-126">設定組織中的使用者與 Microsoft Defender 防毒軟體的互動方式、他們看到的通知，以及是否可以覆寫設定。</span><span class="sxs-lookup"><span data-stu-id="e3586-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="e3586-127">您也可以查看 [管理及設定工具的參考主題](configuration-management-reference-microsoft-defender-antivirus.md) 主題，以取得每個工具的概述，以及進一步說明的連結。</span><span class="sxs-lookup"><span data-stu-id="e3586-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>