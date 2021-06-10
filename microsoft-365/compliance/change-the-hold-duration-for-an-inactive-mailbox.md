---
title: 變更非作用中信箱的保留持續時間
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
ms.custom:
- seo-marvel-apr2020
description: Office 365 信箱變為非使用中之後，請變更保留期間或指派給非使用中信箱之 Office 365 保留原則的持續時間。
ms.openlocfilehash: 49d133c64763cee12cb26e27d372a16ba4ad7e94
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918199"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="b7d83-103">變更非作用中信箱的保留持續時間</span><span class="sxs-lookup"><span data-stu-id="b7d83-103">Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="b7d83-104">非使用中的信箱會在使用者離開組織之後，用來保留離職員工的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b7d83-104">An inactive mailbox is used to retain a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="b7d83-105">當訴訟暫止、In-Place 暫止、Microsoft 365 保留原則，或與 eDiscovery 案例相關聯的保留原則或已刪除的使用者帳戶已刪除時，信箱會變成非使用中。</span><span class="sxs-lookup"><span data-stu-id="b7d83-105">A mailbox becomes inactive when a Litigation Hold, an In-Place Hold, a Microsoft 365 retention policy, or a hold that's associated with an eDiscovery case is placed on the mailbox, and the corresponding user account is deleted.</span></span> <span data-ttu-id="b7d83-106">非使用中信箱的內容會保留在信箱停用的保留期間內，直到未使用中的信箱為止。</span><span class="sxs-lookup"><span data-stu-id="b7d83-106">The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive.</span></span> <span data-ttu-id="b7d83-107">保留期間會定義 [可復原的專案] 資料夾中的專案保留的時間。</span><span class="sxs-lookup"><span data-stu-id="b7d83-107">The hold duration defines how long items in the Recoverable Items folder are held.</span></span> <span data-ttu-id="b7d83-108">當 [可復原的專案] 資料夾中某一專案的保留期間到期時，會永久刪除該專案 (清除從非使用中信箱的) 。</span><span class="sxs-lookup"><span data-stu-id="b7d83-108">When the hold duration expires for an item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="b7d83-109">信箱變為非使用中之後，您可以變更保留或 Microsoft 365 指派給非使用中信箱的保留原則的持續時間。</span><span class="sxs-lookup"><span data-stu-id="b7d83-109">After a mailbox is made inactive, you can change the duration of the hold or Microsoft 365 retention policy assigned to the inactive mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b7d83-110">當我們繼續以保留信箱內容的不同方式投資時，我們宣佈 Exchange 系統管理中心的退休 In-Place 封存。</span><span class="sxs-lookup"><span data-stu-id="b7d83-110">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="b7d83-111">這表示您應該使用訴訟保留和 Microsoft 365 保留原則，以建立非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="b7d83-111">That means you should use Litigation Holds and Microsoft 365 retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="b7d83-112">從2020年4月1日起，您將無法在 Exchange Online 中建立新的 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="b7d83-112">Starting April 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="b7d83-113">不過，您仍然可以變更置於非使用中信箱的 In-Place 保留期間。</span><span class="sxs-lookup"><span data-stu-id="b7d83-113">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="b7d83-114">不過，在2020年7月1日開始，您將無法變更保留期間。</span><span class="sxs-lookup"><span data-stu-id="b7d83-114">However, starting July 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="b7d83-115">您只能移除 In-Place 保留才能刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="b7d83-115">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="b7d83-116">在移除保留之前，仍會保留位於 In-Place 暫止的現有非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="b7d83-116">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="b7d83-117">如需停用 In-Place 保留的詳細資訊，請參閱 [舊版 eDiscovery tools 的退休](legacy-ediscovery-retirement.md)。</span><span class="sxs-lookup"><span data-stu-id="b7d83-117">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
## <a name="connect-to-powershell"></a><span data-ttu-id="b7d83-118">連線 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7d83-118">Connect to PowerShell</span></span>

