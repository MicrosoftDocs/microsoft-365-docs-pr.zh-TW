---
title: 在 Office 365 中建立安全的寄件者清單
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
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: 系統管理員可以深入瞭解 Office 365 和 EOP 中可用的選項，讓輸入郵件可以略過垃圾郵件篩選。
ms.openlocfilehash: f9178dae93f8eb33996d05034d27fceed66edd39
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033407"
---
# <a name="create-safe-sender-lists-in-office-365"></a>在 Office 365 中建立安全的寄件者清單

如果您是 Office 365 客戶的信箱在 Exchange Online 或獨立 Exchange Online Protection （EOP）客戶（沒有 Exchange Online 信箱），EOP 會提供多種方式，以確保使用者接收來自信任寄件者的電子郵件。 這些選項包括 Exchange 郵件流程規則（也稱為傳輸規則）、Outlook 安全寄件者、IP 允許清單（連線篩選）和反垃圾郵件原則中允許的寄件者清單或允許的網域清單。 綜合，您可以將這些選項視為_安全寄件者清單_。

下列清單說明可用的安全寄件者清單，依從最高建議至最低建議的順序進行：

1. 郵件流程規則

2. Outlook 安全寄件者

3. IP 允許清單（連線篩選）

4. 允許的寄件者清單或允許的網域清單（反垃圾郵件原則）

郵件流程規則允許最大的彈性，以確保只允許正確的郵件。 反垃圾郵件原則中的允許寄件者與允許的網域清單不如 IP 允許清單安全，因為寄件者的電子郵件網域很容易遭到欺騙。 不過，IP 允許清單也會帶來風險，因為從該 IP 位址傳送的_任何_網域的電子郵件都會略過垃圾郵件篩選。

