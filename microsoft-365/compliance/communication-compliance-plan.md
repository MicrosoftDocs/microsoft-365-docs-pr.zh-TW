---
title: 規劃通訊合規性
description: 深入瞭解在組織中使用通訊規範的規劃。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 214c5376d4c074525253707e181eee69cefff85e
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045846"
---
# <a name="plan-for-communication-compliance"></a><span data-ttu-id="f1a00-103">規劃通訊合規性</span><span class="sxs-lookup"><span data-stu-id="f1a00-103">Plan for communication compliance</span></span>

<span data-ttu-id="f1a00-104">您的組織中的[通訊合規性](communication-compliance.md)開始之前，必須先閱讀您的資訊技術和合規性管理小組所需的重要規劃活動和考慮。</span><span class="sxs-lookup"><span data-stu-id="f1a00-104">Before getting started with [communication compliance](communication-compliance.md) in your organization, there are important planning activities and considerations that should be reviewed by your information technology and compliance management teams.</span></span> <span data-ttu-id="f1a00-105">在下列各項中徹底瞭解及規劃部署，可協助確保您的實施和使用通訊合規性功能，並與解決方案的最佳作法保持一致。</span><span class="sxs-lookup"><span data-stu-id="f1a00-105">Thoroughly understanding and planning for deployment in the following areas will help ensure that your implementation and use of communication compliance features goes smoothly and is aligned with the best practices for the solution.</span></span>

## <a name="work-with-stakeholders-in-your-organization"></a><span data-ttu-id="f1a00-106">與組織中的專案關係人合作</span><span class="sxs-lookup"><span data-stu-id="f1a00-106">Work with stakeholders in your organization</span></span>

