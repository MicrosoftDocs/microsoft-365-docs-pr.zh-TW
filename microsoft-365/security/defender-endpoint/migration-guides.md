---
title: 用於切換至 Microsoft Defender 以進行端點的遷移指南
description: 瞭解如何將非 Microsoft 365 Defender 解決方案的切換到 Microsoft Defender for Endpoint
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
ms.openlocfilehash: 010cea14bebd4e29822b1826c0ec4577d53baca7
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964858"
---
# <a name="make-the-switch-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="bf31a-103">將參數設為 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bf31a-103">Make the switch to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="bf31a-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="bf31a-104">**Applies to:**</span></span>
- [<span data-ttu-id="bf31a-105">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bf31a-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bf31a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf31a-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bf31a-107">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="bf31a-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bf31a-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="bf31a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="migration-guides"></a><span data-ttu-id="bf31a-109">移轉指南</span><span class="sxs-lookup"><span data-stu-id="bf31a-109">Migration guides</span></span>

<span data-ttu-id="bf31a-110">如果您正在考慮移至 Defender for Endpoint，我們有助您協助。</span><span class="sxs-lookup"><span data-stu-id="bf31a-110">If you're considering moving to Defender for Endpoint, we have guidance to help.</span></span> <span data-ttu-id="bf31a-111">在下表中，複查案例。</span><span class="sxs-lookup"><span data-stu-id="bf31a-111">In the following table, review the scenarios.</span></span> <span data-ttu-id="bf31a-112">選取最適合您狀況的案例，並查看建議的指南。</span><span class="sxs-lookup"><span data-stu-id="bf31a-112">Select the scenario that best represents your situation, and see the recommended guidance.</span></span>

| <span data-ttu-id="bf31a-113">案例</span><span class="sxs-lookup"><span data-stu-id="bf31a-113">Scenario</span></span> | <span data-ttu-id="bf31a-114">指導方針</span><span class="sxs-lookup"><span data-stu-id="bf31a-114">Guidance</span></span> |
|:----|:----|
| <span data-ttu-id="bf31a-115">您尚無 endpoint protection 解決方案，而且想要瞭解更多關於端點的 Defender。</span><span class="sxs-lookup"><span data-stu-id="bf31a-115">You don't have an endpoint protection solution in place yet, and you want to know more about Defender for Endpoint.</span></span> <span data-ttu-id="bf31a-116">您想要查看端點在您的環境中的運作方式。</span><span class="sxs-lookup"><span data-stu-id="bf31a-116">You want to see how Defender for Endpoint works before rolling it out in your environment.</span></span>  | [<span data-ttu-id="bf31a-117">Microsoft Defender for Endpoint 評估實驗室</span><span class="sxs-lookup"><span data-stu-id="bf31a-117">Microsoft Defender for Endpoint evaluation lab</span></span>](evaluation-lab.md)   |
| <span data-ttu-id="bf31a-118">您已經有了您的端點，而且您想要讓部分協助取得及設定相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bf31a-118">You already have Defender for Endpoint, and you want some help getting everything set up and configured.</span></span>  | [<span data-ttu-id="bf31a-119">Microsoft Defender for Endpoint 部署指南</span><span class="sxs-lookup"><span data-stu-id="bf31a-119">Microsoft Defender for Endpoint deployment guide</span></span>](deployment-phases.md)  |
| <span data-ttu-id="bf31a-120">您計畫從非 Microsoft endpoint protection 解決方案切換到 endpoint 和 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="bf31a-120">You're planning to switch from a non-Microsoft endpoint protection solution to Defender for Endpoint and Microsoft Defender Antivirus.</span></span> <span data-ttu-id="bf31a-121">您想要大致瞭解遷移程式及如何進行切換。</span><span class="sxs-lookup"><span data-stu-id="bf31a-121">You want to get an overview of the migration process and how to make the switch.</span></span> |[<span data-ttu-id="bf31a-122">將參數設為 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bf31a-122">Make the switch to Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-migration.md)   |
| <span data-ttu-id="bf31a-123">您已遷移或架至 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="bf31a-123">You've already migrated or onboarded to Defender for Endpoint.</span></span> <span data-ttu-id="bf31a-124">您想要在後續步驟中提供一些協助，例如管理安全性設定、設定更多功能或微調安全性原則。</span><span class="sxs-lookup"><span data-stu-id="bf31a-124">You want some help with next steps, such as managing your security settings, configuring more features, or fine-tuning your security policies.</span></span> | [<span data-ttu-id="bf31a-125">管理 Microsoft Defender for Endpoint，遷移後</span><span class="sxs-lookup"><span data-stu-id="bf31a-125">Manage Microsoft Defender for Endpoint, post-migration</span></span>](manage-atp-post-migration.md) |


## <a name="do-you-have-feedback-for-us"></a><span data-ttu-id="bf31a-126">您是否有我們的意見反應？</span><span class="sxs-lookup"><span data-stu-id="bf31a-126">Do you have feedback for us?</span></span>

<span data-ttu-id="bf31a-127">讓我們知道您的想法！</span><span class="sxs-lookup"><span data-stu-id="bf31a-127">Let us know what you think!</span></span> <span data-ttu-id="bf31a-128">在頁面底部提交您的意見反應。</span><span class="sxs-lookup"><span data-stu-id="bf31a-128">Submit your feedback at the bottom of the page.</span></span> <span data-ttu-id="bf31a-129">我們會將您的意見反應納入考慮，我們會繼續改進並新增遷移指南。</span><span class="sxs-lookup"><span data-stu-id="bf31a-129">We'll take your feedback into account as we continue to improve and add to our migration guidance.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf31a-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bf31a-130">See also</span></span>

- [<span data-ttu-id="bf31a-131">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bf31a-131">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
- [<span data-ttu-id="bf31a-132">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bf31a-132">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="bf31a-133">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf31a-133">Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/microsoft-threat-protection?) 
