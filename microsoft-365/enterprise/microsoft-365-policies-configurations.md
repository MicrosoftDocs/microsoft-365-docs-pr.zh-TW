---
title: 身分識別與裝置存取設定-Microsoft 365 企業版
description: 說明 Microsoft 建議及部署安全的電子郵件、 文件，與應用程式的原則和設定的核心概念。
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/11/2018
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: ea03143c7c42952ab6963d38ae44e79822d0b90a
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866140"
---
# <a name="identity-and-device-access-configurations"></a>身分識別與裝置存取設定

此系列文章說明如何藉由實作建議的環境與設定，包括一組指定設定格式化的條件存取原則設定透過企業行動性 + 安全性產品的雲端服務的安全存取和相關的功能。您可以使用這份指導來保護所有與 Azure Active Directory，包括其他 saas 和服務和內部部署應用程式發佈與 Azure AD 應用程式 Proxy 的 Office 365 服務整合的服務存取權。 

這些建議對齊 Microsoft 安全分數以及[Azure AD 的分數的身分識別](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/identity-secure-score)，並會增加這些分數的組織。這些建議也可協助您實作下列[五個步驟來保護您的身分識別基礎結構](https://docs.microsoft.com/en-us/azure/security/azure-ad-secure-steps)。 

Microsoft 瞭解某些組織有唯一的環境需求或複雜性。如果您是這些組織的其中一個，使用下列建議為起點。不過，大部分組織可以實作這些建議前述。 

## <a name="intended-audience"></a>使用對象

下列建議適用於企業架構師和熟悉[Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx)及[Microsoft 企業行動性 + 安全性](http://microsoft.com/ems)、 之間其他人，包括 Azure Active Directory (identity) Microsoft IT 專業人員Intune （裝置管理） 和 Azure 資訊保護 （資料保護）。

### <a name="customer-environment"></a>客戶環境

建議的原則是適用於企業組織操作完全內 Microsoft cloud 和客戶混合式基礎結構 （已部署在內部部署與 Microsoft cloud）。

提供建議的許多依賴只能使用企業行動性 + 安全性 （EMS） E5 授權的服務。呈現的建議事項會假設完整 EMS E5 授權功能。

對於沒有企業行動性 + 安全性 E5 授權這些組織而言，Microsoft 建議您至少實作所含所有計劃的 Azure AD 基準保護功能。可以中的文章、[比較基準保護功能](/azure/active-directory/active-directory-conditional-access-baseline-protection)，Azure AD 程式庫中找到詳細資訊。

### <a name="caveats"></a>警告

您的組織可能因法規或規範需求，包括可能需要將偏離這些建議設定的原則套用的特定建議而異。這些設定建議在過去尚未提供的使用狀況控制項。我們建議下列控制項，因為我們相信及其所代表的安全性和產能之間的平衡。  

我們已完成我們適合使用以考量各種不同的保護組織的需求，但我們不能夠帳戶或組織的所有唯一方面的所有可能的需求。

## <a name="three-tiers-of-protection"></a>三層的保護

大部分組織都有安全性和資料保護的相關特定需求。 根據產業部門和組織內的職責，這些需求會不同。 例如，您的法務部門和 Office 365 系統管理員可能需要其電子郵件對應的額外安全性和資訊保護控制，但其他業務單位使用者則不需要。 

每個產業也有自己的特殊規定集。而不提供所有可能的安全性選項或建議清單個別產業線段或工作函數已提供建議的三個不同的層的安全性和保護可以套用根據您的需要的層次.

- **[比較基準保護**： 我們建議您建立的最小的標準保護資料以及身分識別及存取資料的裝置。您可以遵循這些基準建議，以提供強式預設保護符合許多組織的需求。
- **機密保護**： 某些客戶有較高層級必須受保護的資料子集或他們可能需要保護較高層級的所有資料。您可以將增加的保護套用至所有或特定的資料設定 Office 365 環境中。我們建議保護身分識別與存取具有相較下的安全性層級的機密資料的裝置。  
- **高度規範**： 有些組織可能會有少量的高度分類的資料、 貿易機密、 consititutes 或規範的資料。Microsoft 提供可協助組織符合這些需求，包括新增的保護身分識別和裝置的功能。

![安全性圓錐圖層所有客戶 > 某些客戶 > 特定的客戶。廣泛的應用程式特定的應用程式](../images/M365-idquality-threetiers.png)

本指南說明如何實作的身分識別保護和每個這些層的保護裝置。這份指導作為您的組織的起點並調整以符合組織的特定需求的原則。

請務必使用一致等級的保護資料、 身分識別，及裝置。例如，如果實作這份指導，請務必來保護您的資料相較下的層級。這些架構模型顯示的相較下的功能。

**Office 365 的身分識別與裝置保護**<br/>
![海報"身分識別與裝置 protection for Office 365"的縮圖](../images/O365_Identity_device_protection_thumb.png)<br/>
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多語言](https://www.microsoft.com/download/details.aspx?id=55032)

**Office 365 的檔案保護方案**<br/>
!["Office 365 中檔案保護解決方案 」 海報的縮圖](../images/24be68b5-d852-4fdb-94ad-94491a19edd8.png)<br/>
[PDF](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.pdf) | [Visio](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.vsdx)

## <a name="security-and-productivity-trade-offs"></a>安全性與生產力的取捨

執行任何安全性策略需要取捨之間的安全性和產能。它是用來評估每個決策如何影響的安全性、 功能及方便使用的平衡很有幫助。

![安全性三角理論平衡安全性、 功能及方便使用。](media/policies-configurations/security-triad.png)

所提供的建議根據下列原則：

- 了解您對象，且是彈性至其安全性及正常運作的需求。
- 只在時間中套用的安全性原則和有意義。

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>服務和概念的身分識別與裝置存取保護

Microsoft 365 企業版的大型組織的設計並將其可安全地整合 Office 365 Enterprise、 10 Enterprise 和 Enterprise 行動性 + 安全性 （EMS） 授權人設為 Windows 創造性及搭配運作。

本節提供 Microsoft 365 服務及重要的身分識別與裝置存取功能的概觀。

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure AD 提供一組完整的身分識別管理功能。保護存取的建議使用下列功能：

- **[自助式密碼重設 (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)**： 允許使用者以重設其密碼安全地和服務台介入未提供驗證系統管理員可以控制的多種驗證方法。

- **[多重要素驗證 (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)**： MFA 需要使用者提供兩種形式的驗證，例如使用者密碼以及從 Microsoft 驗證器應用程式或電話的通知。可大幅減少 MFA 之風險的竊的 identity 可以是用來存取 Office 365 環境。

- **[設定格式化的條件存取](/azure/active-directory/conditional-access/overview)**： Azure AD 評估使用者登入的條件，並使用您為允許存取建立的設定格式化的條件存取原則。例如，在這份指導我們為您示範如何建立對個機密資料的存取權要求裝置規範設定格式化的條件存取原則。這可大幅減少竊身分識別與他就可以存取您的機密資料的風險。它也保護機密資料的裝置，因為裝置符合特定的狀況與安全性需求。

- **[Azure AD 群組](/azure/active-directory/fundamentals/active-directory-manage-groups)**： 條件式存取規則、 intune、 裝置管理和偶數檔案與您的組織中的網站的權限依賴指派給使用者和/或 Azure AD 群組。我們建議您建立 Azure AD 群組，對應至您要實作的保護層級。例如，您高階主管人員就是可能的駭客較高的值目標。因此，它合理指派這些員工 Azure AD 群組並將這個群組指派給設定格式化的條件存取原則及其他強制執行保護存取較高層級的原則。

- **[裝置註冊](/azure/active-directory/devices/overview)**： 將裝置登錄至提供裝置 identity 的 Azure AD。此 identity 用來驗證裝置時的使用者登入並套用設定格式化的條件存取規則需要已加入網域或相容的 Pc。這份指導，我們使用裝置註冊自動登錄已加入網域的 Windows 電腦。裝置註冊是 intune 裝置管理的必要條件。 

- **[Azure AD 身分識別保護](/azure/active-directory/identity-protection/overview)**： Azure AD 身分識別保護可讓您偵測潛在弱點會影響您組織的身分識別和設定自動的修復原則以低、 中型或高登入的風險與使用者風險。這份指導依賴此的風險評估来套用設定格式化的條件存取原則的多重要素驗證。這份指導也包含需要高風險活動偵測到其帳戶時變更其密碼的使用者設定格式化的條件存取原則。

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune)是 Microsoft 的雲端式行動裝置管理服務。這份指導建議的 Windows intune 的 Pc 裝置管理和建議裝置規範原則設定。Intune 會判斷裝置是否符合，並將此資料傳送至要套用設定格式化的條件存取原則時所使用的 Azure AD。

#### <a name="intune-app-protection"></a>Intune 應用程式保護

[Intune 應用程式保護](https://docs.microsoft.com/intune/app-protection-policy)原則可用來保護您的組織資料的行動應用程式]，使用或不到管理註冊裝置。Intune 可協助保護 Office 365 資訊，請確定您的員工仍然可以提高工作效率，並防止資料遺失。藉由實作應用程式層級的原則，您可以限制存取公司資源，並讓您的 IT 部門的控制項內的資料。

這份指導會示範如何建立建議的原則來強制執行的已核准的應用程式使用並判斷這些應用程式如何用於您的商務資料。

### <a name="office-365"></a>Office 365

本指南說明如何實作一組原則來保護存取 Office 365，包括 Exchange Online、 SharePoint Online 和 OneDrive for Business。除了實作這些原則，我們建議您也會引發使用這些資源的 Office 365 租用的保護層級：

- [設定您的 Office 365 租用戶加強安全性](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)： 這些建議適用於基準 security for Office 365 租用戶。
- [Office 365 安全性藍圖： 最常用的優先順序的前 30 天 90 天和超過](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)： 這些建議包括記錄、 資料管理、 系統管理存取和威脅保護。
- [保護 SharePoint Online 網站及檔案](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)： 本系列文章說明如何保護檔案與適當的比較基準 」、 機密、 和高度機密保護層級的網站。

### <a name="windows-10-and-office-365-proplus"></a>Windows 10 和 Office 365 專業增強版

Windows 10 與 Office 365 ProPlus 是建議的用戶端環境的 Pc。我們建議 Windows 10 為 Azure 設計來提供內部部署和 Azure AD 可能帶來最流暢的經驗。Windows 10 也包含可管理透過 Intune 的進階的安全性功能。Office 365 ProPlus 包含 Office 應用程式的最新版本。這些設定格式化的條件存取使用越長越安全的現代驗證和需求。這些應用程式也包含增強的安全性和規範工具。

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>跨三層的保護套用這些功能

下表摘要說明我們跨三層的保護使用這些功能的建議。

|保護機制|基準|敏感性|高管制|
|:-------------------|:-------|:--------|:---------------|
|**強制執行 MFA**|在中或以上的登入風險上|在低或以上的登入風險上|在所有新的工作階段上|
|**強制執行密碼變更**|高風險的使用者|高風險的使用者|高風險的使用者|
|**強制執行 Intune 應用程式保護**|是|是|是|
|**強制執行 Intune 註冊 (COD)**|需要相容或已加入網域的電腦，但允許 BYOD 電話平板電腦|需要相容或已加入網域的裝置|需要相容或已加入網域的裝置|

## <a name="device-ownership"></a>裝置擁有權

上述表格會反映以支援混合的公司擁有裝置，以及個人或將-your-擁有裝置 (BYODs) 之間的人力啟用行動產能的許多組織的趨勢。Intune 應用程式保護原則確保可從 Outlook 行動裝置應用程式] 及 [其他 Office 行動應用程式、 公司擁有裝置和 BYODs exfiltrating 保護電子郵件。  

建議您公司擁有裝置是由 Intune 管理或已加入網域的套用其他保護及控制。根據資料敏感度您的組織可能會選擇不允許 BYODs 特定的使用者人數或特定應用程式。

## <a name="next-steps"></a>後續步驟

[實作身分識別與裝置存取原則的必要工作](identity-access-prerequisites.md)
