---
title: Contoso Corporation 的資訊保護
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 瞭解 Contoso 如何使用 Microsoft 365 for enterprise 中的資訊保護功能，在雲端中保護其數位資產。
ms.openlocfilehash: 51740db9a0bb2e770e959fe8d9dcde15c042f5b8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637232"
---
# <a name="information-protection-for-the-contoso-corporation"></a><span data-ttu-id="b5db7-103">Contoso Corporation 的資訊保護</span><span class="sxs-lookup"><span data-stu-id="b5db7-103">Information protection for the Contoso Corporation</span></span>

<span data-ttu-id="b5db7-p101">Contoso 對其資訊安全性很重要。對其產品設計和專有製造技術相關的智慧財產權的洩漏或破壞會帶來競爭的劣勢。</span><span class="sxs-lookup"><span data-stu-id="b5db7-p101">Contoso is serious about their information security. Leakage or destruction of intellectual property that describes their product designs and proprietary manufacturing techniques would place them at a competitive disadvantage.</span></span>

<span data-ttu-id="b5db7-106">在將其機密數位資產移至雲端之前，Contoso 確定 Microsoft 365 for enterprise 的雲端架構服務是否支援其內部部署資訊分類及保護需求。</span><span class="sxs-lookup"><span data-stu-id="b5db7-106">Before moving their sensitive digital assets to the cloud, Contoso made sure that their on-premises information classification and protection requirements were supported by the cloud-based services of Microsoft 365 for enterprise.</span></span>

## <a name="contoso-data-security-classification"></a><span data-ttu-id="b5db7-107">Contoso 資料安全性分類</span><span class="sxs-lookup"><span data-stu-id="b5db7-107">Contoso data security classification</span></span>

<span data-ttu-id="b5db7-108">Contoso 執行其資料的分析，並確定下列分類層級。</span><span class="sxs-lookup"><span data-stu-id="b5db7-108">Contoso performed an analysis of their data and determined the following classification levels.</span></span>

| <span data-ttu-id="b5db7-109">第 1 級：基準</span><span class="sxs-lookup"><span data-stu-id="b5db7-109">Level 1: Baseline</span></span> | <span data-ttu-id="b5db7-110">第 2 級：敏感性</span><span class="sxs-lookup"><span data-stu-id="b5db7-110">Level 2: Sensitive</span></span> | <span data-ttu-id="b5db7-111">第 3 級：高管制</span><span class="sxs-lookup"><span data-stu-id="b5db7-111">Level 3: Highly regulated</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="b5db7-112">資料經過加密並且僅提供給已驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="b5db7-112">Data is encrypted and available only to authenticated users.</span></span><BR> <BR> <span data-ttu-id="b5db7-p102">針對所有儲存在內部部署和雲端架構存放區和工作負載中的資料提供。當資料位於服務中，且在服務和用戶端裝置之間傳輸時，會進行加密。</span><span class="sxs-lookup"><span data-stu-id="b5db7-p102">Provided for all data stored on-premises and in cloud-based storage and workloads. Data is encrypted while it resides in the service and in transit between the service and client devices.</span></span> <BR><BR><span data-ttu-id="b5db7-115">第 1 級的範例：一般業務通訊 (電子郵件) 和用於行政、銷售和支援員工的檔案之資料。</span><span class="sxs-lookup"><span data-stu-id="b5db7-115">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span> | <span data-ttu-id="b5db7-116">第 1 級再加上增強式驗證及資料遺失保護。</span><span class="sxs-lookup"><span data-stu-id="b5db7-116">Level 1 plus strong authentication and data loss protection.</span></span><BR> <BR> <span data-ttu-id="b5db7-117">增強式驗證包括使用 SMS 驗證的 Azure 多重要素驗證 (MFA)。</span><span class="sxs-lookup"><span data-stu-id="b5db7-117">Strong authentication includes Azure Multi-Factor Authentication (MFA) with SMS validation.</span></span> <span data-ttu-id="b5db7-118">資料遺失防護可確保敏感或重要資訊不會在 Microsoft 雲端外移動。</span><span class="sxs-lookup"><span data-stu-id="b5db7-118">Data loss prevention ensures that sensitive or critical information doesn't travel outside the Microsoft cloud.</span></span><BR><BR><span data-ttu-id="b5db7-119">第 2 級的範例：財務和法務資訊以及新產品的研發資料。</span><span class="sxs-lookup"><span data-stu-id="b5db7-119">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span> | <span data-ttu-id="b5db7-120">第 2 級再加上最高層級的加密、驗證及稽核。</span><span class="sxs-lookup"><span data-stu-id="b5db7-120">Level 2 plus the highest levels of encryption, authentication, and auditing.</span></span><BR><BR><span data-ttu-id="b5db7-121">對靜態資料和雲端資料的最高層級資料加密，遵循地區法規，結合 MFA 與智慧卡以及細微稽核與警示。</span><span class="sxs-lookup"><span data-stu-id="b5db7-121">The highest levels of encryption for data at rest and in the cloud, compliant with regional regulations, combined with MFA with smart cards and granular auditing and alerting.</span></span><BR> <BR><span data-ttu-id="b5db7-122">第3級資料範例包括客戶及合作夥伴個人資訊、產品工程規格，以及專屬的製造技術。</span><span class="sxs-lookup"><span data-stu-id="b5db7-122">Examples of Level 3 data are customer and partner personal information, product engineering specifications, and proprietary manufacturing techniques.</span></span>  |
||||

