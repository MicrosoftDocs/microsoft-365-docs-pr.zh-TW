---
title: 步驟 3：為遠端工作者部署安全性與合規性
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: 使用 Microsoft 365 安全性與合規性服務，以保護遠端工作者的應用程式、資料和裝置。
ms.openlocfilehash: 5ba60a04cf6717f8f9261ed72336445c8d7876bc
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127071"
---
# <a name="step-3-deploy-security-and-compliance-for-remote-workers"></a><span data-ttu-id="3dd28-103">步驟 3：為遠端工作者部署安全性與合規性</span><span class="sxs-lookup"><span data-stu-id="3dd28-103">Step 3: Deploy security and compliance for remote workers</span></span>

<span data-ttu-id="3dd28-104">對於從未，或很少進辦公室的某些遠端工作者來說，安全性和合規性是整體解決方案的重要組成部分。</span><span class="sxs-lookup"><span data-stu-id="3dd28-104">For remote workers, some of whom never go into the office or who go infrequently, security and compliance are an important part of the overall solution.</span></span> <span data-ttu-id="3dd28-105">他們所有的通訊都會透過網際網路進行，而不是局限於組織內部網路。</span><span class="sxs-lookup"><span data-stu-id="3dd28-105">All of their communications occur over the Internet instead of being confined to an organizational intranet.</span></span> 

<span data-ttu-id="3dd28-106">您和您的工作者可以做一些事情來保持生產力，同時降低網路安全風險並持續遵守內部原則和資料法規。</span><span class="sxs-lookup"><span data-stu-id="3dd28-106">There are things you and your workers can do to remain productive while decreasing cybersecurity risk and maintaining compliance with your internal policies and data regulations.</span></span>

<span data-ttu-id="3dd28-107">遠端工作需要下列安全性與合規性元素：</span><span class="sxs-lookup"><span data-stu-id="3dd28-107">Remote work needs these elements of security and compliance:</span></span>

- <span data-ttu-id="3dd28-108">對遠端工作者使用的生產力應用程式 (例如 Microsoft Teams) 進行存取管制</span><span class="sxs-lookup"><span data-stu-id="3dd28-108">Controlled access to the productivity apps that remote workers use, such as Microsoft Teams</span></span> 
- <span data-ttu-id="3dd28-109">管制存取和保護遠端工作者建立和使用的資料，例如聊天交談或共用檔案</span><span class="sxs-lookup"><span data-stu-id="3dd28-109">Controlled access to and protection of the data that remote workers create and use, such as chat conversations or shared files</span></span>
- <span data-ttu-id="3dd28-110">保護 Windows 10 裝置不受惡意程式碼及其他類型的網路攻擊</span><span class="sxs-lookup"><span data-stu-id="3dd28-110">Protection of Windows 10 devices from malware and other types of cyberattacks</span></span>
- <span data-ttu-id="3dd28-111">保護電子郵件、檔案和網站，並以一致的方式標記敏感度和保護層級</span><span class="sxs-lookup"><span data-stu-id="3dd28-111">Protection of email, files, and site with consistent labeling for levels of sensitivity and protection</span></span>
- <span data-ttu-id="3dd28-112">防止資訊外洩</span><span class="sxs-lookup"><span data-stu-id="3dd28-112">Prevention of leaked information</span></span>
- <span data-ttu-id="3dd28-113">遵守地區資料法規</span><span class="sxs-lookup"><span data-stu-id="3dd28-113">Adherence to regional data regulations</span></span>

![使用這些 Microsoft 365 服務確保安全且合規](../media/empower-people-to-work-remotely/remote-workers-security-compliance-grid.png)

## <a name="security"></a><span data-ttu-id="3dd28-115">安全性</span><span class="sxs-lookup"><span data-stu-id="3dd28-115">Security</span></span>

<span data-ttu-id="3dd28-116">使用 Microsoft 365 的安全性功能來保護您的應用程式和資料。</span><span class="sxs-lookup"><span data-stu-id="3dd28-116">Protect your applications and data with these security features of Microsoft 365.</span></span>

