---
title: 建立安全寄件者清單
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解可用及慣用的選項，允許在 Exchange Online Protection (EOP) 中輸入郵件。
ms.openlocfilehash: 38f1ab2451191dd63d5738075dbf42f8201a34ca
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659901"
---
# <a name="create-safe-sender-lists-in-eop"></a>在 EOP 中建立安全的寄件者清單

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


如果您是使用 Exchange Online 中的信箱或獨立 Exchange Online Protection (EOP) 客戶沒有 Exchange Online 信箱的 Microsoft 365 客戶，EOP 提供多種方式，以確保使用者能夠接收來自信任寄件者的電子郵件。 這些選項包括 Exchange 郵件流程規則 (也稱為傳輸規則) 、Outlook 安全寄件者、IP 允許清單 (連線篩選) ，以及反垃圾郵件原則中的允許的寄件者清單或允許的網域清單。 綜合，您可以將這些選項視為 _安全寄件者清單_。

下列清單說明可用的安全寄件者清單，依從最高建議至最低建議的順序進行：

1. 郵件流程規則
2. Outlook 安全寄件者
3. IP 允許清單 (連線篩選) 
4.  (反垃圾郵件原則所允許的寄件者清單或允許的網域清單) 

郵件流程規則允許最大的彈性，以確保只允許正確的郵件。 反垃圾郵件原則中的允許寄件者與允許的網域清單不如 IP 允許清單安全，因為寄件者的電子郵件網域很容易遭到欺騙。 不過，IP 允許清單也會帶來風險，因為從該 IP 位址傳送的 _任何_ 網域的電子郵件都會略過垃圾郵件篩選。

