---
title: 啟用無限封存-系統管理協助
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 針對系統管理員：瞭解如何啟用自動擴充封存，可為使用者提供 Exchange Online 信箱的無限存放區。 您可以為整個組織啟用自動展開的封存，也可以只為特定使用者啟用此功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ac5661ac43ed9c0f35eba20007f0c4c4406ebf20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927823"
---
# <a name="enable-unlimited-archiving---admin-help"></a><span data-ttu-id="1ac48-104">啟用無限封存-系統管理協助</span><span class="sxs-lookup"><span data-stu-id="1ac48-104">Enable unlimited archiving - Admin Help</span></span>

<span data-ttu-id="1ac48-105">您可以使用 Exchange Online 自動展開的封存功能來啟用封存信箱的無限存放空間。</span><span class="sxs-lookup"><span data-stu-id="1ac48-105">You can use the Exchange Online auto-expanding archiving feature to enable unlimited storage space for archive mailboxes.</span></span> <span data-ttu-id="1ac48-106">當自動展開的封存開啟時，會自動將額外的儲存空間新增至使用者的封存信箱，當其接近儲存量限制時。</span><span class="sxs-lookup"><span data-stu-id="1ac48-106">When auto-expanding archiving is turned on, additional storage space is automatically added to a user's archive mailbox when it approaches the storage limit.</span></span> <span data-ttu-id="1ac48-107">結果為無限制的信箱儲存容量。</span><span class="sxs-lookup"><span data-stu-id="1ac48-107">The result is unlimited mailbox storage capacity.</span></span> <span data-ttu-id="1ac48-108">您可以為組織中的每個人或僅針對特定使用者開啟自動擴充封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-108">You can turn on auto-expanding archiving for everyone in your organization or just for specific users.</span></span> <span data-ttu-id="1ac48-109">如需有關自動展開封存的詳細資訊，請參閱 [Office 365 中的無限封存概述](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="1ac48-109">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>

## <a name="before-you-enable-auto-expanding-archiving"></a><span data-ttu-id="1ac48-110">啟用自動擴充封存之前</span><span class="sxs-lookup"><span data-stu-id="1ac48-110">Before you enable auto-expanding archiving</span></span>

- <span data-ttu-id="1ac48-111">您必須是組織中的全域系統管理員，或 Exchange Online 組織中組織管理角色群組的成員，才能啟用整個組織或特定使用者的自動擴充封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-111">You have to be a global administrator in your organization or a member of the Organization Management role group in your Exchange Online organization to enable auto-expanding archiving for your entire organization or for specific users.</span></span> <span data-ttu-id="1ac48-112">或者，您必須是指派「郵件收件者」角色的角色群組成員，才能為特定使用者啟用自動擴充封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-112">Alternately, you have to be a member of a role group that's assigned the Mail Recipients role to enable auto-expanding archiving for specific users.</span></span>

- <span data-ttu-id="1ac48-113">必須啟用使用者的封存信箱，才能啟用自動擴充封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-113">A user's archive mailbox has to be enabled before you can enable auto-expanding archiving.</span></span> <span data-ttu-id="1ac48-114">使用者必須被指派 Exchange Online Plan 2 授權，才能啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="1ac48-114">A user must be assigned an Exchange Online Plan 2 license to enable the archive mailbox.</span></span> <span data-ttu-id="1ac48-115">若使用者已獲指派 Exchange Online Plan 1 授權，您必須指派個別的 Exchange Online 封存授權，以啟用其封存信箱。</span><span class="sxs-lookup"><span data-stu-id="1ac48-115">If a user is assigned an Exchange Online Plan 1 license, you would have to assign them a separate Exchange Online Archiving license to enable their archive mailbox.</span></span> <span data-ttu-id="1ac48-116">請參閱在 [安全性 & 規範中心啟用封存信箱](enable-archive-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="1ac48-116">See [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md).</span></span>

