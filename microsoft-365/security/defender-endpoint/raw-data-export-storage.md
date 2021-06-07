---
title: 將 Microsoft Defender for Endpoint 事件的資料流程傳遞給您的儲存體帳戶
description: 瞭解如何設定 Microsoft Defender for Endpoint to stream Advanced 搜尋事件至您的儲存體帳戶。
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
ms.openlocfilehash: c280baaf3af6f9fcac6059bc2797910eb6c226fd
ms.sourcegitcommit: f0118e61e490496cb23189cc5c73b23e2ba939be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52780174"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="58e2e-104">設定 Microsoft Defender for Endpoint to stream Advanced 搜尋事件至您的儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="58e2e-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="58e2e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="58e2e-105">**Applies to:**</span></span>
- [<span data-ttu-id="58e2e-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="58e2e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="58e2e-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="58e2e-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="58e2e-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="58e2e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="58e2e-109">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="58e2e-109">Before you begin</span></span>

1. <span data-ttu-id="58e2e-110">在您的租使用者中建立[儲存體帳戶](/azure/storage/common/storage-account-overview)。</span><span class="sxs-lookup"><span data-stu-id="58e2e-110">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="58e2e-111">登入您的 [Azure 租](https://ms.portal.azure.com/)使用者，移至訂閱 **> 訂閱 > 資源提供者 > 登錄至 Microsoft。**</span><span class="sxs-lookup"><span data-stu-id="58e2e-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="58e2e-112">啟用原始資料資料流程</span><span class="sxs-lookup"><span data-stu-id="58e2e-112">Enable raw data streaming</span></span>

1. <span data-ttu-id="58e2e-113">以 [**全域管理員**] 或 [_安全性管理員_] \* \* 的身分登入 [Microsoft Defender for 端點入口網站](https://securitycenter.windows.com)。</span><span class="sxs-lookup"><span data-stu-id="58e2e-113">Log in to [Microsoft Defender for Endpoint portal](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="58e2e-114">移至 Microsoft Defender 資訊安全中心上的 [[資料匯出設定] 頁面](https://securitycenter.windows.com/interoperability/dataexport)。</span><span class="sxs-lookup"><span data-stu-id="58e2e-114">Go to [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="58e2e-115">按一下 [ **新增資料匯出設定**]。</span><span class="sxs-lookup"><span data-stu-id="58e2e-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="58e2e-116">選擇新設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="58e2e-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="58e2e-117">選擇 [**轉寄事件] 以 Azure 儲存體**。</span><span class="sxs-lookup"><span data-stu-id="58e2e-117">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="58e2e-118">輸入您的 **儲存體帳戶資源識別碼**。</span><span class="sxs-lookup"><span data-stu-id="58e2e-118">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="58e2e-119">若要取得您的 **儲存體帳戶資源識別碼**，請移至 [Azure 入口](https://ms.portal.azure.com/)網站上的儲存體帳戶頁面 > 內容] 索引標籤 > 複製 **儲存體帳戶資源識別碼** 底下的文字：</span><span class="sxs-lookup"><span data-stu-id="58e2e-119">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage account resource ID**:</span></span>

   ![事件 hub resource ID1 的影像](images/storage-account-resource-id.png)

7. <span data-ttu-id="58e2e-121">選擇您要傳輸的事件，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="58e2e-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="58e2e-122">儲存體帳戶中的事件架構</span><span class="sxs-lookup"><span data-stu-id="58e2e-122">The schema of the events in the Storage account</span></span>

- <span data-ttu-id="58e2e-123">將為每個事件種類建立 blob 容器：</span><span class="sxs-lookup"><span data-stu-id="58e2e-123">A blob container will be created for each event type:</span></span> 

  ![事件 hub resource ID2 的影像](images/storage-account-event-schema.png)

- <span data-ttu-id="58e2e-125">Blob 中每一列的架構皆為下列 JSON：</span><span class="sxs-lookup"><span data-stu-id="58e2e-125">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="58e2e-126">每個 blob 都包含多個資料列。</span><span class="sxs-lookup"><span data-stu-id="58e2e-126">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="58e2e-127">每一列都包含事件名稱、端點的端點接收事件、其所屬的租使用者 (您只會從租使用者) 中取得事件，並在名為 "properties" 的屬性中取得事件為 JSON 格式的事件。</span><span class="sxs-lookup"><span data-stu-id="58e2e-127">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="58e2e-128">如需 Microsoft Defender for Endpoint 事件架構的相關資訊，請參閱 [Advanced 搜尋一覽](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="58e2e-128">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="58e2e-129">在 [高級搜尋] 中， **DeviceInfo** 表格具有一個名為 **MachineGroup** 的欄，其中含有裝置的群組。</span><span class="sxs-lookup"><span data-stu-id="58e2e-129">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="58e2e-130">在這裡，每個事件會同時使用此資料行來修飾。</span><span class="sxs-lookup"><span data-stu-id="58e2e-130">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="58e2e-131">如需詳細資訊，請參閱 [裝置群組](machine-groups.md) 。</span><span class="sxs-lookup"><span data-stu-id="58e2e-131">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="58e2e-132">資料類型對應</span><span class="sxs-lookup"><span data-stu-id="58e2e-132">Data types mapping</span></span>

<span data-ttu-id="58e2e-133">為了取得 events 屬性的資料類型，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="58e2e-133">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="58e2e-134">登入[Microsoft Defender 資訊安全中心](https://securitycenter.windows.com)，然後移至 [[高級搜尋] 頁面](https://securitycenter.windows.com/hunting-package)。</span><span class="sxs-lookup"><span data-stu-id="58e2e-134">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="58e2e-135">執行下列查詢以取得每個事件的資料類型對應：</span><span class="sxs-lookup"><span data-stu-id="58e2e-135">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="58e2e-136">以下是 Device Info 事件的範例：</span><span class="sxs-lookup"><span data-stu-id="58e2e-136">Here is an example for Device Info event:</span></span> 

  ![事件中樞資源識別碼3 的影像](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="58e2e-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="58e2e-138">Related topics</span></span>
- [<span data-ttu-id="58e2e-139">高級搜尋一覽</span><span class="sxs-lookup"><span data-stu-id="58e2e-139">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="58e2e-140">Microsoft Defender for Endpoint 流式 API</span><span class="sxs-lookup"><span data-stu-id="58e2e-140">Microsoft Defender for Endpoint Streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="58e2e-141">將 Microsoft Defender for Endpoint 事件的資料流程傳遞給您的 Azure 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="58e2e-141">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="58e2e-142">Azure 儲存體帳戶檔</span><span class="sxs-lookup"><span data-stu-id="58e2e-142">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)