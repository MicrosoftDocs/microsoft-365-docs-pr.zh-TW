---
title: 還原已刪除的 Office 365 群組
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 瞭解如何還原已刪除的 Office 365 群組。
ms.openlocfilehash: 31d6481f87d7da219e042eefa8f004425caee133
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583160"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="44d43-103">還原刪除的 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="44d43-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="44d43-104">如果您已刪除某個群組，它預設會保留30天。</span><span class="sxs-lookup"><span data-stu-id="44d43-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="44d43-105">這30天的期間會被視為「虛刪除」，因為您仍然可以還原群組。</span><span class="sxs-lookup"><span data-stu-id="44d43-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="44d43-106">30天后，就會永久刪除群組及其相關聯的內容，而且無法還原。</span><span class="sxs-lookup"><span data-stu-id="44d43-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="44d43-107">還原群組時，將會還原下列內容：</span><span class="sxs-lookup"><span data-stu-id="44d43-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="44d43-108">Azure Active Directory （AD） Office 365 群組物件、屬性和成員。</span><span class="sxs-lookup"><span data-stu-id="44d43-108">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="44d43-109">群組的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="44d43-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="44d43-110">Exchange Online 共用收件匣和行事曆。</span><span class="sxs-lookup"><span data-stu-id="44d43-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="44d43-111">SharePoint 線上小組網站和檔案。</span><span class="sxs-lookup"><span data-stu-id="44d43-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="44d43-112">OneNote 筆記本</span><span class="sxs-lookup"><span data-stu-id="44d43-112">OneNote notebook</span></span>
    
- <span data-ttu-id="44d43-113">Planner</span><span class="sxs-lookup"><span data-stu-id="44d43-113">Planner</span></span>
    
- <span data-ttu-id="44d43-114">Teams</span><span class="sxs-lookup"><span data-stu-id="44d43-114">Teams</span></span>

- <span data-ttu-id="44d43-115">Yammer 群組和群組內容（如果 Office 365 群組是由 Yammer 建立）</span><span class="sxs-lookup"><span data-stu-id="44d43-115">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook"></a><span data-ttu-id="44d43-116">使用 Outlook 還原您擁有的群組</span><span class="sxs-lookup"><span data-stu-id="44d43-116">Restore a group that you own by using Outlook</span></span>

<span data-ttu-id="44d43-117">如果您是 Office 365 群組的擁有者，您可以遵循下列步驟，自行在 Outlook 中還原群組：</span><span class="sxs-lookup"><span data-stu-id="44d43-117">If you are the owner of an Office 365 group, you can restore the group yourself in Outlook by following these steps:</span></span>

1. <span data-ttu-id="44d43-118">在 [[刪除的群組] 頁面](https://outlook.office.com/people/group/deleted)上，選取 [**群組**] 節點底下的 [**管理群組**] 選項，然後選擇 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="44d43-118">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="44d43-119">按一下您要還原之群組旁的 [**還原**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="44d43-119">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="44d43-120">若已刪除的群組未出現在這裡，請與系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="44d43-120">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="44d43-121">在 Microsoft 365 系統管理中心中還原群組</span><span class="sxs-lookup"><span data-stu-id="44d43-121">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="44d43-122">如果您是全域系統管理員或群組管理員，則可在 Microsoft 365 系統管理中心還原刪除的群組：</span><span class="sxs-lookup"><span data-stu-id="44d43-122">If you are a global administrator or a groups admin, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="44d43-123">移至位於 [https://admin.microsoft.com](Go to the admin center at https://admin.microsoft.com) 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="44d43-123">Go to the admin center at [https://admin.microsoft.com](Go to the admin center at https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="44d43-124">展開 [**群組**]，然後按一下 [**刪除的群組**]。</span><span class="sxs-lookup"><span data-stu-id="44d43-124">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="44d43-125">選取您要還原的群組，然後按一下 [**還原群組**]。</span><span class="sxs-lookup"><span data-stu-id="44d43-125">Select the group that you want to restore, and then click **Restore group**.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="44d43-126">永久刪除 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="44d43-126">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="44d43-127">在某些情況下，您可能想要永久清除群組，而不需等待30天的虛刪除期限到期。</span><span class="sxs-lookup"><span data-stu-id="44d43-127">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="44d43-128">若要這麼做，請啟動 PowerShell 並執行下列命令以取得該群組的物件識別碼：</span><span class="sxs-lookup"><span data-stu-id="44d43-128">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="44d43-129">記下您要永久刪除之群組或群組的物件識別碼。</span><span class="sxs-lookup"><span data-stu-id="44d43-129">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="44d43-130">永久移除群組及其資料來清除該群組。</span><span class="sxs-lookup"><span data-stu-id="44d43-130">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="44d43-131">若要清除該群組，請在 PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="44d43-131">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="44d43-p103">若要確認群組已成功清除，請再次執行  *Get-AzureADMSDeletedGroup*  Cmdlet 來確認該群組已不再顯示在虛刪除群組清單中。某些情況下，最多可能需要 24 小時才能永久刪除群組及其所有資料。</span><span class="sxs-lookup"><span data-stu-id="44d43-p103">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="44d43-134">有任何關於 Office 365 群組的問題嗎？</span><span class="sxs-lookup"><span data-stu-id="44d43-134">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="44d43-135">流覽[Microsoft 技術社區](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups)以張貼問題，並參與 Office 365 群組的交談。</span><span class="sxs-lookup"><span data-stu-id="44d43-135">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="44d43-136">相關文章</span><span class="sxs-lookup"><span data-stu-id="44d43-136">Related articles</span></span>

[<span data-ttu-id="44d43-137">使用 PowerShell 管理 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="44d43-137">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="44d43-138">使用 Remove-UnifiedGroup Cmdlet 來刪除群組</span><span class="sxs-lookup"><span data-stu-id="44d43-138">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
<span data-ttu-id="44d43-139">[管理連接群組的小組網站設定](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="44d43-139">[Manage your group-connected team site settings](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)</span></span>
  
<span data-ttu-id="44d43-140">[在 Outlook 中刪除群組](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="44d43-140">[Delete a group in Outlook](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)</span></span>
