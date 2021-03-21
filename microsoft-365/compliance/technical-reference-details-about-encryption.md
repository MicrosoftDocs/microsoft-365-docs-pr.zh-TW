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
description: 深入瞭解 Office 365 和 Microsoft 365 中用於加密的各種憑證、技術及傳輸層安全性 (TLS) 密碼套件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e7e50ea399cd694f512e0538de3f7e67c63ee0e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919349"
---
# <a name="technical-reference-details-about-encryption"></a>關於加密的技術參考詳細資料

請參閱本文，以瞭解 [Office 365 中用於加密](encryption.md)的憑證、技術和 TLS 密碼套件。 本文也提供規劃取代的詳細資料。
  
- 如果您正在尋找概要資訊，請參閱 [在 Office 365 中的加密](encryption.md)。
- 如果您正在尋找設定資訊，請參閱 [在 Office 365 企業版中設定加密](set-up-encryption.md)。
- 如需特定 Windows 版本支援之密碼套件的詳細資訊，請參閱 [TLS/SSL (SCHANNEL SSP) 中的密碼套件 ](/windows/desktop/SecAuthN/cipher-suites-in-schannel)。

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 憑證擁有權和管理

您不需要購買或維護 Office 365 的憑證。 相反地，Office 365 會使用自己的憑證。
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>目前的加密標準與計畫取代

若要提供最大的類別加密，Office 365 會定期檢查支援的加密標準。 在某些情況下，舊的標準會被取代，但不會變得更安全。 本文說明目前支援的密碼套件，以及有關規劃取代的其他標準及詳細資料。

## <a name="fips-compliance-for-office-365"></a>適用于 Office 365 的 FIPS 相容性

Office 365 支援的所有密碼套件都使用 FIPS 140-2 可接受的演算法。 Office 365 會繼承來自 Windows (到 Schannel) 的 FIPS 驗證。 如需 Schannel 的詳細資訊，請參閱 [TLS/SSL (SCHANNEL SSP) 中的密碼套件 ](/windows/desktop/SecAuthN/cipher-suites-in-schannel)。
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 支援的 TLS 版本

Tls 和 TLS 之前的 SSL 是使用安全性憑證來加密電腦之間連線的加密通訊協定，可安全地透過網路進行通訊。 Office 365 支援 TLS 版本 1.2 (TLS 1.2) 。

TLS 版本1.3 目前不支援 (TLS 1.3) 。
  
## <a name="support-for-tls-10-and-11-deprecation"></a>支援 TLS 1.0 和1.1 棄用

在365年10月 31 2018 日，Office 已停止支援 TLS 1.0 和1.1。 在 GCC 高端和 DoD 環境中，我們已完成停用 TLS 1.0 和1.1。 我們已開始從1.0 年10月15日開始，針對全球和 GCC 環境停用 TLS 和 1.1 2020，且會在今後的星期和月內繼續進行匯總。

若要維護 Office 365 和 Microsoft 365 服務的安全連線，所有用戶端伺服器與瀏覽器-伺服器的組合都使用 TLS 1.2 和新式密碼套件。 您可能必須更新特定的用戶端-伺服器及瀏覽器伺服器組合。 如需此變更如何影響您的詳細資訊，請參閱在 [Office 365 中準備使用 TLS 1.2 的必要](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)資訊。
  
## <a name="deprecating-support-for-3des"></a>3DES 的取代支援

從2018年10月31日起，Office 365 不再支援使用3DES 密碼套件，以進行 Office 365 的通訊。 更明確地說，Office 365 不再支援 TLS_RSA_WITH_3DES_EDE_CBC_SHA 密碼套件。 從2019年2月28日起，此加密套件已在 Office 365 中停用。 與 Office 365 通訊的用戶端和伺服器必須支援一或多個支援的密碼。 如需支援之密碼的清單，請參閱 [Office 365 支援的 TLS 密碼套件](#tls-cipher-suites-supported-by-office-365)。
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365 不再支援 SHA-1 憑證

從2016年6月起，Office 365 不再接受 SHA-1 憑證進行輸出或輸入連線。 使用 SHA-2 (安全雜湊演算法 2) 或憑證鏈中強的雜湊演算法。
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365 支援的 TLS 密碼套件

TLS 使用 *密碼套件*（加密演算法的集合）建立安全連線。 Office 365 支援下表所列的密碼套件。 表格會依強度順序列出密碼套件，最強的密碼套件優先列出。

Office 365 會先嘗試使用最安全的密碼套件進行連線，以回應連接要求。 如果連線無法運作，Office 365 會嘗試在清單中第二個最安全的密碼套件，依此類推。 服務會連續按清單，直到接受連接為止。 同樣地，當 Office 365 要求連線時，接收服務會選擇是否要使用 TLS 和要使用的密碼套件。

> [!IMPORTANT]
> 請注意 TLS 版本取代，如果有更新的版本，則 *不應該使用* 該版本。 目前不支援 TLS 1.3。 如果舊版服務不需要 TLS 1.0 或1.1，您應該將它們停用。

| 密碼套件 | 金鑰交換演算法/強度 | 轉寄保密 | 密碼/強度 | 驗證演算法 |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|是 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|是 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|是 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|是 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|是 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|是 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |否 <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |否 <br/> |AES/256 <br/>|RSA/112 <br/> |

這些密碼套件支援 TLS 1.0 和1.1 通訊協定，直到其版本到期為止。 針對已取得日期為2020年1月15日的 GCC 高和 DoD 環境，而全球和 GCC 環境為2020。

| 通訊協定 | 加密套件名稱 | 金鑰交換演算法/強度 | 轉寄保密支援 | 驗證演算法/強度 | 密碼/強度 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |否  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |否  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |否   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |否   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>相關文章

[Windows 10 v1903 中的 TLS 密碼套件](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Office 365 中的加密](encryption.md)
  
[設定 Office 365 企業版中的加密](set-up-encryption.md)
  
[在 Windows 安全性狀態更新中，TLS 1.0 的 Schannel 執行：11月24日（2015）](https://support.microsoft.com/kb/3117336)
  
[ (Windows IT 中心的 TLS/SSL 加密增強功能) ](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))
  
[在 Office 365 和 Office 365 GCC 中準備 TLS 1.2](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)