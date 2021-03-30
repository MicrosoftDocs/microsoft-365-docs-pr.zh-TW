---
title: OME) 版本比較的郵件加密 (
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 本文可協助說明不同版本的 Office 365 郵件加密之間的差異。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5c8b0852220b2144c4ab92ec9b692299c9d2c860
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408566"
---
# <a name="compare-versions-of-ome"></a>比較 OME 版本

> [!IMPORTANT]
> 在2021年2月28日，Microsoft 將取代對 Exchange Online 中的 AD RMS 的支援。 如果您已部署的混合式環境所在的 Exchange 信箱是線上的，而且您正在使用具有 Active Directory RMS 內部部署的 IRM，則您必須遷移至 Azure。 部署在 GCC 中型環境中的組織也會受到影響。 如需詳細資訊，請參閱本文中的「AD RMS 已過時，Exchange Online 中的 AD RMS。」。

本文的其餘部分會比較舊版 Office 365 郵件加密 (OME) 到新的 OME 功能和 Office 365 的高級郵件加密。 新功能是 OME 和 Information Rights Management (IRM) 的合併和更新版本。 此外，還會概括說明部署為 GCC 高的獨特特性。 這兩個可以在您的組織中共存。 如需新功能運作方式的詳細資訊，請參閱 [Office 365 Message Encryption (OME) ](ome.md)。

本文是有關 Office 365 郵件加密的更多系列文章的一部分。 本文適用于系統管理員和 ITPros。 如果您只是尋找傳送或接收加密郵件的相關資訊，請參閱 [Office 365 郵件加密 (OME ](ome.md) 中的文章清單) 並找出最符合您需求的文章。

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Exchange Online 中的 AD RMS 棄用情況概述

Exchange Online 包含資訊版權管理 (IRM) 功能，可提供線上和離線保護電子郵件訊息和附件。 根據預設，Exchange Online 會使用 Azure 資訊保護。 不過，您的組織可能已將 Exchange Online IRM 設定為使用內部部署 Active Directory Rights Management Service (AD RMS) 。 Exchange Online 中的 AD RMS 支援已退休。 相反地，Azure 資訊保護完全會取代 AD RMS。

若要評估此項是否會影響您的組織，請參閱 how [to 將 AD RMS 遷移至 Exchange Online 中的 AZURE rms](https://support.microsoft.com/help/5001237)。 本文提供遷移選項的建議。

## <a name="side-by-side-comparison-of-ome-features-and-capabilities"></a>OME 功能與功能的並列比較

|           **情況**           | **舊版 OME**    | **AD RMS 中的 IRM**        | **新的 OME 功能** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*傳送加密郵件*        |透過 Exchange 郵件流程規則|使用者從 Outlook desktop 或網頁型 Outlook 啟動;或透過 Exchange 郵件流程規則|使用者從 Outlook desktop、Mac 版 Outlook 或網頁型 Outlook 啟動;透過 Exchange 郵件流程規則 (也稱為傳輸規則) 和資料遺失防護 (DLP) |
|*Rights management 範本*       |   不適用      |[不要轉寄] 選項及自訂範本|[不要轉寄] 選項、[只供加密] 選項及自訂範本|
|*收件者類型*                   |內部和外部收件者|僅限內部收件者         |內部和外部收件者|
|*內部收件者的經驗*|收件者會收到 HTML 郵件，其可在網頁瀏覽器或行動裝置應用程式中下載及開啟|Outlook 用戶端中的原生內嵌體驗|使用 Outlook 用戶端的相同組織中收件者的原生內嵌經驗。  收件者可以使用 Outlook 以外的用戶端，從 OME 入口網站讀取郵件 () 不需要下載或應用程式。|
|*外部收件者的經驗*|收件者會收到 HTML 郵件，其可在網頁瀏覽器或行動裝置應用程式中下載及開啟|不適用|Microsoft 365 收件者的原生內聯體驗。 所有其他收件者都可以從 OME 入口網站讀取訊息 (不需要下載或應用程式) 。|
|*附件許可權*           |不限制附件|附件受到保護|[不要轉寄] 選項及自訂範本會保護附件。 系統管理員可以選擇是否要保護只供加密之選項的附件。|
|*在 BYOK) 支援中引入您自己的金鑰 (*|無                |無               |支援 BYOK          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>透過舊版 OME 的新 OME 功能的優點

新功能具有下列優點：

- 可使用 [只加密] 選項 (啟用安全共同作業) 、[不要轉寄] 選項及自訂限制的功能。
- 寄件者可以從 Outlook Desktop、Mac 版 Outlook 和 Outlook 網頁版用戶端上的新功能，以手動方式傳送郵件。
- Microsoft 365 收件者可在支援的 Outlook 用戶端中使用內嵌經驗。 或者，系統管理員可以選擇顯示 Microsoft 365 收件者的署名體驗。
- Microsoft 365 以外的帳戶（例如 Gmail、Yahoo 和 Microsoft 帳戶）與 OME 入口網站同盟，可提供更佳的使用者經驗給這些收件者。 所有其他身分識別使用一次性程式碼來存取加密的郵件。
- 系統管理員可以自訂署名，以及建立多個品牌範本。
- 系統管理員可以使用新功能撤銷加密的電子郵件。
- 新功能透過安全性與合規性中心提供詳細的使用方式報告 &amp; 。

## <a name="office-365-advanced-message-encryption-capabilities"></a>Office 365 Advanced Message Encryption 功能

Office 365 Advanced Message Encryption 在新的 OME 功能上提供其他功能。 您的組織中必須設定新的 Office 365 郵件加密功能，才能使用高級郵件加密功能。 此外，為了使用這些功能，收件者必須透過 OME 入口網站來查看及回復安全郵件。 高級功能包括：

- 郵件撤銷

- 郵件到期

- 多個品牌範本

在 GCC High 中不支援 Office 365 高級郵件加密。

如需使用高級郵件加密的詳細資訊，請參閱 [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)。

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>在 GCC 高部署中，Office 365 郵件加密的獨特特性

如果您打算在 GCC 高環境中使用 Office 365 郵件加密，有一些有關收件者經驗的獨特特性。

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>在 GCC 高層和 GCC 高收件者之間加密的電子郵件

寄件者可以手動加密 Outlook 中的電子郵件和 outlook 的 outlook 和 Mac 和 Outlook 網頁版，或組織可以設定使用 Exchange 郵件流程規則來加密電子郵件的原則。

在相同的 Outlook 中，在 Outlook 中的收件者會收到與其他所有使用者相同的內嵌讀取體驗。電腦和 Mac 和 Outlook 網頁版。

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>在 GCC 高層和非 GCC 高收件者之間加密的電子郵件

在 GCC 高界限內的寄件者可以傳送加密的電子郵件，反之亦然。

所有在 GCC （包括365商業性或 Yahoo 等電子郵件提供者的使用者）之外的收件者，都能接收包裝郵件。 此包裝郵件會將收件者重新導向至 OME 入口網站，以便收件者可以讀取和回復郵件。 這種情況也適用于擁有 GCC 高 OME 加密郵件的寄件者高。

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>舊版 OME 與相同承租人中的新功能的共存

您可以在同一個承租人中使用這兩種舊版 OME 和新功能。 身為系統管理員，您可以在建立郵件流程規則時，選擇您要使用的 OME 版本來執行此動作。

- 若要指定舊版的 OME，請使用 Exchange 郵件流程規則動作 **Apply 舊版的 OME**。

- 若要指定新功能，請使用 Exchange 郵件流程規則動作 **Apply Office 365 郵件加密和許可權保護**。

使用者可以使用 Outlook Desktop 中的新功能、Mac 版 Outlook 和網頁版的 Outlook，手動傳送已加密的郵件。

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>從舊版 OME 遷移至新功能

雖然這兩個版本的 OME 可以共存，我們強烈建議您編輯舊的郵件流程規則，使用規則動作套用 **舊版的 OME** ，以使用新功能。 更新這些規則若要使用郵件流程規則動作 **，請套用 Office 365 郵件加密和許可權保護**。 如需相關指示，請參閱 [定義郵件流程規則，以加密 Office 365 中的電子郵件訊息](define-mail-flow-rules-to-encrypt-email.md)。

## <a name="get-started-with-ome"></a>開始使用 OME

一般來說，您的組織會自動啟用新的 OME 功能。 如需組織內新 OME 功能的詳細資訊，請參閱 [設定新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。

如果您已啟用 Azure 資訊保護，系統就會自動為您的組織啟用舊版的 OME。 過去，即使未啟用 Azure 資訊保護，舊版 OME 也會正常運作。 這已不再是案例。

若要開始使用舊版 OME，若您已啟用 Azure 資訊保護，請設定使用規則動作的郵件流程規則：套用 **舊版的 OME**。 如需相關指示，請參閱 [定義郵件流程規則以加密電子郵件訊息](define-mail-flow-rules-to-encrypt-email.md)。