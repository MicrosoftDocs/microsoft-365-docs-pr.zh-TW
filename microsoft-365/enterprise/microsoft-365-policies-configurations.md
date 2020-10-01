---
title: 身分識別與裝置存取設定-適用于企業的 Microsoft 365
description: 說明部署安全電子郵件、檔及應用程式原則及設定的 Microsoft 建議與核心概念。
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: b6e961dc8e7de6bfaf16508fa6c70f8a90fa4080
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327435"
---
# <a name="identity-and-device-access-configurations"></a>身分識別與裝置存取設定

組織目前的安全性周邊環境會延伸至您的網路以外，以包含從各種裝置的任何位置存取雲端架構應用程式的使用者。 您的安全性基礎結構需要判斷是否應授與指定的存取要求，以及在哪些條件下。 

這項判斷應該是根據登入的使用者帳戶、正在使用的裝置、使用者正在使用的應用程式、建立存取要求的位置，以及要求的風險評估。 這項功能有助於確保，只有經核准的使用者與裝置才可存取重要的資源。

本系列文章說明一組身分識別與裝置存取的必要條件設定，以及一組 Azure Active Directory (Azure AD) 條件式存取、Microsoft Intune 及其他原則，以保護對 Microsoft 365 for enterprise cloud app 和服務、其他 SaaS 服務，以及使用 Azure AD 應用程式 Proxy 發佈的內部部署應用程式的存取。

身分識別與裝置存取設定和原則，可在三個層級中使用：基準保護、機密保護，以及針對具有高管制或保密資料之環境的保護。 這些層級及其對應的設定，可針對所有資料、身分識別和裝置，提供一致的保護層級。

這些功能及其建議：

