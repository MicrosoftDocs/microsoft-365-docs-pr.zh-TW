---
title: 在 Microsoft 威脅防護進階搜捕中使用共用查詢
description: 立即開始威脅搜捕，並使用預先定義的共用查詢。 將您的查詢與大眾或您的組織共用。
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，自訂偵測，schema，kusto，github 儲存機制，我的查詢，共用查詢
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7cdb15be274c89bd92995b9e947489c62521c6bb
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429680"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>在進階搜捕中使用共用查詢

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：****
- Microsoft 威脅防護



您可以在同一個組織的多位使用者之間共用[進階搜捕](advanced-hunting-overview.md)查詢。 您也可以在 GitHub 尋找公開的查詢。 這些查詢可讓您快速地執行特定威脅搜捕案例，而不需要從頭開始撰寫查詢。

![共用查詢的影像](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>儲存、修改及共用查詢
您可以儲存新的或現有的查詢，以便只有組織中的其他使用者能存取或共用。 

1. 建立或修改查詢。 

2. 按一下 [儲存查詢]**** 下拉式按鈕，然後選取 [另存新檔]****。
    
3. 輸入查詢的名稱。 

   ![儲存查詢的影像](../../media/advanced-hunting-save-query.png)

4. 選取您要儲存查詢的資料夾。
    - **共用的查詢** — 與組織的所有使用者共用
    - **我的查詢** —只有您可以存取
    
5. 選取 [儲存]****。 

## <a name="delete-or-rename-a-query"></a>刪除或重新命名查詢
1. 以滑鼠右鍵按一下您要重新命名或刪除的查詢。

    ![刪除查詢的影像](../../media/advanced_hunting_delete_rename.png)

2. 選取 [刪除]**** 並確認刪除。 或選取 [重新命名]****，並為查詢提供新名稱。

## <a name="create-a-direct-link-to-a-query"></a>建立查詢的直接連結
若要產生連結，以直接在高級搜尋查詢編輯器中開啟查詢，請完成查詢並選取 [ **共用] 連結**。

## <a name="access-queries-in-the-github-repository"></a>存取 GitHub 儲存庫中的查詢  
Microsoft 安全研究人員會定期在 [GitHub 上的指定公開儲存庫](https://aka.ms/hunting-queries)中共用進階搜捕查詢。 這個儲存庫開放個人提出貢獻。 若要貢獻，請[免費加入 GitHub ](https://github.com/)。

>[!tip]
>Microsoft 安全研究人員也會提供進階搜捕查詢，您可以用來尋找與新興威脅相關聯的活動和指標。 這些查詢是由 Microsoft Defender 安全性中心中的[威脅分析](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)報告提供。

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [搜捕裝置、電子郵件、應用程式和身分識別](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
