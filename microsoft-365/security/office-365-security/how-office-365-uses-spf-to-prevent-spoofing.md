---
title: Office 365 如何使用寄件者原則架構 (SPF) 來防範詐騙
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
description: 摘要： 本文說明 Office 365 如何使用寄件者原則架構 (SPF) TXT 記錄在 DNS 中以確保目的地電子郵件系統信任自您自訂網域傳送的郵件。 這適用於從 Office 365 傳送的外寄郵件。 從 Office 365 傳送到 Office 365 內的收件者的郵件將會一律通過 SPF。
ms.openlocfilehash: 2845fc9b20b337764159d9debc04f165dcb4bf62
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076846"
---
# <a name="how-office-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a>Office 365 如何使用寄件者原則架構 (SPF) 來防範詐騙

 **摘要：** 本文說明 Office 365 如何使用寄件者原則架構 (SPF) TXT 記錄在 DNS 中以確保目的地電子郵件系統信任自您自訂網域傳送的郵件。 這適用於從 Office 365 傳送的外寄郵件。 從 Office 365 傳送到 Office 365 內的收件者的郵件將會一律通過 SPF。 
  
SPF TXT 記錄會驗證送出的電子郵件的網域名稱是 DNS 記錄，以協助防止詐騙和網路釣魚。 SPF 所指稱的擁有者為傳送網域的寄件者的 IP 位址驗證電子郵件訊息的原點而言。 
  
> [!NOTE]
> SPF 記錄類型已在 2014年中取代由網際網路工程任務推動小組 (IETF)。 相反地，請確定在 DNS 中使用 TXT 記錄，以發佈您的 SPF 資訊。 本文的其餘部分會使用該字詞的 SPF TXT 記錄以方便識別。 
  
