---
title: 電子郵件訊息的安全提示
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: 深入瞭解如何透過將安全提示新增至電子郵件，EOP 和 Office 365 保護您的垃圾郵件、網路釣魚和惡意程式碼防護。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 659a83c73b4fef9097aa317332c9951d53b09a33
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994982"
---
# <a name="safety-tips-in-email-messages"></a>電子郵件訊息的安全提示

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) 和 Microsoft 365 保護您的垃圾郵件、網路釣魚和惡意程式碼防護。 如今，有些攻擊非常精心設計，看起來很合理。 將郵件傳送至 [垃圾郵件] 資料夾並不一定足夠。 現在，當您在 web 或任何電子郵件用戶端的 Outlook 或 Outlook 中檢查電子郵件時，EOP 會自動檢查寄件者，並將安全提示新增至電子郵件的頂端。

Outlook 中的安全性秘訣不會取決於您所使用 Outlook 的版本，因為安全提示遭到破譯並直接插入郵件內文。 這表示安全提示會顯示在您所使用的電子郵件客戶程式中。 它會在電子郵件篩選層級進行，而不是在郵件客戶層級轉譯，因此，它不只會顯示在任何版本的 Outlook 中，也會顯示在任何電子郵件客戶程式中。

安全提示--色彩編碼的郵件會警告您有關可能有害的郵件。 您的收件匣中的大部分郵件都不會有安全提示。 您只會在 EOP 和 Microsoft 365 包含您所需的資訊，以協助防範垃圾郵件、網路釣魚和惡意程式碼攻擊時看到。 如果在 [收件匣] 中顯示安全性秘訣，您可以使用下列範例深入瞭解每種類型的安全提示。

- 可疑郵件 (紅色安全提示) 。

    ![顯示紅色安全提示的螢幕擷取畫面。](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    電子郵件中的紅色安全提示表示您收到的訊息包含可疑專案，例如網路釣魚詐騙。 建議您從收件匣刪除這類電子郵件，而不需要開啟它。

- 安全郵件 (綠安全提示) 。

    ![顯示綠色安全提示的螢幕擷取畫面。](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    除了不安全的郵件之外，我們也會告訴您，來自我們信任的寄件者與綠色安全提示的有效郵件。 電子郵件中的綠色安全提示表示我們已檢查郵件的寄件者，並驗證它是安全的。 Microsoft 會維護此信任的寄件者清單，其中包含金融組織及經常哄騙或模仿的人。

## <a name="working-with-safety-tips"></a>使用安全提示

系統管理員可以在反垃圾郵件原則中開啟或關閉安全性秘訣。 如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

如果您不同意 EOP 對郵件進行分類的方式 (也就是說，郵件不是垃圾郵件，或是已標示為垃圾郵件) ，您可以將郵件提交給 Microsoft 進行分析，以協助改善您的體驗。 如需相關指示，請參閱 [將訊息和檔案報告給 Microsoft](report-junk-email-messages-to-microsoft.md)。 您也可以按一下安全提示中的 [意見反應] 連結，直接向 Microsoft 提交批註，以協助我們進行改進。
