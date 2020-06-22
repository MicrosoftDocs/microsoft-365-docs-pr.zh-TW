---
title: 獨立的 SharePoint Online 小組網站
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: 瞭解獨立的 SharePoint Online 小組網站，包括使用、需求以及可以搭配使用的功能。
ms.openlocfilehash: 0646ffc37256702844b550fd1beb841944b2d509
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819530"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="73e6c-103">獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="73e6c-103">Isolated SharePoint Online team sites</span></span>

 <span data-ttu-id="73e6c-104">**摘要：** 了解獨立的 Sharepoint 小組網站的用途。</span><span class="sxs-lookup"><span data-stu-id="73e6c-104">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="73e6c-105">SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="73e6c-105">SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365.</span></span> <span data-ttu-id="73e6c-106">SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization.</span><span class="sxs-lookup"><span data-stu-id="73e6c-106">SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization.</span></span> <span data-ttu-id="73e6c-107">A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span><span class="sxs-lookup"><span data-stu-id="73e6c-107">A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>
  
<span data-ttu-id="73e6c-108">However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators.</span><span class="sxs-lookup"><span data-stu-id="73e6c-108">However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators.</span></span> <span data-ttu-id="73e6c-109">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span><span class="sxs-lookup"><span data-stu-id="73e6c-109">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span></span> <span data-ttu-id="73e6c-110">You might need an isolated site for the following:</span><span class="sxs-lookup"><span data-stu-id="73e6c-110">You might need an isolated site for the following:</span></span>
  
- <span data-ttu-id="73e6c-111">組織中的秘密專案。</span><span class="sxs-lookup"><span data-stu-id="73e6c-111">A secret project within your organization.</span></span>
    
- <span data-ttu-id="73e6c-112">組織的高度敏感或貴重智慧財產權的位置。</span><span class="sxs-lookup"><span data-stu-id="73e6c-112">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>
    
- <span data-ttu-id="73e6c-113">組織採取的法律行動資源，或其受限所在的資源。</span><span class="sxs-lookup"><span data-stu-id="73e6c-113">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>
    
- <span data-ttu-id="73e6c-114">為了在某些地方重疊，但是大部分來說是個別商務實體的多個組織之間共用 Microsoft 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="73e6c-114">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>
    
<span data-ttu-id="73e6c-115">以下是獨立網站的需求：</span><span class="sxs-lookup"><span data-stu-id="73e6c-115">Here are the requirements of an isolated site:</span></span>
  
- <span data-ttu-id="73e6c-116">只有 SharePoint Online 系統管理員可以執行網站系統管理，包括可以存取網站的群組成員資格以及設定自訂權限。</span><span class="sxs-lookup"><span data-stu-id="73e6c-116">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>
    
- <span data-ttu-id="73e6c-117">網站的成員無法邀請其他成員加入小組網站。</span><span class="sxs-lookup"><span data-stu-id="73e6c-117">Members of the site cannot invite other members to the team site.</span></span>
    
- <span data-ttu-id="73e6c-118">Users who are not members of the isolated site cannot request access to the site.</span><span class="sxs-lookup"><span data-stu-id="73e6c-118">Users who are not members of the isolated site cannot request access to the site.</span></span> <span data-ttu-id="73e6c-119">They will receive an access denied web page when they attempt to access any URL associated with the site.</span><span class="sxs-lookup"><span data-stu-id="73e6c-119">They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>
    
<span data-ttu-id="73e6c-120">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time.</span><span class="sxs-lookup"><span data-stu-id="73e6c-120">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time.</span></span> <span data-ttu-id="73e6c-121">For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span><span class="sxs-lookup"><span data-stu-id="73e6c-121">For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>
  
<span data-ttu-id="73e6c-122">獨立的網站可以與其他功能搭配使用，例如：</span><span class="sxs-lookup"><span data-stu-id="73e6c-122">An isolated site can be used with other features, such as:</span></span>
  
- <span data-ttu-id="73e6c-123">資訊版權管理，以便確定網站上的資源保持加密，即使它們是在本機下載並且上傳至可供整個組織使用的其他網站。</span><span class="sxs-lookup"><span data-stu-id="73e6c-123">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>
    
- <span data-ttu-id="73e6c-124">資料外洩防護，以便防止使用者以電子郵件傳送網站的資源，例如檔案。</span><span class="sxs-lookup"><span data-stu-id="73e6c-124">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="73e6c-125">後續步驟</span><span class="sxs-lookup"><span data-stu-id="73e6c-125">Next steps</span></span>

<span data-ttu-id="73e6c-126">若要在試用訂閱中嘗試獨立的 SharePoint Online 小組網站，請參閱＜[獨立的 SharePoint Online 小組網站開發/測試環境](isolated-sharepoint-online-team-site-dev-test-environment.md)＞中的逐步指示</span><span class="sxs-lookup"><span data-stu-id="73e6c-126">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>
  
<span data-ttu-id="73e6c-127">當您準備好要在生產環境中部署獨立的 SharePoint Online 小組網站時，請參閱＜[設計獨立的 SharePoint Online 小組網站](design-an-isolated-sharepoint-online-team-site.md)＞中的逐步設計考量。</span><span class="sxs-lookup"><span data-stu-id="73e6c-127">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="73e6c-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="73e6c-128">Related topics</span></span>

[<span data-ttu-id="73e6c-129">設計獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="73e6c-129">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="73e6c-130">管理獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="73e6c-130">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="73e6c-131">部署獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="73e6c-131">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)


