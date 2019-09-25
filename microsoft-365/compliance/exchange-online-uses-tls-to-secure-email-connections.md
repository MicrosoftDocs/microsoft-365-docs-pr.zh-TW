---
title: Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
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
description: 了解 Exchange 在线和 Office 365 如何使用传输层安全 （TLS） 和转发保密 （FS） 来保护电子邮件通信。 还可以获取有关 Microsoft 颁发的联机交换证书的信息。
ms.openlocfilehash: e165be9a3407abfcc165054f7f147eeb2d2c0a82
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077047"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections-in-office-365"></a>Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線

了解 Exchange 在线和 Office 365 如何使用传输层安全 （TLS） 和转发保密 （FS） 来保护电子邮件通信。 还提供有关 Microsoft 颁发的联机交换证书的信息。
  
## <a name="tls-basics-for-office-365-and-exchange-online"></a>Office 365 和 Exchange Online 的 TLS 基本概念

TLS 之前的傳輸層安全性 (TLS) 和 SSL 是密碼編譯通訊協定，該協定使用安全性憑證來加密電腦之間的連線以保護透過網路進行的通訊。 TLS 取代了安全通訊端層 (SSL)，且往往被稱為 SSL 3.1。 对于 Exchange 在线，我们使用 TLS 来加密我们的 Exchange 服务器与 Exchange 服务器与其他服务器（如本地 Exchange 服务器或收件人的邮件服务器）之间的连接。 一旦連線經過加密，所有透過該連線傳送的資料將會透過加密通道傳送。 不過，若轉寄透過 TLS 加密連線所傳送的郵件，該郵件則不一定會加密。 这是因为，简单来说，TLS不加密消息，只是加密连接。
  
如果您想要加密郵件，便需要使用能加密郵件內容的加密技術，如 Office 郵件加密之類的技術。 如需 Office 365 郵件加密選項的相關資訊，請參閱 [Email encryption in Office 365](email-encryption.md) 及 [Office 365 Message Encryption (OME)](ome.md)。 
  
建议在要在 Office 365 与本地组织或其他组织（如合作伙伴）之间建立安全通信渠道的情况下使用 TLS。 Exchange Online 一律會先嘗試使用 TLS 來保護您的電子郵件，但如果另一方沒有提供 TLS 安全性，則無法一律如此進行。 继续阅读，了解如何使用*连接器*保护所有邮件到本地服务器或重要合作伙伴。 
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Exchange Online 如何在 Exchange Online 客戶之間使用 TLS

Exchange Online 伺服器一律會使用 TLS 1.2 加密連往資料中心內其他 Exchange Online 伺服器的連線。當您傳送郵件給 Office 365 組織內的收件者時，該電子郵件會自動透過使用 TLS 加密的連線來傳送。同時，所有傳送給其他 Office 365 客戶的電子郵件，都會透過使用 TLS 加密並使用轉寄密碼保護的連線來傳送。
  
## <a name="how-office-365-uses-tls-between-office-365-and-external-trusted-partners"></a>Office 365 如何使用 Office 365 和外部可信合作伙伴之间的 TLS

根據預設，Exchange Online 一律會使用「隨機 TLS」。 這表示 Exchange Online 一律會先嘗試使用最安全的 TLS 版本加密連線，如果無法成功，便在 TLS 加密清單中尋找下一順位的版本，直到找到雙方都能同意的版本。 除非您已配置 Exchange Online 以确保仅通过安全连接向该收件人发送邮件，否则默认情况下，如果收件人组织不支持 TLS 加密，则邮件将以未加密的方式发送。 隨機 TLS 對大多數企業而言已足夠。 但是，对于具有合规性要求的企业（如医疗、银行或政府组织），您可以将 Exchange Online 配置为要求或强制 TLS。 有关说明，请参阅[使用 Office 365 中的连接器配置邮件流。](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)
  
