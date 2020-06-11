---
title: 監視和回應組織中的資料隱私權事件
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
description: 使用審核和警示原則及資料主體要求來監視及回應個人資料事件。
ms.openlocfilehash: 5760bb40eb26e2ff0636ea9604cc7c45b7d0ca63
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695064"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="faca5-103">監視和回應組織中的資料隱私權事件</span><span class="sxs-lookup"><span data-stu-id="faca5-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="faca5-104">Microsoft 365 的功能可協助您在 operationalize 相關功能時，監控、調查組織中的資料隱私權事件，並加以回應。</span><span class="sxs-lookup"><span data-stu-id="faca5-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="faca5-105">針對上述各項，具有程式、程式和其他檔，對規章主體的符合性也很重要。</span><span class="sxs-lookup"><span data-stu-id="faca5-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="faca5-106">包括：</span><span class="sxs-lookup"><span data-stu-id="faca5-106">These include:</span></span> 

- <span data-ttu-id="faca5-107">審核和警示原則</span><span class="sxs-lookup"><span data-stu-id="faca5-107">Auditing and alert policies</span></span>
- <span data-ttu-id="faca5-108">資料主體要求（包括內容搜尋和 eDiscovery）</span><span class="sxs-lookup"><span data-stu-id="faca5-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="faca5-109">其他調查工具和報告</span><span class="sxs-lookup"><span data-stu-id="faca5-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="faca5-110">資料隱私權規定會影響監控和回應工具的使用</span><span class="sxs-lookup"><span data-stu-id="faca5-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="faca5-111">以下是可能與資訊管理控制相關之資料隱私權法規的範例清單：</span><span class="sxs-lookup"><span data-stu-id="faca5-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="faca5-112">LGPD 文章46</span><span class="sxs-lookup"><span data-stu-id="faca5-112">LGPD Article 46</span></span>
- <span data-ttu-id="faca5-113">LGPD 文章48</span><span class="sxs-lookup"><span data-stu-id="faca5-113">LGPD Article 48</span></span>
- <span data-ttu-id="faca5-114">GDPR 文章（5）（1）（f）</span><span class="sxs-lookup"><span data-stu-id="faca5-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="faca5-115">GDPR 文章（15）（1）（e）</span><span class="sxs-lookup"><span data-stu-id="faca5-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="faca5-116">HIPAA-高科技（45 C.F.R。</span><span class="sxs-lookup"><span data-stu-id="faca5-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="faca5-117">164.308 （a）（1）（ii）（D））</span><span class="sxs-lookup"><span data-stu-id="faca5-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="faca5-118">HIPAA-高科技（45 C.F.R。</span><span class="sxs-lookup"><span data-stu-id="faca5-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="faca5-119">164.308 （a）（6）（ii）</span><span class="sxs-lookup"><span data-stu-id="faca5-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="faca5-120">HIPAA-高科技（45 C.F.R。</span><span class="sxs-lookup"><span data-stu-id="faca5-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="faca5-121">164.312 （b））</span><span class="sxs-lookup"><span data-stu-id="faca5-121">164.312(b))</span></span>
- <span data-ttu-id="faca5-122">CCPA （1798.105 （c））</span><span class="sxs-lookup"><span data-stu-id="faca5-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="faca5-123">如需詳細資訊，請參閱[評估資料隱私權風險及識別敏感資訊](information-protection-deploy-assess.md)。</span><span class="sxs-lookup"><span data-stu-id="faca5-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="faca5-124">資料隱私權規定一般會呼叫下列以進行監視和回應：</span><span class="sxs-lookup"><span data-stu-id="faca5-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="faca5-125">與儲存、共用及處理個人資料相關的活動的審計、警示和報告</span><span class="sxs-lookup"><span data-stu-id="faca5-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="faca5-126">回應資料主體要求（DSR）的能力，在某些情況下，請執行調查和其他管理措施，以遵守這類要求。</span><span class="sxs-lookup"><span data-stu-id="faca5-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="faca5-127">您的組織可能也想要針對其他目的（如其他法規遵從性需求或商務原因）執行監視和回應活動。</span><span class="sxs-lookup"><span data-stu-id="faca5-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="faca5-128">在整體監控和回應規劃、實施及管理等情況下，建立您的監控和回應架構，以進行資料隱私權。</span><span class="sxs-lookup"><span data-stu-id="faca5-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="faca5-129">為了協助您開始使用 Microsoft 365 的監控和回應架構以取得資料隱私權規定，本文會列出 Microsoft 365 中有用的功能，以回答下列問題：</span><span class="sxs-lookup"><span data-stu-id="faca5-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="faca5-130">在不同的資料類型和來源中，可以使用哪一天的監視、調查和報表技巧？</span><span class="sxs-lookup"><span data-stu-id="faca5-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="faca5-131">處理資料主體要求（Dsr）和任何補救動作（如匿名、密文和刪除）時，所需的機制。</span><span class="sxs-lookup"><span data-stu-id="faca5-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="faca5-132">安全性與合規性中心內的審計和警示原則</span><span class="sxs-lookup"><span data-stu-id="faca5-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="faca5-133">請參閱下列文章以設定審核、高級審核及警示原則：</span><span class="sxs-lookup"><span data-stu-id="faca5-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="faca5-134">整合的稽核</span><span class="sxs-lookup"><span data-stu-id="faca5-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="faca5-135">信箱稽核</span><span class="sxs-lookup"><span data-stu-id="faca5-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="faca5-136">高級審計</span><span class="sxs-lookup"><span data-stu-id="faca5-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="faca5-137">警示原則</span><span class="sxs-lookup"><span data-stu-id="faca5-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="faca5-138">GDPR 和 CCPA 的資料主體要求</span><span class="sxs-lookup"><span data-stu-id="faca5-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="faca5-139">請參閱[GDPR 和 CCPA 的資料主體要求](../compliance/gdpr-dsr-office365.md)，以取得在 Microsoft 365 中回應 DSR 的資訊。</span><span class="sxs-lookup"><span data-stu-id="faca5-139">See [Data Subject Requests for the GDPR and CCPA](../compliance/gdpr-dsr-office365.md) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="faca5-140">在 Microsoft Stream 中管理已刪除的使用者</span><span class="sxs-lookup"><span data-stu-id="faca5-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="faca5-141">若為 Microsoft Stream，當使用者從 Azure Active Directory （Azure AD）刪除時，如果其名稱在該點之前與發佈的資料流程影片相關聯，則其電子郵件地址仍會與影片產生關聯。</span><span class="sxs-lookup"><span data-stu-id="faca5-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="faca5-142">請參閱[管理從 Microsoft Stream 刪除的使用者](https://docs.microsoft.com/stream/managing-deleted-users)以將其移除。</span><span class="sxs-lookup"><span data-stu-id="faca5-142">See [Manage deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) to remove it.</span></span>

