---
title: 適用於高管制資料的 Microsoft Teams 和 SharePoint Online 網站
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/03/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 建立安全的 SharePoint Online 小組網站或 Microsoft Teams 小組，以儲存您最有價值且機密的數位資產。
ms.openlocfilehash: 1243a88e6553b1d58370a60b5e2fec38d3dbcaf6
ms.sourcegitcommit: 681ae93ca1d07532944665cf5d99ff1f08c0b46a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2019
ms.locfileid: "37210049"
---
# <a name="microsoft-teams-and-sharepoint-online-sites-for-highly-regulated-data"></a><span data-ttu-id="039e7-103">適用於高管制資料的 Microsoft Teams 和 SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="039e7-103">Microsoft Teams and SharePoint Online sites for highly regulated data</span></span>

<span data-ttu-id="039e7-104">*此案例同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="039e7-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="039e7-p101">Microsoft 365 企業版包含一套完整的雲端式服務，因此您可以建立、儲存和保護高管制資料。包含的資料為：</span><span class="sxs-lookup"><span data-stu-id="039e7-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data. This includes data that is:</span></span>

- <span data-ttu-id="039e7-107">受限於區域法規。</span><span class="sxs-lookup"><span data-stu-id="039e7-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="039e7-108">貴組織最有價值的資料，例如營業秘密、財務或人力資源資訊，以及組織策略。</span><span class="sxs-lookup"><span data-stu-id="039e7-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="039e7-109">符合此商務需求的 Microsoft 365 企業版雲端式案例需要您：</span><span class="sxs-lookup"><span data-stu-id="039e7-109">A Microsoft 365 Enterprise cloud-based solution that meets this business need requires that you:</span></span>

- <span data-ttu-id="039e7-110">將數位資產 (文件、投影片組、試算表等等) 儲存在 SharePoint Online 小組網站或 Microsoft Teams 小組的 [檔案]\*\*\*\* 索引標籤中。</span><span class="sxs-lookup"><span data-stu-id="039e7-110">Store digital assets (documents, slide decks, spreadsheets, etc.) in a SharePoint Online team site or in the **Files** tab of a Microsoft Teams team.</span></span>
- <span data-ttu-id="039e7-111">鎖定網站或小組，以防止：</span><span class="sxs-lookup"><span data-stu-id="039e7-111">Lock down the site or team to prevent:</span></span>
   - <span data-ttu-id="039e7-112">透過群組成員資格僅存取一組特定的使用者帳戶，這包含可以用哪個權限等級存取 SharePoint Online 小組網站的使用者，以及可以進行管理的使用者。</span><span class="sxs-lookup"><span data-stu-id="039e7-112">Access to only a specific set of user accounts through group membership, which includes those who can access the SharePoint Online team site and at what level of permission, and those who can administer it.</span></span>
   - <span data-ttu-id="039e7-113">網站成員將存取權授與其他使用者。</span><span class="sxs-lookup"><span data-stu-id="039e7-113">Members of the site from granting access to others.</span></span>
   - <span data-ttu-id="039e7-114">非網站成員要求網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="039e7-114">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="039e7-115">為您的 SharePoint Online 網站或小組設定 Office 365 保留標籤，作為在網站或小組中的文件上定義保留原則的預設方法。</span><span class="sxs-lookup"><span data-stu-id="039e7-115">Configure an Office 365 retention label for your SharePoint Online sites or teams as a default way to define retention policies on the documents in the site or team.</span></span>
