---
title: 為攻擊模擬訓練建立裝載
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 系統管理員可以瞭解如何在 Microsoft Defender for Office 365 中建立攻擊模擬訓練的自訂裝載。
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929187"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>建立攻擊模擬訓練的自訂承載

Microsoft 針對各種社交工程技術提供強大的負載目錄，以搭配您的攻擊模擬訓練。 不過，您可能會想要建立更適用于貴組織的自訂裝載。 本文將說明如何在 Microsoft Defender for Office 365 中建立攻擊模擬訓練的裝載。

您可以按一下專用之攜帶點或模擬建立精靈中的建立要載人，以建立[負載](attack-simulation-training.md#selecting-a-payload)。 [  ](https://security.microsoft.com/attacksimulator?viewid=payload)

精靈的第一個步驟會提供您選取一種負載類型。 **目前僅提供電子郵件**。

接下來，選取相關的技巧。 請參閱選取社交工程 [技巧以瞭解有關技巧的詳細資訊](attack-simulation-training.md#selecting-a-social-engineering-technique)。

在下一個步驟中，為任務命名。 或者，您可以為它提供描述。

## <a name="configure-payload"></a>設定負載

現在該建立您的負荷了。 在寄件者詳細資料區段輸入寄件者的名稱、電子郵件地址和 **電子郵件的主體** 。 從提供的清單中挑選網路釣魚 URL。 此 URL 稍後會內嵌在郵件本文中。

> [!TIP]
> 您可以選擇要裝載之寄件者的內部電子郵件，讓這個裝載顯示為來自公司另一個員工。 這將提高對於負載的敏感度，並有助於教育員工內部威脅的風險。

豐富的文字編輯器可用於建立您的負載。 您也可以事先匯出已建立的電子郵件。 當您建立電子郵件內內容時，請利用動態標記，將電子郵件個人化至您的目標。 按一下 **網路釣魚連結** ，將先前選取的網路釣魚 URL 新增到郵件內文。

![Microsoft Defender for Office 365 在建立負載時反顯示網路釣魚連結和動態標記](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> 若要節省時間，請開啟選項，以網路釣魚連結取代電子郵件訊息 **中所有的連結**。

在您建立完喜歡的負荷後，按一下 [下一 **步**。

## <a name="adding-indicators"></a>新增標記

標記可協助員工在受到攻擊時瞭解可以在未來攻擊中尋找的線索。 若要開始，請按一下 [ **新增標記**。

從下拉式清單中選取您目前所要使用標記。 此清單已過策展，包含網路釣魚電子郵件訊息中最常見的線索。 選取後，請確定標記位置設定為 [從電子郵件本文中選取文字，然後按一下 **選取文字**。 將這個標記出現時，將您攜帶的一部分強調顯示，然後按一下 [ **選取**。

![郵件內文中以強調顯示的文字，以在攻擊模擬訓練中新增標記](../../media/attack-sim-preview-select-text.png)

新增自訂描述來描述標記，然後按一下標記預覽框架，即可查看標記的預覽。 完成後，按一下 [ **新增**。 重複這些步驟，直到涵蓋您負載中所有的標記。

## <a name="review-payload"></a>重閱負載

您已完成建立您的負荷。 現在該是檢查詳細資料，並預覽您負載的時間了。 預覽會包含您建立的所有標記。 您可以編輯此步驟中的每個負載部分。 一旦獲得滿足，您可以 **提交** 您的裝載。

> [!IMPORTANT]
> 您建立之裝載會以 **租使用者** 做為來源。 選取負載時，請確認您沒有篩選出租 **使用者**。

## <a name="related-links"></a>相關連結

[開始使用攻擊模擬訓練](attack-simulation-training-get-started.md)

[建立網路釣魚攻擊模擬](attack-simulation-training.md)

[透過攻擊模擬訓練取得深入解析](attack-simulation-training-insights.md)
