---
title: 建立訴訟資料暫留
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: e6201fc938f7481a524a8d3c4171d4c1b67997e9
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076521"
---
# <a name="create-a-litigation-hold"></a><span data-ttu-id="92f29-102">建立訴訟資料暫留</span><span class="sxs-lookup"><span data-stu-id="92f29-102">Create a Litigation Hold</span></span>

<span data-ttu-id="92f29-103">您可以將信箱置於訴訟暫止來保留所有信箱內容，包括已刪除的項目和已修改項目的原始版本。</span><span class="sxs-lookup"><span data-stu-id="92f29-103">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items.</span></span> <span data-ttu-id="92f29-104">當您啟用使用者信箱訴訟暫止時，使用者的封存信箱中的內容 （如果已啟用） 會也保留。</span><span class="sxs-lookup"><span data-stu-id="92f29-104">When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained.</span></span> <span data-ttu-id="92f29-105">當您建立保留時，您可以指定保留期間 （也稱為*時間型保留*），以便刪除和修改過的項目會保留在指定期間內然後永久刪除信箱。</span><span class="sxs-lookup"><span data-stu-id="92f29-105">When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox.</span></span> <span data-ttu-id="92f29-106">您可以只會無限期保留內容或者 （稱為*無限期的保留*），或直到訴訟暫止已移除。</span><span class="sxs-lookup"><span data-stu-id="92f29-106">Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed.</span></span> <span data-ttu-id="92f29-107">如果您指定暫止持續時間，它會計算從日期接收郵件，或建立信箱項目。</span><span class="sxs-lookup"><span data-stu-id="92f29-107">If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="92f29-108">以下是當您建立訴訟暫止狀態時，會發生什麼事。</span><span class="sxs-lookup"><span data-stu-id="92f29-108">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="92f29-109">根據使用者時，會永久刪除的項目會保留在使用者的信箱中的 [可復原的項目] 資料夾保留期間。</span><span class="sxs-lookup"><span data-stu-id="92f29-109">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>
    
- <span data-ttu-id="92f29-110">會從 [可復原的項目] 資料夾清除使用者的項目會保留的保留期間。</span><span class="sxs-lookup"><span data-stu-id="92f29-110">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>
    
- <span data-ttu-id="92f29-111">從 30 GB 增加可復原的項目] 資料夾的儲存配額為 110 GB。</span><span class="sxs-lookup"><span data-stu-id="92f29-111">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>
    
- <span data-ttu-id="92f29-112">使用者的主要和封存信箱中的項目會保留</span><span class="sxs-lookup"><span data-stu-id="92f29-112">Items in the user's primary and the archive mailboxes are retained</span></span>
    
## <a name="before-you-begin"></a><span data-ttu-id="92f29-113">開始之前</span><span class="sxs-lookup"><span data-stu-id="92f29-113">Before you begin</span></span>

- <span data-ttu-id="92f29-114">若要啟用 Exchange Online 信箱訴訟暫止，它必須指派 Exchange Online Plan 2 授權。</span><span class="sxs-lookup"><span data-stu-id="92f29-114">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="92f29-115">如果信箱指派 Exchange Online Plan 1 授權，您必須指派不同 Exchange Online Archiving 授權，才能將它放在保留它。</span><span class="sxs-lookup"><span data-stu-id="92f29-115">If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    

## <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="92f29-116">將信箱設為訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="92f29-116">Place a mailbox on Litigation Hold</span></span>

<span data-ttu-id="92f29-117">以下是可讓信箱處於訴訟暫止使用 Exchange 系統管理中心的步驟。</span><span class="sxs-lookup"><span data-stu-id="92f29-117">Here are the steps to place a mailbox on Litigation Hold using the Exchange admin center.</span></span>

