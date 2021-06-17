---
title: 測試 Microsoft Defender for Endpoint 功能在稽核模式中的運作方式
description: 「稽核模式」可協助您瞭解在啟用裝置時，Microsoft Defender for Endpoint 如何保護您的裝置。
keywords: exploit guard，audit，audit，mode，enabled，disabled，test，demo，評估，實驗室
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 23de13e9a2b0fb02b95c9bb367c3fd99e11e89c8
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985093"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="33e8c-104">在 Microsoft Defender for Endpoint 中測試攻擊面減少</span><span class="sxs-lookup"><span data-stu-id="33e8c-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="33e8c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="33e8c-105">**Applies to:**</span></span>

- [<span data-ttu-id="33e8c-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="33e8c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="33e8c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33e8c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="33e8c-108">在組織的安全性小組中，您可以設定攻擊面減少功能，以在稽核模式中執行，以查看他們的運作方式。</span><span class="sxs-lookup"><span data-stu-id="33e8c-108">As part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work.</span></span> <span data-ttu-id="33e8c-109">在 [稽核模式] 中，您可以啟用：</span><span class="sxs-lookup"><span data-stu-id="33e8c-109">In audit mode, you can enable:</span></span>

- <span data-ttu-id="33e8c-110">受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="33e8c-110">Attack surface reduction rules</span></span>
- <span data-ttu-id="33e8c-111">入侵防護</span><span class="sxs-lookup"><span data-stu-id="33e8c-111">Exploit protection</span></span>
- <span data-ttu-id="33e8c-112">網路保護</span><span class="sxs-lookup"><span data-stu-id="33e8c-112">Network protection</span></span>
- <span data-ttu-id="33e8c-113">和受管理的資料夾存取稽核模式</span><span class="sxs-lookup"><span data-stu-id="33e8c-113">And controlled folder access in audit mode</span></span>

<span data-ttu-id="33e8c-114">「稽核模式」可讓您查看已啟用該功能時， *會* 發生什麼事的記錄。</span><span class="sxs-lookup"><span data-stu-id="33e8c-114">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="33e8c-115">您可以在測試功能的運作方式時啟用稽核模式。</span><span class="sxs-lookup"><span data-stu-id="33e8c-115">You can enable audit mode when testing how the features will work.</span></span> <span data-ttu-id="33e8c-116">這會協助確保您的企業營運應用程式不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="33e8c-116">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="33e8c-117">您也可以瞭解在一段時間內，有多少可疑的檔修改嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="33e8c-117">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="33e8c-118">功能不會封鎖或防止應用程式、腳本或檔案被修改。</span><span class="sxs-lookup"><span data-stu-id="33e8c-118">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="33e8c-119">不過，Windows 事件記錄會將事件記錄為已完全啟用的功能。</span><span class="sxs-lookup"><span data-stu-id="33e8c-119">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="33e8c-120">透過「審計模式」，您可以查看事件記錄檔，以查看該功能在啟用後會有什麼影響。</span><span class="sxs-lookup"><span data-stu-id="33e8c-120">With audit mode, you can review the event log to see what affect the feature would have had if it was enabled.</span></span>

<span data-ttu-id="33e8c-121">若要尋找已審核的專案，請移至 **應用程式和服務**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **運作**。</span><span class="sxs-lookup"><span data-stu-id="33e8c-121">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="33e8c-122">使用 Defender for Endpoint 取得每個事件的詳細資料，尤其是用於調查攻擊面降低規則。</span><span class="sxs-lookup"><span data-stu-id="33e8c-122">Use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="33e8c-123">使用 Defender for Endpoint 主控台，可在 [警示時程表和調查案例中調查問題](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="33e8c-123">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="33e8c-124">您可以使用「群組原則」、「PowerShell」和「設定服務提供者」 (Csp) 來啟用稽核模式。</span><span class="sxs-lookup"><span data-stu-id="33e8c-124">You can enable audit mode using Group Policy, PowerShell, and configuration service providers (CSPs).</span></span>

> [!TIP]
> <span data-ttu-id="33e8c-125">您也可以在[demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)流覽 Windows Defender 的 Testground 網站，確認功能是否正常運作，並查看其運作方式。</span><span class="sxs-lookup"><span data-stu-id="33e8c-125">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="33e8c-126">審核選項</span><span class="sxs-lookup"><span data-stu-id="33e8c-126">Audit options</span></span> | <span data-ttu-id="33e8c-127">如何啟用稽核模式</span><span class="sxs-lookup"><span data-stu-id="33e8c-127">How to enable audit mode</span></span> | <span data-ttu-id="33e8c-128">如何查看事件</span><span class="sxs-lookup"><span data-stu-id="33e8c-128">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="33e8c-129">審核適用于所有事件</span><span class="sxs-lookup"><span data-stu-id="33e8c-129">Audit applies to all events</span></span> | [<span data-ttu-id="33e8c-130">啟用受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="33e8c-130">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="33e8c-131">受控資料夾存取事件</span><span class="sxs-lookup"><span data-stu-id="33e8c-131">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="33e8c-132">審核適用于個別規則</span><span class="sxs-lookup"><span data-stu-id="33e8c-132">Audit applies to individual rules</span></span> | [<span data-ttu-id="33e8c-133">啟用受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="33e8c-133">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="33e8c-134">攻擊面減少規則事件</span><span class="sxs-lookup"><span data-stu-id="33e8c-134">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="33e8c-135">審核適用于所有事件</span><span class="sxs-lookup"><span data-stu-id="33e8c-135">Audit applies to all events</span></span> | [<span data-ttu-id="33e8c-136">啟用網路保護</span><span class="sxs-lookup"><span data-stu-id="33e8c-136">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="33e8c-137">網路保護事件</span><span class="sxs-lookup"><span data-stu-id="33e8c-137">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="33e8c-138">審核適用于個別的緩解</span><span class="sxs-lookup"><span data-stu-id="33e8c-138">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="33e8c-139">啟用入侵防護</span><span class="sxs-lookup"><span data-stu-id="33e8c-139">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="33e8c-140">Exploit protection 事件</span><span class="sxs-lookup"><span data-stu-id="33e8c-140">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
