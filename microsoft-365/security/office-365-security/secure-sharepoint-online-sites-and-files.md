---
title: 保護 SharePoint Online 網站與檔案
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
- SPO_Content
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: 摘要：在 SharePoint Online 和 Office 365 中保護檔案的設定建議。
ms.openlocfilehash: 15b67d2569f2c8ceafb16973ae2bf6862ebb9ded
ms.sourcegitcommit: e4f2f06daa264b8b476813a2dfe80cffb59f968f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311107"
---
# <a name="secure-sharepoint-online-sites-and-files"></a><span data-ttu-id="38390-103">保護 SharePoint Online 網站與檔案</span><span class="sxs-lookup"><span data-stu-id="38390-103">Secure SharePoint Online sites and files</span></span>

 <span data-ttu-id="38390-104">**摘要：** 在 SharePoint Online 和 Office 365 中保護檔案的設定建議。</span><span class="sxs-lookup"><span data-stu-id="38390-104">**Summary:** Configuration recommendations for protecting files in SharePoint Online and Office 365.</span></span>
  
<span data-ttu-id="38390-p101">本文提供設定 SharePoint Online 小組網站和檔案保護的建議，以在安全性和順暢的共同作業間取得平衡。本文定義四種不同的設定，首先是組織內的公用網站，並搭配最開放的共用原則。每項額外設定均代表有意識的保護升級，但資源的存取和共同作業能力則會減少為只提供給相關使用者。使用建議作為起點，並且調整組態以符合您的組織的需求。</span><span class="sxs-lookup"><span data-stu-id="38390-p101">This article provides recommendations for configuring SharePoint Online team sites and file protection that balances security with ease of collaboration. This article defines four different configurations, starting with a public site within your organization with the most open sharing policies. Each additional configuration represents a meaningful step up in protection, but the ability to access and collaborate on resources is reduced to the relevant set of users. Use these recommendations as a starting point and adjust the configurations to meet the needs of your organization.</span></span>
  
<span data-ttu-id="38390-109">本文的設定符合 Microsoft 針對資料、身分識別和裝置的下列三層保護建議：</span><span class="sxs-lookup"><span data-stu-id="38390-109">The configurations in this article align with Microsoft's recommendations for three tiers of protection for data, identities, and devices:</span></span>
  
- <span data-ttu-id="38390-110">基準保護</span><span class="sxs-lookup"><span data-stu-id="38390-110">Baseline protection</span></span>
    
- <span data-ttu-id="38390-111">敏感性保護</span><span class="sxs-lookup"><span data-stu-id="38390-111">Sensitive protection</span></span>
    
- <span data-ttu-id="38390-112">高度機密保護</span><span class="sxs-lookup"><span data-stu-id="38390-112">Highly confidential protection</span></span>
    
<span data-ttu-id="38390-113">如需這些層級和每道層級的建議功能詳細資訊，請參閱下列資源。</span><span class="sxs-lookup"><span data-stu-id="38390-113">For more information about these tiers and capabilities recommended for each tier, see the following resources.</span></span>
  
