---
title: 當您匯出內容搜尋結果時停用報告
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: 編輯 Windows 登錄在本機電腦上，停用的報表，當您從 Office 365 中的安全性 & 合規性中心匯出內容搜尋的結果。 停用這些報告可加速下載時間，並將儲存的磁碟空間。
ms.openlocfilehash: 99f8079bdbb0a3a43d0306dcf6b6ca8ab2c4fbef
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595238"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>當您匯出內容搜尋結果時停用報告

當您要匯出其結果的安全性 & 合規性中心的內容搜尋使用 Office 365 電子文件探索匯出工具時，工具會自動建立，並匯出包含匯出內容相關的其他資訊的兩個報表。 這些報告是 Results.csv 和 Manifest.xml 檔案 （請參閱本主題的詳細說明這些報告的[常見問題集關於停用匯出報告](#frequently-asked-questions-about-disabling-export-reports)一節）。 因為這些檔案可能會很大，您可以加速下載時間，並藉由防止這些檔案所匯出儲存的磁碟空間。 您可以藉由變更您用來匯出搜尋結果的電腦上的 Windows 登錄來這麼做。 如果您想要包含在稍後的報告，您可以編輯的登錄設定。 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>建立登錄設定來停用匯出報告

您將使用來將結果匯出內容搜尋的電腦上執行下列程序。
  
1. 如果它已經開啟，請關閉 Office 365 電子文件探索匯出工具。
    
2. 執行下列一或兩個以下的步驟中，視哪些匯出報告您要停用。
    
    - **Results.csv**
    
      將下列文字儲存到 Windows 登錄檔中，使用.reg; 檔名尾碼例如，DisableResultsCsv.reg。
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      將下列文字儲存到 Windows 登錄檔中，使用.reg; 檔名尾碼例如，DisableManifestXml.reg。
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. 在 Windows 檔案總管] 中，按一下或按兩下您在先前步驟中建立的.reg 檔案。
    
4. 在 [使用者存取控制] 視窗中，按一下 [ **]** 讓登錄編輯程式中進行的變更。 
    
5. 出現提示時若要繼續，按一下 **[是]**。
    
    登錄編輯程式中會顯示訊息，說明設定已成功新增至登錄。
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>編輯若要重新啟用匯出報告的登錄設定

如果您停用 [Results.csv] 及 [Manifest.xml 報表在先前的程序中建立.reg 檔案，您可以編輯若要重新啟用報表，以便在搜尋結果匯出這些檔案。 同樣地，您將用來將結果匯出內容搜尋的電腦上執行下列程序。
  
1. 如果它已經開啟，請關閉 Office 365 電子文件探索匯出工具。
    
2. 編輯一或兩個您在先前的程序中建立的.reg 編輯檔案。
    
    - **Results.csv**
    
        開啟 [記事本] 中的 DisableResultsCsv.reg 檔案變更值`False`以`True`，然後儲存檔案。 例如，您可以編輯檔案之後，它看起來像這樣：
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        開啟 [記事本] 中的 DisableManifestXml.reg 檔案變更值`False`以`True`，然後儲存檔案。 例如，您可以編輯檔案之後，它看起來像這樣：
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. 在 Windows 檔案總管] 中，按一下或按兩下您在上一個步驟中編輯.reg 檔案。
    
4. 在 [使用者存取控制] 視窗中，按一下 [ **]** 讓登錄編輯程式中進行的變更。 
    
5. 出現提示時若要繼續，按一下 **[是]**。
    
    登錄編輯程式中會顯示訊息，說明設定已成功新增至登錄。
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>停用匯出報告相關的常見問題集

 **什麼是 Results.csv 和 Manifest.xml 報告？**
  
將 Results.csv 和 Manifest.xml 檔案包含匯出內容相關的其他資訊。
  
- **Results.csv** Excel 文件包含在搜尋結果會下載每個項目的相關資訊。 電子郵件，結果記錄檔會包含每個郵件的資訊包括： 
    
  - 來源信箱中的郵件的位置 (包括郵件是否處於主要或封存信箱)。
    
  - 郵件已傳送或接收的日期。
    
  - 從郵件主旨行。
    
  - 寄件者和收件者的郵件。
    
  - 郵件是否重複的郵件如果匯出搜尋結果時，啟用重複資料刪除。 重複的郵件將會在**父項目識別碼**] 欄中識別為重複郵件具有值。 **父項目識別碼**] 欄中的值是匯出之郵件的 [**項目 DocumentId** ] 欄中的值相同。 
    
    文件的 SharePoint 和 OneDrive for Business 網站，結果記錄檔包含每個文件的資訊包括：
    
  - 文件的 URL。
    
  - 文件所在之網站集合的 URL。
    
  - 上次修改文件的日期。
    
  - （這位於結果記錄檔中的 [主旨] 欄） 的文件的名稱。
    
- **Manifest.xml**中資訊清單檔案 （XML 格式），其中包含搜尋結果中包含每個項目的相關資訊。 此報告中的資訊會與 [Results.csv] 報告中，相同，但它的格式指定所電子搜索參照模型 (EDRM)。 如需有關 EDRM 的詳細資訊，請移至[https://www.edrm.net](https://www.edrm.net)。
    
 **何時應該停用匯出這些報告？**
  
這取決於您的特定需求。 許多組織不需要搜尋結果的其他資訊，而不需要這些報告。
  
 **我有執行這項作業電腦為何？**
  
 您必須變更您在執行 Office 365 電子文件探索匯出工具的任何本機電腦上的登錄設定。 
  
 **變更此設定之後，我有重新啟動電腦？**
  
否，您不需要重新啟動電腦。 但如果執行 Office 365 電子文件探索匯出工具，您必須關閉它，然後重新啟動它之後變更的登錄設定。
  
 **沒有現有的登錄機碼取得編輯或沒有取得建立新的金鑰嗎？**
  
新的登錄機碼會建立第一次執行您在本主題中的程序中建立的.reg 檔案。 然後設定編輯的每當您變更，然後重新執行.reg 編輯檔案。
