---
title: 身分識別與裝置存取組式 - Microsoft 365 企業版
description: 說明 Microsoft 有關部署安全電子郵件、檔與應用程式政策與群組原則與群組原則的建議與核心概念。
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.prod: m365-security
ms.topic: article
ms.date: 09/29/2020
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-overview
ms.technology: mdo
ms.openlocfilehash: d8a4a3c519ab51a5aed6ad1819a67bf93df2cbb2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928911"
---
# <a name="identity-and-device-access-configurations"></a>身分識別與裝置存取設定

貴組織的現代化安全性周邊現在超越您的網路範圍，包括使用者從任何位置使用各種裝置存取雲端式應用程式。 您的安全性基礎結構需要判斷是否應該授予存取要求，以及哪些條件。

此決定應以該登錄的使用者帳戶、所使用的裝置、使用者用來存取的應用程式、提出存取要求的位置，以及要求之風險的評估為基礎。 這項功能有助於確保，只有經核准的使用者與裝置才可存取重要的資源。

本系列文章說明一組身分識別與裝置存取先決條件設定，以及一組 Azure Active Directory (Azure AD) 條件式存取、Microsoft Intune 和其他策略，以安全存取 Microsoft 365 企業雲端應用程式與服務、其他 SaaS 服務，以及以 Azure AD 應用程式 Proxy 發佈的內部部署應用程式。

身分識別與裝置存取設定和策略建議採用三種層級：基礎保護、機密保護，以及受到高度規範或分類資料之環境的保護。 這些層級及其對應的設定，可針對所有資料、身分識別和裝置，提供一致的保護層級。

這些功能及其建議：