## <a name="additional-investigative-tools"></a><span data-ttu-id="faca5-143">其他調查工具</span><span class="sxs-lookup"><span data-stu-id="faca5-143">Additional investigative tools</span></span>

<span data-ttu-id="faca5-144">以下是其他兩個工具，可在組織中監控、調查和修正資料隱私權相關的事件時非常有用：</span><span class="sxs-lookup"><span data-stu-id="faca5-144">Here are two additional tools that might be useful for monitoring, investigating, and remediating data privacy-related incidents in your organization:</span></span>

- <span data-ttu-id="faca5-145">[Microsoft 365 中的「內幕風險管理](../compliance/insider-risk-management.md)」是 microsoft 規範系統管理中心的一項功能，可讓您偵測、調查和採取行動以應對組織中的危險活動，以協助降低內部風險。</span><span class="sxs-lookup"><span data-stu-id="faca5-145">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md), a feature of the Microsoft Compliance admin center to help minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>
- <span data-ttu-id="faca5-146">Microsoft [365 中的資料調查](../compliance/overview-data-investigations.md)，Microsoft 合規性系統管理中心的功能可搜尋整個 Microsoft 365 的敏感、惡意或誤放資料，然後調查採取適當動作修正該事件的情形。</span><span class="sxs-lookup"><span data-stu-id="faca5-146">[Data investigations in Microsoft 365](../compliance/overview-data-investigations.md), a feature of the Microsoft Compliance admin center to search for sensitive, malicious, or misplaced data across Microsoft 365, and then investigate what happened to take the appropriate actions to remediate the incident.</span></span>
