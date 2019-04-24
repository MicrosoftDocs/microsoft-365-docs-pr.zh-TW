---
title: Contoso Corporation 的高度機密數位資產的 SharePoint Online 網站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 摘要： 如何 Contoso 實施適用於 SharePoint Online 網站高管制的資料，其研究之間更輕鬆地共同作業的團隊。
ms.openlocfilehash: c20e3a1c4ad0b862e81b897acc1462e3a1d1f776
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289215"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="99503-103">Contoso Corporation 的高度機密數位資產的 SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="99503-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="99503-104">**摘要：** Contoso 實作其研究小組之間更輕鬆地共同作業的高管制資料的 SharePoint Online 網站的方式。</span><span class="sxs-lookup"><span data-stu-id="99503-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="99503-105">Contoso 的最有價值的資產是其形式的營業秘密、 專屬的製造技術，例如智慧財產及設計規格正在開發的產品。</span><span class="sxs-lookup"><span data-stu-id="99503-105">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="99503-106">這些資產相關數位表單中，原來儲存為 SharePoint Server 2016 網站上的檔案。</span><span class="sxs-lookup"><span data-stu-id="99503-106">These assets are in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="99503-107">Contoso 部署 Microsoft 365 企業版，他們想要在巴黎、 莫斯科、 紐約、 北京和班加羅爾研究小組間轉換至雲端的更容易存取，且更開啟共同作業其內部部署數位資產。</span><span class="sxs-lookup"><span data-stu-id="99503-107">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="99503-108">不過，由於其機密性質，存取這些檔案必須是一項：</span><span class="sxs-lookup"><span data-stu-id="99503-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="99503-109">受限制的允許檢視或變更，具有持續的權限僅由 SharePoint 系統管理員管理網站的人員設定。</span><span class="sxs-lookup"><span data-stu-id="99503-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="99503-110">保護與資料外洩防護 (DLP) 可防止使用者間分散外部網站。</span><span class="sxs-lookup"><span data-stu-id="99503-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="99503-111">加密和保護與存取控制清單，以防止未經授權的使用者存取其內容，即使他們分配站台外。</span><span class="sxs-lookup"><span data-stu-id="99503-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="99503-112">安全性和 SharePoint 系統管理員在 Contoso 的 IT 部門決定使用[適用於 SharePoint Online 網站高管制資料](teams-sharepoint-online-sites-highly-regulated-data.md)。</span><span class="sxs-lookup"><span data-stu-id="99503-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="99503-113">Contoso 使用下列步驟來建立並保護其研究小組 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="99503-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="99503-114">步驟 1： 檢閱並確認研究小組群組的成員</span><span class="sxs-lookup"><span data-stu-id="99503-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="99503-115">Contoso 的 IT 系統管理員為其研究小組執行 < review of 一組安全性群組。</span><span class="sxs-lookup"><span data-stu-id="99503-115">Contoso IT admins performed a review of the set of security groups for their research teams.</span></span> <span data-ttu-id="99503-116">任何人未 researcher 或不需要存取 research 資產移除它們。</span><span class="sxs-lookup"><span data-stu-id="99503-116">They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="99503-117">他們也建立這些新的安全性群組：</span><span class="sxs-lookup"><span data-stu-id="99503-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="99503-118">**Research 系統管理員** 一組的 SharePoint 系統管理員具有完全控制權的網站，包括修改權限的能力。</span><span class="sxs-lookup"><span data-stu-id="99503-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="99503-119">**Research 成員** 一組安全性群組的世界各地的研究小組。</span><span class="sxs-lookup"><span data-stu-id="99503-119">**Research-Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="99503-120">**參考資料檢視** 一組管理使用者，例如 research 組織，只能在網站檢視資產中的主管。</span><span class="sxs-lookup"><span data-stu-id="99503-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can only view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="99503-121">步驟 2： 建立隔離的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="99503-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="99503-122">第一次建立新的小組網站的 Contoso SharePoint 系統管理員名為**Research**。</span><span class="sxs-lookup"><span data-stu-id="99503-122">Contoso SharePoint admins first created a new team site named **Research**.</span></span> <span data-ttu-id="99503-123">他們，然後設定：</span><span class="sxs-lookup"><span data-stu-id="99503-123">They then configured:</span></span>

