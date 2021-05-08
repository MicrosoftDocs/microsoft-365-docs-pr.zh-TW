---
title: 啟用並設定 Microsoft Defender 防防毒保護功能
description: 在 Microsoft Defender AV 中啟用行為型、啟發式和即時保護。
keywords: 啟發式、機器學習、行為監控、即時保護、always on、Microsoft Defender 防毒程式、反惡意程式碼、安全性、Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 53b1e1474e0870388ec1cfaf214190eb0bdf7beb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274597"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a><span data-ttu-id="8b37d-104">設定行為、啟發學習法和即時保護</span><span class="sxs-lookup"><span data-stu-id="8b37d-104">Configure behavioral, heuristic, and real-time protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8b37d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8b37d-105">**Applies to:**</span></span>

- [<span data-ttu-id="8b37d-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8b37d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8b37d-107">Microsoft Defender 防病毒使用數種方法來提供威脅防護：</span><span class="sxs-lookup"><span data-stu-id="8b37d-107">Microsoft Defender Antivirus uses several methods to provide threat protection:</span></span>

- <span data-ttu-id="8b37d-108">雲端提供的保護，用於近乎立即偵測和封鎖新的和新興的威脅</span><span class="sxs-lookup"><span data-stu-id="8b37d-108">Cloud-delivered protection for near-instant detection and blocking of new and emerging threats</span></span>
- <span data-ttu-id="8b37d-109">Always on 掃描，使用檔案及程式列為監控和其他試探法 (也稱為「即時保護」 ) </span><span class="sxs-lookup"><span data-stu-id="8b37d-109">Always-on scanning, using file and process behavior monitoring and other heuristics (also known as "real-time protection")</span></span>
- <span data-ttu-id="8b37d-110">以機器學習、人力和自動化資料分析及深入的威脅抵禦研究為基礎的專屬保護更新</span><span class="sxs-lookup"><span data-stu-id="8b37d-110">Dedicated protection updates based on machine-learning, human and automated big-data analysis, and in-depth threat resistance research</span></span>

<span data-ttu-id="8b37d-111">您可以設定 Microsoft Defender 防毒軟體如何使用這些方法與群組原則、System Center 設定管理、PowerShell Cmdlet 及 Windows Management Instrumentation (WMI) 。</span><span class="sxs-lookup"><span data-stu-id="8b37d-111">You can configure how Microsoft Defender Antivirus uses these methods with Group Policy, System Center Configuration Manage, PowerShell cmdlets, and Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="8b37d-112">本節包含設定進行永不間斷掃描的功能，包括如何偵測並封鎖視為不安全的應用程式，但可能偵測為惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="8b37d-112">This section covers configuration for always-on scanning, including how to detect and block apps that are deemed unsafe, but may not be detected as malware.</span></span>

<span data-ttu-id="8b37d-113">如需如何啟用及設定 Microsoft Defender 防病毒雲端提供的保護，請參閱 [使用下一代 Microsoft Defender 防病毒技術（透過雲端提供）保護](cloud-protection-microsoft-defender-antivirus.md) 。</span><span class="sxs-lookup"><span data-stu-id="8b37d-113">See [Use next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8b37d-114">本節內容</span><span class="sxs-lookup"><span data-stu-id="8b37d-114">In this section</span></span>

 <span data-ttu-id="8b37d-115">主題</span><span class="sxs-lookup"><span data-stu-id="8b37d-115">Topic</span></span> | <span data-ttu-id="8b37d-116">描述</span><span class="sxs-lookup"><span data-stu-id="8b37d-116">Description</span></span>
---|---
[<span data-ttu-id="8b37d-117">偵測並封鎖潛在的垃圾應用程式</span><span class="sxs-lookup"><span data-stu-id="8b37d-117">Detect and block potentially unwanted applications</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | <span data-ttu-id="8b37d-118">偵測並封鎖您網路中可能不需要的應用程式，例如廣告軟體、瀏覽器修飾符和工具列，以及惡意或虛假的防病毒應用程式</span><span class="sxs-lookup"><span data-stu-id="8b37d-118">Detect and block apps that may be unwanted in your network, such as adware, browser modifiers and toolbars, and rogue or fake antivirus apps</span></span>
[<span data-ttu-id="8b37d-119">啟用並設定 Microsoft Defender 防防毒保護功能</span><span class="sxs-lookup"><span data-stu-id="8b37d-119">Enable and configure Microsoft Defender Antivirus protection capabilities</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md) | <span data-ttu-id="8b37d-120">啟用和設定即時保護、啟發及其他永不啟用的 Microsoft Defender 防病毒監控功能</span><span class="sxs-lookup"><span data-stu-id="8b37d-120">Enable and configure real-time protection, heuristics, and other always-on Microsoft Defender Antivirus monitoring features</span></span>