---
title: 部署三種保護層級的 SharePoint Online 網站
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 摘要：建立及設定各種資訊保護等級的 SharePoint Online 小組網站。
ms.openlocfilehash: 1f67dd1956059162902aefdb194e5e514d063778
ms.sourcegitcommit: a53ec6ab7bf59983780ea7187cd5d56b8b1f4b33
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/07/2020
ms.locfileid: "41855252"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a><span data-ttu-id="ebe9b-103">部署三種保護層級的 SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="ebe9b-103">Deploy SharePoint Online sites for three tiers of protection</span></span>

<span data-ttu-id="ebe9b-p101">您可以使用本文中的步驟，來設計及部署基準、機密和高度機密 SharePoint Online 小組網站。 如需這三種保護層級的詳細資訊，請參閱[保護 SharePoint Online 網站與檔案](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-p101">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="baseline-sharepoint-online-team-sites"></a><span data-ttu-id="ebe9b-106">基準 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="ebe9b-106">Baseline SharePoint Online team sites</span></span>

<span data-ttu-id="ebe9b-p102">基準保護包含公用和私人小組網站。 公用小組網站可供組織中的任何人探索及存取。 私人網站只能供與小組網站關聯的 Office 365 群組成員探索及存取。 這兩種小組網站類型都可讓成員與其他人共用網站。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-p102">Baseline protection includes both public and private team sites. Public team sites can be discovered and accessed by anybody in the organization. Private sites can only be discovered and accessed by members of the Office 365 group associated with the team site. Both of these types of team sites allow members to share the site with others.</span></span>
  
### <a name="public"></a><span data-ttu-id="ebe9b-111">公用</span><span class="sxs-lookup"><span data-stu-id="ebe9b-111">Public</span></span>

<span data-ttu-id="ebe9b-112">若要建立具有公用存取和權限的基準 SharePoint Online 小組網站，遵循[這些指示](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-112">To create a baseline SharePoint Online team site with public access and permissions, follow [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="ebe9b-113">以下是產生的組態。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-113">Here is your resulting configuration.</span></span>
  
![適用於公用 SharePoint Online 小組網站的基準層級保護。](media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a><span data-ttu-id="ebe9b-115">私人</span><span class="sxs-lookup"><span data-stu-id="ebe9b-115">Private</span></span>

<span data-ttu-id="ebe9b-116">若要建立具有私人存取和權限的基準 SharePoint Online 小組網站，遵循[這些指示](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-116">To create a baseline SharePoint Online team site with private access and permissions, follow [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>
  
<span data-ttu-id="ebe9b-117">以下是產生的組態。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-117">Here is your resulting configuration.</span></span>
  
![適用於私人 SharePoint Online 小組網站的基準層級保護。](media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a><span data-ttu-id="ebe9b-119">機密 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="ebe9b-119">Sensitive SharePoint Online team sites</span></span>

<span data-ttu-id="ebe9b-120">敏感性的 SharePoint Online 小組網站始於私人小組網站。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-120">A sensitive SharePoint Online team site starts as a private team site.</span></span>
  
<span data-ttu-id="ebe9b-121">首先，使用[這些指示](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)建立私人 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-121">First, create the private SharePoint Online team site with [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="ebe9b-122">接下來，從新的 SharePoint Online 小組網站，使用下列步驟設定額外使用權限設定。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-122">Next, from the new SharePoint Online team site, configure additional permission settings with these steps.</span></span>

1.  <span data-ttu-id="ebe9b-123">在 SharePoint 小組網站的工具列中，按一下設定圖示，然後按一下 [網站權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-123">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="ebe9b-124">在 [網站權限]\*\*\*\* 窗格的 [共用設定]\*\*\*\* 之下，按一下 [變更共用設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-124">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="ebe9b-125">在 [共用權限]\*\*\*\* 之下，選擇 [只有網站擁有者可以共用檔案、資料夾及網站]\*\*\*\*，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-125">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="ebe9b-126">這些使用權限設定的結果是：</span><span class="sxs-lookup"><span data-stu-id="ebe9b-126">The results of these permission settings are:</span></span>

- <span data-ttu-id="ebe9b-127">成員分享給其他成員的功能已停用。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-127">The ability for members to share with other members is disabled.</span></span>
- <span data-ttu-id="ebe9b-128">非成員要求存取的功能已啟用。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-128">The ability for non-members to request access is enabled.</span></span>

<span data-ttu-id="ebe9b-129">以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-129">Here is your resulting configuration.</span></span>
  
![適用於隔離 SharePoint Online 小組網站的敏感性層級保護。](media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
<span data-ttu-id="ebe9b-131">網站成員現在可以透過其中一個存取群組的群組成員資格，安全地在網站的資源上共同作業。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-131">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a><span data-ttu-id="ebe9b-132">高度機密 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="ebe9b-132">Highly confidential SharePoint Online team sites</span></span>

<span data-ttu-id="ebe9b-133">高度機密的 SharePoint Online 小組網站是含有額外使用權設定的私人小組網站。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-133">A highly confidential SharePoint Online team site is a private team site with additional permissions settings.</span></span>

<span data-ttu-id="ebe9b-134">首先，使用[這些指示](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)建立私人 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-134">First, create the private SharePoint Online team site with [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="ebe9b-135">接下來，從新的 SharePoint Online 小組網站，使用下列步驟設定額外使用權限設定。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-135">Next, from the new SharePoint Online team site, configure additional permission settings with these steps.</span></span>

1.  <span data-ttu-id="ebe9b-136">在 SharePoint 小組網站的工具列中，按一下設定圖示，然後按一下 [網站權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-136">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="ebe9b-137">在 [網站權限]\*\*\*\* 窗格的 [共用設定]\*\*\*\* 之下，按一下 [變更共用設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-137">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="ebe9b-138">在 [共用權限]\*\*\*\* 之下，選擇 [只有網站擁有者可以共用檔案、資料夾及網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-138">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="ebe9b-139">關閉 [允許存取要求]\*\*\*\*，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-139">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="ebe9b-140">這些使用權限設定的結果是：</span><span class="sxs-lookup"><span data-stu-id="ebe9b-140">The results of these permission settings are:</span></span>

- <span data-ttu-id="ebe9b-141">成員分享給其他成員的功能已停用。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-141">The ability for members to share with other members is disabled.</span></span>
- <span data-ttu-id="ebe9b-142">非成員要求存取的功能已停用。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-142">The ability for non-members to request access is disabled.</span></span>

<span data-ttu-id="ebe9b-143">以下是您產生的組態。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-143">Here is your resulting configuration.</span></span>
  
![適用於隔離 SharePoint Online 小組網站的高度機密層級保護。](media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
<span data-ttu-id="ebe9b-145">網站成員現在可以透過其中一個存取群組的群組成員資格，安全地在網站的資源上共同作業。</span><span class="sxs-lookup"><span data-stu-id="ebe9b-145">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="ebe9b-146">下一步</span><span class="sxs-lookup"><span data-stu-id="ebe9b-146">Next step</span></span>

[<span data-ttu-id="ebe9b-147">使用 Office 365 標籤與 DLP 來保護 SharePoint Online 檔案</span><span class="sxs-lookup"><span data-stu-id="ebe9b-147">Protect SharePoint Online files with Office 365 labels and DLP</span></span>](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a><span data-ttu-id="ebe9b-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ebe9b-148">See also</span></span>

[<span data-ttu-id="ebe9b-149">適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南</span><span class="sxs-lookup"><span data-stu-id="ebe9b-149">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="ebe9b-150">雲端採用和混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="ebe9b-150">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
