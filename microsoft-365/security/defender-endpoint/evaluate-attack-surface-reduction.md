---
title: 評估受攻擊面縮小規則
description: 請參閱攻擊面降低會如何阻擋並防止使用自訂示範工具進行攻擊。
keywords: 攻擊面減少，hips，主機入侵防護系統，保護規則，反惡意攻擊，antiexploit，exploit，感染防護，評估，測試，示範
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 07573fd92643ce5fdf3e9140031bf5f15ae8f7aa
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570336"
---
# <a name="evaluate-attack-surface-reduction-rules"></a><span data-ttu-id="8cb62-104">評估受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="8cb62-104">Evaluate attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8cb62-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8cb62-105">**Applies to:**</span></span>
- [<span data-ttu-id="8cb62-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8cb62-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="8cb62-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8cb62-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8cb62-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="8cb62-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8cb62-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="8cb62-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="8cb62-110">攻擊面減少規則可協助防止惡意程式碼用來危害裝置或網路的動作。</span><span class="sxs-lookup"><span data-stu-id="8cb62-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span></span> <span data-ttu-id="8cb62-111">設定執行下列任何版本 Windows 之裝置的攻擊面減少規則：</span><span class="sxs-lookup"><span data-stu-id="8cb62-111">Set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="8cb62-112">Windows 10 專業 [版，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="8cb62-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="8cb62-113">Windows 10 企業 [版，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="8cb62-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="8cb62-114">Windows Server， [版本 1803 (半年通道) ](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="8cb62-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="8cb62-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8cb62-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="8cb62-116">瞭解如何透過稽核模式直接在組織中測試功能，以評估攻擊面減少規則。</span><span class="sxs-lookup"><span data-stu-id="8cb62-116">Learn how to evaluate attack surface reduction rules by enabling audit mode to test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="8cb62-117">您也可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Microsoft Defender for Endpoint 示範案例網站，確認該功能是否正常運作，並查看其運作方式。</span><span class="sxs-lookup"><span data-stu-id="8cb62-117">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="8cb62-118">使用稽核模式衡量影響</span><span class="sxs-lookup"><span data-stu-id="8cb62-118">Use audit mode to measure impact</span></span>

<span data-ttu-id="8cb62-119">在稽核模式中啟用攻擊面降低規則，以查看已完全啟用該功能時，已封鎖的應用程式記錄。</span><span class="sxs-lookup"><span data-stu-id="8cb62-119">Enable attack surface reduction rules in audit mode to view a record of apps that would have been blocked if the feature was fully enabled.</span></span> <span data-ttu-id="8cb62-120">測試該功能在組織中的運作方式，以確保其不會影響您的企業營運應用程式。</span><span class="sxs-lookup"><span data-stu-id="8cb62-120">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="8cb62-121">您也可以瞭解規則在正常使用中會觸發的頻率。</span><span class="sxs-lookup"><span data-stu-id="8cb62-121">You can also get an idea of how often the rules will fire during normal use.</span></span>

<span data-ttu-id="8cb62-122">若要在稽核模式中啟用攻擊面降減規則，請使用下列 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8cb62-122">To enable an attack surface reduction rule in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

<span data-ttu-id="8cb62-123">其中 `<rule ID>` 是 [攻擊面降低規則的 GUID 值](attack-surface-reduction.md#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="8cb62-123">Where `<rule ID>` is a [GUID value of the attack surface reduction rule](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

<span data-ttu-id="8cb62-124">若要在稽核模式中啟用所有新增的攻擊面降低規則，請使用下列 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8cb62-124">To enable all the added attack surface reduction rules in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> <span data-ttu-id="8cb62-125">如果您想要完全審核攻擊面降低規則在組織中的運作方式，您必須使用管理工具，將此設定部署至網路中的裝置 (s) 。</span><span class="sxs-lookup"><span data-stu-id="8cb62-125">If you want to fully audit how attack surface reduction rules will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>

<span data-ttu-id="8cb62-126">您也可以使用「群組原則」、「Intune」或「行動裝置管理」 (MDM) configuration service 提供者 (Csp) 來設定及部署設定。</span><span class="sxs-lookup"><span data-stu-id="8cb62-126">You can also use Group Policy, Intune, or mobile device management (MDM) configuration service providers (CSPs) to configure and deploy the setting.</span></span> <span data-ttu-id="8cb62-127">若要深入瞭解，請參閱主要 [攻擊面減少規則](attack-surface-reduction.md) 文章。</span><span class="sxs-lookup"><span data-stu-id="8cb62-127">Learn more in the main [Attack surface reduction rules](attack-surface-reduction.md) article.</span></span>

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="8cb62-128">在 Windows 事件檢視器中查看攻擊面減少事件</span><span class="sxs-lookup"><span data-stu-id="8cb62-128">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="8cb62-129">若要查看已封鎖的應用程式，請在 Microsoft-Windows Defender/運作性記錄檔中開啟事件檢視器並篩選事件識別碼1121。</span><span class="sxs-lookup"><span data-stu-id="8cb62-129">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1121 in the Microsoft-Windows-Windows Defender/Operational log.</span></span> <span data-ttu-id="8cb62-130">下表列出所有網路保護事件。</span><span class="sxs-lookup"><span data-stu-id="8cb62-130">The following table lists all network protection events.</span></span>

<span data-ttu-id="8cb62-131">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="8cb62-131">Event ID</span></span> | <span data-ttu-id="8cb62-132">說明</span><span class="sxs-lookup"><span data-stu-id="8cb62-132">Description</span></span>
-|-
 <span data-ttu-id="8cb62-133">5007</span><span class="sxs-lookup"><span data-stu-id="8cb62-133">5007</span></span> | <span data-ttu-id="8cb62-134">設定變更時的事件</span><span class="sxs-lookup"><span data-stu-id="8cb62-134">Event when settings are changed</span></span>
 <span data-ttu-id="8cb62-135">1121</span><span class="sxs-lookup"><span data-stu-id="8cb62-135">1121</span></span> | <span data-ttu-id="8cb62-136">在封鎖模式中激發攻擊面降低規則時的事件</span><span class="sxs-lookup"><span data-stu-id="8cb62-136">Event when an attack surface reduction rule fires in block mode</span></span>
 <span data-ttu-id="8cb62-137">1122</span><span class="sxs-lookup"><span data-stu-id="8cb62-137">1122</span></span> | <span data-ttu-id="8cb62-138">在稽核模式中引發攻擊面降低規則時的事件</span><span class="sxs-lookup"><span data-stu-id="8cb62-138">Event when an attack surface reduction rule fires in audit mode</span></span>

## <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="8cb62-139">自訂受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="8cb62-139">Customize attack surface reduction rules</span></span>

<span data-ttu-id="8cb62-140">在評估過程中，您可能會想要個別設定每個規則，或排除某些檔案和進程，以供功能評估使用。</span><span class="sxs-lookup"><span data-stu-id="8cb62-140">During your evaluation, you may wish to configure each rule individually or exclude certain files and processes from being evaluated by the feature.</span></span>

<span data-ttu-id="8cb62-141">如需使用管理工具（包括群組原則和 MDM CSP 原則）設定該功能的詳細資訊，請參閱 [自訂攻擊面降規則](customize-attack-surface-reduction.md) 。</span><span class="sxs-lookup"><span data-stu-id="8cb62-141">See [Customize attack surface reduction rules](customize-attack-surface-reduction.md) for information on configuring the feature with management tools, including Group Policy and MDM CSP policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="8cb62-142">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8cb62-142">See also</span></span>

* [<span data-ttu-id="8cb62-143">使用攻擊面減少規則來減少攻擊面</span><span class="sxs-lookup"><span data-stu-id="8cb62-143">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="8cb62-144">使用稽核模式評估 Windows Defender</span><span class="sxs-lookup"><span data-stu-id="8cb62-144">Use audit mode to evaluate Windows Defender</span></span>](audit-windows-defender.md)
* [<span data-ttu-id="8cb62-145">受攻擊面縮小常見問題集</span><span class="sxs-lookup"><span data-stu-id="8cb62-145">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
