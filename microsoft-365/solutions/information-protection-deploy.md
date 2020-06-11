---
title: 使用 Microsoft 365 部署資料隱私權法規的資訊保護
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: 設定安全性和服務基礎結構，以保護您的資訊並遵守資料隱私權規定。
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695102"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="7cd38-103">使用 Microsoft 365 部署資料隱私權法規的資訊保護</span><span class="sxs-lookup"><span data-stu-id="7cd38-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="7cd38-104">這項解決方案提供有關如何規劃及保護 Microsoft 365 服務中儲存的個人資料，以及可能遵循資料隱私權法規（如歐盟一般資料保護規定（GDPR））的指導方針。</span><span class="sxs-lookup"><span data-stu-id="7cd38-104">This solution provides guidance on how to plan for and protect personal data that is stored in Microsoft 365 services and potentially subject to data privacy regulations such as the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="7cd38-105">此解決方案著重于適用的 Microsoft 資訊保護和符合性功能、Microsoft 規範分數和評估工具，以協助您瞭解資料。</span><span class="sxs-lookup"><span data-stu-id="7cd38-105">This solution focuses on applicable Microsoft information protection and compliance features, Microsoft Compliance Score, and assessment tools to help you know your data.</span></span> 
 
<span data-ttu-id="7cd38-106">其他資訊也會提供使用 Microsoft 身分識別、裝置和威脅防護控制的資料隱私權需求，以及資料事件探索和回應工具。</span><span class="sxs-lookup"><span data-stu-id="7cd38-106">Additional information is also provided on the use of Microsoft identity, device, and threat protection controls for your data privacy needs, as well as data incident discovery and response tools.</span></span> 

## <a name="organization-of-this-guidance-material"></a><span data-ttu-id="7cd38-107">本指南資料的組織</span><span class="sxs-lookup"><span data-stu-id="7cd38-107">Organization of this guidance material</span></span>

<span data-ttu-id="7cd38-108">為了協助您瞭解可供您識別、管理、控制及監視個人資料是否受一或多項隱私權相關的法規制約的 Microsoft 365 工具，本指南會組織成幾節。</span><span class="sxs-lookup"><span data-stu-id="7cd38-108">To help you understand the Microsoft 365 tools available to identify, manage, control, and monitor personal data subject to one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![部署資料隱私權法規的資訊保護](../media/information-protection-deploy/information-protection-deploy-grid.png)

<span data-ttu-id="7cd38-110">每個章節都對應此方案中的個別文章。</span><span class="sxs-lookup"><span data-stu-id="7cd38-110">Each of these sections correspond to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="7cd38-111">如果您已熟悉資料隱私權的義務，並正針對現有的計畫執行，您可能想要將重點放在預防、保護、保留及調查指導方針上。</span><span class="sxs-lookup"><span data-stu-id="7cd38-111">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="7cd38-112">遵循此指導方針不一定會使您符合任何資料隱私權規定，尤其是考慮功能環境以外的必要步驟數目。</span><span class="sxs-lookup"><span data-stu-id="7cd38-112">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="7cd38-113">您負責確定法規遵從性，並向您的法律和合規性小組請教，或從協力廠商尋求規範的指導方針和建議。</span><span class="sxs-lookup"><span data-stu-id="7cd38-113">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="7cd38-114">規劃：評估資料隱私權風險及識別敏感專案</span><span class="sxs-lookup"><span data-stu-id="7cd38-114">Plan: Assess data privacy risks and identify sensitive items</span></span> 

<span data-ttu-id="7cd38-115">評估貴組織所需的資料隱私權規定和風險，是開始實施增強功能（包括透過 Microsoft 365 設定可實現）的重要第一步。</span><span class="sxs-lookup"><span data-stu-id="7cd38-115">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including those achievable through Microsoft 365 configuration.</span></span> <span data-ttu-id="7cd38-116">這可能包括您的組織需要遵守之監管控制的整體準備工作或特定機密資訊類型的識別，以及在 Microsoft 365 環境中的出現。</span><span class="sxs-lookup"><span data-stu-id="7cd38-116">This may include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with, as well as the occurrence of them in your Microsoft 365 environment.</span></span>

<span data-ttu-id="7cd38-117">如需詳細資訊，請參閱[評估資料隱私權風險及識別敏感專案](information-protection-deploy-assess.md)。</span><span class="sxs-lookup"><span data-stu-id="7cd38-117">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-use-compliance-score-and-compliance-manager"></a><span data-ttu-id="7cd38-118">追蹤：使用合規性分數和合規性管理員</span><span class="sxs-lookup"><span data-stu-id="7cd38-118">Track: Use Compliance Score and Compliance Manager</span></span> 

