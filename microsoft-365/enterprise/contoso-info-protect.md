---
title: Contoso Corporation 的資訊保護
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft 365 企業版中的資訊保護功能，在雲端中保護其數位資產。
ms.openlocfilehash: d6167896c3e42c5fef373de7c5be7123467936f4
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831676"
---
# <a name="information-protection-for-the-contoso-corporation"></a><span data-ttu-id="3f2b7-103">Contoso Corporation 的資訊保護</span><span class="sxs-lookup"><span data-stu-id="3f2b7-103">Information protection for the Contoso Corporation</span></span>

<span data-ttu-id="3f2b7-p101">Contoso 相當嚴正地看待其資訊安全性和保護。例如，智慧財產權的外洩或損毀，說明產品設計和專屬製造技術會讓他們處於競爭的劣勢當中。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-p101">Contoso is serious about their information security and protection. For example, leakage or destruction of their intellectual property describing product designs and proprietary manufacturing techniques would place them at a competitive disadvantage.</span></span>

<span data-ttu-id="3f2b7-106">在將機密和最有價值的資產移至雲端之前，他們要確定在 Microsoft 365 企業版的雲端式服務中，支援及實作他們的內部部署資訊分類和保護需求。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-106">Before moving their sensitive and most valuable digital assets to the cloud, they made sure that their on-premises information classification and protection requirements were supported and implemented in the cloud-based services of Microsoft 365 Enterprise.</span></span>

## <a name="contosos-data-security-classification"></a><span data-ttu-id="3f2b7-107">Contoso 的資料安全性分類</span><span class="sxs-lookup"><span data-stu-id="3f2b7-107">Contoso's data security classification</span></span>

<span data-ttu-id="3f2b7-108">Contoso 執行資料分析，並且決定下列層級。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-108">Contoso performed an analysis of their data and determined the following levels.</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="3f2b7-109">**第 1 級：基準**</span><span class="sxs-lookup"><span data-stu-id="3f2b7-109">**Level 1: Baseline**</span></span> | <span data-ttu-id="3f2b7-110">**第 2 級：機密**</span><span class="sxs-lookup"><span data-stu-id="3f2b7-110">**Level 2: Sensitive**</span></span> | <span data-ttu-id="3f2b7-111">**第 3 級：高管制**</span><span class="sxs-lookup"><span data-stu-id="3f2b7-111">**Level 3: Highly regulated**</span></span> |
| <span data-ttu-id="3f2b7-112">資料經過加密並且僅提供給已驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-112">Data is encrypted and available only to authenticated users.</span></span> <BR> <BR> <span data-ttu-id="3f2b7-p102">專為儲存在內部部署及雲端式儲存空間和工作負載 (例如 Office 365) 的所有資料而提供。資料會予以加密，並儲存於服務中，而且會在服務和用戶端裝置之間傳輸。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-p102">Provided for all data stored on premises and in cloud-based storage and workloads, such as Office 365. Data is encrypted while it resides in the service and in transit between the service and client devices.</span></span> <BR><BR> <span data-ttu-id="3f2b7-115">第 1 級的範例：一般業務通訊 (電子郵件) 和用於行政、銷售和支援員工的檔案之資料。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-115">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span> | <span data-ttu-id="3f2b7-116">第 1 級再加上增強式驗證及資料遺失保護。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-116">Level 1 plus strong authentication and data loss protection.</span></span> <BR> <BR> <span data-ttu-id="3f2b7-117">增強式驗證包括使用 SMS 驗證的 Azure 多重要素驗證 (MFA)。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-117">Strong authentication includes Azure Multi-Factor Authentication (MFA) with SMS validation.</span></span> <span data-ttu-id="3f2b7-118">資料遺失防護可確保機密或關鍵資訊不會洩漏到 Microsoft 雲端以外的地方。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-118">Data loss prevention ensures that sensitive or critical information does not travel outside the Microsoft cloud.</span></span> <BR><BR> <span data-ttu-id="3f2b7-119">第 2 級的範例：財務和法務資訊以及新產品的研發資料。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-119">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span> | <span data-ttu-id="3f2b7-120">第 2 級再加上最高層級的加密、驗證及稽核。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-120">Level 2 plus the highest levels of encryption, authentication, and auditing.</span></span> <BR> <BR>  <span data-ttu-id="3f2b7-121">對靜態資料和雲端資料的最高層級資料加密，遵循地區法規，結合 MFA 與智慧卡以及細微稽核與警示。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-121">The highest levels of encryption for data at rest and in the cloud, compliant with regional regulations, combined with MFA with smart cards and granular auditing and alerting.</span></span> <BR> <BR> <span data-ttu-id="3f2b7-122">第 3 級的範例：客戶與合作夥伴的個人身分識別資訊，以及產品的工程規格和專屬的製造技術。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-122">Examples of Level 3 data are customer and partner personally identifiable information, product engineering specifications, and proprietary manufacturing techniques.</span></span>  |
||||

