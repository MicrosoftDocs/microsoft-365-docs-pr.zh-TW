---
title: EOP 中的 ASF 設定
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解 Exchange Online Protection (EOP) 的反垃圾郵件原則中所提供的高級垃圾郵件篩選 (ASF) 設定。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0b6db02815f5b50d199e10685e2895a174997fd2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288678"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>EOP 中的高級垃圾郵件篩選 (ASF) 設定

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> 反垃圾郵件原則中目前可用的 ASF 設定為已被取代的處理常式。 建議您不要在反垃圾郵件原則中使用這些設定。 這些 ASF 設定的功能會併入篩選堆疊的其他部分。 如需詳細資訊，請參閱 [EOP 反垃圾郵件原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。

在所有 Microsoft 365 組織中，EOP 中的反垃圾郵件原則中的高級垃圾郵件篩選 (ASF) 設定可讓系統管理員將郵件標示為以特定郵件內容為基礎的垃圾郵件。 ASF 特別針對這些屬性，因為它們通常是在垃圾郵件中。 根據屬性，ASF 偵測會將郵件標記為 **垃圾** 郵件或 **高可信度垃圾郵件**。

> [!NOTE]
> 啟用一或多個 ASF 設定是一種積極的垃圾郵件篩選方法。 您無法將以 ASF 篩選的郵件報告為誤報。 您可以使用下列方法來識別透過 ASF 篩選的郵件：
>
> - 週期性的使用者垃圾郵件隔離通知。
>
> - 隔離中已篩選的郵件是否存在。
>
> - `X-CustomSpam:`如本文所述，新增至郵件的特定 X 標頭欄位。

下列各節說明安全性 & 合規性中心的反垃圾郵件原則中所提供的 ASF 設定和選項，以及 Exchange Online PowerShell 或獨立 EOP PowerShell ([New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) 和 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)) 。 如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

## <a name="enable-disable-or-test-asf-settings"></a>啟用、停用或測試 ASF 設定

針對每個 ASF 設定，反垃圾郵件原則中提供下列選項：