> [!IMPORTANT]
> <ul><li>請小心，並*監視使用*安全寄件者清單的垃圾郵件篩選例外狀況。</li><li>雖然您可以使用安全寄件者清單來協助誤報（良好的電子郵件標示為垃圾郵件），但您應考慮使用安全寄件者清單做為暫時的解決方案，以盡可能避免使用。 建議您不要使用安全寄件者清單來管理誤報，因為垃圾郵件篩選例外會開啟您的組織，以進行欺騙和其他攻擊。 如果您堅持使用安全寄件者清單來管理誤報，您必須時刻警惕，讓主題在準備好時，讓主題[向 Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md)檔案。</li><li>若要允許網域傳送未驗證的電子郵件（略過反欺騙保護），但不略過反垃圾郵件和反惡意程式碼檢查，您可以將它新增至[AllowedToSpoof 安全寄件者清單](walkthrough-spoof-intelligence-insight.md)</li><li>EOP 和 Outlook 會檢查不同的郵件內容，以判斷郵件的寄件者。 如需詳細資訊，請參閱本主題稍後的「[大量電子郵件](#considerations-for-bulk-email)」一節的考慮。</li></ul>

相比之下，您也有數個選項可以封鎖使用_封鎖的寄件者清單_來自特定來源的電子郵件。 如需詳細資訊，請參閱[在 Office 365 中建立封鎖寄件者清單](create-block-sender-lists-in-office-365.md)。

## <a name="recommended-use-mail-flow-rules"></a>推薦使用郵件流程規則

Exchange Online 和獨立 EOP 中的郵件流程規則使用條件和例外來識別郵件，以及指定應對這些郵件執行的動作。 如需詳細資訊，請參閱[在 Exchange Online 中的郵件流程規則（傳輸規則）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。

下列範例假設您需要 contoso.com 中的電子郵件，以略過垃圾郵件篩選。 若要這麼做，請設定下列設定：

1. **條件**：**寄件者** \> **網域為** \> contoso.com。

2. 設定下列其中一個設定：

   - **郵件流程規則條件**：**郵件頭** \> **包含下列任何字** \> **標頭名稱**： `Authentication-Results` \> **標頭值**： `dmarc=pass`或`dmarc=bestguesspass`。

     此條件會檢查傳送電子郵件網域的寄件者驗證狀態，以確定傳送網域未遭到欺騙。 如需有關電子郵件驗證的詳細資訊，請參閱[SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)及[DMARC](use-dmarc-to-validate-email.md)。

   - **IP 允許清單**：在連線篩選原則中指定來源 IP 位址或位址範圍。
  
     如果傳送網域沒有驗證，請使用此設定。 在 IP 允許清單中的來源 IP 位址到來時，請盡可能具有限制性。 建議的 IP 位址範圍為/24 或更少（越低越好）。 請勿使用屬於消費者服務（例如，outlook.com）或共用基礎結構的 IP 位址範圍。

   > [!IMPORTANT]
   > <ul><li>[永不設定郵件流程規則]*只*會將寄件者網域設定為略過垃圾郵件篩選的條件。 這樣做會*大幅*增加駭客欺騙傳送網域（或模仿完整電子郵件地址）的可能性，請略過所有垃圾郵件篩選，並略過寄件者驗證檢查，使郵件會送達收件者的收件匣。</li><li>請勿使用擁有的網域（也稱為公認的網域）或流行網域（例如，microsoft.com）做為郵件流程規則中的條件。 這樣做會將其視為高風險，因為它會產生機會讓攻擊者傳送本來會進行篩選的電子郵件。</li><li>如果您允許網路位址轉譯（NAT）閘道背後的 IP 位址，您必須知道 NAT 集區所涉及的伺服器，才能知道 IP 允許清單的範圍。 IP 位址和 NAT 參與者可以變更。 您必須定期檢查您的 IP 允許清單專案，以作為標準維護程式的一部分。</li></ul>

3. **選用的條件**：

   - **寄件者** \>是在**組織外**的**內部/外部** \> ：此條件是隱含的，但可使用它來考慮可能未正確設定的內部部署電子郵件伺服器。

   - **主旨或** \>本文的主旨或內文**包含下列任何文字** \> \<關鍵字\>：如果您可以以主旨行或郵件內文中的關鍵字或片語來進一步限制郵件，您可以使用這些字做為條件。

4. **動作**：在規則中設定這兩項動作：

   a. **修改郵件屬性** \> **設定垃圾郵件信賴等級（SCL）** \> **略過垃圾郵件篩選**。

   b. **郵件頭** \> **包含下列任何文字** \> **標頭名稱**： \<CustomHeaderName\> **標頭值**： \<CustomHeaderValue\>。

      例如，`X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`。 如果規則中有多個網域，您可以視需要自訂標頭文字。

      當郵件由於郵件流程規則而略過垃圾郵件篩選時，value `SFV:SKN`值會在**X-Forefront-Antispam-Report**標頭中戳。 如果郵件來自 IP 允許清單上的來源，也會新增此值`IPV:CAL` 。 這些值可協助您進行疑難排解。

![EAC 中的郵件流程規則設定，以略過垃圾郵件篩選。](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>使用 Outlook 安全寄件者

使用者或系統管理員可以將寄件者電子郵件地址新增至信箱中的安全寄件者清單，而不是組織設定。 如需相關指示，請參閱[在 Office 365 中設定 Exchange Online 信箱上的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。

當郵件因使用者的安全寄件者清單而略過垃圾郵件篩選時， **X-Forefront-Antispam-Report**標頭欄位`SFV:SFE`將會包含值，表示略過垃圾郵件、欺騙和網路釣魚篩選。

## <a name="use-the-ip-allow-list"></a>使用 IP 允許清單

如先前所述，您無法使用郵件流程規則，下一個最佳選項是將來源電子郵件伺服器或伺服器新增至連線篩選原則中的 IP 允許清單。 如需詳細資訊，請參閱[Configure connection 篩選 In Office 365](configure-the-connection-filter-policy.md)。

**附註**：

- 請務必將允許的 IP 位址數目維持在最低限度，以免盡可能避免使用整個 IP 位址範圍。

- 請勿使用屬於消費者服務（例如，outlook.com）或共用基礎結構的 IP 位址範圍。

- 請定期查看 IP 允許清單中的專案，並移除您不再需要的專案。

> [!CAUTION]
> 若未進行其他驗證，像是郵件流程規則，來自 IP 允許清單來源的電子郵件會跳過垃圾郵件篩選和寄件者驗證（SPF、DKIM、DMARC）檢查。 這會造成駭客成功將電子郵件傳遞至以其他方式篩選之收件匣的高風險。

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>使用允許的寄件者清單或允許的網域清單

最不可取的選項是使用反垃圾郵件原則中的允許寄件者清單或允許的網域清單。 您應該*盡可能*避免此選項，因為寄件者略過所有垃圾郵件、欺騙和網路釣魚防護，以及寄件者驗證（SPF、DKIM、DMARC）。 這種方法最適合用於暫時測試。 您可以在 Office 365 的 [[設定反垃圾郵件原則](configure-your-spam-filter-policies.md)] 主題中找到詳細步驟。

這兩個清單的上限大約是1000個專案;不過，您只可以將30個專案輸入入口網站。 您必須使用 PowerShell 來新增超過30個專案。

> [!CAUTION]
> <ul><li>這種方法會帶來極高的風險，讓攻擊者成功將電子郵件傳遞至收件匣，否則會加以篩選。</li><li>請勿在允許的網域清單中使用擁有的網域（也稱為公認的網域）或流行網域（例如，microsoft.com）。</li></ul>

## <a name="considerations-for-bulk-email"></a>大量電子郵件的考慮

標準 SMTP 電子郵件由「郵件信封」**(Message Envelope) 和郵件內容組成。 郵件信封包含在 SMTP 伺服器之間傳輸及傳遞郵件所需的資訊。 郵件內容包含統稱為 (「郵件標頭」**) 的郵件標頭欄位和郵件內容。 RFC 5321 會說明郵件信封，而 RFC 5322 中說明郵件頭。 收件者永遠不會看到實際的郵件信封，因為它是由郵件傳輸程式所產生，而且實際上不是郵件的一部分。

- `5321.MailFrom`位址（也稱為「**郵件發**件人位址」、「P1 寄件者」或「信封寄件者」）是郵件 SMTP 傳輸中所用的電子郵件地址。 這個電子郵件地址通常會記錄在郵件頭的 [傳回**路徑**標頭] 欄位中（不過，寄件者可以指定不同的**回郵路徑**電子郵件地址）。 此電子郵件地址用於寄件者驗證檢查（SPF、DKIM、DMARC），而且如果無法傳遞郵件，就是未傳遞回報的收件者（也稱為 NDR 或退回的郵件）。 

- （也稱為**from** Address 或 P2 寄件者）是 [寄件者] 標頭欄位中的電子郵件地址，也就是顯示在電子郵件客戶程式中的寄件者電子郵件地址。 **From** `5322.From`

通常`5321.MailFrom`和`5322.From`位址相同（人員對人員的通訊）。 不過，當您代表其他人傳送電子郵件時，這些位址通常會不同。 這通常是大量電子郵件的常見情況。

例如，假設「藍色 Yonder 航空公司」已雇用瑪姬旅行社傳送電子郵件廣告。 您在 [收件匣] 中收到的訊息具有下列屬性：

- `5321.MailFrom`位址是 blueyonder.airlines@margiestravel.com。

- `5322.From`位址是 blueyonder@news.blueyonderairlines.com，這是您在 Outlook 中看到的內容。

EOP 中的反垃圾郵件原則中的`5321.MailFrom`安全寄件者清單和安全網域清單`5322.From`會檢查及位址。 Outlook 安全寄件者只`5322.From`會使用位址。

若要防止郵件被篩選，您可以採取下列步驟：

- 新增 blueyonder@news.blueyonderairlines.com （ `5322.From`位址）為 Outlook 安全寄件者。

- [使用郵件流程規則](#recommended-use-mail-flow-rules)，條件是尋找來自 blueyonder@news.blueyonderairlines.com （ `5322.From`位址、blueyonder.airlines@margiestravel.com （ `5321.MailFrom`）或兩者的郵件。

如需詳細資訊，請參閱[在 Office 365 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。
