---
title: 在 Office 365 + 管理员帮助中启用无限制存档
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
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
description: 对于管理员：了解如何在 Office 365 中启用自动扩展存档，该存档为用户提供了 Exchange 联机邮箱的无限存储空间。 您可以为整个组织或仅针对特定用户启用自动扩展存档。
ms.openlocfilehash: b140cf9bed811c5af2de2e5441bd3c296ed7effe
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077096"
---
# <a name="enable-unlimited-archiving-in-office-365--admin-help"></a><span data-ttu-id="b3a78-104">在 Office 365 + 管理员帮助中启用无限制存档</span><span class="sxs-lookup"><span data-stu-id="b3a78-104">Enable unlimited archiving in Office 365 — Admin Help</span></span>

<span data-ttu-id="b3a78-105">您可以使用 Office 365 中的 Exchange Online 自动扩展存档功能为存档邮箱启用无限的存储空间。</span><span class="sxs-lookup"><span data-stu-id="b3a78-105">You can use the Exchange Online auto-expanding archiving feature in Office 365 to enable unlimited storage space for archive mailboxes.</span></span> <span data-ttu-id="b3a78-106">启用自动展开存档时，当用户接近存储限制时，会自动向用户存档邮箱添加额外的存储空间。</span><span class="sxs-lookup"><span data-stu-id="b3a78-106">When auto-expanding archiving is turned on, additional storage space is automatically added to a user's archive mailbox when it approaches the storage limit.</span></span> <span data-ttu-id="b3a78-107">结果是邮箱存储容量不受限制。</span><span class="sxs-lookup"><span data-stu-id="b3a78-107">The result is unlimited mailbox storage capacity.</span></span> <span data-ttu-id="b3a78-108">您可以为组织中的每个人或仅针对特定用户打开自动展开存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-108">You can turn on auto-expanding archiving for everyone in your organization or just for specific users.</span></span> <span data-ttu-id="b3a78-109">有关自动扩展存档的详细信息，请参阅[Office 365 中无限制存档概述。](unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="b3a78-109">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b3a78-110">開始之前</span><span class="sxs-lookup"><span data-stu-id="b3a78-110">Before you begin</span></span>

- <span data-ttu-id="b3a78-111">您必须是 Office 365 组织中的全局管理员或 Exchange Online 组织中的组织管理角色组的成员，才能为整个组织或特定用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-111">You have to be a global administrator in your Office 365 organization or a member of the Organization Management role group in your Exchange Online organization to enable auto-expanding archiving for your entire organization or for specific users.</span></span> <span data-ttu-id="b3a78-112">或者，您必须是分配了"邮件收件人"角色的角色组的成员，才能为特定用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-112">Alternately, you have to be a member of a role group that's assigned the Mail Recipients role to enable auto-expanding archiving for specific users.</span></span>
    
- <span data-ttu-id="b3a78-113">在启用自动展开存档之前，必须启用用户的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="b3a78-113">A user's archive mailbox has to be enabled before you can enable auto-expanding archiving.</span></span> <span data-ttu-id="b3a78-114">必须为用户分配 Exchange 联机计划 2 许可证才能启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="b3a78-114">A user must be assigned an Exchange Online Plan 2 license to enable the archive mailbox.</span></span> <span data-ttu-id="b3a78-115">如果为用户分配了 Exchange 联机计划 1 许可证，则必须为其分配单独的 Exchange 联机存档许可证才能启用其存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="b3a78-115">If a user is assigned an Exchange Online Plan 1 license, you would have to assign them a separate Exchange Online Archiving license to enable their archive mailbox.</span></span> <span data-ttu-id="b3a78-116">请参阅[在"安全&合规性中心中启用存档邮箱"。](enable-archive-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="b3a78-116">See [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md).</span></span>
    
