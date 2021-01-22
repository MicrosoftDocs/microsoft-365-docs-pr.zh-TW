---
title: 設定及管理端點功能的 Microsoft Defender
ms.reviewer: ''
description: 設定及管理 Microsoft Defender 端點功能，例如攻擊面縮減及新一代保護
keywords: 設定、管理、功能、縮減攻擊面、新一代防護、安全性控制、端點偵測與回應、自動調查與補救、安全性控制、控制措施
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
ms.openlocfilehash: d04177ef38c1bd04b0b73e29de9d8ab6fc0893ce
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930123"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="8af70-104">設定及管理 Microsoft Defender 端點功能</span><span class="sxs-lookup"><span data-stu-id="8af70-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8af70-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="8af70-105">**Applies to:**</span></span>

- [<span data-ttu-id="8af70-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8af70-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="8af70-107">設定及管理所有的 Microsoft Defender 端點功能，為貴組織獲得最佳安全性保護。</span><span class="sxs-lookup"><span data-stu-id="8af70-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="8af70-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="8af70-108">In this section</span></span> 
<span data-ttu-id="8af70-109">主題</span><span class="sxs-lookup"><span data-stu-id="8af70-109">Topic</span></span> | <span data-ttu-id="8af70-110">說明</span><span class="sxs-lookup"><span data-stu-id="8af70-110">Description</span></span> 
:---|:---
[<span data-ttu-id="8af70-111">設定攻擊面縮減功能</span><span class="sxs-lookup"><span data-stu-id="8af70-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="8af70-112">確保設定設定正確設定並套用不當使用風險降低技術，這組功能會受到攻擊和利用。</span><span class="sxs-lookup"><span data-stu-id="8af70-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="8af70-113">設定新一代保護</span><span class="sxs-lookup"><span data-stu-id="8af70-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="8af70-114">設定新一代防護以發現所有類型的新威脅。</span><span class="sxs-lookup"><span data-stu-id="8af70-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="8af70-115">設定 Microsoft Threat Experts 的功能</span><span class="sxs-lookup"><span data-stu-id="8af70-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="8af70-116">設定和管理如何從 Microsoft 威脅專家取得網路安全性威脅情報。</span><span class="sxs-lookup"><span data-stu-id="8af70-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="8af70-117">設定 Microsoft 365 Defender 整合</span><span class="sxs-lookup"><span data-stu-id="8af70-117">Configure Microsoft 365 Defender integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="8af70-118">設定與 Microsoft Defender for Endpoint 整合的其他解決方案。</span><span class="sxs-lookup"><span data-stu-id="8af70-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="8af70-119">管理和 API 支援</span><span class="sxs-lookup"><span data-stu-id="8af70-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="8af70-120">將警示提取到 SIEM，或使用 API 建立自訂提醒。</span><span class="sxs-lookup"><span data-stu-id="8af70-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="8af70-121">建立及建立 Power BI 報表。</span><span class="sxs-lookup"><span data-stu-id="8af70-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="8af70-122">設定 Microsoft Defender 資訊安全中心設定</span><span class="sxs-lookup"><span data-stu-id="8af70-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="8af70-123">設定入口網站相關設定，例如一般設定、進場功能、啟用預覽體驗及其他設定。</span><span class="sxs-lookup"><span data-stu-id="8af70-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



