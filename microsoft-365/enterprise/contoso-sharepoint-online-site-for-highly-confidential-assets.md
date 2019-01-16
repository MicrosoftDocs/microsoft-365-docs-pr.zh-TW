---
title: Contoso Corporation 的高度機密數位資產的 SharePoint Online 網站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Architecture
description: 摘要： 如何 Contoso 高度實作的 SharePoint Online 網站規範的資料及其研究 （英文） 之間的更輕鬆地共同作業的小組。
ms.openlocfilehash: 697ddb27b56fd529e9c73b89d9f07b8731ad76c3
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866710"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="cba38-103">Contoso Corporation 的高度機密數位資產的 SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="cba38-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="cba38-104">**摘要：** Contoso 的實作方式進行其研究小組間的更輕鬆地共同作業的高度規範資料的 SharePoint Online 網站。</span><span class="sxs-lookup"><span data-stu-id="cba38-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="cba38-p101">Contoso 的最有價值資產是其財產貿易機密資料，例如專屬製造流程技術的表單中與設計規格中開發的產品。這些資產相關數位格式、 原本儲存為 SharePoint Server 2016 網站上的檔案。當 Contoso 部署 Microsoft 365 企業版時，他們想要轉換至更輕鬆地存取與更多 open 共同作業雲端其內部部署數位資產的研究小組 Paris、 莫斯科、 紐約、 北京，以及班加羅爾中不同。</span><span class="sxs-lookup"><span data-stu-id="cba38-p101">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development. These assets are in digital form, originally stored as files on a SharePoint Server 2016 site. When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="cba38-108">不過，因為其機密性質，存取這些檔案必須：</span><span class="sxs-lookup"><span data-stu-id="cba38-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="cba38-109">受限制的人員，他們可以檢視或變更它們，只能由 SharePoint 系統管理員管理網站的進行中的權限組。</span><span class="sxs-lookup"><span data-stu-id="cba38-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="cba38-110">保護與資料遺失防護 (DLP) 若要防止使用者散佈這些外部網站。</span><span class="sxs-lookup"><span data-stu-id="cba38-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="cba38-111">加密及使用受保護的存取控制清單來防止未經授權的使用者存取其內容，即使其分散外部網站。</span><span class="sxs-lookup"><span data-stu-id="cba38-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="cba38-112">安全性與 SharePoint 管理員可以在 Contoso 的 IT 部門決定要使用[的 SharePoint Online 網站高度規範資料](teams-sharepoint-online-sites-highly-regulated-data.md)。</span><span class="sxs-lookup"><span data-stu-id="cba38-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="cba38-113">Contoso 會使用下列步驟可建立及保護其的研究小組的 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="cba38-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="cba38-114">步驟 1： 檢閱並確認研究小組群組的成員</span><span class="sxs-lookup"><span data-stu-id="cba38-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="cba38-p102">Contoso IT 系統管理員執行他們的研究小組的安全性群組的檢閱。他們移除未研究者或沒有不需要參照資產存取的人。</span><span class="sxs-lookup"><span data-stu-id="cba38-p102">Contoso IT admins performed a review of the set of security groups for their research teams. They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="cba38-117">他們也並建立這些新的安全性群組：</span><span class="sxs-lookup"><span data-stu-id="cba38-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="cba38-118">**[參考資料系統管理員** SharePoint 管理員具有完全控制權的網站，包括能夠修改權限組。</span><span class="sxs-lookup"><span data-stu-id="cba38-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="cba38-119">**[參考資料成員** 為全球各地的研究小組安全性群組組。</span><span class="sxs-lookup"><span data-stu-id="cba38-119">**Research Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="cba38-120">**[參考資料檢視器** 管理使用者，例如高階主管的研究 （英文） 組織，可以在網站檢視資產中一組。</span><span class="sxs-lookup"><span data-stu-id="cba38-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="cba38-121">步驟 2： 建立隔離的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="cba38-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="cba38-p103">第一次建立新的小組網站的 Contoso SharePoint admins 名為 **[參考資料**。它們然後設定：</span><span class="sxs-lookup"><span data-stu-id="cba38-p103">Contoso SharePoint admins first created a new team site named **Research**. They then configured:</span></span>

- <span data-ttu-id="cba38-124">使用 [參考資料擁有者 SharePoint 群組中，有**Research-Admins**安全性群組的成員身分的完全控制 」 權限層級</span><span class="sxs-lookup"><span data-stu-id="cba38-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="cba38-125">要使用參考資料成員 SharePoint 群組中，有**Research 成員**」 安全性群組的成員身分的編輯權限層級</span><span class="sxs-lookup"><span data-stu-id="cba38-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="cba38-126">若要使用參考資料訪客 SharePoint 群組中，具有 [**參考資料檢視程式**安全性] 群組成員身分的讀取權限層級</span><span class="sxs-lookup"><span data-stu-id="cba38-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="cba38-127">以下是所產生的 SharePoint 權限層級、 SharePoint 群組和其成員。</span><span class="sxs-lookup"><span data-stu-id="cba38-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="cba38-128">接下來，其設定之網站的其他限制。</span><span class="sxs-lookup"><span data-stu-id="cba38-128">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="cba38-129">如設定的詳細資訊，請參閱 ＜ [Deploy 隔離的 SharePoint Online 小組網站](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)。</span><span class="sxs-lookup"><span data-stu-id="cba38-129">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-office-365-label-dlp-policy"></a><span data-ttu-id="cba38-130">步驟 3： 設定嚴格的 Office 365 標籤 DLP 原則的網站</span><span class="sxs-lookup"><span data-stu-id="cba38-130">Step 3: Configured the site for a restrictive Office 365 label DLP policy</span></span>

<span data-ttu-id="cba38-131">首先，Contoso admins **Research**網站套用**高度機密**的 Office 365 標籤。</span><span class="sxs-lookup"><span data-stu-id="cba38-131">First, Contoso admins applied the **Highly Confidential** Office 365 label to the **Research** site.</span></span>

<span data-ttu-id="cba38-132">接下來，建立新的 Office 365 DLP 原則名為 **[參考資料**的：</span><span class="sxs-lookup"><span data-stu-id="cba38-132">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="cba38-133">使用**高度機密**的 Office 365 標籤。</span><span class="sxs-lookup"><span data-stu-id="cba38-133">Uses the **Highly Confidential** Office 365 label.</span></span> 
- <span data-ttu-id="cba38-134">會套用至**Research**網站。</span><span class="sxs-lookup"><span data-stu-id="cba38-134">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="cba38-135">防止使用者共用文件。</span><span class="sxs-lookup"><span data-stu-id="cba38-135">Prevents users from sharing documents.</span></span>

<span data-ttu-id="cba38-136">如設定的詳細資訊，請參閱 ＜[保護 SharePoint Online 與 Office 365 標籤和 DLP 的檔案](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)。</span><span class="sxs-lookup"><span data-stu-id="cba38-136">For the configuration details, see [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="cba38-137">步驟 4： 建立網站的 Azure 資訊保護子標籤</span><span class="sxs-lookup"><span data-stu-id="cba38-137">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="cba38-138">建立新的 Azure 資訊保護子標籤的 Contoso admins 命名範圍的原則中的預設**高度機密**標籤的 **[參考資料**的：</span><span class="sxs-lookup"><span data-stu-id="cba38-138">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="cba38-139">需要加密。</span><span class="sxs-lookup"><span data-stu-id="cba38-139">Requires encryption.</span></span>
- <span data-ttu-id="cba38-140">允許完整存取**Research 成員**」 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="cba38-140">Allows full access by members of the **Research Members** security group.</span></span>
- <span data-ttu-id="cba38-141">允許讀取權限**參考資料的檢視器**的 [安全性] 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="cba38-141">Allows read access by members of the **Research Viewers** security group.</span></span>

<span data-ttu-id="cba38-142">接下來，他們部署 Azure 資訊保護用戶端裝置的研究小組成員。</span><span class="sxs-lookup"><span data-stu-id="cba38-142">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="cba38-143">如設定的詳細資訊，請參閱 ＜[保護 SharePoint Online Azure 資訊保護檔案](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)。</span><span class="sxs-lookup"><span data-stu-id="cba38-143">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="cba38-144">以下是所產生的高度機密資產**研究**網站組態。</span><span class="sxs-lookup"><span data-stu-id="cba38-144">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="cba38-145">步驟 5： 移轉內部部署 SharePoint 研究 （英文） 資料</span><span class="sxs-lookup"><span data-stu-id="cba38-145">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="cba38-146">Contoso admins 移動的所有內部研究內部部署 SharePoint Server 2016 網站中新**參考資料**的 SharePoint Online 站台的資料夾中的檔案。</span><span class="sxs-lookup"><span data-stu-id="cba38-146">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="cba38-147">步驟 6： 訓練使用者</span><span class="sxs-lookup"><span data-stu-id="cba38-147">Step 6: Trained their users</span></span> 

<span data-ttu-id="cba38-148">Contoso 安全性員工培訓逐步執行其透過強制課程的研究小組：</span><span class="sxs-lookup"><span data-stu-id="cba38-148">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="cba38-149">如何存取新的**研究**SharePoint Online 網站和其現有的檔案。</span><span class="sxs-lookup"><span data-stu-id="cba38-149">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="cba38-150">如何在網站上建立新檔案，以及上傳儲存在本機的新檔案。</span><span class="sxs-lookup"><span data-stu-id="cba38-150">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="cba38-151">示範如何 DLP 原則封鎖來自外部共用檔案。</span><span class="sxs-lookup"><span data-stu-id="cba38-151">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="cba38-152">使用 Azure 資訊保護用戶端標籤具有**Research**子標籤的 [參考資料檔案的方式。</span><span class="sxs-lookup"><span data-stu-id="cba38-152">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="cba38-153">即使它洩露從網站**Research**子標籤保護檔案的方式示範。</span><span class="sxs-lookup"><span data-stu-id="cba38-153">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="cba38-154">最終結果是安全的環境中研究者可以共同作業整個組織中的安全的環境。</span><span class="sxs-lookup"><span data-stu-id="cba38-154">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="cba38-155">如果**Research**子標籤研究 （英文） 文件從 **[參考資料**網站洩露，最好是加密和只可以存取具有有效認證**Research 成員**及**參考資料的檢視器**的安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="cba38-155">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research Members** and **Research Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="cba38-156">下一步</span><span class="sxs-lookup"><span data-stu-id="cba38-156">Next step</span></span>

<span data-ttu-id="cba38-157">在貴組織中[部署](deploy-microsoft-365-enterprise.md) Microsoft 365 企業版。</span><span class="sxs-lookup"><span data-stu-id="cba38-157">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

