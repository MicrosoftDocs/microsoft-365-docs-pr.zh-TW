---
title: 在高級電子檔探索中執行進程模組及載入資料
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
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 瞭解如何使用安全性與 &amp; 合規性中心存取高級 eDiscovery，並執行案例的處理模組。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 011a8448c36ac9f4726f13471c548b7bb2427000
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936156"
---
# <a name="run-the-process-module-and-load-data-in-advanced-ediscovery-classic"></a>在高級 eDiscovery （古典）中執行進程模組和載入資料

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
本節說明高級 eDiscovery 處理模組的功能。 
  
除了檔案資料之外，也可以將中繼資料（例如檔案類型、副檔名、位置或路徑），載入至「高級 eDiscovery」，並針對每個案例加以儲存。 某些中繼資料是由高級 eDiscovery 計算，例如，載入原生檔案時。 
  
Advanced eDiscovery 提供系統中繼資料值，例如接近重複的群組或相關性分數。 其他中繼資料（例如檔案批註）可以由系統管理員新增。 
  
## <a name="running-process"></a>正在執行進程

> [!NOTE]
> 在處理期間，會將批次編號指派給檔案，以允許追蹤檔。 批號也可識別處理選項的處理批次。 其他篩選可依批次號碼和會話進行篩選。 
  
執行下列步驟以執行程式。
  
1. [開啟安全性 &amp;規範中心](go-to-the-securitycompliance-center.md)。 
    
2. 移至 [**搜尋 &amp; 調查** \> **eDiscovery** ]，然後按一下 [**移至高級 eDiscovery**]。
    
3. 在 [Advanced eDiscovery] 的 [顯示**案例**] 頁面中，選取適當的大小寫，然後按一下 [**移至任何情況**]。
    
4. 在 [**準備** \> **處理** \> **程式設定**] 中，從可用的容器清單中選取容器。
    
    ![按一下 [處理常式]，將搜尋結果新增至案例](../media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. 如果您想要將容器新增為 seed 檔案或預先標記的檔案，請按一下 [**高級設定**]。 
    
    使用 seed 檔案，以加速針對較低豐富的問題（通常是2% 或更少）進行訓練。 針對 seed 檔案，建議您選取各種明顯相關的檔案，並處理每個問題大約20-50 種子的處理常式（過於多種子檔可能會歪曲相關性結果）。 Seed 檔案應該由會訓練問題的相同人員進行審閱。
    
    使用預先標記的檔案來自動化相關性訓練。 您應標記至少1500個檔案，並將相關的與非相關檔案的比例保持在集合中，與新增至相關性的集合相同。 這些檔案應以手動方式標記，您應該自信標記品質。
    
    ![處理批次檔案之 [高級設定] 頁面的螢幕擷取畫面](../media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - 在 [ **Seed** ] 區段中： 
    
    選擇 [**標示為種子檔**]，將容器標示為 seed 檔案。 您也需要根據問題的下拉式清單，選擇從**每個問題**進行指派。 從 [**標記**] 下拉式清單中選擇 [**相關**] 或 [**不相關**]。 
    
    > [!NOTE]
    > 將檔案設定為**Seed**後，就無法將其標記為**預先標記**的檔。 
  
  - 在 [**預先標記**的檔案] 區段中： 
    
    選擇 [**標記為預先標記的**檔案]，將容器標示為預先標記的檔案。 您也必須根據問題的下拉式清單，**針對**每個問題進行指派。 從 [**標記**] 下拉式清單中選擇 [**相關**] 或 [**不相關**]。 
    
    > [!NOTE]
    > 將檔案設定為**預先標記**之後，就無法將其標記為**Seed**。 
  
  - 在 [**電子郵件標記**] 區段中。 設定處理的電子郵件的哪一部分會標示為植入或預先標記。 
    
6. 若要開始，請按一下 [**處理**]。 完成時，會顯示流程結果。
    
7. 選如果您需要將資料來源指派給特定的保管人，您可以在**保管人**中新增及編輯保管人名稱， \> **Manage**並在**保管人** \> **指派**中指派保管人。 
    
如果您新增至案例，您可以再次處理。
  
## <a name="related-topics"></a>相關主題

[進階電子文件探索 (傳統版)](office-365-advanced-ediscovery.md)
  
[查看進程模組結果](view-process-module-results-in-advanced-ediscovery.md)

