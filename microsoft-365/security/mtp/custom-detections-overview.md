---
title: Microsoft 365 Defender 中的自訂偵測概觀
description: 瞭解如何使用進位搜尋來建立自訂偵測及產生警示
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、自訂偵測、架構、kusto、microsoft 365、Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae9617a55fd5efb40a3aba07202ebfb1494d4db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928805"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="76907-104">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="76907-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="76907-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="76907-105">**Applies to:**</span></span>
- <span data-ttu-id="76907-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76907-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="76907-107">使用自訂偵測，您可以主動監視並回應各種事件和系統狀態，包括可疑的外泄活動和錯誤配置的端點。</span><span class="sxs-lookup"><span data-stu-id="76907-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="76907-108">這是因為可自訂的偵測規則會自動觸發提醒及回應動作。</span><span class="sxs-lookup"><span data-stu-id="76907-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="76907-109">自訂偵測功能可和 [進位](advanced-hunting-overview.md)搜尋功能一起使用，它提供功能強大且彈性的查詢語言，可涵蓋您網路上廣泛的事件和系統資訊。</span><span class="sxs-lookup"><span data-stu-id="76907-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="76907-110">您可以將它們設定為定期執行、產生警示，以及每當有符合專案時採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="76907-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="76907-111">自訂偵測功能提供：</span><span class="sxs-lookup"><span data-stu-id="76907-111">Custom detections provide:</span></span>
- <span data-ttu-id="76907-112">來自進級搜尋查詢之規則型偵測的警示</span><span class="sxs-lookup"><span data-stu-id="76907-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="76907-113">自動回復動作</span><span class="sxs-lookup"><span data-stu-id="76907-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="76907-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="76907-114">Related topic</span></span>
- [<span data-ttu-id="76907-115">建立及管理自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="76907-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="76907-116">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="76907-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
