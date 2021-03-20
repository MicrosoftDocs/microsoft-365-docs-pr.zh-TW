---
title: 建立訴訟資料暫留
f1.keywords:
- NOCSH
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
description: 瞭解如何將信箱設為訴訟暫止，並在調查期間保留所有信箱內容。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 046ee6fdc7c42026b1a69805883175982e3100b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908397"
---
# <a name="create-a-litigation-hold"></a><span data-ttu-id="b1f1a-103">建立訴訟資料暫留</span><span class="sxs-lookup"><span data-stu-id="b1f1a-103">Create a Litigation Hold</span></span>

<span data-ttu-id="b1f1a-104">您可以將信箱設為訴訟暫止，以保留所有信箱內容，包括已刪除的專案和已修改專案的原始版本。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-104">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items.</span></span> <span data-ttu-id="b1f1a-105">當您將使用者的信箱設為訴訟暫止時，使用者封存信箱中的內容 (若啟用) 也會保留。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-105">When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained.</span></span> <span data-ttu-id="b1f1a-106">當您建立保留時，您可以指定保留期間 (也稱為以 *時間為基礎的保留*) ，所以刪除及修改的專案會保留指定期間內，然後從信箱中永久刪除。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-106">When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox.</span></span> <span data-ttu-id="b1f1a-107">或者，您可以只保留未 (稱為 *無限期保留*) 或移除訴訟暫止的內容。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-107">Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed.</span></span> <span data-ttu-id="b1f1a-108">如果您指定保留期間期限，它會從接收郵件或建立信箱專案的日期開始計算。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-108">If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="b1f1a-109">以下是建立訴訟暫止時發生的情況。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-109">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="b1f1a-110">使用者永久刪除的專案會保留在使用者信箱的 [可復原的專案] 資料夾中的保留期間。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-110">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>
    
- <span data-ttu-id="b1f1a-111">從使用者的 [可復原的專案] 資料夾中清除的專案會在保留期間內保留。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-111">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>
    
- <span data-ttu-id="b1f1a-112">[可復原的專案] 資料夾的儲存配額會從 30 GB 增加為 110 GB。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-112">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>
    
- <span data-ttu-id="b1f1a-113">保留使用者主要和封存信箱中的專案</span><span class="sxs-lookup"><span data-stu-id="b1f1a-113">Items in the user's primary and the archive mailboxes are retained</span></span>
    
## <a name="assign-an-exchange-online-plan-2-license"></a><span data-ttu-id="b1f1a-114">指派 Exchange Online Plan 2 授權</span><span class="sxs-lookup"><span data-stu-id="b1f1a-114">Assign an Exchange Online Plan 2 license</span></span>

- <span data-ttu-id="b1f1a-115">若要將 Exchange Online 信箱設為訴訟暫止狀態，必須將其指派為 Exchange Online Plan 2 授權。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-115">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="b1f1a-116">如果信箱已獲指派 Exchange Online Plan 1 授權，則必須將其指派給其另一個 Exchange Online 封存授權，以便進行暫止。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-116">If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    

## <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="b1f1a-117">將信箱設為訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="b1f1a-117">Place a mailbox on Litigation Hold</span></span>

<span data-ttu-id="b1f1a-118">以下是使用 Exchange 系統管理中心，將信箱設為訴訟暫止狀態的步驟。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-118">Here are the steps to place a mailbox on Litigation Hold using the Exchange admin center.</span></span>