1. <span data-ttu-id="92f29-118">移至 [[https://outlook.office.com/ecp](https://outlook.office.com/ecp)並使用您的全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="92f29-118">Go to [https://outlook.office.com/ecp](https://outlook.office.com/ecp) and sign in using your global administrator account.</span></span>

2. <span data-ttu-id="92f29-119">在左側的導覽窗格中，按一下 [**收件者 > 信箱**。</span><span class="sxs-lookup"><span data-stu-id="92f29-119">Click **Recipients > Mailboxes** in the left navigation pane.</span></span>

3. <span data-ttu-id="92f29-120">選取您想要放置訴訟暫止的信箱，然後按一下 [**編輯**。</span><span class="sxs-lookup"><span data-stu-id="92f29-120">Select the mailbox that you want to place on Litigation Hold, and then click **Edit**.</span></span>

4. <span data-ttu-id="92f29-121">在信箱內容頁面上，按一下 [**信箱功能**]。</span><span class="sxs-lookup"><span data-stu-id="92f29-121">On the mailbox properties page, click **Mailbox features**.</span></span>
    
5. <span data-ttu-id="92f29-122">[**訴訟暫止： 停用**，按一下 [**啟用**]，以讓信箱處於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="92f29-122">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span>
    
6. <span data-ttu-id="92f29-123">在 [**訴訟暫止**] 頁面上，輸入下列選擇性資訊：</span><span class="sxs-lookup"><span data-stu-id="92f29-123">On the **Litigation hold** page, enter the following optional information:</span></span> 
    
    - <span data-ttu-id="92f29-124">**訴訟暫止持續時間 （天）** -使用此方塊來建立時間型保留，並指定當信箱處於訴訟暫止的信箱項目保留多久。</span><span class="sxs-lookup"><span data-stu-id="92f29-124">**Litigation hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold.</span></span> <span data-ttu-id="92f29-125">持續時間自接收或建立信箱項目的日期開始計算。</span><span class="sxs-lookup"><span data-stu-id="92f29-125">The duration is calculated from the date a mailbox item is received or created.</span></span> <span data-ttu-id="92f29-126">當保留期間到期時的特定項目時，則不再會保留該項目。</span><span class="sxs-lookup"><span data-stu-id="92f29-126">When the hold duration expires for a specific item, that item will no longer be preserved.</span></span> <span data-ttu-id="92f29-127">如果您將此方塊保留空白，項目會保留無限期或保留到移除保留為止。</span><span class="sxs-lookup"><span data-stu-id="92f29-127">If you leave this box blank, items are preserved indefinitely or until the hold is removed.</span></span> <span data-ttu-id="92f29-128">請使用天數為單位來指定持續時間。</span><span class="sxs-lookup"><span data-stu-id="92f29-128">Use days to specify the duration.</span></span>
    
    - <span data-ttu-id="92f29-129">**附註**-使用此方塊告知使用者他們的信箱處於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="92f29-129">**Note** - Use this box to inform the user their mailbox is on Litigation Hold.</span></span> <span data-ttu-id="92f29-130">附註會出現在使用者的信箱中的 [帳戶資訊] 頁面上，如果他們使用 Outlook 2010 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="92f29-130">The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later.</span></span> <span data-ttu-id="92f29-131">若要存取此頁面上，使用者可以按一下 [在 Outlook 中的**檔案**。</span><span class="sxs-lookup"><span data-stu-id="92f29-131">To access this page, users can click **File** in Outlook.</span></span>
    
    - <span data-ttu-id="92f29-132">**URL** -使用此方塊以將使用者導向至網站，使其訴訟暫止狀態的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="92f29-132">**URL** - Use this box to direct the user to a website for more information about Litigation Hold.</span></span> <span data-ttu-id="92f29-133">如果他們使用 Outlook 2010 或更新版本，此 URL 會顯示在使用者的信箱中的 [帳戶資訊] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="92f29-133">This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later.</span></span> <span data-ttu-id="92f29-134">若要存取此頁面上，使用者可以按一下 [在 Outlook 中的**檔案**。.</span><span class="sxs-lookup"><span data-stu-id="92f29-134">To access this page, users can click **File** in Outlook..</span></span>

7. <span data-ttu-id="92f29-135">在 [**訴訟暫止**] 頁面上，按一下 [**儲存**，然後按一下 [信箱內容] 頁面上的 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="92f29-135">Click **Save** on the **Litigation hold** page, and then click **Save** on the mailbox properties page.</span></span>

### <a name="create-a-litigation-hold-using-powershell"></a><span data-ttu-id="92f29-136">建立使用 PowerShell 訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="92f29-136">Create a Litigation Hold using PowerShell</span></span>

<span data-ttu-id="92f29-137">您也可以建立訴訟暫止狀態，藉由[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="92f29-137">You can also create a Litigation Hold by running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):</span></span>

```
Set-Mailbox <username> -LitigationHoldEnabled $true
```

<span data-ttu-id="92f29-138">上述命令會無限期保留項目因為未指定保留期間。</span><span class="sxs-lookup"><span data-stu-id="92f29-138">The previous command preserves items indefinitely because the hold duration isn't specified.</span></span> <span data-ttu-id="92f29-139">若要建立時間型保留時，使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="92f29-139">To created a time-based hold, using the following command:</span></span>

```
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

<span data-ttu-id="92f29-140">如需詳細資訊，請參閱[Set-mailbox](https://docs.microsoft.com/en-us/powershell/module/exchange/mailboxes/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="92f29-140">For more information, see [Set-Mailbox](https://docs.microsoft.com/en-us/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

## <a name="how-does-litigation-hold-work"></a><span data-ttu-id="92f29-141">訴訟暫止如何運作？</span><span class="sxs-lookup"><span data-stu-id="92f29-141">How does Litigation Hold work?</span></span>

<span data-ttu-id="92f29-142">在正常刪除項目工作流程中，當使用者永久刪除 (Shift+Delete) 或從 [刪除的項目] 資料夾中刪除項目時，信箱項目會移至 [可復原的項目] 資料夾中的 [刪除] 子資料夾。</span><span class="sxs-lookup"><span data-stu-id="92f29-142">In the normal deleted item workflow, a mailbox item is moved to the Deletions subfolder in the Recoverable Items folder when a user permanently deletes it (Shift + Delete) or deletes it from the Deleted Items folder.</span></span> <span data-ttu-id="92f29-143">當保留期間到期時，刪除原則 (也就是以刪除保留動作設定的保留標記) 也會將項目移至 [刪除] 子資料夾。</span><span class="sxs-lookup"><span data-stu-id="92f29-143">A deletion policy (which is a retention tag configured with a Delete retention action) also moves items to the Deletions subfolder when the retention period expires.</span></span> <span data-ttu-id="92f29-144">當使用者清除 [可復原的項目] 資料夾中的項目，或已刪除項目的保留期間到期時，項目會移至 [可復原的項目] 資料夾中的 [清除] 子資料夾並標示為永久刪除。</span><span class="sxs-lookup"><span data-stu-id="92f29-144">When a user purges an item in the Recoverable Items folder or when the deleted item retention period expires for an item, it's moved to the Purges subfolder in the Recoverable Items folder and marked for permanent deletion.</span></span> <span data-ttu-id="92f29-145">系統會在下一次受管理的資料夾助理員 (MFA) 處理信箱時，從 Exchange 清除項目。</span><span class="sxs-lookup"><span data-stu-id="92f29-145">It will be purged from Exchange the next time the mailbox is processed by the Managed Folder Assistant (MFA).</span></span>

<span data-ttu-id="92f29-p108">當信箱處於訴訟暫止狀態時，[清除] 子資料夾中的項目會依訴訟暫止所指定的保留期間予以保留。保留期間是由接收或建立項目的原始日期開始計算，並定義 [清除] 子資料夾中的項目會保留多久。[清除] 子資料夾中的項目保留期間到期時，項目將標示為永久刪除，並在下一次 MFA 處理信箱時，從 Exchange清除。若信箱設為無限期保留，項目將不會從 [清除] 子資料夾中清除。</span><span class="sxs-lookup"><span data-stu-id="92f29-p108">When a mailbox is placed on Litigation Hold, items in the Purges subfolder are preserved for the hold duration specified by the Litigation Hold. The hold duration is calculated from the original date an item was received or created, and defines how long items in the Purges subfolder are held. When the hold duration expires for an item in the Purges subfolder, the item is marked for permanent deletion and will be purged from Exchange the next time the mailbox is processed by the MFA. If an indefinite hold is placed on a mailbox, items will never be purged from the Purges subfolder.</span></span>

<span data-ttu-id="92f29-150">下圖顯示在 [可復原的項目] 資料夾中的子資料夾以及並保留工作流程程序。</span><span class="sxs-lookup"><span data-stu-id="92f29-150">The following illustration shows the subfolders in the Recoverable Items folders and the hold workflow process.</span></span>

![訴訟暫止生命週期](media/LitigationHoldLifeCycle.png)

> [!NOTE]
> <span data-ttu-id="92f29-152">如果 eDiscovery 案例相關聯保留在信箱上，清除項目會從 [刪除] 子資料夾移到 [DiscoveryHolds] 子資料夾，並會保留直到信箱釋放 eDiscovery 保留中。</span><span class="sxs-lookup"><span data-stu-id="92f29-152">If a hold associated with an eDiscovery case is placed on a mailbox, purged items are moved from the Deletions subfolder to the DiscoveryHolds subfolder and are preserved until the mailbox is released from the eDiscovery hold.</span></span>
  