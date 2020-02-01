---
title: 抵禦傳送至 Office 365 的垃圾郵件
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5fd7d05b-96db-456f-81d6-1ac0e5bff530
ms.collection:
- M365-security-compliance
description: Microsoft 的電子郵件安全性藍圖包括不相符的跨產品方法。 Exchange Online Protection (EOP) 反垃圾郵件和防網路釣魚篩選技術已套用至使用者提供的最新反垃圾郵件和防網路釣魚的工具和整個網路的創新 Microsoft 的電子郵件平台上。 EOP 的目標是要提供一種完整且可使用的電子郵件服務，可協助您偵測並防止使用者的垃圾郵件、 詐騙電子郵件威脅 （網路釣魚） 和惡意程式碼。
ms.openlocfilehash: 888df6224007471db46b669ac4ffe33983057115
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599320"
---
# <a name="fighting-junk-email-sent-to-office-365"></a>抵禦傳送至 Office 365 的垃圾郵件

Microsoft 的電子郵件安全性藍圖包括不相符的跨產品方法。 Exchange Online Protection (EOP) 反垃圾郵件和防網路釣魚篩選技術已套用至使用者提供的最新反垃圾郵件和防網路釣魚的工具和整個網路的創新 Microsoft 的電子郵件平台上。 EOP 的目標是要提供一種完整且可使用的電子郵件服務，可協助您偵測並防止使用者的垃圾郵件、 詐騙電子郵件威脅 （網路釣魚） 和惡意程式碼。
  
## <a name="the-challenge"></a>挑戰

電子郵件已成為重要通訊工具，而不只是讓取用上月、 支援人員、 銷售的組織中，和所有規模的企業。 如已增加至電子郵件的使用，因此有電子郵件不當使用。 不受監控的垃圾郵件可以午前收件匣和網路、 影響使用者滿意度，以及阻礙合法電子郵件通訊的有效性。 這就是為什麼 Microsoft 繼續投入反垃圾郵件技術。 簡言之，它會啟動包含和篩選垃圾電子郵件。 
  
## <a name="our-efforts"></a>我們努力

EOP 提供一些步驟來減少垃圾郵件對我們的使用者的電子郵件經驗的負面影響。
  
### <a name="exchange-online-protection-technology"></a>Exchange Online Protection 技術

若要協助減少垃圾郵件，EOP 會包含垃圾郵件保護使用專屬 EOP 篩選技術來識別和隔開合法電子郵件的垃圾郵件的畫面電子郵件。 EOP 內容篩選器可學習已知的垃圾郵件和網路釣魚威脅和使用者的意見反應我們消費者平台、 Outlook.com。 這些資料型別的協助訓練 EOP 技術來辨識合法電子郵件及垃圾郵件，以及是到寄件者信譽的按鍵輸入。 進行中使用者的意見反應 EOP 中的垃圾郵件分類程式可協助確保 EOP 技術會持續經過訓練的及改善。
  
#### <a name="how-does-eop-work"></a>EOP 的運作方式？

當外部使用者將電子郵件訊息傳送至 EOP 使用者時，EOP 篩選技術評估郵件的內容，並將分級指派給郵件根據郵件是垃圾郵件的可能性。 此分級會儲存為郵件的內容，稱為內訊息本身垃圾郵件信賴等級 (SCL)。 它是傳送到 EOP 內其他反垃圾郵件保護層的 SCL 分級會保留郵件。 
  
EOP 內的規則設定為處理不同 SCL 分級的電子郵件訊息。 如果郵件的 SCL 分級高於特定的閾值，它會被視為垃圾郵件。 將隔離的郵件，或傳遞至使用者的垃圾郵件資料夾根據系統管理員如何設定垃圾郵件傳遞選項。
  
#### <a name="eop-filters"></a>EOP 篩選

