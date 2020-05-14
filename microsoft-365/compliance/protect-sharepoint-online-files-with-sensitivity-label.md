---
title: 使用敏感度標籤來保護 SharePoint Online 檔案
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
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 摘要：套用 Azure 資訊保護來保護高度機密 SharePoint Online 小組網站中的檔案。
ms.openlocfilehash: 8d802d8c2b5202e51089659264b2e2c14f14ad3d
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214627"
---
# <a name="protect-sharepoint-online-files-with-a-sensitivity-label"></a><span data-ttu-id="29858-103">使用敏感度標籤來保護 SharePoint Online 檔案</span><span class="sxs-lookup"><span data-stu-id="29858-103">Protect SharePoint Online files with a sensitivity label</span></span>

<span data-ttu-id="29858-104">使用本文中的步驟來設定敏感度標籤，以提供檔案的加密和權限。</span><span class="sxs-lookup"><span data-stu-id="29858-104">Use the steps in this article to configure a sensitivity label to provide encryption and permissions for files.</span></span> <span data-ttu-id="29858-105">您可以將這些檔案新增至已設定高度機密保護的 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="29858-105">These files can be added to a SharePoint library configured for highly confidential protection.</span></span> <span data-ttu-id="29858-106">或者，您可以直接從網站開啟檔案並套用標籤。</span><span class="sxs-lookup"><span data-stu-id="29858-106">Or, you can open a file directly from the site and apply the label.</span></span> <span data-ttu-id="29858-107">此加密和權限保護會與檔案一起移動，即使是從網站下載檔案也一樣。</span><span class="sxs-lookup"><span data-stu-id="29858-107">The encryption and permissions protection travels with a file even when it is downloaded from the site.</span></span> 

