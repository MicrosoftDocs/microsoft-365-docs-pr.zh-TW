---
title: Microsoft 365 中的資料調查（預覽）版本附注
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
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
description: 在本文中，您將會看到版本資訊，其中包含 Microsoft 365 中「資料調查（預覽）」工具的變更和新功能。
ms.openlocfilehash: 5bb18ccb3354082634780720938fb18164da0ccb
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035725"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a><span data-ttu-id="47643-103">Microsoft 365 中的資料調查（預覽）版本附注</span><span class="sxs-lookup"><span data-stu-id="47643-103">Release notes for Data Investigations (Preview) in Microsoft 365</span></span>

<span data-ttu-id="47643-104">您可以使用 Microsoft 365 中的「新增資料調查（預覽）」工具來會審、調查和修正資料相關的事件，例如資料外泄事件或內部調查。</span><span class="sxs-lookup"><span data-stu-id="47643-104">You can use the new Data Investigations (Preview) tool in in Microsoft 365 to triage, investigate, and remediate data related incidents, such as a data spillage incident or an internal investigation.</span></span> <span data-ttu-id="47643-105">資料調查的公開預覽可讓您及早存取即將推出的功能和更新。</span><span class="sxs-lookup"><span data-stu-id="47643-105">The Public Preview of Data Investigations provides you with early access to the upcoming functionality and updates.</span></span> <span data-ttu-id="47643-106">若要取得最新功能的初期存取，請在安全性 & 規範中心建立新調查（預覽）。</span><span class="sxs-lookup"><span data-stu-id="47643-106">To get early access to the newest features, create a new investigation in Data Investigations (Preview) in the Security & Compliance Center.</span></span> <span data-ttu-id="47643-107">若要深入瞭解，請參閱[管理 Microsoft 365 中的資料外泄事件](manage-data-spillage-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="47643-107">To learn how, see [Manage a data spillage incident in Microsoft 365](manage-data-spillage-incidents.md).</span></span>

## <a name="whats-new"></a><span data-ttu-id="47643-108">新功能</span><span class="sxs-lookup"><span data-stu-id="47643-108">What's new</span></span> 

- <span data-ttu-id="47643-109">**調查**-您可以建立調查，以群組搜尋和事件。</span><span class="sxs-lookup"><span data-stu-id="47643-109">**Investigations** - You can group searches and incidents by creating an investigation.</span></span> <span data-ttu-id="47643-110">新增或移除成員，以管理可以存取調查的人員。</span><span class="sxs-lookup"><span data-stu-id="47643-110">Manage who can access the investigation by adding or removing members.</span></span>  <span data-ttu-id="47643-111">您也可以選取及標示您最愛的調查。</span><span class="sxs-lookup"><span data-stu-id="47643-111">You can also select and mark your favorite investigations.</span></span> <span data-ttu-id="47643-112">使用新的儀表板，追蹤並監控在調查內和跨調查的活動。</span><span class="sxs-lookup"><span data-stu-id="47643-112">Track and monitor activity within and across investigations using new dashboards.</span></span> <span data-ttu-id="47643-113">完成調查之後，您可以關閉或刪除。</span><span class="sxs-lookup"><span data-stu-id="47643-113">After you complete your investigation, you can close or delete it.</span></span>

- <span data-ttu-id="47643-114">**感興趣的人員**-當您將使用者新增至調查的相關人員時，您可以查看其信箱、OneDrive 商務用帳戶，以及 Microsoft 小組網站。</span><span class="sxs-lookup"><span data-stu-id="47643-114">**People of interest** – When you add users to investigations as people of interest, you can see their mailbox, OneDrive for Business account, and Microsoft Teams sites.</span></span> <span data-ttu-id="47643-115">您可以使用它們來限定調查內容搜尋的範圍。</span><span class="sxs-lookup"><span data-stu-id="47643-115">You can use them to scope your investigative content searches.</span></span> <span data-ttu-id="47643-116">若要進一步調查感興趣的人員，您也可以在 Microsoft 365 和其他 Microsoft 服務中查看與其活動相關的審計記錄。</span><span class="sxs-lookup"><span data-stu-id="47643-116">To further investigate a person of interest, you can also view audit records related to their activities in Microsoft 365 and other Microsoft services.</span></span>

- <span data-ttu-id="47643-117">**搜尋**–使用各種搜尋條件建立組織範圍的搜尋。</span><span class="sxs-lookup"><span data-stu-id="47643-117">**Searches** – Create a organization-wide search using various search condition.</span></span> <span data-ttu-id="47643-118">如果您知道想要搜尋的使用者或網站，您可以將這些使用者新增為感興趣的人員，或是在 [搜尋建立] 中指定網站位置。</span><span class="sxs-lookup"><span data-stu-id="47643-118">If you know users or sites that you want to search, you can do so by adding those users as people of interest or specifying site locations in search creation wizard.</span></span> 

- <span data-ttu-id="47643-119">**證據**–建立新的證據集，並新增您要查看的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="47643-119">**Evidence** – Create a new evidence set and add search results that you want to review.</span></span> <span data-ttu-id="47643-120">您可以查看個別檔、批註以留下調查附注，以及匯出結果以移至不同的環境。</span><span class="sxs-lookup"><span data-stu-id="47643-120">You can review individual documents, annotate to leave investigation notes, and export results to move to a different environment.</span></span> 

- <span data-ttu-id="47643-121">**回顧**–使用原生、文字和近原生的視圖，檢查新增至事件的檔。</span><span class="sxs-lookup"><span data-stu-id="47643-121">**Review** – Use a native, text, and near-native views to review the documents added to an incident.</span></span> <span data-ttu-id="47643-122">您也可以將分析套用至檔，以依重複、電子郵件執行緒及主題群組專案，這有助於協助您複查事件。</span><span class="sxs-lookup"><span data-stu-id="47643-122">You can also apply analytics to documents to group items by duplicates, email threads, and themes, which can help assist your review of the incident.</span></span> 

- <span data-ttu-id="47643-123">**標記密文、標記和批註**–在您審閱檔時標記密文、套用標記，並做為批註。</span><span class="sxs-lookup"><span data-stu-id="47643-123">**Redact, tag, and annotate** – Redact text, apply tags, and make annotations as you review documents.</span></span>
  
- <span data-ttu-id="47643-124">**高級索引**–如果有任何部分編制索引的專案，將會根據需要重新編制索引，這樣所有的資料就會可供搜尋使用。</span><span class="sxs-lookup"><span data-stu-id="47643-124">**Advanced indexing** – If there are any partially indexed items, they will be re-indexed on demand so that all data will be available for searching.</span></span>

- <span data-ttu-id="47643-125">**錯誤修正**–修正或下載處理錯誤。</span><span class="sxs-lookup"><span data-stu-id="47643-125">**Error remediation** – Remediate or download processing errors.</span></span> <span data-ttu-id="47643-126">這包括對大型檔案類型的補救支援、受密碼保護的檔案，以及與索引錯誤相關的其他問題。</span><span class="sxs-lookup"><span data-stu-id="47643-126">This includes remediation support for large file types, password protected files, and other issues related to indexing errors.</span></span> 

- <span data-ttu-id="47643-127">**工作**–追蹤長時間執行程式的狀態。</span><span class="sxs-lookup"><span data-stu-id="47643-127">**Jobs** – Track status of long-running processes.</span></span>

- <span data-ttu-id="47643-128">**硬性刪除信箱專案**-在緊急情況下，您可能需要永久刪除錯放的專案。</span><span class="sxs-lookup"><span data-stu-id="47643-128">**Hard-delete mailbox items** - In urgent situations, you may need to permanently delete misplaced items.</span></span> <span data-ttu-id="47643-129">若要這麼做，您可以在安全性 & 規範中心 PowerShell 中執行**New-ComplianceSearchAction-Purge PurgeType HardDelete**命令，以從信箱中永久移除專案。</span><span class="sxs-lookup"><span data-stu-id="47643-129">To do this, you can run the **New-ComplianceSearchAction -Purge -PurgeType HardDelete** command in Security & Compliance Center PowerShell to permanently remove items from mailboxes.</span></span> <span data-ttu-id="47643-130">如需詳細資訊，請參閱 [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction) (英文)。</span><span class="sxs-lookup"><span data-stu-id="47643-130">For more information, see [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction).</span></span>
