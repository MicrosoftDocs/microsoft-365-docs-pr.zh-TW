---
title: 如何找出位於 Exchange Online 信箱的保留類型
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何識別可放在 Microsoft 365 的 Exchange Online 信箱上的不同保留類型。
ms.openlocfilehash: a76b02f6345421871c759e1b31bf19207b474e2a
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816822"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a><span data-ttu-id="17a28-103">如何找出位於 Exchange Online 信箱的保留類型</span><span class="sxs-lookup"><span data-stu-id="17a28-103">How to identify the type of hold placed on an Exchange Online mailbox</span></span>

<span data-ttu-id="17a28-104">本文說明如何在 Microsoft 365 中識別放在 Exchange Online 信箱上的「保留」。</span><span class="sxs-lookup"><span data-stu-id="17a28-104">This article explains how to identify holds placed on Exchange Online mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="17a28-105">Microsoft 365 提供數種方式，讓您的組織可以防止信箱內容遭到永久刪除。</span><span class="sxs-lookup"><span data-stu-id="17a28-105">Microsoft 365 offers several ways that your organization can prevent mailbox content from being permanently deleted.</span></span> <span data-ttu-id="17a28-106">這可讓您的組織保留內容，以符合合規性法規或法律和其他調查類型。</span><span class="sxs-lookup"><span data-stu-id="17a28-106">This allows your organization to retain content to meet compliance regulations or during legal and other types of investigations.</span></span> <span data-ttu-id="17a28-107">以下是 Office 365 中 (*也稱為「保留」*) 的保留功能清單：</span><span class="sxs-lookup"><span data-stu-id="17a28-107">Here's a list of the retention features (also called *holds*) in Office 365:</span></span>

- <span data-ttu-id="17a28-108">**[訴訟暫](create-a-litigation-hold.md)止：** 適用于 Exchange Online 中使用者信箱的保留。</span><span class="sxs-lookup"><span data-stu-id="17a28-108">**[Litigation Hold](create-a-litigation-hold.md):** Holds that are applied to user mailboxes in Exchange Online.</span></span>

- <span data-ttu-id="17a28-109">\*\* [eDiscovery 保留](create-ediscovery-holds.md)：\*\* 與安全性與合規性中心中的核心 eDiscovery 案例相關聯的保留。</span><span class="sxs-lookup"><span data-stu-id="17a28-109">**[eDiscovery hold](create-ediscovery-holds.md):** Holds that are associated with a Core eDiscovery case in the security and compliance center.</span></span> <span data-ttu-id="17a28-110">eDiscovery 保留可以套用到使用者信箱，以及 Microsoft 365 群組和 Microsoft 小組對應的信箱。</span><span class="sxs-lookup"><span data-stu-id="17a28-110">eDiscovery holds can be applied to user mailboxes and to the corresponding mailbox for Microsoft 365 Groups and Microsoft Teams.</span></span>

- <span data-ttu-id="17a28-111">**[保留 In-Place](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds)：** 在 Exchange Online 中使用 Exchange 系統管理中心的「In-Place eDiscovery & 保留」工具，將套用至使用者信箱的保留。</span><span class="sxs-lookup"><span data-stu-id="17a28-111">**[In-Place Hold](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds):** Holds that are applied to user mailboxes by using the In-Place eDiscovery & Hold tool in the Exchange admin center in Exchange Online.</span></span>