<span data-ttu-id="f1a00-107">在您的組織中識別適當的利益關係人，以共同作業，以在通訊相容性警示上採取行動。</span><span class="sxs-lookup"><span data-stu-id="f1a00-107">Identify the appropriate stakeholders in your organization to collaborate for taking actions on communication compliance alerts.</span></span> <span data-ttu-id="f1a00-108">有些建議的專案關係人會考慮納入初始規劃，以及端對端[通訊規範工作流程](communication-compliance.md#workflow)的人員來自組織的下列領域：</span><span class="sxs-lookup"><span data-stu-id="f1a00-108">Some recommended stakeholders to consider including in initial planning and the end-to-end [communication compliance workflow](communication-compliance.md#workflow) are people from the following areas of your organization:</span></span>

- <span data-ttu-id="f1a00-109">資訊技術</span><span class="sxs-lookup"><span data-stu-id="f1a00-109">Information technology</span></span>
- <span data-ttu-id="f1a00-110">合規性</span><span class="sxs-lookup"><span data-stu-id="f1a00-110">Compliance</span></span>
- <span data-ttu-id="f1a00-111">隱私權</span><span class="sxs-lookup"><span data-stu-id="f1a00-111">Privacy</span></span>
- <span data-ttu-id="f1a00-112">安全性</span><span class="sxs-lookup"><span data-stu-id="f1a00-112">Security</span></span>
- <span data-ttu-id="f1a00-113">人力資源</span><span class="sxs-lookup"><span data-stu-id="f1a00-113">Human resources</span></span>
- <span data-ttu-id="f1a00-114">法務</span><span class="sxs-lookup"><span data-stu-id="f1a00-114">Legal</span></span>

## <a name="plan-for-the-investigation-and-remediation-workflow"></a><span data-ttu-id="f1a00-115">規劃調查和修正工作流程</span><span class="sxs-lookup"><span data-stu-id="f1a00-115">Plan for the investigation and remediation workflow</span></span>

<span data-ttu-id="f1a00-116">選取 [專屬的檢閱者]，以在[Microsoft 365 規範中心](https://compliance.microsoft.com/)內的定期節奏上監視和審閱警示。</span><span class="sxs-lookup"><span data-stu-id="f1a00-116">Select dedicated reviewers to monitor and review the alerts on a regular cadence in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="f1a00-117">請記住，您必須[建立新的角色群組](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance)，以啟用具有「**主管審查管理員**」、「**案例管理**」、「**合規性管理員**」及「**審閱**」角色的許可權，以透過原則相符的方式調查和修正郵件。</span><span class="sxs-lookup"><span data-stu-id="f1a00-117">Remember, you’ll need to [create a new role group](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) to enable permissions for reviewers with the **Supervisory Review Administrator**, **Case Management**, **Compliance Administrator**, and **Review** roles to investigate and remediate messages with policy matches.</span></span>

## <a name="plan-for-policies"></a><span data-ttu-id="f1a00-118">規劃原則</span><span class="sxs-lookup"><span data-stu-id="f1a00-118">Plan for policies</span></span>

<span data-ttu-id="f1a00-119">使用冒犯性語言、機密資訊和法規遵從性的[預先定義範本](communication-compliance-feature-reference.md#policy-templates)，快速且輕鬆建立通訊相容性原則。</span><span class="sxs-lookup"><span data-stu-id="f1a00-119">Creating communication compliance policies is quick and easy with the [pre-defined templates](communication-compliance-feature-reference.md#policy-templates) for offensive language, sensitive information, and regulatory compliance.</span></span> <span data-ttu-id="f1a00-120">自訂通訊合規性原則可讓您彈性地偵測和調查組織和需求的相關問題。</span><span class="sxs-lookup"><span data-stu-id="f1a00-120">Custom communication compliance policies allow the flexibility for detecting and investigation issues specific to your organization and requirements.</span></span>

<span data-ttu-id="f1a00-121">規劃通訊相容性原則時，請考慮下列各項：</span><span class="sxs-lookup"><span data-stu-id="f1a00-121">When planning for communication compliance policies, consider the following:</span></span>

- <span data-ttu-id="f1a00-122">請考慮將組織中的所有使用者新增為您的通訊相容性原則的範圍。</span><span class="sxs-lookup"><span data-stu-id="f1a00-122">Consider adding all users in your organization as in-scope for your communication compliance policies.</span></span> <span data-ttu-id="f1a00-123">在某些情況下，將特定使用者識別成範圍內的個別原則是很有用的，不過大多陣列織都應該將所有使用者都包含在已針對騷擾或歧視偵測優化的通訊合規性原則中。</span><span class="sxs-lookup"><span data-stu-id="f1a00-123">Identifying specific users as in-scope for individual policies are useful in some circumstances, however most organizations should include all users in communication compliance policies optimized for harassment or discrimination detection.</span></span>
- <span data-ttu-id="f1a00-124">若要簡化您的設定，請考慮為需要查看其通訊的使用者建立群組。</span><span class="sxs-lookup"><span data-stu-id="f1a00-124">To simplify your setup, consider creating groups for people who need their communications reviewed.</span></span> <span data-ttu-id="f1a00-125">如果您使用的是群組，則為您可能需要數個。</span><span class="sxs-lookup"><span data-stu-id="f1a00-125">If you're using groups; you might need several.</span></span> <span data-ttu-id="f1a00-126">例如，如果您想要掃描兩個不同的使用者群組之間的通訊，或是想要指定未監督的群組。</span><span class="sxs-lookup"><span data-stu-id="f1a00-126">For example, if you want to scan communications between two distinct groups of people, or if you want to specify a group that isn't supervised.</span></span>
- <span data-ttu-id="f1a00-127">設定要在100% 檢查的通訊百分比，以確保原則能夠捕捉組織中的所有相關問題。</span><span class="sxs-lookup"><span data-stu-id="f1a00-127">Configure the percentage of communications to review at 100% to ensure that policies are catching all issues of concern in communications for your organization.</span></span>
- <span data-ttu-id="f1a00-128">您可以從[協力廠商來源](communication-compliance-feature-reference.md#supported-communication-types)掃描通訊，以用於將資料匯入至 Microsoft 365 組織中的信箱。</span><span class="sxs-lookup"><span data-stu-id="f1a00-128">You can scan communications from [third-party sources](communication-compliance-feature-reference.md#supported-communication-types) for data imported into mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="f1a00-129">若要在這些平臺中包含通訊的複查，您必須先設定這些服務的連接器，然後通訊原則才能監視郵件會議原則條件。</span><span class="sxs-lookup"><span data-stu-id="f1a00-129">To include review of communications in these platforms, you’ll need to configure a connector to these services before messages meeting policy conditions are monitored by communication policy.</span></span>
- <span data-ttu-id="f1a00-130">在自訂通訊合規性原則中，原則可以支援非英文的監控語言。</span><span class="sxs-lookup"><span data-stu-id="f1a00-130">Policies can support monitoring languages other than English in custom communication compliance policies.</span></span> <span data-ttu-id="f1a00-131">使用您選擇的語言建立冒犯性文字的[自訂關鍵字字典](communication-compliance-feature-reference.md#custom-keyword-dictionaries)，或使用 Microsoft 365 中的[trainable 分類](classifier-getting-started-with.md)程式建立您自己的機器學習模型。</span><span class="sxs-lookup"><span data-stu-id="f1a00-131">Build a [custom keyword dictionary](communication-compliance-feature-reference.md#custom-keyword-dictionaries) of offensive words in the language of your choice or build your own machine-learning model using [trainable classifiers](classifier-getting-started-with.md) in Microsoft 365.</span></span>
- <span data-ttu-id="f1a00-132">所有組織都有不同的通訊標準和原則需求。</span><span class="sxs-lookup"><span data-stu-id="f1a00-132">All organizations have different communication standards and policy needs.</span></span> <span data-ttu-id="f1a00-133">使用通訊相容性[原則條件](communication-compliance-feature-reference.md#conditional-settings)，或利用[自訂敏感資訊類型](create-a-custom-sensitive-information-type.md)監控特定類型的資訊，監視特定關鍵字。</span><span class="sxs-lookup"><span data-stu-id="f1a00-133">Monitor for specific keywords using communication compliance [policy conditions](communication-compliance-feature-reference.md#conditional-settings) or monitor for specific types of information with [custom sensitive information types](create-a-custom-sensitive-information-type.md).</span></span>

## <a name="ready-to-get-started"></a><span data-ttu-id="f1a00-134">準備好開始使用了嗎？</span><span class="sxs-lookup"><span data-stu-id="f1a00-134">Ready to get started?</span></span>

<span data-ttu-id="f1a00-135">若要設定 Microsoft 365 組織的通訊相容性，請參閱[設定 microsoft 365 的通訊相容](communication-compliance-configure.md)性，[以及如何](communication-compliance-case-study.md)快速設定通訊相容性原則，以監視 Microsoft 小組、Exchange Online 和 Yammer 通訊中的冒犯性語言。</span><span class="sxs-lookup"><span data-stu-id="f1a00-135">To configure communication compliance for your Microsoft 365 organization, see [Configure communication compliance for Microsoft 365](communication-compliance-configure.md) or check out the [case study for Contoso](communication-compliance-case-study.md) and how they quickly configured a communication compliance policy to monitor for offensive language in Microsoft Teams, Exchange Online, and Yammer communications.</span></span>