網域系統管理員在 DNS 中的 TXT 記錄中發佈 SPF 資訊。 SPF 資訊會識別已授權的輸出電子郵件伺服器。 目的地電子郵件系統確認郵件來自 [已授權的輸出電子郵件伺服器。 如果您已熟悉 SPF，或您有簡單的部署，並只需要知道要納入您的 SPF TXT 記錄，在 DNS 中運作的 Office 365，您可以移至[設定 spf 以協助防止詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 如果您不需要是完全裝載於 Office 365 的部署或您想 SPF 的運作方式或如何疑難排解 Office 365 的 SPF，讓閱讀的相關資訊。
  
> [!NOTE]
> 先前，您必須將不同的 SPF TXT 記錄新增至您的自訂網域，如果您也使用 SharePoint Online。 你不再需要這樣做。 此變更會降低 SharePoint Online 通知訊息被置於「垃圾電子郵件」資料夾的機率。 您不需要進行任何變更立即，但如果您收到 「 太多查閱 」 錯誤，修改您的 SPF TXT 記錄中[設定 spf 以協助防止詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)所述。 
     
## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-office-365"></a>若要防止詐騙及 Office 365 中的網路釣魚 SPF 的運作方式
<a name="HowSPFWorks"> </a>

SPF 會決定允許寄件者的傳送代理者網域。 如果寄件者不允許若要這麼做，亦即，如果電子郵件失敗 SPF 檢查在接收伺服器上，在該伺服器上設定垃圾郵件原則決定如何處理郵件。
  
每個 SPF TXT 記錄包含三個部分： 宣告很 SPF TXT 記錄，可以從您的網域，可以傳送在您的網域代理，並強制執行規則的外部網域傳送郵件的 IP 位址。 您需要有效的 SPF TXT 記錄中的所有三個。 本文將告訴您如何形成 SPF TXT 記錄，並提供最佳作法來使用 Office 365 中的服務。 也提供指示，說明如何使用您的網域註冊機構的 DNS 來發佈您的記錄的連結。
  
### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a>SPF 基本概念： 允許從您的自訂網域傳送的 IP 位址
<a name="SPFBasicsIPaddresses"> </a>

請看一下 SPF 規則的基本語法：
  
v = spf1 \<IP\> \<強制執行規則\>
  
例如，假設 contoso.com 有下列 SPF 規則：
  
v = spf1 \<#1 的 IP 位址\> \<IP 位址為 #2\> \<#3 的 IP 位址\>\<強制執行規則\>
  
在這個範例中，SPF 規則會指示接收的電子郵件伺服器，以便只接受來自網域 contoso.com 這些 IP 位址的郵件：
  
- #1 的 IP 位址
    
- IP 位址為 #2
    
- #3 的 IP 位址
    
此 SPF 規則會告訴接收的電子郵件伺服器，如果郵件是從 contoso.com，但不是能從下列其中一個下列三個 IP 位址，接收伺服器應該將強制執行規則套用至郵件。 強制執行規則通常是其中一個選項：
  
- **完全未通過。** 在郵件信封中標示 '完全未通過' 的郵件，然後依照 [接收伺服器的設定垃圾郵件原則，這種類型的郵件。 
    
- **Fail。** 標記 'fail' 郵件信封中的郵件。 一般而言，電子郵件伺服器設定為仍將這些郵件傳遞。 大部分使用者看不到此標記。 
    
- **中性。** 不執行任何動作，也就是，不要將標示郵件信封。 這通常是僅供測試之用，而且不常使用。 
    
下列範例會顯示在不同情況下 SPF 的運作方式。 在下列範例中，contoso.com 是寄件者，且 woodgrovebank.com 接收者。
  
### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a>範例 1： 電子郵件驗證的直接從寄件者傳送給收件者的郵件
<a name="spfExample1"> </a>

SPF 適合時接收來自寄件者的路徑是直接，例如：
  
![流程圖顯示 SPF 如何驗證直接從伺服器傳送至伺服器的電子郵件。](../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)
  
當 woodgrovebank.com 接收郵件，如果 #1 的 IP 位址位於 contoso.com 的 SPF TXT 記錄時，郵件通過 SPF 檢查，並通過驗證。
  
### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a>範例 2： 詐騙的寄件者地址 SPF 檢查失敗
<a name="spfExample2"> </a>

假設 phisher 找到詐騙 contoso.com 的方式：
  
![流程圖顯示 SPF 如何驗證從詐騙的伺服器所傳送之電子郵件。](../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)
  
因為 IP 位址 #12 不是在 contoso.com 的 SPF TXT 記錄，SPF 檢查失敗郵件和收件者可以選擇將標示為垃圾郵件。
  
### <a name="example-3-spf-and-forwarded-messages"></a>範例 3: SPF 和轉寄的郵件
<a name="spfExample3"> </a>

SPF 有一項缺點是，它不會運作時已轉寄電子郵件。 例如，假設 woodgrovebank.com 中的使用者已將設有轉寄規則設定為將所有電子郵件傳送至 outlook.com 帳戶：
  
![流程圖顯示 SPF 在訊息被轉送時無法驗證電子郵件。](../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)
  
原本在 woodgrovebank.com 傳遞 SPF 檢查的郵件，但它就會失敗 SPF 檢查於 outlook.com，因為 IP #25 不在 contoso.com 的 SPF TXT 記錄。 Outlook.com 可能再將該郵件標記為垃圾郵件。 若要解決此問題，SPF 搭配使用與其他電子郵件驗證方法，例如 DKIM 和 DMARC。
  
### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a>SPF 基本概念： 包括可以代表您的網域傳送郵件的協力廠商網域
<a name="SPFBasicsIncludes"> </a>

除了 IP 位址，您也可以設定您的 SPF TXT 記錄，以包含為寄件者的網域。 這些被新增至的 SPF TXT 記錄做為 「 包含 」 陳述式。 例如，contoso.com 可能會想要包含所有來自 contoso.net 和 contoso.org 這也擁有的郵件伺服器的 IP 位址。 若要這麼做，contoso.com 會發佈的 SPF TXT 記錄看起來如下：
  
```
IN TXT "v=spf1 include:contoso.net include:contoso.org -all"
```

時接收伺服器會看到此記錄在 DNS 中，它也會執行 DNS 查閱 contoso.net 然後 contoso.org 的 SPF TXT 記錄上。如果找到其他包含陳述式內 contoso.net 或 contoso.org 的記錄，它會太遵循這些。 以協助防止阻斷服務攻擊，DNS 查閱且單一電子郵件的最大數目為 10。 每個包含陳述式代表其他 DNS 查閱。 如果郵件超過 10 個限制，郵件就會失敗 SPF。 一旦郵件達到此限制，接收伺服器的設定，根據寄件者可能會收到訊息，指出郵件產生 「 太多查閱 」 或 「 已超出最大躍點訊息 」 (其中情形時查閱循環及超越 DNS 逾時）。 如何避免此問題的秘訣，請參閱[疑難排解： Office 365 中 SPF 的最佳作法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。
  
## <a name="requirements-for-your-spf-txt-record-and-office-365"></a>您的 SPF TXT 記錄與 Office 365 的需求
<a name="SPFReqsinO365"> </a>

如果您會設定信箱，當您設定 Office 365，您已經建立做為合法您網域的郵件來源識別 Microsoft 郵件伺服器的 SPF TXT 記錄。 此記錄可能看起來像這樣：
  
```
v=spf1 include:spf.protection.outlook.com -all
```

如果您是完全託管 Office 365 客戶，也就是您沒有傳送輸出郵件的內部部署郵件伺服器，這是唯一的 SPF TXT 記錄，您需要發佈的 Office 365。
  
如果您有混合式部署 （亦即，您有一些信箱在內部和部分裝載於 Office 365），或如果您是 Exchange Online Protection (EOP) 獨立版客戶 （也就是您的組織使用 EOP 來保護您在內部部署信箱），您應該將輸出的 IP 位址的每一部內部邊緣郵件伺服器新增至 DNS 中的 SPF TXT 記錄。
  
## <a name="form-your-spf-txt-record-for-office-365"></a>Office 365 形成 SPF TXT 記錄
<a name="FormYourSPF"> </a>

使用本文中的語法資訊，以形成 SPF TXT 記錄的自訂網域。 雖然還有其他此處未提及，這些都是最常用的語法選項使用選項。 一旦您已形成記錄，您需要在網域註冊機構中更新記錄。
  
網域的相關的資訊您想要包含 for Office 365，請參閱[spf 所需的外部 DNS 記錄](https://support.office.com/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US)。 使用[逐步指示](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404)更新您的網域註冊機構 SPF (TXT) 記錄。 如果未列出您的註冊機構，您必須連絡這些分開，了解如何更新您的記錄。 
  
### <a name="spf-txt-record-syntax-for-office-365"></a>Office 365 的 SPF TXT 記錄語法
<a name="SPFSyntaxO365"> </a>

典型的 SPF TXT 記錄，Office 365 具有下列語法：
  
```
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

例如：
  
```
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

其中：
  
- **v = spf1**是必要。 這會定義 TXT 記錄做為 SPF TXT 記錄。 
    
- **ip4**指示您使用的 IP 版本 4 地址。 **ip6**指示您使用的 IP 版本 6 位址。 如果您使用 IPv6 位址，取代**ip4** **ip6**在本文中的範例。 您也可以指定使用 CIDR 表示法，例如**ip4:192.168.0.1/26**的 IP 位址範圍。
    
-  _IP 位址_是您想要加入的 SPF TXT 記錄的 IP 位址。 通常，這是您組織的外寄郵件伺服器的 IP 位址。 您可以列出多個輸出郵件伺服器。 如需詳細資訊，請參閱[範例： SPF TXT 記錄以多個輸出內部部署信箱伺服器和 Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)。
    
-  _網域名稱_是您想要新增為合法的寄件者的網域。 您應該包含 for Office 365 的網域名稱的清單，請參閱[spf 所需的外部 DNS 記錄](https://support.office.com/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US)。
    
- 強制執行規則通常是下列其中一項：
    
  - -all
    
    會指出完全未通過。 如果您知道所有授權的 IP 位址為您的網域，其清單中的 SPF TXT 記錄，並使用-all （完全未通過） 辨識符號。 此外，如果您只使用 SPF，也就是您不使用 DMARC 或 DKIM，您應該使用-all 辨識符號。 我們建議您一律使用此辨識符號。
    
  - ~ 所有
    
    會指出 fail。 如果您不確定您有 IP 位址的完整清單，則應該使用 ~ 所有 (fail) 辨識符號。 此外，如果您使用 DMARC p = 隔離或 p = 拒絕，則您可以使用 ~ 所有。 否則，使用-all。
    
  - ？ 所有
    
    會指出中性。 測試 SPF 時，會使用這項目。 我們不建議您實際部署中使用此辨識符號。
    
### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-office-365"></a>範例： SPF TXT 記錄時所要使用所有您的郵件會傳送由 Office 365
<a name="ExampleSPFNoSP"> </a>

如果您的郵件的所有傳送由 Office 365，請使用此 SPF TXT 記錄中：
  
```
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-office-365"></a>範例： SPF TXT 記錄以混合式案例中使用其中一個內部部署 Exchange Server 與 Office 365
<a name="ExampleSPFHybridOneExchangeServer"> </a>

在混合式環境中，如果您的內部部署 Exchange 伺服器的 IP 位址為 192.168.0.1，為了要設定以完全未通過 SPF 強制執行規則形成 SPF TXT 記錄，如下所示：
  
```
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-office-365"></a>範例： SPF TXT 記錄以多個輸出內部部署郵件伺服器和 Office 365
<a name="ExampleSPFMultipleMailServerO365"> </a>

如果您有多個輸出郵件伺服器，SPF TXT 記錄中包含的每部郵件伺服器的 IP 位址，並以後面加上空格分隔每個 IP 位址 」 ip4: 「 陳述式。 例如：
  
```
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-office-365"></a>後續步驟： 為 Office 365 設定 SPF
<a name="SPFNextSteps"> </a>

一旦您已成形 SPF TXT 記錄，請遵循中將它新增至您的網域[設定 spf 以協助防止詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)的步驟。 
  
雖然 SPF 設計來協助防止詐騙，但是有的詐騙技術該 SPF 無法防護。 為了防止這些項目，設定 SPF 之後，您也應該為 Office 365 設定 DKIM 和 DMARC。 若要開始使用，請參閱 [使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。 接下來，請參閱[使用 DMARC 來驗證 Office 365 電子郵件](use-dmarc-to-validate-email.md)。
  
## <a name="troubleshooting-best-practices-for-spf-in-office-365"></a>疑難排解： 的 SPF Office 365 中的最佳作法
<a name="SPFTroubleshoot"> </a>

您只可以建立一個 SPF TXT 記錄的自訂網域。 建立多筆記錄會導致循環配置資源這種狀況，而且 SPF 將會失敗。 若要避免此問題，您可以建立每個子網域的個別的記錄。 例如，建立一筆記錄，contoso.com 和 bulkmail.contoso.com 的另一筆記錄。
  
如果電子郵件訊息會造成超過 10 個 DNS 查閱且該郵件會傳遞之前，將永久性錯誤，也稱為_permerror_中，以回應接收的郵件伺服器，並造成失敗 SPF 檢查郵件。 接收伺服器也可能會以未傳遞回報 (NDR)，其中包含類似以下的錯誤回應：
  
- 郵件超過一個躍點計數。
    
- 訊息需要太多查閱。
    
## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-office-365"></a>當您使用協力廠商網域與 Office 365 時避免 「 太多查閱 」 錯誤
<a name="SPFTroubleshoot"> </a>

某些協力廠商網域的 SPF TXT 記錄會直接執行 DNS 查閱且大量接收伺服器。 例如，在撰寫本文時，Salesforce.com 包含 5 包含陳述式，其記錄中：
  
```
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

若要避免此錯誤，您可以實作任何人傳送大量電子郵件，例如，具有特別針對此目的使用子網域的原則。 然後，您會定義包含大量電子郵件的子網域不同 SPF TXT 記錄。
  
 在某些情況下，例如 salesforce.com 範例中，您必須使用的網域中您的 SPF TXT 記錄，但在其他情況下，協力廠商可能已經建立子網域進行您要用於此目的。 例如，exacttarget.com 建立子網域，您需要使用您的 SPF TXT 記錄： 
  
```
cust-spf.exacttarget.com
```

當您在您的 SPF TXT 記錄中包含協力廠商網域時，您需要確認與協力廠商的網域或子網域若要使用，避免執行到 10 個查閱限制。
  
## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a>如何檢視目前 SPF TXT 記錄，並判斷其所需要的查閱數目
<a name="SPFTroubleshoot"> </a>

您可以使用 nslookup 來檢視您的 DNS 記錄，包括您的 SPF TXT 記錄。 或者，如果您想要的話，有許多免費的線上工具提供可用來檢視您的 SPF TXT 記錄的內容。 透過查看您的 SPF TXT 記錄，並依照的鏈結包含陳述式及重新導向，您可以決定記錄需要多少 DNS 查閱。 某些線上工具將偶數計數，並為您顯示這些查閱。 追蹤的此數字，將有助於避免從觸發永久性錯誤，稱為 permerror，接收伺服器從組織傳送的郵件。
  
## <a name="for-more-information"></a>如需詳細資訊
<a name="SPFTroubleshoot"> </a>

需要協助新增 SPF TXT 記錄嗎？ 使用的更新在各種不同的受歡迎的網域註冊機構的 SPF (TXT) 記錄的[逐步指示](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404)。 [反垃圾郵件郵件標頭](anti-spam-message-headers.md)包含針對 SPF 檢查 Office 365 所使用的語法及標頭欄位。 
  

