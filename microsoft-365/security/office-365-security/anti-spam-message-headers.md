---
title: 反垃圾郵件訊息標頭
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
description: 系統管理員可以透過 Exchange Online Protection （EOP）瞭解新增至郵件的標題欄位。 這些標題欄位可提供訊息及其處理方式的相關資訊。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0d2dae09db7b29c28196e2748392311096cd2b1
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411731"
---
# <a name="anti-spam-message-headers-in-microsoft-365"></a>Microsoft 365 的反垃圾郵件標頭

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在所有 Microsoft 365 組織中，Exchange Online Protection (EOP) 會掃描所有內送郵件是否有垃圾郵件、惡意程式碼及其他威脅。 這些掃描的結果會新增至郵件中的下列標頭欄位：

- **X-Forefront-Antispam-Report**：包含訊息及其處理方式的相關資訊。

- **X-Microsoft-Antispam**：包含大宗郵件和網路釣魚的相關額外資訊。

- **Authentication-results**：包含 SPF、DKIM 和 DMARC (電子郵件驗證) 結果的相關資訊。

本文將說明這些標頭欄位提供的項目。

如需如何在各種電子郵件用戶端中檢視電子郵件標頭的詳細資訊，請參閱 [在 Outlook 中查看網際網路郵件標題](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)。

