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
description: 深入瞭解如何將安全性秘訣加入電子郵件，以瞭解 EOP 和 Office 365 如何保護您免受垃圾郵件、網路釣魚和惡意程式碼的防禦。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1820cab63abbbac09aa60a9c1684f3672882451
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059800"
---
# <a name="safety-tips-in-email-messages"></a>電子郵件訊息的安全提示

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) 和 Microsoft 365 保護您的垃圾郵件、網路釣魚和惡意程式碼防護。 如今，有些攻擊非常精心設計，看起來很合理。 將郵件傳送至 [垃圾郵件] 資料夾並不一定足夠。 現在，當您在 Outlook 或 Outlook 網頁版或任何電子郵件客戶程式中檢查您的電子郵件時，EOP 會自動檢查寄件者，並將安全性秘訣加入至電子郵件的最上層。

Outlook 中的安全性秘訣不一定取決於您所使用的 Outlook 版本，因為安全性秘訣會被破譯，並直接插入郵件內文。 這表示安全提示會顯示在任何您使用的電子郵件客戶程式中。 它會在電子郵件篩選層級進行，而不是在郵件客戶層級轉譯，所以不只會顯示在任何版本的 Outlook 中，也會顯示在任何電子郵件客戶程式中。

安全提示--彩色編碼的郵件--會警告您可能有害的郵件。 您的收件匣中的大部分郵件都不會有安全性提示。 只有在 EOP 和 Microsoft 365 具有您所需的資訊，以協助防範垃圾郵件、網路釣魚和惡意程式碼攻擊時，您才會看到這些資訊。 如果在 [收件匣] 中顯示安全性秘訣，您可以使用下列範例深入瞭解每種安全提示類型。

- 可疑的郵件 (紅色的安全性提示) 。

    ![顯示紅色安全提示的螢幕擷取畫面。](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    電子郵件中的紅色安全性秘訣表示您收到的訊息包含可疑專案（例如網路釣魚詐騙）。 建議您從收件匣刪除這類電子郵件，而不需要開啟它。

- 安全郵件 (綠色的安全性提示) 。

    ![顯示綠色安全提示的螢幕擷取畫面。](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    除了不安全的郵件之外，我們也會告訴您來自我們信任的寄件者的有效郵件，並以綠色的安全性提示。 電子郵件中的綠色安全提示是指我們會檢查郵件的寄件者，並驗證它是安全的。 Microsoft 會維護此信任的寄件者清單，其中包含金融組織及經常哄騙或模仿的人。

## <a name="working-with-safety-tips"></a>使用安全提示

即使並非每封郵件都會收到，安全性秘訣還是會針對網頁上的 Outlook 一直啟用。 系統管理員可以關閉其他電子郵件客戶程式（例如 Outlook）的安全性秘訣。 如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

如果您不同意 EOP 對郵件進行分類的方式 (也就是說，郵件不是垃圾郵件，或是已標示為垃圾郵件) ，您可以將郵件提交給 Microsoft 進行分析，以協助改善您的體驗。 如需相關指示，請參閱 [將訊息和檔案報告給 Microsoft](report-junk-email-messages-to-microsoft.md)。 您也可以按一下安全提示中的 [意見反應] 連結，直接向 Microsoft 提交批註，以協助我們進行改進。
