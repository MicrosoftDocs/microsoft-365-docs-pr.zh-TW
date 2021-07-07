---
title: 測試套件指導方針
description: 回顧有關測試套件的指導方針
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322586"
---
# <a name="test-package-guidelines"></a>測試套件指導方針

## <a name="1---script-referencing"></a>1. 腳本參考

當您將 .zip 檔案上傳至入口網站時，會將該檔案的所有內容解壓縮至根資料夾。 您不需要撰寫任何程式碼即可執行此初始解壓縮作業。 您也可以使用相對於所上傳的 zip 檔案的路徑，參考 .zip 內的任何檔案。

在下列範例中，我們會示範如何從 [任務] 索引標籤的 [輸入] 欄位中參照二進位檔案/腳本。藍色的文字應該輸入 [**腳本路徑**] 欄位中，**而不需要用引號** 括住。

請務必注意，在上傳之前，您的 zip 檔案中的內容。 當您將資料夾壓縮時，您的本機機器會在 zip 檔案下建立一個主資料夾。 在此情況下，參考將會如下列 **粗體** 所示：

 **Contoso_App_Folder.zip**
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - ScriptX.ps1 – **"Contoso_App_Folder/ScriptX.ps1"**
  - Script.ps1 – **"Contoso_App_Folder/folder1/script.ps1"**

其他情況下，您的 zip 檔案可能會有您的檔案或內容，但沒有第二層資料夾：

 **Zip_file_uploaded.zip**
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - ScriptX.ps1 – **"ScriptX.ps1"**
  - Script.ps1 – **"folder1/script.ps1"**
  
## <a name="2---script-execution"></a>2. 腳本執行

**Out-of-Box 測試：** 應用程式套件至少要包含三個 PowerShell 腳本，可執行應用程式及其相依專案的自動安裝、啟動和關閉。 每個腳本都應該處理其自己的必要條件、驗證成功，以及在必要的情況下 (執行) 。

**功能測試：** 應用程式套件必須包含至少一個 PowerShell 腳本。 在提供多個腳本的情況下，腳本會在上傳順序中執行，而在特定腳本中的失敗將停止執行後續的腳本。

### <a name="script-requirements"></a>腳本需求

• PowerShell 5.1 版以上的版本 +     

•自動執行    

•錯誤回復碼               

•驗證成功            

•記錄至腳本特定記錄資料夾

在測試管線中，每個腳本都必須完全以無人值守的方式執行。

> [!Note]
> 在成功完成時，腳本應會傳回 "0"，如果執行期間發生任何錯誤，則為非零錯誤代碼。

每個腳本應該會驗證它是否順利運行。 舉例來說. 安裝腳本應該檢查是否存在系統上的某些二進位代碼和/或登錄機碼，在安裝程式二進位檔執行完畢後，請確定安裝成功的適當程度。 

若要正確診斷測試執行期間發生錯誤的情況，這是必要的，例如，無法成功安裝應用程式，而不能啟動應用程式。

> [!Important]
> 請 **避免下列情況：** 腳本不應該重新開機電腦，如果有必要重新開機，請在腳本上載期間指定此項。

## <a name="3---log-collection"></a>3. 記錄檔集合

每個腳本都應該輸出其所產生的任何記錄到名為的資料夾中 ```logs``` 。 名為的目錄中的所有資料夾 ```logs``` ，將會複製並提交至頁面上供下載 ```Test Results``` 。

例如，安裝腳本 (可能位於 **應用程式/腳本/安裝** 目錄) 中，可將其記錄輸出至：記錄檔 **/安裝記錄** 檔，最後的記錄將位於： **Apps/script/install/logs/install .log。**

系統會同時選取檔案及其他 ```install.log``` 資料夾中的其他檔案 ```logs``` ，並將其重新整理以供下載。


## <a name="4---application-binaries"></a>4. 應用程式二進位檔案

任何二進位檔案和相依性應包含在單一 zip 檔案中。 

這些都應該包括安裝應用程式所需的一切 (例如，應用程式安裝程式) ;若應用程式對任何 framework （如 .net Core/Standard or .NET Framework）都有相依性，這些元件應該會包含在檔案中，並可在所提供的腳本中正確地加以參照。


> [!Note]
> 上傳的 zip 檔案名稱中不能有任何空格或特殊字元

## <a name="next-steps"></a>後續步驟

請移至下一篇，以查看一些常見問題 **(常見問題)**
> [!div class="nextstepaction"]
> [下一步](faq.md)