> [!TIP]
> 您可以複製訊息標題的內容並貼到[訊息標題分析器](https://mha.azurewebsites.net/) 工具中。 這項工具可協助您剖析標頭，並以易讀取的格式來呈現。

## <a name="x-forefront-antispam-report-message-header-fields"></a>X-Forefront-Antispam-Report 郵件標頭欄位

當您擁有訊息標題資訊之後，請找出 **X-Forefront-反垃圾郵件報告** 標題。 此標頭中會有多個欄位和值組，並以分號 (;) 分隔。 例如：

`...CTRY:;LANG:hr;SCL:1;SRV:;IPV:NLI;SFV:NSPM;PTR:;CAT:NONE;SFTY:;...`

下表說明個別欄位和值。

> [!NOTE]
> **X-Forefront-Antispam-Report** 標頭包含許多不同的欄位和值。 未在表格中描述的欄位專供 Microsoft 反垃圾郵件小組用於診斷目的。

****

|欄位|描述|
|---|---|
|`ARC`|`ARC` 通訊協定含有下列欄位： <ul><li>`AAR`：記錄來自 DMARC 的 **Authentication-results** 標頭的內容。</li><li>`AMS`：包含郵件的加密簽章。</li><li>`AS`：包含郵件標頭的加密簽章。 此欄位含有名為 `"cv="` 的鏈結驗證標籤，其中包含鏈結驗證結果為 **none**、**pass** 或 **fail**。</li></ul>|
|`CAT:`|郵件所套用的保護原則類別： <ul><li>`BULK`：大量</li><li>`DIMP`：網域模擬</li><li>`GIMP`：[以信箱情報為基礎的模擬](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)</li><li>`HPHSH` 或 `HPHISH`：高信賴度網路釣魚</li><li>`HSPM`：高信賴度垃圾郵件</li><li>`MALW`：惡意程式碼</li><li>`PHSH`：網路釣魚</li><li>`SPM`：垃圾郵件</li><li>`SPOOF`：詐騙</li><li>`UIMP`：使用者模擬</li><li>`AMP`：反惡意程式碼</li><li>`SAP`：安全附件</li><li>`OSPM`：輸出垃圾郵件</li></ul><br/>可以透過多種形式的保護和多次偵測掃描來標記輸入郵件。 原則具有不同的優先次序，將套用優先次序最高的原則。 如需詳細資訊，請參閱[在您的電子郵件上執行多種保護方法和偵測掃描時適用的原則](how-policies-and-protections-are-combined.md)。|
|`CIP:[IP address]`|連接的 IP 位址。 您可以在 IP 允許清單或 IP 封鎖清單中使用這個 IP 位址。 如需詳細資訊，請參閱[設定連線篩選](configure-the-connection-filter-policy.md)。|
|`CTRY`|來源國家/地區是由連線的 IP 位址來判斷，這可能與原始傳送的 IP 位址不同。|
|`H:[helostring]`|連線電子郵件伺服器的 HELO 或 EHLO 字串。|
|`IPV:CAL`|郵件跳過垃圾郵件篩選，因為來源 IP 位址位於 IP 允許清單中。 如需詳細資訊，請參閱[設定連線篩選](configure-the-connection-filter-policy.md)。|
|`IPV:NLI`|IP 位址無法在任何 IP 信譽清單上找到。|
|`LANG`|撰寫郵件所用的語言，如國碼所指定 (例如，ru_RU 代表俄文)。|
|`PTR:[ReverseDNS]`|來源 IP 位址的 PTR 記錄 (又稱為反向 DNS 查閱)。|
|`SCL`|郵件的垃圾郵件信賴等級 (SCL)。 此值越高，表示郵件越有可能是垃圾郵件。 如需詳細資訊，請參閱[垃圾郵件信賴等級 (SCL)](spam-confidence-levels.md)。|
|`SFTY`|郵件已被識別為網路釣魚，並且也會標示為以下其中一個值： <ul><li>9.1：預設值。 郵件包含下列部分或所有元素：網路釣魚 URL、其他網路釣魚內容，或是由內部部署 Exchange 標記為網路釣魚。</li><li>9.11：[組織內部或自我詐騙](anti-spoofing-protection.md#different-types-of-spoofing)。 組織內部詐騙的安全提示會新增至郵件。</li><li>9.19：網域冒充。 傳送端網域嘗試[模擬受保護的網域](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)。 網域模擬的安全提示會新增至郵件 (如果已啟用)。</li><li>9.20：使用者冒充。 寄件使用者嘗試冒充收件者組織中的使用者，或 ATP 防網路釣魚原則中指定的受保護使用者。 使用者模擬的安全提示會新增至郵件 (如果已啟用)。</li><li>9.21：[跨網域詐騙](anti-spoofing-protection.md#different-types-of-spoofing)。 郵件無法通過反詐騙檢查。 [寄件者] 標頭中的寄者件電子郵件網域未驗證，而且是外部網域。 結合[複合驗證](#authentication-results-message-header-fields)使用。</li><li>9.22：與 9.21 相同，唯一不同的是使用者的安全寄件者遭到覆寫。</li><li>9.23：與 9.22 相同，唯一不同的是組織允許遭到覆寫的寄件者或網域。</li><li>9.24：與 9.23 相同，唯一不同的是使用者的 Exchange 郵件流程規則 (又稱為傳輸規則) 遭到覆寫。</li></ul>|
|`SFV:BLK`|已略過篩選，但封鎖郵件，因為該郵件是從使用者的封鎖寄件者清單上的地址傳送。<br/></br> 如需系統管理員如何管理使用者的封鎖寄件者清單的詳細資訊，請參閱[設定 Exchange Online 信箱的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。|
|`SFV:NSPM`|垃圾郵件篩選已將郵件標示為非垃圾郵件，並將郵件傳送給預期的收件者。|
|`SFV:SFE`已略過篩選，但允許郵件，因為該郵件是從使用者的安全寄件者清單上的地址傳送。<br/></br> 如需系統管理員如何管理使用者的安全寄件者清單的詳細資訊，請參閱[設定 Exchange Online 信箱的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。|
|`SFV:SKA`|郵件跳過垃圾郵件篩選，並已傳送到收件匣，因為寄件者位於反垃圾郵件原則中允許的寄件者清單或允許的網域清單。 如需詳細資訊，請參閱[設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。|
|`SFV:SKB`|郵件被標示為垃圾郵件，因為該郵件符合反垃圾郵件原則中封鎖的寄件者清單或封鎖的網域清單中的寄件者。 如需詳細資訊，請參閱[設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。|
|`SFV:SKI`|與 SFV:SKN 類似，郵件基於其他原因而略過垃圾郵件篩選 (例如，租用戶內組織內部的電子郵件)。|
|`SFV:SKN`|郵件在受到垃圾郵件篩選處理之前已被標記為非垃圾郵件。 例如，郵件已由郵件流程規則標示為 SCL-1 或**略過垃圾郵件篩選**。|
|`SFV:SKQ`|郵件已從隔離區釋出，並傳送給預定的收件者。|
|`SFV:SKS`|郵件在受到垃圾郵件篩選處理之前已被標記為垃圾郵件。 例如，郵件已由郵件流程規則標示為 SCL 5 到 9。|
|`SFV:SPM`|垃圾郵件篩選已將此郵件標記為垃圾郵件。|
|`SRV:BULK`|垃圾郵件篩選和大量抱怨層級 (BCL) 閾值將郵件視為大宗郵件。 當 _MarkAsSpamBulkMail_ 參數為 `On` (非預設值)，大量電子郵件會被標示為高信賴度的垃圾郵件 (SCL 9)。 如需詳細資訊，請參閱[設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。|
|`X-CustomSpam: [ASFOption]`|郵件符合進階垃圾郵件篩選 (ASF) 設定。 若要查看每個 ASF 設定的 X 標頭值，請參閱[進階垃圾郵件篩選 (ASF) 設定](advanced-spam-filtering-asf-options.md)。|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>X-Microsoft-Antispam 郵件標頭欄位

下表說明在 **X-Microsoft-Antispam** 郵件標頭中的實用欄位。 此標頭的其他欄位專供 Microsoft 反垃圾郵件小組進行診斷之用。

****

|欄位|描述|
|---|---|
|`BCL`|郵件的大量抱怨層級 (BCL)。 BCL 高，表示大量郵件訊息更容易引發抱怨 (因此更可能是垃圾郵件)。 如需詳細資訊，請參閱[大量相容層級 (BCL)](bulk-complaint-level-values.md)。|
|

## <a name="authentication-results-message-header"></a>Authentication-results 郵件標頭

SPF、DKIM 和 DMARC 的電子郵件驗證檢查結果會記錄 (加戳記) 在輸入郵件的 **Authentication-results** 郵件標頭中。

下列清單說明針對每個類型電子郵件驗證檢查新增至 **Authentication-Results** 標頭的文字：

- SPF 使用下列語法：

  ```text
  spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
  ```

  例如：

  ```text
  spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
  spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
  ```

- DKIM 使用下列語法：

  ```text
  dkim=<pass|fail (reason)|none> header.d=<domain>
  ```

  例如：

  ```text
  dkim=pass (signature was verified) header.d=contoso.com
  dkim=fail (body hash did not verify) header.d=contoso.com
  ```

- DMARC 使用下列語法：

  ```text
  dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
  ```

  例如：

  ```text
  dmarc=pass action=none header.from=contoso.com
  dmarc=bestguesspass action=none header.from=contoso.com
  dmarc=fail action=none header.from=contoso.com
  dmarc=fail action=oreject header.from=contoso.com
  ```

### <a name="authentication-results-message-header-fields"></a>Authentication-results 郵件標頭欄位

下表描述每個電子郵件驗證檢查的欄位和可能的值。

****

|欄位|描述|
|---|---|
|`action`|表示垃圾郵件篩選器根據 DMARC 檢查結果所採取的動作作。 例如： <ul><li>**oreject** 或 **o.reject**：代表覆寫拒絕。 在這種情況下，當 Microsoft 365 從DMARC TXT 記錄具有 p=reject 原則的網域收到 DMARC 檢查失敗的郵件時，將會採取此動作。 Microsoft 365 會將郵件標記為垃圾郵件，而不是刪除或拒絕郵件。 如需 Microsoft 365 以這種方式設定的原因詳細資訊，請參閱 [Microsoft 365 如何處理未通過 DMARC 的輸入電子郵件](use-dmarc-to-validate-email.md#how-microsoft-365-handles-inbound-email-that-fails-dmarc)。</li><li>**pct.quarantine**：表示無論如何都將傳遞百分比少於 100% 的未通過 DMARC 的郵件。 這表示郵件的 DMARC 失敗並且原則設定為為隔離，但 pct 欄位未設定為 100 %，因此系統隨機決定不根據指定網域的原則來套用 DMARC 動作。</li><li>**pct.reject**：表示無論如何都將傳遞百分比少於 100% 的未通過 DMARC 的郵件。 這表示郵件的 DMARC 失敗並且原則設定為為拒絕，但 pct 欄位未設定為 100 %，因此系統隨機決定不根據指定網域的原則來套用 DMARC 動作。</li><li>**permerror**：在 DMARC 評估期間發生永久性錯誤，例如在 DNS 中發生格式錯誤的 DMARC TXT 記錄。 嘗試重新傳送此郵件也不太會有不同的結果。 相反地，您可能需要連絡網域擁有者來解決問題。</li><li>**temperror**：DMARC 評估期間發生暫時錯誤。 您可能可以要求寄件人稍後重新傳送郵件，以便正確處理電子郵件。</li></ul>|
|`compauth`|複合驗證結果。 Microsoft 365 所使用，用於組合多種類型的驗證 (如 SPF、DKIM、DMARC 或郵件的任何其他部分)，以判斷郵件是否經過驗證。 使用 From: 網域作為評估基礎。|
|`dkim`|描述郵件的 DKIM 檢查結果。 可能的值包括： <ul><li>**pass**：表示郵件的 DKIM 檢查通過。</li><li>**fail (原因)**：表示郵件的 DKIM 檢查失敗及原因。 例如，郵件未簽署或簽章未經過驗證。</li><li>**none**：表示郵件未簽署。 這可能會也可能不會表示網域具有 DKIM 記錄或 DKIM 記錄未計算結果，僅表示此郵件未簽署。</li></ul>|
|`dmarc`|描述郵件的 DMARC 檢查結果。 可能的值包括： <ul><li>**pass**：表示郵件的 DMARC 檢查通過。</li><li>**fail**：表示郵件的 DMARC 檢查失敗。</li><li>**bestguesspass**：表示該網域沒有 DMARC TXT 記錄，但如果有，郵件的 DMARC 檢查就會通過。 這是因為 `5321.MailFrom` 位址中的網域 (又稱為「郵件寄件者地址」、P1 寄件者或信封寄件者) 符合 `5322.From` 位址中的網域 (又稱為「寄件者地址」或 P2 寄件者)。</li><li>**none**：表示 DNS 中的寄件網域沒有 DKIM TXT 記錄。|
|`header.d`|如果有的話，表示在 DKIM 簽章中識別出網域。 這是查詢公開金鑰的網域。|
|`header.from`|電子郵件標頭中 `5322.From` 位址的網域 (又稱為「寄件者地址」或 P2 寄件者)。 收件者會看到電子郵件用戶端中的寄件者地址。|
|`reason`|複合驗證通過或失敗的原因。 該值是 3 位數的代碼。 例如： <ul><li>**000**：郵件明確驗證失敗 (`compauth=fail`)。 例如，郵件收到 DMARC 失敗以及隔離或拒絕的動作。</li><li>**001** 表示郵件未通過隱含驗證 (`compauth=fail`)。 這表示，傳送網域未發佈電子郵件驗證記錄，或是有發佈，但是擁有較弱的失敗原則 (SPF 非封鎖性失敗或中性，DMARC 原則為 `p=none`)。</li><li>**002**：組織擁有的寄件者/網域配對原則明確禁止傳送詐騙電子郵件。 這項設定是由系統管理員手動設定。</li><li>**010**：郵件未通過 DMARC，並產生拒絕或隔離動作，而傳送網域是組織接受的其中一個網域 (為自我或組織內部詐騙的一部分)。</li><li>**1xx** 或 **7xx**：郵件通過驗證 (`compauth=pass`)。 最後兩個數字是 Microsoft 365 使用的內部代碼。</li><li>**2xx**：郵件非強制通過驗證 (`compauth=softpass`)。 最後兩個數字是 Microsoft 365 使用的內部代碼。</li><li>**3xx**：郵件未進行複合驗證檢查 (`compauth=none`)。</li><li>**4xx** 或 **9xx**：郵件略過複合驗證 (`compauth=none`)。 最後兩個數字是 Microsoft 365 使用的內部代碼。</li><li>**6xx**：表示郵件未通過隱含的電子郵件驗證，而傳送網域是組織接受的其中一個網域 (為自我詐騙，或稱為組織內部詐騙的一部分)。</li></ul>|
|`smtp.mailfrom`|`5321.MailFrom` 位址的網域 (又稱為「郵件寄件者地址」、P1 寄件者或信封寄件者)。 這是用於未傳遞回報 (又稱為 NDR 或退回的郵件) 的電子郵件地址。|
|`spf`|描述郵件的 SPF 檢查結果。 可能的值包括： <ul><li>`pass (IP address)`：郵件的 SPF 檢查通過，且包含寄件者的 IP 位址。 用戶端獲得授權，可代表寄件者的網域傳送或轉送電子郵件。</li><li>`fail (IP address)`：郵件的 SPF 檢查失敗，且包含寄件者的 IP 位址。 這有時也稱為 _hard fail_。</li><li>`softfail (reason)`：SPF 記錄已將主機指定為不允許傳送，但處於轉換狀態。</li><li>`neutral`：SPF 記錄明確指出它未宣告該 IP 位址是否獲授權可傳送。</li><li>`none`：網域沒有 SPF 記錄或 SPF 記錄未得到結果。</li><li>`temperror`：發生暫時性錯誤。 例如，DNS 錯誤。 相同檢查可能稍後會成功。</li><li>`permerror`：發生永久性錯誤。 例如，網域有格式錯誤的 SPF 記錄時。</li></ul>|
|
