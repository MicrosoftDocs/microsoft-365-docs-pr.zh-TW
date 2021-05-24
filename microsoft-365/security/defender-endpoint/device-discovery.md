---
title: 裝置探索概觀
description: 瞭解如何利用 Microsoft 365 Defender 中的端點探索，尋找您網路中未受管理的裝置
keywords: 裝置探索，探索，被動式，主動，網路，可視性，伺服器，工作站，板載，未受管理的裝置
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ed4e0c477bd2a8840e920b337f05c8730965bcff
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636239"
---
# <a name="device-discovery-overview"></a>裝置探索概觀

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

保護您的環境需要清查您網路中的裝置。 不過，網路中的對應裝置通常會成本高、富有挑戰性且耗時。 

Microsoft Defender for Endpoint 提供裝置探索功能，可協助您尋找連接至公司網路的未受管理裝置，而不需要額外裝置或繁瑣的處理常式變更。


裝置探索功能可讓您：

- **探索連線到公司網路的企業端點** <br>
您可以使用初級或 standard 探索選項，探索尚未架至 Microsoft Defender for Endpoint 的工作站、伺服器及行動端點。  

- **上架探索到的端點**<br>
網路中未受管理的端點會向您的網路引進弱點和風險。 將其上架至服務可提高安全性。 

結合這項功能，在現有威脅和弱點管理經驗中，將會提供對 Microsoft Defender for Endpoint 之板載裝置的新安全性建議。



## <a name="discovery-methods"></a>探索方法
探索分為兩個模式： 

-   基本探索 
-   建議的標準探索 ()  


> [!IMPORTANT]
> 探索已設定為基本模式。 您可以選擇透過 [設定] 頁面保留此設定。 Standard discovery 會成為從2021年7月19日開始之所有客戶的預設模式，除非透過 [設定] 頁面在此日期之前修改。

### <a name="basic-discovery"></a>基本探索 

在此模式中，端點會被動收集您網路中的事件，並從這些事件析取裝置資訊。 基本探索使用 SenseNDR.exe 用於被動式網路資料收集的二進位，而且不會啟動任何網路流量。 端點只會從架裝置所看到的每個網路流量提取資料。 

### <a name="standard-discovery"></a>標準探索 

此模式可讓端點主動探查網路中的觀測裝置，以濃縮收集的資料，以協助您建立可靠且連貫的設備清查。 標準模式使用智慧主動探測，探索有關所觀察裝置的詳細資訊，以濃縮現有的裝置資訊。  

啟用標準模式時，由組織中的網路監視工具可能會觀測出探索感應器所產生的最小和不計的網路活動。  

 如果您選擇不啟用此模式，您的網路中只會獲得有限的非受管理端點的可見度。

Standard discovery 使用各種 PowerShell 腳本，在網路上主動探查裝置。 這些 PowerShell 腳本是由 Microsoft 簽署，並從下列位置執行： `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps` 。 例如，`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`。

您可以變更及自訂探索設定，如需詳細資訊，請參閱 [Configure device discovery](configure-device-discovery.md)。

> [!NOTE]
> 探索引擎會區別公司網路中所接收的網路事件與公司網路以外的網路事件。 未連接到公司網路的裝置將不會被探索或列在設備清查中。 



## <a name="device-inventory"></a>裝置清單 
已發現但尚未由 Microsoft Defender for Endpoint 架及保護的裝置，將會列在 [端點] 索引標籤的 [裝置庫存] 中。您現在可以在名為「上架狀態」的裝置庫存清單清單中使用新的篩選器，其可具有下列任何值：

- 架–端點是架至 Microsoft Defender for Endpoint。
- 可以是架–端點已在網路中探索，且已將作業系統識別為 Microsoft Defender for Endpoint 所支援，但目前並未架。 我們強烈建議您將這些裝置上架。
- 不受支援–端點已在網路中探索，但無法由 Microsoft Defender for Endpoint 所支援。
- 資訊不足–系統無法決定裝置的支援。 在網路上的更多裝置上啟用標準探索，可以豐富探索的屬性。 
 

![裝置庫存儀表板的影像](images/2b62255cd3a9dd42f3219e437b956fb9.png)

> [!TIP]
> 您永遠可以套用篩選器，以從裝置庫存清單中排除未受管理的裝置。 您也可以在 API 查詢上使用 [上架狀態] 欄，以篩選出未受管理的裝置。 

## <a name="vulnerability-assessment-on-discovered-devices"></a>已探索裝置上的漏洞評估
裝置上的漏洞和風險，以及網路中已發現的其他受管理裝置，都屬於「Security 建議」底下的目前 TVM 流程，而且會在整個入口網站中以實體頁面表示。 搜尋「SSH」相關的安全性建議，以尋找與非管理裝置相關的 SSH 安全性漏洞。 

![安全性建議儀表板的影像](images/1156c82ffadd356ce329d1cf551e806c.png)  

## <a name="use-advanced-hunting-on-discovered-devices"></a>在探索的裝置上使用高級搜尋
您可以使用高級搜尋查詢，以取得已探索裝置的知名度。
尋找 DeviceInfo 表格中已探索端點的詳細資料，或 DeviceNetworkInfo 表格中這些裝置的網路相關資訊。
  

![高級搜尋使用的影像](images/f48ba1779eddee9872f167453c24e5c9.png)


裝置探索利用 Microsoft Defender for Endpoint 架裝置作為網路資料來源，以進行非架裝置的屬性活動。 這表示，如果 Microsoft Defender for Endpoint 架裝置與非架裝置通訊，則在時程表上或透過 [高級搜尋 DeviceNetworkEvents] 表格可看到非架裝置上的活動。 



新的事件是傳輸控制通訊協定 (TCP) 連線，而且會符合目前的 DeviceNetworkEvents 配置。 在啟用的非 Microsoft Defender 端點中，TCP 入口至 Microsoft Defender for Endpoint 的裝置。  

也新增了下列動作類型：  

- ConnectionAttempt-嘗試 (syn) 建立 TCP 連接  
- ConnectionAcknowledged-已接受 TCP 連線的認可 (syn\ack)   

您可以嘗試此範例查詢：  

```
DeviceNetworkEvents  
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"  
| take 10  
```


## <a name="changed-behavior"></a>已變更行為
下列章節列出當啟用此功能時，您會在 Microsoft Defender for Endpoint 和/或 Microsoft 365 Security Center 中看到的變更。 
 
1.  未架至 Microsoft Defender to Endpoint 的裝置應該會出現在設備清查、高級搜尋和 API 查詢中。 這可能會大幅增加查詢結果的大小。 
    1. Advanced 搜尋中的 "DeviceInfo" 和 "DeviceNetworkInfo" 資料表現在會保留探索的裝置。 您可以使用 "OnboardingStatus" 屬性來篩選出那些裝置。

    2. 探索的裝置應該會出現在流式 API 查詢結果中。 您可以在查詢中使用篩選來篩選出那些裝置 `OnboardingStatus` 。 

2.  根據定義的準則，未受管理的裝置會指派給現有的裝置群組。 
3.  在極少的情況下，Standard discovery 可能會在網路監視器或安全性工具上觸發警示。 如果您經歷這類事件，請提供意見反應，以協助避免這些問題重複發生。 您可以明確地排除特定目標或整個子網，使其積極地透過 Standard discovery 進行探測。 



## <a name="next-steps"></a>後續步驟
- [設定裝置探索](configure-device-discovery.md)
- [裝置探索 FAQs](device-discovery-faq.md)
