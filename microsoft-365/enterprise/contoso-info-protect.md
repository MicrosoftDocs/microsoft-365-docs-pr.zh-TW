---
title: Contoso Corporation 的資訊保護
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft 365 企業版中的資訊保護功能，在雲端中保護其數位資產。
ms.openlocfilehash: f0869dfd661ae4dbaed74fdfd660c863deb20175
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276110"
---
# <a name="information-protection-for-the-contoso-corporation"></a><span data-ttu-id="d28ac-103">Contoso Corporation 的資訊保護</span><span class="sxs-lookup"><span data-stu-id="d28ac-103">Information protection for the Contoso Corporation</span></span>

<span data-ttu-id="d28ac-104">**摘要：** 了解 Contoso 如何使用 Microsoft 365 企業版中的資訊保護功能，在雲端中保護其數位資產。</span><span class="sxs-lookup"><span data-stu-id="d28ac-104">**Summary:** Understand how Contoso uses information protection features in Microsoft 365 Enterprise to secure their digital assets in the cloud.</span></span>

<span data-ttu-id="d28ac-p101">Contoso 相當嚴正地看待其資訊安全性和保護。例如，智慧財產權的外洩或損毀，說明產品設計和專屬製造技術會讓他們處於競爭的劣勢當中。</span><span class="sxs-lookup"><span data-stu-id="d28ac-p101">Contoso is serious about their information security and protection. For example, leakage or destruction of their intellectual property describing product designs and proprietary manufacturing techniques would place them at a competitive disadvantage.</span></span>

<span data-ttu-id="d28ac-107">在將機密和最有價值的資產移至雲端之前，他們要確定在 Microsoft 365 企業版的雲端式服務中，支援及實作他們的內部部署資訊分類和保護需求。</span><span class="sxs-lookup"><span data-stu-id="d28ac-107">Before moving their sensitive and most valuable digital assets to the cloud, they made sure that their on-premises information classification and protection requirements were supported and implemented in the cloud-based services of Microsoft 365 Enterprise.</span></span>

## <a name="contosos-data-security-classification"></a><span data-ttu-id="d28ac-108">Contoso 的資料安全性分類</span><span class="sxs-lookup"><span data-stu-id="d28ac-108">Contoso's data security classification</span></span>

<span data-ttu-id="d28ac-109">Contoso 執行資料分析，並且決定下列層級。</span><span class="sxs-lookup"><span data-stu-id="d28ac-109">Contoso performed an analysis of their data and determined the following levels.</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="d28ac-110">**第 1 級：基準**</span><span class="sxs-lookup"><span data-stu-id="d28ac-110">**Level 1: Baseline**</span></span> | <span data-ttu-id="d28ac-111">**第 2 級：機密**</span><span class="sxs-lookup"><span data-stu-id="d28ac-111">**Level 2: Sensitive**</span></span> | <span data-ttu-id="d28ac-112">**第 3 級：高管制**</span><span class="sxs-lookup"><span data-stu-id="d28ac-112">**Level 3: Highly regulated**</span></span> |
| <span data-ttu-id="d28ac-113">資料經過加密並且僅提供給已驗證的使用者</span><span class="sxs-lookup"><span data-stu-id="d28ac-113">Data is encrypted and available only to authenticated users</span></span> <BR> <BR> <span data-ttu-id="d28ac-p102">專為儲存在內部部署及雲端式儲存空間和工作負載 (例如 Office 365) 的所有資料而提供。資料會予以加密，並儲存於服務中，而且會在服務和用戶端裝置之間傳輸。</span><span class="sxs-lookup"><span data-stu-id="d28ac-p102">Provided for all data stored on premises and in cloud-based storage and workloads, such as Office 365. Data is encrypted while it resides in the service and in transit between the service and client devices.</span></span> <BR><BR> <span data-ttu-id="d28ac-116">第 1 級的範例：一般業務通訊 (電子郵件) 和用於行政、銷售和支援員工的檔案之資料。</span><span class="sxs-lookup"><span data-stu-id="d28ac-116">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span> | <span data-ttu-id="d28ac-117">第 1 級再加上增強式驗證及資料遺失保護</span><span class="sxs-lookup"><span data-stu-id="d28ac-117">Level 1 plus strong authentication and data loss protection:</span></span> <BR> <BR> <span data-ttu-id="d28ac-p103">增強式驗證包含利用簡訊驗證的多重要素驗證與，而資料遺失保護則確保敏感或重要的資料不會外流傳至內部部署網路以外的地方。</span><span class="sxs-lookup"><span data-stu-id="d28ac-p103">Strong authentication includes multi-factor authentication with SMS validation. Data loss prevention ensures that sensitive or critical information does not travel outside the on-premises network.</span></span> <BR><BR> <span data-ttu-id="d28ac-120">第 2 級的範例：財務和法務資訊以及新產品的研發資料。</span><span class="sxs-lookup"><span data-stu-id="d28ac-120">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span> | <span data-ttu-id="d28ac-121">第 2 級再加上最高層級的加密、驗證及稽核。</span><span class="sxs-lookup"><span data-stu-id="d28ac-121">Level 2 plus the highest levels of encryption, authentication, and auditing.</span></span> <BR> <BR>  <span data-ttu-id="d28ac-122">對靜態資料和雲端資料的最高層級資料加密，遵循地區法規，結合多重要素驗證與智慧卡以及細微稽核與警示。</span><span class="sxs-lookup"><span data-stu-id="d28ac-122">The highest levels of encryption for data at rest and in the cloud, compliant with regional regulations, combined with multi-factor authentication with smart cards and granular auditing and alerting.</span></span> <BR> <BR> <span data-ttu-id="d28ac-123">第 3 級的範例：客戶與合作夥伴的個人身分識別資訊，以及產品的工程規格和專屬的製造技術。</span><span class="sxs-lookup"><span data-stu-id="d28ac-123">Examples of Level 3 data are customer and partner personally identifiable information, product engineering specifications, and proprietary manufacturing techniques.</span></span>  |
||||

