---
title: 設定攻擊面降減功能
description: 使用 Microsoft Intune、Microsoft Endpoint Configuration Manager、PowerShell Cmdlet 及群組原則來設定攻擊面降低。
keywords: asr、攻擊面減少、windows defender、microsoft defender、防毒軟體、av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: d2f984e21338e2f9a4ed579cde2d74339031d649
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770958"
---
# <a name="configure-attack-surface-reduction-capabilities"></a><span data-ttu-id="5c898-104">設定攻擊面降減功能</span><span class="sxs-lookup"><span data-stu-id="5c898-104">Configure attack surface reduction capabilities</span></span>

<span data-ttu-id="5c898-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="5c898-105">**Applies to:**</span></span>
- [<span data-ttu-id="5c898-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5c898-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5c898-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c898-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="5c898-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="5c898-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="5c898-109">[註冊免費試用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="5c898-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="5c898-110">Defender for Endpoint 包含數個攻擊面降低功能。</span><span class="sxs-lookup"><span data-stu-id="5c898-110">Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="5c898-111">若要深入瞭解，請參閱 [攻擊面降減功能](overview-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="5c898-111">To learn more, see [Overview of attack surface reduction capabilities](overview-attack-surface-reduction.md).</span></span> <span data-ttu-id="5c898-112">若要設定環境中的攻擊面減少，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="5c898-112">To configure attack surface reduction in your environment, follow these steps:</span></span> 

1. <span data-ttu-id="5c898-113">[為 Microsoft Edge 啟用硬體型隔離](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)。</span><span class="sxs-lookup"><span data-stu-id="5c898-113">[Enable hardware-based isolation for Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).</span></span>

2. <span data-ttu-id="5c898-114">啟用應用程式控制。</span><span class="sxs-lookup"><span data-stu-id="5c898-114">Enable application control.</span></span> 

   1. <span data-ttu-id="5c898-115">在 Windows 中檢查基底原則。</span><span class="sxs-lookup"><span data-stu-id="5c898-115">Review base policies in Windows.</span></span> <span data-ttu-id="5c898-116">請參閱 [範例基底原則](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)。</span><span class="sxs-lookup"><span data-stu-id="5c898-116">See [example base policies](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).</span></span>
   2. <span data-ttu-id="5c898-117">請參閱 [應用程式控制項設計指南](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)。</span><span class="sxs-lookup"><span data-stu-id="5c898-117">See the [application control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).</span></span>
   3. <span data-ttu-id="5c898-118">請參閱 [應用程式控制項設計指南](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)。</span><span class="sxs-lookup"><span data-stu-id="5c898-118">Refer to the [application control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).</span></span>

3. <span data-ttu-id="5c898-119">[啟用可控資料夾存取](enable-controlled-folders.md)。</span><span class="sxs-lookup"><span data-stu-id="5c898-119">[Enable controlled folder access](enable-controlled-folders.md).</span></span>

4. <span data-ttu-id="5c898-120">[開啟網路保護](enable-network-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="5c898-120">[Turn on Network protection](enable-network-protection.md).</span></span>

5. <span data-ttu-id="5c898-121">[啟用 exploit protection](enable-exploit-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="5c898-121">[Enable exploit protection](enable-exploit-protection.md).</span></span>

6. <span data-ttu-id="5c898-122">[設定攻擊面減少規則](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="5c898-122">[Configure attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

7. <span data-ttu-id="5c898-123">設定網路防火牆。</span><span class="sxs-lookup"><span data-stu-id="5c898-123">Set up your network firewall.</span></span>

   1. <span data-ttu-id="5c898-124">深入瞭解[具有高級安全性的 Windows Defender 防火牆](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。</span><span class="sxs-lookup"><span data-stu-id="5c898-124">Get an overview of [Windows Defender Firewall with advanced security](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span>
   2. <span data-ttu-id="5c898-125">使用[Windows Defender 防火牆設計指南](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide)決定您要如何設計防火牆原則。</span><span class="sxs-lookup"><span data-stu-id="5c898-125">Use the [Windows Defender Firewall design guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) to decide how you want to design your firewall policies.</span></span>
   3. <span data-ttu-id="5c898-126">使用「 [Windows Defender 防火牆部署指南](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)」，設定您組織的具有高級安全性的防火牆。</span><span class="sxs-lookup"><span data-stu-id="5c898-126">Use the [Windows Defender Firewall deployment guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) to set up your organization's firewall with advanced security.</span></span> 

> [!TIP]
> <span data-ttu-id="5c898-127">在大多數情況下，當您設定攻擊面降減功能時，您可以選擇下列方法：</span><span class="sxs-lookup"><span data-stu-id="5c898-127">In most cases, when you configure attack surface reduction capabilities, you can choose from among several methods:</span></span>
> - <span data-ttu-id="5c898-128">Microsoft 端點管理員 (包含 Microsoft Intune 及 Microsoft Endpoint Configuration Manager) </span><span class="sxs-lookup"><span data-stu-id="5c898-128">Microsoft Endpoint Manager (which now includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
> - <span data-ttu-id="5c898-129">群組原則</span><span class="sxs-lookup"><span data-stu-id="5c898-129">Group Policy</span></span>
> - <span data-ttu-id="5c898-130">PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="5c898-130">PowerShell cmdlets</span></span>
