---
title: Microsoft 365 用戶端及服務應用程式支援
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 在本文中，尋找 Microsoft 365 用戶端和服務應用程式支援的詳細資料。
ms.openlocfilehash: 4e32e39281175ed66970a358ff632c2ddbb3ac1a
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097463"
---
# <a name="microsoft-365-client-and-services-app-support"></a>Microsoft 365 用戶端及服務應用程式支援

Microsoft 支援廣泛的安全性、驗證和合規性功能，以確保客戶資料安全，並可讓 IT 系統管理員在 Microsoft 365 系統管理中心中為其使用者自訂原則。 下列功能只是您可以設定的眾多企業功能的子集，具體取決於您的 Microsoft 365 訂閱。

## <a name="client-and-service-support"></a>用戶端和服務支援

### <a name="continuous-access-evaluation-preview"></a>連續存取評估 (預覽) 

連續存取評估的實施方式是讓服務（例如 Exchange Online、SharePoint 線上及小組）在 Azure Active Directory 中訂閱重要事件，以便在即時評估及強制執行這些事件。 重大事件評估不依賴條件式存取原則，所以可用於任何租使用者。

下列事件目前已評估：

- 刪除或停用使用者帳戶
- 變更或重設使用者的密碼
- 已為使用者啟用多重要素驗證
- 管理員明確撤銷使用者的所有重新整理權杖
- Azure AD 身分識別保護偵測到的使用者風險已提升

如需用戶端和服務應用程式支援的連續存取評估的詳細資訊，請參閱 [連續存取評估 (預覽) ](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)。

## <a name="client-support"></a>用戶端支援

### <a name="certificate-based-authentication"></a>憑證型驗證

憑證型驗證 (CBA) 是使用數位憑證來識別使用者、電腦或裝置，然後再將存取權授與資源、網路、應用程式或服務。 在使用者驗證中，它通常會與傳統方法（如使用者名稱和密碼）搭配部署。

有些傳統的解決方案只適用于使用者，例如生物特徵和單一時間密碼 (OTP) 。 使用憑證型驗證時，相同的解決方案可用於所有端點;使用者、裝置和不斷增加的網際網路 (IoT) 。

如需用戶端和服務應用程式支援之憑證型驗證的詳細資訊，請參閱 [Microsoft 365 用戶端應用程式支援：憑證型驗證](microsoft-365-client-support-certificate-based-authentication.md)。

### <a name="conditional-access"></a>條件式存取

條件式存取是 Azure Active Directory 用來將信號一起使用的工具，以作出決策，並強制執行組織存取原則。 條件式存取是在新的身分識別導向控制模型的核心。

條件式存取原則是用來授與資源存取權的 if 語句。 若使用者想要存取資源，使用者必須完成動作。 在進行原則訪問決策時，條件式存取可使用的常見信號包括：

- 使用者或群組成員資格
- IP 位置資訊
- 裝置資訊
- 應用程式資訊
- 即時及計算的風險偵測
- Microsoft Cloud App Security (MCAS)

進行這些存取決定時，原則可以採取不同的動作：

- 原則可以封鎖存取：此設定是最具限制性的動作，可防止使用者存取資源。
- 原則可以授與存取權：此設定的限制較少，但仍然需要下列一或多個選項：

    - 多重要素驗證
    - 要標示為相容的裝置
    - 裝置的混合式 Azure AD 已加入
    - 核准的用戶端應用程式
    - 已設定 (預覽的應用程式保護原則) 

如需用戶端和服務應用程式支援的條件式存取的相關資訊，請參閱：

