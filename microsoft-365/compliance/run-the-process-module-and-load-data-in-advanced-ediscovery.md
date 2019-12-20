---
title: 執行處理序模組及載入 Office 365 進階電子文件探索中的資料
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
description: '了解如何使用 Office 365 安全性&amp;合規性中心存取 Office 365 進階電子文件探索及執行處理序模組的案例。  '
ms.openlocfilehash: ac0b36f17b891f28b4d34ba838551da2de778b17
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802926"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a>執行處理序模組及載入 Office 365 進階電子文件探索中的資料

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
本節說明進階電子文件處理序模組的功能。 
  
除了檔案資料，例如檔案類型、 副檔名、 位置或路徑、 建立日期和時間、 作者、 custodian 和主旨的中繼資料可以載入至進階電子文件探索，並儲存為每個案例。 有些中繼資料的計算方式進階電子文件，例如載入原生檔案時。 
  
進階電子文件提供系統中繼資料值，例如近似重複群組或相關性分數。 由系統管理員可以新增其他中繼資料，例如檔案註釋。 
  
## <a name="running-process"></a>執行程序

> [!NOTE]
> 批次號碼指派給檔案程序期間允許的追蹤檔案。 批次數目也可讓重新處理選項的程序批次的識別。 其他篩選器可用來篩選由批次數目和工作階段。 
  
執行下列步驟來執行處理程序。
  
1. [開啟 Office 365 安全性&amp;合規性中心](go-to-the-securitycompliance-center.md)。 
    
2. 移至**搜尋&amp;調查** \> **eDiscovery** ，然後按一下 [**移至進階電子文件**。
    
3. 在進階電子文件，在顯示的**案例**] 頁面中選取適當的情況下，按一下 [**前往案例**。
    
4. 在 [**準備** \> **程序** \> **安裝程式**，從可用的容器清單容器選取。
    
    ![按一下 [新增至案例的搜尋結果的程序](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. 如果您想要作為植入的檔案或預先標記檔案新增容器，請按一下 [**進階設定...** ]。 
    
    使用植入的檔案來加速問題的訓練與低豐富性 (通常是 2%或更少)。 對於植入的檔案，建議您選取各種是否相關檔案和處理程序的相關 20-50 種子每 （植入的檔案太多可以扭曲相關性結果） 的問題。 植入的檔案應該檢閱同一位人員給將訓練問題。
    
    使用預先標記的檔案來自動化相關性訓練。 您應該標記至少 1500 檔案，並新增至相關性集合相同保留之非相關檔案相關的比例。 這些檔案應該手動標記，而且您應該以內的標記品質。
    
    ![螢幕擷取畫面的進階設定] 頁面上的處理批次檔案](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - 在 [**種子**] 區段中： 
    
    選擇 [**標示成已植入的檔案**，即可將容器標示為植入的檔案。 您也需要選擇要指派給每此問題： 從**問題**下拉式清單。 從**標籤**下拉式清單中選擇**相關**或**不相關**。 
    
    > [!NOTE]
    > 一旦您設定檔案作為**植入**，您無法將它們標示為**預先標記**。 
  
  - 在 [**預先標記的檔案**] 區段中： 
    
    選擇 [**標示成已預先標記檔案**可將標示預先標記檔案中的容器]。 您也需要將它們指派每此問題： 從**問題**下拉式清單。 從**標籤**下拉式清單中選擇**相關**或**不相關**。 
    
    > [!NOTE]
    > 一旦您設定檔做為**預先標記**時，您無法將它們標示為**植入**。 
  
  - 在 [**電子郵件標記**] 區段中。 已處理的電子郵件的哪個部分會被標示為植入或預先標記的設定。 
    
6. 若要開始，請按一下 [**程序**。 完成時，會顯示處理程序的結果。
    
7. （選用）如果您需要指派給特定 custodian 的資料來源，您可以新增和編輯中**Custodians** custodian 名稱\> **Custodians**中的**管理**] 和 [指派 custodians \> **指派**。 
    
如果您新增至案例，然後您可以再次處理。
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[檢視處理序模組結果](view-process-module-results-in-advanced-ediscovery.md)

