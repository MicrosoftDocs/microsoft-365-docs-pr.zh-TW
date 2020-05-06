---
title: 高級 eDiscovery 的版本資訊
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
description: 本文包含用於高級 eDiscovery 的版本資訊，包括已知問題、已修復的問題和新功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 45a4647856fef0186840ec5465bb9250e5d78de4
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034617"
---
# <a name="release-notes-for-advanced-ediscovery"></a><span data-ttu-id="5b463-103">高級 eDiscovery 的版本資訊</span><span class="sxs-lookup"><span data-stu-id="5b463-103">Release notes for Advanced eDiscovery</span></span>

<span data-ttu-id="5b463-104">「高級 eDiscovery」的公開預覽程式是取得近期功能和更新之初期存取的方法。</span><span class="sxs-lookup"><span data-stu-id="5b463-104">The Public Preview program for Advanced eDiscovery is the way to get early access to the upcoming functionality and updates.</span></span> <span data-ttu-id="5b463-105">若要取得最新功能的初期存取，只要在安全性 & 合規性中心建立並使用高級 eDiscovery 案例即可。</span><span class="sxs-lookup"><span data-stu-id="5b463-105">To get early access to the newest features, just create and use an Advanced eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="5b463-106">請參閱[建立新的案例](create-new-ediscovery-case.md)。</span><span class="sxs-lookup"><span data-stu-id="5b463-106">See [Create a new case](create-new-ediscovery-case.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="5b463-107">已知問題</span><span class="sxs-lookup"><span data-stu-id="5b463-107">Known issues</span></span>

<span data-ttu-id="5b463-108">**Microsoft Forms**</span><span class="sxs-lookup"><span data-stu-id="5b463-108">**Microsoft Forms**</span></span>

- <span data-ttu-id="5b463-109">在2019年1月31日之前所建立之表單的資料，在使用高級 eDiscovery 中的搜尋工具來搜尋保管人信箱時，將無法進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="5b463-109">The data corresponding to a form created before January 31, 2019 will not be searchable when using the Search tool in Advanced eDiscovery to search custodian mailboxes.</span></span> <span data-ttu-id="5b463-110">在此日期之後建立的表單可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="5b463-110">Forms created after this date will be available to search.</span></span>

- <span data-ttu-id="5b463-111">使用者建立的表單仍可接收回應，即使在建立表單的使用者已遭刪除之後。</span><span class="sxs-lookup"><span data-stu-id="5b463-111">A form created by a user can still receive responses even after the user who created the Form is deleted.</span></span> <span data-ttu-id="5b463-112">不過，當使用高級 eDiscovery 中的搜尋工具來搜尋保管人信箱時，這些回應的對應資料（在刪除保管人信箱之後所發生的資料）將無法搜尋。</span><span class="sxs-lookup"><span data-stu-id="5b463-112">However, the corresponding data for those responses (that occurred after the custodian mailbox was deleted) will not be searchable when using the Search tool in Advanced eDiscovery to search custodian mailboxes.</span></span>
 
<span data-ttu-id="5b463-113">**Microsoft Sway**</span><span class="sxs-lookup"><span data-stu-id="5b463-113">**Microsoft Sway**</span></span>

- <span data-ttu-id="5b463-114">如果使用者在刪除使用者帳戶的使用者帳戶之前，在該 sway 的擁有者上進行編輯，則在使用高級 eDiscovery 的搜尋工具來搜尋保管人信箱時，這些變更可能不會是可搜尋的。</span><span class="sxs-lookup"><span data-stu-id="5b463-114">If a user edits a sway just prior to the deletion of the user account for the owner of that sway, then those changes may not be be searchable when using the Search tool in Advanced eDiscovery to search custodian mailboxes.</span></span> <span data-ttu-id="5b463-115">當您收到已刪除帳戶的信號時，sway 會立即封鎖對該 sway 所做的變更。</span><span class="sxs-lookup"><span data-stu-id="5b463-115">Sway blocks changes to to a sway as soon as it receives a signal that the account was deleted.</span></span> <span data-ttu-id="5b463-116">不過，在接收到此信號之前，您很可能會編輯 sway。</span><span class="sxs-lookup"><span data-stu-id="5b463-116">However, there's a small chance that a sway can be edited before this signal is received.</span></span>

## <a name="issues-fixed-in-this-release"></a><span data-ttu-id="5b463-117">在此版本中修復的問題</span><span class="sxs-lookup"><span data-stu-id="5b463-117">Issues fixed in this release</span></span>

- <span data-ttu-id="5b463-118">DCR：未編制索引的專案和孤立專案的例外狀況處理</span><span class="sxs-lookup"><span data-stu-id="5b463-118">DCR: Exception handling for unindexed items and orphaned items</span></span>
- <span data-ttu-id="5b463-119">DCR：保留通知</span><span class="sxs-lookup"><span data-stu-id="5b463-119">DCR: Hold notifications</span></span>
- <span data-ttu-id="5b463-120">DCR：電子檔探索中的保管人</span><span class="sxs-lookup"><span data-stu-id="5b463-120">DCR: Custodians in eDiscovery</span></span>

## <a name="whats-new"></a><span data-ttu-id="5b463-121">新功能</span><span class="sxs-lookup"><span data-stu-id="5b463-121">What's new</span></span>

- <span data-ttu-id="5b463-122">**安全性 & 規範中心的重新設計導覽**--「高級 eDiscovery」具有全新的外觀與風格。</span><span class="sxs-lookup"><span data-stu-id="5b463-122">**Redesigned navigation in the Security & Compliance Center** – Advanced eDiscovery has a new look and feel.</span></span> <span data-ttu-id="5b463-123">使用高級 eDiscovery 來管理更多案例工作流程。</span><span class="sxs-lookup"><span data-stu-id="5b463-123">Use Advanced eDiscovery to manage more of your case workflow.</span></span>

- <span data-ttu-id="5b463-124">**案例管理**–還有其他對新案例類型的支援。</span><span class="sxs-lookup"><span data-stu-id="5b463-124">**Case management** – There's additional support for new case types.</span></span> <span data-ttu-id="5b463-125">您也可以選取及儲存近期和最愛的案例。</span><span class="sxs-lookup"><span data-stu-id="5b463-125">You can also select and save your recent and favorite cases.</span></span> <span data-ttu-id="5b463-126">使用新的儀表板，追蹤並監控各案例內的活動。</span><span class="sxs-lookup"><span data-stu-id="5b463-126">Track and monitor activity within and across cases using new dashboards.</span></span>

- <span data-ttu-id="5b463-127">**保管人管理**–在案例中，以資料管理員的身分新增和移除使用者。</span><span class="sxs-lookup"><span data-stu-id="5b463-127">**Custodian management** – Add and remove users as data custodians within a case.</span></span>

- <span data-ttu-id="5b463-128">**Exchange、OneDrive 及小組整合**–自動將使用者的目前信箱、商務用 OneDrive，以及 Microsoft 小組網站新增至案例。</span><span class="sxs-lookup"><span data-stu-id="5b463-128">**Exchange, OneDrive, and Teams Integration** – Automatically add a user's current mailbox, OneDrive for Business account, and Microsoft Teams sites to a case.</span></span> 

- <span data-ttu-id="5b463-129">**管理員通訊**–代表您的組織傳送和管理法律封存通知。</span><span class="sxs-lookup"><span data-stu-id="5b463-129">**Custodian communications** – Send and manage legal hold notifications on behalf of your organization.</span></span>

- <span data-ttu-id="5b463-130">**管理員入口網站**–供保管人的新入口網站存取其使用中保留通知。</span><span class="sxs-lookup"><span data-stu-id="5b463-130">**Custodian portal** – New portal for custodians to access their active hold notices.</span></span>

- <span data-ttu-id="5b463-131">**深入編制索引**–根據需要重新編目部分索引的專案。</span><span class="sxs-lookup"><span data-stu-id="5b463-131">**Deep indexing** – Re-crawl partially indexed items on demand.</span></span>

- <span data-ttu-id="5b463-132">**錯誤修正**–修正或下載處理錯誤;這包括針對大型檔案類型、受密碼保護的檔案等等的修復支援。</span><span class="sxs-lookup"><span data-stu-id="5b463-132">**Error remediation** – Remediate or download processing errors; this include remediation support for large file types, password protected files, and more.</span></span> 

- <span data-ttu-id="5b463-133">**搜尋的增強功能**-透過識別保管人和/或位置來建立搜尋。</span><span class="sxs-lookup"><span data-stu-id="5b463-133">**Improvements to search** – Create a search by identifying custodians and/or locations.</span></span>

- <span data-ttu-id="5b463-134">**複查集**–管理、追蹤及審核一組靜態的檔。</span><span class="sxs-lookup"><span data-stu-id="5b463-134">**Review sets** – Manage, track, and audit static sets of documents.</span></span>

- <span data-ttu-id="5b463-135">**複習**–使用原生、文字和近原生模式，查看新增至您的審閱集的檔。</span><span class="sxs-lookup"><span data-stu-id="5b463-135">**Review** – Use a native, text, and near-native view to review documents added to your review set.</span></span>

- <span data-ttu-id="5b463-136">**標記密文、標記和批註**–在您審閱檔時標記密文、套用標記，並做為批註。</span><span class="sxs-lookup"><span data-stu-id="5b463-136">**Redact, tag, and annotate** – Redact text, apply tags, and make annotations as you review documents.</span></span>
  
- <span data-ttu-id="5b463-137">**分析-已安裝的回顧**–利用高級 eDiscovery 分析，在審校集內尋找、搜尋及挑選結果。</span><span class="sxs-lookup"><span data-stu-id="5b463-137">**Analytics-powered review**– Leverage Advanced eDiscovery analytics to find, search, and cull results within a review set.</span></span>

- <span data-ttu-id="5b463-138">**工作**–追蹤長時間執行程式的狀態。</span><span class="sxs-lookup"><span data-stu-id="5b463-138">**Jobs** – Track status of long-running processes.</span></span>

- <span data-ttu-id="5b463-139">**新的審計活動**–追蹤和查看高級 eDiscovery 的新的「審核」活動。</span><span class="sxs-lookup"><span data-stu-id="5b463-139">**New audit activities** – Track and view new audit activity for Advanced eDiscovery.</span></span>
