---
title: 將 Microsoft Defender for Endpoint 事件的資料流程傳遞給 Azure 事件中心
description: 瞭解如何設定 Microsoft Defender for Endpoint to stream to to Event Hub 中的高級搜尋事件。
keywords: 原始資料匯出，流式 API，API，Azure 事件中心，Azure 儲存體，儲存體帳戶，高級搜尋，原始資料共用
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
ms.openlocfilehash: 8985a40c99ad4db9710dfbf9805d537a921f6c96
ms.sourcegitcommit: f0118e61e490496cb23189cc5c73b23e2ba939be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52780162"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="df405-104">設定 Microsoft Defender for Endpoint to stream Advanced Advanced events to a Azure Event 中樞</span><span class="sxs-lookup"><span data-stu-id="df405-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="df405-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="df405-105">**Applies to:**</span></span>

- [<span data-ttu-id="df405-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="df405-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="df405-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="df405-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="df405-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="df405-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="df405-109">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="df405-109">Before you begin</span></span>

1. <span data-ttu-id="df405-110">在您的租使用者中建立 [事件中樞](/azure/event-hubs/) 。</span><span class="sxs-lookup"><span data-stu-id="df405-110">Create an [event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="df405-111">登入您的 [Azure 租](https://ms.portal.azure.com/)使用者，移至訂閱 > 訂閱 > 資源提供者 > Register to \* \* \* \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="df405-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to \*\*Subscriptions > Your subscription > Resource Providers > Register to \*\*Microsoft.insights\*\*\*\*.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="df405-112">啟用原始資料資料流程</span><span class="sxs-lookup"><span data-stu-id="df405-112">Enable raw data streaming</span></span>

1. <span data-ttu-id="df405-113">以 \***全域管理員** _ 或 _ *_安全性管理員_* \* 的身分登入 [Microsoft Defender 資訊安全中心](https://securitycenter.windows.com)。</span><span class="sxs-lookup"><span data-stu-id="df405-113">Log in to the [Microsoft Defender Security Center](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="df405-114">移至 Microsoft Defender 資訊安全中心上的 [[資料匯出設定] 頁面](https://securitycenter.windows.com/interoperability/dataexport)。</span><span class="sxs-lookup"><span data-stu-id="df405-114">Go to the [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="df405-115">按一下 [ **新增資料匯出設定**]。</span><span class="sxs-lookup"><span data-stu-id="df405-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="df405-116">選擇新設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="df405-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="df405-117">選擇 [ **將事件轉寄到 Azure 事件中心**]。</span><span class="sxs-lookup"><span data-stu-id="df405-117">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="df405-118">輸入您的 **事件中心名稱** 和 **事件中樞資源識別碼**。</span><span class="sxs-lookup"><span data-stu-id="df405-118">Type your **Event Hubs name** and your **Event Hubs resource ID**.</span></span>

   <span data-ttu-id="df405-119">若要取得您的 **事件中樞資源識別碼**，請移至 [azure](https://ms.portal.azure.com/) > 屬性] 索引標籤上的 [azure 事件中心命名空間] 頁面 > 複製 [ **資源識別碼**] 底下的文字：</span><span class="sxs-lookup"><span data-stu-id="df405-119">In order to get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > properties tab > copy the text under **Resource ID**:</span></span>

   ![事件 hub resource Id1 的影像](images/event-hub-resource-id.png)

7. <span data-ttu-id="df405-121">選擇您要傳輸的事件，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="df405-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="df405-122">Azure 事件中樞中的事件架構</span><span class="sxs-lookup"><span data-stu-id="df405-122">The schema of the events in Azure Event Hubs</span></span>

```
{
    "records": [
                    {
                        "time": "<The time WDATP received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <WDATP Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- <span data-ttu-id="df405-123">Azure 事件中樞中的每個事件 hub 郵件都包含記錄清單。</span><span class="sxs-lookup"><span data-stu-id="df405-123">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="df405-124">每筆記錄都包含事件名稱、Microsoft Defender for Endpoint 接收到事件，而租使用者屬於 (您只會從租使用者) 中取得事件，並以 JSON 格式從名為 "**properties**" 的屬性取得事件。</span><span class="sxs-lookup"><span data-stu-id="df405-124">Each record contains the event name, the time Microsoft Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="df405-125">如需 Microsoft Defender for Endpoint 事件架構的相關資訊，請參閱 [Advanced 搜尋一覽](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="df405-125">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="df405-126">在 [高級搜尋] 中， **DeviceInfo** 表格具有一個名為 **MachineGroup** 的欄，其中含有裝置的群組。</span><span class="sxs-lookup"><span data-stu-id="df405-126">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="df405-127">在這裡，每個事件會同時使用此資料行來修飾。</span><span class="sxs-lookup"><span data-stu-id="df405-127">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="df405-128">如需詳細資訊，請參閱 [裝置群組](machine-groups.md) 。</span><span class="sxs-lookup"><span data-stu-id="df405-128">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="df405-129">資料類型對應</span><span class="sxs-lookup"><span data-stu-id="df405-129">Data types mapping</span></span>

<span data-ttu-id="df405-130">若要取得事件屬性的資料類型，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="df405-130">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="df405-131">登入[Microsoft Defender 資訊安全中心](https://securitycenter.windows.com)，然後移至 [[高級搜尋] 頁面](https://securitycenter.windows.com/hunting-package)。</span><span class="sxs-lookup"><span data-stu-id="df405-131">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="df405-132">執行下列查詢以取得每個事件的資料類型對應：</span><span class="sxs-lookup"><span data-stu-id="df405-132">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="df405-133">以下是 Device Info 事件的範例：</span><span class="sxs-lookup"><span data-stu-id="df405-133">Here is an example for Device Info event:</span></span> 

  ![事件 hub resource Id2 的影像](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="df405-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="df405-135">Related topics</span></span>
- [<span data-ttu-id="df405-136">高級搜尋一覽</span><span class="sxs-lookup"><span data-stu-id="df405-136">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="df405-137">Microsoft Defender for Endpoint 流式 API</span><span class="sxs-lookup"><span data-stu-id="df405-137">Microsoft Defender for Endpoint streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="df405-138">將 Microsoft Defender for Endpoint 事件的資料流程傳遞給您的 Azure 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="df405-138">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="df405-139">Azure 事件中心檔</span><span class="sxs-lookup"><span data-stu-id="df405-139">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="df405-140">疑難排解連線問題-Azure 事件中樞</span><span class="sxs-lookup"><span data-stu-id="df405-140">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](/azure/event-hubs/troubleshooting-guide)