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
ms.openlocfilehash: c2ff6eac3254e855d4858edc218ae5df034352e4
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925648"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="8ad5f-104">在 Microsoft Defender for Endpoint 中測試攻擊面減少</span><span class="sxs-lookup"><span data-stu-id="8ad5f-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8ad5f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8ad5f-105">**Applies to:**</span></span>
- [<span data-ttu-id="8ad5f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8ad5f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="8ad5f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ad5f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="8ad5f-108">如果您是組織的安全性小組的一部分，您可以設定攻擊面降低功能，以在稽核模式中執行，以查看他們在組織中的運作方式。</span><span class="sxs-lookup"><span data-stu-id="8ad5f-108">If you're part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work in your organization.</span></span> <span data-ttu-id="8ad5f-109">尤其是，您可以在稽核模式中啟用攻擊面降減規則、exploit protection、網路保護和受管理的資料夾存取。</span><span class="sxs-lookup"><span data-stu-id="8ad5f-109">In particular, you can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="8ad5f-110">「稽核模式」可讓您查看已啟用該功能時， *會* 發生什麼事的記錄。</span><span class="sxs-lookup"><span data-stu-id="8ad5f-110">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="8ad5f-111">在測試功能在組織中的運作方式時，您可能會想要啟用稽核模式。</span><span class="sxs-lookup"><span data-stu-id="8ad5f-111">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="8ad5f-112">這會協助確保您的企業營運應用程式不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="8ad5f-112">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="8ad5f-113">您也可以瞭解在一段時間內，有多少可疑的檔修改嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="8ad5f-113">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="8ad5f-114">功能不會封鎖或防止應用程式、腳本或檔案被修改。</span><span class="sxs-lookup"><span data-stu-id="8ad5f-114">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="8ad5f-115">不過，Windows 事件記錄會將事件記錄為已完全啟用的功能。</span><span class="sxs-lookup"><span data-stu-id="8ad5f-115">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="8ad5f-116">透過「審計模式」，您可以查看事件記錄檔，以查看該功能在啟用時的影響。</span><span class="sxs-lookup"><span data-stu-id="8ad5f-116">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="8ad5f-117">若要尋找已審核的專案，請移至 **應用程式和服務**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **運作**。</span><span class="sxs-lookup"><span data-stu-id="8ad5f-117">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="8ad5f-118">您可以使用 Defender for Endpoint 來取得每個事件的詳細資料，尤其是用於調查攻擊面降低規則。</span><span class="sxs-lookup"><span data-stu-id="8ad5f-118">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="8ad5f-119">使用 Defender for Endpoint 主控台，可在 [警示時程表和調查案例中調查問題](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="8ad5f-119">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="8ad5f-120">您可以使用「群組原則」、「PowerShell」和「設定服務提供者」 (Csp) 來啟用稽核模式。</span><span class="sxs-lookup"><span data-stu-id="8ad5f-120">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="8ad5f-121">您也可以在[demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)流覽 Windows Defender 的 Testground 網站，確認功能是否正常運作，並查看其運作方式。</span><span class="sxs-lookup"><span data-stu-id="8ad5f-121">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="8ad5f-122">審核選項</span><span class="sxs-lookup"><span data-stu-id="8ad5f-122">Audit options</span></span> | <span data-ttu-id="8ad5f-123">如何啟用稽核模式</span><span class="sxs-lookup"><span data-stu-id="8ad5f-123">How to enable audit mode</span></span> | <span data-ttu-id="8ad5f-124">如何查看事件</span><span class="sxs-lookup"><span data-stu-id="8ad5f-124">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="8ad5f-125">審核適用于所有事件</span><span class="sxs-lookup"><span data-stu-id="8ad5f-125">Audit applies to all events</span></span> | [<span data-ttu-id="8ad5f-126">啟用受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="8ad5f-126">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="8ad5f-127">受控資料夾存取事件</span><span class="sxs-lookup"><span data-stu-id="8ad5f-127">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="8ad5f-128">審核適用于個別規則</span><span class="sxs-lookup"><span data-stu-id="8ad5f-128">Audit applies to individual rules</span></span> | [<span data-ttu-id="8ad5f-129">啟用受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="8ad5f-129">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="8ad5f-130">攻擊面減少規則事件</span><span class="sxs-lookup"><span data-stu-id="8ad5f-130">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="8ad5f-131">審核適用于所有事件</span><span class="sxs-lookup"><span data-stu-id="8ad5f-131">Audit applies to all events</span></span> | [<span data-ttu-id="8ad5f-132">啟用網路保護</span><span class="sxs-lookup"><span data-stu-id="8ad5f-132">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="8ad5f-133">網路保護事件</span><span class="sxs-lookup"><span data-stu-id="8ad5f-133">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="8ad5f-134">審核適用于個別的緩解</span><span class="sxs-lookup"><span data-stu-id="8ad5f-134">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="8ad5f-135">啟用入侵防護</span><span class="sxs-lookup"><span data-stu-id="8ad5f-135">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="8ad5f-136">Exploit protection 事件</span><span class="sxs-lookup"><span data-stu-id="8ad5f-136">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)


