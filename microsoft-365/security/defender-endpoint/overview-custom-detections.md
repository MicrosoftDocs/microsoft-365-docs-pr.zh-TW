---
title: Microsoft Defender ATP 中的自訂偵測綜述
ms.reviewer: ''
description: 瞭解您可以如何使用高級搜尋來建立自訂偵測並產生警示
keywords: 自訂偵測、警示、偵測規則、高級搜尋、搜尋、查詢、回應動作、間隔、mdatp、microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6c9befcc4b1224cacb2ab4eb8530e30a397aab49
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056738"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="f851a-104">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="f851a-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f851a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f851a-105">**Applies to:**</span></span>
- [<span data-ttu-id="f851a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f851a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="f851a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f851a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f851a-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f851a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f851a-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f851a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="f851a-110">透過自訂偵測，您可以主動監視和回應各種事件和系統狀態，包括可疑的破壞活動和設定不當的裝置。</span><span class="sxs-lookup"><span data-stu-id="f851a-110">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="f851a-111">您可以使用自動觸發警示和回應動作的可自訂偵測規則來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="f851a-111">You can do this with customizable detection rules that automatically trigger alerts and response actions.</span></span>

<span data-ttu-id="f851a-112">自訂偵測可與 [高級搜尋](advanced-hunting-overview.md)搭配使用，其提供強大且靈活的查詢語言，涵蓋網路的大量事件和系統資訊。</span><span class="sxs-lookup"><span data-stu-id="f851a-112">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="f851a-113">您可以將其設定為定期執行，並在每個專案相符時產生提醒並採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="f851a-113">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="f851a-114">自訂偵測提供：</span><span class="sxs-lookup"><span data-stu-id="f851a-114">Custom detections provide:</span></span>
- <span data-ttu-id="f851a-115">從高級搜尋查詢所建立之規則的偵測警示</span><span class="sxs-lookup"><span data-stu-id="f851a-115">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="f851a-116">適用于檔案和裝置的自動回應動作</span><span class="sxs-lookup"><span data-stu-id="f851a-116">Automatic response actions that apply to files and devices</span></span>

## <a name="related-topics"></a><span data-ttu-id="f851a-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="f851a-117">Related topics</span></span>
- [<span data-ttu-id="f851a-118">建立偵測規則</span><span class="sxs-lookup"><span data-stu-id="f851a-118">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="f851a-119">查看及管理偵測規則</span><span class="sxs-lookup"><span data-stu-id="f851a-119">View and manage detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="f851a-120">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="f851a-120">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
