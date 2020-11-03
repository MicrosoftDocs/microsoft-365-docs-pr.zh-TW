---
title: 使用 Microsoft 365 部署資料隱私權法規的資訊保護
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: ''
description: 設定安全性和服務基礎結構，以保護您的資訊並遵守資料隱私權規定。
ms.openlocfilehash: 9af0a113d9b0eb2cbca07fdf457cd8bb7db3e094
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842293"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="21420-103">使用 Microsoft 365 部署資料隱私權法規的資訊保護</span><span class="sxs-lookup"><span data-stu-id="21420-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="21420-104">您的組織可能會受到區域資料隱私權法規的制約，需要您保護、管理及提供對您的 IT 基礎結構（包括內部部署和雲端）中儲存的個人資訊的權利及控制。</span><span class="sxs-lookup"><span data-stu-id="21420-104">Your organization may be subject to regional data privacy regulations that require you to protect, manage, and provide rights and control over personal information stored in your IT infrastructure, including both on-premises and in the cloud.</span></span> <span data-ttu-id="21420-105">資料隱私權規定的最佳範例是歐盟的一般資料保護法規 (GDPR) 。</span><span class="sxs-lookup"><span data-stu-id="21420-105">The best example of a data privacy regulation is the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="21420-106">無法遵守資料隱私權規定可能會造成大量罰款。</span><span class="sxs-lookup"><span data-stu-id="21420-106">Failure to comply with data privacy regulations can result in substantial fines.</span></span>

<span data-ttu-id="21420-107">365 Microsoft 團隊中的資料類型範例包括 Microsoft 團隊、Exchange 中的電子郵件，以及 SharePoint 和 OneDrive 中的檔案。</span><span class="sxs-lookup"><span data-stu-id="21420-107">Examples of the types of data in Microsoft 365 include chat sessions in Microsoft Teams, emails in Exchange, and files in SharePoint and OneDrive.</span></span> <span data-ttu-id="21420-108">此解決方案提供有關如何評估風險及識別資訊、保護、管理及回應資料隱私權事件，以供 Microsoft 365 服務中儲存的個人資料（受限於資料隱私權法規）的指導。</span><span class="sxs-lookup"><span data-stu-id="21420-108">This solution provides guidance on how to assess risks and identify information, protect, govern, and respond to data privacy incidents for personal data stored in Microsoft 365 services that is subject to data privacy regulations.</span></span>

![何謂資料隱私權法規的資訊保護](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png)

<span data-ttu-id="21420-110">其他資訊也會提供使用 Microsoft 365 身分識別、裝置和威脅防護控制的資料隱私權需求。</span><span class="sxs-lookup"><span data-stu-id="21420-110">Additional information is also provided on the use of Microsoft 365 identity, device, and threat protection controls for your data privacy needs.</span></span> 

<span data-ttu-id="21420-111">若要符合保護資訊以符合資料隱私權規定的準則，請使用下列 Microsoft 365 功能。</span><span class="sxs-lookup"><span data-stu-id="21420-111">To meet the criteria for protecting information for compliance with data privacy regulations, use these Microsoft 365 capabilities and features.</span></span>

