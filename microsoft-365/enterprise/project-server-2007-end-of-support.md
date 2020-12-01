---
title: Project Server 2007 終止支援藍圖
ms.author: efrene
author: efrene
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
ms.assetid: d379018f-72b7-4284-b40a-6c23c8ae38fe
description: 在2017年10月10日，project Server 2007、專案公事包伺服器及專案2007的支援結束。 請立即使用本文規劃升級。
ms.openlocfilehash: f59b319ec39c6b2d1df0876c916332491f1bb0f6
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519796"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Project Server 2007 終止支援藍圖

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

支援在2017中已結束 Office 2007 伺服器及應用程式，您必須考慮遷移的計畫。 如果您目前使用的是 Project Server 2007 和相關產品，請注意下列支援終止的日期：
  
|**產品**|**支援日期結束**|
|:-----|:-----|
|Project Server 2007  <br/> |2017 年 10 月 10 日  <br/> |
|專案公事包伺服器2007  <br/> |2017 年 10 月 10 日  <br/> |
|Project 2007 Standard  <br/> |2017 年 10 月 10 日  <br/> |
|Project 2007 專業版  <br/> |2017 年 10 月 10 日  <br/> |
   
如需有關 Office 2007 伺服器即將退休的詳細資訊，請參閱 [從 Office 2007 伺服器升級至用戶端產品](upgrade-from-office-2007-servers-and-products.md)。
  
## <a name="what-does-end-of-support-mean"></a>*支援終止的* 意義為何？

大部分的 Microsoft 產品都有支援週期，讓他們取得新功能、錯誤修正、安全性修正等等。 此生命週期一般會從產品的初始發行版本持續10年。 此週期的結尾稱為產品的支援終止。 由於 Project Server 2007 于2017年10月10日到達其支援的結尾，所以 Microsoft 不再提供：
  
- 可能發生問題的技術支援。
    
- 針對可能會影響伺服器穩定性和可用性問題的錯誤修正。
    
- 安全性修正程式可能會導致伺服器遭受安全性破壞的漏洞。
    
- 時區更新。
    
在此日期之後，Project Server 2007 的安裝會繼續執行。 但由於先前所列的變更，強烈建議您儘早從 Project Server 2007 進行遷移。
  
## <a name="what-are-my-options"></a>我有哪些選擇？

如果您使用的是 Project Server 2007，您必須探索遷移選項，其中包括：
  
- 遷移至 Project Online
    
- 遷移至較新的內部部署版本的 Project Server (最好的 Project Server 2016) 
    
|**為什麼我想要遷移至 Project Online**|**為什麼我想要遷移至 Project Server 2016**|
|:-----|:-----|
| 我有行動使用者。  <br/> <br/>遷移成本是 (硬體、軟體、時間，以及執行) 的工作的重點。 <br/><br/>  遷移後，維護環境所需的成本是主要的考慮 (例如，「自動更新」、「保證時間」等等) 。  <br/> | 商務規則限制我在雲端中運作我的公司。<br/><br/>  我需要控制環境的更新。  |
   
> [!NOTE]
> 如需從您的 Office 2007 伺服器移動選項的詳細資訊，請參閱 [協助您從 office 2007 伺服器及用戶端升級的資源](upgrade-from-office-2007-servers-and-products.md)。 請注意，Project Server 不支援混合式設定，因為 Project Server 和 Project Online 無法共用相同的資源集區。 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>從 Project Server 2007 遷移時的重要考慮

當您規劃從 Project Server 2007 遷移時，請考慮下列事項：
  
