---
title: 從 Microsoft Cloud Deutschland 進行遷移時的 eDiscovery 體驗相關資訊
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：從 Microsoft Cloud Deutschland 進行遷移的 eDiscovery 遷移步驟。
ms.openlocfilehash: 0128c8563b2043e4ec41d2c5ab1b208bd3977511
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844247"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="21695-103">從 Microsoft Cloud Deutschland 進行遷移時的 eDiscovery 體驗相關資訊</span><span class="sxs-lookup"><span data-stu-id="21695-103">Information about the eDiscovery experience during the migration from Microsoft Cloud Deutschland</span></span>
<span data-ttu-id="21695-104">下列各節提供從 microsoft cloud (德國 Deutschland) 到新德文 datacenter 區域中 Office 365 服務時，有關 eDiscovery 體驗的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="21695-104">The following sections provide additional information about the eDiscovery experience when moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="ediscovery-administration-until-phase-4"></a><span data-ttu-id="21695-105">eDiscovery 管理，直到第4階段</span><span class="sxs-lookup"><span data-stu-id="21695-105">eDiscovery administration until phase 4</span></span>
<span data-ttu-id="21695-106">在第4階段之前，安全性與合規性中心會完全可用。</span><span class="sxs-lookup"><span data-stu-id="21695-106">Until phase 4, the Security and Compliance Center will be fully available.</span></span> <span data-ttu-id="21695-107">所有內容仍會保留在 Microsoft 雲端德國，而且可由 Microsoft Cloud 德國安全性與合規性中心 (加以管理 https://protection.office.de/) 。</span><span class="sxs-lookup"><span data-stu-id="21695-107">All content still remains in the Microsoft Cloud Germany and is manageable by the Microsoft Cloud Germany Security and Compliance Center (https://protection.office.de/).</span></span>

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a><span data-ttu-id="21695-108">階段4之間的 eDiscovery 體驗，直到階段9結束</span><span class="sxs-lookup"><span data-stu-id="21695-108">eDiscovery experience between phase 4 until the the end of phase 9</span></span>
<span data-ttu-id="21695-109">從第4階段開始直到階段9完成，「電子檔探索」搜尋會失敗，或是傳回已遷移之 SharePoint Online、商務用 OneDrive 及 Exchange Online 位置的0個結果。</span><span class="sxs-lookup"><span data-stu-id="21695-109">From the beginning of phase 4 until phase 9 is completed, eDiscovery searches will fail or return 0 results for SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated.</span></span>

> [!NOTE]
> <span data-ttu-id="21695-110">在遷移期間，客戶可以繼續在 [安全性 & 規範中心](/microsoft-365/compliance/manage-legal-investigations)（包括 [內容搜尋](/microsoft-365/compliance/search-for-content)）中建立案例、保留、搜尋和匯出。</span><span class="sxs-lookup"><span data-stu-id="21695-110">During migration, customers can continue to create cases, holds, searches, and exports in the [Security & Compliance Center](/microsoft-365/compliance/manage-legal-investigations), including [Content Search](/microsoft-365/compliance/search-for-content).</span></span> <span data-ttu-id="21695-111">不過，針對已遷移的 SharePoint 線上、商務用 OneDrive 和 Exchange Online 位置進行搜尋會傳回0個結果或產生錯誤。</span><span class="sxs-lookup"><span data-stu-id="21695-111">However, searches against SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated will either return 0 results or produce an error.</span></span>

<span data-ttu-id="21695-112">在遷移期間，如果搜尋傳回零結果或發生錯誤，請在線上 SharePoint 執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="21695-112">In the event that a search returns zero results or an error during migration, please take the following action for SharePoint Online:</span></span>

- <span data-ttu-id="21695-113">遵循[從 OneDrive 或 SharePoint 下載檔案及資料夾](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)中的指示，直接從 SharePoint 線上或商務用 OneDrive 網站下載網站。</span><span class="sxs-lookup"><span data-stu-id="21695-113">Download sites directly from the SharePoint Online or OneDrive for Business site by following the instructions in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span></span> <span data-ttu-id="21695-114">此方法將需要 SharePoint 線上系統管理員許可權或網站的唯讀許可權。</span><span class="sxs-lookup"><span data-stu-id="21695-114">This method will require SharePoint Online administrator permissions or read-only permissions on the site.</span></span>
- <span data-ttu-id="21695-115">若超出限制（[從 OneDrive 或 SharePoint 下載檔案及資料夾](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)中所述），客戶可以遵循[SharePoint 同步處理的指導方針和 Teams 檔案與您的電腦](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)，使用商務用 OneDrive 同步處理用戶端。</span><span class="sxs-lookup"><span data-stu-id="21695-115">If limits are exceeded, as explained in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), customers can use the OneDrive for Business sync client by following the guidance in [Sync SharePoint and Teams files with your computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88).</span></span>

