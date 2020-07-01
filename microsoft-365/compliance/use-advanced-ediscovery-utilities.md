---
title: 使用進階電子文件探索公用程式
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: 深入瞭解 Advanced eDiscovery 中的公用程式，包括案例記錄、清除資料、處理常式錯誤、修改相關性及透明分析。
ms.openlocfilehash: 4283bc7bea509c8a01fb45c433964230a5256f8a
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936616"
---
# <a name="use-advanced-ediscovery-classic-utilities"></a>使用進階電子文件探索 (傳統版) 公用程式

> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
在高級 eDiscovery 中顯示並可用的公用程式，取決於內容和使用者角色。
  
## <a name="case-log"></a>案例記錄

案例記錄會提供應用程式處理活動的詳細清單，可用於追蹤、疑難排解以及定址錯誤和警告。 記錄可以產生，並儲存在主機或伺服器的本機上，或直接傳送至電子郵件地址。
  
記錄檔也可以下載到用戶端的電腦。 您可以根據設定和使用者角色，啟用或停用用戶端下載選項。
  
1. 在功能表列中，按一下 [ **Cogwheel** ] 圖示。 
    
2. 在 [**設定與實用 \> 程式公用程式**] 索引標籤中，選取 [**案例記錄檔 \> 設定**]。
    
3. 選取**記錄層級**，如下所示： 
    
  - **Standard**：包括基本記錄資料。 這通常是監視的必要條件，除非另有建議，否則應該使用此選項。
    
  - **最低**：適用于非常大的情況，只會傳回最新的資料。
    
4. 按一下 [**執行案例記錄**]。 會產生記錄並顯示路徑。 目前及最後一項任務的任務進度資訊會顯示在 [任務狀態] 窗格中。
    
## <a name="clear-data"></a>清除資料

若有必要刪除或重新初始化 case 資料，必須先初始化資料庫實例。 Clear data 公用程式會從案例資料庫、文字檔、案例資料夾及累計結果中刪除所有指定的專案。 只有管理員才能執行該功能。
  
> [!IMPORTANT]
> 此巨集指令是不可逆的，會清除專家所執行的所有相關性標記和分析。 視需要儲存資料的備份。 請特別小心使用此選項。 刪除已標記和排名的檔案可能會影響相關性結果。 
  
1. 在功能表列中，按一下 [ **Cogwheel** ] 圖示。 
    
2. 在 [**設定與實用 \> 程式公用程式**] 索引標籤中，選取 [**清除資料 \> 安裝**]。
    
3. 選取要初始化的資訊選項：
    
  - **相關性**：刪除所有在相關性中完成的工作，包括要載入之檔案的負載和關聯的定義。 它會刪除所有的範例及標記。
    
  - **近乎重複的和電子郵件的執行緒**：刪除近期重複的分析資訊和電子郵件執行緒。
    
  - **主題**：刪除主題相關的資料。
    
  - **匯出歷程記錄**：刪除匯出批次的記錄資訊。
    
4. 按一下 [**清除資料**]。 清除案例資料。 目前及最後一項任務的任務進度資訊會顯示在 [**任務狀態**] 窗格中。 
    
## <a name="modify-relevance"></a>修改相關性

本節說明如何略過或回復相關性範例。
  
1. 在功能表列中，按一下 [ **Cogwheel** ] 圖示。 
    
2. 在 [**設定與實用 \> 程式公用程式**] 索引標籤中，選取 [**修改相關性**]。
    
3. 從選項中選取： 
    
  - **Skip current sample-針對目前的使用者**：這會在開啟案例範例中，標記為**Skip**，所有未標記的檔案都是執行公用程式的使用者。 在標記為**略過**的檔案上不會執行相關性處理。
    
  - **Skip current sample-所有開啟的範例**：這將會標記為**Skip**，所有使用者開啟的範例中的所有未標記檔案。 如果使用者目前正在標記範例，則不建議使用此選項。
    
  - **回復上一個範例**：不管是在「計算」處理常式之前或之後，都將會回復的最後一個已完成相關性訓練範例。 不允許復原追趕範例。
    
4. 按一下 [**執行**] 執行。 
    
## <a name="transparency-analysis"></a>透明度分析

「透明度分析」公用程式會啟用檔案及其所指派相關性分數的詳細視圖。 報告可以做為健全檢查，也可以比較人類審校所定義之檔案的相關性，與「高級 eDiscovery」所指派的相關性相較。 
  
除了相關性分數之外，高級 eDiscovery 還會計算並指派考慮關鍵字內容的關鍵字權重。 檔案中的同一個字可以指派不同的權重，視內容和位置而定。 每個關鍵字都會使用增加的色彩濃度（從黃色到深橙色）和不同的灰色陰影來標示。 色彩編碼是用來以視覺方式指出字詞相對於相關性分數的相對正負號或負數。 
  
在多重問題案例案例中，可能會針對每個問題產生透明分析報告。
  
1. 在功能表列中，按一下 [ **Cogwheel** ] 圖示。 
    
2. 在 [**設定與實用 \> 程式公用程式**] 索引標籤中，選取 [**透明度分析 \> 設定**]。
    
3. 在 * * 檔識別碼 * * 中，輸入要處理之檔案的檔案識別碼。
    
4. 在 [**問題**] 清單中，選取相關的問題。 
    
5. 按一下 [**透明分析**]。 完成後，會顯示檔案的「透明度分析」報告，其中會顯示標示的關鍵字色彩如何與整體相關性分數相關聯。
    
## <a name="see-also"></a>請參閱

[進階電子文件探索 (傳統版)](office-365-advanced-ediscovery.md)
  
[定義案例與租使用者設定](define-case-and-tenant-settings-in-advanced-ediscovery.md)

