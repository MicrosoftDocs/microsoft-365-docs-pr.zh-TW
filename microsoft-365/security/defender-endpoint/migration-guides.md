---
title: 用於切換至 Microsoft Defender 以進行端點的遷移指南
description: 瞭解如何將非 Microsoft 365 的 defender 解決方案切換至 Microsoft defender for Endpoint
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.custom: migrationguides
ms.reviewer: chriggs, depicker, yongrhee
f1.keywords: NOCSH
ms.date: 09/24/2020
ms.technology: mde
ms.openlocfilehash: 7d6d92f3abc79552406c80a46a8c3390b91e31d0
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843007"
---
# <a name="make-the-switch-to-microsoft-defender-for-endpoint-and-microsoft-defender-antivirus"></a><span data-ttu-id="d8ef2-103">切換至 Microsoft Defender for 端點和 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="d8ef2-103">Make the switch to Microsoft Defender for Endpoint and Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d8ef2-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d8ef2-104">**Applies to:**</span></span>
- [<span data-ttu-id="d8ef2-105">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d8ef2-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d8ef2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8ef2-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d8ef2-107">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="d8ef2-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d8ef2-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d8ef2-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="migration-guides"></a><span data-ttu-id="d8ef2-109">移轉指南</span><span class="sxs-lookup"><span data-stu-id="d8ef2-109">Migration guides</span></span>

<span data-ttu-id="d8ef2-110">如果您考慮使用 Microsoft Defender 防毒軟體將非 Microsoft 365 的 defender 解決方案切換至 Microsoft Defender for Endpoint，請參閱我們的遷移指南。</span><span class="sxs-lookup"><span data-stu-id="d8ef2-110">If you're considering switching from a non-Microsoft 365 Defender solution to Microsoft Defender for Endpoint with Microsoft Defender Antivirus, check out our migration guidance.</span></span> <span data-ttu-id="d8ef2-111">選取最適合您在部署程式中的位置的案例，並參閱指導方針。</span><span class="sxs-lookup"><span data-stu-id="d8ef2-111">Select the scenario that best represents where you are in your deployment process, and see the guidance.</span></span>

|<span data-ttu-id="d8ef2-112">案例</span><span class="sxs-lookup"><span data-stu-id="d8ef2-112">Scenario</span></span> |<span data-ttu-id="d8ef2-113">指導方針</span><span class="sxs-lookup"><span data-stu-id="d8ef2-113">Guidance</span></span> |
|:--|:--|
|<span data-ttu-id="d8ef2-114">您尚沒有 endpoint protection 解決方案，而且想要深入瞭解 Microsoft Defender for endpoint & Microsoft Defender 防毒軟體的運作方式。</span><span class="sxs-lookup"><span data-stu-id="d8ef2-114">You do not have an endpoint protection solution yet, and you want to know more about how Microsoft Defender for Endpoint & Microsoft Defender Antivirus work.</span></span>  |[<span data-ttu-id="d8ef2-115">Microsoft Defender for Endpoint 評估實驗室</span><span class="sxs-lookup"><span data-stu-id="d8ef2-115">Microsoft Defender for Endpoint evaluation lab</span></span>](evaluation-lab.md)   |
|<span data-ttu-id="d8ef2-116">您有 Microsoft Defender for Endpoint & Microsoft Defender 防毒軟體，需要協助您取得及設定所有東西。</span><span class="sxs-lookup"><span data-stu-id="d8ef2-116">You have Microsoft Defender for Endpoint & Microsoft Defender Antivirus and need some help getting everything set up and configured.</span></span>  |[<span data-ttu-id="d8ef2-117">Microsoft Defender for Endpoint 部署指南</span><span class="sxs-lookup"><span data-stu-id="d8ef2-117">Microsoft Defender for Endpoint deployment guide</span></span>](deployment-phases.md)  |
|<span data-ttu-id="d8ef2-118">您計畫要從 mcafee 端點安全性 (mcafee) 至 Microsoft Defender for Endpoint & Microsoft Defender 防毒軟體進行遷移。</span><span class="sxs-lookup"><span data-stu-id="d8ef2-118">You're planning to migrate from McAfee Endpoint Security (McAfee) to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="d8ef2-119">從 McAfee 切換至適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d8ef2-119">Switch from McAfee to Microsoft Defender for Endpoint</span></span>](mcafee-to-microsoft-defender-migration.md) |
|<span data-ttu-id="d8ef2-120">您打算從 symantec Endpoint Protection (symantec) 遷移至 Microsoft Defender for Endpoint & Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="d8ef2-120">You're planning to migrate from Symantec Endpoint Protection (Symantec) to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="d8ef2-121">從 Symantec 切換至適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d8ef2-121">Switch from Symantec to Microsoft Defender for Endpoint</span></span>](symantec-to-microsoft-defender-endpoint-migration.md) |
|<span data-ttu-id="d8ef2-122">您計畫從非 microsoft 的 endpoint protection (解決方案進行遷移，但不是 McAfee 或 Symantec) microsoft Defender for endpoint & Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="d8ef2-122">You're planning to migrate from a non-Microsoft endpoint protection solution (other than McAfee or Symantec) to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="d8ef2-123">將參數設為 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d8ef2-123">Make the switch to Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-migration.md)   |
|<span data-ttu-id="d8ef2-124">您已遷移至 Microsoft Defender for Endpoint & Microsoft Defender 防毒軟體，您需要在後續步驟中取得協助，例如設定其他功能或微調安全性設定。</span><span class="sxs-lookup"><span data-stu-id="d8ef2-124">You've migrated to Microsoft Defender for Endpoint & Microsoft Defender Antivirus, and you need help with next steps, such as configuring additional features or fine-tuning your security settings.</span></span> | [<span data-ttu-id="d8ef2-125">管理 Microsoft Defender for Endpoint，遷移後</span><span class="sxs-lookup"><span data-stu-id="d8ef2-125">Manage Microsoft Defender for Endpoint, post-migration</span></span>](manage-atp-post-migration.md) |


## <a name="got-feedback"></a><span data-ttu-id="d8ef2-126">收到意見反應？</span><span class="sxs-lookup"><span data-stu-id="d8ef2-126">Got feedback?</span></span>

<span data-ttu-id="d8ef2-127">讓我們知道您的想法！</span><span class="sxs-lookup"><span data-stu-id="d8ef2-127">Let us know what you think!</span></span> <span data-ttu-id="d8ef2-128">在頁面底部提交您的意見反應。</span><span class="sxs-lookup"><span data-stu-id="d8ef2-128">Submit your feedback at the bottom of the page.</span></span> <span data-ttu-id="d8ef2-129">我們會將您的意見反應納入考慮，我們會繼續改進並新增遷移指南。</span><span class="sxs-lookup"><span data-stu-id="d8ef2-129">We'll take your feedback into account as we continue to improve and add to our migration guidance.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8ef2-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d8ef2-130">See also</span></span>

- [<span data-ttu-id="d8ef2-131">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d8ef2-131">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
- [<span data-ttu-id="d8ef2-132">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d8ef2-132">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="d8ef2-133">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8ef2-133">Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/microsoft-threat-protection?) 
