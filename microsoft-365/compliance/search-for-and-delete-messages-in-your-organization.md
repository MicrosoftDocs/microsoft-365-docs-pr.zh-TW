---
title: 搜尋並刪除 Office 365 組織中的電子郵件
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
description: 使用 Office 365 中安全性與合規性中心的搜尋和清除功能，可搜尋並刪除組織中所有信箱的電子郵件訊息。
ms.openlocfilehash: c05b6addf2fe50a5e6130e3c53fa1df02e50de30
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/15/2020
ms.locfileid: "43516828"
---
# <a name="search-for-and-delete-email-messages"></a><span data-ttu-id="3fcbf-103">搜尋並刪除電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="3fcbf-103">Search for and delete email messages</span></span>

<span data-ttu-id="3fcbf-104">**本文適用於系統管理員。您正嘗試在信箱中尋找要刪除的項目嗎？請參閱[使用立即搜尋尋找郵件或項目](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-104">**This article is for administrators. Are you trying to find items in your mailbox that you want to delete? See [Find a message or item with Instant Search](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**.</span></span>
   
<span data-ttu-id="3fcbf-105">您可以使用 Office365 中的內容搜尋功能來搜尋並刪除組織中所有信箱的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-105">You can use the Content Search feature in Office 365 to search for and delete an email message from all mailboxes in your organization.</span></span> <span data-ttu-id="3fcbf-106">這可幫助您找出並移除可能有害或高風險的電子郵件，例如：</span><span class="sxs-lookup"><span data-stu-id="3fcbf-106">This can help you find and remove potentially harmful or high-risk email, such as:</span></span>
  
- <span data-ttu-id="3fcbf-107">含有危險附件或病毒的郵件</span><span class="sxs-lookup"><span data-stu-id="3fcbf-107">Messages that contain dangerous attachments or viruses</span></span>

- <span data-ttu-id="3fcbf-108">網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="3fcbf-108">Phishing messages</span></span>

- <span data-ttu-id="3fcbf-109">包含敏感資料的郵件</span><span class="sxs-lookup"><span data-stu-id="3fcbf-109">Messages that contain sensitive data</span></span>

> [!CAUTION]
> <span data-ttu-id="3fcbf-110">搜尋和清除是一個強大的功能，可讓獲指派必要權限的任何人刪除組織信箱的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-110">Search and purge is a powerful feature that allows anyone that is assigned the necessary permissions to delete email messages from mailboxes in your organization.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="3fcbf-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="3fcbf-111">Before you begin</span></span>

- <span data-ttu-id="3fcbf-112">若要建立和執行內容搜尋，您必須是「eDiscovery 管理員」\*\*\*\* 角色群組的成員，或者獲指派「合規性搜尋」\*\*\*\* 管理角色。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-112">To create and run a Content Search, you have to be a member of the **eDiscovery Manager** role group or be assigned the **Compliance Search** management role.</span></span> <span data-ttu-id="3fcbf-113">若要刪除郵件，您必須是「組織管理」\*\*\*\* 角色群組的成員，或者獲指派「搜尋及清除」\*\*\*\* 管理角色。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-113">To delete messages, you have to be a member of the **Organization Management** role group or be assigned the **Search And Purge** management role.</span></span> <span data-ttu-id="3fcbf-114">如需新增使用者至角色群組的詳細資訊，請參閱[在安全性與合規性中心中指派電子文件探索權限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-114">For information about adding users to a role group, see [Assign eDiscovery permissions in the Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="3fcbf-115">您必須使用安全性與合規性中心 PowerShell 來刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-115">You have to use Security & Compliance Center PowerShell to delete messages.</span></span> <span data-ttu-id="3fcbf-116">如需如何連線的相關指示，請參閱[步驟 2](#step-2-connect-to-security--compliance-center-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-116">See [Step 2](#step-2-connect-to-security--compliance-center-powershell) for instructions about how to connect.</span></span>
    
- <span data-ttu-id="3fcbf-117">每個信箱一次可以移除最多 10 個項目。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-117">A maximum of 10 items per mailbox can be removed at one time.</span></span> <span data-ttu-id="3fcbf-118">因為搜尋和移除郵件的功能應該是事件回應工具，此限制可以協助確保從信箱快速移除郵件。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-118">Because the capability to search for and remove messages is intended to be an incident-response tool, this limit helps ensure that messages are quickly removed from mailboxes.</span></span> <span data-ttu-id="3fcbf-119">這項功能不是用來清除使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-119">This feature isn't intended to clean up user mailboxes.</span></span>
    
- <span data-ttu-id="3fcbf-120">透過搜尋及清除動作，您最多可以在內容搜尋刪除 50,000 個信箱內的項目。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-120">The maximum number of mailboxes in a Content Search that you can delete items in by doing a search and purge action is 50,000.</span></span> <span data-ttu-id="3fcbf-121">如果內容搜尋 (您在[步驟 1 ](#step-1-create-a-content-search-to-find-the-message-to-delete)中建立) 中有超過 50,000 個來源信箱，則您在步驟 3 中建立的清除動作將失敗。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-121">If the Content Search (that you create in [Step 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) has more than 50,000 source mailboxes, the purge action (that you create in Step 3) will fail.</span></span> <span data-ttu-id="3fcbf-122">請參閱[詳細資訊](#more-information)章節以取得搜尋並清除超過 50,000 個信箱的執行提示。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-122">See the [More information](#more-information) section for a tip on performing a search and purge operation on more than 50,000 mailboxes.</span></span> 
    
- <span data-ttu-id="3fcbf-123">本文所述的程序只能用於刪除 Exchange Online 信箱和公用資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-123">The procedure in this article can only be used to delete items in Exchange Online mailboxes and public folders.</span></span> <span data-ttu-id="3fcbf-124">您無法使用這個程序來刪除 SharePoint 或商務用 OneDrive 上的內容。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-124">You can't use it to delete content from SharePoint or OneDrive for Business sites.</span></span>
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a><span data-ttu-id="3fcbf-125">步驟 1：建立內容搜尋來尋找要刪除的郵件</span><span class="sxs-lookup"><span data-stu-id="3fcbf-125">Step 1: Create a Content Search to find the message to delete</span></span>

<span data-ttu-id="3fcbf-126">第一個步驟是建立和執行內容搜尋，以尋找您想要從組織中的信箱移除的郵件。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-126">The first step is to create and run a Content Search to find the message that you want to remove from mailboxes in your organization.</span></span> <span data-ttu-id="3fcbf-127">您可以使用安全性與合規性中心或執行 **New-ComplianceSearch** 以及 **Start-ComplianceSearch** Cmdlet 來建立搜尋。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-127">You can create the search by using the Security & Compliance Center or by running the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets.</span></span> <span data-ttu-id="3fcbf-128">藉由在[步驟 3](#step-3-delete-the-message) 中執行 **New-ComplianceSearchAction -Purge** 命令，會刪除符合此搜尋查詢的郵件。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-128">The messages that match the query for this search will be deleted by running the **New-ComplianceSearchAction -Purge** command in [Step 3](#step-3-delete-the-message).</span></span> <span data-ttu-id="3fcbf-129">如需如何建立內容搜尋及設定搜尋查詢的資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="3fcbf-129">For information about creating a Content Search and configuring search queries, see the following topics:</span></span> 
  
- [<span data-ttu-id="3fcbf-130">Office 365 中的內容搜尋</span><span class="sxs-lookup"><span data-stu-id="3fcbf-130">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="3fcbf-131">內容搜尋的關鍵字查詢</span><span class="sxs-lookup"><span data-stu-id="3fcbf-131">Keyword queries for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="3fcbf-132">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="3fcbf-132">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [<span data-ttu-id="3fcbf-133">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="3fcbf-133">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> <span data-ttu-id="3fcbf-134">在此步驟中建立的內容搜尋，其搜尋的內容位置不能包含 SharePoint 或商務用 OneDrive 網站。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-134">The content locations that are searched in the Content Search that you create in this step can't include SharePoint or OneDrive for Business sites.</span></span> <span data-ttu-id="3fcbf-135">您只能在內容搜尋中包含將用於電子郵件的信箱和公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-135">You can include only mailboxes and public folders in a Content Search that will be used to email messages.</span></span> <span data-ttu-id="3fcbf-136">如果內容搜尋包含網站，則在步驟 3 中執行 \*\*New-ComplianceSearchAction \*\* Cmdlet 時會收到錯誤。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-136">If the Content Search includes sites, you'll receive an error in Step 3 when you run the **New-ComplianceSearchAction** cmdlet.</span></span> 
  
### <a name="tips-for-finding-messages-to-remove"></a><span data-ttu-id="3fcbf-137">尋找要移除郵件的提示</span><span class="sxs-lookup"><span data-stu-id="3fcbf-137">Tips for finding messages to remove</span></span>

<span data-ttu-id="3fcbf-p109">搜尋查詢的目標是將搜尋結果縮減為只有您想要移除的郵件。以下是一些提示：</span><span class="sxs-lookup"><span data-stu-id="3fcbf-p109">The goal of the search query is to narrow the results of the search to only the message or messages that you want to remove. Here are some tips:</span></span>
  
- <span data-ttu-id="3fcbf-140">如果您知道郵件主旨行中使用的確切文字或片語，請在搜尋查詢中使用 **Subject** 屬性。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-140">If you know the exact text or phrase used in the subject line of the message, use the **Subject** property in the search query.</span></span> 
    
- <span data-ttu-id="3fcbf-141">如果您知道郵件的實際日期 (或日期範圍)，請在搜尋查詢中包含 **Received** 屬性。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-141">If you know that exact date (or date range) of the message, include the **Received** property in the search query.</span></span> 
    
- <span data-ttu-id="3fcbf-142">如果您知道郵件的寄件者，請在搜尋查詢中包含 **From** 屬性。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-142">If you know who sent the message, include the **From** property in the search query.</span></span> 
    
- <span data-ttu-id="3fcbf-143">預覽搜尋結果，以確認內容搜尋僅傳回您想要刪除的郵件。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-143">Preview the search results to verify that the search returned only the message (or messages) that you want to delete.</span></span>
    
- <span data-ttu-id="3fcbf-144">使用搜尋預估統計資料 (在安全性與合規性中心的搜尋詳細資料窗格中顯示，或使用 [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) Cmdlet) 以取得結果總數。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-144">Use the search estimate statistics (displayed in the details pane of the search in the Security & Compliance Center or by using the [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet) to get a count of the total number of results.</span></span> 
    
<span data-ttu-id="3fcbf-145">以下是尋找可疑電子郵件訊息的兩個查詢範例。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-145">Here are two examples of queries to find suspicious email messages.</span></span>
  
- <span data-ttu-id="3fcbf-146">此查詢傳回 2016 年 4 月 13 日和 2016 年 4 月 14 日之間使用者所接收的郵件，且在主旨列中包含文字「動作」和「必要」。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-146">This query returns messages that were received by users between April 13, 2016 and April 14, 2016 and that contain the words "action" and "required" in the subject line.</span></span>
    
    ```powershell
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```

- <span data-ttu-id="3fcbf-147">此查詢傳回 chatsuwloginsset12345@outlook.com 所送出的郵件，且在主旨列中包含精準字詞「更新您的帳戶資訊」。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-147">This query returns messages that were sent by chatsuwloginsset12345@outlook.com and that contain the exact phrase "Update your account information" in the subject line.</span></span>
    
    ```powershell
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

<span data-ttu-id="3fcbf-148">以下是使用查詢來建立並開始搜尋的範例，方法是透過執行 **New-ComplianceSearch** 與 **Start-ComplianceSearch** Cmdlet 來搜尋組織中的所有郵件信箱：</span><span class="sxs-lookup"><span data-stu-id="3fcbf-148">Here's an example of using a query to create and start a search by running the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets to search all mailboxes in the organization:</span></span>

```powershell
$Search=New-ComplianceSearch -Name "Remove Phishing Message" -ExchangeLocation All -ContentMatchQuery '(Received:4/13/2016..4/14/2016) AND (Subject:"Action required")'
Start-ComplianceSearch -Identity $Search.Identity
```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="3fcbf-149">步驟 2︰連線至安全性與合規性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fcbf-149">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="3fcbf-150">下一步是將組織連線至安全性與合規性中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-150">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="3fcbf-151">如需逐步指示，請參閱[連線至安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-151">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
<span data-ttu-id="3fcbf-152">如果您的 Office 365 帳戶使用多重要素驗證 (MFA) 或同盟驗證，您就無法使用前個主題中的指示來連線至安全性與合規性中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-152">If your Office 365 account uses multi-factor authentication (MFA) or federated authentication, you can't use the instructions in the previous topic on connecting to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="3fcbf-153">您應改為參閱[使用多重要素驗證連線至安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)中的指示。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-153">Instead, see the instructions in the topic [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span></span>

<span data-ttu-id="3fcbf-154">當您連線至安全性與合規性中心 PowerShell 之後，請執行在上一個步驟中準備好的 **New-ComplianceSearch** 與 **Start-ComplianceSearch** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-154">After you've connected to Security & Compliance Center PowerShell, run the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets that you prepared in the previous step.</span></span>
  
## <a name="step-3-delete-the-message"></a><span data-ttu-id="3fcbf-155">步驟 3：刪除郵件</span><span class="sxs-lookup"><span data-stu-id="3fcbf-155">Step 3: Delete the message</span></span>

<span data-ttu-id="3fcbf-156">在您建立內容搜尋並進行調整以傳回您想要移除的郵件，並且連線至安全性與合規性 PowerShell 之後，最後一步是執行 **New-ComplianceSearchAction** Cmdlet 來刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-156">After you've created and refined a Content Search to return the message that you want to remove and are connected to Security & Compliance Center PowerShell, the final step is to run the **New-ComplianceSearchAction** cmdlet to delete the message.</span></span> <span data-ttu-id="3fcbf-157">您可以虛刪除或實刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-157">You can soft- or hard-delete the message.</span></span> <span data-ttu-id="3fcbf-158">虛刪除的郵件會移至使用者的 [可復原的項目] 資料夾並保留，直到刪除項目的保留期限到期為止。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-158">A soft-deleted message is moved to a user's Recoverable Items folder and retained until the deleted item retention period expires.</span></span> <span data-ttu-id="3fcbf-159">實刪除的郵件則會在信箱中標示為永久移除，並在受管理的資料夾助理員下次處理信箱時將其永久移除。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-159">Hard-deleted messages are marked for permanent removal from the mailbox and will be permanently removed the next time the mailbox is processed by the Managed Folder Assistant.</span></span> <span data-ttu-id="3fcbf-160">如果信箱啟用了單一項目復原，則會在刪除項目的保留期限到期後，永久刪除實刪除的項目。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-160">If single item recovery is enabled for the mailbox, hard-deleted items will be permanently removed after the deleted item retention period expires.</span></span> <span data-ttu-id="3fcbf-161">如果信箱處於保留狀態，則會保留已刪除的郵件，直到該郵件的保留期間到期或從信箱移除保留為止。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-161">If a mailbox is placed on hold, deleted messages are preserved until the hold duration for the item expires or until the hold is removed from the mailbox.</span></span>
  
<span data-ttu-id="3fcbf-162">在下列範例中，命令將會虛刪除名為「移除網路釣魚郵件」的內容搜尋所傳回的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-162">In the following example, the command soft-deletes the search results returned by a Content Search named "Remove Phishing Message".</span></span> 

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

<span data-ttu-id="3fcbf-163">若要實刪除「移除網路釣魚郵件」內容搜尋所傳回的項目，您可以執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="3fcbf-163">To hard-delete the items returned by the "Remove Phishing Message" content search, you would run this command:</span></span>

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

<span data-ttu-id="3fcbf-164">當您執行上述命令來虛刪除或實刪除郵件時，*SearchName* 參數指定的搜尋是您在步驟 1 建立的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-164">When you run the previous command to soft- or hard-delete messages, the search specified by the  *SearchName*  parameter is the Content Search that you created in Step 1.</span></span> 
  
<span data-ttu-id="3fcbf-165">如需詳細資訊，請參閱 [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction) (英文)。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-165">For more information, see [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction).</span></span>

## <a name="more-information"></a><span data-ttu-id="3fcbf-166">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="3fcbf-166">More information</span></span>

- <span data-ttu-id="3fcbf-167">**如何取得搜尋和移除作業的狀態？**</span><span class="sxs-lookup"><span data-stu-id="3fcbf-167">**How do you get status on the search and remove operation?**</span></span>

    <span data-ttu-id="3fcbf-168">執行 **Get-ComplianceSearchAction** 可取得刪除作業的狀態。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-168">Run the **Get-ComplianceSearchAction** to get the status on the delete operation.</span></span> <span data-ttu-id="3fcbf-169">當您執行 **New-ComplianceSearchAction** Cmdlet 時所建立的物件會使用下列格式命名：`<name of Content Search>_Purge`。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-169">The object that is created when you run the **New-ComplianceSearchAction** cmdlet is named using this format:  `<name of Content Search>_Purge`.</span></span> 
    
- <span data-ttu-id="3fcbf-170">**刪除郵件後，會發生什麼情況？**</span><span class="sxs-lookup"><span data-stu-id="3fcbf-170">**What happens after you delete a message?**</span></span>

   <span data-ttu-id="3fcbf-171">使用 `New-ComplianceSearchAction -Purge -PurgeType HardDelete` 命令刪除的郵件將被移至 [清除] 資料夾，且使用者無法再存取此郵件。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-171">A message that's deleted with the  `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command is moved to the Purges folder and can't be accessed by the user.</span></span> <span data-ttu-id="3fcbf-172">郵件移至 [清除] 資料夾後，如果已針對信箱啟用單一項目復原，則會根據刪除項目的保留期限來保留郵件。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-172">After the message is moved to the Purges folder, the message is retained for the duration of the deleted item retention period if single item recovery is enabled for the mailbox.</span></span> <span data-ttu-id="3fcbf-173">(在 Office 365 中，建立新信箱時即會預設啟用單一項目復原。) 刪除項目的保留期限到期後，郵件將標示為永久刪除，並在受管理的資料夾助理員下次處理信箱時將其從 Office 365 永久清除。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-173">(In Office 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Office 365 the next time the mailbox is processed by the Managed Folder assistant.</span></span> 

   <span data-ttu-id="3fcbf-174">如果您使用 `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` 命令，郵件會移至使用者 [可復原的項目] 資料夾中的 [刪除] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-174">If you use the `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` command, messages are moved to the Deletions folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="3fcbf-175">它不會立即從 Office365 中清除。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-175">It isn't immediately purged from Office 365.</span></span> <span data-ttu-id="3fcbf-176">使用者可以根據為信箱設定的刪除項目保留期間，在持續時間之內復原 [刪除的郵件] 資料夾中的郵件。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-176">The user can recover messages in the Deleted Items folder for the duration based on the deleted item retention period configured for the mailbox.</span></span> <span data-ttu-id="3fcbf-177">此保留期間到期 (或者如果使用者在到期之前清除郵件) 之後，郵件會移至 [清除] 資料夾且使用者無法再存取。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-177">After this retention period expires (or if user purges the message before it expires), the message is moved to the Purges folder and can no longer be accessed by the user.</span></span> <span data-ttu-id="3fcbf-178">郵件位在 [清除] 資料夾後，如果已針對信箱啟用單一項目復原，則會根據為信箱設定的刪除項目的保留期限來保留郵件。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-178">Once in the Purges folder, the message is retained for the duration based on the deleted item retention period configured for the mailbox if single items recovery is enabled for the mailbox.</span></span> <span data-ttu-id="3fcbf-179">(在 Office 365 中，建立新信箱時即會預設啟用單一項目復原。) 刪除項目的保留期限到期後，郵件將標示為永久刪除，並在受管理的資料夾助理員下次處理信箱時將其從 Office 365 永久清除。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-179">(In Office 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Office 365 the next time that the mailbox is processed by the Managed Folder assistant.</span></span> 
    
- <span data-ttu-id="3fcbf-180">**如果要從 50,000 個以上的信箱刪除郵件，該怎麼辦？**</span><span class="sxs-lookup"><span data-stu-id="3fcbf-180">**What if you have to delete a message from more than 50,000 mailboxes?**</span></span>

    <span data-ttu-id="3fcbf-181">如先前所述，您可以針對最多 50,000 個信箱執行搜尋和清除作業。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-181">As previously stated, you can perform a search and purge operation on a maximum of 50,000 mailboxes.</span></span> <span data-ttu-id="3fcbf-182">如果必須對超過 50,000 個信箱執行搜尋和清除作業，請考慮建立臨時搜尋權限篩選條件，以便將搜尋到的信箱數減少為小於 50,000 個信箱。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-182">If you have to do a search and purge operation on more than 50,000 mailboxes, consider creating temporary search permissions filters that would reduce the number of mailboxes that would be searched to less than 50,000 mailboxes.</span></span> <span data-ttu-id="3fcbf-183">例如，如果您的組織包含不同部門、州或國家/地區的信箱，則可以基於其中一個信箱屬性建立信箱搜尋權限篩選條件，以搜尋組織中的信箱子集。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-183">For example, if your organization contains mailboxes in different departments, states, or countries, you can create a mailbox search permissions filter based on one of those mailbox properties to search a subset of mailboxes in your organization.</span></span> <span data-ttu-id="3fcbf-184">建立搜尋權限篩選條件後，您可以建立搜尋 (如步驟 1 所述)，然後再刪除郵件 (如步驟 3 所述)。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-184">After you create the search permissions filter, you would create the search (described in Step 1) and then delete the message (described in Step 3).</span></span> <span data-ttu-id="3fcbf-185">您可以編輯篩選條件來搜尋及清除不同組信箱中的郵件。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-185">Then you can edit the filter to search for and purge messages in a different set of mailboxes.</span></span> <span data-ttu-id="3fcbf-186">如需建立搜尋權限篩選條件的詳細資訊，請參閱[設定內容搜尋的權限篩選](permissions-filtering-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-186">For more information about creating search permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
    
- <span data-ttu-id="3fcbf-187">**搜尋結果中包含的未索引項目是否會被刪除？**</span><span class="sxs-lookup"><span data-stu-id="3fcbf-187">**Will unindexed items included in the search results be deleted?**</span></span>

    <span data-ttu-id="3fcbf-188">不會，\`New-ComplianceSearchAction -Purge 命令不會刪除未索引的項目。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-188">No, the  \`New-ComplianceSearchAction -Purge command doesn't delete unindexed items.</span></span> 
    
- <span data-ttu-id="3fcbf-189">**如果將已放置在就地保留或訴訟資料暫留的信箱中的郵件刪除，或將郵件指派給 Office 365 保留原則，會發生什麼情況？**</span><span class="sxs-lookup"><span data-stu-id="3fcbf-189">**What happens if a message is deleted from a mailbox that has been placed on In-Place Hold or Litigation Hold or is assigned to an Office 365 retention policy?**</span></span>

    <span data-ttu-id="3fcbf-190">清除郵件並將其移動到 [清除] 資料夾後，郵件會保留，直到保留期限到期為止。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-190">After the message is purged and moved to the Purges folder, the message is retained until the hold duration expires.</span></span> <span data-ttu-id="3fcbf-191">如果保留期限無限制，則項目會保留到移除保留或變更保留期限為止。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-191">If the hold duration is unlimited, then items are retained until the hold is removed or the hold duration is changed.</span></span>
    
- <span data-ttu-id="3fcbf-192">**為何搜尋和移除工作流程在不同的安全性與合規性中心角色群組之間是分開的？**</span><span class="sxs-lookup"><span data-stu-id="3fcbf-192">**Why is the search and remove workflow divided among different security and compliance center role groups?**</span></span>

    <span data-ttu-id="3fcbf-193">如先前所述，使用者必須是「eDiscovery 管理員」角色群組的成員，或者獲指派「符合性搜尋」管理角色才能搜尋信箱。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-193">As previously explained, a person has to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role to search mailboxes.</span></span> <span data-ttu-id="3fcbf-194">若要刪除郵件，該人員必須是「組織管理」角色群組的成員，或者獲指派「搜尋及清除」管理角色。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-194">To delete messages, a person has to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="3fcbf-195">這樣就可以控制誰能夠在組織中搜尋信箱以及誰能夠刪除郵件。</span><span class="sxs-lookup"><span data-stu-id="3fcbf-195">This makes it possible to control who can search mailboxes in the organization and who can delete messages.</span></span> 
