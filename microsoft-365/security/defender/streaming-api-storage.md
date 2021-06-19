---
title: 將 Microsoft 365 Defender 事件資料流程給您的儲存體帳戶
description: 瞭解如何設定 Microsoft 365 Defender，將高級搜尋事件傳輸至您的儲存體帳戶。
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
ms.openlocfilehash: 656387e60bac90c7e9de4852779948dabce0efe3
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029654"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="7ed52-104">設定 Microsoft 365 Defender 將高級搜尋事件傳輸至您的儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="7ed52-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7ed52-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="7ed52-105">**Applies to:**</span></span>
- [<span data-ttu-id="7ed52-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ed52-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="7ed52-107">開始之前</span><span class="sxs-lookup"><span data-stu-id="7ed52-107">Before you begin</span></span>

1. <span data-ttu-id="7ed52-108">在您的租使用者中建立[儲存體帳戶](/azure/storage/common/storage-account-overview)。</span><span class="sxs-lookup"><span data-stu-id="7ed52-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="7ed52-109">登入您的 [Azure 租](https://ms.portal.azure.com/)使用者，移至訂閱 **> 訂閱 > 資源提供者 > 註冊至 Microsoft。 Insights**。</span><span class="sxs-lookup"><span data-stu-id="7ed52-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="7ed52-110">啟用原始資料資料流程</span><span class="sxs-lookup"><span data-stu-id="7ed52-110">Enable raw data streaming</span></span>

1. <span data-ttu-id="7ed52-111">登入 Microsoft 365 Defender 入口網站 (<https://security.microsoft.com>) 為 \***全域管理員**] 或 [_安全性管理員_] \* \*。</span><span class="sxs-lookup"><span data-stu-id="7ed52-111">Log in to the Microsoft 365 Defender portal (<https://security.microsoft.com>) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="7ed52-112">移至 **設定** \> **Microsoft 365 Defender** \> **流式 API**。</span><span class="sxs-lookup"><span data-stu-id="7ed52-112">Go to **Settings** \> **Microsoft 365 Defender** \> **Streaming API**.</span></span> <span data-ttu-id="7ed52-113">若要直接移至 [ **流式 API** ] 頁面，請使用 <https://security.microsoft.com/settings/mtp_settings/raw_data_export> 。</span><span class="sxs-lookup"><span data-stu-id="7ed52-113">To go directly to the **Streaming API** page, use <https://security.microsoft.com/settings/mtp_settings/raw_data_export>.</span></span>

3. <span data-ttu-id="7ed52-114">點擊 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="7ed52-114">Click **Add**.</span></span>

4. <span data-ttu-id="7ed52-115">在出現的 [ **新增流式 API 設定** ] 浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="7ed52-115">In the **Add new Streaming API settings** flyout that appears, configure the following settings:</span></span>
   1. <span data-ttu-id="7ed52-116">**名稱**：選擇新設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="7ed52-116">**Name**: Choose a name for your new settings.</span></span>
   2. <span data-ttu-id="7ed52-117">選取 [**轉寄事件] 以 Azure 儲存體**。</span><span class="sxs-lookup"><span data-stu-id="7ed52-117">Select **Forward events to Azure Storage**.</span></span>
   3. <span data-ttu-id="7ed52-118">在出現的 [**儲存體帳戶資源識別碼**] 方塊中，輸入您的 **儲存體帳戶資源識別碼**。</span><span class="sxs-lookup"><span data-stu-id="7ed52-118">In the **Storage Account Resource ID** box that appears, type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="7ed52-119">若要取得 **儲存體帳戶資源識別碼**，請開啟 Azure 入口網站 <https://portal.azure.com> ，然後按一下 [**儲存體帳戶** \> 移至屬性] 索引標籤，以 \> 複製 **儲存體帳戶資源識別碼** 底下的文字。</span><span class="sxs-lookup"><span data-stu-id="7ed52-119">To get your **Storage Account Resource ID**, open the Azure portal at <https://portal.azure.com>, click **Storage accounts** \> go to the properties tab \> copy the text under **Storage Account Resource ID**.</span></span>

      ![事件 hub resource ID1 的影像](../defender-endpoint/images/storage-account-resource-id.png)

   4. <span data-ttu-id="7ed52-121">回到 [ **新增流式 API 設定** ] 浮出控制項，選擇您要傳輸的 **事件種類** 。</span><span class="sxs-lookup"><span data-stu-id="7ed52-121">Back on the **Add new Streaming API settings** flyout, choose the **Event types** that you want to stream.</span></span>

   <span data-ttu-id="7ed52-122">當您完成時，按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="7ed52-122">When you're finished, click **Submit**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="7ed52-123">儲存體帳戶中的事件架構</span><span class="sxs-lookup"><span data-stu-id="7ed52-123">The schema of the events in the Storage account</span></span>

- <span data-ttu-id="7ed52-124">將為每個事件種類建立 blob 容器：</span><span class="sxs-lookup"><span data-stu-id="7ed52-124">A blob container will be created for each event type:</span></span>

  ![事件 hub resource ID2 的影像](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="7ed52-126">Blob 中每一列的架構皆為下列 JSON：</span><span class="sxs-lookup"><span data-stu-id="7ed52-126">The schema of each row in a blob is the following JSON:</span></span>

  ```JSON
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }
  ```

- <span data-ttu-id="7ed52-127">每個 blob 都包含多個資料列。</span><span class="sxs-lookup"><span data-stu-id="7ed52-127">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="7ed52-128">每一列都包含事件名稱、端點的端點接收事件、其所屬的租使用者 (您只會從租使用者) 中取得事件，並在名為 "properties" 的屬性中取得事件為 JSON 格式的事件。</span><span class="sxs-lookup"><span data-stu-id="7ed52-128">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="7ed52-129">如需 Microsoft 365 Defender 事件之架構的詳細資訊，請參閱[高級搜尋一覽](../defender/advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7ed52-129">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="7ed52-130">資料類型對應</span><span class="sxs-lookup"><span data-stu-id="7ed52-130">Data types mapping</span></span>

<span data-ttu-id="7ed52-131">為了取得 events 屬性的資料類型，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7ed52-131">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="7ed52-132">登入 Microsoft 365 Defender 入口網站 (<https://security.microsoft.com>) ，然後移至「**搜尋** \> **高級搜尋**」。</span><span class="sxs-lookup"><span data-stu-id="7ed52-132">Log in to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and go to **Hunting** \> **Advanced hunting**.</span></span> <span data-ttu-id="7ed52-133">若要直接移至 [ **高級搜尋** ] 頁面，請使用 <security.microsoft.com/advanced-hunting>。</span><span class="sxs-lookup"><span data-stu-id="7ed52-133">To go directly to the **Advanced hunting** page, use <security.microsoft.com/advanced-hunting>.</span></span>

2. <span data-ttu-id="7ed52-134">在 [ **查詢** ] 索引標籤上，執行下列查詢以取得每個事件的資料類型對應：</span><span class="sxs-lookup"><span data-stu-id="7ed52-134">On the **Query** tab, run the following query to get the data types mapping for each event:</span></span>

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- <span data-ttu-id="7ed52-135">以下是 Device Info 事件的範例：</span><span class="sxs-lookup"><span data-stu-id="7ed52-135">Here is an example for Device Info event:</span></span>

  ![事件中樞資源識別碼3 的影像](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="7ed52-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="7ed52-137">Related topics</span></span>

- [<span data-ttu-id="7ed52-138">高級搜尋一覽</span><span class="sxs-lookup"><span data-stu-id="7ed52-138">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="7ed52-139">Microsoft 365 Defender流式處理 API</span><span class="sxs-lookup"><span data-stu-id="7ed52-139">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="7ed52-140">將 Microsoft 365 Defender 事件資料流程至您的 Azure 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="7ed52-140">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="7ed52-141">Azure 儲存體帳戶檔</span><span class="sxs-lookup"><span data-stu-id="7ed52-141">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
