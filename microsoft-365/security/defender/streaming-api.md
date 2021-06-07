---
title: Stream Microsoft 365 的 Defender 事件
description: 瞭解如何設定 Microsoft 365 Defender 以將高級搜尋事件傳輸至事件中心或 Azure 儲存體帳戶
keywords: 原始資料匯出，流式 API，API，事件中心，Azure 儲存體，儲存體帳戶，高級搜尋，原始資料共用
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21a83c4876a90a231eb2a78d10a290be2dca2fa0
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782474"
---
# <a name="streaming-api"></a><span data-ttu-id="1f3d9-104">流式處理 API</span><span class="sxs-lookup"><span data-stu-id="1f3d9-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1f3d9-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="1f3d9-105">**Applies to:**</span></span>
- [<span data-ttu-id="1f3d9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f3d9-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="1f3d9-107">在事件中心和/或 Azure 儲存體帳戶中傳輸高級搜尋事件。</span><span class="sxs-lookup"><span data-stu-id="1f3d9-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="1f3d9-108">Microsoft 365Defender 可透過[高級搜尋](../defender/advanced-hunting-overview.md)向[事件中樞](/azure/event-hubs/)和/或[Azure 儲存體帳戶](/azure/event-hubs/)支援流式處理事件。</span><span class="sxs-lookup"><span data-stu-id="1f3d9-108">Microsoft 365 Defender supports streaming events through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="1f3d9-109">本節內容</span><span class="sxs-lookup"><span data-stu-id="1f3d9-109">In this section</span></span>

<span data-ttu-id="1f3d9-110">主題</span><span class="sxs-lookup"><span data-stu-id="1f3d9-110">Topic</span></span> | <span data-ttu-id="1f3d9-111">描述</span><span class="sxs-lookup"><span data-stu-id="1f3d9-111">Description</span></span>
:---|:---
[<span data-ttu-id="1f3d9-112">將事件傳輸至 Azure 事件中心</span><span class="sxs-lookup"><span data-stu-id="1f3d9-112">Stream events to Azure Event Hubs</span></span>](streaming-api-event-hub.md)| <span data-ttu-id="1f3d9-113">瞭解如何在您的租使用者中啟用流式 API，並設定 Microsoft 365 Defender 以將[高級搜尋](../defender/advanced-hunting-overview.md)流式處理至事件中心。</span><span class="sxs-lookup"><span data-stu-id="1f3d9-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="1f3d9-114">將事件傳輸至您的 Azure 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="1f3d9-114">Stream events to your Azure storage account</span></span>](streaming-api-storage.md)| <span data-ttu-id="1f3d9-115">瞭解如何在您的租使用者中啟用流式 API，並設定 Microsoft 365 Defender 以將[高級搜尋](advanced-hunting-overview.md)傳輸至您的 Azure 儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="1f3d9-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1f3d9-116">相關主題</span><span class="sxs-lookup"><span data-stu-id="1f3d9-116">Related topics</span></span>
- [<span data-ttu-id="1f3d9-117">高級搜尋一覽</span><span class="sxs-lookup"><span data-stu-id="1f3d9-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="1f3d9-118">Azure 事件中心檔</span><span class="sxs-lookup"><span data-stu-id="1f3d9-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="1f3d9-119">Azure 儲存體帳戶檔</span><span class="sxs-lookup"><span data-stu-id="1f3d9-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
