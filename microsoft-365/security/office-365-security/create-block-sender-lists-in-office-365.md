---
title: 在 Office 365 中建立封鎖的寄件者清單
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
- MET150s
description: 系統管理員可以深入瞭解 Office 365 和 EOP 中可用的選項，以封鎖輸入郵件。
ms.openlocfilehash: 9d53f49862bd69a846cb80ef584226a0940d2b22
ms.sourcegitcommit: a955324e33097bbd2fc4ad7f2b8d1f3d87bc8580
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43608112"
---
# <a name="create-blocked-sender-lists-in-office-365"></a>在 Office 365 中建立封鎖的寄件者清單

如果您是 Office 365 客戶的信箱位於 Exchange Online 或獨立 Exchange Online Protection （EOP）客戶，但沒有 Exchange Online 信箱，EOP 會提供多種方式，封鎖來自不想要的寄件者的電子郵件。 這些選項包括 Outlook 封鎖的寄件者、封鎖的寄件者清單或反垃圾郵件原則中的封鎖網域清單、Exchange 郵件流程規則（也稱為傳輸規則）和 IP 封鎖清單（連線篩選）。 綜合，您可以將這些選項視為_封鎖的寄件者清單_。

封鎖寄件者的最佳方法會因影響範圍而異。 針對單一使用者，正確的解決方案可能是 Outlook 封鎖的寄件者。 對於許多使用者而言，其中一個其他選項更適合。 下列選項依影響範圍及廣度排名。 清單從窄到寬，但閱讀完整建議的*詳細*資料。

1. Outlook 封鎖的寄件者（儲存于每個信箱的封鎖寄件者清單）

2. 封鎖的寄件者清單或封鎖的網域清單（反垃圾郵件原則）

3. 郵件流程規則

4. IP 封鎖清單（連線篩選）

> [!NOTE]
> 雖然您可以使用全組織的封鎖設定來處理虛假的否定（未接的垃圾郵件），您也應該將這些郵件提交給 Microsoft 進行分析。 使用封鎖清單來管理 false 負片會大幅增加您的管理額外負荷。 如果您使用封鎖清單來轉移未接的垃圾郵件，您必須在準備時讓主題向[Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md)檔案。

相比之下，您也可以使用_安全寄件者清單_，讓您有數個選項永遠允許來自特定來源的電子郵件。 如需詳細資訊，請參閱[在 Office 365 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。

## <a name="use-outlook-blocked-senders"></a>使用 Outlook 封鎖的寄件者

當只有少量的使用者收到不想要的電子郵件時，使用者或系統管理員可以將寄件者電子郵件地址新增至信箱中的封鎖寄件者清單。 如需相關指示，請參閱[在 Office 365 中設定 Exchange Online 信箱上的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。

當郵件因使用者的封鎖寄件者清單而成功封鎖時， **X-Forefront-Antispam-Report**標頭欄位將會包含`SFV:BLK`此值。

> [!NOTE]
> 如果不想要的郵件是來自可信和辨識來源的簡報，請從電子郵件取消訂閱，以停止使用者接收郵件。

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>使用封鎖的寄件者清單或封鎖的網域清單

當多個使用者受到影響時，範圍會變寬，所以下一個最佳選項是反垃圾郵件原則中的封鎖寄件者清單或封鎖的網域清單。 來自清單寄件者的郵件會標示為**垃圾**郵件，而您針對**垃圾郵件**篩選判定所設定的動作會針對郵件採取。 如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

這兩個清單的上限大約是1000個專案。

## <a name="use-mail-flow-rules"></a>使用郵件流程規則

如果您需要封鎖傳送給特定使用者或整個組織內的郵件，您可以使用郵件流程規則。 郵件流程規則比封鎖寄件者清單或封鎖的寄件者網域清單更為靈活，因為它們也可以在不想要的郵件中尋找關鍵字或其他屬性。

不論您用來識別郵件的條件或例外情況為何，您可以將動作設定為將郵件的垃圾郵件信賴等級（SCL）設定為9，這會將郵件標示為**高信賴的垃圾**郵件。 如需詳細資訊，請參閱[使用郵件流程規則設定郵件中的 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。

> [!IMPORTANT]
> 您可以輕鬆地建立*過於*嚴格的規則，所以請務必只使用特別的準則來識別您想要封鎖的郵件。 此外，請務必啟用規則的審計，並測試規則的結果，以確保所有內容如預期般運作。

## <a name="use-the-ip-block-list"></a>使用 IP 封鎖清單

當您無法使用其他其中一個選項來封鎖寄件者時，*只*應該使用連線篩選原則中的 IP 封鎖清單。 如需詳細資訊，請參閱[設定連線篩選原則](configure-the-connection-filter-policy.md)。 務必將封鎖的 Ip 數目維持在最小值，因此*不*建議封鎖整個 IP 位址範圍。

您應*特別*避免新增屬於消費者服務（例如，outlook.com）或共用基礎結構的 IP 位址範圍，並確定您檢查封鎖的 ip 地址清單以作為定期維護的一部分。
