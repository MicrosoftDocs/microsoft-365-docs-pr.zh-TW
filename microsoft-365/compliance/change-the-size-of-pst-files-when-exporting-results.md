---
title: 在匯出 eDiscovery 搜尋結果時變更 PST 檔案的大小
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
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 當您匯出 eDiscovery 搜尋結果時，您可以變更下載到電腦的 PST 檔案的預設大小。
ms.openlocfilehash: eb5fcce037ff5e3444b42c996b4a32d818edd29d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942916"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>在匯出 eDiscovery 搜尋結果時變更 PST 檔案的大小

當您使用 eDiscovery 匯出工具從不同的 Microsoft eDiscovery 工具匯出 eDiscovery 搜尋的電子郵件結果時，可以匯出的 PST 檔案的預設大小為 10 GB。 如果您想要變更此預設大小，您可以在用來匯出搜尋結果的電腦上，編輯 Windows 的註冊表。 執行這項作業的一個原因是，您可以在卸除式媒體（例如 DVD、光碟或 USB 磁片磁碟機）上容納 PST 檔案。 
  
> [!NOTE]
> 在 [安全性 & 規範中心] 中使用「內容搜尋」工具、In-Place ediscovery Exchange Online，以及 SharePoint Online 中的 ediscovery 中心，可使用 ediscovery 匯出工具匯出搜尋結果。
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>當您匯出 eDiscovery 搜尋結果時，建立登錄設定以變更 PST 檔案的大小

在您要用來匯出 eDiscovery 搜尋結果的電腦上執行下列程式。
  
1. 關閉 eDiscovery 匯出工具（若已開啟）。 
    
2. 使用檔案名尾碼註冊，將下列文字儲存至視窗登錄檔;例如，PstExportSize。 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    在上面的範例中，此  `PstSizeLimitInBytes` 值設為1073741824位元組或大約 1 GB。 以下是設定的一些其他範例值  `PstSizeLimitInBytes` 。 
    
    |**大小，以 GB 為單位 ()**|**大小（位元組）**|
    |:-----|:-----|
    |0.7 GB (700 MB)   <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. `PstSizeLimitInBytes`當您匯出搜尋結果時，將值變更為所需的 PST 檔案大小上限，然後儲存檔案。 
    
4. 在 Windows Explorer 中，按一下或按兩下您在先前步驟中建立的 .reg 檔案。
    
5. 在 [使用者存取控制] 視窗中，按一下 **[是]** 讓登錄編輯程式進行變更。 
    
6. 當系統提示您繼續時，請按一下 **[是]**。
    
    登錄編輯器會顯示一則訊息，指出已成功將設定新增至註冊表。
    
7. 您可以重複步驟 3-6，以變更 [登錄]  `PstSizeLimitInBytes` 設定的值。 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>當您匯出 eDiscovery 搜尋結果時，變更 PST 檔案預設大小的常見問題

 **為何預設大小為 10 GB？**
  
10 GB 的預設大小是根據客戶的意見反應而定。10 GB 是在單一 PST 中的最佳內容量與最小可能的檔案損毀之間的完美平衡。
  
 **是否應該增加或減少 PST 檔案的預設大小？**
  
客戶傾向于減少大小限制，讓搜尋結果能容納在其實際運送至其組織中其他位置的可移除媒體。 建議您不要增加預設大小，因為 PST 檔案大於 10 GB 時可能有損毀問題。
  
 **我需要執行此動作的電腦為何？**
  
您必須在您執行 eDiscovery 匯出工具的任何本機電腦上變更登錄設定。
  
 **變更此設定後，是否需要重新開機電腦？**
  
否，您不需要重新開機電腦。 不過，如果 eDiscovery 匯出工具正在執行，您必須關閉它，然後在變更此設定之後重新開機它。
  
 **是否已編輯現有登錄機碼，或是建立新的金鑰？**
  
當您第一次執行您在此程式中建立的 .reg 檔案時，就會建立新的登錄機碼。 然後，每當您變更並重新執行 .reg 編輯檔案時，就會編輯設定。
