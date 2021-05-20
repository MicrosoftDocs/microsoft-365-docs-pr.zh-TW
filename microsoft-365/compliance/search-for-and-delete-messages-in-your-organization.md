---
title: 搜尋並刪除組織中的電子郵件
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: 使用安全性與合規性中心的搜尋和清除功能，可搜尋並刪除組織中所有信箱的電子郵件訊息。
ms.openlocfilehash: 629b236be3f857da47674cda9350d8b89e6f3445
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537640"
---
# <a name="search-for-and-delete-email-messages"></a><span data-ttu-id="5e686-103">搜尋並刪除電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="5e686-103">Search for and delete email messages</span></span>

<span data-ttu-id="5e686-104">**本文適用於系統管理員。您正嘗試在信箱中尋找要刪除的項目嗎？請參閱 [使用立即搜尋尋找郵件或項目](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**。</span><span class="sxs-lookup"><span data-stu-id="5e686-104">**This article is for administrators. Are you trying to find items in your mailbox that you want to delete? See [Find a message or item with Instant Search](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**.</span></span>

<span data-ttu-id="5e686-105">您可以使用內容搜尋功能來搜尋並刪除組織中所有信箱的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="5e686-105">You can use the Content Search feature to search for and delete an email message from all mailboxes in your organization.</span></span> <span data-ttu-id="5e686-106">這可幫助您找出並移除可能有害或高風險的電子郵件，例如：</span><span class="sxs-lookup"><span data-stu-id="5e686-106">This can help you find and remove potentially harmful or high-risk email, such as:</span></span>

- <span data-ttu-id="5e686-107">含有危險附件或病毒的郵件</span><span class="sxs-lookup"><span data-stu-id="5e686-107">Messages that contain dangerous attachments or viruses</span></span>

- <span data-ttu-id="5e686-108">網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="5e686-108">Phishing messages</span></span>

- <span data-ttu-id="5e686-109">包含敏感資料的郵件</span><span class="sxs-lookup"><span data-stu-id="5e686-109">Messages that contain sensitive data</span></span>

> [!CAUTION]
> <span data-ttu-id="5e686-110">搜尋和清除是一個強大的功能，可讓獲指派必要權限的任何人刪除組織信箱的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="5e686-110">Search and purge is a powerful feature that allows anyone that is assigned the necessary permissions to delete email messages from mailboxes in your organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5e686-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="5e686-111">Before you begin</span></span>

- <span data-ttu-id="5e686-112">若要建立和執行內容搜尋，您必須是 **電子文件探索管理員** 角色群組的成員，或者獲指派安全性與合規性中心的 **合規性搜尋** 角色。</span><span class="sxs-lookup"><span data-stu-id="5e686-112">To create and run a Content search, you have to be a member of the **eDiscovery Manager** role group or be assigned the **Compliance Search** role in Security & Compliance Center.</span></span> <span data-ttu-id="5e686-113">若要刪除郵件，您必須是 **組織管理** 角色群組的成員，或者獲指派安全性與合規性中心的 **搜尋及清除** 角色。</span><span class="sxs-lookup"><span data-stu-id="5e686-113">To delete messages, you have to be a member of the **Organization Management** role group or be assigned the **Search And Purge** role in Security & Compliance Center.</span></span> <span data-ttu-id="5e686-114">如需新增使用者至角色群組的詳細資訊，請參閱[在安全性與合規性中心指派電子文件探索權限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="5e686-114">For information about adding users to a role group, see [Assign eDiscovery permissions in the Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="5e686-115">Exchange Online 安全性與安全性與合規性中心都有 **組織管理** 角色群組。</span><span class="sxs-lookup"><span data-stu-id="5e686-115">The **Organization Management** role group exists in both Exchange Online and Security & Compliance Center.</span></span> <span data-ttu-id="5e686-116">這些是提供不同權限的不同角色群組。</span><span class="sxs-lookup"><span data-stu-id="5e686-116">These are separate role groups that give different permissions.</span></span> <span data-ttu-id="5e686-117">成為 Exchange Online 中 **組織管理** 的成員，不會授與其刪除電子郵件訊息所需的權限。</span><span class="sxs-lookup"><span data-stu-id="5e686-117">Being a member of **Organization Management** in Exchange Online does not grant the required permissions to delete email messages.</span></span> <span data-ttu-id="5e686-118">如果您未獲指派安全性與合規性中心 (直接或透過角色群組如 **組織管理**) 的 **搜尋及清除** 角色，執行 **New-ComplianceSearchAction** Cmdlet 時，您會在步驟 3 收到錯誤，其訊息為「找不到符合參數名稱 'Purge' 的參數」。</span><span class="sxs-lookup"><span data-stu-id="5e686-118">If you aren't assigned the **Search And Purge** role in Security & Compliance Center (either directly or through a role group such as **Organization Management**), you'll receive an error in Step 3 when you run the **New-ComplianceSearchAction** cmdlet with the message "A parameter cannot be found that matches parameter name 'Purge'".</span></span>

- <span data-ttu-id="5e686-119">您必須使用安全性與合規性中心 PowerShell 來刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="5e686-119">You have to use Security & Compliance Center PowerShell to delete messages.</span></span> <span data-ttu-id="5e686-120">如需如何連線的相關指示，請參閱[步驟 2](#step-2-connect-to-security--compliance-center-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5e686-120">See [Step 2](#step-2-connect-to-security--compliance-center-powershell) for instructions about how to connect.</span></span>

- <span data-ttu-id="5e686-121">每個信箱一次可以移除最多 10 個項目。</span><span class="sxs-lookup"><span data-stu-id="5e686-121">A maximum of 10 items per mailbox can be removed at one time.</span></span> <span data-ttu-id="5e686-122">因為搜尋和移除郵件的功能應該是事件回應工具，此限制可以協助確保從信箱快速移除郵件。</span><span class="sxs-lookup"><span data-stu-id="5e686-122">Because the capability to search for and remove messages is intended to be an incident-response tool, this limit helps ensure that messages are quickly removed from mailboxes.</span></span> <span data-ttu-id="5e686-123">這項功能不是用來清除使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="5e686-123">This feature isn't intended to clean up user mailboxes.</span></span>

- <span data-ttu-id="5e686-124">透過搜尋及清除動作，您最多可以在內容搜尋刪除 50,000 個信箱內的項目。</span><span class="sxs-lookup"><span data-stu-id="5e686-124">The maximum number of mailboxes in a content search that you can use to delete items by doing a search and purge action is 50,000.</span></span> <span data-ttu-id="5e686-125">如果搜尋功能 (您在[步驟 1 ](#step-1-create-a-content-search-to-find-the-message-to-delete)中所建立的項目) 搜尋超過 50,000 個信箱，則您在步驟 3 中建立的清除動作將失敗。</span><span class="sxs-lookup"><span data-stu-id="5e686-125">If the search (that you create in [Step 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) searches more than 50,000 mailboxes, the purge action (that you create in Step 3) will fail.</span></span> <span data-ttu-id="5e686-126">在單一搜尋中搜尋超過 50,000 個信箱，通常會在您將搜尋設為包含貴組織的所有信箱時發生。</span><span class="sxs-lookup"><span data-stu-id="5e686-126">Searching more than 50,000 mailbox in a single search might typically happen when you configure the search to include all mailboxes in your organization.</span></span> <span data-ttu-id="5e686-127">即使包含符合搜尋查詢項目的信箱少於 50,000 個，此限制仍會適用。</span><span class="sxs-lookup"><span data-stu-id="5e686-127">This restriction still applies even when less than 50,000 mailboxes contain items that match the search query.</span></span> <span data-ttu-id="5e686-128">請參閱 [更多資訊](#more-information) 一節，以瞭解有關使用搜尋權限篩選條件在超過 50,000 個信箱中搜尋和清除項目的指南。</span><span class="sxs-lookup"><span data-stu-id="5e686-128">See the [More information](#more-information) section for guidance about using search permissions filters to search for and purge items from more than 50,000 mailboxes.</span></span>

- <span data-ttu-id="5e686-129">本文所述的程序只能用於刪除 Exchange Online 信箱和公用資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="5e686-129">The procedure in this article can only be used to delete items in Exchange Online mailboxes and public folders.</span></span> <span data-ttu-id="5e686-130">您無法使用這個程序來刪除 SharePoint 或商務用 OneDrive 上的內容。</span><span class="sxs-lookup"><span data-stu-id="5e686-130">You can't use it to delete content from SharePoint or OneDrive for Business sites.</span></span>

- <span data-ttu-id="5e686-131">您無法使用本文所述的程序刪除進階電子文件探索案例的檢閱集中的電子郵件項目。</span><span class="sxs-lookup"><span data-stu-id="5e686-131">Email items in a review set in an Advanced eDiscovery case can't be deleted by using the procedures in this article.</span></span> <span data-ttu-id="5e686-132">這是因為檢閱集中的項目儲存在 Azure 儲存體位置，而不是在實際服務中。</span><span class="sxs-lookup"><span data-stu-id="5e686-132">That's because items in a review set are stored in an Azure Storage location, and not in the live service.</span></span> <span data-ttu-id="5e686-133">這表示不會由您在步驟 1 建立的內容搜尋所傳回。</span><span class="sxs-lookup"><span data-stu-id="5e686-133">This means they won't be returned by the content search that you create in Step 1.</span></span> <span data-ttu-id="5e686-134">若要刪除檢閱集中的項目，您必須刪除包含檢閱集的進階電子文件探索案例。</span><span class="sxs-lookup"><span data-stu-id="5e686-134">To delete items in a review set, you have to delete the Advanced eDiscovery case that contains the review set.</span></span> <span data-ttu-id="5e686-135">如需詳細資訊，請參閱[關閉或刪除進階電子文件探索案例](close-or-delete-case.md)。</span><span class="sxs-lookup"><span data-stu-id="5e686-135">For more information, see [Close or delete an Advanced eDiscovery case](close-or-delete-case.md).</span></span>

## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a><span data-ttu-id="5e686-136">步驟 1：建立內容搜尋來尋找要刪除的郵件</span><span class="sxs-lookup"><span data-stu-id="5e686-136">Step 1: Create a Content Search to find the message to delete</span></span>

<span data-ttu-id="5e686-137">第一個步驟是建立和執行內容搜尋，以尋找您想要從組織中的信箱移除的郵件。</span><span class="sxs-lookup"><span data-stu-id="5e686-137">The first step is to create and run a Content Search to find the message that you want to remove from mailboxes in your organization.</span></span> <span data-ttu-id="5e686-138">您可以使用安全性與合規性中心或執行 **New-ComplianceSearch** 以及 **Start-ComplianceSearch** Cmdlet 來建立搜尋。</span><span class="sxs-lookup"><span data-stu-id="5e686-138">You can create the search by using the Security & Compliance Center or by running the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets.</span></span> <span data-ttu-id="5e686-139">藉由在 [步驟 3](#step-3-delete-the-message) 中執行 **New-ComplianceSearchAction -Purge** 命令，會刪除符合此搜尋查詢的郵件。</span><span class="sxs-lookup"><span data-stu-id="5e686-139">The messages that match the query for this search will be deleted by running the **New-ComplianceSearchAction -Purge** command in [Step 3](#step-3-delete-the-message).</span></span> <span data-ttu-id="5e686-140">如需如何建立內容搜尋及設定搜尋查詢的資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="5e686-140">For information about creating a Content Search and configuring search queries, see the following topics:</span></span>

- [<span data-ttu-id="5e686-141">Office 365 中的內容搜尋</span><span class="sxs-lookup"><span data-stu-id="5e686-141">Content Search in Office 365</span></span>](content-search.md)

- [<span data-ttu-id="5e686-142">內容搜尋的關鍵字查詢</span><span class="sxs-lookup"><span data-stu-id="5e686-142">Keyword queries for Content Search</span></span>](keyword-queries-and-search-conditions.md)

- [<span data-ttu-id="5e686-143">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="5e686-143">New-ComplianceSearch</span></span>](/powershell/module/exchange/New-ComplianceSearch)

- [<span data-ttu-id="5e686-144">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="5e686-144">Start-ComplianceSearch</span></span>](/powershell/module/exchange/Start-ComplianceSearch)

> [!NOTE]
> <span data-ttu-id="5e686-145">在此步驟中建立的內容搜尋，其搜尋的內容位置不能包含 SharePoint 或商務用 OneDrive 網站。</span><span class="sxs-lookup"><span data-stu-id="5e686-145">The content locations that are searched in the Content Search that you create in this step can't include SharePoint or OneDrive for Business sites.</span></span> <span data-ttu-id="5e686-146">您只能在內容搜尋中包含將用於電子郵件的信箱和公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="5e686-146">You can include only mailboxes and public folders in a Content Search that will be used to email messages.</span></span> <span data-ttu-id="5e686-147">如果內容搜尋包含網站，則在步驟 3 中執行 **New-ComplianceSearchAction** Cmdlet 時會收到錯誤。</span><span class="sxs-lookup"><span data-stu-id="5e686-147">If the Content Search includes sites, you'll receive an error in Step 3 when you run the **New-ComplianceSearchAction** cmdlet.</span></span>

### <a name="tips-for-finding-messages-to-remove"></a><span data-ttu-id="5e686-148">尋找要移除郵件的提示</span><span class="sxs-lookup"><span data-stu-id="5e686-148">Tips for finding messages to remove</span></span>

<span data-ttu-id="5e686-p111">搜尋查詢的目標是將搜尋結果縮減為只有您想要移除的郵件。以下是一些提示：</span><span class="sxs-lookup"><span data-stu-id="5e686-p111">The goal of the search query is to narrow the results of the search to only the message or messages that you want to remove. Here are some tips:</span></span>

- <span data-ttu-id="5e686-151">如果您知道郵件主旨行中使用的確切文字或片語，請在搜尋查詢中使用 **Subject** 屬性。</span><span class="sxs-lookup"><span data-stu-id="5e686-151">If you know the exact text or phrase used in the subject line of the message, use the **Subject** property in the search query.</span></span>

- <span data-ttu-id="5e686-152">如果您知道郵件的實際日期 (或日期範圍)，請在搜尋查詢中包含 **Received** 屬性。</span><span class="sxs-lookup"><span data-stu-id="5e686-152">If you know that exact date (or date range) of the message, include the **Received** property in the search query.</span></span>

- <span data-ttu-id="5e686-153">如果您知道郵件的寄件者，請在搜尋查詢中包含 **From** 屬性。</span><span class="sxs-lookup"><span data-stu-id="5e686-153">If you know who sent the message, include the **From** property in the search query.</span></span>

- <span data-ttu-id="5e686-154">預覽搜尋結果，以確認內容搜尋僅傳回您想要刪除的郵件。</span><span class="sxs-lookup"><span data-stu-id="5e686-154">Preview the search results to verify that the search returned only the message (or messages) that you want to delete.</span></span>

- <span data-ttu-id="5e686-155">使用搜尋預估統計資料 (在安全性與合規性中心的搜尋詳細資料窗格中顯示，或使用 [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch) Cmdlet) 以取得結果總數。</span><span class="sxs-lookup"><span data-stu-id="5e686-155">Use the search estimate statistics (displayed in the details pane of the search in the Security & Compliance Center or by using the [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch) cmdlet) to get a count of the total number of results.</span></span>

<span data-ttu-id="5e686-156">以下是尋找可疑電子郵件訊息的兩個查詢範例。</span><span class="sxs-lookup"><span data-stu-id="5e686-156">Here are two examples of queries to find suspicious email messages.</span></span>

- <span data-ttu-id="5e686-157">此查詢傳回 2016 年 4 月 13 日和 2016 年 4 月 14 日之間使用者所接收的郵件，且在主旨列中包含文字「動作」和「必要」。</span><span class="sxs-lookup"><span data-stu-id="5e686-157">This query returns messages that were received by users between April 13, 2016 and April 14, 2016 and that contain the words "action" and "required" in the subject line.</span></span>

  ```powershell
  (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
  ```

- <span data-ttu-id="5e686-158">此查詢傳回 chatsuwloginsset12345@outlook.com 所送出的郵件，且在主旨列中包含精準字詞「更新您的帳戶資訊」。</span><span class="sxs-lookup"><span data-stu-id="5e686-158">This query returns messages that were sent by chatsuwloginsset12345@outlook.com and that contain the exact phrase "Update your account information" in the subject line.</span></span>

  ```powershell
  (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
  ```

<span data-ttu-id="5e686-159">以下是使用查詢來建立並開始搜尋的範例，方法是透過執行 **New-ComplianceSearch** 與 **Start-ComplianceSearch** Cmdlet 來搜尋組織中的所有郵件信箱：</span><span class="sxs-lookup"><span data-stu-id="5e686-159">Here's an example of using a query to create and start a search by running the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets to search all mailboxes in the organization:</span></span>

```powershell
$Search=New-ComplianceSearch -Name "Remove Phishing Message" -ExchangeLocation All -ContentMatchQuery '(Received:4/13/2016..4/14/2016) AND (Subject:"Action required")'
Start-ComplianceSearch -Identity $Search.Identity
```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="5e686-160">步驟 2︰連線至安全性與合規性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e686-160">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="5e686-161">下一步是將組織連線至安全性與合規性中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5e686-161">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="5e686-162">如需逐步指示，請參閱[連線至安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5e686-162">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

<span data-ttu-id="5e686-163">當您連線至安全性與合規性中心 PowerShell 之後，請執行在上一個步驟中準備好的 **New-ComplianceSearch** 與 **Start-ComplianceSearch** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5e686-163">After you've connected to Security & Compliance Center PowerShell, run the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets that you prepared in the previous step.</span></span>

## <a name="step-3-delete-the-message"></a><span data-ttu-id="5e686-164">步驟 3：刪除郵件</span><span class="sxs-lookup"><span data-stu-id="5e686-164">Step 3: Delete the message</span></span>

<span data-ttu-id="5e686-165">在您建立內容搜尋並進行調整以傳回您想要移除的郵件，並且連線至安全性與合規性 PowerShell 之後，最後一步是執行 **New-ComplianceSearchAction** Cmdlet 來刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="5e686-165">After you've created and refined a Content Search to return the message that you want to remove and are connected to Security & Compliance Center PowerShell, the final step is to run the **New-ComplianceSearchAction** cmdlet to delete the message.</span></span> <span data-ttu-id="5e686-166">您可以虛刪除或實刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="5e686-166">You can soft- or hard-delete the message.</span></span> <span data-ttu-id="5e686-167">虛刪除的郵件會移至使用者的 [可復原的項目] 資料夾並保留，直到刪除項目的保留期限到期為止。</span><span class="sxs-lookup"><span data-stu-id="5e686-167">A soft-deleted message is moved to a user's Recoverable Items folder and retained until the deleted item retention period expires.</span></span> <span data-ttu-id="5e686-168">實刪除的郵件則會在信箱中標示為永久移除，並在受管理的資料夾助理員下次處理信箱時將其永久移除。</span><span class="sxs-lookup"><span data-stu-id="5e686-168">Hard-deleted messages are marked for permanent removal from the mailbox and will be permanently removed the next time the mailbox is processed by the Managed Folder Assistant.</span></span> <span data-ttu-id="5e686-169">如果信箱啟用了單一項目復原，則會在刪除項目的保留期限到期後，永久刪除實刪除的項目。</span><span class="sxs-lookup"><span data-stu-id="5e686-169">If single item recovery is enabled for the mailbox, hard-deleted items will be permanently removed after the deleted item retention period expires.</span></span> <span data-ttu-id="5e686-170">如果信箱處於保留狀態，則會保留已刪除的郵件，直到該郵件的保留期間到期或從信箱移除保留為止。</span><span class="sxs-lookup"><span data-stu-id="5e686-170">If a mailbox is placed on hold, deleted messages are preserved until the hold duration for the item expires or until the hold is removed from the mailbox.</span></span>

<span data-ttu-id="5e686-171">在下列範例中，命令將會虛刪除名為「移除網路釣魚郵件」的內容搜尋所傳回的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="5e686-171">In the following example, the command soft-deletes the search results returned by a Content Search named "Remove Phishing Message".</span></span>

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

<span data-ttu-id="5e686-172">若要實刪除「移除網路釣魚郵件」內容搜尋所傳回的項目，您可以執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="5e686-172">To hard-delete the items returned by the "Remove Phishing Message" content search, you would run this command:</span></span>

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

<span data-ttu-id="5e686-173">當您執行上述命令來虛刪除或實刪除郵件時，*SearchName* 參數指定的搜尋是您在步驟 1 建立的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="5e686-173">When you run the previous command to soft- or hard-delete messages, the search specified by the  *SearchName*  parameter is the Content Search that you created in Step 1.</span></span>

<span data-ttu-id="5e686-174">如需詳細資訊，請參閱 [New-ComplianceSearchAction](/powershell/module/exchange/New-ComplianceSearchAction)。</span><span class="sxs-lookup"><span data-stu-id="5e686-174">For more information, see [New-ComplianceSearchAction](/powershell/module/exchange/New-ComplianceSearchAction).</span></span>

## <a name="more-information"></a><span data-ttu-id="5e686-175">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="5e686-175">More information</span></span>

- <span data-ttu-id="5e686-176">**如何取得搜尋和移除作業的狀態？**</span><span class="sxs-lookup"><span data-stu-id="5e686-176">**How do you get status on the search and remove operation?**</span></span>

  <span data-ttu-id="5e686-177">執行 **Get-ComplianceSearchAction** 可取得刪除作業的狀態。</span><span class="sxs-lookup"><span data-stu-id="5e686-177">Run the **Get-ComplianceSearchAction** to get the status on the delete operation.</span></span> <span data-ttu-id="5e686-178">當您執行 **New-ComplianceSearchAction** Cmdlet 時所建立的物件會使用下列格式命名：`<name of Content Search>_Purge`。</span><span class="sxs-lookup"><span data-stu-id="5e686-178">The object that is created when you run the **New-ComplianceSearchAction** cmdlet is named using this format:  `<name of Content Search>_Purge`.</span></span>

- <span data-ttu-id="5e686-179">**刪除郵件後，會發生什麼情況？**</span><span class="sxs-lookup"><span data-stu-id="5e686-179">**What happens after you delete a message?**</span></span>

  <span data-ttu-id="5e686-180">使用 `New-ComplianceSearchAction -Purge -PurgeType HardDelete` 命令刪除的郵件將被移至 [清除] 資料夾，且使用者無法再存取此郵件。</span><span class="sxs-lookup"><span data-stu-id="5e686-180">A message that's deleted with the  `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command is moved to the Purges folder and can't be accessed by the user.</span></span> <span data-ttu-id="5e686-181">郵件移至 [清除] 資料夾後，如果已針對信箱啟用單一項目復原，則會根據刪除項目的保留期限來保留郵件。</span><span class="sxs-lookup"><span data-stu-id="5e686-181">After the message is moved to the Purges folder, the message is retained for the duration of the deleted item retention period if single item recovery is enabled for the mailbox.</span></span> <span data-ttu-id="5e686-182">(在 Microsoft 365 中，建立新信箱時即會預設啟用單一項目復原。) 刪除項目的保留期限到期後，郵件將標示為永久刪除，並在受管理的資料夾助理員下次處理信箱時將其從 Microsoft 365 永久清除。</span><span class="sxs-lookup"><span data-stu-id="5e686-182">(In Microsoft 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Microsoft 365 the next time the mailbox is processed by the Managed Folder assistant.</span></span>

  <span data-ttu-id="5e686-183">如果您使用 `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` 命令，郵件會移至使用者 [可復原的項目] 資料夾中的 [刪除] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="5e686-183">If you use the `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` command, messages are moved to the Deletions folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="5e686-184">它不會立即從 Microsoft 365 中清除。</span><span class="sxs-lookup"><span data-stu-id="5e686-184">It isn't immediately purged from Microsoft 365.</span></span> <span data-ttu-id="5e686-185">使用者可以根據為信箱設定的刪除項目保留期間，在持續時間之內復原 [刪除的郵件] 資料夾中的郵件。</span><span class="sxs-lookup"><span data-stu-id="5e686-185">The user can recover messages in the Deleted Items folder for the duration based on the deleted item retention period configured for the mailbox.</span></span> <span data-ttu-id="5e686-186">此保留期間到期 (或者如果使用者在到期之前清除郵件) 之後，郵件會移至 [清除] 資料夾且使用者無法再存取。</span><span class="sxs-lookup"><span data-stu-id="5e686-186">After this retention period expires (or if user purges the message before it expires), the message is moved to the Purges folder and can no longer be accessed by the user.</span></span> <span data-ttu-id="5e686-187">郵件位在 [清除] 資料夾後，如果已針對信箱啟用單一項目復原，則會根據為信箱設定的刪除項目的保留期限來保留郵件。</span><span class="sxs-lookup"><span data-stu-id="5e686-187">Once in the Purges folder, the message is retained for the duration based on the deleted item retention period configured for the mailbox if single items recovery is enabled for the mailbox.</span></span> <span data-ttu-id="5e686-188">(在 Microsoft 365 中，建立新信箱時即會預設啟用單一項目復原。) 刪除項目的保留期限到期後，郵件將標示為永久刪除，並在受管理的資料夾助理員下次處理信箱時將其從 Microsoft 365 永久清除。</span><span class="sxs-lookup"><span data-stu-id="5e686-188">(In Microsoft 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Microsoft 365 the next time that the mailbox is processed by the Managed Folder assistant.</span></span>

- <span data-ttu-id="5e686-189">**如果要從 50,000 個以上的信箱刪除郵件，該怎麼辦？**</span><span class="sxs-lookup"><span data-stu-id="5e686-189">**What if you have to delete a message from more than 50,000 mailboxes?**</span></span>

  <span data-ttu-id="5e686-190">如先前所述，您可以針對最多 50,000 個信箱執行搜尋和清除作業 (即使包含符合搜尋查詢項目的信箱少於 50,000 個)</span><span class="sxs-lookup"><span data-stu-id="5e686-190">As previously stated, you can perform a search and purge operation on a maximum of 50,000 mailboxes (even if less than 50,000 contain items that match the search query).</span></span> <span data-ttu-id="5e686-191">如果必須對超過 50,000 個信箱執行搜尋和清除作業，請考慮建立臨時搜尋權限篩選條件，以便將搜尋到的信箱數減少為小於 50,000 個信箱。</span><span class="sxs-lookup"><span data-stu-id="5e686-191">If you have to do a search and purge operation on more than 50,000 mailboxes, consider creating temporary search permissions filters that reduce the number of mailboxes that would be searched to less than 50,000 mailboxes.</span></span> <span data-ttu-id="5e686-192">例如，如果您的組織包含不同部門、州或國家/地區的信箱，則可以基於其中一個信箱屬性建立信箱搜尋權限篩選條件，以搜尋組織中的信箱子集。</span><span class="sxs-lookup"><span data-stu-id="5e686-192">For example, if your organization contains mailboxes in different departments, states, or countries, you can create a mailbox search permissions filter based on one of those mailbox properties to search a subset of mailboxes in your organization.</span></span> <span data-ttu-id="5e686-193">建立搜尋權限篩選條件後，您可以建立搜尋 (如步驟 1 所述)，然後再刪除郵件 (如步驟 3 所述)。</span><span class="sxs-lookup"><span data-stu-id="5e686-193">After you create the search permissions filter, you would create the search (described in Step 1) and then delete the message (described in Step 3).</span></span> <span data-ttu-id="5e686-194">您可以編輯篩選條件來搜尋及清除不同組信箱中的郵件。</span><span class="sxs-lookup"><span data-stu-id="5e686-194">Then you can edit the filter to search for and purge messages in a different set of mailboxes.</span></span> <span data-ttu-id="5e686-195">如需建立搜尋權限篩選條件的詳細資訊，請參閱[設定內容搜尋的權限篩選](permissions-filtering-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="5e686-195">For more information about creating search permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>

- <span data-ttu-id="5e686-196">**搜尋結果中包含的未索引項目是否會被刪除？**</span><span class="sxs-lookup"><span data-stu-id="5e686-196">**Will unindexed items included in the search results be deleted?**</span></span>

  <span data-ttu-id="5e686-197">不會，\`New-ComplianceSearchAction -Purge 命令不會刪除未索引的項目。</span><span class="sxs-lookup"><span data-stu-id="5e686-197">No, the  \`New-ComplianceSearchAction -Purge command doesn't delete unindexed items.</span></span>

- <span data-ttu-id="5e686-198">**如果刪除位於就地保留或訴訟資料暫留的信箱中的郵件，或將郵件指派給 Microsoft 365 保留原則，會發生什麼情況？**</span><span class="sxs-lookup"><span data-stu-id="5e686-198">**What happens if a message is deleted from a mailbox that has been placed on In-Place Hold or Litigation Hold or is assigned to an Microsoft 365 retention policy?**</span></span>

  <span data-ttu-id="5e686-199">清除郵件並將其移動到 [清除] 資料夾後，郵件會保留，直到保留期限到期為止。</span><span class="sxs-lookup"><span data-stu-id="5e686-199">After the message is purged and moved to the Purges folder, the message is retained until the hold duration expires.</span></span> <span data-ttu-id="5e686-200">如果保留期限無限制，則項目會保留到移除保留或變更保留期限為止。</span><span class="sxs-lookup"><span data-stu-id="5e686-200">If the hold duration is unlimited, then items are retained until the hold is removed or the hold duration is changed.</span></span>

- <span data-ttu-id="5e686-201">**為何搜尋和移除工作流程在不同的安全性與合規性中心角色群組之間是分開的？**</span><span class="sxs-lookup"><span data-stu-id="5e686-201">**Why is the search and remove workflow divided among different security and compliance center role groups?**</span></span>

  <span data-ttu-id="5e686-202">如先前所述，使用者必須是「eDiscovery 管理員」角色群組的成員，或者獲指派「符合性搜尋」管理角色才能搜尋信箱。</span><span class="sxs-lookup"><span data-stu-id="5e686-202">As previously explained, a person has to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role to search mailboxes.</span></span> <span data-ttu-id="5e686-203">若要刪除郵件，該人員必須是「組織管理」角色群組的成員，或者獲指派「搜尋及清除」管理角色。</span><span class="sxs-lookup"><span data-stu-id="5e686-203">To delete messages, a person has to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="5e686-204">這樣就可以控制誰能夠在組織中搜尋信箱以及誰能夠刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="5e686-204">This makes it possible to control who can search mailboxes in the organization and who can delete messages.</span></span>
