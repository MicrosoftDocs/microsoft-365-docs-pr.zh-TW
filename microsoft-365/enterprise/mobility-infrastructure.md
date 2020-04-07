---
title: 階段 5 - 行動裝置管理
description: Microsoft 365 企業版包含使用 Microsoft Intune 的行動裝置管理。 查看需求和必要條件、使用您的 Azure Active Directory 資源設定 Intune、註冊 iOS、macOS、Android 和 Windows 裝置、部署應用程式、建立設定設定檔、使用符合性原則，以及使用 Microsoft 365 Enterprise 為行動裝置管理啟用條件式存取。
keywords: Microsoft 365，Microsoft 365 企業版，Microsoft 365 檔，行動裝置管理，Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: a957ef037aed1f9aba923af428c2a440790dbfba
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153889"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>第5階段： Microsoft 365 企業版行動裝置管理

![階段 5：行動裝置管理](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*這項功能適用于 Microsoft 365 企業版的 E3 和 E5 版本*

Microsoft 365 企業版包含的功能可協助您管理組織內的裝置及其應用程式。 使用 Microsoft Intune，您可以管理 iOS、Android、macOS 和 Windows 裝置，以保護您組織的資源（包括您的資料）的存取。 

在此階段中，您會在 Intune 中註冊裝置，並建立並強制執行原則，以保護您的資料安全且受到保護。 您[可以在線上](https://docs.microsoft.com/intune)取得 Intune 檔的整個文件庫。 在您開始之前，請先複習《 [Intune 部署規劃、設計及實施手冊》](https://docs.microsoft.com/intune/planning-guide) 。

## <a name="step-1-plan-for-your-scenario"></a>步驟1：規劃案例

管理行動裝置的其中一個主要原因是保護和保護您組織的資源。 [使用 Microsoft Intune 的常見方式](https://docs.microsoft.com/intune/common-scenarios)列出一些實際的範例，包括保護 Office 365 電子郵件和資料。

Intune 可讓您使用行動裝置管理（MDM）或行動應用程式管理（MAM）來管理組織存取權的選項。 MDM 是使用者在 Intune 中「註冊」其裝置的時間。 註冊後，他們就是受管理的裝置，而且可以接收組織使用的任何原則、規則和設定。 例如，您可以安裝特定的應用程式、建立密碼原則、安裝 VPN 連線等等。

具有自己個人裝置的使用者可能不想要註冊其裝置，或由 Intune 和您的原則進行管理。 不過，您仍然需要保護組織的資源和資料。 在此案例中，您可以使用 MAM 來保護您的應用程式。 例如，您可以使用需要使用者在存取裝置上的 SharePoint 時輸入 PIN 碼的 MAM 原則。

您也會決定要如何管理個人或組織所擁有的裝置。 您可能想要視裝置的用途而異。 例如，您可能想要針對人力資源（HR）中的使用者或 Sales 中的使用者，提供不同的計畫。 [識別行動裝置管理使用案例案例](https://docs.microsoft.com/intune/planning-guide-scenarios)可讓您開始，並包含有關這些不同案例的一些指導方針。

## <a name="step-2-get-your-prerequisites"></a>步驟2：取得您的必要條件

接下來，根據您的需求和您在上一個步驟中建立的案例，來取得您的必要條件。 [實施您的計畫](https://docs.microsoft.com/intune/planning-guide-onboarding)，列出所有需求。 以下是使用 Microsoft 365 的 Intune 所需的重要專案：

- **Intune 訂閱**：隨附于 microsoft 365，可讓您在[Azure 入口網站](https://portal.azure.com)中存取 microsoft Intune
- **Office 365 訂閱**：隨附于 Microsoft 365，可用於 Office 應用程式（包括電子郵件）
- **Azure Active Directory （AZURE AD） premium**：隨附于 Microsoft 365，用來建立使用者或安全性群組。 這些群組會接收您建立的 Intune 原則，例如強制密碼長度以解除鎖定裝置。 您可以使用您在[第2階段](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)中建立的群組： [身分識別]。

根據組織的需求而定，可能會有一些額外的需求。 例如，如果您要管理 iOS 裝置，則需要 Apple MDM Push 憑證。 如果您使用的是內部部署 Exchange，則需要內部部署 Exchange connector。 當您取得這些步驟時，會概括這些額外的需求。

## <a name="step-3-set-up-intune"></a>步驟3：設定 Intune

Intune 使用 Azure AD 中的許多功能，包括您的網域、使用者和您的群組。 您也可以建立新的使用者和新的群組，以符合您的公司需求。 例如，您可以建立一個名為**iOS 裝置**或**所有 HR 使用者**的群組。  利用[動態群組](https://docs.microsoft.com/intune/groups-add)，可讓您根據簡易或高級規則來建立使用者或裝置群組。

這個步驟重點是設定 Intune 並為您準備好管理裝置。

1. 請**[確認是否支援您的裝置](https://docs.microsoft.com/intune/supported-devices-browsers)**。 請確認您的 iOS、macOS、Android、Galaxy 和 Windows 裝置都支援 Intune。 如果您的組織包含不受支援的裝置，則原則不會套用到這些裝置。

2. **[自訂您的功能變數名稱](https://docs.microsoft.com/intune/custom-domain-name-configure)**。 根據預設，會自動在 Azure AD 中建立名為「類似**your-domain.onmicrosoft.com** 」的網域。 您的組織可以自訂**onmicrosoft.com** 。 當您自訂時，它也會在連線至 Intune 及使用資源時，為使用者提供熟悉的網域。

3. 登**[入 Intune](https://docs.microsoft.com/intune/account-sign-up)**。 當您登入時，系統會提示您輸入組織的相關資訊。 Intune 隨附于 Microsoft 365，可以從[microsoft 365 系統管理中心](https://admin.microsoft.com)直接開啟。 您也可以直接從[Azure 入口網站](https://portal.azure.com)開啟 Intune。

4. **[選擇您的行動裝置管理](https://docs.microsoft.com/intune/mdm-authority-set)** 設定。 您第一次使用 Intune 時，您必須啟用裝置管理。 Intune 可以做為僅限雲端的服務、使用 Intune 和 Microsoft 端點設定管理員的混合，或是使用 Office 365 的行動裝置管理。 您可以選擇哪個設定最適合您的組織。

5. **[新增使用者](https://docs.microsoft.com/intune/users-add)** 並**[新增群組](https://docs.microsoft.com/intune/groups-add)**。 

   您可以手動新增使用者或使用混合身分識別與 Azure AD Connect，以使用 Intune 同步您的內部部署使用者帳戶。 您也可以將系統管理員角色授與特定的使用者。 除非您的裝置是 "userless" 裝置，例如 kiosk 裝置，否則需要使用者。

   Azure AD 群組是用來簡化您在 Intune 中管理裝置和使用者的方式。 您可以使用群組進行許多不同的工作。 例如，您的組織想要在 Android 裝置上需要特定的應用程式。 您可以建立 Android 裝置群組，並將此應用程式的原則部署至群組。

    在 Intune 中，您可以新增您在[第2階段](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)中建立的使用者或群組： Identity

6. **[指派授權](https://docs.microsoft.com/intune/licenses-assign)**。 若要讓使用者或裝置在 Intune 中註冊，他們需要啟用 Intune 服務的 Microsoft 365 許可證，才能存取 Intune 服務。 您365指派 microsoft Intune 服務預設會在 Microsoft 365 系統管理中心或 PowerShell 中啟用 microsoft Intune 服務授權。

## <a name="step-4-enroll-devices"></a>步驟4：註冊裝置

若要管理裝置，必須在 Intune 中註冊裝置。 身為系統管理員，您將為使用者和裝置設定註冊限制和原則。 每個裝置平臺（iOS、Android、macOS 和 Windows）都有多種選項。 您可以讓您的使用者自行註冊。 或者，您可以自動化註冊，讓使用者只需登入裝置。

使用 Intune 時，註冊是一個重要步驟。 [[註冊裝置](https://docs.microsoft.com/intune/device-enrollment)] 會列出不同裝置的步驟。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南： iOS 和 Android device 登記](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>步驟5：新增及部署應用程式

行動裝置上的應用程式通常是使用者存取您公司資源的最快方式。 

使用應用程式時有一些挑戰，因為有不同的裝置，包括個人裝置和公司裝置。 而且，您也想要保護組織的資源和其資料，同時確保使用者的生產力。

Intune 可管理應用程式，包括新增應用程式、將其指派給不同的使用者或群組，以及查看其他重要的詳細資料。 例如，您可以查看哪些應用程式安裝失敗、檢查應用程式的版本等等。

當使用者取得行動裝置時，第一個工作是存取組織的電子郵件和檔。 使用 Intune，您可以使用裝置中預先安裝的電子郵件應用程式，來[建立及部署電子郵件設定](https://docs.microsoft.com/intune/email-settings-configure)。 

[[新增應用程式](https://docs.microsoft.com/intune/apps/apps-add)] 文章會列出在您組織內的裝置上新增、部署、監視、設定及保護應用程式的步驟。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：裝置相容性原則](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>步驟6：開啟相容性和條件式存取

在上述步驟中，您會設定您的環境，並啟用 Intune。 現在，您已準備好使用相容性和條件式存取來建立某些原則。

合規性和條件式存取對管理裝置很重要。 建立[規範原則](https://docs.microsoft.com/intune/device-compliance-get-started)，以協助保護您組織的資源。 當您建立符合性原則時，會定義裝置必須具備的標準或「基準」。 例如，您可以選擇可接受（或不可接受的）威脅層級、封鎖越獄的裝置、需要密碼長度，等等。 如果這些裝置不符合您的規則，則表示它們不相容，您可以封鎖對資源的存取。

這種 "封鎖" 會引入[條件式存取](https://docs.microsoft.com/intune/conditional-access)。 如果裝置被視為不相容，您可以封鎖對電子郵件、SharePoint 等的存取。

[Azure 入口網站](https://portal.azure.com)中的 Intune 可讓您建立這些原則，並將它們套用至您的使用者和裝置。 最佳作法是啟動 small，然後使用分段方法。 例如，建立封鎖越獄裝置的 iOS 原則。 套用（在 Intune 中稱為「指派」）原則至試驗或測試群組。 在初始測試之後，將更多使用者新增至試驗群組。 使用分段方法，您可以從各種使用者類型取得意見反應。

請參閱如何[開始使用裝置符合性原則](https://docs.microsoft.com/intune/device-compliance-get-started)及[瞭解條件式存取和 Intune？](https://docs.microsoft.com/intune/conditional-access)以協助您開始使用。

## <a name="step-7-apply-features-and-settings"></a>步驟7：套用功能和設定

這些功能和設定通常會被視為 Intune 的「酷」部分，而且功能非常強大。 當您使用條件式存取成功地強制執行某些規範原則之後，即可建立**裝置設定檔**。

[Azure 入口網站](https://portal.azure.com)中的 Intune 可讓您根據您的裝置平臺-iOS、MacOS、Android 和 Windows，建立不同的設定檔。 例如，您可以：

- 在 Windows 10 裝置上使用 Endpoint protection，以啟用不同的 BitLocker 選項，包括加密。
- 使用 iOS 裝置上的「受限制的應用程式」功能，建立可安裝的已核准應用程式清單。 或者，建立禁止的應用程式清單。
- 使用 Kiosk 設定來選擇哪些應用程式可用於在展臺模式中執行的 Android 裝置。
- 在執行 macOS 的裝置上套用 Wi-Fi connection 及其設定，包括安全性類型。

[使用裝置設定檔套用裝置上的功能和設定](https://docs.microsoft.com/intune/device-profiles)為閱讀設定檔的絕佳位置，請參閱 how to create a profile 等等。

請記住、開始小型和使用分段方法。 將設定檔指派給試驗或測試群組。 然後，將設定檔指派給其他試驗群組。

## <a name="step-8-get-to-know-the-other-features"></a>步驟8：瞭解其他功能

Intune 是一種強大的服務，包含許多功能。 以下是您可以使用 Intune 執行的一些其他工作：

- 管理 Windows[裝置](https://docs.microsoft.com/intune/windows-update-for-business-configure) & [電腦](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)上的軟體和更新，以及[iOS](https://docs.microsoft.com/intune/software-updates-ios)裝置
- 在 Windows 10 裝置上開啟[Microsoft Defender 高級威脅防護（ATP）](https://docs.microsoft.com/intune/advanced-threat-protection) ，並使用相容性和條件式存取來保護對公司資源的存取，例如 SharePoint 或 Exchange Online
- 使用[注意](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector)、 [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)及其他行動防護威脅合作夥伴
- 新增協力廠商[憑證授權單位單位（CA）](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview)以發行和更新憑證
- 為您的公司入口網站應用程式、取得應用程式等[使用者提供指引](https://docs.microsoft.com/intune/end-user-educate)
- 使用審核記錄檔，監視[應用程式](https://docs.microsoft.com/intune/apps-monitor)和[裝置合規性及設定設定檔](https://docs.microsoft.com/intune/compliance-policy-monitor)，以及更多遙測。 您也可以連線到[Intune 資料倉儲](https://docs.microsoft.com/intune/reports-nav-create-intune-reports)，並使用 Power BI 以取得更多報表需求。


## <a name="identity-and-device-access-recommendations"></a>身分識別與裝置存取建議

Microsoft 會針對[身分識別與裝置存取](microsoft-365-policies-configurations.md)提供一組建議，以確保安全且具有生產力的員工。 針對裝置存取，請使用下列文章中的建議和設定，以及此階段中的步驟：

- [必要條件](identity-access-prerequisites.md)
- [一般身分識別與裝置存取原則](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

深入瞭解 Microsoft 的 IT 專家如何[使用 EMS 管理裝置](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8)。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 如何執行 Microsoft 365 企業版

請參閱 Contoso Corporation （虛構但有代表性的跨國企業）如何使用 Microsoft 365 雲端服務[部署行動裝置管理基礎結構](contoso-mdm.md)。

![Contoso 公司](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>下一步

[行動裝置管理基礎結構出口準則](mobility-infrastructure-exit-criteria.md)

