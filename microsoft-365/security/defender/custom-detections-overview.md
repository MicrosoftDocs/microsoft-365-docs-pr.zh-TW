---
title: Microsoft 365 Defender 中的自訂偵測概述
description: 瞭解您可以如何使用高級搜尋來建立自訂偵測並產生警示
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，自訂偵測，schema，kusto，microsoft 365，Microsoft 威脅防護
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 589a15aa456a96a5eef8042d922d338f056a882d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498838"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="eac52-104">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="eac52-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="eac52-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="eac52-105">**Applies to:**</span></span>
- <span data-ttu-id="eac52-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eac52-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="eac52-107">透過自訂偵測，您可以主動監視和回應各種事件和系統狀態，包括可疑的破壞活動和設定不當的端點。</span><span class="sxs-lookup"><span data-stu-id="eac52-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="eac52-108">這種方式是可自訂的偵測規則，自動觸發警示和回應動作。</span><span class="sxs-lookup"><span data-stu-id="eac52-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="eac52-109">自訂偵測可與 [高級搜尋](advanced-hunting-overview.md)搭配使用，其提供強大且靈活的查詢語言，涵蓋網路的大量事件和系統資訊。</span><span class="sxs-lookup"><span data-stu-id="eac52-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="eac52-110">您可以將其設定為定期執行，並在每個專案相符時產生提醒並採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="eac52-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="eac52-111">自訂偵測提供：</span><span class="sxs-lookup"><span data-stu-id="eac52-111">Custom detections provide:</span></span>
- <span data-ttu-id="eac52-112">從高級搜尋查詢所建立之規則的偵測警示</span><span class="sxs-lookup"><span data-stu-id="eac52-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="eac52-113">自動回應動作</span><span class="sxs-lookup"><span data-stu-id="eac52-113">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="eac52-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eac52-114">See also</span></span>
- [<span data-ttu-id="eac52-115">建立及管理自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="eac52-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="eac52-116">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="eac52-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="eac52-117">從 Microsoft Defender for Endpoint 遷移高級搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="eac52-117">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
