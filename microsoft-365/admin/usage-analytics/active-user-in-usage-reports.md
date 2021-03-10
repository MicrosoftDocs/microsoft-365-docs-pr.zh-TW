---
title: Microsoft 365 使用方式報告中的作用中使用者
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: 深入瞭解 Microsoft 365 流量分析、活動報告和採用度量的使用者。
ms.openlocfilehash: 7b8d15a88568c9af8b11a157dad2ec5f76ace6d3
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2021
ms.locfileid: "50603969"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a><span data-ttu-id="0d13b-103">Microsoft 365 使用方式報告中的作用中使用者</span><span class="sxs-lookup"><span data-stu-id="0d13b-103">Active user in Microsoft 365 usage reports</span></span>

## <a name="active-user-in-usage-reports"></a><span data-ttu-id="0d13b-104">使用情況報告中的作用中使用者</span><span class="sxs-lookup"><span data-stu-id="0d13b-104">Active user in usage reports</span></span>

<span data-ttu-id="0d13b-105">Microsoft [365 使用方式分析](usage-analytics.md) 的 microsoft 365 產品使用中使用者和系統 [管理中心的活動報告](../activity-reports/activity-reports.md) 定義如下。</span><span class="sxs-lookup"><span data-stu-id="0d13b-105">An active user of Microsoft 365 products for [Microsoft 365 usage analytics](usage-analytics.md) and the [Activity Reports in the admin center](../activity-reports/activity-reports.md) is defined as follows.</span></span> 
  
