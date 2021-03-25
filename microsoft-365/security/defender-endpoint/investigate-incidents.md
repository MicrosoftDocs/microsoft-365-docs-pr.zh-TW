---
title: 調查 Microsoft Defender ATP 中的事件
description: 請參閱相關聯的警示、管理事件，以及查看警示中繼資料，以協助您調查事件。
keywords: 調查、事件、警示、中繼資料、風險、偵測來源、受影響的裝置、模式、關聯性
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5a74da55d733d690cb218c78b87b67d6eba6b9d2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186050"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a>調查 Microsoft Defender for Endpoint 中的事件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


調查影響網路的事件、瞭解其含義，以及對照證據進行分析。 

當您調查事件時，您會看到：
- 事件詳細資料
- 事件批註和動作
- 索引標籤 (警示、裝置、調查、證據、圖形) 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a>分析事件詳細資料 
按一下事件以查看 [ **事件] 窗格**。 選取 [ **開啟事件] 頁面** ，查看事件詳細資料和相關資訊 (警示、裝置、調查、證據、圖形) 。 

![事件 details1 的影像](images/atp-incident-details.png)

### <a name="alerts"></a>警示
您可以調查警示，並查看其在事件中如何連結在一起。 根據下列原因，將警示分組到事件：
- 自動調查-自動調查會在調查原始警示時觸發連結的警示 
- 檔特性-與警示相關聯的檔案具有類似的特性
- 手動關聯-手動連結通知的使用者
- Proximate time-警示在特定時間範圍內的相同裝置上觸發
- 同一個檔案-與警示相關聯的檔案完全相同
- 同一個 URL-觸發警示的 URL 完全相同

![[警示] 索引標籤與 [事件詳細資料] 頁面，顯示預警在該事件中的相互關聯原因。](images/atp-incidents-alerts-reason.png)

您也可以管理警示，並查看警示中繼資料及其他資訊。 如需詳細資訊，請參閱 [調查警示](investigate-alerts.md)。 

### <a name="devices"></a>裝置
您也可以調查指定之事件的一部分或相關的裝置。 如需詳細資訊，請參閱 [調查裝置](investigate-machines.md)。

![[事件詳細資料] 頁面中的 [裝置影像] 索引標籤](images/atp-incident-device-tab.png)

### <a name="investigations"></a>調查
選取 [ **調查** ]，查看系統所啟動的所有自動調查，以回應事件警示。

![[事件詳細資料] 頁面中的 [調查] 索引標籤](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a>透過證據
Microsoft Defender for Endpoint 會自動調查事件中的所有受支援事件和可疑實體，以提供 autoresponse 及重要檔案、程式、服務等相關資訊。 

每個分析的實體都會標示為已感染、已修正或可疑。 

![[事件詳細資料] 頁面中的 [證據] 索引標籤](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a>視覺化關聯的 cybersecurity 威脅 
Microsoft Defender for Endpoint 會將威脅資訊匯總到事件中，讓您可以看到來自各種資料點的模式和關聯性。 您可以透過 incident graph 查看這類關聯。

### <a name="incident-graph"></a>事件圖形
**圖形** 會告訴您 cybersecurity 攻擊的故事。 例如，它會顯示進入點，在哪個裝置上觀察到損損或活動的指示器。 等。

![事件圖形的影像](images/atp-incident-graph-tab.png)

您可以按一下事件圖上的圓圈，以查看惡意檔案的詳細資料、相關聯的檔案偵測，以及在全球範圍內有多少個實例（如果有的話），如果有，則表示您的組織中有多少個實例。

![事件詳細資料的影像](images/atp-incident-graph-details.png)

## <a name="related-topics"></a>相關主題
- [事件佇列](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [調查 Microsoft Defender for Endpoint 中的事件](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-incidents)
- [管理 Microsoft Defender for Endpoint 事件](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-incidents)
