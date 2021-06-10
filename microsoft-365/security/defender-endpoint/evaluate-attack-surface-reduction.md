---
title: 評估受攻擊面縮小規則
description: 請參閱攻擊面降低會如何阻擋並防止使用自訂示範工具進行攻擊。
keywords: 攻擊面減少，hips，主機入侵防護系統，保護規則，反惡意攻擊，antiexploit，exploit，感染防護，評估，測試，示範
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: c2dea22cc8a0ebb875f83ebd5a3e42f723e5f254
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771318"
---
# <a name="evaluate-attack-surface-reduction-rules"></a><span data-ttu-id="0ac39-104">評估受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="0ac39-104">Evaluate attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0ac39-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="0ac39-105">**Applies to:**</span></span>

- [<span data-ttu-id="0ac39-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0ac39-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="0ac39-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ac39-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0ac39-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="0ac39-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0ac39-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="0ac39-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="0ac39-110">攻擊面減少規則可協助防止惡意程式碼用來危害裝置或網路的動作。</span><span class="sxs-lookup"><span data-stu-id="0ac39-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span></span> <span data-ttu-id="0ac39-111">攻擊面減少規則可協助關閉惡意程式碼和勒索軟體所使用的許多一般進入點。</span><span class="sxs-lookup"><span data-stu-id="0ac39-111">Attack surface reduction rules help close off many of the common entry points used by malware and ransomware.</span></span> 

<span data-ttu-id="0ac39-112">設定執行下列任何版本及版本 Windows 之裝置的攻擊面減少規則：</span><span class="sxs-lookup"><span data-stu-id="0ac39-112">Set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="0ac39-113">Windows 10 專業版，[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本</span><span class="sxs-lookup"><span data-stu-id="0ac39-113">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="0ac39-114">Windows 10 企業版，[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本</span><span class="sxs-lookup"><span data-stu-id="0ac39-114">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="0ac39-115">Windows伺服器，[版本 1803 (半年通道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更新版本</span><span class="sxs-lookup"><span data-stu-id="0ac39-115">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="0ac39-116">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="0ac39-116">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="0ac39-117">瞭解如何透過稽核模式直接在組織中測試功能，以評估攻擊面減少規則。</span><span class="sxs-lookup"><span data-stu-id="0ac39-117">Learn how to evaluate attack surface reduction rules by enabling audit mode to test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="0ac39-118">您也可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Microsoft Defender for Endpoint 示範案例網站，確認該功能是否正常運作，並查看其運作方式。</span><span class="sxs-lookup"><span data-stu-id="0ac39-118">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="0ac39-119">使用稽核模式衡量影響</span><span class="sxs-lookup"><span data-stu-id="0ac39-119">Use audit mode to measure impact</span></span>

<span data-ttu-id="0ac39-120">在稽核模式中啟用攻擊面降低規則，以查看已完全啟用該功能時，已封鎖的應用程式記錄。</span><span class="sxs-lookup"><span data-stu-id="0ac39-120">Enable attack surface reduction rules in audit mode to view a record of apps that would have been blocked if the feature was fully enabled.</span></span> <span data-ttu-id="0ac39-121">測試該功能在組織中的運作方式，以確保其不會影響您的企業營運應用程式。</span><span class="sxs-lookup"><span data-stu-id="0ac39-121">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="0ac39-122">您也可以瞭解規則在正常使用中會觸發的頻率。</span><span class="sxs-lookup"><span data-stu-id="0ac39-122">You can also get an idea of how often the rules will fire during normal use.</span></span>

<span data-ttu-id="0ac39-123">若要在稽核模式中啟用攻擊面降減規則，請使用下列 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0ac39-123">To enable an attack surface reduction rule in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

<span data-ttu-id="0ac39-124">其中 `<rule ID>` 是 [攻擊面降低規則的 GUID 值](attack-surface-reduction.md#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="0ac39-124">Where `<rule ID>` is a [GUID value of the attack surface reduction rule](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

<span data-ttu-id="0ac39-125">若要在稽核模式中啟用所有新增的攻擊面降低規則，請使用下列 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0ac39-125">To enable all the added attack surface reduction rules in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> <span data-ttu-id="0ac39-126">如果您想要完全審核攻擊面降低規則在組織中的運作方式，您必須使用管理工具，將此設定部署至網路中的裝置 (s) 。</span><span class="sxs-lookup"><span data-stu-id="0ac39-126">If you want to fully audit how attack surface reduction rules will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>

<span data-ttu-id="0ac39-127">您也可以使用「群組原則」、「Intune」或「行動裝置管理」 (MDM) configuration service 提供者 (Csp) 來設定及部署設定。</span><span class="sxs-lookup"><span data-stu-id="0ac39-127">You can also use Group Policy, Intune, or mobile device management (MDM) configuration service providers (CSPs) to configure and deploy the setting.</span></span> <span data-ttu-id="0ac39-128">若要深入瞭解，請參閱主要 [攻擊面減少規則](attack-surface-reduction.md) 文章。</span><span class="sxs-lookup"><span data-stu-id="0ac39-128">Learn more in the main [Attack surface reduction rules](attack-surface-reduction.md) article.</span></span>

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="0ac39-129">在 Windows 事件檢視器中查看攻擊面降低事件</span><span class="sxs-lookup"><span data-stu-id="0ac39-129">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="0ac39-130">若要查看已封鎖的應用程式，請在 Microsoft Windows Windows Defender/Operational 記錄中開啟事件檢視器並篩選事件識別碼1121。</span><span class="sxs-lookup"><span data-stu-id="0ac39-130">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1121 in the Microsoft-Windows-Windows Defender/Operational log.</span></span> <span data-ttu-id="0ac39-131">下表列出所有網路保護事件。</span><span class="sxs-lookup"><span data-stu-id="0ac39-131">The following table lists all network protection events.</span></span>

<span data-ttu-id="0ac39-132">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="0ac39-132">Event ID</span></span> | <span data-ttu-id="0ac39-133">描述</span><span class="sxs-lookup"><span data-stu-id="0ac39-133">Description</span></span>
-|-
 <span data-ttu-id="0ac39-134">5007</span><span class="sxs-lookup"><span data-stu-id="0ac39-134">5007</span></span> | <span data-ttu-id="0ac39-135">設定變更時的事件</span><span class="sxs-lookup"><span data-stu-id="0ac39-135">Event when settings are changed</span></span>
 <span data-ttu-id="0ac39-136">1121</span><span class="sxs-lookup"><span data-stu-id="0ac39-136">1121</span></span> | <span data-ttu-id="0ac39-137">在封鎖模式中激發攻擊面降低規則時的事件</span><span class="sxs-lookup"><span data-stu-id="0ac39-137">Event when an attack surface reduction rule fires in block mode</span></span>
 <span data-ttu-id="0ac39-138">1122</span><span class="sxs-lookup"><span data-stu-id="0ac39-138">1122</span></span> | <span data-ttu-id="0ac39-139">在稽核模式中引發攻擊面降低規則時的事件</span><span class="sxs-lookup"><span data-stu-id="0ac39-139">Event when an attack surface reduction rule fires in audit mode</span></span>

## <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="0ac39-140">自訂受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="0ac39-140">Customize attack surface reduction rules</span></span>

<span data-ttu-id="0ac39-141">在評估過程中，您可能會想要個別設定每個規則，或排除某些檔案和進程，以供功能評估使用。</span><span class="sxs-lookup"><span data-stu-id="0ac39-141">During your evaluation, you may wish to configure each rule individually or exclude certain files and processes from being evaluated by the feature.</span></span>

<span data-ttu-id="0ac39-142">如需使用管理工具（包括群組原則和 MDM CSP 原則）設定該功能的詳細資訊，請參閱 [自訂攻擊面降規則](customize-attack-surface-reduction.md) 。</span><span class="sxs-lookup"><span data-stu-id="0ac39-142">See [Customize attack surface reduction rules](customize-attack-surface-reduction.md) for information on configuring the feature with management tools, including Group Policy and MDM CSP policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ac39-143">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0ac39-143">See also</span></span>

* [<span data-ttu-id="0ac39-144">使用攻擊面減少規則來減少攻擊面</span><span class="sxs-lookup"><span data-stu-id="0ac39-144">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="0ac39-145">使用稽核模式評估 Windows Defender</span><span class="sxs-lookup"><span data-stu-id="0ac39-145">Use audit mode to evaluate Windows Defender</span></span>](audit-windows-defender.md)
* [<span data-ttu-id="0ac39-146">受攻擊面縮小常見問題集</span><span class="sxs-lookup"><span data-stu-id="0ac39-146">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