## <a name="contosos-information-policies"></a><span data-ttu-id="d28ac-124">Contoso 的資訊原則</span><span class="sxs-lookup"><span data-stu-id="d28ac-124">Contoso's information policies</span></span>
<span data-ttu-id="d28ac-125">下表列出 Contoso 的資訊原則。</span><span class="sxs-lookup"><span data-stu-id="d28ac-125">The following table lists Contoso's information policies.</span></span>

|||||
|:-------|:-----|:-----|:-----|
|  | <span data-ttu-id="d28ac-126">**存取**</span><span class="sxs-lookup"><span data-stu-id="d28ac-126">**Access**</span></span> | <span data-ttu-id="d28ac-127">**資料保留**</span><span class="sxs-lookup"><span data-stu-id="d28ac-127">**Data retention**</span></span> | <span data-ttu-id="d28ac-128">**資訊保護**</span><span class="sxs-lookup"><span data-stu-id="d28ac-128">**Information protection**</span></span> |
| <span data-ttu-id="d28ac-129">低商業價值 (第 1 級：基準)</span><span class="sxs-lookup"><span data-stu-id="d28ac-129">Low business value (Level 1: Baseline)</span></span> | <span data-ttu-id="d28ac-130">允許所有人存取</span><span class="sxs-lookup"><span data-stu-id="d28ac-130">Allow access to all</span></span>  | <span data-ttu-id="d28ac-131">6 個月</span><span class="sxs-lookup"><span data-stu-id="d28ac-131">6 months</span></span> | <span data-ttu-id="d28ac-132">使用加密</span><span class="sxs-lookup"><span data-stu-id="d28ac-132">Use encryption</span></span> |
| <span data-ttu-id="d28ac-133">中等商業價值 (第 2 級：敏感性)</span><span class="sxs-lookup"><span data-stu-id="d28ac-133">Medium business value (Level 2: Sensitive)</span></span> | <span data-ttu-id="d28ac-134">允許 Contoso 員工、次承攬人和合作夥伴存取</span><span class="sxs-lookup"><span data-stu-id="d28ac-134">Allow access to Contoso employees, subcontractors, and partners</span></span> <BR> <BR> <span data-ttu-id="d28ac-135">使用多重要素驗證 (MFA)、傳輸層安全性 (TLS) 和行動裝置應用程式管理 (MAM)</span><span class="sxs-lookup"><span data-stu-id="d28ac-135">Use multi-factor authentication (MFA), Transport Layer Security (TLS), and Mobile Application Management (MAM)</span></span> | <span data-ttu-id="d28ac-136">2 年</span><span class="sxs-lookup"><span data-stu-id="d28ac-136">2 years</span></span>  | <span data-ttu-id="d28ac-137">使用雜湊值以確保資料完整</span><span class="sxs-lookup"><span data-stu-id="d28ac-137">Use hash values for data integrity</span></span>  |
| <span data-ttu-id="d28ac-138">高商業價值 (第 3 級：高管制)</span><span class="sxs-lookup"><span data-stu-id="d28ac-138">High business value (Level 3: Highly regulated)</span></span> | <span data-ttu-id="d28ac-139">允許高階主管以及工程部和製造部的主管存取</span><span class="sxs-lookup"><span data-stu-id="d28ac-139">Allow access to executives and leads in engineering and manufacturing</span></span> <BR> <BR> <span data-ttu-id="d28ac-140">版權管理系統 (RMS)，只有受控網路裝置</span><span class="sxs-lookup"><span data-stu-id="d28ac-140">Rights Management System (RMS) with managed network devices only</span></span>  | <span data-ttu-id="d28ac-141">7 年</span><span class="sxs-lookup"><span data-stu-id="d28ac-141">7 years</span></span>  | <span data-ttu-id="d28ac-142">使用數位簽章以提供不可否認性</span><span class="sxs-lookup"><span data-stu-id="d28ac-142">Use digital signatures for non-repudiation</span></span>  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-enterprise"></a><span data-ttu-id="d28ac-143">Contoso 使用 Microsoft 365 企業版進行資訊保護的途徑</span><span class="sxs-lookup"><span data-stu-id="d28ac-143">Contoso’s path to information protection with Microsoft 365 Enterprise</span></span>