|<span data-ttu-id="0d13b-106">**產品**</span><span class="sxs-lookup"><span data-stu-id="0d13b-106">**Product**</span></span>|<span data-ttu-id="0d13b-107">**作用中使用者定義**</span><span class="sxs-lookup"><span data-stu-id="0d13b-107">**Definition of an active user**</span></span>|<span data-ttu-id="0d13b-108">**附註**</span><span class="sxs-lookup"><span data-stu-id="0d13b-108">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0d13b-109">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0d13b-109">Exchange Online</span></span>  <br/> |<span data-ttu-id="0d13b-110">任何執行下列動作的使用者：標示為已讀取、傳送訊息、建立約會、傳送會議邀請、接受 (為暫定) 或謝絕會議邀請、取消會議）。</span><span class="sxs-lookup"><span data-stu-id="0d13b-110">Any user who has performed any of the following actions: Mark as read, send messages, create appointments, send meeting requests, accept (as tentative) or decline meeting requests, cancel meetings.</span></span>  <br/> |<span data-ttu-id="0d13b-111">未顯示任何行事曆資訊，這會新增接下來的更新中。</span><span class="sxs-lookup"><span data-stu-id="0d13b-111">No calendar information is represented, this will be added in an upcoming update.</span></span>  <br/> |
|<span data-ttu-id="0d13b-112">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0d13b-112">SharePoint Online</span></span>  <br/> |<span data-ttu-id="0d13b-113">透過在任何網站上建立、修改、檢視、刪除、內外部共用或同步處理至用戶端以與檔案互動，或是檢視任何網站頁面的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="0d13b-113">Any user who has interacted with a file by creating, modifying, viewing, deleting, sharing internally or externally, or synchronizing to clients on any site or viewed a page on any site.</span></span>  <br/> |<span data-ttu-id="0d13b-114">Microsoft 365 使用方式分析範本應用程式中的 SharePoint 線上作用中使用者度量，只會反映對 SharePoint 小組網站或群組網站進行檔案活動的使用者。</span><span class="sxs-lookup"><span data-stu-id="0d13b-114">The active user metric for SharePoint Online in the Microsoft 365 Usage Analytics template app only reflect users who did file activity against a SharePoint Team site or a Group site.</span></span> <span data-ttu-id="0d13b-115">範本應用程式會更新，將定義同步處理為與系統管理中心的使用方式報告上的定義相同。</span><span class="sxs-lookup"><span data-stu-id="0d13b-115">The template app will be updated to synchronize the definition to the same as that on the usage reports in the admin center.</span></span>  <br/> |
|<span data-ttu-id="0d13b-116">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="0d13b-116">OneDrive for Business</span></span>  <br/> |<span data-ttu-id="0d13b-117">透過建立、修改、檢視、刪除、內外部共用或同步處理至用戶端以與檔案互動的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="0d13b-117">Any user who has interacted with a file by creating, modifying, viewing, deleting, sharing internally or externally, or synchronizing to clients.</span></span>  <br/> ||
|<span data-ttu-id="0d13b-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="0d13b-118">Yammer</span></span>  <br/> |<span data-ttu-id="0d13b-119">已在 Yammer 上讀取、張貼或喜歡訊息的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="0d13b-119">Any user who has read, posted, or liked a message on Yammer.</span></span>  <br/> ||
|<span data-ttu-id="0d13b-120">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="0d13b-120">Skype for Business</span></span>  <br/> |<span data-ttu-id="0d13b-121">已參與端對端工作階段 (包括即時傳訊、音訊和視訊通話、應用程式共用和檔案轉移) 或已主辦或參與會議的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="0d13b-121">Any user who has participated in a peer-to-peer session (including instant messaging, audio and video calls, application sharing, and file transfers) or who has organized or participated in a conference.</span></span>  <br/> ||
|<span data-ttu-id="0d13b-122">Office</span><span class="sxs-lookup"><span data-stu-id="0d13b-122">Office</span></span>  <br/> |<span data-ttu-id="0d13b-123">在至少一個裝置上啟用其 Microsoft 365 Pro Plus、Visio Pro 或 Project Pro 訂閱的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="0d13b-123">Any user who has activated their Microsoft 365 Pro Plus, Visio Pro or Project Pro subscription on at least one device.</span></span>  <br/> ||
|<span data-ttu-id="0d13b-124">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="0d13b-124">Microsoft 365 Groups</span></span>  <br/> |<span data-ttu-id="0d13b-125">任何有信箱活動的群組成員 (若有郵件已傳送至群組)。</span><span class="sxs-lookup"><span data-stu-id="0d13b-125">Any group member that has mailbox activity (if a message has been sent to the group)</span></span>  <br/> |<span data-ttu-id="0d13b-126">這項定義將會隨著群組網站檔案活動和 Yammer 群組活動的增強，在群組網站上 (檔案活動，以及傳送到與群組相關聯之 Yammer 群組的郵件。 ) 此資料目前不適用於 Microsoft 365 使用方式分析範本應用程式</span><span class="sxs-lookup"><span data-stu-id="0d13b-126">This definition will be enhanced with group site file activity and Yammer group activity (file activity on group site and message posted to Yammer group associated with the group.) This data is currently not available in the Microsoft 365 Usage Analytics template app</span></span>  <br/> |
|<span data-ttu-id="0d13b-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d13b-127">Microsoft Teams</span></span>  <br/> |<span data-ttu-id="0d13b-128">已參加聊天訊息、私人聊天訊息、通話、會議或其他活動的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="0d13b-128">Any user who has participated in chat messages, private chat messages, calls,meetings or other activity.</span></span> <span data-ttu-id="0d13b-129">其他活動是由使用者定義為其他小組活動的數目，其中包括（但不限於）：對郵件、應用程式、檔、搜尋、關注小組和頻道進行處理，並加以 favoriting。</span><span class="sxs-lookup"><span data-stu-id="0d13b-129">Other activity is defined as the number of other team activities by the user some of which include, and not limited to: liking messages, apps, working on files, searching, following teams and channel and favoriting them.</span></span>  <br/> ||
   
## <a name="adoption-metrics"></a><span data-ttu-id="0d13b-130">採用度量</span><span class="sxs-lookup"><span data-stu-id="0d13b-130">Adoption Metrics</span></span>