反垃圾郵件篩選的技術，除了 EOP 也可讓系統管理員設定篩選層級，以進一步自訂電子郵件傳遞至其使用者帳戶。 系統管理員可以輕易地寄件者或網域名稱新增至 [安全寄件者和網域清單，讓來自該寄件者或網域的電子郵件永遠不會被視為垃圾郵件，不論郵件的內容。 如需資訊，請參閱[安全寄件者和封鎖的寄件者會列出在 Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)。
  
### <a name="phishing-protection"></a>網路釣魚保護

網路釣魚 （讀成"釣魚 」） 是一種身分識別竊取和其中一個網際網路上的最快問世威脅。 要求個人或財務資訊或包含連結至網站來要求這類資訊時，您通常可以識別網路釣魚郵件。 EOP 提供網路釣魚保護功能的專屬的 EOP 篩選的技術的一部分。 EOP 篩選技術分析來幫助偵測詐騙連結或來協助保護使用者免受這些類型的線上詐騙詐騙的網域的電子郵件。
  
#### <a name="how-does-phishing-protection-work"></a>網路釣魚保護的運作方式？

通常的網路釣魚電子郵件會傳送含有連結，一次點選連結將使用者重新導向至詐騙網站出現有效 （例如您金融機構或線上服務）。 此網路釣魚網站通常會提示使用者輸入使用者名稱、 密碼和身分證號碼等的個人資訊。 您輸入網路釣魚網站的任何資訊可協助 phisher 竊取您的身分識別。 藉由使用已知受信任的品牌名稱及標誌，網路釣客便能夠看起來像是合法。 網路釣魚篩選技術提供在 EOP 檢查有潛在網路釣魚電子郵件的特性。 如果找到，電子郵件移至 [垃圾郵件] 資料夾。
  
Microsoft 會將重點放其反網路釣魚技術努力在兩個店面： 先依協助防止網路釣魚電子郵件無法送達我們的使用者和第二個協助以消除使用者正在 deceived 冒名的電子郵件和網站的可能性。 
  
> [!TIP]
> Internet Explorer 版本 7 及更將封鎖或警告使用者，當使用者造訪已知或潛在的網路釣魚網站，讓它們不誘騙提供個人資訊。[請確定您有最新版本的 Internet Explorer](https://www.microsoft.com/windows/ie/default.mspx)。 
  
#### <a name="authentication"></a>驗證

網域詐騙是一種模仿合法電子郵件地址進行尋找合法的詐騙電子郵件。 詐騙用於惡意的個人或組織中網路釣魚詐騙誘人員 divulging 機密個人資訊。 識別竊取和其他類型詐騙的可能會導致這類資訊的揭露。
  
EOP 會使用寄件者保護架構 (SPF)、 DomainKeys Identified Mail (DKIM) 和網域型郵件驗證、 報告和符合性聲明 (DMARC) 和其他隱含驗證來驗證郵件是來自聲稱來自該網域. 建議的所有寄件者使用 SPF 和 DKIM 來保護其收件者從垃圾郵件和網路釣魚詐騙。 建議的寄件者，請考慮發佈 DMARC 來拒絕或隔離來自未經授權寄件者傳送的郵件。
  
- 若要深入了解關於 SPF 的詳細資訊，請參閱[RFC 7208](https://tools.ietf.org/html/rfc7208)和[寄件者原則架構](https://www.openspf.org/)。
    
- 若要深入了解 DKIM，請參閱[RFC 6376](https://tools.ietf.org/html/rfc6376)和[DKIM.org](https://dkim.org/)。
    
- 若要深入了解 DMARC，請參閱[DMARC.org](https://dmarc.org/)。
    
### <a name="legislation"></a>法規

在 Microsoft，我們相信開發的新技術和自我規定需要有效的政府原則及法律架構的支援。 全球垃圾郵件激增具有刺激許多立法內文的郵件來調整商業電子郵件。 許多國家/地區現在有垃圾郵件對抗法律就地。 美國聯邦與州法律管理垃圾郵件，而且此互補的方法，協助來減少垃圾郵件的無縫隙至繁榮的合法電子商務。 可以垃圾郵件動作會展開供 curbing 詐騙和詐騙電子郵件的工具。
  

