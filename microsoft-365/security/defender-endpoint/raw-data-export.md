---
title: Stream Microsoft Defender for Endpoint 事件
description: 瞭解如何設定 Microsoft Defender ATP，以將高級搜尋事件傳輸至事件中心或 Azure 儲存體帳戶
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
ms.openlocfilehash: 22f4e4c974b60e291273eb9bebfa34583f4e2fb7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058184"
---
# <a name="raw-data-streaming-api"></a><span data-ttu-id="b0e33-104">原始資料流程式處理 API</span><span class="sxs-lookup"><span data-stu-id="b0e33-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b0e33-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b0e33-105">**Applies to:**</span></span>
- [<span data-ttu-id="b0e33-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b0e33-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="b0e33-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b0e33-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b0e33-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b0e33-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="b0e33-109">在事件中心和/或 Azure 儲存體帳戶中傳輸高級搜尋事件。</span><span class="sxs-lookup"><span data-stu-id="b0e33-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="b0e33-110">Defender for Endpoint 支援透過 [Advanced 搜尋](advanced-hunting-overview.md) 向 [事件中樞](https://docs.microsoft.com/azure/event-hubs/) 和/或 [Azure 儲存體帳戶](https://docs.microsoft.com/azure/event-hubs/)進行所有可用事件的資料流程。</span><span class="sxs-lookup"><span data-stu-id="b0e33-110">Defender for Endpoint supports streaming all the events available through [Advanced Hunting](advanced-hunting-overview.md) to an [Event Hubs](https://docs.microsoft.com/azure/event-hubs/) and/or [Azure storage account](https://docs.microsoft.com/azure/event-hubs/).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="b0e33-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="b0e33-111">In this section</span></span>

<span data-ttu-id="b0e33-112">主題</span><span class="sxs-lookup"><span data-stu-id="b0e33-112">Topic</span></span> | <span data-ttu-id="b0e33-113">描述</span><span class="sxs-lookup"><span data-stu-id="b0e33-113">Description</span></span>
:---|:---
[<span data-ttu-id="b0e33-114">將 Microsoft Defender for Endpoint 事件的資料流程傳遞給 Azure 事件中心</span><span class="sxs-lookup"><span data-stu-id="b0e33-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="b0e33-115">瞭解如何在您的租使用者中啟用流式 API，並設定 Defender for Endpoint，以將 [高級搜尋](advanced-hunting-overview.md) 流式處理至事件中心。</span><span class="sxs-lookup"><span data-stu-id="b0e33-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="b0e33-116">Azure 儲存體帳戶的端點事件的資料流程 Defender</span><span class="sxs-lookup"><span data-stu-id="b0e33-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="b0e33-117">瞭解如何在您的租使用者中啟用流式 API，並設定 Defender for Endpoint，以將 [高級搜尋](advanced-hunting-overview.md) 流式處理至您的 Azure 儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="b0e33-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b0e33-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="b0e33-118">Related topics</span></span>
- [<span data-ttu-id="b0e33-119">高級搜尋一覽</span><span class="sxs-lookup"><span data-stu-id="b0e33-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b0e33-120">Azure 事件中心檔</span><span class="sxs-lookup"><span data-stu-id="b0e33-120">Azure Event Hubs documentation</span></span>](https://docs.microsoft.com/azure/event-hubs/)
- [<span data-ttu-id="b0e33-121">Azure 儲存體帳戶檔</span><span class="sxs-lookup"><span data-stu-id="b0e33-121">Azure Storage Account documentation</span></span>](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
