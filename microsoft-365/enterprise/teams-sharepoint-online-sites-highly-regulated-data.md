---
title: 適用於高度管制資料的 SharePoint 網站
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/04/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 建立安全的 SharePoint 小組網站來儲存您最重要且最敏感的檔案。
ms.openlocfilehash: dc604870826075cee645dd466b82f908e1571339
ms.sourcegitcommit: e1ffb98ac8159d1dc814930fe388d3e37cbdc7e2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/05/2019
ms.locfileid: "37403176"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="7da90-103">適用於高度管制資料的 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="7da90-103">Microsoft Teams and SharePoint Online sites for highly regulated data</span></span>

<span data-ttu-id="7da90-104">*此案例同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="7da90-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7da90-p101">Microsoft 365 企業版包含一套完整的雲端式服務，因此您可以建立、儲存和保護檔案中儲存的高度管制資料。包含的資料為：</span><span class="sxs-lookup"><span data-stu-id="7da90-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data. This includes data that is:</span></span>

- <span data-ttu-id="7da90-107">受限於區域法規。</span><span class="sxs-lookup"><span data-stu-id="7da90-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="7da90-108">貴組織最有價值的資料，例如營業秘密、財務或人力資源資訊，以及組織策略。</span><span class="sxs-lookup"><span data-stu-id="7da90-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="7da90-109">符合此商務需求的 Microsoft 365 企業版雲端式案例需要您：</span><span class="sxs-lookup"><span data-stu-id="7da90-109">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="7da90-110">在 SharePoint 小組網站中儲存檔案 (文件、投影片檔案、試算表等)。</span><span class="sxs-lookup"><span data-stu-id="7da90-110">Store digital assets (documents, slide decks, spreadsheets, etc.) in a SharePoint Online team site or in the Files tab of a Microsoft Teams team.</span></span>
- <span data-ttu-id="7da90-111">鎖定網站，以防止：</span><span class="sxs-lookup"><span data-stu-id="7da90-111">Lock down the site or team to prevent:</span></span>
  - <span data-ttu-id="7da90-112">非網站的 Office 365 群組成員的使用者存取。</span><span class="sxs-lookup"><span data-stu-id="7da90-112">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="7da90-113">網站成員將存取權授與其他使用者。</span><span class="sxs-lookup"><span data-stu-id="7da90-113">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="7da90-114">非網站成員要求網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="7da90-114">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="7da90-115">為 SharePoint 網站設定 Office 365 保留標籤，作為防止使用者在組織外部傳送檔案的預設方法。</span><span class="sxs-lookup"><span data-stu-id="7da90-115">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="7da90-116">使用隨檔案一起移動的加密來加密網站中最敏感的檔案。</span><span class="sxs-lookup"><span data-stu-id="7da90-116">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="7da90-117">將權限新增至最敏感的檔案，以致於雖然是在網站外部共用這些檔案，開啟檔案時仍然需要具有權限之使用者帳戶的有效認證。</span><span class="sxs-lookup"><span data-stu-id="7da90-117">Add permissions to the most sensitive digital assets so that if even if they get shared outside of the site, opening the asset still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="7da90-118">下表將此案例的需求對應至 Microsoft 365 企業版的功能。</span><span class="sxs-lookup"><span data-stu-id="7da90-118">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="7da90-119">**需求**</span><span class="sxs-lookup"><span data-stu-id="7da90-119">**Requirement**</span></span> | <span data-ttu-id="7da90-120">**Microsoft 365 企業版功能**</span><span class="sxs-lookup"><span data-stu-id="7da90-120">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="7da90-121">儲存檔案</span><span class="sxs-lookup"><span data-stu-id="7da90-121">Store files online</span></span> | <span data-ttu-id="7da90-122">SharePoint 小組網站</span><span class="sxs-lookup"><span data-stu-id="7da90-122">Sensitive SharePoint Online team sites</span></span> |
