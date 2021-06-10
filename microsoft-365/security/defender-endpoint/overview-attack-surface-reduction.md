---
title: 攻擊面縮小概觀
ms.reviewer: ''
description: 深入瞭解 Microsoft Defender for Endpoint 的攻擊面減少功能。
keywords: asr，攻擊面降低，Microsoft Defender for Endpoint，microsoft defender，防病毒，av，windows Defender
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
ms.custom: asr
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: b6fb9bb327816b7e166a443a0d07932d30421a19
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771690"
---
# <a name="overview-of-attack-surface-reduction-capabilities"></a><span data-ttu-id="db3e6-104">攻擊面降減功能的概覽</span><span class="sxs-lookup"><span data-stu-id="db3e6-104">Overview of attack surface reduction capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="db3e6-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="db3e6-105">**Applies to:**</span></span>
- [<span data-ttu-id="db3e6-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="db3e6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="db3e6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db3e6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="db3e6-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="db3e6-108">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="db3e6-109">[註冊免費試用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="db3e6-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink).</span></span>

<span data-ttu-id="db3e6-110">您的攻擊面是您的組織容易遭到 cyberthreats 和攻擊的所有地方。</span><span class="sxs-lookup"><span data-stu-id="db3e6-110">Your attack surfaces are all the places where your organization is vulnerable to cyberthreats and attacks.</span></span> <span data-ttu-id="db3e6-111">Defender for Endpoint 包含許多功能，可協助減少攻擊面。</span><span class="sxs-lookup"><span data-stu-id="db3e6-111">Defender for Endpoint includes several capabilities to help reduce your attack surfaces.</span></span> <span data-ttu-id="db3e6-112">觀看下列影片以深入瞭解攻擊面降低。</span><span class="sxs-lookup"><span data-stu-id="db3e6-112">Watch the following video to learn more about attack surface reduction.</span></span><p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]

## <a name="resources-to-learn-more-about-attack-surface-reduction"></a><span data-ttu-id="db3e6-113">深入瞭解攻擊面減少的資源</span><span class="sxs-lookup"><span data-stu-id="db3e6-113">Resources to learn more about attack surface reduction</span></span>

<span data-ttu-id="db3e6-114">如影片中所述，端點的 Defender 包含數個攻擊面降低功能。</span><span class="sxs-lookup"><span data-stu-id="db3e6-114">As mentioned in the video, Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="db3e6-115">請使用下列資源深入瞭解：</span><span class="sxs-lookup"><span data-stu-id="db3e6-115">Use the following resources to learn more:</span></span>

| <span data-ttu-id="db3e6-116">文章</span><span class="sxs-lookup"><span data-stu-id="db3e6-116">Article</span></span> | <span data-ttu-id="db3e6-117">描述</span><span class="sxs-lookup"><span data-stu-id="db3e6-117">Description</span></span> |
|:---|:---|
| [<span data-ttu-id="db3e6-118">硬體隔離</span><span class="sxs-lookup"><span data-stu-id="db3e6-118">Hardware-based isolation</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | <span data-ttu-id="db3e6-119">在啟動和執行時，保護及維護系統的完整性。</span><span class="sxs-lookup"><span data-stu-id="db3e6-119">Protect and maintain the integrity of a system as it starts and while it's running.</span></span> <span data-ttu-id="db3e6-120">透過地域和遠端認證來驗證系統完整性。</span><span class="sxs-lookup"><span data-stu-id="db3e6-120">Validate system integrity through local and remote attestation.</span></span> <span data-ttu-id="db3e6-121">而且，使用 Microsoft Edge 容器隔離可協助防範惡意網站。</span><span class="sxs-lookup"><span data-stu-id="db3e6-121">And, use container isolation for Microsoft Edge to help guard against malicious websites.</span></span> |
| [<span data-ttu-id="db3e6-122">應用程式控制</span><span class="sxs-lookup"><span data-stu-id="db3e6-122">Application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | <span data-ttu-id="db3e6-123">使用應用程式控制，讓應用程式必須獲得信任才能執行。</span><span class="sxs-lookup"><span data-stu-id="db3e6-123">Use application control so that your applications must earn trust in order to run.</span></span> |
| [<span data-ttu-id="db3e6-124">受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="db3e6-124">Controlled folder access</span></span>](controlled-folders.md) | <span data-ttu-id="db3e6-125">協助防止惡意或可疑的應用程式 (包括檔案加密的勒索軟體) 惡意軟體變更您的重要系統資料夾中的檔案 (需要 Microsoft Defender 防毒軟體) </span><span class="sxs-lookup"><span data-stu-id="db3e6-125">Help prevent malicious or suspicious apps (including file-encrypting ransomware malware) from making changes to files in your key system folders (Requires Microsoft Defender Antivirus)</span></span> |
| [<span data-ttu-id="db3e6-126">網路保護</span><span class="sxs-lookup"><span data-stu-id="db3e6-126">Network protection</span></span>](network-protection.md) | <span data-ttu-id="db3e6-127">將保護功能擴充至組織裝置上的網路流量和連線能力。</span><span class="sxs-lookup"><span data-stu-id="db3e6-127">Extend protection to your network traffic and connectivity on your organization's devices.</span></span> <span data-ttu-id="db3e6-128"> (需要 Microsoft Defender 防毒軟體) </span><span class="sxs-lookup"><span data-stu-id="db3e6-128">(Requires Microsoft Defender Antivirus)</span></span> |
| [<span data-ttu-id="db3e6-129">入侵防護</span><span class="sxs-lookup"><span data-stu-id="db3e6-129">Exploit protection</span></span>](exploit-protection.md) | <span data-ttu-id="db3e6-130">協助保護您組織使用的作業系統和應用程式。</span><span class="sxs-lookup"><span data-stu-id="db3e6-130">Help protect operating systems and apps your organization uses from being exploited.</span></span> <span data-ttu-id="db3e6-131">Exploit protection 也可搭配協力廠商的防病毒解決方案使用。</span><span class="sxs-lookup"><span data-stu-id="db3e6-131">Exploit protection also works with third-party antivirus solutions.</span></span> |
| [<span data-ttu-id="db3e6-132">受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="db3e6-132">Attack surface reduction rules</span></span>](attack-surface-reduction.md) | <span data-ttu-id="db3e6-133">利用可協助阻止惡意程式碼的智慧型規則，減少應用程式中的漏弱點 (攻擊面)。</span><span class="sxs-lookup"><span data-stu-id="db3e6-133">Reduce vulnerabilities (attack surfaces) in your applications with intelligent rules that help stop malware.</span></span> <span data-ttu-id="db3e6-134"> (需要 Microsoft Defender 防毒軟體) 。</span><span class="sxs-lookup"><span data-stu-id="db3e6-134">(Requires Microsoft Defender Antivirus).</span></span> |
| [<span data-ttu-id="db3e6-135">裝置控制</span><span class="sxs-lookup"><span data-stu-id="db3e6-135">Device control</span></span>](device-control-report.md) | <span data-ttu-id="db3e6-136">監視和控制裝置上所使用的媒體，例如組織中的可移動儲存裝置和 USB 磁片磁碟機，以防止資料遺失。</span><span class="sxs-lookup"><span data-stu-id="db3e6-136">Protects against data loss by monitoring and controlling media used on devices, such as removable storage and USB drives, in your organization.</span></span> |