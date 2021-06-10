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
description: 在 Microsoft 365 中為數據隱私權法規（如 GDPR 和加州消費者隱私權法案 (CCPA) （包括 Microsoft Teams、SharePoint 和電子郵件）設定資訊保護。
ms.openlocfilehash: cae3a559c2bce39ecb02afa9be0878ff5e19ba48
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100768"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="f069c-103">使用 Microsoft 365 部署資料隱私權法規的資訊保護</span><span class="sxs-lookup"><span data-stu-id="f069c-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="f069c-104">您的組織可能會受到區域資料隱私權法規的制約，需要您保護、管理及提供對您的 IT 基礎結構（包括內部部署和雲端）中儲存的個人資訊的權利及控制。</span><span class="sxs-lookup"><span data-stu-id="f069c-104">Your organization may be subject to regional data privacy regulations that require you to protect, manage, and provide rights and control over personal information stored in your IT infrastructure, including both on-premises and in the cloud.</span></span> <span data-ttu-id="f069c-105">資料隱私權規定的最佳範例是歐盟的一般資料保護法規 (GDPR) 。</span><span class="sxs-lookup"><span data-stu-id="f069c-105">The best example of a data privacy regulation is the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="f069c-106">無法遵守資料隱私權規定可能會造成大量罰款。</span><span class="sxs-lookup"><span data-stu-id="f069c-106">Failure to comply with data privacy regulations can result in substantial fines.</span></span>

<span data-ttu-id="f069c-107">Microsoft 365 中的資料類型範例包括 Microsoft Teams 中的交談會話、Exchange 中的電子郵件，以及 SharePoint 及 OneDrive 中的檔案。</span><span class="sxs-lookup"><span data-stu-id="f069c-107">Examples of the types of data in Microsoft 365 include chat sessions in Microsoft Teams, emails in Exchange, and files in SharePoint and OneDrive.</span></span> <span data-ttu-id="f069c-108">這項解決方案提供有關如何評估風險和採取適當動作來保護 Microsoft 365 中個人資料的指導。</span><span class="sxs-lookup"><span data-stu-id="f069c-108">This solution provides guidance on how to assess risks and take appropriate action to protect personal data in Microsoft 365.</span></span> <span data-ttu-id="f069c-109">這包括識別個人資訊，讓您可以保護、管理及回應資料隱私權事件。</span><span class="sxs-lookup"><span data-stu-id="f069c-109">This includes identifying  personal information so you can protect, govern, and respond to data privacy incidents.</span></span>

