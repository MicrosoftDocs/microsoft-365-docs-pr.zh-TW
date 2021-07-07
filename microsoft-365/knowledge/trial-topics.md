---
title: 執行 Microsoft Viva 主題的試用版
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: ''
search.appverid: ''
localization_priority: Normal
description: 瞭解如何為您的組織中的 Microsoft Viva 主題規劃及執行試用試驗計畫。
ms.openlocfilehash: 128e82e7664a76baa55d37e983319c9f344624fd
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327088"
---
# <a name="run-a-trial-of-microsoft-viva-topics"></a>執行 Microsoft Viva 主題的試用版

本文說明如何設定和執行試用試驗計畫，以將 Viva 主題部署至您的組織。 本文也建議試用版的最佳作法。

## <a name="sign-up-for-a-trial"></a>註冊試用版

您可以從下列其中一個來源公開試用試用版。 這些試驗提供25天的使用者 Viva 主題存取權。

- [Viva 主題產品頁面](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)

- [Microsoft 365 系統管理中心](https://admin.microsoft.com)
    1.  登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。
    2.  移至 **帳單**  >  **購買服務**。
    3.  向下捲動至 **[附加元件]** 區段。
    4.  在 **主題經驗** 圖上，選取 [ **詳細資料**]。
    5.  選取 **[取得免費試用版]**。
    6.  遵循餘下的嚮導步驟確認試用版。

您必須是 Microsoft 365 全域管理員或計費系統管理員，才能啟用試用版。

> [!NOTE]
> 您只能為每個 Microsoft 365 租使用者新增一次 Public 實驗。

### <a name="who-should-be-involved-in-a-trial"></a>試用版中應包括神秘

|角色  |活動  |
|---------|---------|
|Microsoft 365 全域管理員或計費系統管理員  |   啟動試用和指派授權      |
|Microsoft 365 全域系統管理員或 SharePoint 系統管理員    |       設定 Viva 主題及建立主題中心  |
|商務使用者     |   執行知識管理員、主題參與者及主題使用者角色      |

### <a name="before-you-activate-a-trial"></a>啟動試用之前

規劃是 Viva 主題有效試用的必要條件。 試用期是有限的，且必須包含主題探索及流覽主題的品質、管理和使用者體驗。

#### <a name="discovery"></a>發現

有兩個高級策略選項可讓您在試用期間設定主題探索：

- 為所有或大部分的 SharePoint 線上內容編制索引。
   - 大型租使用者最多可能需要兩周才能進行完整的索引。 雖然在此期間內會以增量方式產生主題，但完整編制索引可能會消耗最多一半的試用期。
   - 針對具有大量資料的承租人，此選項會產生非常大量的主題，甚至是數十千。

- 識別您的 SharePoint 網站的子集以編制索引。

這些策略的選擇是下列兩個因素的平衡：

- 具有足夠的資料來產生有意義的主題。 Viva 主題中的 AI 已調整為可用於大型資料集，理想的是檔數量超過10000的檔。
- 在試用期間內不產生這麼多主題，以在可用時段內進行評估是非常驚人的。

對大多數的組織而言，第二個策略會產生最佳結果。

> [!NOTE]
> 由於 AI 要求的檔數目，建議您在實際執行租使用者上執行 Viva 主題試驗。 在此期間，不會影響承租人的效能。 只有具有試用版授權的使用者才能存取 Viva 主題的使用者經驗。

#### <a name="roles"></a>角色

在試用期間內，必須使用三個角色，如下表所述。

|角色  |活動  |
|---------|---------|
|知識管理員     |   控制主題的週期階段。確認和移除主題;擔任主題投稿人的社區管理員      |
|主題參與者    |      內容主題專家，誰可以：<br> 查看主題，以評估 AI 定義內容的品質<br>Curate 已探索的主題與其他內容<br>建立其他無法透過 AI 探索的主題   |
|主題消費者    |     透過頁面要聞和搜尋使用主題<br>針對所呈現的主題值提供意見反應    |

#### <a name="expected-topics"></a>預期主題

您可以使用此方法來記錄您期望透過 AI 產生的主題，即使這只是以假設為基礎也是如此。 當您為可輕鬆識別 sme 的 SharePoint 網站的子集編制索引時，這個工作很容易完成。

有記錄的清單可協助您：

- 請複查 AI 產生的主題清單，其可能會大於預期的數目。
- 瞭解您可能需要手動建立或為 curation 的優先順序的主題。

在成功部署或 Viva 主題的實驗中，一定要混合使用 AI 定義及人工建立的主題。

## <a name="activate-a-trial"></a>啟動試用版

當您啟動試用版時，您必須：

- 將授權指派給相關的使用者。
- 執行 [其他](set-up-topic-experiences.md) Viva 主題的設定。

啟用試用時，主題探索程式會開始。

## <a name="during-a-trial"></a>在試用期間

試用期應該用來評估下列 Viva 主題的元件：

- AI-建議的主題和主題內容
- 在新式 SharePoint 頁面及 Microsoft 搜尋中，使用者體驗、呈現主題卡片

請考慮下列因素：

- 為了讓 Viva 主題能夠提供最大值，主題中的內容必須是 AI 定義的內容和策劃內容的組合。
- 所有使用者經驗都是「許可權已被修整」 (包括「 **管理主題** 」頁面上的知識管理員的視圖) 。 使用者只會看到一個主題，是否有許可權可以查看用來產生該主題的一些資源。 這表示不同的使用者可能會在相同的主題頁面上看到不同的內容。
- 使用者可能會在 [ **管理主題** ] 頁面看到多個具有相同名稱的主題。 這些主題不一定重複，但可能是因為單一字詞會在資料的多個內容中使用，例如兩個不同專案所使用的專案程式碼名稱。

## <a name="after-a-trial"></a>試用後

根據試用的結果，您可以決定是否要繼續使用 Viva 主題的實際執行使用。

### <a name="proceed-to-production-use"></a>繼續使用實際執行環境

為了確保服務的連續性，您必須購買必要數目的授權，並將這些授權指派給使用者。 試用期結束後沒有完整授權的試用使用者將無法存取任何 Viva 主題經驗。

### <a name="dont-proceed-to-production-use"></a>請勿繼續實際執行使用

如果您未在試用後購買授權：

- 主題探索將停止。
- 使用者將不會再看到主題要聞或卡片。
- 不會刪除主題中心，但建議的主題和管理主題無法使用。
- 任何 AI 定義的主題都會遺失。
- 主題參與者已編輯的主題將保留在主題中心頁面庫中。 只有手動提供的內容會保留在這些頁面上，而不是任何 AI 建議的內容。

## <a name="see-also"></a>請參閱

[開始推動採用 Microsoft Viva 主題](topics-adoption-getstarted.md)