- <span data-ttu-id="99503-124">使用參考資料擁有者 SharePoint 群組中，具有**研究-Admins**安全性群組的成員身分的完全控制 」 權限等級</span><span class="sxs-lookup"><span data-stu-id="99503-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="99503-125">使用 [參考成員] SharePoint 群組中，具有**Research 成員**安全性群組的成員身分的編輯權限等級</span><span class="sxs-lookup"><span data-stu-id="99503-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="99503-126">使用 Research 訪客 SharePoint 群組，其為成員的 [**參考資料檢視**安全性] 群組的讀取權限等級</span><span class="sxs-lookup"><span data-stu-id="99503-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="99503-127">以下是所產生的 SharePoint 權限等級、 SharePoint 群組和其成員。</span><span class="sxs-lookup"><span data-stu-id="99503-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="99503-128">接下來，其設定之網站的其他限制。</span><span class="sxs-lookup"><span data-stu-id="99503-128">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="99503-129">如設定的詳細資訊，請參閱[部署隔離的 SharePoint Online 小組網站](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)。</span><span class="sxs-lookup"><span data-stu-id="99503-129">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="99503-130">步驟 3： 設定嚴格的 DLP 原則的網站</span><span class="sxs-lookup"><span data-stu-id="99503-130">Step 3: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="99503-131">首先，Contoso 系統管理員套用**Research**網站的**高度機密**的 Office 365 保留標籤。</span><span class="sxs-lookup"><span data-stu-id="99503-131">First, Contoso admins applied the **Highly Confidential** Office 365 retention label to the **Research** site.</span></span>

<span data-ttu-id="99503-132">接下來，建立新的 Office 365 DLP 原則名為**Research**的：</span><span class="sxs-lookup"><span data-stu-id="99503-132">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="99503-133">使用**高度機密**的 Office 365 保留標籤。</span><span class="sxs-lookup"><span data-stu-id="99503-133">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="99503-134">會套用至**Research**網站。</span><span class="sxs-lookup"><span data-stu-id="99503-134">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="99503-135">防止使用者共用文件。</span><span class="sxs-lookup"><span data-stu-id="99503-135">Prevents users from sharing documents.</span></span>

<span data-ttu-id="99503-136">如設定的詳細資訊，請參閱 <<c0>使用 Office 365 標籤與 DLP 保護 SharePoint Online 檔案。</span><span class="sxs-lookup"><span data-stu-id="99503-136">For the configuration details, see [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="99503-137">步驟 4： 建立網站的 Azure 資訊保護子標籤</span><span class="sxs-lookup"><span data-stu-id="99503-137">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="99503-138">Contoso 系統管理員建立新的 Azure 資訊保護子標籤名為**Research**的預設**高度機密**] 標籤中的限域原則的：</span><span class="sxs-lookup"><span data-stu-id="99503-138">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="99503-139">需要加密。</span><span class="sxs-lookup"><span data-stu-id="99503-139">Requires encryption.</span></span>
- <span data-ttu-id="99503-140">允許完整存取**Research 成員**的 [安全性] 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="99503-140">Allows full access by members of the **Research-Members** security group.</span></span>
- <span data-ttu-id="99503-141">允許讀取權限由**參考資料檢視**的 [安全性] 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="99503-141">Allows read access by members of the **Research-Viewers** security group.</span></span>

