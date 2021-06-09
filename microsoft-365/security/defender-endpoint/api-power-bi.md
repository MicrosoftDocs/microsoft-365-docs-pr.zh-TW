---
title: Microsoft Defender for Endpoint APIs connection to Power BI
ms.reviewer: ''
description: 在 Microsoft Defender for Endpoint APIs 上建立 Power Business 智慧 (BI) 報告。
keywords: api、支援的 api、Power BI、報告
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0ddb38e713f08c101639976b9f2c8c1ee32e63a3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843779"
---
# <a name="create-custom-reports-using-power-bi"></a>使用 Power BI 建立自訂報表

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

在本節中，您將會瞭解如何在「Power BI 的 Defender」 APIs 上建立報表。

第一個範例會示範如何將 Power BI 連接至高級搜尋 API，第二個範例會示範 OData APIs 的連線，例如機器動作或警示。

## <a name="connect-power-bi-to-advanced-hunting-api"></a>連線 Power BI 的高級搜尋 API

- 開啟 Microsoft Power BI

- 按一下 [**取得資料**  >  **空白查詢**]

    ![建立空白查詢的影像](images/power-bi-create-blank-query.png)

- 按一下 [**高級編輯器**]

    ![開啟的高級編輯器的影像](images/power-bi-open-advanced-editor.png)

- 複製下列專案，然後將它貼到編輯器中：

```
    let 
        AdvancedHuntingQuery = "DeviceEvents | where ActionType contains 'Anti' | limit 20",

        HuntingUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries",

        Response = Json.Document(Web.Contents(HuntingUrl, [Query=[key=AdvancedHuntingQuery]])),

        TypeMap = #table(
            { "Type", "PowerBiType" },
            {
                { "Double",   Double.Type },
                { "Int64",    Int64.Type },
                { "Int32",    Int32.Type },
                { "Int16",    Int16.Type },
                { "UInt64",   Number.Type },
                { "UInt32",   Number.Type },
                { "UInt16",   Number.Type },
                { "Byte",     Byte.Type },
                { "Single",   Single.Type },
                { "Decimal",  Decimal.Type },
                { "TimeSpan", Duration.Type },
                { "DateTime", DateTimeZone.Type },
                { "String",   Text.Type },
                { "Boolean",  Logical.Type },
                { "SByte",    Logical.Type },
                { "Guid",     Text.Type }
            }),

        Schema = Table.FromRecords(Response[Schema]),
        TypedSchema = Table.Join(Table.SelectColumns(Schema, {"Name", "Type"}), {"Type"}, TypeMap , {"Type"}),
        Results = Response[Results],
        Rows = Table.FromRecords(Results, Schema[Name]),
        Table = Table.TransformColumnTypes(Rows, Table.ToList(TypedSchema, (c) => {c{0}, c{2}}))

    in Table

```

- 按一下 [**完成**]

- 按一下 [**編輯認證**]

    ![編輯 credentials0 的影像](images/power-bi-edit-credentials.png)

- 選取 **組織帳戶** 登  >  **入**

    ![Set credentials1 的影像](images/power-bi-set-credentials-organizational.png)

- 輸入您的認證，並等候登入

- 按一下 [**連線**

    ![Set credentials2 的影像](images/power-bi-set-credentials-organizational-cont.png)

- 現在，您的查詢結果會顯示為表格，而且您可以在其上開始建立視覺化效果！

- 您可以複製此資料表、重新命名它，然後編輯內部的高級搜尋查詢，以取得任何您想要的資料。

## <a name="connect-power-bi-to-odata-apis"></a>連線 Power BI OData APIs

- 與上述範例唯一不同的是，編輯器中的查詢。 

- 複製下列專案，然後將它貼到編輯器中，以從您的組織中拉出所有 **機器動作** ：

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source

```

- 您可以對 **警示** 和 **機器** 執行相同的作業。

- 您也可以使用查詢篩選的 OData 查詢，請參閱 [使用 OData 查詢](exposed-apis-odata-samples.md)


## <a name="power-bi-dashboard-samples-in-github"></a>Power BI GitHub 中的儀表板範例
如需詳細資訊，請參閱[Power BI 報表範本](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)。

## <a name="sample-reports"></a>範例報告
查看 Microsoft Defender for Endpoint Power BI 報表範例。 如需詳細資訊，請參閱 [流覽程式碼範例](/samples/browse/?products=mdatp)。


## <a name="related-topic"></a>相關主題
- [APIs 的 Defender for Endpoint](apis-intro.md)
- [進階搜捕 API](run-advanced-query-api.md)
- [使用 OData 查詢](exposed-apis-odata-samples.md)
