---
title: Exchange Online 如何保護您的電子郵件機密資料
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: 除了為 Microsoft 365 提供安全性、隱私權及合規性資訊的 Office 365 信任中心之外，您可能想知道 Microsoft 如何協助保護您在其資料中心內儲存的機密。 我們使用稱為「分散式金鑰管理員」的技術 (DKM) 。
ms.openlocfilehash: 2f6e51b7fe9cd75cbd265c3135050a08130f34d8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906959"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Exchange Online 如何保護您的電子郵件機密資料

本文說明 Microsoft 如何在其資料中心內保護您的電子郵件機密。
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>如何保護您所提供的機密資訊的安全性？

除了為[Office 365 提供安全性、隱私權及合規性資訊](./get-started-with-service-trust-portal.md)的 Office 365 信任中心之外，您可能想知道 Microsoft 如何協助保護您在其資料中心內提供的機密。 我們使用稱為「分散式金鑰管理員」的技術 (DKM) 。
  
[分散式金鑰管理員](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) 是一種用戶端功能，使用一組機密金鑰來加密及解密資訊。 只有 Active Directory 網域服務中特定安全性群組的成員才能存取這些機碼，以便解密由 DKM 所加密的資料。 在 Exchange Online 中，只有在執行 Exchange 程式的特定服務帳戶才是該安全性群組的一部分。 在資料中心的標準作業程式中，未被任何人提供此安全性群組的一部分認證，因此沒有人員可以存取可將這些機密解密的金鑰。
  
針對調試、疑難排解或審計目的，資料中心管理員必須要求提升存取權，才可取得屬於安全性群組一部分的臨時認證。 此程式需要多個合法的法律核准層級。 若授予存取權，就會記錄並審核所有活動。 此外，access 只會被授與已設定的時間間隔之後自動到期。
  
針對額外的保護，DKM 技術包含自動化金鑰翻轉和封存。 這也可確保您可以繼續存取較舊的內容，而不需要無限期地依賴相同的金鑰。
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Exchange Online 如何使用 DKM？

Microsoft 會使用 [[分散式金鑰管理員](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)]，在 Exchange Online 資料中心內加密您的機密。 例如：
  
- 已線上帳戶的電子郵件帳戶認證。 連線的帳戶是協力廠商帳戶，例如 Hotmail、Gmail 和 Yahoo！ 郵件帳戶。

- 客戶金鑰。 如果您使用 [服務加密搭配客戶金鑰](customer-key-overview.md)，您將使用 [Azure 金鑰 Vault](/azure/key-vault/key-vault-whatis) 來保護您的機密。

## <a name="related-topics"></a>相關主題

[Office 365 中的加密](encryption.md)
  
[關於加密的技術參考詳細資料](technical-reference-details-about-encryption.md)
  
[安全性與 &amp; 合規性中心的服務保證](./service-assurance.md)
