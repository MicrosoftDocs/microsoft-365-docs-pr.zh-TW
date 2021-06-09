---
title: 步驟 3： 執行第一個事件的事件後檢查
description: 如何在 Microsoft 365 Defender 中執行第一個事件的複查。
keywords: 事件, 警示, 調查, 關聯, 攻擊, 電腦, 裝置, 使用者, 身分識別, 身分識別, 信箱, 電子郵件, 365, microsoft, m365
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
ms.openlocfilehash: 6b5311a2923d7b299ba4f70ef3c2e8d91809e7c8
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651365"
---
# <a name="step-3-perform-a-post-incident-review-of-your-first-incident"></a><span data-ttu-id="b18c1-105">步驟 3.</span><span class="sxs-lookup"><span data-stu-id="b18c1-105">Step 3.</span></span> <span data-ttu-id="b18c1-106">執行第一個事件的事件後檢查</span><span class="sxs-lookup"><span data-stu-id="b18c1-106">Perform a post-incident review of your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b18c1-107">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b18c1-107">**Applies to:**</span></span>
- <span data-ttu-id="b18c1-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b18c1-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="b18c1-109">國家標準和技術研究院 (NIST) 建議在採取所有步驟來復原攻擊後，組織必須複查該事件，以瞭解該事件，並改進安全性的狀況或處理常式。</span><span class="sxs-lookup"><span data-stu-id="b18c1-109">National Institute of Standards and Technology (NIST) recommends that once all steps have been taken to recover from the attack, organizations must review the incident to learn from it and improve security posture or processes.</span></span> <span data-ttu-id="b18c1-110">評估事件處理的不同層面對準備下一個事件變得很重要。</span><span class="sxs-lookup"><span data-stu-id="b18c1-110">Assessing the different aspects of incident-handling becomes important in preparing for the next incident.</span></span>

<span data-ttu-id="b18c1-111">Microsoft 365您可以為組織提供與[MITRE ATT&CK Framework](https://attack.mitre.org/)相符的警示，以協助執行後續事件活動。</span><span class="sxs-lookup"><span data-stu-id="b18c1-111">Microsoft 365 Defender can assist in performing post-incident activities by providing an organization with alerts that align with [MITRE ATT&CK Framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="b18c1-112">所有 Microsoft Defender 解決方案標籤會依照 ATT&CK 戰術或技術所進行的攻擊。</span><span class="sxs-lookup"><span data-stu-id="b18c1-112">All Microsoft Defender solutions label attacks in accordance with an ATT&CK tactic or technique.</span></span> 

<span data-ttu-id="b18c1-113">將警示對應至此工業架構，您可以：</span><span class="sxs-lookup"><span data-stu-id="b18c1-113">By mapping alerts to this industry framework, you can:</span></span>

- <span data-ttu-id="b18c1-114">進行安全性覆蓋範圍的分析。</span><span class="sxs-lookup"><span data-stu-id="b18c1-114">Conduct an analysis of gaps in security coverage.</span></span>
- <span data-ttu-id="b18c1-115">決定敵人和活動的歸屬。</span><span class="sxs-lookup"><span data-stu-id="b18c1-115">Determine adversary and campaign attribution.</span></span>
- <span data-ttu-id="b18c1-116">執行趨勢分析。</span><span class="sxs-lookup"><span data-stu-id="b18c1-116">Perform trend analysis.</span></span>
- <span data-ttu-id="b18c1-117">識別攻擊方法知曉中的技能差距。</span><span class="sxs-lookup"><span data-stu-id="b18c1-117">Identify skill gaps in attack method awareness.</span></span>
- <span data-ttu-id="b18c1-118">建立 Power Automate 行動手冊，以加快修復速度。</span><span class="sxs-lookup"><span data-stu-id="b18c1-118">Create a Power Automate Playbook for faster remediation.</span></span> 

<span data-ttu-id="b18c1-119">事件後檢查活動也可導致微調安全性設定和安全性小組的程式，以加強組織的回應能力。</span><span class="sxs-lookup"><span data-stu-id="b18c1-119">Post-incident review activity can also result in fine-tuning your security configuration and security team's processes, enhancing your organization’s response capabilities.</span></span>

## <a name="next-step"></a><span data-ttu-id="b18c1-120">下一步</span><span class="sxs-lookup"><span data-stu-id="b18c1-120">Next step</span></span>

<span data-ttu-id="b18c1-121">請參閱下列其他調查路徑：</span><span class="sxs-lookup"><span data-stu-id="b18c1-121">See these additional investigation paths:</span></span>

- [<span data-ttu-id="b18c1-122">網路釣魚電子郵件</span><span class="sxs-lookup"><span data-stu-id="b18c1-122">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="b18c1-123">以身分識別為基礎的攻擊</span><span class="sxs-lookup"><span data-stu-id="b18c1-123">Identity-based attack</span></span>](first-incident-path-identity.md)


## <a name="see-also"></a><span data-ttu-id="b18c1-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b18c1-124">See also</span></span>

- [<span data-ttu-id="b18c1-125">事件概觀</span><span class="sxs-lookup"><span data-stu-id="b18c1-125">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b18c1-126">調查事件</span><span class="sxs-lookup"><span data-stu-id="b18c1-126">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="b18c1-127">管理事件</span><span class="sxs-lookup"><span data-stu-id="b18c1-127">Manage incidents</span></span>](manage-incidents.md)
