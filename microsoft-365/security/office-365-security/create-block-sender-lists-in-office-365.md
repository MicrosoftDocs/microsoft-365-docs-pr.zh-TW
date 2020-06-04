---
title: 建立封鎖寄件者清單
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
description: 系統管理員可以深入瞭解可用及慣用的選項，以在 Exchange Online Protection （EOP）中封鎖輸入郵件。
ms.openlocfilehash: 2862fa4a33a31eac9c61f94aa929133d2dc69fc8
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545897"
---
# <a name="create-blocked-sender-lists-in-eop"></a>在 EOP 中建立封鎖的寄件者清單

在未使用 Exchange online 信箱的 Exchange Online 或獨立 Exchange Online Protection （EOP）組織中使用信箱的 Microsoft 365 組織中，EOP 提供多種方式，封鎖來自不想要的寄件者的電子郵件。 這些選項包括 Outlook 封鎖的寄件者、封鎖的寄件者清單或反垃圾郵件原則中的封鎖網域清單、Exchange 郵件流程規則（也稱為傳輸規則）和 IP 封鎖清單（連線篩選）。 綜合，您可以將這些選項視為_封鎖的寄件者清單_。

封鎖寄件者的最佳方法會因影響範圍而異。 針對單一使用者，正確的解決方案可能是 Outlook 封鎖的寄件者。 對於許多使用者而言，其中一個其他選項更適合。 下列選項依影響範圍及廣度排名。 清單從窄到寬，但閱讀完整建議的*詳細*資料。

1. Outlook 封鎖的寄件者（儲存于每個信箱的封鎖寄件者清單）

2. 封鎖的寄件者清單或封鎖的網域清單（反垃圾郵件原則）

3. 郵件流程規則

4. IP 封鎖清單（連線篩選）

> [!NOTE]
> 雖然您可以使用全組織的封鎖設定來處理虛假的否定（未接的垃圾郵件），您也應該將這些郵件提交給 Microsoft 進行分析。 使用封鎖清單來管理 false 負片會大幅增加您的管理額外負荷。 如果您使用封鎖清單來轉移未接的垃圾郵件，您必須在準備時讓主題向[Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md)檔案。

相比之下，您也可以使用_安全寄件者清單_，讓您有數個選項永遠允許來自特定來源的電子郵件。 如需詳細資訊，請參閱[建立安全寄件者清單](create-safe-sender-lists-in-office-365.md)。

## <a name="email-message-basics"></a>電子郵件訊息基礎

標準 SMTP 電子郵件由「郵件信封」**(Message Envelope) 和郵件內容組成。 郵件信封包含在 SMTP 伺服器之間傳輸及傳遞郵件所需的資訊。 郵件內容包含統稱為 (「郵件標頭」**) 的郵件標頭欄位和郵件內容。 RFC 5321 會說明郵件信封，而 RFC 5322 中說明郵件頭。 收件者永遠不會看到實際的郵件信封，因為它是由郵件傳輸程式所產生，而且實際上不是郵件的一部分。

- `5321.MailFrom`位址（也稱為「**郵件發**件人位址」、「P1 寄件者」或「信封寄件者」）是郵件 SMTP 傳輸中所用的電子郵件地址。 這個電子郵件地址通常會記錄在郵件頭的 [傳回**路徑**標頭] 欄位中（不過，寄件者可以指定不同的**回郵路徑**電子郵件地址）。 如果無法傳遞郵件，則表示收件者未傳遞回報（也稱為 NDR 或退回的郵件）。

- `5322.From`（也稱為**from** address 或 P2 寄件者）是 [**發**件人] 標頭欄位中的電子郵件地址，也就是顯示在電子郵件客戶程式中的寄件者電子郵件地址。

通常 `5321.MailFrom` 和 `5322.From` 位址相同（人員對人員的通訊）。 不過，當您代表其他人傳送電子郵件時，位址可能會不同。

EOP 中，封鎖的寄件者清單和封鎖的網域清單會檢查 `5321.MailFrom` 和 `5322.From` 位址。 Outlook 封鎖的寄件者只會使用該 `5322.From` 位址。

## <a name="use-outlook-blocked-senders"></a>使用 Outlook 封鎖的寄件者

當只有少量的使用者收到不想要的電子郵件時，使用者或系統管理員可以將寄件者電子郵件地址新增至信箱中的封鎖寄件者清單。 如需相關指示，請參閱[在 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。

當郵件因使用者的封鎖寄件者清單而成功封鎖時， **X-Forefront-Antispam-Report**標頭欄位將會包含此值 `SFV:BLK` 。

> [!NOTE]
> 如果不想要的郵件是來自可信和辨識來源的簡報，請從電子郵件取消訂閱，以停止使用者接收郵件。

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>使用封鎖的寄件者清單或封鎖的網域清單

當多個使用者受到影響時，範圍會變寬，所以下一個最佳選項是反垃圾郵件原則中的封鎖寄件者清單或封鎖的網域清單。 來自清單寄件者的郵件會標示為**垃圾**郵件，而您針對**垃圾郵件**篩選判定所設定的動作會針對郵件採取。 如需詳細資訊，請參閱[設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

這兩個清單的上限大約是1000個專案。

## <a name="use-mail-flow-rules"></a>使用郵件流程規則

如果您需要封鎖傳送給特定使用者或整個組織內的郵件，您可以使用郵件流程規則。 郵件流程規則比封鎖寄件者清單或封鎖的寄件者網域清單更為靈活，因為它們也可以在不想要的郵件中尋找關鍵字或其他屬性。

不論您用來識別郵件的條件或例外情況為何，您可以將動作設定為將郵件的垃圾郵件信賴等級（SCL）設定為9，這會將郵件標示為**高信賴的垃圾**郵件。 如需詳細資訊，請參閱[使用郵件流程規則設定郵件中的 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。

> [!IMPORTANT]
> 您可以輕鬆地建立*過於*嚴格的規則，所以請務必只使用特別的準則來識別您想要封鎖的郵件。 此外，請務必啟用規則的審計，並測試規則的結果，以確保所有內容如預期般運作。

## <a name="use-the-ip-block-list"></a>使用 IP 封鎖清單

當您無法使用其他其中一個選項來封鎖寄件者時，*只*應該使用連線篩選原則中的 IP 封鎖清單。 如需詳細資訊，請參閱[設定連線篩選原則](configure-the-connection-filter-policy.md)。 務必將封鎖的 Ip 數目維持在最小值，因此*不*建議封鎖整個 IP 位址範圍。

您應*特別*避免新增屬於消費者服務（例如，outlook.com）或共用基礎結構的 IP 位址範圍，並確定您檢查封鎖的 ip 地址清單以作為定期維護的一部分。
