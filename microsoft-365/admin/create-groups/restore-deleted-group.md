---
title: 還原已刪除的 Microsoft 365 群組
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: 已刪除的群組會保留30天，您仍可還原此群組。 30天后，就會永久刪除群組及其內容。
ms.openlocfilehash: 2c20c2bd3ce91331e7160132047dbf3ecd79c4b8
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635735"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="6b695-104">還原已刪除的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="6b695-104">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="6b695-105">如果您已刪除某個群組，它預設會保留30天。</span><span class="sxs-lookup"><span data-stu-id="6b695-105">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="6b695-106">這30天的期間會被視為「虛刪除」，因為您仍然可以還原群組。</span><span class="sxs-lookup"><span data-stu-id="6b695-106">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="6b695-107">30天后，就會永久刪除群組及其相關聯的內容，而且無法還原。</span><span class="sxs-lookup"><span data-stu-id="6b695-107">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="6b695-108">還原群組時，將會還原下列內容：</span><span class="sxs-lookup"><span data-stu-id="6b695-108">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="6b695-109">Azure Active Directory (AD) Microsoft 365 Groups 物件、屬性和成員。</span><span class="sxs-lookup"><span data-stu-id="6b695-109">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="6b695-110">群組的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6b695-110">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="6b695-111">Exchange Online 共用收件匣和行事曆。</span><span class="sxs-lookup"><span data-stu-id="6b695-111">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="6b695-112">SharePoint線上小組網站和檔案。</span><span class="sxs-lookup"><span data-stu-id="6b695-112">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="6b695-113">OneNote 筆記本</span><span class="sxs-lookup"><span data-stu-id="6b695-113">OneNote notebook</span></span>
    
- <span data-ttu-id="6b695-114">Planner</span><span class="sxs-lookup"><span data-stu-id="6b695-114">Planner</span></span>
    
- <span data-ttu-id="6b695-115">Teams</span><span class="sxs-lookup"><span data-stu-id="6b695-115">Teams</span></span>

- <span data-ttu-id="6b695-116">Yammer 群組和群組內容 (如果 Microsoft 365 群組是從 Yammer 建立的) </span><span class="sxs-lookup"><span data-stu-id="6b695-116">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="6b695-117">本文說明只還原 Microsoft 365 的群組。</span><span class="sxs-lookup"><span data-stu-id="6b695-117">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="6b695-118">所有其他群組一經刪除，便無法還原。</span><span class="sxs-lookup"><span data-stu-id="6b695-118">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="6b695-119">還原群組</span><span class="sxs-lookup"><span data-stu-id="6b695-119">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="6b695-120">Outlook</span><span class="sxs-lookup"><span data-stu-id="6b695-120">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="6b695-121">如果您是 Microsoft 365 群組的擁有者，您可以遵循下列步驟，在網頁上 Outlook 中，自行還原群組：</span><span class="sxs-lookup"><span data-stu-id="6b695-121">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="6b695-122">在 [[刪除的群組] 頁面](https://outlook.office.com/people/group/deleted)上，選取 [**群組**] 節點底下的 [**管理群組**] 選項，然後選擇 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="6b695-122">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="6b695-123">按一下您要還原之群組旁的 [ **還原** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6b695-123">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="6b695-124">若已刪除的群組未出現在這裡，請與系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="6b695-124">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="6b695-125">系統管理中心</span><span class="sxs-lookup"><span data-stu-id="6b695-125">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="6b695-126">如果您是全域系統管理員或群組管理員，您可以在 Microsoft 365 系統管理中心還原已刪除的群組：</span><span class="sxs-lookup"><span data-stu-id="6b695-126">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="6b695-127">移至 [[系統管理中心]](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="6b695-127">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="6b695-128">展開 [ **群組**]，然後按一下 [ **刪除的群組**]。</span><span class="sxs-lookup"><span data-stu-id="6b695-128">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="6b695-129">選取您要還原的群組，然後按一下 [ **還原群組**]。</span><span class="sxs-lookup"><span data-stu-id="6b695-129">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="6b695-130">在某些情況下，您可能需要24小時的時間才能還原群組及其所有資料。</span><span class="sxs-lookup"><span data-stu-id="6b695-130">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="6b695-131">有 Microsoft 365 群組的相關問題嗎？</span><span class="sxs-lookup"><span data-stu-id="6b695-131">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="6b695-132">流覽[Microsoft 技術 Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups)以張貼問題，並參與有關 Microsoft 365 群組的交談。</span><span class="sxs-lookup"><span data-stu-id="6b695-132">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="6b695-133">相關內容</span><span class="sxs-lookup"><span data-stu-id="6b695-133">Related content</span></span>

<span data-ttu-id="6b695-134">[使用 PowerShell (文章管理 Microsoft 365 群組](../../enterprise/manage-microsoft-365-groups-with-powershell.md)) </span><span class="sxs-lookup"><span data-stu-id="6b695-134">[Manage Microsoft 365 Groups with PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (article)</span></span>\
<span data-ttu-id="6b695-135">[使用 Remove-UnifiedGroup Cmdlet 刪除群組](/powershell/module/exchange/remove-unifiedgroup) (文章) </span><span class="sxs-lookup"><span data-stu-id="6b695-135">[Delete groups using the Remove-UnifiedGroup cmdlet](/powershell/module/exchange/remove-unifiedgroup) (article)</span></span>\
<span data-ttu-id="6b695-136">[管理群組連線的小組網站設定](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (篇) </span><span class="sxs-lookup"><span data-stu-id="6b695-136">[Manage your group-connected team site settings](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (article)</span></span>\
<span data-ttu-id="6b695-137">[在 Outlook (文章中刪除群組](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)) </span><span class="sxs-lookup"><span data-stu-id="6b695-137">[Delete a group in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (article)</span></span>