| <span data-ttu-id="7da90-123">鎖定網站</span><span class="sxs-lookup"><span data-stu-id="7da90-123">Lock down the site</span></span> | <span data-ttu-id="7da90-124">Azure Active Directory (Azure AD) 群組和 SharePoint 小組網站權限</span><span class="sxs-lookup"><span data-stu-id="7da90-124">Azure Active Directory (Azure AD) groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="7da90-125">為網站上的檔案新增標籤</span><span class="sxs-lookup"><span data-stu-id="7da90-125">Label the digital assets of the site</span></span> | <span data-ttu-id="7da90-126">Office 365 保留標籤</span><span class="sxs-lookup"><span data-stu-id="7da90-126">Office 365 retention labels</span></span> |
| <span data-ttu-id="7da90-127">將檔案傳送到組織外部時封鎖使用者</span><span class="sxs-lookup"><span data-stu-id="7da90-127">Block users when sending files outside the organization</span></span> | <span data-ttu-id="7da90-128">Office 365 中的資料外洩防護 (DLP) 原則</span><span class="sxs-lookup"><span data-stu-id="7da90-128">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="7da90-129">加密網站上的所有檔案</span><span class="sxs-lookup"><span data-stu-id="7da90-129">Encrypt all of the digital assets of the site</span></span> | <span data-ttu-id="7da90-130">Office 365 敏感度子標籤</span><span class="sxs-lookup"><span data-stu-id="7da90-130">Office 365 sensitivity sublabels</span></span> |
| <span data-ttu-id="7da90-131">新增權限至網站的檔案</span><span class="sxs-lookup"><span data-stu-id="7da90-131">Add permissions to the digital assets of the site</span></span> | <span data-ttu-id="7da90-132">Office 365 敏感度子標籤</span><span class="sxs-lookup"><span data-stu-id="7da90-132">Office 365 sensitivity sublabels</span></span> |
|||

<span data-ttu-id="7da90-133">以下是安全的 SharePoint 網站的設定。</span><span class="sxs-lookup"><span data-stu-id="7da90-133">Here is the configuration for a SharePoint Online site.</span></span>

