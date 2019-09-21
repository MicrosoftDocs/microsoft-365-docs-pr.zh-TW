---
title: 控制 Office 365 的輸出垃圾郵件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: 如果您的組織傳送大量的大宗郵件標示為垃圾郵件，可能會遭到封鎖無法傳送電子郵件與 Office 365。 閱讀本篇文章以深入了解發生的原因以及可以怎麼做其相關資訊。
ms.openlocfilehash: 09aa71cd8b273a3235bc2673d3d17c3decf71da5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078017"
---
# <a name="controlling-outbound-spam-in-office-365"></a>控制 Office 365 的輸出垃圾郵件

我們採取認真管理輸出垃圾郵件，因為我們的共用的服務。  有許多客戶背後的資源，其中一位客戶傳送輸出垃圾郵件，如果它可能會降低服務的輸出 IP 信譽，以及影響成功請務必遵循傳送的電子郵件的其他客戶共用集區。

> [!IMPORTANT]
> 當寄件者是受限制的通知現在是安全性 & 合規性中心 (SCC) 警示的平台的一部分。 而不是使用傳送通知給如下所述的方法，可以 」 限制使用者無法傳送電子郵件 」 警示中找到，提醒使用者的清單。 請開始使用安全性 & 合規性中心中的[警示原則] 頁面上](https://sip.protection.office.com/alertpolicies)設定警示，因為會在未來移除先前的方法。 了解新[受限的使用者體驗](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)的 」。

## <a name="what-admins-can-do-to-control-outbound-spam"></a>系統管理員可以怎麼做以控制輸出垃圾郵件

- **啟用帳戶會傳送垃圾郵件或關閉時的通知**。 系統管理員可以取得使用每當郵件已標示為 [輸出垃圾郵件，並透過高風險集區傳送。 藉由監視此信箱，系統管理員可以偵測如果他們在其網路中有洩漏的帳戶，或垃圾郵件篩選器會錯誤地標示他們的電子郵件為垃圾郵件。  設定輸出垃圾郵件原則的詳細資訊可以找到[以下](configure-the-outbound-spam-policy.md)。
 
- **以手動方式檢閱 3rd 廠商電子郵件提供者的垃圾郵件抱怨**。 有許多 3rd 廠商電子郵件服務如 Outlook.com、 Yahoo 和 AOL 提供意見反應迴圈： 如果其服務中的任何使用者將標記從我們的服務為垃圾郵件的電子郵件，郵件會封裝，且檢閱傳送給我們。 若要深入了解 Outlook.com 的寄件者支援，請按一下[這裡](https://sendersupport.olc.protection.outlook.com/pm/services.aspx)。

## <a name="what-eop-does-to-control-outbound-spam"></a>EOP 用途來控制輸出垃圾郵件 

1. **輸出傳輸至另一個集區的 Ip 的區隔**。 客戶傳送輸出透過服務每封郵件會掃描的垃圾郵件。 如果郵件是垃圾郵件，它會透過高風險傳遞集區路由傳送。 此 IP 集區包含無法傳遞狀態通知和垃圾郵件。 傳遞至預定的收件者不一定會為許多協力廠商不會接受電子郵件，因為它會發出的電子郵件的品質。

分割流量如此一來，可確保低品質電子郵件 （垃圾郵件，非法回應 Ndr） 不會不向一般的外寄電子郵件集區的信譽。 雖然這不是萬用高風險集區通常在許多接收器周圍網際網路，具有低信譽。 

2. **監視的 IP 信譽**。 Office 365 查詢各種 3rd 廠商 IP 封鎖清單中，並會產生提醒，如果我們輸出 Ip 的任何列於這些。 這可讓我們時垃圾郵件而造成降低我們信譽快速作出反應。 產生警示時，我們提供內部文件外圍要取得 delisted 採取哪些步驟。 

3. **停用的違規帳戶時傳送太多電子郵件標示為垃圾郵件**。 雖然我們隔離我們的垃圾郵件和非垃圾郵件到兩個個別輸出 IP 集區，電子郵件帳戶無法無限期地傳送垃圾郵件。 我們監視哪些帳戶會傳送垃圾郵件和它超過保密的限制，封鎖而無法傳送垃圾郵件的帳戶。

單一郵件標示為垃圾郵件可能是垃圾郵件引擎，也稱為誤判 misclassification。 我們將它傳送透過高風險集區，讓它的移出; 有機會不過，大量的簡短時間圖文框中的郵件表示問題及時，會發生，我們封鎖傳送任何更多的電子郵件帳戶。 有個別的電子郵件帳戶也如同整個租用戶的彙總存在於不同閾值。

4. **停用的違規的帳戶，在傳送太短時間內太多電子郵件時**。 除了上述的外觀比例標示為垃圾郵件的限制，也有時到達整體的限制，不論將郵件標示為垃圾郵件封鎖帳戶的限制。 此限制存在的原因是因為遭到入侵的帳戶無法傳送垃圾郵件篩選器未接的零時差垃圾郵件。 因為困難，如果不可能發生，有時分辨合法的大量散發郵件活動及大規模的垃圾郵件活動之間的差異，這些限制會啟動來限制任何可能造成的損害。

> [!NOTE]
> #3 和 #4，我們不通告的確切的限制。  這是防止濫發垃圾郵件者從遊戲系統，並確保，我們就可以變更的限制，當我們需要。 限制是損害的夠高，平均商務使用者永遠不會叫用它們和低，並且含有大部分的濫發垃圾郵件者可以執行。 

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a>想要傳送輸出大量的電子郵件透過 EOP 客戶的建議因應措施

很難將想要傳送大量電子郵件與服務防止遭入侵的帳戶和大量 emailers 不佳的清單取得作法與客戶之間的平衡。 同樣地，登陸 3rd 廠商封鎖清單上的輸出 IP 的成本是高於封鎖無法傳送輸出電子郵件客戶。 [Exchange Online 服務說明](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx#Receiving and sending limits)所述，使用 EOP 來傳送大量電子郵件並不支援使用的服務和只允許 「 最佳 」 為基礎。 針對想要傳送大量電子郵件的客戶，我們建議下列項目：

a. **傳送大量電子郵件透過它自己的內部部署郵件伺服器**。 這表示客戶必須維護自己的電子郵件基礎結構，這種類型的電子郵件。

b. **使用第 3 方大量 emailer 傳送大量的通訊**。 有幾個 3rd 廠商大量 emailers 很傳送大量電子郵件的唯一事業。 他們可以使用以確保它們有良好的電子方式，且他們具有專用於強制執行資源的客戶。 

通訊、 行動裝置，惡意程式碼反不當使用工作群組 (MAAWG) 會發佈其成員資格名冊[以下](http://www.maawg.org/about/roster)。 數個大量電子郵件提供者清單上，而是負責網際網路公民已知。 
  
## <a name="for-more-information"></a>如需詳細資訊

[當寄件者被封鎖無法傳送輸出垃圾郵件的範例通知](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[Office 365 電子郵件的反垃圾郵件保護](anti-spam-protection.md)

[Office 365 的反詐騙保護](anti-spoofing-protection.md)

[垃圾郵件信賴等級](spam-confidence-levels.md)