## <a name="contoso-information-policies"></a><span data-ttu-id="b5db7-123">Contoso 資訊原則</span><span class="sxs-lookup"><span data-stu-id="b5db7-123">Contoso information policies</span></span>
<span data-ttu-id="b5db7-124">下表列出 Contoso 資訊原則。</span><span class="sxs-lookup"><span data-stu-id="b5db7-124">The following table lists the Contoso information policies.</span></span>


| <span data-ttu-id="b5db7-125">值</span><span class="sxs-lookup"><span data-stu-id="b5db7-125">Value</span></span> | <span data-ttu-id="b5db7-126">Access</span><span class="sxs-lookup"><span data-stu-id="b5db7-126">Access</span></span> | <span data-ttu-id="b5db7-127">資料保留</span><span class="sxs-lookup"><span data-stu-id="b5db7-127">Data retention</span></span> | <span data-ttu-id="b5db7-128">資訊保護</span><span class="sxs-lookup"><span data-stu-id="b5db7-128">Information protection</span></span> |
|:-------|:-----|:-----|:-----|
| <span data-ttu-id="b5db7-129">低商業價值 (第 1 級：基準)</span><span class="sxs-lookup"><span data-stu-id="b5db7-129">Low business value (Level 1: Baseline)</span></span> | <span data-ttu-id="b5db7-130">允許存取所有。</span><span class="sxs-lookup"><span data-stu-id="b5db7-130">Allow access to all.</span></span>  | <span data-ttu-id="b5db7-131">6 個月</span><span class="sxs-lookup"><span data-stu-id="b5db7-131">6 months</span></span> | <span data-ttu-id="b5db7-132">使用加密。</span><span class="sxs-lookup"><span data-stu-id="b5db7-132">Use encryption.</span></span> |
| <span data-ttu-id="b5db7-133">中等商業價值 (第 2 級：敏感性)</span><span class="sxs-lookup"><span data-stu-id="b5db7-133">Medium business value (Level 2: Sensitive)</span></span> | <span data-ttu-id="b5db7-134">允許存取 Contoso 員工、分包商和合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="b5db7-134">Allow access to Contoso employees, subcontractors, and partners.</span></span> <BR><BR> <span data-ttu-id="b5db7-135">使用 MFA、傳輸層安全性 (TLS) 和行動裝置應用程式管理 (MAM)。</span><span class="sxs-lookup"><span data-stu-id="b5db7-135">Use MFA, Transport Layer Security (TLS), and Mobile Application Management (MAM).</span></span> | <span data-ttu-id="b5db7-136">2 年</span><span class="sxs-lookup"><span data-stu-id="b5db7-136">2 years</span></span>  | <span data-ttu-id="b5db7-137">使用雜湊值以確保資料完整。</span><span class="sxs-lookup"><span data-stu-id="b5db7-137">Use hash values for data integrity.</span></span>  |
| <span data-ttu-id="b5db7-138">高商業價值 (第 3 級：高管制)</span><span class="sxs-lookup"><span data-stu-id="b5db7-138">High business value (Level 3: Highly regulated)</span></span> | <span data-ttu-id="b5db7-139">允許高階主管以及工程部和製造部的主管存取。</span><span class="sxs-lookup"><span data-stu-id="b5db7-139">Allow access to executives and leads in engineering and manufacturing.</span></span> <BR> <BR> <span data-ttu-id="b5db7-140">版權管理系統 (RMS)，只有受控網路裝置。</span><span class="sxs-lookup"><span data-stu-id="b5db7-140">Rights Management System (RMS) with managed network devices only.</span></span>  | <span data-ttu-id="b5db7-141">7 年</span><span class="sxs-lookup"><span data-stu-id="b5db7-141">7 years</span></span>  | <span data-ttu-id="b5db7-142">使用數位簽章以提供不可否認性。</span><span class="sxs-lookup"><span data-stu-id="b5db7-142">Use digital signatures for non-repudiation.</span></span>  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a><span data-ttu-id="b5db7-143">Microsoft 365 for enterprise 的資訊保護的 Contoso 途徑</span><span class="sxs-lookup"><span data-stu-id="b5db7-143">The Contoso path to information protection with Microsoft 365 for enterprise</span></span>

