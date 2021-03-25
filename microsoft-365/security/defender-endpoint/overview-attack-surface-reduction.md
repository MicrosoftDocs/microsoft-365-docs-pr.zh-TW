---
title: 攻擊面減少的概述
ms.reviewer: ''
description: 深入瞭解 Microsoft Defender ATP 的攻擊面減少功能。
keywords: asr、攻擊面減少、microsoft defender atp、microsoft defender （endpoint）、microsoft defender、防毒軟體、av、windows defender
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
ms.openlocfilehash: e4e10ba82ec344449b003c0a9cc9d27d99047005
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186242"
---
# <a name="overview-of-attack-surface-reduction"></a><span data-ttu-id="1cb96-104">攻擊面減少的概述</span><span class="sxs-lookup"><span data-stu-id="1cb96-104">Overview of attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1cb96-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="1cb96-105">**Applies to:**</span></span>
- [<span data-ttu-id="1cb96-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1cb96-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1cb96-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1cb96-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1cb96-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1cb96-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1cb96-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="1cb96-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="1cb96-110">將您的組織易於 cyberthreats 和攻擊的位置降到最低，有助於減少攻擊面。</span><span class="sxs-lookup"><span data-stu-id="1cb96-110">Help reduce your attack surfaces, by minimizing the places where your organization is vulnerable to cyberthreats and attacks.</span></span> <span data-ttu-id="1cb96-111">使用下列資源來設定組織中裝置和應用程式的保護。</span><span class="sxs-lookup"><span data-stu-id="1cb96-111">Use the following resources to configure protection for the devices and applications in your organization.</span></span>


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]


<span data-ttu-id="1cb96-112">文章</span><span class="sxs-lookup"><span data-stu-id="1cb96-112">Article</span></span> | <span data-ttu-id="1cb96-113">描述</span><span class="sxs-lookup"><span data-stu-id="1cb96-113">Description</span></span>
-|-
[<span data-ttu-id="1cb96-114">受攻擊面縮小</span><span class="sxs-lookup"><span data-stu-id="1cb96-114">Attack surface reduction</span></span>](./attack-surface-reduction.md) | <span data-ttu-id="1cb96-115">利用可協助阻止惡意程式碼的智慧型規則，減少應用程式中的漏弱點 (攻擊面)。</span><span class="sxs-lookup"><span data-stu-id="1cb96-115">Reduce vulnerabilities (attack surfaces) in your applications with intelligent rules that help stop malware.</span></span> <span data-ttu-id="1cb96-116"> (需要 Microsoft Defender 防病毒) 。</span><span class="sxs-lookup"><span data-stu-id="1cb96-116">(Requires Microsoft Defender Antivirus).</span></span>
[<span data-ttu-id="1cb96-117">以硬體為基礎的隔離</span><span class="sxs-lookup"><span data-stu-id="1cb96-117">Hardware-based isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | <span data-ttu-id="1cb96-118">在啟動和執行時，保護及維護系統的完整性。</span><span class="sxs-lookup"><span data-stu-id="1cb96-118">Protect and maintain the integrity of a system as it starts and while it's running.</span></span> <span data-ttu-id="1cb96-119">透過地域和遠端認證來驗證系統完整性。</span><span class="sxs-lookup"><span data-stu-id="1cb96-119">Validate system integrity through local and remote attestation.</span></span> <span data-ttu-id="1cb96-120">而且，使用 Microsoft Edge 的容器隔離來協助抵禦惡意網站。</span><span class="sxs-lookup"><span data-stu-id="1cb96-120">And, use container isolation for Microsoft Edge to help guard against malicious websites.</span></span>
[<span data-ttu-id="1cb96-121">應用程式控制</span><span class="sxs-lookup"><span data-stu-id="1cb96-121">Application control</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control.md) | <span data-ttu-id="1cb96-122">使用應用程式控制，讓應用程式必須獲得信任才能執行。</span><span class="sxs-lookup"><span data-stu-id="1cb96-122">Use application control so that your applications must earn trust in order to run.</span></span>
[<span data-ttu-id="1cb96-123">Exploit protection</span><span class="sxs-lookup"><span data-stu-id="1cb96-123">Exploit protection</span></span>](./exploit-protection.md) | <span data-ttu-id="1cb96-124">協助保護您組織使用的作業系統和應用程式。</span><span class="sxs-lookup"><span data-stu-id="1cb96-124">Help protect operating systems and apps your organization uses from being exploited.</span></span> <span data-ttu-id="1cb96-125">Exploit protection 也可搭配協力廠商的防病毒解決方案使用。</span><span class="sxs-lookup"><span data-stu-id="1cb96-125">Exploit protection also works with third-party antivirus solutions.</span></span>
[<span data-ttu-id="1cb96-126">網路保護</span><span class="sxs-lookup"><span data-stu-id="1cb96-126">Network protection</span></span>](./network-protection.md) | <span data-ttu-id="1cb96-127">將保護功能擴充至組織裝置上的網路流量和連線能力。</span><span class="sxs-lookup"><span data-stu-id="1cb96-127">Extend protection to your network traffic and connectivity on your organization's devices.</span></span> <span data-ttu-id="1cb96-128"> (需要 Microsoft Defender 防病毒) </span><span class="sxs-lookup"><span data-stu-id="1cb96-128">(Requires Microsoft Defender Antivirus)</span></span>
[<span data-ttu-id="1cb96-129">Web 保護</span><span class="sxs-lookup"><span data-stu-id="1cb96-129">Web protection</span></span>](./web-protection-overview.md) | <span data-ttu-id="1cb96-130">保護您的裝置免受網頁威脅，並協助您控制不想要的內容。</span><span class="sxs-lookup"><span data-stu-id="1cb96-130">Secure your devices against web threats and help you regulate unwanted content.</span></span>
[<span data-ttu-id="1cb96-131">受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="1cb96-131">Controlled folder access</span></span>](./controlled-folders.md) | <span data-ttu-id="1cb96-132">協助防止惡意或可疑的應用程式 (包括檔案加密的勒索軟體) 惡意軟體變更您的重要系統資料夾中的檔案， (需要 Microsoft Defender 防毒軟體) </span><span class="sxs-lookup"><span data-stu-id="1cb96-132">Help prevent malicious or suspicious apps (including file-encrypting ransomware malware) from making changes to files in your key system folders (Requires Microsoft Defender Antivirus)</span></span>
[<span data-ttu-id="1cb96-133">網路防火牆</span><span class="sxs-lookup"><span data-stu-id="1cb96-133">Network firewall</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security.md) | <span data-ttu-id="1cb96-134">防止未經授權的流量透過雙向網路流量篩選，流向或從組織的裝置。</span><span class="sxs-lookup"><span data-stu-id="1cb96-134">Prevent unauthorized traffic from flowing to or from your organization's devices with two-way network traffic filtering.</span></span>
[<span data-ttu-id="1cb96-135">攻擊面減少常見問題</span><span class="sxs-lookup"><span data-stu-id="1cb96-135">Attack surface reduction FAQ</span></span>](./attack-surface-reduction-faq.md) | <span data-ttu-id="1cb96-136">有關攻擊面減少規則、授權等等的常見問題。</span><span class="sxs-lookup"><span data-stu-id="1cb96-136">Frequently asked questions about Attack surface reduction rules, licensing, and more.</span></span>
