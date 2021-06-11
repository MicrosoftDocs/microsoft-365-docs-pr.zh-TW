---
title: 資料遺失防護參考
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: low
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 資料遺失防護參考材料
ms.openlocfilehash: a6dc0b2702899e05f78c54331fb33b87495672d8
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572558"
---
# <a name="data-loss-prevention-reference"></a><span data-ttu-id="cc427-103">資料遺失防護參考</span><span class="sxs-lookup"><span data-stu-id="cc427-103">Data loss prevention reference</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="cc427-104">這是參考主題不再是 Microsoft 365 資料遺失防護 (DLP) 資訊的主要資源。</span><span class="sxs-lookup"><span data-stu-id="cc427-104">This is reference topic is no longer the main resource for Microsoft 365 data loss prevention (DLP) information.</span></span> <span data-ttu-id="cc427-105">DLP 內容集會進行更新及重構。</span><span class="sxs-lookup"><span data-stu-id="cc427-105">The DLP content set is being updated and restructured.</span></span> <span data-ttu-id="cc427-106">本文涵蓋的主題將移至新的更新的文章。</span><span class="sxs-lookup"><span data-stu-id="cc427-106">The topics covered in this article will be moving to new, updated articles.</span></span> <span data-ttu-id="cc427-107">如需有關 DLP 的詳細資訊，請參閱 [瞭解資料遺失防護](dlp-learn-about-dlp.md)。</span><span class="sxs-lookup"><span data-stu-id="cc427-107">For more information about DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
<!-- move this note to a more appropriate place, no topic should start with a note -->
> [!NOTE]
> <span data-ttu-id="cc427-108">針對已取得 Office 365 進階合規性授權的使用者，系統最近將資料外洩防護功能新增至 Microsoft Teams 聊天和頻道訊息，該功能可作為獨立選項提供，並包含在 Office 365 E5 和 Microsoft 365 E5 合規性中。</span><span class="sxs-lookup"><span data-stu-id="cc427-108">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 Advanced Compliance, which is available as a standalone option and is included in Office 365 E5 and Microsoft 365 E5 Compliance.</span></span> <span data-ttu-id="cc427-109">若要深入了解授權需求，請參閱 [Microsoft 365 租用戶層級服務授權指導方針](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)</span><span class="sxs-lookup"><span data-stu-id="cc427-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>



<!-- MOVED TO LEARN ABOUT To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its inadvertent disclosure. Sensitive information can include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records. With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.
  
With a DLP policy, you can:
  
- **Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**
    
    For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.
    
- **Prevent the accidental sharing of sensitive information**. 
    
    For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.
    
- **Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**
    
    Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office desktop programs include the same capabilities to identify sensitive information and apply DLP policies. DLP provides continuous monitoring when people share content in these Office programs.
    
- **Help users learn how to stay compliant without interrupting their workflow.**
    
    You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.
    
- **View DLP alerts and reports showing content that matches your organization’s DLP policies.**
    
    To view alerts and metadata related to your DLP policies you can use the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md). You can also view policy match reports to assess how your organization is complying with a DLP policy. If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported

-->    
## <a name="create-and-manage-dlp-policies"></a><span data-ttu-id="cc427-110">建立及管理 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="cc427-110">Create and manage DLP policies</span></span>

<span data-ttu-id="cc427-111">您可以在 Microsoft 365 合規性中心的 [資料外洩防護] 頁面上建立及管理 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="cc427-111">You create and manage DLP policies on the Data loss prevention page in the Microsoft 365 Compliance center.</span></span>
  
![Office 365 安全性與合規性中心內的資料外洩防護頁面](../media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
<!-- MOVED TO LEARN ABOUT ## What a DLP policy contains

A DLP policy contains a few basic things:
  
- Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages. 
    
- When and how to protect the content by enforcing **rules** comprised of: 
    
  - **Conditions** the content must match before the rule is enforced. For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization. 
    
  - **Actions** that you want the rule to take automatically when content matching the conditions is found. For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification. -->
    
<span data-ttu-id="cc427-113">您可以使用規則以符合特定的保護需求，然後使用 DLP 原則將常見保護需求分成一組，例如所有需要遵守特定法規的規則。</span><span class="sxs-lookup"><span data-stu-id="cc427-113">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="cc427-114">例如，您的 DLP 原則可能協助您偵測是否存在受到健康保險流通與責任法案 (HIPAA) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="cc427-114">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA).</span></span> <span data-ttu-id="cc427-115">此 DLP 原則可尋找任何含有此敏感性資訊並與組織外部人員共用的文件 (條件)，然後封鎖此文件的存取並傳送通知 (動作)，進而協助保護所有 SharePoint Online 網站與所有商務用 OneDrive 網站 (位置) 的 HIPAA 資料 (內容)。</span><span class="sxs-lookup"><span data-stu-id="cc427-115">This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that's shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions).</span></span> <span data-ttu-id="cc427-116">這些需求會儲存為個別規則並分組為 DLP 原則，以簡化管理和報告。</span><span class="sxs-lookup"><span data-stu-id="cc427-116">These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![圖表顯示 DLP 原則包含位置和規則](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
<!-- MOVED TO LEARN ABOUT ### Locations

DLP policies are applied to sensitive items across Microsoft 365 locations and can be further scoped as detailed in this table.


|Location | Include/exclude by|
|---------|---------|
|Exchange email| distribution groups|
|SharePoint sites |sites |
|OneDrive accounts |accounts |
|Teams chat and channel messages |accounts |
|Windows 10 devices |user or group |
|Microsoft Cloud App Security |instance |
 -->

<span data-ttu-id="cc427-118">如果您選擇在 Exchange 中包含特定通訊群組，DLP 原則將只會限定至該群組的成員。</span><span class="sxs-lookup"><span data-stu-id="cc427-118">If you choose to include specific distribution groups in Exchange, the DLP policy will be scoped only to the members of that group.</span></span> <span data-ttu-id="cc427-119">類似地排除通訊群組會從原則評估中排除該通訊群組的所有成員。</span><span class="sxs-lookup"><span data-stu-id="cc427-119">Similarly excluding a distribution group will exclude all the members of that distribution group from policy evaluation.</span></span> <span data-ttu-id="cc427-120">您可以選擇將原則限定至通訊清單、動態通訊群組和安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="cc427-120">You can choose to scope a policy to the members of distribution lists, dynamic distribution groups, and security groups.</span></span> <span data-ttu-id="cc427-121">DLP 原則最多可包含 50 項此類的包含和排除。</span><span class="sxs-lookup"><span data-stu-id="cc427-121">A DLP policy can contain no more than 50 such inclusions and exclusions.</span></span>

<span data-ttu-id="cc427-122">如果您選擇包含或排除特定 SharePoint 網站，則 DLP 原則只能包含不超過 100 項此類包含或排除。</span><span class="sxs-lookup"><span data-stu-id="cc427-122">If you choose to include or exclude specific SharePoint sites, a DLP policy can contain no more than 100 such inclusions and exclusions.</span></span> <span data-ttu-id="cc427-123">雖然有這個限制，但您可以套用全組織原則或套用到整個位置的原則來超過這些限制。</span><span class="sxs-lookup"><span data-stu-id="cc427-123">Although this limit exists, you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>

<span data-ttu-id="cc427-124">如果您選擇包含或排除特定的 OneDrive 帳戶或群組，則 DLP 原則不能包含超過 100 個使用者帳戶或 50 個群組作為包含或排除。</span><span class="sxs-lookup"><span data-stu-id="cc427-124">If you choose to include or exclude specific OneDrive accounts or groups, a DLP policy can contain no more than 100 user accounts or 50 groups as inclusion or exclusion.</span></span>

> [!NOTE]
> <span data-ttu-id="cc427-125">使用帳戶或群組的商務用 OneDrive 原則範圍目前處於公開預覽。</span><span class="sxs-lookup"><span data-stu-id="cc427-125">OneDrive for business policy scoping using accounts or groups is in public preview.</span></span> <span data-ttu-id="cc427-126">在此階段期間，您可以隨著 DLP 原則包含或排除使用者帳戶和群組。</span><span class="sxs-lookup"><span data-stu-id="cc427-126">During this phase, you can either include or exclude user accounts and groups as part of a DLP policy.</span></span> <span data-ttu-id="cc427-127">不支援在相同原則中同時使用包含和排除。</span><span class="sxs-lookup"><span data-stu-id="cc427-127">Both inclusion and exclusion as part of the same policy is not supported.</span></span>
  
### <a name="rules"></a><span data-ttu-id="cc427-128">規則</span><span class="sxs-lookup"><span data-stu-id="cc427-128">Rules</span></span>

> [!NOTE]
> <span data-ttu-id="cc427-129">沒有設定警報時，DLP 原則的預設行為是不會警示或觸發。</span><span class="sxs-lookup"><span data-stu-id="cc427-129">The default behavior of a DLP policy, when there is no alert configured, is not to alert or trigger.</span></span> <span data-ttu-id="cc427-130">這僅適用於預設資訊類型。</span><span class="sxs-lookup"><span data-stu-id="cc427-130">This applies only to default information types.</span></span> <span data-ttu-id="cc427-131">對於自訂資訊類型，即使原則中未定義任何動作，系統仍會發出警示。</span><span class="sxs-lookup"><span data-stu-id="cc427-131">For custom information types, the system will alert even if there is no action defined in the policy.</span></span>

