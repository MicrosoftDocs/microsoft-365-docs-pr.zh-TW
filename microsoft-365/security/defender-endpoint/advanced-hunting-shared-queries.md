---
title: 在進階搜捕中使用共用查詢
description: 立即開始威脅搜捕，並使用預先定義的共用查詢。 將您的查詢與大眾或您的組織共用。
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp 搜尋、查詢、遙測、自訂偵測、架構、kusto、github 儲存庫、我的查詢、共用查詢
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 78a532167e4256e3453803f1a0b4a9e4875771cf
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499430"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>在進階搜捕中使用共用查詢

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

適用於：
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

您可以在同一個組織的多位使用者之間共用[進階搜捕](advanced-hunting-overview.md)查詢。 您也可以在 GitHub 尋找公開的查詢。 這些查詢可讓您快速地執行特定威脅搜捕案例，而不需要從頭開始撰寫查詢。

![共用查詢的影像](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>儲存、修改及共用查詢
您可以儲存新的或現有的查詢，以便只有組織中的其他使用者能存取或共用。

1. 輸入新的查詢或從 [ **共用查詢** ] 或 [我的 **查詢**] 中載入現有的查詢。

2. 選取 **[儲存]** 或 [ **另** 存新檔] 選項。 若要避免覆寫現有的查詢，請選擇 [ **另存** 新檔]。

3. 輸入查詢的名稱。

   ![儲存查詢的影像](images/advanced-hunting-save-query.png)

4. 選取您要儲存查詢的資料夾。
    - **共用查詢** -共用給組織中的所有使用者
    - **我的查詢** —只有您可以存取
    
5. 選取 [儲存]。

## <a name="delete-or-rename-a-query"></a>刪除或重新命名查詢
1. 以滑鼠右鍵按一下您要重新命名或刪除的查詢。

    ![刪除查詢的影像](images/atp_advanced_hunting_delete_rename.png)

2. 選取 [刪除] 並確認刪除。 或選取 [重新命名]，並為查詢提供新名稱。

## <a name="create-a-direct-link-to-a-query"></a>建立查詢的直接連結
若要產生連結，以直接在高級搜尋查詢編輯器中開啟查詢，請完成查詢並選取 [ **共用] 連結**。

## <a name="access-queries-in-the-github-repository"></a>存取 GitHub 儲存庫中的查詢  
Microsoft 安全研究人員會定期在 [GitHub 上的指定公開儲存庫](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries)中共用進階搜捕查詢。 這個儲存庫開放個人提出貢獻。 若要貢獻，請[免費加入 GitHub ](https://github.com/)。 

>[!TIP]
>Microsoft 安全研究人員也會提供進階搜捕查詢，您可以用來尋找與新興威脅相關聯的活動和指標。 這些查詢是由 Microsoft Defender 安全性中心中的[威脅分析](threat-analytics.md)報告提供。

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [了解結構描述](advanced-hunting-schema-reference.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
- [自訂偵測概觀](overview-custom-detections.md)
