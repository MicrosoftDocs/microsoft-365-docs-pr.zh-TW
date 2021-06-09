---
title: 回應第一個事件的簡介
description: 在 Microsoft 365 Defender 中回應第一個事件的基本概念。
keywords: 事件、警示、調查、關聯性、攻擊、裝置、使用者、身分識別、身分識別、信箱、電子郵件、365、microsoft、m365、事件回應、網路攻擊
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6e65a12f42b9f5f75c1a19cb9c4a261c94feaf31
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841711"
---
# <a name="introduction-to-responding-to-your-first-incident"></a><span data-ttu-id="bdbcd-104">回應第一個事件的簡介</span><span class="sxs-lookup"><span data-stu-id="bdbcd-104">Introduction to responding to your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="bdbcd-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="bdbcd-105">**Applies to:**</span></span>
- <span data-ttu-id="bdbcd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bdbcd-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bdbcd-107">組織的事件回應策略決定其處理日益中斷的安全性事件和網路犯罪的能力。</span><span class="sxs-lookup"><span data-stu-id="bdbcd-107">An organization's incident response strategy determines its ability to deal with increasingly disruptive security incidents and cybercrime.</span></span> <span data-ttu-id="bdbcd-108">採取預防措施很重要時，快速從偵測到的事件中包含、消除及復原的能力，可使損毀和業務損毀減至最少。</span><span class="sxs-lookup"><span data-stu-id="bdbcd-108">While taking preventative measures is important, the ability to act quickly to contain, eradicate, and recover from detected incidents can minimize damage and business losses.</span></span>

<span data-ttu-id="bdbcd-109">這個事件回應演練會顯示您做為安全性運作小組的一部分，如何在 Microsoft 365 Defender 內執行大部分的主要事件回應步驟。</span><span class="sxs-lookup"><span data-stu-id="bdbcd-109">This incident response walkthrough shows how you, as part of a security operations team, can perform most of the key incident response steps within Microsoft 365 Defender.</span></span> <span data-ttu-id="bdbcd-110">步驟如下：</span><span class="sxs-lookup"><span data-stu-id="bdbcd-110">Here are the steps:</span></span>

- <span data-ttu-id="bdbcd-111">安全狀況的準備</span><span class="sxs-lookup"><span data-stu-id="bdbcd-111">Preparation of your security posture</span></span>
- <span data-ttu-id="bdbcd-112">針對每個事件：</span><span class="sxs-lookup"><span data-stu-id="bdbcd-112">For each incident:</span></span>
  - <span data-ttu-id="bdbcd-113">步驟1：會審和分析</span><span class="sxs-lookup"><span data-stu-id="bdbcd-113">Step 1: Triage and analysis</span></span>
  - <span data-ttu-id="bdbcd-114">步驟2：修復 (包含、eradication 及復原) </span><span class="sxs-lookup"><span data-stu-id="bdbcd-114">Step 2: Remediation (containment, eradication, and recovery)</span></span>
  - <span data-ttu-id="bdbcd-115">步驟3：事件後檢查</span><span class="sxs-lookup"><span data-stu-id="bdbcd-115">Step 3: Post-incident review</span></span>

<span data-ttu-id="bdbcd-116">安全事件是由跨國的標準和技術研究院 (NIST) （即實際或可能 jeopardizes 資訊系統之機密性、完整性或可用性的事件）所定義;或是系統處理、儲存或傳輸的資訊;或違反安全性原則、安全性程式或可接受的使用原則的違反或即將發生威脅。</span><span class="sxs-lookup"><span data-stu-id="bdbcd-116">A security incident is defined by National Institute of Standards and Technology (NIST) as "an occurrence that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system; or the information the system processes, stores, or transmits; or that constitutes a violation or imminent threat of violation of security policies, security procedures, or acceptable use policies."</span></span>

<span data-ttu-id="bdbcd-117">Microsoft 365 Defender 中的事件是分析和事件回應的邏輯起始點。</span><span class="sxs-lookup"><span data-stu-id="bdbcd-117">Incidents in Microsoft 365 Defender are the logical starting points for analysis and incident response.</span></span> <span data-ttu-id="bdbcd-118">分析和修正事件通常可組成安全性作業小組的工作。</span><span class="sxs-lookup"><span data-stu-id="bdbcd-118">Analyzing and remediating incidents typically makes up most of a security operations team's tasks.</span></span>

## <a name="next-step"></a><span data-ttu-id="bdbcd-119">下一步</span><span class="sxs-lookup"><span data-stu-id="bdbcd-119">Next step</span></span>

<span data-ttu-id="bdbcd-120">[![準備組織和 Microsoft 365 租使用者](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="bdbcd-120">[![Prepare your organization and Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span></span>

<span data-ttu-id="bdbcd-121">請確定您的組織和 Microsoft 365 租使用者已[準備好進行事件處理](first-incident-prepare.md)。</span><span class="sxs-lookup"><span data-stu-id="bdbcd-121">Make sure your organization and Microsoft 365 tenant is [prepared for incident handling](first-incident-prepare.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bdbcd-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bdbcd-122">See also</span></span>

<span data-ttu-id="bdbcd-123">Microsoft 365 Defender 的事件回應指導：</span><span class="sxs-lookup"><span data-stu-id="bdbcd-123">Incident response guidance for Microsoft 365 Defender:</span></span>

- [<span data-ttu-id="bdbcd-124">事件概觀</span><span class="sxs-lookup"><span data-stu-id="bdbcd-124">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="bdbcd-125">調查事件</span><span class="sxs-lookup"><span data-stu-id="bdbcd-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="bdbcd-126">管理事件</span><span class="sxs-lookup"><span data-stu-id="bdbcd-126">Manage incidents</span></span>](manage-incidents.md)

<span data-ttu-id="bdbcd-127">其他第一個事件回應的範例：</span><span class="sxs-lookup"><span data-stu-id="bdbcd-127">Additional examples of first incident responses:</span></span>

- [<span data-ttu-id="bdbcd-128">網路釣魚電子郵件</span><span class="sxs-lookup"><span data-stu-id="bdbcd-128">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="bdbcd-129">Identity-基礎攻擊</span><span class="sxs-lookup"><span data-stu-id="bdbcd-129">Identity-base attack</span></span>](first-incident-path-identity.md)

[<span data-ttu-id="bdbcd-130">詳細的事件回應行動手冊</span><span class="sxs-lookup"><span data-stu-id="bdbcd-130">Detailed incident response playbooks</span></span>](/security/compass/incident-response-playbooks)


