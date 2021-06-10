---
title: 開始使用活動總管
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 活動總管透過讓您查看和篩選使用者對套用標籤的內容執行的操作，來完善資料分類功能。
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114005"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="7da03-103">開始使用活動總管</span><span class="sxs-lookup"><span data-stu-id="7da03-103">Get started with activity explorer</span></span>

<span data-ttu-id="7da03-104">[資料分類概述](data-classification-overview.md)和[內容瀏覽器](data-classification-content-explorer.md)索引標籤可讓您深入瞭解已發現及已標示的內容，以及內容的位置。</span><span class="sxs-lookup"><span data-stu-id="7da03-104">The [data classification overview](data-classification-overview.md) and [content explorer](data-classification-content-explorer.md) tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="7da03-105">活動總管透過讓您監視對已套用標籤的內容執行的工作，從而完善此功能套件。</span><span class="sxs-lookup"><span data-stu-id="7da03-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="7da03-106">活動瀏覽器提供已標示內容的活動歷史視圖。</span><span class="sxs-lookup"><span data-stu-id="7da03-106">Activity explorer provides a historical view of activities on your labeled content.</span></span> <span data-ttu-id="7da03-107">活動資訊收集自 Microsoft 365 的整合審計記錄檔，並在活動資源管理器 UI 中進行轉換和使用。</span><span class="sxs-lookup"><span data-stu-id="7da03-107">The activity information is collected from the Microsoft 365 unified audit logs, transformed and made available in the Activity explorer UI.</span></span> 