## <a name="contosos-information-policies"></a><span data-ttu-id="3f2b7-123">Contoso 的資訊原則</span><span class="sxs-lookup"><span data-stu-id="3f2b7-123">Contoso's information policies</span></span>
<span data-ttu-id="3f2b7-124">下表列出 Contoso 的資訊原則。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-124">The following table lists Contoso's information policies.</span></span>

|||||
|:-------|:-----|:-----|:-----|
|  | <span data-ttu-id="3f2b7-125">**存取**</span><span class="sxs-lookup"><span data-stu-id="3f2b7-125">**Access**</span></span> | <span data-ttu-id="3f2b7-126">**資料保留**</span><span class="sxs-lookup"><span data-stu-id="3f2b7-126">**Data retention**</span></span> | <span data-ttu-id="3f2b7-127">**資訊保護**</span><span class="sxs-lookup"><span data-stu-id="3f2b7-127">**Information protection**</span></span> |
| <span data-ttu-id="3f2b7-128">低商業價值 (第 1 級：基準)</span><span class="sxs-lookup"><span data-stu-id="3f2b7-128">Low business value (Level 1: Baseline)</span></span> | <span data-ttu-id="3f2b7-129">允許所有人存取</span><span class="sxs-lookup"><span data-stu-id="3f2b7-129">Allow access to all</span></span>  | <span data-ttu-id="3f2b7-130">6 個月</span><span class="sxs-lookup"><span data-stu-id="3f2b7-130">6 months</span></span> | <span data-ttu-id="3f2b7-131">使用加密。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-131">Use encryption.</span></span> |
| <span data-ttu-id="3f2b7-132">中等商業價值 (第 2 級：敏感性)</span><span class="sxs-lookup"><span data-stu-id="3f2b7-132">Medium business value (Level 2: Sensitive)</span></span> | <span data-ttu-id="3f2b7-133">允許 Contoso 員工、次承攬人和合作夥伴存取</span><span class="sxs-lookup"><span data-stu-id="3f2b7-133">Allow access to Contoso employees, subcontractors, and partners</span></span> <BR> <BR> <span data-ttu-id="3f2b7-134">使用 MFA、傳輸層安全性 (TLS) 和行動裝置應用程式管理 (MAM)。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-134">Use MFA, Transport Layer Security (TLS), and Mobile Application Management (MAM).</span></span> | <span data-ttu-id="3f2b7-135">2 年</span><span class="sxs-lookup"><span data-stu-id="3f2b7-135">2 years</span></span>  | <span data-ttu-id="3f2b7-136">使用雜湊值以確保資料完整。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-136">Use hash values for data integrity.</span></span>  |
| <span data-ttu-id="3f2b7-137">高商業價值 (第 3 級：高管制)</span><span class="sxs-lookup"><span data-stu-id="3f2b7-137">High business value (Level 3: Highly regulated)</span></span> | <span data-ttu-id="3f2b7-138">允許高階主管以及工程部和製造部的主管存取。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-138">Allow access to executives and leads in engineering and manufacturing.</span></span> <BR> <BR> <span data-ttu-id="3f2b7-139">版權管理系統 (RMS)，只有受控網路裝置。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-139">Rights Management System (RMS) with managed network devices only.</span></span>  | <span data-ttu-id="3f2b7-140">7 年</span><span class="sxs-lookup"><span data-stu-id="3f2b7-140">7 years</span></span>  | <span data-ttu-id="3f2b7-141">使用數位簽章以提供不可否認性。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-141">Use digital signatures for non-repudiation.</span></span>  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-enterprise"></a><span data-ttu-id="3f2b7-142">Contoso 使用 Microsoft 365 企業版進行資訊保護的途徑</span><span class="sxs-lookup"><span data-stu-id="3f2b7-142">Contoso’s path to information protection with Microsoft 365 Enterprise</span></span>