- 支援 Microsoft 365 E3 和 Microsoft 365 E5。
- 會與 [Microsoft 安全分數](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) 和 [Azure AD 中的身分識別分數](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)對齊，並且會為您的組織增加這些分數。
- 會協助您執行下列 [五個步驟，以保護您的身分識別基礎結構](https://docs.microsoft.com/azure/security/azure-ad-secure-steps)。

如果您的組織有獨特的環境需求或複雜性，請使用這些建議做為開始點。 不過，大多陣列織可依照預定的方式來執行這些建議。

>[!Note]
>Microsoft 也會為 Office 365 訂閱銷售企業行動 + 安全性 (EMS) 授權。 EMS E3 和 EMS E5 功能相當於 Microsoft 365 E3 和 Microsoft 365 E5 中的功能。 如需詳細資訊，請參閱 [EMS 方案](https://www.microsoft.com/en-us/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) 。
>

## <a name="intended-audience"></a>目標物件

這些建議適用于企業架構師和 IT 專業人員，熟悉 Microsoft 365 雲端生產力與安全性服務，其中包括 Azure AD (身分識別) 、Microsoft Intune (裝置管理) ，以及 Azure 資訊保護 (資料保護) 。

### <a name="customer-environment"></a>客戶環境

建議的原則適用于完全在 Microsoft 雲端內運作的企業組織，以及具有混合式身分識別基礎結構的客戶，也就是內部部署 Active Directory 網域服務 (AD DS) 樹系，與 Azure AD 租使用者同步。

所提供的許多建議，都依賴只有 Microsoft 365 E5 才能使用的服務、使用身分識別 & 威脅防護附加元件、EMS E5 或 Azure Premium P2 授權的 Microsoft 365 E3。

對於沒有這些授權的組織，Microsoft 建議您至少執行 [安全性預設值，這些預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)包含在所有 Microsoft 365 方案中。 

### <a name="caveats"></a>警告

您的組織可能會受限於法規或其他法規遵從性需求，包括可能要求您套用與這些建議設定分開之原則的特定建議。 這些設定會建議過去未提供的使用情形控制項。 我們建議使用這些控制措施，因為我們相信它們代表安全性和生產力之間的平衡。  

我們已盡力考慮各種組織保護需求，但我們不能考慮所有可能的需求，或組織的所有獨有方面。

## <a name="three-tiers-of-protection"></a>三種保護層級

大部分組織都有安全性和資料保護的相關特定需求。 根據產業部門和組織內的職責，這些需求會不同。 例如，您的法律部門和系統管理員可能需要其他的安全性和資訊保護，而不是其他商業單位所需的電子郵件對應。 

每個產業也都有自己的一組特殊法規。 建議針對三種不同的安全性和保護層級，而不是提供所有可能安全性選項的清單，也是針對每個行業區段或工作功能所提供的建議。

- **基準保護**：我們建議您建立保護資料的最低標準，以及存取資料的身分識別和裝置。 您可以遵循下列基準建議，提供符合許多組織需求的強預設保護。
- **敏感保護**：有些客戶的資料子集必須在較高的層級加以保護，否則可能需要以較高的層次保護所有的資料。 您可以將增強的保護套用至 Microsoft 365 環境中的所有或特定資料集。 建議保護以可比較的安全性層級存取敏感性資料的身分識別和裝置。  
- **高度管制**：有些組織可能會具有少量的資料，以高度分類，組成交易機密或管制資料。 Microsoft 所提供的功能可協助組織符合這些需求，包含針對身分識別和裝置新增的保護。

![安全性錐-所有客戶 > 某些客戶 > 特定客戶。 特定應用程式的廣泛應用程式](../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

本指南說明如何針對每一種保護層級的身分識別和裝置執行保護。 使用此指導方針做為組織的起點，並調整原則，以符合組織的特定需求。

請務必在您的資料、身分識別和裝置之間，使用一致層級的保護。 例如，如果您要執行此指導方針，請務必保護您的資料，以同等的層次。 

Microsoft 365 架構模型的身分 **識別與裝置保護** 會顯示哪些功能是可比較的。

[![Microsoft 365 海報的身分識別和裝置保護的縮圖影像](../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br/>  [以 PDF 格式查看](../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \|[以 PDF 格式下載](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \|[下載為 Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

此外，請參閱 [部署資訊保護以取得資料隱私權法規](../solutions/information-protection-deploy.md) 解決方案，以保護儲存在 Microsoft 365 中的資訊。

## <a name="security-and-productivity-trade-offs"></a>安全性與生產力的取捨

實施任何安全性策略時，必須權衡安全性和生產力。 評估每個決策對安全性、功能和易用性的影響。

![安全性三角平衡安全性、功能和易用性。](../media/microsoft-365-policies-configurations/security-triad.png)

提供的建議是以下列原則為基礎：

- 知道您的使用者，並根據安全性和功能需求進行彈性。
- 及時套用安全性原則，並確保其有意義。

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>身分識別與裝置存取保護的服務和概念

適用于企業的 Microsoft 365 是針對大型組織設計的，可讓每個人都具有創造性且安全地協同運作。

本節概述對身分識別與裝置存取非常重要的 Microsoft 365 服務和功能。

### <a name="azure-ad"></a>Azure AD

Azure AD 提供完整的身分識別管理功能套件。 我們建議使用這些功能來保護存取。

| 功能 | 描述 | 授權 |
|:-------|:-----|:-------|
| [多重要素驗證 (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks) | MFA 要求使用者提供兩種形式的驗證，例如使用者密碼加上 Microsoft 驗證應用程式或電話的通知。 MFA 大幅降低可供盜竊之認證存取您環境的風險。 Microsoft 365 使用 Azure Multi-Factor 驗證服務進行 MFA 型登入。 | Microsoft 365 E3 或 E5 |
| [條件式存取](/azure/active-directory/conditional-access/overview) | Azure AD 評估使用者登入的條件，並使用條件式存取原則來決定允許的存取。 例如，在此指導中，我們會告訴您如何建立條件式存取原則，以要求存取機密資料的裝置合規性。 這會極大降低具有自身裝置和盜竊認證的駭客可以存取您機密資料的風險。 它也會保護裝置上的機密資料，因為裝置必須符合健康和安全性的特定需求。 | Microsoft 365 E3 或 E5 |
| [Azure AD 群組](/azure/active-directory/fundamentals/active-directory-manage-groups) | 條件式存取原則、具有 Intune 的裝置管理，以及對您組織中檔案和網站的許可權，都依賴指派給使用者帳戶或 Azure AD 群組。 建議您建立對應至您所實施之保護層級的 Azure AD 群組。 例如，您的 executive 人員很可能是駭客的高價值目標。 因此，您可以將這些員工的使用者帳戶新增至 Azure AD 群組，並將此群組指派給條件式存取原則及其他強制進行存取保護等級的原則。 | Microsoft 365 E3 或 E5 |
| [裝置註冊](/azure/active-directory/devices/overview) | 您可以在 Azure AD 中註冊裝置，以建立裝置的身分識別。 此身分識別是用來在使用者登入並套用需要加入網域或合規的電腦的條件式存取原則時，用來驗證裝置。 針對此指南，我們使用裝置註冊功能自動註冊加入網域的 Windows 電腦。 裝置註冊是使用 Intune 管理裝置的必要條件。 | Microsoft 365 E3 或 E5 |
| [Azure AD Identity Protection](/azure/active-directory/identity-protection/overview) | 可讓您偵測影響組織之身分識別的潛在弱點，並設定自動修正原則為低、中、高的登入風險和使用者風險。 本指南取決於此風險評估，針對多重要素驗證套用條件式存取原則。 本指南也包含條件式存取原則，需要使用者在其帳戶中偵測到高風險的活動時變更其密碼。 | Microsoft 365 E5，使用 Identity & 威脅防護附加元件、EMS E5 或 Azure Premium P2 授權的 Microsoft 365 E3 |
| [自助式密碼重設 (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks) | 可讓您的使用者安全地重設其密碼，而不需要協助桌面的干預，只要提供系統管理員可控制的多個驗證方法的驗證。 | Microsoft 365 E3 或 E5 |
| [Azure AD 密碼保護](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) | 偵測並封鎖已知弱密碼和其變種，以及組織特有的其他弱字詞。 預設全域禁用密碼清單會自動套用至 Azure AD 租用戶中的所有使用者。 您可以在自訂禁用密碼清單中定義其他條目。 使用者變更或重設密碼時，系統會檢查這些禁用密碼清單，以強制使用強式密碼。 |  Microsoft 365 E3 或 E5 |
||||

![身分識別與裝置存取的元件。](../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) 是 Microsoft 雲端型行動裝置管理服務。 本指南建議使用 Intune 的 Windows 電腦裝置管理，並建議裝置合規性原則設定。 Intune 會判斷是否符合裝置，並將此資料傳送至 Azure AD，以在套用條件式存取原則時使用。

#### <a name="intune-app-protection"></a>Intune 應用程式保護

您可以使用[Intune 應用程式保護](https://docs.microsoft.com/intune/app-protection-policy)原則，在行動應用程式中保護您組織的資料，但不需要將裝置登記至管理。 Intune 可協助保護資訊，確保您的員工仍可生產力，並防止資料遺失。 透過實施應用層級原則，您可以限制公司資源的存取權，並將資料放在 IT 部門的控制中。

本指南說明如何建立建議原則，以強制使用已核准的應用程式，以及決定如何將這些應用程式與您的商務資料搭配使用。

### <a name="microsoft-365"></a>Microsoft 365

本指南將告訴您如何實施一組原則，以保護 Microsoft 365 雲端服務（包括 Microsoft 團隊、Exchange Online、SharePoint 線上和商務 OneDrive）的存取權。 除了執行這些原則之外，也建議您使用下列資源提升租使用者的保護層級：

- [設定租用戶以提高安全性](../security/office-365-security/tenant-wide-setup-for-increased-security.md)

  適用于租使用者之基準安全性的建議。

- [安全性藍圖：前30天、90天和之後的最高優先順序](../security/office-365-security/security-roadmap.md)

  包括記錄、資料管理、系統管理存取和威脅防護的建議。

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 和 Microsoft 365 Apps 企業版

Windows 10 搭配使用 Microsoft 365 應用程式的企業版是電腦的建議用戶端環境。 由於 Azure 設計為同時提供內部部署和 Azure AD 的最平滑體驗，因此建議採用 Windows 10。 Windows 10 也包含可透過 Intune 管理的高級安全性功能。 Microsoft 365 應用程式企業版包含最新版的 Office 應用程式。 這些使用的是新式驗證，也就是更安全，也是條件式存取的必要條件。 這些應用程式也包含增強的安全性和符合性工具。

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>跨三種保護層級應用這些功能

下表摘要說明在三種保護層級使用這些功能的建議。

|保護機制|基準|敏感性|高管制|
|:-------------------|:-------|:--------|:---------------|
|**強制執行 MFA**|在中或以上的登入風險上|在低或以上的登入風險上|在所有新的工作階段上|
|**強制執行密碼變更**|高風險使用者的|高風險使用者的|高風險使用者的|
|**強制執行 Intune 應用程式保護**|是|是|是|
|**針對組織擁有的裝置強制執行 Intune 登記**|需要相容或加入網域的電腦，但允許附帶裝置 (BYOD) 電話和平板電腦|需要相容或加入網域的裝置|需要相容或加入網域的裝置|

## <a name="device-ownership"></a>裝置擁有權

上表反映許多組織支援混合使用組織的裝置的趨勢，以及個人或 BYODs，以在整個工作力內啟用行動生產力。 Intune 應用程式保護原則可確保電子郵件在組織所擁有的裝置和 BYODs 上，避免從 Outlook 行動應用程式和其他 Office 行動應用程式 exfiltrating 出。  

建議以 Intune 或加入網域的方式管理組織擁有的裝置，以套用其他的保護和控制。 根據資料敏感度，您的組織可以選擇不允許特定使用者人口或特定應用程式的 BYODs。

## <a name="deployment-and-your-apps"></a>部署和您的應用程式

在設定及推出 Azure AD 整合應用程式的身分識別與裝置存取設定之前，您必須： 

- 決定您要保護組織中使用的應用程式。 
- 分析此應用程式清單，以決定提供適當保護等級的原則集合。 

  您不應為應用程式建立個別的原則集合，因為其管理可能會變得麻煩。 Microsoft 建議您將相同使用者的相同保護需求群組為您的應用程式。 

  例如，您可以使用一組原則，其中包括所有使用者的基準保護的所有 Microsoft 365 應用程式，以及所有機密應用程式的第二組原則，例如人力資源或財務部門所使用的原則，並將它們套用到這些群組。 

一旦您已決定要保護之應用程式的原則集，請逐步向您的使用者推廣原則，以解決問題的方式。  

例如，設定將用於所有 Microsoft 365 應用程式的原則，僅限 exchange Online 與 Exchange 的其他變更。 請向您的使用者推出這些原則，並處理任何問題。 然後，新增小組的其他變更，並將其推廣給您的使用者。 然後，新增包含其他變更的 SharePoint。 繼續新增應用程式的其餘部分，直到您可以自信地設定這些基準原則，以包含所有的 Microsoft 365 應用程式。 

同樣地，針對您的敏感應用程式，建立一組原則，並一次加入一個應用程式，直到所有的問題都包含在機密應用程式原則集中為止。 

Microsoft 建議您不要建立適用于所有應用程式的原則集，因為這可能會造成某些未預期的設定。 例如，封鎖所有應用程式的原則可能會鎖定您的系統管理員無法從 Azure 入口網站，且無法為 Microsoft Graph 等重要端點設定排除。 

## <a name="steps-in-the-process-of-configuring-identity-and-device-access"></a>設定身分識別與裝置存取之程式中的步驟

![設定身分識別與裝置存取的步驟。](../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. 設定必要身分識別功能及其設定。
2. 設定通用身分識別和存取條件式存取原則。
3. 為來賓和外部使用者設定條件式存取原則。
4. 針對 microsoft 團隊、Exchange Online 和 SharePoint，設定 Microsoft 365 雲端 app 的條件式存取原則。

## <a name="next-step"></a>下一步

[實施身分識別與裝置存取原則的必要條件工作](identity-access-prerequisites.md)
