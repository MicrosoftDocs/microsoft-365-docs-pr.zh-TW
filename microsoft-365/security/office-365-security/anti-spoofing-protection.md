---
title: Office 365 的反詐騙保護
ms.author: tracyp
author: MSFTtracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: 本文說明 Office 365 如何減少使用偽造寄件者網域的網路釣魚攻擊，即詐騙網域。 其達成目的的方式是透過分析郵件，和封鎖無法使用標準電子郵件驗證方法或其他寄件者信譽技術來進行驗證的郵件。 採用此項變更是為了減少 Office 365 中的組織所暴露的網路釣魚攻擊數量。
ms.openlocfilehash: 1bcf6b954c69297981eafecef192cab0e55a7684
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2020
ms.locfileid: "41112737"
---
# <a name="anti-spoofing-protection-in-office-365"></a>Office 365 的反詐騙保護

本文說明 Office 365 如何減少使用偽造寄件者網域的網路釣魚攻擊，即詐騙網域。 其達成目的的方式是透過分析郵件，和封鎖無法使用標準電子郵件驗證方法或其他寄件者信譽技術來進行驗證的郵件。 採用此項變更是為了減少 Office 365 中的組織所暴露的網路釣魚攻擊數量。

本文也會說明進行此項變更的原因、客戶如何準備進行此變更、如何查看將受影響的郵件、如何回報郵件、如何緩解誤報情況，以及 Microsoft 的寄件人應如何預備此項變更。

Microsoft 的反詐騙技術最初部署在具有 Office 365 企業版 E5 訂閱，或已為其訂閱購買 Office 365 進階威脅防護 (ATP) 附加元件的組織中。 自 2018 年 10 月起，我們會將防護擴充至擁有 Exchange Online Protection (EOP) 的組織中。 此外，由於我們所有的篩選器皆會相互學習，所以 Outlook.com使用者也可能會受到影響。

## <a name="how-spoofing-is-used-in-phishing-attacks"></a>網路釣魚攻擊中的詐騙方式

為保護使用者，Microsoft 嚴正看待網路釣魚攻擊。 垃圾郵件製造者和網路釣魚者常用的技術之一就是詐騙，也就是偽造寄件者，讓郵件看起來源自非實際來源的其他人或其他地方。 這是設計來取得使用者認證的網路釣魚攻擊的慣用伎倆。 Microsoft 的反詐騙技術會特別檢查 [寄件者:標頭]，其會顯示在像 Outlook 這類的電子郵件用戶端中。 當 Microsoft 高度確信 [寄件者:標頭] 遭到偽造時，它會將該郵件標識為詐騙郵件。

詐騙郵件對實際使用者有兩個負面影響：

### <a name="1-spoofed-messages-deceive-users"></a>1. 詐騙郵件欺騙使用者

首先，詐騙郵件會誘騙使用者按下連結並給予其憑證，下載惡意程式碼或回覆具有敏感內容的郵件 (後者稱為商務電子郵件入侵)。 例如，以下是假冒寄件者為 msoutlook94@service.outlook.com 的網路釣魚郵件：

![冒充 service.outlook.com 的網路釣魚郵件](../media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)

上述郵件並不是真正從 service.outlook.com 寄出的郵件，而是網路釣魚者所偽造的郵件。 這封郵件試圖誘騙使用者按下郵件內的連結。

下個範例是假冒的 contoso.com：

![網路釣魚郵件 - 商務電子郵件入侵](../media/da15adaa-708b-4e73-8165-482fc9182090.jpg)

郵件看起來合法，但實際上卻是偽造的。 這封網路釣魚郵件是一種商務電子郵件入侵，也就是網路釣魚的子類別。

### <a name="2-users-confuse-real-messages-for-fake-ones"></a>2. 使用者無法分辨真假郵件

第二，詐騙郵件會讓使用者產生不確定感，他們知道什麼是網路釣魚郵件，但卻無法分辨真實郵件和詐騙郵件之間的差異。 例如，下列是來自 Microsoft 安全性帳戶電子郵件地址的實際密碼重設郵件範例：

![Microsoft 合法密碼重設](../media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)

上述郵件確實是來自 Microsoft，但使用者仍然還是會收到誘騙使用者按下連結並給予其憑證，下載惡意程式碼或回覆具有敏感內容的網路釣魚郵件。 因為分辨真實密碼重設郵件與假冒郵件有其難度，許多使用者會略過這些郵件、將它們回報為垃圾郵件或在不應該的情況下，將這些郵件回報給 Microsoft 為遺漏的網路釣魚詐騙。

為了阻止詐騙郵件，電子郵件篩選產業已開發出諸如 [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)、[DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email) 和 [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email) 等電子郵件驗證通訊協定。 DMARC 透過檢查郵件的寄件者來防止偽造。 也就是使用者在其電子郵件用戶端中看到的寄件者 (在以上範例中，它是 service.outlook.com、outlook.com 和 accountprotection.microsoft.com)。 此外，使用者也可以看到網域已通過 SPF 或 DKIM，這表示網域已驗證，因此不是偽造的。 如需完整討論內容，請參閱本文稍後的*了解為什麼電子郵件驗證不一定能夠阻止詐騙*一節。

不過，問題在於電子郵件驗證記錄並非強制必要的。 因此，雖然採用強式驗證原則的網域 (如 microsoft.com 和 skype.com) 可防止詐騙，但是發佈較弱的驗證原則、或甚至完全未採用任何原則的網域就成了詐騙目標。截至 2018 年 3 月，在財富雜誌前 500 大公司的網域中，只有 9% 發佈強式的電子郵件驗證原則。 剩下 91% 則可能受網路釣魚者的詐騙，且可能傳送郵件到使用者端來欺騙使用者，除非電子郵件篩選器使用另外的原則進行偵測：

