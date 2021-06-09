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
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: 編輯您的本機電腦上的 Windows 登錄，以在從安全性 & 規範中心匯出內容搜尋結果時停用報告。
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817852"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>當您匯出內容搜尋結果時停用報告

當您使用 eDiscovery 匯出工具在安全性 & 合規性中心匯出內容搜尋的結果時，此工具會自動建立及匯出包含匯出內容之其他資訊的兩個報告。 這些報告為 Results.csv 檔和 Manifest.xml 檔案 (請參閱本主題中 [關於停用「匯出報告](#frequently-asked-questions-about-disabling-export-reports) 」一節的常見問題，以取得這些報告) 的詳細描述。 因為這些檔案可能非常大，所以您可以透過防止匯出這些檔案，加快下載時間，並節省磁碟空間。 您可以在用來匯出搜尋結果的電腦上，變更 Windows 登錄來執行此動作。 如果您想要稍後加入報告，您可以編輯登錄設定。 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>建立登錄設定以停用匯出報告

在您要用來匯出結果的電腦上執行下列程式，以進行內容搜尋。
  
1. 關閉 eDiscovery 匯出工具（若已開啟）。
    
2. 根據您要停用的匯出報表，執行下列其中一項或兩項步驟。
    
    - **Results.csv**
    
      使用檔案名尾碼註冊，將下列文字儲存至 Windows 登錄檔案中;例如，DisableResultsCsv。
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      使用檔案名尾碼註冊，將下列文字儲存至 Windows 登錄檔案中;例如，DisableManifestXml。
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. 在 Windows Explorer 中，按一下或按兩下您在先前步驟中建立的 .reg 檔案。
    
4. 在 [使用者存取控制] 視窗中，按一下 **[是]** 讓登錄編輯程式進行變更。 
    
5. 當系統提示您繼續時，請按一下 **[是]**。
    
    登錄編輯器會顯示一則訊息，指出已成功將設定新增至註冊表。
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>編輯登錄設定以重新啟用匯出報告

如果您停用 Results.csv，並在先前程式中建立 .reg 檔案以 Manifest.xml 報告，您可以編輯這些檔案，以重新啟用報告，使其與搜尋結果一起匯出。 此外，在您要用來匯出結果內容搜尋的電腦上執行下列程式。
  
1. 關閉 eDiscovery 匯出工具（若已開啟）。
    
2. 編輯您在先前程式中建立的其中一個或兩個 .reg 編輯檔案。
    
    - **Results.csv**
    
        在記事本中開啟 DisableResultsCsv 檔案，將值變更 `False` 為，然後 `True` 儲存檔案。 例如，編輯檔案之後，它看起來像這樣：
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        在記事本中開啟 DisableManifestXml 檔案，將值變更 `False` 為，然後 `True` 儲存檔案。 例如，編輯檔案之後，它看起來像這樣：
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. 在 Windows Explorer 中，按一下或按兩下您在上一個步驟中編輯的 .reg 檔案。
    
4. 在 [使用者存取控制] 視窗中，按一下 **[是]** 讓登錄編輯程式進行變更。 
    
5. 當系統提示您繼續時，請按一下 **[是]**。
    
    登錄編輯器會顯示一則訊息，指出已成功將設定新增至註冊表。
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>停用匯出報告的常見問題

 **Results.csv 和 Manifest.xml 報表為何？**
  
Results.csv 和 Manifest.xml 檔案包含匯出內容的其他資訊。
  
- **Results.csv** 包含每個專案的相關資訊的 Excel 檔，該專案會做為搜尋結果下載。 針對電子郵件，結果記錄檔包含每封郵件的相關資訊，包括： 
    
  - 來源信箱中郵件的位置 (，包含郵件是在主要或封存信箱) 中。
    
  - 傳送或接收郵件的日期。
    
  - 郵件的主旨行。
    
  - 郵件的寄件者和收件者。
    
  - 當您匯出搜尋結果時啟用重復資料刪除時，郵件是否是重複的郵件。 重複郵件會在 **Parent ItemId** ] 欄中，將值識別為重複郵件。 **Parent ItemId** ] 欄中的值與所匯出郵件之 [**專案 DocumentId** ] 欄中的值相同。 
    
    針對來自 SharePoint 和商務用 OneDrive 網站的檔，結果記錄檔包含每個檔的相關資訊，包括：
    
  - 檔的 URL。
    
  - 檔所在之網站集合的 URL。
    
  - 上次修改檔的日期。
    
  - 位於結果記錄檔的 [主旨] 欄中的檔 (名稱) 。
    
- **Manifest.xml** 包含搜尋結果中所包含之每個專案相關資訊的資訊清單檔案 (以 XML 格式) 。 此報告中的資訊與 Results.csv 報告相同，但其格式為「電子 Discovery 參考模型」 (EDRM) 所指定的格式。 如需 EDRM 的詳細資訊，請前往 [https://www.edrm.net](https://www.edrm.net) 。
    
 **何時應該停用匯出這些報告？**
  
這取決於您的特定需求。 許多組織不需要搜尋結果的額外資訊，而且不需要這些報告。
  
 **我需要執行此動作的電腦為何？**
  
 您必須在執行 eDiscovery 匯出工具的任何本機電腦上變更登錄設定。 
  
 **變更此設定後，是否需要重新開機電腦？**
  
否，您不需要重新開機電腦。 不過，如果正在執行 eDiscovery 匯出工具，您必須關閉它，然後在變更登錄設定之後重新開機它。
  
 **是否已編輯現有登錄機碼，或是建立新的金鑰？**
  
當您第一次執行您在本主題的程式中所建立的 .reg 檔案時，就會建立新的登錄機碼。 然後，每當您變更並重新執行 .reg 編輯檔案時，就會編輯設定。
