---
title: 在 Office 365 中搜尋使用者和系統管理員活動的稽核記錄檔
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/18/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MOE150
ms.assetid: 57ca5138-0ae0-4d34-bd40-240441ef2fb6
description: Office 365 稽核記錄是整合的稽核記錄。 為什麼使用整合的稽核記錄？ 因為訂閱來自您組織的大多數 Office 365 服務的事件都會記錄在您可以搜尋的單一稽核記錄。 這表示您可以搜尋的使用者與這些服務的系統管理員活動：
ms.openlocfilehash: 1d3f45d24a8d1a83c20f5d36b12ced761e00f936
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077545"
---
# <a name="search-the-audit-log-for-user-and-admin-activity-in-office-365"></a><span data-ttu-id="4d247-106">在 Office 365 中搜尋使用者和系統管理員活動的稽核記錄檔</span><span class="sxs-lookup"><span data-stu-id="4d247-106">Search the audit log for user and admin activity in Office 365</span></span>

<span data-ttu-id="4d247-107">Office 365 稽核記錄是整合的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="4d247-107">The Office 365 audit log is a unified audit log.</span></span> <span data-ttu-id="4d247-108">為什麼使用整合的稽核記錄？</span><span class="sxs-lookup"><span data-stu-id="4d247-108">Why a unified audit log?</span></span> <span data-ttu-id="4d247-109">因為訂閱來自您組織的大多數 Office 365 服務的事件都會記錄在您可以搜尋的單一稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="4d247-109">Because events from most Office 365 services that you're organization subscribes to are recorded in a single audit log that you can search.</span></span> <span data-ttu-id="4d247-110">這表示您可以搜尋的使用者與這些服務的系統管理員活動：</span><span class="sxs-lookup"><span data-stu-id="4d247-110">That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="4d247-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="4d247-111">SharePoint</span></span>
- <span data-ttu-id="4d247-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="4d247-112">OneDrive</span></span>
- <span data-ttu-id="4d247-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="4d247-113">Exchange</span></span>
- <span data-ttu-id="4d247-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4d247-114">Azure Active Directory</span></span>
- <span data-ttu-id="4d247-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4d247-115">Microsoft Teams</span></span>
- <span data-ttu-id="4d247-116">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4d247-116">eDiscovery</span></span>
- <span data-ttu-id="4d247-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="4d247-117">Power BI</span></span>
- <span data-ttu-id="4d247-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="4d247-118">Yammer</span></span>
- <span data-ttu-id="4d247-119">Sway</span><span class="sxs-lookup"><span data-stu-id="4d247-119">Sway</span></span>
- <span data-ttu-id="4d247-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="4d247-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="4d247-121">設定稽核</span><span class="sxs-lookup"><span data-stu-id="4d247-121">Set up auditing</span></span>
  
<span data-ttu-id="4d247-122">沒有幾件事，您必須執行才能搜尋 Office 365 稽核記錄檔。</span><span class="sxs-lookup"><span data-stu-id="4d247-122">There's few things you have to do before you can search the Office 365 audit log.</span></span>
  
- <span data-ttu-id="4d247-123">若要開始錄製事件，您可以搜尋[開啟稽核記錄搜尋](turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="4d247-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="4d247-124">[啟用信箱稽核](enable-mailbox-auditing.md)，您可以搜尋的信箱相關的事件;例如當使用者登入其信箱或清除項目從其可復原的項目] 資料夾</span><span class="sxs-lookup"><span data-stu-id="4d247-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="4d247-125">搜尋稽核記錄</span><span class="sxs-lookup"><span data-stu-id="4d247-125">Search the audit log</span></span>
  
<span data-ttu-id="4d247-126">您開啟稽核功能之後，您搜尋數百個個別的事件類型從多個 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="4d247-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Office 365 services.</span></span>
  
- <span data-ttu-id="4d247-127">[搜尋稽核記錄檔](search-the-audit-log-in-security-and-compliance.md)的使用者和系統管理員活動</span><span class="sxs-lookup"><span data-stu-id="4d247-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="4d247-128">[了解詳細的內容](detailed-properties-in-the-office-365-audit-log.md)在搜尋結果中包含每個稽核記錄</span><span class="sxs-lookup"><span data-stu-id="4d247-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="4d247-129">系統管理員和合規性管理員所執行的[搜尋 eDiscovery 相關的活動](search-for-ediscovery-activities-in-the-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="4d247-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 
