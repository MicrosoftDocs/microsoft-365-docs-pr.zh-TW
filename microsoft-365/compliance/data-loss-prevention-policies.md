---
title: 資料外洩防護概觀
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/12/2019
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 透過安全性與合規性中心的資料外洩防護 (DLP) 原則，您可以識別、監控及自動保護整個 Office 365 的敏感性資訊。
ms.openlocfilehash: 940db3e32c67ee0c457bd499f63a562343f09e2b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076394"
---
# <a name="overview-of-data-loss-prevention"></a><span data-ttu-id="51b6a-103">資料外洩防護概觀</span><span class="sxs-lookup"><span data-stu-id="51b6a-103">Overview of data loss prevention policies</span></span>
<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
> [!NOTE]
> <span data-ttu-id="51b6a-104">針對已取得 Office 365 進階合規性授權的使用者，系統最近將資料外洩防護功能新增至 Microsoft Teams 聊天和頻道訊息，該功能可作為獨立選項提供，並包含在 Office 365 E5 和 Microsoft 365 E5 合規性中。</span><span class="sxs-lookup"><span data-stu-id="51b6a-104">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 Advanced Compliance, which is available as a standalone option and is included in Office 365 E5 and Microsoft 365 E5 Compliance.</span></span> <span data-ttu-id="51b6a-105">若要深入了解授權需求，請參閱 [Microsoft 365 租用戶層級服務授權指導方針](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)</span><span class="sxs-lookup"><span data-stu-id="51b6a-105">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

<span data-ttu-id="51b6a-106">為了符合企業標準和產業規定，組織必須保護敏感性資訊並防止意外洩漏。</span><span class="sxs-lookup"><span data-stu-id="51b6a-106">To comply with business standards and industry regulations, organizations need to protect sensitive information and prevent its inadvertent disclosure.</span></span> <span data-ttu-id="51b6a-107">敏感性資訊包括財務資料或個人識別資訊 (PII)，例如信用卡號碼、身分證字號或健康記錄。</span><span class="sxs-lookup"><span data-stu-id="51b6a-107">Examples of sensitive information that you might want to prevent from leaking outside your organization include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records.</span></span> <span data-ttu-id="51b6a-108">透過 Office 365 安全性與合規性中心的資料外洩防護 (DLP) 原則，您可以識別、監控及自動保護整個 Office 365 的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="51b6a-108">With data loss prevention (DLP) policies in the Office 365 Security & Compliance center, you can identify, monitor, and automatically protect sensitive information across Microsoft 365.</span></span>
  
<span data-ttu-id="51b6a-109">採用 DLP 原則，您可以：</span><span class="sxs-lookup"><span data-stu-id="51b6a-109">With a DLP policy, you can:</span></span>
  
- <span data-ttu-id="51b6a-110">**在多個位置識別敏感性資訊，例如 Exchange Online、SharePoint Online、商務用 OneDrive 及 Microsoft Teams。**</span><span class="sxs-lookup"><span data-stu-id="51b6a-110">**Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**</span></span>
    
    <span data-ttu-id="51b6a-111">例如，您可以識別任何含有商務用 OneDrive 網站所儲存信用卡號碼的文件，也可以只監視特定人員的 OneDrive 網站。</span><span class="sxs-lookup"><span data-stu-id="51b6a-111">For example, you can identify any document containing a credit card number that’s stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.</span></span>
    
- <span data-ttu-id="51b6a-112">**防止意外共用敏感性資訊**。</span><span class="sxs-lookup"><span data-stu-id="51b6a-112">**Prevent the accidental sharing of sensitive information**.</span></span> 
    
    <span data-ttu-id="51b6a-113">舉例來說，您可以使用文件或電子郵件中的健康記錄識別文件或電子郵件是否與組織外部人員共用，然後自動封鎖該文件的存取權，或是防止電子郵件傳送。</span><span class="sxs-lookup"><span data-stu-id="51b6a-113">For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.</span></span>
    
- <span data-ttu-id="51b6a-114">**監視和保護 Excel、PowerPoint 和 Word 桌面版中的敏感性資訊。**</span><span class="sxs-lookup"><span data-stu-id="51b6a-114">**Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**</span></span>
    
    <span data-ttu-id="51b6a-115">如同在 Exchange Online、SharePoint Online 和商務用 OneDrive 中，這些 Office 桌面程式也包含識別敏感性資訊及套用 DLP 原則的相同功能。</span><span class="sxs-lookup"><span data-stu-id="51b6a-115">Just like in SharePoint Online and OneDrive for Business, these Office 2016 desktop programs include the same capabilities to identify sensitive information and apply DLP policies.</span></span> <span data-ttu-id="51b6a-116">DLP 可在多人共用這些 Office 程式中的內容時提供持續監視的功能。</span><span class="sxs-lookup"><span data-stu-id="51b6a-116">DLP provides continuous monitoring when people share content in these Office 2016 programs.</span></span>
    
- <span data-ttu-id="51b6a-117">**協助使用者了解如何符合規範，而不中斷其工作流程。**</span><span class="sxs-lookup"><span data-stu-id="51b6a-117">**Help users learn how to stay compliant without interrupting their workflow.**</span></span>
    
    <span data-ttu-id="51b6a-118">您可以讓使用者了解 DLP 原則，協助他們符合規範，而不會封鎖其工作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-118">You can educate your users about DLP policies and help them remain compliant without blocking their work.</span></span> <span data-ttu-id="51b6a-119">例如，如果某個使用者嘗試共用含有敏感資訊的文件，DLP 原則可以傳送電子郵件通知給他們，同時在文件庫的內容中顯示原則提示，允許他們因為正當商務理由而覆寫原則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-119">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span> <span data-ttu-id="51b6a-120">相同原則提示也會顯示在 Outlook 網頁版、Outlook、Excel、PowerPoint 及 Word。</span><span class="sxs-lookup"><span data-stu-id="51b6a-120">The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.</span></span>
    
- <span data-ttu-id="51b6a-121">**檢視 DLP 報告以了解有哪些內容符合您的組織的 DLP 原則。**</span><span class="sxs-lookup"><span data-stu-id="51b6a-121">**View DLP reports showing content that matches your organization's DLP policies.**</span></span>
    
    <span data-ttu-id="51b6a-122">若要評估貴組織遵守 DLP 原則的情形，您可以查看符合原則或規則的數量。</span><span class="sxs-lookup"><span data-stu-id="51b6a-122">To assess how your organization is complying with a DLP policy, you can see how many matches each policy and rule has over time.</span></span> <span data-ttu-id="51b6a-123">如果 DLP 原則允許使用者覆寫原則提示並回報誤判，您也可以查看使用者回報的內容。</span><span class="sxs-lookup"><span data-stu-id="51b6a-123">If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported.</span></span>
    
<span data-ttu-id="51b6a-124">您可以在 Office 365 安全性與合規性中心的 [資料外洩防護] 頁面上建立及管理 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-124">You create and manage DLP policies on the Data loss prevention page in the Office 365 Compliance Center.</span></span>
  
