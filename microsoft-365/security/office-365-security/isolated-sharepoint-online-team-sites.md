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
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: 瞭解獨立的 SharePoint Online 小組網站，包括使用、需求以及可以搭配使用的功能。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 056c6f2a463d38dd27b26d484995280dddedf436
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286582"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="5c6b3-103">獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="5c6b3-103">Isolated SharePoint Online team sites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5c6b3-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="5c6b3-104">**Applies to**</span></span>
- [<span data-ttu-id="5c6b3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5c6b3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5c6b3-106">適用於 Office 365 的 Microsoft Defender 方案 1</span><span class="sxs-lookup"><span data-stu-id="5c6b3-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="5c6b3-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5c6b3-107">SharePoint Online</span></span> 

 <span data-ttu-id="5c6b3-108">**摘要：** 了解獨立的 Sharepoint 小組網站的用途。</span><span class="sxs-lookup"><span data-stu-id="5c6b3-108">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="5c6b3-p101">SharePoint Online 小組網站是快速建立共同作業空間的簡易方式。使用者可以在 Microsoft Office 365 中對記事、文件、文章、行事曆及其他資源進行共同作業。SharePoint Online 小組網站是以 Microsoft 365 群組為基礎，具有簡化的系統管理模型，可供一組私人群組成員或整個組織進行開放的共同作業。預設 SharePoint Online 小組網站可讓 Microsoft 365 群組的成員邀請其他使用者並且控制權限設定。</span><span class="sxs-lookup"><span data-stu-id="5c6b3-p101">SharePoint Online team sites are an easy way to quickly create a space for collaboration. Users can work together on notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>

<span data-ttu-id="5c6b3-113">不過，您有時會需要群組成員資格所控制的網站存取以及由 SharePoint 系統管理員所管理的 SharePoint Online 權限等級。</span><span class="sxs-lookup"><span data-stu-id="5c6b3-113">However, you'll sometimes need site access to be controlled by group memberships, and SharePoint Online permission levels managed by SharePoint administrators.</span></span> <span data-ttu-id="5c6b3-114">我們稱之為獨立的網站，此種網站會獨立於在該網站上共同作業、查看其內容或進行網站管理的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="5c6b3-114">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span></span> <span data-ttu-id="5c6b3-115">以下是您可能需要獨立網站的原因：</span><span class="sxs-lookup"><span data-stu-id="5c6b3-115">You might need an isolated site for the following:</span></span>

- <span data-ttu-id="5c6b3-116">組織中的秘密專案。</span><span class="sxs-lookup"><span data-stu-id="5c6b3-116">A secret project within your organization.</span></span>

- <span data-ttu-id="5c6b3-117">組織的高度敏感或貴重智慧財產權的位置。</span><span class="sxs-lookup"><span data-stu-id="5c6b3-117">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>

- <span data-ttu-id="5c6b3-118">組織採取的法律行動資源，或其受限所在的資源。</span><span class="sxs-lookup"><span data-stu-id="5c6b3-118">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>

- <span data-ttu-id="5c6b3-119">為了在某些地方重疊，但是大部分來說是個別商務實體的多個組織之間共用 Microsoft 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="5c6b3-119">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>

<span data-ttu-id="5c6b3-120">以下是獨立網站的需求：</span><span class="sxs-lookup"><span data-stu-id="5c6b3-120">Here are the requirements of an isolated site:</span></span>

- <span data-ttu-id="5c6b3-121">只有 SharePoint Online 系統管理員可以執行網站系統管理，包括可以存取網站的群組成員資格以及設定自訂權限。</span><span class="sxs-lookup"><span data-stu-id="5c6b3-121">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>

- <span data-ttu-id="5c6b3-122">網站的成員無法邀請其他成員加入小組網站。</span><span class="sxs-lookup"><span data-stu-id="5c6b3-122">Members of the site cannot invite other members to the team site.</span></span>

- <span data-ttu-id="5c6b3-p103">不是獨立網站成員的使用者無法要求網站的存取權。當他們嘗試存取與網站相關聯的任何 URL 時，會進入存取遭拒網頁。</span><span class="sxs-lookup"><span data-stu-id="5c6b3-p103">Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>

<span data-ttu-id="5c6b3-p104">SharePoint Online 系統管理員要求集中式存取控制和自訂權限的代價是網站經過一段時間後仍然是獨立的。舉例來說，目前成員無論有意或無意，都無法對不應該是網站成員的 Microsoft 365 訂閱內其他使用者進行邀請或設定自訂權限。</span><span class="sxs-lookup"><span data-stu-id="5c6b3-p104">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>

<span data-ttu-id="5c6b3-127">獨立的網站可以與其他功能搭配使用，例如：</span><span class="sxs-lookup"><span data-stu-id="5c6b3-127">An isolated site can be used with other features, such as:</span></span>

- <span data-ttu-id="5c6b3-128">資訊版權管理，以便確定網站上的資源保持加密，即使它們是在本機下載並且上傳至可供整個組織使用的其他網站。</span><span class="sxs-lookup"><span data-stu-id="5c6b3-128">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>

- <span data-ttu-id="5c6b3-129">資料外洩防護，以便防止使用者以電子郵件傳送網站的資源，例如檔案。</span><span class="sxs-lookup"><span data-stu-id="5c6b3-129">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5c6b3-130">後續步驟</span><span class="sxs-lookup"><span data-stu-id="5c6b3-130">Next steps</span></span>

<span data-ttu-id="5c6b3-131">若要在試用訂閱中嘗試獨立的 SharePoint Online 小組網站，請參閱＜[獨立的 SharePoint Online 小組網站開發/測試環境](isolated-sharepoint-online-team-site-dev-test-environment.md)＞中的逐步指示</span><span class="sxs-lookup"><span data-stu-id="5c6b3-131">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>

<span data-ttu-id="5c6b3-132">當您準備好要在生產環境中部署獨立的 SharePoint Online 小組網站時，請參閱＜[設計獨立的 SharePoint Online 小組網站](design-an-isolated-sharepoint-online-team-site.md)＞中的逐步設計考量。</span><span class="sxs-lookup"><span data-stu-id="5c6b3-132">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5c6b3-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="5c6b3-133">Related topics</span></span>

[<span data-ttu-id="5c6b3-134">設計獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="5c6b3-134">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="5c6b3-135">管理獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="5c6b3-135">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="5c6b3-136">部署獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="5c6b3-136">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
