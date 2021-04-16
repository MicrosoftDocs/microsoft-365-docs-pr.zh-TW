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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3ad23e030048506784edd8f1988fa33263a085ae
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861332"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="1d0d0-104">設定及管理 Microsoft Defender for Endpoint 功能</span><span class="sxs-lookup"><span data-stu-id="1d0d0-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1d0d0-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="1d0d0-105">**Applies to:**</span></span>

- [<span data-ttu-id="1d0d0-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1d0d0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1d0d0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d0d0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1d0d0-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="1d0d0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1d0d0-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="1d0d0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="1d0d0-110">瞭解如何設定及管理用於端點功能的 Defender，以取得組織的最佳安全性保護。</span><span class="sxs-lookup"><span data-stu-id="1d0d0-110">Learn how to configure and manage Defender for Endpoint features, to get the best security protection for your organization.</span></span>

<span data-ttu-id="1d0d0-111">如需連線組織中新裝置的實際建議，請參閱「 [Microsoft Defender For Endpoint service」的板載裝置](./onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="1d0d0-111">For practical advice on connecting new devices in your organization, see [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1d0d0-112">本節內容</span><span class="sxs-lookup"><span data-stu-id="1d0d0-112">In this section</span></span>

<span data-ttu-id="1d0d0-113">主題</span><span class="sxs-lookup"><span data-stu-id="1d0d0-113">Topic</span></span> | <span data-ttu-id="1d0d0-114">描述</span><span class="sxs-lookup"><span data-stu-id="1d0d0-114">Description</span></span>
:---|:---
[<span data-ttu-id="1d0d0-115">設定 Microsoft Defender 安全性中心設定</span><span class="sxs-lookup"><span data-stu-id="1d0d0-115">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="1d0d0-116">設定與入口相關的設定，例如一般設定、高級功能或啟用預覽體驗。</span><span class="sxs-lookup"><span data-stu-id="1d0d0-116">Configure portal-related settings such as general settings, advanced features, or enable the preview experience.</span></span>
[<span data-ttu-id="1d0d0-117">設定攻擊面降減功能</span><span class="sxs-lookup"><span data-stu-id="1d0d0-117">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) | <span data-ttu-id="1d0d0-118">設定攻擊面降減功能，以確保設定正確套用，並設定 exploit 緩解技術。</span><span class="sxs-lookup"><span data-stu-id="1d0d0-118">Configure attack surface reduction capabilities, to ensure that settings are properly applied, and exploit mitigation techniques are set.</span></span>
[<span data-ttu-id="1d0d0-119">設定下一代保護</span><span class="sxs-lookup"><span data-stu-id="1d0d0-119">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="1d0d0-120">設定下一代保護，以捕捉所有類型的威脅。</span><span class="sxs-lookup"><span data-stu-id="1d0d0-120">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="1d0d0-121">設定 Microsoft 威脅專家功能</span><span class="sxs-lookup"><span data-stu-id="1d0d0-121">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="1d0d0-122">從 Microsoft 威脅專家設定及管理 cybersecurity 威脅智慧。</span><span class="sxs-lookup"><span data-stu-id="1d0d0-122">Configure and manage cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="1d0d0-123">設定 Microsoft 威脅防護整合</span><span class="sxs-lookup"><span data-stu-id="1d0d0-123">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration) | <span data-ttu-id="1d0d0-124">設定其他與 Defender for Endpoint 整合的解決方案。</span><span class="sxs-lookup"><span data-stu-id="1d0d0-124">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="1d0d0-125">管理和 API 支援</span><span class="sxs-lookup"><span data-stu-id="1d0d0-125">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis) | <span data-ttu-id="1d0d0-126">將警示放入您的安全性資訊和事件管理 (SIEM) 或使用 APIs 建立自訂警示。</span><span class="sxs-lookup"><span data-stu-id="1d0d0-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span></span> <span data-ttu-id="1d0d0-127">建立並組建 Power BI 報告。</span><span class="sxs-lookup"><span data-stu-id="1d0d0-127">Create and build Power BI reports.</span></span>