<span data-ttu-id="29858-p102">這些步驟是屬於較大的解決方案，用於設定 SharePoint 網站和這些網站中檔案的高度機密保護。如需詳細資訊，請參閱[保護 SharePoint Online 網站與檔案](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="29858-p102">These steps are part of a larger solution for configuring highly confidential protection for SharePoint sites and the files within these sites. For more information, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span> 

<span data-ttu-id="29858-110">不建議針對所有的客戶在 SharePoint Online 中的檔案使用敏感度標籤，但可供需要此檔案子集合保護層級的客戶選擇使用。</span><span class="sxs-lookup"><span data-stu-id="29858-110">Using sensitivity labels for files in SharePoint Online is not recommended for all customers, but is an option for customers who need this level of protection for a subset of files.</span></span>

<span data-ttu-id="29858-111">這套解決方案的一些相關重要注意事項：</span><span class="sxs-lookup"><span data-stu-id="29858-111">Some important notes about this solution:</span></span>
- <span data-ttu-id="29858-112">如果貴組織未[在 SharePoint 和 OneDrive (公開預覽版) 中針對 Office 檔案啟用敏感度標籤](/microsoft-365/compliance/sensitivity-labels-sharepoint-onedrive-files)：當您將加密套用到儲存在 Office 365 中的檔案時，服務無法處理這些檔案的內容。</span><span class="sxs-lookup"><span data-stu-id="29858-112">If your organization hasn't [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](/microsoft-365/compliance/sensitivity-labels-sharepoint-onedrive-files): When encryption is applied to files stored in Office 365, the service cannot process the contents of these files.</span></span> <span data-ttu-id="29858-113">共同撰寫、eDiscovery、搜尋、Delve 和其他共同作業功能無法運作。</span><span class="sxs-lookup"><span data-stu-id="29858-113">Co-authoring, eDiscovery, search, Delve, and other collaborative features do not work.</span></span> <span data-ttu-id="29858-114">此外，資料外洩防護 (DLP) 原則只可用於中繼資料 (包括標籤)，但無法用於這些檔案的內容 (例如檔案中的信用卡號碼)。</span><span class="sxs-lookup"><span data-stu-id="29858-114">Data Loss Prevention (DLP) policies can only work with the metadata (including labels) but not the contents of these files (such as credit card numbers within files).</span></span>

- <span data-ttu-id="29858-115">本解決方案要求使用者選取適用保護的標籤。</span><span class="sxs-lookup"><span data-stu-id="29858-115">This solution requires a user to select a label that applies the protection.</span></span> <span data-ttu-id="29858-116">如果您需要自動加密和 SharePoint 的功能來為檔案編製索引及檢查檔案，請考慮在 SharePoint Online 中使用資訊版權管理 (IRM)。</span><span class="sxs-lookup"><span data-stu-id="29858-116">If you require automatic encryption and the ability for SharePoint to index and inspect the files, consider using Information Rights Management (IRM) in SharePoint Online.</span></span> <span data-ttu-id="29858-117">當您為 IRM 設定 SharePoint 文件庫，即會在下載檔案以供編輯時自動加密。</span><span class="sxs-lookup"><span data-stu-id="29858-117">When you configure a SharePoint library for IRM, files are automatically encrypted when they are downloaded for editing.</span></span>  <span data-ttu-id="29858-118">SharePoint IRM 包含可能會影響您決策的限制。</span><span class="sxs-lookup"><span data-stu-id="29858-118">SharePoint IRM includes limitations that might influence your decision.</span></span> <span data-ttu-id="29858-119">如需詳細資訊，請參閱[在 SharePoint 系統管理中心設定資訊版權管理 (IRM)](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="29858-119">For more information, see [Set up Information Rights Management (IRM) in SharePoint admin center](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center).</span></span>

## <a name="admin-setup"></a><span data-ttu-id="29858-120">系統管理員設定</span><span class="sxs-lookup"><span data-stu-id="29858-120">Admin setup</span></span>

<span data-ttu-id="29858-121">若要為特定 SharePoint Online 小組網站中的檔案達成這個額外的安全性層級，您必須設定自訂的敏感度標籤，而此標籤可以是單獨的標籤，或是高度管制資料之一般標籤的子標籤。</span><span class="sxs-lookup"><span data-stu-id="29858-121">To accomplish this additional level of security for files in a specific SharePoint Online team site, you must configure a customized sensitivity label that is either its own label or a sublabel of the general label for highly regulated data.</span></span> <span data-ttu-id="29858-122">只有 SharePoint Online 小組網站的 Microsoft 365 群組成員，才會在其標籤清單中看到自訂的標籤或子標籤。</span><span class="sxs-lookup"><span data-stu-id="29858-122">Only members of the Microsoft 365 group for the SharePoint Online team site will see the customized label or sublabel in their list of labels.</span></span>

- <span data-ttu-id="29858-123">當您需要同時用於全域使用和個別私人小組的少量標籤時，請使用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="29858-123">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span>

- <span data-ttu-id="29858-124">當您有大量標籤，或想要將高度機密小組的標籤整理到高度機密檔案之多用途標籤之下時，請使用敏感度子標籤。</span><span class="sxs-lookup"><span data-stu-id="29858-124">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for highly confidential teams under a general-purpose label for highly confidential files.</span></span>

<span data-ttu-id="29858-125">依照[下列指示](encryption-sensitivity-labels.md)，設定具有下列設定的不同標籤或子標籤：</span><span class="sxs-lookup"><span data-stu-id="29858-125">Use [these instructions](encryption-sensitivity-labels.md) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="29858-126">標籤或子標籤的名稱中包含小組網站的名稱</span><span class="sxs-lookup"><span data-stu-id="29858-126">The name of the label or sublabel contains the name of the team site</span></span>
- <span data-ttu-id="29858-127">已啟用加密</span><span class="sxs-lookup"><span data-stu-id="29858-127">Encryption is enabled</span></span>
- <span data-ttu-id="29858-128">小組網站的 Microsoft 365 群組具有共同撰寫權限</span><span class="sxs-lookup"><span data-stu-id="29858-128">The Microsoft 365 group for the team site has Co-Author permissions</span></span>

<span data-ttu-id="29858-129">建立之後，請為您的使用者發佈新的標籤或子標籤，讓他們能夠在檔案上傳至小組前先在本機的檔案套用標籤，或等到檔案儲存至小組時再套用。</span><span class="sxs-lookup"><span data-stu-id="29858-129">After creating, publish the new label or sublabel for your users, who can then apply them to files either locally before uploading them to the team or later once the file is stored in the team.</span></span>
 
<span data-ttu-id="29858-130">您一旦使用，便能從 Microsoft Word、Excel 和 PowerPoint 的 [常用]\*\*\*\* 功能區中選取 [敏感度]\*\*\*\* 選項的靈敏度標籤。</span><span class="sxs-lookup"><span data-stu-id="29858-130">Once your uses can select the sensitivity label from the **Sensitivity** option from the **Home** ribbon in Microsoft Word, Excel, and PowerPoint.</span></span>
  
> [!NOTE]
> <span data-ttu-id="29858-131">如果您有多個高度敏感度的 SharePoint Online 小組網站，即應建立多個靈敏度標籤。</span><span class="sxs-lookup"><span data-stu-id="29858-131">If you have multiple highly sensitive SharePoint Online team sites, you should create multiple sensitivity labels.</span></span> 
  
## <a name="adding-permissions-for-external-users"></a><span data-ttu-id="29858-132">新增外部使用者的權限</span><span class="sxs-lookup"><span data-stu-id="29858-132">Adding permissions for external users</span></span>
<span data-ttu-id="29858-133">您可以使用兩種方式，將敏感度標籤所保護的檔案存取權授與外部使用者。</span><span class="sxs-lookup"><span data-stu-id="29858-133">There are two ways you can grant external users access to files protected with a sensitivity label.</span></span> <span data-ttu-id="29858-134">在這兩種情況下，外部使用者皆必須擁有 Azure AD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="29858-134">In both cases, external users must have an Azure AD account.</span></span> <span data-ttu-id="29858-135">如果外部使用者不屬於使用 Azure AD 的組織成員，可以使用 [https://aka.ms/aip-signup](https://aka.ms/aip-signup) 這個註冊頁面，以個人身分取得 Azure AD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="29858-135">If external users aren't members of an organization that uses Azure AD, they can obtain an Azure AD account as an individual by using this signup page: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).</span></span>

 - <span data-ttu-id="29858-136">將外部使用者新增至小組網站的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="29858-136">Add external users to the Microsoft 365 group for the team site.</span></span> <span data-ttu-id="29858-137">您必須先將帳戶新增為目錄中的 B2B 使用者。</span><span class="sxs-lookup"><span data-stu-id="29858-137">You'll need to first add the account as a B2B user in your directory.</span></span> <span data-ttu-id="29858-138">當 [Azure Rights Management 進行群組成員資格的快取](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection)時，可能需要數小時的時間。</span><span class="sxs-lookup"><span data-stu-id="29858-138">It can take a couple of hours for [group membership caching by Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection).</span></span>  
 - <span data-ttu-id="29858-139">將外部使用者帳戶直接新增至標籤設定。</span><span class="sxs-lookup"><span data-stu-id="29858-139">Add external user accounts directly to the label configuration.</span></span> <span data-ttu-id="29858-140">您可以從組織 (例如 Fabrikam.com)、Microsoft 365 群組 (例如組織內的財務部門) 或使用者，新增所有使用者。</span><span class="sxs-lookup"><span data-stu-id="29858-140">You can add all users from an organization (e.g. Fabrikam.com), a Microsoft 365 group (such as a finance group within an organization), or user.</span></span> <span data-ttu-id="29858-141">例如，您可以將外部的監理人員小組新增至敏感度標籤的許可項目中。</span><span class="sxs-lookup"><span data-stu-id="29858-141">For example, you can add an external team of regulators to the permissions of your sensitivity label.</span></span>

## <a name="see-also"></a><span data-ttu-id="29858-142">另請參閱</span><span class="sxs-lookup"><span data-stu-id="29858-142">See Also</span></span>

[<span data-ttu-id="29858-143">適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南</span><span class="sxs-lookup"><span data-stu-id="29858-143">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="29858-144">雲端採用和混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="29858-144">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
