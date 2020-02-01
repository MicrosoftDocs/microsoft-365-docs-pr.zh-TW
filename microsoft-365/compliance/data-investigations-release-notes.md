---
title: Microsoft 365 中的資料調查 （預覽） 的版本資訊
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文說明 Microsoft 365 的新資料調查 （預覽） 工具。
ms.openlocfilehash: 57605566a8847a3630e1c4656f98f71ebb414f86
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595410"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a><span data-ttu-id="1bf9c-103">Microsoft 365 中的資料調查 （預覽） 的版本資訊</span><span class="sxs-lookup"><span data-stu-id="1bf9c-103">Release notes for Data Investigations (Preview) in Microsoft 365</span></span>

<span data-ttu-id="1bf9c-104">您可以使用新的資料調查 （預覽） 工具在 Microsoft 365 分級、 調查及修復資料相關事件，例如資料外洩事件或內部調查。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-104">You can use the new Data Investigations (Preview) tool in in Microsoft 365 to triage, investigate, and remediate data related incidents, such as a data spillage incident or an internal investigation.</span></span> <span data-ttu-id="1bf9c-105">資料調查公用預覽為您提供搶先即將推出的功能和更新。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-105">The Public Preview of Data Investigations provides you with early access to the upcoming functionality and updates.</span></span> <span data-ttu-id="1bf9c-106">若要搶先使用最新功能，請在安全 & 與規範中心中的資料調查 （預覽） 建立新的調查。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-106">To get early access to the newest features, create a new investigation in Data Investigations (Preview) in the Security & Compliance Center.</span></span> <span data-ttu-id="1bf9c-107">若要深入了解，請參閱[管理 Microsoft 365 中的資料外洩事件](manage-data-spillage-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-107">To learn how, see [Manage a data spillage incident in Microsoft 365](manage-data-spillage-incidents.md).</span></span>

## <a name="whats-new"></a><span data-ttu-id="1bf9c-108">新功能</span><span class="sxs-lookup"><span data-stu-id="1bf9c-108">What’s new</span></span> 

- <span data-ttu-id="1bf9c-109">**調查**-您可以藉由建立調查群組搜尋和事件。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-109">**Investigations** - You can group searches and incidents by creating an investigation.</span></span> <span data-ttu-id="1bf9c-110">管理誰可以存取調查藉由新增或移除成員。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-110">Manage who can access the investigation by adding or removing members.</span></span>  <span data-ttu-id="1bf9c-111">您也可以選取並標記您最愛的調查。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-111">You can also select and mark your favorite investigations.</span></span> <span data-ttu-id="1bf9c-112">追蹤及監視活動內和使用新的儀表板調查之間。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-112">Track and monitor activity within and across investigations using new dashboards.</span></span> <span data-ttu-id="1bf9c-113">完成您調查之後，您可以關閉或刪除它。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-113">After you complete your investigation, you can close or delete it.</span></span>

- <span data-ttu-id="1bf9c-114">**人員感興趣的**– 當您將使用者新增至調查上為感興趣的人員時，您可以查看他們的信箱，OneDrive 商務帳戶及 Microsoft Teams 網站。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-114">**People of interest** – When you add users to investigations as people of interest, you can see their mailbox, OneDrive for Business account, and Microsoft Teams sites.</span></span> <span data-ttu-id="1bf9c-115">您可以使用它們來調查的內容搜尋範圍。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-115">You can use them to scope your investigative content searches.</span></span> <span data-ttu-id="1bf9c-116">若要進一步調查感興趣的人員，您也可以檢視稽核記錄相關的 Office 365 和其他 Microsoft 服務中其活動。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-116">To further investigate a person of interest, you can also view audit records related to their activities in Office 365 and other Microsoft services.</span></span>

- <span data-ttu-id="1bf9c-117">**搜尋**– 建立整個組織搜尋使用各種搜尋條件。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-117">**Searches** – Create a organization-wide search using various search condition.</span></span> <span data-ttu-id="1bf9c-118">如果您知道使用者或您想要搜尋的網站，您可以新增這些使用者人員感興趣或搜尋建立精靈] 中指定的網站 」 位置，以執行。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-118">If you know users or sites that you want to search, you can do so by adding those users as people of interest or specifying site locations in search creation wizard.</span></span> 

- <span data-ttu-id="1bf9c-119">**辨識項**– 建立新的辨識項集合，並新增您想要檢閱的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-119">**Evidence** – Create a new evidence set and add search results that you want to review.</span></span> <span data-ttu-id="1bf9c-120">您可以檢閱個別文件、 留下調查備忘稿，加上註解和匯出結果，以移至不同的環境。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-120">You can review individual documents, annotate to leave investigation notes, and export results to move to a different environment.</span></span> 

- <span data-ttu-id="1bf9c-121">**檢閱**– 使用原生、 文字和附近原生檢視檢閱新增至事件的文件。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-121">**Review** – Use a native, text, and near-native views to review the documents added to an incident.</span></span> <span data-ttu-id="1bf9c-122">您也可以套用至文件以群組項目的分析的重複項目、 電子郵件執行緒和佈景主題，可協助協助您檢閱事件。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-122">You can also apply analytics to documents to group items by duplicates, email threads, and themes, which can help assist your review of the incident.</span></span> 

- <span data-ttu-id="1bf9c-123">**Redact，加上標籤，並加上註解**– Redact 文字、 套用標記，以及當您檢閱文件註釋。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-123">**Redact, tag, and annotate** – Redact text, apply tags, and make annotations as you review documents.</span></span>
  
- <span data-ttu-id="1bf9c-124">**進階編製索引**– 如果有任何已局部編製索引的項目，它們會視需要重新編製索引，讓所有資料都將可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-124">**Advanced indexing** – If there are any partially indexed items, they will be re-indexed on demand so that all data will be available for searching.</span></span>

- <span data-ttu-id="1bf9c-125">**錯誤修復**– 修復或下載處理錯誤。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-125">**Error remediation** – Remediate or download processing errors.</span></span> <span data-ttu-id="1bf9c-126">這包括修復支援大型檔案類型、 受密碼保護的檔案及編製索引的錯誤與相關的其他問題。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-126">This includes remediation support for large file types, password protected files, and other issues related to indexing errors.</span></span> 

- <span data-ttu-id="1bf9c-127">**工作**– 長時間執行程序的追蹤狀態。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-127">**Jobs** – Track status of long-running processes.</span></span>

- <span data-ttu-id="1bf9c-128">**硬碟刪除信箱項目**-在緊急情況下，您可能需要永久刪除 [找不到的項目。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-128">**Hard-delete mailbox items** - In urgent situations, you may need to permanently delete misplaced items.</span></span> <span data-ttu-id="1bf9c-129">若要這麼做，您可以執行**New-compliancesearchaction-清除-PurgeType HardDelete**命令中安全性 & 合規性中心 PowerShell 可永久移除信箱中的項目。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-129">To do this, you can run the **New-ComplianceSearchAction -Purge -PurgeType HardDelete** command in Security & Compliance Center PowerShell to permanently remove items from mailboxes.</span></span> <span data-ttu-id="1bf9c-130">如需詳細資訊，請參閱 [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction) (英文)。</span><span class="sxs-lookup"><span data-stu-id="1bf9c-130">For more information, see [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction).</span></span>
