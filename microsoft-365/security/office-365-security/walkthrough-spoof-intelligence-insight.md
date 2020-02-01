---
title: 欺騙情報探索的演練
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/30/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 請參閱 < 新的詐騙智慧深入了解的運作方式。
ms.openlocfilehash: 38bf75a2ebeabd41aace42c6116d37ecbe28a2de
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598010"
---
# <a name="walkthrough-spoof-intelligence-insight"></a>逐步解說： 詐騙智慧深入解析

藉由使用詐騙智慧深入見解，您可以快速地判斷哪一個寄件者合法傳送未驗證電子郵件。 藉由允許他們傳送冒名的郵件，您可以降低風險的任何誤判移至您的使用者。
  
此外，您也可以使用詐騙智慧監視及管理允許的網域-配對，以提供額外的安全性層級，並防止不安全的郵件抵達您組織中。
  
您可以使用詐騙智慧深入了解安全性&amp;合規性中心，如果您的公司或學校帳戶具有 Office 365 全域系統管理員、 安全性系統管理員或安全性讀取權限。 如需詳細資訊，請參閱[中 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md)。
  
如果您是初次使用[報表和深入了解 Office 365 安全性&amp;合規性中心](reports-and-insights-in-security-and-compliance.md)，它可能會說明若要查看如何您可以輕鬆地瀏覽從儀表板到深入見解和建議的動作。
  
您可以檢視從多個儀表板詐騙智慧深入了解安全性&amp;合規性中心。 不論您正在尋找在哪一個儀表板，深入了解提供相同的詳細資訊，並可讓您快速地執行相同工作。
  
這是下列其中一個安全性的幾個逐步解說&amp;合規性中心。 若要瀏覽報表和深入資訊，請參閱 [相關的主題] 區段中的逐步解說。
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a>易於存取安全性詐騙智慧深入見解&amp;合規性中心

1. 若要開始，您將需要[移至安全性&amp;合規性中心](../../compliance/go-to-the-securitycompliance-center.md)。
    
2. 安全性&amp;合規性中心，移至**威脅管理** \> **儀表板。**
    
3. 在 [**深入了解**] 列中，尋找詐騙智慧深入解析。 如果您已啟用詐騙智慧，然後深入解析為授權**Spoofed 網域，在過去 30 天的驗證失敗**。 如果您未啟用詐騙保護，然後深入了解會提示您若要這麼做所使用的標題**啟用詐騙保護**。 
    
## <a name="about-the-insight-on-the-dashboard"></a>關於儀表板上深入解析

深入了解儀表板上的會顯示如下的資訊。
  
![詐騙智慧深入了解的螢幕擷取畫面](../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
此深入了解有兩種模式：
  
 **深入了解模式**。 如果您有啟用任何詐騙原則，然後深入了解顯示多少郵件已由我們詐騙智慧功能影響過去 30 天。 
  
 **如果模式**。 如果您沒有任何已啟用的詐騙原則，然後深入了解顯示多少留言可能*會*有已受到我們詐騙智慧功能過去 30 天。 
  
無論如何，深入了解中顯示的詐騙的網域分成兩個類別;可疑網域配對和非可疑網域配對。 這些類別會進一步細分為三個不同的 bucket，供您檢閱。 
  
*網域配對*是組合 」 從: 「 地址和傳送基礎結構。 
  
- 「 從 」 地址是由您的郵件應用程式顯示自地址的地址。 此地址可識別電子郵件的作者。 也就是負責撰寫郵件的使用者或系統信箱。 這有時稱為 5322.From 地址。
    
- 傳送基礎結構或寄件者是組織網域的傳送端 IP 位址的 PTR 記錄。 如果傳送 IP 位址不有任何的 PTR 記錄，則寄件者會用來識別所傳送的 IP 255.255.255.0 CIDR 標記法的子網路遮罩 （/ 24）。 例如，如果 IP 位址是 192.168.100.100 完成 IP 位址的寄件者則 192.168.100.100/24。
    
 **可疑網域組**包括： 
  
- **高信賴度詐騙**。 Office 365 收到強式訊號這些網域所可疑，根據歷史傳送模式和網域信譽分數。 Office 365 是高度以內的網域詐騙並從這些網域傳送的訊息是較不可能是合法。 
    
- **中度信賴詐騙**。 Office 365 收到中等訊號這些網域所可疑，根據歷史傳送模式和網域信譽分數。 Office 365 是普通以內的網域詐騙和是合法的寄件者這些網域的郵件。 此 bucket 有更多機會包含 false positive (Fp) 比高信賴度詐騙 bucket。 
    
 **非可疑網域組**包括**人詐騙**。 救回的詐騙都有失敗的明確的驗證檢查 ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing)， [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、 [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email))，但傳遞我們延伸的驗證檢查的網域。 由於此，Office 365 人代替您郵件和反詐騙採取任何動作已在郵件上。 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>檢視從詐騙智慧深入了解可疑網域組的詳細的資訊

1. 詐騙智慧深入見解，在按一下任何網域組 （高、 中或救回）。
  
**詐騙智慧深入了解**頁面隨即出現顯示未經驗證的郵件傳送到組織的寄件者的清單。 在此頁面上的資訊可協助您判斷是否與否，會獲授權冒名的郵件，或如果您需要採取進一步的動作。 您可以排序資訊訊息計數，偵測上次到詐騙，日期等等。 （按一下欄標題，例如**郵件計數**或**最後一次看到**，例如）。 
    
2. 表格，開啟包含相關的網域組豐富資訊的詳細資料] 窗格中選取項目，包括為什麼我們攔截這，您需要做些什麼，網域摘要、 WhoIs 有關寄件者和我們討論過寄件者相同租用戶中的類似電子郵件。 從這裡開始，您也可以選擇新增或移除**AllowedToSpoof**安全寄件者清單中的網域組。 
  
![詐騙智慧深入了解詳細資料窗格中的網域的螢幕擷取畫面](../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>新增或移除 AllowedToSpoof 安全寄件者清單中的網域

您新增或移除 AllowedToSpoof 安全寄件者清單中的網域，同時檢閱詳細資料窗格中的網域組的詐騙智慧深入解析。 只要據此設定將開關切換。
  
這會修改唯一的網域配對結合詐騙的網域與傳送基礎結構，而不提供涵蓋範圍整個詐騙的網域或隔離中的傳送基礎結構。 例如，如果您將下列網域組新增至 'AllowedToSpoof' 寄件者允許清單：*詐騙網域*」 gmail.com 」 和*傳送基礎結構*」 tms *。 mx.com 」，* 然後只從該網域配對的郵件仍可詐騙。 其他的寄件者嘗試詐騙 」 gmail.com 」 與 「 tms.mx.com 」 嘗試詐騙會繼續受保護的詐騙智慧其他網域。 
  
## <a name="related-topics"></a>相關主題

[深入了解詐騙情報](learn-about-spoof-intelligence.md)
  
[Office 365 的反詐騙保護](anti-spoofing-protection.md)
  
[逐步解說 - 從儀表板到深入解析](from-a-dashboard-to-an-insight.md)
  
[逐步解說 - 從詳細報告到深入解析](from-a-detailed-report-to-an-insight.md)
  
[逐步解說 - 從深入解析到詳細報告](from-an-insight-to-a-detailed-report.md)
  

