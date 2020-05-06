---
title: 將使用者憑證同步至 Office 365 進行 S/MIME 處理
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您將瞭解如何在 Exchange Online 中傳送與 S/MIME 保護的郵件，然後再將適當的憑證發佈到 Office 365。
ms.openlocfilehash: f9e0bef2f7d2125e2daeb86b3cf44ae433aae117
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035209"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>將使用者憑證同步至 Office 365 進行 S/MIME 處理

在 Exchange Online 中，任何人都可以傳送 S/MIME 保護的郵件，必須設定適當的憑證。 若要透過 Exchange Online 傳送加密郵件，寄件者的電子郵件應用程式會使用收件者的公用憑證來加密郵件。 這個公用的 X.509 憑證必須發行至 Office 365。

## <a name="to-sync-certificates-that-support-smime"></a>同步處理支援 S/MIME 的憑證

設定 S/MIME 的首要步驟，是在您的本機 Active Directory 網域服務中核發憑證並加以發行。 如需詳細資訊，請參閱 [Active Directory 憑證服務概觀](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))。

發行憑證後，請使用 Azure AD Connect 工具，將您的內部部署 Exchange 環境中的使用者資料同步處理至 Office 365。 如需此程式的詳細資訊，請參閱[AZURE AD Connect sync：瞭解和自訂同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)處理。

除了同步處理其他目錄資料之外，針對 S/MIME 目的，該工具會同步處理每個使用者物件的**userCertificate**和**userSMIMECertificate**屬性，因此可以使用這些資料來簽署和加密郵件。

## <a name="more-information"></a>詳細資訊

[可用於訊息簽署和加密的 S/MIME](s-mime-for-message-signing-and-encryption.md)

[何謂 Azure AD Connect？](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
