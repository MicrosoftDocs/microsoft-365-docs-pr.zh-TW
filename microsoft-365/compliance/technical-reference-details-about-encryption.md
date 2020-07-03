---
title: 有關加密的技術參考詳細資料
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 06/15/2020
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: 深入瞭解 Office 365 中用於加密的各種憑證、技術和 TLS 密碼套件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91fa21fff12c429032af6468ff3024acfc6ca2ab
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024539"
---
# <a name="technical-reference-details-about-encryption"></a>有關加密的技術參考詳細資料

請參閱本文，以瞭解[Office 365 中用於加密](encryption.md)的憑證、技術和 TLS 密碼套件。 本文也提供規劃取代的詳細資料。
  
- 如果您正在尋找概要資訊，請參閱[在 Office 365 中的加密](encryption.md)。
- 如果您正在尋找設定資訊，請參閱[在 Office 365 企業版中設定加密](set-up-encryption.md)。
- 如需特定 Windows 版本支援之密碼套件的詳細資訊，請參閱[TLS/SSL （SCHANNEL SSP）中的密碼套件](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)。

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 憑證擁有權和管理

您不需要購買或維護 Office 365 的憑證，因為 Microsoft 會使用自己的憑證。
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>目前的加密標準與計畫取代

為了繼續提供 Office 365 的最大類型加密，Microsoft 會定期查看支援的加密標準。 在某些情況下，我們有時需要取代舊的標準，因此不會有較低的安全性。 本主題說明目前支援的密碼套件和其他標準，以及有關計畫取代的詳細資料。 

## <a name="fips-compliance-for-office-365"></a>適用于 Office 365 的 FIPS 相容性

Office 365 支援的所有密碼套件都使用 FIPS 140-2 可接受的演算法。 Office 365 繼承來自 Windows （經由 Schannel）的 FIPS 驗證。 如需 Schannel 的詳細資訊，請參閱[TLS/SSL （SCHANNEL SSP）中的密碼套件](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)。
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 支援的 TLS 版本

傳輸層安全性 (TLS) 以及 TLS 之前的 SSL 都是密碼編譯通訊協定，它們使用安全性憑證來加密電腦之間的連線，進而透過網路保護通訊安全。 Office 365 支援 TLS 版本1.2 （TLS 1.2）。

目前不支援 TLS 版本1.3 （TLS 1.3）。
  
## <a name="support-for-tls-10-and-11-deprecation-and-what-this-means-for-you"></a>支援 TLS 1.0 和1.1 的情況，以及這對您的意義

從2018年10月31日起，Office 365 不再支援 TLS 1.0 和1.1。 這表示 Microsoft 將不會修正在使用 TLS 1.0 和 1.1 連線到 Office 365 的用戶端、裝置或服務中發現的新問題。

這並不是指 Office 365 會封鎖 TLS 1.0 和1.1 連接。

[！附注] 雖然我們最初針對全球和 GCC 環境將日期設定為2020年6月1日，用於 TLS 1.0 和 TLS 1.1 為已過時，但此日期已不再有效。 這是因為 COVID-19。 當我們有此過時的新日期時，我們會在這裡發佈它。 

針對 GCC 高和 DoD 環境，官方已過時于2020年1月15日發生。

您應確定所有用戶端伺服器及瀏覽器的組合都使用 TLS 1.2 和新式密碼套件，以維護 Office 365 和 Microsoft 365 服務的安全連線。 您可能必須更新特定的用戶端-伺服器及瀏覽器伺服器組合。 如需有關這對您的影響的詳細資訊，請參閱在[Office 365 中準備 TLS 1.2 的強制使用](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。
  
## <a name="deprecating-support-for-3des"></a>3DES 的取代支援

從2018年10月31日起，Office 365 不再支援使用3DES 密碼套件，以進行 Office 365 的通訊。 更明確地說，Office 365 不再支援 TLS_RSA_WITH_3DES_EDE_CBC_SHA 密碼套件。 從2019年2月28日起，此加密套件已在 Office 365 中停用。 在此日期之後與 Office 365 通訊的用戶端和伺服器必須至少支援本主題中所列的更安全密碼之一（請參閱[Office 365 支援的 TLS 密碼套件](#tls-cipher-suites-supported-by-office-365)）。
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365 不再支援 SHA-1 憑證

從2016年6月，Office 365 不再接受 SHA-1 憑證進行輸出或輸入連線。 如果您目前使用憑證鏈中 SHA-1 憑證，則需要更新鏈以使用 SHA-2 （Secure 雜湊演算法2）或更強的雜湊演算法。
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365 支援的 TLS 密碼套件

加密套件是 TLS 用來建立安全連線的加密演算法集合。 下表依強度列出 Office 365 支援的加密套件，強度最大的加密套件列在最上面。 當 Office 365 收到連線要求時，Office 365 會先嘗試使用最上層的密碼套件進行連線。 然後，如果失敗，Office 365 會嘗試清單中的第二個密碼套件，直到清單中。 當 Office 365 傳送連線要求給另一部伺服器或用戶端時，則全由接收端的伺服器或用戶端選擇加密套件，或是否使用 TLS。

> [!IMPORTANT]
> 請注意 TLS 版本取代，如果有更新的版本，則*不應該使用*該版本。 目前不支援 TLS 1.3。 如果舊版服務不需要 TLS 1.0 或1.1，您應該將它們停用。
  
|**通訊協定**|**加密套件名稱**|**金鑰交換演算法/強度**|**完全向前保密支援**|**驗證演算法/強度**|**密碼/強度**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/128  <br/> |
   
## <a name="related-topics"></a>相關主題
[Windows 10 v1903 中的 TLS 密碼套件](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Office 365 中的加密](encryption.md)
  
[設定 Office 365 企業版中的加密](set-up-encryption.md)
  
[在 Windows 安全性狀態更新中，TLS 1.0 的 Schannel 執行：11月24日（2015）](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL 加密增強功能（Windows IT 中心）](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  
 [在 Office 365 和 Office 365 GCC 中準備 TLS 1.2](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)

