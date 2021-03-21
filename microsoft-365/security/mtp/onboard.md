---
title: 設定及管理 Microsoft Defender for Endpoint 功能
ms.reviewer: ''
description: 設定及管理 Microsoft Defender for Endpoint 功能（例如攻擊面降低和下一代保護）
keywords: 設定、管理、功能、攻擊面降低、下一代保護、安全性控制、端點偵測和回應、自動調查和修正、安全性控制項、控制項
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c3bb09820f4a22c8ecb1e49c699db5b6f4cabc68
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928613"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="6d40a-104">設定及管理 Microsoft Defender for Endpoint 功能</span><span class="sxs-lookup"><span data-stu-id="6d40a-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6d40a-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="6d40a-105">**Applies to:**</span></span>

- [<span data-ttu-id="6d40a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6d40a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="6d40a-107">設定及管理所有 Microsoft Defender for Endpoint 功能，以取得組織的最佳安全性保護。</span><span class="sxs-lookup"><span data-stu-id="6d40a-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="6d40a-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="6d40a-108">In this section</span></span> 
<span data-ttu-id="6d40a-109">主題</span><span class="sxs-lookup"><span data-stu-id="6d40a-109">Topic</span></span> | <span data-ttu-id="6d40a-110">描述</span><span class="sxs-lookup"><span data-stu-id="6d40a-110">Description</span></span> 
:---|:---
[<span data-ttu-id="6d40a-111">設定攻擊面降減功能</span><span class="sxs-lookup"><span data-stu-id="6d40a-111">Configure attack surface reduction capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="6d40a-112">透過確定設定設定正確，並套用利用緩解技術，這些功能可讓攻擊和利用。</span><span class="sxs-lookup"><span data-stu-id="6d40a-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="6d40a-113">設定下一代保護</span><span class="sxs-lookup"><span data-stu-id="6d40a-113">Configure next generation protection</span></span>](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="6d40a-114">設定下一代保護以捕捉所有的新興威脅類型。</span><span class="sxs-lookup"><span data-stu-id="6d40a-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="6d40a-115">設定 Microsoft 威脅專家功能</span><span class="sxs-lookup"><span data-stu-id="6d40a-115">Configure Microsoft Threat Experts capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="6d40a-116">設定和管理您想要如何從 Microsoft 威脅專家取得 cybersecurity 威脅情報。</span><span class="sxs-lookup"><span data-stu-id="6d40a-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="6d40a-117">設定 Microsoft 365 Defender 整合</span><span class="sxs-lookup"><span data-stu-id="6d40a-117">Configure Microsoft 365 Defender integration</span></span>](/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="6d40a-118">設定與 Microsoft Defender for Endpoint 整合的其他解決方案。</span><span class="sxs-lookup"><span data-stu-id="6d40a-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="6d40a-119">管理和 API 支援</span><span class="sxs-lookup"><span data-stu-id="6d40a-119">Management and API support</span></span>](/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="6d40a-120">將提醒納入您的 SIEM，或使用 APIs 建立自訂警示。</span><span class="sxs-lookup"><span data-stu-id="6d40a-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="6d40a-121">建立並組建 Power BI 報告。</span><span class="sxs-lookup"><span data-stu-id="6d40a-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="6d40a-122">設定 Microsoft Defender 安全性中心設定</span><span class="sxs-lookup"><span data-stu-id="6d40a-122">Configure Microsoft Defender Security Center settings</span></span>](/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="6d40a-123">設定與入口相關的設定，例如一般設定、高級功能、啟用預覽體驗和其他。</span><span class="sxs-lookup"><span data-stu-id="6d40a-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>