<span data-ttu-id="7cd38-119">合規性分數和合規性管理員提供一組整合的工具，可在 Microsoft 365 合規性系統管理中心和服務信任入口網站中使用。</span><span class="sxs-lookup"><span data-stu-id="7cd38-119">Compliance Score and Compliance Manager provide an integrated set of tools available in the Microsoft 365 Compliance admin center and Services Trust Portal.</span></span> <span data-ttu-id="7cd38-120">這些工具共同為您提供內建的功能，可以追蹤和管理整體的整體功能，以及與您所進行的多個資料隱私權法規相關的功能。</span><span class="sxs-lookup"><span data-stu-id="7cd38-120">Together, these tools provide you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations to which you are subjected.</span></span>

<span data-ttu-id="7cd38-121">這些工具也可讓您利用各項法規特有的內建評估範本，您可以在其中追蹤選取的每個評估範本的動作專案，以及查看特定的規章控制項，並將它們與特定動作相關聯。</span><span class="sxs-lookup"><span data-stu-id="7cd38-121">The tools also allow you to leverage built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="7cd38-122">如需詳細資訊，請參閱[使用合規性分數和合規性管理員管理改進動作](information-protection-deploy-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="7cd38-122">For more information, see [Use Compliance Score and Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="7cd38-123">禁止：針對資料隱私權規定使用身分識別、裝置和威脅防護</span><span class="sxs-lookup"><span data-stu-id="7cd38-123">Prevent: Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="7cd38-124">Microsoft 365 提供許多身分識別、裝置和威脅防護功能，可讓您用來協助遵守資料隱私權法規合規性。</span><span class="sxs-lookup"><span data-stu-id="7cd38-124">Microsoft 365 provides a number of identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="7cd38-125">如需詳細資訊，請參閱[使用身分識別、裝置和威脅防護以取得資料隱私權規定](information-protection-deploy-identity-device-threat.md)。</span><span class="sxs-lookup"><span data-stu-id="7cd38-125">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="7cd38-126">本文簡短說明這些方面的資料隱私權法規一般會通話的內容，並提供相關 Microsoft 365 解決方案的清單，並提供詳細資訊的連結，可協助您處理任何執行需求。</span><span class="sxs-lookup"><span data-stu-id="7cd38-126">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="7cd38-127">保護受資料隱私權法規制約的資訊</span><span class="sxs-lookup"><span data-stu-id="7cd38-127">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="7cd38-128">資料隱私權規定是指可在您的環境中使用的許多個人資訊保護控制項，包含超過40保護 GDPR 的範例集合中的四個數據隱私權規定、加州消費者保護法（美國衛生保健隱私權法案）和巴西資料保護法案（LGPD）等各項的資訊控制。</span><span class="sxs-lookup"><span data-stu-id="7cd38-128">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than forty Protect Information controls across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="7cd38-129">如需詳細資訊，請參閱[保護您組織中的資料隱私權法規的資訊](information-protection-deploy-protect-information.md)。</span><span class="sxs-lookup"><span data-stu-id="7cd38-129">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="7cd38-130">本文將說明可用於為組織中的資料保密的資訊保護需求提供主要控制項架構。</span><span class="sxs-lookup"><span data-stu-id="7cd38-130">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="7cd38-131">保留：管理受資料隱私權法規制約的資訊</span><span class="sxs-lookup"><span data-stu-id="7cd38-131">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="7cd38-132">針對您的環境可採用的個人資訊控管，資料隱私權法規的呼叫，包括 GDPR、CCPA、HIPAA-高科技的範例，以及 LGPD 的四個數據隱私權規定中的超過二十五個控制措施。</span><span class="sxs-lookup"><span data-stu-id="7cd38-132">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than twenty-four controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="7cd38-133">如需詳細資訊，請參閱[管理組織中的資料隱私權規定所遵循的資訊](information-protection-deploy-govern.md)。</span><span class="sxs-lookup"><span data-stu-id="7cd38-133">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="7cd38-134">在資訊控管（如惡意保留、刪除及封存）上可能會有不明確的資料隱私權規定 &mdash; ， &mdash; 本文將展示主要控制項架構，您可以針對組織中的資料隱私權使用位址資訊管理需求。</span><span class="sxs-lookup"><span data-stu-id="7cd38-134">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a><span data-ttu-id="7cd38-135">調查：監控並回應資料隱私權法規的使用</span><span class="sxs-lookup"><span data-stu-id="7cd38-135">Investigate: Monitor and respond subject to data privacy regulation</span></span>

<span data-ttu-id="7cd38-136">在您 operationalize 相關功能時，有一些 Microsoft 365 功能可協助您監視、調查組織中的資料隱私權事件，並加以回應。</span><span class="sxs-lookup"><span data-stu-id="7cd38-136">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="7cd38-137">針對上述各項，具有程式、程式及其他檔，都很重要，都是示範規章主體的合規性。</span><span class="sxs-lookup"><span data-stu-id="7cd38-137">Having processes, procedures, and other documentation for each of these can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="7cd38-138">如需詳細資訊，請參閱[監視並回應組織中的資料隱私權事件](information-protection-deploy-monitor-respond.md)。</span><span class="sxs-lookup"><span data-stu-id="7cd38-138">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