<span data-ttu-id="b5db7-144">Contoso 遵循這些步驟，針對其資訊保護需求準備 Microsoft 365 for enterprise：</span><span class="sxs-lookup"><span data-stu-id="b5db7-144">Contoso followed these steps to prepare Microsoft 365 for enterprise for their information-protection requirements:</span></span>

1. <span data-ttu-id="b5db7-145">識別要保護的資訊</span><span class="sxs-lookup"><span data-stu-id="b5db7-145">Identify what information to protect</span></span>

   <span data-ttu-id="b5db7-146">Contoso 對內部部署 SharePoint 網站和檔案共用上的現有數位資產進行全面的審查，並對每個資產進行分類。</span><span class="sxs-lookup"><span data-stu-id="b5db7-146">Contoso did an extensive review of their existing digital assets located on on-premises SharePoint sites and file shares, and classified each asset.</span></span>

2. <span data-ttu-id="b5db7-147">決定資料層級的存取、保留和資訊保護原則</span><span class="sxs-lookup"><span data-stu-id="b5db7-147">Determine access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="b5db7-148">Contoso 根據資料層級決定原則需求，這些原則需求是用來在移至雲端時保護現有的數位資產。</span><span class="sxs-lookup"><span data-stu-id="b5db7-148">Based on the data levels, Contoso determined detailed policy requirements, which were used to protect existing digital assets as they were moved to the cloud.</span></span>

3. <span data-ttu-id="b5db7-149">為不同的資訊層級建立靈敏度標籤及其設定</span><span class="sxs-lookup"><span data-stu-id="b5db7-149">Create sensitivity labels and their settings for the different levels of information</span></span>

   <span data-ttu-id="b5db7-150">Contoso 針對其資料層級建立了敏感度標籤，以及包括加密、權限和浮水印等高管制標籤。</span><span class="sxs-lookup"><span data-stu-id="b5db7-150">Contoso created sensitivity labels for their data levels, with their highly regulated label that includes encryption, permissions, and watermarks.</span></span>

4.  <span data-ttu-id="b5db7-151">將資料從內部部署 SharePoint 網站和檔案共用移至新的 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="b5db7-151">Move data from on-premises SharePoint sites and file shares to their new SharePoint sites</span></span>

    <span data-ttu-id="b5db7-152">遷移至新 SharePoint 網站的檔案，會繼承指派給網站的預設保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b5db7-152">The files migrated to the new SharePoint sites inherited the default retention labels assigned to the site.</span></span>

5.  <span data-ttu-id="b5db7-153">訓練員工如何對新檔使用敏感度標籤，如何在建立新的 SharePoint 網站時與 Contoso 一起互動，以及永遠在 SharePoint 網站上儲存數位資產</span><span class="sxs-lookup"><span data-stu-id="b5db7-153">Train employees how to use sensitivity labels for new documents, how to interact with Contoso IT when creating new SharePoint sites, and to always store digital assets on SharePoint sites</span></span>

    <span data-ttu-id="b5db7-154">變更不良工作者資訊儲存習慣通常會被視為雲端的資訊保護轉換最困難的部分。</span><span class="sxs-lookup"><span data-stu-id="b5db7-154">Changing bad worker information-storage habits is often considered the hardest part of the information protection transition for the cloud.</span></span> <span data-ttu-id="b5db7-155">Contoso IT 和管理工作需要讓員工一定要在雲端中標籤和儲存其數位資產、避免使用內部部署檔案共用，也不會使用協力廠商雲端儲存服務或 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="b5db7-155">Contoso IT and management needed to get employees to always label and store their digital assets in the cloud, refrain from using on-premises file shares, and not use third-party cloud storage services or USB drives.</span></span>

## <a name="conditional-access-policies-for-information-protection"></a><span data-ttu-id="b5db7-156">資訊保護的條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="b5db7-156">Conditional Access policies for information protection</span></span>

<span data-ttu-id="b5db7-157">在 Exchange Online 和 SharePoint 的部署過程中，Contoso 設定下列一組條件式存取原則，並將它們套用至適當的群組：</span><span class="sxs-lookup"><span data-stu-id="b5db7-157">As part of their rollout of Exchange Online and SharePoint, Contoso configured the following set of Conditional Access policies and applied them to the appropriate groups:</span></span>