![何謂資料隱私權法規的資訊保護](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png#lightbox)

<span data-ttu-id="f069c-111">其他資訊也是針對您的資料隱私權需求，使用 Microsoft 365 身分識別、裝置和威脅防護控制時所提供。</span><span class="sxs-lookup"><span data-stu-id="f069c-111">Additional information is also provided on the use of Microsoft 365 identity, device, and threat protection controls for your data privacy needs.</span></span> 

<span data-ttu-id="f069c-112">這些 Microsoft 365 的功能和功能可協助您符合保護資訊的準則。</span><span class="sxs-lookup"><span data-stu-id="f069c-112">These Microsoft 365 capabilities and features help you meet the criteria for protecting information.</span></span>

| <span data-ttu-id="f069c-113">功能</span><span class="sxs-lookup"><span data-stu-id="f069c-113">Capability or feature</span></span> | <span data-ttu-id="f069c-114">描述</span><span class="sxs-lookup"><span data-stu-id="f069c-114">Description</span></span> | <span data-ttu-id="f069c-115">授權</span><span class="sxs-lookup"><span data-stu-id="f069c-115">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="f069c-116">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="f069c-116">Compliance Manager</span></span> | <span data-ttu-id="f069c-117">管理法規遵從性活動、取得您目前的規範設定的整體分數，並尋找改進的建議。</span><span class="sxs-lookup"><span data-stu-id="f069c-117">Manage regulatory compliance activities, get an overall score of your current compliance configuration, and find recommendations for improvement.</span></span> <span data-ttu-id="f069c-118">這是 Microsoft 365 規範中心內的工作流程型風險評估工具。</span><span class="sxs-lookup"><span data-stu-id="f069c-118">This is a workflow-based risk assessment tool in the Microsoft 365 compliance center.</span></span> | <span data-ttu-id="f069c-119">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="f069c-119">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="f069c-120">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f069c-120">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="f069c-121">保護您的 Microsoft 365 應用程式和資料不受攻擊，例如電子郵件訊息、Office 文件和共同作業工具。</span><span class="sxs-lookup"><span data-stu-id="f069c-121">Protect your Microsoft 365 apps and data—such as email messages, Office documents, and collaboration tools—from attack.</span></span> | <span data-ttu-id="f069c-122">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="f069c-122">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="f069c-123">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="f069c-123">Sensitivity labels</span></span> | <span data-ttu-id="f069c-124">分類及保護貴組織的資料，而不會阻礙使用者的生產力和其共同作業的能力。</span><span class="sxs-lookup"><span data-stu-id="f069c-124">Classify and protect your organization's data without hindering the productivity of users and their ability to collaborate.</span></span> <span data-ttu-id="f069c-125">在電子郵件、檔案或網站上放置具有不同保護層級的標籤。</span><span class="sxs-lookup"><span data-stu-id="f069c-125">Place labels with various levels of protection on email, files, or sites.</span></span> | <span data-ttu-id="f069c-126">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="f069c-126">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="f069c-127">資料外洩防護 (DLP)</span><span class="sxs-lookup"><span data-stu-id="f069c-127">Data Loss Protection (DLP)</span></span> | <span data-ttu-id="f069c-128">偵測、警告和封鎖包含個人資訊（內部及外部）的危險、無意或不適當共用資料。</span><span class="sxs-lookup"><span data-stu-id="f069c-128">Detect, warn, and block risky, inadvertent, or inappropriate sharing of data containing personal information, both internally and externally.</span></span> | <span data-ttu-id="f069c-129">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="f069c-129">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="f069c-130">資料保留標籤和原則</span><span class="sxs-lookup"><span data-stu-id="f069c-130">Data retention labels and policies</span></span> | <span data-ttu-id="f069c-131">實施資訊管理控制措施。</span><span class="sxs-lookup"><span data-stu-id="f069c-131">Implement information governance controls.</span></span> <span data-ttu-id="f069c-132">這包括決定要保留資料的時間長度 (例如與客戶相關的個人資料) ，以符合組織的原則或資料法規。</span><span class="sxs-lookup"><span data-stu-id="f069c-132">These can include determining how long to keep data (such as personal data related to customers) to comply with your organization's policies or data regulations.</span></span> | <span data-ttu-id="f069c-133">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="f069c-133">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="f069c-134">電子郵件加密</span><span class="sxs-lookup"><span data-stu-id="f069c-134">Email encryption</span></span> | <span data-ttu-id="f069c-135">在組織內部和外部的人員之間傳送及接收加密的電子郵件，以保護個人資料。</span><span class="sxs-lookup"><span data-stu-id="f069c-135">Protect personal data by sending and receiving encrypted email messages between people inside and outside your organization.</span></span> | <span data-ttu-id="f069c-136">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="f069c-136">Microsoft 365 E3 and E5</span></span> |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a><span data-ttu-id="f069c-137">此解決方案中指導方針的組織</span><span class="sxs-lookup"><span data-stu-id="f069c-137">Organization of the guidance in this solution</span></span>

<span data-ttu-id="f069c-138">為了協助您瞭解可用來協助您達成一或多項隱私權相關規章的 Microsoft 365 工具，本指南已分為各節。</span><span class="sxs-lookup"><span data-stu-id="f069c-138">To help you understand the Microsoft 365 tools available to help you meet one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![針對資料隱私權規定實施資訊保護的步驟](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

<span data-ttu-id="f069c-140">這兩個區段分別對應于此方案中的個別文章。</span><span class="sxs-lookup"><span data-stu-id="f069c-140">Each of these sections corresponds to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="f069c-141">如果您已熟悉資料隱私權的義務，並正針對現有的計畫執行，您可能想要將重點放在預防、保護、保留及調查指導方針上。</span><span class="sxs-lookup"><span data-stu-id="f069c-141">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="f069c-142">遵循此指導方針不一定會使您符合任何資料隱私權規定，尤其是考慮功能環境以外的必要步驟數目。</span><span class="sxs-lookup"><span data-stu-id="f069c-142">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="f069c-143">您負責確定法規遵從性，並向您的法律和合規性小組請教，或從協力廠商尋求規範的指導方針和建議。</span><span class="sxs-lookup"><span data-stu-id="f069c-143">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="f069c-144">規劃：評估資料隱私權風險及識別敏感專案</span><span class="sxs-lookup"><span data-stu-id="f069c-144">Plan: Assess data privacy risks and identify sensitive items</span></span>

<span data-ttu-id="f069c-145">評估貴組織所需的資料隱私權規定和風險，是開始實施改進功能（包括 Microsoft 365 中的設定功能）之前必須先做的重要第一步。</span><span class="sxs-lookup"><span data-stu-id="f069c-145">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including configuring capabilities in Microsoft 365.</span></span> <span data-ttu-id="f069c-146">這項工作可以包含您的組織需要遵守監管控制規範的整體準備情況評估或特定機密資訊類型的識別。</span><span class="sxs-lookup"><span data-stu-id="f069c-146">This work can include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with.</span></span>

<span data-ttu-id="f069c-147">如需詳細資訊，請參閱 [評估資料隱私權風險及識別敏感專案](information-protection-deploy-assess.md)。</span><span class="sxs-lookup"><span data-stu-id="f069c-147">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a><span data-ttu-id="f069c-148">追蹤：執行風險評估，並檢查您的合規性分數</span><span class="sxs-lookup"><span data-stu-id="f069c-148">Track: Run risk assessments and check your compliance score</span></span>

<span data-ttu-id="f069c-149">合規性管理員可在 Microsoft 365 規範中心提供，其可讓您在整體上追蹤及管理改善動作，以及與套用至您的多個資料隱私權法規相關的功能。</span><span class="sxs-lookup"><span data-stu-id="f069c-149">Compliance Manager, available in the Microsoft 365 compliance center, provides you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations that apply to you.</span></span>

<span data-ttu-id="f069c-150">您可以使用每個法規特有的內建評估範本，您可以在其中追蹤選取的每個評估範本的動作專案，以及查看特定的規章控制項，並將其與特定動作相關聯。</span><span class="sxs-lookup"><span data-stu-id="f069c-150">You can use built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="f069c-151">如需詳細資訊，請參閱 [Use 合規性管理員管理改進動作](information-protection-deploy-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="f069c-151">For more information, see [Use Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-protect-personal-data"></a><span data-ttu-id="f069c-152">防止：保護個人資料</span><span class="sxs-lookup"><span data-stu-id="f069c-152">Prevent: Protect personal data</span></span>

<span data-ttu-id="f069c-153">Microsoft 365 提供身分識別、裝置和威脅防護功能，可讓您用來協助遵守資料隱私權法規合規性。</span><span class="sxs-lookup"><span data-stu-id="f069c-153">Microsoft 365 provides identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="f069c-154">如需詳細資訊，請參閱 [使用身分識別、裝置和威脅防護以取得資料隱私權規定](information-protection-deploy-identity-device-threat.md)。</span><span class="sxs-lookup"><span data-stu-id="f069c-154">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="f069c-155">本文將簡短說明這些方面的資料隱私權法規一般會通話的內容，並提供相關的 Microsoft 365 解決方案清單，並提供詳細資訊的連結，可協助您處理任何的執行需求。</span><span class="sxs-lookup"><span data-stu-id="f069c-155">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="f069c-156">保護受資料隱私權法規制約的資訊</span><span class="sxs-lookup"><span data-stu-id="f069c-156">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="f069c-157">資料隱私權規定是指可在您的環境中使用的許多個人資訊保護控制項，包含超過40個控制措施，以保護 GDPR 的範例集合中的四個數據隱私權規定，例如，加州消費者 Protection 法案 (CCPA) ，HIPAA-高科技 (美國衛生保健隱私權法案) ，以及巴西資料保護法案 (LGPD) 。</span><span class="sxs-lookup"><span data-stu-id="f069c-157">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than 40 controls for protecting information across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="f069c-158">如需詳細資訊，請參閱 [保護您組織中的資料隱私權法規的資訊](information-protection-deploy-protect-information.md)。</span><span class="sxs-lookup"><span data-stu-id="f069c-158">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="f069c-159">本文將說明可用於為組織中的資料保密的資訊保護需求提供主要控制項架構。</span><span class="sxs-lookup"><span data-stu-id="f069c-159">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="f069c-160">保留：管理受資料隱私權法規制約的資訊</span><span class="sxs-lookup"><span data-stu-id="f069c-160">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="f069c-161">針對您的環境可採用的個人資訊控管控制，資料隱私權法規的呼叫，包括 GDPR、CCPA、HIPAA-高科技的範例，以及 LGPD 的四種資料隱私權規定中的超過24個控制項。</span><span class="sxs-lookup"><span data-stu-id="f069c-161">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than 24 controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="f069c-162">如需詳細資訊，請參閱 [管理組織中的資料隱私權規定所遵循的資訊](information-protection-deploy-govern.md)。</span><span class="sxs-lookup"><span data-stu-id="f069c-162">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="f069c-163">在資訊控管（如惡意保留、刪除及封存）上可能會有不明確的資料隱私權規定 &mdash; ， &mdash; 本文將展示主要控制項架構，您可以針對組織中的資料隱私權使用位址資訊管理需求。</span><span class="sxs-lookup"><span data-stu-id="f069c-163">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a><span data-ttu-id="f069c-164">調查：監控、調查資料隱私權事件，並作出回應</span><span class="sxs-lookup"><span data-stu-id="f069c-164">Investigate: Monitor, investigate, and respond to data privacy incidents</span></span>

<span data-ttu-id="f069c-165">在您 operationalize 相關功能時，有一些 Microsoft 365 功能可協助您監視、調查組織中的資料隱私權事件，並加以回應。</span><span class="sxs-lookup"><span data-stu-id="f069c-165">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="f069c-166">使用這些功能的程式、程式及其他檔，都很重要，就是示範規章主體的合規性。</span><span class="sxs-lookup"><span data-stu-id="f069c-166">Having processes, procedures, and other documentation for using these features can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="f069c-167">如需詳細資訊，請參閱 [監視並回應組織中的資料隱私權事件](information-protection-deploy-monitor-respond.md)。</span><span class="sxs-lookup"><span data-stu-id="f069c-167">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