| <span data-ttu-id="3dd28-117">功能</span><span class="sxs-lookup"><span data-stu-id="3dd28-117">Capability or feature</span></span> | <span data-ttu-id="3dd28-118">描述</span><span class="sxs-lookup"><span data-stu-id="3dd28-118">Description</span></span> | <span data-ttu-id="3dd28-119">授權</span><span class="sxs-lookup"><span data-stu-id="3dd28-119">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="3dd28-120">Office 365 進階威脅防護（ATP）</span><span class="sxs-lookup"><span data-stu-id="3dd28-120">Office 365 Advanced Threat Protection (ATP)</span></span> | <span data-ttu-id="3dd28-121">保護您的 Microsoft 365 應用程式和資料不受攻擊，例如電子郵件訊息、Office 文件和共同作業工具。</span><span class="sxs-lookup"><span data-stu-id="3dd28-121">Protect your Microsoft 365 apps and data—such as email messages, Office documents, and collaboration tools—from attack.</span></span> <br><br> <span data-ttu-id="3dd28-122">Office ATP 會收集並分析來自應用程式的訊號，以進行偵測、調查，並修正安全風險，並抵禦電子郵件訊息、連結 (Url) 和共同作業工具所帶來的惡意威脅，以保護組織。</span><span class="sxs-lookup"><span data-stu-id="3dd28-122">Office ATP collects and analyzes signals from your apps for detection, investigation, and remediation of security risks and safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> | <span data-ttu-id="3dd28-123">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="3dd28-123">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="3dd28-124">惡意程式碼防護</span><span class="sxs-lookup"><span data-stu-id="3dd28-124">Malware protection</span></span> | <span data-ttu-id="3dd28-125">‎Windows Defender 防毒軟體和 Device Guard 提供裝置型惡意程式碼保護功能。</span><span class="sxs-lookup"><span data-stu-id="3dd28-125">‎Windows Defender Antivirus and Device Guard provides device-based malware protection.</span></span> <br><br> <span data-ttu-id="3dd28-126">SharePoint‎ Online 會自動掃描檔案上傳是否有已知的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="3dd28-126">SharePoint‎ Online automatically scans file uploads for known malware.</span></span> <span data-ttu-id="3dd28-127">‎</span><span class="sxs-lookup"><span data-stu-id="3dd28-127">‎</span></span><br><br> <span data-ttu-id="3dd28-128">Exchange Online Protection‎ (‎EOP‎) 可保護雲端信箱。</span><span class="sxs-lookup"><span data-stu-id="3dd28-128">Exchange Online Protection‎ (‎EOP‎) secures cloud mailboxes.</span></span> | <span data-ttu-id="3dd28-129">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="3dd28-129">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="3dd28-130">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="3dd28-130">Microsoft Defender ATP</span></span> | <span data-ttu-id="3dd28-131">保護組織的裝置不受網路威脅和資料外洩，並偵測、調查及應變進階威脅。</span><span class="sxs-lookup"><span data-stu-id="3dd28-131">Protect your organization’s devices from cyberthreats and data breaches and detect, investigate, and respond to advanced threats.</span></span> | <span data-ttu-id="3dd28-132">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3dd28-132">Microsoft 365 E5</span></span> |
| <span data-ttu-id="3dd28-133">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3dd28-133">Cloud App Security</span></span> | <span data-ttu-id="3dd28-134">保護您的雲端服務不受攻擊，包括 Microsoft 365 和其他 SaaS 應用程式。</span><span class="sxs-lookup"><span data-stu-id="3dd28-134">Protect your cloud-based services—both Microsoft 365 and other SaaS apps— from attack.</span></span> | <span data-ttu-id="3dd28-135">Microsoft 365 E5 或個別的 Cloud App Security 授權</span><span class="sxs-lookup"><span data-stu-id="3dd28-135">Microsoft 365 E5 or individual Cloud App Security licenses</span></span> |
| <span data-ttu-id="3dd28-136">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="3dd28-136">Azure AD Identity Protection</span></span>  | <span data-ttu-id="3dd28-137">自動化身分識別風險的偵測和修正。</span><span class="sxs-lookup"><span data-stu-id="3dd28-137">Automate detection and remediation of identity-based risks.</span></span> <br><br><span data-ttu-id="3dd28-138">建立以風險為基礎的條件式存取原則，對於有風險的登入要求多重要素驗證 (MFA)。</span><span class="sxs-lookup"><span data-stu-id="3dd28-138">Create risk-based Conditional Access policies to require multi-factor authentication (MFA) for risky sign-ins.</span></span> | <span data-ttu-id="3dd28-139">Microsoft 365 E5 或 E3 (含 Azure AD Premium P2 授權)</span><span class="sxs-lookup"><span data-stu-id="3dd28-139">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> |
||||

