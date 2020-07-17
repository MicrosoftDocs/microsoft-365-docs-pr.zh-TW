---
title: 與來賓使用者共用網站和檔案
f1.keywords: NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 89502322-bfbb-43d6-9207-4030f8ce26e0
ROBOTS: NOINDEX
description: '瞭解如何與組織外部的人員共用網站和檔案。 '
ms.openlocfilehash: 79760f662ec68d2ac9089586fd9cbf38b0bd9897
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780046"
---
# <a name="share-sites-and-files-with-guest-users"></a><span data-ttu-id="efb10-103">與來賓使用者共用網站和檔案</span><span class="sxs-lookup"><span data-stu-id="efb10-103">Share sites and files with guest users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="efb10-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="efb10-104">The admin center is changing.</span></span> <span data-ttu-id="efb10-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="efb10-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="efb10-106">若要與組織外部的人員進行共同作業，您可以在外部共用整個網站或特定檔案。</span><span class="sxs-lookup"><span data-stu-id="efb10-106">To collaborate with people outside your organization, you can share entire sites or specific files externally.</span></span> <span data-ttu-id="efb10-107">如果您想要直接設定共用，請選擇您要啟用的案例：</span><span class="sxs-lookup"><span data-stu-id="efb10-107">If you want to get straight to setting up sharing, choose the scenario you want to enable:</span></span>

- [<span data-ttu-id="efb10-108">在文件上與來賓共同作業</span><span class="sxs-lookup"><span data-stu-id="efb10-108">Collaborate with guests on a document</span></span>](../../solutions/collaborate-on-documents.md)
- [<span data-ttu-id="efb10-109">在網站中與來賓共同作業</span><span class="sxs-lookup"><span data-stu-id="efb10-109">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="efb10-110">在小組中與來賓共同作業</span><span class="sxs-lookup"><span data-stu-id="efb10-110">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)
  
## <a name="deciding-how-to-share-your-content"></a><span data-ttu-id="efb10-111">決定共用內容的方式</span><span class="sxs-lookup"><span data-stu-id="efb10-111">Deciding how to share your content</span></span>

<span data-ttu-id="efb10-112">當您考慮是否要與外部人員共用內容以及採用何種方式時，請思考以下幾點：</span><span class="sxs-lookup"><span data-stu-id="efb10-112">When considering if and how you want to share content externally, think about the following:</span></span>
  
- <span data-ttu-id="efb10-113">您想要將網站內容的存取權授與所有子網站，以及您想要讓他們做什麼？</span><span class="sxs-lookup"><span data-stu-id="efb10-113">To whom do you want to grant access to content on the site and any subsites, and what do you want them to be able to do?</span></span>
    
- <span data-ttu-id="efb10-114">您要將外部共用內容的權限授與組織內部的哪些人？</span><span class="sxs-lookup"><span data-stu-id="efb10-114">To whom in your organization do you want to grant permission to share content externally?</span></span> 
    
- <span data-ttu-id="efb10-115">是否有絕不允許組織外部人員檢視的內容？</span><span class="sxs-lookup"><span data-stu-id="efb10-115">Is there content you want to ensure is never available to be viewed by people external to your organization?</span></span>
    
<span data-ttu-id="efb10-116">上述問題的答案可幫助您規劃內容共用的策略。</span><span class="sxs-lookup"><span data-stu-id="efb10-116">The answers to these questions will help you plan your strategy for content sharing.</span></span>
  
