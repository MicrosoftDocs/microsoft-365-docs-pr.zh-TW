---
title: 階段 5-行動裝置管理
description: Microsoft 365 企業版包含使用 Microsoft Intune 行動裝置管理。 檢閱需求和先決條件，設定 Intune 使用 Azure Active Directory 資源，註冊 iOS、 macOS、 Android 和 Windows 裝置，部署應用程式、 建立設定檔、 使用合規性政策，並啟用的行動裝置條件式存取使用 Microsoft 365 企業版的裝置管理。
keywords: Microsoft 365，Microsoft 365 企業版，Microsoft 365 文件、 行動裝置管理、 Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/18/2018
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 35fa9f53b555de48f4a5acc09d0619ba978ca87a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291206"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>階段 5: Microsoft 365 企業版的行動裝置管理

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*此功能適用於 Microsoft 365 企業版 E3 和 E5 版本*

Microsoft 365 企業版包含可協助您管理裝置和其應用程式]，在您的組織內的功能。 您可以使用 Microsoft Intune，管理 iOS、 Android、 macOS 和 Windows 裝置，來保護貴組織的資源，包括您的資料存取權。 Intune 與 Azure Active Directory (Azure AD) 整合，並會為 Microsoft 365 啟用下列商務案例：

- 在組織內外部儲存及共用檔案，順暢地跨越組織界限工作
- 隨時隨地在裝置上安全地工作，以達成更多目標，同時維持彈性的工作方式
- 通過產業驗證符合合規性的全球標準，提供控制和可見度讓您安心
- 保護您的資訊，並降低資料遺失風險
- 偵測並防範外部威脅
- 監控、 報告及分析活動，以回應迅速提供組織的安全性
- 保護您的使用者和自己的帳戶