- [<span data-ttu-id="b5db7-158">裝置原則的受控和非受控應用程式存取</span><span class="sxs-lookup"><span data-stu-id="b5db7-158">Managed and unmanaged application access on devices policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="b5db7-159">Exchange Online 存取原則</span><span class="sxs-lookup"><span data-stu-id="b5db7-159">Exchange Online access policies</span></span>](../security/office-365-security/secure-email-recommended-policies.md)
- [<span data-ttu-id="b5db7-160">SharePoint 存取原則</span><span class="sxs-lookup"><span data-stu-id="b5db7-160">SharePoint access policies</span></span>](../security/office-365-security/sharepoint-file-access-policies.md)

<span data-ttu-id="b5db7-161">以下是設定資訊保護的 Contoso 原則所產生的結果。</span><span class="sxs-lookup"><span data-stu-id="b5db7-161">Here's resulting set of Contoso policies for information protection.</span></span>

![裝置、Exchange Online 和 SharePoint 條件式存取原則](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
><span data-ttu-id="b5db7-163">Contoso 也會為身分識別和登入設定額外的條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="b5db7-163">Contoso also configured additional Conditional Access policies for identity and sign-in.</span></span> <span data-ttu-id="b5db7-164">請參閱 [Contoso Corporation 的身分識別](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。</span><span class="sxs-lookup"><span data-stu-id="b5db7-164">See [Identity for the Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>
>

<span data-ttu-id="b5db7-165">這些原則會確保：</span><span class="sxs-lookup"><span data-stu-id="b5db7-165">These policies ensure that:</span></span>

- <span data-ttu-id="b5db7-166">允許的應用程式，以及他們可對組織的資料採取的動作，是由應用程式保護原則定義。</span><span class="sxs-lookup"><span data-stu-id="b5db7-166">Apps that are allowed and the actions they can take with the organization's data are defined by app protection policies.</span></span>
- <span data-ttu-id="b5db7-167">電腦和行動裝置都必須符合規範。</span><span class="sxs-lookup"><span data-stu-id="b5db7-167">PCs and mobile devices must be compliant.</span></span>
- <span data-ttu-id="b5db7-168">Exchange Online 使用 Office 365 郵件加密 (OME) 用於 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b5db7-168">Exchange Online uses Office 365 message encryption (OME) for Exchange Online.</span></span>
- <span data-ttu-id="b5db7-169">SharePoint 會使用應用程式強制性限制。</span><span class="sxs-lookup"><span data-stu-id="b5db7-169">SharePoint uses app-enforced restrictions.</span></span>
- <span data-ttu-id="b5db7-170">SharePoint 會針對僅限瀏覽器存取使用存取控制原則，並封鎖未受控裝置的存取。</span><span class="sxs-lookup"><span data-stu-id="b5db7-170">SharePoint uses access control policies for browser-only access and to block access for unmanaged devices.</span></span>

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a><span data-ttu-id="b5db7-171">將 Microsoft 365 企業版功能對應至 Contoso 資料層級</span><span class="sxs-lookup"><span data-stu-id="b5db7-171">Mapping Microsoft 365 for enterprise features to Contoso data levels</span></span>

<span data-ttu-id="b5db7-172">下表將 Contoso 資料層級對應至 Microsoft 365 for enterprise 中的資訊保護功能。</span><span class="sxs-lookup"><span data-stu-id="b5db7-172">The following table maps Contoso data levels to information protection features in Microsoft 365 for enterprise.</span></span>

| <span data-ttu-id="b5db7-173">層級</span><span class="sxs-lookup"><span data-stu-id="b5db7-173">Level</span></span> | <span data-ttu-id="b5db7-174">Microsoft 365 雲端服務</span><span class="sxs-lookup"><span data-stu-id="b5db7-174">Microsoft 365 cloud services</span></span> | <span data-ttu-id="b5db7-175">Windows 10 和 Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="b5db7-175">Windows 10 and Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="b5db7-176">安全性與合規性</span><span class="sxs-lookup"><span data-stu-id="b5db7-176">Security and compliance</span></span> |
|:-------|:-----|:-----|:-----|
| <span data-ttu-id="b5db7-177">第 1 級：基準</span><span class="sxs-lookup"><span data-stu-id="b5db7-177">Level 1: Baseline</span></span>  | <span data-ttu-id="b5db7-178">SharePoint 和 Exchange Online 條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="b5db7-178">SharePoint and Exchange Online Conditional Access policies</span></span> <BR> <span data-ttu-id="b5db7-179">SharePoint 網站的權限</span><span class="sxs-lookup"><span data-stu-id="b5db7-179">Permissions on SharePoint sites</span></span> | <span data-ttu-id="b5db7-180">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="b5db7-180">Sensitivity labels</span></span> <BR> <span data-ttu-id="b5db7-181">BitLocker</span><span class="sxs-lookup"><span data-stu-id="b5db7-181">BitLocker</span></span> <BR> <span data-ttu-id="b5db7-182">Windows 資訊保護</span><span class="sxs-lookup"><span data-stu-id="b5db7-182">Windows Information Protection</span></span> | <span data-ttu-id="b5db7-183">裝置條件式存取原則和行動裝置應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="b5db7-183">Device Conditional Access policies and Mobile Application Management policies</span></span> |
| <span data-ttu-id="b5db7-184">第 2 級：敏感性</span><span class="sxs-lookup"><span data-stu-id="b5db7-184">Level 2: Sensitive</span></span> | <span data-ttu-id="b5db7-185">第 1 級增強版：</span><span class="sxs-lookup"><span data-stu-id="b5db7-185">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="b5db7-186">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="b5db7-186">Sensitivity labels</span></span> <BR> <span data-ttu-id="b5db7-187">SharePoint 網站上的 Microsoft 365 保留標籤</span><span class="sxs-lookup"><span data-stu-id="b5db7-187">Microsoft 365 retention labels on SharePoint sites</span></span> <BR> <span data-ttu-id="b5db7-188">SharePoint 和 Exchange Online 的資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="b5db7-188">Data Loss Prevention for SharePoint and Exchange Online</span></span> <BR> <span data-ttu-id="b5db7-189">隔離的 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="b5db7-189">Isolated SharePoint sites</span></span>  | <span data-ttu-id="b5db7-190">第 1 級增強版：</span><span class="sxs-lookup"><span data-stu-id="b5db7-190">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="b5db7-191">數位資產上的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="b5db7-191">Sensitivity labels on digital assets</span></span>  | <span data-ttu-id="b5db7-192">第 1 級</span><span class="sxs-lookup"><span data-stu-id="b5db7-192">Level 1</span></span> |
| <span data-ttu-id="b5db7-193">第 3 級：高管制</span><span class="sxs-lookup"><span data-stu-id="b5db7-193">Level 3: Highly regulated</span></span> | <span data-ttu-id="b5db7-194">第 2 級增強版：</span><span class="sxs-lookup"><span data-stu-id="b5db7-194">Level 2 plus:</span></span> <BR><BR> <span data-ttu-id="b5db7-195">讓您自己的金鑰 (BYOK) 加密及保護貿易機密資訊</span><span class="sxs-lookup"><span data-stu-id="b5db7-195">Bring your own key (BYOK) encryption and protection for trade secret information</span></span> <BR> <span data-ttu-id="b5db7-196">與 Microsoft 365 服務互動的企業營運應用程式的 Azure 金鑰 Vault</span><span class="sxs-lookup"><span data-stu-id="b5db7-196">Azure Key Vault for line-of-business applications that interact with Microsoft 365 services</span></span> | <span data-ttu-id="b5db7-197">第 2 級</span><span class="sxs-lookup"><span data-stu-id="b5db7-197">Level 2</span></span> | <span data-ttu-id="b5db7-198">第 1 級</span><span class="sxs-lookup"><span data-stu-id="b5db7-198">Level 1</span></span> |
|||||

<span data-ttu-id="b5db7-199">以下是所產生的 Contoso 資訊保護設定。</span><span class="sxs-lookup"><span data-stu-id="b5db7-199">Here's the resulting Contoso information-protection configuration.</span></span>

![Contoso 的資訊保護設定結果](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a><span data-ttu-id="b5db7-201">下一步</span><span class="sxs-lookup"><span data-stu-id="b5db7-201">Next step</span></span>

<span data-ttu-id="b5db7-202">[請參閱](contoso-security-summary.md) Contoso 如何針對身分識別與存取管理、威脅防護、資訊保護和安全性管理，使用跨 Microsoft 365 的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="b5db7-202">[See](contoso-security-summary.md) how Contoso uses the security features across Microsoft 365 for enterprise for identity and access management, threat protection, information protection, and security management.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5db7-203">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b5db7-203">See also</span></span>

[<span data-ttu-id="b5db7-204">安全性藍圖</span><span class="sxs-lookup"><span data-stu-id="b5db7-204">Security roadmap</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)

[<span data-ttu-id="b5db7-205">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="b5db7-205">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b5db7-206">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="b5db7-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