<span data-ttu-id="cc427-132">用來對貴組織內容強制執行您的商務需求的，就是規則。</span><span class="sxs-lookup"><span data-stu-id="cc427-132">Rules are what enforce your business requirements on your organization's content.</span></span> <span data-ttu-id="cc427-133">一項原則包含一或多個規則，而每個規則是由條件和動作所組成。</span><span class="sxs-lookup"><span data-stu-id="cc427-133">A policy contains one or more rules, and each rule consists of conditions and actions.</span></span> <span data-ttu-id="cc427-134">對每個規則而言，條件符合時，就會自動採取動作。</span><span class="sxs-lookup"><span data-stu-id="cc427-134">For each rule, when the conditions are met, the actions are taken automatically.</span></span> <span data-ttu-id="cc427-135">規則會依序執行，從每個原則中最高優先順序的規則開始。</span><span class="sxs-lookup"><span data-stu-id="cc427-135">Rules are executed sequentially, starting with the highest-priority rule in each policy.</span></span>
  
<span data-ttu-id="cc427-136">規則也會提供通知選項，以通知使用者 (透過原則提示和電子郵件通知) 和系統管理員 (透過電子郵件事件報告) 內容符合規則。</span><span class="sxs-lookup"><span data-stu-id="cc427-136">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="cc427-137">規則的組成元件及個別說明如下。</span><span class="sxs-lookup"><span data-stu-id="cc427-137">Here are the components of a rule, each explained below.</span></span>
  
