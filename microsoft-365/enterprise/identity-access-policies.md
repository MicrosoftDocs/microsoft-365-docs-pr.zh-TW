---
title: 通用身分識別和裝置存取原則-Microsoft 365 企業版 |Microsoft 檔
description: 描述建議的一般身分識別和裝置存取原則及設定。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
ms.openlocfilehash: 1512ba01f78d901177254fce86d0154e97e36496
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950784"
---
# <a name="common-identity-and-device-access-policies"></a>一般身分識別與裝置存取原則

本文說明保護 Microsoft 365 雲端服務存取權的常見建議原則，包括使用 Azure Active Directory (Azure AD) 應用程式 Proxy 發佈的內部部署應用程式。 

本指南討論如何在新布建的環境中部署建議的原則。 在不同的實驗室環境中設定這些原則，可讓您瞭解並評估建議的原則，再將首輾轉移至您的預製和實際執行環境。 您新布建的環境可以是僅限雲端或混合式，以反映評估需求。  

## <a name="policy-set"></a>原則集 

下圖說明建議的原則組。 它會顯示每個原則套用至哪個層級的保護，以及這些原則套用至電腦或電話和平板電腦，或是這兩種裝置的類別。 它也會指出您設定這些原則的位置。

設定身分[ ![ 識別與裝置存取的常見原則，](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [請參閱較大版本的此影像](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

以下是單一頁面 PDF 摘要，具有個別原則的連結：

[![Microsoft 365 講義的身分識別和裝置保護的縮圖影像](../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br/>  [以 PDF 格式查看](../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \|[以 PDF 格式下載](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)  

本文的其餘部分將說明如何設定這些原則。 

>[!Note]
>建議使用多重要素驗證 (MFA) 在 Intune 中註冊裝置之前，請先確認裝置是否擁有預定的使用者。 您必須先在 Intune 中註冊裝置，才能強制執行裝置規範原則。
>

為了讓您有時間完成這些工作，建議您依照此表中所列的順序實施基準原則。 不過，針對敏感和高管制保護層級的 MFA 原則，可在任何時候實施。

|保護層級|原則|詳細資訊|
|:---------------|:-------|:----------------|
|**Baseline**|[當登入風險為*中*或*高*時，需要 MFA](#require-mfa-based-on-sign-in-risk)| |
|        |[封鎖不支援新式驗證的用戶端](#block-clients-that-dont-support-modern-authentication)|未使用新式驗證的用戶端可以略過條件式存取原則，因此請務必封鎖這些設定。|
|        |[高風險使用者必須變更密碼](#high-risk-users-must-change-password)|當偵測到其帳戶的高風險活動時，強制使用者在登入時變更其密碼。|
|        |[套用應用程式資料保護原則](#apply-app-data-protection-policies)|每個平臺有一個 Intune App Protection 原則 (Windows、iOS/iPadOS、Android) 。|
|        |[需要核准的應用程式和應用程式保護](#require-approved-apps-and-app-protection)|使用 iOS、iPadOS 或 Android 強制執行手機和平板電腦行動裝置應用程式的保護。|
|        |[定義裝置合規性原則](#define-device-compliance-policies)|每個平臺一個原則。|
|        |[需要相容的電腦](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|強制使用 Windows 或 MacOS 對電腦進行 Intune 管理。|
|**敏感度**|[當登入風險為*低*、*中*或*高*時，需要 MFA](#require-mfa-based-on-sign-in-risk)| |
|         |[需要相容 *的電腦和* 行動裝置](#require-compliant-pcs-and-mobile-devices)|在 (Windows 或 MacOS) 和手機或平板電腦 (iOS、iPadOS 或 Android) 的電腦上，強制執行 Intune 管理。|
|**高管制**|[*永遠* 需要 MFA](#require-mfa-based-on-sign-in-risk)|
| | | |

## <a name="assigning-policies-to-groups-and-users"></a>指派原則給群組和使用者

設定原則之前，請先識別您針對每個保護層所使用的 Azure AD 群組。 一般會將基準保護套用至組織中的每個人。 包含在基線及敏感保護中的使用者，將會套用所有的基準原則，加上機密原則。 保護是累積的，且強制執行限制性最強的原則。 

建議的做法是建立 Azure AD 群組，以進行條件式存取排除。 在 [**工作分派**] 區段的 [**使用者和群組**的**排除**值] 設定中，將此群組新增至所有的條件式存取原則。 這可讓您在疑難排解存取問題時，提供使用者存取的方法。 這只是建議的臨時解決方案。 監視此群組中的變更，並確定排除群組的使用只是預定的。 

以下是需要 MFA 之群組指派及排除的範例。

![MFA 原則的群組指派及排除範例](../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

結果如下：

- 當登入風險為「中」或「高」時，所有使用者都必須使用 MFA。

- 當登入風險為低、中或高時，必須使用 Executive 人員群組的成員，才能使用 MFA。

  在此情況下，主管人員群組的成員會同時符合比較基準和機密的條件式存取原則。 這兩個原則的存取控制都結合在一起，在此案例中相當於機密的條件式存取原則。

- 主要機密專案 X 群組的成員必須使用 MFA

  在此情況下，主要機密專案 X 群組的成員會同時符合比較基準和高管制的條件式存取原則。 這兩個原則的存取控制會結合在一起。 因為高管制條件式存取原則的存取控制限制更嚴格，所以使用它。

對群組和使用者套用較高級別的保護時請務必小心。 例如，在每次登入時，最上層機密專案 X 群組的成員將需要使用 MFA，即使他們不是在 Project X 的高管制內容上運作也是一樣。  

在這些建議中建立的所有 Azure AD 群組都必須建立為 Microsoft 365 群組。 在保護 Microsoft 小組和 SharePoint 中的檔時，此功能對於部署敏感度標籤很重要。

![用於建立 Microsoft 365 群組的螢幕截圖](../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>需要根據登入風險進行 MFA

您應讓使用者在需要使用之前，註冊 MFA。 如果您有 Microsoft 365 E5、Microsoft 365 E3 和身分識別 & 威脅防護附加元件、Office 365 搭配 EMS E5 或個別 Azure AD Premium P2 授權，您可以使用具有 Azure AD 身分識別保護的 MFA 註冊原則，以要求使用者註冊 MFA。 必要條件 [工作](identity-access-prerequisites.md) 包含向 MFA 註冊所有使用者。

使用者註冊後，您可以要求使用新的條件式存取原則進行 MFA 登入。

1. 前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。
2. 在 [Azure 服務] 清單中，選擇 [ **Azure Active Directory**]。
3. 在 [ **管理** ] 清單中，選擇 [ **安全性**]，然後選擇 [ **條件式存取**]。
4. 選擇 [ **新增原則** ]，然後輸入新原則的名稱。

下表說明根據登入風險要求 MFA 的條件式存取原則設定。

在 [ **工作分派** ] 區段中：

|設定|屬性|值|附註|
|:---|:---------|:-----|:----|
|使用者和群組|Include| **選取 [使用者和群組] > 使用者和群組**：選取包含目標使用者帳戶的特定群組。 |從包含試驗使用者帳戶的群組開始。|
||排除| **使用者和群組**：選取您的條件式存取例外狀況群組; (應用程式身分識別) 的服務帳戶。|成員資格應以所需的暫存方式來修改。|
|雲端應用程式或動作| **雲端應用程式 > 包含** | **選取應用程式**：選取您想要套用此原則的應用程式。 例如，選取 [Exchange Online]。||
|條件| | |設定您的環境和需求特有的條件。|
||登入風險||請參閱下表中的指南。|
|||||

**登入風險條件設定**

根據目標的保護層級套用風險層級設定。

|保護層級|需要的風險層級值|動作|
|:---------|:-----|:----|
|基準|高、中|請檢查兩者。|
|敏感性|高、中、低|全部檢查三個。|
|高管制| |保留所有選項的選取狀態，永遠強制執行 MFA。|
||||

在 [ **存取控制** ] 區段中：

|設定|屬性|值|動作|
|:---|:---------|:-----|:----|
|授與|**授予存取**| | Select |
|||**需要多重要素驗證**| 檢查 |
||**需要所有選取的控制項** ||Select|
|||||

選擇 [ **選取** ] 以儲存 **授** 與設定。

最後 **，選取 [** **啟用原則**]，然後選擇 [ **建立**]。

此外，請考慮使用 [if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 工具來測試原則。

## <a name="block-clients-that-dont-support-modern-authentication"></a>封鎖不支援新式驗證的用戶端

使用這些表格中的設定條件式存取原則，以封鎖不支援新式驗證的用戶端。

請參閱 [本文](microsoft-365-client-support-modern-authentication.md) ，以取得 Microsoft suppport 新式驗證的 Microsoft 365 用戶端清單。

在 [ **工作分派** ] 區段中：

|設定|屬性|值|附註|
|:---|:---------|:-----|:----|
|使用者和群組|Include| **選取 [使用者和群組] > 使用者和群組**：選取包含目標使用者帳戶的特定群組。 |從包含試驗使用者帳戶的群組開始。|
||排除| **使用者和群組**：選取您的條件式存取例外狀況群組; (應用程式身分識別) 的服務帳戶。|成員資格應以所需的暫存方式來修改。|
|雲端應用程式或動作|**雲端應用程式 > 包含**| **選取應用程式**：選取對應至不支援新式驗證之用戶端的應用程式。||
|條件| **用戶端應用程式** | 為 [**設定**] 選擇 [**是]** <br> 清除**瀏覽器**和行動**應用程式與桌面用戶端**的核取記號 | |
||||

在 [ **存取控制** ] 區段中：

|設定|屬性|值|動作|
|:---|:---------|:-----|:----|
|授與|**封鎖存取**| | Select |
||**需要所有選取的控制項** ||Select|
|||||

選擇 [ **選取** ] 以儲存 **授** 與設定。

最後 **，選取 [** **啟用原則**]，然後選擇 [ **建立**]。

請考慮使用 [if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 工具來測試原則。

## <a name="high-risk-users-must-change-password"></a>高風險使用者必須變更密碼

若要確定登入時，強制所有高風險使用者的受損帳戶執行密碼變更，您必須套用下列原則。

Log in to the [Microsoft Azure portal (https://portal.azure.com)](https://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.

在 [ **工作分派** ] 區段中：

|類型|屬性|值|動作|
|:---|:---------|:-----|:----|
|使用者|Include|**所有使用者**|Select|
|使用者風險| **High**||Select|
|||||

在 [第二個 **工作分派** ] 區段中：

| 類型 | 屬性 | 值                  | 動作 |
|:-----|:-----------|:------------------------|:------|
| Access | **允許存取** |  | Select  |
|      |     | **需要密碼變更** | 檢查  |
|||||

選擇 [ **完成** ] 以儲存 **存取** 設定。

最後，選取 [ **On** for **強制原則**]，然後選擇 [ **儲存**]。

請考慮使用 [if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 工具來測試原則。

使用此原則搭配 [設定 AZURE AD 密碼保護](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)，它會偵測並封鎖已知弱密碼和其變種，以及組織特有的其他弱字詞。 使用 Azure AD 密碼保護可確保變更的密碼為強式密碼。

## <a name="apply-app-data-protection-policies"></a>套用應用程式資料保護原則

應用程式保護原則 (應用程式) 定義允許哪些應用程式，以及可以對組織的資料採取的動作。 應用程式中的可用選項可讓組織針對其特定需求量身定制防護。 在某些情況下，可能不會很顯然，執行完整案例需要哪些原則設定。 為了協助組織優先考慮行動用戶端端點強化，Microsoft 已引進其應用程式資料保護架構的分類，以供 iOS 和 Android 行動應用程式管理。 

應用程式資料保護架構分為三個不同的設定層級，每個層級都是以舊版為基礎： 

- **企業基本資料保護** (層級 1) 確保使用 PIN 碼保護應用程式，並執行選擇性的清除作業。 針對 Android 裝置，此層級會驗證 Android 裝置認證。 這是一種入門級的設定，可在 Exchange Online 信箱原則中提供類似的資料保護控制，並將其和使用者對應用程式的人口介紹。 
- **企業增強型資料保護** (第2級) 引進應用程式資料洩漏防護機制和最低作業系統需求。 這是適用于大多數行動使用者存取工作或學校資料的設定。 
- **企業高資料保護** (第3級) 引進高級資料保護機制、增強型 PIN 設定，以及應用程式行動威脅防護。 這種設定對存取高風險資料的使用者而言是必要的。 

若要查看每個設定層級的特定建議，以及必須保護的最小應用程式，請 [使用 app protection 原則，查看資料保護框架](https://docs.microsoft.com/mem/intune/apps/app-protection-framework)。 

使用身分 [識別與裝置存取](microsoft-365-policies-configurations.md)設定中所述的原則，比較基準和機密保護階層與第2級企業增強型資料保護設定緊密對應。 高度管制防護階層密切對應于第3級企業高資料保護設定。

|保護層級 |應用程式保護原則  |詳細資訊  |
|---------|---------|---------|
|基準     | [第2級增強型資料保護](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | 在層級2中強制執行的原則設定包括對層級1建議的所有原則設定，而且只會新增或更新下列原則設定，以執行更多控制項，以及比第1級更複雜的設定。         |
|敏感性     | [第2級增強型資料保護](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | 在層級2中強制執行的原則設定包括對層級1建議的所有原則設定，而且只會新增或更新下列原則設定，以執行更多控制項，以及比第1級更複雜的設定。        |
|高度管制     | [第3級企業高資料保護](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)        | 在層級3中強制執行的原則設定包括對層級1和2建議的所有原則設定，而且只會新增或更新下列原則設定，以執行更多控制措施，以及比第2級更為複雜的設定。        |

若要使用 data protection framework 設定，為每個平臺 (iOS 和 Android) 建立新的應用程式保護原則，您可以：

1. 遵循 [如何使用 Microsoft Intune 建立及部署應用程式保護原則](https://docs.microsoft.com/mem/intune/apps/app-protection-policies)的步驟，手動建立原則。 
2. 使用[intune 的 PowerShell 腳本](https://github.com/microsoftgraph/powershell-intune-samples)，匯入範例[Intune App Protection POLICY Configuration Framework JSON 範本](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies)。

## <a name="require-approved-apps-and-app-protection"></a>需要核准的應用程式和應用程式保護

若要強制執行您在 Intune 中所套用的應用程式保護原則，您必須建立一個條件式存取原則，以要求核准的用戶端應用程式，以及應用程式保護原則中設定的條件。 

強制執行應用程式保護原則需要 [使用應用程式保護原則，以具備條件式存取權存取雲端應用](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)程式的原則。 這些原則都包含在此建議的身分識別和存取設定原則組中。

若要建立需要經核准的應用程式和應用程式保護的條件式存取原則365，請在 [案例1： microsoft 365 應用程式需要已核准的應用程式搭配應用程式保護原則](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)，以允許 Outlook IOS 和 Android，但封鎖 OAuth 功能的 Exchange ActiveSync 用戶端無法連線至 Exchange Online。

   > [!NOTE]
   > 這種原則可確保行動使用者可以使用適用的應用程式來存取所有 Office 端點。

如果您要啟用對 Exchange Online 的行動存取，請執行 [封鎖 ActiveSync 用戶端](secure-email-recommended-policies.md#block-activesync-clients)，以防止 Exchange ActiveSync 用戶端利用基本驗證連線至 Exchange Online。 本文頂端的圖例中並未說明這項原則。 它會在 [保護電子郵件的原則建議](secure-email-recommended-policies.md)中說明及描述。

 這些原則利用授與控制措施 [需要核准的用戶端應用程式](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) ，並 [要求應用程式保護原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)。

最後，封鎖 iOS 和 Android 裝置上其他用戶端應用程式的舊版驗證，以確保這些用戶端無法略過條件式存取原則。 如果您遵循本文的指導方針，您已設定 [封鎖不支援新式驗證的用戶端](#block-clients-that-dont-support-modern-authentication)。

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>定義裝置合規性原則

裝置合規性原則定義裝置必須符合才能決定符合規範的需求。 您可以從 Microsoft 端點管理員系統管理中心中建立 Intune 裝置相容性原則。

您必須為每個電腦、電話或平板電腦平臺建立一個原則：

- Android 裝置管理員
- Android 企業版
- iOS/iPadOS
- macOS
- Windows 8.1 和更新版本
- Windows 10 和更新版本

若要建立裝置規範原則，請使用您的系統管理員認證登入[Microsoft 端點](https://endpoint.microsoft.com)管理員系統管理中心，然後流覽**裝置**  >  **規範原則**  >  **原則**。 選取 [ **建立原則**]。

若要部署裝置規範原則，必須將其指派給使用者群組。 您可以在建立並儲存原則之後加以指派。 在系統管理中心中，選取原則，然後選取 [ **工作分派**]。 選取您想要接收原則的群組之後，請選取 [ **儲存** ] 以儲存該群組指派並部署原則。

如需在 Intune 中建立相容性原則的逐步指引，請參閱在 Intune 檔中 [建立 Microsoft Intune 中的符合性原則](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) 。

### <a name="recommended-settings-for-windows-10-and-later"></a>Windows 10 和更新版本的建議設定

在執行 Windows 10 和更新版本的電腦上（如「 **步驟2：規範設定**」中所設定），建議使用下列設定來建立原則。

如需 **裝置健康情況 > Windows 健康認證服務評估規則**，請參閱下表。

|屬性|值|動作|
|:---------|:-----|:----|
|需要 BitLocker|需要| Select |
|需要在裝置上啟用安全啟動|需要| Select |
|需要程式碼完整性|需要| Select |
||||

在 [ **裝置屬性**] 中，根據您的 IT 及安全性原則，為作業系統版本指定適當的值。

如需 **Configuration Manager 的相容性**，請選取 [ **需要**]。

如需 **系統安全性**，請參閱下表。

|類型|屬性|值|動作|
|:---|:---------|:-----|:----|
|密碼|需要密碼以解除鎖定行動裝置|需要| Select |
||簡單密碼|封鎖|Select|
||密碼類型|裝置預設值|Select|
||密碼最小長度|6 |類型|
||需要密碼的最長空閒分鐘數|15 |類型 <br>此設定支援 Android 版本4.0 和更新版本，或在 KNOX 4.0 及以上版本。 IOS 裝置的支援 iOS 8.0 和更新版本。|
||密碼到期 (天) |41|類型|
||可避免重複使用的先前密碼數目|5 |類型|
||當裝置從空閒狀態傳回時，需要密碼 (Mobile 和全息) |需要|適用于 Windows 10 和更新版本|
|加密|裝置上的資料儲存區加密|需要|Select|
|裝置安全性|防火牆|需要|Select|
||防毒|需要|Select|
||間諜|需要|Select <br> 此設定需要使用 Windows Security Center 註冊的反間諜軟體方案。|
|後衛|Microsoft Defender 反惡意軟體|需要|Select|
||Microsoft Defender 反惡意軟體最低版本||類型 <br> 僅支援 Windows 10 desktop。 Microsoft 建議自最近的版本後的版本不超過五個。|
||最新的 Microsoft Defender 反惡意軟體簽名|需要|Select|
||即時保護|需要|Select <br>僅支援 Windows 10 desktop|
|||||

**Microsoft Defender ATP**

|類型|屬性|值|動作|
|:---|:---------|:-----|:----|
|Microsoft Defender 高級威脅防護規則|需要裝置位於或低於機器風險分數|中|Select|
|||||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>需要相容的 Pc (，但不符合相容的電話和平板) 

在新增要要求相容的電腦的原則之前，請務必在 Intune 中註冊要管理的裝置。 建議您先使用多重要素驗證，再將裝置登記到 Intune 中，以確保裝置已擁有預定的使用者。 

若要要求相容的電腦：

1. 前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。
2. 在 [Azure 服務] 清單中，選擇 [ **Azure Active Directory**]。
3. 在 [ **管理** ] 清單中，選擇 [ **安全性**]，然後選擇 [ **條件式存取**]。
4. 選擇 [ **新增原則** ]，然後輸入新原則的名稱。

5. 在 [ **工作分派**] 底下，選擇 [ **使用者和群組** ]，並包含您要套用原則的人員。 此外，請排除您的條件式存取排除群組。

6. 在 [ **工作分派**] 底下，選擇 [ **雲端應用程式或動作**]。

7. 針對 [ **包含**]，選擇 [ **選取應用程式] > 選取**]，然後從 [ **雲端應用程式** ] 清單中選取所需的應用程式。 例如，選取 [Exchange Online]。 完成後，選擇 [ **選取** ]。

8. 若要要求相容的 Pc (但不相容的電話和平板) ，請在 [ **工作分派**] 底下，選擇 [ **> 裝置平臺**]。 為 **[設定] 選取 [是]** 。 **Configure** 選擇 [  **選取裝置平臺**]，然後選取 [ **Windows** 和 **macOS**]，然後選擇 [ **完成**]。

9. 在 [ **存取控制**] 底下，選擇 **[授** 與]。

10. 選擇 **[授與存取權** ]，然後檢查 [ **要求裝置標示為相容性**]。 如果是多個控制項，請選取 **[需要所有選取的控制項**]。 完成時，請選擇 [ **選取**]。 

10. 選取 **[** **啟用原則**]，然後選擇 [ **建立**]。

>[!Note]
>啟用此原則之前，請先確定您的裝置是否相容。 否則，您可能會收到鎖定，而且將無法變更此原則，直到您的使用者帳戶已新增至條件式存取排除群組為止。
>

## <a name="require-compliant-pcs-and-mobile-devices"></a>需要相容 *的電腦和* 行動裝置

若要要求所有裝置的相容性：

1. 前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。
2. 在 [Azure 服務] 清單中，選擇 [ **Azure Active Directory**]。
3. 在 [ **管理** ] 清單中，選擇 [ **安全性**]，然後選擇 [ **條件式存取**]。
4. 選擇 [ **新增原則** ]，然後輸入新原則的名稱。

5. 在 [ **工作分派**] 底下，選擇 [ **使用者和群組** ]，並包含您要套用原則的人員。 此外，請排除您的條件式存取排除群組。

6. 在 [ **工作分派**] 底下，選擇 [ **雲端應用程式或動作**]。

7. 針對 [ **包含**]，選擇 [ **選取應用程式] > 選取**]，然後從 [ **雲端應用程式** ] 清單中選取所需的應用程式。 例如，選取 [Exchange Online]。 完成後，選擇 [ **選取** ]。

8. 在 [ **存取控制**] 底下，選擇 **[授** 與]。

9. 選擇 **[授與存取權** ]，然後檢查 [ **要求裝置標示為相容性**]。 如果是多個控制項，請選取 **[需要所有選取的控制項**]。 完成時，請選擇 [ **選取**]。 

10. 選取 **[** **啟用原則**]，然後選擇 [ **建立**]。

>[!Note]
>啟用此原則之前，請先確定您的裝置是否相容。 否則，您可能會收到鎖定，而且將無法變更此原則，直到您的使用者帳戶已新增至條件式存取排除群組為止。
>

## <a name="next-step"></a>後續步驟

[![步驟3：來賓和外部使用者的原則](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[深入瞭解來賓和外部使用者的原則建議](identity-access-policies-guest-access.md)
