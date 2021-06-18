---
title: 關於加密的技術參考詳細資料
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
- Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: 瞭解 Office 365 和 Microsoft 365 中用於加密的各種憑證、技術及傳輸層安全性 (TLS) 密碼套件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b2257338ab214ccdaa08f1aa8f322aad98d7c8b
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007546"
---
# <a name="technical-reference-details-about-encryption"></a>關於加密的技術參考詳細資料

請參閱本文以瞭解[在 Office 365 中用於加密](encryption.md)的憑證、技術和 TLS 密碼套件。 本文也提供規劃取代的詳細資料。
  
- 如果您正在尋找概要資訊，請參閱[Encryption in Office 365](encryption.md)。
- 如果您正在尋找設定資訊，請參閱[Office 365 Enterprise 中的設定加密](set-up-encryption.md)。
- 如需特定版本 Windows 所支援之密碼套件的詳細資訊，請參閱[TLS/SSL (Schannel SSP) 中的密碼套件](/windows/desktop/SecAuthN/cipher-suites-in-schannel)。

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 憑證擁有權和管理

您不需要購買或維護 Office 365 的憑證。 相反地，Office 365 會使用自己的憑證。
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>目前的加密標準與計畫取代

若要提供最大的類別加密，Office 365 定期審閱支援的加密標準。 在某些情況下，舊的標準會被取代，但不會變得更安全。 本文說明目前支援的密碼套件，以及有關規劃取代的其他標準及詳細資料。

## <a name="fips-compliance-for-office-365"></a>Office 365 的 FIPS 相容性

Office 365 所支援的所有密碼套件都使用 FIPS 140-2 的可接受演算法。 Office 365 會從 Windows (經由 Schannel) 繼承 FIPS 驗證。 如需 Schannel 的詳細資訊，請參閱 [TLS/SSL (SCHANNEL SSP) 中的密碼套件 ](/windows/desktop/SecAuthN/cipher-suites-in-schannel)。
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 支援的 TLS 版本

Tls 和 TLS 之前的 SSL 是使用安全性憑證來加密電腦之間連線的加密通訊協定，可安全地透過網路進行通訊。 Office 365 支援 tls 版本 1.2 (tls 1.2) 。

TLS 版本1.3 目前不支援 (TLS 1.3) 。

> [!IMPORTANT]
> 請注意 TLS 版本取代，如果有更新的版本，則 *不應該使用* 該版本。 如果舊版服務不需要 TLS 1.0 或1.1，您應該將它們停用。
  
## <a name="support-for-tls-10-and-11-deprecation"></a>支援 TLS 1.0 和1.1 棄用

Office 365 已停止支援在1.0 年10月 31 2018 日在 TLS 和1.1。 在 GCC 高及 DoD 環境中，我們已完成停用 TLS 1.0 和1.1。 我們已開始從1.0 年10月15日開始，為全球和 GCC 環境停用 TLS 和 1.1 2020，並在今後的星期和月份內繼續進行匯總。