![DLP 規則編輯器的區段](../media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="cc427-139">條件</span><span class="sxs-lookup"><span data-stu-id="cc427-139">Conditions</span></span>

<span data-ttu-id="cc427-140">條件很重要，因為它們會決定您要尋找的資訊類型，以及何時採取動作。</span><span class="sxs-lookup"><span data-stu-id="cc427-140">Conditions are important because they determine what types of information you're looking for, and when to take an action.</span></span> <span data-ttu-id="cc427-141">例如，您可以選擇略過包含護照號碼的內容，除非內容中包含超過 10 個這類號碼，並與組織外部人員共用。</span><span class="sxs-lookup"><span data-stu-id="cc427-141">For example, you might choose to ignore content containing passport numbers unless the content contains more than 10 such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="cc427-142">條件著重於 **內容** (例如您要尋找哪些類型的敏感性資訊)，也著重於 **內容** (例如文件與誰共用)。</span><span class="sxs-lookup"><span data-stu-id="cc427-142">Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with.</span></span> <span data-ttu-id="cc427-143">您可以使用條件對不同的風險層級指派不同的動作。</span><span class="sxs-lookup"><span data-stu-id="cc427-143">You can use conditions to assign different actions to different risk levels.</span></span> <span data-ttu-id="cc427-144">例如，相較於與組織外部人員共用的敏感性內容，內部共用的敏感性內容風險可能較低，所需的動作也較少。</span><span class="sxs-lookup"><span data-stu-id="cc427-144">For example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![清單會顯示可用的 DLP 條件](../media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="cc427-146">目前可用的條件可以判斷：</span><span class="sxs-lookup"><span data-stu-id="cc427-146">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="cc427-147">內容是否包含機密資訊。</span><span class="sxs-lookup"><span data-stu-id="cc427-147">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="cc427-148">內容是否包含標籤。</span><span class="sxs-lookup"><span data-stu-id="cc427-148">Content contains a label.</span></span> <span data-ttu-id="cc427-149">如需詳細資訊，請參閱下一節的[將保留標籤做為 DLP 原則的條件](#using-a-retention-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="cc427-149">For more information, see the below section [Using a retention label as a condition in a DLP policy](#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>
    
- <span data-ttu-id="cc427-150">內容是否與組織外部或內部人員共用。</span><span class="sxs-lookup"><span data-stu-id="cc427-150">Content is shared with people outside or inside your organization.</span></span>

  > [!NOTE]
  > <span data-ttu-id="cc427-151">在主持組織 Active Directory 或 Azure Active Directory 租用戶中擁有非來賓帳戶的使用者，將視為組織內部人員。</span><span class="sxs-lookup"><span data-stu-id="cc427-151">Users who have non-guest accounts in a host organization's Active Directory or Azure Active Directory tenant are considered as people inside the organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="cc427-152">敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="cc427-152">Types of sensitive information</span></span>

<span data-ttu-id="cc427-153">DLP 原則有助於保護敏感性資訊 (已定義為 **敏感性資訊類型**)。</span><span class="sxs-lookup"><span data-stu-id="cc427-153">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="cc427-154">Microsoft 365 包含許多不同區域多種常見敏感資訊類型可供您使用，例如信用卡號碼、銀行帳戶號碼、身分證號碼和護照號碼。</span><span class="sxs-lookup"><span data-stu-id="cc427-154">Microsoft 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![可用的敏感性資訊類型清單](../media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="cc427-156">DLP 原則在尋找信用卡號碼等敏感性資訊類型時，並不只是尋找 16 位數的數字。</span><span class="sxs-lookup"><span data-stu-id="cc427-156">When a DLP policy looks for a sensitive information type such as a credit card number, it doesn't simply look for a 16-digit number.</span></span> <span data-ttu-id="cc427-157">使用下列各項的組合可定義和偵測每種敏感資訊類型：</span><span class="sxs-lookup"><span data-stu-id="cc427-157">Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="cc427-158">關鍵字。</span><span class="sxs-lookup"><span data-stu-id="cc427-158">Keywords.</span></span>
    
- <span data-ttu-id="cc427-159">驗證總和檢查碼或結構的內部函數。</span><span class="sxs-lookup"><span data-stu-id="cc427-159">Internal functions to validate checksums or composition.</span></span>
    
- <span data-ttu-id="cc427-160">用以尋找模式相符項目的規則運算式評估。</span><span class="sxs-lookup"><span data-stu-id="cc427-160">Evaluation of regular expressions to find pattern matches.</span></span>
    
- <span data-ttu-id="cc427-161">其他內容檢查。</span><span class="sxs-lookup"><span data-stu-id="cc427-161">Other content examination.</span></span>
    
<span data-ttu-id="cc427-162">這有助於 DLP 偵測達到高度準確性，同時減少可能造成工作中斷的誤判數。</span><span class="sxs-lookup"><span data-stu-id="cc427-162">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples' work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="cc427-163">動作</span><span class="sxs-lookup"><span data-stu-id="cc427-163">Actions</span></span>

<span data-ttu-id="cc427-164">當內容符合規則中的條件時，就可以套用動作以自動保護內容。</span><span class="sxs-lookup"><span data-stu-id="cc427-164">When content matches a condition in a rule, you can apply actions to automatically protect the content.</span></span>
  
![可用的 DLP 動作清單](../media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="cc427-166">您現在可以採取的動作如下：</span><span class="sxs-lookup"><span data-stu-id="cc427-166">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="cc427-167">**限制內容存取權**：根據您的需求，您可以透過三種方式限制內容存取權：</span><span class="sxs-lookup"><span data-stu-id="cc427-167">**Restrict access to the content** Depending on your need, you can restrict access to content in three ways:</span></span>

  1. <span data-ttu-id="cc427-168">限制所有人存取內容。</span><span class="sxs-lookup"><span data-stu-id="cc427-168">Restrict access to content for everyone.</span></span>
  2. <span data-ttu-id="cc427-169">限制組織外部人員存取內容。</span><span class="sxs-lookup"><span data-stu-id="cc427-169">Restrict access to content for people outside the organization.</span></span>
  3. <span data-ttu-id="cc427-170">限制「有連結的任何人」存取。</span><span class="sxs-lookup"><span data-stu-id="cc427-170">Restrict access to "Anyone with the link."</span></span>

  <span data-ttu-id="cc427-171">針對網站內容，這表示文件的權限除了主要網站集合系統管理員、文件擁有者以及最後修改文件的人員以外，所有人都受到限制。</span><span class="sxs-lookup"><span data-stu-id="cc427-171">For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> <span data-ttu-id="cc427-172">這些人員可以移除文件中的敏感性資訊或採取改善動作。</span><span class="sxs-lookup"><span data-stu-id="cc427-172">These people can remove the sensitive information from the document or take other remedial action.</span></span> <span data-ttu-id="cc427-173">當文件符合合規性時，將會自動還原原始權限。</span><span class="sxs-lookup"><span data-stu-id="cc427-173">When the document is in compliance, the original permissions are automatically restored.</span></span> <span data-ttu-id="cc427-174">當文件的存取權遭到封鎖時，文件會在網站的文件庫中顯示，帶有特殊原則提示圖示。</span><span class="sxs-lookup"><span data-stu-id="cc427-174">When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
  ![顯示文件存取的原則提示被封鎖](../media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
  <span data-ttu-id="cc427-176">若是電子郵件內容，這個動作會禁止郵件傳送。</span><span class="sxs-lookup"><span data-stu-id="cc427-176">For email content, this action blocks the message from being sent.</span></span> <span data-ttu-id="cc427-177">取決於 DLP 規則的設定，寄件者會看到 NDR 或 (若規則使用通知) 原則提示及/或電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="cc427-177">Depending on how the DLP rule is configured, the sender sees an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
  ![未授權收件者必須從郵件中移除的警告](../media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="cc427-179">使用者通知和使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="cc427-179">User notifications and user overrides</span></span>

<span data-ttu-id="cc427-180">您可以使用通知和覆寫，讓使用者了解 DLP 原則，協助他們符合規範，而不會封鎖其工作。</span><span class="sxs-lookup"><span data-stu-id="cc427-180">You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work.</span></span> <span data-ttu-id="cc427-181">例如，如果某個使用者嘗試共用含有敏感資訊的文件，DLP 原則可以傳送電子郵件通知給他們，同時在文件庫的內容中顯示原則提示，允許他們因為正當商務理由而覆寫原則。</span><span class="sxs-lookup"><span data-stu-id="cc427-181">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span>
  
![DLP 原則編輯器的使用者通知和使用者覆寫區段](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="cc427-183">電子郵件可以通知傳送、共用或上次修改內容的人員；若是網站內容，還會另外通知主要網站集合系統管理員和文件擁有者。</span><span class="sxs-lookup"><span data-stu-id="cc427-183">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner.</span></span> <span data-ttu-id="cc427-184">此外，您可以從電子郵件通知中新增或移除人員。</span><span class="sxs-lookup"><span data-stu-id="cc427-184">In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="cc427-185">除了傳送電子郵件通知以外，使用者通知也會顯示原則提示：</span><span class="sxs-lookup"><span data-stu-id="cc427-185">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="cc427-186">Outlook 和 Outlook 網頁版中。</span><span class="sxs-lookup"><span data-stu-id="cc427-186">In Outlook and Outlook on the web.</span></span>
    
- <span data-ttu-id="cc427-187">針對 SharePoint Online 或商務用 OneDrive 網站上的文件。</span><span class="sxs-lookup"><span data-stu-id="cc427-187">For the document on a SharePoint Online or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="cc427-188">當文件儲存在 DLP 原則所包含的網站上時，則在 Excel、PowerPoint 及 Word 中。</span><span class="sxs-lookup"><span data-stu-id="cc427-188">In Excel, PowerPoint, and Word, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="cc427-189">電子郵件通知和原則提示會說明內容與 DLP 原則衝突的原因。</span><span class="sxs-lookup"><span data-stu-id="cc427-189">The email notification and policy tip explain why content conflicts with a DLP policy.</span></span> <span data-ttu-id="cc427-190">經選擇後，電子郵件通知和原則提示將可讓使用者藉由回報為誤判或提供正當業務理由來覆寫規則。</span><span class="sxs-lookup"><span data-stu-id="cc427-190">If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification.</span></span> <span data-ttu-id="cc427-191">這可協助您將 DLP 原則正確的相關資訊傳達給使用者，並強制執行這些原則而不會妨礙到其正常工作。</span><span class="sxs-lookup"><span data-stu-id="cc427-191">This can help you educate users about your DLP policies and enforce them without preventing people from doing their work.</span></span> <span data-ttu-id="cc427-192">覆寫及誤判的相關資訊也會記錄並回報 (請參閱以下關於 DLP 報告的資訊)，並納入事件報告中 (下一節)，以便法務人員可以定期檢閱此資訊。</span><span class="sxs-lookup"><span data-stu-id="cc427-192">Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="cc427-193">以下是商務用 OneDrive 帳戶中的原則提示外觀。</span><span class="sxs-lookup"><span data-stu-id="cc427-193">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![OneDrive 帳戶中的文件原則提示](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 <span data-ttu-id="cc427-195">若要深入了解 DLP 原則中的使用者通知和原則提示，請參閱 [使用通知和原則提示](use-notifications-and-policy-tips.md)。</span><span class="sxs-lookup"><span data-stu-id="cc427-195">To learn more about user notifications and policy tips in DLP policies, see [Use notifications and policy tips](use-notifications-and-policy-tips.md).</span></span>

#### <a name="alerts-and-incident-reports"></a><span data-ttu-id="cc427-196">警示和事件報告</span><span class="sxs-lookup"><span data-stu-id="cc427-196">Alerts and Incident reports</span></span>

<span data-ttu-id="cc427-197">規則相符時，您可以將含有警示詳細資料的警示電子郵件傳送給您的法務人員 (或是您選擇的任何人)。</span><span class="sxs-lookup"><span data-stu-id="cc427-197">When a rule is matched, you can send an alert email to your compliance officer ( or any person(s) you choose) with details of the alert.</span></span> <span data-ttu-id="cc427-198">這份警示電子郵件將帶有 [DLP 警示管理儀表板](dlp-configure-view-alerts-policies.md)的連結，法務人員可以打開連結以檢視警示和活動的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cc427-198">This alert email will carry a link of the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md) which the compliance officer can go to view the details of alert and events.</span></span> <span data-ttu-id="cc427-199">儀表板包含觸發警示的事件詳細資料，以及相符的 DLP 原則詳細資料和已偵測到的敏感性內容。</span><span class="sxs-lookup"><span data-stu-id="cc427-199">The dashboard contains details of the event that triggered the alert along with details of the DLP policy matched and the sensitive content detected.</span></span>

<span data-ttu-id="cc427-200">此外，您也可以傳送事件詳細資料的事件報告。</span><span class="sxs-lookup"><span data-stu-id="cc427-200">In addition, you can also send an incident report with details of the event.</span></span> <span data-ttu-id="cc427-201">這份報告包含相符項目的相關資訊、符合規則的實際內容，以及上次修改內容的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="cc427-201">This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content.</span></span> <span data-ttu-id="cc427-202">若是電子郵件訊息，報告則會以附件的方式提供與 DLP 原則相符的原始郵件。</span><span class="sxs-lookup"><span data-stu-id="cc427-202">For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cc427-203">![設定事件報告的頁面](../media/Alerts-and-incident-report.png)</span><span class="sxs-lookup"><span data-stu-id="cc427-203">![Page for configuring incident reports](../media/Alerts-and-incident-report.png)</span></span>

<span data-ttu-id="cc427-204">DLP 掃描電子郵件的方式不同於 SharePoint Online 或商務用 OneDrive 中的項目。</span><span class="sxs-lookup"><span data-stu-id="cc427-204">DLP scans email differently from items in SharePoint Online or OneDrive for Business.</span></span> <span data-ttu-id="cc427-205">在 SharePoint Online 和商務用 OneDrive 中，DLP 會掃描現有項目以及新的項目，並在發現相符項目時產生警示和事件報告。</span><span class="sxs-lookup"><span data-stu-id="cc427-205">In SharePoint Online and OneDrive for Business, DLP scans existing items as well as new ones and generates an alert and incident report whenever a match is found.</span></span> <span data-ttu-id="cc427-206">在 Exchange Online 中，DLP 僅會掃描新的電子郵件訊息，並在原則相符時產生報告。</span><span class="sxs-lookup"><span data-stu-id="cc427-206">In Exchange Online, DLP only scans new email messages and generates a report if there is a policy match.</span></span> <span data-ttu-id="cc427-207">DLP ***不會*** 掃描或比對信箱或封存內儲存的既有電子郵件項目。</span><span class="sxs-lookup"><span data-stu-id="cc427-207">DLP ***does not*** scan or match previously existing email items that are stored in a mailbox or archive.</span></span>
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="cc427-208">群組和邏輯運算子</span><span class="sxs-lookup"><span data-stu-id="cc427-208">Grouping and logical operators</span></span>

<span data-ttu-id="cc427-209">DLP 原則通常都有簡單的需求，例如識別包含美國社會安全號碼的所有內容。</span><span class="sxs-lookup"><span data-stu-id="cc427-209">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number.</span></span> <span data-ttu-id="cc427-210">不過，在其他情況下，DLP 原則可能需要識別出粗略定義的資料。</span><span class="sxs-lookup"><span data-stu-id="cc427-210">However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="cc427-211">例如，若要識別受限於美國健康保險資訊流通及責任法案 (HIPAA) 的內容，您需要尋找：</span><span class="sxs-lookup"><span data-stu-id="cc427-211">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="cc427-212">包含特定類型之機密資訊的內容，例如美國社會安全號碼或藥物管理局 (DEA) 編號。</span><span class="sxs-lookup"><span data-stu-id="cc427-212">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="cc427-213">AND</span><span class="sxs-lookup"><span data-stu-id="cc427-213">AND</span></span>
    
- <span data-ttu-id="cc427-214">更難以識別的內容，例如病患的照護通訊或提供的醫療服務描述。</span><span class="sxs-lookup"><span data-stu-id="cc427-214">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided.</span></span> <span data-ttu-id="cc427-215">要識別此種內容，需要將關鍵字與極大的關鍵字清單比對，例如國際疾病分類 (ICD-9-CM 或 ICD-10-CM)。</span><span class="sxs-lookup"><span data-stu-id="cc427-215">Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="cc427-216">您可以使用群組和邏輯運算子 (AND、OR) 輕鬆識別此類粗略定義的資料。</span><span class="sxs-lookup"><span data-stu-id="cc427-216">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR).</span></span> <span data-ttu-id="cc427-217">您在建立 DLP 原則時可以：</span><span class="sxs-lookup"><span data-stu-id="cc427-217">When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="cc427-218">群組機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="cc427-218">Group sensitive information types.</span></span>
    
- <span data-ttu-id="cc427-219">選擇群組內機密資訊類型之間和群組本身之間的邏輯運算子。</span><span class="sxs-lookup"><span data-stu-id="cc427-219">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="cc427-220">選擇群組內的運算子</span><span class="sxs-lookup"><span data-stu-id="cc427-220">Choosing the operator within a group</span></span>

<span data-ttu-id="cc427-221">在群組內，您可以選擇是只要滿足群組中的任一條件還是必須滿足所有條件，以便將內容視為符合規則。</span><span class="sxs-lookup"><span data-stu-id="cc427-221">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![顯示群組之內運算子的群組](../media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="cc427-223">新增群組</span><span class="sxs-lookup"><span data-stu-id="cc427-223">Adding a group</span></span>

<span data-ttu-id="cc427-224">您可以快速新增具有自己本身之條件和運算子的群組。</span><span class="sxs-lookup"><span data-stu-id="cc427-224">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
![[新增群組] 按鈕](../media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="cc427-226">選擇群組之間的運算子</span><span class="sxs-lookup"><span data-stu-id="cc427-226">Choosing the operator between groups</span></span>

<span data-ttu-id="cc427-227">在群組之間，您可以選擇只要滿足一個群組中的條件，還是必須滿足所有群組的條件，才能將內容視為符合規則。</span><span class="sxs-lookup"><span data-stu-id="cc427-227">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="cc427-228">例如，內建的美國 HIPAA 原則中有一個規則在群組之間使用 **AND** 運算子，以識別包含以下群組的內容：</span><span class="sxs-lookup"><span data-stu-id="cc427-228">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="cc427-229">來自 **[PII 識別碼]** 群組 (至少有一個社會安全號碼或 DEA 編號)</span><span class="sxs-lookup"><span data-stu-id="cc427-229">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="cc427-230">**和**</span><span class="sxs-lookup"><span data-stu-id="cc427-230">**AND**</span></span>
    
- <span data-ttu-id="cc427-231">來自 **[醫療術語]** 群組 (至少有一個 ICD-9-CM 關鍵字或 ICD-10-CM 關鍵字)</span><span class="sxs-lookup"><span data-stu-id="cc427-231">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![顯示群組之間運算子的群組](../media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="cc427-233">處理規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="cc427-233">The priority by which rules are processed</span></span>

<span data-ttu-id="cc427-234">當您在原則中建立規則時，每個規則都會根據建立時間指派優先順序，也就是說，第一個建立的規則具有第一優先順序，第二個建立的規則具有第二優先順序，依此類推。</span><span class="sxs-lookup"><span data-stu-id="cc427-234">When you create rules in a policy, each rule is assigned a priority in the order in which it's created — meaning, the rule created first has first priority, the rule created second has second priority, and so on.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cc427-235">![依優先順序排列的規則](../media/dlp-rules-in-priority-order.png)</span><span class="sxs-lookup"><span data-stu-id="cc427-235">![Rules in priority order](../media/dlp-rules-in-priority-order.png)</span></span>
  
<span data-ttu-id="cc427-236">您設定一個以上的 DLP 原則之後，可以變更一或多個原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="cc427-236">After you have set up more than one DLP policy, you can change the priority of one or more policies.</span></span> <span data-ttu-id="cc427-237">若要這樣做，請選取原則，選擇 **[編輯原則]**，然後使用 **[優先順序]** 清單來指定優先順序。</span><span class="sxs-lookup"><span data-stu-id="cc427-237">To do that, select a policy, choose **Edit policy**, and use the **Priority** list to specify its priority.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cc427-238">![設定原則的優先順序](../media/dlp-set-policy-priority.png)</span><span class="sxs-lookup"><span data-stu-id="cc427-238">![Set priority for a policy](../media/dlp-set-policy-priority.png)</span></span>

<span data-ttu-id="cc427-239">以規則評估內容時，系統會依優先順序處理規則。</span><span class="sxs-lookup"><span data-stu-id="cc427-239">When content is evaluated against rules, the rules are processed in priority order.</span></span> <span data-ttu-id="cc427-240">如果內容符合多條規則，系統會依優先順序進行處理，並強制執行限制最嚴苛的動作。</span><span class="sxs-lookup"><span data-stu-id="cc427-240">If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced.</span></span> <span data-ttu-id="cc427-241">舉例來說，如果內容符合下列所有規則，系統會強制執行規則 3，因為它是優先順序最高、最嚴格的規則：</span><span class="sxs-lookup"><span data-stu-id="cc427-241">For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="cc427-242">規則 1：只通知使用者</span><span class="sxs-lookup"><span data-stu-id="cc427-242">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="cc427-243">規則 2：通知使用者、限制存取且允許使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="cc427-243">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="cc427-244">規則 3：通知使用者、限制存取且不允許使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="cc427-244">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="cc427-245">規則 4：只通知使用者</span><span class="sxs-lookup"><span data-stu-id="cc427-245">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="cc427-246">規則 5：限制存取</span><span class="sxs-lookup"><span data-stu-id="cc427-246">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="cc427-247">規則 6：通知使用者、限制存取且不允許使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="cc427-247">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="cc427-248">請注意，在此範例中雖然只強制執行了最嚴格的那項規則，但所有符合規則的項目都會記錄在稽核記錄中，並顯示於 DLP 報告。</span><span class="sxs-lookup"><span data-stu-id="cc427-248">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="cc427-249">關於原則提示，請注意：</span><span class="sxs-lookup"><span data-stu-id="cc427-249">Regarding policy tips, note that:</span></span>
  
- <span data-ttu-id="cc427-250">只會顯示最高優先順序、最嚴格規則的原則提示。</span><span class="sxs-lookup"><span data-stu-id="cc427-250">Only the policy tip from the highest priority, most restrictive rule will be shown.</span></span> <span data-ttu-id="cc427-251">例如，會封鎖內容存取權的規則與僅傳送通知的規則，只會顯示前者的原則提示。</span><span class="sxs-lookup"><span data-stu-id="cc427-251">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="cc427-252">這樣可避免使用者看到重疊顯示的原則提示。</span><span class="sxs-lookup"><span data-stu-id="cc427-252">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="cc427-253">如果最嚴格規則中的原則提示允許人員覆寫規則，則覆寫此規則也將會覆寫內容符合的任何其他規則。</span><span class="sxs-lookup"><span data-stu-id="cc427-253">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="cc427-254">調整規則以讓它們更容易或更難符合</span><span class="sxs-lookup"><span data-stu-id="cc427-254">Tuning rules to make them easier or harder to match</span></span>

<span data-ttu-id="cc427-255">在建立並開啟 DLP 原則後，有時候會遇到下列問題：</span><span class="sxs-lookup"><span data-stu-id="cc427-255">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="cc427-256">太多 **非** 敏感性資訊的內容符合規則，換句話說就是太多誤判。</span><span class="sxs-lookup"><span data-stu-id="cc427-256">Too much content that **is not** sensitive information matches the rules — in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="cc427-257">太少內容 **是** 敏感性資訊符合規則。</span><span class="sxs-lookup"><span data-stu-id="cc427-257">Too little content that **is** sensitive information matches the rules.</span></span> <span data-ttu-id="cc427-258">換句話說，不會對敏感性資訊強制執行保護動作。</span><span class="sxs-lookup"><span data-stu-id="cc427-258">In other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="cc427-259">若要解決這些問題，您可以調整規則的執行個體計數及比對精確度，使得內容更難或更易於符合規則。</span><span class="sxs-lookup"><span data-stu-id="cc427-259">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules.</span></span> <span data-ttu-id="cc427-260">規則中使用的每個機密資訊類型都同時具有執行個體計數及比對精確度。</span><span class="sxs-lookup"><span data-stu-id="cc427-260">Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="cc427-261">執行個體計數</span><span class="sxs-lookup"><span data-stu-id="cc427-261">Instance count</span></span>

<span data-ttu-id="cc427-262">執行個體計數指的是特定敏感性資訊類型必須在內容中出現多少次才能符合規則的次數。</span><span class="sxs-lookup"><span data-stu-id="cc427-262">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule.</span></span> <span data-ttu-id="cc427-263">例如，如果識別出 1 到 9 個之間的不重複美國或英國護照號碼，</span><span class="sxs-lookup"><span data-stu-id="cc427-263">For example, content matches the rule shown below if between 1 and 9 unique U.S. or U.K.</span></span> <span data-ttu-id="cc427-264">內容就符合以下顯示的規則。</span><span class="sxs-lookup"><span data-stu-id="cc427-264">passport numbers are identified.</span></span>

> [!NOTE]
> <span data-ttu-id="cc427-265">執行個體計數僅包含符合敏感性資訊類型和關鍵字的 **不重複** 項目。</span><span class="sxs-lookup"><span data-stu-id="cc427-265">The instance count includes only **unique** matches for sensitive information types and keywords.</span></span> <span data-ttu-id="cc427-266">例如，如果有一封電子郵件內出現 10 次同一組信用卡號碼，這 10 次只會採計為該信用卡號碼出現一次。</span><span class="sxs-lookup"><span data-stu-id="cc427-266">For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span>
  
<span data-ttu-id="cc427-267">使用執行個體計數來調整規則的指導方針非常簡單：</span><span class="sxs-lookup"><span data-stu-id="cc427-267">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="cc427-268">若要讓規則更容易符合，請減少 **[最小]** 計數及/或增加 **[最大]** 計數。</span><span class="sxs-lookup"><span data-stu-id="cc427-268">To make the rule easier to match, decrease the **min** count and/or increase the **max** count.</span></span> <span data-ttu-id="cc427-269">您也可以刪除 **[最大]** 中的數值以將它設定成 **[任意]**。</span><span class="sxs-lookup"><span data-stu-id="cc427-269">You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="cc427-270">若要讓規則更難符合，請增加 **[最小]** 計數。</span><span class="sxs-lookup"><span data-stu-id="cc427-270">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="cc427-271">一般而言，您會在執行個體計數較低 (例如 1 到 9) 的規則中使用較不具限制性的動作，例如傳送使用者通知。</span><span class="sxs-lookup"><span data-stu-id="cc427-271">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9).</span></span> <span data-ttu-id="cc427-272">並在執行個體計數較高 (例如 10 到任意) 的規則中使用較多限制的動作，例如限制存取內容且不允許使用者覆寫。</span><span class="sxs-lookup"><span data-stu-id="cc427-272">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![規則編輯器中的執行個體計數](../media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="cc427-274">比對精確度</span><span class="sxs-lookup"><span data-stu-id="cc427-274">Match accuracy</span></span>

<span data-ttu-id="cc427-275">如上所述，機密資訊類型會由不同類型證據所形成的組合來定義與偵測。</span><span class="sxs-lookup"><span data-stu-id="cc427-275">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence.</span></span> <span data-ttu-id="cc427-276">一般而言，機密資訊類型會由多種這樣的組合 (稱為模式) 所定義。</span><span class="sxs-lookup"><span data-stu-id="cc427-276">Commonly, a sensitive information type is defined by multiple such combinations, called patterns.</span></span> <span data-ttu-id="cc427-277">證據需求較低的模式具有較低的比對精確度 (或信賴等級)，而證據需求較高的模式，其比對精確度 (或信賴等級) 則較高。</span><span class="sxs-lookup"><span data-stu-id="cc427-277">A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level).</span></span> <span data-ttu-id="cc427-278">若要深入了解各機密資訊類型實際使用的模式及信賴等級，請參閱[敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="cc427-278">To learn more about the actual patterns and confidence levels used by every sensitive information type, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>
  
<span data-ttu-id="cc427-279">例如，名為 [信用卡號碼] 的機密資訊類型是由兩種模式所定義：</span><span class="sxs-lookup"><span data-stu-id="cc427-279">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="cc427-280">一個 65% 信賴度的模式，所需證據為：</span><span class="sxs-lookup"><span data-stu-id="cc427-280">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="cc427-281">一組信用卡號碼形式的數字。</span><span class="sxs-lookup"><span data-stu-id="cc427-281">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="cc427-282">一組通過總和檢查碼的數字。</span><span class="sxs-lookup"><span data-stu-id="cc427-282">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="cc427-283">一個 85% 信賴度的模式，所需證據為：</span><span class="sxs-lookup"><span data-stu-id="cc427-283">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="cc427-284">一組信用卡號碼形式的數字。</span><span class="sxs-lookup"><span data-stu-id="cc427-284">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="cc427-285">一組通過總和檢查碼的數字。</span><span class="sxs-lookup"><span data-stu-id="cc427-285">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="cc427-286">格式正確的關鍵字或到期日。</span><span class="sxs-lookup"><span data-stu-id="cc427-286">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="cc427-287">您可以在自己的規則中使用這些信賴等級 (或比對精確度)。</span><span class="sxs-lookup"><span data-stu-id="cc427-287">You can use these confidence levels (or match accuracy) in your rules.</span></span> <span data-ttu-id="cc427-288">一般而言，您會在比對精確度較低的規則中使用較不具限制性的動作，例如傳送使用者通知。</span><span class="sxs-lookup"><span data-stu-id="cc427-288">Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy.</span></span> <span data-ttu-id="cc427-289">並在比對精確度較高的規則中使用較多限制的動作，例如限制存取內容且不允許使用者覆寫。</span><span class="sxs-lookup"><span data-stu-id="cc427-289">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="cc427-290">請務必記得，當在內容中辨識出特定機密資訊類型 (例如信用卡號碼) 時，系統只會傳回一個信賴等級：</span><span class="sxs-lookup"><span data-stu-id="cc427-290">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="cc427-291">如果所有符合項目都是來自同一個模式，那麼會傳回該模式的信賴等級。</span><span class="sxs-lookup"><span data-stu-id="cc427-291">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="cc427-292">如果符合的模式不只一個 (亦即有兩種不同信賴等級的相符項目)，則會傳回單一模式中最大的信賴等級。</span><span class="sxs-lookup"><span data-stu-id="cc427-292">If there are matches for more than one pattern (that is, there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned.</span></span> <span data-ttu-id="cc427-293">這部分就有點複雜了。</span><span class="sxs-lookup"><span data-stu-id="cc427-293">This is the tricky part.</span></span> <span data-ttu-id="cc427-294">以信用卡為例，如果同時符合了 65% 和 85% 的模式，該機密資訊傳回的信賴等級會大於 90%，因為證據越多代表信賴度越高。</span><span class="sxs-lookup"><span data-stu-id="cc427-294">For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="cc427-295">因此，如果您想要為信用卡建立兩個互斥規則，一個比對精確度為 65%，另一個為 85%，那麼比對精確度的範圍會像下面這樣。</span><span class="sxs-lookup"><span data-stu-id="cc427-295">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this.</span></span> <span data-ttu-id="cc427-296">第一個規則只會挑選與模式 65% 相符的項目。</span><span class="sxs-lookup"><span data-stu-id="cc427-296">The first rule picks up only matches of the 65% pattern.</span></span> <span data-ttu-id="cc427-297">第二個規則至少會挑選 85% 相符的項目，並可能會有其他較低信賴度的相符項目。</span><span class="sxs-lookup"><span data-stu-id="cc427-297">The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![兩個比對精確度範圍不同的規則](../media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="cc427-299">由於這些原因，建立具有不同比對精確度之規則的指導方針為：</span><span class="sxs-lookup"><span data-stu-id="cc427-299">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="cc427-300">最低信賴等級的 **[最小]** 和 **[最大]** 值通常會使用同一個值 (而不是一個範圍)。</span><span class="sxs-lookup"><span data-stu-id="cc427-300">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="cc427-301">最高的信賴等級通常會是一個稍高於最低信賴等級到 100 的範圍。</span><span class="sxs-lookup"><span data-stu-id="cc427-301">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="cc427-302">任何介於中間的信賴等級則通常是一個稍高於最低信賴等級，到稍低於最高信賴等級之間的範圍。</span><span class="sxs-lookup"><span data-stu-id="cc427-302">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="cc427-303">使用保留標籤作為 DLP 原則的條件</span><span class="sxs-lookup"><span data-stu-id="cc427-303">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="cc427-304">當您在 DLP 原則中使用先前建立及發佈的[保留標籤](retention.md#retention-labels)做為條件時，請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="cc427-304">When you use a previously created and published [retention label](retention.md#retention-labels) as a condition in a DLP policy, there are some things to be aware of:</span></span>

- <span data-ttu-id="cc427-305">您必須先建立並發佈保留標籤，然後才能嘗試將它做為 DLP 原則中的條件。</span><span class="sxs-lookup"><span data-stu-id="cc427-305">The retention label must be created and published before you attempt to use it as a condition in a DLP policy.</span></span>
- <span data-ttu-id="cc427-306">已發佈的保留標籤會在一到七天內進行同步處理。如需詳細資訊，關於保留原則中已發佈的保留標籤請參閱 [當保留標籤可以使用時](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) ，關於自動發佈的保留標籤請參閱 [保留標籤要多久才會生效](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect)。</span><span class="sxs-lookup"><span data-stu-id="cc427-306">Published retention labels can take from one to seven days to sync. For more information, see [When retention labels become available to apply](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) for retention labels published in a retention policy, and [How long it takes for retention labels to take effect](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect) for retention labels that are auto-published.</span></span>
- <span data-ttu-id="cc427-307">\*\*僅 SharePoint 和 OneDrive 中的項目才支援\*\*\*在原則中使用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="cc427-307">Using a retention label in a policy \*\*is only supported for items in SharePoint and OneDrive\*\*\*.</span></span>

  ![做為條件的標籤](../media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

  <span data-ttu-id="cc427-309">如果您的項目受保留與處置的限制，且您也想要對這些項目套用其他控制，則可以在 DLP 原則中使用保留標籤，例如：</span><span class="sxs-lookup"><span data-stu-id="cc427-309">You might want to use a retention label in a DLP policy if you have items that are under retention and disposition, and you also want to apply other controls to them, for example:</span></span>

  - <span data-ttu-id="cc427-310">您發佈了一個名為 **2018 年稅務** 的保留標籤，該保留標籤會套用至儲存在 SharePoint 中 2018 年的稅務文件，保留 10 年，然後加以處置。</span><span class="sxs-lookup"><span data-stu-id="cc427-310">You published a retention label named **tax year 2018**, which when applied to tax documents from 2018 that are stored in SharePoint retains them for 10 years then disposes of them.</span></span> <span data-ttu-id="cc427-311">您也不想要在組織外共用這些項目，則可以使用 DLP 原則執行此動作。</span><span class="sxs-lookup"><span data-stu-id="cc427-311">You also don't want those items being shared outside your organization, which you can do with a DLP policy.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="cc427-312">如果您指定保留標籤做為 DLP 原則的條件，且也將 Exchange 和/或 Teams 包含為位置，您會遇到此錯誤：**「不支援保護電子郵件與小組訊息內套用標籤的內容。請移除下列標籤或關閉 Exchange 與 Teams 做為位置。」**</span><span class="sxs-lookup"><span data-stu-id="cc427-312">You'll get this error if you specify a retention label as a condition in a DLP policy and you also include Exchange and/or Teams as a location: **"Protecting labeled content in email and teams messages isn't supported. Either remove the label below or turn off Exchange and Teams as a location."**</span></span> <span data-ttu-id="cc427-313">這是因為 Exchange 傳輸不會在提交與傳遞郵件期間評估標籤中繼資料。</span><span class="sxs-lookup"><span data-stu-id="cc427-313">This is because Exchange transport does not evaluate the label metadata during message submission and delivery.</span></span> 

### <a name="using-a-sensitivity-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="cc427-314">使用敏感度標籤做為 DLP 原則的條件</span><span class="sxs-lookup"><span data-stu-id="cc427-314">Using a sensitivity label as a condition in a DLP policy</span></span>

<span data-ttu-id="cc427-315">若要[深入瞭解](./dlp-sensitivity-label-as-condition.md)，請參閱使用敏感度標籤做為 DLP 原則中的條件。</span><span class="sxs-lookup"><span data-stu-id="cc427-315">[Learn more](./dlp-sensitivity-label-as-condition.md) about using Sensitivity label as a condition in DLP policies.</span></span>
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="cc427-316">這項功能與其他功能的關係</span><span class="sxs-lookup"><span data-stu-id="cc427-316">How this feature relates to other features</span></span>

<span data-ttu-id="cc427-317">有多項功能可以套用到含有敏感性資訊的內容：</span><span class="sxs-lookup"><span data-stu-id="cc427-317">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="cc427-318">[保留標籤和保留原則](retention.md) 都能對內容強制執行 **保留** 動作。</span><span class="sxs-lookup"><span data-stu-id="cc427-318">A [retention label and a retention policy](retention.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="cc427-319">DLP 原則可以對內容強制執行 **「保護」** 動作。</span><span class="sxs-lookup"><span data-stu-id="cc427-319">A DLP policy can enforce **protection** actions on this content.</span></span> <span data-ttu-id="cc427-320">您不僅要為內容設定標籤，還要讓內容滿足其他條件，DLP 原則才能強制執行這些動作。</span><span class="sxs-lookup"><span data-stu-id="cc427-320">And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![可對敏感性資訊執行的功能圖表](../media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="cc427-322">請注意，DLP 原則的偵測功能比套用到敏感性資訊的任何標籤或保留原則來得強大。</span><span class="sxs-lookup"><span data-stu-id="cc427-322">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information.</span></span> <span data-ttu-id="cc427-323">DLP 原則可以針對含有敏感性資訊的內容強制執行保護動作。如果敏感性資訊已從內容中移除，就可以在系統再次掃描內容後復原相關的保護動作。</span><span class="sxs-lookup"><span data-stu-id="cc427-323">A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned.</span></span> <span data-ttu-id="cc427-324">但是，如果保留原則或標籤套用到含有敏感性資訊的內容，就是一次性動件。之後即使移除敏感性資訊，也無法復原。</span><span class="sxs-lookup"><span data-stu-id="cc427-324">But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information is removed.</span></span>
  
<span data-ttu-id="cc427-325">如果將標籤做為 DLP 原則的條件，就可以針對設有該標籤的內容來強制執行保留和保護動作。</span><span class="sxs-lookup"><span data-stu-id="cc427-325">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label.</span></span> <span data-ttu-id="cc427-326">設有標籤的內容就像是含有敏感性資訊的內容，標籤和敏感性資訊類型都是用來分類內容的屬性，您可以藉此針對內容強制執行動作。</span><span class="sxs-lookup"><span data-stu-id="cc427-326">You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![將標籤做為條件的 DLP 原則的圖表](../media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="cc427-328">簡單設定和進階設定的比較</span><span class="sxs-lookup"><span data-stu-id="cc427-328">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="cc427-329">建立 DLP 原則時，您可選擇簡單或進階設定：</span><span class="sxs-lookup"><span data-stu-id="cc427-329">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="cc427-330">**簡單設定** 可讓您輕鬆建立最常見的 DLP 原則，而不使用規則編輯器來建立或修改規則。</span><span class="sxs-lookup"><span data-stu-id="cc427-330">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="cc427-331">**進階設定** 會使用規則編輯器，提供您 DLP 原則設定的完整控制權。</span><span class="sxs-lookup"><span data-stu-id="cc427-331">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="cc427-332">別擔心，除了設定方式以外，簡單設定與進階設定的運作方式完全相同，皆會強制執行由條件及動作構成的原則，唯一的差別在於使用簡單設定時，您不會看見規則編輯器。</span><span class="sxs-lookup"><span data-stu-id="cc427-332">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions—only with simple settings, you don't see the rule editor.</span></span> <span data-ttu-id="cc427-333">最快的方式便是建立 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="cc427-333">It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="cc427-334">簡單設定</span><span class="sxs-lookup"><span data-stu-id="cc427-334">Simple settings</span></span>

<span data-ttu-id="cc427-335">目前，最常見的 DLP 情境是建立原則以協助保護含有敏感性資訊的內容，避免組織外部的人員共用這類內容，並採取自動修正動作，如限制可存取內容的對象、傳送使用者或系統管理員通知，並稽核事件以便日後調查。</span><span class="sxs-lookup"><span data-stu-id="cc427-335">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remediating action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation.</span></span> <span data-ttu-id="cc427-336">採用 DLP 的人員可協助避免敏感性資訊不當外洩。</span><span class="sxs-lookup"><span data-stu-id="cc427-336">People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="cc427-337">若要以更簡單的方式達成這個目標，請在建立 DLP 原則時，選擇 **[使用簡單設定]**。</span><span class="sxs-lookup"><span data-stu-id="cc427-337">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**.</span></span> <span data-ttu-id="cc427-338">這些設定會提供執行最常見 DLP 原則所需的項目，讓您不必進入規則編輯器。</span><span class="sxs-lookup"><span data-stu-id="cc427-338">These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![用於顯示簡易和進階設定的 DLP 選項](../media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="cc427-340">進階設定</span><span class="sxs-lookup"><span data-stu-id="cc427-340">Advanced settings</span></span>

<span data-ttu-id="cc427-341">如果您要建立更多自訂 DLP 原則，您可以選擇 **[使用進階設定]**。</span><span class="sxs-lookup"><span data-stu-id="cc427-341">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="cc427-342">使用進階設定即可顯示規則編輯器。在編輯器中，您擁有所有選項的完整控制權，包括每個規則的執行個體計數及相符準確度 (信賴層級)。</span><span class="sxs-lookup"><span data-stu-id="cc427-342">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="cc427-343">若要快速移至某個區段，只要按一下規則編輯器頂端瀏覽區中的項目，即可移至下方的該區段。</span><span class="sxs-lookup"><span data-stu-id="cc427-343">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![DLP 規則編輯器的頂端瀏覽功能表](../media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="cc427-345">DLP 原則範本</span><span class="sxs-lookup"><span data-stu-id="cc427-345">DLP policy templates</span></span>

<span data-ttu-id="cc427-346">建立 DLP 原則的第一步是選擇要保護的資訊。</span><span class="sxs-lookup"><span data-stu-id="cc427-346">The first step in creating a DLP policy is choosing what information to protect.</span></span> <span data-ttu-id="cc427-347">從 DLP 範本開始，您就省去從頭建立新規則集，以及釐清應依預設包含資訊類型的工作。</span><span class="sxs-lookup"><span data-stu-id="cc427-347">By starting with a DLP template, you save the work of building a new set of rules from scratch, and figuring out which types of information should be included by default.</span></span> <span data-ttu-id="cc427-348">接著，您可以新增或修改這些需求以微調規則，達到組織的特定需求。</span><span class="sxs-lookup"><span data-stu-id="cc427-348">You can then add to or modify these requirements to fine tune the rule to meet your organization's specific requirements.</span></span>
  
<span data-ttu-id="cc427-349">預先設定的原則範本可協助您偵測特定的敏感性資訊類型，例如 HIPAA 資料、PCI-DSS 資料、Gramm-Leach-Bliley 金融服務業現代化法案資料，或甚至是特定地區設定的個人識別資訊 (PII)。</span><span class="sxs-lookup"><span data-stu-id="cc427-349">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (P.I.).</span></span> <span data-ttu-id="cc427-350">為了讓您能輕鬆地尋找並保護常見的敏感資訊類型，Microsoft 365 中包含的原則範本納入了最常見的敏感資訊類型，讓您快速著手使用。</span><span class="sxs-lookup"><span data-stu-id="cc427-350">To make it easy for you to find and protect common types of sensitive information, the policy templates included in Microsoft 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![資料外洩防護原則的範本清單，重點在於針對美國的範本愛國者法案](../media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="cc427-352">貴組織也可能設有專屬需求，在這種情況下，您可以選擇 **[自訂原則]** 選項從頭建立 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="cc427-352">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch by choosing the **Custom policy** option.</span></span> <span data-ttu-id="cc427-353">自訂原則中不會有任何內容，也不含預先製作的規則。</span><span class="sxs-lookup"><span data-stu-id="cc427-353">A custom policy is empty and contains no premade rules.</span></span> 
  
<!-- ## Roll out DLP policies gradually with test mode

rehomed to Plan for DLP

When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.
  
If you're creating DLP policies with a large potential impact, we recommend following this sequence:
  
1. **Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization. 
    
2. **Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules. 
    
3. **Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend. 

    ![Options for using test mode and turning on policy](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    You can turn off a DLP policy at any time, which affects all rules in the policy. However, each rule can also be turned off individually by toggling its status in the rule editor.

    ![Options for turning off a rule in a policy](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    You can also change the priority of multiple rules in a policy. To do that, open a policy for editing. In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.

    > [!div class="mx-imgBorder"]
    > ![Set rule priority](../media/dlp-set-rule-priority.png)-->
  
## <a name="dlp-reports"></a><span data-ttu-id="cc427-354">DLP 報告</span><span class="sxs-lookup"><span data-stu-id="cc427-354">DLP reports</span></span>

<span data-ttu-id="cc427-355">建立並開啟您的 DLP 原則之後，您會想要確認原則是否達到您想要的效果並有助於您符合規範。</span><span class="sxs-lookup"><span data-stu-id="cc427-355">After you create and turn on your DLP policies, you'll want to verify that they're working as you intended and helping you stay compliant.</span></span> <span data-ttu-id="cc427-356">透過 DLP 報告，您可以快速檢視一段時間內的 DLP 原則和規則相符項目的數目，以及誤判和覆寫的數目。</span><span class="sxs-lookup"><span data-stu-id="cc427-356">With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides.</span></span> <span data-ttu-id="cc427-357">針對每份報告，您可以依據位置、時間範圍篩選這些相符項目，甚至將其範圍縮小到特定原則、規則或動作。</span><span class="sxs-lookup"><span data-stu-id="cc427-357">For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="cc427-358">透過 DLP 報告，您將可取得深入的商業資訊，並且：</span><span class="sxs-lookup"><span data-stu-id="cc427-358">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="cc427-359">將重點放在特定時段，以了解尖峰和趨勢的原因。</span><span class="sxs-lookup"><span data-stu-id="cc427-359">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="cc427-360">探索違反貴組織規範原則的商務程序。</span><span class="sxs-lookup"><span data-stu-id="cc427-360">Discover business processes that violate your organization's compliance policies.</span></span>
    
- <span data-ttu-id="cc427-361">了解 DLP 原則帶來的任何業務影響。</span><span class="sxs-lookup"><span data-stu-id="cc427-361">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="cc427-362">此外，您可以使用 DLP 報告來微調您所執行的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="cc427-362">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![安全性與合規性中心中的報表儀表板](../media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="cc427-364">DLP 原則的運作方式</span><span class="sxs-lookup"><span data-stu-id="cc427-364">How DLP policies work</span></span>

<span data-ttu-id="cc427-p150">DLP 會使用深度內容分析 (不只是簡單的文字掃描) 來偵測敏感資訊。此深度內容分析會使用關鍵字比對、字典比對、規則運算式評估、內部函數和其他方法來偵測符合 DLP 原則的內容。可能只有一小部分的資料會被視為敏感資訊。DLP 原則可識別、監視和自動保護該項資料，而不會妨礙或影響到使用其餘內容的人員。</span><span class="sxs-lookup"><span data-stu-id="cc427-p150">DLP detects sensitive information by using deep content analysis (not just a simple text scan). This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies. Potentially only a small percentage of your data is considered sensitive. A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="cc427-369">原則會同步處理</span><span class="sxs-lookup"><span data-stu-id="cc427-369">Policies are synced</span></span>

<span data-ttu-id="cc427-370">在安全性與合規性中心中建立 DLP 原則之後，原則會儲存在中央原則存放區中，然後再同步處理至各種內容來源，包括：</span><span class="sxs-lookup"><span data-stu-id="cc427-370">After you create a DLP policy in the Security &amp; Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="cc427-371">Exchange Online，再從這裡到 Outlook 網頁版和 Outlook。</span><span class="sxs-lookup"><span data-stu-id="cc427-371">Exchange Online, and from there to Outlook on the web and Outlook.</span></span>
    
- <span data-ttu-id="cc427-372">商務用 OneDrive 網站。</span><span class="sxs-lookup"><span data-stu-id="cc427-372">OneDrive for Business sites.</span></span>
    
- <span data-ttu-id="cc427-373">SharePoint Online 網站。</span><span class="sxs-lookup"><span data-stu-id="cc427-373">SharePoint Online sites.</span></span>
    
- <span data-ttu-id="cc427-374">Office 桌上型電腦程式 (Excel、PowerPoint 及 Word)。</span><span class="sxs-lookup"><span data-stu-id="cc427-374">Office desktop programs (Excel, PowerPoint, and Word).</span></span>

- <span data-ttu-id="cc427-375">Microsoft Teams 頻道和聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="cc427-375">Microsoft Teams channels and chat messages.</span></span>
    
<span data-ttu-id="cc427-376">原則同步處理至正確的位置之後，會開始評估內容並強制執行動作。</span><span class="sxs-lookup"><span data-stu-id="cc427-376">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="cc427-377">商務用 OneDrive 和 SharePoint Online 網站中的原則評估</span><span class="sxs-lookup"><span data-stu-id="cc427-377">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="cc427-378">在您所有的 SharePoint Online 網站和商務用 OneDrive 網站上，文件都會持續變動 — 文件會不斷地建立、編輯、共用等等。</span><span class="sxs-lookup"><span data-stu-id="cc427-378">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they're continually being created, edited, shared, and so on.</span></span> <span data-ttu-id="cc427-379">這表示文件可能會隨時違反或符合 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="cc427-379">This means documents can conflict or become compliant with a DLP policy at any time.</span></span> <span data-ttu-id="cc427-380">例如，人員可以將不含敏感資訊文件上傳到小組網站，而後另一個人可以編輯同一份文件並在其中加入敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="cc427-380">For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="cc427-p152">因此，DLP 原則會頻繁地在背景中檢查文件是否有原則相符項目。您可以將此視為非同步原則評估。</span><span class="sxs-lookup"><span data-stu-id="cc427-p152">For this reason, DLP policies check documents for policy matches frequently in the background. You can think of this as asynchronous policy evaluation. </span></span><!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a><span data-ttu-id="cc427-383">運作方式</span><span class="sxs-lookup"><span data-stu-id="cc427-383">How it works</span></span>
 
<span data-ttu-id="cc427-384">當使用者新增或變更其網站中的文件時，搜尋引擎會掃描內容，使您可以在稍後搜尋。</span><span class="sxs-lookup"><span data-stu-id="cc427-384">As people add or change documents in their sites, the search engine scans the content, so that you can search for it later.</span></span> <span data-ttu-id="cc427-385">執行這個動作時，也會掃描內容的敏感性資訊，並檢查它是否為共用。</span><span class="sxs-lookup"><span data-stu-id="cc427-385">While this is happening, the content's also scanned for sensitive information and to check if it's shared.</span></span> <span data-ttu-id="cc427-386">找到的任何敏感性資訊會安全地儲存在搜尋索引中，只有合規性小組能夠存取，一般使用者無法存取。</span><span class="sxs-lookup"><span data-stu-id="cc427-386">Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users.</span></span> <span data-ttu-id="cc427-387">您已開啟的每個 DLP 原則會在背景執行 (以非同步方式)，頻繁地對於符合原則的任何內容檢查搜尋，並套用動作以防止意外的資料外洩。</span><span class="sxs-lookup"><span data-stu-id="cc427-387">Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![顯示 DLP 原則如何以非同步的方式評估內容的圖表](../media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording --><span data-ttu-id="cc427-p154"> 最後，文件可能會違反 DLP 原則，但也可能會符合 DLP 原則。例如，如果人員在文件中加入信用卡號碼，有可能會導致 DLP 原則自動封鎖文件的存取。但如果人員稍後移除敏感資訊，則會在下次依據原則進行評估時自動復原動作 (在此案例中為封鎖)。</span><span class="sxs-lookup"><span data-stu-id="cc427-p154"> Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy. For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically. But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="cc427-392">DLP 會評估可編製索引的任何內容。</span><span class="sxs-lookup"><span data-stu-id="cc427-392">DLP evaluates any content that can be indexed.</span></span> <span data-ttu-id="cc427-393">若要進一步了解依預設會對哪些檔案類型進行編目，請參閱 [SharePoint Server 中的預設編目副檔名和剖析檔案類型](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)。</span><span class="sxs-lookup"><span data-stu-id="cc427-393">For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).</span></span>

> [!NOTE]
> <span data-ttu-id="cc427-394">為了防止在 DLP 原則進行分析之前共用檔，在 SharePoint 中共用的新檔案可能會封鎖，直到其內容已編制索引為止。</span><span class="sxs-lookup"><span data-stu-id="cc427-394">In order to prevent documents from being shared before DLP policies had the opportunity to analyze them, sharing of new files in SharePoint can be blocked until its content has been indexed.</span></span> <span data-ttu-id="cc427-395">如需詳細資訊，請參閱 [透過預設，將新檔案標示為敏感檔案](/sharepoint/sensitive-by-default)。</span><span class="sxs-lookup"><span data-stu-id="cc427-395">See, [Mark new files as sensitive by default](/sharepoint/sensitive-by-default) for detailed information.</span></span> 
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a><span data-ttu-id="cc427-396">Exchange Online、Outlook 和 Outlook 網頁版中的原則評估</span><span class="sxs-lookup"><span data-stu-id="cc427-396">Policy evaluation in Exchange Online, Outlook, and Outlook on the web</span></span>

<span data-ttu-id="cc427-397">當您建立 DLP 原則，其中包含 Exchange Online 作為位置時，原則會從 Office 365 安全性與合規性中心同步到 Exchange Online，然後從 Exchange Online 同步到 Outlook 網頁版和 Outlook。</span><span class="sxs-lookup"><span data-stu-id="cc427-397">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook.</span></span>
  
<span data-ttu-id="cc427-398">在 Outlook 中撰寫郵件時，若使用者撰寫的內容經評估後判定違反 DLP 原則，就會看見原則提示。</span><span class="sxs-lookup"><span data-stu-id="cc427-398">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies.</span></span> <span data-ttu-id="cc427-399">郵件送出時，系統會在一般郵件流程中進行 DLP 原則評估，此外也會一併執行 Exchange 系統管理中心中建立的 Exchange 郵件流程規則 (也稱為傳輸規則) 和 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="cc427-399">And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange mail flow rules (also known as transport rules) and DLP policies created in the Exchange admin center.</span></span> <span data-ttu-id="cc427-400">DLP 原則會掃描郵件和所有附件。</span><span class="sxs-lookup"><span data-stu-id="cc427-400">DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a><span data-ttu-id="cc427-401">Office 桌上型電腦程式中的原則評估</span><span class="sxs-lookup"><span data-stu-id="cc427-401">Policy evaluation in the Office desktop programs</span></span>

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
<span data-ttu-id="cc427-402">Excel、PowerPoint 和 Word 都具有與 SharePoint Online 和商務用 OneDrive 相同的功能，可識別敏感資訊並套用 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="cc427-402">Excel, PowerPoint, and Word include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="cc427-403">這些 Office 程式會直接從中央原則存放區同步處理其 DLP 原則，並在有人使用從 DLP 原則所包含的網站開啟的文件時，持續根據 DLP 原則來評估內容。</span><span class="sxs-lookup"><span data-stu-id="cc427-403">These Office programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that's included in a DLP policy.</span></span>
  
<span data-ttu-id="cc427-404">Office 中的 DLP 原則評估依設計並不會影響程式的效能或內容使用者的產能。</span><span class="sxs-lookup"><span data-stu-id="cc427-404">DLP policy evaluation in Office is designed not to affect the performance of the programs or the productivity of people working on content.</span></span> <span data-ttu-id="cc427-405">如果他們正在處理大型文件，或使用者的電腦忙碌中，可能需要幾秒鐘才會顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="cc427-405">If they're working on a large document, or the user's computer is busy, it might take a few seconds for a policy tip to appear.</span></span>

### <a name="policy-evaluation-in-microsoft-teams"></a><span data-ttu-id="cc427-406">Microsoft Teams 中的原則評估</span><span class="sxs-lookup"><span data-stu-id="cc427-406">Policy evaluation in Microsoft Teams</span></span>
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

<span data-ttu-id="cc427-407">當您建立 DLP 原則，其中包含 Microsoft Teams 作為位置時，原則會從 Office 365 安全性與合規性中心同步到使用者帳戶與 Microsoft Teams 頻道和聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="cc427-407">When you create a DLP policy that includes Microsoft Teams as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to user accounts and Microsoft Teams channels and chat messages.</span></span> <span data-ttu-id="cc427-408">根據 DLP 原則的設定方式，當有人嘗試在 Microsoft Teams 聊天或頻道訊息中共用敏感性資訊時，可以封鎖或撤銷訊息。</span><span class="sxs-lookup"><span data-stu-id="cc427-408">Depending on how DLP policies are configured, when someone attempts to share sensitive information in a Microsoft Teams chat or channel message, the message can be blocked or revoked.</span></span> <span data-ttu-id="cc427-409">此外，若文件包含敏感性資訊且與來賓 (外部使用者) 共用，則不會對這些使用者開放。</span><span class="sxs-lookup"><span data-stu-id="cc427-409">And, documents that contain sensitive information and that are shared with guests (external users) won't open for those users.</span></span> <span data-ttu-id="cc427-410">若要深入了解，請參閱[資料外洩防護和 Microsoft Teams](dlp-microsoft-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="cc427-410">To learn more, see [Data loss prevention and Microsoft Teams](dlp-microsoft-teams.md).</span></span>
 
## <a name="permissions"></a><span data-ttu-id="cc427-411">權限</span><span class="sxs-lookup"><span data-stu-id="cc427-411">Permissions</span></span>

<span data-ttu-id="cc427-412">您的合規性小組中將建立 DLP 原則的成員必須具備安全性與合規性中心的權限。</span><span class="sxs-lookup"><span data-stu-id="cc427-412">Members of your compliance team who will create DLP policies need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="cc427-413">根據預設，您的租用戶系統管理員具備安全性與合規性中心的存取權，且能夠將權限授與法務人員和其他人員，而不必將租用戶系統管理員的所有權限授與他們。若要這樣做，建議您：</span><span class="sxs-lookup"><span data-stu-id="cc427-413">By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="cc427-414">在 Microsoft 365 中建立一個群組，並將法務人員新增至此群組。</span><span class="sxs-lookup"><span data-stu-id="cc427-414">Create a group in Microsoft 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="cc427-415">在安全性與合規性中心的 **[權限]** 頁面上建立角色群組。</span><span class="sxs-lookup"><span data-stu-id="cc427-415">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 

3. <span data-ttu-id="cc427-416">建立角色群組時，請使用 [選擇角色] 區段，將下列角色新增至角色群組: [DLP 合規性管理]。</span><span class="sxs-lookup"><span data-stu-id="cc427-416">While creating the role group, use the **Choose Roles** section to add the following role to the Role Group: **DLP Compliance Management**.</span></span>
    
4. <span data-ttu-id="cc427-417">使用 [選擇成員] 區段，將您建立的 Microsoft 365 群組新增至角色群組。</span><span class="sxs-lookup"><span data-stu-id="cc427-417">Use the **Choose Members** section to add the Microsoft 365 group you created before to the role group.</span></span>

<span data-ttu-id="cc427-418">您也可以透過授予 [僅限檢視 DLP 合規性管理] 角色，來建立擁有 DLP 原則和 DLP 報告的僅限檢視權限角色群組。</span><span class="sxs-lookup"><span data-stu-id="cc427-418">You can also create a role group with view-only privileges to the DLP policies and DLP reports by granting the **View-Only DLP Compliance Management** role.</span></span>

<span data-ttu-id="cc427-419">如需詳細資訊，請參閱[授與使用者存取 Office 365 合規性中心的權限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="cc427-419">For more information, see [Give users access to the Office 365 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="cc427-p162">需要這些權限才能建立及套用 DLP 原則。原則強制執行不需要內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="cc427-p162">These permissions are required only to create and apply a DLP policy. Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="cc427-422">尋找 DLP Cmdlet</span><span class="sxs-lookup"><span data-stu-id="cc427-422">Find the DLP cmdlets</span></span>

<span data-ttu-id="cc427-423">若要對安全性與合規性中心使用大部分 Cmdlet，您必須：</span><span class="sxs-lookup"><span data-stu-id="cc427-423">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. <span data-ttu-id="cc427-424">[使用遠端 PowerShell 連線到 Office 365 安全性與合規性中心](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="cc427-424">[Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
    
2. <span data-ttu-id="cc427-425">使用任何 [policy-and-compliance-dlp Cmdlet](/powershell/module/exchange/export-dlppolicycollection)。</span><span class="sxs-lookup"><span data-stu-id="cc427-425">Use any of these [policy-and-compliance-dlp cmdlets](/powershell/module/exchange/export-dlppolicycollection).</span></span>
    
<span data-ttu-id="cc427-426">不過，DLP 報告需要從整個 Microsoft 365 擷取資料，包含 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="cc427-426">However, DLP reports need pull data from across Microsoft 365, including Exchange Online.</span></span> <span data-ttu-id="cc427-427">有鑑於此，**DLP 報告的 Cmdlet 可在 Exchange Online PowerShell 中使用，但安全性與合規性中心 PowerShell 則不行**。</span><span class="sxs-lookup"><span data-stu-id="cc427-427">For this reason, **the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell**.</span></span> <span data-ttu-id="cc427-428">因此，若要為 DLP 報告使用 Cmdlet，您需要︰</span><span class="sxs-lookup"><span data-stu-id="cc427-428">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. <span data-ttu-id="cc427-429">[使用遠端 PowerShell 連線到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="cc427-429">[Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="cc427-430">為 DLP 報告使用下列任何 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="cc427-430">Use any of these cmdlets for the DLP reports:</span></span>
    
    - [<span data-ttu-id="cc427-431">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="cc427-431">Get-DlpDetectionsReport</span></span>](/powershell/module/exchange/Get-DlpDetectionsReport)

    - [<span data-ttu-id="cc427-432">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="cc427-432">Get-DlpDetailReport</span></span>](/powershell/module/exchange/Get-DlpDetailReport)
    
## <a name="more-information"></a><span data-ttu-id="cc427-433">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="cc427-433">More information</span></span>

- [<span data-ttu-id="cc427-434">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="cc427-434">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="cc427-435">傳送通知並顯示 DLP 原則的原則秘訣</span><span class="sxs-lookup"><span data-stu-id="cc427-435">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="cc427-436">建立 DLP 原則來保護具有 FCI 或其他屬性的文件</span><span class="sxs-lookup"><span data-stu-id="cc427-436">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="cc427-437">DLP 原則範本包含哪些內容</span><span class="sxs-lookup"><span data-stu-id="cc427-437">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="cc427-438">敏感性資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="cc427-438">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
    
- [<span data-ttu-id="cc427-439">DLP 功能所尋找的項目</span><span class="sxs-lookup"><span data-stu-id="cc427-439">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="cc427-440">建立自訂的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="cc427-440">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
