---
title: Office 365 加密鏈 - DOD 和 GCC High
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/24/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 查看 Office 365 中的 DOD 和 GCC 高根憑證和憑證授權 (CAs) 的完整清單。
ms.openlocfilehash: 19f164669392372c99c562f55cfb05487d9f7ed2
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308276"
---
# <a name="office-365-encryption-chains---dod-and-gcc-high"></a>Office 365 加密鏈 - DOD 和 GCC High

Office 365 利用許多不同的憑證提供者。 下列說明當存取 Office 365 時， **DOD 和 GCC 高的使用者** 可能會遇到的已知 Office 365 根憑證的完整清單。 如需您可能需要在自己的基礎結構中安裝之憑證的詳細資訊，請參閱 [Plan For Office 365 的協力廠商 SSL 憑證](https://docs.microsoft.com/microsoft-365/enterprise/plan-for-third-party-ssl-certificates)。

下列憑證資訊適用于 **所有 DOD 和 GCC 高級客戶**。

>[!NOTE]
>如需適用于 **全球客戶**的憑證資訊，請參閱 [Office 365 加密連結](encryption-office-365-certificate-chains.md)。

| **憑證類型** | **P7b 下載** | **CRL 端點** | **OCSP 端點** |
| --- | --- | --- | --- | --- |
| 公開信任的根和中級憑證 | [Office 365 ITAR 憑證捆綁 (P7B) ](https://download.microsoft.com/download/b/3/a/b3ae08a2-516c-46a9-8723-6256e4fd6383/O365_Chain_Certs_ITAR20200304.p7b) | crl.entrust.net<br>crl3.digicert.com<br>crl4.digicert.com | ocsp.digicert.com<br>ocsp.entrust.net |

展開下列的根及中間部分，以查看憑證提供者的其他詳細資料。

## <a name="office-365-certificate-details"></a>**Office 365 憑證詳細資料**

### <a name="baltimore-cybertrust-root"></a>**Baltimore CyberTrust Root**

| **主旨** | CN = 巴爾的摩 CyberTrust Root<br>OU = CyberTrust<br>O = 巴爾的摩<br>C = IE |
| --- | --- |
| **序號** | 02：00：00： B9 |
| **公開金鑰長度** | RSA 2048 bits (e 65537)  |
| **簽名演算法** | sha1RSA |
| **不早的合法性** | 5月 12 18:46:00 2000 UTC |
| **不晚的合法性** | 5月 12 23:59:00 2025 UTC |
| **主體金鑰識別碼** | e5：9d：59：30：82：47：58： cc： ac： fa：08：54：36：86：7b：3a： b5：4：4d： f0 |
| **指紋 (SHA-1) ** | D4DE20D05E66FC53FE1A50882C78DB2852CAE474 |
| **指紋 (SHA-256) ** | 16AF57A9F676B0AB126095AA5EBADEF22AB31119D644AC95CD4B93DBF3F26AEB |
| **Pin (SHA-256) ** | Y9mvm0exBk1JoQ57f9Vm28jKo5lFm/woKcVxrYxu80o = |

### <a name="digicert-cloud-services-ca-1"></a>**DigiCert 雲端服務 CA-1**

| **主旨** | CN = DigiCert 雲端服務 CA-1<br>O = DigiCert Inc。<br>C=US |
| --- | --- |
| **發行者** | CN = DigiCert 通用根 CA<br>OU = digicert<br>O = DigiCert Inc。<br>C=US |
| **序號** | 01：9E： C1： C6： BD：3F：59：7B： B2：0C：33：38： E5：51： D8：77 |
| **公開金鑰長度** | RSA 2048 bits (e 65537)  |
| **簽名演算法** | sha256RSA |
| **不早的合法性** | 08月 04 12:00:00 2015 UTC |
| **不晚的合法性** | 08月 04 12:00:00 2030 UTC |
| **主體金鑰識別碼** | dd：51： d0： a2：31：73： a9：73： ae：8f： b4：01：7e：5d：8c：57： cb：9f： f0： f7 |
| **授權機碼識別碼** | keyid：03： de：50：35：56： d1：4c： bb：66： f0： a3： e2：1b：1b： c3：97： b2：3d： d1：55 |
| **指紋 (SHA-1) ** | 81B68D6CD2F221F8F534E677523BB236BBA1DC56 |
| **指紋 (SHA-256) ** | 2F6889961A7CA7067E8BA103C2CF9B9A924F8CA293F11178E23A1978D2F133D3 |
| **Pin (SHA-256) ** | UgpUVparimk8QCjtWQaUQ7EGrtrykc/L8N66EhFY3VE = |
| **CRL URLs** | http://crl4.digicert.com/DigiCertGlobalRootCA.crl<br>http://crl3.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="digicert-global-root-ca"></a>**DigiCert 通用根 CA**

| **主旨** | CN = DigiCert 通用根 CA<br>OU = digicert<br>O = DigiCert Inc。<br>C=US |
| --- | --- |
| **序號** | 08：3B： E0：56：90：42：46： B1： A1：75：6A： C9：59：91： C7：4A |
| **公開金鑰長度** | RSA 2048 bits (e 65537)  |
| **簽名演算法** | sha1RSA |
| **不早的合法性** | 10 00:00:00 2006 年11月 |
| **不晚的合法性** | 10 00:00:00 2031 年11月 |
| **主體金鑰識別碼** | 03：取消：50：35：56： d1：4c： bb：66： f0： a3： e2：1b：1b： c3：97： b2：3d： d1：55 |
| **授權機碼識別碼** | keyid：03： de：50：35：56： d1：4c： bb：66： f0： a3： e2：1b：1b： c3：97： b2：3d： d1：55 |
| **指紋 (SHA-1) ** | A8985D3A65E5E5C4B2D7D66D40C6DD2FB19C5436 |
| **指紋 (SHA-256) ** | 4348A0E9444C78CB265E058D5E8944B4D84F9662BD26DB257F8934A443C70161 |
| **Pin (SHA-256) ** | r/mIkG3eEpVdm + u/ko/cwxzOMo1bk4TyHIlByibiA5E = |

### <a name="digicert-high-assurance-ev-root-ca"></a>**DigiCert 高確定性 EV 根 CA**

| **主旨** | CN = DigiCert 高確定性 EV 根 CA<br>OU = digicert<br>O = DigiCert Inc。<br>C=US |
| --- | --- |
| **序號** | 02： AC：5C：26：6A：0B：40：9B：8F：0B：79： F2： AE：46：25：77 |
| **公開金鑰長度** | RSA 2048 bits (e 65537)  |
| **簽名演算法** | sha1RSA |
| **不早的合法性** | 10 00:00:00 2006 年11月 |
| **不晚的合法性** | 10 00:00:00 2031 年11月 |
| **主體金鑰識別碼** | b1：3e： c3：69：03： f8： bf：47：01： d4：：26：1a：08：02： ef：63：64：2b： c3 |
| **授權機碼識別碼** | keyid： b1：3e： c3：69：03： f8： bf：47：01： d4：02：26：1a：64：2b： c3 |
| **指紋 (SHA-1) ** | 5FB7EE0633E259DBAD0C4C9AE6D38F1A61C7DC25 |
| **指紋 (SHA-256) ** | 7431E5F4C3C1CE4690774F0B61E05440883BA9A01ED00BA6ABD7806ED3B118CF |
| **Pin (SHA-256) ** | WoiWRyIOVNa9ihaBciRSC7XHjliYS9VwUGOIud4PB18 = |

### <a name="digicert-sha2-extended-validation-server-ca"></a>**DigiCert SHA2 擴充驗證服務器 CA**

| **主旨** | CN = DigiCert SHA2 擴充驗證服務器 CA<br>OU = digicert<br>O = DigiCert Inc。<br>C=US |
| --- | --- |
| **序號** | 0C：79： A9：44： B0：8C：11：95：20：92：61：5F： E2：6B：1D：83 |
| **公開金鑰長度** | RSA 2048 bits (e 65537)  |
| **簽名演算法** | sha256RSA |
| **不早的合法性** | Oct 22 00:00:00 2013 UTC |
| **不晚的合法性** | Oct 22 00:00:00 2028 UTC |
| **主體金鑰識別碼** | 3D： D3：50： A5： D6： A0： AD： EE： F3：4A：60：0A：65： D3：21： D4： F8： F8： D6：0F |
| **授權機碼識別碼** | keyID： b1：3e： c3：69：03： f8： bf：47：01： d4：02：26：1a：64：2b： c3 |
| **指紋 (SHA-1) ** | 7E2F3A4F8FE8FA8A5730AECA029696637E986F3F |
| **指紋 (SHA-256) ** | 403E062A2653059113285BAF80A0D4AE422C848C9F78FAD01FC94BC5B87FEF1A |

### <a name="entrust-root-certification-authority"></a>**Entrust 根憑證授權單位單位**

| **主旨** | CN = Entrust 根憑證授權單位單位<br>OU = " (c) 2006 Entrust，Inc."。<br>OU = entrust/CPS 是以參考合併<br>OU = 請參閱 www.entrust.net/legal-terms<br>O = &quot; Entrust，inc.。&quot;<br>C=US |
| --- | --- |
| **序號** | 45：6B：50：54 |
| **公開金鑰長度** | RSA 2048 bits (e 65537)  |
| **簽名演算法** | sha1RSA |
| **不早的合法性** | 27 12:23:42 2006 年11月 |
| **不晚的合法性** | 27 12:53:42 2026 年11月 |
| **主體金鑰識別碼** | 68：90： E4：67： A4： A6：53：80： C7：86：66： A4： F1： F7：4B：43： FB：84： BD：6D |
| **授權機碼識別碼** | keyID：68：90： e4：67： a4： a6：53：80： c7：86：66： a4： f1： f7：4b：43： fb： 84 .. bd：6d |
| **指紋 (SHA-1) ** | B31EB1B740E36C8402DADC37D44DF5D4674952F9 |
| **指紋 (SHA-256) ** | 73C176434F1BC6D5ADF45B0E76E727287C8DE57616C1E6E6141A2B2CBC7D8E4C |

### <a name="entrust-root-certification-authority---g2"></a>**Entrust 根憑證授權單位單位-G2**

| **主旨** | CN = Entrust 根憑證授權單位單位-G2<br>OU = &quot; (c) 2009 Entrust，inc. 供授權使用&quot;<br>OU = 請參閱 www.entrust.net/legal-terms<br>O = &quot; Entrust，inc.。&quot;<br>C=US |
| --- | --- |
| **序號** | 4A：53：8C：28 |
| **公開金鑰長度** | RSA 2048 bits (e 65537)  |
| **簽名演算法** | sha256RSA |
| **不早的合法性** | 07 17:25:54 2009 年7月 |
| **不晚的合法性** | Dec 07 17:55:54 2030 UTC |
| **主體金鑰識別碼** | 6a：72：26：7a： d0：1e： ef：7d： e7：3b：69：51： d4：6c：8d：9f：90：12：66： ab |
| **指紋 (SHA-1) ** | 8CF427FD790C3AD166068DE81E57EFBB932272D4 |
| **指紋 (SHA-256) ** | 43DF5774B03E7FEF5FE40D931A7BEDF1BB2E6B42738C4E6D3841103D3AA7F339 |
| **Pin (SHA-256) ** | du6FkDdMcVQ3u8prumAo6t3i3G27uMP2EOhR8R0at/U = |

### <a name="entrustnet-certification-authority-2048"></a>**Entrust.net Certification Authority (2048)**

| **主旨** | CN = Entrust) 網路憑證授權單位 (2048<br>OU = (c) 1999 Entrust.net 限制<br>OU = entrust net/CPS \_ 2048 包含。  (限制 s liab。 ) <br>O = Entrust |
| --- | --- |
| **序號** | 38：63： DE： F8 |
| **公開金鑰長度** | RSA 2048 bits (e 65537)  |
| **簽名演算法** | sha1RSA |
| **不早的合法性** | Dec 24 17:50:51 1999 UTC |
| **不晚的合法性** | 24 14:15:12 2029 年7月 |
| **主體金鑰識別碼** | 55： e4：81： d1：11：80：是： d8：89： b9：下列： a3：31：16： b9：70 |
| **指紋 (SHA-1) ** | 503006091D97D4F5AE39F7CBE7927D7D652D3431 |
| **指紋 (SHA-256) ** | 6DC47172E01CBCB0BF62580D895FE2B8AC9AD4F873801E0C10B9C837D21EB177 |
| **Pin (SHA-256) ** | HqPF5D7WbC2imDpCpKebHpBnhs6fG1hiFBmgBGOofTg = |

### <a name="entrust-certification-authority---l1c"></a>**Entrust 憑證授權單位單位-L1C**

| **主旨** | CN = Entrust 憑證授權單位單位-L1C<br>OU = &quot; (c) 2009 Entrust，inc.。&quot;<br>OU = entrust/rpa 是以參考合併<br>O = &quot; Entrust，inc.。&quot;<br>C=US |
| --- | --- |
| **發行者** | CN = Entrust) 網路憑證授權單位 (2048<br>OU = (c) 1999 Entrust.net 限制<br>OU = entrust net/CPS \_ 2048 包含。  (限制 liab。 ) <br>O = Entrust |
| **序號** | 4C：0E：8C：39 |
| **公開金鑰長度** | RSA 2048 bits (e 65537)  |
| **簽名演算法** | sha1RSA |
| **不早的合法性** | 11 15:40:40 2011 年11月 |
| **不晚的合法性** | 11 02:51:17 2021 年11月 |
| **主體金鑰識別碼** | 1e： f1： ab：89：6： f8：49：0f：01：33：77： ee：14：7a： ee：19：7c：93：28：4d |
| **授權機碼識別碼** | keyid：55： e4：81： d1：11：80：是： d8：89： b9： a1： a3：31：16： b9：70 |
| **指紋 (SHA-1) ** | C53E73073F93CE7895DE7484126BC303DAB9E657 |
| **指紋 (SHA-256) ** | 0EE4DAF71A85D842D23F4910FD4C909B7271861931F1D5FEAC868225F52700E2 |
| **Pin (SHA-256) ** | VFv5NemtodoRftw8KsvFb8AoCWwOJL6bOJS + Ui0bQ94 = |
| **CRL URLs** | http://crl.entrust.net/2048ca.crl |
| **OCSP URLs** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1e"></a>**Entrust 憑證授權單位單位-L1E**

| **主旨** | CN = Entrust 憑證授權單位單位-L1E<br>OU = &quot; (c) 2009 Entrust，inc.。&quot;<br>OU = entrust/rpa 是以參考合併<br>O = &quot; Entrust，inc.。&quot;<br>C=US |
| --- | --- |
| **發行者** | CN = Entrust) 網路憑證授權單位 (2048<br>OU = (c) 1999 Entrust.net 限制<br>OU = entrust net/CPS \_ 2048 包含。  (限制 liab。 ) <br>O = Entrust |
| **序號** | 4C：0E： C9：18 |
| **公開金鑰長度** | RSA 2048 bits (e 65537)  |
| **簽名演算法** | sha1RSA |
| **不早的合法性** | 11 15:40:40 2011 年11月 |
| **不晚的合法性** | 11 02:51:17 2021 年11月 |
| **主體金鑰識別碼** | 5B：41：8A： B2： C4：43： C1： BD： BF： C8：54：41：55：9D： E0：96： AD： FF： B9： A1 |
| **授權機碼識別碼** | keyid：68：90： e4：67： a4： a6：53：80： c7：86：66： a4： f1： f7：4b：43： fb： 84 .. bd：6d |
| **指紋 (SHA-1) ** | 8A000CC056F7D17349F045BEB0319A3B91C9F979 |
| **指紋 (SHA-256) ** | 3C7A634E5778A0F731972B702DAE24B2CF2060219F607E69878B164C61A06C41 |
| **CRL URLs** | http://crl.entrust.net/rootca1.crl |
| **OCSP URLs** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1k"></a>**Entrust 憑證授權單位單位-L1K**

| **主旨** | CN = Entrust 憑證授權單位單位-L1K<br>OU = &quot; (c) 2012 Entrust，inc. 供授權使用&quot;<br>OU = 請參閱 www.entrust.net/legal-terms<br>O = &quot; Entrust，inc.。&quot;<br>C=US |
| --- | --- |
| **發行者** | CN = Entrust 根憑證授權單位單位-G2<br>OU = &quot; (c) 2009 Entrust，inc. 供授權使用&quot;<br>OU = 請參閱 www.entrust.net/legal-terms<br>O = &quot; Entrust，inc.。&quot;<br>C=US |
| **序號** | 0E： E9：4C： C3：00：00：00：00：51： D3：77：85 |
| **公開金鑰長度** | RSA 2048 bits (e 65537)  |
| **簽名演算法** | sha256RSA |
| **不早的合法性** | Oct 05 19:13:56 2015 UTC |
| **不晚的合法性** | Dec 05 19:43:56 2030 UTC |
| **主體金鑰識別碼** | 82： a2：70：74： dd： bc：53：3f： cf：7b： d4： f7： cd：7f： a7：60： c6：0a：4c： bf |
| **授權機碼識別碼** | keyid：6a：72：26：7a： d0：1e： ef：7d： e7：3b：69：51： d4：6c：8d：9f：90：12：66： ab |
| **指紋 (SHA-1) ** | F21C12F46CDB6B2E16F09F9419CDFF328437B2D7 |
| **指紋 (SHA-256) ** | 13EFB39A2F6654E8C67BD04F4C6D4C90CD6CAB5091BCEDC73787F6B77D3D3FE7 |
| **Pin (SHA-256) ** | 980Ionqp3wkYtN9SZVgMzuWQzJta1nfxNPwTem1X0uc = |
| **CRL URLs** | http://crl.entrust.net/g2ca.crl |
| **OCSP URLs** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1m"></a>**Entrust 憑證授權單位單位-L1M**

| **主旨** | CN = Entrust 核證機關-L1M，OU = &quot; (c) 2014 Entrust，inc.-僅限授權使用&quot;<br>OU = 請參閱 www.entrust.net/legal-terms<br>O = &quot; Entrust，inc.。&quot;<br>C=US |
| --- | --- |
| **發行者** | CN = Entrust 根憑證授權單位單位-G2<br>OU = &quot; (c) 2009 Entrust，inc. 供授權使用&quot;<br>OU = 請參閱 www.entrust.net/legal-terms<br>O = &quot; Entrust，inc.。&quot;<br>C=US |
| **序號** | 61： A1： E7： D2：00：00：00：00：51： D3：66： A6 |
| **公開金鑰長度** | RSA 2048 bits (e 65537)  |
| **簽名演算法** | sha256RSA |
| **不早的合法性** | Dec 15 07:25:03 2014 UTC |
| **不晚的合法性** | Oct 15 08:55:03 2030 UTC |
| **主體金鑰識別碼** | C3： F7： D0： B5：2A：30： AD： AF：0D：91：21：70：39：54： DD： BC：89：70： C7：3A |
| **授權機碼識別碼** | keyid：6a：72：26：7a： d0：1e： ef：7d： e7：3b：69：51： d4：6c：8d：9f：90：12：66： ab |
| **指紋 (SHA-1) ** | CC136695639065FAB47074D28C55314C66077E90 |
| **指紋 (SHA-256) ** | 75C5B3F01FD1F51A2C447AB7C785D72E69FA9C472C08571E7EADF3B8EABAE70C |
| **CRL URLs** | http://crl.entrust.net/g2ca.crl |
| **OCSP URLs** | http://ocsp.entrust.net |

### <a name="microsoft-it-tls-ca-1"></a>**Microsoft IT TLS CA 1**

| **主旨** | CN=Microsoft IT TLS CA 1<br>OU = Microsoft IT<br>O=Microsoft 公司<br>L=Redmond<br>S=Washington<br>C=US |
| --- | --- |
| **發行者** | CN = 巴爾的摩 CyberTrust Root<br>OU = CyberTrust<br>O = 巴爾的摩<br>C = IE |
| **序號** | 08： B8：7A：50：1B：是：9C： DA：2D：16：4D：3E：39：51： BF：55 |
| **公開金鑰長度** | RSA 4096 bits (e 65537)  |
| **簽名演算法** | sha256RSA |
| **不早的合法性** | 5月 20 12:51:28 2016 UTC |
| **不晚的合法性** | 5月 20 12:51:28 2024 UTC |
| **主體金鑰識別碼** | 58：88：9f： d6： dc：9c：48：22： b7：14：3e： ff：84：88： e8： e6：85： ff： fa：7d |
| **授權機碼識別碼** | keyid： e5：9d：59：30：82：47：58： cc： ac： fa：08：54： b5：04：4d：3a： f0 |
| **指紋 (SHA-1) ** | 417E225037FBFAA4F95761D5AE729E1AEA7E3A42 |
| **指紋 (SHA-256) ** | 4FF404F02E2CD00188F15D1C00F4B6D1E38B5A395CF85314EAEBA855B6A64B75 |
| **Pin (SHA-256) ** | xjXxgkOYlag7jCtR5DreZm9b61iaIhd + J3 + b2LiybIw = |
| **CRL URLs** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-2"></a>**Microsoft IT TLS CA 2**

| **主旨** | CN=Microsoft IT TLS CA 2<br>OU = Microsoft IT<br>O=Microsoft 公司<br>L=Redmond<br>S=Washington<br>C=US |
| --- | --- |
| **發行者** | CN = 巴爾的摩 CyberTrust Root<br>OU = CyberTrust<br>O = 巴爾的摩<br>C = IE |
| **序號** | 0F：2C：10： C9：5B：06： C0：93：7F： B8： D4：49： F8：3E：85：69 |
| **公開金鑰長度** | RSA 4096 bits (e 65537)  |
| **簽名演算法** | sha256RSA |
| **不早的合法性** | 5月 20 12:51:57 2016 UTC |
| **不晚的合法性** | 5月 20 12:51:57 2024 UTC |
| **主體金鑰識別碼** | 91：9e：3b：44：6c：3d：57：9c：42：77：2a：34： d7：4f： d1： cc：4a：97：2c： da |
| **授權機碼識別碼** | keyid： e5：9d：59：30：82：47：58： cc： ac： fa：08：54： b5：04：4d：3a： f0 |
| **指紋 (SHA-1) ** | 54D9D20239080C32316ED9FF980A48988F4ADF2D |
| **指紋 (SHA-256) ** | 4E107C981B42ACBE41C01067E16D44DB64814D4193E572317EA04B87C79C475F |
| **Pin (SHA-256) ** | wBdPad95AU7OgLRs0FU/E6ILO1MSCM84kJ9y0H + TT7s = |
| **CRL URLs** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-4"></a>**Microsoft IT TLS CA 4**

| **主旨** | CN=Microsoft IT TLS CA 4<br>OU = Microsoft IT<br>O=Microsoft 公司<br>L=Redmond<br>S=Washington<br>C=US |
| --- | --- |
| **發行者** | CN = 巴爾的摩 CyberTrust Root<br>OU = CyberTrust<br>O = 巴爾的摩<br>C = IE |
| **序號** | 0B：6A： B3： B0：3E： B1： A9： F6： C4：60：92：6A： A8： CD： FE： B3 |
| **公開金鑰長度** | RSA 4096 bits (e 65537)  |
| **簽名演算法** | sha256RSA |
| **不早的合法性** | 5月 20 12:52:38 2016 UTC |
| **不晚的合法性** | 5月 20 12:52:38 2024 UTC |
| **主體金鑰識別碼** | 7a：7b：8c： c1： cf： e7： a0： ca：1c： d4：6b： fa： fb： e1：33： c3：0f：1a： a2：9d |
| **授權機碼識別碼** | keyid： e5：9d：59：30：82：47：58： cc： ac： fa：08：54： b5：04：4d：3a： f0 |
| **指紋 (SHA-1) ** | 8A38755D0996823FE8FA3116A277CE446EAC4E99 |
| **指紋 (SHA-256) ** | 5FFAC43E0DDC5B4AF2B696F6BC4DB7E91DF314BB8FE0D0713A0B1A7AD2A68FAC |
| **Pin (SHA-256) ** | wUY9EOTJmS7Aj4fDVCu/KeE + + mV7FgIcbn4WhMz1I2k = |
| **CRL URLs** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-5"></a>**Microsoft IT TLS CA 5**

| **主旨** | CN=Microsoft IT TLS CA 5<br>OU = Microsoft IT<br>O=Microsoft 公司<br>L=Redmond<br>S=Washington<br>C=US |
| --- | --- |
| **發行者** | CN = 巴爾的摩 CyberTrust Root<br>OU = CyberTrust<br>O = 巴爾的摩<br>C = IE |
| **序號** | 08：88： CD：52：5F：19：24：44：4D：14： A5：82：91： DE： B9：52 |
| **公開金鑰長度** | RSA 4096 bits (e 65537)  |
| **簽名演算法** | sha256RSA |
| **不早的合法性** | 5月 20 12:53:03 2016 UTC |
| **不晚的合法性** | 5月 20 12:53:03 2024 UTC |
| **主體金鑰識別碼** | 08： fe：25：9f：74： ea：87：04： c2： bc： bb：8e： a8：38：5f：33： c6： d1：6c：65 |
| **授權機碼識別碼** | keyid： e5：9d：59：30：82：47：58： cc： ac： fa：08：54： b5：04：4d：3a： f0 |
| **指紋 (SHA-1) ** | AD898AC73DF333EB60AC1F5FC6C4B2219DDB79B7 |
| **指紋 (SHA-256) ** | F0EE5914ED94C7252D058B4E39808AEE6FA8F62CF0974FB7D6D2A9DF16E3A87F |
| **Pin (SHA-256) ** | RCbqB + W8nwjznTeP4O6VjqcwdxIgI79eBpnBKRr32gc = |
| **CRL URLs** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP URLs** | http://ocsp.digicert.com |
