---
title: 使用適用于 Office 365 的 Microsoft Defender 模擬網路釣魚攻擊
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 系統管理員可以瞭解如何在 Microsoft Defender for Office 365 中模擬網路釣魚攻擊，並訓練其使用者使用網路釣魚防護。
ms.technology: mdo
ms.openlocfilehash: f22fe8633d8ffa8856f851369739a0f12364342b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929199"
---
# <a name="simulate-a-phishing-attack"></a>模擬網路釣魚攻擊

Microsoft Defender for Office 365 中的攻擊攻擊訓練可讓您在組織中執行惡意網路攻擊攻擊，以測試您的安全性原則與作法，以及訓練員工提升認知度及降低他們對於攻擊的敏感度。 本文將引導您完成使用模擬攻擊訓練建立模擬網路釣魚攻擊。

有關攻擊模擬訓練的入門資訊，請參閱開始使用攻擊 [模擬訓練](attack-simulation-training-get-started.md)。

若要啟動模擬網路釣魚攻擊，請開啟 Microsoft [365](https://security.microsoft.com/)資訊安全中心、前往電子郵件&共同攻擊模擬訓練，然後切換到Microsoft 365 資訊安全中心的模擬訓練，然後切換到Microsoft 365 資訊安全中心。  \>  [](https://security.microsoft.com/attacksimulator?viewid=simulations)

在 **模擬下**，選取 **+啟動模擬**。

![在 Microsoft 365 資訊安全中心中啟動模擬按鈕](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> 建立模擬時，您隨時都可以儲存並關閉模擬，稍後再繼續進行模擬。

## <a name="selecting-a-social-engineering-technique"></a>選取社交工程技術

從 4 種不同的技巧中選取，由 [MITRE ATT&CK®所挑選](https://attack.mitre.org/techniques/enterprise/)。 不同的裝載適用于不同的技術：

- **認證認證** 認證會嘗試將使用者帶至具有輸入框的已知網站以收集認證，以提交使用者名稱和密碼。
- **惡意程式碼** 附件會將惡意附件新增到郵件中。 當使用者開啟附件時，會執行任意程式碼，協助攻擊者入侵目標裝置。
- **附件中的連結** 是一種認證混合式。 攻擊者在電子郵件附件中插入 URL。 附件中的 URL 採用與認證認證相同的技術。
- **惡意程式碼** 連結會從已知的檔案共用服務上託管的檔案執行一些任意程式碼。 此訊息會包含此惡意檔案的連結。 開啟檔案，協助攻擊者入侵目標裝置。

> [!TIP]
> 按一下每項 **技巧描述** 內的 View 詳細資料，將會顯示進一步的資訊，以及該技巧的模擬步驟。
>
> ![Microsoft 365 資訊安全中心在攻擊模擬訓練內認證收集的模擬步驟](../../media/attack-sim-preview-sim-steps.png)

選取技巧並按一下 [下一步之後，為模擬命名和描述可選擇性地提供一個名稱。

## <a name="selecting-a-payload"></a>選取負載

接下來，您必須從現有的負載目錄選取一個負載。

負載具有可協助您選擇的資料點：

- **按一下比率** 會計算按一下此負載人數。
- **根據針對** Office 365 客戶之 Microsoft Defender 所受到負載的歷史資料，預測受到此負載入侵之人員百分比。
- **啟動的** 模擬會計算此負載在其他模擬中使用的次數。
- **可透過** 篩選使用複雜度，是根據由線索以受攻擊之目標之負載中的標記數目計算。 標記數多一點會導致複雜度降低。
- **可** 透過篩選使用的來源會指出該負載是否建立于您的租使用者上，或屬於 Microsoft 現有負載目錄的一 (全域) 。

![Microsoft 365 資訊安全中心中受到攻擊的模擬訓練中選取的負載](../../media/attack-sim-preview-select-payload.png)

從清單中選取一個負載，以查看該負載的預覽，以及該負載的其他相關資訊。

如果您想要建立自己的裝載，請閱讀建立攻擊模擬訓練的 [裝載](attack-simulation-training-payloads.md)。

## <a name="audience-targeting"></a>對象目標

現在該選取此模擬物件。 您可以選擇將 **貴組織的所有使用者** 納入，或 **只包含特定使用者和群組**。

當您選擇只 **包含特定使用者和群組時** ，您可以：

- **新增使用者**，這可讓您針對租使用者運用搜尋功能，以及進一步搜尋和篩選功能，例如鎖定過去 3 個月內未受到模擬鎖定的使用者。
  ![在 Microsoft 365 資訊安全中心進行攻擊模擬訓練中的使用者篩選](../../media/attack-sim-preview-user-targeting.png)
- **從 CSV 進行** 匯出可讓您針對此模擬，匯出預先定義的使用者集。

## <a name="assigning-training"></a>指派訓練

建議您為每個模擬指派訓練，因為參與訓練的員工較不容易受到類似的攻擊。

您可以選擇要指派訓練，或自己選取訓練課程和單元。

選取 **訓練到期日，** 以確保員工及時完成訓練。

> [!NOTE]
> 如果您選擇自己選取課程和模組，您仍然可以看到建議的內容，以及所有可用的課程和模組。
>
> ![在 Microsoft 365 資訊安全中心中新增攻擊模擬訓練內的建議訓練](../../media/attack-sim-preview-add-training.png)

在接下來的步驟中，如果您選擇自己選取，您將必須新增訓練，並自訂您的訓練登陸頁面。 您將可以預覽訓練登陸頁面，以及變更其頁標題和本體。

## <a name="launch-details-and-review"></a>啟動詳細資料並評論

現在一切已全部完成，您可以立即啟動此模擬，或將模擬排程為稍後的日期。 您也需要選擇何時結束此模擬。 我們將停止在過去選取的時間，拍攝此模擬的互動。

**讓地區知道時區傳遞** ，以在員工上班時間根據地區的模擬攻擊訊息。

完成後，請按一下 [下一步 **，然後查看** 模擬的詳細資訊。 按一下任 **一** 部分的 [編輯工具，即可返回並變更任何需要變更的細節。 完成後，按一下 [ **提交**。
