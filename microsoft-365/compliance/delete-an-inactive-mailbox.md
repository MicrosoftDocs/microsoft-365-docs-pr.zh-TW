---
title: 在 Office 365 中刪除非作用中的信箱
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: 當您不再需要保留 Office 365 非使用中信箱的內容時，您可以移除 [保留]，以永久刪除非使用中的信箱。 移除保留後，非作用中的信箱會標示為待刪除，並且會在處理完後永久刪除。
ms.openlocfilehash: 69628a0e3c39a0a842b2efa58c34b75c7663c728
ms.sourcegitcommit: 7646e2d742d1b2fad085a00200a2a10461dd4bac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978253"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="88d22-104">在 Office 365 中刪除非作用中的信箱</span><span class="sxs-lookup"><span data-stu-id="88d22-104">Delete an inactive mailbox in Office 365</span></span>

<span data-ttu-id="88d22-105">在前任員工離開您的組織之後，可透過非使用中信箱來保留其電子郵件。</span><span class="sxs-lookup"><span data-stu-id="88d22-105">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="88d22-106">當您不再需要保留非使用中信箱的內容時，您可以移除 [保留]，以永久刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-106">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="88d22-107">此外，可能會在非使用中的信箱上放置多個保留。</span><span class="sxs-lookup"><span data-stu-id="88d22-107">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="88d22-108">例如，非使用中的信箱可能處於訴訟暫止狀態，且有一或多個 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="88d22-108">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="88d22-109">此外，Office 365 保留原則（在 Office 365 或 Microsoft 365 中的安全性與合規性中心建立）可能會套用到非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-109">Additionally, an Office 365 retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="88d22-110">您必須移除非使用中信箱的所有保留和 Office 365 保留原則，才能加以刪除。</span><span class="sxs-lookup"><span data-stu-id="88d22-110">You have to remove all holds and Office 365 retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="88d22-111">移除保留和保留原則之後，非作用中的信箱會標示為待刪除，並且會在處理完後永久刪除。</span><span class="sxs-lookup"><span data-stu-id="88d22-111">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="88d22-112">當我們繼續以保留信箱內容的不同方式投資時，我們宣佈在 Exchange 系統管理中心中封存 In-Place 的退休。</span><span class="sxs-lookup"><span data-stu-id="88d22-112">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="88d22-113">這表示您應該使用訴訟保留和 Office 365 保留原則來建立非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-113">That means you should use Litigation Holds and Office 365 retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="88d22-114">從2020年7月1日起，您將無法在 Exchange Online 中建立新的 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="88d22-114">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="88d22-115">不過，您仍然可以變更置於非使用中信箱的 In-Place 保留期間。</span><span class="sxs-lookup"><span data-stu-id="88d22-115">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="88d22-116">不過，從2020年10月1日開始，您將無法變更保留期間。</span><span class="sxs-lookup"><span data-stu-id="88d22-116">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="88d22-117">您只能移除 In-Place 保留才能刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-117">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="88d22-118">在移除保留之前，仍會保留位於 In-Place 暫止的現有非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-118">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="88d22-119">如需停用 In-Place 保留的詳細資訊，請參閱[舊版 eDiscovery tools 的退休](legacy-ediscovery-retirement.md)。</span><span class="sxs-lookup"><span data-stu-id="88d22-119">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="88d22-120">請參閱[詳細資訊](#more-information)一節，以取得從非使用中的信箱移除保留專案之後所發生狀況的描述。</span><span class="sxs-lookup"><span data-stu-id="88d22-120">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="88d22-121">開始之前</span><span class="sxs-lookup"><span data-stu-id="88d22-121">Before you begin</span></span>