- [<span data-ttu-id="38390-114">Office 365 的身分識別與裝置保護</span><span class="sxs-lookup"><span data-stu-id="38390-114">Identity and Device Protection for Office 365</span></span>](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#BKMK_O365IDP)
    
- [<span data-ttu-id="38390-115">Office 365 的檔案保護方案</span><span class="sxs-lookup"><span data-stu-id="38390-115">File Protection Solutions in Office 365</span></span>](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#BKMK_O365fileprotect)
    
## <a name="capability-overview"></a><span data-ttu-id="38390-116">功能概觀</span><span class="sxs-lookup"><span data-stu-id="38390-116">Capability overview</span></span>

<span data-ttu-id="38390-117">建議的 SharePoint Online 小組網站依據各種不同 Microsoft 365 功能而定。</span><span class="sxs-lookup"><span data-stu-id="38390-117">Recommendations for SharePoint Online team sites draw on a variety of Microsoft 365 capabilities.</span></span> <span data-ttu-id="38390-118">下圖顯示四種 SharePoint Online 小組網站的建議設定。</span><span class="sxs-lookup"><span data-stu-id="38390-118">The following illustration shows the recommended configurations for four SharePoint Online team sites.</span></span>

![SharePoint 網站的建議設定](../media/SharePoint-site-configurations.png)

<span data-ttu-id="38390-120">如圖例所示：</span><span class="sxs-lookup"><span data-stu-id="38390-120">As illustrated:</span></span>
  
- <span data-ttu-id="38390-p103">基準保護包括公用網站與私用網站這兩個 SharePoint Online 小組網站的選項。 公用網站可供組織中的任何人探索及存取。 私用網站則僅供網站成員探索及存取。 這兩個網站的設定都允許群組外部共用。</span><span class="sxs-lookup"><span data-stu-id="38390-p103">Baseline protection includes two options for SharePoint Online team sites — a public site and private site. Public sites can be discovered and accessed by anybody in the organization. Private sites can only be discovered and accessed by members of the site. Both of these site configurations allow for sharing outside the group.</span></span>
    
- <span data-ttu-id="38390-125">設有敏感性與高度機密保護的網站為私用網站，其存取權僅限於特定群組的成員。</span><span class="sxs-lookup"><span data-stu-id="38390-125">Sites for sensitive and highly confidential protection are private sites with access limited only to members of specific groups.</span></span>
    
- <span data-ttu-id="38390-126">[保留標籤](../../compliance/labels.md)提供一個方式來分類網站內的檔案。</span><span class="sxs-lookup"><span data-stu-id="38390-126">[Retention labels](../../compliance/labels.md) provide a way to classify files within the sites.</span></span> <span data-ttu-id="38390-127">系統會將每個 SharePoint Online 小組網站設為自動替文件庫中的檔案加上該網站的預設保留標籤。</span><span class="sxs-lookup"><span data-stu-id="38390-127">Each of the SharePoint Online team sites are configured to automatically label files in document libraries with a default retention label for the site.</span></span> <span data-ttu-id="38390-128">此範例的標籤對應到這四種網站設定，分別是「內部公用」、「私用」、「敏感性」與「高度機密」。</span><span class="sxs-lookup"><span data-stu-id="38390-128">Corresponding to the four site configurations, the labels in this example are Internal Public, Private, Sensitive, and Highly Confidential.</span></span> <span data-ttu-id="38390-129">使用者可以變更標籤，但這種設定可確保所有檔案都收到預設標籤。</span><span class="sxs-lookup"><span data-stu-id="38390-129">Users can change the labels, but this configuration ensures all files receive a default label.</span></span>
    
- <span data-ttu-id="38390-130">系統會針對「敏感性」和「高度機密」的保留標籤設定[資料外洩防護](../../compliance/data-loss-prevention-policies.md) (DLP) 原則，以在使用者嘗試將這類檔案傳送到組織外部時，對他們發出警告或阻止此動作。</span><span class="sxs-lookup"><span data-stu-id="38390-130">[Data loss prevention](../../compliance/data-loss-prevention-policies.md) (DLP) policies are configured for the Sensitive and Highly Confidential retention labels to either warn or prevent users when they attempt to send these types of files outside the organization.</span></span>
    
- <span data-ttu-id="38390-131">如果在您的案例中有需要，您可以使用[敏感度標籤](../../compliance/sensitivity-labels.md)以使用加密與權限來保護高度機密檔案。</span><span class="sxs-lookup"><span data-stu-id="38390-131">If needed for your scenario, you can use [sensitivity labels](../../compliance/sensitivity-labels.md) to protect highly confidential files with encryption and permissions.</span></span> <span data-ttu-id="38390-132">針對 Azure 資訊保護客戶，您可以使用 Microsoft 365 合規性中心的 Azure 資訊保護標籤，而如果您選擇執行額外或進階組態，標籤就會與 Azure 入口網站同步處理。</span><span class="sxs-lookup"><span data-stu-id="38390-132">For Azure Information Protection customers, you can use your Azure Information Protection labels in the Microsoft 365 compliance center, and your labels will be synced with the Azure portal in case you choose to perform additional or advanced configuration.</span></span> <span data-ttu-id="38390-133">Azure 資訊保護標籤與 Office 365 敏感度標籤完全彼此相容。</span><span class="sxs-lookup"><span data-stu-id="38390-133">Azure Information Protection labels and Office 365 sensitivity labels are fully compatible with each other.</span></span> <span data-ttu-id="38390-134">這表示，比方說，如果您有使用 Azure 資訊保護加上標籤的內容，則不需將內容重新分類或重新加上標籤。並非每位客戶都需要此層級的保護。</span><span class="sxs-lookup"><span data-stu-id="38390-134">This means, for example, if you have content labeled by Azure Information Protection, you won’t need to reclassify or relabel your content.Not all customers need this level of protection.</span></span> 
    
## <a name="tenant-wide-settings-for-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="38390-135">SharePoint Online 和商務用 OneDrive 的租用戶整體設定</span><span class="sxs-lookup"><span data-stu-id="38390-135">Tenant-wide settings for SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="38390-p106">SharePoint Online 和商務用 OneDrive 包含的租用戶整體設定會影響所有網站與使用者。 其中某些設定可以於網站層級進行調整，使其更加嚴格 (但不能更寬鬆)。 本節說明會影響安全性與共同作業的租用戶整體設定。</span><span class="sxs-lookup"><span data-stu-id="38390-p106">SharePoint Online and OneDrive for Business include tenant-wide settings that affect all sites and users. Some of these settings can also be adjusted at the site level to be more restrictive (but not less). This section discusses tenant-wide settings that affect security and collaboration.</span></span> 
  
### <a name="sharing"></a><span data-ttu-id="38390-139">共用</span><span class="sxs-lookup"><span data-stu-id="38390-139">Sharing</span></span>

<span data-ttu-id="38390-140">針對這個解決方案，我們建議下列的租用戶整體設定：</span><span class="sxs-lookup"><span data-stu-id="38390-140">For this solution, we recommend the following tenant-wide settings:</span></span>
  
- <span data-ttu-id="38390-141">保留預設共用原則，以允許所有帳戶類型的共用作業，包括匿名共用。</span><span class="sxs-lookup"><span data-stu-id="38390-141">Keep the default sharing policy that allows all sharing with all account types, including anonymous sharing.</span></span>
    
- <span data-ttu-id="38390-142">您可視需要將匿名的連結設為過期。</span><span class="sxs-lookup"><span data-stu-id="38390-142">Set anonymous links to expire, if desired.</span></span>
    
- <span data-ttu-id="38390-p107">將共用的預設連結類型變更為「內部」。 這有助於防止資料不慎洩漏到組織外部。</span><span class="sxs-lookup"><span data-stu-id="38390-p107">Change the default link type for sharing to Internal. This helps prevent accidental data leakage outside your organization.</span></span>
    
<span data-ttu-id="38390-p108">雖然允許外部共用似乎有悖常理，但相較於以電子郵件傳送檔案，此方法可以更充分地掌控檔案共用情況。 SharePoint Online 與 Outlook 一起運作，以提供安全的檔案共同作業。</span><span class="sxs-lookup"><span data-stu-id="38390-p108">While it might seem counterintuitive to allow external sharing, this approach provides more control over file sharing compared to sending files in email. SharePoint Online and Outlook work together to provide secure collaboration on files.</span></span> 
  
- <span data-ttu-id="38390-147">根據預設，Outlook 會共用檔案的連結，而非以電子郵件傳送檔案。</span><span class="sxs-lookup"><span data-stu-id="38390-147">By default, Outlook shares a link to a file instead of sending the file in email.</span></span> 
    
- <span data-ttu-id="38390-148">SharePoint Online 與商務用 OneDrive 可讓您輕易地與組織內外的參與者共用檔案連結</span><span class="sxs-lookup"><span data-stu-id="38390-148">SharePoint Online and OneDrive for Business make it easy to share links to files with contributors who are both inside and outside your organization</span></span>
    
<span data-ttu-id="38390-p109">您也可以使用相關控制來協助控管外部共用。 例如，您可以：</span><span class="sxs-lookup"><span data-stu-id="38390-p109">You also have controls to help govern external sharing. For example, you can:</span></span>
  
- <span data-ttu-id="38390-151">停用匿名訪客的連結。</span><span class="sxs-lookup"><span data-stu-id="38390-151">Disable an anonymous guest link.</span></span>
    
- <span data-ttu-id="38390-152">撤銷使用者的網站存取權。</span><span class="sxs-lookup"><span data-stu-id="38390-152">Revoke user access to a site.</span></span>
    
- <span data-ttu-id="38390-153">查看誰具有特定網站或文件的存取權。</span><span class="sxs-lookup"><span data-stu-id="38390-153">See who has access to a specific site or document.</span></span>
    
- <span data-ttu-id="38390-154">將匿名共用連結設為過期 (租用戶設定)。</span><span class="sxs-lookup"><span data-stu-id="38390-154">Set anonymous sharing links to expire (tenant setting).</span></span>
    
- <span data-ttu-id="38390-155">限制可在組織外部共用的人員 (租用戶設定)。</span><span class="sxs-lookup"><span data-stu-id="38390-155">Limit who can share outside your organization (tenant setting).</span></span>
    
### <a name="use-external-sharing-together-with-data-loss-prevention-dlp"></a><span data-ttu-id="38390-156">搭配使用外部共用與資料外洩防護 (DLP)</span><span class="sxs-lookup"><span data-stu-id="38390-156">Use external sharing together with data loss prevention (DLP)</span></span>

<span data-ttu-id="38390-p110">如果您不允許外部共用，有業務需求的使用者就必須找到替代工具和方法。Microsoft 建議您結合外部共用與 DLP 原則來保護敏感性與高度機密檔案。</span><span class="sxs-lookup"><span data-stu-id="38390-p110">If you don't allow external sharing, users with a business need will find alternate tools and methods. Microsoft recommends you combine external sharing with DLP policies to protect sensitive and highly confidential files.</span></span>
  
### <a name="device-access-settings"></a><span data-ttu-id="38390-159">裝置存取設定</span><span class="sxs-lookup"><span data-stu-id="38390-159">Device access settings</span></span>

<span data-ttu-id="38390-160">SharePoint Online 和商務用 OneDrive 的裝置存取設定可讓您決定要僅限瀏覽器存取 (無法下載檔案)，或是封鎖存取。</span><span class="sxs-lookup"><span data-stu-id="38390-160">Device access settings for SharePoint Online and OneDrive for Business let you determine whether access is limited to browser only (files can't be downloaded) or if access is blocked.</span></span> <span data-ttu-id="38390-161">如需詳細資訊，請參閱[控制未受管理裝置的存取權](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="38390-161">For more information, see [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span> 

<span data-ttu-id="38390-162">若要使用裝置存取設定搭配 Azure Active Directory 中建議的條件式存取原則，請參閱[保護 SharePoint 網站和檔案的原則建議](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)。</span><span class="sxs-lookup"><span data-stu-id="38390-162">To use device access settings with recommended conditional access policies in Azure Active Directory, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>
  
### <a name="onedrive-for-business"></a><span data-ttu-id="38390-163">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="38390-163">OneDrive for Business</span></span>

<span data-ttu-id="38390-p112">請瀏覽這些設定，以決定是否要變更商務用 OneDrive 的網站預設設定。 目前，會複製 SharePoint Online 系統管理中心的共用和裝置存取設定，並套用到這兩個環境。</span><span class="sxs-lookup"><span data-stu-id="38390-p112">Visit these settings to decide if you want to change the default settings for OneDrive for Business sites. Currently, the sharing and device access settings are duplicated from the SharePoint Online admin center and apply to both environments.</span></span>
  
## <a name="sharepoint-team-site-configuration"></a><span data-ttu-id="38390-166">SharePoint 小組網站設定</span><span class="sxs-lookup"><span data-stu-id="38390-166">SharePoint team site configuration</span></span>

<span data-ttu-id="38390-p113">下表摘要說明本文稍早所述之每個小組網站的設定。 您可以使用這些設定作為建議的起點，並依據組織需求調整網站類型與設定。 並非每個組織都需要所有類型的網站。 只有少數的組織需要高度機密的保護。</span><span class="sxs-lookup"><span data-stu-id="38390-p113">The following table summarizes the configuration for each of the team sites described earlier in this article. Use these configurations as starting point recommendations and adjust the site types and configurations to meet the needs of your organization. Not every organization needs every type of site. Only a small number of organizations require highly confidential protection.</span></span>
  
||||||
|:-----|:-----|:-----|:-----|:-----|
||<span data-ttu-id="38390-171">**基準保護 #1**</span><span class="sxs-lookup"><span data-stu-id="38390-171">**Baseline protection #1**</span></span> <br/> |<span data-ttu-id="38390-172">**基準保護 #2**</span><span class="sxs-lookup"><span data-stu-id="38390-172">**Baseline protection #2**</span></span> <br/> |<span data-ttu-id="38390-173">**敏感性保護**</span><span class="sxs-lookup"><span data-stu-id="38390-173">**Sensitive protection**</span></span> <br/> |<span data-ttu-id="38390-174">**高度機密**</span><span class="sxs-lookup"><span data-stu-id="38390-174">**Highly confidential**</span></span> <br/> |
|<span data-ttu-id="38390-175">描述</span><span class="sxs-lookup"><span data-stu-id="38390-175">Description</span></span>  <br/> |<span data-ttu-id="38390-176">開啟組織內的探索及共同作業。</span><span class="sxs-lookup"><span data-stu-id="38390-176">Open discovery and collaboration within the organization.</span></span>  <br/> |<span data-ttu-id="38390-177">私用網站和群組，其可在群組外部共用。</span><span class="sxs-lookup"><span data-stu-id="38390-177">Private site and group with sharing allowed outside the group.</span></span>  <br/> |<span data-ttu-id="38390-p114">隔離的網站，其存取層級會依據特定群組的成員資格而定義。 只允許網站的成員共用。 當使用者嘗試將檔案傳送到組織外部時，DLP 會對其發出警告。</span><span class="sxs-lookup"><span data-stu-id="38390-p114">Isolated site, in which levels of access are defined by membership in specific groups. Sharing is only allowed to members of the site. DLP warns users when attempting to send files outside the organization.</span></span>  <br/> |<span data-ttu-id="38390-p115">使用 Azure 資訊保護的隔離網站 + 檔案加密與權限。 DLP 可防止使用者將檔案傳送到組織外部。</span><span class="sxs-lookup"><span data-stu-id="38390-p115">Isolated site + file encryption and permissions with Azure Information Protection. DLP prevents users from sending files outside the organization.</span></span>  <br/> |
|<span data-ttu-id="38390-183">私用或公用的小組網站</span><span class="sxs-lookup"><span data-stu-id="38390-183">Private or public team site</span></span>  <br/> |<span data-ttu-id="38390-184">公用</span><span class="sxs-lookup"><span data-stu-id="38390-184">Public</span></span>  <br/> |<span data-ttu-id="38390-185">Private</span><span class="sxs-lookup"><span data-stu-id="38390-185">Private</span></span>  <br/> |<span data-ttu-id="38390-186">Private</span><span class="sxs-lookup"><span data-stu-id="38390-186">Private</span></span>  <br/> |<span data-ttu-id="38390-187">Private</span><span class="sxs-lookup"><span data-stu-id="38390-187">Private</span></span>  <br/> |
|<span data-ttu-id="38390-188">誰可以存取？</span><span class="sxs-lookup"><span data-stu-id="38390-188">Who has access?</span></span>  <br/> |<span data-ttu-id="38390-189">組織中所有人，包括 B2B 使用者和訪客使用者。</span><span class="sxs-lookup"><span data-stu-id="38390-189">Everybody in the organization, including B2B users and guest users.</span></span>  <br/> |<span data-ttu-id="38390-p116">僅限網站的成員。 其他人可以要求存取權。</span><span class="sxs-lookup"><span data-stu-id="38390-p116">Members of the site only. Others can request access.</span></span>  <br/> |<span data-ttu-id="38390-p117">僅限網站的成員。 其他人可以要求存取權。</span><span class="sxs-lookup"><span data-stu-id="38390-p117">Members of the site only. Others can request access.</span></span>  <br/> |<span data-ttu-id="38390-p118">僅限成員。 其他人無法要求存取權。</span><span class="sxs-lookup"><span data-stu-id="38390-p118">Members only. Others cannot request access.</span></span>  <br/> |
|<span data-ttu-id="38390-196">網站層級的共用控制</span><span class="sxs-lookup"><span data-stu-id="38390-196">Site-level sharing controls</span></span>  <br/> |<span data-ttu-id="38390-p119">允許與任何人共用。 預設設定。</span><span class="sxs-lookup"><span data-stu-id="38390-p119">Sharing allowed with anybody. Default settings.</span></span>  <br/> |<span data-ttu-id="38390-p120">允許與任何人共用。 預設設定。</span><span class="sxs-lookup"><span data-stu-id="38390-p120">Sharing allowed with anybody. Default settings.</span></span>  <br/> |<span data-ttu-id="38390-201">成員無法共用網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="38390-201">Members cannot share access to the site.</span></span>  <br/> <span data-ttu-id="38390-202">非成員可以要求存取網站，但這些要求需要網站系統管理員處理。</span><span class="sxs-lookup"><span data-stu-id="38390-202">Non-members can request access to the site, but these requests need to be addressed by a site administrator.</span></span>  <br/> |<span data-ttu-id="38390-203">成員無法共用網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="38390-203">Members cannot share access to the site.</span></span>  <br/> <span data-ttu-id="38390-204">非成員無法要求存取網站或內容。</span><span class="sxs-lookup"><span data-stu-id="38390-204">Non-members cannot request access to the site or contents.</span></span>  <br/> |
|<span data-ttu-id="38390-205">網站層級的裝置存取控制</span><span class="sxs-lookup"><span data-stu-id="38390-205">Site-level device access controls</span></span>  <br/> |<span data-ttu-id="38390-206">無額外控制。</span><span class="sxs-lookup"><span data-stu-id="38390-206">No additional controls.</span></span>  <br/> |<span data-ttu-id="38390-207">無額外控制。</span><span class="sxs-lookup"><span data-stu-id="38390-207">No additional controls.</span></span>  <br/> |<span data-ttu-id="38390-p121">防止使用者下載檔案到不相容或非加入網域的裝置。如此一來，所有其他裝置僅可進行瀏覽器存取。</span><span class="sxs-lookup"><span data-stu-id="38390-p121">Prevents users from downloading files to non-compliant or non-domain joined devices. This allows browser-only access from all other devices.</span></span>  <br/> |<span data-ttu-id="38390-210">封鎖將檔案下載至不相容或非加入網域的裝置。</span><span class="sxs-lookup"><span data-stu-id="38390-210">Block downloading of files to non-compliant or non-domain joined devices.</span></span>  <br/> |
|<span data-ttu-id="38390-211">保留標籤</span><span class="sxs-lookup"><span data-stu-id="38390-211">Retention labels</span></span>  <br/> |<span data-ttu-id="38390-212">內部公用</span><span class="sxs-lookup"><span data-stu-id="38390-212">Internal Public</span></span>  <br/> |<span data-ttu-id="38390-213">Private</span><span class="sxs-lookup"><span data-stu-id="38390-213">Private</span></span>  <br/> |<span data-ttu-id="38390-214">敏感性</span><span class="sxs-lookup"><span data-stu-id="38390-214">Sensitive</span></span>  <br/> |<span data-ttu-id="38390-215">高度機密</span><span class="sxs-lookup"><span data-stu-id="38390-215">Highly Confidential</span></span>  <br/> |
|<span data-ttu-id="38390-216">DLP 原則</span><span class="sxs-lookup"><span data-stu-id="38390-216">DLP policies</span></span>  <br/> |||<span data-ttu-id="38390-217">當使用者將標記為「敏感性」的檔案傳送到組織外部時，會對其發出警告。</span><span class="sxs-lookup"><span data-stu-id="38390-217">Warn users when sending files that are labeled as Sensitive outside the organization.</span></span>  <br/> <span data-ttu-id="38390-218">若要封鎖敏感性資料類型的外部共用，例如信用卡號碼或其他個人資料，您可以為這些資料類型 (包括您設定的自訂資料類型) 設定額外的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="38390-218">To block external sharing of sensitive data types, such as credit card numbers or other personal data, you can configure additional DLP policies for these data types (including custom data types you configure).</span></span>  <br/> |<span data-ttu-id="38390-p122">封鎖使用者，使其無法將標示為高度機密的檔案傳送到組織外部。 允許使用者提供理由來覆寫這項預設，包括共用檔案的對象。</span><span class="sxs-lookup"><span data-stu-id="38390-p122">Block users from sending files that are labeled as highly confidential outside organization. Allow users to override this by providing justification, including who they are sharing the file with.</span></span>  <br/> |
|<span data-ttu-id="38390-221">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="38390-221">Sensitivity labels</span></span>  <br/> ||||<span data-ttu-id="38390-222">使用敏感度標籤可自動加密並授與檔案權限。</span><span class="sxs-lookup"><span data-stu-id="38390-222">Use sensitivity labels to automatically encrypt and grant permissions to files.</span></span> <span data-ttu-id="38390-223">敏感度標籤會使用 Azure 資訊保護來加密檔案。</span><span class="sxs-lookup"><span data-stu-id="38390-223">Sensitivity labels use Azure Information Protection to encrypt files.</span></span> <span data-ttu-id="38390-224">這項保護會與檔案一起移動，以免檔案外洩。</span><span class="sxs-lookup"><span data-stu-id="38390-224">This protection travels with the files in case they are leaked.</span></span>  <br/> <span data-ttu-id="38390-p124">Office 365 無法讀取以 Azure 資訊保護加密的檔案。此外，DLP 原則僅會使用中繼資料 (包括標籤)，而不會使用這些檔案的內容 (例如檔案中的信用卡號碼)。</span><span class="sxs-lookup"><span data-stu-id="38390-p124">Office 365 cannot read files encrypted with Azure Information Protection. Additionally, DLP policies can only work with the metadata (including labels) but not the contents of these files (such as credit card numbers within files).</span></span>  <br/> |
   
<span data-ttu-id="38390-227">如需此解決方案中這四種不同類型 SharePoint Online 小組網站的部署步驟，請參閱[部署三層保護的 SharePoint Online 網站](../../compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="38390-227">For the steps to deploy the four different types of SharePoint Online team sites in this solution, see [Deploy SharePoint Online sites for three tiers of protection](../../compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection.md).</span></span> 
  
## <a name="office-365-retention-labels"></a><span data-ttu-id="38390-228">Office 365 保留標籤</span><span class="sxs-lookup"><span data-stu-id="38390-228">Office 365 retention labels</span></span>

<span data-ttu-id="38390-229">建議您在含有敏感性資料的環境中使用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="38390-229">Using retention labels is recommended for environments with sensitive data.</span></span> <span data-ttu-id="38390-230">設定並發佈保留標籤之後：</span><span class="sxs-lookup"><span data-stu-id="38390-230">After you configure and publish retention labels:</span></span>
  
- <span data-ttu-id="38390-231">您可以將預設標籤套用至 SharePoint Online 小組網站的文件庫，以便讓該文件庫中的所有文件取得預設標籤。</span><span class="sxs-lookup"><span data-stu-id="38390-231">You can apply a default label to a document library in a SharePoint Online team site, so that all documents in that library get the default label.</span></span> 
    
- <span data-ttu-id="38390-232">您可以自動將標籤套用到內容 (如果內容符合特定條件的話)。</span><span class="sxs-lookup"><span data-stu-id="38390-232">You can apply labels to content automatically if it matches specific conditions.</span></span>
    
- <span data-ttu-id="38390-233">您可以套用以保留標籤為基礎的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="38390-233">You can apply DLP policies that are based on retention labels.</span></span>
    
- <span data-ttu-id="38390-p126">組織的人員可以手動套用標籤至 Outlook 網頁版、Outlook 2010 及更新版本、商務用 OneDrive、SharePoint Online 以及 Office 365 群組中的內容。使用者通常最清楚自己使用的內容類型，因此可以對其分類並套用適當的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="38390-p126">People in your organization can apply a label manually to content in Outlook on the web, Outlook 2010 and later, OneDrive for Business, SharePoint Online, and Office 365 groups. Users often know best what type of content they're working with, so they can classify it and have the appropriate DLP policy applied.</span></span>
    
![SharePoint 網站的建議設定](../media/7fed0126-ab4a-4480-922c-681970642339.png)
  
<span data-ttu-id="38390-237">如圖例所示，此解決方案包括建立下列保留標籤：</span><span class="sxs-lookup"><span data-stu-id="38390-237">As illustrated, this solution includes creating the following retention labels:</span></span>
  
- <span data-ttu-id="38390-238">高度機密</span><span class="sxs-lookup"><span data-stu-id="38390-238">Highly Confidential</span></span>
    
- <span data-ttu-id="38390-239">敏感性</span><span class="sxs-lookup"><span data-stu-id="38390-239">Sensitive</span></span>
    
- <span data-ttu-id="38390-240">Private</span><span class="sxs-lookup"><span data-stu-id="38390-240">Private</span></span>
    
- <span data-ttu-id="38390-241">內部公用</span><span class="sxs-lookup"><span data-stu-id="38390-241">Internal Public</span></span>
    
<span data-ttu-id="38390-p127">這些標籤會對應到本文稍早的圖例與圖表中的建議網站。此解決方案建議您設定 DLP 原則，以協助避免標示為「敏感性」和「高度機密」的檔案外洩。</span><span class="sxs-lookup"><span data-stu-id="38390-p127">These labels are mapped to the recommended sites in the illustrations and charts earlier in this article. This solution recommends configuring DLP policies to help prevent the leakage of files labeled as Sensitive and Highly Confidential.</span></span>
  
<span data-ttu-id="38390-244">如需在此解決方案中設定保留標籤和 DLP 原則的步驟，請參閱[使用保留標籤與 DLP 來保護 SharePoint Online 檔案](../../compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)。</span><span class="sxs-lookup"><span data-stu-id="38390-244">For the steps to configure retention labels and DLP policies in this solution, see [Protect SharePoint Online files with retention labels and DLP](../../compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp.md).</span></span>
  
## <a name="sensitivity-labels"></a><span data-ttu-id="38390-245">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="38390-245">Sensitivity labels</span></span> 

<span data-ttu-id="38390-246">若您的安全性案例有需要，您可以使用敏感度標籤來套用可隨時追蹤檔案的保護。</span><span class="sxs-lookup"><span data-stu-id="38390-246">If warranted for your security scenario, you can use sensitivity labels to apply protections that follow the files wherever they go.</span></span> <span data-ttu-id="38390-247">Microsoft 365 合規性中心的敏感度標籤和 Azure 資訊保護標籤是相同的。</span><span class="sxs-lookup"><span data-stu-id="38390-247">Sensitivity labels in the Microsoft 365 compliance center and Azure Information Protection labels are the same.</span></span> <span data-ttu-id="38390-248">建議您為此解決方案使用限域的 Azure 資訊保護原則以及高度機密標籤的子標籤，來加密需要以最高安全性等級保護的檔案，和為其授予權限。</span><span class="sxs-lookup"><span data-stu-id="38390-248">For this solution, we recommend you use a scoped Azure Information Protection policy and a sub-label of the Highly Confidential label to encrypt and grant permissions to files that need to be protected with the highest level of security.</span></span> 
  
<span data-ttu-id="38390-249">請留意，若將 Azure 資訊保護套用至儲存於 Office 365 中的檔案，服務就無法處理這些檔案的內容。</span><span class="sxs-lookup"><span data-stu-id="38390-249">Be aware that when Azure Information Protection encryption is applied to files stored in Office 365, the service cannot process the contents of these files.</span></span> <span data-ttu-id="38390-250">共同撰寫、eDiscovery、搜尋、Delve 和其他共同作業功能無法運作。</span><span class="sxs-lookup"><span data-stu-id="38390-250">Co-authoring, eDiscovery, search, Delve, and other collaborative features do not work.</span></span> <span data-ttu-id="38390-251">此外，DLP 原則只可用於中繼資料 (包括保留標籤)，但不可用於這些檔案的內容 (例如檔案中的信用卡號碼)。</span><span class="sxs-lookup"><span data-stu-id="38390-251">DLP policies can only work with the metadata (including retention labels) but not the contents of these files (such as credit card numbers within files).</span></span>

<span data-ttu-id="38390-252">如需詳細資訊，請參閱[敏感度標籤概觀](../../compliance/sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="38390-252">For more information, see [Overview of sensitivity labels](../../compliance/sensitivity-labels.md).</span></span>

    
### <a name="adding-permissions-for-external-users"></a><span data-ttu-id="38390-253">新增外部使用者的權限</span><span class="sxs-lookup"><span data-stu-id="38390-253">Adding permissions for external users</span></span>

<span data-ttu-id="38390-p130">您可以使用兩種方式，將 Azure 資訊保護所保護的檔案存取權授與外部使用者。在這兩種情況下，外部使用者皆必須擁有 Azure AD 帳戶。如果外部使用者不屬於使用 Azure AD 的組織成員，可以使用 [https://aka.ms/aip-signup](https://aka.ms/aip-signup) 這個註冊頁面，以個人身分取得 Azure AD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="38390-p130">There are two ways you can grant external users access to files protected with Azure Information Protection. In both these cases, external users must have an Azure AD account. If external users aren't members of an organization that uses Azure AD, they can obtain an Azure AD account as an individual by using this sign-up page: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).</span></span>
  
- <span data-ttu-id="38390-257">將外部使用者新增至用來設定保護標籤的 Azure AD 群組</span><span class="sxs-lookup"><span data-stu-id="38390-257">Add external users to an Azure AD group that is used to configure protection for a label</span></span>
    
     <span data-ttu-id="38390-p131">您必須先將帳戶新增為目錄中的 B2B 使用者。當 [Azure 版權管理進行群組成員資格的快取](https://docs.microsoft.com/information-protection/plan-design/prepare)時，可能需要花費數小時的時間。使用此方法時，會授與所有受標籤保護的現有檔案權限 (包括將使用者新增至 Azure AD 群組之前即受保護的檔案)。</span><span class="sxs-lookup"><span data-stu-id="38390-p131">You'll need to first add the account as a B2B user in your directory. It can take a couple of hours for [group membership caching by Azure Rights Management](https://docs.microsoft.com/information-protection/plan-design/prepare). With this method, permissions are granted to all existing files protected with the label (even files protected before a user is added to the Azure AD group).</span></span>
    
- <span data-ttu-id="38390-261">將外部使用者直接新增至標籤保護。</span><span class="sxs-lookup"><span data-stu-id="38390-261">Add external users directly to the label protection</span></span>
    
     <span data-ttu-id="38390-p132">您可以從組織 (例如 Fabrikam.com)、Azure AD 群組 (例如組織內的財務部門) 或個別使用者，新增所有使用者。例如，您可以將外部的監理人員小組新增至標籤保護。使用此方法時，僅會授與在外部實體新增至保護之後受標籤保護的檔案權限。</span><span class="sxs-lookup"><span data-stu-id="38390-p132">You can add all users from an organization (e.g. Fabrikam.com), an Azure AD group (such as a finance group within an organization), or an individual user. For example, you can add an external team of regulators to the protection for a label. With this method, permissions are granted only to files protected with the label after the external entity is added to the protection.</span></span>
    
### <a name="deploying-and-using-azure-information-protection"></a><span data-ttu-id="38390-265">部署並使用 Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="38390-265">Deploying and using Azure Information Protection</span></span>

<span data-ttu-id="38390-266">如需在此解決方案中設定 Azure 資訊保護的步驟，請參閱[使用 Azure 資訊保護來保護 SharePoint Online 檔案](../../compliance/protect-sharepoint-online-files-with-azure-information-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="38390-266">For the steps to configure Azure Information Protection in this solution, see [Protect SharePoint Online files with Azure Information Protection](../../compliance/protect-sharepoint-online-files-with-azure-information-protection.md).</span></span>
  

## <a name="next-step"></a><span data-ttu-id="38390-267">下一步</span><span class="sxs-lookup"><span data-stu-id="38390-267">Next step</span></span>

<span data-ttu-id="38390-268">使用[開發/測試環境中保護 SharePoint Online 網站的安全](secure-sharepoint-online-sites-in-a-dev-test-environment.md)將其構建為概念驗證。</span><span class="sxs-lookup"><span data-stu-id="38390-268">Build this out as a proof-of-concept with [Secure SharePoint Online sites in a dev/test environment](secure-sharepoint-online-sites-in-a-dev-test-environment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="38390-269">另請參閱</span><span class="sxs-lookup"><span data-stu-id="38390-269">See Also</span></span>

[<span data-ttu-id="38390-270">適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南</span><span class="sxs-lookup"><span data-stu-id="38390-270">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="38390-271">雲端採用和混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="38390-271">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
