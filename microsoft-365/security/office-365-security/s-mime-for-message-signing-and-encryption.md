---
title: 可用於訊息簽署和加密在 Exchange Online 中的 S/MIME
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: 系統管理員可以了解如何在 Exchange Online 中使用 S/MIME。
ms.openlocfilehash: 64a76d1e9eebea86e548a06bf05d0030b0396d3d
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38032148"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>可用於訊息簽署和加密在 Exchange Online 中的 S/MIME

S/MIME （安全多用途網際網路郵件延伸） 是一種被廣為接受的方法 （或更精確的通訊協定） 傳送以數位方式簽署和已加密郵件。 S/MIME 可讓您將電子郵件加密和進行數位簽署。 對電子郵件使用 S/MIME 時，可讓收件者確定收件匣裡的郵件確實為寄件者所寄出。 也可讓收件者確定郵件來自特定的寄件者，而不是由其他人假冒寄件者。 為了達到此目的，S/MIME 提供密碼編譯的安全性服務，例如驗證、訊息完整性和來源不可否認性 (使用數位簽章)。 另外還可加強電子郵件通訊的隱私性和資料安全性 (使用加密)。 如需 S/MIME 在電子郵件方面的歷史和架構的完整背景資訊，請參閱＜[瞭解 S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)＞。

身為 Exchange Online 的系統管理員，您可以在組織中啟用信箱的 S/mime 安全性。 使用以下各連結主題以及 Exchange Online PowerShell 中的指導方針，來設定 S/MIME。 若要使用 S/MIME 支援的電子郵件用戶端中，您組織中的使用者必須進行簽署和加密發出的憑證和發佈至您內部部署 Active Directory 網域服務 (AD DS) 的資料。 AD DS 必須位於您可掌控的實際位置上的電腦，而不是在遠端設備或網際網路某處的雲端式服務上。 如需 AD DS 的詳細資訊，請參閱＜[Active Directory 網域服務](https://go.microsoft.com/fwlink/?LinkID=394064)＞。

## <a name="supported-scenarios-and-technical-considerations"></a>支援的案例和技術考量

您可以設定 S/MIME，若要使用任何下列的結束點：

- Outlook 2010 或更新版本

- 網頁型 Outlook (先前為 Outlook Web App)

- Exchange ActiveSync (EAS)

遵循與每個端點設定 S/MIME 的步驟是稍有不同。 一般而言，您必須執行下列步驟：

- 安裝以 Windows 為基礎的憑證授權單位，並且設定公開金鑰基礎結構，來核發 S/MIME 憑證。也支援協力廠商憑證提供者所發出的憑證。如需詳細資訊，請參閱 [Active Directory 憑證服務概觀](https://technet.microsoft.com/library/hh831740.aspx)。

- 在內部部署中發佈使用者憑證的**UserSMIMECertificate**和/或**UserCertificate**屬性中的 AD DS 帳戶。

- 在 Exchange Online 組織中，使用適當的 DirSync 版本，將使用者憑證從 AD DS 同步至 Azure Active Directory。這些憑證會從 Azure Active Directory 同步至 Exchange Online 目錄，並於加密寄給收件者的郵件時使用。

- 設定虛擬憑證集合以驗證 S/MIME。 驗證電子郵件，以確保它已由受信任的憑證簽署的簽章時，網頁型 Outlook 會使用這項資訊。

- 設定 Outlook 或 EAS 端點來使用 S/MIME。

> [!NOTE]
> 您無法在 Outlook 網頁版 Mac、 iOS、 Android 或其他非 Windows 裝置上安裝 S/MIME 控制項。 如需詳細資訊，請參閱[使用 outlook 網頁版中的 S/MIME 加密郵件](https://support.office.com/article/878c79fc-7088-4b39-966f-14512658f480)。

## <a name="setup-smime-with-outlook-on-the-web"></a>安裝 S/MIME 與 outlook 網頁版

Exchange online 與 outlook 網頁版設定 S/MIME 包含下列主要步驟：

1. [設定 Outlook 網頁版的 S/MIME 設定](configure-s-mime-settings-for-outlook-web-app.md)

2. [設定虛擬憑證集合以驗證 S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)

3. [將使用者憑證同步至 Office 365 進行 S/MIME 處理](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>相關郵件加密技術

當郵件安全性已變得更重要的是，系統管理員必須了解的原則和概念的安全通訊。 了解這是特別重要因為成長的各種不同的防護技術 （包括 S/MIME） 可供使用。 若要深入了解 S/MIME 及其於電子郵件上的運作，請參閱＜[瞭解 S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)＞。 各種加密技術可搭配運作，以為靜止和傳輸中的郵件提供保護。 S/MIME 可以與下列技術同時運作，但彼此並不具依存關係：

- **傳輸層安全性 (TLS)** 會加密電子郵件伺服器之間的通道或路由，以協助防止側錄和竊聽。

- **安全通訊端層 (SSL)** 會加密電子郵件用戶端與 Office 365 伺服器之間的連線。

- **BitLocker** 會加密資料中心硬碟上的資料，因此如果有人未獲授權就存取，便無法讀取資料。

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME 與 Office 365 郵件加密的比較

S/MIME 需要憑證和發佈基礎結構 (常用於企業對企業及企業對消費者情況)。在 S/MIME 中，由使用者控制密碼編譯金鑰，且在他們所傳送的每一封郵件上，都可選擇是否使用金鑰。電子郵件程式 (例如 Outlook) 會搜尋受信任的根憑證授單位，以進行數位簽署並驗證簽章。Office 365 郵件加密是系統管理員 (而不是個別使用者) 可設定的原則型加密服務，可將傳送給組織內外任何人的郵件加密。它是以 Azure 版權管理 (RMS) 為基礎的線上服務，且不依賴任何公開金鑰基礎結構。Office 365 郵件加密還提供其他功能，例如以組織的品牌來自訂郵件。如需 Office 365 郵件加密的相關資訊，請參閱 [Office 365 郵件加密](https://go.microsoft.com/fwlink/?LinkID=392525)。

## <a name="more-information"></a>詳細資訊

[網頁型 Outlook](https://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)

[安全郵件 (2000)](https://technet.microsoft.com/library/cc962043.aspx)
