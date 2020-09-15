---
title: 適用於 Office 伺服器的 GDPR
description: 了解如何解決 Office 內部部署伺服器中的一般資料保護規定 (GDPR) 需求。
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5ee42a12f65ad5eff0a33ef2b61d328ebdc7af3e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547329"
---
# <a name="gdpr-for-office-on-premises-servers"></a><span data-ttu-id="b94a0-103">適用於內部部署 Office 伺服器的 GDPR</span><span class="sxs-lookup"><span data-stu-id="b94a0-103">GDPR for Office on-premises Servers</span></span>

<span data-ttu-id="b94a0-p101">一般資料保護規定 (GDPR) 引進了適用於組織的需求，以保護個人資料並且適當地回應資料主體要求。這一系列的文章提供內部部署工作負載的建議方法：</span><span class="sxs-lookup"><span data-stu-id="b94a0-p101">The General Data Protection Regulation (GDPR) introduces requirements for organizations to protect personal data and respond appropriately to data subject requests. This series of articles provides recommended approaches for on-premises workloads:</span></span>

- [<span data-ttu-id="b94a0-106">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="b94a0-106">SharePoint Server</span></span>](gdpr-for-sharepoint-server.md)

- [<span data-ttu-id="b94a0-107">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="b94a0-107">Exchange Server</span></span>](gdpr-for-exchange-server.md)

- [<span data-ttu-id="b94a0-108">商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="b94a0-108">Skype for Business Server</span></span>](gdpr-for-skype-for-business-server.md)

- [<span data-ttu-id="b94a0-109">Project Server</span><span class="sxs-lookup"><span data-stu-id="b94a0-109">Project Server</span></span>](gdpr-for-project-server.md)

- [<span data-ttu-id="b94a0-110">Office Web Apps Server 和 Office Online Server</span><span class="sxs-lookup"><span data-stu-id="b94a0-110">Office Web Apps Server and Office Online Server</span></span>](gdpr-for-office-online-server.md)

- [<span data-ttu-id="b94a0-111">內部部署檔案共用</span><span class="sxs-lookup"><span data-stu-id="b94a0-111">On-premises file shares</span></span>](gdpr-for-on-premises-file-shares.md)

<span data-ttu-id="b94a0-112">如需有關 GDPR 以及 Microsoft 可以如何協助您的詳細資訊，請參閱 [Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview
)。</span><span class="sxs-lookup"><span data-stu-id="b94a0-112">For more information about the GDPR and how Microsoft can help you, see the [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview
).</span></span>

<span data-ttu-id="b94a0-p102">在您使用內部部署資料進行任何工作之前，請洽詢您的法務和合規性小組，以尋求指引並且深入了解使用個人資料的現有分類結構描述和方法。Microsoft 在位於 [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>) 的「Microsoft GDPR 資料探索工具組」中提供開發和擴充分類結構描述的建議。這個工具組也會說明將內部部署資料移至雲端 (您可以在其中使用更複雜的資料控管功能) 的方法。本節中的這篇文章提供對於要保留在內部部署的資料的建議。</span><span class="sxs-lookup"><span data-stu-id="b94a0-p102">Before doing any work with on-premises data, consult with your legal and compliance teams to seek guidance and to learn about existing classification schemas and approaches to working with personal data. Microsoft provides recommendations for developing and extending classifications schemas in the Microsoft GDPR Data Discovery Toolkit at [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). This toolkit also describes approaches for moving on-premises data to the cloud where you can use more sophisticated data governance capabilities, if this is desired. The articles in this section provide recommendations for data that is intended to remain on premises.</span></span>

<span data-ttu-id="b94a0-p103">下圖列出在各個工作負載中使用的建議功能，以探索、分類、保護及監視個人資料。請參閱本節中的文章以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b94a0-p103">The following illustration lists recommended capabilities to use across each of these workloads to discover, classify, protect, and monitor personal data. See the articles in this section for more information.</span></span>

![圖表描述如何在各個工作負載中探索、分類、保護及監控個人資料功能](../media/gdpr-for-office-servers-image1.png)

## <a name="illustration-description"></a><span data-ttu-id="b94a0-120">圖例說明</span><span class="sxs-lookup"><span data-stu-id="b94a0-120">Illustration description</span></span>

<span data-ttu-id="b94a0-121">為了便於存取，下表會在圖例中提供相同的範例。</span><span class="sxs-lookup"><span data-stu-id="b94a0-121">For accessibility, the following table provides the same examples in the illustration.</span></span>

****

