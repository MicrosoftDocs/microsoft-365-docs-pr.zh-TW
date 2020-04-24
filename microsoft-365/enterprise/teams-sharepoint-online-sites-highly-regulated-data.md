---
title: 適用於高度管制資料的 SharePoint 網站
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: 建立安全的 SharePoint 小組網站來儲存您最重要且最敏感的檔案。
ms.openlocfilehash: 97a01275d1d45cb02e66e88f82c95311bcb6fe70
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636708"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="0207e-103">適用於高度管制資料的 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="0207e-103">SharePoint sites for highly regulated data</span></span>

<span data-ttu-id="0207e-104">*此案例同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="0207e-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="0207e-p101">Microsoft 365 企業版包含一套完整的雲端式服務，因此您可以建立、儲存、保護和管理檔案中儲存的高度管制資料。包含的資料為：</span><span class="sxs-lookup"><span data-stu-id="0207e-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, secure, and manage your highly regulated data stored in files. This includes data that is:</span></span>

- <span data-ttu-id="0207e-107">受限於區域法規。</span><span class="sxs-lookup"><span data-stu-id="0207e-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="0207e-108">貴組織最有價值的資料，例如營業秘密、財務或人力資源資訊，以及組織策略。</span><span class="sxs-lookup"><span data-stu-id="0207e-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

