---
title: 匯出 eDiscovery 搜尋結果時變更 PST 檔案的大小
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 您可以變更預設的 PST 檔案大小，當您匯出 eDiscovery 搜尋結果下載到您的電腦。
ms.openlocfilehash: 9deb90e688617981499bee286b95a0442fa1a1b4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595930"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>匯出 eDiscovery 搜尋結果時變更 PST 檔案的大小

當您匯出 eDiscovery 搜尋的電子郵件結果從不同的 Microsoft eDiscovery 工具使用 Office 365 電子文件探索匯出工具時，可匯出的 PST 檔案的預設大小為 10 GB。 如果您想要變更此預設的大小，您可以編輯您用來匯出搜尋結果的電腦上的 Windows 登錄。 若要這麼做的原因之一是讓 PST 檔案可容納抽取式媒體、 這類 DVD、 光碟片或 USB 磁碟機上。 
  
> [!NOTE]
> Office 365 電子文件探索匯出工具用來匯出搜尋結果時使用內容搜尋工具中的安全性與合規性中心，就地 eDiscovery 在 Exchange Online 和 SharePoint Online 中的 eDiscovery 中心。
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>建立要變更的 PST 檔案大小，當您匯出 eDiscovery 搜尋結果的登錄設定

您要使用可匯出的 eDiscovery 搜尋結果的電腦上執行下列程序。
  
1. 如果它已經開啟，請關閉 Office 365 電子文件探索匯出工具。 
    
2. 將下列文字儲存到視窗登錄檔案中，使用.reg; 檔名尾碼例如，PstExportSize.reg。 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    在範例中，與上述`PstSizeLimitInBytes`值設為 1,073,741,824 位元組或大約 1 GB。 以下是一些其他範例值`PstSizeLimitInBytes`設定。 
    
    |**調整大小以 GB （大約）**|**大小 （位元組）**|
    |:-----|:-----|
    |0.7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. 變更`PstSizeLimitInBytes`值，當您匯出搜尋結果，並再將檔案儲存為 PST 檔案所需最大大小。 
    
4. 在 Windows 檔案總管] 中，按一下或按兩下您在先前步驟中建立的.reg 檔案。
    
5. 在 [使用者存取控制] 視窗中，按一下 [ **]** 讓登錄編輯程式中進行的變更。 
    
6. 出現提示時若要繼續，按一下 **[是]**。
    
    登錄編輯程式中會顯示訊息，說明設定已成功新增至登錄。
    
7. 您可以重複執行步驟 3 至 6，若要變更的值為`PstSizeLimitInBytes`登錄設定。 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>當您匯出 eDiscovery 搜尋結果時變更 PST 檔案的預設大小的相關的常見問題集

 **原因是 [預設大小為 10 GB 嗎？**
  
10 GB 的預設大小已根據客戶意見反應。10 GB 是內容的最佳中單一 PST 與檔案損毀的最小機會量間的良好平衡。
  
 **我應該增加或減少 PST 檔案的預設大小？**
  
客戶通常會減少的大小限制，使搜尋結果將會放在其實際可以運送到其組織中其他位置的抽取式媒體上。 我們不建議您增加預設的大小，因為 PST 檔案大於 10GB 可能已損毀問題。
  
 **我有執行這項作業電腦為何？**
  
您要變更您在執行 Office 365 電子文件探索匯出工具的任何本機電腦上的登錄設定。
  
 **變更此設定後，必須將電腦重新開機嗎？**
  
否，您不需要重新開機。 但是，如果執行 Office 365 電子文件探索匯出工具，您必須關閉它，並重新啟動後您變更此設定。
  
 **沒有現有的登錄機碼取得編輯或沒有取得建立新的金鑰嗎？**
  
新的登錄機碼會建立第一次執行您在此程序中建立的.reg 檔案。 然後設定編輯的每當您變更並重新執行.reg 編輯檔案。
