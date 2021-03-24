---
title: 設定及管理 Microsoft Defender ATP 功能
ms.reviewer: ''
description: 設定及管理 Microsoft Defender ATP 功能，例如攻擊面減少，以及下一代保護
keywords: 設定、管理、功能、攻擊面降低、下一代保護、安全性控制、端點偵測和回應、自動調查和修正、安全性控制項、控制項
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e2082929cf1fb7f4b55331cf62adcd9b936168d0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056811"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="02b36-104">設定及管理 Microsoft Defender for Endpoint 功能</span><span class="sxs-lookup"><span data-stu-id="02b36-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="02b36-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="02b36-105">**Applies to:**</span></span>
- [<span data-ttu-id="02b36-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="02b36-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="02b36-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02b36-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="02b36-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="02b36-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="02b36-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="02b36-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="02b36-110">設定及管理所有的 Defender for Endpoint 功能，以取得組織的最佳安全性保護。</span><span class="sxs-lookup"><span data-stu-id="02b36-110">Configure and manage all the Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="02b36-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="02b36-111">In this section</span></span> 
<span data-ttu-id="02b36-112">主題</span><span class="sxs-lookup"><span data-stu-id="02b36-112">Topic</span></span> | <span data-ttu-id="02b36-113">描述</span><span class="sxs-lookup"><span data-stu-id="02b36-113">Description</span></span> 
:---|:---
[<span data-ttu-id="02b36-114">設定攻擊面降減功能</span><span class="sxs-lookup"><span data-stu-id="02b36-114">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) |  <span data-ttu-id="02b36-115">透過確定設定設定正確，並套用利用緩解技術，這些功能可讓攻擊和利用。</span><span class="sxs-lookup"><span data-stu-id="02b36-115">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="02b36-116">設定下一代保護</span><span class="sxs-lookup"><span data-stu-id="02b36-116">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="02b36-117">設定下一代保護，以捕捉所有類型的威脅。</span><span class="sxs-lookup"><span data-stu-id="02b36-117">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="02b36-118">設定 Microsoft 威脅專家功能</span><span class="sxs-lookup"><span data-stu-id="02b36-118">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="02b36-119">設定和管理您想要如何從 Microsoft 威脅專家取得 cybersecurity 威脅情報。</span><span class="sxs-lookup"><span data-stu-id="02b36-119">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="02b36-120">設定 Microsoft 威脅防護整合</span><span class="sxs-lookup"><span data-stu-id="02b36-120">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration)| <span data-ttu-id="02b36-121">設定其他與 Defender for Endpoint 整合的解決方案。</span><span class="sxs-lookup"><span data-stu-id="02b36-121">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="02b36-122">管理和 API 支援</span><span class="sxs-lookup"><span data-stu-id="02b36-122">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis)| <span data-ttu-id="02b36-123">將提醒納入您的 SIEM，或使用 APIs 建立自訂警示。</span><span class="sxs-lookup"><span data-stu-id="02b36-123">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="02b36-124">建立並組建 Power BI 報告。</span><span class="sxs-lookup"><span data-stu-id="02b36-124">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="02b36-125">設定 Microsoft Defender 安全性中心設定</span><span class="sxs-lookup"><span data-stu-id="02b36-125">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) |  <span data-ttu-id="02b36-126">設定與入口相關的設定，例如一般設定、高級功能、啟用預覽體驗和其他。</span><span class="sxs-lookup"><span data-stu-id="02b36-126">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