- <span data-ttu-id="b7d83-119">您必須使用 Exchange Online PowerShell 變更非使用中信箱的訴訟暫止保留期間。</span><span class="sxs-lookup"><span data-stu-id="b7d83-119">You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox.</span></span> <span data-ttu-id="b7d83-120">您無法使用 Exchange 系統管理中心 (EAC) 。</span><span class="sxs-lookup"><span data-stu-id="b7d83-120">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="b7d83-121">不過，您可以使用 Exchange Online PowerShell 或 EAC 來變更 In-Place 保留的保留期間。</span><span class="sxs-lookup"><span data-stu-id="b7d83-121">But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold.</span></span> <span data-ttu-id="b7d83-122">您可以使用「安全性與合規性中心」或「安全性 & 合規性中心」 PowerShell 變更 Microsoft 365 保留原則的保留期間。</span><span class="sxs-lookup"><span data-stu-id="b7d83-122">You can use the security and compliance center or the Security & Compliance Center PowerShell to change the hold duration for a Microsoft 365 retention policy.</span></span>
    
- <span data-ttu-id="b7d83-123">若要連接至 Exchange Online PowerShell 或安全性 & 規範中心 PowerShell，請參閱下列其中一個主題：</span><span class="sxs-lookup"><span data-stu-id="b7d83-123">To connect to Exchange Online PowerShell or Security & Compliance Center PowerShell, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="b7d83-124">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7d83-124">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
  - [<span data-ttu-id="b7d83-125">連線到安全性與合規性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7d83-125">Connect to Security & Compliance Center PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell)
    
- <span data-ttu-id="b7d83-126">與 eDiscovery 案例相關聯的保留是無限保留，這表示沒有可以變更的保留期間。</span><span class="sxs-lookup"><span data-stu-id="b7d83-126">Holds associated with eDiscovery cases are infinite holds, which means there's no hold duration that can be changed.</span></span> <span data-ttu-id="b7d83-127">專案會永遠保留，或直到移除保留，並刪除非作用中的信箱為止。</span><span class="sxs-lookup"><span data-stu-id="b7d83-127">Items are held forever or until the hold is removed and the inactive mailbox is deleted.</span></span>
    
- <span data-ttu-id="b7d83-128">如需非使用中信箱的相關資訊，請參閱[Microsoft 365 中的非使用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="b7d83-128">For more information about inactive mailboxes, see [Inactive mailboxes in Microsoft 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="b7d83-129">步驟1：識別非使用中信箱上的封存</span><span class="sxs-lookup"><span data-stu-id="b7d83-129">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="b7d83-130">因為不同類型的保留或一或多個 Microsoft 365 保留原則可能會放在非使用中的信箱上，所以第一步是在非使用中的信箱上識別保留。</span><span class="sxs-lookup"><span data-stu-id="b7d83-130">Because different types of holds or one or more Microsoft 365 retention policies might be placed on an inactive mailbox, the first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="b7d83-131">在 Exchange Online PowerShell 中執行下列命令，以顯示組織中所有非使用中信箱的保留資訊。</span><span class="sxs-lookup"><span data-stu-id="b7d83-131">Run the following command in Exchange Online PowerShell to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

<span data-ttu-id="b7d83-132">**True** 的 **LitigationHoldEnabled** 屬性值表示非使用中的信箱處於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="b7d83-132">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="b7d83-133">如果 In-Place 保留、eDiscovery 保留或 Microsoft 365 保留原則放在非使用中的信箱上，保留原則的 GUID 會顯示為 **InPlaceHolds** 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="b7d83-133">If an In-Place Hold, eDiscovery hold, or Microsoft 365 retention policy is placed on an inactive mailbox, a GUID for the hold or retention policy is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="b7d83-134">例如，下列會顯示五個非作用中信箱的結果。</span><span class="sxs-lookup"><span data-stu-id="b7d83-134">For example, the following shows results for five inactive mailboxes.</span></span> 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```

<span data-ttu-id="b7d83-135">下表識別用來使每個信箱非使用中的五種不同保留類型。</span><span class="sxs-lookup"><span data-stu-id="b7d83-135">The following table identifies the five different hold types that were used to make each mailbox inactive.</span></span>
  
|<span data-ttu-id="b7d83-136">**非使用中信箱**</span><span class="sxs-lookup"><span data-stu-id="b7d83-136">**Inactive mailbox**</span></span>|<span data-ttu-id="b7d83-137">**保留類型**</span><span class="sxs-lookup"><span data-stu-id="b7d83-137">**Hold type**</span></span>|<span data-ttu-id="b7d83-138">**如何在非使用中的信箱上識別保留**</span><span class="sxs-lookup"><span data-stu-id="b7d83-138">**How to identify the hold on the inactive mailbox**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b7d83-139">王小姐 Beebe</span><span class="sxs-lookup"><span data-stu-id="b7d83-139">Ann Beebe</span></span>  <br/> |<span data-ttu-id="b7d83-140">訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="b7d83-140">Litigation Hold</span></span>  <br/> |<span data-ttu-id="b7d83-141">*LitigationHoldEnabled* 屬性設定為 `True` 。</span><span class="sxs-lookup"><span data-stu-id="b7d83-141">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="b7d83-142">Pilar Pinilla</span><span class="sxs-lookup"><span data-stu-id="b7d83-142">Pilar Pinilla</span></span>  <br/> |<span data-ttu-id="b7d83-143">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="b7d83-143">In-Place Hold</span></span>  <br/> |<span data-ttu-id="b7d83-144">*InPlaceHolds* 屬性包含放在非使用中信箱上的 In-Place 保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="b7d83-144">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the inactive mailbox.</span></span> <span data-ttu-id="b7d83-145">您可以告知這是 In-Place 保留，因為識別碼不是以前置詞開頭。</span><span class="sxs-lookup"><span data-stu-id="b7d83-145">You can tell this is an In-Place Hold because the ID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="b7d83-146">您可以使用 `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` Exchange Online PowerShell 中的命令，取得非使用中信箱上 In-Place 保留的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b7d83-146">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the inactive mailbox.</span></span>  <br/> |
|<span data-ttu-id="b7d83-147">Mario Necaise</span><span class="sxs-lookup"><span data-stu-id="b7d83-147">Mario Necaise</span></span>  <br/> |<span data-ttu-id="b7d83-148">安全性 & 規範中心內的全組織 Microsoft 365 保留原則</span><span class="sxs-lookup"><span data-stu-id="b7d83-148">Organization-wide Microsoft 365 retention policy in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="b7d83-149">*InPlaceHolds* 屬性是空的。</span><span class="sxs-lookup"><span data-stu-id="b7d83-149">The  *InPlaceHolds*  property is empty.</span></span> <span data-ttu-id="b7d83-150">這表示一或多個組織範圍或 (Exchange 寬) Microsoft 365 保留原則會套用至非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="b7d83-150">This indicates that one or more organization-wide or (Exchange-wide) Microsoft 365 retention policy is applied to the inactive mailbox.</span></span> <span data-ttu-id="b7d83-151">在此情況下，您可以 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 在 Exchange Online PowerShell 中執行命令，以取得整個組織 Microsoft 365 保留原則的 guid 清單。</span><span class="sxs-lookup"><span data-stu-id="b7d83-151">In this case, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Microsoft 365 retention policies.</span></span> <span data-ttu-id="b7d83-152">套用至 Exchange 信箱的組織範圍保留原則的 GUID 會以前置詞開始 `mbx` ; 例如， `mbxa3056bb15562480fadb46ce523ff7b02` 。</span><span class="sxs-lookup"><span data-stu-id="b7d83-152">The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example,  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <br/><span data-ttu-id="b7d83-153">若要識別套用至非使用中信箱的 Microsoft 365 保留原則，請在安全性 & 規範中心 PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="b7d83-153">To identity the Microsoft 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span>  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|<span data-ttu-id="b7d83-154">Carol Olson</span><span class="sxs-lookup"><span data-stu-id="b7d83-154">Carol Olson</span></span>  <br/> |<span data-ttu-id="b7d83-155">套用至特定信箱之安全性 & 規範中心的 Microsoft 365 保留原則</span><span class="sxs-lookup"><span data-stu-id="b7d83-155">Microsoft 365 retention policy in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> |<span data-ttu-id="b7d83-156">*InPlaceHolds* 屬性包含套用至非使用中信箱之 Microsoft 365 保留原則的 GUID。</span><span class="sxs-lookup"><span data-stu-id="b7d83-156">The  *InPlaceHolds*  property contains the GUID of the Microsoft 365 retention policy that's applied to the inactive mailbox.</span></span> <span data-ttu-id="b7d83-157">您可以告知這是套用至特定信箱的保留原則，因為 GUID 會以前置詞開頭  `mbx` 。</span><span class="sxs-lookup"><span data-stu-id="b7d83-157">You can tell this is a retention policy that applied to specific mailboxes because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="b7d83-158">如果套用至非使用中信箱的保留原則 GUID 是以前置詞開始 `skp` ，則表示將保留原則套用至商務用 Skype 交談。</span><span class="sxs-lookup"><span data-stu-id="b7d83-158">If the GUID of the retention policy applied to the inactive mailbox started with the  `skp` prefix, it would indicate that the retention policy is applied to Skype for Business conversations.</span></span>  <br/><br/> <span data-ttu-id="b7d83-159">若要識別套用至非使用中信箱的 Microsoft 365 保留原則，請在安全性 & 規範中心 PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="b7d83-159">To identity the Microsoft 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span><br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/><span data-ttu-id="b7d83-160">`mbx` `skp` 當您執行此命令時，請務必移除或首碼。</span><span class="sxs-lookup"><span data-stu-id="b7d83-160">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="b7d83-161">Abraham McMahon</span><span class="sxs-lookup"><span data-stu-id="b7d83-161">Abraham McMahon</span></span>  <br/> |<span data-ttu-id="b7d83-162">安全性 & 規範中心的 eDiscovery 案例保留</span><span class="sxs-lookup"><span data-stu-id="b7d83-162">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="b7d83-163">*InPlaceHolds* 屬性包含放在非使用中信箱上的 eDiscovery 案例保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="b7d83-163">The  *InPlaceHolds*  property contains the GUID of the eDiscovery case hold that's placed on the inactive mailbox.</span></span> <span data-ttu-id="b7d83-164">您可以告訴這是 eDiscovery 案例保留，因為 GUID 是以前置詞開頭  `UniH` 。</span><span class="sxs-lookup"><span data-stu-id="b7d83-164">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="b7d83-165">您可以使用  `Get-CaseHoldPolicy` 安全性 & 規範中心 PowerShell 中的指令程式，取得與非作用中信箱相關聯之 eDiscovery 案例的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b7d83-165">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the inactive mailbox is associated with.</span></span> <span data-ttu-id="b7d83-166">例如，您可以執行命令  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 以顯示非使用中信箱上之案例保留的名稱。</span><span class="sxs-lookup"><span data-stu-id="b7d83-166">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox.</span></span> <span data-ttu-id="b7d83-167">`UniH`當您執行此命令時，請務必移除前置詞。</span><span class="sxs-lookup"><span data-stu-id="b7d83-167">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="b7d83-168">若要識別與非作用中信箱上之保留相關的 eDiscovery 案例，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="b7d83-168">To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.</span></span>  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> <span data-ttu-id="b7d83-169">**附注：** 建議您不要對非使用中的信箱使用 eDiscovery 保留。</span><span class="sxs-lookup"><span data-stu-id="b7d83-169">**Note:** We don't recommend using eDiscovery holds for inactive mailboxes.</span></span> <span data-ttu-id="b7d83-170">That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue.</span><span class="sxs-lookup"><span data-stu-id="b7d83-170">That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue.</span></span> <span data-ttu-id="b7d83-171">在某些情況下，法律案例可能會被移除，與案例相關聯的封存也會被移除，並且 eDiscovery 案例會關閉 (或) 中刪除。</span><span class="sxs-lookup"><span data-stu-id="b7d83-171">At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed (or deleted).</span></span> <span data-ttu-id="b7d83-172">實際上，如果放在非使用中信箱的保留與 eDiscovery 案例相關聯，且已發行保留或 eDiscovery 案例已關閉或已刪除，則系統會永久刪除非作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="b7d83-172">In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and the hold is released or the eDiscovery case is closed or deleted, the inactive mailbox will be permanently deleted.</span></span> 

<span data-ttu-id="b7d83-173">如需 Microsoft 365 保留原則的詳細資訊，請參閱[瞭解保留原則和保留標籤](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="b7d83-173">For more information about Microsoft 365 retention policies, see [Learn about retention policies and retention labels](retention.md).</span></span>
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="b7d83-174">步驟2：變更非使用中信箱的保留期間</span><span class="sxs-lookup"><span data-stu-id="b7d83-174">Step 2: Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="b7d83-175">在您識別在非使用中的信箱上放置何種保留類型之後 (，以及是否有多個保留) 時，下一步是變更保留的持續時間。</span><span class="sxs-lookup"><span data-stu-id="b7d83-175">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to change the duration for the hold.</span></span> 
  
### <a name="change-the-duration-for-a-litigation-hold"></a><span data-ttu-id="b7d83-176">變更訴訟暫止持續時間</span><span class="sxs-lookup"><span data-stu-id="b7d83-176">Change the duration for a Litigation Hold</span></span>

<span data-ttu-id="b7d83-177">以下說明如何使用 Exchange Online PowerShell 變更放在非使用中信箱的訴訟暫止保留期間。</span><span class="sxs-lookup"><span data-stu-id="b7d83-177">Here's how to use Exchange Online PowerShell to change the hold duration for a Litigation Hold that is placed on an inactive mailbox.</span></span> <span data-ttu-id="b7d83-178">您無法使用 EAC。</span><span class="sxs-lookup"><span data-stu-id="b7d83-178">You can't use the EAC.</span></span> <span data-ttu-id="b7d83-179">執行下列命令來變更保留期間。</span><span class="sxs-lookup"><span data-stu-id="b7d83-179">Run the following command to change the hold duration.</span></span> <span data-ttu-id="b7d83-180">在此範例中，保留期間會變更為無限制的時段。</span><span class="sxs-lookup"><span data-stu-id="b7d83-180">In this example, the hold duration is changed to an unlimited period of time.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

<span data-ttu-id="b7d83-181">結果是非使用中信箱中的專案會無限期保留，或直到移除保留或保留期間變更為不同的值。</span><span class="sxs-lookup"><span data-stu-id="b7d83-181">The result is that items in the inactive mailbox are retained indefinitely or until the hold is removed or the hold duration is changed to a different value.</span></span>
  
> [!TIP]
> <span data-ttu-id="b7d83-182">識別非使用中信箱的最佳方式是使用其 **辨別名稱** 或 **Exchange GUID** 值。</span><span class="sxs-lookup"><span data-stu-id="b7d83-182">The best way to identify an inactive mailbox is by using its **Distinguished Name** or **Exchange GUID** value.</span></span> <span data-ttu-id="b7d83-183">使用其中一個值可協助避免意外指定錯誤的信箱。</span><span class="sxs-lookup"><span data-stu-id="b7d83-183">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="change-the-duration-for-an-in-place-hold"></a><span data-ttu-id="b7d83-184">變更 In-Place 保留的持續時間</span><span class="sxs-lookup"><span data-stu-id="b7d83-184">Change the duration for an In-Place Hold</span></span>

 <span data-ttu-id="b7d83-185">已停用 In-Place 保留，而且無法再修改。</span><span class="sxs-lookup"><span data-stu-id="b7d83-185">In-Place Holds have been retired and can no longer be modified.</span></span> <span data-ttu-id="b7d83-186">如果非使用中的信箱已套用 In-Place 保留，您就無法變更保留期間。</span><span class="sxs-lookup"><span data-stu-id="b7d83-186">If an inactive mailbox has an In-Place Hold applied to it, you can't change the hold duration.</span></span> <span data-ttu-id="b7d83-187">您只可以移除 In-Place 保留，這會導致刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="b7d83-187">You can only remove the In-Place Hold, which will result in the deletion of the inactive mailbox.</span></span> <span data-ttu-id="b7d83-188">如需詳細資訊，請參閱 [刪除非使用中的信箱](delete-an-inactive-mailbox.md#remove-in-place-holds)。</span><span class="sxs-lookup"><span data-stu-id="b7d83-188">For more information, see [Delete an inactive mailbox](delete-an-inactive-mailbox.md#remove-in-place-holds).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="b7d83-189">其他資訊</span><span class="sxs-lookup"><span data-stu-id="b7d83-189">More information</span></span>

- <span data-ttu-id="b7d83-190">**如何計算非使用中信箱之專案的保留期間？**</span><span class="sxs-lookup"><span data-stu-id="b7d83-190">**How is the hold duration calculated for an item in an inactive mailbox?**</span></span> <span data-ttu-id="b7d83-191">工期是從接收或建立信箱專案的原始日期開始計算。</span><span class="sxs-lookup"><span data-stu-id="b7d83-191">The duration is calculated from the original date a mailbox item was received or created.</span></span> 
    
- <span data-ttu-id="b7d83-192">**保留期間到期時，會發生什麼情況？**</span><span class="sxs-lookup"><span data-stu-id="b7d83-192">**What happens when the hold duration expires?**</span></span> <span data-ttu-id="b7d83-193">當 [可復原的專案] 資料夾中的信箱專案的保留期間到期時，會永久刪除該專案 (清除從非使用中信箱的) 。</span><span class="sxs-lookup"><span data-stu-id="b7d83-193">When the hold duration expires for a mailbox item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="b7d83-194">若未針對非使用中信箱的保留指定持續時間，則永遠不會 (清除 [可復原的專案] 資料夾中的專案，除非非使用中信箱的保留期間變更) 。</span><span class="sxs-lookup"><span data-stu-id="b7d83-194">If there's no duration specified for the hold placed on the inactive mailbox, items in the Recoverable Items folder are never purged (unless the hold duration for the inactive mailbox is changed).</span></span> 
    
- <span data-ttu-id="b7d83-195">**是否仍在非使用中的信箱上處理 Exchange 保留原則？**</span><span class="sxs-lookup"><span data-stu-id="b7d83-195">**Is an Exchange retention policy still processed on inactive mailboxes?**</span></span> <span data-ttu-id="b7d83-196">如果 Exchange 保留原則 (通訊記錄管理或 MRM，Exchange Online) 中的功能會在信箱停用時套用至信箱，則會繼續在非使用中的信箱上處理使用 [**刪除** 保留] 動作所設定之保留標記的刪除原則 (。</span><span class="sxs-lookup"><span data-stu-id="b7d83-196">If an Exchange retention policy (the messaging records management, or MRM, feature in Exchange Online) was applied to a mailbox when it was made inactive, the deletion policies (which are retention tags configured with a **Delete** retention action) will continue to be processed on the inactive mailbox.</span></span> <span data-ttu-id="b7d83-197">這表示使用刪除原則標記的專案會移至 [可復原的專案] 資料夾，保留期間到期時。</span><span class="sxs-lookup"><span data-stu-id="b7d83-197">That means items that are tagged with a deletion policy are moved to the Recoverable Items folder when the retention period expires.</span></span> <span data-ttu-id="b7d83-198">當專案的保留期間到期時，這些專案便會從非使用中信箱清除。</span><span class="sxs-lookup"><span data-stu-id="b7d83-198">Those items are then purged from the inactive mailbox when the hold duration for an item expires.</span></span> 
    
    <span data-ttu-id="b7d83-199">相反地，任何封存原則 (，其是以指派給非使用中信箱之保留原則中所包含的 **MoveToArchive** 保留動作) 所設定的保留標記會被忽略。</span><span class="sxs-lookup"><span data-stu-id="b7d83-199">Conversely, any archive policies (which are retention tags configured with a **MoveToArchive** retention action) that are included in the retention policy assigned to an inactive mailbox are ignored.</span></span> <span data-ttu-id="b7d83-200">這表示使用封存原則標記的非作用中信箱中的專案會在保留期間到期時保留在主要信箱中。</span><span class="sxs-lookup"><span data-stu-id="b7d83-200">That means items in an inactive mailbox that are tagged with an archive policy remain in the primary mailbox when the retention period expires.</span></span> <span data-ttu-id="b7d83-201">它們不被移至封存信箱或封存信箱中 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="b7d83-201">They're not moved to the archive mailbox or to the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="b7d83-202">由於使用者無法登入非使用中的信箱，因此沒有必要使用資料中心資源來處理封存原則。</span><span class="sxs-lookup"><span data-stu-id="b7d83-202">Because a user can't sign in to an inactive mailbox, there's no reason to consume datacenter resources to process archive policies.</span></span> 

- <span data-ttu-id="b7d83-203">**若要檢查新保留期間的訴訟暫止狀態，請執行下列命令：**</span><span class="sxs-lookup"><span data-stu-id="b7d83-203">**To check the new hold duration for a Litigation Hold, run the following commands**</span></span> 

   ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

- <span data-ttu-id="b7d83-204">**如同一般信箱，受管理的資料夾助理 (MFA) 也會處理非使用中的信箱。**</span><span class="sxs-lookup"><span data-stu-id="b7d83-204">**Like regular mailboxes, the Managed Folder Assistant (MFA) also processes inactive mailboxes.**</span></span> <span data-ttu-id="b7d83-205">在 Exchange Online 中，MFA 大約每7天處理一次信箱。</span><span class="sxs-lookup"><span data-stu-id="b7d83-205">In Exchange Online, the MFA processes mailboxes approximately once every seven days.</span></span> <span data-ttu-id="b7d83-206">在您變更非使用中信箱的保留期間之後，您可以使用 **Start-ManagedFolderAssistant** Cmdlet 立即開始處理非使用中信箱的新保留期間。</span><span class="sxs-lookup"><span data-stu-id="b7d83-206">After you change the hold duration for an inactive mailbox, you can use the **Start-ManagedFolderAssistant** cmdlet to immediately start processing the new hold duration for the inactive mailbox.</span></span> <span data-ttu-id="b7d83-207">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="b7d83-207">Run the following command.</span></span> 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- <span data-ttu-id="b7d83-208">**如果有多個保留放在非使用中的信箱上，則不會顯示所有保留 Guid。**</span><span class="sxs-lookup"><span data-stu-id="b7d83-208">**If many holds are placed on an inactive mailbox, not all of the hold GUIDs will be displayed.**</span></span> <span data-ttu-id="b7d83-209">您可以執行下列命令來顯示所有保留 (的 Guid，但不包括已在非使用中信箱上的訴訟保留) 。</span><span class="sxs-lookup"><span data-stu-id="b7d83-209">You can run the following command to display the GUIDs for all holds (except Litigation Holds) that are placed on an inactive mailbox.</span></span> 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```