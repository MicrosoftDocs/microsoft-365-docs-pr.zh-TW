---
title: 建立攻擊模擬訓練的負載
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
description: 系統管理員可以瞭解如何在 Microsoft Defender 中建立用於 Office 365 的自訂負載，以進行攻擊模擬訓練。
ms.technology: mdo
ms.openlocfilehash: ac7963b71c466e8dfdc513a2563776cd4e10af95
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878757"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>建立攻擊模擬訓練的自訂承載

**適用** 于 [Office 365 方案2的 Microsoft Defender](defender-for-office-365.md)

Microsoft 為各種社交工程技術提供強大的負載目錄，以與您的攻擊模擬訓練進行搭配。 不過，您可能會想要建立更適合貴組織的自訂負載。 本文說明如何在 Microsoft Defender 的 Office 365 中建立負載，以進行攻擊模擬訓練。

您可以按一下 [[專用 **負載**]](https://security.microsoft.com/attacksimulator?viewid=payload)索引標籤或 [[類比建立嚮導]](attack-simulation-training.md#selecting-a-payload)中的 [**建立負載**]，以建立負載。

嚮導的第一個步驟會選取一種負載類型。 **目前只有電子郵件可供使用**。

接下來，選取相關聯的技術。 在 [選擇社交工程技術](attack-simulation-training.md#selecting-a-social-engineering-technique)時，請參閱技巧的詳細資料。

在下一個步驟中，為您的負載命名。 您也可以選擇提供描述。

## <a name="configure-payload"></a>設定有效載荷

現在就開始建立您的負載。 在 [ **寄件者詳細資料** ] 區段中輸入寄件者的名稱、電子郵件地址及電子郵件的主旨。 從提供的清單中挑選網路釣魚 URL。 稍後會將此 URL 嵌入郵件的本文中。

> [!TIP]
> 您可以為您的載荷寄件者選擇內部電子郵件，這會使該負載顯示為來自公司的其他員工。 這會增加對有效負載的敏感程度，並協助員工對內部威脅的風險進行教育。

可以使用 rtf 文字編輯器來建立您的負載。 您也可以匯入預先建立的電子郵件。 當您建立電子郵件的本文時，請利用 **動態標記** ，將電子郵件自訂至您的目標。 按一下 [ **仿冒連結** ]，將先前所選的網路釣魚 URL 新增至郵件的本文中。

![為 Office 365 的 Microsoft Defender 的負載建立中突出顯示網路釣魚連結和動態標記](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> 若要節省時間，請切換此選項以 **取代電子郵件中的所有連結與網路釣魚連結**。

當您想要建立負載後，請按 **[下一步]**。

## <a name="adding-indicators"></a>新增指示器

指標會協助員工透過攻擊模擬，瞭解他們可以在未來的攻擊中尋找的線索。 若要開始，請按一下 [ **新增指示器**]。

從下拉式清單中選取您想要使用的指示器。 這個清單是策劃，包含出現在網路釣魚電子郵件訊息中的最常見的線索。 選取之後，請確定指示器位置已設定為 **從電子郵件的內** 文，然後按一下 [ **選取文字**]。 反白顯示此指標會出現的部分負載，然後按一下 [ **選取**]。

![郵件內文中的突出顯示文字，以加入攻擊模擬訓練中的指示器](../../media/attack-sim-preview-select-text.png)

新增自訂描述以描述指示器，然後按一下指標預覽框架內，以查看指示器預覽。 完成後，按一下 [ **新增**]。 重複這些步驟，直到您已在您的負載中涵蓋所有指示器為止。

## <a name="review-payload"></a>檢查負載

您已經完成您的負載的建立。 現在請查看詳細資料，並查看您的負載預覽。 預覽會包含您已建立的所有指示器。 您可以從這個步驟編輯每個部分的負載。 完成後，您就可以 **提交** 您的負載。

> [!IMPORTANT]
> 您已建立的負載會將 **承租人** 當做其來源。 選取 [有效負載] 時，請確定您不會篩選出 **租** 使用者。

## <a name="related-links"></a>相關連結

[開始使用攻擊模擬訓練](attack-simulation-training-get-started.md)

[建立網路釣魚攻擊模擬](attack-simulation-training.md)

[透過攻擊模擬訓練取得深入解析](attack-simulation-training-insights.md)