- 從 Project Server 2007 **取得 Microsoft 合作夥伴的協助** 會非常困難，而且需要進行許多準備和規劃。 如果您不是最初設定 Project Server 2007 的人員，可能特別有挑戰性。 幸運的是，Microsoft 協力廠商可以協助您，不論您計畫要遷移至 Project Server 2016 或 Project Online。 搜尋 Microsoft 合作夥伴，以協助您在 [Microsoft Partner Center](https://go.microsoft.com/fwlink/p/?linkid=841249)上進行遷移。 在「  *黃金專案」和「產品群組管理* 」上進行搜尋，以查看所有在 Project 中具備專業知識的 Microsoft 合作夥伴清單。 
    
- **規劃自訂** -許多您在 project server 2007 環境中所做的自訂，當您遷移至 project server 2016 或 project Online 時，可能無法運作。 在不同的版本之間，Project Server 架構的差異很大。 所支援的作業系統、資料庫伺服器及用戶端網頁瀏覽器也不同。 規劃如何測試或重新建立新環境的自訂專案。 規劃也為考慮是否仍需要每個自訂專案提供了一個不錯的機會。 如需詳細資訊，請參閱＜[Create a plan for current customizations during upgrade to SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=842061)＞。 
    
- **時間和耐心** 升級的規劃、執行及測試需要時間和精力，尤其是在您升級至 Project Server 2016 時。 例如，如果您從 Project Server 2007 遷移至 Project Server 2016，您必須先遷移至 Project Server 2010，檢查您的資料，然後在遷移至每個後續版本時執行相同的動作。 您可能想要與 Microsoft 合作夥伴核對，以取得所需的時間及成本的預估。
    
## <a name="migrate-to-project-online"></a>遷移至 Project Online

如果您選擇從 Project Server 2007 遷移至 Project Online，您可以執行下列動作以手動遷移專案計劃資料：
  
1. 將專案方案從 Project Server 2003 儲存為 mpp 格式。
    
2. 在 Project Professional 2013、Project Professional 2016 或 Project Online 桌面用戶端中，開啟每一個 mpp 檔案，然後將其儲存併發布到 Project Online。
    
您可以在 Project Online 中以手動方式建立 Microsoft Project Web App (PWA) 設定。 例如，重新建立任何必要的自訂欄位或企業行事曆。 Microsoft 合作夥伴也可協助您進行此程式。
  
主要資源：
  
|**資源**|**描述**|
|:-----|:-----|
|[Project Online 快速入門](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |如何設定和使用 Project Online <br/> |
|[Project Online 服務說明](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |可供您使用之不同 Project Online 方案的相關資訊 <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>遷移至較新的內部部署版本的 Project Server

我們強烈相信您可以透過遷移至 Project Online，獲得最佳的價值和使用者經驗。 不過，我們也知道某些組織需要將專案資料保留在內部部署環境中。 如果您選擇將專案資料保留在內部部署中，您可以將 Project Server 2007 環境遷移至 Project Server 2010、Project Server 2013 或 Project Server 2016。
  
如果您無法遷移至 Project Online，建議您將遷移至 Project Server 2016。 Project Server 2016 包含舊版本 Project Server 的所有功能。 雖然有些功能只能在 Project Online 中使用，但它與 Project Online 可用的體驗最為接近。
  
每次遷移之後，您應該檢查您的資料是否已順利遷移。
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>如何遷移至 Project Server 2016？

Project Server 2007 與 Project Server 2016 之間的架構差異會防止直接遷移路徑。 因此，您必須將 Project Server 2007 資料移轉至 Project Server 的每個後續版本，直到達到 Project Server 2016 為止。
  
請遵循下列步驟，以進行 Project Server 2016：
  
1. 從 Project Server 2007 遷移至 Project Server 2010。
    
2. 從 Project 將2010遷移至 Project Server 2013。
    
3. 從 Project Server 2013 遷移至 Project Server 2016。
    
每次遷移後，請確定您的資料已順利遷移。
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>步驟1：從 Project Server 2007 遷移至 Project Server 2010

如需從 Project Server 2007 升級至 Project Server 2010 所需執行之作業的完整說明，請參閱 [upgrade To Project server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812)。
  
主要資源：
  
|**資源**|**描述**|
|:-----|:-----|
|[Project Server 2010 升級概述](https://go.microsoft.com/fwlink/p/?linkid=841813) <br/> |從 Project Server 2007 升級至 Project Server 2010 時，所需執行之作業的高層次視圖 <br/> |
|[規劃升級到 Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841815) <br/> |從 Project Server 2007 升級為 Project Server 2010 （包括系統需求）時的規劃考慮  <br/> |
   
#### <a name="how-do-i-upgrade"></a>如何升級？

如需詳細資訊，請參閱 [升級至 Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812)。 不過，請務必瞭解，您可以使用兩種不同的方法來進行升級：
  
- **資料庫附加升級：** 此方法只會升級環境的內容，而不是設定設定。 如果您是從 Office Project Server 2007 （只支援32作業系統的硬體）進行升級，則需要此專案。 資料庫附加升級方法有兩種類型：
    
  - **資料庫附加 *完整升級*** -會遷移儲存在 Office project Server 2007 資料庫中的專案資料，以及儲存在 SharePoint 內容資料庫中的 Microsoft project Web App 網站資料。
    
  - **資料庫附加 *核心升級*** -僅遷移 project Server 資料庫中儲存的專案資料。
    
- **就地升級**：伺服器陣列的設定資料和伺服器陣列上的所有內容都會在現有的硬體上以固定順序升級。 當您啟動升級程式時，安裝程式會讓整個伺服器陣列離線。 在升級完成之前，網站與 Microsoft Project Web App 網站都無法使用，然後安裝程式會重新開機伺服器。 在您開始就地升級之後，就無法暫停升級或回退至先前的版本。 最好是製作實際執行環境的鏡像影像，並對此環境執行就地升級，而不是在實際執行環境中。 
    
其他資源：
  
- [Microsoft Project Server 2010 升級的 SuperFlow](https://go.microsoft.com/fwlink/p/?linkid=841277)
    
- [從 Project Server 2007 遷移至 Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841278)
    
- [Project Web App 網頁元件的升級考慮](https://go.microsoft.com/fwlink/p/?linkid=841276)
    
- [專案軟體發展工具組 (SDK) ](https://go.microsoft.com/fwlink/p/?linkid=841275)
    
### <a name="step-2-migrate-to-project-server-2013"></a>步驟2：遷移至 Project Server 2013

在您確認資料順利遷移後，下一步是遷移至 Project Server 2013。
  
如需從 Project Server 2010 升級至 Project Server 2013 所需執行之作業的完整說明，請參閱 [upgrade To Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)。 
  
主要資源：
  
|**資源**|**描述**|
|:-----|:-----|
|[Project Server 2013 升級程式概述](https://go.microsoft.com/fwlink/p/?linkid=841822) <br/> |從 Project Server 2010 升級至 Project Server 2013 時，所需執行的工作  <br/> |
|[規劃升級到 Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823) <br/> |從 Project Server 2010 升級為 Project Server 2013 （包括系統需求）時的規劃考慮 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>升級至此版本的相關事項

[Project Server 2013 升級的新功能](https://go.microsoft.com/fwlink/p/?linkid=841824) 說明此版本升級的重要變更。 最值得注意的是： 
  
- 沒有就地升級至 Project Server 2013。 資料庫附加方法是唯一支援的方法，可從 Project Server 2010 升級至 Project Server 2013。
    
- 升級程式不僅會將您的 Project Server 2010 資料轉換成 Project Server 2013 格式，還會將這四個 Project Server 2010 資料庫合併成單一 Project Web App 資料庫。
    
- 在2013版本中，SharePoint Server 和 Project Server 都會變更為宣告式驗證。 如果您使用的是傳統驗證，則必須考慮升級的這一因素。 如需詳細資訊，請參閱＜[在 SharePoint 2013 中從傳統模式移轉至宣告式驗證](https://go.microsoft.com/fwlink/p/?linkid=841825)＞。
    
其他資源：
  
- [升級到 Project Server 2013 的升級程序概觀](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [升級您的資料庫與 Project Web App 網站集合 (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Microsoft Project Server 升級過程圖表](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [極佳的資料庫整合，Project Server 2010 至2013遷移，8個簡單的步驟](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>步驟3：遷移至 Project Server 2016

在您確認資料順利遷移後，下一步是遷移至 Project Server 2016。
  
如需從 Project Server 2013 升級至 Project Server 2016 所需執行之作業的完整說明，請參閱 [upgrade To Project server 2016](https://docs.microsoft.com//project/upgrading-to-project-server-2016)。
  
主要資源：
  
|**資源**|**描述**|
|:-----|:-----|
|[Project Server 2016 升級程序概觀](https://go.microsoft.com/fwlink/p/?linkid=841260) <br/> |從 Project Server 2013 升級至 Project Server 2016 時，所需執行的工作 <br/> |
|[規劃升級到 Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841826) <br/> |從 Project Server 2013 升級為 Project Server 2016 的規劃考慮 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>升級至此版本的相關事項

[關於 Project Server 2016 升級，您需要瞭解的事項](https://go.microsoft.com/fwlink/p/?linkid=841827) 會告訴您，此版本的升級有重要的變更，包括：
  
- 當您建立要遷移 Project Server 2013 資料的 Project Server 2016 環境時，Project Server 2016 安裝檔案會包含在 SharePoint Server 2016 中。 如需詳細資訊，請參閱 [部署 Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829)。
    
- 資源計劃在 Project Server 2016 中已被取代。 您的 Project Server 2013 資源計劃將遷移至 Project Server 2016 和 Project Online 中的資源預訂。 如需詳細資訊，請參閱 [綜述： Resource 預訂](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 。 
    
## <a name="migrate-from-portfolio-server-2007"></a>從產品群組伺服器2007遷移

專案公事包伺服器2007與 Project Server 2007 搭配使用，以用於公事包策略、優先順序和優化。 在此版本之後，不會建立其他版本的專案產品群組伺服器。 不過，Project Server 2016 的公事包管理功能和 Project Online 的 Premium 版本都是可用的。 不過，來自 Project 產品群組伺服器2007的資料不能遷移到這兩者。 必須重新建立諸如商務驅動程式之類的資料。
  
其他資源：
  
- [Project Online 服務說明：](https://go.microsoft.com/fwlink/p/?linkid=841280) 請參閱 Project Server 2016 和 Project Online Premium 中包含的產品群組管理功能。
    
- [Microsoft Office 專案公事包伺服器2007遷移指南。](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>相關主題

[SharePoint Server 2007 終止支援藍圖](sharepoint-2007-end-of-support.md)
  
[協助您從 Office 2007 伺服器及用戶端升級的資源](upgrade-from-office-2007-servers-and-products.md)
  
