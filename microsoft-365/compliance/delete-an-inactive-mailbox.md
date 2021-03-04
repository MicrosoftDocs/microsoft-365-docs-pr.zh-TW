---
title: 刪除非作用中的信箱
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
ms.custom:
- seo-marvel-apr2020
description: 當您不再需要保留 Microsoft 365 非使用中信箱的內容時，您可以永久刪除非使用中的信箱。
ms.openlocfilehash: 0e5a56fce7f41b0c3b30e56aefbaae0593470756
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423210"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="bb99a-103">刪除非作用中的信箱</span><span class="sxs-lookup"><span data-stu-id="bb99a-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="bb99a-104">在前任員工離開您的組織之後，可透過非使用中信箱來保留其電子郵件。</span><span class="sxs-lookup"><span data-stu-id="bb99a-104">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="bb99a-105">當您不再需要保留非使用中信箱的內容時，您可以移除 [保留]，以永久刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="bb99a-106">此外，可能會在非使用中的信箱上放置多個保留。</span><span class="sxs-lookup"><span data-stu-id="bb99a-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="bb99a-107">例如，非使用中的信箱可能處於訴訟暫止狀態，且有一或多個 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="bb99a-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="bb99a-108">此外，Office 365 或 Microsoft 365) 中的安全性與合規性中心中所建立的保留原則 (，都可能會套用到非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="bb99a-109">您必須移除非使用中信箱的所有保留和保留原則，才能加以刪除。</span><span class="sxs-lookup"><span data-stu-id="bb99a-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="bb99a-110">移除保留和保留原則之後，非作用中的信箱會標示為待刪除，並且會在處理完後永久刪除。</span><span class="sxs-lookup"><span data-stu-id="bb99a-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bb99a-111">當我們繼續以保留信箱內容的不同方式投資時，我們宣佈在 Exchange 系統管理中心中封存 In-Place 的退休。</span><span class="sxs-lookup"><span data-stu-id="bb99a-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="bb99a-112">這表示您應該使用訴訟保留和保留原則來建立非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="bb99a-113">從2020年7月1日起，您將無法在 Exchange Online 中建立新的 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="bb99a-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="bb99a-114">不過，您仍然可以變更置於非使用中信箱的 In-Place 保留期間。</span><span class="sxs-lookup"><span data-stu-id="bb99a-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="bb99a-115">不過，從2020年10月1日開始，您將無法變更保留期間。</span><span class="sxs-lookup"><span data-stu-id="bb99a-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="bb99a-116">您只能移除 In-Place 保留才能刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="bb99a-117">在移除保留之前，仍會保留位於 In-Place 暫止的現有非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="bb99a-118">如需停用 In-Place 保留的詳細資訊，請參閱 [舊版 eDiscovery tools 的退休](legacy-ediscovery-retirement.md)。</span><span class="sxs-lookup"><span data-stu-id="bb99a-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="bb99a-119">請參閱 [詳細資訊](#more-information) 一節，以取得從非使用中的信箱移除保留專案之後所發生狀況的描述。</span><span class="sxs-lookup"><span data-stu-id="bb99a-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="bb99a-120">刪除非使用中的信箱之前</span><span class="sxs-lookup"><span data-stu-id="bb99a-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="bb99a-121">您必須使用 Exchange Online PowerShell 移除非使用中信箱的訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="bb99a-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="bb99a-122">您無法使用 Exchange 系統管理中心 (EAC) 。</span><span class="sxs-lookup"><span data-stu-id="bb99a-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="bb99a-123">如需逐步指示，請參閱[連線到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bb99a-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="bb99a-124">您可以將非使用中信箱的內容複寫到另一個信箱，然後再移除保留和刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-124">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="bb99a-125">如需詳細資訊，請參閱 [Restore a 非使用中的信箱在 Office 365](restore-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="bb99a-125">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="bb99a-126">如果您移除非使用中信箱的保留原則或保留原則，且該信箱的虛刪除信箱保留期間已過期，則會永久刪除信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-126">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="bb99a-127">刪除後，便無法復原。</span><span class="sxs-lookup"><span data-stu-id="bb99a-127">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="bb99a-128">在您移除保留之前，請確定您不再需要信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="bb99a-128">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="bb99a-129">如果您想要重新啟用非使用中的信箱，可以進行復原。</span><span class="sxs-lookup"><span data-stu-id="bb99a-129">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="bb99a-130">如需詳細資訊，請參閱 [復原 Office 365 中的非使用中信箱](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="bb99a-130">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="bb99a-131">如需非使用中信箱的相關資訊，請參閱 [Office 365 中的非使用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="bb99a-131">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="bb99a-132">步驟1：識別非使用中信箱上的封存</span><span class="sxs-lookup"><span data-stu-id="bb99a-132">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="bb99a-133">如先前所述，訴訟暫止、In-Place 保留或保留原則可能會放在非使用中的信箱上。</span><span class="sxs-lookup"><span data-stu-id="bb99a-133">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="bb99a-134">第一步是在非使用中的信箱上識別保留。</span><span class="sxs-lookup"><span data-stu-id="bb99a-134">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="bb99a-135">執行下列命令，以顯示組織中所有非使用中信箱的保留資訊。</span><span class="sxs-lookup"><span data-stu-id="bb99a-135">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="bb99a-136">**True** 的 **LitigationHoldEnabled** 屬性值表示非使用中的信箱處於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="bb99a-136">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="bb99a-137">如果將 In-Place 定格放在非使用中的信箱上，則保留的 GUID 會顯示為 **InPlaceHolds** 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="bb99a-137">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="bb99a-138">例如，下列兩個非使用中信箱的結果會顯示對王 Beebe 進行訴訟暫止，以及將 In-Place 保留和保留原則置於 Pilar Pinilla。</span><span class="sxs-lookup"><span data-stu-id="bb99a-138">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that an In-Place Hold and retention policy are placed on Pilar Pinilla.</span></span>
  
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
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="bb99a-139">如果有大量的 In-Place 保留原則或保留原則放在非使用中的信箱，則不會顯示所有 In-Place 保留 Guid。</span><span class="sxs-lookup"><span data-stu-id="bb99a-139">If a lot of In-Place Holds or retention policies are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="bb99a-140">您可以執行下列命令，在 InPlaceHolds 屬性中顯示所有的 Guid：  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="bb99a-140">You can run the following command to display all the GUIDs in the InPlaceHolds property:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
<span data-ttu-id="bb99a-141">如需識別保留的詳細資訊，請參閱 how [to 識別信箱中放置的保留類型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="bb99a-141">For more information about identify holds, see [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="bb99a-142">步驟2：移除非使用中信箱的保留</span><span class="sxs-lookup"><span data-stu-id="bb99a-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="bb99a-143">在您識別在非使用中的信箱上放置何種保留類型之後 (，以及是否有多個保留) 時，下一步是移除信箱上的保留。</span><span class="sxs-lookup"><span data-stu-id="bb99a-143">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span></span> <span data-ttu-id="bb99a-144">如先前所述，您必須移除所有保留以永久刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-144">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span>
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="bb99a-145">移除訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="bb99a-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="bb99a-146">如先前所述，您必須使用 Windows PowerShell 移除非使用中信箱的訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="bb99a-146">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="bb99a-147">您無法使用 EAC。</span><span class="sxs-lookup"><span data-stu-id="bb99a-147">You can't use the EAC.</span></span> <span data-ttu-id="bb99a-148">執行下列命令，以移除訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="bb99a-148">Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="bb99a-149">識別非使用中信箱的最佳方式是使用其辨別名稱或 Exchange GUID 值。</span><span class="sxs-lookup"><span data-stu-id="bb99a-149">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="bb99a-150">使用其中一個值可協助避免意外指定錯誤的信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-150">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a><span data-ttu-id="bb99a-151">從保留原則中移除非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="bb99a-151">Remove an inactive mailbox from a retention policy</span></span>

<span data-ttu-id="bb99a-152">從 Microsoft 365 保留原則中移除非使用中信箱的程式，視指派給非使用中信箱的保留原則為全組織或明確。</span><span class="sxs-lookup"><span data-stu-id="bb99a-152">The procedure to remove an inactive mailbox from a Microsoft 365 retention policy depends whether the retention policy assigned to the inactive mailbox is organization-wide or explicit.</span></span> <span data-ttu-id="bb99a-153">指派給非使用中信箱之保留原則的類型。</span><span class="sxs-lookup"><span data-stu-id="bb99a-153">on the type of retention policy that's assigned to the inactive mailbox.</span></span>

- <span data-ttu-id="bb99a-154">指派給組織中所有信箱的全組織保留原則。</span><span class="sxs-lookup"><span data-stu-id="bb99a-154">Organization-wide retention policies assigned to all mailboxes in the organization.</span></span> <span data-ttu-id="bb99a-155">使用 Exchange Online PowerShell 中的 **Get-OrganizationConfig** Cmdlet，以取得整個組織保留原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="bb99a-155">Use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span>

- <span data-ttu-id="bb99a-156">指派給特定信箱的特定位置保留原則。</span><span class="sxs-lookup"><span data-stu-id="bb99a-156">Specific location retention policies assigned to specific mailboxes.</span></span> <span data-ttu-id="bb99a-157">這些是指派給特定使用者之內容位置的原則。</span><span class="sxs-lookup"><span data-stu-id="bb99a-157">These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="bb99a-158">使用 Exchange Online PowerShell 中的 **Get-Mailbox IncludeInactiveMailbox 指令程式** ，以取得指派給特定非使用中信箱之保留原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="bb99a-158">Use the **Get-Mailbox -IncludeInactiveMailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific inactive mailboxes.</span></span>

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a><span data-ttu-id="bb99a-159">從整個組織的保留原則中移除非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="bb99a-159">Remove an inactive mailbox from an organization-wide retention policy</span></span>

<span data-ttu-id="bb99a-160">在 Exchange Online PowerShell 中執行下列命令，以從整個組織的保留原則中排除非作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-160">Run the following command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide retention policy.</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

<span data-ttu-id="bb99a-161">如需識別套用至非使用中信箱之組織範圍內保留原則的詳細資訊，以及取得保留原則的 GUID，請參閱 [如何識別信箱上的保留類型的](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig)「Get-OrganizationConfig」一節。</span><span class="sxs-lookup"><span data-stu-id="bb99a-161">For more information identifying organization-wide retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-OrganizationConfig" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig).</span></span>

<span data-ttu-id="bb99a-162">或者，您也可以執行下列命令，從所有全組織原則中移除非使用中的信箱：</span><span class="sxs-lookup"><span data-stu-id="bb99a-162">Alternatively, you can run the following command to remove the inactive mailbox from all organization-wide policies:</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a><span data-ttu-id="bb99a-163">從特定位置保留原則中移除非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="bb99a-163">Remove an inactive mailbox from a specific location retention policy</span></span>

<span data-ttu-id="bb99a-164">在 [ [安全性 & 規範 PowerShell 中心](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) ] 中執行下列命令，以從明確保留原則中移除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-164">Run the following command in [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) to remove an inactive mailbox from an explicit retention policy.</span></span>

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

<span data-ttu-id="bb99a-165">如需識別套用至非使用中信箱之特定位置保留原則的詳細資訊，以及取得保留原則的 GUID，請參閱 [如何識別信箱中所放置類型的](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox)「Get-Mailbox」一節。</span><span class="sxs-lookup"><span data-stu-id="bb99a-165">For more information identifying specific location retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-Mailbox" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox).</span></span>

### <a name="remove-in-place-holds"></a><span data-ttu-id="bb99a-166">移除就地保留</span><span class="sxs-lookup"><span data-stu-id="bb99a-166">Remove In-Place Holds</span></span>

 <span data-ttu-id="bb99a-167">有兩種方式可以移除非使用中信箱的 In-Place 保留：</span><span class="sxs-lookup"><span data-stu-id="bb99a-167">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="bb99a-168">**刪除 In-Place 保留物件** 如果您想要永久刪除的非作用中信箱是唯一的 In-Place 保留來源信箱，您只需刪除 In-Place 保留物件即可。</span><span class="sxs-lookup"><span data-stu-id="bb99a-168">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="bb99a-169">您必須先停用保留，才能刪除 In-Place 保留物件。</span><span class="sxs-lookup"><span data-stu-id="bb99a-169">You have to disable the hold before you can delete an In-Place Hold object.</span></span> <span data-ttu-id="bb99a-170">如果您嘗試刪除已啟用保留的 In-Place 保留物件，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="bb99a-170">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="bb99a-171">**移除非使用中的信箱做為 In-Place 保留的來源信箱** 如果您想要保留其他來源信箱以供 In-Place 保留，您可以從來源信箱清單中移除非使用中的信箱，並保留 In-Place 保留物件。</span><span class="sxs-lookup"><span data-stu-id="bb99a-171">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span>

#### <a name="delete-an-in-place-hold"></a><span data-ttu-id="bb99a-172">刪除 In-Place 暫止</span><span class="sxs-lookup"><span data-stu-id="bb99a-172">Delete an In-Place Hold</span></span>

1. <span data-ttu-id="bb99a-173">建立包含您要刪除之 In-Place 保留之屬性的變數。</span><span class="sxs-lookup"><span data-stu-id="bb99a-173">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span></span> <span data-ttu-id="bb99a-174">使用您在步驟1中取得的 In-Place 保留 GUID [：識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="bb99a-174">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="bb99a-175">停用 In-Place 暫止的保留。</span><span class="sxs-lookup"><span data-stu-id="bb99a-175">Disable the hold on the In-Place Hold.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="bb99a-176">刪除 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="bb99a-176">Delete the In-Place Hold.</span></span>

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="bb99a-177">從 In-Place 保留中移除非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="bb99a-177">Remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="bb99a-178">如果 In-Place 保留包含大量的來源信箱，則可能是非使用中的信箱不會列在 EAC 的 [ **來源** ] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="bb99a-178">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="bb99a-179">當您編輯 In-Place 保留時，[ **來源** ] 頁面上最多可顯示3000個信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-179">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="bb99a-180">如果「 **來源** 」頁面沒有列出非使用中的信箱，您可以使用 Exchange Online PowerShell 將其從 In-Place 保留中移除。</span><span class="sxs-lookup"><span data-stu-id="bb99a-180">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="bb99a-181">建立包含非使用中信箱上的 In-Place 保留屬性的變數。</span><span class="sxs-lookup"><span data-stu-id="bb99a-181">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span></span> <span data-ttu-id="bb99a-182">使用您在步驟1中取得的 In-Place 保留 GUID [：識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="bb99a-182">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="bb99a-183">確認非使用中的信箱已列為 In-Place 保留的來源信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-183">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > <span data-ttu-id="bb99a-184">In-Place 保留的 source 屬性會依其 *LegacyExchangeDN* 屬性 *識別來源信箱*。</span><span class="sxs-lookup"><span data-stu-id="bb99a-184">The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="bb99a-185">由於此屬性唯一識別非使用中的信箱，因此使用 In-Place 保留中的 *來源* 屬性可協助避免移除錯誤的信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-185">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="bb99a-186">如果兩個信箱具有相同的別名或 SMTP 位址，也有助於避免發生問題。</span><span class="sxs-lookup"><span data-stu-id="bb99a-186">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 

3. <span data-ttu-id="bb99a-187">從變數中的來源信箱清單中移除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-187">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="bb99a-188">請務必使用上一個步驟中命令所傳回的非使用中信箱的 **LegacyExchangeDN** 。</span><span class="sxs-lookup"><span data-stu-id="bb99a-188">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="bb99a-189">例如，下列命令會移除 Pilar Pinilla 的非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-189">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="bb99a-190">確認非使用中信箱已從變數中的來源信箱清單中移除。</span><span class="sxs-lookup"><span data-stu-id="bb99a-190">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>

   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="bb99a-191">使用更新的來源信箱清單（不含非使用中的信箱）修改 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="bb99a-191">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="bb99a-192">確認已從 In-Place 保留的來源信箱清單中移除非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-192">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="bb99a-193">其他資訊</span><span class="sxs-lookup"><span data-stu-id="bb99a-193">More information</span></span>

- <span data-ttu-id="bb99a-194">**非使用中的信箱是虛刪除信箱的類型。**</span><span class="sxs-lookup"><span data-stu-id="bb99a-194">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="bb99a-195">在 Exchange Online 中，虛刪除的信箱是已刪除但可在特定保留期間內復原的信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-195">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="bb99a-196">Exchange Online 中的虛刪除信箱保留期間是30天。</span><span class="sxs-lookup"><span data-stu-id="bb99a-196">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="bb99a-197">這表示信箱可在虛刪除的30天內復原。</span><span class="sxs-lookup"><span data-stu-id="bb99a-197">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span></span> <span data-ttu-id="bb99a-198">30天后，虛刪除的信箱會標示為永久刪除，且無法復原。</span><span class="sxs-lookup"><span data-stu-id="bb99a-198">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span>

- <span data-ttu-id="bb99a-199">**移除非使用中信箱的保留後，會發生什麼情況？**</span><span class="sxs-lookup"><span data-stu-id="bb99a-199">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="bb99a-200">信箱會被視為其他虛刪除的信箱，並在30天的虛刪除信箱保留期間到期後標示為永久刪除。</span><span class="sxs-lookup"><span data-stu-id="bb99a-200">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="bb99a-201">此保留期間會在信箱最初變為非使用中的日期開始。</span><span class="sxs-lookup"><span data-stu-id="bb99a-201">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="bb99a-202">此日期稱為虛刪除日期，也就是在刪除對應的使用者帳戶，或是使用 **Remove-Mailbox** Cmdlet 刪除 Exchange Online 信箱時的日期。</span><span class="sxs-lookup"><span data-stu-id="bb99a-202">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="bb99a-203">[虛刪除] 日期不是移除保留的日期。</span><span class="sxs-lookup"><span data-stu-id="bb99a-203">The soft-deleted date isn't the date on which you remove the hold.</span></span>

- <span data-ttu-id="bb99a-204">**移除保留後，是否會永久刪除非作用中的信箱？**</span><span class="sxs-lookup"><span data-stu-id="bb99a-204">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="bb99a-205">如果非使用中信箱的虛刪除日期超過30天，則在您移除保留後，就不會永久刪除該信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-205">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span></span> <span data-ttu-id="bb99a-206">信箱將會標示為永久刪除，而且會在下一次處理時刪除。</span><span class="sxs-lookup"><span data-stu-id="bb99a-206">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span>

- <span data-ttu-id="bb99a-207">**虛刪除信箱保留期間對非使用中信箱的影響如何？**</span><span class="sxs-lookup"><span data-stu-id="bb99a-207">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="bb99a-208">如果非使用中信箱的虛刪除日期超過超過30天，則在刪除保留的日期之前，會將信箱標記為永久刪除。</span><span class="sxs-lookup"><span data-stu-id="bb99a-208">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="bb99a-209">不過，如果非使用中的信箱在過去30天內有虛刪除的日期，而且您移除保留，您可以將信箱復原，直到虛刪除的信箱保留期間到期為止。</span><span class="sxs-lookup"><span data-stu-id="bb99a-209">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="bb99a-210">如需詳細資訊，請參閱 [刪除或還原 Exchange Online 中的使用者信箱](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes)。</span><span class="sxs-lookup"><span data-stu-id="bb99a-210">For details, see [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes).</span></span> <span data-ttu-id="bb99a-211">當虛刪除的信箱保留期間到期後，您必須遵循復原非使用中信箱的程式。</span><span class="sxs-lookup"><span data-stu-id="bb99a-211">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="bb99a-212">如需詳細資訊，請參閱 [復原 Office 365 中的非使用中信箱](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="bb99a-212">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="bb99a-213">**移除保留後，如何顯示非使用中信箱的相關資訊？**</span><span class="sxs-lookup"><span data-stu-id="bb99a-213">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="bb99a-214">在移除保留，且非作用中的信箱回復回虛刪除信箱之後，就不會使用  *InactiveMailboxOnly*  參數搭配 **Get-Mailbox** Cmdlet 來傳回。</span><span class="sxs-lookup"><span data-stu-id="bb99a-214">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="bb99a-215">不過，您可以使用 **Get-Mailbox-SoftDeletedMailbox** 命令來顯示信箱的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bb99a-215">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="bb99a-216">例如：</span><span class="sxs-lookup"><span data-stu-id="bb99a-216">For example:</span></span>

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

  <span data-ttu-id="bb99a-217">在上述範例中， *WhenSoftDeleted* 屬性會識別虛刪除的日期，在此範例中為2014年10月30日。</span><span class="sxs-lookup"><span data-stu-id="bb99a-217">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="bb99a-218">如果此虛刪除信箱先前為已移除保留的非使用中信箱，則會在 *WhenSoftDeleted* 屬性值後的30天內永久刪除該信箱。</span><span class="sxs-lookup"><span data-stu-id="bb99a-218">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="bb99a-219">在此情況下，信箱會在2014年11月30日之後永久刪除。</span><span class="sxs-lookup"><span data-stu-id="bb99a-219">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>
