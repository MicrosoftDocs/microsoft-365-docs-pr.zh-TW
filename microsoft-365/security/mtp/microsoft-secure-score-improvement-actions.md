---
title: 透過 Microsoft 安全分數評估安全性狀況
description: 說明如何採取動作，以改善 Microsoft 365 安全中心的 Microsoft 安全分數。
keywords: 安全性、惡意程式碼、Microsoft 365、M365、安全分數、安全性中心、改進動作
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 3b913b3d53abf8c46fbcc9e053f91f512864c9d8
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315828"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>使用 Microsoft 安全分數評估安全性狀況

Microsoft Secure 得分是組織的安全性狀況度量，具有較高的數目，表示執行的改善動作越多。 可在 https://security.microsoft.com/securescore [Microsoft 365 的安全性中心](overview-security-center.md)找到該網址。

為了協助您更快速地取得所需資訊，Microsoft 改進的動作會組織成群組：

*  (Azure Active Directory 帳戶 & 角色的身分識別) 
* 資料 (Microsoft 資訊保護) 
* 裝置 (Microsoft Defender ATP，稱為 [裝置的 Microsoft 安全分數](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)) 
* App (電子郵件和雲端應用程式，包括 Office 365 和 Microsoft Cloud App Security) 
* 基礎結構 (現在沒有任何改進動作) 

>[!NOTE]
>在最近發行的 Microsoft Secure 得分中，已發行的評分模型已發佈，使 Microsoft 安全分數暫時不相容身分識別安全分數和圖形 API。 [檢視詳細資料](microsoft-secure-score-whats-new.md)

在 [Microsoft Secure 得分一覽] 頁面中，瞭解如何在這些群組間分割點，以及可以使用哪些點數。 您也可以取得總分的整體總分、安全分數的歷史趨勢和基準比較，以及可以採取以改善評分的優先改進動作。

