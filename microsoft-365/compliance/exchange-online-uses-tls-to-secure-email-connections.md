---
title: Exchange Online 如何使用 TLS 保護電子郵件連線
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 瞭解 Exchange Online 和 Microsoft 365 如何使用 Transport Layer Security (TLS) 及轉寄保密 (FS) ，以確保電子郵件通訊的安全。 此外，也可取得 Microsoft 所發行之憑證的相關資訊，以供 Exchange Online 使用。
ms.openlocfilehash: cc7ca631f9322fdc8a85cfaba197e63d06d08aee
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906949"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>Exchange Online 如何使用 TLS 保護電子郵件連線

瞭解 Exchange Online 和 Microsoft 365 如何使用 Transport Layer Security (TLS) 及轉寄保密 (FS) ，以確保電子郵件通訊的安全。 也提供 Microsoft 所發行之憑證的相關資訊，以供 Exchange Online 使用。
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>Microsoft 365 和 Exchange Online 的 TLS 基礎

TLS 之前的傳輸層安全性 (TLS) 和 SSL 是密碼編譯通訊協定，該協定使用安全性憑證來加密電腦之間的連線以保護透過網路進行的通訊。 TLS 取代了安全通訊端層 (SSL)，且往往被稱為 SSL 3.1。 針對 Exchange Online，我們使用 TLS 來加密 Exchange 伺服器之間的連線，以及 Exchange 伺服器與其他伺服器之間的連線，例如您的內部部署 Exchange 伺服器或收件者的郵件伺服器。 一旦連線經過加密，所有透過該連線傳送的資料將會透過加密通道傳送。 不過，若轉寄透過 TLS 加密連線所傳送的郵件，該郵件則不一定會加密。 這是因為在簡單的字詞中，TLS 不會加密郵件，只是連接。
  
如果您想要加密郵件，便需要使用能加密郵件內容的加密技術，如 Office 郵件加密之類的技術。如需 Office 365 郵件加密選項的相關資訊，請參閱 [Email encryption in Office 365](email-encryption.md) 及 [Office 365 Message Encryption (OME)](ome.md)。 
  
當您想要在 Microsoft 與您的內部部署組織或其他組織（例如合作夥伴）之間設定安全通道時，建議使用 TLS。 Exchange Online 一律會先嘗試使用 TLS 來保護您的電子郵件，但如果另一方沒有提供 TLS 安全性，則無法一律如此進行。 繼續閱讀若要瞭解如何使用  *連接器* 將所有郵件安全傳送至內部部署伺服器或重要的合作夥伴。 

若要為我們的客戶提供一流的加密，Microsoft 已棄用 (TLS) 版本1.0 和1.1 的傳輸層安全性[Office 365](tls-1.0-and-1.1-deprecation-for-office-365.md)和[Office 365 GCC](tls-1-2-in-office-365-gcc.md)。 不過，您可以繼續使用未加密的 SMTP 連線，而不需要任何 TLS。 建議您不要在未加密的情況下進行電子郵件傳輸。  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Exchange Online 如何在 Exchange Online 客戶之間使用 TLS

Exchange Online 伺服器一律會使用 TLS 1.2 加密連往資料中心內其他 Exchange Online 伺服器的連線。 當您將郵件傳送給組織內的收件者時，會透過使用 TLS 加密的連線來傳送郵件。 此外，您傳送給其他客戶的所有電子郵件，都會透過使用 TLS 加密的連線來傳送，並使用轉寄機密加以保護。
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>Microsoft 365 如何在 Microsoft 365 與外部信任的合作夥伴之間使用 TLS