- <span data-ttu-id="1ac48-117">您也可以使用 PowerShell 來啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="1ac48-117">You can also use PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="1ac48-118">請參閱 [More information](#more-information) 一節，以取得 PowerShell 命令的範例，您可以用來為組織中的所有使用者啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="1ac48-118">See the [More information](#more-information) section for an example of the PowerShell command that you can use to enable archive mailboxes for all users in your organization.</span></span>

- <span data-ttu-id="1ac48-119">自動展開封存也支援共用信箱。</span><span class="sxs-lookup"><span data-stu-id="1ac48-119">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="1ac48-120">若要啟用共用信箱的封存，則需要 exchange Online Plan 2 授權或 Exchange online Plan 1 授權與 Exchange Online 封存授權。</span><span class="sxs-lookup"><span data-stu-id="1ac48-120">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>

- <span data-ttu-id="1ac48-121">自動展開封存可防止您復原或還原非使用中的 [信箱](inactive-mailboxes-in-office-365.md#what-are-inactive-mailboxes)。</span><span class="sxs-lookup"><span data-stu-id="1ac48-121">Auto-expanding archiving prevents you from recovering or restoring an [inactive mailbox](inactive-mailboxes-in-office-365.md#what-are-inactive-mailboxes).</span></span> <span data-ttu-id="1ac48-122">這表示如果您為信箱啟用自動展開的封存，而且信箱在日後變為非使用中，則您將無法透過將內容合併至現有的信箱) 來 [復原非使用中的信箱](recover-an-inactive-mailbox.md) () 或將 [其還原](restore-an-inactive-mailbox.md) (。</span><span class="sxs-lookup"><span data-stu-id="1ac48-122">That means if you enable auto-expanding archiving for a mailbox and the mailbox is made inactive at a later date, you won't be able to [recover the inactive mailbox](recover-an-inactive-mailbox.md) (by converting it to an active mailbox) or [restore it](restore-an-inactive-mailbox.md) (by merging the contents to an existing mailbox).</span></span> <span data-ttu-id="1ac48-123">若在非使用中的信箱上啟用自動擴充封存，恢復資料的唯一方法是使用 Microsoft 365 規範中心的「內容搜尋」工具，從信箱中匯出資料，然後匯入至另一個信箱。</span><span class="sxs-lookup"><span data-stu-id="1ac48-123">If auto-expanding archiving is enabled on an inactive mailbox, the only way to recover data is by using the Content search tool in the Microsoft 365 compliance center to export the data from the mailbox and import to another mailbox.</span></span> <span data-ttu-id="1ac48-124">如需詳細資訊，請參閱非使用中 [信箱](inactive-mailboxes-in-office-365.md#inactive-mailboxes-and-auto-expanding-archives)的「非使用中信箱和自動展開的封存」一節。</span><span class="sxs-lookup"><span data-stu-id="1ac48-124">For more information, see the "Inactive mailboxes and auto-expanding archives" section in [Overview of inactive mailboxes](inactive-mailboxes-in-office-365.md#inactive-mailboxes-and-auto-expanding-archives).</span></span>

- <span data-ttu-id="1ac48-125">您無法使用 Exchange 系統管理中心或安全性 & 規範中心來啟用自動擴充封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-125">You can't use the Exchange admin center or the Security & Compliance Center to enable auto-expanding archiving.</span></span> <span data-ttu-id="1ac48-126">您必須使用 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1ac48-126">You have to use Exchange Online PowerShell.</span></span> <span data-ttu-id="1ac48-127">若要使用遠端 PowerShell 連線到您的 Exchange Online 組織，請參閱 [connect To Exchange online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1ac48-127">To connect to your Exchange Online organization using remote PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a><span data-ttu-id="1ac48-128">啟用整個組織的自動擴充封存</span><span class="sxs-lookup"><span data-stu-id="1ac48-128">Enable auto-expanding archiving for your entire organization</span></span>

<span data-ttu-id="1ac48-129">您可以為整個組織啟用自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-129">You can enable auto-expanding archiving for your entire organization.</span></span> <span data-ttu-id="1ac48-130">開啟之後，會針對現有的使用者信箱及建立的新使用者信箱啟用自動擴充封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-130">After you turn it on, auto-expanding archiving will be enabled for existing user mailboxes and for new user mailboxes that are created.</span></span> <span data-ttu-id="1ac48-131">當您建立使用者信箱時，請務必啟用使用者的主要封存信箱，這樣新使用者信箱的自動擴充封存功能才能運作。</span><span class="sxs-lookup"><span data-stu-id="1ac48-131">When you create user mailboxes, be sure to enable the user's main archive mailbox so the auto-expanding archiving feature works for the new user mailbox.</span></span>
  
1. [<span data-ttu-id="1ac48-132">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ac48-132">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="1ac48-133">在 Exchange Online PowerShell 中執行下列命令，以啟用整個組織的自動擴充封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-133">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for your entire organization.</span></span>

    ```powershell
    Set-OrganizationConfig -AutoExpandingArchive
    ```

## <a name="enable-auto-expanding-archiving-for-specific-users"></a><span data-ttu-id="1ac48-134">啟用特定使用者的自動擴充封存</span><span class="sxs-lookup"><span data-stu-id="1ac48-134">Enable auto-expanding archiving for specific users</span></span>

<span data-ttu-id="1ac48-135">除了為組織中的每位使用者啟用自動擴充封存，您只可對特定使用者啟用該封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-135">Instead of enabling auto-expanding archiving for every user in your organization, you can enable it only for specific users.</span></span> <span data-ttu-id="1ac48-136">您也可以這麼做，因為只有某些使用者可能需要大量的封存儲存容量。</span><span class="sxs-lookup"><span data-stu-id="1ac48-136">You might do this because only some users might have a need for a large archive storage capacity.</span></span>
  
<span data-ttu-id="1ac48-137">當您為特定使用者啟用自動擴充封存，且使用者的信箱處於暫止狀態或指派給保留原則時，會進行下列兩項設定變更：</span><span class="sxs-lookup"><span data-stu-id="1ac48-137">When you enable auto-expanding archiving for a specific user and the user's mailbox in on hold or assigned to a retention policy, the following two configurations changes are made:</span></span>
  
- <span data-ttu-id="1ac48-138">使用者主要封存信箱的儲存配額會從 100 GB (增加到 110 GB) 。</span><span class="sxs-lookup"><span data-stu-id="1ac48-138">The storage quota for the user's primary archive mailbox is increased by 10 GB (from 100 GB to 110 GB).</span></span> <span data-ttu-id="1ac48-139">封存警告配額也會以 10 GB (增加，從 90 GB 到 100 GB) 。</span><span class="sxs-lookup"><span data-stu-id="1ac48-139">The archive warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span>

- <span data-ttu-id="1ac48-140">使用者主要信箱中 [可復原的專案] 資料夾的儲存配額已增加 10 GB (，也會從 100 GB 增加至 110 GB) 。</span><span class="sxs-lookup"><span data-stu-id="1ac48-140">The storage quota for the Recoverable Items folder in the user's primary mailbox is increased by 10 GB (also from 100 GB to 110 GB).</span></span> <span data-ttu-id="1ac48-141">可復原的專案警告配額也會從 90 GB (到 100 GB) ，增加 10 GB。</span><span class="sxs-lookup"><span data-stu-id="1ac48-141">The Recoverable Items warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span> <span data-ttu-id="1ac48-142">只有當信箱處於暫止狀態或指派給保留原則時，這些變更才適用。</span><span class="sxs-lookup"><span data-stu-id="1ac48-142">These changes are applicable only if the mailbox in on hold or assigned to a retention policy.</span></span>

<span data-ttu-id="1ac48-143">新增此額外的空間，以避免在自動展開的封存布建之前可能發生的任何儲存問題。</span><span class="sxs-lookup"><span data-stu-id="1ac48-143">This additional space is added to prevent any storage issues that may occur before the auto-expanding archive is provisioned.</span></span> <span data-ttu-id="1ac48-144">當您為整個組織啟用自動擴充封存時，  *將不會*  新增額外的儲存空間，如前一節所述。</span><span class="sxs-lookup"><span data-stu-id="1ac48-144">Additional storage space  *is not*  added when you enable auto-expanding archiving for your entire organization, as described in the previous section.</span></span>
  
1. [<span data-ttu-id="1ac48-145">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ac48-145">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="1ac48-146">在 Exchange Online PowerShell 中執行下列命令，以啟用特定使用者的自動擴充封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-146">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for a specific user.</span></span> <span data-ttu-id="1ac48-147">如先前所述，必須先啟用使用者的封存信箱 (主封存) ，才能為該使用者開啟自動展開的封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-147">As previously explained, the user's archive mailbox (main archive) must be enabled before you can turn on auto-expanding archiving for that user.</span></span>

    ```powershell
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```

> [!IMPORTANT]
> <span data-ttu-id="1ac48-148">在 Exchange 混合式部署中，您無法使用 **Enable-Mailbox-AutoExpandingArchive** 命令來啟用自動擴充封存，該使用者的主要信箱為內部部署，而且其封存信箱為雲端架構。</span><span class="sxs-lookup"><span data-stu-id="1ac48-148">In an Exchange hybrid deployment, you can't use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for a specific user whose primary mailbox is on-premises and whose archive mailbox is cloud-based.</span></span> <span data-ttu-id="1ac48-149">若要在 Exchange 混合式部署中為雲端式封存信箱啟用自動擴充封存，您必須在 Exchange Online PowerShell 中執行 **Set-OrganizationConfig AutoExpandingArchive** 命令，以啟用整個組織的自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-149">To enable auto-expanding archiving for cloud-based archive mailboxes in an Exchange hybrid deployment, you have to run the **Set-OrganizationConfig -AutoExpandingArchive** command in Exchange Online PowerShell to enable auto-expanding archiving for the entire organization.</span></span> <span data-ttu-id="1ac48-150">如果使用者的主要和封存信箱都是雲端架構，則可以使用 **Enable-Mailbox-AutoExpandingArchive** 命令來啟用該特定使用者的自動擴充封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-150">If a user's primary and archive mailboxes are both cloud-based, then you can use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for that specific user.</span></span>
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a><span data-ttu-id="1ac48-151">確認已啟用自動展開封存</span><span class="sxs-lookup"><span data-stu-id="1ac48-151">Verify that auto-expanding archiving is enabled</span></span>

<span data-ttu-id="1ac48-152">若要確認已為您的組織啟用自動展開封存，請在 Exchange Online PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="1ac48-152">To verify that auto-expanding archiving is enabled for your organization, run the following command in Exchange Online PowerShell.</span></span>

```powershell
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

<span data-ttu-id="1ac48-153">值表示為  `True` 組織啟用自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-153">A value of  `True` indicates that auto-expanding archiving is enabled for the organization.</span></span> 
  
<span data-ttu-id="1ac48-154">若要確認特定使用者已啟用自動展開封存，請在 Exchange Online PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="1ac48-154">To verify that auto-expanding archiving is enabled for a specific user, run the following command in Exchange Online PowerShell.</span></span>
  
```powershell
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```

<span data-ttu-id="1ac48-155">值  `True` 表示已為使用者啟用自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-155">A value of  `True` indicates that auto-expanding archiving is enabled for the user.</span></span>
  
<span data-ttu-id="1ac48-156">若要判斷是否已啟用非使用中信箱的自動展開封存，請在 Exchange Online PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="1ac48-156">To determine if auto-expanding archiving is enabled for inactive mailboxes, run the following command in Exchange Online PowerShell.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL UserPrincipalName,AutoExpandingArchiveEnabled
```

<span data-ttu-id="1ac48-157">值，  `True` 表示已啟用非使用中信箱的自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-157">A value of  `True` indicates that auto-expanding archiving is enabled for the inactive mailbox.</span></span> <span data-ttu-id="1ac48-158">值 `False` 表示未啟用自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-158">A value of `False` indicates that auto-expanding archiving isn't enabled.</span></span>

<span data-ttu-id="1ac48-159">啟用自動擴充封存後，請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="1ac48-159">Keep the following things in mind after you enable auto-expanding archiving:</span></span>
  
- <span data-ttu-id="1ac48-160">如果您執行 **Set-OrganizationConfig AutoExpandingArchive** 命令來啟用組織的自動擴充封存，您不需要在個別的信箱上執行 **Enable-Mailbox AutoExpandingArchive** 。</span><span class="sxs-lookup"><span data-stu-id="1ac48-160">If you run the **Set-OrganizationConfig -AutoExpandingArchive** command to enable auto-expanding archiving for your organization, you don't have to run the **Enable-Mailbox -AutoExpandingArchive** on individual mailboxes.</span></span> <span data-ttu-id="1ac48-161">執行 **Set-OrganizationConfig** Cmdlet 以啟用組織的自動展開封存時，不會將使用者信箱上的  *AutoExpandingArchiveEnabled*  屬性變更為 `True` 。</span><span class="sxs-lookup"><span data-stu-id="1ac48-161">Running the **Set-OrganizationConfig** cmdlet to enable auto-expanding archiving for your organization doesn't change the  *AutoExpandingArchiveEnabled*  property on user mailboxes to `True`.</span></span>

- <span data-ttu-id="1ac48-162">同樣地，當您啟用自動擴充封存功能時，  *ArchiveQuota*  和  *ArchiveWarningQuota*  信箱屬性的值不會變更。</span><span class="sxs-lookup"><span data-stu-id="1ac48-162">Similarly, the values for the  *ArchiveQuota*  and  *ArchiveWarningQuota*  mailbox properties aren't changed when you enable auto-expanding archiving.</span></span> <span data-ttu-id="1ac48-163">實際上，當您啟用使用者信箱的自動擴充封存，且  *AutoExpandingArchiveEnabled*  屬性設定為時  `True` ，會忽略  *ArchiveQuota*  和  *ArchiveWarningQuota*  屬性。</span><span class="sxs-lookup"><span data-stu-id="1ac48-163">In fact, when you enable auto-expanding archiving for a user mailbox and the  *AutoExpandingArchiveEnabled*  property is set to  `True`, the  *ArchiveQuota*  and  *ArchiveWarningQuota*  properties are ignored.</span></span> <span data-ttu-id="1ac48-164">以下是針對使用者信箱啟用自動擴充封存後，這些信箱屬性的範例。</span><span class="sxs-lookup"><span data-stu-id="1ac48-164">Here's an example of these mailbox properties after auto-expanding archiving is enabled for a user's mailbox.</span></span> 

    ![啟用自動擴充封存後，就會忽略 ArchiveQuota 和 ArchiveWarningQuota 屬性](../media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

## <a name="more-information"></a><span data-ttu-id="1ac48-166">其他資訊</span><span class="sxs-lookup"><span data-stu-id="1ac48-166">More information</span></span>

- <span data-ttu-id="1ac48-167">您也可以使用 PowerShell 來啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="1ac48-167">You can also use PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="1ac48-168">例如，您可以在 Exchange Online PowerShell 中執行下列命令，以啟用尚未啟用封存信箱之所有使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="1ac48-168">For example, you can run the following command in Exchange Online PowerShell to enable archive mailboxes for all users whose archive mailbox isn't already enabled.</span></span>

    ```powershell
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- <span data-ttu-id="1ac48-169">在您為組織或特定使用者開啟自動展開的封存後，封存信箱會在封存信箱 (包含 [可復原的專案] 資料夾時，轉換為自動展開封存) 達到 90 GB。</span><span class="sxs-lookup"><span data-stu-id="1ac48-169">After you turn on auto-expanding archiving for your organization or for a specific user, an archive mailbox is converted to an auto-expanding archive when the archive mailbox (including the Recoverable Items folder) reaches 90 GB.</span></span> <span data-ttu-id="1ac48-170">最多可能需要30天的時間，才能布建額外的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="1ac48-170">It can take up to 30 days for the additional storage space to be provisioned.</span></span>

- <span data-ttu-id="1ac48-171">當您開啟自動展開的封存功能之後，就無法將其關閉。</span><span class="sxs-lookup"><span data-stu-id="1ac48-171">After you turn on auto-expanding archiving, it can't be turned off.</span></span> <span data-ttu-id="1ac48-172">此外，管理員無法調整自動擴充封存的儲存配額。</span><span class="sxs-lookup"><span data-stu-id="1ac48-172">Additionally, administrators can't adjust the storage quota for auto-expanding archiving.</span></span>

- <span data-ttu-id="1ac48-173">在 Exchange 混合式部署中，針對具有內部部署主要信箱的使用者，支援自動擴充封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-173">Auto-expanding archiving is supported for cloud-based archive mailboxes in an Exchange hybrid deployment for users who have an on-premises primary mailbox.</span></span> <span data-ttu-id="1ac48-174">不過，啟用雲端式封存信箱的自動展開封存後，您就無法將封存信箱的信箱移回內部部署 Exchange 組織。</span><span class="sxs-lookup"><span data-stu-id="1ac48-174">However, after auto-expanding archiving is enabled for a cloud-based archive mailbox, you can't off-board that archive mailbox back to the on-premises Exchange organization.</span></span> <span data-ttu-id="1ac48-175">在任何版本的 Exchange Server 中，都不支援自動展開封存的內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="1ac48-175">Auto-expanding archiving isn't supported for on-premises mailboxes in any version of Exchange Server.</span></span>

- <span data-ttu-id="1ac48-176">如需使用者可用於存取其封存信箱中其他儲存區之專案的 Outlook 用戶端清單，請參閱 [無限制](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)封存的「outlook 要求存取自動擴充的封存中的專案」一節。</span><span class="sxs-lookup"><span data-stu-id="1ac48-176">For a list of Outlook clients that users can use to access items in the additional storage area in their archive mailbox, see the "Outlook requirements for accessing items in an auto-expanded archive" section in [Overview of unlimited archiving](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).</span></span>

- <span data-ttu-id="1ac48-177">如先前所述，當您執行 **Enable-Mailbox AutoExpandingArchive** 命令時，會將 10 GB 新增至使用者主要封存信箱的儲存配額 (及 [可復原的專案] 資料夾中) 。</span><span class="sxs-lookup"><span data-stu-id="1ac48-177">As previously explained, 10 GB is added to the storage quota of the user's primary archive mailbox (and to the Recoverable Items folder if the mailbox is on hold) when you run the **Enable-Mailbox -AutoExpandingArchive** command.</span></span> <span data-ttu-id="1ac48-178">這會提供額外的儲存空間，直到已布建自動擴充的儲存空間， (可能需要長達30天) 。</span><span class="sxs-lookup"><span data-stu-id="1ac48-178">This provides additional storage until the auto-expanded storage space is provisioned (which can take up to 30 days).</span></span> <span data-ttu-id="1ac48-179">當您執行 **Set-OrganizationConfig AutoExpandingArchive** 以啟用組織中所有信箱的自動擴充封存功能時，並不會新增此額外的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="1ac48-179">This additional storage space isn't added when you run the **Set-OrganizationConfig -AutoExpandingArchive** to enable auto-expanding archiving for all mailboxes in your organization.</span></span> <span data-ttu-id="1ac48-180">如果您已對整個組織啟用自動展開的封存，但需要為特定使用者新增額外的 10 GB 儲存空間，您可以在該信箱上執行 **Enable-Mailbox AutoExpandingArchive** 命令。</span><span class="sxs-lookup"><span data-stu-id="1ac48-180">If you enabled auto-expanding archiving for the entire organization, but need to add the additional 10 GB of storage space for a specific user, you can run the **Enable-Mailbox -AutoExpandingArchive** command on that mailbox.</span></span> <span data-ttu-id="1ac48-181">您會收到錯誤訊息，指出已經啟用自動擴充封存，但額外的儲存空間會新增至信箱。</span><span class="sxs-lookup"><span data-stu-id="1ac48-181">You will receive an error saying that auto-expanding archiving has already been enabled, but the additional storage space will be added to the mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ac48-182">[！注意] 只有針對個別使用者或共用信箱所用的信箱支援自動擴充封存，但其增長率並未超過每日 1 GB。</span><span class="sxs-lookup"><span data-stu-id="1ac48-182">Auto-expanding archiving is only supported for mailboxes used for individual users or shared mailboxes with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="1ac48-183">不允許使用日誌記錄、傳輸規則或自動轉寄規則，將郵件複製到封存信箱以進行封存。</span><span class="sxs-lookup"><span data-stu-id="1ac48-183">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox for the purposes of archiving is not permitted.</span></span> <span data-ttu-id="1ac48-184">使用者的封存信箱僅供該使用者使用。</span><span class="sxs-lookup"><span data-stu-id="1ac48-184">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="1ac48-185">Microsoft 保留在使用者的封存信箱用來儲存其他使用者的封存資料或其他不適當用途的情況下，拒絕無限封存的權利。</span><span class="sxs-lookup"><span data-stu-id="1ac48-185">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users or in other cases of inappropriate use.</span></span>