<span data-ttu-id="d28ac-144">Contoso 使用下列步驟，針對其資訊保護需求準備 Microsoft 365 企業版：</span><span class="sxs-lookup"><span data-stu-id="d28ac-144">Contoso used the following steps to prepare Microsoft 365 Enterprise for their information protection requirements:</span></span>

1. <span data-ttu-id="d28ac-145">識別要保護的資訊</span><span class="sxs-lookup"><span data-stu-id="d28ac-145">Identified what information to protect</span></span>

   <span data-ttu-id="d28ac-146">Contoso 大量檢閱內部部署 SharePoint 網站和檔案共用上的現有數位資產，並且對每個項目進行分類。</span><span class="sxs-lookup"><span data-stu-id="d28ac-146">Contoso did an extensive review of their existing digital assets located on on-premises SharePoint sites and file shares and classified each one.</span></span>

2. <span data-ttu-id="d28ac-147">判別各資料層級的存取權、保留期和資訊保護原則</span><span class="sxs-lookup"><span data-stu-id="d28ac-147">Determined access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="d28ac-148">Contoso 根據資料層級決定原則需求，這些原則需求是用來在移至雲端時保護現有的數位資產。</span><span class="sxs-lookup"><span data-stu-id="d28ac-148">Based on the data levels, Contoso determined detailed policy requirements, which were used to protect existing digital assets as they were moved to the cloud.</span></span>

3. <span data-ttu-id="d28ac-149">針對不同的資訊層級建立敏感度標籤及其設定</span><span class="sxs-lookup"><span data-stu-id="d28ac-149">Created Azure Information Protection labels and their settings for the different levels of information</span></span>

   <span data-ttu-id="d28ac-150">Contoso 針對其資料層級建立了敏感度標籤，其中包括加密、權限和浮水印等敏感性和高管制標籤。</span><span class="sxs-lookup"><span data-stu-id="d28ac-150">Contoso created sensitivity labels for their data levels, with sensitive and highly regulated label including encryption, permissions, and watermarks.</span></span>