- <span data-ttu-id="17a28-112">\*\* [Microsoft 365 保留原則](retention.md)：\*\* 可以設定為保留 (或保留，然後刪除 Exchange Online 中使用者信箱中的) 內容，以及 Microsoft 365 群組和 Microsoft 團隊對應的信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="17a28-112">**[Microsoft 365 retention policies](retention.md):** Can be configured to retain (or retain and then delete) content in user mailboxes in Exchange Online and in the corresponding mailbox for Microsoft 365 Groups and Microsoft Teams.</span></span> <span data-ttu-id="17a28-113">您也可以建立保留原則，以保留儲存在使用者信箱中的商務用 Skype 交談。</span><span class="sxs-lookup"><span data-stu-id="17a28-113">You can also create a retention policy to retain Skype for Business Conversations, which are stored in user mailboxes.</span></span>

  <span data-ttu-id="17a28-114">有兩種類型的 Microsoft 365 保留原則可指派給信箱。</span><span class="sxs-lookup"><span data-stu-id="17a28-114">There are two types of Microsoft 365 retention policies that can be assigned to mailboxes.</span></span>

    - <span data-ttu-id="17a28-115">**特定位置保留原則：** 這些是指派給特定使用者之內容位置的原則。</span><span class="sxs-lookup"><span data-stu-id="17a28-115">**Specific location retention policies:** These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="17a28-116">您可以在 Exchange Online PowerShell 中使用 **Get-Mailbox** Cmdlet，以取得指派給特定信箱之保留原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="17a28-116">You use the **Get-Mailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific mailboxes.</span></span> <span data-ttu-id="17a28-117">如需此類型保留原則的詳細資訊，請參閱從保留原則檔中 [包含或排除特定包含或排除的原則](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions) 一節。</span><span class="sxs-lookup"><span data-stu-id="17a28-117">For more information about this type of retention policy, see the section [A policy with specific inclusions or exclusions](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions) from the retention policy documentation.</span></span>

    - <span data-ttu-id="17a28-118">**整個組織保留原則：** 這些是指派給組織中所有內容位置的原則。</span><span class="sxs-lookup"><span data-stu-id="17a28-118">**Organization-wide retention policies:** These are policies that are assigned to all content locations in your organization.</span></span> <span data-ttu-id="17a28-119">您可以在 Exchange Online PowerShell 中使用 **Get-OrganizationConfig** Cmdlet，以取得整個組織保留原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="17a28-119">You use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span> <span data-ttu-id="17a28-120">如需此類型保留原則的詳細資訊，請參閱從保留原則檔 [套用至整個位置的原則](create-retention-policies.md#a-policy-that-applies-to-entire-locations) 一節。</span><span class="sxs-lookup"><span data-stu-id="17a28-120">For more information about this type of retention policy, see the section [A policy that applies to entire locations](create-retention-policies.md#a-policy-that-applies-to-entire-locations) from the retention policy documentation.</span></span>

- <span data-ttu-id="17a28-121">**[Microsoft 365 保留標籤](retention.md)：** 如果使用者將 Microsoft 365 保留卷 (標套用至一個設定為保留內容或保留，然後刪除其信箱中 *任何* 資料夾或專案的) 內容，則會在信箱上保留信箱，就像該信箱是放在訴訟暫止狀態或指派給 Microsoft 365 保留原則。</span><span class="sxs-lookup"><span data-stu-id="17a28-121">**[Microsoft 365 retention labels](retention.md):** If a user applies a Microsoft 365 retention label (one that's configured to retain content or retain and then delete content) to *any* folder or item in their mailbox, a hold is placed on the mailbox as if the mailbox was placed on Litigation Hold or assigned to a Microsoft 365 retention policy.</span></span> <span data-ttu-id="17a28-122">如需詳細資訊，請參閱「保留中的信箱」， [因為保留標籤已套用至本文中的資料夾或專案](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) 一節。</span><span class="sxs-lookup"><span data-stu-id="17a28-122">For more information, see the [Identifying mailboxes on hold because a retention label has been applied to a folder or item](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) section in this article.</span></span>

<span data-ttu-id="17a28-123">若要管理暫止的信箱，您可能必須識別放在信箱上的保留類型，這樣才能執行工作，例如變更保留期間、暫時或永久移除保留，或排除來自 Microsoft 365 保留原則的信箱。</span><span class="sxs-lookup"><span data-stu-id="17a28-123">To manage mailboxes on hold, you may have to identify the type of hold that's placed on a mailbox so that you can perform tasks such as changing the hold duration, temporarily or permanently removing the hold, or excluding a mailbox from a Microsoft 365 retention policy.</span></span> <span data-ttu-id="17a28-124">在這些情況下，第一步是識別放在信箱上的保留類型。</span><span class="sxs-lookup"><span data-stu-id="17a28-124">In these cases, the first step is to identify the type of hold placed on the mailbox.</span></span> <span data-ttu-id="17a28-125">而且由於多個保留 (和不同類型的保留) 可以放在單一信箱上，如果您想要移除或變更保留，您必須識別信箱上的所有保留。</span><span class="sxs-lookup"><span data-stu-id="17a28-125">And because multiple holds (and different types of holds) can be placed on a single mailbox, you have to identify all holds placed on a mailbox if you want to remove or change a hold.</span></span>

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a><span data-ttu-id="17a28-126">步驟1：取得放在信箱上之保留的 GUID</span><span class="sxs-lookup"><span data-stu-id="17a28-126">Step 1: Obtain the GUID for holds placed on a mailbox</span></span>

<span data-ttu-id="17a28-127">您可以在 Exchange Online PowerShell 中執行下列兩個 Cmdlet，以取得信箱中所放置之保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="17a28-127">You can run the following two cmdlets in Exchange Online PowerShell to get the GUID of the holds that are placed on a mailbox.</span></span> <span data-ttu-id="17a28-128">在取得 GUID 之後，您可以使用它來識別步驟2中的特定保留。</span><span class="sxs-lookup"><span data-stu-id="17a28-128">After you obtain a GUID, you use it to identify the specific hold in Step 2.</span></span> <span data-ttu-id="17a28-129">GUID 未識別訴訟暫止。</span><span class="sxs-lookup"><span data-stu-id="17a28-129">A Litigation Hold isn't identified by a GUID.</span></span> <span data-ttu-id="17a28-130">已啟用或停用信箱的訴訟資料暫留。</span><span class="sxs-lookup"><span data-stu-id="17a28-130">Litigation Holds are either enabled or disabled for a mailbox.</span></span>

- <span data-ttu-id="17a28-131">**Get-Mailbox：** 您可以使用此 Cmdlet 來判斷是否已啟用信箱的訴訟資料暫留，以及是否要取得 eDiscovery 保留的 Guid、In-Place 保留，以及專門指派給信箱的 Microsoft 365 保留原則。</span><span class="sxs-lookup"><span data-stu-id="17a28-131">**Get-Mailbox:** Use this cmdlet to determine whether Litigation Hold is enabled for a mailbox and to get the GUIDs for eDiscovery holds, In-Place Holds, and Microsoft 365 retention policies that are specifically assigned to a mailbox.</span></span> <span data-ttu-id="17a28-132">此 Cmdlet 的輸出也會指出是否已明確從整個組織的保留原則中排除信箱。</span><span class="sxs-lookup"><span data-stu-id="17a28-132">The output of this cmdlet will also indicate if a mailbox has been explicitly excluded from an organization-wide retention policy.</span></span>

- <span data-ttu-id="17a28-133">**Get-OrganizationConfig：** 使用此 Cmdlet 取得整個組織保留原則的 Guid。</span><span class="sxs-lookup"><span data-stu-id="17a28-133">**Get-OrganizationConfig:** Use this cmdlet to get the GUIDs for organization-wide retention policies.</span></span>

<span data-ttu-id="17a28-134">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="17a28-134">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

### <a name="get-mailbox"></a><span data-ttu-id="17a28-135">Get-Mailbox</span><span class="sxs-lookup"><span data-stu-id="17a28-135">Get-Mailbox</span></span>

<span data-ttu-id="17a28-136">執行下列命令，以取得適用于信箱的保留和 Microsoft 365 保留原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="17a28-136">Run the following command to get information about the holds and Microsoft 365 retention policies applied to a mailbox.</span></span>

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="17a28-137">如果 InPlaceHolds 屬性中的值太多，而且不是所有的值都顯示出來，您可以執行此 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` 命令，將每個 GUID 顯示在不同的行上。</span><span class="sxs-lookup"><span data-stu-id="17a28-137">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="17a28-138">下表說明當您執行**Get-Mailbox** Cmdlet 時，如何根據*InPlaceHolds*屬性中的值來識別不同類型的保留。</span><span class="sxs-lookup"><span data-stu-id="17a28-138">The following table describes how to identify different types of holds based on the values in the *InPlaceHolds* property when you run the **Get-Mailbox** cmdlet.</span></span>


|<span data-ttu-id="17a28-139">保留類型</span><span class="sxs-lookup"><span data-stu-id="17a28-139">Hold type</span></span>  |<span data-ttu-id="17a28-140">範例值</span><span class="sxs-lookup"><span data-stu-id="17a28-140">Example value</span></span>  |<span data-ttu-id="17a28-141">如何識別保留</span><span class="sxs-lookup"><span data-stu-id="17a28-141">How to identify the hold</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="17a28-142">訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="17a28-142">Litigation Hold</span></span>     |    `True`     |     <span data-ttu-id="17a28-143">當 *LitigationHoldEnabled* 屬性設定為時，信箱的訴訟資料暫留已啟用 `True` 。</span><span class="sxs-lookup"><span data-stu-id="17a28-143">Litigation Hold is enabled for a mailbox when the *LitigationHoldEnabled* property is set to `True`.</span></span>    |
|<span data-ttu-id="17a28-144">eDiscovery 保留</span><span class="sxs-lookup"><span data-stu-id="17a28-144">eDiscovery hold</span></span>     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   <span data-ttu-id="17a28-145">*InPlaceHolds 屬性*包含與安全性與合規性中心中的 eDiscovery 案例相關聯之任何保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="17a28-145">The *InPlaceHolds property* contains the GUID of any hold associated with an eDiscovery case in the security and compliance center.</span></span> <span data-ttu-id="17a28-146">您可以告訴這是 eDiscovery 暫止保留，因為 GUID 是以 `UniH` 前置詞 (表示的整合保留) 。</span><span class="sxs-lookup"><span data-stu-id="17a28-146">You can tell this is an eDiscovery hold because the GUID starts with the `UniH` prefix (which denotes a Unified Hold).</span></span>      |
|<span data-ttu-id="17a28-147">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="17a28-147">In-Place Hold</span></span>     |     `c0ba3ce811b6432a8751430937152491` <br/> <span data-ttu-id="17a28-148">或</span><span class="sxs-lookup"><span data-stu-id="17a28-148">or</span></span> <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     <span data-ttu-id="17a28-149">*InPlaceHolds*屬性包含放在信箱上的 IN-PLACE 保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="17a28-149">The *InPlaceHolds* property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="17a28-150">您可以告知這是 In-Place 保留，因為 GUID 不是以前置詞開頭，也不是以前置詞開頭 `cld` 。</span><span class="sxs-lookup"><span data-stu-id="17a28-150">You can tell this is an In-Place Hold because the GUID either doesn't start with a prefix or it starts with the `cld` prefix.</span></span>     |
|<span data-ttu-id="17a28-151">專門套用至信箱的 Microsoft 365 保留原則</span><span class="sxs-lookup"><span data-stu-id="17a28-151">Microsoft 365 retention policy specifically applied to the mailbox</span></span>     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> <span data-ttu-id="17a28-152">或</span><span class="sxs-lookup"><span data-stu-id="17a28-152">or</span></span> <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     <span data-ttu-id="17a28-153">InPlaceHolds 屬性包含套用至信箱之任何特定位置保留原則的 Guid。</span><span class="sxs-lookup"><span data-stu-id="17a28-153">The InPlaceHolds property contains GUIDs of any specific location retention policy that's applied to the mailbox.</span></span> <span data-ttu-id="17a28-154">您可以識別保留原則，因為 GUID 是以 `mbx` 或前置詞開頭 `skp` 。</span><span class="sxs-lookup"><span data-stu-id="17a28-154">You can identify retention policies because the GUID starts with the `mbx` or the `skp` prefix.</span></span> <span data-ttu-id="17a28-155">`skp`前置詞表示將保留原則套用至使用者信箱中的商務用 Skype 交談。</span><span class="sxs-lookup"><span data-stu-id="17a28-155">The `skp` prefix indicates that the retention policy is applied to Skype for Business conversations in the user's mailbox.</span></span>    |
|<span data-ttu-id="17a28-156">從全組織的 Microsoft 365 保留原則中排除</span><span class="sxs-lookup"><span data-stu-id="17a28-156">Excluded from an organization-wide Microsoft 365 retention policy</span></span>     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     <span data-ttu-id="17a28-157">如果信箱是從全組織的 Microsoft 365 保留原則中排除，則會在 InPlaceHolds 屬性中顯示信箱所排除的保留原則 GUID，並以前置詞加以識別 `-mbx` 。</span><span class="sxs-lookup"><span data-stu-id="17a28-157">If a mailbox is excluded from an organization-wide Microsoft 365 retention policy, the GUID for the retention policy the mailbox is excluded from is displayed in the InPlaceHolds property and is identified by the `-mbx` prefix.</span></span>    |

### <a name="get-organizationconfig"></a><span data-ttu-id="17a28-158">Get-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="17a28-158">Get-OrganizationConfig</span></span>
<span data-ttu-id="17a28-159">當您執行**Get-Mailbox** Cmdlet 時，如果*InPlaceHolds*屬性是空的，則仍有一個或多個組織範圍的 Microsoft 365 保留原則會套用至信箱。</span><span class="sxs-lookup"><span data-stu-id="17a28-159">If the *InPlaceHolds* property is empty when you run the **Get-Mailbox** cmdlet, there still may be one or more organization-wide Microsoft 365 retention policies applied to the mailbox.</span></span> <span data-ttu-id="17a28-160">在 Exchange Online PowerShell 中執行下列命令，以取得整個組織的 Microsoft 365 保留原則的 Guid 清單。</span><span class="sxs-lookup"><span data-stu-id="17a28-160">Run the following command in Exchange Online PowerShell to get a list of GUIDs for organization-wide Microsoft 365 retention policies.</span></span>

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="17a28-161">如果 InPlaceHolds 屬性中的值太多，而且不是所有的值都顯示出來，您可以執行此 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 命令，將每個 GUID 顯示在不同的行上。</span><span class="sxs-lookup"><span data-stu-id="17a28-161">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="17a28-162">下表說明組織範圍的不同類型，以及如何在您執行**Get-OrganizationConfig** Cmdlet 時，根據*InPlaceHolds*屬性所包含的 guid 來識別每個類型。</span><span class="sxs-lookup"><span data-stu-id="17a28-162">The following table describes the different types of organization-wide holds and how to identify each type based on the GUIDs contained in *InPlaceHolds* property when you run the **Get-OrganizationConfig** cmdlet.</span></span>


|<span data-ttu-id="17a28-163">保留類型</span><span class="sxs-lookup"><span data-stu-id="17a28-163">Hold type</span></span>  |<span data-ttu-id="17a28-164">範例值</span><span class="sxs-lookup"><span data-stu-id="17a28-164">Example value</span></span>  |<span data-ttu-id="17a28-165">說明</span><span class="sxs-lookup"><span data-stu-id="17a28-165">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="17a28-166">適用于 Exchange 信箱、Exchange 公用資料夾和團隊聊天的 Microsoft 365 保留原則</span><span class="sxs-lookup"><span data-stu-id="17a28-166">Microsoft 365 retention policies applied to Exchange mailboxes, Exchange public folders, and Teams chats</span></span>    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   <span data-ttu-id="17a28-167">套用至 Exchange 信箱、Exchange 公用資料夾和1xN 聊天室的組織內的保留原則，都是由以前置詞開頭的 Guid 來識別 `mbx` 。</span><span class="sxs-lookup"><span data-stu-id="17a28-167">Organization-wide retention policies applied to Exchange mailboxes, Exchange public folders, and 1xN chats in Microsoft Teams are identified by GUIDs that start with the `mbx` prefix.</span></span> <span data-ttu-id="17a28-168">附注1xN 聊天會儲存在個別聊天參與者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="17a28-168">Note 1xN chats are stored in the mailbox of the individual chat participants.</span></span>      |
|<span data-ttu-id="17a28-169">套用至 Microsoft 365 群組和團隊通道郵件的 microsoft 365 保留原則</span><span class="sxs-lookup"><span data-stu-id="17a28-169">Microsoft 365 retention policy applied to Microsoft 365 Groups and Teams channel messages</span></span>     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    <span data-ttu-id="17a28-170">在 Microsoft 小組中套用至 Microsoft 365 群組和通道郵件的全組織保留原則，會由以前置詞開頭的 Guid 來識別 `grp` 。</span><span class="sxs-lookup"><span data-stu-id="17a28-170">Organization-wide retention policies applied to Microsoft 365 groups and channel messages in Microsoft Teams are identified by GUIDs that start with the `grp` prefix.</span></span> <span data-ttu-id="17a28-171">附注通道郵件會儲存在與 Microsoft 小組相關聯的群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="17a28-171">Note channel messages are stored in the group mailbox that is associated with a Microsoft Team.</span></span>     |

<span data-ttu-id="17a28-172">如需適用于 Microsoft 小組之保留原則的詳細資訊，請參閱 [瞭解 Microsoft 小組的保留原則](retention-policies-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="17a28-172">For more information about retention policies applied to Microsoft Teams, see [Learn about retention policies for Microsoft Teams](retention-policies-teams.md).</span></span>

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a><span data-ttu-id="17a28-173">瞭解保留原則的 InPlaceHolds 值格式</span><span class="sxs-lookup"><span data-stu-id="17a28-173">Understanding the format of the InPlaceHolds value for retention policies</span></span>

<span data-ttu-id="17a28-174">除了 (將 InPlaceHolds 屬性中的專案識別為 Microsoft 365 保留原則的 mbx、skp 或 grp) 之外，此值還會包含一個尾碼，識別針對原則所設定的保留動作類型。</span><span class="sxs-lookup"><span data-stu-id="17a28-174">In addition to the prefix (mbx, skp, or grp) that identifies an item in the InPlaceHolds property as a Microsoft 365 retention policy, the value also contains a suffix that identifies the type of retention action that's configured for the policy.</span></span> <span data-ttu-id="17a28-175">例如，下列範例中的動作尾碼會以粗體反白顯示：</span><span class="sxs-lookup"><span data-stu-id="17a28-175">For example, the action suffix is highlighted in bold type in the following examples:</span></span>

   <span data-ttu-id="17a28-176">`skp127d7cf1076947929bf136b7a2a8c36f`**：1**</span><span class="sxs-lookup"><span data-stu-id="17a28-176">`skp127d7cf1076947929bf136b7a2a8c36f`**:1**</span></span>

   <span data-ttu-id="17a28-177">`mbx7cfb30345d454ac0a989ab3041051209`**：2**</span><span class="sxs-lookup"><span data-stu-id="17a28-177">`mbx7cfb30345d454ac0a989ab3041051209`**:2**</span></span>

   <span data-ttu-id="17a28-178">`grp1a0a132ee8944501a4bb6a452ec31171`**：3**</span><span class="sxs-lookup"><span data-stu-id="17a28-178">`grp1a0a132ee8944501a4bb6a452ec31171`**:3**</span></span>

<span data-ttu-id="17a28-179">下表定義三種可能的保留動作：</span><span class="sxs-lookup"><span data-stu-id="17a28-179">The following table defines the three possible retention actions:</span></span>

|<span data-ttu-id="17a28-180">值</span><span class="sxs-lookup"><span data-stu-id="17a28-180">Value</span></span>  |<span data-ttu-id="17a28-181">說明</span><span class="sxs-lookup"><span data-stu-id="17a28-181">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="17a28-182">**1**</span><span class="sxs-lookup"><span data-stu-id="17a28-182">**1**</span></span>     | <span data-ttu-id="17a28-183">表示保留原則已設定為刪除專案。</span><span class="sxs-lookup"><span data-stu-id="17a28-183">Indicates that the retention policy is configured to delete items.</span></span> <span data-ttu-id="17a28-184">原則不會保留專案。</span><span class="sxs-lookup"><span data-stu-id="17a28-184">The policy doesn't retain items.</span></span>        |
|<span data-ttu-id="17a28-185">**2**</span><span class="sxs-lookup"><span data-stu-id="17a28-185">**2**</span></span>    |    <span data-ttu-id="17a28-186">表示保留原則設定為保留專案。</span><span class="sxs-lookup"><span data-stu-id="17a28-186">Indicates that the retention policy is configured to hold items.</span></span> <span data-ttu-id="17a28-187">原則不會在保留期間到期之後刪除專案。</span><span class="sxs-lookup"><span data-stu-id="17a28-187">The policy doesn't delete items after the retention period expires.</span></span>     |
|<span data-ttu-id="17a28-188">**個**</span><span class="sxs-lookup"><span data-stu-id="17a28-188">**3**</span></span>     |   <span data-ttu-id="17a28-189">表示保留原則已設定為保留專案，然後在保留期間到期時加以刪除。</span><span class="sxs-lookup"><span data-stu-id="17a28-189">Indicates that the retention policy is configured to hold items and then delete them after the retention period expires.</span></span>      |

<span data-ttu-id="17a28-190">如需有關保留動作的詳細資訊，請參閱在 [特定時間段內保留內容](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) 一節。</span><span class="sxs-lookup"><span data-stu-id="17a28-190">For more information about retention actions, see the [Retaining content for a specific period of time](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) section.</span></span>
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a><span data-ttu-id="17a28-191">步驟2：使用 GUID 識別保留</span><span class="sxs-lookup"><span data-stu-id="17a28-191">Step 2: Use the GUID to identify the hold</span></span>

<span data-ttu-id="17a28-192">在您取得套用至信箱之保留的 GUID 之後，下一步是使用該 GUID 來識別保留。</span><span class="sxs-lookup"><span data-stu-id="17a28-192">After you obtain the GUID for a hold that is applied to a mailbox, the next step is to use that GUID to identify the hold.</span></span> <span data-ttu-id="17a28-193">下列各節說明如何使用保留 GUID 來識別保留的名稱 (及其他資訊) 。</span><span class="sxs-lookup"><span data-stu-id="17a28-193">The following sections show how to identify the name of the hold (and other information) by using the hold GUID.</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="17a28-194">eDiscovery 保留</span><span class="sxs-lookup"><span data-stu-id="17a28-194">eDiscovery holds</span></span>

<span data-ttu-id="17a28-195">在安全性 & 規範中心 PowerShell 中執行下列命令，以找出套用至信箱的 eDiscovery 暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="17a28-195">Run the following commands in Security & Compliance Center PowerShell to identify an eDiscovery hold that's applied to the mailbox.</span></span> <span data-ttu-id="17a28-196">針對您在步驟1中識別的 eDiscovery 保留，使用 GUID (不包括 UniH 前置詞) 。</span><span class="sxs-lookup"><span data-stu-id="17a28-196">Use the GUID (not including the UniH prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="17a28-197">第一個命令會建立包含保留相關資訊的變數。</span><span class="sxs-lookup"><span data-stu-id="17a28-197">The first command creates a variable that contains information about the hold.</span></span> <span data-ttu-id="17a28-198">在其他命令中使用此變數。</span><span class="sxs-lookup"><span data-stu-id="17a28-198">This variable is used in the other commands.</span></span> <span data-ttu-id="17a28-199">第二個命令會顯示與該保留相關聯的 eDiscovery 案例名稱。</span><span class="sxs-lookup"><span data-stu-id="17a28-199">The second command displays the name of the eDiscovery case the hold is associated with.</span></span> <span data-ttu-id="17a28-200">第三個命令會顯示保留的名稱，以及保留所套用的信箱清單。</span><span class="sxs-lookup"><span data-stu-id="17a28-200">The third command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

<span data-ttu-id="17a28-201">若要連線至安全性 & 合規性中心 PowerShell，請參閱  [connect To security & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="17a28-201">To connect to Security & Compliance Center PowerShell, see  [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

### <a name="in-place-holds"></a><span data-ttu-id="17a28-202">就地保留</span><span class="sxs-lookup"><span data-stu-id="17a28-202">In-Place Holds</span></span>

<span data-ttu-id="17a28-203">在 Exchange Online PowerShell 中執行下列命令，以識別套用至信箱的 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="17a28-203">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's applied to the mailbox.</span></span> <span data-ttu-id="17a28-204">使用您在步驟1中識別的 In-Place 保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="17a28-204">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> <span data-ttu-id="17a28-205">此命令會顯示保留專案的名稱，以及保留所套用的信箱清單。</span><span class="sxs-lookup"><span data-stu-id="17a28-205">The command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

<span data-ttu-id="17a28-206">如果 In-Place 保留的 GUID 是以前置詞開頭 `cld` ，請務必在執行先前的命令時包含首碼。</span><span class="sxs-lookup"><span data-stu-id="17a28-206">If the GUID for the In-Place Hold starts with the `cld` prefix, be sure to include the prefix when running the previous command.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17a28-207">當我們繼續以保留信箱內容的不同方式投資時，我們宣佈 Exchange 系統管理中心 (EAC) 的退休 In-Place。</span><span class="sxs-lookup"><span data-stu-id="17a28-207">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="17a28-208">從2020年7月1日起，您將無法在 Exchange Online 中建立新的 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="17a28-208">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="17a28-209">不過，您仍然可以管理 EAC 中的 In-Place，或是使用 Exchange Online PowerShell 中的 **Set-MailboxSearch** Cmdlet 來管理。</span><span class="sxs-lookup"><span data-stu-id="17a28-209">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="17a28-210">不過，從2020年10月1日開始，您將無法管理 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="17a28-210">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="17a28-211">您只會在 EAC 中或使用 **Remove-MailboxSearch** Cmdlet 中移除它們。</span><span class="sxs-lookup"><span data-stu-id="17a28-211">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="17a28-212">如需停用 In-Place 保留的詳細資訊，請參閱 [舊版 eDiscovery tools 的退休](legacy-ediscovery-retirement.md)。</span><span class="sxs-lookup"><span data-stu-id="17a28-212">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>

### <a name="microsoft-365-retention-policies"></a><span data-ttu-id="17a28-213">Microsoft 365 保留原則</span><span class="sxs-lookup"><span data-stu-id="17a28-213">Microsoft 365 retention policies</span></span>

<span data-ttu-id="17a28-214">在 [安全性 & 規範中心] 中執行下列命令，PowerShell 識別套用至信箱) 的 Microsoft 365 保留原則 (整個組織或特定位置。</span><span class="sxs-lookup"><span data-stu-id="17a28-214">Run the following command in Security & Compliance Center PowerShell to identity the Microsoft 365 retention policy (organization-wide or specific location) that's applied to the mailbox.</span></span> <span data-ttu-id="17a28-215">使用 GUID (不要包含您在步驟1中識別的 mbx、skp 或 grp 首碼或動作尾碼) 。</span><span class="sxs-lookup"><span data-stu-id="17a28-215">Use the GUID (not including the mbx, skp, or grp prefix or the action suffix) that you identified in Step 1.</span></span>

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a><span data-ttu-id="17a28-216">因為保留標籤已套用至資料夾或專案，因此識別保留的信箱</span><span class="sxs-lookup"><span data-stu-id="17a28-216">Identifying mailboxes on hold because a retention label has been applied to a folder or item</span></span>

<span data-ttu-id="17a28-217">每當使用者套用設定為保留內容或保留的保留標籤，然後將內容刪除至其信箱中的任何資料夾或專案時， *ComplianceTagHoldApplied* 信箱屬性都會設為 **True**。</span><span class="sxs-lookup"><span data-stu-id="17a28-217">Whenever a user applies a retention label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="17a28-218">當發生這種情況時，信箱會被視為保留，就像是設定為訴訟暫止或指派給 Microsoft 365 保留原則一樣。</span><span class="sxs-lookup"><span data-stu-id="17a28-218">When this happens, the mailbox is considered to be on hold, as if it was placed on Litigation Hold or assigned to a Microsoft 365 retention policy.</span></span> <span data-ttu-id="17a28-219">當 *ComplianceTagHoldApplied* 屬性設定為 **True**時，可能會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="17a28-219">When the *ComplianceTagHoldApplied* property is set to **True**, the following things may occur:</span></span>

- <span data-ttu-id="17a28-220">如果信箱或使用者的使用者帳戶已刪除，則信箱會變成非使用中的 [信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="17a28-220">If the mailbox or the user's user account is deleted, the mailbox becomes an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span>
- <span data-ttu-id="17a28-221">您無法停用主要信箱或封存信箱 (的信箱（如果已啟用) ）。</span><span class="sxs-lookup"><span data-stu-id="17a28-221">You aren't able to disable the mailbox (either the primary mailbox or the archive mailbox, if it's enabled).</span></span>
- <span data-ttu-id="17a28-222">信箱中的專案可以保留的時間超過預期。</span><span class="sxs-lookup"><span data-stu-id="17a28-222">Items in the mailbox may be retained longer than expected.</span></span> <span data-ttu-id="17a28-223">這是因為信箱處於保留狀態，因此不會永久刪除 (清除) 中的專案。</span><span class="sxs-lookup"><span data-stu-id="17a28-223">This is because the mailbox is on hold and therefore no items are permanently deleted (purged).</span></span>

<span data-ttu-id="17a28-224">若要查看 *ComplianceTagHoldApplied* 屬性的值，請在 Exchange Online 中執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="17a28-224">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="17a28-225">如需保留標籤的詳細資訊，請參閱 [保留標籤](retention.md#retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="17a28-225">For more information about retention labels, see [retention labels](retention.md#retention-labels).</span></span>

## <a name="managing-mailboxes-on-delay-hold"></a><span data-ttu-id="17a28-226">管理延遲暫止的信箱</span><span class="sxs-lookup"><span data-stu-id="17a28-226">Managing mailboxes on delay hold</span></span>

<span data-ttu-id="17a28-227">從信箱移除任何類型的保留後，會套用 *延遲保留* 。</span><span class="sxs-lookup"><span data-stu-id="17a28-227">After any type of hold is removed from a mailbox, a *delay hold* is applied.</span></span> <span data-ttu-id="17a28-228">這表示實際刪除保留的時間延遲30天，以防止資料被永久刪除 (從信箱中清除) 。</span><span class="sxs-lookup"><span data-stu-id="17a28-228">This means that the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted (purged) from the mailbox.</span></span> <span data-ttu-id="17a28-229">這可讓系統管理員在移除保留後，搜尋或復原將會清除的信箱專案。</span><span class="sxs-lookup"><span data-stu-id="17a28-229">This gives admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.</span></span> <span data-ttu-id="17a28-230">[延遲保留] 會在下一次受管理的資料夾助理處理信箱，並偵測已移除保留時，放在信箱上。</span><span class="sxs-lookup"><span data-stu-id="17a28-230">A delay hold is placed on a mailbox the next time the Managed Folder Assistant processes the mailbox and detects that a hold was removed.</span></span> <span data-ttu-id="17a28-231">具體說來，當受管理的資料夾助理將下列其中一個信箱屬性設定為 **True**時，會將延遲保留套用至信箱：</span><span class="sxs-lookup"><span data-stu-id="17a28-231">Specifically, a delay hold is applied to a mailbox when the Managed Folder Assistant sets one of the following mailbox properties to **True**:</span></span>

- <span data-ttu-id="17a28-232">**DelayHoldApplied：** 此屬性適用于使用 Outlook 的使用者所產生的電子郵件與 Outlook，以及儲存在使用者信箱中的 web) 上的 Outlook 所產生的內容 (。</span><span class="sxs-lookup"><span data-stu-id="17a28-232">**DelayHoldApplied:** This property applies to email-related content (generated by people using Outlook and Outlook on the web) that's stored in a user's mailbox.</span></span>

- <span data-ttu-id="17a28-233">**DelayReleaseHoldApplied：** 此屬性適用于由非 Outlook 應用程式（如 Microsoft 團隊、Microsoft Forms 及 Microsoft Yammer) 所產生）所產生的雲端式內容 (，這些應用程式儲存在使用者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="17a28-233">**DelayReleaseHoldApplied:** This property applies to cloud-based content (generated by non-Outlook apps such as Microsoft Teams, Microsoft Forms, and Microsoft Yammer) that's stored in a user's mailbox.</span></span> <span data-ttu-id="17a28-234">Microsoft app 所產生的雲端資料通常會儲存在使用者信箱中的隱藏資料夾中。</span><span class="sxs-lookup"><span data-stu-id="17a28-234">Cloud data generated by a Microsoft app is typically stored in a hidden folder in a user's mailbox.</span></span>
 
 <span data-ttu-id="17a28-235">當 [任何先前的屬性] 設定為 True 時，信箱 (上的 [延遲保留] 設定為) **True** 時，信箱仍會被視為無限期保留期間（如同信箱處於訴訟暫止狀態時）。</span><span class="sxs-lookup"><span data-stu-id="17a28-235">When a delay hold is placed on the mailbox (when either of the previous properties is set to **True**), the mailbox is still considered to be on hold for an unlimited hold duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="17a28-236">30天后，延遲保留會到期，而且 Microsoft 365 會嘗試將 DelayHoldApplied 或 DelayReleaseHoldApplied 屬性設定為 **False**) ，以移除延遲保留 (，使保留成為移除。</span><span class="sxs-lookup"><span data-stu-id="17a28-236">After 30 days, the delay hold expires, and Microsoft 365 will automatically attempt to remove the delay hold (by setting the DelayHoldApplied or DelayReleaseHoldApplied property to **False**) so that the hold is removed.</span></span> <span data-ttu-id="17a28-237">在上述任一屬性設定為 **False**之後，在下一次受管理的資料夾助理處理信箱時，會清除標示為待移除的對應專案。</span><span class="sxs-lookup"><span data-stu-id="17a28-237">After either of these properties are set to **False**, the corresponding items that are marked for removal are purged the next time the mailbox is processed by the Managed Folder Assistant.</span></span>

<span data-ttu-id="17a28-238">若要查看信箱的 DelayHoldApplied 和 DelayReleaseHoldApplied 屬性的值，請在 Exchange Online PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="17a28-238">To view the values for the DelayHoldApplied and DelayReleaseHoldApplied properties for a mailbox, run the following command in Exchange Online PowerShell.</span></span>

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

<span data-ttu-id="17a28-239">若要在到期之前移除延遲保留，您可以在 Exchange Online PowerShell 中執行 () 下列命令，取決於您要變更的屬性：</span><span class="sxs-lookup"><span data-stu-id="17a28-239">To remove the delay hold before it expires, you can run one (or both) the following commands in Exchange Online PowerShell, depending on which property you want to change:</span></span> 
 
```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

<span data-ttu-id="17a28-240">或者</span><span class="sxs-lookup"><span data-stu-id="17a28-240">Or</span></span>
 
```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

<span data-ttu-id="17a28-241">您必須在 Exchange Online 中指派合法保留角色，才能使用 *RemoveDelayHoldApplied* 或 *RemoveDelayReleaseHoldApplied* 參數。</span><span class="sxs-lookup"><span data-stu-id="17a28-241">You must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* or *RemoveDelayReleaseHoldApplied* parameters.</span></span> 

<span data-ttu-id="17a28-242">若要移除非使用中信箱的延遲保留，請在 Exchange Online 中執行下列其中一個命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="17a28-242">To remove the delay hold on an inactive mailbox, run one of the following commands in Exchange Online PowerShell:</span></span>

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

<span data-ttu-id="17a28-243">或者</span><span class="sxs-lookup"><span data-stu-id="17a28-243">Or</span></span>

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> <span data-ttu-id="17a28-244">在上一個命令中指定非使用中信箱的最佳方式是使用其辨別名稱或 Exchange GUID 值。</span><span class="sxs-lookup"><span data-stu-id="17a28-244">The best way to specify an inactive mailbox in the previous command is to use its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="17a28-245">使用其中一個值可協助避免意外指定錯誤的信箱。</span><span class="sxs-lookup"><span data-stu-id="17a28-245">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 

<span data-ttu-id="17a28-246">如需使用這些參數管理延遲保留的詳細資訊，請參閱 [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="17a28-246">For more information about using these parameters for managing delay holds, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="17a28-247">在 [延遲保留] 中管理信箱時，請牢記下列事項：</span><span class="sxs-lookup"><span data-stu-id="17a28-247">Keep the following things in mind when managing a mailbox on delay hold:</span></span>

- <span data-ttu-id="17a28-248">如果 DelayHoldApplied 或 DelayReleaseHoldApplied 屬性設定為 **True** ，而信箱 (或對應的使用者帳戶) 被刪除，則信箱會變成非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="17a28-248">If either the DelayHoldApplied or DelayReleaseHoldApplied property is set to **True** and a mailbox (or the corresponding user account) is deleted, the mailbox becomes an inactive mailbox.</span></span> <span data-ttu-id="17a28-249">這是因為如果其中一個屬性設定為 **True**，並刪除保留的信箱導致非使用中的信箱，信箱會被視為保留。</span><span class="sxs-lookup"><span data-stu-id="17a28-249">That's because a mailbox is considered to be on hold if either property is set to **True**, and deleting a mailbox on hold results in an inactive mailbox.</span></span> <span data-ttu-id="17a28-250">若要刪除信箱，但未將其設為非使用中的信箱，您必須將這兩個屬性設定為 **False**。</span><span class="sxs-lookup"><span data-stu-id="17a28-250">To delete a mailbox and not make it an inactive mailbox, you have to set both properties to **False**.</span></span>

- <span data-ttu-id="17a28-251">如先前所述，如果 DelayHoldApplied 或 DelayReleaseHoldApplied 屬性設定為 **True**，信箱會被視為無限制保留期間的保留期間。</span><span class="sxs-lookup"><span data-stu-id="17a28-251">As previous stated, a mailbox is considered to be on hold for an unlimited hold duration if either the DelayHoldApplied or DelayReleaseHoldApplied property is set to **True**.</span></span> <span data-ttu-id="17a28-252">不過，這並不表示保留信箱中的 *所有* 內容。</span><span class="sxs-lookup"><span data-stu-id="17a28-252">However, that doesn't mean that *all* content in the mailbox is preserved.</span></span> <span data-ttu-id="17a28-253">它會根據設定為每個屬性的值而定。</span><span class="sxs-lookup"><span data-stu-id="17a28-253">It depends on the value that's set to each property.</span></span> <span data-ttu-id="17a28-254">例如，假設這兩個屬性都設定為 **True** ，因為保留已從信箱中移除。</span><span class="sxs-lookup"><span data-stu-id="17a28-254">For example, let's say both properties are set to **True** because holds are removed from the mailbox.</span></span> <span data-ttu-id="17a28-255">然後，使用 *RemoveDelayReleaseHoldApplied* 參數) ，只會移除套用至非 Outlook 雲端資料 (的延遲保留。</span><span class="sxs-lookup"><span data-stu-id="17a28-255">Then you remove only the delay hold that's applied to non-Outlook cloud data (by using the *RemoveDelayReleaseHoldApplied* parameter).</span></span> <span data-ttu-id="17a28-256">在下一次受管理的資料夾助理處理信箱時，會清除標示為待移除的非 Outlook 專案。</span><span class="sxs-lookup"><span data-stu-id="17a28-256">The next time the Managed Folder Assistant processes the mailbox, the non-Outlook items marked for removal are purged.</span></span> <span data-ttu-id="17a28-257">因為 DelayHoldApplied 屬性仍設定為 **True**，所以不會清除任何標為待移除的 Outlook 專案。</span><span class="sxs-lookup"><span data-stu-id="17a28-257">Any Outlook items marked for removal won't be purged because the DelayHoldApplied property is still set to **True**.</span></span> <span data-ttu-id="17a28-258">相反的情況也是真：如果 DelayHoldApplied 設定為 **False** ，而 DelayReleaseHoldApplied 設定為 **true**，則只會清除標示為待移除的 Outlook 專案。</span><span class="sxs-lookup"><span data-stu-id="17a28-258">The opposite would also be true: if DelayHoldApplied is set to **False** and DelayReleaseHoldApplied is set to **True**, then only Outlook items marked for removal would be purged.</span></span>

## <a name="next-steps"></a><span data-ttu-id="17a28-259">後續步驟</span><span class="sxs-lookup"><span data-stu-id="17a28-259">Next steps</span></span>

<span data-ttu-id="17a28-260">在您識別套用至信箱的保留後，您可以執行工作，例如變更保留期間、暫時或永久移除保留，或排除 Microsoft 365 保留原則中非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="17a28-260">After you identify the holds that are applied to a mailbox, you can perform tasks such as changing the duration of the hold, temporarily or permanently removing the hold, or excluding an inactive mailbox from a Microsoft 365 retention policy.</span></span> <span data-ttu-id="17a28-261">如需執行與保留相關之工作的詳細資訊，請參閱下列其中一個主題：</span><span class="sxs-lookup"><span data-stu-id="17a28-261">For more information about performing tasks related to holds, see the one of the following topics:</span></span>

- <span data-ttu-id="17a28-262">在安全性 & 規範中心」中執行[Set-RetentionCompliancePolicy AddExchangeLocationException \<user mailbox> ](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)命令，PowerShell 從整個組織的 Microsoft 365 保留原則中排除信箱。</span><span class="sxs-lookup"><span data-stu-id="17a28-262">Run the [Set-RetentionCompliancePolicy -AddExchangeLocationException \<user mailbox>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) command in Security & Compliance Center PowerShell to exclude a mailbox from an organization-wide Microsoft 365 retention policy.</span></span> <span data-ttu-id="17a28-263">這個命令僅可用於 *ExchangeLocation* 屬性值等於的保留原則 `All` 。</span><span class="sxs-lookup"><span data-stu-id="17a28-263">This command can only be used for retention policies where the value for the *ExchangeLocation* property equals `All`.</span></span>

- <span data-ttu-id="17a28-264">在 Exchange Online PowerShell 中執行[Set-Mailbox ExcludeFromOrgHolds \<hold GUID without prefix or suffix> ](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)命令，以從整個組織的 Microsoft 365 保留原則中排除非作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="17a28-264">Run the [Set-Mailbox -ExcludeFromOrgHolds \<hold GUID without prefix or suffix>](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide Microsoft 365 retention policy.</span></span>

- [<span data-ttu-id="17a28-265">變更非使用中信箱的保留期間</span><span class="sxs-lookup"><span data-stu-id="17a28-265">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="17a28-266">刪除非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="17a28-266">Delete an inactive mailbox</span></span>](delete-an-inactive-mailbox.md)

- [<span data-ttu-id="17a28-267">刪除雲端式信箱中可復原的項目資料夾中的保留項目</span><span class="sxs-lookup"><span data-stu-id="17a28-267">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold</span></span>](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
