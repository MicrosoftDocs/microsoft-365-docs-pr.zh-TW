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
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>設定 Microsoft 365 Defender 將高級搜尋事件傳輸至您的儲存體帳戶

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a>開始之前：

1. 在您的租使用者中建立[儲存體帳戶](/azure/storage/common/storage-account-overview)。

2. 登入您的 [Azure 租](https://ms.portal.azure.com/)使用者，移至訂閱 **> 訂閱 > 資源提供者 > 註冊至 Microsoft。 Insights**。

## <a name="enable-raw-data-streaming"></a>啟用原始資料資料流程：

1. 以 ***全域管理員** _ 或 _ *_安全性管理員_* * 的身分登入 [Microsoft 365 Defender 的安全性中心](https://security.microsoft.com)。

2. 前往 Microsoft Defender 資訊安全中心中的 [[資料匯出設定] 頁面](https://security.microsoft.com/settings/mtp_settings/raw_data_export)。

3. 按一下 [ **新增資料匯出設定**]。

4. 選擇新設定的名稱。

5. 選擇 [**轉寄事件] 以 Azure 儲存體**。

6. 輸入您的 **儲存體帳戶資源識別碼**。 若要取得您的 **儲存體帳戶資源識別碼**，請移至 [Azure 入口](https://ms.portal.azure.com/)網站上的儲存體帳戶頁面 > 內容] 索引標籤 > 複製 **儲存體帳戶資源識別碼** 底下的文字：

   ![事件 hub resource ID1 的影像](../defender-endpoint/images/storage-account-resource-id.png)

7. 選擇您要傳輸的事件，然後按一下 [ **儲存**]。

## <a name="the-schema-of-the-events-in-the-storage-account"></a>儲存體帳戶中的事件架構：

- 將為每個事件種類建立 blob 容器： 

  ![事件 hub resource ID2 的影像](../defender-endpoint/images/storage-account-event-schema.png)

- Blob 中每一列的架構皆為下列 JSON： 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- 每個 blob 都包含多個資料列。

- 每一列都包含事件名稱、端點的端點接收事件、其所屬的租使用者 (您只會從租使用者) 中取得事件，並在名為 "properties" 的屬性中取得事件為 JSON 格式的事件。

- 如需 Microsoft 365 Defender 事件之架構的詳細資訊，請參閱[高級搜尋一覽](../defender/advanced-hunting-overview.md)。


## <a name="data-types-mapping"></a>資料類型對應

為了取得 events 屬性的資料類型，請執行下列動作：

1. 登入[Microsoft 365 的安全性中心](https://security.microsoft.com)，然後移至 [[高級搜尋] 頁面](https://security.microsoft.com/hunting-package)。

2. 執行下列查詢以取得每個事件的資料類型對應： 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- 以下是 Device Info 事件的範例： 

  ![事件中樞資源識別碼3 的影像](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>相關主題
- [高級搜尋一覽](../defender/advanced-hunting-overview.md)
- [Microsoft 365 Defender流式處理 API](streaming-api.md)
- [將 Microsoft 365 Defender 事件資料流程至您的 Azure 儲存體帳戶](streaming-api-storage.md)
- [Azure 儲存體帳戶檔](/azure/storage/common/storage-account-overview)