<span data-ttu-id="3f2b7-143">Contoso 使用下列步驟，針對其資訊保護需求準備 Microsoft 365 企業版：</span><span class="sxs-lookup"><span data-stu-id="3f2b7-143">Contoso used the following steps to prepare Microsoft 365 Enterprise for their information protection requirements:</span></span>

1. <span data-ttu-id="3f2b7-144">識別要保護的資訊</span><span class="sxs-lookup"><span data-stu-id="3f2b7-144">Identified what information to protect</span></span>

   <span data-ttu-id="3f2b7-145">Contoso 大量檢閱內部部署 SharePoint 網站和檔案共用上的現有數位資產，並且對每個項目進行分類。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-145">Contoso did an extensive review of their existing digital assets located on on-premises SharePoint sites and file shares and classified each one.</span></span>

2. <span data-ttu-id="3f2b7-146">判別各資料層級的存取權、保留期和資訊保護原則</span><span class="sxs-lookup"><span data-stu-id="3f2b7-146">Determined access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="3f2b7-147">Contoso 根據資料層級決定原則需求，這些原則需求是用來在移至雲端時保護現有的數位資產。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-147">Based on the data levels, Contoso determined detailed policy requirements, which were used to protect existing digital assets as they were moved to the cloud.</span></span>

3. <span data-ttu-id="3f2b7-148">針對不同的資訊層級建立敏感度標籤及其設定</span><span class="sxs-lookup"><span data-stu-id="3f2b7-148">Created sensitivity labels and their settings for the different levels of information</span></span>

   <span data-ttu-id="3f2b7-149">Contoso 針對其資料層級建立了敏感度標籤，以及包括加密、權限和浮水印等高管制標籤。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-149">Contoso created sensitivity labels for their data levels, with their highly regulated label that includes encryption, permissions, and watermarks.</span></span>

4. <span data-ttu-id="3f2b7-150">針對機密和高管制資料建立受保護的 SharePoint 網站，具有鎖定存取的權限</span><span class="sxs-lookup"><span data-stu-id="3f2b7-150">Created protected SharePoint sites for sensitive and highly regulated data with permissions that lock down access</span></span>

   <span data-ttu-id="3f2b7-151">敏感性和高度管控網站都是透過額外權限限制設定為私人小組網站。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-151">Both sensitive and highly regulated sites were configured as private team sites with additional permissions restrictions.</span></span> <span data-ttu-id="3f2b7-152">此外，也以使用對應的保留標籤來設定敏感性和高管制 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-152">Sensitive and highly regulated SharePoint sites were also configured with a corresponding retention label.</span></span> <span data-ttu-id="3f2b7-153">儲存在高管制 SharePoint 網站中的檔案受到高管制標籤的敏感度子標籤保護。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-153">Files stored in highly regulated SharePoint sites are protected with a sensitivity sublabel of the Highly Regulated label.</span></span> <span data-ttu-id="3f2b7-154">如需詳細資訊，請參閱[適用於高度管制資料的 SharePoint 網站](teams-sharepoint-online-sites-highly-regulated-data.md)案例。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-154">For more information, see the [SharePoint sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md) scenario.</span></span>

