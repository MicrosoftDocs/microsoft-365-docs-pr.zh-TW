---
title: Office 365 中的 ASF 設定
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
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解反垃圾郵件原則中的高級垃圾郵件篩選（ASF）設定，可讓系統管理員識別郵件，其中包含垃圾郵件中經常使用的特定郵件屬性。
ms.openlocfilehash: 31793f5996cc27cf7e5de75d9c190657e6592c57
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034130"
---
# <a name="advanced-spam-filter-asf-settings-in-office-365"></a>Office 365 中的高級垃圾郵件篩選器（ASF）設定

> [!NOTE]
> 反垃圾郵件原則中目前可用的 ASF 設定為已被取代的處理常式。 建議您不要在反垃圾郵件原則中使用這些設定。 這些 ASF 設定的功能會併入篩選堆疊的其他部分。 如需詳細資訊，請參閱[EOP 反垃圾郵件原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。

反垃圾郵件原則（也稱為垃圾郵件篩選原則或內容篩選原則）中的高級垃圾郵件篩選（ASF）設定可讓系統管理員將郵件標示為以特定郵件內容為基礎的垃圾郵件。 ASF 特別針對這些屬性，因為它們通常是在垃圾郵件中。 根據屬性，ASF 偵測會將郵件標記為**垃圾**郵件或**高可信度垃圾郵件**。

> [!NOTE]
> 啟用一或多個 ASF 設定是一種積極的垃圾郵件篩選方法。 您無法將以 ASF 篩選的郵件報告為誤報。 您可以使用下列方法來識別透過 ASF 篩選的郵件： <ul><li>週期性的使用者垃圾郵件隔離通知。</li><li>隔離中已篩選的郵件是否存在。</li><li>如本`X-CustomSpam:`主題所述，新增至郵件的特定 X 標頭欄位。</li></ul>

下列各節說明安全性 & 合規性中心的反垃圾郵件原則，以及 Exchange Online PowerShell 或獨立 Exchange Online Protection PowerShell （[New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterpolicy)及[Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)）中可用的 ASF 設定和選項。 如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

## <a name="enable-disable-or-test-asf-settings"></a>啟用、停用或測試 ASF 設定

針對每個 ASF 設定，反垃圾郵件原則中提供下列選項：

- **On**： ASF 會將對應的 X 標頭欄位新增至郵件，並將郵件標示為**垃圾**郵件（[提高垃圾郵件分數設定](#increase-spam-score-settings)的 Scl 5 或6）或**高信賴的垃圾郵件**（將[標記為垃圾郵件設定](#mark-as-spam-settings)的 scl 9）。

- **Off**： [ASF] 設定為 [已停用]。 此為預設值，建議您不要變更它。

- **Test**： ASF 會將對應的 X 標頭欄位新增到郵件中。 「**測試模式選項**」（*TestModeAction*）值會決定郵件所發生的情況：

  - **None**：郵件路由和傳遞不會受到 ASF 偵測的影響。 郵件仍受限於 EOP 中的其他篩選類型和規則。

  - **新增預設的 X 標頭文字（*AddXHeader*）**： x 標頭值`X-CustomSpam: This message was filtered by the custom spam filter option`會新增至郵件。 您可以在收件匣規則或郵件流程規則（也稱為傳輸規則）中使用此值，以影響郵件的路由和傳遞。

  - **傳送 Bcc 郵件（*BccMessage*）**：指定的電子郵件地址（PowerShell 中的*TestModeBccToRecipients*參數值）會新增至郵件的 [密件副本] 欄位，郵件會傳遞至 [密件副本收件者]。 在安全性 & 合規性中心，您可以使用分號（;）分隔多個電子郵件地址。 在 PowerShell 中，您可以使用逗號來分隔多個電子郵件地址。

  **附註**：

  - 無法使用下列 ASF 設定的測試模式：

    - **條件式寄件者識別碼篩選： hard fail** （*MarkAsSpamFromAddressAuthFail*）

    - **NDR 退信攻擊**（*MarkAsSpamNdrBackscatter*）

    - **SPF 記錄： hard fail** （*MarkAsSpamSpfRecordHardFail*）

  - [相同的測試模式] 動作會套用至*所有*設定為**test**的 ASF 設定。 您無法針對不同的 ASF 設定設定不同的測試模式動作。

## <a name="increase-spam-score-settings"></a>增加垃圾郵件分數設定

下列 ASF 設定會將偵測到郵件的垃圾郵件信賴等級（SCL）設定為5或6，這對應于**垃圾**郵件篩選器判定和反垃圾郵件原則中的對應動作。

||||
|:-----|:-----|:-----|
|**反垃圾郵件原則設定**|**描述**|**新增 X 標頭**|
|**遠端網站的影像連結** <br/><br/> *IncreaseScoreWithImageLinks*|包含`<Img>`遠端網站之 HTML 標籤連結（例如，使用 HTTP）的郵件會標示為垃圾郵件。|`X-CustomSpam: Image links to remote sites`|
|**URL 重新導向到其他埠** <br/><br/> *IncreaseScoreWithRedirectToOtherPort*|包含超連結的郵件，該超連結會重新導向到80（HTTP）以外的 TCP 埠、8080（備用 HTTP）或443（HTTPS）標記為垃圾郵件。|`X-CustomSpam: URL redirect to other port`|
|**URL 中的數位 IP 位址** <br/><br/> *IncreaseScoreWithNumericIps*|包含以數位為基礎的 URLs （通常為 IP 位址）的郵件會標示為垃圾郵件。|`X-CustomSpam: Numeric IP in URL`|
|**.Biz 或. 資訊網站的 URL** <br/><br/> *IncreaseScoreWithBizOrInfoUrls*|郵件內文中包含 .biz 或. info 連結的郵件會標示為垃圾郵件。|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>標記為垃圾郵件設定

下列 ASF 設定會將偵測到的郵件的 SCL 設定為9，這會對應到**高可信度垃圾郵件**篩選判定和反垃圾郵件原則中的對應動作。

||||
|:-----|:-----|:-----|
|**反垃圾郵件原則設定**|**描述**|**新增 X 標頭**|
|**空白郵件** <br/><br/> *MarkAsSpamEmptyMessages*|沒有主旨的郵件、郵件內文中沒有內容，而且沒有任何附件標示為高信賴的垃圾郵件。|`X-CustomSpam: Empty Message`|
|**HTML 中的 JavaScript 或 VBScript** <br/><br/> *MarkAsSpamJavaScriptInHtml*|使用 HTML 中 JavaScript 或 Visual Basic Script Edition 的郵件會標示為高信賴的垃圾郵件。 <br/><br/> 電子郵件訊息中使用這些指令碼語言，會自動發生特定動作。|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**HTML 中的框架或 IFrame 標記** <br><br/> *MarkAsSpamFramesInHtml*|包含`<frame>`或`<iframe>` HTML 標籤的郵件會標示為高信賴的垃圾郵件。 <br/><br/> 這些標記是用在電子郵件中，以格式化頁面以顯示文字或圖形。|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**HTML 中的物件標記** <br><br/> *MarkAsSpamObjectTagsInHtml*|包含`<object>` HTML 標籤的郵件會標示為高信賴的垃圾郵件。 <br/><br/> 這個標記可讓外掛程式或應用程式在 HTML 視窗中執行。|`X-CustomSpam: Object tag in html`|
|**HTML 中的嵌入標記** <br><br/> *MarkAsSpamEmbedTagsInHtml*|包含`<embed>` HTML 標籤的郵件會標示為高信賴的垃圾郵件。 <br/><br/> 這個標記可讓您在 HTML 檔案中嵌入不同類型的檔，例如聲音、影片或圖片。|`X-CustomSpam: Embed tag in html`|
|**HTML 中的表單標記** <br><br/> *MarkAsSpamFormTagsInHtml*|包含`<form>` HTML 標籤的郵件會標示為高信賴的垃圾郵件。 <br/><br/> 這個標記用來建立網站表單。 電子郵件廣告通常會包含此標記以徵求收件者的資訊。|`X-CustomSpam: Form tag in html`|
|**HTML 中的 Web 臭蟲** <br><br/> *MarkAsSpamWebBugsInHtml*|*Web 臭蟲*（也稱為*web 信標*）是一種圖形元素（通常是一圖元 x 一個圖元），用來判斷郵件是否已讀取。 <br/><br/> 包含 web 臭蟲的郵件會標示為高信賴的垃圾郵件。 <br/><br/> 合法的電子報可能會使用 web 臭蟲，不過許多人認為這是隱私權的侵犯。 |`X-CustomSpam: Web bug`|
|**套用機密的單字清單** <br><br/> *MarkAsSpamSensitiveWordList*|Microsoft 會維護具有可能冒犯性郵件相關聯的動態但不可編輯的字清單。 <br/><br/> 包含在主旨或郵件內文中的機密單字清單中的字詞的郵件會標示為高信賴的垃圾郵件。|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF 記錄：硬性失敗** <br><br/> *MarkAsSpamSpfRecordHardFail*|從來源電子郵件網域之 DNS 中的 SPF 寄件者原則架構（SPF）記錄中未指定的 IP 位址所傳送的郵件，會標示為高信賴的垃圾郵件。 <br/><br/> 此設定無法使用測試模式。|`X-CustomSpam: SPF Record Fail`|
|**條件式寄件者識別碼篩選： hard fail** <br><br/> *MarkAsSpamFromAddressAuthFail*|硬性失敗的郵件會將有條件的寄件者識別碼檢查標記為垃圾郵件。 <br/><br/> 此設定會結合使用寄件者識別碼檢查的 SPF 檢查，以協助防止包含偽造寄件者的郵件頭。 <br/><br/> 此設定無法使用測試模式。|`X-CustomSpam: SPF From Record Fail`|
|**NDR 退信攻擊** <br><br/> *MarkAsSpamNdrBackscatter*|*退信攻擊*是由電子郵件中的偽造寄件者所造成的無用未傳遞回報（也稱為 NDRs 或退回的郵件）。 如需詳細資訊，請參閱[退信攻擊 messages AND EOP](backscatter-messages-and-eop.md)。 <br/><br/> 您不需要在下列環境中設定此設定，因為會傳遞合法的 NDRs，而退信攻擊會標示為垃圾郵件： <ul><li>使用 Exchange Online 信箱的 Microsoft 365 組織。</li><li>您透過 EOP 路由傳送*輸出*電子郵件的內部部署電子郵件組織。</li></ul><br/> 在會保護輸入電子郵件至內部部署信箱的獨立 EOP 環境中，開啟或關閉此設定的結果如下： <ul><li> **開啟**：已傳遞合法的 NDRs，並將退信攻擊標示為垃圾郵件。</li><li>**Off**：合法的 NDRs 和退信攻擊會透過一般垃圾郵件篩選。 大部分合法的 NDRs 都會傳遞給原始郵件寄件者。 部分（但非全部）退信攻擊會標示為高信賴的垃圾郵件。 根據定義，退信攻擊只能傳遞給欺騙寄件者，而不能傳遞給原始寄件者。</li></ul><br/> 此設定無法使用測試模式。|`X-CustomSpam: Backscatter NDR`|
|
