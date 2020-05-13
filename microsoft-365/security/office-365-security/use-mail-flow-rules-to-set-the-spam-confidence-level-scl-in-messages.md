---
title: 使用郵件流程規則到郵件中的 SCL
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 瞭解如何建立郵件流程規則（傳輸規則）來識別郵件，以及在 Exchange Online Protection 中設定郵件的垃圾郵件信賴等級（SCL）。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f9af154a9f71992597e111147b792cd5286e2ad3
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208558"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>使用郵件流程規則來設定 EOP 中郵件的垃圾郵件信賴等級（SCL）

在未使用 Exchange online 信箱的 Exchange Online 或獨立 Exchange Online Protection （EOP）組織中使用信箱的 Microsoft 365 組織中，EOP 會使用反垃圾郵件原則（也稱為垃圾郵件篩選原則或內容篩選原則）來掃描輸入郵件中的垃圾郵件。 如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

如果您想要將特定郵件標記為垃圾郵件，然後再透過垃圾郵件篩選進行掃描，或將郵件標示為略過垃圾郵件篩選，您可以建立郵件流程規則（也稱為傳輸規則）來識別郵件，並設定垃圾郵件信賴等級（SCL）。 如需有關 SCL 的詳細資訊，請參閱[EOP 中的垃圾郵件信賴等級（SCL）](spam-confidence-levels.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您必須先在 Exchange Online 中指派許可權，才能執行這些程式。 具體而言，您必須被指派**傳輸規則**角色，預設會指派給**組織管理**、**規範管理**及**記錄管理**角色。 如需詳細資訊，請參閱[管理 Exchange Online 中的角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。

- 若要在 Exchange Online 中開啟 EAC，請參閱 exchange [online 中的 exchange admin center](https://docs.microsoft.com/Exchange/exchange-admin-center)。

- 如需 Exchange Online 中郵件流程規則的相關資訊，請參閱[郵件流程規則（傳輸規則） Exchange online 中的郵件流程規則（傳輸規則）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>使用 EAC 來建立郵件流程規則，以設定郵件的 SCL

1. 在 EAC 中，移至 [郵件流程]**** \> [規則]****。

2. 按一下 [**新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) ，然後選取 [**建立新的規則**]。

3. 在開啟的 [**新增規則**] 頁面中，設定下列設定：

   - **名稱**：輸入規則的唯一描述性名稱。

   - 按一下 [**更多選項**]。

   - 在下列情況中套用**此規則**：選取一或多個條件來識別郵件。 如需詳細資訊，請參閱[在 Exchange Online 中的郵件流程規則條件和例外狀況（謂語）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。

   - **請執行下列**動作：選取 [**修改郵件屬性**] \> **設定垃圾郵件信賴等級（SCL）**。 在出現的 [**指定 SCL** ] 對話方塊中，設定下列其中一個值：

   - **略過垃圾郵件篩選**：這會將 SCL 設為-1，這表示郵件會略過垃圾郵件篩選。

     > [!CAUTION]
     > 請務必小心允許郵件略過垃圾郵件篩選。 攻擊者可以利用此弱點，將網路釣魚和其他惡意郵件傳送至您的組織。 郵件流程規則需要的不僅僅是寄件者的電子郵件地址或網域。 如需詳細資訊，請參閱[在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。

   - **0 至 4**：透過垃圾郵件篩選傳送郵件以進行其他處理。

   - **5 或 6**：郵件被標示為**垃圾**郵件。 您為反垃圾郵件原則中的**垃圾**郵件篩選 verdicts 設定的動作會套用至郵件（預設值為 [**將郵件移至垃圾郵件資料夾**]）。

   - **7 至 9**：郵件標示為**高信賴的垃圾郵件**。 您為反垃圾郵件原則中已設定**高信賴度垃圾郵件**篩選 verdicts 的動作會套用至郵件（預設值為 [**將郵件移至垃圾郵件資料夾**]）。

4. 指定規則所需的任何其他屬性。 完成後，按一下 [儲存]****。

## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要驗證此程式是否正常運作，請將電子郵件訊息傳送給組織內部的人員，並確認對郵件執行的動作如期。 例如，如果您**將垃圾郵件信賴等級（SCL）設定**為**略過垃圾郵件篩選**，則郵件應該會傳送至指定收件者的收件匣。 不過，如果您**將垃圾郵件信賴等級（SCL）設定**為**9**，且適用的反垃圾郵件原則的**高可信度垃圾郵件**動作是將郵件移至 [垃圾郵件] 資料夾，則郵件應該會傳送至指定收件者的 [垃圾郵件] 資料夾。