![財富雜誌前 500 大公司採用的 DMARC 原則](../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

不在財富雜誌前 500 大中的中小型企業，有發佈強式電子郵件驗證原則的比例更少，且北美和西歐地區以外的網域具有強式電子郵件驗證原則的比例同樣很少。

這是個嚴重的問題，因為企業可能沒意識到電子郵件驗證的功用，但網路釣魚者卻瞭若指掌並利用這項缺口。

如需設定 SPF、DKIM 和 DMARC 的相關資訊，請參閱本文稍後的 *Office 365 的客戶*這一節。

## <a name="stopping-spoofing-with-implicit-email-authentication"></a>使用隱含的電子郵件驗證防止詐騙

因為網路釣魚和魚叉式網路釣魚這類問題的發生，以及強式電子郵件驗證原則的採用率有限，Microsoft 持續開發各項功能來保護客戶。 因此，Microsoft 已開始採用*隱含的電子郵件驗證*，如果網域未進行驗證，Microsoft 會將它視為它已發佈電子郵件驗證記錄，並在未通過時對其進行相應處理。

為此，Microsoft 為一般電子郵件驗證建置了大量擴充功能，包括寄件者信譽、寄件者/收件者歷史記錄、行為分析和其他先進技術。 傳送郵件的網域若未發佈電子郵件驗證，該郵件將被標示為詐騙郵件，除非郵件包含其他能指出其合法性的訊號。

如此一來，使用者就能確信他們所收到的電子郵件未遭到假冒，寄件者也能放心，沒有人會冒充他們的網域，而 Office 365 的客戶也能提供更完善的防護，如冒充防護。

若要查看 Microsoft 的一般公告，請參閱[網路釣魚的範圍第 2 部分 - Office 365 中增強的反詐騙保護](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)。

## <a name="identifying-that-a-message-is-classified-as-spoofed"></a>識別分類為詐騙郵件的郵件

### <a name="composite-authentication"></a>複合驗證

雖然 SPF、DKIM 和 DMARC 本身是很有幫助，但是如果郵件沒有明確驗證記錄，它們不會傳達足夠的驗證狀態。 因此，Microsoft 開發了一種演算法，將多個訊號組合成一個稱為「複合驗證」的單一值，或簡稱為 compauth。 系統會在 Office 365 客戶的郵件標頭的 *Authentication-Results* 標頭中，註記 compauth 值。

```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|**CompAuth 結果**|**描述**|
|:-----|:-----|
|失敗|郵件未通過明確驗證 (傳送網域明確地在 DNS 中發佈記錄) 或隱含驗證 (傳送網域未在 DNS 中發佈記錄，因此 Office 365 將結果內插為已發佈記錄)。|
|通過|郵寄通過明確驗證 (郵件通過 DMARC 或 [Best Guess Passed DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) 或信賴度高的隱含驗證 (傳送網域未發佈電子郵件驗證記錄，但 Office 365 具有強式後端訊號，指出郵件可能合法)。|
|softpass|郵件通過信賴度低到中的隱含驗證 (傳送網域未發佈電子郵件驗證，但 Office 365 具有後端訊號，指出郵件為合法，但訊號的強度較弱)。|
|無|郵件未進行驗證 (或有進行驗證，但不符合)，但因為寄件者信譽或其他因素而未套用複合驗證。|

|||
|:-----|:-----|
|**原因**|**描述**|
|0xx |郵件未通過複合驗證。<br/>**000** 表示郵件未通過 DMARC，並產生拒絕或隔離動作。  <br/>**001** 表示郵件未通過隱含電子郵件驗證。 這表示，傳送網域未發佈電子郵件驗證記錄，或是有發佈，但是擁有較弱的失敗原則 (SPF 非封鎖性失敗或中性，DMARC 原則為 p=none)。  <br/>**002** 代表組織擁有的寄件者/網域配對原則明確禁止傳送詐騙電子郵件，這項設定是由系統管理員手動設定。  <br/>**010** 表示郵件未通過 DMARC，並產生拒絕或隔離動作，而傳送網域是組織接受的其中一個網域 (為 self-to-self 或 intra-org, spoofing 的一部分)。|
|1xx、2xx、3xx、4xx 和 5xx|對應於不同內部代碼，說明為何郵件通過隱含驗證，或未進行驗證但卻未採取動作的原因。|
|6xx|表示郵件未通過隱含的電子郵件驗證，而傳送網域是組織接受的其中一個網域 (為自我詐騙，或稱為組織內部詐騙的一部分)。|

透過查看郵件標頭，系統管理員甚至使用者可以判斷 Office 365如何做出寄件者可能被假冒的結論。

### <a name="differentiating-between-different-types-of-spoofing"></a>區分不同類型的詐騙

Microsoft 將詐騙郵件區分為兩種類型：

#### <a name="intra-org-spoofing"></a>組織內部詐騙

也稱為自我詐騙，當寄件者地址中的網域與收件者網域相同或相符時 (當收件者網域是組織[接受的網域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)之一時)，就會發生這種情況；或者，當寄件者地址中的網域是同一組織的一部分時。

例如，下列寄件者和收件者來自相同網域 (contoso.com)。 在電子郵件地址間插入空格以防止垃圾郵件機器人從此網頁進行收集)：

> 寄件者: sender @ contoso.com <br/> 收件者: recipient @ contoso.com

下列寄件者和收件者網域與組織網域相符 (fabrikam.com)：

> 寄件者: sender @ foo.fabrikam.com <br/> 收件者: recipient @ bar.fabrikam.com

下列寄件者和收件者網域不同 (microsoft.com 和 bing.com)，但他們屬於同個組織 (也就是，他們同屬於組織接受的網域)：

> 寄件者: sender @ microsoft.com <br/> 收件者: recipient @ bing.com

未通過組織內部詐騙的郵件，其標頭包含下列值：

`X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11`

CAT 是郵件類別，一般會註記為 SPM (垃圾郵件)，但偶而會註記為 HSPM (信賴度高的垃圾郵件) 或 PHISH (網路釣魚)，係根據郵件內發現的其他模式類型而定。

SFTY 是郵件安全層級，第一個數字 (9) 表示郵件是網路釣魚，而點之後的第二組數字 (11) 表示其為組織內部詐騙。

尚未提供「複合驗證」特定的原因碼來表示組織內部詐騙，將於 2018 下半年加以註記 (時間表未定)。

#### <a name="cross-domain-spoofing"></a>跨網域詐騙

當收件者地址中的傳送網域是接收組織的外部網域時，就會發生這種情況。 因為跨網域詐騙在標頭會包含下列值，因此郵件未通過複合驗證：

`Authentication-Results: ... compauth=fail reason=000/001`

`X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22`

在這兩種情況下，郵件中會註記下列紅色安全提示，或依照收件者信箱語言自訂的相同提示：

![紅色安全提示 - 詐騙偵測](../media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)

透過查看收件者地址並了解收件者電子郵件的內容，或者透過檢查電子郵件標頭，您才能分辨內部組織詐騙和跨網域詐騙。

## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a>Office 365 客戶如何預備自己，以採用全新的反詐騙防護

### <a name="information-for-administrators"></a>適用於系統管理員的資訊

身為 Office 365 組織的系統管理員，您應該留意一些重要資訊。

### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>了解為什麼電子郵件驗證不一定能夠阻止詐騙

新的反詐騙防護依賴電子郵件驗證 (SPF、DKIM 和 DMARC) 不要將郵件標示為詐騙郵件。 常見的範例是，傳送網域永不發佈 SPF 記錄。 如果沒有 SPF 記錄，或未正確設定 SPF 記錄，已傳送的郵件會被標示為詐騙郵件，除非 Microsoft 的後端情報指出該郵件為合法。

例如，在部署反詐騙功能之前，郵件可能看起來會像下面一樣，沒有 SPF 記錄、沒有 DKIM 記錄，也沒有 DMARC記錄：

```text
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com;
From: sender @ fabrikam.com
To: receiver @ contoso.com
```

部署反詐騙功能之後，如果您有 Office 365 企業版 E5、EOP 或 ATP，則會加註 compauth 值：

```text
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: sender @ fabrikam.com
To: receiver @ contoso.com
```

如果 fabrikam.com 透過設定 SPF 記錄，但未設定 DKIM 記錄來修正此問題，郵件可能會通過複合驗證，因為通過 SPF 的網域與寄件者地址中的網域相符：

```text
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: sender @ fabrikam.com
To: receiver @ contoso.com
```

或者，如果設定了 DKIM 記錄，但未設定 SPF 記錄，郵件還是會通過複合驗證，因為通過 DKIM-Signature 的網域與寄件者地址中的網域相符：

```text
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: sender @ fabrikam.com
To: receiver @ contoso.com
```

不過，網路釣魚者也可能會設定 SPF 和 DKIM，並使用自己的網域來簽署郵件，但在寄件者地址中指定不同的網域。 SPF 或 DKIM 都未要求網域與寄件者地址中的網域相符，因此除非 fabrikam.com 發佈了 DMARC 記錄，否則使用 DMARC 不會將郵件標示為詐騙：

```text
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=fabrikam.com;
From: sender @ fabrikam.com
To: receiver @ contoso.com
```

在電子郵件用戶端 (Outlook、網頁版 Outlook 或任何其他電子郵件用戶端) 中，只會顯示寄件者網域，不會顯示 SPF 或 DKIM 中的網域，這可能會誤導使用者認為郵件是來自 fabrikam.com，但實際上郵件來自 maliciousDomain.com。

![郵件已通過驗證，但寄件者網域未與通過 SPF 或 DKIM 的網域相符](../media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)

為此，Office 365 要求寄件者地址中的網域與 SPF 或 DKIM 簽章中的網域相符，若未相符，則會包含某些其他內部訊號，來指出該郵件為合法郵件。 否則，郵件的 compauth 會失敗。

```text
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@fabrikam.com
```

因此，Office 365 反詐騙會阻止沒有驗證的網域、阻止設定驗證，但寄件者地址中的網域不相符的網域，因為這是使用者看到的網域並會相信這就是郵件的寄件者。 這在組織外部的網域，以及組織內的網域都是如此。

因此，如果您曾經收到未通過複合驗證的郵件被標示為詐騙郵件，即使郵件已通過 SPF 和 DKIM，這是因為通過 SPF 和 DKIM 的網域與寄件者地址中的網域不相符。

### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a>了解詐騙電子郵件處理方式的變化

目前，對於 Office 365 中的所有組織 - ATP 和非 ATP - 未通過 DMARC 的郵件若套用拒絕或隔離原則，將被標示為垃圾郵件，並且通常會採取信賴度高的垃圾郵件動作，有時候則採取一般垃圾郵件動作 (取決於是否有其他垃圾郵件規則首將它識別為垃圾郵件)。 組織內部詐騙偵測會採取一般垃圾郵件動作。 不需要啟用此行為，也不能停用此行為。

但是，對於跨網域詐騙郵件，在此變更之前，它們會經過一般垃圾郵件、網路釣魚和惡意程式碼檢查，如果篩選器的其他部分將其標示為可疑，則會將它們分別標記為垃圾郵件、網路釣魚或惡意程式碼。 透過新的跨網域詐騙防護，在預設情況下，任何無法通過驗證的郵件都將採取 [防網路釣魚] \> [反詐騙] 原則中定義的動作。 如果其中一項未定義，就會將郵件移到使用者的 [垃圾郵件] 資料夾。 在某些情況下，還會在較可疑的郵件上新增紅色安全提示。

這可能會導致之前標示為垃圾郵件的某些郵件仍被標示為垃圾郵件，但現在還會顯示紅色安全提示；在其他情況下，之前標示為非垃圾郵件的郵件將開始被標示垃圾郵件 (CAT:SPOOF)，並新增紅色安全提示。 在其他情況下，將所有垃圾郵件和網路釣魚郵件移到隔離區的客戶現在會看到這些郵件轉到 [垃圾郵件] 資料夾 (此行為可變更，請參閱[變更您的反詐騙設定](#changing-your-anti-spoofing-settings))。

假冒郵件有多種不同的方式 (請參閱本文稍早所述的的[區分不同類型的詐騙](#differentiating-between-different-types-of-spoofing))，但是截至 2018 年 3 月，Office 365 處理這些郵件的方式尚未統一。 下表快速摘要跨網域詐騙防護這個新行為：

|**詐騙類型**|**類別**|**是否新增安全提示？**|**適用對象**|
|:-----|:-----|:-----|:-----|
|DMARC 失敗 (隔離或拒絕)|HSPM (預設)，也可以是 SPM 或 PHSH|否 (還沒有)|所有 Office 365 客戶，Outlook.com|
|自我|SPM|是|所有 Office 365 組織，Outlook.com|
|跨網域|詐騙|是|Office 365 進階威脅防護 (ATP) 與 E5 客戶|

### <a name="changing-your-anti-spoofing-settings"></a>變更您的反詐騙設定

若要建立或更新 (跨網域) 反詐騙設定，請瀏覽至 [安全性與合規性中心] 中的 [威脅管理] \> [原則] 索引標籤下的 [防網路釣魚] \>[反詐騙] 設定。 如果您之前從未建立過任何防網路釣魚設定，您必須建立一個新：

![防網路釣魚 - 建立新原則](../media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)

如果您已建立，則可以加以選取來修改：

![防網路釣魚 - 修改現有原則](../media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)

選取您剛剛建立的原則，然後繼續進行[深入了解詐騙情報](learn-about-spoof-intelligence.md)中所述的步驟。

![啟用或停用反詐騙功能](../media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)

![啟用或停用反詐騙安全提示](../media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)

若要使用 PowerShell 建立新原則：

```powershell
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: The name should not exclude 64 characters, including spaces.
# If it does, you will need to pick a smaller name.
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy $name -RecipientDomainIs $domains
```

您可以使用 PowerShell 並遵照 [Set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy) 文件中的指示來修改防網路釣魚原則參數。 您可以指定 $name 做為參數：

```powershell
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

2018 年下半年，就不需要由您來建立預設原則，系統會為您建立一個涵蓋組織內所有收件者的原則，因此您就不需手動指定 (在最終實作前，以下螢幕擷取畫面有可能變更。)

![防網路釣魚的預設原則](../media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)

不同於您所建立的原則，您無法刪除預設原則、修改它的優先順序，或選擇要納入範圍的使用者、網域或群組。

![防網路釣魚預設原則的詳細資訊](../media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)

若要使用 PowerShell 設定預設的防護功能：

```powershell
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

只有當 Office 365 前面有另一台郵件伺服器或多台伺服器，您才應該停用反詐騙防護功能 (詳細資料，請參閱「停用反詐騙功能的合法案例」)。

```powershell
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false
```

> [!IMPORTANT]
> 如果電子郵件路徑中的第一躍點是 Office 365，且有太多合法電子郵件被標示為詐騙郵件，您應該先設定允許傳送詐騙電子郵件到您網域的寄件者 (請參閱本主題中的[管理傳送未經驗證電子郵件的合法寄件者](#managing-legitimate-senders-who-are-sending-unauthenticated-email) (英文) 一節)。 如果還是發生太多誤判 (也就是合法郵件被標示為詐騙郵件)，我們則不建議停用反詐騙防護功能。 但是，我們建議您選擇基本防護，不要選擇高度防護。 處理誤判總比將組織暴露在詐騙電子郵件下好，因為後者長期下來可能會耗費相當可觀的成本。

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a>管理傳送未經驗證電子郵件的合法寄件者

Office 365 會追蹤誰傳送未經驗證電子郵件到您的組織。 如果該服務認為寄件者不合法，則會標示為 *compauth* 失敗。 雖然需要根據郵件所套用的反詐騙原則，此郵件還是會分類為詐騙郵件。

不過，身為系統管理員，您可以指定可傳送詐騙電子郵件的寄件者，來覆寫 Office 365 決策。

#### <a name="method-1---if-your-organization-owns-the-domain-set-up-email-authentication"></a>方法 1 - 如果您的組織擁有該網域，請設定電子郵件驗證

在您擁有多個租用戶，或與多個租用戶互動的情況下，這個方法可用來解決組織內部詐騙和跨網域詐騙。 其也有助於解決跨網域詐騙，您在其中傳送郵件給 Office 365 內的客戶，以及主控於其他提供者的第三方。

如需詳細資訊，請參閱 [Office 365 的客戶](#customers-of-office-365)。

#### <a name="method-2---use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a>方法 2 - 使用詐騙情報來設定允許傳送未經驗證電子郵件的寄件者

您也可以使用[詐騙情報](learn-about-spoof-intelligence.md)來允許寄件者將未經驗證的郵件傳送至您的組織。

對外部網域來說，詐騙使用者是寄件者地址中的網域，而傳送基礎架構則是傳送 IP 位置 (分為 /24 CIDR 範圍) 或 PTR 記錄的組織網域 (在以下螢幕擷取畫面中，傳送 IP 可能是131.107.18.4，其 PTR 記錄是 outbound.mail.protection.outlook.com，這將顯示為傳送基礎架構的 outlook.com)。

若要允許此寄件者傳送未經驗證的電子郵件，請將 [否] **** 變更為 [是]****。

![設定反詐騙允許的寄件者](../media/d4334921-d820-4334-8217-788279701e94.jpg)

您也可以使用 PowerShell 以允許特定寄件者偽造您的網域：

```powershell
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![從 Powershell 設定冒名寄件者](../media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)

在上一個影像中，新增了額外的分行符號，讓這個螢幕擷取畫面顯示為最適大小。 一般來說，所有值會顯示在同一行。

編輯檔案並尋找對應至 outlook.com 和 bing.com 的行，並將 AllowedToSpoof 項目從 No 變更為 Yes：

![在 Powershell 中將 spoof allow 設定為 Yes](../media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)

儲存檔案，然後再執行：

```powershell
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

現在，這能讓 bing.com 從 \*.outlook.com 傳送未經驗證的電子郵件。

#### <a name="method-3---create-an-allow-entry-for-the-senderrecipient-pair"></a>方法 3 - 為寄件者/收件者配對建立允許項目

您也可以選擇略過篩選特定寄件者的所有垃圾郵件。 如需詳細資訊，請參閱[如何在 Office 365 中安全地將寄件者新增至允許清單](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/)。

如果您使用這個方法，將略過垃圾郵件和部分網路釣魚篩選，但不會略過惡意程式碼篩選。

#### <a name="method-4---contact-the-sender-and-ask-them-to-set-up-email-authentication"></a>方法 4 - 連絡寄件者，並要求他們設定電子郵件驗證

有鑑於垃圾郵件和網路釣魚問題，Microsoft 建議所有寄件者設定電子郵件驗證。 如果您知道傳送網域的系統管理員，請連絡他們來設定電子郵件驗證記錄，這樣您就不需要新增任何覆寫設定。 如需詳細資訊，請參閱本文稍後的[非 Office 365 客戶的網域系統管理員](#administrators-of-domains-that-are-not-office-365-customers)。

雖然一開始驗證傳送網域可能會有困難，但隨著時間過去，有越來越多的電子郵件篩選器開始篩選垃圾郵件或甚至拒絕他們的電子郵件，促使他們設定正確記錄以確保更佳的傳遞。

### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a>檢視報告，了解有多少郵件被標示為詐騙郵件

啟用反詐騙原則後，您就可以使用調查和應變功能來得知有多少郵件被標示為網路釣魚郵件。 若要這麼做，請移至安全性與合規性中心 (SCC)，在 [威脅管理] \> [總管] 下，將 [檢視] 設為 [網路釣魚]，並依 [寄件者網域] 或 [防護狀態] 來群組：

![檢視有多少郵件被標示為網路釣魚郵件](../media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)

您可以與各式各樣的報告互動，以查看有多少郵件被標示為網路釣魚郵件，包括被標示為 SPOOF 的郵件。 若要深入了解，請參閱[Office 365 威脅調查與應變快速入門](office-365-ti.md)。

由於詐騙與其他類型的網路釣魚不同 (一般網路釣魚，網域使用者冒充等)，您還無法拆分哪些郵件被標記。 不過，日後您將能透過安全性與合規性中心來完成。 之後，您就可以使用這份報告來辨別因為驗證失敗，導致可能合法但被卻標示為詐騙的傳送網域。

下列螢幕擷取畫面是此資料外觀的提議，但發行時可能有所變更：

![依據偵測類型檢視網路釣魚報告](../media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)

針對非 ATP 和 E5 的客戶，之後可在威脅防護狀態 (TPS) 報告下使用這些報告，但將延遲至少 24 個小時。 當這些客戶整合至安全性與合規性中心之後，這個頁面將會更新。

### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a>預測有多少郵件被標示為詐騙郵件

當 Office 365 更新其設定，讓您您關閉反詐騙強制措施後，或者啟用基本或高度強制措施，您將能夠查看在不同設定下郵件處置方式的變更。 也就是說，如果反詐騙功能原本是關閉的，當您改為基本，您能看到有多少郵件將被偵測為詐騙郵件；或者，如果原本是基本，當您改為高度時，您會看到是否有更多郵件會被偵測為詐騙郵件。

這項功能目前還在開發階段。 隨著更多詳細資料定義之後，此頁面將更新安全性與合規性中心的螢幕擷取畫面以及 PowerShell範例。

![啟用反詐騙的「模擬」報告](../media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)

![用於允許詐騙寄件者可能的 UX](../media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)

### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a>停用反詐騙功能的合法案例

反詐騙功能可提供客戶更堅強的防護，以免受網路釣魚攻擊，因此強烈建議您不要停用反詐騙防護功能。 停用後，您可能解決了短期的誤判狀況，但長期下來，您將暴露在更多風險之中。 在寄件人端設定驗證，或在網路釣魚原則中進行調整的成本通常是一次性事件或僅需要最少的定期維護。 但是，從資料洩露或資產受損的網路釣魚攻擊中恢復的成本，卻高得多。

基於這個原因，比起停用反詐騙防護功能，解決反詐騙誤判情況的益處更大。

但是，有一個合法案例反倒應該停用反詐騙功能，也就是在郵件路由中有其他郵件篩選產品，而且 Office 365 不是電子郵件路徑中的第一個躍點：

![客戶 MX 記錄並非指向 Office 365](../media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)

另一個伺服器可以是 Exchange 內部部署郵件伺服器、類似 Ironport 的郵件篩選裝置，或其他雲端託管服務。

如果收件人網域的 MX 記錄未指向 Office 365，則無需停用反詐騙功能，因為 Office 365 會查詢您的接收網域的 MX 記錄，並在其指向其他服務時禁止反詐騙功能。 如果您不知道網域中是否還有其他伺服器，則可以使用類似 MX Toolbox 的網站來查詢 MX 記錄。 它可能會顯示如下所示的結果：

![MX 記錄會指出網域未指向 Office 365](../media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)

這個網域擁有的 MX 記錄未指向 Office 365，因此 Office 365 不會套用反詐騙強制措施。

不過，如果您的收件者網域的 MX 記錄「未」** 指向 Office 365，即使 Office 365 前有其他服務，您也應該停用反詐騙功能。 最常見的範例是使用收件者重寫：

![收件者重寫的路由圖表](../media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)

網域 contoso.com 的 MX 記錄指向內部部署伺服器，而網域 @office365.contoso.net 的 MX 記錄指向 Office 365，因為其 MX 記錄中包含 \*.protection.outlook.com 或 \*.eo.outlook.com：

![MX 記錄指向 Office 365，因此可能是收件者重寫](../media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)

請務必區分收件人網域 MX 記錄何時未指向 Office 365，以及何時進行了收件人重寫。 請務必分辨出這兩種情況之間的差異。

如果您不確定您的接收網域是否已經過收件人重寫，有時您可以透過查看郵件標頭來判斷。

a) 首先，在 Authentication-Results 標頭中查看收件者網域的郵件標頭：

```text
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=fabrikam.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.fabrikam.com;
  office365.contoso.net; dmarc=none action=none
  header.from=fabrikam.com; compauth=fail reason=001
```

收件者網域為上面的粗體紅色字中，在本案例為 office365.contoso.net。 這可能會跟 To: 標頭中的收件者不同：

To: Example Recipient \<recipient @ contoso.com\>

針對實際的收件者網域執行 MX 記錄查詢。 如果其包含 \*.protection.outlook.com、mail.messaging.microsoft.com、\*.eo.outlook.com 或 mail.global.frontbridge.com，則表示 MX 指向 Office 365。

如果它不包含這些值，則表示 MX 未指向 Office 365。 您可以使用 MX Toolbox 這項工具來進行驗證。

對於此特定範例，以下內容表示contoso.com (從 To：標頭看起來像收件人網域) 具有指向內部部署伺服器的 MX 記錄點：

![MX 記錄指向內部部署伺服器](../media/2444144a-9a90-4319-96b2-d115041f669f.jpg)

不過，實際的收件者是 office365.contoso.net，其 MX 記錄確實指向 Office 365：

![MX 指向 Office 365，必須是收件者重寫](../media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)

因此，這封郵件可能經過收件者重寫。

b) 第二，請務必能分辨收件者重寫的常見使用案例。 如果您要收件者網域重寫為 \*.onmicrosoft.com，而非重寫為 \*.mail.onmicrosoft.com。

當您確定了在另一台伺服器後面路由的最終收件者網域，以及收件者網域的 MX 記錄確實指向 Office 365 (在其 DNS 記錄中發佈) 後，您就可以繼續停用反詐騙功能。

請記住，如果路由路徑中的網域的第一個躍點是 Office 365，請不要停用反詐騙功能，請只在 Office 365 位於一或多個服務後才停用。

### <a name="how-to-disable-anti-spoofing"></a>如何停用反詐騙功能

如果您已建立防網路釣魚原則，請將 *EnableAntispoofEnforcement* 參數設為 $false：

```powershell
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false
```

若您不知道要停用的原則 (或多個原則) 的名稱，可以予以顯示：

```powershell
Get-AntiphishPolicy | Format-List Name
```

如果您沒有任何現有的防網路釣魚原則，您可以建立一個然後再停用它 (即使您沒有原則，仍然會套用反詐騙功能；2018 下半年，系統將會為您建立一個預設原則讓您停用，而不需自行建立)。 完成此動作需進行多個步驟：

```powershell
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: If the name is more than 64 characters, you will need to choose a smaller one
```

```powershell
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy -RecipientDomainIs $domains
# Finally, scope the anti-phishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false
```

僅可透過 Cmdlet 停用反詐騙功能 (之後可在安全性與合規性中心中進行)。 如果您沒有 PowerShell 存取權，開立支援票證。

請記住，這應僅適用於傳送到 Office 365 時經過間接路由的網域。 請不要因為某些誤判的發生而停用反詐騙功能，從長遠看來，解決誤判所帶來的效益更好。

### <a name="information-for-individual-users"></a>適用個別使用者的資訊

個別使用者在與反詐騙安全提示的互動方式上會受到限制。 不過，為解決常見案例有幾件事是您可以做的。

### <a name="common-scenario-discussion-lists"></a>常見案例 - 討論清單

已知討論清單存在反詐騙問題，是因為它們轉寄郵件並修改郵件內容，但卻保留原始寄件者地址的方式。

例如，假設 Gabriela Laureano (glaureano @ contoso.com) 對賞鳥和加入 birdwatchers @ fabrikam.com 討論清單有興趣。 當她傳送郵件給討論清單時，其郵件看起來像這樣：

> **寄件者：** Gabriela Laureano \<glaureano @ contoso.com\> <br/> **收件者：** Birdwatcher's Discussion List \<birdwatchers @ fabrikam.com\> <br/> 
**主旨：** 本週雷尼爾山頂 觀賞藍鳥的絕佳景點 <br/><br/>有人這週想要上雷尼爾山 賞景嗎？

當電子郵件清單收到郵件時，他們會設定郵件格式、修改郵件內容，並將其重送給討論清單上的其餘成員，成員由來自許多不同電子郵件接收者的參與者組成。

> **寄件者：** Gabriela Laureano \<glaureano @ contoso.com\> <br/> **收件者：** Birdwatcher's Discussion List \<birdwatchers @ fabrikam.com\> <br/> **主旨：**[賞鳥人士] 本週雷尼爾山頂 觀賞藍鳥的絕佳景點 <br/><br/> 有人這週想要上雷尼爾山 賞景嗎？ <br/><br/> 此郵件已傳送給「賞鳥人士」討論清單。 您隨時可以取消訂閱。

在此範例中，重送的郵件具有相同的寄件者地址 (glaureano @ contoso.com)，但原始郵件在主旨列新增了標籤，以及在郵件底部新增頁腳而經過修改。 這種類郵件修改常見於郵寄清單中，且可能會導致誤判。

如果您或組織內部人員是郵寄清單的系統管理員，可以設定它略過反詐騙檢查。

- 請查看 DMARC.org 上的常見問題集：[我操作郵寄清單，並想要與 DMARC 互相操作，該怎麼做？](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)

- 閱讀此部落格文章的指示：[郵寄清單操作人員與 DMARC 互相操作以避免失敗的提示](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)

- 若考慮在郵寄清單伺服器上安裝更新以支援 ARC，請參閱 [https://arc-spec.org](https://arc-spec.org/)

如果您未擁有郵寄清單：

- 您可以要求郵件清單的維護者採用之前其中一個選項 (他們也應該為郵件清單重送的來源網域設定電子郵件驗證)。

- 您可以在電子郵件用戶端中建立信箱規則，將郵件移動至收件匣。 您也可以要求組織的系統管理員如同本主題中的[管理傳送未經驗證電子郵件的合法寄件者](#managing-legitimate-senders-who-are-sending-unauthenticated-email) (英文) 一節所討論，設定允許規則或覆寫規則。

- 您可以向 Office 365 開立支援票證，以建立郵寄清單的覆寫，將它視為合法。

### <a name="other-scenarios"></a>其他案例

1. 如果以上這兩個常見案例皆不適用於您的情況，請向 Microsoft 回報該郵件為誤判。 如需詳細資訊，請參閱本文章稍後的[如何向 Microsoft 回報垃圾郵件或非垃圾郵件？](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft)這一節。

2. 您也可以連絡您的電子郵件系統管理員，請他們向 Microsoft 開立支援票證。 Microsoft 工程小組會研究該郵件為何會被標示為詐騙郵件。

3. 此外，如果您知道誰是寄件者，並確定他們並非惡意詐騙，您可回覆寄件者，並指出他們從未經過驗證的伺服器傳送郵件。 當您這樣做時，有時原始寄件者會與設定必要電子郵件驗證記錄的 IT 系統管理員連絡。

   當有夠多寄件者回覆網域擁有者，他們應該設定電子郵件驗證記錄時，就可促使他們採取動作。 雖然 Microsoft 也會與網域擁有者合作發佈所需的記錄，但是當個別使用者提出要求時，助益更大。

4. 此外，還可以將寄件者加入安全寄件者清單。 但是請注意，如果網路釣魚者偽造帳戶，郵件就會傳送至您的信箱。 因此，請謹慎使用這個選項。

## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a>Microsoft 的寄件者應如何準備反詐騙防護功能

如果您是系統管理員，目前會將郵件傳送給 Microsoft，不論是傳送到 Office 365 或 Outlook.com，您應該確保您的電子郵件已正確經過驗證，否則它可能會被標示為垃圾郵件或網路釣魚郵件。

### <a name="customers-of-office-365"></a>Office 365 的客戶

如果您是 Office 365 客戶，而您使用 Office 365 來傳送外寄電子郵件：

- 針對您的網域，[在 Office 365 中設定 SPF 以防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- 針對主要網域，[在 Office 365 中使用 DKIM 以驗證從您的自訂網域傳送的外寄電子郵件](use-dkim-to-validate-outbound-email.md)

- [請考慮設定 DMARC 記錄](use-dmarc-to-validate-email.md)，讓網域能判斷誰是合法的寄件者

Microsoft 不會針對 SPF、DKIM 和 DMARC 提供詳細實作指南。 但是，網路上已發佈許多相關資訊。 也有協力廠商可專門協助您的組織設定電子郵件驗證記錄。

### <a name="administrators-of-domains-that-are-not-office-365-customers"></a>非 Office 365 客戶的網域系統管理員

如果您是網域系統管理員，但不是 Office 365 客戶：

- 您應該設定 SPF 來發佈網域的傳送 IP 位址，並一併設定 DKIM (若可用) 來數位簽署郵件。 您也可以考慮設定 DMARC 記錄。

- 如果有大量寄件者代表您發送電子郵件，您應該與他們想出一個傳送電子郵件的方式，讓寄件者地址 (如果它屬於您) 中的傳送網域與通過 SPF 或 DMARC 的網域相符。

- 如果您擁有內部部署郵件伺服器，或從軟體即服務提供者傳送郵件，或從 Microsoft Azure、GoDaddy、Rackspace、Amazon Web Services 這類的雲端託管服務傳送郵件，您應該確保將它們新增至您的 SP F記錄中。

- 如果您使用由 ISP 主控的小型網域，您應該根據 ISP 提供給您的指示設定 SPF 記錄。 多數 ISP 都會提供這類指示，也可以在該公司的支援頁面上找到。

- 即使您之前從未發佈過電子郵件驗證，郵件系統也運作的十分良好，您仍應發佈電子郵件驗證記錄，以傳送至 Microsoft。 這麼做可以幫助防止網路釣魚，並降低您或您的收件方組織收到網路釣魚郵件的機會。

### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a>如果您不知道誰以您的網域傳送電子郵件，該怎麼辦？

許多網域不發佈 SPF 記錄的原因是他們不認識所有寄件者。 沒關係，您並不需要認識所有寄件者。 您反倒應該先發佈您知道的寄件者的 SPF 記錄，特別是公司流量所在位置，並發佈中性 SPF 原則，`?all`：

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

中性 SPF 原則表示從公司基礎架構傳送的任何電子郵件都將通過所有其他電子郵件接收者的電子郵件驗證。 來自您不認識的寄件者人的電子郵件將回歸中性，這幾乎與根本不發佈 SPF 記錄相同。

傳送到 Office 365 時，來自公司流量的電子郵件將被標示為已經過驗證，但來自您不知道的來源的電子郵件仍可能被標示為詐騙郵件 (取決於 Office 365 是否可以針對它進行隱含驗證)。 但是，比起所有電子郵件都被 Office 365 標示為詐騙郵件，這不失為一項改進。

當您開始使用具有 ?all 後援原則的 SPF 記錄後，您可以逐漸納入越來越多的傳送基礎結構，然後發佈更嚴格的原則。

### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a>如果您是郵寄清單擁有者，該怎麼辦？

請參閱本主題之前的[常見案例：討論清單](#common-scenario-discussion-lists) (英文) 一節。

### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a>如果您是網際網路服務提供者 (ISP)、電子郵件服務提供者 (ESP) 或雲端主控服務等基礎結構提供者，該怎麼辦？

如果您主控網域的電子郵件，且該網域用來傳送電子郵件，或提供可傳送電子郵件的主控基礎結構，您應該執行下列動作：

- 確定您的客戶擁有詳細說明如何發佈 SPF 記錄的文件

- 即使客戶未明確設定 (使用預設網域登入)，仍考慮在外寄電子郵件中簽署 DKIM 簽章。 您甚至可以使用 DKIM 簽章對電子郵件進行雙重簽署 (如果已經設定了客戶的網域，則為第一次，第二次使用您公司的 DKIM簽章)

即使您對來自您的平台的電子郵件進行驗證，也無法保證Microsoft 的可傳遞性，但至少可保證 Microsoft 不會因為郵件未經過驗證，而將它列為垃圾郵件。 如需 Outlook.com 如何篩選電子郵件的詳細資料，請參閱[Outlook.com Postmaster 頁面](https://postmaster.live.com/pm/postmaster.aspx)。

如需服務提供者最佳作法的詳細資訊，請參閱[適用服務提供者的 M3AAWG 行動傳訊最佳做法](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)。

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="why-is-microsoft-making-this-change"></a>Microsoft 為何要進行這項變更？

由於網路釣魚攻擊的影響，以及電子郵件驗證已存在超過 15 年，因此 Microsoft 認為若繼續允許未經驗證的電子郵件，其中的風險高於遺失合法電子郵件的風險。

### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a>這項變更會造成合法的電子郵件被標示為垃圾郵件嗎？

一開始會有一些郵件被標示為垃圾郵件。 但是，一段時間後，寄件者將進行調整，然後對於大多數電子郵件路徑，錯誤標示詐騙的郵件數量可以忽略不計。

在將這項功能部署到其他客戶之前的幾週，Microsoft 本身先行採用了此功能。 一開始會出現一些干擾，但慢慢的會減少。

### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a>Microsoft 是否會將此功能提供給 Office 365 的 Outlook.com 和非進階威脅防護客戶？

Microsoft 的反詐騙技術最初部署在具有 Office 365 企業版 E5 訂閱，或已為其訂閱購買 Office 365 進階威脅防護 (ATP) 附加元件的組織中。 自 2018 年 10 月起，我們已將防護擴充至擁有 Exchange Online Protection (EOP) 的組織中。 未來，我們可能會發佈給 Outlook.com 使用。 但是，如果我們這樣做，可能會有一些功能不適用，例如報告和自訂覆寫。

### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>如何向 Microsoft 回報垃圾郵件或非垃圾郵件？

您可以使用 [Outlook 的回報郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)，如果未安裝 Outlook，則可[將垃圾郵件，非垃圾郵件和網路釣魚詐騙郵件提交給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。

### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a>我是網域系統管理員，但我不認識所有寄件者！

請參閱[非 Office 365 客戶的網域系統管理員](#administrators-of-domains-that-are-not-office-365-customers)。

### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a>如果我為組織停用反詐騙防護會發生什麼情況，即使 Office 365 是我的主要篩選器？

我們不建議這樣做，因為您將會暴露在更多未篩選出的網路釣魚及垃圾郵件中。 並非所有的網路釣魚都是詐騙，也不是所有詐騙郵件都會遺漏。 不過，比起啟用反詐騙功能的客戶，您的風險較高。

### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>啟用反詐騙防護表示我都不會收到任何網路釣魚郵件嗎？

很抱歉，不是這樣，因為網路釣魚者會因應使用其他技術，例如入侵帳戶或設定免費服務的帳戶。 但是，防網路釣魚防護在偵測這些其他類型的網路釣魚方法上效果更好，因為 Office 365 的保護層是設計成能相互配合運作，並環環相扣。

### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a>其他大型的電子郵件接收者會封鎖未經驗證的電子郵件嗎？

幾乎所有的大型的電子郵件接收者都採用傳統的 SPF、DKIM 和 DMARC。 有些接收者會進行比這些標準更嚴格的其他檢查，但很少會像Office 365 一樣能阻止未經驗證的電子郵件並將其視為詐騙郵件。 不過，因為網路釣魚的問題，大部分產業對於這類特殊電子郵件的控制越來越嚴格。

### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a>如果已啟用反詐騙功能，是否仍需要為「SPF 驗證失敗」啟用進階垃圾郵件篩選選項？

不用，因為反詐騙功能不僅會考慮SPF 驗證失敗，還會考慮更廣泛的標準，所以不需再使用此選項。 如果同時啟用反詐騙功能和 SPF 驗證失敗選項，則可能會發生更多誤判。 我們建議您停用這項功能，因為它幾乎不會增加垃圾郵件或網路釣魚郵件的捕獲率，反而會產生更多誤判。

### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a>寄件者重寫機制 (SRS) 是否有助於修復轉寄的電子郵件？

SRS 僅能修正轉寄電子郵件的部分問題。 透過重寫 SMTP MAIL FROM，SRS可以確保轉寄郵件能在下一個目的地通過 SPF。 但是，由於反詐騙功能會根據寄件者地址以及 MAIL FROM 或 DKIM 簽署網域 (或其他訊號)，因此不足以防止轉寄的電子郵件被標示為詐騙郵件。
