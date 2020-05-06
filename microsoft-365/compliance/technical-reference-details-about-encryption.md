---
title: 有關加密的技術參考詳細資料
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 03/29/2019
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
ms.openlocfilehash: f15f55c4a66d579d547a164633613175f254640b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034527"
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

傳輸層安全性 (TLS) 以及 TLS 之前的 SSL 都是密碼編譯通訊協定，它們使用安全性憑證來加密電腦之間的連線，進而透過網路保護通訊安全。Office 365 支援數個 TLS 版本，包括：
  
- TLS 1.2 版 (TLS 1.2)
    
- TLS 1.1 版 (TLS 1.1)
    
- TLS 1.0 版 (TLS 1.0)
    
 TLS 1.0 和 TLS 1.1 支援將不會被取代為10月31日2018。 如需詳細資訊，請參閱[取代 support FOR TLS 1.0 和 1.1](technical-reference-details-about-encryption.md#TLS11and12deprecation) 。 
 
 目前不支援 TLS 版本1.3 （TLS 1.3）。
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a>取代對 TLS 1.0 和1.1 的支援，以及這對您的意義
<a name="TLS11and12deprecation"> </a>

從2018年10月31日起，Office 365 不再支援 TLS 1.0 和1.1。 這表示 Microsoft 將不會修正在使用 TLS 1.0 和 1.1 連線到 Office 365 的用戶端、裝置或服務中發現的新問題。

請注意，這不是指 Office 365 會封鎖 TLS 1.0 和1.1 連接。 

TLS 1.0 和 TLS 1.1 將在下列日期正式取代：
- 全球和 GCC 環境中客戶的2020年6月1日。
- 2020年1月15日和 DoD 以及主權環境中的客戶。 

您應確定所有用戶端伺服器及瀏覽器的組合都使用 TLS 1.2 和新式密碼符合，以維護 Office 365 服務的安全連線。 您可能需要更新某些用戶端伺服器與瀏覽器-伺服器的組合。 如需有關這對您的影響的詳細資訊，請參閱在[Office 365 中準備 TLS 1.2 的強制使用](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365)。

您應確定所有用戶端伺服器與瀏覽器混合使用 TLS 1.2 （或更新版本），以維護 Office 365 服務的連線。 您可能需要更新某些用戶端伺服器與瀏覽器-伺服器的組合。 如需有關這對您的影響的詳細資訊，請參閱在[Office 365 中準備 TLS 1.2 的強制使用](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。

  
## <a name="deprecating-support-for-3des"></a>3DES 的取代支援
<a name="TLS11and12deprecation"> </a>

從2018年10月31日起，Office 365 不再支援使用3DES 密碼套件，以進行 Office 365 的通訊。 更明確地說，Office 365 不再支援 TLS_RSA_WITH_3DES_EDE_CBC_SHA 密碼套件。 從2019年2月28日起，此加密套件在 Office 365 中已停用。 在此日期之後與 O365 進行通訊的用戶端和伺服器必須至少支援本主題中所列的一個更安全的密碼（請參閱[Office 365 支援的 TLS 密碼套件](technical-reference-details-about-encryption.md#TLSCipherSuites)）。
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365 不再支援 SHA-1 憑證
<a name="TLS11and12deprecation"> </a>

從2016年6月，Office 365 不再接受 SHA-1 憑證進行輸出或輸入連線。 如果您目前使用憑證鏈中 SHA-1 憑證，則需要更新鏈以使用 SHA-2 （Secure 雜湊演算法2）或更強的雜湊演算法。
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365 支援的 TLS 密碼套件
<a name="TLSCipherSuites"> </a>

加密套件是 TLS 用來建立安全連線的加密演算法集合。 Office 365 支援的密碼套件列在下表中，依強弱列于第一個所列的最強式密碼套件。 當 Office 365 收到連線要求時，Office 365 會先嘗試使用最上面的加密套件進行連線，如果不成功，則嘗試清單中的第二個加密套件，依此類推。 當 Office 365 傳送連線要求給另一部伺服器或用戶端時，則全由接收端的伺服器或用戶端選擇加密套件，或是否使用 TLS。

> [!IMPORTANT]
> 請注意 TLS 版本取代，如果有更新的版本，則*不應該使用*該版本。 換句話說，可支援 TLS 1.0、1.1 及1.2 的任何地方，請選擇*最新*支援的版本（TLS 1.2）。 目前不支援 TLS。 如果舊版服務不需要 TLS 1.0 或1.1，您應該考慮停用這些服務。 
  
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
  
 [在 Office 365 和 Office 365 GCC 中準備 TLS 1。2](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)