如果您決定在所屬組織與信任的合作夥伴組織之間設定 TLS，Exchange Online 可以使用「強制 TLS」建立信任的通訊通道。 強制 TLS 會要求合作夥伴組織必須使用安全性憑證向 Exchange Online 進行驗證，才能傳送郵件給您。 您的合作夥伴必須管理自己的憑證，才能執行此動作。 在 Exchange Online 中，我们使用连接器来保护您发送的邮件在邮件到达收件人的电子邮件提供商之前免受未经授权的访问。 有关使用连接器配置邮件流的信息，请参阅在[Office 365 中使用连接器配置邮件流。](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS 和混合 Exchange Server 部署

若要管理混合 Exchange 部署，您的內部部署 Exchange 伺服器需要使用安全性憑證向 Office 365 驗證，才能傳送郵件給信箱只位在 Office 365 內的收件者。 因此，您需要管理本地 Exchange 服务器自己的安全证书。 您也必須安全地儲存和維護這些伺服器憑證。 有关在混合部署中管理证书的详细信息，请参阅[混合部署的证书要求。](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx)
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>如何在 Office 365 中設定 Exchange Online 的強制 TLS

Exchange Online 客戶若想要使用強制 TLS 保護所有傳送和接收的電子郵件，需要設定多個需要 TLS 的連接器。 一個連接器用於傳送給使用者信箱的電子郵件，另一個連接器用於從使用者信箱寄出的電子郵件。 請在 Office 365 中的 Exchange 系統管理中心建立這些連接器。 有关说明，请参阅[使用 Office 365 中的连接器配置邮件流。](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)
  
## <a name="tls-certificate-information-for-exchange-online"></a>Exchange Online 的 TLS 憑證資訊

下表說明 Exchange Online 使用的憑證資訊。 如果您的商業夥伴要在其電子郵件伺服器上設定的強制 TLS，您必須提供這項資訊給他們。 請注意，基於安全性考量，我們的憑證會隨時變更。 我们已经在数据中心内推出了对证书的更新。 新证书的有效期为 2018 年 9 月 3 日。
  
 **当前证书信息自 2018 年 9 月 3 日起生效**
  
|**屬性**|**值**|
|:-----|:-----|
|憑證授權單位根發行者  <br/> |全局标志根 CA = R1 <br/> |
|憑證名稱  <br/> |mail.protection.outlook.com  <br/> |
|組織  <br/> |Microsoft Corporation  <br/> |
|組織單位  <br/> |  <br/> |
|憑證金鑰強度  <br/> |2048  <br/> |
   
 **已弃用的证书信息有效期至 2018 年 9 月 3 日**
  
为了帮助确保平稳过渡，我们将继续提供旧证书信息供您参考一段时间，但是，从现在起，您应该使用当前的证书信息。
  
****

|**屬性**|**值**|
|:-----|:-----|
|憑證授權單位根發行者  <br/> |Baltimore CyberTrust Root  <br/> |
|憑證名稱  <br/> |mail.protection.outlook.com  <br/> |
|組織  <br/> |Microsoft Corporation  <br/> |
|組織單位  <br/> |Microsoft Corporation  <br/> |
|憑證金鑰強度  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>准备新的 Exchange 在线证书

新证书由不同的证书颁发机构 （CA） 与 Exchange Online 使用以前的证书颁发。 因此，您可能需要执行某些操作才能使用新证书。

新证书需要连接到新 CA 的终结点，作为验证证书的一部分。 否则可能导致邮件流受到负面影响。 如果使用仅允许邮件服务器与特定目标连接的防火墙来保护邮件服务器，则需要检查服务器是否能够验证新证书。 要确认服务器可以使用新证书，请完成以下步骤：

1. 使用 Windows PowerShell 连接到本地 Exchange 服务器，然后运行以下命令：  
  `certutil -URL http://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. 在显示的窗口中，**选择"检索"。**
3. 当实用程序完成其检查时，它将返回状态。 如果状态**显示"确定"，** 则邮件服务器可以成功验证新证书。 如果没有，您需要确定导致连接失败的原因。 最有可能的是，您需要更新防火墙的设置。 需要访问的终结点的完整列表包括：
    - ocsp.globalsign.com
     - crl.globalsign.com
     - secure.globalsign.com   

通常，您通过 Windows 更新自动接收根证书的更新。 但是，某些部署具有额外的安全性，可防止自动进行这些更新。 在这些 Windows 更新无法自动更新根证书的锁定部署中，您需要通过完成以下步骤确保安装了正确的根 CA 证书：
1.  使用 Windows PowerShell 连接到本地 Exchange 服务器，然后运行以下命令：  
  `certmgr.msc`
2. **在"受信任的根证书颁发机构/证书"** 下，确认新证书已列出。

## <a name="get-more-information-about-tls-and-office-365"></a>取得 TLS 和 Office 365 的詳細資訊

有关支持的密码套件列表，请参阅 Office [365 中有关加密的技术参考详细信息。](technical-reference-details-about-encryption.md)
  
[為夥伴組織的安全郵件流程設定連接器](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[具有增强电子邮件安全性的连接器](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Office 365 中的加密](encryption.md)
  

