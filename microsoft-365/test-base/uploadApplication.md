---
title: Upload 套件
description: 如何將 appplication、二進位檔案和相依性上傳至測試基底
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: e8b4323eda31c55bbf32de0996fc7bd48d54ade2
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322594"
---
# <a name="step-2-uploading-a-package"></a>步驟2：上傳套件

在 [測試基本入口網站] 頁面上，流覽至左導覽列中的「Upload 新套件選項」，如下所示： ![ Upload 新套件](Media/Upload-New-Package.png)

請遵循下列步驟，上傳新的套件。

## <a name="enter-details-for-your-package"></a>輸入套件的詳細資料

在 [測試詳細資料] 索引標籤上，輸入您的套裝軟體名稱、版本及其他詳細資料（如有要求）。 

您可以透過此儀表板執行 **Out-of-Box** 和 **功能測試**。

下列步驟提供如何填寫封裝詳細資料的指南：

1.  **在欄位中輸入要為您的套件提供的名稱 ```“Package name``` 。**

> [!Note]  
> 輸入的套件名稱及版本組合在您的組織中必須是唯一的。 這會透過如下所示的勾選標記加以驗證。
  
  - 如果您選擇重複使用套件的名稱，則其版本號碼必須是唯一的 (亦即，決不會搭配具有該特定名稱) 的套裝軟體一起使用。
  - 如果套件名稱 + 版本的組合不會通過唯一性檢查，您將會看到錯誤訊息，其為 *"package with the package version"*。 

![上傳封裝指令的影像](Media/Instructions.png)

2. **在 [套件版本] 欄位中輸入版本。**

![套件版本](Media/ApplicationVersion.png)

3.  **選取您要在此套件上執行的測試類型**

    **Out-of-Box (OOB)** 測試會執行 *安裝*、*啟動*、*關閉* 和 *卸載* 套件。 安裝之後，在執行單次卸載之前，會重複30次啟動關閉常式。 
    
    這種 OOB 測試為您提供套件上的標準化遙測，以與各 Windows 建立進行比較。

    **功能測試** 會執行您上傳的測試腳本 (s) 套件。 腳本會在上傳順序中執行，在特定腳本中的失敗將會停止執行後續的腳本。

> [!Note]
> **所有** 腳本最多執行80分鐘。 
    
4.  **選取作業系統更新類型**

   - 「安全性更新」可讓您的套件針對 Windows 發行每月的每月安全性更新的增量 churns 進行測試。 
   - 「功能更新」可讓您的套件隨 Windows Windows 的預覽體驗計畫一起更新的測試版本。
<!---
Change to the correct picture
-->
![作業系統更新類型](Media/OSUpdateType.png)

5.  **選取作業系統版本 (s) 以進行安全性更新測試。**

在 [多重選取] 下拉式清單中，選取安裝套件的作業系統版本 (s) Windows。 

  - 若要測試您的套裝軟體只 Windows 用戶端作業系統，請從功能表清單中選取適用的 Windows 11 作業系統版本。
  - 若要測試您的套裝軟體僅限 Windows Server os，請從功能表清單中選取適用的 Windows 伺服器作業系統版本。
  - 若要在 Windows 用戶端和伺服器作業系統上測試套件，請從功能表清單中選取 [所有適用的 os]。 

> [!Note]
> 如果您選擇針對伺服器和用戶端作業系統來測試您的套件，請確定套件是相容的，而且可以在這兩個作業系統上同時執行。


![選取作業系統版本](Media/OSVersion.png)
<!---
Change to the correct picture
-->
6.  **選取功能更新測試的選項：**

  - 在 [選取會員通道] 選項上，選取 ```Windows Insider Program Channel``` 作為套件應測試的組建。
  
    我們目前使用內部版本 flighted 中的組建。

  - 在 [選取要洞察的作業系統基準] 選項上，選取要用來比較測試結果的基準 Windows OS 版本。 

> [!Note]
> 目前不支援伺服器作業系統的功能更新測試
<!---
Note to actual note format for markdown
-->
<!---
Change to the correct picture
-->
![功能更新測試](Media/FeatureUpdate.png)

7.  已完成的測試詳細資料頁面應該如下所示： 

![查看測試詳細資料](Media/TestDetails.png)
## <a name="next-steps"></a>後續步驟

我們接下來的文章將把您的二進位檔案上傳至我們的提供者。
> [!div class="nextstepaction"]
> [下一步](binaries.md)

<!---
Add button for next page
-->