> [!IMPORTANT]
>
> - 小心使用安全寄件者清單密切監視垃圾郵件篩選的 *任何* 例外狀況。
>
> - 雖然您可以使用安全寄件者清單來協助誤報 (已標示為垃圾郵件) 的良好電子郵件，但您應考慮使用安全寄件者清單做為暫時的解決方案，以盡可能避免使用。 建議您不要使用安全寄件者清單來管理誤報，因為垃圾郵件篩選例外會開啟您的組織，以進行欺騙和其他攻擊。 如果您堅持使用安全寄件者清單來管理誤報，您必須時刻警惕，讓主題在準備好時，讓主題 [向 Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md) 檔案。
>
> - 若要讓網域傳送未驗證的電子郵件 (略過反欺騙保護) 但不略過反垃圾郵件和反惡意程式碼檢查，您可以將它新增至[AllowedToSpoof 安全寄件者清單](walkthrough-spoof-intelligence-insight.md)。
>
> - EOP 和 Outlook 會檢查不同的郵件內容，以判斷郵件的寄件者。 如需詳細資訊，請參閱本文稍後的「 [大量電子郵件](#considerations-for-bulk-email) 」一節的考慮。

相比之下，您也有數個選項可以封鎖使用 _封鎖的寄件者清單_ 來自特定來源的電子郵件。 如需詳細資訊，請參閱[在 EOP 中建立封鎖寄件者清單](create-block-sender-lists-in-office-365.md)。

## <a name="recommended-use-mail-flow-rules"></a>建議的 () 使用郵件流程規則

Exchange Online 和獨立 EOP 中的郵件流程規則使用條件和例外來識別郵件，以及指定應對這些郵件執行的動作。 如需詳細資訊，請參閱 [Mail flow rules (transport rules) In Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。

下列範例假設您需要 contoso.com 中的電子郵件，以略過垃圾郵件篩選。 若要這麼做，請設定下列設定：

1. **條件**： **寄件者** \> **網域為** \> contoso.com。

2. 設定下列其中一個設定：

   - **郵件流程規則條件**： **郵件頭** \> **包含下列任何字** \> **標頭名稱**： `Authentication-Results` \> **標頭值**： `dmarc=pass` 或 `dmarc=bestguesspass` 。

     此條件會檢查傳送電子郵件網域的電子郵件驗證狀態，以確定傳送網域未遭到欺騙。 如需有關電子郵件驗證的詳細資訊，請參閱 [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)及 [DMARC](use-dmarc-to-validate-email.md)。

   - **IP 允許清單**：在連線篩選原則中指定來源 IP 位址或位址範圍。

     若寄送網域未使用電子郵件驗證，請使用此設定。 在 IP 允許清單中的來源 IP 位址到來時，請盡可能具有限制性。 建議的 IP 位址範圍為/24 或更少 () 越好。 請勿使用屬於消費者服務的 IP 位址範圍 (例如，outlook.com) 或共用基礎結構。

   > [!IMPORTANT]
   >
   > - 永遠不 *會將發* 件人網域的郵件流程規則設定為略過垃圾郵件篩選的條件。 這樣做會 *大幅* 增加攻擊者欺騙傳送網域的可能性 (或模擬完整的電子郵件地址) 、略過所有垃圾郵件篩選，並略過寄件者驗證檢查，使郵件會到達收件者的收件匣。
   >
   > - 請勿使用您擁有的網域 (又稱為公認的網域) 或流行的網域 (例如，microsoft.com) 為郵件流程規則中的條件。 這樣做會將其視為高風險，因為它會產生機會讓攻擊者傳送本來會進行篩選的電子郵件。
   >
   > - 如果您允許在網路位址轉譯之後的 IP 位址 (NAT) 閘道，您必須知道 NAT 集區所涉及的伺服器，才能知道您的 IP 允許清單的範圍。 IP 位址和 NAT 參與者可以變更。 您必須定期檢查您的 IP 允許清單專案，以作為標準維護程式的一部分。

3. **選用的條件**：

   - **寄件者** \>**內部/外部** \>**組織外部**：此為隱含條件，但可使用它來考慮可能未正確設定的內部部署電子郵件伺服器。

   - **主語或** \> 本文主旨 **或本文包含任何這些字詞** \>\<keywords\>：如果您可以透過主旨行或郵件內文中的關鍵字或片語來進一步限制郵件，您可以使用這些字做為條件。

4. **動作**：在規則中設定這兩項動作：

   a. **修改郵件屬性** \>**將垃圾郵件信賴等級設定 (SCL)** \>**略過垃圾郵件篩選**。

   b. **修改郵件屬性** \>**設定郵件頭**：**將郵件頭設定** \<CustomHeaderName\> **為值** \<CustomHeaderValue\> 。

      例如，`X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`。 如果規則中有多個網域，您可以視需要自訂標頭文字。

      當郵件由於郵件流程規則而略過垃圾郵件篩選時，value `SFV:SKN` 值會在 **X-Forefront-Antispam-Report** 標頭中戳。 如果郵件來自 IP 允許清單上的來源， `IPV:CAL` 也會新增此值。 這些值可協助您進行疑難排解。

![EAC 中的郵件流程規則設定，以略過垃圾郵件篩選。](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>使用 Outlook 安全寄件者

使用者或系統管理員可以將寄件者電子郵件地址新增至信箱中的安全寄件者清單，而不是組織設定。 如需相關指示，請參閱 [在 Office 365 中設定 Exchange Online 信箱上的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。 在大多數情況下，這不是必要的，因為寄件者會略過部分的篩選堆疊。 雖然您信任寄件者，但仍然可以危及寄件者，並會傳送惡意內容。 您最好讓篩選器執行每封郵件檢查所需的動作，然後在篩選器有錯誤時， [向 Microsoft 報告 false 肯定/負數](report-junk-email-messages-to-microsoft.md) 。 略過篩選堆疊也會干擾 [ZAP](zero-hour-auto-purge.md)。

當郵件因使用者的安全寄件者清單而略過垃圾郵件篩選時， **X-Forefront-Antispam-Report** 標頭欄位將會包含此值 `SFV:SFE` ，表示已略過篩選垃圾郵件、欺騙和網路釣魚。

## <a name="use-the-ip-allow-list"></a>使用 IP 允許清單

如先前所述，您無法使用郵件流程規則，下一個最佳選項是將來源電子郵件伺服器或伺服器新增至連線篩選原則中的 IP 允許清單。 如需詳細資訊，請參閱 [Configure connection 篩選 IN EOP](configure-the-connection-filter-policy.md)。

**附註**：

- 請務必將允許的 IP 位址數目維持在最低限度，以免盡可能避免使用整個 IP 位址範圍。

- 請勿使用屬於消費者服務的 IP 位址範圍 (例如，outlook.com) 或共用基礎結構。

- 請定期查看 IP 允許清單中的專案，並移除您不再需要的專案。

> [!CAUTION]
> 若未進行其他驗證，像是郵件流程規則，來自 IP 允許清單來源的電子郵件會略過垃圾郵件篩選和寄件者驗證 (SPF、DKIM、DMARC) 檢查。 這會造成駭客成功將電子郵件傳遞至以其他方式篩選之收件匣的高風險。

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>使用允許的寄件者清單或允許的網域清單

最不可取的選項是使用反垃圾郵件原則中的允許寄件者清單或允許的網域清單。 您應 *盡可能* 避免此選項，因為寄件者略過所有垃圾郵件、欺騙和網路釣魚防護，而寄件者驗證 (SPF、DKIM、DMARC) 。 這個方法最適合用來進行暫時測試。 您可以在 EOP 主題中的 [設定反垃圾郵件原則](configure-your-spam-filter-policies.md) 中找到詳細步驟。

這兩個清單的上限大約是1000個專案;不過，您只可以將30個專案輸入入口網站。 您必須使用 PowerShell 來新增超過30個專案。

> [!CAUTION]
>
> - 這種方法會帶來極高的風險，讓攻擊者成功將電子郵件傳遞至收件匣，否則會加以篩選。
>
> - 請勿使用您擁有的網域 (又稱為公認的網域) 或流行的網域 (例如，允許的網域清單中的 microsoft.com) 。

## <a name="considerations-for-bulk-email"></a>大量電子郵件的考慮

標準 SMTP 電子郵件由「郵件信封」(Message Envelope) 和郵件內容組成。 郵件信封包含在 SMTP 伺服器之間傳輸及傳遞郵件所需的資訊。 郵件內容包含統稱為 (「郵件標頭」) 的郵件標頭欄位和郵件內容。 RFC 5321 會說明郵件信封，而 RFC 5322 中說明郵件頭。 收件者永遠不會看到實際的郵件信封，因為它是由郵件傳輸程式所產生，而且實際上不是郵件的一部分。

- 此 `5321.MailFrom` 位址 (也稱為「 **郵件來自** 位址」、「P1 寄件者」或「信封寄件者」) 是在郵件的 SMTP 傳輸中使用的電子郵件地址。 這個電子郵件地址通常會記錄在郵件頭的 [傳回 **路徑** 標頭] 欄位中 (不過，寄件者可能會指定不同的傳回 **路徑** 電子郵件地址) 。 如果無法傳遞郵件，表示未傳遞回報的收件者 (也稱為 NDR 或退回郵件) 。

- `5322.From` (也稱為 **from** address 或 P2 sender) 是電子郵件地址 **的收** 件者標頭欄位，也就是顯示在電子郵件客戶程式中的寄件者電子郵件地址。

通常， `5321.MailFrom` 與 `5322.From` 位址 (人員對人員通訊) 相同。 不過，當您代表其他人傳送電子郵件時，位址可能會不同。 這通常是大量電子郵件訊息的情形。

例如，假設「藍色 Yonder 航空公司」已雇用瑪姬旅行社傳送電子郵件廣告。 您在 [收件匣] 中收到的訊息具有下列屬性：

- `5321.MailFrom`位址是 blueyonder.airlines@margiestravel.com。

- `5322.From`位址是 blueyonder@news.blueyonderairlines.com，這是您在 Outlook 中看到的內容。

EOP 中的反垃圾郵件原則中的安全寄件者清單和安全網域清單僅檢查 `5322.From` 位址，這類似使用該位址的 Outlook 安全寄件者 `5322.From` 。

若要防止郵件被篩選，您可以採取下列步驟：

- 新增 blueyonder@news.blueyonderairlines.com (`5322.From`) 為 Outlook 安全寄件者的位址。

- [使用郵件流程規則](#recommended-use-mail-flow-rules) ，條件是尋找來自 blueyonder@news.blueyonderairlines.com (`5322.From` 位址、Blueyonder.airlines@margiestravel.com (`5321.MailFrom`) 或兩者的郵件。

如需詳細資訊，請參閱 [在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。