- Microsoft 365 E3 和 Microsoft 365 E5 中支援。
- 與 Microsoft [安全](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) 分數及 Azure [AD](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)中的身分識別分數一致，將會為貴組織增加這些分數。
- 將可協助您執行 [這五個步驟來保護您的身分識別基礎結構](https://docs.microsoft.com/azure/security/azure-ad-secure-steps)。

如果貴組織有獨特的環境需求或複雜度，請使用這些建議做為起點。 不過，大部分的組織都可以以指定的方式執行這些建議。

> [!NOTE]
> Microsoft 也出售適用于 Office 365 訂閱 (EMS) Enterprise Mobility + Security。 EMS E3 和 EMS E5 功能相當於 Microsoft 365 E3 和 Microsoft 365 E5 中的功能。 請參閱 [EMS 方案](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) 以瞭解詳細資料。

## <a name="intended-audience"></a>預定物件

這些建議適用于熟悉 Microsoft 365 雲端生產力和安全性服務的企業架構和 IT 專業人員，包括 Azure AD (身分識別) 、Microsoft Intune (裝置管理) 和 Azure 資訊保護 (資料保護) 。

### <a name="customer-environment"></a>客戶環境

建議的策略適用于完全在 Microsoft 雲端中作業的企業組織，以及混合式身分識別基礎結構的客戶，這是與 Azure AD 租使用者同步處理內部部署 Active Directory 網域服務 (AD DS) 樹樹。

許多提供的建議僅仰賴具有身分識別 & 威脅防護附加元件、EMS E5 或 Azure Premium P2 授權之 Microsoft 365 E5、Microsoft 365 E3 所提供的服務。

對於沒有這些授權的組織，Microsoft 建議您至少執行安全性預設值，這是所有[](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)Microsoft 365 方案中包含的。

### <a name="caveats"></a>警告

貴組織可能受法規或其他合規性要求所規範，包括可能會要求您執行與這些建議群組原則不同的特定建議。 這些設定會建議過去未提供的使用情形控制項。 建議您使用這些控制措施，因為我們認為它們代表安全性與生產力的平衡。

我們已盡力處理各種組織保護需求，但無法針對所有可能的需求或貴組織的所有獨特層面負責。

## <a name="three-tiers-of-protection"></a>三層保護

大部分組織都有安全性和資料保護的相關特定需求。 根據產業部門和組織內的職責，這些需求會不同。 例如，您的法務部門與系統管理員可能會要求有關電子郵件通訊的額外安全性和資訊保護控制項，這是其他業務單位所不需要的。

每個產業也都有自己的一組特殊法規。 除了提供所有可能的安全性選項清單，或是各產業區段或工作功能的建議外，我們針對三種不同的安全性和保護層級提供了建議，這些等級可以根據您的需求細微程度來申請。

- **基礎保護**：建議您建立最低標準來保護資料，以及存取資料的身分和裝置。 您可以遵循這些比較基準建議，提供符合許多組織需求的強預設保護。
- **機密保護**：有些客戶的資料子集必須在較高層級受到保護，或者可能會要求所有資料在較高層級受到保護。 您可以對 Microsoft 365 環境中所有或特定資料集套用進一步的保護。 建議保護以可比較的安全性層級存取敏感性資料的身分識別和裝置。
- **受到高度規範**：有些組織可能只有少量的資料受到高度分類、構成交易秘訣或受到規範的資料。 Microsoft 所提供的功能可協助組織符合這些需求，包含針對身分識別和裝置新增的保護。

![安全性圓錐圖 - 所有>客戶>特定客戶。 將應用程式廣泛應用至特定應用程式](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

本指南會針對這些保護層級的每個層級，顯示如何針對身分定義和裝置執行保護。 使用此指引為貴組織的起點，並調整政策以符合貴組織的特定需求。

請務必在您的資料、身分識別和裝置之間，使用一致層級的保護。 例如，如果您執行此指引，請務必以相當等級保護您的資料。

**Microsoft 365** 架構模型的身分識別與裝置保護能顯示哪些功能可比對。

[![Microsoft 365 海報身分識別與裝置保護的拇指影像](../../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br> [以 PDF 格式查看](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \|[以 PDF 格式下載](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \|[以 Visio 下載](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

此外，請參閱資料隱私權 [法規的](../../solutions/information-protection-deploy.md) 部署資訊保護解決方案，以保護 Microsoft 365 中儲存的資訊。

## <a name="security-and-productivity-trade-offs"></a>安全性與生產力的取捨

要實施任何安全性策略，需要在安全性與生產力之間進行比對。 評估每個決策如何影響安全性、功能和容易使用性，會很有説明。

![安全性三重平衡：安全性、功能和便於使用。](../../media/microsoft-365-policies-configurations/security-triad.png)

提供的建議是以下列原則為基礎：

- 認識您的使用者，並靈活處理其安全性和功能需求。
- 及時申請安全性原則，確保原則具有意義。

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>身分識別與裝置存取保護的服務與概念

Microsoft 365 企業版專為大型組織設計，讓每個人都能發揮創意，並安全地共同作業。

本節提供對身分識別與裝置存取非常重要之 Microsoft 365 服務和功能概觀。

### <a name="azure-ad"></a>Azure AD

Azure AD 提供完整的身分識別管理功能套件。 我們建議您使用這些功能來安全存取。

|功能|描述|授權|
|---|---|---|
|[多重要素驗證 (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|MFA 需要使用者提供兩種形式的驗證，例如使用者密碼以及 Microsoft Authenticator App 的通知或電話。 MFA 大幅縮減了遭竊的認證可能會用來存取您環境的風險。 Microsoft 365 會針對 MFA 型的登錄使用 Azure AD 多重要素驗證服務。|Microsoft 365 E3 或 E5|
|[條件式存取](/azure/active-directory/conditional-access/overview)|Azure AD 會評估使用者登錄的條件，並使用條件式存取策略來判斷允許的存取。 例如，在本指南中，我們會顯示如何建立條件式存取政策，要求裝置符合機密資料的存取要求。 這可大幅降低駭客以自己的裝置和遭竊的認證存取您機密資料的風險。 它也保護裝置上的機密資料，因為裝置必須符合健康及安全性的特定需求。|Microsoft 365 E3 或 E5|
|[Azure AD 群組](/azure/active-directory/fundamentals/active-directory-manage-groups)|條件式存取策略、使用 Intune 的裝置管理，甚至是貴組織檔案和網站的許可權，都仰賴指派給使用者帳戶或 Azure AD 群組。 建議您建立與要實施之保護層級對應的 Azure AD 群組。 例如，您的高職員工可能會是駭客的較高值目標。 因此，將這些員工的使用者帳戶新增到 Azure AD 群組，並將此群組指派給條件式存取策略及其他可針對存取強制執行較高層級保護的其他策略，是有意義的方法。|Microsoft 365 E3 或 E5|
|[裝置註冊](/azure/active-directory/devices/overview)|您將裝置註冊到 Azure AD 以建立裝置身分識別。 此身分識別會用來驗證使用者何時要登錄的裝置，以及使用需要加入網域或符合規範之電腦的條件式存取原則。 針對此指引，我們會使用裝置註冊來自動註冊加入網域的 Windows 電腦。 裝置註冊是使用 Intune 管理裝置的先決條件。|Microsoft 365 E3 或 E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|可讓您偵測會影響貴組織身分識別的潛在弱點，並設定自動化補救政策，以低、中、高登錄風險與使用者風險。 此指引將依據此風險評估來為多重要素驗證適用條件式存取原則。 此指引也包含條件式存取政策，要求使用者在偵測到其帳戶有高風險活動時變更密碼。|Microsoft 365 E5、具有身分識別 &威脅防護附加元件、EMS E5 或 Azure Premium P2 授權的 Microsoft 365 E3|
|[自助式密碼重設 (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|您可以讓使用者安全地重設密碼，而不需要技術支援中心介入，方法是提供系統管理員可控制的多種驗證方法驗證。|Microsoft 365 E3 或 E5|
|[Azure AD 密碼保護](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)|偵測並封鎖已知的弱式密碼及其變體，以及貴組織特有的其他弱式字詞。 預設全域禁用密碼清單會自動套用至 Azure AD 租用戶中的所有使用者。 您可以在自訂禁用密碼清單中定義其他條目。 使用者變更或重設密碼時，系統會檢查這些禁用密碼清單，以強制使用強式密碼。|Microsoft 365 E3 或 E5|
|

以下是身分識別與裝置存取的元件，包括 Intune 和 Azure AD 物件、設定及子服務。

![身分識別與裝置存取的元件](../../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) 是 Microsoft 的雲端行動裝置管理服務。 本指引會建議使用 Intune 管理 Windows 電腦裝置，並建議裝置合規性政策組組。 Intune 會判斷裝置是否符合規範，並將此資料傳送至 Azure AD，以用於應用程式條件式存取原則。

#### <a name="intune-app-protection"></a>Intune 應用程式保護

[Intune 應用程式](https://docs.microsoft.com/intune/app-protection-policy) 保護原則可用來保護貴組織行動裝置 App 的資料，包含或不將裝置註冊到管理中。 Intune 可協助保護資訊、確保您的員工仍可保持生產力，以及防止資料遺失。 您可以實施應用程式層級策略來限制公司資源的存取權，並控制 IT 部門的資料。

本指南將指導您建立建議政策，以強制使用核准的應用程式，以及決定這些應用程式可如何與商務資料一起使用。

### <a name="microsoft-365"></a>Microsoft 365

本指南將引導您執行一組保護 Microsoft 365 雲端服務存取權的策略，包括 Microsoft Teams、Exchange Online、SharePoint Online 和商務用 OneDrive。 除了執行這些策略之外，建議您也使用這些資源提高租使用者的保護層級：

- [設定租用戶以提高安全性](tenant-wide-setup-for-increased-security.md)

  適用于您租使用者基準安全性的建議。

- [安全性藍圖：前 30 天、90 天及之後的主要優先順序](security-roadmap.md)

  包含記錄、資料管理、系統管理員存取和威脅防護的建議。

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 和 Microsoft 365 Apps 企業版

Windows 10 與 Microsoft 365 Apps 企業版是電腦建議使用的用戶端環境。 建議您使用 Windows 10，因為 Azure 的設計目的是為內部部署和 Azure AD 提供最順暢的體驗。 Windows 10 也包含可透過 Intune 管理的進位安全性功能。 適用于企業的 Microsoft 365 應用程式包含最新版本的 Office 應用程式。 這些驗證會使用新式驗證，更加安全，也要求使用條件式存取。 這些應用程式也包含增強的安全性與合規性工具。

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>將這些功能適用于這三種保護層級

下表摘要列出在三種保護層級中使用這些功能的建議。

|保護機制|基準|敏感性|高管制|
|---|---|---|---|
|**強制執行 MFA**|在中或以上的登入風險上|在低或以上的登入風險上|在所有新的工作階段上|
|**強制執行密碼變更**|針對高風險使用者|針對高風險使用者|針對高風險使用者|
|**強制執行 Intune 應用程式保護**|是|是|是|
|**針對組織擁有的裝置強制執行 Intune 註冊**|需要符合規範或已加入網域之電腦，但允許攜帶您自己的裝置 (使用) 與平板電腦|需要符合規範或加入網域的裝置|需要符合規範或加入網域的裝置|
|

## <a name="device-ownership"></a>裝置擁有權

上表反映許多組織支援混合使用組織所擁有裝置以及個人或 BYOD 的趨勢，以提升員工行動生產力。 Intune 應用程式保護政策可確保電子郵件受到保護，避免在組織擁有的裝置和 BYODS 上從 Outlook 行動裝置 App 和其他 Office 行動裝置 App 中外泄。

我們建議由 Intune 或已加入網域的裝置管理，以申請額外的保護及控制。 根據資料敏感度，貴組織可能會選擇不允許特定使用者人口或特定應用程式的 BYOD。

## <a name="deployment-and-your-apps"></a>部署和您的應用程式

在針對 Azure AD 整合式應用程式，在設定檔和推出身分識別與裝置存取組式之前，您必須先：

- 決定貴組織中要保護哪些應用程式。
- 分析此應用程式清單，以判斷提供適當保護層級的一群組原則。

  由於管理可能會變得棘手，因此您不應該為應用程式建立每組不同的策略。 Microsoft 建議您針對相同的使用者，將相同的保護需求相同的應用程式分組。

  例如，您可以建立一組原則，包含所有使用者的所有 Microsoft 365 應用程式以執行比較基準保護，以及第二組適用于所有機密應用程式原則 ，例如人力資源部門或財務部門使用的應用程式，然後套用至這些群組。

一旦決定要保護之應用程式的一群組原則後，再逐漸將政策推出給使用者，解決一邊的問題。

例如，設定將僅用於 Exchange Online 的所有 Microsoft 365 應用程式使用，以及 Exchange 的其他變更。 將這些建議推出給使用者，並解決任何問題。 然後，新增 Teams 和其額外變更，然後將它推出給使用者。 然後，新增 SharePoint 及其額外變更。 繼續新增其餘的應用程式，直到您放心地設定這些比較基準策略以包含所有 Microsoft 365 應用程式。

同樣地，針對您敏感性的應用程式，請建立一群組原則，並一次新增一個應用程式，並解決任何問題，直到問題全部包含在機密應用程式策略集內。

Microsoft 建議您不要建立適用于所有應用程式原則集，因為這可能會導致一些非預期的設定。 例如，封鎖所有應用程式的政策可能會讓系統管理員無法進入 Azure 入口網站，而且無法針對 Microsoft Graph 等重要端點進行排除。

## <a name="steps-in-the-process-of-configuring-identity-and-device-access"></a>身分識別與裝置存取的安裝步驟

![設定身分識別與裝置存取權的步驟。](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. 設定先決條件身分識別功能及其設定。
2. 設定通用身分識別及存取條件式存取策略。
3. 為來賓和外部使用者設定條件式存取政策。
4. 為 Microsoft 365 雲端應用程式設定條件式存取策略，例如 Microsoft Teams、Exchange Online 和 SharePoint。

在您完成身分識別與裝置存取之後，請參閱 [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2) 功能部署指南，以取得可考慮額外功能的階段檢查清單，以及 [Azure AD](https://docs.microsoft.com/azure/active-directory/governance/) 身分識別控控來保護、監控及稽核存取。

## <a name="next-step"></a>下一步

[要執行身分識別與裝置存取策略的先決條件](identity-access-prerequisites.md)