為了維護 Office 365 和 Microsoft 365 服務的安全連線，所有用戶端伺服器與瀏覽器的組合都使用 TLS 1.2 和新式密碼套件。 您可能必須更新特定的用戶端-伺服器及瀏覽器伺服器組合。 如需此變更如何影響您的詳細資訊，請參閱[在 Office 365 中準備 TLS 1.2 的強制用法](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。
  
## <a name="deprecating-support-for-3des"></a>3DES 的取代支援

自2018年10月31日起，Office 365 不再支援使用3DES 密碼套件，以 Office 365 進行通訊。 更具體地說，Office 365 不再支援 TLS_RSA_WITH_3DES_EDE_CBC_SHA 密碼套件。 從2019年2月28日起，在 Office 365 中已停用此加密套件。 與 Office 365 通訊的用戶端和伺服器必須支援一或多個支援的密碼。 如需支援的密碼清單，請參閱[Office 365 所支援的 TLS 密碼套件](#tls-cipher-suites-supported-by-office-365)。
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365 不再支援 SHA-1 憑證

從2016年6月起，Office 365 不再接受輸出或輸入連線的 SHA-1 憑證。 使用 SHA-2 (安全雜湊演算法 2) 或憑證鏈中強的雜湊演算法。
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365 所支援的 TLS 密碼套件

TLS 使用 *密碼套件*（加密演算法的集合）建立安全連線。 Office 365 支援下表所列的密碼套件。 表格會依強度順序列出密碼套件，最強的密碼套件優先列出。

Office 365 會先嘗試使用最安全的密碼套件進行連線，以回應連接要求。 如果連線無法運作，Office 365 會嘗試在清單中嘗試第二個最安全的密碼套件，依此類推。 服務會連續按清單，直到接受連接為止。 同樣地，當 Office 365 要求連線時，接收服務會選擇是否要使用 TLS 和要使用的密碼套件。

| 加密套件名稱 | 金鑰交換演算法/強度 | 轉寄保密 | 密碼/強度 | 驗證演算法/強度 |
|:-----|:-----|:-----|:-----|:-----|
| TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> | ECDH/192  <br/> | 是  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> | ECDH/128  <br/> | 是  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384  <br/> | ECDH/192  <br/> | 是  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256  <br/> | ECDH/128  <br/> | 是  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA     <br/> | ECDH/192  <br/> | 是  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA     <br/> | ECDH/128  <br/> | 是  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_RSA_WITH_AES_256_GCM_SHA384        <br/> | RSA/112   <br/> | 否   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_RSA_WITH_AES_128_GCM_SHA256        <br/> | RSA/112   <br/> | 否   <br/> | AES/256  <br/> | RSA/112  <br/> |

下列密碼套件支援 TLS 1.0 和1.1 通訊協定，直到其版本到期為止。 若為 GCC 的高和 DoD 環境（即已過時的日期為2020年1月15日）。 在全球和 GCC 的環境中，日期為2020年10月15日。

| 通訊協定 | 加密套件名稱 | 金鑰交換演算法/強度 | 轉寄保密 | 密碼/強度 | 驗證演算法/強度 | 
|:-----|:-----|:-----|:-----|:-----|:-----|
| TLS 1.0、1.1、1.2  <br/> | TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> | ECDH/192  <br/> | 是  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0、1.1、1.2  <br/> | TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> | ECDH/128  <br/> | 是  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS 1.0、1.1、1.2  <br/> | TLS_RSA_WITH_AES_256_CBC_SHA        <br/> | RSA/112   <br/> | 否   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0、1.1、1.2  <br/> | TLS_RSA_WITH_AES_128_CBC_SHA        <br/> | RSA/112   <br/> | 否   <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS 1.0、1.1、1.2  <br/> | TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> | RSA/112   <br/> | 否   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0、1.1、1.2  <br/> | TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> | RSA/112   <br/> | 否   <br/> | AES/256  <br/> | RSA/112  <br/> |

某些 Office 365 產品 (包含 Microsoft Teams) 使用[Azure 前端](/azure/frontdoor/front-door-overview)以終止 TLS 連線並有效地路由網路流量。 必須啟用至少一個 [Azure 前端 OVER TLS 1.2 的密碼套件](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-) ，才能成功連線到這些產品。 針對 Windows 10 及以上版本，我們建議啟用一或兩個 ECDHE 密碼套件，以取得更好的安全性。 Windows 7、8和8.1 與 Azure 前門的 ECDHE 密碼套件不相容，且已提供 DHE 密碼套件，以與這些作業系統相容。

## <a name="related-articles"></a>相關文章

[Windows 10 v1903 中的 TLS 密碼套件](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Office 365 中的加密](encryption.md)
  
[設定 Office 365 企業版中的加密](set-up-encryption.md)
  
[在 Windows 安全性狀態更新中，TLS 1.0 的 Schannel 實現：2015年11月24日（限）](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL 加密增強 (Windows IT 中心) ](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))
  
[在 Office 365 和 Office 365 GCC 中準備 TLS 1.2](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)

[Azure 前端所支援的目前密碼套件為何？](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-)