如需詳細資訊，請參閱[使用 Microsoft 365 進行數位轉換](http://transform.microsoft.com) (英文)。 

在這個階段，您可以註冊您的裝置在 Intune 中，並建立並強制執行原則，以協助保護您的資料，安全無虞且受保護。 Intune 文件的整個文件庫[可用線上](https://docs.microsoft.com/intune)。 它也是很好的作法，以在您開始之前檢閱[Intune 部署規劃、 設計和實作指南](https://docs.microsoft.com/intune/planning-guide)。

## <a name="step-1-plan-for-your-scenario"></a>步驟 1： 規劃您的案例

若要管理行動裝置的主要原因之一是安全性和保護您的組織資源。 [若要使用 Microsoft Intune 的常用方式](https://docs.microsoft.com/intune/common-scenarios)列出一些真實世界的範例，包括保護 Office 365 電子郵件和資料。

Intune 提供您選項來管理您組織中使用[行動裝置管理 (MDM) 或行動應用程式管理 (MAM)](https://docs.microsoft.com/intune/byod-technology-decisions)存取。 MDM 時，使用者的 「 註冊 「 在 Intune 中的其裝置。 一旦註冊，他們受管理的裝置，且可以接收任何原則、 規則和貴組織所使用的設定。 例如，您可以安裝特定應用程式、 建立密碼原則、 安裝 VPN 連線，等等。

使用者與自己的個人裝置可能不想要註冊他們的裝置，或由 Intune 和您的原則進行管理。 但是，您仍然需要保護貴組織的資源和資料。 在此案例中，您可以保護您的應用程式使用 MAM。 例如，您可以使用 MAM 原則，要求使用者在裝置上存取 SharePoint 時輸入 pin 碼。

您也將決定您要管理個人或公司擁有裝置的方式。 若要根據其使用方式，將裝置。 例如，您可能想為使用者不同的計劃人力資源 (HR) 或銷售中的使用者。 [身分識別的行動裝置管理使用案例案例](https://docs.microsoft.com/intune/planning-guide-scenarios)可以協助您開始，並包含這些不同案例的一些指引。

## <a name="step-2-get-your-prerequisites"></a>步驟 2： 取得您的必要條件

接下來，取得您根據需求的先決條件和您在上一個步驟中建立的分析藍本。 [實作您的計劃](https://docs.microsoft.com/intune/planning-guide-onboarding)列出所有的需求。 以下是您需要使用 Microsoft 365 的 Intune 的重要項目：

- **Intune 訂用帳戶**： 隨附於 Microsoft 365，並可讓您存取[Azure 入口網站](https://portal.azure.com)中的 Microsoft Intune
- **Office 365 訂閱**： 隨附於 Microsoft 365，以及用於 Office 應用程式，包括電子郵件
- **Azure Active Directory (Azure AD) 高階**： 隨附於 Microsoft 365，而且會用來建立使用者或安全性群組。 這些群組會收到 Intune 原則以您建立，例如強制執行密碼長度裝置解除鎖定。 在您建立的群組[階段 2： 身分識別](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)可用。

可能會有一些額外的需求，視您的組織需要而定。 例如，如果您將管理 iOS 裝置，您將需要 Apple MDM 推入的憑證。 如果您使用內部部署 Exchange，則您需要在內部部署 Exchange 連接器。 當您收到這些步驟概述這些額外的需求。

## <a name="step-3-set-up-intune"></a>步驟 3： 設定 Intune

Intune 使用 Azure AD，包括您的網域，您的使用者，以及您的群組中的許多功能。 您也可以建立新的使用者和新的群組，以符合您公司的需求。 例如，您可以建立一個稱為 「 **iOS 裝置**，或者**所有 HR 使用者**群組。  善用[動態群組](https://docs.microsoft.com/intune/groups-add)可讓您建立使用者或根據周圍簡單或進階規則的裝置群組。

此步驟著重於設定 Intune，並準備您管理您的裝置。

1. **[確認您的裝置支援](https://docs.microsoft.com/intune/supported-devices-browsers)**。 確認您的 iOS、 macOS、 Android、 星空、 和 Windows 裝置支援 Intune。 如果您的組織中包含不支援的裝置，原則不會套用至這些裝置。

2. **[自訂您的網域名稱](https://docs.microsoft.com/intune/custom-domain-name-configure)**。 根據預設，網域名為像是**your domain.onmicrosoft.com**會自動建立 Azure AD 中。 **onmicrosoft.com**可自訂為您的組織。 自訂時，它也會提供使用者熟悉的網域時連線到 Intune 和使用的資源。

3. **[登入 Intune](https://docs.microsoft.com/intune/account-sign-up)**。 當您登入時，可能會提示您輸入您的組織的相關資訊。 Intune 隨附於 Microsoft 365，並可直接從[Microsoft 365 系統管理中心](https://admin.microsoft.com)開啟。 您也可以開啟 Intune 直接從[Azure 入口網站](https://portal.azure.com)。

4. **[選擇您的行動裝置管理設定](https://docs.microsoft.com/intune/mdm-authority-set)**。 第一次您使用 Intune，您必須啟用裝置管理。 Intune 可用為僅限雲端服務時，使用 Intune 和 System Center Configuration Manager，或使用行動裝置管理 Office 365 的混合部署。 您可以選擇的設定最適合您的組織。

5. **[新增使用者](https://docs.microsoft.com/intune/users-add)** 並**[加入群組](https://docs.microsoft.com/intune/groups-add)**。 

   您可以手動新增使用者，或連線到 Azure AD 同步處理使用者與 Intune。 您也可以提供系統管理員角色給特定使用者。 除非您的裝置 」 userless 」 的裝置，例如 kiosk 裝置，所需的使用者。

   Azure AD 群組用來簡化您管理裝置和在 Intune 中的使用者。 使用群組，您可以執行許多不同的工作。 例如，您的組織想要需要 Android 裝置上的特定應用程式。 您可以建立 Android 裝置群組，並部署到群組與此應用程式的原則。

    在 Intune 中，您可以新增使用者或群組，您在建立[階段 2： 身分識別](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)

6. **[指派授權](https://docs.microsoft.com/intune/licenses-assign)**。 使用者或裝置在 Intune 中註冊，他們必須在裝置上的授權。 每個使用者或 userless 裝置需要 Intune 授權存取的 Intune 服務。 這些授權隨附於 Microsoft 365，且必須在 Intune 中指派。

## <a name="step-4-enroll-devices"></a>步驟 4： 註冊裝置

若要管理的裝置，裝置必須註冊在 Intune 中。 身為管理員，您將設定註冊限制和您的使用者和裝置的原則。 每個裝置平台 （iOS、 Android、 macOS 和 Windows） 有各式各樣的選項。 您可以讓您自行註冊的使用者。 或者，您可以自動註冊，讓使用者只要登入該裝置。

註冊時使用 Intune 重要步驟。 [註冊裝置](https://docs.microsoft.com/intune/device-enrollment)列出不同裝置的步驟。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南： iOS 和 Android 裝置註冊](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>步驟 5： 新增及部署應用程式

在行動裝置上的應用程式通常是最快方式使用者取得公司資源的存取權。 

挑戰時有使用應用程式，都有不同的裝置，包括個人裝置和公司規範的裝置。 且您想要保護貴組織的資源和其資料，同時確保使用者生產力。

Intune 可以管理應用程式，包括新增應用程式、 將它們指派給不同的使用者或群組，並檢閱其他重要的詳細資料。 例如，您可以看到哪些應用程式失敗安裝，請檢查應用程式，以及其他版本。

當使用者取得行動裝置時，其中第一個工作是存取組織的電子郵件和文件。 使用 Intune，您可以[建立及部署電子郵件設定](https://docs.microsoft.com/intune/email-settings-configure)的裝置上使用預先安裝的電子郵件應用程式。 

[新增應用程式](https://docs.microsoft.com/intune/app-management)列出的步驟來新增、 部署、 監視、 設定和保護貴內的裝置上的應用程式

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南： 裝置合規性原則](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>步驟 6： 開啟規範和條件式存取

在先前步驟中，您可以設定您的環境，並啟用 Intune。 現在，您可以建立使用合規性和條件式存取原則。

合規性和條件式存取極為重要管理裝置。 建立**[符合性原則](https://docs.microsoft.com/intune/device-compliance-get-started)**，協助保護貴組織的資源。 當您建立合規性政策時，您要定義標準或的裝置必須具備 「 基準 」。 例如，您可以選擇可接受 （或無法接受） 威脅層級、 封鎖越獄裝置、 需要密碼長度，等等。 如果這些裝置不符合您的規則，這表示它們不相容，然後可以封鎖存取您的資源。

此 「 封鎖 」 引進**[條件式存取](https://docs.microsoft.com/intune/conditional-access)**。 如果裝置被視為不相容，您可以封鎖存取電子郵件、 SharePoint、 等等。

在[Azure 入口網站](https://portal.azure.com)中的 Intune 可讓您建立這些原則，並將它們套用至您的使用者和裝置。 最佳作法是，啟動小型，並使用分段的方法。 例如，建立 iOS 原則會封鎖越獄裝置。 （稱為 「 指派 「 在 Intune 中的） 的原則套用至試驗或測試群組。 初始測試之後，新增更多使用者到試驗群組。 使用分段的方式，您可以從各種使用者類型取得意見反應。

[開始使用裝置合規性原則](https://docs.microsoft.com/intune/device-compliance-get-started)和[的條件式存取的功能？](https://docs.microsoft.com/intune/conditional-access)可協助您快速入門。

## <a name="step-7-apply-features-and-settings"></a>步驟 7： 將套用的功能與設定

這些功能和設定通常被視為 「 酷 」 Intune，且非常強大。 一旦您已成功地強制執行某些使用條件式存取的符合性原則，就可以建立**裝置的設定檔**。

在[Azure 入口網站](https://portal.azure.com)中的 Intune 可讓您建立不同的設定檔，根據您的裝置平台的 iOS、 macOS、 Android 和 Windows。 例如，您可以：

- 使用 Windows 10 裝置上的端點保護，來啟用不同 BitLocker 選項，包括加密。
- 使用 iOS 裝置上的受限制的應用程式功能，來建立核准，皆可安裝的應用程式的清單。 或者，建立一份禁止之應用程式。
- 若要選擇哪個應用程式可以用在 kiosk 模式中執行的 Android 裝置上使用 Kiosk 設定。
- 適用於 Wi-fi 連線以及其設定，包括上執行 macOS 裝置的安全性類型。
- 等等

[什麼是 Microsoft Intune 裝置設定檔？](https://docs.microsoft.com/intune/device-profiles)是很理想的閱讀有關的設定檔資訊，請參閱如何建立設定檔，等等。

請記得，啟動小，並使用分段的方法。 給試驗或測試群組指派設定檔。 然後，指派給更多的試驗群組的設定檔。

## <a name="step-8-get-to-know-the-other-features"></a>步驟 8： 取得知道其他功能

Intune 是功能強大的服務，並包含許多功能。 以下是一些您可以使用 Intune 的其他工作：

- 管理軟體和 Windows[裝置](https://docs.microsoft.com/intune/windows-update-for-business-configure)上的更新 & [電腦](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)和[iOS](https://docs.microsoft.com/intune/software-updates-ios)裝置
- 在 [ [Windows Defender 進階威脅防護 (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection)上開啟 Windows 10 裝置，並使用合規性和條件式存取來保護存取公司資源，例如 SharePoint 或 Exchange Online
- 使用[注意](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector)、 [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)及其他行動防禦威脅協力廠商
- 新增[協力廠商憑證授權單位 (CA)](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview)發行，以及更新憑證
- [提供相關指導，以您的使用者](https://docs.microsoft.com/intune/end-user-educate)在公司入口網站應用程式，取得應用程式]，等等
- 監視[應用程式](https://docs.microsoft.com/intune/apps-monitor)、 監控[裝置相容性](https://docs.microsoft.com/intune/compliance-policy-monitor)、 監視器[設定設定檔](https://docs.microsoft.com/intune/compliance-policy-monitor)、 和多個遙測使用稽核記錄檔。 您也可以連線到[Intune 資料倉儲](https://docs.microsoft.com/intune/reports-nav-create-intune-reports)，並使用更多報告需求的 Power BI。


## <a name="identity-and-device-access-recommendations"></a>身分識別與裝置存取建議

Microsoft 會針對[身分識別與裝置存取](microsoft-365-policies-configurations.md)提供一組建議，以確保安全且具有生產力的員工。 裝置存取使用建議和設定步驟以及下列文章中在這個階段中：

- [必要條件](identity-access-prerequisites.md)
- [一般身分識別與裝置存取原則](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

了解 Microsoft IT 專家如何規劃及部署 EMS 與裝置管理，使用以下資源：

- [使用企業行動力 + 安全性管理現代行動生產力](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security) (英文)
- [使用 Microsoft Intune 連線到公司的 Windows 10 裝置](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune) (英文)
- [為 Microsoft 的 iOS、OS X 和 Android 設備啟用移動生產力](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft) (英文)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 如何執行 Microsoft 365 企業版

請參閱 Contoso Corporation，虛構但有代表性的跨國企業，[部署其行動裝置管理基礎結構](contoso-mdm.md)與 Microsoft 365 雲端服務的方式。

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>下一步

[行動裝置管理基礎結構允出準則](mobility-infrastructure-exit-criteria.md)

