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
ms.custom: api
ms.openlocfilehash: 03b19f3af3c140729db2b5d51bb7ae11d906497b
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771642"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>設定 Microsoft Defender for Endpoint to stream Advanced Advanced events to a Azure Event 中樞

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a>開始之前

1. 在您的租使用者中建立 [事件中樞](/azure/event-hubs/) 。

2. 登入您的 [Azure 租](https://ms.portal.azure.com/)使用者，移至訂閱 > 訂閱 > 資源提供者 > Register to * * * * * *。

## <a name="enable-raw-data-streaming"></a>啟用原始資料資料流程

1. 以 ***全域管理員** _ 或 _ *_安全性管理員_* * 的身分登入 [Microsoft Defender 資訊安全中心](https://securitycenter.windows.com)。

2. 移至 Microsoft Defender 資訊安全中心上的 [[資料匯出設定] 頁面](https://securitycenter.windows.com/interoperability/dataexport)。

3. 按一下 [ **新增資料匯出設定**]。

4. 選擇新設定的名稱。

5. 選擇 [ **將事件轉寄到 Azure 事件中心**]。

6. 輸入您的 **事件中心名稱** 和 **事件中樞資源識別碼**。

   若要取得您的 **事件中樞資源識別碼**，請移至 [azure](https://ms.portal.azure.com/) > 屬性] 索引標籤上的 [azure 事件中心命名空間] 頁面 > 複製 [ **資源識別碼**] 底下的文字：

   ![事件 hub resource Id1 的影像](images/event-hub-resource-id.png)

7. 選擇您要傳輸的事件，然後按一下 [ **儲存**]。

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Azure 事件中樞中的事件架構

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

- Azure 事件中樞中的每個事件 hub 郵件都包含記錄清單。

- 每筆記錄都包含事件名稱、Microsoft Defender for Endpoint 接收到事件，而租使用者屬於 (您只會從租使用者) 中取得事件，並以 JSON 格式從名為 "**properties**" 的屬性取得事件。

- 如需 Microsoft Defender for Endpoint 事件架構的相關資訊，請參閱 [Advanced 搜尋一覽](advanced-hunting-overview.md)。

- 在 [高級搜尋] 中， **DeviceInfo** 表格具有一個名為 **MachineGroup** 的欄，其中含有裝置的群組。 在這裡，每個事件會同時使用此資料行來修飾。 如需詳細資訊，請參閱 [裝置群組](machine-groups.md) 。

## <a name="data-types-mapping"></a>資料類型對應

若要取得事件屬性的資料類型，請執行下列動作：

1. 登入[Microsoft Defender 資訊安全中心](https://securitycenter.windows.com)，然後移至 [[高級搜尋] 頁面](https://securitycenter.windows.com/hunting-package)。

2. 執行下列查詢以取得每個事件的資料類型對應：
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- 以下是 Device Info 事件的範例： 

  ![事件 hub resource Id2 的影像](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>相關主題
- [高級搜尋一覽](advanced-hunting-overview.md)
- [Microsoft Defender for Endpoint 流式 API](raw-data-export.md)
- [將 Microsoft Defender for Endpoint 事件的資料流程傳遞給您的 Azure 儲存體帳戶](raw-data-export-storage.md)
- [Azure 事件中心檔](/azure/event-hubs/)
- [疑難排解連線問題-Azure 事件中樞](/azure/event-hubs/troubleshooting-guide)