- <span data-ttu-id="039e7-116">防止使用者將檔案傳送到組織外部。</span><span class="sxs-lookup"><span data-stu-id="039e7-116">Block users from sending files outside the organization.</span></span>
- <span data-ttu-id="039e7-117">加密網站或小組上最機密的數位資產。</span><span class="sxs-lookup"><span data-stu-id="039e7-117">Encrypt the most sensitive digital assets of the site or team.</span></span>
- <span data-ttu-id="039e7-118">新增權限至最機密的數位資產，即使這些資產在網站外部共用，開啟資產時仍然需要具有權限之使用者帳戶的有效認證。</span><span class="sxs-lookup"><span data-stu-id="039e7-118">Add permissions to the most sensitive digital assets so that if even if they get shared outside of the site, opening the asset still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="039e7-119">下表將此案例的需求對應至 Microsoft 365 企業版的功能。</span><span class="sxs-lookup"><span data-stu-id="039e7-119">The following table maps the requirements of this solution to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="039e7-120">**需求**</span><span class="sxs-lookup"><span data-stu-id="039e7-120">**Requirement**</span></span> | <span data-ttu-id="039e7-121">**Microsoft 365 企業版功能**</span><span class="sxs-lookup"><span data-stu-id="039e7-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="039e7-122">儲存數位資產</span><span class="sxs-lookup"><span data-stu-id="039e7-122">Store digital assets</span></span> | <span data-ttu-id="039e7-123">SharePoint Online 小組網站和 Office 365 中的小組</span><span class="sxs-lookup"><span data-stu-id="039e7-123">SharePoint Online team sites and teams in Office 365</span></span> |
| <span data-ttu-id="039e7-124">鎖定網站</span><span class="sxs-lookup"><span data-stu-id="039e7-124">Lock down the site</span></span> | <span data-ttu-id="039e7-125">Azure AD 群組和 SharePoint Online 小組網站權限</span><span class="sxs-lookup"><span data-stu-id="039e7-125">Azure AD groups and SharePoint Online team site permissions</span></span> |
| <span data-ttu-id="039e7-126">標示網站的數位資產</span><span class="sxs-lookup"><span data-stu-id="039e7-126">Label the digital assets of the site</span></span> | <span data-ttu-id="039e7-127">Office 365 保留標籤</span><span class="sxs-lookup"><span data-stu-id="039e7-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="039e7-128">將檔案傳送到組織外部時封鎖使用者</span><span class="sxs-lookup"><span data-stu-id="039e7-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="039e7-129">Office 365 中的資料外洩防護 (DLP) 原則</span><span class="sxs-lookup"><span data-stu-id="039e7-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="039e7-130">加密網站的所有數位資產</span><span class="sxs-lookup"><span data-stu-id="039e7-130">Encrypt all of the digital assets of the site</span></span> | <span data-ttu-id="039e7-131">Enterprise Mobility + Security (EMS) 中的 Azure 資訊保護子標籤</span><span class="sxs-lookup"><span data-stu-id="039e7-131">Azure Information Protection sub-labels in Enterprise Mobility + Security (EMS)</span></span> |
| <span data-ttu-id="039e7-132">新增權限至網站的數位資產</span><span class="sxs-lookup"><span data-stu-id="039e7-132">Add permissions to the digital assets of the site</span></span> | <span data-ttu-id="039e7-133">EMS 中的 Azure 資訊保護子標籤</span><span class="sxs-lookup"><span data-stu-id="039e7-133">Azure Information Protection sub-labels in EMS</span></span> |
|||

<span data-ttu-id="039e7-134">以下是 SharePoint Online 網站的組態。</span><span class="sxs-lookup"><span data-stu-id="039e7-134">Here is the configuration for a SharePoint Online site.</span></span>

