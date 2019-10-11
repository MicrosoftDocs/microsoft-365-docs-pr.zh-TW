---
title: 反垃圾郵件訊息標頭
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: Exchange Online Protection 掃描輸入的電子郵件訊息時，會在每封郵件插入 **X-Forefront-Antispam-Report** 標頭。
ms.openlocfilehash: 5b7cefc2057d4e7705c991348a7710c2eaa4c7d9
ms.sourcegitcommit: ef5bcfe1e3d7d5a2a3c476477a0f82c84ed709e9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2019
ms.locfileid: "37428414"
---
# <a name="anti-spam-message-headers"></a>反垃圾郵件訊息標頭

Exchange Online Protection 掃描輸入的電子郵件訊息時，會在每封郵件插入 **X-Forefront-Antispam-Report** 標頭。 此標頭的欄位有助於提供系統管理員郵件及其處理方式的相關資訊。 **X-Microsoft-Antispam** 標頭中的欄位可提供大宗郵件和網路釣魚的額外資訊。 除了這兩個標頭之外，Exchange Online Protection 還會為其在 **Authentication-results** 標頭中處理的每封郵件插入電子郵件身份驗證結果。

如需如何在各種電子郵件用戶端中檢視電子郵件標頭的詳細資訊，請參閱[郵件標頭分析器](https://go.microsoft.com/fwlink/p/?LinkId=306583)。 
  
> [!TIP]
>  您可以複製郵件標頭的內容並貼到[郵件分析器](https://testconnectivity.microsoft.com/?tabid=mha) 工具中。 這項工具可協助您剖析標頭，並以易讀取的格式來呈現。
  
## <a name="x-forefront-antispam-report-message-header-fields"></a>X-Forefront-Antispam-Report 郵件標頭欄位

存取郵件標頭資訊之後，請搜尋 **X-Forefront-Antispam-Report**，然後尋找以下欄位。 此標頭的其他欄位專供 Microsoft 反垃圾郵件小組進行診斷之用。

|**標頭欄位**|**描述**|
|:-----|:-----|
|CIP：[IP 位址]|連接的 IP 位址。 在連線篩選器中建立 IP 允許清單或 IP 封鎖清單時，您可以指定此 IP 位址。 如需詳細資訊，請參閱[設定連線篩選原則](configure-the-connection-filter-policy.md)。|
|CTRY|郵件連線到服務的來源國家。這是由連線的 IP 位址來判斷，這可能與原始傳送的 IP 位址不同。|
|LANG|撰寫郵件所用的語言，如國碼所指定 (例如，ru_RU 代表俄文)。|
|SCL|郵件的垃圾郵件信賴等級 (SCL) 值。 如需解譯這些值的相關資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。|
|PCL|郵件的網路釣魚信賴等級 (PCL) 值。|
|SRV:BULK|郵件被識別為大量電子郵件。 如果啟用 [封鎖所有大量電子郵件的進階垃圾郵件篩選選項]****，則會將電子郵件標記為垃圾郵件。 如果未啟用，則會在其餘的篩選規則判斷該郵件為垃圾郵件時，才將它標記為垃圾郵件。|
|SFV:SFE|已略過篩選作業並允許郵件傳入，因為該郵件是從個人的安全寄件者清單上的地址寄送而來。|
|SFV:BLK|已略過篩選作業，但郵件遭到封鎖，因為該郵件是從個人的封鎖寄件者清單上的地址寄來的。  <br/> **秘訣**：如需使用者應如何建立安全和封鎖寄件者清單的詳細資訊，請參閱[封鎖或允許 (垃圾郵件設定)](https://go.microsoft.com/fwlink/p/?LinkId=294862) (Outlook 網頁版) 以及[垃圾電子郵件篩選概觀](https://go.microsoft.com/fwlink/p/?LinkId=270065) (Outlook)。|
|IPV:CAL|因為 IP 位址指定於連線篩選的 [IP 允許] 清單中，所以已透過垃圾郵件篩選允許郵件。|
|IPV:NLI|IP 位址不被列在任何 IP 信譽清單中。|
|SFV:SPM|內容篩選已將郵件標記為垃圾郵件。|
|SFV:SKS|內容篩選在處理郵件前，已將郵件標記為垃圾郵件。 這包括符合郵件流程規則 (也稱為傳輸規則) 而自動標記為垃圾郵件，因而略過所有其他篩選的郵件。|
|SFV:SKA|郵件已略過篩選並已傳送到收件匣，因為它符合垃圾郵件篩選原則中的允許清單，例如 [寄件者允許]**** 清單。|
|SFV:SKB|郵件已標示為垃圾郵件，因為它符合垃圾郵件篩選原則中的封鎖清單，例如 [寄件者封鎖]**** 清單。|
|SFV:SKN|郵件在受到內容篩選處理之前已被標記為非垃圾郵件。 這包括符合郵件流程規則而自動標記為非垃圾郵件，因而略過所有其他篩選的郵件。|
|SFV:SKI|與 SFV:SKN 類似；郵件基於其他原因 (例如，因為是租用戶內的組織內部電子郵件) 而略過篩選。|
|SFV:SKQ|郵件已從隔離區釋出，並傳送給預定的收件者。|
|SFV:NSPM|郵件標記為非垃圾郵件，並傳送給預定的收件者。|
|H:[helostring]|連線郵件伺服器的 HELO 或 EHLO 字串。|
|PTR:[ReverseDNS]|傳送 IP 位址 (也稱為反向 DNS 位址) 的 PTR 記錄或指標記錄。|
|CAT：|郵件所套用的保護原則類別： <br/>MALW：惡意程式碼 <br/>PHSH：網路釣魚 <br/>HSPM：高信賴度的垃圾郵件 <br/>SPOOF：詐騙 <br/>SPM：垃圾郵件 <br/>BULK：大量郵件 <br/>DIMP：網域冒充 <br/>UIMP：使用者冒充 <br/>可能可以透過多種形式的保護和多次偵測掃描來標記傳入郵件。 原則具有不同的優先次序，將套用優先次序最高的原則。 請參閱[在您的電子郵件上執行多種保護方法和偵測掃描時適用的原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/how-policies-and-protections-are-combined)。|
|SFTY|郵件已被識別為網路釣魚，並且也會標示為以下其中一個值： <br/>9.1：預設值。 該郵件包含網路釣魚 URL、可能包含其他網路釣魚內容，或者在將郵件轉送到 Office 365 之前，可能已被其他郵件篩選器 (如內部部署的 Exchange Server 版本) 標記為網路釣魚郵件。 <br/>9.11：郵件的反詐騙檢查失敗，其中 [寄件者:] 標頭中的寄件網域與接收網域相同，或與接收網域相同或屬於同一組織。 這表示將在郵件中新增組織內部詐騙安全提示。 <br/>9.19：郵件的網域模擬檢查失敗，寄件網域嘗試模擬接收者擁有的網域，或受反網路釣魚原則保護的自訂網域。 這表示如果透過反網路釣魚原則來啟用，則會在郵件中新增模擬安全提示。 <br/>9.20：郵件的使用者模擬檢查失敗，寄件使用者嘗試模擬接收者組織內的使用者，或受反網路釣魚原則保護的自訂使用者。 這表示如果透過反網路釣魚原則來啟用，則會在郵件中新增模擬安全提示。 <br/>9.21：郵件的反詐騙檢查失敗，[寄件者:] 標頭中的寄件網域不驗證且來自外部網域。 搭配 CompAuth 使用 (請參閱 Authentication-Results)。 <br/>9.22：與 9.21 相同，唯一不同的是使用者的安全寄件者遭到覆寫。 <br/>9.23：與 9.22 相同，唯一不同的是組織允許遭到覆寫的寄件者或網域。 <br/>9.24：與 9.23 相同，唯一不同的是使用者的 Exchange 郵件流程規則遭到覆寫。|
|X-CustomSpam: [ASFOption]|郵件符合進階的垃圾郵件篩選選項。 例如，**X-CustomSpam: Image links to remote sites** 表示已符合 [遠端站台的影像連結]**** ASF 選項。 若要了解每個特定的 ASF 選項新增的 X-header 文字，請參閱[進階垃圾郵件篩選選項](advanced-spam-filtering-asf-options.md)。|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>X-Microsoft-Antispam 郵件標頭欄位

下表說明在 **X-Microsoft-Antispam** 郵件標頭中的實用欄位。 此標頭的其他欄位專供 Microsoft 反垃圾郵件小組進行診斷之用。
  
|**標頭欄位**|**描述**|
|:-----|:-----|
|BCL|郵件的大量相容層級 (BCL)。 如需詳細資訊，請參閱[大量相容層級值](bulk-complaint-level-values.md)。|
|PCL|郵件的網路釣魚信賴等級 (PCL)，表示郵件是否為網路釣魚郵件。 此狀態可以傳回下列其中一個數值： <br/>**0-3**：郵件內容不可能是網路釣魚郵件。 <br/>**4-8**：郵件內容有可能是網路釣魚郵件。 <br/>**-9990**：(僅限 Exchange Online Protection) 郵件內容有可能是網路釣魚郵件。  <br/>  這些值用於判定您的電子郵件用戶端會對郵件採取的動作。 例如，Outlook 會使用 PCL 戳記來封鎖可疑郵件的內容。 如需網路釣魚及 Outlook 如何處理網路釣魚郵件的詳細資訊，請參閱[開啟或關閉電子郵件中的連結](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8)。|
|

## <a name="authentication-results-message-header"></a>Authentication-results 郵件標頭

當我們的郵件伺服器收到電子郵件時，Office 365 會在 **Authentication-results** 郵件標頭中記錄或標記對 SPF、DKIM 和DMARC 的檢查結果。
  
### <a name="check-stamp-syntax-and-examples"></a>檢查戳記語法及範例

以下語法範例顯示，當我們的郵件伺服器在收到郵件時，Office 365 針對進行電子郵件驗證檢查的每封電子郵件套用至郵件標頭的文字「戳記」部分。 該戳記會新增至 **Authentication-Results** 標頭。
  
**語法：SPF 檢查戳記**
  
針對 SPF 會套用下列語法。
  
```text
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

**範例：SPF 檢查戳記**
  
```text
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

**語法：DKIM 檢查戳記**
  
針對 DKIM 會套用下列語法。
  
```text
dkim=<pass|fail (reason)|none> header.d=<domain>
```

**範例：DKIM 檢查戳記**
  
```text
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

**語法：DMARC 檢查戳記**
  
針對 DMARC 會套用下列語法。
  
```text
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

**範例：DMARC 檢查戳記**
  
```text
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>Office 365 電子郵件驗證使用的 Authentication-results 郵件標頭欄位

下表描述每個電子郵件驗證檢查的欄位和可能的值。
  
|**標頭欄位**|**描述**|
|:-----|:-----|
|spf|描述郵件的 SPF 檢查結果。 可能的值包括： <br/>**pass (IP 位址)**：表示郵件的 SPF 檢查通過，且會包含寄件者的 IP 位址。 用戶端獲得授權，可代表寄件者的網域傳送或轉送電子郵件。 <br/>**fail (IP 位址)**：表示郵件的 SPF 檢查失敗，且會包含寄件者的 IP 位址。 有時也稱為 _hard fail_。 <br/>**softfail (原因)**：表示 SPF 記錄已將主機指定為不允許傳送但處於轉換狀態。 <br/>**neutral**：表示 SPF 記錄已明確聲明它未宣告 IP 地址是否已獲授權。 <br/>**none**：表示網域沒有 SPF 記錄或 SPF 記錄未計算結果。 <br/>**temperror**：表示錯誤的發生可能是暫時性的，例如 DNS 錯誤。 稍後再試可能就會成功，系統管理員無須採取任何動作。 <br/>**permerror**：表示發生永久性錯誤。 例如，當網域擁有的 SPF 記錄格式錯誤時，就可能會發生永久性錯誤。|
|smtp.mailfrom|包含郵件傳送來源的來源網域。 有關此電子郵件的任何錯誤都將傳送給郵件管理員或負責該網域的實體。 這有時稱為 5321.MailFrom 地址或郵件信封上的反向路徑地址。|
|dkim|描述郵件的 DKIM 檢查結果。 可能的值包括： <br/>**pass**：表示郵件的 DKIM 檢查通過。 <br/>**fail (原因)**：表示郵件的 DKIM 檢查失敗及原因。 例如，郵件未簽署或簽章未經過驗證。 <br/>**none**：表示郵件未簽署。 這可能會也可能不會表示網域具有 DKIM 記錄或 DKIM 記錄未計算結果，僅表示此郵件未簽署。|
|header.d|如果有的話，表示在 DKIM 簽章中識別出網域。 這是查詢公開金鑰的網域。|
|dmarc|描述郵件的 DMARC 檢查結果。 可能的值包括： <br/>**pass**：表示郵件的 DMARC 檢查通過。 <br/>**fail**：表示郵件的 DMARC 檢查失敗。 <br/>**bestguesspass**：表示該網域沒有 DMARC TXT 記錄，但如果有，郵件的 DMARC 檢查就會通過。 這是因為 5321.MailFrom 地址中的網域符合 5322.From 地址中的網域。 <br/>**none**：表示 DNS 中的寄件網域沒有 DKIM TXT 記錄。|
|action|表示垃圾郵件篩選器根據 DMARC 檢查結果所採取的動作作。 例如： <br/>**permerror**：在 DMARC 評估期間發生永久性錯誤，例如在 DNS 中發生格式錯誤的 DMARC TXT 記錄。 嘗試重新傳送此郵件也不太會有不同的結果。 相反地，您可能需要連絡網域擁有者來解決問題。 <br/>**temperror**：DMARC 評估期間發生暫時錯誤。 您可能可以要求寄件人稍後重新傳送郵件，以便正確處理電子郵件。 <br/>**oreject** 或 **o.reject**：代表覆寫拒絕。 在這種情況下，當 Office 365 從DMARC TXT 記錄具有 p = reject 原則的網域收到 DMARC 檢查失敗的郵件時，Office 365 將採取此動作。 Office 365 會將郵件標記為垃圾郵件，而不是刪除或拒絕郵件。 如需 Office 365 以這種方式設定的原因詳細資訊，請參閱 [Office 365 如何處理未通過 DMARC 的輸入電子郵件](use-dmarc-to-validate-email.md#inbounddmarcfail)。 <br/>**pct.quarantine**：表示無論如何都將傳遞百分比少於 100% 的未通過 DMARC 的郵件。 這表示郵件的 DMARC 失敗並且原則設定為為隔離，但 pct 欄位未設定為 100 %，因此系統隨機決定不根據指定網域的原則來套用 DMARC 動作。 <br/>**pct.reject**：表示無論如何都將傳遞百分比少於 100% 的未通過 DMARC 的郵件。 這表示郵件的 DMARC 失敗並且原則設定為為拒絕，但 pct 欄位未設定為 100 %，因此系統隨機決定不根據指定網域的原則來套用 DMARC 動作。|
|header.from|電子郵件標頭中 From 地址的網域。 這有時稱為 _5322.From_ 地址。|
|compauth|複合驗證結果。 Office 365 所使用，用於組合多種類型的驗證 (如 SPF、DKIM、DMARC 或郵件的任何其他部分)，以判斷郵件是否經過驗證。 使用 From: 網域作為評估基礎。|
|reason|複合驗證通過或失敗的原因。 原因值由三個數字組成： <br/>**000**：郵件驗證明確失敗。 例如，郵件收到 DMARC 失敗以及隔離或拒絕的動作。 <br/>**001**：郵件驗證隱含地失敗，且寄件網域未發佈驗證原則。 例如，DMARC 原則為 p=none。 <br/>**1xx**：郵件通過驗證。 後面兩個數字是 Office 365 使用的內部代碼。 <br/>**2xx**：郵件非強制通過驗證。 後面兩個數字是 Office 365 使用的內部代碼。 <br/>**3xx**：郵件未進行複合驗證檢查。 <br/>**4xx**：郵件略過複合驗證。 後面兩個數字是 Office 365 使用的內部代碼。|
|
