---
title: 在 Microsoft 365 Defender 高級搜尋中使用共用查詢
description: 立即開始威脅搜捕，並使用預先定義的共用查詢。 將您的查詢與大眾或您的組織共用。
keywords: 「高級搜尋」、「威脅搜尋」、「網路威脅搜尋」、「Microsoft 365 Defender」、「Microsoft 365」、「m365」、「搜尋」、「遙測」、「自訂偵測」、「架構」、「kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 83c78f9df5560c75e40a171d770e994b86049204
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952581"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>在進階搜捕中使用共用查詢

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender
- 適用於端點的 Microsoft Defender



您可以在同一個組織的多位使用者之間共用[進階搜捕](advanced-hunting-overview.md)查詢。 您也可以在 GitHub 尋找公開的查詢。 這些查詢可讓您快速地執行特定威脅搜捕案例，而不需要從頭開始撰寫查詢。

![共用查詢的影像](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>儲存、修改及共用查詢
您可以儲存新的或現有的查詢，以便只有組織中的其他使用者能存取或共用。 

1. 建立或修改查詢。 

2. 按一下 [儲存查詢] 下拉式按鈕，然後選取 [另存新檔]。
    
3. 輸入查詢的名稱。 

   ![儲存查詢的影像](../../media/advanced-hunting-save-query.png)

4. 選取您要儲存查詢的資料夾。
    - **共用的查詢** — 與組織的所有使用者共用
    - **我的查詢** —只有您可以存取
    
5. 選取 [儲存]。 

## <a name="delete-or-rename-a-query"></a>刪除或重新命名查詢
1. 以滑鼠右鍵按一下您要重新命名或刪除的查詢。

    ![刪除查詢的影像](../../media/advanced_hunting_delete_rename.png)

2. 選取 [刪除] 並確認刪除。 或選取 [重新命名]，並為查詢提供新名稱。

## <a name="create-a-direct-link-to-a-query"></a>建立查詢的直接連結
若要產生連結，以直接在高級搜尋查詢編輯器中開啟查詢，請完成查詢並選取 [ **共用] 連結**。

## <a name="access-queries-in-the-github-repository"></a>存取 GitHub 儲存庫中的查詢  
Microsoft 安全研究人員會定期在 [GitHub 上的指定公開儲存庫](https://aka.ms/hunting-queries)中共用進階搜捕查詢。 這個儲存庫開放個人提出貢獻。 若要貢獻，請[免費加入 GitHub ](https://github.com/)。

>[!tip]
>Microsoft 安全研究人員也會提供進階搜捕查詢，您可以用來尋找與新興威脅相關聯的活動和指標。 這些查詢是由 Microsoft Defender 安全性中心中的[威脅分析](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)報告提供。

>[!NOTE]
>本文中的部分表格可能無法在 Microsoft Defender for Endpoint 中使用。 使用更多資料來源[開啟 Microsoft 365 Defender](m365d-enable.md)以搜尋威脅。 您可以遵循[從 microsoft defender for endpoint 遷移高級搜尋查詢](advanced-hunting-migrate-from-mde.md)中的步驟，將您的高級搜尋工作流程從 microsoft defender for endpoint 移至 Microsoft 365 Defender。

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)