---
title: 匯出 eDiscovery 搜尋結果從 Office 365 時，增加的下載速度
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: 了解如何設定 Windows 登錄，以增加資料輸送量，從安全性 & 合規性中心] 及 [進階電子文件探索中 Office 365 下載搜尋結果，並搜尋資料時。
ms.openlocfilehash: 44f595e6beffcc3d6789ad7b6f70ad77a48381cb
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076992"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a>匯出 eDiscovery 搜尋結果從 Office 365 時，增加的下載速度

當您使用 Office 365 電子文件探索匯出工具來下載安全性 & 合規性中心的內容搜尋的結果或下載 Office 365 進階電子文件探索中的資料時，此工具會啟動若要下載的並行匯出作業數目到本機電腦的資料。 根據預設，同時進行的作業數目設為 8 的次數中您要用來下載資料之電腦的核心。 例如，如果您有雙核心電腦 （亦即一晶片上的兩個管理中心處理單位），同時進行匯出作業的預設數為 16。 若要增加資料傳輸輸送量並提升並下載程序，您可以藉由使用若要下載搜尋結果的電腦上設定 Windows 登錄設定增加同時進行的作業數目。 為了提升並下載程序，我們建議您以設定為 24 同時進行的作業開始。
  
如果您透過低頻寬網路下載搜尋結果，請增加此設定可能會造成負面影響。 或者，您可以增加到超過 24 同時進行的作業 （同時進行的作業的最大數目為 48） 的高頻寬網路中的設定。 設定此登錄設定之後，您可能必須變更，以找出最佳的同時進行的作業，為您的環境。
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a>建立登錄設定來匯出資料時變更的同時進行的作業數目

您將搜尋結果下載來自安全 & 與規範中心或進階電子文件中的資料使用的電腦上執行下列程序。
  
1. 如果它已經開啟，請關閉 Office 365 電子文件探索匯出工具。 
    
2. 將下列文字儲存到視窗登錄檔案中，使用.reg; 檔名尾碼例如，ConcurrentOperations.reg。 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    如同先前的說明，我們建議您開始使用 24 同時進行的作業，，，然後變更 [視需要此設定。
    
3. 在 Windows 檔案總管] 中，按一下或按兩下您在上一個步驟中建立的.reg 檔案。
    
4. 在 [使用者存取控制] 視窗中，按一下 [ **]** 讓登錄編輯程式中進行的變更。 
    
5. 出現提示時若要繼續，按一下 **[是]**。
    
    登錄編輯程式中會顯示訊息，說明設定已成功新增至登錄。
    
6. 您可以重複執行步驟 2-5 若要變更的值為`DownloadConcurrency`登錄設定。 
    
    > [!IMPORTANT]
    > 在您建立或變更之後`DownloadConcurrency`登錄設定，請務必建立新的匯出工作或重新啟動現有匯出作業的搜尋結果或您想要下載的資料。 請參閱如需詳細資訊的[詳細資訊](#more-information)一節。 
  
## <a name="more-information"></a>詳細資訊

- 新的登錄機碼會建立第一次執行您在此程序中建立的.reg 檔案。 然後在`DownloadConcurrency`登錄設定編輯的每當您變更，然後重新執行.reg 編輯檔案。 
    
- Office 365 電子文件探索匯出工具會使用[Azure AzCopy 公用程式](https://go.microsoft.com/fwlink/?linkid=849949)來下載搜尋資料，從安全性 & 合規性中心或進階電子文件。 設定`DownloadConcurrency`登錄設定是類似於執行 AzCopy 公用程式時使用 **/NC**參數。 這樣的登錄設定`"DownloadConcurrency=24"`會有相同效果： 使用的參數值`/NC:24`AzCopy 公用程式。 
    
- 如果您要停止匯出下載仍在建構中，然後將其重新 （嘗試再次下載搜尋結果），Office 365 電子文件探索匯出工具會嘗試繼續的相同下載。 因此，如果您啟動下載，停止，，然後變更`DownloadConcurrency`登錄設定，下載可能會失敗如果重新啟動 （藉由按一下 [**下載匯出的結果**)。 這是因為匯出工具將會嘗試繼續使用無效，因為您已變更的登錄設定的設定先前下載。
    
    因此，當您變更`DownloadConcurrency`登錄設定，請務必重新啟動匯出工作 （按一下 [**重新啟動匯出**) 安全性 & 合規性中心。 然後您可以下載匯出的結果。 如需有關匯出搜尋結果和資料的詳細資訊，請參閱：
    
  - [匯出內容搜尋結果](export-search-results.md)
    
  - [在 Office 365 進階電子文件探索中匯出結果](export-results-in-advanced-ediscovery.md)
    