<span data-ttu-id="3dd28-140">如需詳細資訊，請參閱[開始使用 Microsoft 365 合規性的快速工作](../compliance/compliance-quick-tasks.md) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="3dd28-140">See [Quick tasks for getting started with Microsoft 365 compliance](../compliance/compliance-quick-tasks.md) for more information.</span></span>

## <a name="compliance"></a><span data-ttu-id="3dd28-141">合規性</span><span class="sxs-lookup"><span data-stu-id="3dd28-141">Compliance</span></span>

<span data-ttu-id="3dd28-142">遵守內部原則或管理法規需求，並遵循下列 Microsoft 365 合規性功能。</span><span class="sxs-lookup"><span data-stu-id="3dd28-142">Comply with internal policies or regulatory requirements with these compliance features of Microsoft 365.</span></span>

| <span data-ttu-id="3dd28-143">功能</span><span class="sxs-lookup"><span data-stu-id="3dd28-143">Capability or feature</span></span> | <span data-ttu-id="3dd28-144">描述</span><span class="sxs-lookup"><span data-stu-id="3dd28-144">Description</span></span> | <span data-ttu-id="3dd28-145">授權</span><span class="sxs-lookup"><span data-stu-id="3dd28-145">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="3dd28-146">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="3dd28-146">Sensitivity labels</span></span> | <span data-ttu-id="3dd28-147">在電子郵件、文件或網站上套用具有不同保護層級的標籤，可以在不影響使用者工作效率和共同作業能力的情況下對組織的資料進行分類和保護。</span><span class="sxs-lookup"><span data-stu-id="3dd28-147">Classify and protect your organization's data without hindering the productivity of users and their ability to collaborate by placing labels with various levels of protection on email, files, or sites.</span></span> | <span data-ttu-id="3dd28-148">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="3dd28-148">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="3dd28-149">資料外洩防護 (DLP)</span><span class="sxs-lookup"><span data-stu-id="3dd28-149">Data Loss Protection (DLP)</span></span> | <span data-ttu-id="3dd28-150">偵測、警告，並封鎖風險、不慎或不當的共用，例如共用包含個人資訊的資料 (內部和外部)。</span><span class="sxs-lookup"><span data-stu-id="3dd28-150">Detect, warn, and block risky, inadvertent, or inappropriate sharing, such as sharing of data containing personal information, both internally and externally.</span></span> | <span data-ttu-id="3dd28-151">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="3dd28-151">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="3dd28-152">條件式存取應用程式控制</span><span class="sxs-lookup"><span data-stu-id="3dd28-152">Conditional Access App Control</span></span> | <span data-ttu-id="3dd28-153">防止敏感性資料遭下載至使用者的個人裝置。</span><span class="sxs-lookup"><span data-stu-id="3dd28-153">Prevent sensitive data from being downloaded to users' personal devices.</span></span> | <span data-ttu-id="3dd28-154">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="3dd28-154">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="3dd28-155">資料保留標籤和原則</span><span class="sxs-lookup"><span data-stu-id="3dd28-155">Data retention labels and policies</span></span> | <span data-ttu-id="3dd28-156">實施資訊控管控制，例如資料的保留時間以及對客戶個人資料儲存的要求，以符合組織的原則或資料法規。</span><span class="sxs-lookup"><span data-stu-id="3dd28-156">Implement information governance controls, such as how long to keep data and requirements on the storage of personal data on customers, to comply with your organization's policies or data regulations.</span></span> | <span data-ttu-id="3dd28-157">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="3dd28-157">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="3dd28-158">Office 郵件加密 (OME)</span><span class="sxs-lookup"><span data-stu-id="3dd28-158">Office message encryption (OME)</span></span> | <span data-ttu-id="3dd28-159">在組織內外的人員之間傳送和接收加密的電子郵件訊息，包含管制資料，例如客戶的個人資料。</span><span class="sxs-lookup"><span data-stu-id="3dd28-159">Send and receive encrypted email messages between people inside and outside your organization that contains regulated data, such as personal data on customers.</span></span> | <span data-ttu-id="3dd28-160">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="3dd28-160">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="3dd28-161">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="3dd28-161">Compliance Manager</span></span> | <span data-ttu-id="3dd28-162">使用 Microsoft 服務信任入口網站中的這個工作流程型風險評估工具來管理與 Microsoft 雲端服務相關的合規性活動。</span><span class="sxs-lookup"><span data-stu-id="3dd28-162">Manage regulatory compliance activities related to Microsoft cloud services with this workflow-based risk assessment tool in the Microsoft Service Trust Portal.</span></span> | <span data-ttu-id="3dd28-163">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="3dd28-163">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="3dd28-164">合規性分數 (預覽)</span><span class="sxs-lookup"><span data-stu-id="3dd28-164">Compliance Score (preview)</span></span> | <span data-ttu-id="3dd28-165">在 Microsoft 365 合規性中心中，查看合規性設定的整體分數以及改善建議。</span><span class="sxs-lookup"><span data-stu-id="3dd28-165">See an overall score of your current compliance configuration and recommendations for improving it in the Microsoft 365 Compliance Center.</span></span> | <span data-ttu-id="3dd28-166">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="3dd28-166">Microsoft 365 E3 and E5</span></span> |
||||