- <span data-ttu-id="88d22-122">您必須使用 Exchange Online PowerShell 移除非使用中信箱的訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="88d22-122">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="88d22-123">您無法使用 Exchange 系統管理中心（EAC）。</span><span class="sxs-lookup"><span data-stu-id="88d22-123">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="88d22-124">如需逐步指示，請參閱[Connect To Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="88d22-124">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="88d22-125">您可以使用 Exchange Online PowerShell 或 EAC 從非使用中的信箱移除 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="88d22-125">You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="88d22-126">您可以將非使用中信箱的內容複寫到另一個信箱，然後再移除保留和刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-126">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="88d22-127">如需詳細資訊，請參閱[Restore a 非使用中的信箱在 Office 365](restore-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="88d22-127">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="88d22-128">如果您移除非使用中信箱的保留原則或 Office 365 保留原則，且該信箱的虛刪除信箱保留期間已過期，則會永久刪除該信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-128">If you remove the hold or Office 365 retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="88d22-129">刪除後，便無法復原。</span><span class="sxs-lookup"><span data-stu-id="88d22-129">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="88d22-130">在您移除保留之前，請確定您不再需要信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="88d22-130">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="88d22-131">如果您想要重新啟用非使用中的信箱，可以進行復原。</span><span class="sxs-lookup"><span data-stu-id="88d22-131">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="88d22-132">如需詳細資訊，請參閱[復原 Office 365 中的非使用中信箱](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="88d22-132">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="88d22-133">如需非使用中信箱的相關資訊，請參閱[Office 365 中的非使用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="88d22-133">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="88d22-134">步驟1：識別非使用中信箱上的封存</span><span class="sxs-lookup"><span data-stu-id="88d22-134">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="88d22-135">如先前所述，訴訟暫止、In-Place 保留或 Office 365 保留原則可能會放在非使用中的信箱上。</span><span class="sxs-lookup"><span data-stu-id="88d22-135">As previously stated, a Litigation Hold, In-Place Hold, or Office 365 retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="88d22-136">第一步是在非使用中的信箱上識別保留。</span><span class="sxs-lookup"><span data-stu-id="88d22-136">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="88d22-137">執行下列命令，以顯示組織中所有非使用中信箱的保留資訊。</span><span class="sxs-lookup"><span data-stu-id="88d22-137">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="88d22-138">**True**的**LitigationHoldEnabled**屬性值表示非使用中的信箱處於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="88d22-138">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="88d22-139">如果將 In-Place 定格放在非使用中的信箱上，則保留的 GUID 會顯示為**InPlaceHolds**屬性的值。</span><span class="sxs-lookup"><span data-stu-id="88d22-139">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="88d22-140">例如，下列兩個非使用中信箱的結果會顯示對王 Beebe 進行訴訟暫止，並將兩個 In-Place 保留置於 Pilar Pinilla。</span><span class="sxs-lookup"><span data-stu-id="88d22-140">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="88d22-141">如果有大量的 In-Place 保留在非使用中的信箱上，則不會顯示所有 In-Place 保留 Guid。</span><span class="sxs-lookup"><span data-stu-id="88d22-141">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="88d22-142">您可以執行下列命令來顯示所有 In-Place 保留的 Guid：`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="88d22-142">You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="88d22-143">步驟2：移除非使用中信箱的保留</span><span class="sxs-lookup"><span data-stu-id="88d22-143">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="88d22-144">在您識別在非使用中的信箱上放置的保留類型（以及是否有多個保留）之後，下一步是移除信箱上的保留。</span><span class="sxs-lookup"><span data-stu-id="88d22-144">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span></span> <span data-ttu-id="88d22-145">如先前所述，您必須移除所有保留以永久刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-145">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="88d22-146">移除訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="88d22-146">Remove a Litigation Hold</span></span>

<span data-ttu-id="88d22-147">如先前所述，您必須使用 Windows PowerShell 移除非使用中信箱的訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="88d22-147">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="88d22-148">您無法使用 EAC。</span><span class="sxs-lookup"><span data-stu-id="88d22-148">You can't use the EAC.</span></span> <span data-ttu-id="88d22-149">執行下列命令，以移除訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="88d22-149">Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="88d22-150">識別非使用中信箱的最佳方式是使用其辨別名稱或 Exchange GUID 值。</span><span class="sxs-lookup"><span data-stu-id="88d22-150">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="88d22-151">使用其中一個值可協助避免意外指定錯誤的信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-151">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="88d22-152">移除 In-Place 保留</span><span class="sxs-lookup"><span data-stu-id="88d22-152">Remove In-Place Holds</span></span>

 <span data-ttu-id="88d22-153">有兩種方式可以移除非使用中信箱的 In-Place 保留：</span><span class="sxs-lookup"><span data-stu-id="88d22-153">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="88d22-154">**刪除 In-Place 保留物件**如果您想要永久刪除的非作用中信箱是唯一的 In-Place 保留來源信箱，您只需刪除 In-Place 保留物件即可。</span><span class="sxs-lookup"><span data-stu-id="88d22-154">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="88d22-155">您必須先停用保留，才能刪除 In-Place 保留物件。</span><span class="sxs-lookup"><span data-stu-id="88d22-155">You have to disable the hold before you can delete an In-Place Hold object.</span></span> <span data-ttu-id="88d22-156">如果您嘗試刪除已啟用保留的 In-Place 保留物件，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="88d22-156">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="88d22-157">**移除非使用中的信箱做為 In-Place 保留的來源信箱**如果您想要保留其他來源信箱以供 In-Place 保留，您可以從來源信箱清單中移除非使用中的信箱，並保留 In-Place 保留物件。</span><span class="sxs-lookup"><span data-stu-id="88d22-157">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="88d22-158">使用 EAC 來刪除 In-Place 暫止</span><span class="sxs-lookup"><span data-stu-id="88d22-158">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="88d22-159">如果您知道要刪除的 In-Place 保留名稱，您可以移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="88d22-159">If you know the name of the In-Place Hold that you want to delete, you can go to the next step.</span></span> <span data-ttu-id="88d22-160">否則，請執行下列命令，以取得放在您要永久刪除之非使用中信箱上的 In-Place 保留名稱。</span><span class="sxs-lookup"><span data-stu-id="88d22-160">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete.</span></span> <span data-ttu-id="88d22-161">使用您在步驟1中取得的 In-Place 保留 GUID [：識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="88d22-161">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="88d22-162">在 EAC 中，移至 [**規範管理** \> **] &amp; In-Place eDiscovery 保留**]。</span><span class="sxs-lookup"><span data-stu-id="88d22-162">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="88d22-163">選取您要刪除的 In-Place 保留，然後按一下 [**編輯** ![編輯圖示](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)]。</span><span class="sxs-lookup"><span data-stu-id="88d22-163">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="88d22-164">在 [ **In-Place eDiscovery &amp;暫**止屬性] 頁面上，按一下 [ **In-Place 保留**]，取消選取 [**將符合搜尋查詢的內容放入保留的所選信箱**] 方塊，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="88d22-164">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="88d22-165">在 [ **In-Place eDiscovery &amp;保留**] 頁面上，再次選取 In-Place [保留]，然後按一下 [](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)**刪除**![刪除圖示]。</span><span class="sxs-lookup"><span data-stu-id="88d22-165">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="88d22-166">在警告中，按一下 **[是]** 以刪除 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="88d22-166">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="88d22-167">使用 Exchange Online PowerShell 刪除 In-Place 保留</span><span class="sxs-lookup"><span data-stu-id="88d22-167">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="88d22-168">建立包含您要刪除之 In-Place 保留之屬性的變數。</span><span class="sxs-lookup"><span data-stu-id="88d22-168">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span></span> <span data-ttu-id="88d22-169">使用您在步驟1中取得的 In-Place 保留 GUID [：識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="88d22-169">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="88d22-170">停用 In-Place 暫止的保留。</span><span class="sxs-lookup"><span data-stu-id="88d22-170">Disable the hold on the In-Place Hold.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="88d22-171">刪除 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="88d22-171">Delete the In-Place Hold.</span></span>
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="88d22-172">使用 EAC 從 In-Place 保留中移除非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="88d22-172">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="88d22-173">如果您知道放在非使用中信箱上的 In-Place 保留名稱，您可以移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="88d22-173">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step.</span></span> <span data-ttu-id="88d22-174">否則，請執行下列命令，以取得信箱上所放置的 In-Place 暫止名稱。</span><span class="sxs-lookup"><span data-stu-id="88d22-174">Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox.</span></span> <span data-ttu-id="88d22-175">使用您在步驟1中取得的 In-Place 保留 GUID [：識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="88d22-175">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="88d22-176">在 EAC 中，移至 [**規範管理** \> **] &amp; In-Place eDiscovery 保留**]。</span><span class="sxs-lookup"><span data-stu-id="88d22-176">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="88d22-177">選取非使用中信箱上的 In-Place 保留，然後按一下 [**編輯** ![編輯圖示](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)]。</span><span class="sxs-lookup"><span data-stu-id="88d22-177">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="88d22-178">在 [ **In-Place eDiscovery &amp;暫**止屬性] 頁面上，按一下 [**來源**]。</span><span class="sxs-lookup"><span data-stu-id="88d22-178">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="88d22-179">在來源信箱清單中，按一下您要移除之非使用中信箱的名稱，然後按一下 [**移除**![移除圖示](../media/adf01106-cc79-475c-8673-065371c1897b.gif)]。</span><span class="sxs-lookup"><span data-stu-id="88d22-179">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](../media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="88d22-180">按一下 [**儲存**] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="88d22-180">Click **Save** to save the change.</span></span> <span data-ttu-id="88d22-181">隨即顯示一則訊息，指出作業已成功完成。</span><span class="sxs-lookup"><span data-stu-id="88d22-181">A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="88d22-182">重複步驟1到6，以移除非使用中信箱上的其他 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="88d22-182">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="88d22-183">使用 Exchange Online PowerShell 從 In-Place 保留中移除非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="88d22-183">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="88d22-184">如果 In-Place 保留包含大量的來源信箱，則可能是非使用中的信箱不會列在 EAC 的 [**來源**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="88d22-184">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="88d22-185">當您編輯 In-Place 保留時，[**來源**] 頁面上最多可顯示3000個信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-185">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="88d22-186">如果「**來源**」頁面沒有列出非使用中的信箱，您可以使用 Exchange Online PowerShell 將其從 In-Place 保留中移除。</span><span class="sxs-lookup"><span data-stu-id="88d22-186">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="88d22-187">建立包含非使用中信箱上的 In-Place 保留屬性的變數。</span><span class="sxs-lookup"><span data-stu-id="88d22-187">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span></span> <span data-ttu-id="88d22-188">使用您在步驟1中取得的 In-Place 保留 GUID [：識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="88d22-188">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="88d22-189">確認非使用中的信箱已列為 In-Place 保留的來源信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-189">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   <span data-ttu-id="88d22-190">**附注：** In-Place 保留的 source 屬性會依其*LegacyExchangeDN*屬性*識別來源信箱*。</span><span class="sxs-lookup"><span data-stu-id="88d22-190">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="88d22-191">由於此屬性唯一識別非使用中的信箱，因此使用 In-Place 保留中的*來源*屬性可協助避免移除錯誤的信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-191">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="88d22-192">如果兩個信箱具有相同的別名或 SMTP 位址，也有助於避免發生問題。</span><span class="sxs-lookup"><span data-stu-id="88d22-192">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="88d22-193">從變數中的來源信箱清單中移除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-193">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="88d22-194">請務必使用上一個步驟中命令所傳回的非使用中信箱的**LegacyExchangeDN** 。</span><span class="sxs-lookup"><span data-stu-id="88d22-194">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="88d22-195">例如，下列命令會移除 Pilar Pinilla 的非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-195">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="88d22-196">確認非使用中信箱已從變數中的來源信箱清單中移除。</span><span class="sxs-lookup"><span data-stu-id="88d22-196">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="88d22-197">使用更新的來源信箱清單（不含非使用中的信箱）修改 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="88d22-197">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="88d22-198">確認已從 In-Place 保留的來源信箱清單中移除非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-198">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="88d22-199">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="88d22-199">More information</span></span>

- <span data-ttu-id="88d22-200">**非使用中的信箱是虛刪除信箱的類型。**</span><span class="sxs-lookup"><span data-stu-id="88d22-200">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="88d22-201">在 Exchange Online 中，虛刪除的信箱是已刪除但可在特定保留期間內復原的信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-201">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="88d22-202">Exchange Online 中的虛刪除信箱保留期間是30天。</span><span class="sxs-lookup"><span data-stu-id="88d22-202">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="88d22-203">這表示信箱可在虛刪除的30天內復原。</span><span class="sxs-lookup"><span data-stu-id="88d22-203">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span></span> <span data-ttu-id="88d22-204">30天后，虛刪除的信箱會標示為永久刪除，且無法復原。</span><span class="sxs-lookup"><span data-stu-id="88d22-204">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="88d22-205">**移除非使用中信箱的保留後，會發生什麼情況？**</span><span class="sxs-lookup"><span data-stu-id="88d22-205">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="88d22-206">信箱會被視為其他虛刪除的信箱，並在30天的虛刪除信箱保留期間到期後標示為永久刪除。</span><span class="sxs-lookup"><span data-stu-id="88d22-206">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="88d22-207">此保留期間會在信箱最初變為非使用中的日期開始。</span><span class="sxs-lookup"><span data-stu-id="88d22-207">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="88d22-208">此日期稱為虛刪除日期，也就是在刪除對應的 Office 365 使用者帳戶，或是使用**Remove-Mailbox** Cmdlet 刪除 Exchange Online 信箱時的日期。</span><span class="sxs-lookup"><span data-stu-id="88d22-208">This date is known as the soft-deleted date, which is the date the corresponding Office 365 user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="88d22-209">[虛刪除] 日期不是移除保留的日期。</span><span class="sxs-lookup"><span data-stu-id="88d22-209">The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="88d22-210">**移除保留後，是否會永久刪除非作用中的信箱？**</span><span class="sxs-lookup"><span data-stu-id="88d22-210">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="88d22-211">如果非使用中信箱的虛刪除日期超過30天，則在您移除保留後，就不會永久刪除該信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-211">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span></span> <span data-ttu-id="88d22-212">信箱將會標示為永久刪除，而且會在下一次處理時刪除。</span><span class="sxs-lookup"><span data-stu-id="88d22-212">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="88d22-213">**虛刪除信箱保留期間對非使用中信箱的影響如何？**</span><span class="sxs-lookup"><span data-stu-id="88d22-213">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="88d22-214">如果非使用中信箱的虛刪除日期超過超過30天，則在刪除保留的日期之前，會將信箱標記為永久刪除。</span><span class="sxs-lookup"><span data-stu-id="88d22-214">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="88d22-215">不過，如果非使用中的信箱在過去30天內有虛刪除的日期，而且您移除保留，您可以將信箱復原，直到虛刪除的信箱保留期間到期為止。</span><span class="sxs-lookup"><span data-stu-id="88d22-215">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="88d22-216">如需詳細資訊，請參閱[刪除或還原 Exchange Online 中的使用者信箱](https://go.microsoft.com/fwlink/?linkid=856835)。</span><span class="sxs-lookup"><span data-stu-id="88d22-216">For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span></span> <span data-ttu-id="88d22-217">當虛刪除的信箱保留期間到期後，您必須遵循復原非使用中信箱的程式。</span><span class="sxs-lookup"><span data-stu-id="88d22-217">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="88d22-218">如需詳細資訊，請參閱[復原 Office 365 中的非使用中信箱](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="88d22-218">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="88d22-219">**移除保留後，如何顯示非使用中信箱的相關資訊？**</span><span class="sxs-lookup"><span data-stu-id="88d22-219">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="88d22-220">在移除保留，且非作用中的信箱回復回虛刪除信箱之後，就不會使用*InactiveMailboxOnly*參數搭配**Get-Mailbox** Cmdlet 來傳回。</span><span class="sxs-lookup"><span data-stu-id="88d22-220">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="88d22-221">不過，您可以使用**Get-Mailbox-SoftDeletedMailbox**命令來顯示信箱的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="88d22-221">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="88d22-222">例如：</span><span class="sxs-lookup"><span data-stu-id="88d22-222">For example:</span></span> 
    
  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
  ```

  <span data-ttu-id="88d22-223">在上述範例中， *WhenSoftDeleted*屬性會識別虛刪除的日期，在此範例中為2014年10月30日。</span><span class="sxs-lookup"><span data-stu-id="88d22-223">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="88d22-224">如果此虛刪除信箱先前為已移除保留的非使用中信箱，則會在*WhenSoftDeleted*屬性值後的30天內永久刪除該信箱。</span><span class="sxs-lookup"><span data-stu-id="88d22-224">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="88d22-225">在此情況下，信箱會在2014年11月30日之後永久刪除。</span><span class="sxs-lookup"><span data-stu-id="88d22-225">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

