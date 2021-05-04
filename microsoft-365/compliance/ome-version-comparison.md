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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 本文說明不同的 Office 365 郵件加密版本之間的差異。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 92beb3625c0b115fe77f1667a448bf0bf9589040
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760131"
---
# <a name="compare-versions-of-ome"></a>比較 OME 版本

> [!IMPORTANT]
> 在2021年2月28日，在 Exchange Online 中，Microsoft 已過時支援 AD RMS。 如果您已部署的混合式環境所在的 Exchange 信箱已線上，且您正在使用具有 Active Directory RMS 內部部署的 IRM，您將需要遷移至 Azure。 部署在 GCC 適中環境中的組織也會受到影響。 如需詳細資訊，請參閱本文中的「AD RMS 棄用 Exchange Online 中的概述」。

本文的其餘部分會將舊版 Office 365 郵件加密 (OME) 比較為新的 OME 功能及 Office 365 進階郵件加密。 新功能是 OME 和 Information Rights Management (IRM) 的合併和更新版本。 此外，還會概括說明部署至 GCC 高的獨特特性。 這兩個可以在您的組織中共存。 如需新功能運作方式的詳細資訊，請參閱[Office 365 郵件加密 (OME) ](ome.md)。

本文是有關 Office 365 郵件加密的更多系列文章的一部分。 本文適用于系統管理員和 ITPros。 如果您只是尋找傳送或接收加密郵件的相關資訊，請參閱[Office 365 郵件加密 (OME](ome.md)中的文章清單) 並找出最符合您需求的文章。

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Exchange Online 中的 AD RMS 棄用情況概述

Exchange Online 包含資訊版權管理 (IRM) 功能，可提供線上和離線保護電子郵件訊息和附件。 根據預設，Exchange Online 會使用 Azure 資訊保護。 不過，您的組織可能已設定 Exchange Online IRM 使用內部部署 Active Directory Rights Management 服務 (AD RMS) 。 Exchange Online 中的 AD RMS 支援已退休。 相反地，Azure 資訊保護完全會取代 AD RMS。