| <span data-ttu-id="21420-112">功能</span><span class="sxs-lookup"><span data-stu-id="21420-112">Capability or feature</span></span> | <span data-ttu-id="21420-113">描述</span><span class="sxs-lookup"><span data-stu-id="21420-113">Description</span></span> | <span data-ttu-id="21420-114">授權</span><span class="sxs-lookup"><span data-stu-id="21420-114">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="21420-115">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="21420-115">Compliance Manager</span></span> | <span data-ttu-id="21420-116">管理法規遵從性活動、取得目前的規範設定的整體分數，以及在 Microsoft 365 規範中心的此工作流程型風險評估工具中尋找改進的建議。</span><span class="sxs-lookup"><span data-stu-id="21420-116">Manage regulatory compliance activities, get an overall score of your current compliance configuration, and find recommendations for improvement in this workflow-based risk assessment tool in the Microsoft 365 compliance center.</span></span> | <span data-ttu-id="21420-117">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="21420-117">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="21420-118">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="21420-118">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="21420-119">保護您的 Microsoft 365 應用程式和資料不受攻擊，例如電子郵件訊息、Office 文件和共同作業工具。</span><span class="sxs-lookup"><span data-stu-id="21420-119">Protect your Microsoft 365 apps and data—such as email messages, Office documents, and collaboration tools—from attack.</span></span> | <span data-ttu-id="21420-120">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="21420-120">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="21420-121">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="21420-121">Sensitivity labels</span></span> | <span data-ttu-id="21420-122">在電子郵件、文件或網站上套用具有不同保護層級的標籤，可以在不影響使用者工作效率和共同作業能力的情況下對組織的資料進行分類和保護。</span><span class="sxs-lookup"><span data-stu-id="21420-122">Classify and protect your organization's data without hindering the productivity of users and their ability to collaborate by placing labels with various levels of protection on email, files, or sites.</span></span> | <span data-ttu-id="21420-123">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="21420-123">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="21420-124">資料外洩防護 (DLP)</span><span class="sxs-lookup"><span data-stu-id="21420-124">Data Loss Protection (DLP)</span></span> | <span data-ttu-id="21420-125">偵測、警告，並封鎖風險、不慎或不當的共用，例如共用包含個人資訊的資料 (內部和外部)。</span><span class="sxs-lookup"><span data-stu-id="21420-125">Detect, warn, and block risky, inadvertent, or inappropriate sharing, such as sharing of data containing personal information, both internally and externally.</span></span> | <span data-ttu-id="21420-126">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="21420-126">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="21420-127">資料保留標籤和原則</span><span class="sxs-lookup"><span data-stu-id="21420-127">Data retention labels and policies</span></span> | <span data-ttu-id="21420-128">實施資訊控管控制，例如資料的保留時間以及對客戶個人資料儲存的要求，以符合組織的原則或資料法規。</span><span class="sxs-lookup"><span data-stu-id="21420-128">Implement information governance controls, such as how long to keep data and requirements on the storage of personal data on customers, to comply with your organization's policies or data regulations.</span></span> | <span data-ttu-id="21420-129">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="21420-129">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="21420-130">電子郵件加密</span><span class="sxs-lookup"><span data-stu-id="21420-130">Email encryption</span></span> | <span data-ttu-id="21420-131">在組織內外的人員之間傳送和接收加密的電子郵件訊息，包含管制資料，例如客戶的個人資料。</span><span class="sxs-lookup"><span data-stu-id="21420-131">Send and receive encrypted email messages between people inside and outside your organization that contains regulated data, such as personal data on customers.</span></span> | <span data-ttu-id="21420-132">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="21420-132">Microsoft 365 E3 and E5</span></span> |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a><span data-ttu-id="21420-133">此解決方案中指導方針的組織</span><span class="sxs-lookup"><span data-stu-id="21420-133">Organization of the guidance in this solution</span></span>

