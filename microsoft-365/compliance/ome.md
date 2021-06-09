---
title: 郵件加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 02/07/2020
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何在組織內部和外部的人員之間傳送和接收加密的電子郵件。
ms.openlocfilehash: 504fa9918636cd596cde0d242083ccb7b9817e69
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927711"
---
# <a name="message-encryption"></a>郵件加密

人員通常會使用電子郵件來交換機密資訊，例如財務資料、法律合約、機密產品資訊、銷售報告和預測、病患健康資訊，或是客戶和員工資訊。因此，信箱可能會成為大量潛在機密資訊的存放庫，而且資訊外洩可能會變成組織的嚴重威脅。

使用 Office 365 郵件加密，您的組織可在組織內外的人員之間傳送和接收加密的電子郵件。 Office 365 郵件加密可搭配 Outlook.com、Yahoo!、Gmail，以及其他電子郵件服務運作。 電子郵件加密可協助確保只有預定的收件者可以查看郵件內容。

## <a name="how-office-365-message-encryption-works"></a>Office 365 郵件加密的運作方式

本文的其餘部分適用于新的 OME 功能。

Office 365 郵件加密是一項線上服務，其基礎是 Microsoft Azure Rights Management (azure RMS) ，這是 azure 資訊保護的一部分。 此服務包含加密、身分識別和授權原則，以協助保護您的電子郵件。 您可以使用 rights management 範本、[ [不要轉寄] 選項](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)及 [ [僅限加密] 選項](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)來加密郵件。

然後，使用者可以使用這些選項來加密電子郵件訊息和各種附件。 如需支援的附件類型的完整清單，請參閱 [irm for email to email to email 中的「irm 原則所涵蓋的檔案類型](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)」。

您也可以以系統管理員身分定義郵件流程規則，以套用這種保護。 例如，您可以建立規則，要求所有傳送給特定收件者的郵件，或在主旨行中包含特定文字的郵件，也指定收件者無法複製或列印郵件的內容。

與舊版的 OME 不同的是，當您要將郵件傳送給組織或 Microsoft 365 以外的收件者時，新功能會提供統一的傳送者體驗。 此外，收件者會收到受保護的電子郵件訊息傳送至網頁上 Outlook 2016 或 Outlook 的 Microsoft 365 帳戶，不需要執行任何其他動作即可查看郵件。 它可順利運作。 使用其他電子郵件用戶端和電子郵件服務提供者的收件者也可獲得改進的體驗。 如需詳細資訊，請參閱[瞭解 Office 365 中的受保護郵件](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)，以及[如何開啟受保護的郵件](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)。

如需舊版 OME 與新 OME 功能之間差異的詳細清單，請參閱 [比較版本的 OME](ome-version-comparison.md)。

