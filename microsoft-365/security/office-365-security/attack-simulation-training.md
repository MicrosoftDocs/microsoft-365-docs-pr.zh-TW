---
title: 使用 Microsoft Defender 來模擬網路的網路釣魚攻擊
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 瞭解如何模擬網路釣魚攻擊，並使用 Microsoft Defender for Office 365 中的攻擊模擬訓練，訓練您的使用者網路釣魚防護。
ms.openlocfilehash: 8f5f457f60c81fe961282f33bb8c37f4d9e27aab
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616101"
---
# <a name="simulate-a-phishing-attack"></a>模擬網路釣魚攻擊

透過 Microsoft Defender for Office 365 的攻擊模擬器訓練可讓您在組織上執行良性網路攻擊模擬，以測試您的安全性原則和作法，以及訓練組織的員工以提升其知名度，並減少對攻擊的敏感程度。 下列步驟會引導您使用攻擊模擬器訓練來模擬網路釣魚攻擊。

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

若要啟動模擬網路釣魚攻擊，請流覽至 [Microsoft 365 的安全性中心](https://security.microsoft.com/)。 在 [ **電子郵件 &** 共同作業] 底下，按一下 **攻擊模擬器** 上的 [ [**模擬**](https://security.microsoft.com/attacksimulator?viewid=simulations) ]，然後切換至 [

在 [ **類比** ] 下，選取 [ **啟動類比**]。

![在 Microsoft 365 的安全性中心啟動模擬按鈕](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> 在類比建立過程中的任何時刻，您都可以儲存並關閉，繼續進行類比。

## <a name="selecting-a-social-engineering-technique"></a>選取社交工程技術

從4個不同的技術中，策劃 [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/)。 不同的負載可用於不同的技術。

- **認證搜集** 會嘗試透過使用輸入方塊送出使用者名稱和密碼，以取得員工的身分識別的網站來收集認證。
- **惡意程式碼附件** 會將惡意附件加入郵件。 開啟時，這個附件會執行一些可協助攻擊者損害目標裝置的任意程式碼。
- **附件中的連結** 是一種混合式認證的類型。 攻擊者會將 URL 插入電子郵件附件。 附件內的 URL 與認證探索所遵循的技術相同。
- **連結至惡意** 代碼會從眾所周知的檔案共用網站上的檔案執行一些任意程式碼。 此惡意檔案的連結會新增至傳送至目標的郵件，然後按一下此連結會執行該檔案，並協助攻擊者損害目標裝置。

> [!TIP]
> 按一下每個技術說明中的 [ **查看詳細資料** ]，可顯示技術的進一步資訊，以及該技巧的類比步驟。
>
> ![Microsoft 365 安全中心內的認證模擬訓練中認證的類比步驟](../../media/attack-sim-preview-sim-steps.png)

當您選取了該方法並按一下 **[下一步]** ，便會提供類比名稱和選擇性的描述。

## <a name="selecting-a-payload"></a>選取負載

接下來，您必須從預先存在的負載目錄中選取負載。

負載具有許多可協助您選擇的資料點：

- **按一下 [流量** 計數] 按此負載的人數。
- **預測的折衷率** 會根據此負載在 Microsoft Defender for Office 365 客戶上的歷史資料，預測此負載會危及之人員的百分比。
- **模擬已啟動** 計算此負載在其他類比中使用的次數。
- 可透過 **篩選器** 使用的 **複雜性**，是根據在其指示其為攻擊之目標的負載內的指標數目來計算。 更多指示器會導致較低的複雜性。
- **來源**（透過 **篩選器** 提供）會指出是否已在您的租使用者上建立負載，或是 Microsoft 預先存在的負載目錄 (全域) 的一部分。

![Microsoft 365 security center 中的攻擊模擬訓練中所選的負載](../../media/attack-sim-preview-select-payload.png)

從清單中選取一個負載，以查看具有其相關詳細資訊的負載預覽。

如果您想要建立自己的負載，請參閱 [建立攻擊模擬訓練的負載](attack-simulation-training-payloads.md)。

## <a name="audience-targeting"></a>對象目標

現在請選擇此模擬的物件。 您可以選擇 **包含組織中的所有使用者** ，或 **只包含特定的使用者和群組**。

當您選擇 **只包含特定的使用者和群組** 時，您可以執行下列其中一項：

- **新增使用者**，可讓您利用租使用者的搜尋功能，以及高級搜尋和篩選功能，例如以過去3個月內模擬的目標使用者為目標。
  ![Microsoft 365 安全中心的攻擊模擬訓練中的使用者篩選](../../media/attack-sim-preview-user-targeting.png)
- **從 CSV 匯入** 可讓您為此模擬匯入一組預先定義的使用者。

## <a name="assigning-training"></a>指派訓練

建議您指派每個類比的訓練，因為參加訓練的員工會不易遭受類似的攻擊。

您可以選擇將訓練指派給您或自行選擇訓練課程和模組。

選取 [ **訓練到期日** ]，確定員工及時完成訓練。

> [!NOTE]
> 如果您選擇自行選取課程和模組，您仍然可以查看建議的內容，以及所有可用的課程和模組。
>
> ![在 Microsoft 365 安全中心的攻擊模擬訓練中新增建議訓練](../../media/attack-sim-preview-add-training.png)

在後續步驟中，如果您選擇自行自行選擇訓練，您將需要 **新增** 訓練，並自訂訓練登陸頁面。 您可以預覽 [訓練] 登陸頁面，也可以變更其頁首和本文。

## <a name="launch-details-and-review"></a>發佈詳細資料和評論

現在已設定所有內容，您可以立即啟動這項類比，也可以在稍後的日期排程。 您也必須選擇何時結束此模擬。 在選取的時間之後，我們將停止與此模擬進行的捕捉互動。

**啟用地區感知時區傳遞** ，以根據地區的工作時間，將模擬的攻擊訊息傳遞給您的員工。

完成後，請按一下 **[下一步]** 並查看類比的詳細資料。 在任何要回復的元件上按一下 [ **編輯** ]，然後變更任何需要變更的詳細資料。 完成後，按一下 [ **提交**]。
