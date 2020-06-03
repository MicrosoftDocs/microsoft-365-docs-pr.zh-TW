---
title: Microsoft 威脅防護中的自訂偵測綜述
description: 瞭解您可以如何使用高級搜尋來建立自訂偵測並產生警示
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，自訂偵測，schema，kusto，microsoft 365，Microsoft 威脅防護
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: cdbaf9cfd2172656ed75cb3c0a1a9e361070f25b
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498348"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="28298-104">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="28298-104">Custom detections overview</span></span>

<span data-ttu-id="28298-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="28298-105">**Applies to:**</span></span>
- <span data-ttu-id="28298-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="28298-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="28298-107">透過自訂偵測，您可以主動監視和回應各種事件和系統狀態，包括可疑的破壞活動和設定不當的端點。</span><span class="sxs-lookup"><span data-stu-id="28298-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="28298-108">這種方式是可自訂的偵測規則，自動觸發警示和回應動作。</span><span class="sxs-lookup"><span data-stu-id="28298-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="28298-109">自訂偵測可與[高級搜尋](advanced-hunting-overview.md)搭配使用，其提供強大且靈活的查詢語言，涵蓋網路的大量事件和系統資訊。</span><span class="sxs-lookup"><span data-stu-id="28298-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="28298-110">您可以將其設定為定期執行，並在每個專案相符時產生提醒並採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="28298-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="28298-111">自訂偵測提供：</span><span class="sxs-lookup"><span data-stu-id="28298-111">Custom detections provide:</span></span>
- <span data-ttu-id="28298-112">從高級搜尋查詢所建立之規則的偵測警示</span><span class="sxs-lookup"><span data-stu-id="28298-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="28298-113">自動回應動作</span><span class="sxs-lookup"><span data-stu-id="28298-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="28298-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="28298-114">Related topic</span></span>
- [<span data-ttu-id="28298-115">建立及管理自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="28298-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="28298-116">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="28298-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)