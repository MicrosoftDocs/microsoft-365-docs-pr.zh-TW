---
title: Office 365 預設安全性
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: '深入瞭解 Exchange Online Protection (EOP 中的 [安全的預設值] 設定) '
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c737647202e82af0fc217c0eadb3e2573d13a9b1
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177642"
---
# <a name="secure-by-default-in-office-365"></a>Office 365 預設安全性

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

「預設使用安全」是一種術語，用來定義盡可能最安全的預設設定。

不過，安全性需要與生產力進行平衡。 這可能包括平衡：

- **可用性**：設定不應該以使用者生產力的方式取得。
- **風險**：安全性可能會封鎖重要的活動。
- **舊的設定**：有些舊版產品及功能的設定可能出於商務原因而必須維護，即使新的新式設定也有所改善。

使用 Exchange Online 中信箱的 Microsoft 365 組織會受到 Exchange Online Protection (EOP) 的保護。 這種保護包括：

- 具有可疑惡意軟體的電子郵件將會自動遭到隔離，並會通知收件者。 請參閱 [在 EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md)。
- 識別為高可信度網路釣魚的電子郵件會依照反垃圾郵件原則動作進行處理。 請參閱 [在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

如需 EOP 的詳細資訊，請參閱[Exchange Online Protection 總覽](exchange-online-protection-overview.md)。

因為 Microsoft 想要讓客戶保持安全，但在預設情況下，有些承租人覆寫不會套用到惡意程式碼或高可信度網路釣魚。 這些覆寫包括：

-  (反垃圾郵件原則所允許的寄件者清單或允許的網域清單) 
- Outlook 保管庫寄件者
- IP 允許清單 (連線篩選) 

您可以在 [ [建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)] 中找到這些優先選項的詳細資訊。

> [!NOTE]
> 我們已棄用 [ **將郵件移至垃圾郵件資料夾** ] 動作，讓 **高可信度網路釣魚電子郵件** 成為 EOP 反垃圾郵件原則。 使用此動作進行高可信度網路釣魚郵件的反垃圾郵件原則會轉換成 **隔離郵件**。 高信賴網路釣魚郵件的重新 **導向電子郵件地址** 動作不會受到影響。

安全的預設值不是可以開啟或關閉的設定，但是我們的篩選功能的方式，讓您的信箱不會有潛在危險或有害的郵件。 應該隔離惡意程式碼和高可信度網路釣魚郵件。 只有系統管理員可以管理被隔離為惡意程式碼或高可信度網路釣魚的郵件，而且也可以從那裡向 Microsoft 報告誤報。 如需詳細資訊，請參閱 [在 EOP 中管理被隔離的郵件和檔案為系統管理員](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>更深入瞭解為何這麼做

根據預設，安全的精神是：我們對郵件採取相同的動作，即使您知道郵件是惡意的，即使已設定的例外狀況允許傳送郵件也是一樣。 這是我們永遠用於惡意程式碼的相同方法，現在我們將這種相同的行為擴充為高信賴網路釣魚郵件。

我們的資料會指出使用者的30倍于垃圾郵件資料夾和隔離區中的郵件中，按一下惡意連結的可能性也會比較高。 我們的資料也會指出為高信賴網路釣魚郵件標示為錯誤) 的誤報比率 (很低，且系統管理員可以使用系統管理員提交來解析任何誤報。

我們也會判斷反垃圾郵件原則中允許的寄件者與允許的網域清單，以及保管庫 Outlook 中的寄件者過於廣泛，且造成的損害超過良好的損害。

若要將它放在另一種方式中：作為一種安全性服務，我們將替您代表，以避免使用者遭到破壞。

## <a name="exceptions"></a>例外狀況

> [!NOTE]
> 在2021年8月，安全性預設會擴充為 Exchange 郵件流程規則 (也稱為傳輸規則) 。 如果您使用郵件流程規則來允許協力廠商網路釣魚模擬或未篩選的傳遞至安全作業信箱，您最後必須消除這些規則，並在 _有可用的功能時_，切換至使用 [高級傳遞原則](configure-advanced-delivery.md)。

唯一允許高信賴網路釣魚郵件旁路篩選的覆寫是郵件流程規則。 若要使用郵件流程規則來略過篩選，請參閱 [使用郵件流程規則設定郵件中的 SCL](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)。

在下列案例中，您應該只考慮使用覆寫：

- 網路釣魚模擬：模擬的攻擊可協助您在實際攻擊影響組織之前，識別有漏洞的使用者。
- 安全性/SecOps 信箱：安全小組用來取得未篩選郵件 (良好且錯誤) 的專用信箱。 Teams 可以查看是否包含惡意內容。
- 協力廠商篩選：當網域的 MX 記錄未指向 Office 365 時，Secure 預設不適用。
- 誤報：您可能想要暫時允許由 Microsoft 透過系統 [管理員報送](admin-submission.md)進行的某些郵件仍在進行分析。 就像所有覆寫一樣，建議它們是臨時性的。