4. <span data-ttu-id="d28ac-151">針對機密和高管制資料建立受保護的 SharePoint Online 網站，具有鎖定存取的權限</span><span class="sxs-lookup"><span data-stu-id="d28ac-151">Created protected SharePoint Online sites for sensitive and highly regulated data with permissions that lock down access</span></span>

   <span data-ttu-id="d28ac-152">機密和高管制網站均已設定為[隔離網站](https://docs.microsoft.com/office365/enterprise/isolated-sharepoint-online-team-sites)，在其中預設 SharePoint Online 小組網站的權限已自訂為 Azure Active Directory (Azure AD) 群組。</span><span class="sxs-lookup"><span data-stu-id="d28ac-152">Both sensitive and highly regulated sites were configured as [isolated sites](https://docs.microsoft.com/office365/enterprise/isolated-sharepoint-online-team-sites), in which the default SharePoint Online team site permissions were customized to Azure Active Directory (Azure AD) groups.</span></span> <span data-ttu-id="d28ac-153">此外，也以使用對應的保留標籤來設定敏感性和高管制 SharePoint Online 網站。</span><span class="sxs-lookup"><span data-stu-id="d28ac-153">Sensitive and highly regulated SharePoint Online sites were also configured with a corrresponding retention label.</span></span> <span data-ttu-id="d28ac-154">儲存在高管制 SharePoint Online 網站中的檔案受到高管制敏感度標籤保護。</span><span class="sxs-lookup"><span data-stu-id="d28ac-154">Files stored in highly regulated SharePoint Online sites are protected with the Highly Regulated sensitivity label.</span></span> <span data-ttu-id="d28ac-155">如需詳細資訊，請參閱[適用於高管制資料的 Microsoft Teams 和 SharePoint Online 網站](teams-sharepoint-online-sites-highly-regulated-data.md)案例。</span><span class="sxs-lookup"><span data-stu-id="d28ac-155">For more information, see the [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md) scenario.</span></span>

5.  <span data-ttu-id="d28ac-156">從內部部署 SharePoint 網站和檔案共用將資料移至新的 SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="d28ac-156">Moved data from on-premises SharePoint sites and file shares to their new SharePoint Online sites</span></span>

    <span data-ttu-id="d28ac-157">遷移至新 SharePoint Online 網站的檔案，會繼承指派給網站的預設保留標籤。</span><span class="sxs-lookup"><span data-stu-id="d28ac-157">The files migrated to the new SharePoint Online sites inherited the default Office 365 labels assigned to the site.</span></span>

6.  <span data-ttu-id="d28ac-158">訓練員工如何針對新文件使用敏感度標籤、如何在建立新 SharePoint Online 網站時與 Contoso IT 互動，以及一律將數位資產儲存在 SharePoint Online 網站上</span><span class="sxs-lookup"><span data-stu-id="d28ac-158">Trained employees on how to use Azure Information Protection labels for new documents, how to interact with Contoso IT when creating new SharePoint Online sites, and to always store digital assets on SharePoint Online sites</span></span>

    <span data-ttu-id="d28ac-159">這個部分是雲端資訊保護轉換最困難的部分，Contoso IT 和管理階層必須改變組織員工總是在雲端儲存及標示其數位資產、抑制使用內部部署檔案共用，而從不使用第三方雲端儲存服務或 USB 磁碟機這樣的一個資訊儲存壞習慣。</span><span class="sxs-lookup"><span data-stu-id="d28ac-159">Considered the hardest part of the information protection transition for the cloud, Contoso IT and management needed to change the bad information storage habits of the organization’s employees to always store and label their digital assets in the cloud, refrain from using on-premises file shares, and never use third-party cloud storage services or USB drives.</span></span>

## <a name="conditional-access-policies-for-information-protection"></a><span data-ttu-id="d28ac-160">資訊保護的條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="d28ac-160">Conditional access policies for information protection</span></span>

<span data-ttu-id="d28ac-161">搭配其身分識別和行動裝置管理基礎結構，以及作為推出 Exchange Online 和 SharePoint Online 的一部分，Contoso 設定下列條件式存取原則集合，並且將該集合套用至適當的 Azure AD 群組：</span><span class="sxs-lookup"><span data-stu-id="d28ac-161">In conjunction with their identity and mobile device management infrastructure and as part of their rollout of Exchange Online and SharePoint Online, Contoso configured the following set of conditional access policies and applied them to the appropriate Azure AD groups:</span></span>

- [<span data-ttu-id="d28ac-162">裝置原則的受控和非受控應用程式存取</span><span class="sxs-lookup"><span data-stu-id="d28ac-162">Managed and unmanaged application access on devices policies</span></span>](identity-access-policies.md)
- [<span data-ttu-id="d28ac-163">Exchange Online 存取原則</span><span class="sxs-lookup"><span data-stu-id="d28ac-163">Exchange Online access policies</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="d28ac-164">SharePoint Online 存取原則</span><span class="sxs-lookup"><span data-stu-id="d28ac-164">SharePoint Online access policies</span></span>](sharepoint-file-access-policies.md)

<span data-ttu-id="d28ac-165">圖 1 顯示 Contoso 的資訊保護原則結果集合。</span><span class="sxs-lookup"><span data-stu-id="d28ac-165">Figure 1 shows Contoso's resulting set of policies for information protection.</span></span>

![](./media/contoso-info-protect/contoso-info-protect-fig1.png)

<span data-ttu-id="d28ac-166">**圖 1：裝置、Exchange Online 和 SharePoint Online 條件式存取原則**</span><span class="sxs-lookup"><span data-stu-id="d28ac-166">**Figure 1: Device, Exchange Online, and SharePoint Online conditional access policies**</span></span>
 
>[!Note]
><span data-ttu-id="d28ac-p105">Contoso 也會為身分識別和登入設定額外的條件式存取原則。請參閱 [Contoso Corporation 的身分識別](contoso-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="d28ac-p105">Contoso also configured additional conditional access policies for identity and sign-in. See [Identity for the Contoso Corporation](contoso-identity.md).</span></span>
>

<span data-ttu-id="d28ac-169">這些原則會確保：</span><span class="sxs-lookup"><span data-stu-id="d28ac-169">These policies ensure that:</span></span>

- <span data-ttu-id="d28ac-170">允許使用應用程式，並由應用程式保護原則定義這些應用程式可以對組織資料執行哪些動作。</span><span class="sxs-lookup"><span data-stu-id="d28ac-170">Apps are allowed and the actions they can take with your organization data are defined by app protection policies.</span></span>
- <span data-ttu-id="d28ac-171">電腦和行動裝置都必須符合規範。</span><span class="sxs-lookup"><span data-stu-id="d28ac-171">PCs and mobile devices must be compliant.</span></span>
- <span data-ttu-id="d28ac-172">Exchange Online 使用適用於 Exchange Online 的 Office 365 訊息加密。</span><span class="sxs-lookup"><span data-stu-id="d28ac-172">Exchange Online uses Office 365 message encryption for Exchange Online.</span></span>
- <span data-ttu-id="d28ac-173">SharePoint Online 會使用應用程式強制限制。</span><span class="sxs-lookup"><span data-stu-id="d28ac-173">SharePoint Online uses app enforced restrictions.</span></span>
- <span data-ttu-id="d28ac-174">SharePoint Online 會針對僅限瀏覽器存取使用存取控制原則，並封鎖未受控裝置的存取。</span><span class="sxs-lookup"><span data-stu-id="d28ac-174">SharePoint Online uses access control policies for browser-only access and to block access for unmanaged devices.</span></span>

## <a name="mapping-microsoft-365-enterprise-features-to-contosos-data-levels"></a><span data-ttu-id="d28ac-175">將 Microsoft 365 企業版功能對應至 Contoso 的資料層級</span><span class="sxs-lookup"><span data-stu-id="d28ac-175">Mapping Microsoft 365 Enterprise features to Contoso's data levels</span></span>

<span data-ttu-id="d28ac-176">下表顯示 Contoso 資料層級與 Microsoft 365 企業版資訊保護功能的對應。</span><span class="sxs-lookup"><span data-stu-id="d28ac-176">The following table shows the mapping the Contoso's data levels to information protection features in Microsoft 365 Enterprise.</span></span>

|||||
|:-------|:-----|:-----|:-----|
| | <span data-ttu-id="d28ac-177">**Office 365**</span><span class="sxs-lookup"><span data-stu-id="d28ac-177">**Office 365**</span></span> | <span data-ttu-id="d28ac-178">**Windows 10 和 Office 365 專業增強版**</span><span class="sxs-lookup"><span data-stu-id="d28ac-178">**Windows 10 and Office 365 ProPlus**</span></span> | <span data-ttu-id="d28ac-179">**EMS**</span><span class="sxs-lookup"><span data-stu-id="d28ac-179">**EMS**</span></span> |
| <span data-ttu-id="d28ac-180">第 1 級：基準</span><span class="sxs-lookup"><span data-stu-id="d28ac-180">Level 1: Baseline</span></span>  | <span data-ttu-id="d28ac-181">SharePoint Online 和 Exchange Online 條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="d28ac-181">SharePoint Online and Exchange Online conditional access policies</span></span> <BR> <span data-ttu-id="d28ac-182">SharePoint Online 網站的權限</span><span class="sxs-lookup"><span data-stu-id="d28ac-182">Permissions on SharePoint Online sites</span></span> | <span data-ttu-id="d28ac-183">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="d28ac-183">Sensitivity labels</span></span> <BR> <span data-ttu-id="d28ac-184">BitLocker</span><span class="sxs-lookup"><span data-stu-id="d28ac-184">BitLocker</span></span> <BR> <span data-ttu-id="d28ac-185">Windows 資訊保護</span><span class="sxs-lookup"><span data-stu-id="d28ac-185">Windows Information Protection</span></span> | <span data-ttu-id="d28ac-186">裝置條件式存取原則和行動裝置應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="d28ac-186">Device conditional access policies and Mobile Application Management policies</span></span> |
| <span data-ttu-id="d28ac-187">第 2 級：敏感性</span><span class="sxs-lookup"><span data-stu-id="d28ac-187">Level 2: Sensitive</span></span> | <span data-ttu-id="d28ac-188">第 1 級增強版：</span><span class="sxs-lookup"><span data-stu-id="d28ac-188">Level 1: Baseline plus:</span></span> <BR> <BR> <span data-ttu-id="d28ac-189">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="d28ac-189">Sensitivity labels</span></span> <BR> <span data-ttu-id="d28ac-190">SharePoint Online 網站的 Office 365 標籤</span><span class="sxs-lookup"><span data-stu-id="d28ac-190">Office 365 labels on SharePoint Online sites</span></span> <BR> <span data-ttu-id="d28ac-191">SharePoint Online 和 Exchange Online 的 Office 365 資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="d28ac-191">Office 365 Data Loss Prevention for SharePoint Online and Exchange Online</span></span> <BR> <span data-ttu-id="d28ac-192">隔離的 SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="d28ac-192">Isolated SharePoint Online sites</span></span>  | <span data-ttu-id="d28ac-193">第 1 級增強版：</span><span class="sxs-lookup"><span data-stu-id="d28ac-193">Level 1: Baseline plus:</span></span> <BR> <BR> <span data-ttu-id="d28ac-194">數位資產上的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="d28ac-194">Sensitivity labels on digital assets</span></span> <BR> <span data-ttu-id="d28ac-195">Office 365 進階資料控管</span><span class="sxs-lookup"><span data-stu-id="d28ac-195">Office 365 Advanced Data Governance</span></span> | <span data-ttu-id="d28ac-196">第 1 級</span><span class="sxs-lookup"><span data-stu-id="d28ac-196">Level 1 Entry Point</span></span> |
| <span data-ttu-id="d28ac-197">第 3 級：高管制</span><span class="sxs-lookup"><span data-stu-id="d28ac-197">Level 3: Highly regulated</span></span> | <span data-ttu-id="d28ac-198">第 2 級增強版：</span><span class="sxs-lookup"><span data-stu-id="d28ac-198">Level 2: Highly sensitive plus:</span></span> <BR><BR> <span data-ttu-id="d28ac-199">針對營業秘密資訊的使用自己的金鑰 (BYOK) 加密和保護</span><span class="sxs-lookup"><span data-stu-id="d28ac-199">Bring Your Own Key (BYOK) encryption and protection for trade secret information</span></span> <BR> <span data-ttu-id="d28ac-200">適用於與 Office 365 服務互動之企業營運應用程式的 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="d28ac-200">Azure Key Vault for line of business applications that interact with Office 365 services</span></span> | <span data-ttu-id="d28ac-201">第 2 級</span><span class="sxs-lookup"><span data-stu-id="d28ac-201">Level: 2</span></span> | <span data-ttu-id="d28ac-202">第 1 級</span><span class="sxs-lookup"><span data-stu-id="d28ac-202">Level 1 Entry Point</span></span> |
|||||


## <a name="next-step"></a><span data-ttu-id="d28ac-203">下一步</span><span class="sxs-lookup"><span data-stu-id="d28ac-203">Next step</span></span>

<span data-ttu-id="d28ac-204">[請參閱](contoso-security-summary.md) Contoso 如何針對身分識別與存取管理、威脅防護、資訊保護和安全性管理，使用 Microsoft 365 企業版的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="d28ac-204">[See](contoso-security-summary.md) how Contoso has used the security features across Microsoft 365 Enterprise for identity and access management, threat protection, information protection, and security management.</span></span>

## <a name="see-also"></a><span data-ttu-id="d28ac-205">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d28ac-205">See also</span></span>

[<span data-ttu-id="d28ac-206">Microsoft 365 企業版的資訊保護</span><span class="sxs-lookup"><span data-stu-id="d28ac-206">Information protection for Microsoft 365 Enterprise</span></span>](infoprotect-infrastructure.md)

[<span data-ttu-id="d28ac-207">部署指南</span><span class="sxs-lookup"><span data-stu-id="d28ac-207">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d28ac-208">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="d28ac-208">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)