![適用於高度管制資料的 SharePoint 網站案例](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="7da90-135">此案例需要您已部署：</span><span class="sxs-lookup"><span data-stu-id="7da90-135">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="7da90-136">基礎結構的[身分識別](identity-infrastructure.md)階段及[資訊保護](infoprotect-infrastructure.md)階段的步驟 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="7da90-136">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="7da90-137">[SharePoint](sharepoint-online-onedrive-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="7da90-137">SharePoint</span></span>

<span data-ttu-id="7da90-138">下列階段會逐步帶您針對適用於高度管制資料的 SharePoint 網站，進行設計、設定及推動採用。</span><span class="sxs-lookup"><span data-stu-id="7da90-138">The following phases step you through designing, configuring, and driving adoption for SharePoint Online sites and teams for highly regulated data.</span></span>

<span data-ttu-id="7da90-139">若要查看 Contoso Corporation (虛構但有代表性的跨國企業) 如何為其研究小組設計 SharePoint 網站，請參閱[範例設定](contoso-sharepoint-online-site-for-highly-confidential-assets.md)。</span><span class="sxs-lookup"><span data-stu-id="7da90-139">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint Online site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="7da90-140">身分識別與裝置存取必要條件</span><span class="sxs-lookup"><span data-stu-id="7da90-140">Identity and device access prerequisites</span></span>

<span data-ttu-id="7da90-141">若要保護 SharePoint 網站的存取權，請確定您已設定[身分識別與裝置存取原則](identity-access-policies.md)和[建議的 SharePoint 存取原則](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7da90-141">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="7da90-142">階段 1：設計</span><span class="sxs-lookup"><span data-stu-id="7da90-142">Phase 1: Design</span></span>

<span data-ttu-id="7da90-143">若為高度管制的資料建立 SharePoint 網站，您必須先確定網站的目的。</span><span class="sxs-lookup"><span data-stu-id="7da90-143">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="7da90-144">例如，製造業組織的研發部門需要 SharePoint 網站來儲存現有產品的目前設計規格，以及在新產品上共同作業。</span><span class="sxs-lookup"><span data-stu-id="7da90-144">To create a SharePoint Online site or team for highly regulated data, you must first identify its purpose. For example, the research and development department of a manufacturing organization needs a SharePoint Online site to store current design specifications for existing products and a place to collaborate on new products. Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span> <span data-ttu-id="7da90-145">只有研發部門和選取的主管成員才允許存取網站。</span><span class="sxs-lookup"><span data-stu-id="7da90-145">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="7da90-146">該目的會驅使基本組態項目的決定，例如：</span><span class="sxs-lookup"><span data-stu-id="7da90-146">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="7da90-147">要指派至網站的文件部分以及標籤的 DLP 原則集合的 Office 365 保留標籤</span><span class="sxs-lookup"><span data-stu-id="7da90-147">The Office 365 retention label to assign to the site and the set of DLP policies for the label</span></span>
- <span data-ttu-id="7da90-148">Office 365 敏感度子標籤的設定，可讓使用者套用到儲存在網站中的高度敏感檔案</span><span class="sxs-lookup"><span data-stu-id="7da90-148">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="7da90-149">決定後，您就能使用這些設定在階段 2 中設定網站。</span><span class="sxs-lookup"><span data-stu-id="7da90-149">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="7da90-150">步驟 1：Office 365 保留標籤和 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="7da90-150">Step 2: Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="7da90-151">當套用至 SharePoint 小組網站的文件部分時，Office 365 保留標籤提供預設方法，來分類儲存在網站上的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="7da90-151">When applied to a SharePoint Online team site, Office 365 retention labels provide a default method of classifying all digital assets stored on the site.</span></span>
 
<span data-ttu-id="7da90-152">針對適用於高度管制資料的 SharePoint 網站，您必須決定要使用哪個 Office 365 保留標籤。</span><span class="sxs-lookup"><span data-stu-id="7da90-152">For SharePoint Online sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="7da90-153">如需 Office 365 標籤的設計考量，請參閱 [Office 365 分類和標籤](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="7da90-153">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="7da90-p103">若要保護機密資訊並防止意外或故意洩露，您可以使用 DLP 原則。如需詳細資訊，請參閱[概觀](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)。</span><span class="sxs-lookup"><span data-stu-id="7da90-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="7da90-156">針對 SharePoint 網站，您必須針對指派至網站的 Office 365 保留標籤設定 DLP 原則，以在使用者嘗試與外部使用者共用檔案時，封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="7da90-156">For SharePoint Online sites for highly regulated data, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share digital assets with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="7da90-157">步驟 2：您的 Office 365 敏感度子標籤</span><span class="sxs-lookup"><span data-stu-id="7da90-157">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="7da90-158">若要將加密和權限集提供給最敏感的檔案，使用者必須套用 Office 365 敏感度子標籤。</span><span class="sxs-lookup"><span data-stu-id="7da90-158">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity sublabel.</span></span>

<span data-ttu-id="7da90-159">子標籤位於現有標籤下方。</span><span class="sxs-lookup"><span data-stu-id="7da90-159">A sublabel exists under an existing label.</span></span> <span data-ttu-id="7da90-160">例如，您可以在高度管制標籤底下建立研發子標籤。</span><span class="sxs-lookup"><span data-stu-id="7da90-160">For example, you can create a Research & Development sublabel under the Highly Regulated label.</span></span> <span data-ttu-id="7da90-161">對於適用於高度管制資料的 SharePoint 網站，您需設定權限，只允許網站成員能開啟及變更附加子標籤的檔案。</span><span class="sxs-lookup"><span data-stu-id="7da90-161">For SharePoint sites for highly regulated data, you configure the permissions so that only site members can open and change the file to which the sublabel is attached.</span></span>

<span data-ttu-id="7da90-162">所套用的子標籤設定會隨著檔案移動。</span><span class="sxs-lookup"><span data-stu-id="7da90-162">The settings of the applied sublabel travel with the file.</span></span> <span data-ttu-id="7da90-163">即使檔案流出網站外部，也只有擁有權限的已驗證使用者帳戶能開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="7da90-163">The settings of the applied sub-label travel with the asset. Even if it is downloaded and shared outside the site, only authenticated user accounts that have permissions can open it.</span></span>


### <a name="design-results"></a><span data-ttu-id="7da90-164">設計結果</span><span class="sxs-lookup"><span data-stu-id="7da90-164">Design results</span></span>

<span data-ttu-id="7da90-165">您已決定下列項目：</span><span class="sxs-lookup"><span data-stu-id="7da90-165">You have determined the following:</span></span>

- <span data-ttu-id="7da90-166">適當的 Office 365 保留標籤和與標籤相關聯的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="7da90-166">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="7da90-167">包含加密和權限的 Office 365 敏感度子標籤設定</span><span class="sxs-lookup"><span data-stu-id="7da90-167">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="7da90-168">階段 2：設定</span><span class="sxs-lookup"><span data-stu-id="7da90-168">Phase 2: Configure</span></span>

<span data-ttu-id="7da90-169">在這個階段中，您會採用在階段 1 中決定的設定，然後實作這些設定來建立適用於高度管制資料的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="7da90-169">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint Online site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="7da90-170">步驟 1：使用對應 Office 365 群組的擁有者和成員來建立私人 SharePoint 小組網站</span><span class="sxs-lookup"><span data-stu-id="7da90-170">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="7da90-171">按照[以下指示]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8)來建立私人 SharePoint 小組網站。</span><span class="sxs-lookup"><span data-stu-id="7da90-171">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="7da90-172">步驟 2：為 SharePoint 小組網站設定額外的權限設定</span><span class="sxs-lookup"><span data-stu-id="7da90-172">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="7da90-173">從 SharePoint 網站設定這些權限設定。</span><span class="sxs-lookup"><span data-stu-id="7da90-173">From the SharePoint site, configure these permission settings.</span></span>

1.  <span data-ttu-id="7da90-174">在工具列中，按一下設定圖示，然後按一下 [網站權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7da90-174">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="7da90-175">在 [網站權限]\*\*\*\* 窗格中，按一下 [進階權限設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7da90-175">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
3.  <span data-ttu-id="7da90-176">在新的 [權限]\*\*\*\* 瀏覽器索引標籤中，按一下 [存取要求設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7da90-176">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
4.  <span data-ttu-id="7da90-177">在 [存取要求設定]\*\*\*\* 對話方塊中，清除 [允許成員共用網站以及個別檔案和資料夾]\*\*\*\* 和 [允許存取要求]\*\*\*\* 核取方塊，(以全部清除這三個核取方塊)，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7da90-177">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>

<span data-ttu-id="7da90-178">清除這些設定後，網站群組成員與其他成員或非成員要求網站存取權以共用網站的功能將會停用。</span><span class="sxs-lookup"><span data-stu-id="7da90-178">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="7da90-179">步驟 3：針對 Office 365 保留標籤設定網站</span><span class="sxs-lookup"><span data-stu-id="7da90-179">Step 2: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="7da90-180">使用[使用 Office 365 標籤與 DLP 來保護 SharePoint 檔案](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)中的指示來：</span><span class="sxs-lookup"><span data-stu-id="7da90-180">Use the instructions in [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="7da90-181">建立並發布適用於高度管制資料的保留標籤 (如有需要)。</span><span class="sxs-lookup"><span data-stu-id="7da90-181">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="7da90-182">針對步驟 1 中建立的保留標籤設定網站。</span><span class="sxs-lookup"><span data-stu-id="7da90-182">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="7da90-183">為使用在步驟 2 中建立的保留標籤的高度管制資料建立 DLP 原則，並封鎖使用者在組織外傳送檔案</span><span class="sxs-lookup"><span data-stu-id="7da90-183">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="7da90-184">步驟 4：為網站建立 Office 365 敏感度子標籤</span><span class="sxs-lookup"><span data-stu-id="7da90-184">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="7da90-185">適用於高度管制資料的敏感度標籤可讓任何人套用至任何檔案，但是安全網站不同，它需要自己的子標籤，以致於指派子標籤的檔案都能：</span><span class="sxs-lookup"><span data-stu-id="7da90-185">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="7da90-186">受到加密，且加密會隨檔案移動。</span><span class="sxs-lookup"><span data-stu-id="7da90-186">Are encrypted and the encryption travels with the file.</span></span>
-   <span data-ttu-id="7da90-187">包含自訂權限，因此只有網站群組的成員能夠開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="7da90-187">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="7da90-188">若要針對儲存在網站中的檔案完成這項額外的安全性，您必須設定一個新的敏感度標籤，而它屬於高度管制檔案之一般標籤的子標籤。</span><span class="sxs-lookup"><span data-stu-id="7da90-188">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="7da90-189">只有網站的群組成員能在高度管制標籤的子標籤清單中看到該網站。</span><span class="sxs-lookup"><span data-stu-id="7da90-189">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="7da90-190">使用[這裡](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)的指示來為高度管制檔案所使用的標籤設定子標籤，其設定如下：</span><span class="sxs-lookup"><span data-stu-id="7da90-190">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="7da90-191">子標籤的名稱包含網站名稱，以便在將子標籤指派到檔案時輕鬆建立關聯。</span><span class="sxs-lookup"><span data-stu-id="7da90-191">The name of the sublabel contains the name of the site for easy association when assign the sublabel to a file.</span></span>
- <span data-ttu-id="7da90-192">啟用加密。</span><span class="sxs-lookup"><span data-stu-id="7da90-192">Encryption is enabled.</span></span>
- <span data-ttu-id="7da90-193">網站群組具有共同撰寫權限。</span><span class="sxs-lookup"><span data-stu-id="7da90-193">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="7da90-194">設定結果</span><span class="sxs-lookup"><span data-stu-id="7da90-194">Configuration results</span></span>

<span data-ttu-id="7da90-195">您已設定下列項目：</span><span class="sxs-lookup"><span data-stu-id="7da90-195">You have configured the following:</span></span>

- <span data-ttu-id="7da90-196">SharePoint 網站上的其他限制權限設定</span><span class="sxs-lookup"><span data-stu-id="7da90-196">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="7da90-197">指派給 SharePoint 網站文件部分的 Office 365 保留標籤</span><span class="sxs-lookup"><span data-stu-id="7da90-197">An Office 365 retention label assigned to the SharePoint Online isolated site</span></span>
- <span data-ttu-id="7da90-198">Office 365 保留標籤的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="7da90-198">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="7da90-199">使用者可將 Office 365 敏感度子標籤套用到儲存在網站中的最敏感檔案，其會加密檔案並只允許小組網站群組的成員擁有共同撰寫存取權</span><span class="sxs-lookup"><span data-stu-id="7da90-199">An Office 365 sensitivity sublabel that users can apply to the most sensitive files stored in the site that encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="7da90-200">以下是所產生的設定。</span><span class="sxs-lookup"><span data-stu-id="7da90-200">Here is the resulting configuration.</span></span>

![適用於高度管制資料的 SharePoint 網站案例](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)


<span data-ttu-id="7da90-202">以下是使用者已將敏感度子標籤套用至儲存在網站中的檔案的範例。</span><span class="sxs-lookup"><span data-stu-id="7da90-202">Here is an example of a user that has applied the sensitivity sublabel to a file stored in the site.</span></span>

![適用於高度管制資料的 SharePoint 網站案例](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="7da90-204">階段 3：推動使用者採用</span><span class="sxs-lookup"><span data-stu-id="7da90-204">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="7da90-205">如果一直將適用於高度管制資料的 SharePoint 網站用於儲存和存取敏感檔案，則 SharePoint 網站只能保護資料。</span><span class="sxs-lookup"><span data-stu-id="7da90-205">A SharePoint Online site or team for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive digital assets. This is the hardest phase because it relies on users changing their ways.</span></span> <span data-ttu-id="7da90-206">這是最難的階段，因為這有賴於使用者變更習慣和偏好。</span><span class="sxs-lookup"><span data-stu-id="7da90-206">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="7da90-207">例如，員工以前都習慣將敏感檔案儲存在 USB 磁碟或個人雲端式儲存解決方案，而現在必須將檔案單獨儲存在適用於高度管制資料的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="7da90-207">For example, executives that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint Online site or team for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="7da90-208">步驟 1：訓練您的使用者</span><span class="sxs-lookup"><span data-stu-id="7da90-208">Step 1: Train your users</span></span>

<span data-ttu-id="7da90-209">完成您的設定之後，請訓練一組使用者，這些使用者是網站存取群組的成員：</span><span class="sxs-lookup"><span data-stu-id="7da90-209">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="7da90-210">了解使用新網站來保護有價值檔案的重要性以及高度管制資料外洩的後果，例如法律後果、法規罰款、勒索軟體或喪失競爭優勢。</span><span class="sxs-lookup"><span data-stu-id="7da90-210">On the importance of using the new site or team to protect valuable assets and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="7da90-211">如何存取網站及其檔案。</span><span class="sxs-lookup"><span data-stu-id="7da90-211">How to access the site and its assets.</span></span>
- <span data-ttu-id="7da90-212">如何在網站上建立新檔案，以及上傳儲存在本機的新檔案。</span><span class="sxs-lookup"><span data-stu-id="7da90-212">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="7da90-213">DLP 原則如何封鎖他們免於在外部共用檔案。</span><span class="sxs-lookup"><span data-stu-id="7da90-213">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="7da90-214">如何使用網站的子標籤來標記最敏感的檔案。</span><span class="sxs-lookup"><span data-stu-id="7da90-214">How to label the most sensitive files with the sublabel for the site.</span></span>
- <span data-ttu-id="7da90-215">子標籤如何保護檔案，即使該檔案從網站外洩。</span><span class="sxs-lookup"><span data-stu-id="7da90-215">How the sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="7da90-216">此訓練應該包含實際操作練習，讓使用者可以體驗這些作業及其結果。</span><span class="sxs-lookup"><span data-stu-id="7da90-216">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="7da90-217">步驟 2：進行使用量和檔案的定期檢閱</span><span class="sxs-lookup"><span data-stu-id="7da90-217">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="7da90-218">在幾週的訓練之後，SharePoint 網站的 SharePoint 系統管理員可以：</span><span class="sxs-lookup"><span data-stu-id="7da90-218">In the weeks after training, the SharePoint administrator for the SharePoint Online site or team can:</span></span>

- <span data-ttu-id="7da90-219">分析網站的使用方式，並且與預期使用方式進行比較。</span><span class="sxs-lookup"><span data-stu-id="7da90-219">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="7da90-220">確認已使用敏感度子標籤正確地標示高度敏感檔案。</span><span class="sxs-lookup"><span data-stu-id="7da90-220">Verify that sensitive or highly regulated files have been properly labeled with the appropriate sensitivity label.</span></span>

<span data-ttu-id="7da90-221">視需要重新訓練您的使用者。</span><span class="sxs-lookup"><span data-stu-id="7da90-221">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="7da90-222">使用者採用結果</span><span class="sxs-lookup"><span data-stu-id="7da90-222">User adoption results</span></span>

<span data-ttu-id="7da90-223">高度管制的檔案會單獨儲存在適用於高度管制資料的 SharePoint 網站上，且最敏感的檔案已套用網站的敏感度子標籤。</span><span class="sxs-lookup"><span data-stu-id="7da90-223">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="7da90-224">Contoso Corporation 如何部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="7da90-224">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7da90-225">Contoso Corporation 是虛構但具代表性的全球製造業集團，其總部位於法國巴黎。</span><span class="sxs-lookup"><span data-stu-id="7da90-225">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="7da90-226">查看 Contoso 如何設計、設定，然後為其在巴黎、莫斯科、紐約、北京和班加羅爾的研究小組推動採用[安全的 SharePoint 網站](contoso-sharepoint-online-site-for-highly-confidential-assets.md)。</span><span class="sxs-lookup"><span data-stu-id="7da90-226">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint Online site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="7da90-227">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7da90-227">See also</span></span>

[<span data-ttu-id="7da90-228">部署指南</span><span class="sxs-lookup"><span data-stu-id="7da90-228">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="7da90-229">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="7da90-229">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