|<span data-ttu-id="b94a0-122">動作</span><span class="sxs-lookup"><span data-stu-id="b94a0-122">Action</span></span>|<span data-ttu-id="b94a0-123">Windows Server 檔案共用</span><span class="sxs-lookup"><span data-stu-id="b94a0-123">Windows Server file shares</span></span>|<span data-ttu-id="b94a0-124">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="b94a0-124">SharePoint Server</span></span>|<span data-ttu-id="b94a0-125">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="b94a0-125">Exchange Server</span></span>|<span data-ttu-id="b94a0-126">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="b94a0-126">Skype for Business</span></span>|<span data-ttu-id="b94a0-127">Project Server</span><span class="sxs-lookup"><span data-stu-id="b94a0-127">Project Server</span></span>|
|---|---|---|---|---|---|
|<span data-ttu-id="b94a0-128">探索</span><span class="sxs-lookup"><span data-stu-id="b94a0-128">Discover</span></span>|<span data-ttu-id="b94a0-129">Azure 資訊保護掃描器<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b94a0-129">Azure Information Protection scanner<sup>\*</sup></span></span>|<span data-ttu-id="b94a0-130">搜尋中心或電子文件探索 (在分類資料之後)</span><span class="sxs-lookup"><span data-stu-id="b94a0-130">Search Center or eDiscovery (after data is classified)</span></span> <br/><br/> <span data-ttu-id="b94a0-131">Azure 資訊保護掃描器<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b94a0-131">Azure Information Protection scanner<sup>\*</sup></span></span>|<span data-ttu-id="b94a0-132">Exchange eDiscovery 入口網站</span><span class="sxs-lookup"><span data-stu-id="b94a0-132">Exchange eDiscovery Portal</span></span>|<span data-ttu-id="b94a0-133">Exchange eDiscovery 入口網站</span><span class="sxs-lookup"><span data-stu-id="b94a0-133">Exchange eDiscovery portal</span></span>|<span data-ttu-id="b94a0-134">用於探索和匯出的 SQL 指令碼</span><span class="sxs-lookup"><span data-stu-id="b94a0-134">SQL scripts for discovery and exporting</span></span>|
|<span data-ttu-id="b94a0-135">分類</span><span class="sxs-lookup"><span data-stu-id="b94a0-135">Classify</span></span>|<span data-ttu-id="b94a0-136">Azure 資訊保護掃描器<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b94a0-136">Azure Information Protection scanner<sup>\*</sup></span></span> <br/><br/> <span data-ttu-id="b94a0-137">Office 365 敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="b94a0-137">Office 365 sensitive information types</span></span>|<span data-ttu-id="b94a0-138">Azure 資訊保護掃描器<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b94a0-138">Azure Information Protection scanner<sup>\*</sup></span></span> <br/><br/> <span data-ttu-id="b94a0-139">Office 365 敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="b94a0-139">Office 365 sensitive information types</span></span>|<span data-ttu-id="b94a0-140">Exchange 保留標記和保留原則</span><span class="sxs-lookup"><span data-stu-id="b94a0-140">Exchange retention tags and retention policies</span></span>|<span data-ttu-id="b94a0-141">Exchange 保留標記和保留原則</span><span class="sxs-lookup"><span data-stu-id="b94a0-141">Exchange retention tags and retention policies</span></span>||
|<span data-ttu-id="b94a0-142">保護</span><span class="sxs-lookup"><span data-stu-id="b94a0-142">Protect</span></span>||<span data-ttu-id="b94a0-143">Exchange Server 資料外洩防護規則</span><span class="sxs-lookup"><span data-stu-id="b94a0-143">Exchange Server data loss prevention rules</span></span> <br/><br/> <span data-ttu-id="b94a0-144">權限，文件庫的 IRM 保護</span><span class="sxs-lookup"><span data-stu-id="b94a0-144">Permissions, IRM-protection for libraries</span></span>|<span data-ttu-id="b94a0-145">Exchange Server 資料外洩防護規則</span><span class="sxs-lookup"><span data-stu-id="b94a0-145">Exchange Server data loss prevention rules</span></span> <br/><br/> <span data-ttu-id="b94a0-146">與 Exchange Server 的 IRM 整合</span><span class="sxs-lookup"><span data-stu-id="b94a0-146">IRM integration with Exchange Server</span></span>|||
|<span data-ttu-id="b94a0-147">監視</span><span class="sxs-lookup"><span data-stu-id="b94a0-147">Monitor</span></span>|<span data-ttu-id="b94a0-148">整合記錄與 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="b94a0-148">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="b94a0-149">整合記錄與 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="b94a0-149">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="b94a0-150">整合記錄與 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="b94a0-150">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="b94a0-151">整合記錄與 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="b94a0-151">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="b94a0-152">整合記錄與 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="b94a0-152">Integrate logs with SIEM tools</span></span>|
|

<span data-ttu-id="b94a0-153"><sup>\*</sup> 請注意，保護會加密檔案。</span><span class="sxs-lookup"><span data-stu-id="b94a0-153"><sup>\*</sup> Note that protection encrypts the file.</span></span> <span data-ttu-id="b94a0-154">因此，SharePoint Server 在保護的檔案中找不到敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="b94a0-154">Consequently, SharePoint Server can't find the sensitive information types in protected files.</span></span>