>[!Note]
> <span data-ttu-id="0207e-109">使用 Microsoft Teams 的類似案例[在此](secure-teams-highly-regulated-data-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="0207e-109">A similar scenario using Microsoft Teams is [here](secure-teams-highly-regulated-data-scenario.md).</span></span>
>

<span data-ttu-id="0207e-110">符合此商務需求的 Microsoft 365 企業版雲端式案例需要您：</span><span class="sxs-lookup"><span data-stu-id="0207e-110">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="0207e-111">在 SharePoint 小組網站中儲存檔案 (文件、投影片檔案、試算表等)。</span><span class="sxs-lookup"><span data-stu-id="0207e-111">Store files (documents, slide decks, spreadsheets, etc.) in a SharePoint team site.</span></span>
- <span data-ttu-id="0207e-112">鎖定網站，以防止：</span><span class="sxs-lookup"><span data-stu-id="0207e-112">Lock down the site to prevent:</span></span>
  - <span data-ttu-id="0207e-113">非網站的 Microsoft 365 群組成員的使用者存取。</span><span class="sxs-lookup"><span data-stu-id="0207e-113">Access to users who are not members of the Microsoft 365 group for the site.</span></span>
  - <span data-ttu-id="0207e-114">網站成員將存取權授與其他使用者。</span><span class="sxs-lookup"><span data-stu-id="0207e-114">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="0207e-115">非網站成員要求網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="0207e-115">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="0207e-116">為 SharePoint 網站設定保留標籤，作為防止使用者在組織外部傳送檔案的預設方法。</span><span class="sxs-lookup"><span data-stu-id="0207e-116">Configure a retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="0207e-117">使用隨檔案一起移動的加密來加密網站中最敏感的檔案。</span><span class="sxs-lookup"><span data-stu-id="0207e-117">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="0207e-118">將權限新增至最敏感的檔案，以致於雖然是在網站外部共用這些檔案，開啟檔案時仍然需要具有權限之使用者帳戶的有效認證。</span><span class="sxs-lookup"><span data-stu-id="0207e-118">Add permissions to the most sensitive files so that if even if they get shared outside of the site, opening the file still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="0207e-119">下表將此案例的需求對應至 Microsoft 365 企業版的功能。</span><span class="sxs-lookup"><span data-stu-id="0207e-119">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="0207e-120">**需求**</span><span class="sxs-lookup"><span data-stu-id="0207e-120">**Requirement**</span></span> | <span data-ttu-id="0207e-121">**Microsoft 365 企業版功能**</span><span class="sxs-lookup"><span data-stu-id="0207e-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="0207e-122">儲存檔案</span><span class="sxs-lookup"><span data-stu-id="0207e-122">Store files</span></span> | <span data-ttu-id="0207e-123">SharePoint 小組網站</span><span class="sxs-lookup"><span data-stu-id="0207e-123">SharePoint team sites</span></span> |
| <span data-ttu-id="0207e-124">鎖定網站</span><span class="sxs-lookup"><span data-stu-id="0207e-124">Lock down the site</span></span> | <span data-ttu-id="0207e-125">Microsoft 365 群組和 SharePoint 小組網站的權限</span><span class="sxs-lookup"><span data-stu-id="0207e-125">Microsoft 365 groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="0207e-126">為網站上的檔案新增標籤</span><span class="sxs-lookup"><span data-stu-id="0207e-126">Label the files of the site</span></span> | <span data-ttu-id="0207e-127">Microsoft 365 保留標籤</span><span class="sxs-lookup"><span data-stu-id="0207e-127">Microsoft 365 retention labels</span></span> |
| <span data-ttu-id="0207e-128">將檔案傳送到組織外部時封鎖使用者</span><span class="sxs-lookup"><span data-stu-id="0207e-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="0207e-129">資料遺失保護 (DLP) 原則</span><span class="sxs-lookup"><span data-stu-id="0207e-129">Data Loss Prevention (DLP) policies</span></span> |
| <span data-ttu-id="0207e-130">加密網站上的所有檔案</span><span class="sxs-lookup"><span data-stu-id="0207e-130">Encrypt all of the files of the site</span></span> | <span data-ttu-id="0207e-131">Microsoft 365 敏感度標籤或子標籤</span><span class="sxs-lookup"><span data-stu-id="0207e-131">Microsoft 365 sensitivity labels or sublabels</span></span> |
| <span data-ttu-id="0207e-132">新增權限至網站的檔案</span><span class="sxs-lookup"><span data-stu-id="0207e-132">Add permissions to the files of the site</span></span> | <span data-ttu-id="0207e-133">Microsoft 365 敏感度標籤或子標籤</span><span class="sxs-lookup"><span data-stu-id="0207e-133">Microsoft 365 sensitivity labels or sublabels</span></span> |
|||

<span data-ttu-id="0207e-134">以下是安全 SharePoint 網站的設定範例。</span><span class="sxs-lookup"><span data-stu-id="0207e-134">Here is an example configuration for a secure SharePoint site.</span></span>

![適用於高度管制資料的 SharePoint 網站案例](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="0207e-136">此案例需要您已部署：</span><span class="sxs-lookup"><span data-stu-id="0207e-136">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="0207e-137">基礎結構的[身分識別](identity-infrastructure.md)階段及[資訊保護](infoprotect-infrastructure.md)階段的步驟 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="0207e-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="0207e-138">[SharePoint](sharepoint-online-onedrive-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="0207e-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span></span>

<span data-ttu-id="0207e-139">下列階段會逐步帶您針對適用於高度管制資料的 SharePoint 網站，進行設計、設定及推動採用。</span><span class="sxs-lookup"><span data-stu-id="0207e-139">The following phases step you through designing, configuring, and driving adoption for SharePoint sites for highly regulated data.</span></span>

<a name="poster"></a> <span data-ttu-id="0207e-140">如需此案例的 1 頁式摘要，請參閱[適用於高度管制資料的 SharePoint 網站海報](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)。</span><span class="sxs-lookup"><span data-stu-id="0207e-140">For a 1-page summary of this scenario, see the [SharePoint sites for highly regulated data poster](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).</span></span>

<span data-ttu-id="0207e-141">[![適用於高度管制資料的 SharePoint 網站海報](../media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)</span><span class="sxs-lookup"><span data-stu-id="0207e-141">[![SharePoint sites for highly regulated data poster](../media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)</span></span>

<span data-ttu-id="0207e-142">您也可以用 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) 或 [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) 格式下載此海報，以及用 Letter、Legal 或 Tabloid (11 x 17) 大小的紙張列印此海報。</span><span class="sxs-lookup"><span data-stu-id="0207e-142">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>


## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="0207e-143">身分識別與裝置存取必要條件</span><span class="sxs-lookup"><span data-stu-id="0207e-143">Identity and device access prerequisites</span></span>

<span data-ttu-id="0207e-144">若要保護 SharePoint 網站的存取權，請確定您已設定[身分識別與裝置存取原則](identity-access-policies.md)和[建議的 SharePoint 存取原則](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0207e-144">To protect access to the SharePoint site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="0207e-145">階段 1：設計</span><span class="sxs-lookup"><span data-stu-id="0207e-145">Phase 1: Design</span></span>

<span data-ttu-id="0207e-146">若為高度管制的資料建立 SharePoint 網站，您必須先確定網站的目的。</span><span class="sxs-lookup"><span data-stu-id="0207e-146">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="0207e-147">例如，製造業組織的研發部門需要 SharePoint 網站來儲存現有產品的目前設計規格，以及在新產品上共同作業。</span><span class="sxs-lookup"><span data-stu-id="0207e-147">For example, the research and development department of a manufacturing organization needs a SharePoint site to store current design specifications for existing products and a place to collaborate on new products.</span></span> <span data-ttu-id="0207e-148">只有研發部門和選取的主管成員才允許存取網站。</span><span class="sxs-lookup"><span data-stu-id="0207e-148">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="0207e-149">該目的會驅使基本組態項目的決定，例如：</span><span class="sxs-lookup"><span data-stu-id="0207e-149">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="0207e-150">要指派至網站的文件部分以及標籤 DLP 原則集合的保留標籤</span><span class="sxs-lookup"><span data-stu-id="0207e-150">The retention label to assign to the Documents portion of the site and DLP policies for the label</span></span>
- <span data-ttu-id="0207e-151">敏感度子標籤的設定，可讓使用者套用到儲存在網站中的高度敏感檔案</span><span class="sxs-lookup"><span data-stu-id="0207e-151">The settings of a sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="0207e-152">決定後，您就能使用這些設定在階段 2 中設定網站。</span><span class="sxs-lookup"><span data-stu-id="0207e-152">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-microsoft-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="0207e-153">步驟 1 Microsoft 365 保留標籤和 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="0207e-153">Step 1 Microsoft 365 retention labels and DLP policies</span></span>

<span data-ttu-id="0207e-154">當套用至 SharePoint 小組網站的文件部分時，保留標籤提供預設方法，來分類儲存在網站上的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="0207e-154">When applied to the Documents portion of a SharePoint team site, retention labels provide a default method of classifying all files stored on the site.</span></span>
 
<span data-ttu-id="0207e-155">針對適用於高度管制資料的 SharePoint 網站，您必須決定要使用哪個保留標籤。</span><span class="sxs-lookup"><span data-stu-id="0207e-155">For SharePoint sites for highly regulated data, you need to determine which retention label to use.</span></span>

<span data-ttu-id="0207e-156">如需標籤的設計考量，請參閱 [Microsoft 365 分類和標籤](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="0207e-156">For the design considerations of labels, see [Microsoft 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="0207e-p103">若要保護機密資訊並防止意外或故意洩露，您可以使用 DLP 原則。如需詳細資訊，請參閱[概觀](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)。</span><span class="sxs-lookup"><span data-stu-id="0207e-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="0207e-159">針對 SharePoint 網站，您必須針對指派至網站的保留標籤設定 DLP 原則，以在使用者嘗試與外部使用者共用檔案時，封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="0207e-159">For SharePoint sites, you must configure a DLP policy for the retention label assigned to the site to block users when they attempt to share files with external users.</span></span> 

### <a name="step-2-your-microsoft-365-sensitivity-sublabel"></a><span data-ttu-id="0207e-160">步驟2：您的 Microsoft 365 敏感度子標籤</span><span class="sxs-lookup"><span data-stu-id="0207e-160">Step 2: Your Microsoft 365 sensitivity sublabel</span></span>

<span data-ttu-id="0207e-161">若要將加密和權限集提供給最敏感的檔案，使用者必須套用敏感度標籤和子標籤。</span><span class="sxs-lookup"><span data-stu-id="0207e-161">To provide encryption and a set of permissions to your most sensitive files, users must apply a sensitivity label or sublabel.</span></span> <span data-ttu-id="0207e-162">子標籤位於現有標籤下方。</span><span class="sxs-lookup"><span data-stu-id="0207e-162">A sublabel exists under an existing label.</span></span> 

<span data-ttu-id="0207e-163">當您的需求是少量標籤、可同時用於全域使用和個別的私人小組時，請使用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="0207e-163">Use a sensitivity label when you need is a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="0207e-164">當您有大量標籤或想要將安全網站的標籤整理在您的高度管制標籤之下時，請使用敏感度子標籤。</span><span class="sxs-lookup"><span data-stu-id="0207e-164">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for secure sites the under your highly regulated label.</span></span> 

<span data-ttu-id="0207e-165">所套用的標籤或子標籤設定會隨著檔案移動。</span><span class="sxs-lookup"><span data-stu-id="0207e-165">The settings of the applied label or sublabel travel with the file.</span></span> <span data-ttu-id="0207e-166">即使檔案流出網站外部，也只有擁有權限的已驗證使用者帳戶能開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="0207e-166">Even if it is leaked outside the site, only authenticated user accounts that have permissions can open it.</span></span>

### <a name="design-results"></a><span data-ttu-id="0207e-167">設計結果</span><span class="sxs-lookup"><span data-stu-id="0207e-167">Design results</span></span>

<span data-ttu-id="0207e-168">您已決定下列項目：</span><span class="sxs-lookup"><span data-stu-id="0207e-168">You have determined the following:</span></span>

- <span data-ttu-id="0207e-169">適當的保留標籤和與標籤相關聯的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="0207e-169">The appropriate retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="0207e-170">包含加密和權限的敏感度子標籤設定</span><span class="sxs-lookup"><span data-stu-id="0207e-170">The settings of the sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="0207e-171">階段 2：設定</span><span class="sxs-lookup"><span data-stu-id="0207e-171">Phase 2: Configure</span></span>

<span data-ttu-id="0207e-172">在這個階段中，您會採用在階段 1 中決定的設定，然後實作這些設定來建立適用於高度管制資料的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="0207e-172">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-microsoft-365-group"></a><span data-ttu-id="0207e-173">步驟 1：使用對應 Microsoft 365 群組的擁有者和成員來建立私人 SharePoint 小組網站</span><span class="sxs-lookup"><span data-stu-id="0207e-173">Step 1: Create a private SharePoint team site with owners and members of the corresponding Microsoft 365 group</span></span>

<span data-ttu-id="0207e-174">按照[以下指示]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8)來建立私人 SharePoint 小組網站。</span><span class="sxs-lookup"><span data-stu-id="0207e-174">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="0207e-175">步驟 2：為 SharePoint 小組網站設定額外的權限設定</span><span class="sxs-lookup"><span data-stu-id="0207e-175">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="0207e-176">從 SharePoint 網站設定這些權限設定。</span><span class="sxs-lookup"><span data-stu-id="0207e-176">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="0207e-177">在工具列中，按一下設定圖示，然後按一下 [網站權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0207e-177">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="0207e-178">在 [網站權限]\*\*\*\* 窗格的 [共用設定]\*\*\*\* 之下，按一下 [變更共用設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0207e-178">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="0207e-179">在 [共用權限]\*\*\*\* 之下，選擇 [只有網站擁有者可以共用檔案、資料夾及網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0207e-179">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="0207e-180">關閉 [允許存取要求]\*\*\*\*，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0207e-180">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="0207e-181">清除這些設定後，網站群組成員與其他成員或非成員要求網站存取權以共用網站的功能將會停用。</span><span class="sxs-lookup"><span data-stu-id="0207e-181">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-a-retention-label"></a><span data-ttu-id="0207e-182">步驟 3：針對保留標籤設定網站</span><span class="sxs-lookup"><span data-stu-id="0207e-182">Step 3: Configure the site for a retention label</span></span>

<span data-ttu-id="0207e-183">使用[使用標籤與 DLP 來保護 SharePoint 檔案](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)中的指示來：</span><span class="sxs-lookup"><span data-stu-id="0207e-183">Use the instructions in [Protect SharePoint files with labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="0207e-184">建立並發布適用於高度管制資料的保留標籤 (如有需要)。</span><span class="sxs-lookup"><span data-stu-id="0207e-184">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="0207e-185">針對步驟 1 中建立的保留標籤設定網站。</span><span class="sxs-lookup"><span data-stu-id="0207e-185">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="0207e-186">為使用在步驟 2 中建立的保留標籤的高度管制資料建立 DLP 原則，並封鎖使用者在組織外傳送檔案</span><span class="sxs-lookup"><span data-stu-id="0207e-186">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-a-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="0207e-187">步驟 4：為網站建立敏感度子標籤</span><span class="sxs-lookup"><span data-stu-id="0207e-187">Step 4: Create a sensitivity sublabel for the site</span></span>

<span data-ttu-id="0207e-188">適用於高度管制資料的敏感度標籤可讓任何人套用至任何檔案，但是安全網站不同，它需要自己的子標籤，以致於指派子標籤的檔案都能：</span><span class="sxs-lookup"><span data-stu-id="0207e-188">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="0207e-189">受到加密，且加密會隨檔案移動。</span><span class="sxs-lookup"><span data-stu-id="0207e-189">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="0207e-190">包含自訂權限，因此只有網站群組的成員能夠開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="0207e-190">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="0207e-191">若要針對儲存在網站中的檔案完成這項額外的安全性，您必須針對高度管制檔案設定一個新的敏感度標籤或一般標籤的子標籤。</span><span class="sxs-lookup"><span data-stu-id="0207e-191">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label or a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="0207e-192">只有網站的群組成員能在高度管制標籤的子標籤清單中看到該網站。</span><span class="sxs-lookup"><span data-stu-id="0207e-192">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="0207e-193">使用[這裡](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)的指示來為高度管制檔案所使用的標籤設定標籤或子標籤，其設定如下：</span><span class="sxs-lookup"><span data-stu-id="0207e-193">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a label or a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="0207e-194">標籤或子標籤的名稱包含網站名稱，以便在將標籤或子標籤指派到檔案時輕鬆建立關聯。</span><span class="sxs-lookup"><span data-stu-id="0207e-194">The name of the label or sublabel contains the name of the site for easy association when assigning the label or sublabel to a file.</span></span>
- <span data-ttu-id="0207e-195">啟用加密。</span><span class="sxs-lookup"><span data-stu-id="0207e-195">Encryption is enabled.</span></span>
- <span data-ttu-id="0207e-196">網站群組具有共同撰寫權限。</span><span class="sxs-lookup"><span data-stu-id="0207e-196">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="0207e-197">設定結果</span><span class="sxs-lookup"><span data-stu-id="0207e-197">Configuration results</span></span>

<span data-ttu-id="0207e-198">您已設定下列項目：</span><span class="sxs-lookup"><span data-stu-id="0207e-198">You have configured the following:</span></span>

- <span data-ttu-id="0207e-199">SharePoint 網站上的其他限制權限設定</span><span class="sxs-lookup"><span data-stu-id="0207e-199">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="0207e-200">指派給 SharePoint 網站文件部分的保留標籤</span><span class="sxs-lookup"><span data-stu-id="0207e-200">A retention label assigned to the Documents portion of the SharePoint site</span></span>
- <span data-ttu-id="0207e-201">保留標籤的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="0207e-201">A DLP policy for the retention label</span></span>
- <span data-ttu-id="0207e-202">使用者可將敏感度標籤或子標籤套用到儲存在網站中的最敏感檔案，其會加密檔案並只允許小組網站群組的成員擁有共同撰寫存取權</span><span class="sxs-lookup"><span data-stu-id="0207e-202">A sensitivity label or sublabel that users can apply to the most sensitive files stored in the site, which encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="0207e-203">以下是使用高度管制標籤的子標籤所產生的設定。</span><span class="sxs-lookup"><span data-stu-id="0207e-203">Here is the resulting configuration that uses a sublabel of the Highly regulated label.</span></span>

![適用於高度管制資料的 SharePoint 網站案例](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="0207e-205">以下是使用者將子標籤套用至儲存在網站中的檔案的範例。</span><span class="sxs-lookup"><span data-stu-id="0207e-205">Here is an example of a user that has applied the sublabel to a file stored in the site.</span></span>

![適用於高度管制資料的 SharePoint 網站案例](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="0207e-207">階段 3：推動使用者採用</span><span class="sxs-lookup"><span data-stu-id="0207e-207">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="0207e-208">如果一直將適用於高度管制資料的 SharePoint 網站用於儲存和存取敏感檔案，則 SharePoint 網站只能保護資料。</span><span class="sxs-lookup"><span data-stu-id="0207e-208">A SharePoint site for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive files.</span></span> <span data-ttu-id="0207e-209">這是最難的階段，因為這有賴於使用者變更習慣和偏好。</span><span class="sxs-lookup"><span data-stu-id="0207e-209">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="0207e-210">例如，員工以前都習慣將敏感檔案儲存在 USB 磁碟或個人雲端式儲存解決方案，而現在必須將檔案單獨儲存在適用於高度管制資料的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="0207e-210">For example, employees that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="0207e-211">步驟 1：訓練您的使用者</span><span class="sxs-lookup"><span data-stu-id="0207e-211">Step 1: Train your users</span></span>

<span data-ttu-id="0207e-212">完成您的設定之後，請訓練一組使用者，這些使用者是網站成員：</span><span class="sxs-lookup"><span data-stu-id="0207e-212">After completing your configuration, train the set of users who are members of the site:</span></span>

- <span data-ttu-id="0207e-213">了解使用新網站來保護有價值檔案的重要性以及高度管制資料外洩的後果，例如法律後果、法規罰款、勒索軟體或喪失競爭優勢。</span><span class="sxs-lookup"><span data-stu-id="0207e-213">On the importance of using the new site to protect valuable files and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="0207e-214">如何存取網站及其檔案。</span><span class="sxs-lookup"><span data-stu-id="0207e-214">How to access the site and its files.</span></span>
- <span data-ttu-id="0207e-215">如何在網站上建立新檔案，以及上傳儲存在本機的新檔案。</span><span class="sxs-lookup"><span data-stu-id="0207e-215">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="0207e-216">DLP 原則如何封鎖他們免於在外部共用檔案。</span><span class="sxs-lookup"><span data-stu-id="0207e-216">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="0207e-217">如何使用網站的標籤或子標籤來標記最敏感的檔案。</span><span class="sxs-lookup"><span data-stu-id="0207e-217">How to label the most sensitive files with the label or sublabel for the site.</span></span>
- <span data-ttu-id="0207e-218">標籤或子標籤如何保護檔案，即使該檔案從網站外洩。</span><span class="sxs-lookup"><span data-stu-id="0207e-218">How the label or sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="0207e-219">此訓練應該包含實際操作練習，讓使用者可以體驗這些作業及其結果。</span><span class="sxs-lookup"><span data-stu-id="0207e-219">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="0207e-220">步驟 2：進行使用量和檔案的定期檢閱</span><span class="sxs-lookup"><span data-stu-id="0207e-220">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="0207e-221">在幾週的訓練之後，SharePoint 網站的 SharePoint 系統管理員可以：</span><span class="sxs-lookup"><span data-stu-id="0207e-221">In the weeks after training, the SharePoint administrator for the SharePoint site can:</span></span>

- <span data-ttu-id="0207e-222">分析網站的使用方式，並且與預期使用方式進行比較。</span><span class="sxs-lookup"><span data-stu-id="0207e-222">Analyze usage for the site and compare it with usage expectations.</span></span>
- <span data-ttu-id="0207e-223">確認已使用敏感度標籤或子標籤正確地標示高度敏感檔案。</span><span class="sxs-lookup"><span data-stu-id="0207e-223">Verify that highly sensitive files have been properly labeled with the sensitivity label or sublabel.</span></span>

  <span data-ttu-id="0207e-224">您可以在 SharePoint 檢視資料夾，然後透過 [新增欄]\*\*\*\* 的 [顯示/隱藏欄]\*\*\*\* 選項新增 [敏感度]\*\*\*\* 欄，查看哪些檔案有被指派標籤。</span><span class="sxs-lookup"><span data-stu-id="0207e-224">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>


<span data-ttu-id="0207e-225">視需要重新訓練您的使用者。</span><span class="sxs-lookup"><span data-stu-id="0207e-225">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="0207e-226">使用者採用結果</span><span class="sxs-lookup"><span data-stu-id="0207e-226">User adoption results</span></span>

<span data-ttu-id="0207e-227">高度管制的檔案會單獨儲存在適用於高度管制資料的 SharePoint 網站上，且最敏感的檔案已套用網站的敏感度標籤或子標籤。</span><span class="sxs-lookup"><span data-stu-id="0207e-227">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity label or sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-used-a-sharepoint-site-for-highly-regulated-data"></a><span data-ttu-id="0207e-228">Contoso Corporation 如何對高度管制的資料使用 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="0207e-228">How the Contoso Corporation used a SharePoint site for highly regulated data</span></span>

<span data-ttu-id="0207e-229">Contoso Corporation 是虛構但具代表性的全球製造業集團。</span><span class="sxs-lookup"><span data-stu-id="0207e-229">The Contoso Corporation is a fictional but representative global manufacturing conglomerate.</span></span> <span data-ttu-id="0207e-230">查看 Contoso 如何設計、設定，然後為其在巴黎、莫斯科、紐約、北京和班加羅爾的研究小組推動採用[安全的 SharePoint 網站](contoso-sharepoint-online-site-for-highly-confidential-assets.md)。</span><span class="sxs-lookup"><span data-stu-id="0207e-230">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="0207e-231">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0207e-231">See also</span></span>

[<span data-ttu-id="0207e-232">適用於高度管制資料的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0207e-232">Teams for highly regulated data</span></span>](secure-teams-highly-regulated-data-scenario.md)

[<span data-ttu-id="0207e-233">Microsoft 365 企業版工作負載和案例</span><span class="sxs-lookup"><span data-stu-id="0207e-233">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="0207e-234">[Microsoft 365 生產力資源庫](https://aka.ms/productivitylibrary)https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="0207e-234">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="0207e-235">部署指南</span><span class="sxs-lookup"><span data-stu-id="0207e-235">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
