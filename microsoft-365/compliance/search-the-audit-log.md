---
title: 搜尋審核記錄中的使用者和系統管理員活動
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/18/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MOE150
- MET150
ms.assetid: 57ca5138-0ae0-4d34-bd40-240441ef2fb6
description: 「審核記錄」是一個整合的審計記錄檔。 為什麼使用整合的稽核記錄？ 因為組織所訂閱的大部分服務事件會記錄在您可以搜尋的單一審核記錄中。 這表示您可以在這些服務中搜尋使用者和系統管理員活動：
ms.openlocfilehash: 3cc76b272516c0e0508c7d76f0b93da44effa487
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943642"
---
# <a name="search-the-audit-log-for-user-and-admin-activity"></a><span data-ttu-id="108b6-106">搜尋審核記錄中的使用者和系統管理員活動</span><span class="sxs-lookup"><span data-stu-id="108b6-106">Search the audit log for user and admin activity</span></span>

<span data-ttu-id="108b6-107">「審核記錄」是一個整合的審計記錄檔。</span><span class="sxs-lookup"><span data-stu-id="108b6-107">The audit log is a unified audit log.</span></span> <span data-ttu-id="108b6-108">為什麼使用整合的稽核記錄？</span><span class="sxs-lookup"><span data-stu-id="108b6-108">Why a unified audit log?</span></span> <span data-ttu-id="108b6-109">因為您組織所訂閱的大部分服務事件會記錄在您可以搜尋的單一審核記錄中。</span><span class="sxs-lookup"><span data-stu-id="108b6-109">Because events from most services that you're organization subscribes to are recorded in a single audit log that you can search.</span></span> <span data-ttu-id="108b6-110">這表示您可以在這些服務中搜尋使用者和系統管理員活動：</span><span class="sxs-lookup"><span data-stu-id="108b6-110">That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="108b6-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="108b6-111">SharePoint</span></span>
- <span data-ttu-id="108b6-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="108b6-112">OneDrive</span></span>
- <span data-ttu-id="108b6-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="108b6-113">Exchange</span></span>
- <span data-ttu-id="108b6-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="108b6-114">Azure Active Directory</span></span>
- <span data-ttu-id="108b6-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="108b6-115">Microsoft Teams</span></span>
- <span data-ttu-id="108b6-116">電子文件探索</span><span class="sxs-lookup"><span data-stu-id="108b6-116">eDiscovery</span></span>
- <span data-ttu-id="108b6-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="108b6-117">Power BI</span></span>
- <span data-ttu-id="108b6-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="108b6-118">Yammer</span></span>
- <span data-ttu-id="108b6-119">Sway</span><span class="sxs-lookup"><span data-stu-id="108b6-119">Sway</span></span>
- <span data-ttu-id="108b6-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="108b6-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="108b6-121">設定審計</span><span class="sxs-lookup"><span data-stu-id="108b6-121">Set up auditing</span></span>
  
<span data-ttu-id="108b6-122">您必須先完成一些工作，才能搜尋審核記錄。</span><span class="sxs-lookup"><span data-stu-id="108b6-122">There's few things you have to do before you can search the audit log.</span></span>
  
- <span data-ttu-id="108b6-123">[開啟審計記錄搜尋](turn-audit-log-search-on-or-off.md)，以開始記錄您可以搜尋的事件</span><span class="sxs-lookup"><span data-stu-id="108b6-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="108b6-124">[啟用信箱審核](enable-mailbox-auditing.md)，以便搜尋信箱相關事件。例如，當使用者登入其信箱或清除其 [可復原的專案] 資料夾中的專案時</span><span class="sxs-lookup"><span data-stu-id="108b6-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="108b6-125">搜尋稽核記錄</span><span class="sxs-lookup"><span data-stu-id="108b6-125">Search the audit log</span></span>
  
<span data-ttu-id="108b6-126">在您開啟審核後，請從多個 Microsoft 365 服務搜尋數百個個別類型的事件。</span><span class="sxs-lookup"><span data-stu-id="108b6-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Microsoft 365 services.</span></span>
  
- <span data-ttu-id="108b6-127">[搜尋審核記錄中](search-the-audit-log-in-security-and-compliance.md)的使用者和系統管理員活動</span><span class="sxs-lookup"><span data-stu-id="108b6-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="108b6-128">瞭解搜尋結果中所包含的每個審計記錄[的詳細屬性](detailed-properties-in-the-office-365-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="108b6-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="108b6-129">搜尋由系統管理員和合規性管理員執行的[eDiscovery 相關活動](search-for-ediscovery-activities-in-the-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="108b6-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 