<span data-ttu-id="3dd28-167">如需詳細資訊，請參閱[安全性團隊支援在家工作的 12 個首要工作](../security/top-security-tasks-for-remote-work.md)。</span><span class="sxs-lookup"><span data-stu-id="3dd28-167">See [Top 12 tasks for security teams to support working from home](../security/top-security-tasks-for-remote-work.md) for more information.</span></span>

## <a name="results-of-step-3"></a><span data-ttu-id="3dd28-168">步驟 3 的結果</span><span class="sxs-lookup"><span data-stu-id="3dd28-168">Results of Step 3</span></span>

<span data-ttu-id="3dd28-169">針對您的遠端工作者，您已實施：</span><span class="sxs-lookup"><span data-stu-id="3dd28-169">For your remote workers, you have implemented:</span></span>

- <span data-ttu-id="3dd28-170">安全性：</span><span class="sxs-lookup"><span data-stu-id="3dd28-170">Security:</span></span>
  - <span data-ttu-id="3dd28-171">對遠端工作者用來進行通訊和共同作業的應用程式和資料進行存取管制</span><span class="sxs-lookup"><span data-stu-id="3dd28-171">Controlled access to apps and data that remote workers use to communicate and collaborate</span></span>
  - <span data-ttu-id="3dd28-172">針對雲端服務資料、電子郵件和 Windows 10 裝置進行惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="3dd28-172">Malware protection for cloud service data, email, and Windows 10 devices</span></span> 
- <span data-ttu-id="3dd28-173">合規性：</span><span class="sxs-lookup"><span data-stu-id="3dd28-173">Compliance:</span></span>
  - <span data-ttu-id="3dd28-174">以一致的方式標記敏感度和保護層級</span><span class="sxs-lookup"><span data-stu-id="3dd28-174">Consistent labeling for levels of sensitivity and protection</span></span>
  - <span data-ttu-id="3dd28-175">防止資訊洩漏的原則</span><span class="sxs-lookup"><span data-stu-id="3dd28-175">Policies to prevention information leakage</span></span>
  - <span data-ttu-id="3dd28-176">遵守地區資料法規</span><span class="sxs-lookup"><span data-stu-id="3dd28-176">Adherence to regional data regulations</span></span>

## <a name="next-step"></a><span data-ttu-id="3dd28-177">下一步</span><span class="sxs-lookup"><span data-stu-id="3dd28-177">Next step</span></span>

<span data-ttu-id="3dd28-178">繼續執行[步驟 4](empower-people-to-work-remotely-manage-endpoints.md) 以管理裝置、電腦及其他端點。</span><span class="sxs-lookup"><span data-stu-id="3dd28-178">Continue with [Step 4](empower-people-to-work-remotely-manage-endpoints.md) to manage your devices, PCs, and other endpoints.</span></span>