根據預設，Exchange Online 一律會使用「隨機 TLS」。 這表示 Exchange Online 一律會先嘗試使用最安全的 TLS 版本加密連線，如果無法成功，便在 TLS 加密清單中尋找下一順位的版本，直到找到雙方都能同意的版本。 除非您已設定 Exchange Online，以確保傳送給該收件者的郵件只會透過安全連線來傳送，否則如果收件者組織不支援 TLS 加密，郵件將會以未加密的方式傳送。 隨機 TLS 對大多數企業而言已足夠。 不過，針對具備法規遵從性需求（例如醫療、銀行或政府組織）的企業，您可以設定 Exchange Online 以要求（或強制） TLS。 如需相關指示，請參閱[使用 Office 365 中的連接器設定郵件流程](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。
  
如果您決定在所屬組織與信任的合作夥伴組織之間設定 TLS，Exchange Online 可以使用「強制 TLS」建立信任的通訊通道。 強制 TLS 會要求合作夥伴組織必須使用安全性憑證向 Exchange Online 進行驗證，才能傳送郵件給您。 您的合作夥伴必須管理自己的憑證，才能執行此動作。 在 Exchange Online 中，我們使用連接器來保護您在收件者的電子郵件提供者到達之前，您從未經授權的存取中傳送的郵件。 如需使用連接器來設定郵件流程的詳細資訊，請參閱[使用 Office 365 中的連接器設定郵件流程](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS 和混合 Exchange Server 部署

如果您正在管理混合式 Exchange 部署，您的內部部署 Exchange 伺服器必須使用安全性憑證 Microsoft 365 進行驗證，才能將郵件傳送給其信箱只在 Office 365 中的收件者。 因此，您必須為內部部署 Exchange 伺服器管理自己的安全性憑證。 您也必須安全地儲存和維護這些伺服器憑證。 如需在混合式部署中管理憑證的詳細資訊，請參閱 [混合部署的憑證需求](/exchange/certificate-requirements)。
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>如何在 Office 365 中設定 Exchange Online 的強制 TLS

Exchange Online 客戶若想要使用強制 TLS 保護所有傳送和接收的電子郵件，需要設定多個需要 TLS 的連接器。 一個連接器用於傳送給使用者信箱的電子郵件，另一個連接器用於從使用者信箱寄出的電子郵件。 請在 Office 365 中的 Exchange 系統管理中心建立這些連接器。 如需相關指示，請參閱[使用 Office 365 中的連接器設定郵件流程](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。
  
## <a name="tls-certificate-information-for-exchange-online"></a>Exchange Online 的 TLS 憑證資訊

下表說明 Exchange Online 使用的憑證資訊。 如果您的商業夥伴要在其電子郵件伺服器上設定的強制 TLS，您必須提供這項資訊給他們。 請注意，基於安全性考量，我們的憑證會隨時變更。 我們已推出我們資料中心內憑證的更新。 新的憑證從2018年9月3日有效。
  
 **目前從2018年9月3日有效的憑證資訊**
  
| Attribute | 值 |
|:-----|:-----|
|憑證授權單位根發行者  <br/> |GlobalSign 根 CA – R1 <br/> |
|憑證名稱  <br/> |mail.protection.outlook.com  <br/> |
|組織  <br/> |Microsoft Corporation  <br/> |
|組織單位  <br/> |  <br/> |
|憑證金鑰強度  <br/> |2048  <br/> |
   
 **已被取代的憑證資訊有效截止2018年9月3日**
  
為了協助確保順利轉換，我們會繼續提供您參考的舊憑證資訊供您參考，但您現在應該使用目前的憑證資訊。
  
****

| Attribute | 值 |
|:-----|:-----|
|憑證授權單位根發行者  <br/> |Baltimore CyberTrust Root  <br/> |
|憑證名稱  <br/> |mail.protection.outlook.com  <br/> |
|組織  <br/> |Microsoft Corporation  <br/> |
|組織單位  <br/> |Microsoft Corporation  <br/> |
|憑證金鑰強度  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>準備新的 Exchange Online 憑證

新的憑證是由不同的憑證授權單位單位所發行 (CA) Exchange Online 所使用的先前憑證。 因此，您可能需要執行某些動作，才能使用新的憑證。

新的憑證需要在驗證憑證時，連線至新 CA 的端點。 若失敗，可能會造成郵件流程受到不良影響。 如果您使用僅讓郵件伺服器與某些目的地連線的防火牆來保護您的郵件伺服器，您需要檢查您的伺服器是否能夠驗證新的憑證。 若要確認您的伺服器可以使用新的憑證，請完成下列步驟：

1. 使用 Windows PowerShell 連線到本機 Exchange Server，然後執行下列命令：  
  `certutil -URL https://crl.globalsign.com/gsorganizationvalsha2g3.crl`

1. 在出現的視窗中，選擇 [ **取得**]。

1. 當公用程式完成檢查時，它會傳回狀態。 如果狀態顯示 **[確定]**，則您的郵件伺服器會順利驗證新憑證。 如果不是，您需要判斷造成連接失敗的原因。 最可能的情況是，您必須更新防火牆的設定。 需要存取的端點完整清單包括：
    - ocsp.globalsign.com
    - crl.globalsign.com
    - secure.globalsign.com   

一般來說，您會透過 Windows 更新，自動收到您的根憑證更新。 不過，有些部署有其他的安全性，可防止這些更新自動發生。 在這些鎖定部署中 Windows 更新無法自動更新根憑證的情況下，您必須完成下列步驟，以確保安裝正確的根 CA 憑證：
1.  使用 Windows PowerShell 連線到本機 Exchange Server，然後執行下列命令：  
  `certmgr.msc`

2. 在 [ **受信任的憑證授權單位單位/憑證**] 底下，確認新的憑證已列出。

## <a name="get-more-information-about-tls-and-microsoft-365"></a>取得 TLS 和 Microsoft 365 的詳細資訊

如需支援的密碼套件清單，請參閱 [技術參考有關加密的詳細資料](technical-reference-details-about-encryption.md)。
  
[為夥伴組織的安全郵件流程設定連接器](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)
  
[具有增強電子郵件安全性的連接器](/previous-versions/exchange-server/exchange-150/dn942516(v=exchg.150))
  
[Microsoft 365 中的加密](encryption.md)