<span data-ttu-id="99503-142">接下來，這些部署的 Azure 資訊保護用戶端裝置的研究小組成員。</span><span class="sxs-lookup"><span data-stu-id="99503-142">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="99503-143">如設定的詳細資訊，請參閱[使用 Azure 資訊保護保護 SharePoint Online 檔案](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)。</span><span class="sxs-lookup"><span data-stu-id="99503-143">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="99503-144">以下是高度機密資產的**研究**網站所產生的組態。</span><span class="sxs-lookup"><span data-stu-id="99503-144">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="99503-145">**研究**站台的資料夾中的檔案受到：</span><span class="sxs-lookup"><span data-stu-id="99503-145">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="99503-146">**研究**Azure 資訊保護子標籤，適用於加密和使用權檔案會對每個檔案已移動或複製從**Research**網站。</span><span class="sxs-lookup"><span data-stu-id="99503-146">The **Research** Azure Information Protection sublabel, which applies encryption and permssions to each file that travel with the file when it is moved or copied from the **Research** site.</span></span>
- <span data-ttu-id="99503-147">**研究**DLP 原則，會使用**高度機密**的保留標籤和離開網站時，防止檔案的設定。</span><span class="sxs-lookup"><span data-stu-id="99503-147">The **Research** DLP policy, which uses the **Highly Sensitive** retention label and settings that prevent the file from leaving the site.</span></span>
- <span data-ttu-id="99503-148">網站權限，只允許存取成員**Research 成員**和**參考資料檢視者**安全性群組和管理由**Research Admins**安全性群組的成員集合。</span><span class="sxs-lookup"><span data-stu-id="99503-148">The set of site permissions, which only allow access to members of the **Research-Members** and **Research-Viewers** security groups and administration by members of the **Research-Admins** security group.</span></span>

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="99503-149">步驟 5： 移轉的內部部署 SharePoint research 資料</span><span class="sxs-lookup"><span data-stu-id="99503-149">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="99503-150">Contoso 系統管理員移動所有內部研發網站中的內部部署 SharePoint Server 2016 中新**的參考資料**的 SharePoint Online 站台資料夾的檔案。</span><span class="sxs-lookup"><span data-stu-id="99503-150">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="99503-151">步驟 6： 訓練使用者</span><span class="sxs-lookup"><span data-stu-id="99503-151">Step 6: Trained their users</span></span> 

<span data-ttu-id="99503-152">Contoso 的安全性人員訓練逐步執行它們透過強制課程中的研究小組：</span><span class="sxs-lookup"><span data-stu-id="99503-152">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="99503-153">How to： 存取新的**研究**SharePoint Online 網站和其現有的檔案。</span><span class="sxs-lookup"><span data-stu-id="99503-153">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="99503-154">如何在網站上建立新檔案，以及上傳儲存在本機的新檔案。</span><span class="sxs-lookup"><span data-stu-id="99503-154">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="99503-155">示範 DLP 原則會封鎖從外部共用的檔案。</span><span class="sxs-lookup"><span data-stu-id="99503-155">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="99503-156">如何使用 Azure 資訊保護用戶端標籤具有**Research**子標籤的參考資料檔案。</span><span class="sxs-lookup"><span data-stu-id="99503-156">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="99503-157">**Research**子標籤如何保護檔案，即使它從網站遺漏的示範。</span><span class="sxs-lookup"><span data-stu-id="99503-157">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="99503-158">最後的結果是安全的環境研究人員可以共同在安全的環境中的組織。</span><span class="sxs-lookup"><span data-stu-id="99503-158">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="99503-159">如果從**Research**網站遺漏研究文件與**研究**子標籤，它會經過加密並且只有具有有效認證**Research 成員**和**參考資料檢視**安全性群組的成員可以存取。</span><span class="sxs-lookup"><span data-stu-id="99503-159">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research-Members** and **Research-Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="99503-160">下一步</span><span class="sxs-lookup"><span data-stu-id="99503-160">Next step</span></span>

<span data-ttu-id="99503-161">[部署](deploy-microsoft-365-enterprise.md)Microsoft 365 企業版，您組織中。</span><span class="sxs-lookup"><span data-stu-id="99503-161">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