- **On**： ASF 會將對應的 X 標頭欄位新增至郵件，並將郵件標示為 **垃圾** 郵件 (scl 5 或6以 [提升垃圾郵件分數設定](#increase-spam-score-settings)) 或 **高信賴的垃圾郵件** (SCL 9 做為) 的 [垃圾郵件設定](#mark-as-spam-settings) 。

- **Off**： [ASF] 設定為 [已停用]。 此為預設值，建議您不要變更它。

- **Test**： ASF 會將對應的 X 標頭欄位新增到郵件中。 「 **測試模式選項** 」會判斷郵件會發生什麼變化 (*TestModeAction*) 值：

  - **無**：郵件傳遞不會受到 ASF 偵測的影響。 郵件仍受限於 EOP 中的其他篩選類型和規則。

  - **新增預設的 X 標頭文字 (*AddXHeader*)**：會將 X 標頭值 `X-CustomSpam: This message was filtered by the custom spam filter option` 新增至郵件。 您可以使用收件匣規則或郵件流程規則中的這個值 (也稱為傳輸規則) 會影響郵件的傳遞。

  - **傳送 Bcc 郵件 (*BccMessage*)**： TestModeBccToRecipients PowerShell 中 (*)* 參數值所指定的電子郵件地址會新增至郵件的 [密件副本] 欄位，而郵件會傳遞至其他的密件副本收件者。 在 [安全性 & 規範中心] 中，您可以使用分號 (; ) 分隔多個電子郵件地址。 在 PowerShell 中，您可以使用逗號來分隔多個電子郵件地址。

  **附註**：

  - 無法使用下列 ASF 設定的測試模式：

    - **條件式寄件者識別碼篩選： hard fail** (*MarkAsSpamFromAddressAuthFail*) 
    - **NDR 退信攻擊** (*MarkAsSpamNdrBackscatter*) 
    - **SPF 記錄： hard fail** (*MarkAsSpamSpfRecordHardFail*) 

  - [相同的測試模式] 動作會套用至 *所有* 設定為 **test** 的 ASF 設定。 您無法針對不同的 ASF 設定設定不同的測試模式動作。

## <a name="increase-spam-score-settings"></a>增加垃圾郵件分數設定

下列 ASF 設定會將所偵測郵件的垃圾郵件信賴等級設定 (SCL) 為5或6，這對應于 **垃圾** 郵件篩選判定和反垃圾郵件原則中的對應動作。

****

|反垃圾郵件原則設定|描述|新增 X 標頭|
|---|---|---|
|**遠端網站的影像連結** <p> *IncreaseScoreWithImageLinks*|包含 `<Img>` 遠端網站之 HTML 標籤連結的郵件 (例如，使用 HTTP) 會標示為垃圾郵件。|`X-CustomSpam: Image links to remote sites`|
|**URL 重新導向到其他埠** <p> *IncreaseScoreWithRedirectToOtherPort*|包含超連結的郵件會重新導向至 80 (HTTP) 、8080 (替代的 HTTP) 或 443 (HTTPS) 標示為垃圾郵件。|`X-CustomSpam: URL redirect to other port`|
|**URL 中的數位 IP 位址** <p> *IncreaseScoreWithNumericIps*|包含依數值 URLs 的郵件 (通常會將) 的 IP 位址標示為垃圾郵件。|`X-CustomSpam: Numeric IP in URL`|
|**.Biz 或. 資訊網站的 URL** <p> *IncreaseScoreWithBizOrInfoUrls*|`.biz`郵件內文包含或連結的郵件 `.info` 會標示為垃圾郵件。|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>標記為垃圾郵件設定

下列 ASF 設定會將偵測到的郵件的 SCL 設定為9，這會對應到 **高可信度垃圾郵件** 篩選判定和反垃圾郵件原則中的對應動作。

****

|反垃圾郵件原則設定|描述|新增 X 標頭|
|---|---|---|
|**空白郵件** <p> *MarkAsSpamEmptyMessages*|沒有主旨的郵件、郵件內文中沒有內容，而且沒有任何附件標示為高信賴的垃圾郵件。|`X-CustomSpam: Empty Message`|
|**HTML 中的 JavaScript 或 VBScript** <p> *MarkAsSpamJavaScriptInHtml*|使用 HTML 中 JavaScript 或 Visual Basic Script Edition 的郵件會標示為高信賴的垃圾郵件。 <p> 電子郵件訊息中使用這些指令碼語言，會自動發生特定動作。|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**HTML 中的框架或 IFrame 標記** <p> *MarkAsSpamFramesInHtml*|包含 `<frame>` 或 `<iframe>` HTML 標籤的郵件會標示為高信賴的垃圾郵件。 <p> 這些標記是用在電子郵件中，以格式化頁面以顯示文字或圖形。|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**HTML 中的物件標記** <p> *MarkAsSpamObjectTagsInHtml*|包含 `<object>` HTML 標籤的郵件會標示為高信賴的垃圾郵件。 <p> 這個標記可讓外掛程式或應用程式在 HTML 視窗中執行。|`X-CustomSpam: Object tag in html`|
|**HTML 中的嵌入標記** <p> *MarkAsSpamEmbedTagsInHtml*|包含 `<embed>` HTML 標籤的郵件會標示為高信賴的垃圾郵件。 <p> 這個標記可讓您在 HTML 檔案中嵌入不同種類的檔 (例如，聲音、影片或圖片) 。|`X-CustomSpam: Embed tag in html`|
|**HTML 中的表單標記** <p> *MarkAsSpamFormTagsInHtml*|包含 `<form>` HTML 標籤的郵件會標示為高信賴的垃圾郵件。 <p> 這個標記用來建立網站表單。 電子郵件廣告通常會包含此標記以徵求收件者的資訊。|`X-CustomSpam: Form tag in html`|
|**HTML 中的 Web 臭蟲** <p> *MarkAsSpamWebBugsInHtml*|*Web 臭蟲* (也稱為 *網頁信標*) 是一種圖形元素， (通常是一圖元的圖元) ，用來判斷郵件是否由收件者讀取。 <p> 包含 web 臭蟲的郵件會標示為高信賴的垃圾郵件。 <p> 合法的電子報可能會使用 web 臭蟲，不過許多人認為這是隱私權的侵犯。 |`X-CustomSpam: Web bug`|
|**套用機密的單字清單** <p> *MarkAsSpamSensitiveWordList*|Microsoft 會維護具有可能冒犯性郵件相關聯的動態但不可編輯的字清單。 <p> 包含在主旨或郵件內文中的機密單字清單中的字詞的郵件會標示為高信賴的垃圾郵件。|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF 記錄：硬性失敗** <p> *MarkAsSpamSpfRecordHardFail*|從 [SPF 寄件者原則] 框架中未指定之 IP 位址傳送的郵件，會將來源電子郵件網域的 DNS 中的「 (SPF) 記錄，標記為高信賴的垃圾郵件。 <p> 此設定無法使用測試模式。|`X-CustomSpam: SPF Record Fail`|
|**條件式寄件者識別碼篩選： hard fail** <p> *MarkAsSpamFromAddressAuthFail*|硬性失敗的郵件會將有條件的寄件者識別碼檢查標記為垃圾郵件。 <p> 此設定會結合使用寄件者識別碼檢查的 SPF 檢查，以協助防止包含偽造寄件者的郵件頭。 <p> 此設定無法使用測試模式。|`X-CustomSpam: SPF From Record Fail`|
|**NDR 退信攻擊** <p> *MarkAsSpamNdrBackscatter*|*退信攻擊* 無用的未傳遞回報 (也稱為 NDRs 或退回郵件) 由電子郵件中的偽造寄件者所造成。 如需詳細資訊，請參閱 [退信攻擊 messages AND EOP](backscatter-messages-and-eop.md)。 <p> 您不需要在下列環境中設定此設定，因為會傳遞合法的 NDRs，而退信攻擊會標示為垃圾郵件： <ul><li>使用 Exchange Online 信箱的 Microsoft 365 組織。</li><li>您透過 EOP 路由傳送 *輸出* 電子郵件的內部部署電子郵件組織。</li></ul> <p> 在會保護輸入電子郵件至內部部署信箱的獨立 EOP 環境中，開啟或關閉此設定的結果如下： <ul><li> **開啟**：已傳遞合法的 NDRs，並將退信攻擊標示為垃圾郵件。</li><li>**Off**：合法的 NDRs 和退信攻擊會透過一般垃圾郵件篩選。 大部分合法的 NDRs 都會傳遞給原始郵件寄件者。 部分（但非全部）退信攻擊會標示為高信賴的垃圾郵件。 根據定義，退信攻擊只能傳遞給欺騙寄件者，而不能傳遞給原始寄件者。</li></ul> <p> 此設定無法使用測試模式。|`X-CustomSpam: Backscatter NDR`|
|