1. <span data-ttu-id="b1f1a-119">移至 [https://outlook.office.com/ecp](https://outlook.office.com/ecp) 並使用全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-119">Go to [https://outlook.office.com/ecp](https://outlook.office.com/ecp) and sign in using your global administrator account.</span></span>

2. <span data-ttu-id="b1f1a-120">按一下左導覽窗格中的 [收件者] **> 信箱** 。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-120">Click **Recipients > Mailboxes** in the left navigation pane.</span></span>

3. <span data-ttu-id="b1f1a-121">選取您要進行訴訟暫止的信箱，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-121">Select the mailbox that you want to place on Litigation Hold, and then click **Edit**.</span></span>

4. <span data-ttu-id="b1f1a-122">在信箱屬性頁面上，按一下 [ **信箱功能**]。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-122">On the mailbox properties page, click **Mailbox features**.</span></span>
    
5. <span data-ttu-id="b1f1a-123">在 [ **訴訟暫止：已停用**] 下，按一下 [ **啟用** ]，將信箱設為訴訟暫止。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-123">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span>
    
6. <span data-ttu-id="b1f1a-124">在 [ **訴訟暫** 止] 頁面上，輸入下列選擇性資訊：</span><span class="sxs-lookup"><span data-stu-id="b1f1a-124">On the **Litigation hold** page, enter the following optional information:</span></span> 
    
    - <span data-ttu-id="b1f1a-125">**訴訟暫止持續時間 (天數)** -使用此方塊可建立以時間為基礎的保留，並指定當信箱處於訴訟暫止狀態時，要保留的信箱專案長度。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-125">**Litigation hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold.</span></span> <span data-ttu-id="b1f1a-126">持續時間自接收或建立信箱項目的日期開始計算。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-126">The duration is calculated from the date a mailbox item is received or created.</span></span> <span data-ttu-id="b1f1a-127">特定專案的保留期間到期時，將不再保留該專案。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-127">When the hold duration expires for a specific item, that item will no longer be preserved.</span></span> <span data-ttu-id="b1f1a-128">如果您將此方塊保留空白，則專案會無限期保留，或直到移除保留為止。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-128">If you leave this box blank, items are preserved indefinitely or until the hold is removed.</span></span> <span data-ttu-id="b1f1a-129">請使用天數為單位來指定持續時間。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-129">Use days to specify the duration.</span></span>
    
    - <span data-ttu-id="b1f1a-130">**附注** -使用此方塊通知使用者其信箱處於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-130">**Note** - Use this box to inform the user their mailbox is on Litigation Hold.</span></span> <span data-ttu-id="b1f1a-131">如果使用者是使用 Outlook 2010 或更新版本，則附注會出現在使用者信箱中的 [帳戶資訊] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-131">The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later.</span></span> <span data-ttu-id="b1f1a-132">若要存取此頁面，使用者可以 **按一下 Outlook 中的 [** 檔案]。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-132">To access this page, users can click **File** in Outlook.</span></span>
    
    - <span data-ttu-id="b1f1a-133">**URL** -使用此方塊可將使用者導向至網站，以取得訴訟暫止的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-133">**URL** - Use this box to direct the user to a website for more information about Litigation Hold.</span></span> <span data-ttu-id="b1f1a-134">如果使用者使用 Outlook 2010 或更新版本，則此 URL 會出現在使用者信箱的 [帳戶資訊] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-134">This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later.</span></span> <span data-ttu-id="b1f1a-135">若要存取此頁面，使用者可以 **按一下 [** Outlook] 中的 [檔案]。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-135">To access this page, users can click **File** in Outlook..</span></span>

7. <span data-ttu-id="b1f1a-136">按一下 [**訴訟暫** 止] 頁面上的 [**儲存**]，然後按一下 [信箱屬性] 頁面上的 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-136">Click **Save** on the **Litigation hold** page, and then click **Save** on the mailbox properties page.</span></span>

### <a name="create-a-litigation-hold-using-powershell"></a><span data-ttu-id="b1f1a-137">使用 PowerShell 建立訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="b1f1a-137">Create a Litigation Hold using PowerShell</span></span>

<span data-ttu-id="b1f1a-138">您也可以在 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中執行下列命令，以建立訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-138">You can also create a Litigation Hold by running the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

<span data-ttu-id="b1f1a-139">上一個命令會無限期保留專案，因為未指定保留期間。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-139">The previous command preserves items indefinitely because the hold duration isn't specified.</span></span> <span data-ttu-id="b1f1a-140">若要建立以時間為基礎的保留，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="b1f1a-140">To created a time-based hold, using the following command:</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

<span data-ttu-id="b1f1a-141">如需詳細資訊，請參閱 [Set-Mailbox](/powershell/module/exchange/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-141">For more information, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

## <a name="how-does-litigation-hold-work"></a><span data-ttu-id="b1f1a-142">訴訟暫止如何運作？</span><span class="sxs-lookup"><span data-stu-id="b1f1a-142">How does Litigation Hold work?</span></span>

<span data-ttu-id="b1f1a-143">在正常刪除項目工作流程中，當使用者永久刪除 (Shift+Delete) 或從 [刪除的項目] 資料夾中刪除項目時，信箱項目會移至 [可復原的項目] 資料夾中的 [刪除] 子資料夾。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-143">In the normal deleted item workflow, a mailbox item is moved to the Deletions subfolder in the Recoverable Items folder when a user permanently deletes it (Shift + Delete) or deletes it from the Deleted Items folder.</span></span> <span data-ttu-id="b1f1a-144">當保留期間到期時，刪除原則 (也就是以刪除保留動作設定的保留標記) 也會將項目移至 [刪除] 子資料夾。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-144">A deletion policy (which is a retention tag configured with a Delete retention action) also moves items to the Deletions subfolder when the retention period expires.</span></span> <span data-ttu-id="b1f1a-145">當使用者清除 [可復原的項目] 資料夾中的項目，或已刪除項目的保留期間到期時，項目會移至 [可復原的項目] 資料夾中的 [清除] 子資料夾並標示為永久刪除。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-145">When a user purges an item in the Recoverable Items folder or when the deleted item retention period expires for an item, it's moved to the Purges subfolder in the Recoverable Items folder and marked for permanent deletion.</span></span> <span data-ttu-id="b1f1a-146">系統會在下一次受管理的資料夾助理員 (MFA) 處理信箱時，從 Exchange 清除項目。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-146">It will be purged from Exchange the next time the mailbox is processed by the Managed Folder Assistant (MFA).</span></span>

<span data-ttu-id="b1f1a-p108">當信箱處於訴訟暫止狀態時，[清除] 子資料夾中的項目會依訴訟暫止所指定的保留期間予以保留。保留期間是由接收或建立項目的原始日期開始計算，並定義 [清除] 子資料夾中的項目會保留多久。[清除] 子資料夾中的項目保留期間到期時，項目將標示為永久刪除，並在下一次 MFA 處理信箱時，從 Exchange清除。若信箱設為無限期保留，項目將不會從 [清除] 子資料夾中清除。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-p108">When a mailbox is placed on Litigation Hold, items in the Purges subfolder are preserved for the hold duration specified by the Litigation Hold. The hold duration is calculated from the original date an item was received or created, and defines how long items in the Purges subfolder are held. When the hold duration expires for an item in the Purges subfolder, the item is marked for permanent deletion and will be purged from Exchange the next time the mailbox is processed by the MFA. If an indefinite hold is placed on a mailbox, items will never be purged from the Purges subfolder.</span></span>

<span data-ttu-id="b1f1a-151">下圖顯示在 [可復原的項目] 資料夾中的子資料夾以及並保留工作流程程序。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-151">The following illustration shows the subfolders in the Recoverable Items folders and the hold workflow process.</span></span>

![訴訟暫止週期](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> <span data-ttu-id="b1f1a-153">如果與 eDiscovery 案例相關聯的封存是放在信箱上，已清除的專案會從 [刪除] 子資料夾移至 DiscoveryHolds 子資料夾，而且會保留，直到信箱從 eDiscovery 保留中釋放為止。</span><span class="sxs-lookup"><span data-stu-id="b1f1a-153">If a hold associated with an eDiscovery case is placed on a mailbox, purged items are moved from the Deletions subfolder to the DiscoveryHolds subfolder and are preserved until the mailbox is released from the eDiscovery hold.</span></span>
