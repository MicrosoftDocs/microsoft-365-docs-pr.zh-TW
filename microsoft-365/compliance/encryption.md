---
title: 加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365solution-mip
- m365initiative-compliance
description: 使用 Office 365，您的內容會在靜止時以最強的加密、通訊協定和技術進行加密。 深入瞭解 Office 365 中的加密。
ms.openlocfilehash: 28a5b55e63c3b66725aaa4a21e5dc750105c7c5a
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408593"
---
# <a name="encryption"></a>加密

加密是檔案保護和資訊保護原則的重要部分。 本文概要說明 Office 365 的加密。 取得加密工作的協助，例如如何設定組織的加密，以及如何以密碼保護 Office 檔。
  
- 如需 TLS 等憑證和技術的相關資訊，請參閱 [Office 365 中有關加密的技術參考詳細資料](technical-reference-details-about-encryption.md)。

- 如需如何設定或設定組織加密的相關資訊，請參閱 [在 Office 365 Enterprise 中設定加密](set-up-encryption.md)。

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>何謂加密，以及如何在 Office 365 中運作？

加密程式會將您的資料編碼 (稱為明文) 成密文。 不像純文字，使用者或電腦不能使用密文，除非解密密文，否則會解密。 解密需要只有授權使用者才能使用的加密金鑰。 加密可協助確保只有授權的收件者才能解密您的內容。 內容包含檔、電子郵件、行事曆專案等等。
  
加密本身不會妨礙內容攔截。 加密是組織較大的資訊保護原則的一部分。 使用加密，有助於確保只有授權的協力廠商可以使用加密的資料。
  
您可以同時有多個層級的加密。 例如，您可以加密電子郵件訊息，也可以加密透過電子郵件流向的通訊通道。 使用 Office 365，您的資料會在靜止時加密，而且會使用數種強大的加密通訊協定，以及包含傳輸層安全性/安全通訊端層 (的技術 TLS/SSL) 、網際網路通訊協定安全性 (IPSec) ，以及進階加密標準 (AES) 。
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>靜態資料的加密，以及傳輸中的資料

 **靜態資料的範例** 包括您已上傳至 SharePoint 文件庫的檔案、Project Online 資料、您已在商務用 Skype 會議中上傳的檔、您已儲存在信箱中資料夾中的電子郵件訊息和附件，以及您上傳至商務 OneDrive 的檔案。
  
 **傳輸中的資料範例** 包括正在傳遞的郵件訊息，或是線上會議中所發生的交談。 在 Office 365 中，每當使用者的裝置與 Microsoft 伺服器通訊時，或是當 Microsoft 伺服器與另一部伺服器通訊時，資料即會運送。
  
使用 Office 365 時，多個層和類型的加密可共同運作，以保護您的資料。 下表包含一些範例，並提供其他資訊的連結。
  
|**內容種類**|**加密技術**|**可深入了解的資源**|
|:-----|:-----|:-----|
|裝置上的檔案。 這些檔案可包含儲存于資料夾中的電子郵件、儲存在電腦上的 Office 檔、平板電腦或電話，或儲存至 Microsoft 雲端的資料。  <br/> |在 Microsoft 資料中心中 BitLocker。 您也可以在用戶端電腦上使用 BitLocker，例如 Windows 電腦和平板電腦  <br/> Microsoft 資料中心的分散式金鑰管理員 (DKM)   <br/> Microsoft 365 的客戶金鑰  <br/> |[Windows IT 中心： BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft 信任中心：加密](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [雲端安全性控制數列：加密靜態資料](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Exchange Online 如何保護您的電子郵件機密資料](exchange-online-secures-email-secrets.md) <br/> [使用客戶金鑰的服務加密](customer-key-overview.md) <br/> |
|使用者間傳輸的檔案。 這些檔案可包含使用者共用的 Office 檔或 SharePoint 清單專案。  <br/> |傳輸中的檔 TLS  <br/> |[商務用 OneDrive 和 SharePoint Online 中的資料加密](data-encryption-in-odb-and-spo.md) (英文) <br/> [商務用 Skype Online：安全性和封存](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|在收件者之間傳輸電子郵件。 這封電子郵件包含 Exchange Online 所主控的電子郵件。  <br/> |Office 365 郵件加密，包含 Azure Rights Management、S/MIME 和 TLS，以供傳輸電子郵件  <br/> |[Office 365 郵件加密 (OME)](ome.md) <br/> [Office 365 中的電子郵件加密](email-encryption.md) <br/> [Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|使用 Microsoft 團隊在收件者之間傳輸的研討、郵件和檔案。 <br/> |小組使用 TLS 和 MTLS 來加密立即訊息。 媒體流量已使用 Secure RTP (SRTP) 進行加密。 小組使用 FIPS (聯邦資訊處理標準) 相容演算法，以進行加密金鑰交換。 <br/> |[小組的加密](https://docs.microsoft.com/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>若要達到安全性和合規性需求，需要更多控制加密，該怎麼辦？

Microsoft 365 針對 Office 365 中的大量加密、檔加密和信箱加密，提供 Microsoft 管理的解決方案。 此外，Microsoft 還提供您可以管理和控制的加密解決方案。 這些加密解決方案是在 Azure 上建立。
  
若要深入了解，請參閱下列資源：
  
- [什麼是 Azure 版權管理？](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [在系統管理中心啟動 Rights Management](https://docs.microsoft.com/microsoft-365/enterprise/activate-rms-in-microsoft-365)

- [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)

- [Office 365 中的客戶金鑰服務加密](customer-key-overview.md)

- [Microsoft 365 的雙金鑰加密](double-key-encryption.md)

## <a name="how-do-i"></a>我如何...

|**若要執行這項工作**|**請參閱這些資源**|
|:-----|:-----|
|設定組織的加密  <br/> |[設定 Office 365 企業版中的加密](set-up-encryption.md) <br/> |
|查看憑證、技術和 TLS 密碼套件的詳細資料 <br/> |[加密的技術詳細資料](technical-reference-details-about-encryption.md) <br/> |
|在行動裝置上使用加密的郵件  <br/> |[在您的 Android 裝置上查看加密郵件](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [在 iPhone 或 iPad 上查看加密郵件](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|使用密碼保護加密檔  <br/><br/>  瀏覽器不支援密碼保護。 使用桌上出版的 Word、Excel 及 PowerPoint 以進行密碼保護。 |[新增或移除檔、活頁簿或簡報中的保護](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> 選擇 [ **新增保護** ] 區段，然後查看 [ **使用密碼加密**]。  |
|移除檔的加密  <br/> |[新增或移除檔、活頁簿或簡報中的保護](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> 選擇 [ **移除保護** ] 區段，然後參閱 [ **移除密碼加密**]。  |


## <a name="related-topics"></a>相關主題

[規劃 Microsoft 365 的安全性和資訊保護功能](plan-for-security-and-compliance.md)

[保護商務用 Microsoft 365 方案的十大方式](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data?view=o365-worldwide)

[Microsoft Stream 影片層級加密和播放流程](https://docs.microsoft.com/stream/network-overview#video-level-encryption-and-playback-flow)
