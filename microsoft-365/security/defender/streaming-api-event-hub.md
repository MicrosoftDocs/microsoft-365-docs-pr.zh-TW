---
title: Azure 事件中樞的資料流程 Microsoft 365 Defender 事件
description: 瞭解如何設定 Microsoft 365 Defender，以將高級搜尋事件傳輸至您的事件中樞。
keywords: 原始資料匯出，流式 API，API，Azure 事件中樞，Azure 儲存體，儲存體帳戶，高級搜尋，原始資料共用
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
ms.openlocfilehash: c62f175fc8227f64b9f18de78a2a793b2201691c
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782366"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a>設定 Microsoft 365 Defender 以將高級搜尋事件傳輸至您的 Azure 事件中樞

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>在您開始之前

1. 在您的租使用者中建立 [事件中樞](/azure/event-hubs/) 。

2. 登入您的 [Azure 租](https://ms.portal.azure.com/)使用者，移至訂閱 **> 訂閱 > 資源提供者 > 登錄至 Microsoft。**

3. 建立事件 Hub 命名空間，移至 **事件中樞 > 新增** 並選取適用于預期負載的定價層、輸送量單位和自動陀螺接。 如需詳細資訊，請參閱[定價-事件中心 |Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)。  

### <a name="add-contributor-permissions"></a>新增投稿者許可權 
在建立事件 Hub 命名空間之後，您將需要將應用程式註冊服務主體新增為 Reader、Azure 事件中樞資料接收器，以及將登入 Microsoft 365 Defender 的使用者 (這也可以在資源群組或訂閱層級) 進行。 

移至 **事件中心命名空間 > 的存取控制 (IAM) >** 在 **角色指派** 下新增及驗證。

## <a name="enable-raw-data-streaming"></a>啟用原始資料資料流程

1. 以 ***全域管理員** _ 或 _ *_安全性管理員_* * 的身分登入 [Microsoft 365 的 Defender 安全中心](https://security.microsoft.com)。

2. 移至 [ [流式處理 API 設定] 頁面](https://security.microsoft.com/settings/mtp_settings/raw_data_export)。

3. 按一下 [ **新增**]。

4. 選擇新設定的名稱。

5. 選擇 [ **將事件轉寄至 Azure 事件中樞**]。

6. 您可以選取是否要將事件資料匯出到單一事件中樞，或將每個事件資料表匯出至事件 Hub 命名空間中的不同事件 hub。 

7. 若要將事件資料匯出到單一事件中樞，請輸入您的 **事件中樞名稱** 和 **事件中樞資源識別碼**。

   若要取得 **事件 Hub 資源識別碼**，請移至 azure 的事件中心命名空間頁面 [ [azure](https://ms.portal.azure.com/)屬性] 索引標籤上，  >   > 複製 [**資源識別碼**] 底下的文字：

   ![事件 Hub resource Id1 的影像](../defender-endpoint/images/event-hub-resource-id.png)

8. 選擇您要傳輸的事件，然後按一下 [ **儲存**]。

## <a name="the-schema-of-the-events-in-azure-event-hub"></a>Azure 事件中樞中的事件架構

```
{
    "records": [
                    {
                        "time": "<The time Microsoft 365 Defender received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- Azure 事件 Hub 中的每個事件 Hub 郵件都包含記錄清單。

- 每筆記錄都包含事件名稱、Microsoft 365 Defender 接收事件的時間、租使用者所屬的租使用者 (您只會從承租人) 中取得事件，而在名為 "**properties**" 的屬性中則會以 JSON 格式取得事件。

- 如需 Microsoft 365 的 Defender 事件架構的詳細資訊，請參閱[高級搜尋一覽](advanced-hunting-overview.md)。

- 在 [高級搜尋] 中， **DeviceInfo** 表格具有一個名為 **MachineGroup** 的欄，其中含有裝置的群組。 在這裡，每個事件會同時使用此資料行來修飾。 




## <a name="data-types-mapping"></a>資料類型對應

若要取得事件屬性的資料類型，請執行下列動作：

1. 登入[Microsoft 365 的安全性中心](https://security.microsoft.com)，然後移至 [[高級搜尋] 頁面](https://security.microsoft.com/hunting-package)。

2. 執行下列查詢以取得每個事件的資料類型對應：
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- 以下是 Device Info 事件的範例： 

  ![事件 Hub resource Id2 的影像](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>相關主題
- [高級搜尋一覽](advanced-hunting-overview.md)
- [Microsoft 365Defender 資料流程 API](streaming-api.md)
- [將 Microsoft 365 的 Defender 事件資料流程至您的 Azure 儲存體帳戶](streaming-api-storage.md)
- [Azure 事件中樞檔](/azure/event-hubs/)
- [疑難排解連線問題-Azure 事件中樞](/azure/event-hubs/troubleshooting-guide)
