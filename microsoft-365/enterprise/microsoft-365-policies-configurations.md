---
title: 身分識別與裝置存取設定-Microsoft 365 企業版
description: 說明部署安全電子郵件、檔及應用程式原則及設定的 Microsoft 建議與核心概念。
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/11/2018
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 0512d51f2789383c7612c3dbd97c0a77c2c4c7fa
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214659"
---
# <a name="identity-and-device-access-configurations"></a>身分識別與裝置存取設定

本系列文章說明如何透過企業行動性 + 安全性（EMS）產品來設定雲端服務的安全存取，其方式是實施建議的環境和設定，包括一組規定的條件式存取原則和相關功能。 EMS 是 Microsoft 365 的核心元件。 您可以使用此指導方針來保護與 Azure Active Directory 整合的所有服務的存取，包括 Microsoft 365 服務、其他 SaaS 服務，以及使用 Azure AD 應用程式 Proxy 發佈的內部部署應用程式。 

這些建議會與 Microsoft 安全分數和[AZURE AD 中的身分識別排名](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)保持一致，並且將為您的組織增加這些分數。 這些建議也會協助您執行下列[五個步驟，以保護您的身分識別基礎結構](https://docs.microsoft.com/azure/security/azure-ad-secure-steps)。 

Microsoft 知道某些組織有獨特的環境需求或複雜性。 如果您是這些組織之一，請使用這些建議做為開始點。 不過，大多陣列織可依照預定的方式來執行這些建議。 

## <a name="intended-audience"></a>目標物件

這些建議適用于企業架構師及 IT 專業人員，熟悉[Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx)和[Microsoft 企業行動性 + 安全性](https://microsoft.com/ems)，包括其他、azure Active Directory （身分識別）、Microsoft Intune （裝置管理）和 azure 資訊保護（資料保護）。

### <a name="customer-environment"></a>客戶環境

建議的原則適用于完全在 Microsoft 雲端內運作的企業組織，以及具有混合式基礎結構（同時部署于內部部署和 Microsoft 雲端）的客戶。

所提供的許多建議，都依賴只有 Enterprise 可移動性 + Security （EMS） E5 授權才能使用的服務。 所呈現的建議假設是完整的 EMS E5 授權功能。

對於沒有企業行動 + 安全性 E5 授權的組織，Microsoft 建議您至少執行所有方案隨附的 Azure AD 基準保護功能。 您可以在 Azure AD library 中的文章（[即「基準保護](/azure/active-directory/active-directory-conditional-access-baseline-protection)」）中找到詳細資訊。

### <a name="caveats"></a>警告

您的組織可能會受限於法規或其他法規遵從性需求，包括可能要求您套用與這些建議設定分開之原則的特定建議。 這些設定會建議過去未提供的使用情形控制項。 建議使用這些控制項，因為我們相信它們代表安全性與生產力之間的平衡。  

我們已盡力考慮各種組織保護需求，但我們不能考慮所有可能的需求，或組織的所有獨有方面。

## <a name="three-tiers-of-protection"></a>三種保護層級

大部分組織都有安全性和資料保護的相關特定需求。 根據產業部門和組織內的職責，這些需求會不同。 例如，您的法律部門和系統管理員可能需要其他的安全性和資訊保護，而不是其他商業單位使用者所需的電子郵件對應。 

每個產業也都有自己的一組特殊法規。 建議針對三種不同的安全性和保護層級，而不是提供所有可能安全性選項的清單，也是針對每個行業區段或工作功能所提供的建議。

- **基準保護**：我們建議您建立保護資料的最低標準，以及存取資料的身分識別和裝置。 您可以遵循下列基準建議，提供符合許多組織需求的強預設保護。
- **敏感保護**：有些客戶的資料子集必須在較高的層級加以保護，否則可能需要以較高的層次保護所有的資料。 您可以將增強的保護套用至 Microsoft 365 環境中的所有或特定資料集。 建議保護以可比較的安全性層級存取敏感性資料的身分識別和裝置。  
- **高管制**：有些組織的資料量可能非常高，consititutes 貿易機密或管制資料。 Microsoft 所提供的功能可協助組織符合這些需求，包含針對身分識別和裝置新增的保護。

![安全性錐-所有客戶 > 某些客戶 > 特定客戶。 特定應用程式的廣泛應用程式](../media/M365-idquality-threetiers.png)

本指南說明如何針對每一種保護層級的身分識別和裝置執行保護。 使用此指導方針做為組織的起點，並調整原則，以符合組織的特定需求。

請務必在您的資料、身分識別和裝置之間，使用一致層級的保護。 例如，如果您要執行此指導方針，請務必保護您的資料，以同等的層次。 這些架構模型會顯示哪些功能是可比較的。

**Office 365 的身分識別與裝置保護**<br/>
![海報「Office 365 的身分識別與裝置保護」的縮圖](../media/O365_Identity_device_protection_thumb.png)<br/>
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多語言](https://www.microsoft.com/download/details.aspx?id=55032)

**Office 365 的檔案保護方案**<br/>
![海報「Office 365 中的檔案保護解決方案」的縮圖](../media/24be68b5-d852-4fdb-94ad-94491a19edd8.png)<br/>
[PDF](https://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.pdf) | [Visio](https://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.vsdx)

## <a name="security-and-productivity-trade-offs"></a>安全性與生產力的取捨

實施任何安全性策略時，必須權衡安全性和生產力。 評估每個決策對安全性、功能和易用性的影響。

![安全性三角平衡安全性、功能和易用性。](../media/policies-configurations/security-triad.png)

提供的建議是以下列原則為基礎：

- 知道您的物件，以及其安全性和功能需求的彈性。
- 及時套用安全性原則，並確保其有意義。

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>身分識別與裝置存取保護的服務和概念

Microsoft 365 企業版專為大型組織設計，並整合 Office 365 企業版、Windows 10 Enterprise 和 Enterprise 可移動性 + Security （EMS），讓每個人都有創造性且安全地協同運作。

本節概述對身分識別與裝置存取非常重要的 Microsoft 365 服務和功能。

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure AD 提供完整的身分識別管理功能套件。 為了保護存取，我們建議使用下列功能：

- **[自助密碼重設（SSPR）](/azure/active-directory/authentication/concept-sspr-howitworks)**：可讓您的使用者安全地重設其密碼，而不需要技術支援人員介入，只要提供系統管理員可控制的多個驗證方法，即可加以驗證。

- **[多重要素驗證（MFA）](/azure/active-directory/authentication/concept-mfa-howitworks)**： MFA 要求使用者提供兩種形式的驗證，例如使用者密碼加上 Microsoft 驗證應用程式或電話的通知。 MFA 大幅降低可用於存取您環境的盜竊身分識別的風險。

- **[條件式存取](/azure/active-directory/conditional-access/overview)**： Azure AD 評估使用者登入的條件，並使用您建立以允許存取的條件式存取原則。 例如，在此指導中，我們會告訴您如何建立條件式存取原則，以要求存取機密資料的裝置合規性。 這可以極大降低具有盜竊身分識別的駭客可以存取您機密資料的風險。 它也會保護裝置上的機密資料，因為裝置會符合健康和安全性的特定需求。

- **[AZURE ad 群組](/azure/active-directory/fundamentals/active-directory-manage-groups)**：條件式存取規則、具有 Intune 的裝置管理，以及組織中檔案和網站的許可權，都依賴指派給使用者和/或 Azure AD 群組。 建議您建立對應至您所實施之保護層級的 Azure AD 群組。 例如，您的 executive 人員很可能是駭客的高價值目標。 因此，您可以將這些員工指派至 Azure AD 群組，並將此群組指派給條件式存取原則及其他強制進行存取保護等級的原則。

- **[裝置註冊](/azure/active-directory/devices/overview)**：您可以在 Azure AD 中註冊裝置，以提供裝置的身分識別。 當使用者登入並套用需要加入網域或合規的電腦的條件式存取規則時，此身分識別可用於驗證裝置。 針對此指南，我們使用 device registration，自動註冊加入網域的 Windows 電腦。 Device registration 是使用 Intune 管理裝置的必要條件。 

- **[AZURE ad 身分識別保護](/azure/active-directory/identity-protection/overview)**： azure Ad 身分識別保護可讓您偵測影響組織之身分識別的潛在弱點，並將自動修正原則設定為低、中、高的登入風險和使用者風險。 本指南取決於此風險評估，針對多重要素驗證套用條件式存取原則。 本指南也包含條件式存取原則，需要使用者在其帳戶中偵測到高風險的活動時變更其密碼。

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune)是 Microsoft 雲端型行動裝置管理服務。 本指南建議使用 Intune 的 Windows 電腦裝置管理，並建議裝置合規性原則設定。 Intune 會判斷是否符合裝置，並將此資料傳送至 Azure AD，以在套用條件式存取原則時使用。

#### <a name="intune-app-protection"></a>Intune 應用程式保護

您可以使用[Intune 應用程式保護](https://docs.microsoft.com/intune/app-protection-policy)原則，在行動應用程式中保護您組織的資料，但不需要將裝置登記至管理。 Intune 可協助保護資訊，確保您的員工仍可生產力，並防止資料遺失。 透過實施應用層級原則，您可以限制公司資源的存取權，並將資料放在 IT 部門的控制中。

本指南說明如何建立建議原則，以強制使用已核准的應用程式，以及決定如何將這些應用程式與您的商務資料搭配使用。

### <a name="microsoft-365"></a>Microsoft 365

本指南說明如何實施一組原則，以保護 Office 365 的存取，包括 Exchange Online、SharePoint 線上和商務 OneDrive。 除了執行這些原則之外，也建議您使用下列資源提升租使用者的保護層級：

- [設定您的承租人以提升安全性](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)：這些建議適用于您租使用者的基準安全性。
- [Microsoft 365 安全性藍圖：前30天、90天和之後的主要優先順序](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)：這些建議包括記錄、資料管理、系統管理存取和威脅防護。


### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 和 Microsoft 365 Apps 企業版

Windows 10 和 Microsoft 365 應用程式企業版是電腦的建議用戶端環境。 建議 Windows 10，因為 Azure 設計用來提供內部部署和 Azure AD 的最新可能體驗。 Windows 10 也包含可透過 Intune 管理的高級安全性功能。 Microsoft 365 應用程式企業版包含最新版的 Office 應用程式。 這些使用的是新式驗證，也就是更安全，也是條件式存取的必要條件。 這些應用程式也包含增強的安全性和符合性工具。

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>跨三種保護層級應用這些功能

下表摘要說明在三種保護層級使用這些功能的建議。

|保護機制|基準|敏感性|高管制|
|:-------------------|:-------|:--------|:---------------|
|**強制執行 MFA**|在中或以上的登入風險上|在低或以上的登入風險上|在所有新的工作階段上|
|**強制執行密碼變更**|高風險使用者的|高風險使用者的|高風險使用者的|
|**強制執行 Intune 應用程式保護**|是|是|是|
|**強制執行 Intune 註冊（貨到付款）**|需要相容或加入網域的電腦，但允許 BYOD 手機/平板電腦|需要相容或加入網域的裝置|需要相容或加入網域的裝置|

## <a name="device-ownership"></a>裝置擁有權

上表反映許多組織支援混合使用公司所擁有裝置的趨勢，以及個人或自行裝置（BYODs），以在整個員工中啟用行動生產力。 Intune 應用程式保護原則可確保電子郵件在公司所擁有的裝置和 BYODs 上，避免從 Outlook 行動應用程式和其他 Office 行動應用程式 exfiltrating。  

建議以 Intune 或加入網域的方式管理公司所擁有的裝置，以套用其他的保護和控制。 根據資料敏感度，您的組織可以選擇不允許特定使用者人口或特定應用程式的 BYODs。

## <a name="next-steps"></a>後續步驟

[實施身分識別與裝置存取原則的必要條件工作](identity-access-prerequisites.md)
