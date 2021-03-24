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
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: dda0e58e587add2693f8448dd0833ce17706786c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059939"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a><span data-ttu-id="47f2f-104">測試 Microsoft Defender for Endpoint 功能在稽核模式中的運作方式</span><span class="sxs-lookup"><span data-stu-id="47f2f-104">Test how Microsoft Defender for Endpoint features work in audit mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="47f2f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="47f2f-105">**Applies to:**</span></span>
- [<span data-ttu-id="47f2f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="47f2f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="47f2f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="47f2f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="47f2f-108">您可以在稽核模式中啟用攻擊面降減規則、exploit protection、網路保護和受管理的資料夾存取。</span><span class="sxs-lookup"><span data-stu-id="47f2f-108">You can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="47f2f-109">「稽核模式」可讓您查看已啟用該功能時， *會* 發生什麼事的記錄。</span><span class="sxs-lookup"><span data-stu-id="47f2f-109">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="47f2f-110">在測試功能在組織中的運作方式時，您可能會想要啟用稽核模式。</span><span class="sxs-lookup"><span data-stu-id="47f2f-110">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="47f2f-111">這會協助確保您的企業營運應用程式不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="47f2f-111">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="47f2f-112">您也可以瞭解在一段時間內，有多少可疑的檔修改嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="47f2f-112">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="47f2f-113">功能不會封鎖或防止應用程式、腳本或檔案被修改。</span><span class="sxs-lookup"><span data-stu-id="47f2f-113">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="47f2f-114">不過，Windows 事件記錄會記錄事件，就好像已完全啟用這些功能。</span><span class="sxs-lookup"><span data-stu-id="47f2f-114">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="47f2f-115">透過「審計模式」，您可以查看事件記錄檔，以查看該功能在啟用時的影響。</span><span class="sxs-lookup"><span data-stu-id="47f2f-115">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="47f2f-116">若要尋找已審核的專案，請移至 **應用程式和服務**  >  **Microsoft**  >  **windows**  >  **windows Defender**  >  **運作**。</span><span class="sxs-lookup"><span data-stu-id="47f2f-116">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="47f2f-117">您可以使用 Defender for Endpoint 來取得每個事件的詳細資料，尤其是用於調查攻擊面降低規則。</span><span class="sxs-lookup"><span data-stu-id="47f2f-117">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="47f2f-118">使用 Defender for Endpoint 主控台，可在 [警示時程表和調查案例中調查問題](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="47f2f-118">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="47f2f-119">您可以使用「群組原則」、「PowerShell」和「設定服務提供者」 (Csp) 來啟用稽核模式。</span><span class="sxs-lookup"><span data-stu-id="47f2f-119">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="47f2f-120">您也可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Windows Defender Testground 網站，確認功能是否正常運作，並查看其運作方式。</span><span class="sxs-lookup"><span data-stu-id="47f2f-120">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="47f2f-121">**審核選項**</span><span class="sxs-lookup"><span data-stu-id="47f2f-121">**Audit options**</span></span> | <span data-ttu-id="47f2f-122">**如何啟用稽核模式**</span><span class="sxs-lookup"><span data-stu-id="47f2f-122">**How to enable audit mode**</span></span> | <span data-ttu-id="47f2f-123">**如何查看事件**</span><span class="sxs-lookup"><span data-stu-id="47f2f-123">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="47f2f-124">審核適用于所有事件</span><span class="sxs-lookup"><span data-stu-id="47f2f-124">Audit applies to all events</span></span> | [<span data-ttu-id="47f2f-125">啟用受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="47f2f-125">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="47f2f-126">受控資料夾存取事件</span><span class="sxs-lookup"><span data-stu-id="47f2f-126">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="47f2f-127">審核適用于個別規則</span><span class="sxs-lookup"><span data-stu-id="47f2f-127">Audit applies to individual rules</span></span> | [<span data-ttu-id="47f2f-128">啟用攻擊面減少規則</span><span class="sxs-lookup"><span data-stu-id="47f2f-128">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="47f2f-129">攻擊面減少規則事件</span><span class="sxs-lookup"><span data-stu-id="47f2f-129">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="47f2f-130">審核適用于所有事件</span><span class="sxs-lookup"><span data-stu-id="47f2f-130">Audit applies to all events</span></span> | [<span data-ttu-id="47f2f-131">啟用網路保護</span><span class="sxs-lookup"><span data-stu-id="47f2f-131">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="47f2f-132">網路保護事件</span><span class="sxs-lookup"><span data-stu-id="47f2f-132">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="47f2f-133">審核適用于個別的緩解</span><span class="sxs-lookup"><span data-stu-id="47f2f-133">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="47f2f-134">啟用 exploit protection</span><span class="sxs-lookup"><span data-stu-id="47f2f-134">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="47f2f-135">Exploit protection 事件</span><span class="sxs-lookup"><span data-stu-id="47f2f-135">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a><span data-ttu-id="47f2f-136">相關主題</span><span class="sxs-lookup"><span data-stu-id="47f2f-136">Related topics</span></span>

* [<span data-ttu-id="47f2f-137">保護裝置免受攻擊</span><span class="sxs-lookup"><span data-stu-id="47f2f-137">Protect devices from exploits</span></span>](exploit-protection.md)
* [<span data-ttu-id="47f2f-138">使用攻擊面減少規則來減少攻擊面</span><span class="sxs-lookup"><span data-stu-id="47f2f-138">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="47f2f-139">保護您的網路</span><span class="sxs-lookup"><span data-stu-id="47f2f-139">Protect your network</span></span>](network-protection.md)
* [<span data-ttu-id="47f2f-140">保護重要的資料夾</span><span class="sxs-lookup"><span data-stu-id="47f2f-140">Protect important folders</span></span>](controlled-folders.md)
