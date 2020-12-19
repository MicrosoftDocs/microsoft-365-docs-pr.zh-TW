---
title: Microsoft 365 中的電子郵件加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: 比較 Microsoft 365 加密選項，包括 Office 365 郵件加密 (OME)、S/MIME、資訊版權管理 (IRM)，並了解傳輸層安全性 (TLS)。
ms.openlocfilehash: e1f222595479ce525b38ab97971c998f77c78581
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709577"
---
# <a name="email-encryption"></a>電子郵件加密

本文件會比較 Microsoft 365 中的加密選項，包括 Office 365 郵件加密 (OME)、S/MIME、資訊版權管理 (IRM)，並介紹傳輸層安全性 (TLS)。
  
Microsoft 365 提供多種加密選項，有助於滿足您對電子郵件安全性的商務需求。 本文提供在 Office 365 中加密電子郵件的三個方式。 如果您想要深入了解 Office 365 中的所有安全性功能，請瀏覽 [Office 365 信任中心](https://go.microsoft.com/fwlink/p/?LinkID=282470)。 本文介紹三種加密類型，可供 Microsoft 365 系統管理員用於協助保護 Office 365 中的電子郵件：
  
- Office 郵件加密 (OME)。

- 安全多用途網際網路郵件延伸 (S/MIME)。

- 資訊版權管理 (IRM)。

## <a name="how-microsoft-365-uses-email-encryption"></a>Microsoft 365 如何使用電子郵件加密

加密是將資訊編碼的程序，以便只有經過授權的收件者能解碼並使用資訊。 Microsoft 365 使用兩個方式來加密：在服務中，以及以自訂控制項的形式。 在服務中，Microsoft 365 會預設使用加密；您不需要進行任何設定。 例如，Microsoft 365 使用傳輸層安全性 (TLS) 來加密兩個伺服器間的連線或工作階段。 
  
電子郵件加密一般的運作方式如下：
  
- 郵件在寄件者的電腦上或是於傳輸時在中央伺服器上進行加密，從純文字轉換成無法讀取的加密文字。

- 郵件在傳輸過程中保持加密文字，萬一遭攔截可防止郵件被讀取。

- 一旦收件者收到郵件時，會以下列兩種方式之一將郵件轉換回可閱讀的純文字：

  - 收件者的電腦使用金鑰將郵件解密，或

  - 中央伺服器在驗證收件者的身分後，會代替收件者將郵件解密。

如需詳細了解 Microsoft 365 如何保護伺服器之間的通訊，例如 Microsoft 365 內的組織之間，或 Microsoft 365 與 Microsoft 365 外部受信任商業夥伴之間，請參閱 [Exchange Online 如何使用 TLS 保護 Office 365 中的電子郵件連線安全性](exchange-online-uses-tls-to-secure-email-connections.md)。
  
觀看此影片來取得 [Office 365 中的加密](https://www.youtube.com/watch?v=KmfxCd5ublI)簡介。
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>比較 Office 365 中提供的電子郵件加密選項

|電子郵件加密技術|![OME 的說明概念圖](../media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![IRM 的說明概念圖](../media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![SMIME 的說明概念圖](../media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|這是什麼？|Office 365 郵件加密 (OME) 是內建於 Azure 版權管理 (Azure RMS) 的服務，可讓您將加密的電子郵件傳送給組織內部或外部的人，無論目的地電子郵件地址為何 (Gmail、Yahoo! Mail、Outlook.com 等)。 <br/> 身為系統管理員，您可以設定用以定義加密條件的傳輸規則。 當使用者傳送的郵件符合某規則時，會自動套用加密。 <br/> 若要檢視加密的郵件，收件者可以取得單次密碼、登入 Microsoft 帳戶、或登入工作或學校相關聯的 Office 365 帳戶。 收件者也可以傳送加密的回覆。 他們不需要 Microsoft 365 訂閱，即可檢視加密的郵件或傳送加密的回覆。|IRM 是加密解決方案，也可對電子郵件套用使用限制。 這有助於防止敏感資訊被未經授權的人員列印、轉寄或複製。 <br/> Microsoft 365 中的 IRM 功能使用 Azure 版權管理 (Azure RMS)。|S/MIME 是一種憑證型加密解決方案，可讓您對郵件進行加密及數位簽署。 郵件加密有助於確保只有預定的收件者可以開啟並閱讀郵件。 數位簽章可協助收件者驗證寄件者的身分。 <br/> 數位簽章和郵件加密之所以可行，皆因為使用了唯一數位憑證，此憑證包含用於驗證數位簽章及加密或解密郵件的金鑰。 <br/> 若要使用 S/MIME，您必須記錄每位收件者的公開金鑰。 收件者必須維護自己的私密金鑰，並妥善保護。 如果收件者的私密金鑰受到危害，收件者必須取得新的私密金鑰，並轉發公開金鑰給所有可能的寄件者。|
|能做什麼？|OME： <br/> 將傳送給內部或外部收件者的郵件加密。 <br/>  可讓使用者將加密的郵件傳送至任何電子郵件地址，包括 Outlook.com、Yahoo! Mail 和 Gmail。 <br/>  可讓身為系統管理員的您自訂電子郵件檢視入口網站，以反映您組織的品牌。 <br/> Microsoft 安全地管理及儲存金鑰，因此您不需要勞心。 <br/> 只要加密的郵件可以在瀏覽器中開啟 (以 HTML 附件傳送)，就不需要任何特殊的用戶端軟體。|IRM： <br/> 利用加密和使用限制為電子郵件和附件提供線上和離線保護。 <br/> 可讓身為系統管理員的您能夠設定傳輸規則或 Outlook 保護規則，以自動將 IRM 套用至選取的郵件。 <br/> 可讓使用者以手動方式在 Outlook 或 Outlook 網頁版 (先前稱為 Outlook Web App) 中套用範本。|S/MIME 以數位簽章解決寄件者驗證，以加密解決郵件機密性。|
|不能做什麼？|OME 不允許您將使用限制套用至郵件。 例如，您無法使用它讓收件者停止轉寄或列印加密的郵件。|某些應用程式可能無法在所有裝置上支援 IRM 電子郵件。 如需這些應用程式和支援 IRM 電子郵件的其他產品的詳細資訊，請參閱[用戶端裝置功能](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities)。|S/MIME 不允許對加密的郵件掃描惡意程式碼、垃圾郵件或原則。|
|建議和範例案例|當您想要將機密商業資訊傳送給組織外部的人，無論他們是消費者或其他公司時，我們建議使用 OME。 例如：  <br/>  銀行員工將信用卡帳單傳送給客戶  <br/>  醫生的診所將醫療記錄傳送給病患  <br/>  律師將機密的法律資訊傳送給其他律師|當您想要套用使用限制以及加密時，我們建議使用 IRM。 例如：  <br/>  經理將新產品的機密詳細資訊傳送給組員時套用「不要轉寄」選項。  <br/>  行政人員需要與其他公司共用投標提案，其中一個附件是由使用 Office 365 的夥伴提供，並要求電子郵件和附件皆受到保護。|當您的組織或收件者的組織需要真正的端對端加密時，我們建議使用 S/MIME。  <br/>  S/MIME 最常用於下列情況：  <br/>  政府機構與其他政府機關通訊  <br/>  企業與政府機構通訊|
||

## <a name="what-encryption-options-are-available-for-my-microsoft-365-subscription"></a>我的 Microsoft 365 訂閱有哪些可用的加密選項？

如需您的 Microsoft 365 訂閱的電子郵件加密選項的詳細資訊，請參閱 [Exchange Online 服務說明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)。 您可以在這裡找到下列加密功能的相關資訊：
  
- Azure RMS，包括 IRM 功能和 OME

- S/MIME

- TLS

- 靜態資料的加密 (透過 BitLocker)

您也可以使用協力廠商的加密工具來搭配 Microsoft 365，例如 PGP (Pretty Good Privacy)。 Microsoft 365 不支援 PGP/MIME，而且您只能使用 PGP/內嵌來傳送及接收經過 PGP 加密的電子郵件。

## <a name="what-about-encryption-for-data-at-rest"></a>靜態資料的加密呢？

「靜態資料」指的是在傳輸中非作用中的資料。 在 Microsoft 365 中，電子郵件靜態資料的加密方式是 BitLocker 磁碟加密。 BitLocker 會加密 Microsoft 資料中心中的硬碟，以增強防護防止未經授權的存取。 若要深入了解，請參閱 [BitLocker 概觀](https://go.microsoft.com/fwlink/p/?LinkId=394737)。
  
## <a name="more-information-about-email-encryption-options"></a>電子郵件加密選項的相關資訊

如需本文中電子郵件加密選項以及 TLS 的詳細資訊，請參閱這些文件：
  
**OME**
  
[Office 365 郵件加密 (OME)](ome.md)
  
**IRM**
  
[Exchange Online 中的資訊版權管理](https://technet.microsoft.com/library/jj983436%28v=exchg.150%29.aspx)
  
[什麼是 Azure 版權管理？](https://technet.microsoft.com/library/jj585026)
  
**S/MIME**
  
[可用於訊息簽署和加密的 S/MIME](https://technet.microsoft.com/library/dn626158)
  
[了解 S/MIME](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[了解公開金鑰加密](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx)
  
**TLS**
  
[使用連接器設定自訂郵件流程](https://technet.microsoft.com/library/jj723138%28v=exchg.150%29.aspx)
