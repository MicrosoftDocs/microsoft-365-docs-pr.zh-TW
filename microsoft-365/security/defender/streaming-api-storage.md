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
ms.openlocfilehash: fa61e2fd0591d375a17bad6e166a76c1ca40862e
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028880"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="15707-104">設定 Microsoft 365 Defender 將高級搜尋事件傳輸至您的儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="15707-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="15707-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="15707-105">**Applies to:**</span></span>
- [<span data-ttu-id="15707-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15707-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a><span data-ttu-id="15707-107">開始之前：</span><span class="sxs-lookup"><span data-stu-id="15707-107">Before you begin:</span></span>

1. <span data-ttu-id="15707-108">在您的租使用者中建立[儲存體帳戶](/azure/storage/common/storage-account-overview)。</span><span class="sxs-lookup"><span data-stu-id="15707-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="15707-109">登入您的 [Azure 租](https://ms.portal.azure.com/)使用者，移至訂閱 **> 訂閱 > 資源提供者 > 註冊至 Microsoft。 Insights**。</span><span class="sxs-lookup"><span data-stu-id="15707-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="15707-110">啟用原始資料資料流程：</span><span class="sxs-lookup"><span data-stu-id="15707-110">Enable raw data streaming:</span></span>

1. <span data-ttu-id="15707-111">以 \***全域管理員** _ 或 _ *_安全性管理員_* \* 的身分登入 [Microsoft 365 Defender 的安全性中心](https://security.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="15707-111">Log in to [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="15707-112">前往 Microsoft Defender 資訊安全中心中的 [[資料匯出設定] 頁面](https://security.microsoft.com/settings/mtp_settings/raw_data_export)。</span><span class="sxs-lookup"><span data-stu-id="15707-112">Go to [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="15707-113">按一下 [ **新增資料匯出設定**]。</span><span class="sxs-lookup"><span data-stu-id="15707-113">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="15707-114">選擇新設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="15707-114">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="15707-115">選擇 [**轉寄事件] 以 Azure 儲存體**。</span><span class="sxs-lookup"><span data-stu-id="15707-115">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="15707-116">輸入您的 **儲存體帳戶資源識別碼**。</span><span class="sxs-lookup"><span data-stu-id="15707-116">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="15707-117">若要取得您的 **儲存體帳戶資源識別碼**，請移至 [Azure 入口](https://ms.portal.azure.com/)網站上的儲存體帳戶頁面 > 內容] 索引標籤 > 複製 **儲存體帳戶資源識別碼** 底下的文字：</span><span class="sxs-lookup"><span data-stu-id="15707-117">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage Account Resource ID**:</span></span>

   ![事件 hub resource ID1 的影像](../defender-endpoint/images/storage-account-resource-id.png)

7. <span data-ttu-id="15707-119">選擇您要傳輸的事件，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="15707-119">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="15707-120">儲存體帳戶中的事件架構：</span><span class="sxs-lookup"><span data-stu-id="15707-120">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="15707-121">將為每個事件種類建立 blob 容器：</span><span class="sxs-lookup"><span data-stu-id="15707-121">A blob container will be created for each event type:</span></span> 

  ![事件 hub resource ID2 的影像](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="15707-123">Blob 中每一列的架構皆為下列 JSON：</span><span class="sxs-lookup"><span data-stu-id="15707-123">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="15707-124">每個 blob 都包含多個資料列。</span><span class="sxs-lookup"><span data-stu-id="15707-124">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="15707-125">每一列都包含事件名稱、端點的端點接收事件、其所屬的租使用者 (您只會從租使用者) 中取得事件，並在名為 "properties" 的屬性中取得事件為 JSON 格式的事件。</span><span class="sxs-lookup"><span data-stu-id="15707-125">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="15707-126">如需 Microsoft 365 Defender 事件之架構的詳細資訊，請參閱[高級搜尋一覽](../defender/advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="15707-126">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="15707-127">資料類型對應</span><span class="sxs-lookup"><span data-stu-id="15707-127">Data types mapping</span></span>

<span data-ttu-id="15707-128">為了取得 events 屬性的資料類型，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="15707-128">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="15707-129">登入[Microsoft 365 的安全性中心](https://security.microsoft.com)，然後移至 [[高級搜尋] 頁面](https://security.microsoft.com/hunting-package)。</span><span class="sxs-lookup"><span data-stu-id="15707-129">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="15707-130">執行下列查詢以取得每個事件的資料類型對應：</span><span class="sxs-lookup"><span data-stu-id="15707-130">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="15707-131">以下是 Device Info 事件的範例：</span><span class="sxs-lookup"><span data-stu-id="15707-131">Here is an example for Device Info event:</span></span> 

  ![事件中樞資源識別碼3 的影像](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="15707-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="15707-133">Related topics</span></span>
- [<span data-ttu-id="15707-134">高級搜尋一覽</span><span class="sxs-lookup"><span data-stu-id="15707-134">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="15707-135">Microsoft 365 Defender流式處理 API</span><span class="sxs-lookup"><span data-stu-id="15707-135">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="15707-136">將 Microsoft 365 Defender 事件資料流程至您的 Azure 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="15707-136">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="15707-137">Azure 儲存體帳戶檔</span><span class="sxs-lookup"><span data-stu-id="15707-137">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
