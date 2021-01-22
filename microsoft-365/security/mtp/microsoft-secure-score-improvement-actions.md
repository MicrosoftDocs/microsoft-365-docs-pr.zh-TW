---
title: 透過 Microsoft 安全分數來評估您的安全性工作
description: 說明如何採取動作來改善 Microsoft 365 資訊安全中心的 Microsoft 安全分數。
keywords: Microsoft 安全分數， 安全分數， Office 365 安全分數， Microsoft 安全性分數， Microsoft 365 安全性中心， 改進動作
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 8cf416e773abc6cbe1fd891fcec9f02a5011c413
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930639"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>使用 Microsoft 安全分數來評估您的安全性工作

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 安全分數是組織安全性措施的度量，數位越高，表示已採取更多改進動作。 您可以在 https://security.microsoft.com/securescore [Microsoft 365 資訊安全中心找到。](overview-security-center.md)

為了説明您更快速地瞭解您需要的資訊，Microsoft 改進動作分為多個群組：

* Azure Active Directory (身分識別&角色) 
* 裝置 (Microsoft Defender for Endpoint，稱為[Microsoft 裝置安全分數) ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)
* App (電子郵件和雲端 App，包括 Office 365 和 Microsoft 雲端 App 安全性) 

>[!NOTE]
>在最新發佈的 Microsoft 安全分數中，已推出改良的計分模型，讓 Microsoft 安全分數暫時與身分識別安全分數和圖形 API 不相容。 [檢視詳細資料](microsoft-secure-score-whats-new.md)

在 Microsoft 安全分數概觀頁面中，查看在這些群組中分數的分配與可用的分數。 您也可以全面查看總計分數、安全分數的歷史趨勢和基準比較，以及可採取哪些改進動作來改進分數的優先順序。

![安全分數首頁](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>檢查您目前的分數

若要檢查您目前的分數，請前往 Microsoft 安全分數概觀頁面，並尋找顯示您安全分數 **的磚**。 您的分數會以百分比顯示，以及您可能在總計可能分數中已成就的點數。

此外，如果您選取分數旁邊的包含按鈕，您可以選擇不同的分數視圖。 這些不同的分數視圖會顯示在分數磚和點分解圖的圖形中。

以下是您可以加到您整體分數的視圖中的分數，以更完整地瞭解整體分數：

- **計畫分數**：完成計畫的動作時顯示預計的分數
- **目前的授權分數**：顯示目前的 Microsoft 授權可以達到的分數
- **可成就的** 分數：顯示能與 Microsoft 授權和目前風險接受度一起達成的成績

如果您已經包含所有可能的分數視圖，此視圖看起來會像這樣：

![您的安全分數，包括計畫分數、目前的授權分數和可達成的成績](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>採取動作以改善您的分數

改進 **動作按鈕** 會列出能解決可能攻擊面的安全性建議。 它也包括其狀態 (位址、計畫、接受的風險、透過協力廠商解決、透過替代的風險降低和已完成) 。 您可以搜尋、篩選及分組所有改進動作。  

### <a name="ranking"></a>排名

排名是根據要達到的點數、執行困難、使用者影響和複雜度來計算。 排名最高的改進動作有大量的剩餘點數，其困難度、使用者影響和複雜度都較低。

### <a name="view-improvement-action-details"></a>查看改進動作詳細資料

當您選取特定的改進動作時，會出現一個完整頁面飛出視窗。  

![改進動作飛出顯示範例](../../media/secure-score/secure-score-improvement-action-details.png)

若要完成動作，您有幾個選項：

- 選取 **管理** 以前往組選畫面，然後進行變更。 接著，您就會獲得動作值得一讀的點數，顯示在飛出飛出中。點數更新通常約需要 24 小時。

- 選取 **共用** 以複製改進動作的直接連結。 您也可以選擇共用連結的平臺，例如電子郵件、Microsoft Teams、Microsoft Planner 或 ServiceNow。 選取 ServiceNow 將讓您建立在 ServiceNow 和 Microsoft 365 資訊安全中心首頁中可見的變更票證。 若要深入瞭解，請參閱 [Microsoft 365 資訊安全中心與 ServiceNow 整合](tickets-security-center.md)。

新增 **記** 事以追蹤進度或您想要新增批註的任何專案。 如果您在 **改進動作中** 加入自己的標記，您可以根據這些標記進行篩選。

### <a name="choose-an-improvement-action-status"></a>選擇改進動作狀態

選擇任何改進動作的特定狀態並記錄附注。

- **解決** - 您瞭解改進動作是必要的，並計畫在未來某一點解決。 此狀態也適用于偵測為部分完成但尚未完成的動作。
- **已規劃** - 有具體的計畫可完成改進動作。
- **接受的風險** - 安全性應一定會與可用性保持平衡，而並非每個建議都適用于您的環境。 在這種情況下，您可以選擇接受風險或其餘風險，而不是增加改進動作。 您將不會獲得任何點數，但改進動作清單中將不會再顯示該動作。 您可以在歷程記錄中查看此動作，或隨時復原。
- **透過協力廠商解決****並透過替代** 風險降低方式解決 - 協力廠商應用程式或軟體或內部工具已經解決改進動作。 您將獲得值得執行的動作分數，這樣您的分數就更能夠反映整體的安全性表現。 如果協力廠商或內部工具已不再涵蓋該控制項，您可以選擇其他狀態。 請記住，如果改進動作標示為這些狀態之一，Microsoft 將完全無法看到完整的執行。

#### <a name="threat--vulnerability-management-improvement-actions"></a>威脅&弱點管理改進動作

對於「裝置」類別中的改進動作，您無法選擇狀態。 相反地，系統將會將您導向 Microsoft [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) Defender 資訊安全中心的相關威脅和弱點管理[安全性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)建議以採取行動。 您選擇和理由的例外會限制于該入口網站。 它不會在 Microsoft 安全分數入口網站中。

#### <a name="completed-improvement-actions"></a>已完成的改進動作

一旦完成改善動作的所有可能重點後，改進動作會進入「已完成」狀態。 已完成的改進動作雖然 Microsoft 資料已確認，但您無法變更狀態。

### <a name="assess-information-and-review-user-impact"></a>評估資訊並評論使用者影響

名為快速 **流覽的區** 段會告訴您類別、可防範的攻擊以及產品。

**如果使用者** 有改進行動，使用者的影響會受到影響，而受影響的使用者會受到影響。 

### <a name="implement-the-improvement-action"></a>執行改進動作

The **Implementation section** shows any prerequisites， step-by-step next steps to complete the improvement action， the current implementation status of the improvement action， and any learn more links.

先決條件包括解決改進動作之前需要的任何授權或需完成的動作。 請確定您的授權中有足夠的座位以完成改進動作，而且這些授權已套用至必要的使用者。  

## <a name="we-want-to-hear-from-you"></a>我們想知道您的想法

如有任何問題，請張貼在安全性、隱私權和合規性& [告訴我們](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 。 我們正在監控社群，並且會為您提供協助。

## <a name="related-resources"></a>相關資源

- [Microsoft 安全分數概觀](microsoft-secure-score.md)
- [追蹤您的 Microsoft 安全分數記錄並達成目標](microsoft-secure-score-history-metrics-trends.md)
- [即將推出的功能](microsoft-secure-score-whats-coming.md)
- [新功能](microsoft-secure-score-whats-new.md)
