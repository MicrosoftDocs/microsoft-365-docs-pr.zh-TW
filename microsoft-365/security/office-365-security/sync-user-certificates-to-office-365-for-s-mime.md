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
ms.openlocfilehash: 7b42f757ade54e362afc65f920096252bf69eb31
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38030837"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>將使用者憑證同步至 Office 365 進行 S/MIME 處理

任何人都可以傳送受 S/MIME 保護的郵件在 Exchange Online 之前，請將適當的憑證必須設定。 若要傳送加密的郵件，透過 Exchange Online，寄件者的電子郵件應用程式會使用收件者的公用憑證來加密郵件。 這個公用的 X.509 憑證必須發行至 Office 365。

## <a name="to-sync-certificates-that-support-smime"></a>同步處理支援 S/MIME 的憑證

設定 S/MIME 的首要步驟，是在您的本機 Active Directory 網域服務中核發憑證並加以發行。 如需管理 Exchange Server 中的憑證的詳細資訊，請參閱[Digital Certificates and SSL](https://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx)。

您的憑證發行後，使用 Azure Active Directory 同步處理工具來同步處理至 Office 365 的使用者資料從您的內部部署 Exchange 環境。 如需有關此程序的詳細資訊，請參閱[DirSync： 目錄同步處理工具版本的版本歷程記錄](https://go.microsoft.com/fwlink/p/?LinkId=392587)。

以及其他目錄資料，針對 S/MIME 用途同步處理工具會同步處理每個使用者物件的**userCertificate**和**userSMIMECertificate**屬性，讓資料可用來簽署及加密郵件。

## <a name="more-information"></a>詳細資訊

[可用於訊息簽署和加密的 S/MIME](s-mime-for-message-signing-and-encryption.md)

[Azure Active Directory 同步處理工具](https://go.microsoft.com/fwlink/p/?LinkId=392587)
