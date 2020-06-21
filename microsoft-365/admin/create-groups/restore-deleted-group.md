---
title: 還原已刪除的群組​​
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 瞭解如何還原已刪除的 Microsoft 365 群組。
ms.openlocfilehash: d7cf548816af1661298458f27c704d654845075d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818504"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="e2c40-103">還原已刪除的群組</span><span class="sxs-lookup"><span data-stu-id="e2c40-103">Restore a deleted Group</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e2c40-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="e2c40-104">The admin center is changing.</span></span> <span data-ttu-id="e2c40-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="e2c40-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="e2c40-106">如果您已刪除某個群組，它預設會保留30天。</span><span class="sxs-lookup"><span data-stu-id="e2c40-106">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="e2c40-107">這30天的期間會被視為「虛刪除」，因為您仍然可以還原群組。</span><span class="sxs-lookup"><span data-stu-id="e2c40-107">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="e2c40-108">30天后，就會永久刪除群組及其相關聯的內容，而且無法還原。</span><span class="sxs-lookup"><span data-stu-id="e2c40-108">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="e2c40-109">還原群組時，將會還原下列內容：</span><span class="sxs-lookup"><span data-stu-id="e2c40-109">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="e2c40-110">Azure Active Directory （AD） Microsoft 365 群組物件、屬性和成員。</span><span class="sxs-lookup"><span data-stu-id="e2c40-110">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="e2c40-111">群組的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e2c40-111">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="e2c40-112">Exchange Online 共用收件匣和行事曆。</span><span class="sxs-lookup"><span data-stu-id="e2c40-112">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="e2c40-113">SharePoint 線上小組網站和檔案。</span><span class="sxs-lookup"><span data-stu-id="e2c40-113">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="e2c40-114">OneNote 筆記本</span><span class="sxs-lookup"><span data-stu-id="e2c40-114">OneNote notebook</span></span>
    
- <span data-ttu-id="e2c40-115">Planner</span><span class="sxs-lookup"><span data-stu-id="e2c40-115">Planner</span></span>
    
- <span data-ttu-id="e2c40-116">Teams</span><span class="sxs-lookup"><span data-stu-id="e2c40-116">Teams</span></span>

- <span data-ttu-id="e2c40-117">Yammer 群組和群組內容（如果 Microsoft 365 群組是由 Yammer 建立）</span><span class="sxs-lookup"><span data-stu-id="e2c40-117">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a><span data-ttu-id="e2c40-118">使用 Outlook 網頁版還原您擁有的群組</span><span class="sxs-lookup"><span data-stu-id="e2c40-118">Restore a group that you own by using Outlook on the web</span></span>

<span data-ttu-id="e2c40-119">如果您是 Microsoft 365 群組的擁有者，您可以遵循下列步驟，在網頁版 Outlook 中還原群組：</span><span class="sxs-lookup"><span data-stu-id="e2c40-119">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="e2c40-120">在 [[刪除的群組] 頁面](https://outlook.office.com/people/group/deleted)上，選取 [**群組**] 節點底下的 [**管理群組**] 選項，然後選擇 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="e2c40-120">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="e2c40-121">按一下您要還原之群組旁的 [**還原**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e2c40-121">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="e2c40-122">若已刪除的群組未出現在這裡，請與系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="e2c40-122">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="e2c40-123">在 Microsoft 365 系統管理中心中還原群組</span><span class="sxs-lookup"><span data-stu-id="e2c40-123">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="e2c40-124">如果您是全域系統管理員或群組管理員，您可以在 Microsoft 365 系統管理中心還原刪除的群組：</span><span class="sxs-lookup"><span data-stu-id="e2c40-124">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="e2c40-125">移至系統[管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="e2c40-125">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="e2c40-126">展開 [**群組**]，然後按一下 [**刪除的群組**]。</span><span class="sxs-lookup"><span data-stu-id="e2c40-126">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="e2c40-127">選取您要還原的群組，然後按一下 [**還原群組**]。</span><span class="sxs-lookup"><span data-stu-id="e2c40-127">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="e2c40-128">在某些情況下，您可能需要24小時的時間才能還原群組及其所有資料。</span><span class="sxs-lookup"><span data-stu-id="e2c40-128">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="e2c40-129">永久刪除 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="e2c40-129">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="e2c40-130">在某些情況下，您可能想要永久清除群組，而不需等待30天的虛刪除期限到期。</span><span class="sxs-lookup"><span data-stu-id="e2c40-130">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="e2c40-131">若要這麼做，請啟動 PowerShell 並執行下列命令以取得該群組的物件識別碼：</span><span class="sxs-lookup"><span data-stu-id="e2c40-131">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="e2c40-132">記下您要永久刪除之群組或群組的物件識別碼。</span><span class="sxs-lookup"><span data-stu-id="e2c40-132">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e2c40-133">永久移除群組及其資料來清除該群組。</span><span class="sxs-lookup"><span data-stu-id="e2c40-133">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="e2c40-134">若要清除該群組，請在 PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e2c40-134">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="e2c40-135">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups.</span><span class="sxs-lookup"><span data-stu-id="e2c40-135">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups.</span></span> <span data-ttu-id="e2c40-136">In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span><span class="sxs-lookup"><span data-stu-id="e2c40-136">In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="e2c40-137">有關于 Microsoft 365 群組的問題嗎？</span><span class="sxs-lookup"><span data-stu-id="e2c40-137">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="e2c40-138">流覽[Microsoft 技術社區](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups)以張貼問題，並參與 microsoft 365 群組的交談。</span><span class="sxs-lookup"><span data-stu-id="e2c40-138">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="e2c40-139">相關文章</span><span class="sxs-lookup"><span data-stu-id="e2c40-139">Related articles</span></span>

[<span data-ttu-id="e2c40-140">使用 PowerShell 管理 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="e2c40-140">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)
  
[<span data-ttu-id="e2c40-141">使用 Remove-UnifiedGroup Cmdlet 來刪除群組</span><span class="sxs-lookup"><span data-stu-id="e2c40-141">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
<span data-ttu-id="e2c40-142">[管理連接群組的小組網站設定](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="e2c40-142">[Manage your group-connected team site settings](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)</span></span>
  
<span data-ttu-id="e2c40-143">[在 Outlook 中刪除群組](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="e2c40-143">[Delete a group in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)</span></span>
