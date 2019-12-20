---
title: 在 Microsoft 威脅防護進階搜捕中使用共用查詢
description: 立即開始威脅搜捕，並使用預先定義的共用查詢。 將您的查詢與大眾或您的組織共用。
keywords: 進階搜捕, 威脅搜捕, 網路威脅搜捕, 搜尋, 查詢, 遙測, 自訂偵測, 結構描述, kusto, github 儲存庫, 我的查詢, 共用查詢
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: fb8addc7bc9e8ab01cc72bbdf02c12559d263196
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808688"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>在進階搜捕中使用共用查詢

適用於：****
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

您可以在同一個組織的多位使用者之間共用[進階搜捕](advanced-hunting-overview.md)查詢。 您也可以在 GitHub 尋找公開的查詢。 這些查詢可讓您快速地執行特定威脅搜捕案例，而不需要從頭開始撰寫查詢。

![共用查詢的影像](../images/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>儲存、修改及共用查詢
您可以儲存新的或現有的查詢，以便只有組織中的其他使用者能存取或共用。 

1. 建立或修改查詢。 

2. 按一下 [儲存查詢]**** 下拉式按鈕，然後選取 [另存新檔]****。
    
3. 輸入查詢的名稱。 

   ![儲存查詢的影像](../images/advanced-hunting-save-query.png)

4. 選取您要儲存查詢的資料夾。
    - **共用的查詢** — 與組織的所有使用者共用
    - **我的查詢** —只有您可以存取
    
5. 選取 [儲存]****。 

## <a name="delete-or-rename-a-query"></a>刪除或重新命名查詢
1. 以滑鼠右鍵按一下您要重新命名或刪除的查詢。

    ![刪除查詢的影像](../images/advanced_hunting_delete_rename.png)

2. 選取 [刪除]**** 並確認刪除。 或選取 [重新命名]****，並為查詢提供新名稱。

## <a name="access-queries-in-the-github-repository"></a>存取 GitHub 儲存庫中的查詢  
Microsoft 安全研究人員會定期在 [GitHub 上的指定公開儲存庫](https://github.com/microsoft/MTP-AHQ)中共用進階搜捕查詢。 這個儲存庫開放個人提出貢獻。 若要貢獻，請[免費加入 GitHub ](https://github.com/)。

>[!tip]
>Microsoft 安全研究人員也會提供進階搜捕查詢，您可以用來尋找與新興威脅相關聯的活動和指標。 這些查詢是由 Microsoft Defender 安全性中心中的[威脅分析](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)報告提供。

## <a name="related-topics"></a>相關主題
- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)