- [Microsoft 365 用戶端應用程式支援：以裝置為基礎的條件式存取](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a>行動應用程式管理

使用者通常會從相同行動裝置存取組織和個人檔、電子郵件和資料。 這些裝置通常是由個人擁有，應設定為同時保護組織資料和使用者個人隱私權。

當使用者存取組織資料時，組織必須確信組織原則（例如設定原則及保護原則）得以套用，以協助保護裝置上的組織資料。 此外，使用者在裝置上的個人內容應該保留在組織的控制範圍之外。

若為組織管理的內容，您可以套用應用程式管理原則，以控制如何使用 Microsoft Intune 存取、共用和使用資料。 例如，支援下列動作：

- Remote 擦除受管理的組織內容 (也稱為組織資料) 
- 避免將組織內容粘貼到非組織位置
- 需要 PIN 才能存取組織內容
- 防止受管理的應用程式在越獄或根的裝置上執行
- 防止將組織內容儲存至未核准的雲端儲存提供者
- 防止未核准的內容傳輸到受管理的應用程式
- 只有在套用原則之後才允許存取組織內容
- 提供應用程式設定以管理應用程式的行為和設定
- 停用多身分識別功能或個人用途，將受管理的應用程式限制為已定義的身分識別。

如需使用 Microsoft Intune 行動應用程式管理的詳細資訊，請參閱 [什麼是 Microsoft intune 應用程式管理？](/mem/intune/apps/app-management)

### <a name="multi-factor-authentication"></a>多重要素驗證

[多重要素驗證 (MFA) 是一種電腦存取控制方法，在此方法中，使用者只有在成功顯示幾個個別的證據以驗證機制後，才會被授與存取權。 此方法通常至少使用下列兩種類別：

- 知識 (他們知道的內容) 
- 已擁有 () 的內容
- Inherence () 的內容

如需用戶端和服務應用程式支援之多重要素驗證的詳細資訊，請參閱 [Microsoft 365 用戶端應用程式支援：多重要素驗證](microsoft-365-client-support-multi-factor-authentication.md)。

### <a name="single-sign-on"></a>單一登入

單一登入 (SSO) 會在使用者登入 Azure Active Directory 中的應用程式時，加入安全性和便利性。 使用單一登入時，使用者可以使用一個帳戶登入一次，以存取內部部署 Active Directory 網域服務 (AD DS) 加入網域的裝置、軟體為服務 (SaaS) 應用程式，以及組織中的 web 應用程式。

如需有關用戶端和服務應用程式支援的單一登入的詳細資訊，請參閱 [Microsoft 365 用戶端應用程式支援：單一登入](microsoft-365-client-support-single-sign-on.md)。

## <a name="services-support"></a>服務支援

### <a name="modern-authentication"></a>新式驗證

新式驗證可讓客戶針對 Office 365 進行驗證的新案例，並針對租使用者系統管理員強制執行各 Office 365 租使用者的特定驗證需求，例如：

- 多重要素驗證支援與租使用者和服務的管理互動，以及與應用程式及其資料的使用者互動
- 條件式存取
- SAML-based 協力廠商身分識別提供者登入
- 個人電腦上的智慧卡登入
- 行動裝置上的憑證型驗證
- 不再需要透過基本驗證傳輸認證。

如需新式驗證服務支援的相關資訊，請參閱 [authentication 與 authorization](/azure/active-directory/develop/authentication-vs-authorization)。

### <a name="azure-active-directory-conditional-access"></a>Azure Active Directory 條件式存取

Azure Active Directory (Azure AD) 條件式存取規則，可讓客戶根據諸如裝置規範或網路位置等屬性，控制線上服務的存取權。 您可以使用下列解決方案：

- Azure AD 多重要素驗證-基礎的條件式存取
- Azure AD 位置基礎的條件式存取
- Azure AD 裝置基礎的條件式存取

Azure AD 條件式存取規則會套用於每個應用程式，客戶可以根據不同的條件來控制存取。 使用行動 [裝置管理 (MDM) 或 Intune](/mem/intune/fundamentals/what-is-device-management)，客戶必須能夠將 Microsoft 365 的存取許可權制為僅限使用組織裝置的使用者，或是已註冊個人裝置以進行管理的使用者。 例如，客戶可以設定條件式存取規則，以強制執行下列控制項：

- 只允許來自已加入網域或符合網域的裝置的存取權
- 針對所有 Exchange Online 服務存取強制執行多重要素驗證

如需 Azure Active Directory 條件式存取的相關資訊，請參閱 [什麼是條件式存取？](/azure/active-directory/conditional-access/overview)

### <a name="tls-12-support"></a>TLS 1.2 支援

若要為我們的客戶提供一流的加密，Microsoft 計畫停止支援傳輸層安全性 (TLS) 版本1.0 和 1.1 in Office 365 和 Office 365 GCC。

我們明白資料的安全性很重要，也承諾透明公開可能會影響 TLS 服務使用的變更。 建議所有用戶端伺服器及瀏覽器-伺服器的組合使用 TLS 1.2 (或更新版本) ，以維護 Office 365 服務的連線。 您可能必須更新特定的用戶端-伺服器及瀏覽器伺服器組合。

如需 TLS 1.2 支援和服務支援的詳細資訊，請參閱在 [office 365 和 office 365 GCC 中準備 TLS 1.2](/microsoft-365/compliance/prepare-tls-1.2-in-office-365)。
