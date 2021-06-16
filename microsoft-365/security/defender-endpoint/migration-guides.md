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
ms.date: 06/14/2021
ms.technology: mde
ms.openlocfilehash: 4d10de35358d528f004ee11e931fc6f41ce20482
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930496"
---
# <a name="make-the-switch-to-microsoft-defender-for-endpoint-and-microsoft-defender-antivirus"></a><span data-ttu-id="d6e18-103">切換至 Microsoft Defender for 端點和 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="d6e18-103">Make the switch to Microsoft Defender for Endpoint and Microsoft Defender Antivirus</span></span>

<span data-ttu-id="d6e18-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d6e18-104">**Applies to:**</span></span>
- [<span data-ttu-id="d6e18-105">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d6e18-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d6e18-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d6e18-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d6e18-107">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="d6e18-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d6e18-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d6e18-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="migration-guides"></a><span data-ttu-id="d6e18-109">移轉指南</span><span class="sxs-lookup"><span data-stu-id="d6e18-109">Migration guides</span></span>

<span data-ttu-id="d6e18-110">如果您考慮使用 Microsoft Defender 防毒軟體將非 Microsoft 365 的 defender 解決方案切換至 Microsoft Defender for Endpoint，請參閱我們的遷移指南。</span><span class="sxs-lookup"><span data-stu-id="d6e18-110">If you're considering switching from a non-Microsoft 365 Defender solution to Microsoft Defender for Endpoint with Microsoft Defender Antivirus, check out our migration guidance.</span></span> <span data-ttu-id="d6e18-111">選取最適合您在部署程式中的位置的案例，並參閱指導方針。</span><span class="sxs-lookup"><span data-stu-id="d6e18-111">Select the scenario that best represents where you are in your deployment process, and see the guidance.</span></span>

|<span data-ttu-id="d6e18-112">案例</span><span class="sxs-lookup"><span data-stu-id="d6e18-112">Scenario</span></span> |<span data-ttu-id="d6e18-113">指導方針</span><span class="sxs-lookup"><span data-stu-id="d6e18-113">Guidance</span></span> |
|:--|:--|
|<span data-ttu-id="d6e18-114">您尚沒有 endpoint protection 解決方案，而且想要深入瞭解 Microsoft Defender for endpoint & Microsoft Defender 防毒軟體的運作方式。</span><span class="sxs-lookup"><span data-stu-id="d6e18-114">You do not have an endpoint protection solution yet, and you want to know more about how Microsoft Defender for Endpoint & Microsoft Defender Antivirus work.</span></span>  |[<span data-ttu-id="d6e18-115">Microsoft Defender for Endpoint 評估實驗室</span><span class="sxs-lookup"><span data-stu-id="d6e18-115">Microsoft Defender for Endpoint evaluation lab</span></span>](evaluation-lab.md)   |
|<span data-ttu-id="d6e18-116">您有 Microsoft Defender for Endpoint & Microsoft Defender 防毒軟體，需要協助您取得及設定所有東西。</span><span class="sxs-lookup"><span data-stu-id="d6e18-116">You have Microsoft Defender for Endpoint & Microsoft Defender Antivirus and need some help getting everything set up and configured.</span></span>  |[<span data-ttu-id="d6e18-117">Microsoft Defender for Endpoint 部署指南</span><span class="sxs-lookup"><span data-stu-id="d6e18-117">Microsoft Defender for Endpoint deployment guide</span></span>](deployment-phases.md)  |
|<span data-ttu-id="d6e18-118">您計畫要從非 Microsoft endpoint protection 解決方案遷移至 Microsoft Defender for endpoint & Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="d6e18-118">You're planning to migrate from a non-Microsoft endpoint protection solution to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="d6e18-119">將參數設為 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d6e18-119">Make the switch to Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-migration.md)   |
|<span data-ttu-id="d6e18-120">您已遷移至 Microsoft Defender for Endpoint & Microsoft Defender 防毒軟體，您需要在後續步驟中取得協助，例如設定其他功能或微調安全性設定。</span><span class="sxs-lookup"><span data-stu-id="d6e18-120">You've migrated to Microsoft Defender for Endpoint & Microsoft Defender Antivirus, and you need help with next steps, such as configuring additional features or fine-tuning your security settings.</span></span> | [<span data-ttu-id="d6e18-121">管理 Microsoft Defender for Endpoint，遷移後</span><span class="sxs-lookup"><span data-stu-id="d6e18-121">Manage Microsoft Defender for Endpoint, post-migration</span></span>](manage-atp-post-migration.md) |


## <a name="do-you-have-feedback-for-us"></a><span data-ttu-id="d6e18-122">您是否有我們的意見反應？</span><span class="sxs-lookup"><span data-stu-id="d6e18-122">Do you have feedback for us?</span></span>

<span data-ttu-id="d6e18-123">讓我們知道您的想法！</span><span class="sxs-lookup"><span data-stu-id="d6e18-123">Let us know what you think!</span></span> <span data-ttu-id="d6e18-124">在頁面底部提交您的意見反應。</span><span class="sxs-lookup"><span data-stu-id="d6e18-124">Submit your feedback at the bottom of the page.</span></span> <span data-ttu-id="d6e18-125">我們會將您的意見反應納入考慮，我們會繼續改進並新增遷移指南。</span><span class="sxs-lookup"><span data-stu-id="d6e18-125">We'll take your feedback into account as we continue to improve and add to our migration guidance.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6e18-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d6e18-126">See also</span></span>

- [<span data-ttu-id="d6e18-127">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d6e18-127">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
- [<span data-ttu-id="d6e18-128">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d6e18-128">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="d6e18-129">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d6e18-129">Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/microsoft-threat-protection?) 