5.  <span data-ttu-id="3f2b7-155">從內部部署 SharePoint 網站和檔案共用將資料移至新的 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="3f2b7-155">Moved data from on-premises SharePoint sites and file shares to their new SharePoint sites</span></span>

    <span data-ttu-id="3f2b7-156">遷移至新 SharePoint 網站的檔案，會繼承指派給網站的預設保留標籤。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-156">The files migrated to the new SharePoint sites inherited the default retention labels assigned to the site.</span></span>

6.  <span data-ttu-id="3f2b7-157">訓練員工如何針對新文件使用敏感度標籤、如何在建立新 SharePoint 網站時與 Contoso IT 互動，以及一律將數位資產儲存在 SharePoint 網站上</span><span class="sxs-lookup"><span data-stu-id="3f2b7-157">Trained employees on how to use sensitivity labels for new documents, how to interact with Contoso IT when creating new SharePoint sites, and to always store digital assets on SharePoint sites</span></span>

    <span data-ttu-id="3f2b7-158">這個部分是雲端資訊保護轉換最困難的部分，Contoso IT 和管理階層必須改變組織員工總是在雲端標示及儲存其數位資產、抑制使用內部部署檔案共用，而從不使用第三方雲端儲存服務或 USB 磁碟機這樣的一個資訊儲存壞習慣。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-158">Considered the hardest part of the information protection transition for the cloud, Contoso IT and management needed to change the bad information storage habits of the organization’s employees to always label and store their digital assets in the cloud, refrain from using on-premises file shares, and never use third-party cloud storage services or USB drives.</span></span>

## <a name="conditional-access-policies-for-information-protection"></a><span data-ttu-id="3f2b7-159">資訊保護的條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="3f2b7-159">Conditional Access policies for information protection</span></span>

<span data-ttu-id="3f2b7-160">搭配其身分識別和行動裝置管理基礎結構，以及作為推出 Exchange Online 和 SharePoint 的一部分，Contoso 設定下列條件式存取原則集合，並且將該集合套用至適當的群組：</span><span class="sxs-lookup"><span data-stu-id="3f2b7-160">In conjunction with their identity and mobile device management infrastructure and as part of their rollout of Exchange Online and SharePoint, Contoso configured the following set of Conditional Access policies and applied them to the appropriate groups:</span></span>

- [<span data-ttu-id="3f2b7-161">裝置原則的受控和非受控應用程式存取</span><span class="sxs-lookup"><span data-stu-id="3f2b7-161">Managed and unmanaged application access on devices policies</span></span>](identity-access-policies.md)
- [<span data-ttu-id="3f2b7-162">Exchange Online 存取原則</span><span class="sxs-lookup"><span data-stu-id="3f2b7-162">Exchange Online access policies</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="3f2b7-163">SharePoint 存取原則</span><span class="sxs-lookup"><span data-stu-id="3f2b7-163">SharePoint access policies</span></span>](sharepoint-file-access-policies.md)

<span data-ttu-id="3f2b7-164">以下是 Contoso 的資訊保護原則結果集合。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-164">Here is Contoso's resulting set of policies for information protection.</span></span>

