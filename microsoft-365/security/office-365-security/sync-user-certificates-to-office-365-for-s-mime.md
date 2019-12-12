---
title: 將使用者憑證同步至 Office 365 進行 S/MIME 處理
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: 在設定正確的憑證之前，任何人都無法傳送受 S/MIME 保護的郵件。為了透過 Exchange Online 傳送加密郵件，寄件者的電子郵件程式會使用收件者的公用憑證為郵件加密。這個公用的 X.509 憑證必須發行至 Office 365。
ms.openlocfilehash: caf5c3694034f3415b42f3b09302b6605fbf09cb
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970089"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>將使用者憑證同步至 Office 365 進行 S/MIME 處理

任何人都可以傳送受 S/MIME 保護的郵件在 Exchange Online 之前，請將適當的憑證必須設定。 若要傳送加密的郵件，透過 Exchange Online，寄件者的電子郵件應用程式會使用收件者的公用憑證來加密郵件。 這個公用的 X.509 憑證必須發行至 Office 365。

## <a name="to-sync-certificates-that-support-smime"></a>同步處理支援 S/MIME 的憑證

設定 S/MIME 的首要步驟，是在您的本機 Active Directory 網域服務中核發憑證並加以發行。 如需詳細資訊，請參閱 [Active Directory 憑證服務概觀](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))。

您的憑證發行後，使用 Azure AD Connect 工具來同步處理至 Office 365 的使用者資料從您的內部部署 Exchange 環境。 如需有關此程序的詳細資訊，請參閱[Azure AD Connect 同步處理： 了解及自訂同步處理](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。

以及其他目錄資料，針對 S/MIME 用途同步處理工具會同步處理每個使用者物件的**userCertificate**和**userSMIMECertificate**屬性，讓資料可用來簽署及加密郵件。

## <a name="more-information"></a>詳細資訊

[可用於訊息簽署和加密的 S/MIME](s-mime-for-message-signing-and-encryption.md)

[什麼是 Azure AD Connect？](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