<span data-ttu-id="0d13b-131">[Microsoft 365 流量分析](usage-analytics.md) 包含與使用中的使用者相關的其他採用量值，以顯示隨時間的產品採用方式。</span><span class="sxs-lookup"><span data-stu-id="0d13b-131">[Microsoft 365 usage analytics](usage-analytics.md) contains additional adoption metrics related to active users to show adoption of the products over time.</span></span> <span data-ttu-id="0d13b-132">在選取的月、年及產品中，這些計量值都是有效的，並且定義如下。</span><span class="sxs-lookup"><span data-stu-id="0d13b-132">These metrics are valid for the month, year, and product selected and are defined as follows.</span></span> 
  
|<span data-ttu-id="0d13b-133">**計量**</span><span class="sxs-lookup"><span data-stu-id="0d13b-133">**Metric**</span></span>|<span data-ttu-id="0d13b-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="0d13b-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0d13b-135">EnabledUsers</span><span class="sxs-lookup"><span data-stu-id="0d13b-135">EnabledUsers</span></span>  <br/> |<span data-ttu-id="0d13b-136">在月份中啟用要使用產品的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="0d13b-136">Number of users enabled to use the product in the month.</span></span>  <br/> |
|<span data-ttu-id="0d13b-137">ActiveUsers</span><span class="sxs-lookup"><span data-stu-id="0d13b-137">ActiveUsers</span></span>  <br/> |<span data-ttu-id="0d13b-138">在當月使用中的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="0d13b-138">Number of users active in the month.</span></span>  <br/> |
|<span data-ttu-id="0d13b-139">MoMReturningUsers</span><span class="sxs-lookup"><span data-stu-id="0d13b-139">MoMReturningUsers</span></span>  <br/> |<span data-ttu-id="0d13b-140">在上月中也可以使用中的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="0d13b-140">Number of users active in the month that were also active in the preceding month.</span></span>  <br/> |
|<span data-ttu-id="0d13b-141">FirstTimeUsers</span><span class="sxs-lookup"><span data-stu-id="0d13b-141">FirstTimeUsers</span></span>  <br/> |<span data-ttu-id="0d13b-142">先前從未使用此服務的月份中的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="0d13b-142">Number of users active in the month that had never used the service before.</span></span>  <br/> |
|<span data-ttu-id="0d13b-143">CumulativeActiveUsers</span><span class="sxs-lookup"><span data-stu-id="0d13b-143">CumulativeActiveUsers</span></span>  <br/> |<span data-ttu-id="0d13b-144">在當月內使用的使用者數目，以及上個月的數目。</span><span class="sxs-lookup"><span data-stu-id="0d13b-144">Number of users active in the month plus any preceding month.</span></span>  <br/> |
|<span data-ttu-id="0d13b-145">ActiveUsers (% ) </span><span class="sxs-lookup"><span data-stu-id="0d13b-145">ActiveUsers(%)</span></span>  <br/> |<span data-ttu-id="0d13b-146">相對於該月份中啟用的使用者數目，以舍入為最接近第十個的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="0d13b-146">Percent of users, rounded to the nearest tenth, active in the month compared to the number of users enabled in that month.</span></span>  <br/> |
|<span data-ttu-id="0d13b-147">MoMReturningUsers (% ) </span><span class="sxs-lookup"><span data-stu-id="0d13b-147">MoMReturningUsers(%)</span></span>  <br/> |<span data-ttu-id="0d13b-148">相對於作用中使用者數目，在上個月中也可以使用的使用者，四捨五入為最接近第十個的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="0d13b-148">Percent of users, rounded to the nearest tenth, active in the month that were also active in the preceding month compared to the number of active users.</span></span>  <br/> |
   
<span data-ttu-id="0d13b-149">MoMReturningUsers、FirstTimeUsers、 &amp; CumulativeActiveUsers 已在包含 Microsoft 團隊的情況下，從2018年1月1日開始重設。</span><span class="sxs-lookup"><span data-stu-id="0d13b-149">MoMReturningUsers, FirstTimeUsers, &amp; CumulativeActiveUsers were reset starting January 1st 2018 with the inclusion of Microsoft Teams.</span></span>
  