![預留位置螢幕擷取畫面概觀活動總管](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="7da03-109">有超過 30 個不同的篩選可使用，其中包括：</span><span class="sxs-lookup"><span data-stu-id="7da03-109">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="7da03-110">日期範圍</span><span class="sxs-lookup"><span data-stu-id="7da03-110">date range</span></span>
- <span data-ttu-id="7da03-111">活動類型</span><span class="sxs-lookup"><span data-stu-id="7da03-111">activity type</span></span>
- <span data-ttu-id="7da03-112">位置</span><span class="sxs-lookup"><span data-stu-id="7da03-112">location</span></span>
- <span data-ttu-id="7da03-113">使用者</span><span class="sxs-lookup"><span data-stu-id="7da03-113">user</span></span>
- <span data-ttu-id="7da03-114">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="7da03-114">sensitivity label</span></span>
- <span data-ttu-id="7da03-115">保留標籤</span><span class="sxs-lookup"><span data-stu-id="7da03-115">retention label</span></span>
- <span data-ttu-id="7da03-116">檔案路徑</span><span class="sxs-lookup"><span data-stu-id="7da03-116">file path</span></span>
- <span data-ttu-id="7da03-117">DLP 原則</span><span class="sxs-lookup"><span data-stu-id="7da03-117">DLP policy</span></span>



## <a name="prerequisites"></a><span data-ttu-id="7da03-118">必要條件</span><span class="sxs-lookup"><span data-stu-id="7da03-118">Prerequisites</span></span>

<span data-ttu-id="7da03-119">每個存取並使用資料分類的帳戶，都必須有從下列其中一個訂閱中指派的授權：</span><span class="sxs-lookup"><span data-stu-id="7da03-119">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="7da03-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="7da03-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="7da03-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="7da03-121">Office 365 (E5)</span></span>
- <span data-ttu-id="7da03-122">進階合規性 (E5) 附加元件</span><span class="sxs-lookup"><span data-stu-id="7da03-122">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="7da03-123">進階威脅情報 (E5) 附加元件</span><span class="sxs-lookup"><span data-stu-id="7da03-123">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="7da03-124">Microsoft 365 E5/A5 資訊保護和控管</span><span class="sxs-lookup"><span data-stu-id="7da03-124">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="7da03-125">Microsoft 365 E5/A5 合規性</span><span class="sxs-lookup"><span data-stu-id="7da03-125">Microsoft 365 E5/A5 Compliance</span></span>

### <a name="permissions"></a><span data-ttu-id="7da03-126">權限</span><span class="sxs-lookup"><span data-stu-id="7da03-126">Permissions</span></span>

 <span data-ttu-id="7da03-127">若要存取 [活動流覽] 索引標籤，必須明確指派任何其中一個角色群組的成員資格或明確授與該角色的帳戶。</span><span class="sxs-lookup"><span data-stu-id="7da03-127">In order to get access to the activity explorer tab, an account must be explicitly assigned membership in any one of these role groups or explicitly granted the role.</span></span>

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

<span data-ttu-id="7da03-128">**Microsoft 365 角色群組**</span><span class="sxs-lookup"><span data-stu-id="7da03-128">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="7da03-129">全域管理員</span><span class="sxs-lookup"><span data-stu-id="7da03-129">Global administrator</span></span>
- <span data-ttu-id="7da03-130">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="7da03-130">Compliance administrator</span></span>
- <span data-ttu-id="7da03-131">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="7da03-131">Security administrator</span></span>
- <span data-ttu-id="7da03-132">合規性資料管理員</span><span class="sxs-lookup"><span data-stu-id="7da03-132">Compliance data administrator</span></span>

<span data-ttu-id="7da03-133">**Microsoft 365 角色**</span><span class="sxs-lookup"><span data-stu-id="7da03-133">**Microsoft 365 roles**</span></span>

- <span data-ttu-id="7da03-134">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="7da03-134">Compliance administrator</span></span>
- <span data-ttu-id="7da03-135">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="7da03-135">Security administrator</span></span>

## <a name="activity-types"></a><span data-ttu-id="7da03-136">活動類型</span><span class="sxs-lookup"><span data-stu-id="7da03-136">Activity types</span></span>

<span data-ttu-id="7da03-137">活動 explorer 會從多個活動來源收集審計記錄檔的活動資訊。</span><span class="sxs-lookup"><span data-stu-id="7da03-137">Activity explorer gathers activity information from the audit logs on multiple sources of activities.</span></span> <span data-ttu-id="7da03-138">如需詳細資訊，請參閱活動瀏覽器 [中可用](data-classification-activity-explorer-available-events.md)的標記事件。</span><span class="sxs-lookup"><span data-stu-id="7da03-138">For more detailed information on what labeling activity makes it to Activity explorer, see [Labeling events available in Activity explorer](data-classification-activity-explorer-available-events.md).</span></span>

<span data-ttu-id="7da03-139">**敏感度標籤活動** 和 **保留標記活動**，來自 Office 原生應用程式、Azure 資訊保護增益集、SharePoint 線上、Exchange Online (敏感度標籤只) 和 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="7da03-139">**Sensitivity label activities** and **Retention labeling activities** from Office native applications, Azure Information Protection add-in, SharePoint Online, Exchange Online (sensitivity labels only) and OneDrive.</span></span> <span data-ttu-id="7da03-140">部分範例如下：</span><span class="sxs-lookup"><span data-stu-id="7da03-140">Some examples are:</span></span>

- <span data-ttu-id="7da03-141">已套用標籤</span><span class="sxs-lookup"><span data-stu-id="7da03-141">label applied</span></span>
- <span data-ttu-id="7da03-142">已變更標籤 (升級、降級或移除)</span><span class="sxs-lookup"><span data-stu-id="7da03-142">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="7da03-143">自動加上標籤模擬</span><span class="sxs-lookup"><span data-stu-id="7da03-143">auto-labeling simulation</span></span>
- <span data-ttu-id="7da03-144">檔案讀取</span><span class="sxs-lookup"><span data-stu-id="7da03-144">file read</span></span> 

<span data-ttu-id="7da03-145">**Azure 資訊保護 (AIP) 掃描器和 AIP 用戶端**</span><span class="sxs-lookup"><span data-stu-id="7da03-145">**Azure Information Protection (AIP) scanner and AIP clients**</span></span>

- <span data-ttu-id="7da03-146">套用保護</span><span class="sxs-lookup"><span data-stu-id="7da03-146">protection applied</span></span>
- <span data-ttu-id="7da03-147">變更保護</span><span class="sxs-lookup"><span data-stu-id="7da03-147">protection changed</span></span>
- <span data-ttu-id="7da03-148">已移除保護</span><span class="sxs-lookup"><span data-stu-id="7da03-148">protection removed</span></span>
- <span data-ttu-id="7da03-149">探索的檔案</span><span class="sxs-lookup"><span data-stu-id="7da03-149">files discovered</span></span> 

<span data-ttu-id="7da03-150">活動 explorer 也會收集 **DLP 原則** 比對來自 Exchange Online 的事件、SharePoint 線上、OneDrive、Teams 聊天與通道 (預覽) 、內部部署 SharePoint 資料夾與文件庫，以及內部部署檔案共用，以及透過 **端點資料遺失防護 Windows 10 DLP (** 裝置的) 裝置。</span><span class="sxs-lookup"><span data-stu-id="7da03-150">Activity explorer also gathers **DLP policy matches** events from Exchange Online, SharePoint Online, OneDrive, Teams Chat and Channel (preview), on-premises SharePoint folders and libraries, and on-premises file shares, and Windows 10 devices via **Endpoint data loss prevention (DLP)**.</span></span> <span data-ttu-id="7da03-151">Windows 10 裝置的一些事件範例是檔案：</span><span class="sxs-lookup"><span data-stu-id="7da03-151">Some examples events from Windows 10 devices are file:</span></span>

- <span data-ttu-id="7da03-152">刪除</span><span class="sxs-lookup"><span data-stu-id="7da03-152">deletions</span></span>
- <span data-ttu-id="7da03-153">創作</span><span class="sxs-lookup"><span data-stu-id="7da03-153">creations</span></span>
- <span data-ttu-id="7da03-154">複製到剪貼簿</span><span class="sxs-lookup"><span data-stu-id="7da03-154">copied to clipboard</span></span>
- <span data-ttu-id="7da03-155">修改時間</span><span class="sxs-lookup"><span data-stu-id="7da03-155">modified</span></span>
- <span data-ttu-id="7da03-156">讀</span><span class="sxs-lookup"><span data-stu-id="7da03-156">read</span></span>
- <span data-ttu-id="7da03-157">列印的</span><span class="sxs-lookup"><span data-stu-id="7da03-157">printed</span></span>
- <span data-ttu-id="7da03-158">重新命名的</span><span class="sxs-lookup"><span data-stu-id="7da03-158">renamed</span></span>
- <span data-ttu-id="7da03-159">複製到網路共用</span><span class="sxs-lookup"><span data-stu-id="7da03-159">copied to network share</span></span>
- <span data-ttu-id="7da03-160">unallowed 應用程式存取</span><span class="sxs-lookup"><span data-stu-id="7da03-160">accessed by unallowed app</span></span> 

<span data-ttu-id="7da03-161">瞭解您機密標示內容所採取的動作，是您可以查看是否已放入的控制項，例如 [資料遺失防護](dlp-learn-about-dlp.md) 是否有效。</span><span class="sxs-lookup"><span data-stu-id="7da03-161">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention](dlp-learn-about-dlp.md) are effective or not.</span></span> <span data-ttu-id="7da03-162">如果無效，或者如果您發現一些意外情況 (例如大量加上`highly confidential`標籤並降級為`general`的項目)，則可以管理各種原則並採取新動作來限制不需要的行為。</span><span class="sxs-lookup"><span data-stu-id="7da03-162">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="7da03-163">活動總管目前未監視 Exchange Online 的保留活動。</span><span class="sxs-lookup"><span data-stu-id="7da03-163">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="7da03-164">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7da03-164">See also</span></span>

- [<span data-ttu-id="7da03-165">了解敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="7da03-165">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="7da03-166">瞭解保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="7da03-166">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="7da03-167">了解敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="7da03-167">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="7da03-168">了解資料分類</span><span class="sxs-lookup"><span data-stu-id="7da03-168">Learn about data classification</span></span>](data-classification-overview.md)