- <span data-ttu-id="b3a78-117">您还可以使用 PowerShell 启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="b3a78-117">You can also use PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="b3a78-118">有关 PowerShell 命令的示例，请参阅"[详细信息"](#more-information)部分，可用于为组织中的所有用户启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="b3a78-118">See the [More information](#more-information) section for an example of the PowerShell command that you can use to enable archive mailboxes for all users in your organization.</span></span> 
    
- <span data-ttu-id="b3a78-119">自動展開封存也支援共用信箱。</span><span class="sxs-lookup"><span data-stu-id="b3a78-119">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="b3a78-120">要启用共享邮箱的存档，需要使用 Exchange 联机存档许可证的 Exchange 联机计划 2 许可证或 Exchange 联机计划 1 许可证。</span><span class="sxs-lookup"><span data-stu-id="b3a78-120">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>
    
- <span data-ttu-id="b3a78-121">不能使用 Exchange 管理中心或安全&合规性中心启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-121">You can't use the Exchange admin center or the Security & Compliance Center to enable auto-expanding archiving.</span></span> <span data-ttu-id="b3a78-122">您必须使用 Exchange 在线电源外壳。</span><span class="sxs-lookup"><span data-stu-id="b3a78-122">You have to use Exchange Online PowerShell.</span></span> <span data-ttu-id="b3a78-123">要使用远程 PowerShell 连接到 Exchange 在线组织，请参阅[连接到 Exchange 在线 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="b3a78-123">To connect to your Exchange Online organization using remote PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a><span data-ttu-id="b3a78-124">为整个组织启用自动扩展存档</span><span class="sxs-lookup"><span data-stu-id="b3a78-124">Enable auto-expanding archiving for your entire organization</span></span>

<span data-ttu-id="b3a78-125">您可以为整个组织启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-125">You can enable auto-expanding archiving for your entire organization.</span></span> <span data-ttu-id="b3a78-126">启用后，将启用对现有用户邮箱和已创建的新用户邮箱的自动展开存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-126">After you turn it on, auto-expanding archiving will be enabled for existing user mailboxes and for new user mailboxes that are created.</span></span> <span data-ttu-id="b3a78-127">创建用户邮箱时，请确保启用用户的主存档邮箱，以便自动展开存档功能适用于新用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="b3a78-127">When you create user mailboxes, be sure to enable the user's main archive mailbox so the auto-expanding archiving feature works for the new user mailbox.</span></span>
  
1. [<span data-ttu-id="b3a78-128">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3a78-128">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="b3a78-129">在 Exchange 在线 PowerShell 中运行以下命令，为整个组织启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-129">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for your entire organization.</span></span>

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a><span data-ttu-id="b3a78-130">为特定用户启用自动扩展存档</span><span class="sxs-lookup"><span data-stu-id="b3a78-130">Enable auto-expanding archiving for specific users</span></span>

<span data-ttu-id="b3a78-131">您可以只为特定用户启用自动扩展存档，而不是为组织中的每个用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-131">Instead of enabling auto-expanding archiving for every user in your organization, you can enable it only for specific users.</span></span> <span data-ttu-id="b3a78-132">可以执行此操作，因为只有某些用户可能需要较大的存档存储容量。</span><span class="sxs-lookup"><span data-stu-id="b3a78-132">You might do this because only some users might have a need for a large archive storage capacity.</span></span>
  
<span data-ttu-id="b3a78-133">当您为特定用户启用自动展开存档，并且用户邮箱处于保留状态或分配给 Office 365 保留策略时，将进行以下两个配置更改：</span><span class="sxs-lookup"><span data-stu-id="b3a78-133">When you enable auto-expanding archiving for a specific user and the user's mailbox in on hold or assigned to an Office 365 retention policy, the following two configurations changes are made:</span></span>
  
- <span data-ttu-id="b3a78-134">用户主存档邮箱的存储配额增加 10 GB（从 100 GB 增加到 110 GB）。</span><span class="sxs-lookup"><span data-stu-id="b3a78-134">The storage quota for the user's primary archive mailbox is increased by 10 GB (from 100 GB to 110 GB).</span></span> <span data-ttu-id="b3a78-135">存档警告配额也增加了 10 GB（从 90 GB 增加到 100 GB）。</span><span class="sxs-lookup"><span data-stu-id="b3a78-135">The archive warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span>
    
- <span data-ttu-id="b3a78-136">用户主邮箱中的"可恢复项目"文件夹的存储配额将增加 10 GB（也从 100 GB 增加到 110 GB）。</span><span class="sxs-lookup"><span data-stu-id="b3a78-136">The storage quota for the Recoverable Items folder in the user's primary mailbox is increased by 10 GB (also from 100 GB to 110 GB).</span></span> <span data-ttu-id="b3a78-137">可恢复项目警告配额也增加了 10 GB（从 90 GB 增加到 100 GB）。</span><span class="sxs-lookup"><span data-stu-id="b3a78-137">The Recoverable Items warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span> <span data-ttu-id="b3a78-138">仅当处于保留状态或分配给 Office 365 保留策略的邮箱时，这些更改才适用。</span><span class="sxs-lookup"><span data-stu-id="b3a78-138">These changes are applicable only if the mailbox in on hold or assigned to an Office 365 retention policy.</span></span>
    
<span data-ttu-id="b3a78-139">添加此额外空间是为了防止在预配自动扩展存档之前可能出现的任何存储问题。</span><span class="sxs-lookup"><span data-stu-id="b3a78-139">This additional space is added to prevent any storage issues that may occur before the auto-expanding archive is provisioned.</span></span> <span data-ttu-id="b3a78-140">如上一节所述，在为整个组织启用自动扩展存档时，*不会*添加额外的存储空间。</span><span class="sxs-lookup"><span data-stu-id="b3a78-140">Additional storage space  *is not*  added when you enable auto-expanding archiving for your entire organization, as described in the previous section.</span></span> 
  
1. [<span data-ttu-id="b3a78-141">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3a78-141">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="b3a78-142">在 Exchange 在线 PowerShell 中运行以下命令，为特定用户启用自动展开存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-142">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for a specific user.</span></span> <span data-ttu-id="b3a78-143">如前所述，必须先启用用户的存档邮箱（主存档），然后才能为该用户启用自动展开存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-143">As previously explained, the user's archive mailbox (main archive) must be enabled before you can turn on auto-expanding archiving for that user.</span></span>
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> <span data-ttu-id="b3a78-144">在 Exchange 混合部署中，不能**使用"启用-邮箱 - 自动扩展存档"** 命令为主邮箱位于本地且其存档邮箱基于云的特定用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-144">In an Exchange hybrid deployment, you can't use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for specific a user whose primary mailbox is on premises and their archive mailbox is cloud-based.</span></span> <span data-ttu-id="b3a78-145">要在 Exchange 混合部署中启用基于云的存档邮箱的自动扩展存档，您必须在 Exchange 在线 PowerShell 中**运行"设置组织- 自动扩展存档"** 命令，以便自动扩展存档整个组织。</span><span class="sxs-lookup"><span data-stu-id="b3a78-145">To enable auto-expanding archiving for cloud-based archive mailboxes in an Exchange hybrid deployment, you have to run the **Set-OrganizationConfig -AutoExpandingArchive** command in Exchange Online PowerShell to enable auto-expanding archiving for the entire organization.</span></span> <span data-ttu-id="b3a78-146">如果用户的主邮箱和存档邮箱都是基于云的，**则可以使用"启用邮箱-自动扩展存档"** 命令为该特定用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-146">If a user's primary and archive mailboxes are both cloud-based, then you can use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for that specific user.</span></span> 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a><span data-ttu-id="b3a78-147">验证是否启用了自动展开存档</span><span class="sxs-lookup"><span data-stu-id="b3a78-147">Verify that auto-expanding archiving is enabled</span></span>

<span data-ttu-id="b3a78-148">要验证是否为您的组织启用了自动扩展存档，请运行 Exchange 联机 PowerShell 中的以下命令。</span><span class="sxs-lookup"><span data-stu-id="b3a78-148">To verify that auto-expanding archiving is enabled for your organization, run the following command in Exchange Online PowerShell.</span></span>

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

<span data-ttu-id="b3a78-149">的值`True`指示为组织启用了自动展开存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-149">A value of  `True` indicates that auto-expanding archiving is enabled for the organization.</span></span> 
  
<span data-ttu-id="b3a78-150">要验证是否为特定用户启用了自动展开存档，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="b3a78-150">To verify that auto-expanding archiving is enabledd for a specific user, run the following command in Exchange Online PowerShell.</span></span>
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
<span data-ttu-id="b3a78-151">的值`True`指示已为用户启用了自动展开存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-151">A value of  `True` indicates that auto-expanding archiving is enabled for the user.</span></span> 
  
<span data-ttu-id="b3a78-152">启用自动扩展存档后，请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="b3a78-152">Keep the following things in mind after you enable auto-expanding archiving:</span></span>
  
- <span data-ttu-id="b3a78-153">如果**运行"设置组织Config-自动扩展存档"** 命令为您的组织启用自动扩展存档，则不必在单个邮箱上运行**启用-邮箱 -自动扩展存档。**</span><span class="sxs-lookup"><span data-stu-id="b3a78-153">If you run the **Set-OrganizationConfig -AutoExpandingArchive** command to enable auto-expanding archiving for your organization, you don't have to run the **Enable-Mailbox -AutoExpandingArchive** on individual mailboxes.</span></span> <span data-ttu-id="b3a78-154">运行"**设置组织Config** cmdlet"以为组织启用自动展开存档不会将用户邮箱*上的"自动展开存档启用"* 属性更改为`True`。</span><span class="sxs-lookup"><span data-stu-id="b3a78-154">Running the **Set-OrganizationConfig** cmdlet to enable auto-expanding archiving for your organization doesn't change the  *AutoExpandingArchiveEnabled*  property on user mailboxes to  `True`.</span></span>
    
- <span data-ttu-id="b3a78-155">同样，启用自动展开存档时，*存档配额*和*存档警告配额*邮箱属性的值不会更改。</span><span class="sxs-lookup"><span data-stu-id="b3a78-155">Similarly, the values for the  *ArchiveQuota*  and  *ArchiveWarningQuota*  mailbox properties aren't changed when you enable auto-expanding archiving.</span></span> <span data-ttu-id="b3a78-156">实际上，当您为用户邮箱启用自动展开存档，并且*自动展开存档启用*的属性设置为`True`时，将忽略*存档配额*和*存档警告配额*属性。</span><span class="sxs-lookup"><span data-stu-id="b3a78-156">In fact, when you enable auto-expanding archiving for a user mailbox and the  *AutoExpandingArchiveEnabled*  property is set to  `True`, the  *ArchiveQuota*  and  *ArchiveWarningQuota*  properties are ignored.</span></span> <span data-ttu-id="b3a78-157">下面是为用户邮箱启用自动展开存档后这些邮箱属性的示例。</span><span class="sxs-lookup"><span data-stu-id="b3a78-157">Here's an example of these mailbox properties after auto-expanding archiving is enabled for a user's mailbox.</span></span> 
    
    ![启用自动展开存档后，将忽略存档配额和存档警告配额属性](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a><span data-ttu-id="b3a78-159">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b3a78-159">More information</span></span>

- <span data-ttu-id="b3a78-160">您还可以使用 PowerShell 启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="b3a78-160">You can also use PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="b3a78-161">例如，您可以在 Exchange Online PowerShell 中运行以下命令，为尚未启用存档邮箱的所有用户启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="b3a78-161">For example, you can run the following command in Exchange Online PowerShell to enable archive mailboxes for all users whose archive mailbox isn't already enabled.</span></span>

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- <span data-ttu-id="b3a78-162">为组织或特定用户打开自动展开存档后，当存档邮箱（包括可恢复项目文件夹）达到 90 GB 时，存档邮箱将转换为自动展开的存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-162">After you turn on auto-expanding archiving for your organization or for a specific user, an archive mailbox is converted to an auto-expanding archive when the archive mailbox (including the Recoverable Items folder) reaches 90 GB.</span></span> <span data-ttu-id="b3a78-163">预配额外的存储空间最多可能需要 30 天。</span><span class="sxs-lookup"><span data-stu-id="b3a78-163">It can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
- <span data-ttu-id="b3a78-164">打开自动展开存档后，无法将其关闭。</span><span class="sxs-lookup"><span data-stu-id="b3a78-164">After you turn on auto-expanding archiving, it can't be turned off.</span></span>
    
- <span data-ttu-id="b3a78-165">Exchange 混合部署中为具有本地主邮箱的用户支持基于云的存档邮箱的自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-165">Auto-expanding archiving is supported for cloud-based archive mailboxes in an Exchange hybrid deployment for users who have an on-premises primary mailbox.</span></span> <span data-ttu-id="b3a78-166">但是，在为基于云的存档邮箱启用自动扩展存档后，无法将该存档邮箱从板外重新归档回本地 Exchange 组织。</span><span class="sxs-lookup"><span data-stu-id="b3a78-166">However, after auto-expanding archiving is enabled for a cloud-based archive mailbox, you can't off-board that archive mailbox back to the on-premises Exchange organization.</span></span> <span data-ttu-id="b3a78-167">Exchange Server 2010 中的本地邮箱不支持自动展开存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-167">Auto-expanding archiving isn't supported for on-premises mailboxes in Exchange Server 2010.</span></span>
    
- <span data-ttu-id="b3a78-168">有关用户可以用于访问其存档邮箱中其他存储区域中的项目的 Outlook 客户端列表，请参阅[Office 365 中无限制存档概述](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)中的"访问自动扩展存档中项目的 Outlook 要求"部分.</span><span class="sxs-lookup"><span data-stu-id="b3a78-168">For a list of Outlook clients that users can use to access items in the additional storage area in their archive mailbox, see the "Outlook requirements for accessing items in an auto-expanded archive" section in [Overview of unlimited archiving in Office 365](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).</span></span>
    
- <span data-ttu-id="b3a78-169">如前所述，在运行**启用邮箱 - 自动展开存档**命令时，将 10 GB 添加到用户主存档邮箱的存储配额（如果邮箱处于保留状态，则添加到可恢复项目文件夹）。</span><span class="sxs-lookup"><span data-stu-id="b3a78-169">As previously explained, 10 GB is added to the storage quota of the user's primary archive mailbox (and to the Recoverable Items folder if the mailbox is on hold) when you run the **Enable-Mailbox -AutoExpandingArchive** command.</span></span> <span data-ttu-id="b3a78-170">这将提供额外的存储空间，直到预配自动扩展的存储空间（最多可能需要 30 天）。</span><span class="sxs-lookup"><span data-stu-id="b3a78-170">This provides additional storage until the auto-expanded storage space is provisioned (which can take up to 30 days).</span></span> <span data-ttu-id="b3a78-171">**运行"设置组织Config-自动扩展存档"** 以启用组织内所有邮箱的自动扩展存档时，不会添加此额外的存储空间。</span><span class="sxs-lookup"><span data-stu-id="b3a78-171">This additional storage space isn't added when you run the **Set-OrganizationConfig -AutoExpandingArchive** to enable auto-expanding archiving for all mailboxes in your organization.</span></span> <span data-ttu-id="b3a78-172">如果为整个组织启用了自动扩展存档，但需要为特定用户添加额外的 10 GB 存储空间，则可以在该邮箱上运行**启用邮箱 -自动展开存档**命令。</span><span class="sxs-lookup"><span data-stu-id="b3a78-172">If you enabled auto-expanding archiving for the entire organization, but need to add the additional 10 GB of storage space for a specific user, you can run the **Enable-Mailbox -AutoExpandingArchive** command on that mailbox.</span></span> <span data-ttu-id="b3a78-173">您将收到一个错误，指出已启用自动展开存档，但额外的存储空间将添加到邮箱中。</span><span class="sxs-lookup"><span data-stu-id="b3a78-173">You will receive an error saying that auto-expanding archiving has already been enabled, but the additional storage space will be added to the mailbox.</span></span> 

- <span data-ttu-id="b3a78-174">系統管理員無法調整儲存空間配額。</span><span class="sxs-lookup"><span data-stu-id="b3a78-174">Administrators can't adjust the storage quota.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3a78-175">自动展开存档仅支持用于单个用户或共享邮箱的邮箱，其增长率每天不超过 1 GB。</span><span class="sxs-lookup"><span data-stu-id="b3a78-175">Auto-expanding archiving is only supported for mailboxes used for individual users or shared mailboxes with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="b3a78-176">不允许使用日记、传输规则或自动转发规则将邮件复制到存档邮箱以进行存档。</span><span class="sxs-lookup"><span data-stu-id="b3a78-176">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox for the purposes of archiving is not permitted.</span></span> <span data-ttu-id="b3a78-177">使用者的封存信箱僅供該使用者使用。</span><span class="sxs-lookup"><span data-stu-id="b3a78-177">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="b3a78-178">Microsoft 保留在使用者封存信箱中用來儲存其他使用者之封存資料的執行個體中拒絕不受限封存的權限。</span><span class="sxs-lookup"><span data-stu-id="b3a78-178">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users.</span></span>