若要評估此項是否會影響您的組織，請參閱 how [to Exchange Online 中將 AD rms 遷移到 AZURE rms](https://support.microsoft.com/help/5001237)。 本文提供遷移選項的建議。

## <a name="side-by-side-comparison-of-ome-features-and-capabilities"></a>OME 功能與功能的並列比較

|           **情況**           | **舊版 OME**    | **AD RMS 中的 IRM**        | **新的 OME 功能** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*傳送加密郵件*        |透過 Exchange 郵件流程規則|使用者從 Outlook 桌面或網頁上的 Outlook 進行初始化;或透過 Exchange 郵件流程規則|使用者從網頁 Outlook 桌面、Mac 版 Outlook 或 Outlook 開始;透過 Exchange 郵件流程規則 (也稱為傳輸規則) 和資料遺失防護 (DLP) |
|*Rights management 範本*       |   不適用      |[不要轉寄] 選項及自訂範本|[不要轉寄] 選項、[只供加密] 選項及自訂範本|
|*收件者類型*                   |內部和外部收件者|僅限內部收件者         |內部和外部收件者|
|*內部收件者的經驗*|收件者會收到 HTML 郵件，其可在網頁瀏覽器或行動裝置應用程式中下載及開啟|Outlook 用戶端中的原生內嵌體驗|使用 Outlook 用戶端，在相同組織中收件者的原生內聯體驗。  收件者可以使用 Outlook 以外的用戶端，從 OME 入口網站讀取郵件 (不需要下載或 app) 。|
|*外部收件者的經驗*|收件者會收到 HTML 郵件，其可在網頁瀏覽器或行動裝置應用程式中下載及開啟|不適用|Microsoft 365 收件者的原生內聯體驗。 所有其他收件者都可以從 OME 入口網站讀取訊息 (不需要下載或應用程式) 。|
|*附件許可權*           |不限制附件|附件受到保護|[不要轉寄] 選項及自訂範本會保護附件。 系統管理員可以選擇是否要保護只供加密之選項的附件。|
|*在 BYOK) 支援中引入您自己的金鑰 (*|無                |無               |支援 BYOK          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>透過舊版 OME 的新 OME 功能的優點

新功能具有下列優點：

- 可使用 [只加密] 選項 (啟用安全共同作業) 、[不要轉寄] 選項及自訂限制的功能。
- 寄件者可以從 Outlook 桌面 Mac 版 Outlook 和 Outlook 網頁用戶端上的新功能，以手動方式傳送郵件。
- Microsoft 365 收件者可在支援的 Outlook 用戶端中使用內嵌經驗。 或者，系統管理員可以選擇顯示 Microsoft 365 收件者的署名體驗。
- Microsoft 365 以外的帳戶（如 Gmail、Yahoo 和 Microsoft 帳戶）與 OME 入口網站同盟，可提供更佳的使用者經驗給這些收件者。 所有其他身分識別使用一次性程式碼來存取加密的郵件。
- 系統管理員可以自訂署名，以及建立多個品牌範本。
- 系統管理員可以使用新功能撤銷加密的電子郵件。
- 新功能透過安全性與合規性中心提供詳細的使用方式報告 &amp; 。

## <a name="office-365-advanced-message-encryption-capabilities"></a>Office 365 進階郵件加密功能

Office 365 進階郵件加密提供新 OME 功能的其他功能。 您必須在組織中設定新的 Office 365 郵件加密功能，才能使用高級郵件加密功能。 此外，為了使用這些功能，收件者必須透過 OME 入口網站來查看及回復安全郵件。 高級功能包括：

- 郵件撤銷

- 郵件到期

- 多個品牌範本

GCC High 不支援 Office 365 進階郵件加密。

如需使用高級郵件加密的詳細資訊，請參閱[Office 365 進階郵件加密](ome-advanced-message-encryption.md)。

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>GCC 高部署中 Office 365 郵件加密的獨特特性

如果您打算在 GCC 高環境中使用 Office 365 郵件加密，則有一些有關收件者經驗的獨特特性。

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>GCC 高和 GCC 高收件者之間的加密電子郵件

寄件者可以在 Outlook 中手動加密電子郵件，以供 PC 和 Mac 和網頁上 Outlook，或是組織可以設定使用 Exchange 郵件流程規則來加密電子郵件的原則。

在 GCC 高接收內收件者在 Outlook 電腦及 Mac 的相同內嵌讀取體驗，以及 Outlook 網頁上的所有其他使用者。

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>GCC 高和非 GCC 高收件者之間的加密電子郵件

GCC 高範圍內的寄件者可以傳送加密的電子郵件，而不是 GCC 的高界限，反之亦然。

所有超出 GCC 高的收件者，包括商業性 Microsoft 365 使用者、Outlook .com 使用者，以及其他電子郵件提供者（例如 Gmail 和 Yahoo）的其他使用者接收包裝郵件。 此包裝郵件會將收件者重新導向至 OME 入口網站，以便收件者可以讀取和回復郵件。 這也適用于 GCC 高傳送 OME 加密郵件以外的寄件者 GCC 高。

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>舊版 OME 與相同承租人中的新功能的共存

您可以在同一個承租人中使用這兩種舊版 OME 和新功能。 身為系統管理員，您可以在建立郵件流程規則時，選擇您要使用的 OME 版本來執行此動作。

- 若要指定舊版的 OME，請使用 Exchange 郵件流程規則] 動作套用 **舊版的 OME**。

- 若要指定新功能，請使用 Exchange 郵件流程規則動作，套用 **Office 365 郵件加密和許可權保護**。

使用者可以使用 Outlook 桌面、Mac 版 Outlook 和 Outlook 網頁上的新功能，手動傳送已加密的郵件。

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>從舊版 OME 遷移至新功能

雖然這兩個版本的 OME 可以共存，我們強烈建議您編輯舊的郵件流程規則，使用規則動作套用 **舊版的 OME** ，以使用新功能。 更新這些規則若要使用郵件流程規則動作 **，請套用 Office 365 郵件加密和許可權保護**。 如需相關指示，請參閱[定義郵件流程規則，以加密 Office 365 中的電子郵件](define-mail-flow-rules-to-encrypt-email.md)。

## <a name="get-started-with-ome"></a>開始使用 OME

一般來說，您的組織會自動啟用新的 OME 功能。 如需組織內新 OME 功能的相關資訊，請參閱[Set up new Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。

如果您已啟用 Azure 資訊保護，系統就會自動為您的組織啟用舊版的 OME。 過去，即使未啟用 Azure 資訊保護，舊版 OME 也會正常運作。 這已不再是案例。

若要開始使用舊版 OME，若您已啟用 Azure 資訊保護，請設定使用規則動作的郵件流程規則：套用 **舊版的 OME**。 如需相關指示，請參閱 [定義郵件流程規則以加密電子郵件訊息](define-mail-flow-rules-to-encrypt-email.md)。