![適用於高管制資料案例的 Microsoft Teams 和 SharePoint Online 網站](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="039e7-136">此案例需要您已部署：</span><span class="sxs-lookup"><span data-stu-id="039e7-136">This solution requires that you have already deployed:</span></span>

- <span data-ttu-id="039e7-137">基礎結構的[身分識別](identity-infrastructure.md)階段及[資訊保護](infoprotect-infrastructure.md)階段的步驟 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="039e7-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="039e7-138">針對 SharePoint Online 小組網站中的高管制資料，部署 [SharePoint Online](sharepoint-online-onedrive-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="039e7-138">For highly regulated data in SharePoint Online team sites, [SharePoint Online](sharepoint-online-onedrive-workload.md).</span></span>
- <span data-ttu-id="039e7-139">針對 Microsoft Teams 小組中的高管制資料，部署 [Microsoft Teams](teams-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="039e7-139">For highly regulated data in Microsoft Teams teams, [Microsoft Teams](teams-workload.md).</span></span>

<span data-ttu-id="039e7-140">下列階段會逐步帶您針對適用於高管制資料的 SharePoint Online 網站和小組，進行設計、設定及推動採用。</span><span class="sxs-lookup"><span data-stu-id="039e7-140">The following phases step you through the design, configuration, and driving adoption for SharePoint Online sites and teams for highly regulated data.</span></span>

<span data-ttu-id="039e7-141">若要查看 Contoso Corporation (虛構但有代表性的跨國企業) 如何為其研究小組設計 SharePoint Online 網站，請參閱[範例設定](contoso-sharepoint-online-site-for-highly-confidential-assets.md)。</span><span class="sxs-lookup"><span data-stu-id="039e7-141">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint Online site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

<span data-ttu-id="039e7-p102">高管制資料的小組需要您先建立適用於高管制資料的 SharePoint Online 小組網站。然後建立新的小組，該小組使用 SharePoint Online 小組網站的 Office 365 群組。如需詳細資訊，請參閱階段 2，步驟 4。</span><span class="sxs-lookup"><span data-stu-id="039e7-p102">A team for highly regulated data requires that you first create a SharePoint Online team site for highly regulated data. You then create a new team that uses the Office 365 group of the SharePoint Online team site. See Phase 2, Step 4 for more information.</span></span>

<span data-ttu-id="039e7-145">以下是小組的組態。</span><span class="sxs-lookup"><span data-stu-id="039e7-145">Here is the configuration for a team.</span></span>

![適用於高管制資料案例的 Microsoft Teams 和 SharePoint Online 網站](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-team.png)


## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="039e7-147">身分識別與裝置存取必要條件</span><span class="sxs-lookup"><span data-stu-id="039e7-147">Identity and device access prerequisites</span></span>

<span data-ttu-id="039e7-148">若要保護小組或 SharePoint Online 網站的存取權，請確定您已設定[身分識別與裝置存取原則](identity-access-policies.md)和[建議的 SharePoint Online 存取原則](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="039e7-148">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="039e7-149">階段 1：設計</span><span class="sxs-lookup"><span data-stu-id="039e7-149">Phase 1: Design</span></span>

<span data-ttu-id="039e7-p103">若要建立適用於高管制資料的 SharePoint Online 網站或小組，您必須先識別其目的。例如，製造業組織的研究和開發部門需要 SharePoint Online 網站來儲存現有產品的目前設計規格，以及一個為新產品共同作業的地方。只有研究和開發部門的成員和選取的管理階層人員可以存取網站。</span><span class="sxs-lookup"><span data-stu-id="039e7-p103">To create a SharePoint Online site or team for highly regulated data, you must first identify its purpose. For example, the research and development department of a manufacturing organization needs a SharePoint Online site to store current design specifications for existing products and a place to collaborate on new products. Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="039e7-153">該目的會驅使基本組態項目的決定，例如：</span><span class="sxs-lookup"><span data-stu-id="039e7-153">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="039e7-154">SharePoint Online 權限集和 SharePoint 群組的集合</span><span class="sxs-lookup"><span data-stu-id="039e7-154">The set of SharePoint Online permission sets and SharePoint groups</span></span>
- <span data-ttu-id="039e7-155">存取群組的集合，要新增至 SharePoint 群組的 Azure AD 安全性群組及其成員</span><span class="sxs-lookup"><span data-stu-id="039e7-155">The set of access groups, the Azure AD security groups and their members to add to the SharePoint groups</span></span>
- <span data-ttu-id="039e7-156">要指派至網站和標籤的 DLP 原則集合的 Office 365 保留標籤</span><span class="sxs-lookup"><span data-stu-id="039e7-156">The Office 365 retention label to assign to the site and the set of DLP policies for the label</span></span>
- <span data-ttu-id="039e7-157">Azure 資訊保護子標籤的設定，使用者會將其套用至網站中的高度機密數位資產</span><span class="sxs-lookup"><span data-stu-id="039e7-157">The settings of an Azure Information Protection sub-label that users apply to highly sensitive digital assets stored in the site</span></span>

<span data-ttu-id="039e7-158">一旦決定，您會使用這些設定在階段 2 中設定網站。</span><span class="sxs-lookup"><span data-stu-id="039e7-158">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-an-isolated-sharepoint-online-site"></a><span data-ttu-id="039e7-159">步驟 1：隔離的 SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="039e7-159">Step 1: An isolated SharePoint Online site</span></span>

<span data-ttu-id="039e7-p104">鎖定版本的 SharePoint Online 小組網站也稱為隔離的網站。與私人小組網站的預設設定不同，隔離的網站是設定來防止：</span><span class="sxs-lookup"><span data-stu-id="039e7-p104">The locked-down version of a SharePoint Online team site is known as an isolated site. Unlike the default settings of private team sites, isolated sites are configured to prevent:</span></span>

- <span data-ttu-id="039e7-162">非指定群組成員的存取。</span><span class="sxs-lookup"><span data-stu-id="039e7-162">Access to those who are not members of specified groups.</span></span>
- <span data-ttu-id="039e7-163">要求存取。</span><span class="sxs-lookup"><span data-stu-id="039e7-163">The requesting of access.</span></span>
- <span data-ttu-id="039e7-164">指定群組目前成員未經授權授與存取權。</span><span class="sxs-lookup"><span data-stu-id="039e7-164">The unauthorized granting of access by current members of specified groups.</span></span>
- <span data-ttu-id="039e7-165">存取群組成員對網站進行系統管理。</span><span class="sxs-lookup"><span data-stu-id="039e7-165">Administration of the site by access group members.</span></span>

<span data-ttu-id="039e7-166">包含高管制資產之 SharePoint Online 小組網站的安全性不會變更，除非是由網站的 SharePoint 系統管理員執行。</span><span class="sxs-lookup"><span data-stu-id="039e7-166">The security of SharePoint Online team sites that contain highly regulated assets do not change unless done by a SharePoint administrator for the site.</span></span>

<span data-ttu-id="039e7-167">請參閱[設計隔離的 SharePoint Online 小組網站](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site)，以取得決定權限等級、SharePoint 群組、存取群組與群組成員集合的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="039e7-167">See [Design an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site) for the details to determine the set of permission levels, SharePoint groups, access groups, and group members.</span></span>

### <a name="step-2-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="039e7-168">步驟 2：Office 365 保留標籤和 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="039e7-168">Step 2: Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="039e7-169">當套用至 SharePoint Online 小組網站時，Office 365 保留標籤提供預設方法，來分類儲存在網站上的所有數位資產。</span><span class="sxs-lookup"><span data-stu-id="039e7-169">When applied to a SharePoint Online team site, Office 365 retention labels provide a default method of classifying all digital assets stored on the site.</span></span>
 
<span data-ttu-id="039e7-170">針對適用於高管制資料的 SharePoint Online 網站，您必須決定要使用哪個 Office 365 保留標籤。</span><span class="sxs-lookup"><span data-stu-id="039e7-170">For SharePoint Online sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="039e7-171">如需 Office 365 標籤的設計考量，請參閱 [Office 365 分類和標籤](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="039e7-171">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="039e7-p105">若要保護機密資訊並防止意外或故意洩露，您可以使用 DLP 原則。如需詳細資訊，請參閱[概觀](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)。</span><span class="sxs-lookup"><span data-stu-id="039e7-p105">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="039e7-174">針對適用於高管制資料的 SharePoint Online 網站，您必須針對指派至網站的 Office 365 保留標籤設定 DLP 原則，以在使用者嘗試與外部使用者共用數位資產時，封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="039e7-174">For SharePoint Online sites for highly regulated data, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share digital assets with external users.</span></span> 

### <a name="step-3-your-azure-information-protection-sub-label"></a><span data-ttu-id="039e7-175">步驟 3：您的 Azure 資訊保護子標籤</span><span class="sxs-lookup"><span data-stu-id="039e7-175">Step 3: Your Azure Information Protection sub-label</span></span>

<span data-ttu-id="039e7-p106">若要為最機密的數位資產提供加密和權限集，使用者必須使用 Azure 資訊保護用戶端來套用 Azure 資訊保護標籤。若要針對適用於高管制資料的 SharePoint Online 網站使用 Azure 資訊保護標籤，您必須在有範圍的原則中設定 Azure 資訊保護子標籤。</span><span class="sxs-lookup"><span data-stu-id="039e7-p106">To provide encryption and a set of permissions to your most sensitive digital assets, users must apply an Azure Information Protection label using the Azure Information Protection client. To use Azure Information Protection labels for SharePoint Online sites for highly regulated data, you must configure an Azure Information Protection sub-label in a scoped policy.</span></span> 

<span data-ttu-id="039e7-p107">子標籤存在於現有標籤底下。例如，您可以在「高度機密」標籤底下建立「研究和開發」子標籤。有範圍的原則是僅套用至使用者子集的原則。針對適用於高管制資料的 SharePoint Online 網站，範圍是屬於網站存取群組成員的使用者集合。</span><span class="sxs-lookup"><span data-stu-id="039e7-p107">A sub-label exists under an existing label. For example, you can create a Research & Development sub-label under the Highly Confidential label. A scoped policy is one that applies only to a subset of users. For SharePoint Online sites for highly regulated data, the scope is the set of users that are members of the access groups for the site.</span></span>

<span data-ttu-id="039e7-p108">已套用子標籤的設定會隨著資產移動。即使它已下載並且在網站外部共用，只有經過驗證的使用者帳戶有權可以開啟它。</span><span class="sxs-lookup"><span data-stu-id="039e7-p108">The settings of the applied sub-label travel with the asset. Even if it is downloaded and shared outside the site, only authenticated user accounts that have permissions can open it.</span></span>

### <a name="design-results"></a><span data-ttu-id="039e7-184">設計結果</span><span class="sxs-lookup"><span data-stu-id="039e7-184">Design results</span></span>

<span data-ttu-id="039e7-185">您已決定下列項目：</span><span class="sxs-lookup"><span data-stu-id="039e7-185">You have determined the following:</span></span>

- <span data-ttu-id="039e7-186">SharePoint 群組和權限等級的集合</span><span class="sxs-lookup"><span data-stu-id="039e7-186">The set of SharePoint groups and permission levels</span></span>
- <span data-ttu-id="039e7-187">存取群組和每個權限等級之成員的集合</span><span class="sxs-lookup"><span data-stu-id="039e7-187">The set of access groups and their members for each permission level</span></span>
- <span data-ttu-id="039e7-188">適當的 Office 365 保留標籤和與標籤相關聯的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="039e7-188">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="039e7-189">包含加密和權限的 Azure 資訊保護子標籤設定</span><span class="sxs-lookup"><span data-stu-id="039e7-189">The settings of the Azure Information Protection sub-label that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="039e7-190">階段 2：設定</span><span class="sxs-lookup"><span data-stu-id="039e7-190">Phase 2: Configure</span></span>

<span data-ttu-id="039e7-191">在這個階段中，您採用在階段 1 中決定的設定，然後實作以建立適用於高管制資料的 SharePoint Online 網站。</span><span class="sxs-lookup"><span data-stu-id="039e7-191">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint Online site for highly regulated data.</span></span>

### <a name="step-1-create-and-configure-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="039e7-192">步驟 1：建立及設定隔離的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="039e7-192">Step 1: Create and configure an isolated SharePoint Online team site</span></span>

<span data-ttu-id="039e7-193">使用[部署隔離的 SharePoint Online 小組網站](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site) 中的指示：</span><span class="sxs-lookup"><span data-stu-id="039e7-193">Use the instructions in [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site) to:</span></span>

- <span data-ttu-id="039e7-194">針對在網站上使用的每個 SharePoint 權限等級，建立及填入存取群組。</span><span class="sxs-lookup"><span data-stu-id="039e7-194">Create and populate the access groups for each SharePoint permission level used on the site.</span></span>
- <span data-ttu-id="039e7-195">建立及設定隔離的小組網站。</span><span class="sxs-lookup"><span data-stu-id="039e7-195">Create and configure the isolated team site.</span></span>

### <a name="step-2-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="039e7-196">步驟 2：針對 Office 365 保留標籤設定網站</span><span class="sxs-lookup"><span data-stu-id="039e7-196">Step 2: Configure the site for an Office 365 retention label DLP policy</span></span>

<span data-ttu-id="039e7-197">使用[使用 Office 365 標籤與 DLP 來保護 SharePoint Online 檔案](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)中的指示來：</span><span class="sxs-lookup"><span data-stu-id="039e7-197">Use the instructions in [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

- <span data-ttu-id="039e7-198">識別或建立 Office 365 保留標籤，並且將其套用至隔離的 SharePoint Online 網站。</span><span class="sxs-lookup"><span data-stu-id="039e7-198">Identify or create the Office 365 retention label and apply it to your isolated SharePoint Online site.</span></span>
- <span data-ttu-id="039e7-199">建立及設定 DLP 原則，該原則會在使用者嘗試在組織外部共用 SharePoint Online 網站上的數位資產時，封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="039e7-199">Create and configure the DLP policy that blocks users when they attempt to share a digital asset on your SharePoint Online site outside the organization.</span></span>

### <a name="step-3-create-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="039e7-200">步驟 3：針對網站建立 Azure 資訊保護子標籤</span><span class="sxs-lookup"><span data-stu-id="039e7-200">Step 3: Create an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="039e7-201">使用[使用 Azure 資訊保護來保護 SharePoint Online 檔案](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)中的指示來：</span><span class="sxs-lookup"><span data-stu-id="039e7-201">Use the instructions in [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection) to:</span></span> 

- <span data-ttu-id="039e7-202">在有範圍的原則中建立及設定 Azure 資訊保護子標籤。</span><span class="sxs-lookup"><span data-stu-id="039e7-202">Create and configure an Azure Information Protection sub-label in a scoped policy.</span></span>
- <span data-ttu-id="039e7-203">將 Azure 資訊保護用戶端部署至使用者電腦。</span><span class="sxs-lookup"><span data-stu-id="039e7-203">Deploy the Azure Information Protection client to user computers.</span></span>

### <a name="step-4-optional-create-a-team-for-the-highly-regulated-data"></a><span data-ttu-id="039e7-204">步驟 4 (選用)：建立適用於高管制資料的小組</span><span class="sxs-lookup"><span data-stu-id="039e7-204">Step 4 (optional): Create a team for the highly regulated data</span></span>

<span data-ttu-id="039e7-p109">如果您想要一個適用於高管制資料的小組，首先建立適用於高管制資料的 SharePoint Online 網站。當您建立初始私人 SharePoint Online 小組網站時，您會指定 Office 365 群組名稱。</span><span class="sxs-lookup"><span data-stu-id="039e7-p109">If you want a team for highly regulated data, you first create a SharePoint Online site for highly regulated data. When you create the initial private SharePoint Online team site, you specify an Office 365 group name.</span></span>

<span data-ttu-id="039e7-207">完整設定適用於高管制資料的 SharePoint Online 網站之後，使用以下步驟來將其轉換為適用於高管制資料的小組：</span><span class="sxs-lookup"><span data-stu-id="039e7-207">After the SharePoint Online site for highly regulated data is fully configured, use these steps to convert it into a team for highly regulated data:</span></span>

1. <span data-ttu-id="039e7-208">登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="039e7-208">Sign in to Office 365.</span></span>
2. <span data-ttu-id="039e7-209">從 [Microsoft Office 的首頁]\*\*\*\* 索引標籤中，按一下 [Teams]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="039e7-209">From the **Microsoft Office Home** tab, click **Teams**.</span></span>
3. <span data-ttu-id="039e7-210">從 [Microsoft Teams]\*\*\*\* 索引標籤的 [加入或建立小組]\*\*\*\* 窗格中，按一下 [建立小組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="039e7-210">From the **Microsoft Teams** tab, in the **Join or create a team** pane, click **Create team**.</span></span>
4. <span data-ttu-id="039e7-211">在 [建立您的小組]\*\*\*\* 窗格中，按一下 [從現有的 Office 365 群組建立小組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="039e7-211">In the **Create your team** pane, click **Create a team from an existing Office 365 group**.</span></span>
5. <span data-ttu-id="039e7-212">在 Office 365 群組的清單中，選取對應至適用於高管制資料的 SharePoint Online 網站的 Office 365 群組名稱，然後按一下 [選擇小組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="039e7-212">In the list of Office 365 groups, select the name of the Office 365 group corresponding to the SharePoint Online site for highly regulated data, and then click **Choose team**.</span></span>

<span data-ttu-id="039e7-p110">新小組的 [檔案]\*\*\*\* 索引標籤會列出對應 SharePoint Online 網站之 [文件]\*\*\*\* 區域中 [一般]\*\*\*\* 資料夾中的內容。若要查看適用於小組之 SharePoint Online 網站的其餘資源，請按一下省略符號，然後按一下 [在 SharePoint 中開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="039e7-p110">The **Files** tab of the new team lists the contents of the **General** folder of the **Documents** area of the corresponding SharePoint Online site. To see the rest of the resources of the SharePoint Online site for the team, click the ellipsis, and then click **Open in SharePoint**.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="039e7-215">設定結果</span><span class="sxs-lookup"><span data-stu-id="039e7-215">Configuration results</span></span>

<span data-ttu-id="039e7-216">您已設定下列項目：</span><span class="sxs-lookup"><span data-stu-id="039e7-216">You have configured the following:</span></span>

- <span data-ttu-id="039e7-217">SharePoint Online 隔離網站</span><span class="sxs-lookup"><span data-stu-id="039e7-217">A SharePoint Online isolated site</span></span>
- <span data-ttu-id="039e7-218">指派給 SharePoint Online 隔離網站的 Office 365 保留標籤</span><span class="sxs-lookup"><span data-stu-id="039e7-218">An Office 365 retention label assigned to the SharePoint Online isolated site</span></span>
- <span data-ttu-id="039e7-219">Office 365 保留標籤的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="039e7-219">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="039e7-220">使用者可以套用至最機密數位資產之有範圍原則的 Azure 資訊保護子標籤，是儲存在會加密資產並且強制執行權限的網站中。</span><span class="sxs-lookup"><span data-stu-id="039e7-220">An Azure Information Protection sub-label of a scoped policy that users can apply to the most sensitive digital assets stored in the site that encrypts the asset and enforces permissions</span></span>
- <span data-ttu-id="039e7-221">如有需要，適用於高管制資料的小組是以 SharePoint Online 網站為基礎</span><span class="sxs-lookup"><span data-stu-id="039e7-221">If needed, a team for highly regulated data based on the SharePoint Online site</span></span>

## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="039e7-222">階段 3：推動使用者採用</span><span class="sxs-lookup"><span data-stu-id="039e7-222">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="039e7-p111">適用於高管制資料的 SharePoint Online 網站或小組，只能在持續用於儲存和存取機密數位資產時保護資料。這是最難的階段，因為這個階段仰賴使用者改變他們的方式。</span><span class="sxs-lookup"><span data-stu-id="039e7-p111">A SharePoint Online site or team for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive digital assets. This is the hardest phase because it relies on users changing their ways.</span></span> 

<span data-ttu-id="039e7-225">例如，以往都是將機密檔案儲存在 USB 磁碟或個人雲端式儲存解決方案的管理階層人員，現在必須將檔案完全都儲存在適用於高管制資料的 SharePoint Online 網站或小組中。</span><span class="sxs-lookup"><span data-stu-id="039e7-225">For example, executives that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint Online site or team for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="039e7-226">步驟 1：訓練您的使用者</span><span class="sxs-lookup"><span data-stu-id="039e7-226">Step 1: Train your users</span></span>

<span data-ttu-id="039e7-227">完成您的設定之後，請訓練一組使用者，這些使用者是網站存取群組的成員：</span><span class="sxs-lookup"><span data-stu-id="039e7-227">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="039e7-228">著重在使用新網站或小組來保護有價值資產的重要性，以及高管制資料外洩的後果，例如法律後果、法規罰款、勒索軟體或喪失競爭優勢。</span><span class="sxs-lookup"><span data-stu-id="039e7-228">On the importance of using the new site or team to protect valuable assets and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="039e7-229">如何存取網站及其資產。</span><span class="sxs-lookup"><span data-stu-id="039e7-229">How to access the site and its assets.</span></span>
- <span data-ttu-id="039e7-230">如何在網站上建立新檔案，以及上傳儲存在本機的新檔案。</span><span class="sxs-lookup"><span data-stu-id="039e7-230">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="039e7-231">DLP 原則如何封鎖他們免於在外部共用檔案。</span><span class="sxs-lookup"><span data-stu-id="039e7-231">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="039e7-232">如何使用 Azure 資訊保護用戶端，以設定的子標籤來標示最機密的數位資產。</span><span class="sxs-lookup"><span data-stu-id="039e7-232">How to use the Azure Information Protection client to label the most sensitive digital assets with the configured sub-label.</span></span>
- <span data-ttu-id="039e7-233">Azure 資訊保護子標籤如何在資產即使是洩漏到網站或小組外部時加以保護。</span><span class="sxs-lookup"><span data-stu-id="039e7-233">How the Azure Information Protection sub-label protects an asset even when it is leaked off the site or team.</span></span>

<span data-ttu-id="039e7-234">此訓練應該包含實際操作練習，讓使用者可以體驗這些作業及其結果。</span><span class="sxs-lookup"><span data-stu-id="039e7-234">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="039e7-235">步驟 2：進行使用量和檔案的定期檢閱</span><span class="sxs-lookup"><span data-stu-id="039e7-235">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="039e7-236">在幾週的訓練之後，SharePoint Online 網站或小組的 SharePoint 系統管理員可以：</span><span class="sxs-lookup"><span data-stu-id="039e7-236">In the weeks after training, the SharePoint administrator for the SharePoint Online site or team can:</span></span>

- <span data-ttu-id="039e7-237">分析網站或小組的使用量，並且與預期使用量進行比較。</span><span class="sxs-lookup"><span data-stu-id="039e7-237">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="039e7-238">確認高度機密檔案已使用 Azure 資訊保護子標籤適當地標示。</span><span class="sxs-lookup"><span data-stu-id="039e7-238">Verify that highly sensitive files have been properly labeled with the Azure Information Protection sub-label.</span></span>

<span data-ttu-id="039e7-239">視需要重新訓練您的使用者。</span><span class="sxs-lookup"><span data-stu-id="039e7-239">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="039e7-240">使用者採用結果</span><span class="sxs-lookup"><span data-stu-id="039e7-240">User adoption results</span></span>

<span data-ttu-id="039e7-241">機密數位資產僅儲存在適用於高管制資料的 SharePoint Online 網站或小組上，最機密的資產已設定為套用 Azure 資訊保護子標籤。</span><span class="sxs-lookup"><span data-stu-id="039e7-241">Sensitive digital assets are stored exclusively on SharePoint Online sites or teams for highly regulated data and that the most sensitive assets have the configured Azure Information Protection sub-label applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="039e7-242">Contoso Corporation 如何部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="039e7-242">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="039e7-243">Contoso Corporation 是虛構但具代表性的全球製造業集團，其總部位於法國巴黎。</span><span class="sxs-lookup"><span data-stu-id="039e7-243">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="039e7-244">查看 Contoso 如何設計、設定，然後為其在巴黎、莫斯科、紐約、北京和班加羅爾的研究小組推動採用[安全的 SharePoint Online 網站](contoso-sharepoint-online-site-for-highly-confidential-assets.md)。</span><span class="sxs-lookup"><span data-stu-id="039e7-244">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint Online site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="039e7-245">請參閱</span><span class="sxs-lookup"><span data-stu-id="039e7-245">See also</span></span>

[<span data-ttu-id="039e7-246">部署指南</span><span class="sxs-lookup"><span data-stu-id="039e7-246">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="039e7-247">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="039e7-247">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="039e7-248">在開發/測試環境中保護 SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="039e7-248">Secure SharePoint Online sites in a dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-in-a-dev-test-environment)
