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
description: 瞭解如何還原已刪除的 Microsoft 365 群組。
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753240"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="5030f-103">還原已刪除的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="5030f-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="5030f-104">如果您已刪除某個群組，它預設會保留30天。</span><span class="sxs-lookup"><span data-stu-id="5030f-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="5030f-105">這30天的期間會被視為「虛刪除」，因為您仍然可以還原群組。</span><span class="sxs-lookup"><span data-stu-id="5030f-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="5030f-106">30天后，就會永久刪除群組及其相關聯的內容，而且無法還原。</span><span class="sxs-lookup"><span data-stu-id="5030f-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="5030f-107">還原群組時，將會還原下列內容：</span><span class="sxs-lookup"><span data-stu-id="5030f-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="5030f-108">Azure Active Directory (AD) Microsoft 365 Groups 物件、屬性和成員。</span><span class="sxs-lookup"><span data-stu-id="5030f-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="5030f-109">群組的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="5030f-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="5030f-110">Exchange Online 共用收件匣和行事曆。</span><span class="sxs-lookup"><span data-stu-id="5030f-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="5030f-111">SharePoint 線上小組網站和檔案。</span><span class="sxs-lookup"><span data-stu-id="5030f-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="5030f-112">OneNote 筆記本</span><span class="sxs-lookup"><span data-stu-id="5030f-112">OneNote notebook</span></span>
    
- <span data-ttu-id="5030f-113">Planner</span><span class="sxs-lookup"><span data-stu-id="5030f-113">Planner</span></span>
    
- <span data-ttu-id="5030f-114">Teams</span><span class="sxs-lookup"><span data-stu-id="5030f-114">Teams</span></span>

- <span data-ttu-id="5030f-115">Yammer 群組和群組內容 (如果 Microsoft 365 群組是由 Yammer 建立) </span><span class="sxs-lookup"><span data-stu-id="5030f-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="5030f-116">本文說明只還原 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="5030f-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="5030f-117">所有其他群組一經刪除，便無法還原。</span><span class="sxs-lookup"><span data-stu-id="5030f-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="5030f-118">還原群組</span><span class="sxs-lookup"><span data-stu-id="5030f-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="5030f-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="5030f-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="5030f-120">如果您是 Microsoft 365 群組的擁有者，您可以遵循下列步驟，在網頁版 Outlook 中還原群組：</span><span class="sxs-lookup"><span data-stu-id="5030f-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="5030f-121">在 [[刪除的群組] 頁面](https://outlook.office.com/people/group/deleted)上，選取 [**群組**] 節點底下的 [**管理群組**] 選項，然後選擇 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="5030f-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="5030f-122">按一下您要還原之群組旁的 [ **還原** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5030f-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="5030f-123">若已刪除的群組未出現在這裡，請與系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="5030f-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="5030f-124">系統管理中心</span><span class="sxs-lookup"><span data-stu-id="5030f-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="5030f-125">如果您是全域系統管理員或群組管理員，您可以在 Microsoft 365 系統管理中心還原刪除的群組：</span><span class="sxs-lookup"><span data-stu-id="5030f-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="5030f-126">移至 [[系統管理中心]](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="5030f-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="5030f-127">展開 [ **群組**]，然後按一下 [ **刪除的群組**]。</span><span class="sxs-lookup"><span data-stu-id="5030f-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="5030f-128">選取您要還原的群組，然後按一下 [ **還原群組**]。</span><span class="sxs-lookup"><span data-stu-id="5030f-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="5030f-129">在某些情況下，您可能需要24小時的時間才能還原群組及其所有資料。</span><span class="sxs-lookup"><span data-stu-id="5030f-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="5030f-130">有關于 Microsoft 365 群組的問題嗎？</span><span class="sxs-lookup"><span data-stu-id="5030f-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="5030f-131">流覽 [Microsoft 技術社區](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) 以張貼問題，並參與 microsoft 365 群組的交談。</span><span class="sxs-lookup"><span data-stu-id="5030f-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="5030f-132">相關文章</span><span class="sxs-lookup"><span data-stu-id="5030f-132">Related articles</span></span>

[<span data-ttu-id="5030f-133">使用 PowerShell 管理 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="5030f-133">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="5030f-134">使用 Remove-UnifiedGroup Cmdlet 來刪除群組</span><span class="sxs-lookup"><span data-stu-id="5030f-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
<span data-ttu-id="5030f-135">[管理連接群組的小組網站設定](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="5030f-135">[Manage your group-connected team site settings](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)</span></span>
  
<span data-ttu-id="5030f-136">[在 Outlook 中刪除群組](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="5030f-136">[Delete a group in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)</span></span>