|<span data-ttu-id="efb10-117">**不妨試試以下做法：**</span><span class="sxs-lookup"><span data-stu-id="efb10-117">**Try this:**</span></span>|<span data-ttu-id="efb10-118">**如果您需要…**</span><span class="sxs-lookup"><span data-stu-id="efb10-118">**If you need to…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="efb10-119">新增來賓至群組</span><span class="sxs-lookup"><span data-stu-id="efb10-119">Add a guest to a group</span></span>  <br/> |<span data-ttu-id="efb10-120">讓組織外部的人員可以隨時存取小組網站上的資訊和內容。</span><span class="sxs-lookup"><span data-stu-id="efb10-120">Provide someone outside your organization with ongoing access to information and content on a team site.</span></span> <span data-ttu-id="efb10-121">他們需要如同您網站完整使用者的操作功能，才能建立、編輯和檢視內容。</span><span class="sxs-lookup"><span data-stu-id="efb10-121">They need the ability to perform like a full user of your site and create, edit, and view content.</span></span>  <br/> |
|<span data-ttu-id="efb10-122">共用檔，並要求來賓進行驗證。</span><span class="sxs-lookup"><span data-stu-id="efb10-122">Share a document and require guests to authenticate.</span></span>  <br/> |<span data-ttu-id="efb10-123">讓組織外部的特定人員可以安全地存取檔，以供審閱或共同作業，但這些人員不需要存取網站上的其他內容。</span><span class="sxs-lookup"><span data-stu-id="efb10-123">Provide specific people outside your organization with secure access to a document for review or collaboration, but these people do not require access to other content on the site.</span></span>  <br/> |
|<span data-ttu-id="efb10-124">共用檔，但不需要驗證。</span><span class="sxs-lookup"><span data-stu-id="efb10-124">Share a document, but don't require authentication.</span></span>  <br/> |<span data-ttu-id="efb10-125">與組織外部人員共用非機密文件的連結，以便其檢視文件，或以意見反應更新文件。</span><span class="sxs-lookup"><span data-stu-id="efb10-125">Share a link to a non-sensitive or non-confidential document with people outside your organization so that they can either view it or update it with feedback.</span></span> <span data-ttu-id="efb10-126">這些人員不需要存取網站上的內容。</span><span class="sxs-lookup"><span data-stu-id="efb10-126">These people do not require access to content on the site.</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="efb10-127">當您停用外部共用時，目前具有存取權的組織外部人員將無法再存取。</span><span class="sxs-lookup"><span data-stu-id="efb10-127">When you disable external sharing, people outside the organization who currently have access will no longer have access.</span></span> <span data-ttu-id="efb10-128">如果您稍後重新開啟外部共用，將會為這些人員還原存取權。</span><span class="sxs-lookup"><span data-stu-id="efb10-128">If you later turn external sharing back on, access will be restored for these people.</span></span> <span data-ttu-id="efb10-129">若要防止使用者存取共用內容，請[將其從 Microsoft 365 群組中移除](/office365/admin/create-groups/add-or-remove-members-from-groups)，從網站移除其許可權，或[停止與其共用檔案或資料夾](https://support.microsoft.com/office/0a36470f-d7fe-40a0-bd74-0ac6c1e13323)。</span><span class="sxs-lookup"><span data-stu-id="efb10-129">To prevent a user from accessing a shared content, [remove them from the Microsoft 365 group](/office365/admin/create-groups/add-or-remove-members-from-groups), remove their permissions from the site, or [stop sharing the file or folder with them](https://support.microsoft.com/office/0a36470f-d7fe-40a0-bd74-0ac6c1e13323).</span></span> 
  
## <a name="enable-external-sharing-at-the-organization-level"></a><span data-ttu-id="efb10-130">在組織層級啟用外部共用</span><span class="sxs-lookup"><span data-stu-id="efb10-130">Enable external sharing at the organization level</span></span>

<span data-ttu-id="efb10-131">預設會在組織層級開啟外部共用，但不適用於所有新網站。</span><span class="sxs-lookup"><span data-stu-id="efb10-131">External sharing is turned on by default at the organization level, but not for all new sites.</span></span> <span data-ttu-id="efb10-132">如需詳細資訊，請參閱[外部共用一覽](/sharepoint/external-sharing-overview)。</span><span class="sxs-lookup"><span data-stu-id="efb10-132">For info, see [External sharing overview](/sharepoint/external-sharing-overview).</span></span> 

> [!NOTE]
>  <span data-ttu-id="efb10-133">若要允許對任何網站進行外部共用，您必須在組織層級允許它。</span><span class="sxs-lookup"><span data-stu-id="efb10-133">To allow external sharing for any site, you need to allow it at the organization level.</span></span> 
  
1. <span data-ttu-id="efb10-134">在系統[管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)中，于首頁上的搜尋方塊中輸入「外部」，然後選擇 [**網站外部共用**]。</span><span class="sxs-lookup"><span data-stu-id="efb10-134">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), type "external" in the search box on the Home page, and choose **Sites external sharing**.</span></span>
  
2. <span data-ttu-id="efb10-135">在開啟的頁面上，選擇使用者是否可以只與現有來賓共用、新的和現有的來賓或任何人共用。</span><span class="sxs-lookup"><span data-stu-id="efb10-135">On the page that opens, choose whether users can share with existing guests only, new and existing guests, or anyone.</span></span> 
    
3. <span data-ttu-id="efb10-136">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="efb10-136">Select **Save**.</span></span>
    
<span data-ttu-id="efb10-137">在組織層級啟用外部共用之後，您可以微調共用設定，以停用特定網站的外部共用。</span><span class="sxs-lookup"><span data-stu-id="efb10-137">After you enable external sharing at the organization level, you can fine tune your sharing settings to disable external sharing for particular sites.</span></span> <span data-ttu-id="efb10-138">如需詳細資訊，請參閱[開啟或關閉網站的外部共用](/sharepoint/change-external-sharing-site)。</span><span class="sxs-lookup"><span data-stu-id="efb10-138">For info, see [Turn external sharing on or off for a site](/sharepoint/change-external-sharing-site).</span></span>
  

  

    