![裝置、Exchange Online 和 SharePoint 條件式存取原則](./media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
><span data-ttu-id="3f2b7-166">Contoso 也會為身分識別和登入設定額外的條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-166">Contoso also configured additional Conditional Access policies for identity and sign-in.</span></span> <span data-ttu-id="3f2b7-167">請參閱 [Contoso Corporation 的身分識別](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-167">See [Identity for the Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>
>

<span data-ttu-id="3f2b7-168">這些原則會確保：</span><span class="sxs-lookup"><span data-stu-id="3f2b7-168">These policies ensure that:</span></span>

- <span data-ttu-id="3f2b7-169">允許使用應用程式，並由應用程式保護原則定義這些應用程式可以對組織資料執行哪些動作。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-169">Apps are allowed and the actions they can take with your organization data are defined by app protection policies.</span></span>
- <span data-ttu-id="3f2b7-170">電腦和行動裝置都必須符合規範。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-170">PCs and mobile devices must be compliant.</span></span>
- <span data-ttu-id="3f2b7-171">Exchange Online 使用適用於 Exchange Online 的 Office 365 訊息加密。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-171">Exchange Online uses Office 365 message encryption for Exchange Online.</span></span>
- <span data-ttu-id="3f2b7-172">SharePoint 使用應用程式強制限制。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-172">SharePoint uses app enforced restrictions.</span></span>
- <span data-ttu-id="3f2b7-173">SharePoint 會針對僅限瀏覽器存取使用存取控制原則，並封鎖未受控裝置的存取。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-173">SharePoint uses access control policies for browser-only access and to block access for unmanaged devices.</span></span>

## <a name="mapping-microsoft-365-enterprise-features-to-contosos-data-levels"></a><span data-ttu-id="3f2b7-174">將 Microsoft 365 企業版功能對應至 Contoso 的資料層級</span><span class="sxs-lookup"><span data-stu-id="3f2b7-174">Mapping Microsoft 365 Enterprise features to Contoso's data levels</span></span>

<span data-ttu-id="3f2b7-175">下表將 Contoso 資料層級與 Microsoft 365 企業版的資訊保護功能對應。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-175">The following table maps Contoso's data levels to information protection features in Microsoft 365 Enterprise.</span></span>

|||||
|:-------|:-----|:-----|:-----|
| | <span data-ttu-id="3f2b7-176">**Office 365**</span><span class="sxs-lookup"><span data-stu-id="3f2b7-176">**Office 365**</span></span> | <span data-ttu-id="3f2b7-177">**Windows 10 和 Office 365 專業增強版**</span><span class="sxs-lookup"><span data-stu-id="3f2b7-177">**Windows 10 and Office 365 ProPlus**</span></span> | <span data-ttu-id="3f2b7-178">**EMS**</span><span class="sxs-lookup"><span data-stu-id="3f2b7-178">**EMS**</span></span> |
| <span data-ttu-id="3f2b7-179">第 1 級：基準</span><span class="sxs-lookup"><span data-stu-id="3f2b7-179">Level 1: Baseline</span></span>  | <span data-ttu-id="3f2b7-180">SharePoint 和 Exchange Online 條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="3f2b7-180">SharePoint and Exchange Online Conditional Access policies</span></span> <BR> <span data-ttu-id="3f2b7-181">SharePoint 網站的權限</span><span class="sxs-lookup"><span data-stu-id="3f2b7-181">Permissions on SharePoint sites</span></span> | <span data-ttu-id="3f2b7-182">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="3f2b7-182">Sensitivity labels</span></span> <BR> <span data-ttu-id="3f2b7-183">BitLocker</span><span class="sxs-lookup"><span data-stu-id="3f2b7-183">BitLocker</span></span> <BR> <span data-ttu-id="3f2b7-184">Windows 資訊保護</span><span class="sxs-lookup"><span data-stu-id="3f2b7-184">Windows Information Protection</span></span> | <span data-ttu-id="3f2b7-185">裝置條件式存取原則和行動裝置應用程式管理原則</span><span class="sxs-lookup"><span data-stu-id="3f2b7-185">Device Conditional Access policies and Mobile Application Management policies</span></span> |
| <span data-ttu-id="3f2b7-186">第 2 級：敏感性</span><span class="sxs-lookup"><span data-stu-id="3f2b7-186">Level 2: Sensitive</span></span> | <span data-ttu-id="3f2b7-187">第 1 級增強版：</span><span class="sxs-lookup"><span data-stu-id="3f2b7-187">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="3f2b7-188">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="3f2b7-188">Sensitivity labels</span></span> <BR> <span data-ttu-id="3f2b7-189">SharePoint 網站上的 Office 365 保留標籤</span><span class="sxs-lookup"><span data-stu-id="3f2b7-189">Office 365 retention labels on SharePoint sites</span></span> <BR> <span data-ttu-id="3f2b7-190">SharePoint 和 Exchange Online 的 Office 365 資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="3f2b7-190">Office 365 Data Loss Prevention for SharePoint and Exchange Online</span></span> <BR> <span data-ttu-id="3f2b7-191">隔離的 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="3f2b7-191">Isolated SharePoint sites</span></span>  | <span data-ttu-id="3f2b7-192">第 1 級增強版：</span><span class="sxs-lookup"><span data-stu-id="3f2b7-192">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="3f2b7-193">數位資產上的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="3f2b7-193">Sensitivity labels on digital assets</span></span>  | <span data-ttu-id="3f2b7-194">第 1 級</span><span class="sxs-lookup"><span data-stu-id="3f2b7-194">Level 1</span></span> |
| <span data-ttu-id="3f2b7-195">第 3 級：高管制</span><span class="sxs-lookup"><span data-stu-id="3f2b7-195">Level 3: Highly regulated</span></span> | <span data-ttu-id="3f2b7-196">第 2 級增強版：</span><span class="sxs-lookup"><span data-stu-id="3f2b7-196">Level 2 plus:</span></span> <BR><BR> <span data-ttu-id="3f2b7-197">針對營業秘密資訊的使用自己的金鑰 (BYOK) 加密和保護</span><span class="sxs-lookup"><span data-stu-id="3f2b7-197">Bring Your Own Key (BYOK) encryption and protection for trade secret information</span></span> <BR> <span data-ttu-id="3f2b7-198">適用於與 Office 365 服務互動之企業營運應用程式的 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="3f2b7-198">Azure Key Vault for line of business applications that interact with Office 365 services</span></span> | <span data-ttu-id="3f2b7-199">第 2 級</span><span class="sxs-lookup"><span data-stu-id="3f2b7-199">Level 2</span></span> | <span data-ttu-id="3f2b7-200">第 1 級</span><span class="sxs-lookup"><span data-stu-id="3f2b7-200">Level 1</span></span> |
|||||

<span data-ttu-id="3f2b7-201">以下是 Contoso 的資訊保護設定結果。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-201">Here is Contoso's resulting information protection configuration.</span></span>

![Contoso 的資訊保護設定結果](./media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a><span data-ttu-id="3f2b7-203">下一步</span><span class="sxs-lookup"><span data-stu-id="3f2b7-203">Next step</span></span>

<span data-ttu-id="3f2b7-204">[請參閱](contoso-security-summary.md) Contoso 如何針對身分識別與存取管理、威脅防護、資訊保護和安全性管理，使用 Microsoft 365 企業版的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="3f2b7-204">[See](contoso-security-summary.md) how Contoso has used the security features across Microsoft 365 Enterprise for identity and access management, threat protection, information protection, and security management.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f2b7-205">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3f2b7-205">See also</span></span>

[<span data-ttu-id="3f2b7-206">Microsoft 365 企業版的資訊保護</span><span class="sxs-lookup"><span data-stu-id="3f2b7-206">Information protection for Microsoft 365 Enterprise</span></span>](infoprotect-infrastructure.md)

[<span data-ttu-id="3f2b7-207">部署指南</span><span class="sxs-lookup"><span data-stu-id="3f2b7-207">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="3f2b7-208">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="3f2b7-208">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)