![Office 365 安全性與合規性中心內的資料外洩防護頁面](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a><span data-ttu-id="51b6a-126">DLP 原則的內容</span><span class="sxs-lookup"><span data-stu-id="51b6a-126">What a DLP policy contains</span></span>

<span data-ttu-id="51b6a-127">DLP 原則包含一些基本事項：</span><span class="sxs-lookup"><span data-stu-id="51b6a-127">A DLP policy contains a few basic things:</span></span>
  
- <span data-ttu-id="51b6a-128">要保護內容的位置：**位置**，例如 Exchange Online、SharePoint Online 和商務用 OneDrive 網站，以及 Microsoft Teams 聊天和頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="51b6a-128">Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages.</span></span> 
    
- <span data-ttu-id="51b6a-129">何時及如何藉由執行強制包含下列要素的**規則**來保護內容：</span><span class="sxs-lookup"><span data-stu-id="51b6a-129">When and how to protect the content by enforcing **rules** comprised of:</span></span> 
    
  - <span data-ttu-id="51b6a-130">**條件**：內容必須符合，才會強制執行規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-130">**Conditions** the content must match before the rule is enforced.</span></span> <span data-ttu-id="51b6a-131">例如，規則可能設定為僅尋找包含身分證號碼並與組織外部人員共用的內容。</span><span class="sxs-lookup"><span data-stu-id="51b6a-131">For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization.</span></span> 
    
  - <span data-ttu-id="51b6a-132">您要原則在找到符合條件的內容時自動採取的**動作**。</span><span class="sxs-lookup"><span data-stu-id="51b6a-132">**Actions** that you want the rule to take automatically when content matching the conditions is found -- for example, block access to the document and send both the user and compliance officer an email notification.</span></span> <span data-ttu-id="51b6a-133">例如規則可能設定為封鎖文件的存取，以及傳送電子郵件通知給使用者和法務人員。</span><span class="sxs-lookup"><span data-stu-id="51b6a-133">For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification.</span></span> 
    
<span data-ttu-id="51b6a-134">您可以使用規則以符合特定的保護需求，然後使用 DLP 原則將常見保護需求分成一組，例如所有需要遵守特定法規的規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-134">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="51b6a-135">例如，您的 DLP 原則可能協助您偵測是否存在受到健康保險流通與責任法案 (HIPAA) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="51b6a-135">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA).</span></span> <span data-ttu-id="51b6a-136">此 DLP 原則可尋找任何含有此敏感性資訊並與組織外部人員共用的文件 (條件)，然後封鎖此文件的存取並傳送通知 (動作)，進而協助保護所有 SharePoint Online 網站與所有商務用 OneDrive 網站 (位置) 的 HIPAA 資料 (內容)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-136">This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that’s shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions).</span></span> <span data-ttu-id="51b6a-137">這些需求會儲存為個別規則並分組為 DLP 原則，以簡化管理和報告。</span><span class="sxs-lookup"><span data-stu-id="51b6a-137">These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![圖表顯示 DLP 原則包含位置和規則](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a><span data-ttu-id="51b6a-139">位置</span><span class="sxs-lookup"><span data-stu-id="51b6a-139">Locations</span></span>

<span data-ttu-id="51b6a-140">不論敏感性資訊是在 Exchange Online、SharePoint Online、商務用 OneDrive 或 Microsoft Teams 上，DLP 原則都可以透過 Office 365 尋找及保護該資訊。</span><span class="sxs-lookup"><span data-stu-id="51b6a-140">A DLP policy can find and protect sensitive information across Office 365, whether that information is located in Exchange Online, SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="51b6a-141">您可以選擇保護 Exchange 電子郵件、Microsoft Teams 聊天和頻道訊息，以及所有 SharePoint 或 OneDrive 文件庫中的內容，或者針對原則選取特定位置。</span><span class="sxs-lookup"><span data-stu-id="51b6a-141">You can choose to protect content in Exchange email, Microsoft Teams chats and channel messages, and all SharePoint or OneDrive libraries, or select specific locations for a policy.</span></span>
  
![DLP 原則可以套用的位置選項](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
<span data-ttu-id="51b6a-143">如果您選擇包含或排除特定 SharePoint 網站或 OneDrive 帳戶，則 DLP 原則只能包含不超過 100 項此類包含或排除。</span><span class="sxs-lookup"><span data-stu-id="51b6a-143">If you choose to include or exclude specific SharePoint sites or OneDrive accounts, a DLP policy can contain no more than 100 such inclusions and exclusions.</span></span> <span data-ttu-id="51b6a-144">雖然有這個限制，但您可以套用全組織原則或套用到整個位置的原則來超過這些限制。</span><span class="sxs-lookup"><span data-stu-id="51b6a-144">Although this limit exists, you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>
  
### <a name="rules"></a><span data-ttu-id="51b6a-145">規則</span><span class="sxs-lookup"><span data-stu-id="51b6a-145">Rules</span></span>

<span data-ttu-id="51b6a-146">用來對貴組織內容強制執行您的商務需求的，就是規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-146">Rules are what enforce your business requirements on the information stored by your organization.</span></span> <span data-ttu-id="51b6a-147">一項原則包含一或多個規則，而每個規則是由條件和動作所組成。</span><span class="sxs-lookup"><span data-stu-id="51b6a-147">A policy contains one or more rules, and each rule consists of conditions and actions.</span></span> <span data-ttu-id="51b6a-148">對每個規則而言，條件符合時，就會自動採取動作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-148">For each rule, when the conditions are met, the actions are taken automatically.</span></span> <span data-ttu-id="51b6a-149">規則會依序執行，從每個原則中最高優先順序的規則開始。</span><span class="sxs-lookup"><span data-stu-id="51b6a-149">Rules are executed sequentially, starting with the lowest order rule in each policy.</span></span>
  
<span data-ttu-id="51b6a-150">規則也會提供通知選項，以通知使用者 (透過原則提示和電子郵件通知) 和系統管理員 (透過電子郵件事件報告) 內容符合規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-150">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="51b6a-151">規則的組成元件及個別說明如下。</span><span class="sxs-lookup"><span data-stu-id="51b6a-151">Here are the components of a rule, each explained below.</span></span>
  
![DLP 規則編輯器的區段](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="51b6a-153">條件</span><span class="sxs-lookup"><span data-stu-id="51b6a-153">Conditions</span></span>

<span data-ttu-id="51b6a-154">條件很重要，因為它們會決定您要尋找的資訊類型，以及何時採取動作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-154">Conditions are important because they determine what types of information you’re looking for, and when to take an action.</span></span> <span data-ttu-id="51b6a-155">例如，您可以選擇略過包含護照號碼的內容，除非內容中包含超過 10 個這類號碼，並與組織外部人員共用。</span><span class="sxs-lookup"><span data-stu-id="51b6a-155">For example, you might choose to ignore documents containing passport numbers unless the document contains more than ten such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="51b6a-156">條件著重於**內容** (例如您要尋找哪些類型的敏感性資訊)，也著重於**內容** (例如文件與誰共用)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-156">Conditions focus on the content, such as what types of sensitive information you’re looking for, and also on the context, such as who the document is shared with.</span></span> <span data-ttu-id="51b6a-157">您可以使用條件對不同的風險層級指派不同的動作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-157">You can use conditions to assign different actions to different risk levels.</span></span> <span data-ttu-id="51b6a-158">例如，相較於與組織外部人員共用的敏感性內容，內部共用的敏感性內容風險可能較低，所需的動作也較少。</span><span class="sxs-lookup"><span data-stu-id="51b6a-158">You can use conditions to assign different actions to different risk levels -- for example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![清單會顯示可用的 DLP 條件](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="51b6a-160">目前可用的條件可以判斷：</span><span class="sxs-lookup"><span data-stu-id="51b6a-160">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="51b6a-161">內容是否包含機密資訊。</span><span class="sxs-lookup"><span data-stu-id="51b6a-161">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="51b6a-162">內容是否包含標籤。</span><span class="sxs-lookup"><span data-stu-id="51b6a-162">Content contains a label.</span></span> <span data-ttu-id="51b6a-163">如需詳細資訊，請參閱下節的[將標籤做為 DLP 原則的條件](#using-a-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-163">For more information, see [Using a label as a condition in a DLP policy](#using-a-label-as-a-condition-in-a-dlp-policy).</span></span>
    
- <span data-ttu-id="51b6a-164">內容是否與組織外部或內部人員共用。</span><span class="sxs-lookup"><span data-stu-id="51b6a-164">Content is shared with people outside or inside your organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="51b6a-165">敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="51b6a-165">Types of sensitive information</span></span>

<span data-ttu-id="51b6a-166">DLP 原則有助於保護敏感性資訊 (已定義為**敏感性資訊類型**)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-166">A DLP policy can help  protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="51b6a-167">Office 365 包含許多不同區域多種常見敏感資訊類型可供您使用，例如信用卡號碼、銀行帳戶號碼、身分證號碼和護照號碼。</span><span class="sxs-lookup"><span data-stu-id="51b6a-167">Office 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![可用的敏感性資訊類型清單](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="51b6a-169">DLP 原則在尋找信用卡號碼等敏感性資訊類型時，並不只是尋找 16 位數的數字。</span><span class="sxs-lookup"><span data-stu-id="51b6a-169">When a DLP policy looks for a sensitive information type such as a credit card number, it does not simply look for a 16-digit number.</span></span> <span data-ttu-id="51b6a-170">使用下列各項的組合可定義和偵測每種敏感資訊類型：</span><span class="sxs-lookup"><span data-stu-id="51b6a-170">Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="51b6a-171">關鍵字</span><span class="sxs-lookup"><span data-stu-id="51b6a-171">Keywords</span></span>
    
- <span data-ttu-id="51b6a-172">驗證總和檢查碼或結構的內部函數</span><span class="sxs-lookup"><span data-stu-id="51b6a-172">Internal functions to validate checksums or composition</span></span>
    
- <span data-ttu-id="51b6a-173">用以尋找模式相符項目的規則運算式評估</span><span class="sxs-lookup"><span data-stu-id="51b6a-173">Evaluation of regular expressions to find pattern matches</span></span>
    
- <span data-ttu-id="51b6a-174">其他內容檢查</span><span class="sxs-lookup"><span data-stu-id="51b6a-174">Other content examination</span></span>
    
<span data-ttu-id="51b6a-175">這有助於 DLP 偵測達到高度準確性，同時減少可能造成工作中斷的誤判數。</span><span class="sxs-lookup"><span data-stu-id="51b6a-175">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples’ work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="51b6a-176">動作</span><span class="sxs-lookup"><span data-stu-id="51b6a-176">Actions</span></span>

<span data-ttu-id="51b6a-177">當內容符合規則中的條件時，就可以套用動作以自動保護內容。</span><span class="sxs-lookup"><span data-stu-id="51b6a-177">When content matches a condition in a rule, you can apply actions to automatically protect the document or content.</span></span>
  
![可用的 DLP 動作清單](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="51b6a-179">您現在可以採取的動作如下：</span><span class="sxs-lookup"><span data-stu-id="51b6a-179">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="51b6a-180">**限制對內容的存取** 針對網站內容，這表示文件的權限除了主要網站集合系統管理員、文件擁有者以及最後修改文件的人員以外，所有人都受到限制。</span><span class="sxs-lookup"><span data-stu-id="51b6a-180">**Restrict access to the content** For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> <span data-ttu-id="51b6a-181">這些人員可以移除文件中的敏感性資訊或採取改善動作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-181">These people can remove the sensitive information from the document or take other remedial action.</span></span> <span data-ttu-id="51b6a-182">當文件符合合規性時，將會自動還原原始權限。</span><span class="sxs-lookup"><span data-stu-id="51b6a-182">When the document is in compliance, the original permissions will be automatically restored.</span></span> <span data-ttu-id="51b6a-183">當文件的存取權遭到封鎖時，文件會在網站的文件庫中顯示，帶有特殊原則提示圖示。</span><span class="sxs-lookup"><span data-stu-id="51b6a-183">When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
    ![顯示文件存取的原則提示被封鎖](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    <span data-ttu-id="51b6a-185">若是電子郵件內容，這個動作會禁止郵件傳送。</span><span class="sxs-lookup"><span data-stu-id="51b6a-185">For email content, this action blocks the message from being sent.</span></span> <span data-ttu-id="51b6a-186">取決於 DLP 規則的設定，寄件者會看到 NDR 或 (若規則使用通知) 原則提示及/或電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="51b6a-186">Depending on how the DLP rule is configured, the sender sees an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
    ![未授權收件者必須從郵件中移除的警告](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="51b6a-188">使用者通知和使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="51b6a-188">User notifications and user overrides</span></span>

<span data-ttu-id="51b6a-189">您可以使用通知和覆寫，讓使用者了解 DLP 原則，協助他們符合規範，而不會封鎖其工作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-189">You can educate your users about DLP policies and help them to remain compliant without blocking their work.</span></span> <span data-ttu-id="51b6a-190">例如，如果某個使用者嘗試共用含有敏感資訊的文件，DLP 原則可以傳送電子郵件通知給他們，同時在文件庫的內容中顯示原則提示，允許他們因為正當商務理由而覆寫原則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-190">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span>
  
![DLP 原則編輯器的使用者通知和使用者覆寫區段](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="51b6a-192">電子郵件可以通知傳送、共用或上次修改內容的人員；若是網站內容，還會另外通知主要網站集合系統管理員和文件擁有者。</span><span class="sxs-lookup"><span data-stu-id="51b6a-192">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner.</span></span> <span data-ttu-id="51b6a-193">此外，您可以從電子郵件通知中新增或移除人員。</span><span class="sxs-lookup"><span data-stu-id="51b6a-193">In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="51b6a-194">除了傳送電子郵件通知以外，使用者通知也會顯示原則提示：</span><span class="sxs-lookup"><span data-stu-id="51b6a-194">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="51b6a-195">Outlook 和 Outlook 網頁版中。</span><span class="sxs-lookup"><span data-stu-id="51b6a-195">Personal tags in Outlook and Outlook on the web</span></span>
    
- <span data-ttu-id="51b6a-196">針對 SharePoint Online 或商務用 OneDrive 網站上的文件。</span><span class="sxs-lookup"><span data-stu-id="51b6a-196">For the document on a SharePoint Online or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="51b6a-197">當文件儲存在 DLP 原則所包含的網站上時，則在 Excel、PowerPoint 及 Word 中。</span><span class="sxs-lookup"><span data-stu-id="51b6a-197">In addition to sending an email notification, this action displays a policy tip for the document on the site, and also in Excel 2016, PowerPoint 2016, and Word 2016, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="51b6a-198">電子郵件通知和原則提示會說明內容與 DLP 原則衝突的原因。</span><span class="sxs-lookup"><span data-stu-id="51b6a-198">The email notification and policy tip explain why a document conflicts with a DLP policy.</span></span> <span data-ttu-id="51b6a-199">經選擇後，電子郵件通知和原則提示將可讓使用者藉由回報為誤判或提供正當業務理由來覆寫規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-199">If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification.</span></span> <span data-ttu-id="51b6a-200">這可協助您將 DLP 原則正確的相關資訊傳達給使用者，並強制執行這些原則而不會妨礙到其正常工作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-200">This can help you educate users about your DLP policies and enforce them without preventing people from doing their work.</span></span> <span data-ttu-id="51b6a-201">覆寫及誤判的相關資訊也會記錄並回報 (請參閱以下關於 DLP 報告的資訊)，並納入事件報告中 (下一節)，以便法務人員可以定期檢閱此資訊。</span><span class="sxs-lookup"><span data-stu-id="51b6a-201">Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="51b6a-202">以下是商務用 OneDrive 帳戶中的原則提示外觀。</span><span class="sxs-lookup"><span data-stu-id="51b6a-202">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![OneDrive 帳戶中的文件原則提示](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)
  
#### <a name="incident-reports"></a><span data-ttu-id="51b6a-204">事件報告</span><span class="sxs-lookup"><span data-stu-id="51b6a-204">Incident reports</span></span>

<span data-ttu-id="51b6a-205">規則相符時，您可以將含有事件詳細資料的事件報告傳送給您的法務人員 (或是您選擇的任何人)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-205">When a rule is matched, you can send an incident report to your compliance officer with details of the event.</span></span> <span data-ttu-id="51b6a-206">這份報告包含相符項目的相關資訊、符合規則的實際內容，以及上次修改內容的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="51b6a-206">This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content.</span></span> <span data-ttu-id="51b6a-207">若是電子郵件訊息，報告則會以附件的方式提供與 DLP 原則相符的原始郵件。</span><span class="sxs-lookup"><span data-stu-id="51b6a-207">For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>
  
![設定事件報告的頁面](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="51b6a-209">群組和邏輯運算子</span><span class="sxs-lookup"><span data-stu-id="51b6a-209">Grouping and logical operators</span></span>

<span data-ttu-id="51b6a-210">DLP 原則通常都有簡單的需求，例如識別包含美國社會安全號碼的所有內容。</span><span class="sxs-lookup"><span data-stu-id="51b6a-210">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number.</span></span> <span data-ttu-id="51b6a-211">不過，在其他情況下，DLP 原則可能需要識別出粗略定義的資料。</span><span class="sxs-lookup"><span data-stu-id="51b6a-211">However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="51b6a-212">例如，若要識別受限於美國健康保險資訊流通及責任法案 (HIPAA) 的內容，您需要尋找：</span><span class="sxs-lookup"><span data-stu-id="51b6a-212">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="51b6a-213">包含特定類型之機密資訊的內容，例如美國社會安全號碼或藥物管理局 (DEA) 編號。</span><span class="sxs-lookup"><span data-stu-id="51b6a-213">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="51b6a-214">AND</span><span class="sxs-lookup"><span data-stu-id="51b6a-214">AND</span></span>
    
- <span data-ttu-id="51b6a-215">更難以識別的內容，例如病患的照護通訊或提供的醫療服務描述。</span><span class="sxs-lookup"><span data-stu-id="51b6a-215">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided.</span></span> <span data-ttu-id="51b6a-216">要識別此種內容，需要將關鍵字與極大的關鍵字清單比對，例如國際疾病分類 (ICD-9-CM 或 ICD-10-CM)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-216">Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="51b6a-217">您可以使用群組和邏輯運算子 (AND、OR) 輕鬆識別此類粗略定義的資料。</span><span class="sxs-lookup"><span data-stu-id="51b6a-217">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR).</span></span> <span data-ttu-id="51b6a-218">您在建立 DLP 原則時可以：</span><span class="sxs-lookup"><span data-stu-id="51b6a-218">When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="51b6a-219">群組機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="51b6a-219">Custom sensitive information types</span></span>
    
- <span data-ttu-id="51b6a-220">選擇群組內機密資訊類型之間和群組本身之間的邏輯運算子。</span><span class="sxs-lookup"><span data-stu-id="51b6a-220">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="51b6a-221">選擇群組內的運算子</span><span class="sxs-lookup"><span data-stu-id="51b6a-221">Choosing the operator within a group</span></span>

<span data-ttu-id="51b6a-222">在群組內，您可以選擇是只要滿足群組中的任一條件還是必須滿足所有條件，以便將內容視為符合規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-222">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![顯示群組之內運算子的群組](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="51b6a-224">新增群組</span><span class="sxs-lookup"><span data-stu-id="51b6a-224">Adding a group as a geo admin</span></span>

<span data-ttu-id="51b6a-225">您可以快速新增具有自己本身之條件和運算子的群組。</span><span class="sxs-lookup"><span data-stu-id="51b6a-225">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
![[新增群組] 按鈕](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="51b6a-227">選擇群組之間的運算子</span><span class="sxs-lookup"><span data-stu-id="51b6a-227">Choosing the operator between groups</span></span>

<span data-ttu-id="51b6a-228">在群組之間，您可以選擇只要滿足一個群組中的條件，還是必須滿足所有群組的條件，才能將內容視為符合規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-228">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="51b6a-229">例如，內建的美國 \*\*\*\* HIPAA 原則中有一個規則在群組之間使用 **AND** 運算子，以識別包含以下群組的內容：</span><span class="sxs-lookup"><span data-stu-id="51b6a-229">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="51b6a-230">來自 [PII 識別碼]\*\*\*\* 群組 (至少有一個社會安全號碼或\*\*\*\* DEA 編號)</span><span class="sxs-lookup"><span data-stu-id="51b6a-230">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="51b6a-231">**和**</span><span class="sxs-lookup"><span data-stu-id="51b6a-231">**AND**</span></span>
    
- <span data-ttu-id="51b6a-232">來自 [醫療術語]\*\*\*\* 群組 (至少有一個 ICD-9-CM 關鍵字或\*\*\*\* ICD-10-CM 關鍵字)</span><span class="sxs-lookup"><span data-stu-id="51b6a-232">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![顯示群組之間運算子的群組](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="51b6a-234">處理規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="51b6a-234">The priority by which rules are processed</span></span>

<span data-ttu-id="51b6a-235">當您在原則中建立規則時，每個規則都會根據建立時間指派優先順序，也就是說，第一個建立的規則具有第一優先順序，第二個建立的規則具有第二優先順序，依此類推。</span><span class="sxs-lookup"><span data-stu-id="51b6a-235">When you create rules in a policy, each rule is assigned a priority in the order in which it's created — meaning, the rule created first has first priority, the rule created second has second priority, and so on.</span></span> 
  
![依優先順序排列的規則](media/f7dc06bf-bc6f-485c-bcdb-606edbcf6565.png)
  
<span data-ttu-id="51b6a-237">您設定一個以上的 DLP 原則之後，可以變更一或多個原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="51b6a-237">After you have set up more than one DLP policy, you can change the priority of one or more policies.</span></span> <span data-ttu-id="51b6a-238">若要這樣做，請選取原則，選擇 [編輯原則]\*\*\*\*，然後使用 [優先順序]\*\*\*\* 清單來指定優先順序。</span><span class="sxs-lookup"><span data-stu-id="51b6a-238">To do that, select a policy, choose **Edit policy**, and use the **Priority** list to specify its priority.</span></span>

![設定原則的優先順序](media/dlp-set-policy-priority.png)

<span data-ttu-id="51b6a-240">以規則評估內容時，系統會依優先順序處理規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-240">When content is evaluated against rules, the rules are processed in priority order.</span></span> <span data-ttu-id="51b6a-241">如果內容符合多條規則，系統會依優先順序進行處理，並強制執行限制最嚴苛的動作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-241">If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced.</span></span> <span data-ttu-id="51b6a-242">舉例來說，如果內容符合下列所有規則，系統會強制執行規則 3，因為它是優先順序最高、最嚴格的規則：</span><span class="sxs-lookup"><span data-stu-id="51b6a-242">For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="51b6a-243">規則 1：只通知使用者</span><span class="sxs-lookup"><span data-stu-id="51b6a-243">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="51b6a-244">規則 2：通知使用者、限制存取且允許使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="51b6a-244">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="51b6a-245">規則 3：通知使用者、限制存取且不允許使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="51b6a-245">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="51b6a-246">規則 4：只通知使用者</span><span class="sxs-lookup"><span data-stu-id="51b6a-246">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="51b6a-247">規則 5：限制存取</span><span class="sxs-lookup"><span data-stu-id="51b6a-247">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="51b6a-248">規則 6：通知使用者、限制存取且不允許使用者覆寫</span><span class="sxs-lookup"><span data-stu-id="51b6a-248">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="51b6a-249">請注意，在此範例中雖然只強制執行了最嚴格的那項規則，但所有符合規則的項目都會記錄在稽核記錄中，並顯示於 DLP 報告。</span><span class="sxs-lookup"><span data-stu-id="51b6a-249">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="51b6a-250">關於原則提示，請注意：</span><span class="sxs-lookup"><span data-stu-id="51b6a-250">Regarding policy tips, note that:</span></span>
  
- <span data-ttu-id="51b6a-251">只會顯示最高優先順序、最嚴格規則的原則提示。</span><span class="sxs-lookup"><span data-stu-id="51b6a-251">Only the policy tip from the highest priority, most restrictive rule will be shown.</span></span> <span data-ttu-id="51b6a-252">例如，會封鎖內容存取權的規則與僅傳送通知的規則，只會顯示前者的原則提示。</span><span class="sxs-lookup"><span data-stu-id="51b6a-252">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="51b6a-253">這樣可避免使用者看到重疊顯示的原則提示。</span><span class="sxs-lookup"><span data-stu-id="51b6a-253">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="51b6a-254">如果最嚴格規則中的原則提示允許人員覆寫規則，則覆寫此規則也將會覆寫內容符合的任何其他規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-254">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="51b6a-255">調整規則以讓它們更容易或更難符合</span><span class="sxs-lookup"><span data-stu-id="51b6a-255">For more information on these options, see Tuning rules to make them easier or harder to match.</span></span>

<span data-ttu-id="51b6a-256">在建立並開啟 DLP 原則後，有時候會遇到下列問題：</span><span class="sxs-lookup"><span data-stu-id="51b6a-256">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="51b6a-257">太多**非**敏感性資訊的內容符合規則，換句話說就是太多誤判。</span><span class="sxs-lookup"><span data-stu-id="51b6a-257">Too much content that **is not** sensitive information matches the rules — in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="51b6a-258">太少內容**是**敏感性資訊符合規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-258">Too little content that **is** sensitive information matches the rules.</span></span> <span data-ttu-id="51b6a-259">換句話說，不會對敏感性資訊強制執行保護動作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-259">In other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="51b6a-260">若要解決這些問題，您可以調整規則的執行個體計數及比對精確度，使得內容更難或更易於符合規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-260">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules.</span></span> <span data-ttu-id="51b6a-261">規則中使用的每個機密資訊類型都同時具有執行個體計數及比對精確度。</span><span class="sxs-lookup"><span data-stu-id="51b6a-261">Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="51b6a-262">執行個體計數</span><span class="sxs-lookup"><span data-stu-id="51b6a-262">Instance count</span></span>

<span data-ttu-id="51b6a-263">執行個體計數指的是特定敏感性資訊類型必須在內容中出現多少次才能符合規則的次數。</span><span class="sxs-lookup"><span data-stu-id="51b6a-263">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule.</span></span> <span data-ttu-id="51b6a-264">例如，如果識別出 1 到 9 個之間的不重複美國或英國護照號碼，</span><span class="sxs-lookup"><span data-stu-id="51b6a-264">For example, content matches the rule shown below if between 1 and 9 unique U.S. or U.K.</span></span> <span data-ttu-id="51b6a-265">內容就符合以下顯示的規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-265">passport numbers are identified.</span></span>
  
<span data-ttu-id="51b6a-266">請注意，執行個體計數僅包含符合敏感性資訊類型的**不重複**關鍵字。</span><span class="sxs-lookup"><span data-stu-id="51b6a-266">Note that the instance count includes only **unique** matches for sensitive information types and keywords.</span></span> <span data-ttu-id="51b6a-267">例如，如果有一封電子郵件內出現 10 次同一組信用卡號碼，這 10 次只會採計為該信用卡號碼出現一次。</span><span class="sxs-lookup"><span data-stu-id="51b6a-267">For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span> 
  
<span data-ttu-id="51b6a-268">使用執行個體計數來調整規則的指導方針非常簡單：</span><span class="sxs-lookup"><span data-stu-id="51b6a-268">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="51b6a-269">若要讓規則更容易符合，請減少 [最小]\*\*\*\* 計數及/或增加 [最大]\*\*\*\* 計數。</span><span class="sxs-lookup"><span data-stu-id="51b6a-269">To make the rule easier to match, decrease the **min** count and/or increase the **max** count.</span></span> <span data-ttu-id="51b6a-270">您也可以刪除 [最大]\*\*\*\* 中的數值以將它設定成 [任意]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="51b6a-270">You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="51b6a-271">若要讓規則更難符合，請增加 [最小]\*\*\*\* 計數。</span><span class="sxs-lookup"><span data-stu-id="51b6a-271">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="51b6a-272">一般而言，您會在執行個體計數較低 (例如 1 到 9) 的規則中使用較不具限制性的動作，例如傳送使用者通知。</span><span class="sxs-lookup"><span data-stu-id="51b6a-272">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9).</span></span> <span data-ttu-id="51b6a-273">並在執行個體計數較高 (例如 10 到任意) 的規則中使用較多限制的動作，例如限制存取內容且不允許使用者覆寫。</span><span class="sxs-lookup"><span data-stu-id="51b6a-273">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![規則編輯器中的執行個體計數](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="51b6a-275">比對精確度</span><span class="sxs-lookup"><span data-stu-id="51b6a-275">Match accuracy</span></span>

<span data-ttu-id="51b6a-276">如上所述，機密資訊類型會由不同類型證據所形成的組合來定義與偵測。</span><span class="sxs-lookup"><span data-stu-id="51b6a-276">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence.</span></span> <span data-ttu-id="51b6a-277">一般而言，機密資訊類型會由多種這樣的組合 (稱為模式) 所定義。</span><span class="sxs-lookup"><span data-stu-id="51b6a-277">Commonly, a sensitive information type is defined by multiple such combinations, called patterns.</span></span> <span data-ttu-id="51b6a-278">證據需求較低的模式具有較低的比對精確度 (或信賴等級)，而證據需求較高的模式，其比對精確度 (或信賴等級) 則較高。</span><span class="sxs-lookup"><span data-stu-id="51b6a-278">A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level).</span></span> <span data-ttu-id="51b6a-279">若要深入了解各機密資訊類型實際使用的模式及信賴等級，請參閱[機密資訊類型尋找的目標為何](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-279">To learn more about the actual patterns and confidence levels used by every sensitive information type, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
<span data-ttu-id="51b6a-280">例如，名為 [信用卡號碼] 的機密資訊類型是由兩種模式所定義：</span><span class="sxs-lookup"><span data-stu-id="51b6a-280">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="51b6a-281">一個 65% 信賴度的模式，所需證據為：</span><span class="sxs-lookup"><span data-stu-id="51b6a-281">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="51b6a-282">一組信用卡號碼形式的數字。</span><span class="sxs-lookup"><span data-stu-id="51b6a-282">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="51b6a-283">一組通過總和檢查碼的數字。</span><span class="sxs-lookup"><span data-stu-id="51b6a-283">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="51b6a-284">一個 85% 信賴度的模式，所需證據為：</span><span class="sxs-lookup"><span data-stu-id="51b6a-284">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="51b6a-285">一組信用卡號碼形式的數字。</span><span class="sxs-lookup"><span data-stu-id="51b6a-285">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="51b6a-286">一組通過總和檢查碼的數字。</span><span class="sxs-lookup"><span data-stu-id="51b6a-286">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="51b6a-287">格式正確的關鍵字或到期日。</span><span class="sxs-lookup"><span data-stu-id="51b6a-287">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="51b6a-288">您可以在自己的規則中使用這些信賴等級 (或比對精確度)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-288">You can use these confidence levels (or match accuracy) in your rules.</span></span> <span data-ttu-id="51b6a-289">一般而言，您會在比對精確度較低的規則中使用較不具限制性的動作，例如傳送使用者通知。</span><span class="sxs-lookup"><span data-stu-id="51b6a-289">Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy.</span></span> <span data-ttu-id="51b6a-290">並在比對精確度較高的規則中使用較多限制的動作，例如限制存取內容且不允許使用者覆寫。</span><span class="sxs-lookup"><span data-stu-id="51b6a-290">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="51b6a-291">請務必記得，當在內容中辨識出特定機密資訊類型 (例如信用卡號碼) 時，系統只會傳回一個信賴等級：</span><span class="sxs-lookup"><span data-stu-id="51b6a-291">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="51b6a-292">如果所有符合項目都是來自同一個模式，那麼會傳回該模式的信賴等級。</span><span class="sxs-lookup"><span data-stu-id="51b6a-292">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="51b6a-293">如果符合的模式不只一個 (亦即有兩種不同信賴等級的相符項目)，則會傳回單一模式中最大的信賴等級。</span><span class="sxs-lookup"><span data-stu-id="51b6a-293">If there are matches for more than one pattern (that is, there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned.</span></span> <span data-ttu-id="51b6a-294">這部分就有點複雜了。</span><span class="sxs-lookup"><span data-stu-id="51b6a-294">This is the tricky part.</span></span> <span data-ttu-id="51b6a-295">以信用卡為例，如果同時符合了 65% 和 85% 的模式，該機密資訊傳回的信賴等級會大於 90%，因為證據越多代表信賴度越高。</span><span class="sxs-lookup"><span data-stu-id="51b6a-295">For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="51b6a-296">因此，如果您想要為信用卡建立兩個互斥規則，一個比對精確度為 65%，另一個為 85%，那麼比對精確度的範圍會像下面這樣。</span><span class="sxs-lookup"><span data-stu-id="51b6a-296">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this.</span></span> <span data-ttu-id="51b6a-297">第一個規則只會挑選與模式 65% 相符的項目。</span><span class="sxs-lookup"><span data-stu-id="51b6a-297">The first rule picks up only matches of the 65% pattern.</span></span> <span data-ttu-id="51b6a-298">第二個規則至少會挑選\*\*\*\* 85% 相符的項目，並可能會有\*\*\*\* 其他較低信賴度的相符項目。</span><span class="sxs-lookup"><span data-stu-id="51b6a-298">The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![兩個比對精確度範圍不同的規則](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="51b6a-300">由於這些原因，建立具有不同比對精確度之規則的指導方針為：</span><span class="sxs-lookup"><span data-stu-id="51b6a-300">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="51b6a-301">最低信賴等級的 [最小]\*\*\*\* 和 [最大]\*\*\*\* 值通常會使用同一個值 (而不是一個範圍)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-301">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="51b6a-302">最高的信賴等級通常會是一個稍高於最低信賴等級到 100 的範圍。</span><span class="sxs-lookup"><span data-stu-id="51b6a-302">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="51b6a-303">任何介於中間的信賴等級則通常是一個稍高於最低信賴等級，到稍低於最高信賴等級之間的範圍。</span><span class="sxs-lookup"><span data-stu-id="51b6a-303">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="51b6a-304">使用標籤做為 DLP 原則的條件</span><span class="sxs-lookup"><span data-stu-id="51b6a-304">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="51b6a-305">您可以建立標籤，然後：</span><span class="sxs-lookup"><span data-stu-id="51b6a-305">You can create a label and then:</span></span>
<!-- what kind of label? -->
  
- <span data-ttu-id="51b6a-306">**發佈**標籤，以便使用者查看並手動將它套用到內容。</span><span class="sxs-lookup"><span data-stu-id="51b6a-306">**Publish** it, so that end users can see and manually apply the label to content.</span></span> 
    
- <span data-ttu-id="51b6a-307">**自動將它套用**到與您所選條件相符的內容。</span><span class="sxs-lookup"><span data-stu-id="51b6a-307">**Auto-apply** it to content that matches the conditions that you choose.</span></span> 
    
<span data-ttu-id="51b6a-308">如需標籤的詳細資訊，請參閱[保留標籤概觀](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-308">For more information about labels, see [Overview of labels](labels.md).</span></span>
  
<span data-ttu-id="51b6a-309">建立標籤後，就可以將標籤做為 DLP 原則的條件。</span><span class="sxs-lookup"><span data-stu-id="51b6a-309">After you create a label, you can then use that label as a condition in your DLP policies.</span></span> <span data-ttu-id="51b6a-310">例如，您可能會因為下列理由而執行這個動作：</span><span class="sxs-lookup"><span data-stu-id="51b6a-310">For example, you might want to do this because:</span></span>
  
- <span data-ttu-id="51b6a-311">您已發佈名稱為「機密」\*\*\*\* 的標籤，因此組織的員工可以手動將此標籤套用到含有機密資訊的電子郵件和文件。</span><span class="sxs-lookup"><span data-stu-id="51b6a-311">You published a label named **Confidential**, so that people in your organization can manually apply the label to confidential email and documents.</span></span> <span data-ttu-id="51b6a-312">如果將這個標籤做為 DLP 原則的條件，就可以限制設有「機密」\*\*\*\* 標籤的內容不得與組織外部人員共用。</span><span class="sxs-lookup"><span data-stu-id="51b6a-312">By using this label as a condition in your DLP policy, you can restrict content labeled **Confidential** from being shared with people outside your organization.</span></span> 
    
- <span data-ttu-id="51b6a-313">您已為名稱為「高山房屋」\*\*\*\* 的專案建立同名的標籤，並將該標籤自動套用到包含關鍵字「高山房屋」的內容。</span><span class="sxs-lookup"><span data-stu-id="51b6a-313">You created a label named **Alpine House** for a project of that name, and then applied that label automatically to content containing the keywords "Alpine House".</span></span> <span data-ttu-id="51b6a-314">如果將這個標籤做為 DLP 原則的條件，就可以在使用者要與組織外部人員共用這項內容時，向使用者顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="51b6a-314">By using this label as a condition in your DLP policy, you can show a policy tip to end users when they're about to share this content with someone outside your organization.</span></span> 
    
- <span data-ttu-id="51b6a-315">您已發佈名稱為「稅務記錄」\*\*\*\* 的標籤，讓記錄管理員可以手動將該標籤套用到必須歸類為記錄的內容。</span><span class="sxs-lookup"><span data-stu-id="51b6a-315">You published a label named **Tax record**, so that your records manager can manually apply the label to content that needs to be classified as a record.</span></span> <span data-ttu-id="51b6a-316">如果將這個標籤做為 DLP 原則的條件，就可以找出設有這個標籤和含有 ITIN 或 SSN 等其他類型敏感性資訊的內容、針對設有「稅務記錄」\*\*\*\* 標籤的內容執行保護動作，以及從 DLP 報告和稽核記錄資料中取得詳細的 DLP 原則活動報告。</span><span class="sxs-lookup"><span data-stu-id="51b6a-316">By using this label as a condition in your DLP policy, you can look for content with this label along with other types of sensitive information such as ITINs or SSNs; apply protection actions to content labeled **Tax record**; and get detailed activity reports about the DLP policy from the DLP reports and audit log data.</span></span> 
    
- <span data-ttu-id="51b6a-317">您已將名稱為「主管階層團隊 - 機密」\*\*\*\* 的標籤發佈到一群主管的 Exchange 信箱和 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="51b6a-317">You published a label named **Executive Leadership Team - Sensitive** to the Exchange mailboxes and OneDrive accounts of a group of executives.</span></span> <span data-ttu-id="51b6a-318">如果將這個標籤做為 DLP 原則的條件，就可以針對相同內容和使用者子集來強制執行保留和保護動作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-318">By using this label as a condition in your DLP policy, you can enforce both retention and protection actions on the same subset of content and users.</span></span> 
    
<span data-ttu-id="51b6a-319">如果將標籤做為 DLP 規則的條件，就可以針對一組特定的內容、位置或使用者來選擇性強制執行保護動作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-319">By using labels as a condition in your DLP rules, can you selectively enforce protection actions on a specific set of content, locations, or users.</span></span>
  
![做為條件的標籤](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

### <a name="support-for-sensitivity-labels-is-coming"></a><span data-ttu-id="51b6a-321">敏感度標籤的支援即將推出</span><span class="sxs-lookup"><span data-stu-id="51b6a-321">Support for sensitivity labels is coming</span></span>

<span data-ttu-id="51b6a-322">您目前只能使用保留標籤做為條件，不能使用[敏感度標籤](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-322">You can currently use only a retention label as a condition, not a [sensitivity label](sensitivity-labels.md).</span></span> <span data-ttu-id="51b6a-323">我們目前正在努力支援在這個條件中使用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="51b6a-323">We're currently working on support for using a sensitivity label in this condition.</span></span>
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="51b6a-324">這項功能與其他功能的關係</span><span class="sxs-lookup"><span data-stu-id="51b6a-324">How this feature relates to other features</span></span>

<span data-ttu-id="51b6a-325">有多項功能可以套用到含有敏感性資訊的內容：</span><span class="sxs-lookup"><span data-stu-id="51b6a-325">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="51b6a-326">[保留標籤](labels.md#applying-a-retention-label-automatically-based-on-conditions)和[保留原則](retention-policies.md)都能對內容強制執行「保留」\*\*\*\* 動作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-326">A [retention label](labels.md#applying-a-retention-label-automatically-based-on-conditions) and a [retention policy](retention-policies.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="51b6a-327">DLP 原則可以對內容強制執行「保護」\*\*\*\* 動作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-327">A DLP policy can enforce **protection** actions on this content.</span></span> <span data-ttu-id="51b6a-328">您不僅要為內容設定標籤，還要讓內容滿足其他條件，DLP 原則才能強制執行這些動作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-328">And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![可對敏感性資訊執行的功能圖表](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="51b6a-330">請注意，DLP 原則的偵測功能比套用到敏感性資訊的任何標籤或保留原則來得強大。</span><span class="sxs-lookup"><span data-stu-id="51b6a-330">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information.</span></span> <span data-ttu-id="51b6a-331">DLP 原則可以針對含有敏感性資訊的內容強制執行保護動作。如果敏感性資訊已從內容中移除，就可以在系統再次掃描內容後復原相關的保護動作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-331">A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned.</span></span> <span data-ttu-id="51b6a-332">但是，如果保留原則或標籤套用到含有敏感性資訊的內容，就是一次性動件。之後即使移除敏感性資訊，也無法復原。</span><span class="sxs-lookup"><span data-stu-id="51b6a-332">But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information is removed.</span></span>
  
<span data-ttu-id="51b6a-333">如果將標籤做為 DLP 原則的條件，就可以針對設有該標籤的內容來強制執行保留和保護動作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-333">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label.</span></span> <span data-ttu-id="51b6a-334">設有標籤的內容就像是含有敏感性資訊的內容，標籤和敏感性資訊類型都是用來分類內容的屬性，您可以藉此針對內容強制執行動作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-334">You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![將標籤做為條件的 DLP 原則的圖表](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="51b6a-336">簡單設定和進階設定的比較</span><span class="sxs-lookup"><span data-stu-id="51b6a-336">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="51b6a-337">建立 DLP 原則時，您可選擇簡單或進階設定：</span><span class="sxs-lookup"><span data-stu-id="51b6a-337">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="51b6a-338">**簡單設定**可讓您輕鬆建立最常見的 DLP 原則，而不使用規則編輯器來建立或修改規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-338">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="51b6a-339">**進階設定**會使用規則編輯器，提供您 DLP 原則設定的完整控制權。</span><span class="sxs-lookup"><span data-stu-id="51b6a-339">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="51b6a-340">別擔心，除了設定方式以外，簡單設定與進階設定的運作方式完全相同，皆會強制執行由條件及動作構成的原則，唯一的差別在於使用簡單設定時，您不會看見規則編輯器。</span><span class="sxs-lookup"><span data-stu-id="51b6a-340">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions -- only with simple settings, you don't see the rule editor.</span></span> <span data-ttu-id="51b6a-341">最快的方式便是建立 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-341">It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="51b6a-342">簡單設定</span><span class="sxs-lookup"><span data-stu-id="51b6a-342">Simple MAPI settings</span></span>

<span data-ttu-id="51b6a-343">目前，最常見的 DLP 情境是建立原則以協助保護含有敏感性資訊的內容，避免組織外部的人員共用這類內容，並採取自動修正動作，如限制可存取內容的對象、傳送使用者或系統管理員通知，並稽核事件以便日後調查。</span><span class="sxs-lookup"><span data-stu-id="51b6a-343">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remediating action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation.</span></span> <span data-ttu-id="51b6a-344">採用 DLP 的人員可協助避免敏感性資訊不當外洩。</span><span class="sxs-lookup"><span data-stu-id="51b6a-344">People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="51b6a-345">若要以更簡單的方式達成這個目標，請在建立 DLP 原則時，選擇 [使用簡單設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="51b6a-345">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**.</span></span> <span data-ttu-id="51b6a-346">這些設定會提供執行最常見 DLP 原則所需的項目，讓您不必進入規則編輯器。</span><span class="sxs-lookup"><span data-stu-id="51b6a-346">These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![用於顯示簡易和進階設定的 DLP 選項](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="51b6a-348">進階設定</span><span class="sxs-lookup"><span data-stu-id="51b6a-348">Advanced settings</span></span>

<span data-ttu-id="51b6a-349">如果您要建立更多自訂 DLP 原則，您可以選擇 [使用進階設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="51b6a-349">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="51b6a-350">使用進階設定即可顯示規則編輯器。在編輯器中，您擁有所有選項的完整控制權，包括每個規則的執行個體計數及相符準確度 (信賴層級)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-350">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="51b6a-351">若要快速移至某個區段，只要按一下規則編輯器頂端瀏覽區中的項目，即可移至下方的該區段。</span><span class="sxs-lookup"><span data-stu-id="51b6a-351">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![DLP 規則編輯器的頂端瀏覽功能表](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="51b6a-353">DLP 原則範本</span><span class="sxs-lookup"><span data-stu-id="51b6a-353">DLP policy templates</span></span>

<span data-ttu-id="51b6a-354">建立 DLP 原則的第一步是選擇要保護的資訊。</span><span class="sxs-lookup"><span data-stu-id="51b6a-354">The first step in creating a DLP policy is choosing what information to protect.</span></span> <span data-ttu-id="51b6a-355">從 DLP 範本開始，您就省去從頭建立新規則集，以及釐清應依預設包含資訊類型的工作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-355">This saves you the work of building a new set of rules from scratch, and figuring out which types of information should be included by default.</span></span> <span data-ttu-id="51b6a-356">接著，您可以新增或修改這些需求以微調規則，達到組織的特定需求。</span><span class="sxs-lookup"><span data-stu-id="51b6a-356">You can then add to or modify these requirements to fine tune the rule to meet your organization’s specific requirements.</span></span>
  
<span data-ttu-id="51b6a-357">預先設定的原則範本可協助您偵測特定的敏感性資訊類型，例如 HIPAA 資料、PCI-DSS 資料、Gramm-Leach-Bliley 金融服務業現代化法案資料，或甚至是特定地區設定的個人識別資訊 (PII)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-357">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (PII).</span></span> <span data-ttu-id="51b6a-358">為了讓您能輕鬆地尋找並保護常見的敏感資訊類型，Office 365 中包含的原則範本納入了最常見的敏感資訊類型，讓您快速著手使用。</span><span class="sxs-lookup"><span data-stu-id="51b6a-358">To make it easy for you to find and protect common types of sensitive information, the policy templates included in Office 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![資料外洩防護原則的範本清單，重點在於針對美國的範本愛國者法案](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="51b6a-360">貴組織也可能設有專屬需求，在這種情況下，您可以選擇 [自訂原則]\*\*\*\* 選項從頭建立 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-360">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch.</span></span> <span data-ttu-id="51b6a-361">自訂原則中不會有任何內容，也不含預先製作的規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-361">A custom policy is empty and contains no premade rules.</span></span> 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a><span data-ttu-id="51b6a-362">以測試模式逐漸推出 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="51b6a-362">Roll out DLP policies gradually with test mode</span></span>

<span data-ttu-id="51b6a-363">建立 DLP 原則時，您應考慮逐漸推出這些原則，以便在完全強制執行之前評估其影響及測試其效果。</span><span class="sxs-lookup"><span data-stu-id="51b6a-363">When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them.</span></span> <span data-ttu-id="51b6a-364">例如，您不希望新的 DLP 原則不慎封鎖數千份完成工作所需之文件的存取。</span><span class="sxs-lookup"><span data-stu-id="51b6a-364">For example, you don’t want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.</span></span>
  
<span data-ttu-id="51b6a-365">如果您正在建立的 DLP 原則可能有重大影響，建議依照下列順序進行：</span><span class="sxs-lookup"><span data-stu-id="51b6a-365">If you’re creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
  
1. <span data-ttu-id="51b6a-366">**以測試模式啟動但不顯示原則提示**，然後使用 DLP 報告和任何事件報告來評估影響。</span><span class="sxs-lookup"><span data-stu-id="51b6a-366">**Start in test mode without Policy Tips** and then use the DLP reports to assess the impact.</span></span> <span data-ttu-id="51b6a-367">您可以使用 DLP 報告來檢視原則相符項目的號碼、位置、類型和嚴重性。</span><span class="sxs-lookup"><span data-stu-id="51b6a-367">You can use DLP reports to view the number, location, type, and severity of policy matches.</span></span> <span data-ttu-id="51b6a-368">根據結果，您可以視需要微調規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-368">Based on the results, you can fine tune the rules as needed.</span></span> <span data-ttu-id="51b6a-369">在測試模式中，DLP 原則不會影響您的組織中工作人員的生產力。</span><span class="sxs-lookup"><span data-stu-id="51b6a-369">In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
2. <span data-ttu-id="51b6a-p156">**移至測試模式並顯示通知和原則提示**，以便您開始教導使用者相關規範原則及熟悉即將套用的規則。在這個階段，您也可以要求使用者回報誤判，以便您進一步調整規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-p156">**Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span> 
    
3. <span data-ttu-id="51b6a-372">**開始完整強制執行原則**，以便套用規則中的動作，並保護內容。</span><span class="sxs-lookup"><span data-stu-id="51b6a-372">**Start full enforcement on the policies** so that the actions in the rules are applied and the content’s protected.</span></span> <span data-ttu-id="51b6a-373">繼續監視 DLP 報告以及任何事件報告或通知，確保得到您想要的結果。</span><span class="sxs-lookup"><span data-stu-id="51b6a-373">Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 
    
![使用測試模式和開啟原則的選項](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
<span data-ttu-id="51b6a-375">您可以隨時關閉 DLP 原則，關閉會影響原則中的所有規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-375">You can turn off a DLP policy at any time, which affects all rules in the policy.</span></span> <span data-ttu-id="51b6a-376">不過，也可以藉由在規則編輯器中切換每個規則的狀態來個別關閉規則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-376">However, each rule can also be turned off individually by toggling its status in the rule editor.</span></span>
  
![在原則中關閉規則的選項](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

<span data-ttu-id="51b6a-378">您也可以變更原則中多個規則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="51b6a-378">You can also change the priority of multiple rules in a policy.</span></span> <span data-ttu-id="51b6a-379">若要這樣做，請開啟原則進行編輯。</span><span class="sxs-lookup"><span data-stu-id="51b6a-379">To do that, open a policy for editing.</span></span> <span data-ttu-id="51b6a-380">在規則列中，選擇省略符號 (**...**)，然後選擇一個選項，例如 [下移]\*\*\*\* 或 [移至最後]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="51b6a-380">In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.</span></span>

![設定規則優先順序](media/dlp-set-rule-priority.png)
  
## <a name="dlp-reports"></a><span data-ttu-id="51b6a-382">DLP 報告</span><span class="sxs-lookup"><span data-stu-id="51b6a-382">DLP reports</span></span>

<span data-ttu-id="51b6a-383">建立並開啟您的 DLP 原則之後，您會想要確認原則是否達到您想要的效果並有助於您符合規範。</span><span class="sxs-lookup"><span data-stu-id="51b6a-383">After you create and turn on your DLP policies, you’ll want to verify that they’re working as you intended and helping you stay compliant.</span></span> <span data-ttu-id="51b6a-384">透過 DLP 報告，您可以快速檢視一段時間內的 DLP 原則和規則相符項目的數目，以及誤判和覆寫的數目。</span><span class="sxs-lookup"><span data-stu-id="51b6a-384">With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides.</span></span> <span data-ttu-id="51b6a-385">針對每份報告，您可以依據位置、時間範圍篩選這些相符項目，甚至將其範圍縮小到特定原則、規則或動作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-385">For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="51b6a-386">透過 DLP 報告，您將可取得深入的商業資訊，並且：</span><span class="sxs-lookup"><span data-stu-id="51b6a-386">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="51b6a-387">將重點放在特定時段，以了解尖峰和趨勢的原因。</span><span class="sxs-lookup"><span data-stu-id="51b6a-387">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="51b6a-388">探索違反貴組織規範原則的商務程序。</span><span class="sxs-lookup"><span data-stu-id="51b6a-388">Discover business processes that violate your organization’s compliance policies.</span></span>
    
- <span data-ttu-id="51b6a-389">了解 DLP 原則帶來的任何業務影響。</span><span class="sxs-lookup"><span data-stu-id="51b6a-389">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="51b6a-390">此外，您可以使用 DLP 報告來微調您所執行的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-390">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![安全性與合規性中心中的報表儀表板](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="51b6a-392">DLP 原則的運作方式</span><span class="sxs-lookup"><span data-stu-id="51b6a-392">How DLP policies work</span></span>

<span data-ttu-id="51b6a-p161">DLP 會使用深度內容分析 (不只是簡單的文字掃描) 來偵測敏感資訊。此深度內容分析會使用關鍵字比對、字典比對、規則運算式評估、內部函數和其他方法來偵測符合 DLP 原則的內容。可能只有一小部分的資料會被視為敏感資訊。DLP 原則可識別、監視和自動保護該項資料，而不會妨礙或影響到使用其餘內容的人員。</span><span class="sxs-lookup"><span data-stu-id="51b6a-p161">DLP detects sensitive information by using deep content analysis (not just a simple text scan). This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies. Potentially only a small percentage of your data is considered sensitive. A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="51b6a-397">原則會同步處理</span><span class="sxs-lookup"><span data-stu-id="51b6a-397">Policies are synced</span></span>

<span data-ttu-id="51b6a-398">在安全性與合規性中心中建立 DLP 原則之後，原則會儲存在中央原則存放區中，然後再同步處理至各種內容來源，包括：</span><span class="sxs-lookup"><span data-stu-id="51b6a-398">After you create a DLP policy in the  ComplianceAdmin, it’s stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="51b6a-399">Exchange Online，再從這裡到 Outlook 網頁版和 Outlook</span><span class="sxs-lookup"><span data-stu-id="51b6a-399">Exchange Online, and from there to Outlook on the web and Outlook</span></span>
    
- <span data-ttu-id="51b6a-400">商務用 OneDrive 網站</span><span class="sxs-lookup"><span data-stu-id="51b6a-400">OneDrive for Business sites</span></span>
    
- <span data-ttu-id="51b6a-401">SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="51b6a-401">SharePoint Online sites</span></span>
    
- <span data-ttu-id="51b6a-402">Office 桌上型電腦程式 (Excel、PowerPoint 及 Word)</span><span class="sxs-lookup"><span data-stu-id="51b6a-402">Office 2016 desktop programs (Excel 2016, PowerPoint 2016, and Word 2016)</span></span>

- <span data-ttu-id="51b6a-403">Microsoft Teams 頻道和聊天訊息</span><span class="sxs-lookup"><span data-stu-id="51b6a-403">Microsoft Teams channels and chat messages</span></span>
    
<span data-ttu-id="51b6a-404">原則同步處理至正確的位置之後，會開始評估內容並強制執行動作。</span><span class="sxs-lookup"><span data-stu-id="51b6a-404">After the policy’s synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="51b6a-405">商務用 OneDrive 和 SharePoint Online 網站中的原則評估</span><span class="sxs-lookup"><span data-stu-id="51b6a-405">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="51b6a-406">在您所有的 SharePoint Online 網站和商務用 OneDrive 網站上，文件都會持續變動 — 文件會不斷地建立、編輯、共用等等。</span><span class="sxs-lookup"><span data-stu-id="51b6a-406">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they’re continually being created, edited, shared, and so on.</span></span> <span data-ttu-id="51b6a-407">這表示文件可能會隨時違反或符合 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-407">This means documents can conflict or become compliant with a DLP policy at any time.</span></span> <span data-ttu-id="51b6a-408">例如，人員可以將不含敏感資訊文件上傳到小組網站，而後另一個人可以編輯同一份文件並在其中加入敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="51b6a-408">For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="51b6a-409">因此，DLP 原則會頻繁地在背景中檢查文件是否有原則相符項目。</span><span class="sxs-lookup"><span data-stu-id="51b6a-409">For this reason, DLP policies check documents for policy matches frequently in the background.</span></span> <span data-ttu-id="51b6a-410">您可以將此視為非同步原則評估。</span><span class="sxs-lookup"><span data-stu-id="51b6a-410">You can think of this as asynchronous policy evaluation.</span></span>
<!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a><span data-ttu-id="51b6a-411">運作方式</span><span class="sxs-lookup"><span data-stu-id="51b6a-411">How it works</span></span>
 
<span data-ttu-id="51b6a-412">當使用者新增或變更其網站中的文件時，搜尋引擎會掃描內容，使您可以在稍後搜尋。</span><span class="sxs-lookup"><span data-stu-id="51b6a-412">As people add or change documents in their sites, the search engine scans the content, so that you can search for it later.</span></span> <span data-ttu-id="51b6a-413">執行這個動作時，也會掃描內容的敏感性資訊，並檢查它是否為共用。</span><span class="sxs-lookup"><span data-stu-id="51b6a-413">While this is happening, the content's also scanned for sensitive information and to check if it's shared.</span></span> <span data-ttu-id="51b6a-414">找到的任何敏感性資訊會安全地儲存在搜尋索引中，只有合規性小組能夠存取，一般使用者無法存取。</span><span class="sxs-lookup"><span data-stu-id="51b6a-414">Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users.</span></span> <span data-ttu-id="51b6a-415">您已開啟的每個 DLP 原則會在背景執行 (以非同步方式)，頻繁地對於符合原則的任何內容檢查搜尋，並套用動作以防止意外的資料外洩。</span><span class="sxs-lookup"><span data-stu-id="51b6a-415">Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![顯示 DLP 原則如何以非同步的方式評估內容的圖表](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording --><span data-ttu-id="51b6a-p165"> 最後，文件可能會違反 DLP 原則，但也可能會符合 DLP 原則。例如，如果人員在文件中加入信用卡號碼，有可能會導致 DLP 原則自動封鎖文件的存取。但如果人員稍後移除敏感資訊，則會在下次依據原則進行評估時自動復原動作 (在此案例中為封鎖)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-p165"> Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy. For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically. But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="51b6a-420">DLP 會評估可編製索引的任何內容。</span><span class="sxs-lookup"><span data-stu-id="51b6a-420">DLP evaluates any content that can be indexed.</span></span> <span data-ttu-id="51b6a-421">若要進一步了解依預設會對哪些檔案類型進行編目，請參閱 [SharePoint Server 中的預設編目副檔名和剖析檔案類型](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-421">For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server 2013http://go.microsoft.com/fwlink/p/?LinkID=627430](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).</span></span>
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a><span data-ttu-id="51b6a-422">Exchange Online、Outlook 和 Outlook 網頁版中的原則評估</span><span class="sxs-lookup"><span data-stu-id="51b6a-422">Policy evaluation in Exchange Online, Outlook, and Outlook on the web</span></span>

<span data-ttu-id="51b6a-423">當您建立 DLP 原則，其中包含 Exchange Online 作為位置時，原則會從 Office 365 安全性與合規性中心同步到 Exchange Online，然後從 Exchange Online 同步到 Outlook 網頁版和 Outlook。</span><span class="sxs-lookup"><span data-stu-id="51b6a-423">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook.</span></span>
  
<span data-ttu-id="51b6a-424">在 Outlook 中撰寫郵件時，若使用者撰寫的內容經評估後判定違反 DLP 原則，就會看見原則提示。</span><span class="sxs-lookup"><span data-stu-id="51b6a-424">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies.</span></span> <span data-ttu-id="51b6a-425">郵件送出時，系統會在一般郵件流程中進行 DLP 原則評估，此外也會一併執行 Exchange 系統管理中心中建立的 Exchange 郵件流程規則 (也稱為傳輸規則) 和 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-425">And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange mail flow rules (also known as transport rules) and DLP policies created in the Exchange admin center.</span></span> <span data-ttu-id="51b6a-426">DLP 原則會掃描郵件和所有附件。</span><span class="sxs-lookup"><span data-stu-id="51b6a-426">DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a><span data-ttu-id="51b6a-427">Office 桌上型電腦程式中的原則評估</span><span class="sxs-lookup"><span data-stu-id="51b6a-427">Policy evaluation in the Office 2016 desktop programs</span></span>

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
<span data-ttu-id="51b6a-428">Excel、PowerPoint 和 Word 都具有與 SharePoint Online 和商務用 OneDrive 相同的功能，可識別敏感資訊並套用 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-428">Excel 2016, PowerPoint 2016, and Word 2016 include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="51b6a-429">這些 Office 程式會直接從中央原則存放區同步處理其 DLP 原則，並在有人使用從 DLP 原則所包含的網站開啟的文件時，持續根據 DLP 原則來評估內容。</span><span class="sxs-lookup"><span data-stu-id="51b6a-429">These Office 2016 programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that’s included in a DLP policy.</span></span>
  
<span data-ttu-id="51b6a-430">Office 中的 DLP 原則評估依設計並不會影響程式的效能或內容使用者的產能。</span><span class="sxs-lookup"><span data-stu-id="51b6a-430">DLP policy evaluation in Office 2016 is designed not to affect the performance of the programs or the productivity of people working on content.</span></span> <span data-ttu-id="51b6a-431">如果他們正在處理大型文件，或使用者的電腦忙碌中，可能需要幾秒鐘才會顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="51b6a-431">If they’re working on a large document, or the user’s computer is busy, it might take a few seconds for a policy tip to appear.</span></span>

### <a name="policy-evaluation-in-microsoft-teams"></a><span data-ttu-id="51b6a-432">Microsoft Teams 中的原則評估</span><span class="sxs-lookup"><span data-stu-id="51b6a-432">Policy evaluation in Microsoft Teams</span></span>
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

<span data-ttu-id="51b6a-433">當您建立 DLP 原則，其中包含 Microsoft Teams 作為位置時，原則會從 Office 365 安全性與合規性中心同步到使用者帳戶與 Microsoft Teams 頻道和聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="51b6a-433">When you create a DLP policy that includes Microsoft Teams as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to user accounts and Microsoft Teams channels and chat messages.</span></span> <span data-ttu-id="51b6a-434">根據 DLP 原則的設定方式，當有人嘗試在 Microsoft Teams 聊天或頻道訊息中共用敏感性資訊時，可以封鎖或撤銷訊息。</span><span class="sxs-lookup"><span data-stu-id="51b6a-434">Depending on how DLP policies are configured, when someone attempts to share sensitive information in a Microsoft Teams chat or channel message, the message can be blocked or revoked.</span></span> <span data-ttu-id="51b6a-435">此外，若文件包含敏感性資訊且與來賓 (外部使用者) 共用，則不會對這些使用者開放。</span><span class="sxs-lookup"><span data-stu-id="51b6a-435">And, documents that contain sensitive information and that are shared with guests (external users) won't open for those users.</span></span> <span data-ttu-id="51b6a-436">若要深入了解，請參閱[資料外洩防護和 Microsoft Teams](dlp-microsoft-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-436">To learn more, see [Data loss prevention and Microsoft Teams](dlp-microsoft-teams.md).</span></span>
 
## <a name="permissions"></a><span data-ttu-id="51b6a-437">權限</span><span class="sxs-lookup"><span data-stu-id="51b6a-437">Permissions</span></span>

<span data-ttu-id="51b6a-438">您的合規性小組中將建立 DLP 原則的成員必須具備安全性與合規性中心的權限。</span><span class="sxs-lookup"><span data-stu-id="51b6a-438">Members of your compliance team who will create DLP policies need permissions to the Compliance Center.</span></span> <span data-ttu-id="51b6a-439">根據預設，您的租用戶系統管理員具備安全性與合規性中心的存取權，且能夠將權限授與法務人員和其他人員，而不必將租用戶系統管理員的所有權限授與他們。若要這樣做，建議您：</span><span class="sxs-lookup"><span data-stu-id="51b6a-439">Members of your compliance team who will create DLP policies need permissions to the ComplianceAdmin. By default, your tenant admin will have access to this location and can give compliance officers and other people access to the ComplianceAdmin, without giving them all of the permissions of a tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="51b6a-440">在 Office 365 中建立一個群組，並將法務人員新增至此群組。</span><span class="sxs-lookup"><span data-stu-id="51b6a-440">Create a group in Office 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="51b6a-441">在安全性與合規性中心的 [權限]\*\*\*\* 頁面上建立角色群組。</span><span class="sxs-lookup"><span data-stu-id="51b6a-441">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 
    
3. <span data-ttu-id="51b6a-442">將 Office 365 群組新增至此角色群組。</span><span class="sxs-lookup"><span data-stu-id="51b6a-442">Add the Office 365 group to the role group.</span></span>
    
<span data-ttu-id="51b6a-443">如需詳細資訊，請參閱[授與使用者存取 Office 365 合規性中心的權限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="51b6a-443">For more information, see [Give users access to the Office 365 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="51b6a-444">需要這些權限才能建立及套用 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="51b6a-444">These permissions are required only to create and apply a DLP policy.</span></span> <span data-ttu-id="51b6a-445">原則強制執行不需要內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="51b6a-445">Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="51b6a-446">尋找 DLP Cmdlet</span><span class="sxs-lookup"><span data-stu-id="51b6a-446">Find the DLP cmdlets</span></span>

<span data-ttu-id="51b6a-447">若要對安全性與合規性中心使用大部分 Cmdlet，您必須：</span><span class="sxs-lookup"><span data-stu-id="51b6a-447">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="51b6a-448">使用遠端 PowerShell 連線到 Office 365 安全性與合規性中心</span><span class="sxs-lookup"><span data-stu-id="51b6a-448">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)
    
2. <span data-ttu-id="51b6a-449">使用任何 [policy-and-compliance-dlp cmdlets](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/export-dlppolicycollection?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="51b6a-449">Use any of these [policy-and-compliance-dlp cmdlets](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/export-dlppolicycollection?view=exchange-ps)</span></span>
    
<span data-ttu-id="51b6a-450">不過，DLP 報告需要從整個 Office 365 擷取資料，包含 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="51b6a-450">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="51b6a-451">有鑑於此，**DLP 報告的 Cmdlet 可在 Exchange Online PowerShell 中使用，但安全性與合規性中心 PowerShell 則不行**。</span><span class="sxs-lookup"><span data-stu-id="51b6a-451">For this reason, **the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell**.</span></span> <span data-ttu-id="51b6a-452">因此，若要為 DLP 報告使用 Cmdlet，您需要︰</span><span class="sxs-lookup"><span data-stu-id="51b6a-452">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="51b6a-453">使用遠端 PowerShell 連線到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="51b6a-453">Connect to Exchange Online using remote PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)
    
2. <span data-ttu-id="51b6a-454">為 DLP 報告使用下列任何 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="51b6a-454">Use any of these cmdlets for the DLP reports:</span></span>
    
  - [<span data-ttu-id="51b6a-455">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="51b6a-455">Get-DlpDetectionsReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetectionsReport?view=exchange-ps)
    
  - [<span data-ttu-id="51b6a-456">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="51b6a-456">Get-DlpDetailReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetailReport?view=exchange-ps)
    
## <a name="more-information"></a><span data-ttu-id="51b6a-457">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="51b6a-457">More information</span></span>

- [<span data-ttu-id="51b6a-458">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="51b6a-458">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="51b6a-459">傳送通知並顯示 DLP 原則的原則秘訣</span><span class="sxs-lookup"><span data-stu-id="51b6a-459">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="51b6a-460">建立 DLP 原則來保護具有 FCI 或其他屬性的文件</span><span class="sxs-lookup"><span data-stu-id="51b6a-460">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="51b6a-461">DLP 原則範本包含哪些內容</span><span class="sxs-lookup"><span data-stu-id="51b6a-461">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="51b6a-462">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="51b6a-462">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="51b6a-463">DLP 功能所尋找的項目</span><span class="sxs-lookup"><span data-stu-id="51b6a-463">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="51b6a-464">建立自訂的敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="51b6a-464">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    

