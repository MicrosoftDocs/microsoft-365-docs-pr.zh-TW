---
title: 提高匯出 eDiscovery 搜尋結果時的下載速度
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何設定 Windows 登錄，以在下載搜尋結果和資料時增加資料輸送量。
ms.openlocfilehash: a68a616d2dced4a3dd70580e1b258c95a0b5e39e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817672"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results"></a>提高匯出 eDiscovery 搜尋結果時的下載速度

當您使用 eDiscovery 匯出工具在安全性 & 合規性中心下載內容搜尋的結果或從高級 eDiscovery 下載資料時，此工具會啟動特定數目的併發匯出作業，以將資料下載到您的本機電腦。 根據預設，並行作業數目會設定為您要用來下載資料之電腦中的核心數目的8倍。 例如，如果您有一個雙核計算機（即一個晶片上的兩個中央處理單位），則同時匯出作業的預設數目為16。 若要增加資料傳輸輸送量並加速下載程式，您可以在您用來下載搜尋結果的電腦上設定 Windows 登錄設定，以增加並行作業的數目。 若要加速下載程式，建議您從24個同時作業的設定開始。
  
如果您透過低頻寬網路下載搜尋結果，增加此設定可能會造成負面影響。 或者，您也可以將此設定增加至高頻寬網路中超過24個同時作業（同時作業的最大數目為48）。 在您設定此登錄設定之後，您可能需要變更它，以找出您環境的最佳並行作業數目。
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a>建立登錄設定，以在匯出資料時變更同時作業的數目

在電腦上執行下列程式，以從 Security & 合規性中心或從高級 eDiscovery 的資料下載搜尋結果。
  
1. 關閉 eDiscovery 匯出工具（若已開啟）。 
    
2. 使用檔案名尾碼註冊，將下列文字儲存至視窗登錄檔;例如，ConcurrentOperations。 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    如先前所述，我們建議您從24個同時進行的作業開始，然後視需要變更此設定。
    
3. 在 [Windows Explorer] 中，按一下或按兩下您在上一個步驟中建立的 .reg 檔案。
    
4. 在 [使用者存取控制] 視窗中，按一下 **[是]** 讓登錄編輯程式進行變更。 
    
5. 當系統提示您繼續時，請按一下 **[是]**。
    
    登錄編輯器會顯示一則訊息，指出已成功將設定新增至註冊表。
    
6. 您可以重複步驟 2-5，以變更 [登錄] `DownloadConcurrency` 設定的值。 
    
    > [!IMPORTANT]
    > 在您建立或變更登錄 `DownloadConcurrency` 設定之後，請務必建立新的匯出工作或重新開機您要下載之搜尋結果或資料的現有匯出工作。 如需詳細資訊，請參閱[詳細資訊](#more-information)一節。 
  
## <a name="more-information"></a>詳細資訊

- 當您第一次執行您在此程式中建立的 .reg 檔案時，就會建立新的登錄機碼。 然後， `DownloadConcurrency` 每當您變更並重新執行 .reg 編輯檔案時，就會編輯登錄設定。 
    
- EDiscovery 匯出工具使用[Azure AzCopy 公用程式](https://go.microsoft.com/fwlink/?linkid=849949)，從安全性 & 規範中心或從高級 eDiscovery 下載搜尋資料。 設定登錄 `DownloadConcurrency` 設定與執行 AzCopy 公用程式時使用 **/NC**參數類似。 所以登錄設定的 `"DownloadConcurrency=24"` 效果與使用 AzCopy 公用程式的參數值相同 `/NC:24` 。 
    
- 如果您停止目前正在進行的匯出下載，然後重新開機它（嘗試再次下載搜尋結果），eDiscovery 匯出工具會嘗試繼續相同的下載。 因此，如果您開始下載，請停止它，然後變更登錄 `DownloadConcurrency` 設定，當您重新開機時（按一下 [**下載匯出的結果**]），下載可能會失敗。 這是因為匯出工具會嘗試使用不正確設定來繼續先前的下載，因為您已變更登錄設定。
    
    因此，變更登錄設定之後 `DownloadConcurrency` ，請務必在安全性 & 規範中心內重新開機匯出工作（按一下 [**重新開機匯出**]）。 然後您可以下載匯出的結果。 如需匯出搜尋結果和資料的詳細資訊，請參閱：
    
  - [匯出內容搜尋結果](export-search-results.md)
    
  - [在高級電子檔探索中匯出結果](export-results-in-advanced-ediscovery.md)
    
