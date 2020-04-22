---
title: 加密 BitLocker
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 摘要：在雲端中 BitLocker 加密的相關資訊。
ms.openlocfilehash: 5596848e392736e20e8c796e6fd409b9c43235d4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637349"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker 與 Distributed Key Manager (DKM) 的加密

Microsoft 伺服器使用 BitLocker，將包含客戶資料的磁片磁碟機加密在磁片區層級。 BitLocker 加密是 Windows 內建的資料保護功能。 BitLocker 是用來保護威脅的技術之一，以防其他程式或控制措施（例如，對硬體的存取控制或回收）發生不足時，可能會導致某些人能夠實際存取包含客戶資料的磁片。 在此情況下，BitLocker 會因遺失、被竊或無法正確解除委任的電腦和磁片，避免資料竊取或洩密的可能性。

在 Exchange Online、SharePoint 線上和商務用 Skype 中包含客戶資料的磁片上，使用進階加密標準（AES）256位加密來部署 BitLocker。 磁片磁區是以完整大量加密金鑰（FVEK）加密，該金鑰是以「磁片區金鑰」（VMK）加密，該主金鑰又會系結至伺服器中的受信任的平臺模組（TPM）。 VMK 直接保護 FVEK，因此保護 VMK 變得很重要。 下圖說明特定伺服器的 BitLocker 金鑰保護鏈的範例（在此情況下，使用 Exchange Online 伺服器）。

下表說明特定伺服器（在此案例中為 Exchange Online 伺服器）的 BitLocker 金鑰保護鏈。

| 金鑰保護器 | 粒 度 | 產生的方式？ | 儲存在哪裡？ | 保護 |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| AES 256 位外部金鑰 | 每個伺服器 | BitLocker APIs | TPM 或機密安全 | 密碼箱/存取控制 |
|  |  |  | 信箱伺服器登錄 | TPM 加密 |
| 48位數的數位密碼 | 每個磁片 | BitLocker APIs | Active Directory | 密碼箱/存取控制 |
| X.509 憑證做為資料復原代理程式（DRA）也稱為公開金鑰保護器 | 環境（例如 Exchange Online 多租戶） | Microsoft CA | 組建系統 | 任何使用者都沒有私密金鑰的完整密碼。 密碼為實體防護。 |


BitLocker 金鑰管理需要管理用於在 Microsoft 資料中心內解除鎖定/復原加密磁片的復原金鑰。 Microsoft 365 將主要金鑰儲存在安全的共用中，只能由已被篩選和核准的使用者存取。 機碼的認證是儲存在存取控制資料（我們稱之為「機密存放區」）的安全存放庫中，這需要高層次的仰角和管理核准，才能使用即時存取提升工具進行存取。

BitLocker 支援可以分為兩個管理類別的按鍵：

- BitLocker 受管理的金鑰，通常是短暫存留的，且與安裝在伺服器上或指定磁片上之作業系統實例的存留時間相關聯。 在重新安裝伺服器或格式化磁片時，這些機碼會被刪除並重設。

- BitLocker 在 BitLocker 之外進行管理，但用於磁片解密的復原金鑰。 BitLocker 會針對重新安裝作業系統的情況使用復原機碼，並已存在已加密的資料磁片。 在 Exchange Online 中，受管理的可用性監控探查也會使用復原機碼，在此情況下，回應程式可能需要解除磁片的鎖定。

使用完整大量加密金鑰加密 BitLocker 受保護的磁片區，然後使用大量的主要金鑰加密。 BitLocker 會使用 FIPS 相容的演算法，以確保加密金鑰永遠不會以明文儲存或傳送。 Microsoft 365 執行的客戶資料就地保護不會偏離預設的 BitLocker 實現。