<span data-ttu-id="21420-134">為了協助您瞭解可供您識別、管理、控制及監視個人資料是否受一或多項隱私權相關的法規制約的 Microsoft 365 工具，本指南會組織成幾節。</span><span class="sxs-lookup"><span data-stu-id="21420-134">To help you understand the Microsoft 365 tools available to identify, manage, control, and monitor personal data subject to one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![針對資料隱私權規定實施資訊保護的步驟](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

<span data-ttu-id="21420-136">每個章節都對應此方案中的個別文章。</span><span class="sxs-lookup"><span data-stu-id="21420-136">Each of these sections correspond to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="21420-137">如果您已熟悉資料隱私權的義務，並正針對現有的計畫執行，您可能想要將重點放在預防、保護、保留及調查指導方針上。</span><span class="sxs-lookup"><span data-stu-id="21420-137">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="21420-138">遵循此指導方針不一定會使您符合任何資料隱私權規定，尤其是考慮功能環境以外的必要步驟數目。</span><span class="sxs-lookup"><span data-stu-id="21420-138">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="21420-139">您負責確定法規遵從性，並向您的法律和合規性小組請教，或從協力廠商尋求規範的指導方針和建議。</span><span class="sxs-lookup"><span data-stu-id="21420-139">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="21420-140">規劃：評估資料隱私權風險及識別敏感專案</span><span class="sxs-lookup"><span data-stu-id="21420-140">Plan: Assess data privacy risks and identify sensitive items</span></span>

<span data-ttu-id="21420-141">評估貴組織所需的資料隱私權規定和風險，是開始實施增強功能（包括透過 Microsoft 365 設定可實現）的重要第一步。</span><span class="sxs-lookup"><span data-stu-id="21420-141">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including those achievable through Microsoft 365 configuration.</span></span> <span data-ttu-id="21420-142">這可能包括您的組織需要遵守之監管控制的整體準備工作或特定機密資訊類型的識別，以及在 Microsoft 365 環境中的出現。</span><span class="sxs-lookup"><span data-stu-id="21420-142">This may include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with, as well as the occurrence of them in your Microsoft 365 environment.</span></span>

<span data-ttu-id="21420-143">如需詳細資訊，請參閱 [評估資料隱私權風險及識別敏感專案](information-protection-deploy-assess.md)。</span><span class="sxs-lookup"><span data-stu-id="21420-143">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a><span data-ttu-id="21420-144">追蹤：執行風險評估，並檢查您的合規性分數</span><span class="sxs-lookup"><span data-stu-id="21420-144">Track: Run risk assessments and check your compliance score</span></span>

<span data-ttu-id="21420-145">合規性管理員（適用于 Microsoft 365 規範中心）提供了內建的功能，可用於追蹤及管理整體的改善動作，以及與您套用至多個資料隱私權法規相關的功能。</span><span class="sxs-lookup"><span data-stu-id="21420-145">Compliance Manager, available in the Microsoft 365 compliance center, provides you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations that apply to you.</span></span>

<span data-ttu-id="21420-146">利用每項法規特有的綜合評估範本，您可以在其中追蹤所選取之每個評估範本的動作專案，以及查看特定的規章控制，以及將它們與特定動作相關聯。</span><span class="sxs-lookup"><span data-stu-id="21420-146">Leverage built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="21420-147">如需詳細資訊，請參閱 [Use 合規性管理員管理改進動作](information-protection-deploy-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="21420-147">For more information, see [Use Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-protect-personal-data"></a><span data-ttu-id="21420-148">防止：保護個人資料</span><span class="sxs-lookup"><span data-stu-id="21420-148">Prevent: Protect personal data</span></span>

<span data-ttu-id="21420-149">Microsoft 365 提供許多身分識別、裝置和威脅防護功能，可讓您用來協助遵守資料隱私權法規合規性。</span><span class="sxs-lookup"><span data-stu-id="21420-149">Microsoft 365 provides a number of identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="21420-150">如需詳細資訊，請參閱 [使用身分識別、裝置和威脅防護以取得資料隱私權規定](information-protection-deploy-identity-device-threat.md)。</span><span class="sxs-lookup"><span data-stu-id="21420-150">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="21420-151">本文簡短說明這些方面的資料隱私權法規一般會通話的內容，並提供相關 Microsoft 365 解決方案的清單，並提供詳細資訊的連結，可協助您處理任何執行需求。</span><span class="sxs-lookup"><span data-stu-id="21420-151">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="21420-152">保護受資料隱私權法規制約的資訊</span><span class="sxs-lookup"><span data-stu-id="21420-152">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="21420-153">資料隱私權規定是指可在您的環境中使用的許多個人資訊保護控制項，包含超過40保護 GDPR 的範例集合中的四個數據隱私權規定，LGPD 法案 Act (CCPA) 、HIPAA-高科技 (美國衛生保健隱私權法案) 及巴西資料保護法案 () 。</span><span class="sxs-lookup"><span data-stu-id="21420-153">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than forty Protect Information controls across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="21420-154">如需詳細資訊，請參閱 [保護您組織中的資料隱私權法規的資訊](information-protection-deploy-protect-information.md)。</span><span class="sxs-lookup"><span data-stu-id="21420-154">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="21420-155">本文將說明可用於為組織中的資料保密的資訊保護需求提供主要控制項架構。</span><span class="sxs-lookup"><span data-stu-id="21420-155">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="21420-156">保留：管理受資料隱私權法規制約的資訊</span><span class="sxs-lookup"><span data-stu-id="21420-156">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="21420-157">針對您的環境可採用的個人資訊控管，資料隱私權法規的呼叫，包括 GDPR、CCPA、HIPAA-高科技的範例，以及 LGPD 的四個數據隱私權規定中的超過二十五個控制措施。</span><span class="sxs-lookup"><span data-stu-id="21420-157">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than twenty-four controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="21420-158">如需詳細資訊，請參閱 [管理組織中的資料隱私權規定所遵循的資訊](information-protection-deploy-govern.md)。</span><span class="sxs-lookup"><span data-stu-id="21420-158">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="21420-159">在資訊控管（如惡意保留、刪除及封存）上可能會有不明確的資料隱私權規定 &mdash; ， &mdash; 本文將展示主要控制項架構，您可以針對組織中的資料隱私權使用位址資訊管理需求。</span><span class="sxs-lookup"><span data-stu-id="21420-159">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a><span data-ttu-id="21420-160">調查：監控、調查資料隱私權事件，並作出回應</span><span class="sxs-lookup"><span data-stu-id="21420-160">Investigate: Monitor, investigate, and respond to data privacy incidents</span></span>

<span data-ttu-id="21420-161">在您 operationalize 相關功能時，有一些 Microsoft 365 功能可協助您監視、調查組織中的資料隱私權事件，並加以回應。</span><span class="sxs-lookup"><span data-stu-id="21420-161">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="21420-162">針對上述各項，具有程式、程式及其他檔，都很重要，都是示範規章主體的合規性。</span><span class="sxs-lookup"><span data-stu-id="21420-162">Having processes, procedures, and other documentation for each of these can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="21420-163">如需詳細資訊，請參閱 [監視並回應組織中的資料隱私權事件](information-protection-deploy-monitor-respond.md)。</span><span class="sxs-lookup"><span data-stu-id="21420-163">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