當某人傳送符合加密郵件流程規則的電子郵件時，會先加密郵件，然後再傳送郵件。 所有 Microsoft 365 使用 Outlook 用戶端來讀取郵件的使用者都可以接收加密和許可權保護郵件的本機、第一類讀取體驗，即使這些使用者與寄件者不在相同的組織中也是一樣。 支援的 Outlook 用戶端包括 Outlook 桌面、Outlook Mac、Outlook mobile on iOS 和 Android，以及網頁 Outlook （以前稱為 (Outlook Web App）。

已加密郵件的收件者收到加密或受版權保護的郵件傳送至其 Outlook .com、gmail 和 Yahoo 時，會收到一封包裝郵件，它會將其導向至 OME 入口網站，讓他們可以使用 Microsoft 帳戶、Gmail 或 Yahoo 認證輕鬆進行驗證。

在 Outlook 以外的用戶端上讀取加密或受版權保護的郵件的使用者也會使用 OME 入口網站來查看其所收到的加密和受版權保護的郵件。

如果受保護郵件的寄件者的 GCC 高，且收件者超出 GCC 高（包括商業性使用者、Outlook .com 使用者）和其他電子郵件提供者（例如 Gmail）的使用者，收件者會收到包裝郵件。 包裝郵件會將收件者導向至 OME 入口網站，以便收件者可以讀取和回復郵件。 否則，如果寄件者和收件者同時位於 GCC 高環境中，即使這些寄件者和收件者不在相同的組織中，則使用 Outlook 用戶端的收件者可以讀取郵件，以進行加密和許可權保護的郵件接收原始的第一類閱讀體驗。 如需 GCC 高的不同體驗的詳細資訊，請參閱[比較 OME 版本](ome-version-comparison.md)。

如需您可以使用 OME 加密之郵件和附件大小限制的相關資訊，請參閱[Exchange Online 限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Office 365 進階郵件加密如何在 OME 上運作

Office 365 進階郵件加密可讓您建立多個品牌範本，讓您可以微調對收件者郵件的控制權，並建立自訂商標體驗，以支援各種組織結構。

Microsoft 365 中的高級郵件加密可協助您符合法規遵從性義務，需要對外部收件者的加密電子郵件存取更靈活的控制。 在 Office 365 中使用高級郵件加密，以系統管理員的身分，您可以控制在組織外共用的敏感電子郵件，其方式是透過偵測敏感資訊類型的自動原則 (例如，PII、財務或健康情況 IDs) 或關鍵字，以透過安全的網頁入口網站來終止存取加密的電子郵件，以加強保護。 身為系統管理員，您可以隨時撤銷電子郵件存取權，以進一步控制透過 Microsoft 365 網頁入口網站存取的加密電子郵件。

郵件吊銷和到期僅適用于您的使用者傳送給組織外部收件者的電子郵件。 此外，收件者必須透過網頁入口網站來存取電子郵件。 為了確保收件者使用入口網站接收電子郵件，您可以設定套用包裝的自訂商標範本。 然後，您可以在郵件流程規則中套用署名範本。 如需高級郵件加密的詳細資訊，請參閱[Office 365 進階郵件加密](ome-advanced-message-encryption.md)。

## <a name="defining-rules-for-office-365-message-encryption"></a>為 Office 365 郵件加密定義規則

為 Office 365 郵件加密啟用新功能的一種方式是 Exchange Online 和 Exchange Online Protection 系統管理員定義郵件流程規則。 這些規則會判斷應加密哪些條件電子郵件。 為規則設定加密動作時，任何符合規則條件的郵件會先加密，然後再傳送。

郵件流程規則是彈性的，可讓您結合條件，讓您在單一規則中符合特定的安全性需求。 例如，您可以建立規則來加密所有包含指定關鍵字的郵件，並將其寄給外部收件者。 Office 365 郵件加密的新功能也會加密加密電子郵件收件者的回復。

如需如何建立郵件流程規則以利用新的 OME 功能的詳細資訊，請參閱[Define Office 365 郵件加密的規則](define-mail-flow-rules-to-encrypt-email.md)。

## <a name="get-started-with-the-new-ome-capabilities"></a>開始使用新的 OME 功能

如果您已準備好開始使用組織內的新 OME 功能，請參閱[設定新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>傳送、查看和回復加密的電子郵件

透過 Office 365 郵件加密，使用者可以從網頁上 Outlook 和 Outlook 傳送加密的電子郵件。 此外，系統管理員可以在 Microsoft 365 中設定郵件流程規則，以根據關鍵字比對或其他條件自動加密電子郵件。

組織內加密郵件的收件者可以在任何版本 Outlook 中順利讀取這些郵件，包括 Outlook 的電腦、Mac 版 Outlook、Outlook 網頁版、Outlook iOS，以及適用于 Android 的 Outlook。 在其他電子郵件用戶端上接收加密郵件的使用者，可在 OME 入口網站中查看郵件。

如需如何傳送和查看加密郵件的詳細指導，請參閱下列文章。

|請閱讀本文 .。。|如果您是 .。。|
|:-----|:-----|
|[深入瞭解 Office 365 中的受保護郵件](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|想要深入瞭解加密郵件的運作方式，以及您可以使用哪些選項的使用者。|
|[如何開啟受保護的郵件？](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|想要讀取已傳送給您之受保護郵件的使用者。 本文包含從不同的 Outlook 版本和不同的電子郵件帳戶（包括在諸如 gmail 和 yahoo！等 Microsoft 365 以外的帳戶）讀取郵件的相關資訊。 帳戶。|
|[在 Outlook 中傳送、查看和回復加密的郵件](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)|想要從 Outlook 傳送、查看或回復加密郵件的使用者。 即使您不是組織的成員，仍然會收到 Outlook 中傳送給您的加密郵件通知。 如需如何查看和回復從 Office 365 傳送之加密郵件的指示，請使用本文。|
|[傳送數位簽署或加密的郵件](https://support.microsoft.com/office/send-a-digitally-signed-or-encrypted-message-a18ecf7f-a7ac-4edd-b02e-687b05eff547)|想要使用 Mac 版 Outlook 傳送、查看或回復加密郵件的使用者。 本文也涵蓋如何使用 OME 以外的加密方法，例如 S/MIME。|
|[在您的 Android 裝置上查看加密郵件](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|在您的 Android 裝置上收到使用 Office 365 郵件加密加密郵件的使用者，您可以使用可用 OME 檢視器應用程式來查看郵件，並傳送加密的回復。 本文說明如何進行。|
|[在您的 iPhone 或 iPad 上查看加密的郵件](https://support.microsoft.com/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)|已收到使用 iPhone 或 iPad 上的 Office 365 郵件加密加密郵件的使用者，您可以使用可用 OME 檢視器應用程式來查看郵件，並傳送加密回復。 本文說明如何進行。|
||