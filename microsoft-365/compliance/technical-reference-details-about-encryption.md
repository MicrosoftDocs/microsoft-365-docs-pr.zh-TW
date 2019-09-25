---
title: 關於 Office 365 中加密的技術參考細節
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
description: 查看 Office 365 中有关百科全书的技术详细信息。
ms.openlocfilehash: 0ae26aa6a534f0de0923f869acb94d7ee8529f31
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077481"
---
# <a name="technical-reference-details-about-encryption-in-office-365"></a>關於 Office 365 中加密的技術參考細節

请参阅本文，了解[用于 Office 365 中加密的](encryption.md)证书、技术和 TLS 密码套件。 本文还提供了有关计划弃用的详细信息。
  
- 如果要查找概述信息，请参阅[Office 365 中的加密](encryption.md)。
- 如果要查找设置信息，请参阅在 Office [365 企业版中设置加密。](set-up-encryption.md)
- 有关特定版本的 Windows 支持的密码套件的信息，请参阅[TLS/SSL （通道 SSP） 中的密码套件。](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 憑證擁有權和管理

您不需要購買或維護 Office 365 的憑證，因為 Microsoft 會使用自己的憑證。
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>当前加密标准和计划弃用

为了继续为 Office 365 提供同类最佳的加密，Microsoft 定期审查支持的加密标准。 有时，我们需要弃用旧标准，因为它们已经过时，因此不太安全。 本主题介绍当前支持的密码套件和其他标准，以及有关计划弃用的详细信息。 

## <a name="fips-compliance-for-office-365"></a>Office 365 的 FIPS 合规性
Office 365 支持的所有密码套件都使用 FIPS 140-2 下可接受的算法。 Office 365 从 Windows（通过通道）继承 FIPS 验证。 有关通道的信息，请参阅[TLS/SSL （通道 SSP） 中的密码套件](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)。
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 支援的 TLS 版本

傳輸層安全性 (TLS) 以及 TLS 之前的 SSL 都是密碼編譯通訊協定，它們使用安全性憑證來加密電腦之間的連線，進而透過網路保護通訊安全。Office 365 支援數個 TLS 版本，包括：
  
- TLS 1.2 版 (TLS 1.2)
    
- TLS 1.1 版 (TLS 1.1)
    
- TLS 1.0 版 (TLS 1.0)
    
 TLS 1.0 和 TLS 1.1 支持将于 2018 年 10 月 31 日弃用。 有关详细信息，请参阅[弃用 TLS 1.0 和 1.1 的支持以及这对您意味着什么。](technical-reference-details-about-encryption.md#TLS11and12deprecation) 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a>弃用对 TLS 1.0 和 1.1 的支持，以及这对您意味着什么
<a name="TLS11and12deprecation"> </a>

自 2018 年 10 月 31 日起，Office 365 不再支持 TLS 1.0 和 1.1。 这意味着 Microsoft 不会使用 TLS 1.0 和 1.1 修复在连接到 Office 365 的客户端、设备或服务中发现的新问题。

注意，这并不意味着 Office 365 将阻止 TLS 1.0 和 1.1 连接。 

TLS 1.0 和 TLS 1.1 将在以下日期正式弃用：
- 2020 年 6 月 1 日，适用于世界和 GCC 环境中的客户。
- 2020 年 1 月 15 日，适用于 GCC 高和 DoD 主权环境中的客户。 

应确保所有客户端-服务器和浏览器-服务器组合都使用 TLS 1.2（或更高版本）来维护与 Office 365 服务的连接。 您可能需要更新某些客户端-服务器和浏览器-服务器组合。 有关这对您的影响的信息，请参阅准备在[Office 365 中强制使用 TLS 1.2。](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365)
  
## <a name="deprecating-support-for-3des"></a>对 3DES 的弃用支持
<a name="TLS11and12deprecation"> </a>

自 2018 年 10 月 31 日起，Office 365 不再支持使用 3DES 密码套件与 Office 365 通信。 更具体地说，Office 365 不再支持 TLS_RSA_WITH_3DES_EDE_CBC_SHA 密码套件。 自 2019 年 2 月 28 日起，此密码套件在 Office 365 中处于禁用状态。 在此日期之后与 O365 通信的客户端和服务器必须至少支持本主题中列出的一个更安全的密码（请参阅[Office 365 支持的 TLS 密码套件）。](technical-reference-details-about-encryption.md#TLSCipherSuites)
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365 不再支援 SHA-1 憑證
<a name="TLS11and12deprecation"> </a>

自 2016 年 6 月起，Office 365 不再接受出站或入站连接的 SHA-1 证书。 如果当前在证书链中使用具有 SHA-1 的证书，则需要更新该链以使用 SHA-2（安全哈希算法 2）或更强的哈希算法。
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365 支持的 TLS 密码套件
<a name="TLSCipherSuites"> </a>

加密套件是 TLS 用來建立安全連線的加密演算法集合。 由 Office 365 支持的密码套件列在下表中，其强度顺序为第一个列出的最强密码套件。 當 Office 365 收到連線要求時，Office 365 會先嘗試使用最上面的加密套件進行連線，如果不成功，則嘗試清單中的第二個加密套件，依此類推。 當 Office 365 傳送連線要求給另一部伺服器或用戶端時，則全由接收端的伺服器或用戶端選擇加密套件，或是否使用 TLS。

> [!IMPORTANT]
> 请注意，TLS 版本已弃用，并且不应在有较新版本可用时*使用*弃用版本。 换句话说，在它列出的任何位置都支持 TLS 1.0、1.1 和 1.2，请选择*最新版本*（TLS 1.2）。
  
|**协议**|**加密套件名稱**|**密钥交换算法/强度**|**完美的前向保密支持**|**身份验证算法/强度**|**密码/强度**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.2  <br/> |TLS_ECDHE_RSA_带_AES_256_GCM_SHA384  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_带_AES_128_GCM_SHA256  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/128  <br/> |
   
## <a name="related-topics"></a>相關主題
[Windows 10 v1607 中的 TLS 密码套件](https://docs.microsoft.com/windows/desktop/SecAuthN/tls-cipher-suites-in-windows-10-v1607)

[Office 365 中的加密](encryption.md)
  
[設定 Office 365 企業版中的加密](set-up-encryption.md)
  
[Windows 安全状态更新中 TLS 1.0 的通道实现：2015 年 11 月 24 日](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL 加密增强功能（Windows IT 中心）](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