- <span data-ttu-id="21695-116">如需詳細資訊，請參閱[Exchange Server 中的就地電子檔探索](/Exchange/policy-and-compliance/ediscovery/ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="21695-116">For more information, see  [In-Place eDiscovery in Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery).</span></span>


## <a name="ediscovery-administration-after-phase-9"></a><span data-ttu-id="21695-117">階段9之後的 eDiscovery 管理</span><span class="sxs-lookup"><span data-stu-id="21695-117">eDiscovery administration after phase 9</span></span>

<span data-ttu-id="21695-118">**適用于：** 所有使用 eDiscovery 的客戶</span><span class="sxs-lookup"><span data-stu-id="21695-118">**Applies to:** All customers using eDiscovery</span></span>

<span data-ttu-id="21695-119">在階段9中，移至新的德國資料中心區域的最後步驟將會完成。</span><span class="sxs-lookup"><span data-stu-id="21695-119">In phase 9, the final steps for moving to the new German datacenter region will be completed.</span></span> <span data-ttu-id="21695-120">在這個階段，將會遷移所有剩餘的服務元件。</span><span class="sxs-lookup"><span data-stu-id="21695-120">In this phase, all remaining service components will be migrated.</span></span>
<span data-ttu-id="21695-121">在階段9之後，使用 Microsoft 雲端德國的安全性與合規性中心 (protection.office.de) 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="21695-121">After phase 9, using the Security and Compliance Center in Microsoft Cloud Germany (protection.office.de) is no longer supported.</span></span> <span data-ttu-id="21695-122">請改為使用新的「 [安全中心](https://security.microsoft.com/) 」或「 [合規性中心](https://compliance.microsoft.com/) 」。</span><span class="sxs-lookup"><span data-stu-id="21695-122">Please use the new [Security Center](https://security.microsoft.com/) or [Compliance Center](https://compliance.microsoft.com/) instead.</span></span> <span data-ttu-id="21695-123">所有資料都已遷移至新的系統管理員入口網站。</span><span class="sxs-lookup"><span data-stu-id="21695-123">All data have been migrated to the new admin portals.</span></span>

| <span data-ttu-id="21695-124">步驟 (s) </span><span class="sxs-lookup"><span data-stu-id="21695-124">Step(s)</span></span> | <span data-ttu-id="21695-125">描述</span><span class="sxs-lookup"><span data-stu-id="21695-125">Description</span></span> | <span data-ttu-id="21695-126">影響</span><span class="sxs-lookup"><span data-stu-id="21695-126">Impact</span></span> |
|:-------|:-------|:-------|
|  <span data-ttu-id="21695-127">所有 SharePoint 線上、商務用 OneDrive 和 Exchange Online 位置都與安全性與合規性中心 (SCC) 一起遷移。</span><span class="sxs-lookup"><span data-stu-id="21695-127">All SharePoint Online, OneDrive for Business, and Exchange Online locations have been migrated along with the Security and Compliance Center (SCC).</span></span> | <span data-ttu-id="21695-128">所有 eDiscovery 活動都應該從世界租使用者執行。</span><span class="sxs-lookup"><span data-stu-id="21695-128">All eDiscovery activity should be run from the worldwide tenant.</span></span> <span data-ttu-id="21695-129">搜尋現在會是100% 成功。</span><span class="sxs-lookup"><span data-stu-id="21695-129">Searches will now be 100% successful.</span></span> <span data-ttu-id="21695-130">任何失敗或錯誤都應該遵循正常支援通道。</span><span class="sxs-lookup"><span data-stu-id="21695-130">Any failures or errors should follow normal support channels.</span></span> | <span data-ttu-id="21695-131">無</span><span class="sxs-lookup"><span data-stu-id="21695-131">None</span></span> |
||||

### <a name="ediscovery-retention-policy"></a><span data-ttu-id="21695-132">eDiscovery 保留原則</span><span class="sxs-lookup"><span data-stu-id="21695-132">eDiscovery Retention Policy</span></span>
<span data-ttu-id="21695-133">**適用于：**  所有已套用保留原則的客戶做為預先遷移步驟的一部分</span><span class="sxs-lookup"><span data-stu-id="21695-133">**Applies to:**  All customers who applied a retention policy as part of the pre-migration steps</span></span>

| <span data-ttu-id="21695-134">步驟 (s) </span><span class="sxs-lookup"><span data-stu-id="21695-134">Step(s)</span></span> | <span data-ttu-id="21695-135">描述</span><span class="sxs-lookup"><span data-stu-id="21695-135">Description</span></span> | <span data-ttu-id="21695-136">影響</span><span class="sxs-lookup"><span data-stu-id="21695-136">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="21695-137">移除在遷移前步驟中建立的全組織保留原則</span><span class="sxs-lookup"><span data-stu-id="21695-137">Remove organization-wide retention policies that were created during pre-migration steps</span></span> | <span data-ttu-id="21695-138">客戶可以移除在客戶的預先遷移工作中所建立的全組織保留原則。</span><span class="sxs-lookup"><span data-stu-id="21695-138">Customers can remove the organization-wide retention policies that were created during the customers' pre-migration work.</span></span> | <span data-ttu-id="21695-139">無</span><span class="sxs-lookup"><span data-stu-id="21695-139">None</span></span> |
||||