![安全分數首頁](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>檢查您目前的分數

若要檢查您目前的分數，請移至 [Microsoft Secure 得分一覽] 頁面，並尋找包含 **您安全分數**的麻將牌。 您的分數會顯示為百分數，以及您已從總可能點數取得的點數。

此外，如果您選取分數旁邊的 [ **包含** ] 按鈕，您可以選擇不同的分數視圖。 這些不同的分數視圖會顯示在 [分數] 磚和 [點] 分解圖上的圖表中。

以下是您可以新增至您的整體分數視圖的分數，可讓您更完整的整體分數的描述如下：

- 已**計畫分數**：在計畫的動作完成時顯示預計分數
- **目前的授權分數**：顯示可使用您目前的 Microsoft 授權所能達到的分數
- 可**實現分數**：顯示可透過您的 Microsoft 授權和目前的風險接受程度達到的分數

如果您已包含所有可能的分數視圖，則此視圖的外觀會如下：

![您的安全分數，包括已計畫的分數、目前的授權分數，以及能達到的分數](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>採取動作以提升您的分數

[ **改進動作** ] 索引標籤會列出解決可能攻擊曲面的安全性建議。 此外，它還包括其狀態 (，以解決、規劃、接受的風險、透過協力廠商解決，以及透過替代的緩解可解決，以及已完成的) 。 您可以搜尋、篩選和群組所有的「改進」動作。  

### <a name="ranking"></a>排名

排名是根據剩下的點數、實施難度、使用者影響和複雜性而定。 最高排名的「改進」動作具有很大的分數，但有低難度、使用者影響和複雜性。

### <a name="view-improvement-action-details"></a>查看改進動作詳細資料

當您選取特定的 [提升] 動作時，會出現完整的頁面快顯視窗。  

![改進動作飛出範例 ](../../media/secure-score/secure-score-improvement-action-details.png)
 *圖2：改進動作飛出範例*

若要完成此動作，您有幾個選項：

* 選取 [ **管理** ] 以進入設定畫面並進行變更。 接著，您將會在飛出的位置看到必要的動作。點通常需要24小時才能更新。

* 選取 [ **共用** ]，將直接連結複製到 [改進] 動作。 您也可以選擇要共用連結的平臺，例如電子郵件、Microsoft 小組、Microsoft Planner 或 ServiceNow。 選取 [ServiceNow 將可讓您建立 ServiceNow 和 Microsoft 365 安全性中心首頁會顯示的變更票證。 若要深入瞭解，請參閱 [Microsoft 365 security center 和 ServiceNow integration](tickets-security-center.md)。

### <a name="choose-an-improvement-action-status"></a>選擇改進動作狀態

選擇 [改進] 動作特有的任何狀態和記錄附注。

- **若要解決** 此事項-您可以辨識改進動作是必要的，並計畫于未來某一點進行處理。 這種狀態也適用于已偵測到部分但未完全完成的動作。
- 已**計畫**-已有適當的計畫可完成改進動作。
- 已**接受風險**-安全性絕對應該與可用性進行平衡，而不是每個建議適用于您的環境。 在這種情況下，您可以選擇接受風險或餘下的風險，而不會制定改進動作。 您不會獲得任何點數，但是動作將不再顯示在 [改進動作] 清單中。 您可以在歷史記錄中查看此動作，也可以隨時復原。
- **透過協力廠商解決** ，並 **透過替代的緩解措施解決** -改進動作已經由協力廠商應用程式或軟體或內部工具所解決。 您將會看到必要的動作點，所以您的分數會更好反映整體的安全性狀況。 如果協力廠商或內部工具不再涵蓋該控制項，您可以選擇其他狀態。 請記住，如果改進動作標示為這兩種狀態，Microsoft 將無法深入瞭解實施的完整性。

#### <a name="threat--vulnerability-management-improvement-actions"></a>威脅 & 弱點管理的改進動作

若要在 "Device" 類別中改進動作，您將無法選擇狀態。 相反地，您會被導向相關 [威脅 & 弱點管理 (TVM) 安全性建議](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) 的 [Microsoft Defender security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) 採取行動。 您選擇的例外狀況和您所撰寫的對齊方式，都是該入口網站特有的。 它不會出現在 Microsoft Secure 得分入口網站中。

#### <a name="completed-improvement-actions"></a>已完成的改進動作

在完成改進動作的所有可能點之後，[改進動作] 的狀態為「已完成」。 已完成的改進動作會透過 Microsoft data 加以確認，而且您將無法變更狀態。

### <a name="assess-information-and-review-user-impact"></a>評估資訊並複查使用者影響

一 **眼** 就會告訴您，您的類別、可以防禦的攻擊，以及產品。

[ **使用者影響** ] 顯示使用者在已頒佈改進動作時的體驗，以及 **受影響的使用者** 會顯示誰會體驗。

### <a name="implement-the-improvement-action"></a>實施改進動作

「 **實施** 」區段顯示所有必要條件、逐步後續步驟，以完成 [改進] 動作、[改進動作] 的目前實施狀態，以及任何 [深入瞭解] 連結。

必要條件包括需要取得的任何授權，或是在解決改進動作之前必須完成的動作。 請確定您的授權有足夠的座位，可完成 [改進] 動作，並將這些授權套用至必要的使用者。  

## <a name="we-want-to-hear-from-you"></a>我們想要聽到您的來信

如果您有任何問題，請在 [安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 社區中發佈以告知我們。 我們正在監視社區，並會提供協助。

## <a name="related-resources"></a>相關資源

- [Microsoft 安全評分概述](microsoft-secure-score.md)
- [追蹤您的 Microsoft 安全分數記錄並符合目標](microsoft-secure-score-history-metrics-trends.md)
- [即將推出的功能](microsoft-secure-score-whats-coming.md)
- [新功能](microsoft-secure-score-whats-new.md)