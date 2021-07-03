---
title: 修正由整備評估工具發現的問題
description: 針對每個工具找到的問題所採取的詳細動作
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 9d2f9a95b3d5d90b79122d55477284083ea8332e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286882"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>修正由整備評估工具發現的問題

針對每個檢查，該工具會報告下列四個可能的結果之一：


|結果  |意義  |
|---------|---------|
|就緒     | 完成註冊之前，不需要執行任何動作。        |
|公告    | 請遵循工具或本文中的步驟，以取得註冊和使用者的最佳體驗。 您 *可以* 完成註冊，但是必須先修正這些問題，再部署第一個裝置。        |
|未就緒 | *如果您未修正這些問題，註冊將會失敗。* 請遵循工具或本文中的步驟加以解決。        |
|錯誤 | 您所使用的 Azure Active Directory (AD) 角色的許可權不足，無法執行這種檢查。 |

> [!NOTE]
> 此工具報告的結果會反映您的設定狀態，只會在您執行它的特定時間點反映。 如果您稍後對 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的原則進行任何變更，「就緒」的專案可能會變成「尚未準備好」。 若要避免 Microsoft 受管理的電腦作業的問題，請在變更任何原則之前，先檢查本文所述的特定設定。

## <a name="microsoft-intune-settings"></a>Microsoft Intune 設定

您可以在 Microsoft 端點管理員系統[管理中心](https://endpoint.microsoft.com)存取 Intune 設定。

### <a name="autopilot-deployment-profile"></a>Autopilot 部署設定檔

您不應該有任何現有的 Autopilot 設定檔，可將指派或動態群組設定為 Microsoft 受管理的電腦裝置。 Microsoft 受管理的電腦會使用 Autopilot 布建新裝置。

**未就緒**

您有指派給所有裝置的 Autopilot 設定檔。 如需步驟，請參閱[使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置](/mem/autopilot/enrollment-autopilot)。 Microsoft 受管理的電腦註冊後，請將您的 Autopilot 原則設定為排除 **現代的工作場所裝置-所有** Azure AD 群組。

**公告**

請確定您的 Autopilot 設定檔目標是指派或動態 Azure AD 群組，但不包括 Microsoft 受管理的電腦裝置。 如需步驟，請參閱[使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置](/mem/autopilot/enrollment-autopilot)。 Microsoft 受管理的電腦註冊後，請將您的 Autopilot 設定檔設定為排除 **現代的工作場所裝置-所有** Azure AD 群組。


### <a name="certificate-connectors"></a>憑證連接器

如果您有任何您想要在 Microsoft 受管理的電腦中註冊之裝置使用的憑證連接器，連接器不應該有任何錯誤。 下列其中一項諮詢只適用于您的情況，所以請務必仔細檢查。

**公告**

不存在任何憑證連接器。 您可能不需要任何連接器，但您應評估您的 Microsoft 受管理的電腦裝置上是否需要一些網路連線能力。 如需詳細資訊，請參閱[為 Microsoft 受管理的電腦準備憑證和網路設定檔](certs-wifi-lan.md)。

**公告**

至少有一個憑證連接器有錯誤。 如果您需要此連接器為 Microsoft 受管理的電腦裝置提供憑證，則必須解決此錯誤。 如需詳細資訊，請參閱[為 Microsoft 受管理的電腦準備憑證和網路設定檔](certs-wifi-lan.md)。


**公告**

您至少有一個憑證連接器，而且不會報告錯誤。 不過，在準備部署時，您可能需要建立設定檔，以重複使用 Microsoft 受管理的電腦裝置的連接器。 如需詳細資訊，請參閱[為 Microsoft 受管理的電腦準備憑證和網路設定檔](certs-wifi-lan.md)。

### <a name="company-portal"></a>公司入口網站

Microsoft 受管理的電腦需要 IT 管理員為其具有 Microsoft 受管理的電腦裝置的使用者安裝 Intune 公司入口網站。 

**未就緒**

您沒有為使用者安裝公司入口網站。 購買公司入口網站，並強制在 Intune 與商務用 Microsoft Store 之間進行同步處理。 如需詳細資訊，請參閱[在裝置上安裝 Intune 公司入口網站](../get-started/company-portal.md)。


### <a name="conditional-access-policies"></a>條件式存取原則

條件式存取原則不得阻止 Microsoft 受管理的電腦在 Intune 和 Azure ad 中管理 Azure ad 組織 (承租人) 。

**未就緒**

您有至少一個目標為所有使用者的條件式存取原則。 在註冊期間，我們會從相關的條件式存取原則中排除 Microsoft 受管理的電腦服務帳戶，並套用新的條件式存取原則，以限制對這些帳戶的存取。 註冊後，您可以在 Microsoft 端點管理員中查看 Microsoft 受管理的電腦條件式存取原則。 如需這些服務帳戶的詳細資訊，請參閱 [標準運作程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**公告**

您有條件式存取原則可以避免 Microsoft 受管理的電腦管理 Microsoft 受管理的電腦服務。 在註冊期間，我們會從相關的條件式存取原則中排除 Microsoft 受管理的電腦服務帳戶，並套用新的條件式存取原則，以限制對這些帳戶的存取。 如需這些服務帳戶的詳細資訊，請參閱 [標準運作程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**Error**

Intune 系統管理員角色沒有足夠的許可權可進行這種檢查。 您也需要指派的任何 Azure AD 角色，以執行這項檢查：

- 安全性讀取者
- 安全性系統管理員
- 條件式存取管理員
- 全域讀取者
- 裝置管理員


### <a name="device-compliance-policies"></a>裝置合規性原則

Azure AD 組織中的 Intune 裝置相容性原則可能會影響 Microsoft 受管理的電腦裝置。

**未就緒**

您至少具有一個針對所有使用者的符合性原則。 Microsoft 受管理的電腦包含將會以 Microsoft 受管理的電腦裝置為目標的相容性原則。  變更原則，以針對不包含任何 Microsoft 受管理的電腦使用者或裝置的特定 Azure AD 群組。 如需步驟，請參閱[Create a 合規性原則 in Microsoft Intune](/mem/intune/protect/create-compliance-policy)。

**公告**

請確定您沒有以任何 Microsoft 受管理的電腦使用者為目標的任何規範原則。 如需步驟，請參閱[Create a 合規性原則 in Microsoft Intune](/mem/intune/protect/create-compliance-policy)。



### <a name="device-configuration-profiles"></a>裝置設定檔

Azure AD 組織中的 Intune 裝置設定設定檔，不得針對任何 Microsoft 管理桌面裝置或使用者。

**未就緒**

您至少要有一個設定設定檔，針對所有使用者、所有裝置或兩者。 將設定檔重設為面向不包含任何 Microsoft 受管理的電腦裝置的特定 Azure AD 群組。 如需步驟，請參閱[使用中的自訂設定建立設定檔 Microsoft Intune](/mem/intune/configuration/custom-settings-configure)。

**公告**

請確定任何您沒有的設定原則都包含任何 Microsoft 受管理的電腦裝置或使用者。 如需步驟，請參閱[使用中的自訂設定建立設定檔 Microsoft Intune](/mem/intune/configuration/custom-settings-configure)。



### <a name="device-type-restrictions"></a>裝置類型限制

Microsoft 受管理的電腦裝置必須允許在 Intune 中註冊。

**未就緒**

您目前至少已設定一個登錄限制原則，以避免 Windows 裝置在 Intune 中註冊。 請遵循針對針對 Microsoft 受管理的電腦使用者之每個註冊限制原則 [設定註冊限制](/mem/intune/enrollment/enrollment-restrictions-set)的步驟，並將 **Windows (MDM)** 設定為 [**允許**]。 不過，您可以將任何 **屬於個人** 的 **Windows (MDM)** 裝置設定為 [**封鎖**]。 


### <a name="enrollment-status-page"></a>註冊狀態頁面

您目前已啟用「註冊狀態」頁面 (ESP) 。 如果您想要參與此功能的 Microsoft 受管理的電腦公開預覽，可以略過此專案。 如需詳細資訊，請參閱 [使用 Autopilot 和註冊狀態頁面的初次執行體驗](../get-started/esp-first-run.md)。

**未就緒**

您已設定 ESP 預設設定檔來 **顯示應用程式和設定檔設定進度**。 停用此設定，或遵循[設定 [註冊狀態] 頁面](/mem/intune/enrollment/windows-enrollment-status)中的步驟，確定任何 Azure AD 群組的指派都不包括 Microsoft 受管理的電腦裝置。

**公告**

請確定任何具有「**顯示應用程式和設定檔設定進度**」設定的設定檔都未指派給包含 Microsoft 受管理的電腦裝置的任何 Azure AD 群組。 如需詳細資訊，請參閱 [設定註冊狀態頁面](/mem/intune/enrollment/windows-enrollment-status)。

### <a name="microsoft-store-for-business"></a>商務用 Microsoft Store

我們使用商務用 Microsoft Store 和部署 Microsoft 受管理的電腦上的公司入口網站應用程式，讓使用者可以選擇性地安裝某些應用程式，例如 Microsoft Project 和 Microsoft Visio (允許) 的位置。

**未就緒**

商務用 Microsoft Store 未啟用或未與 Intune 同步。 如需詳細資訊，請參閱 how [to 使用 Microsoft Intune 商務用 Microsoft Store 管理大量購買的應用程式](/mem/intune/apps/windows-store-for-business)，並[在裝置上安裝 Intune 公司入口網站](../get-started/company-portal.md)。

### <a name="multifactor-authentication"></a>多重要素驗證

多重要素驗證不得阻止 Microsoft 受管理的電腦在 Intune 和 Azure ad 中管理 Azure ad 組織 (承租人) 。


**未就緒**

針對指派給所有 **使用者的條件** 式存取原則，您可以設定某些多重要素驗證原則。 在註冊期間，我們會從相關的條件式存取原則中排除 Microsoft 受管理的電腦服務帳戶，並套用新的條件式存取原則，以限制對這些帳戶的存取。 如需這些服務帳戶的詳細資訊，請參閱 [標準運作程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**公告**

您在有條件存取原則上必須進行多重驗證，以防止 Microsoft 受管理的電腦管理 Microsoft 受管理的電腦服務。 在註冊期間，我們會從相關的條件式存取原則中排除 Microsoft 受管理的電腦服務帳戶，並套用新的條件式存取原則，以限制對這些帳戶的存取。 如需這些服務帳戶的詳細資訊，請參閱 [標準運作程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**Error**

Intune 系統管理員角色沒有足夠的許可權可進行這種檢查。 您也需要指派的任何 Azure AD 角色，以執行這項檢查：

- 安全性讀取者
- 安全性系統管理員
- 條件式存取管理員
- 全域讀取者
- 裝置管理員


### <a name="powershell-scripts"></a>PowerShell 腳本

Windows PowerShell 腳本無法以目標 Microsoft 受管理的電腦裝置的方式指派。  

**公告**

請確定您的 Azure AD 組織中的 Windows PowerShell 腳本不會以任何 Microsoft 管理桌面裝置或使用者為目標。 請勿指派 PowerShell 腳本來設定所有使用者、所有裝置或兩者。 變更原則，以使用以特定 Azure AD 群組為目標的工作分派，不包含任何 Microsoft 受管理的電腦裝置或使用者。 如需詳細資訊，請參閱[在 Intune 中使用 Windows 10 裝置上的 PowerShell 腳本](/mem/intune/apps/intune-management-extension)。

### <a name="region"></a>區域

您的地區必須 Microsoft 受管理的電腦支援。

**未就緒**

目前不支援您的 Azure AD 組織區域 Microsoft 受管理的電腦。 如需詳細資訊，請參閱[Microsoft 受管理的電腦支援的地區和語言](../service-description/regions-languages.md)。

**公告**

Microsoft 受管理的電腦不支援 Azure AD 組織所在的一或多個國家/地區。 如需詳細資訊，請參閱[Microsoft 受管理的電腦支援的地區和語言](../service-description/regions-languages.md)。


### <a name="security-baselines"></a>安全性基準

安全性基準原則不應該以任何 Microsoft 受管理的電腦裝置為目標。

**未就緒**

您有一個針對所有使用者、所有裝置或兩者的安全性基準設定檔。 變更原則，以使用面向不包含任何 Microsoft 受管理的電腦裝置之特定 Azure AD 群組的工作分派。 如需步驟，請參閱[Use security 基線 to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines)。 在註冊期間，我們會將新的安全性基準套用到所有的 Microsoft 受管理的電腦裝置。 註冊後，您可以在 Microsoft 端點管理員的 [設定 **原則**] 區域中，複查 Microsoft 受管理的電腦安全性基準原則。

**公告**

請確定任何已排除 Microsoft 受管理的電腦裝置的安全性基準原則。 如需步驟，請參閱[Use security 基線 to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines)。 在註冊期間，我們會將新的安全性基準套用到所有的 Microsoft 受管理的電腦裝置。 **新式的工作場所裝置-所有** Azure AD 群組是我們在 Microsoft 受管理的電腦中註冊時所建立的動態群組，所以在註冊後，您必須傳回此群組以排除此群組。 


### <a name="windows-apps"></a>Windows 應用程式

查看您的 Microsoft 受管理的電腦使用者所需的應用程式。

**公告**

您應該準備要讓 Microsoft 受管理的電腦使用者擁有的應用程式清單。 由於這些應用程式必須透過 Intune 部署，因此請評估重複使用現有的 Intune 應用程式。 請考慮使用公司入口網站 (請參閱在裝置和註冊狀態頁面[上安裝 Intune 公司入口網站](../get-started/company-portal.md) (ESP) ，將應用程式發佈至您的使用者。 如需詳細資訊，請參閱使用 Autopilot 的[應用 Microsoft 受管理的電腦程式](apps.md)和[初次執行體驗和註冊狀態頁面](../get-started/esp-first-run.md)。

您可以向您的 Microsoft 帳戶代表尋求 Microsoft Endpoint Configuration Manager 中的查詢，以識別準備好要遷移至 Intune 或需要調整的應用程式。


### <a name="windows-hello-for-business"></a>Windows Hello 企業版

Microsoft 受管理的電腦需要啟用商務 Windows Hello。

**未就緒**

已停用商務用 Windows Hello。 遵循[建立商務用 Windows Hello 原則](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步驟來啟用

**公告**

未設定商務用 Windows Hello。 遵循 [[建立商務用 Windows Hello] 原則](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步驟來啟用。


### <a name="windows-10-update-rings"></a>Windows 10 更新振鈴

Intune 中的「Windows 10 更新環路」原則不得以任何 Microsoft 受管理的電腦裝置為目標。

**未就緒**

您有一個「更新鈴聲」原則，針對所有裝置、所有使用者或兩者。 變更原則，以使用面向不包含任何 Microsoft 受管理的電腦裝置之特定 Azure AD 群組的工作分派。 如需步驟，請參閱[管理 Intune 中的 Windows 10 軟體更新](/mem/intune/protect/windows-update-for-business-configure)。

**公告**

請確定任何更新環原則您已排除現代的 **工作場所裝置-所有** Azure AD 群組。 如果您已將 Azure AD 使用者群組指派給這些原則，請確定任何更新環原則您已排除現代的 **工作場所-所有** 您新增 Microsoft 受管理的電腦使用者的 azure ad 群組，或)  (或同等群組。 如需步驟，請參閱[管理 Intune 中的 Windows 10 軟體更新](/mem/intune/protect/windows-update-for-business-configure)。 現代的 **工作場所裝置（多功能**）和 **現代的工作場所-所有** Azure AD 群組都是您在 Microsoft 受管理的電腦註冊時所建立的群組，所以您必須在註冊後傳回排除此群組。


## <a name="azure-active-directory-settings"></a>Azure Active Directory 設定

您可以在[Azure 入口網站](https://portal.azure.com)中存取 Azure Active Directory 設定。

### <a name="intune-enrollment"></a>Intune 登記

您的 Azure AD 組織中的 Windows 10 裝置必須能夠在 Intune 中自動註冊。

**公告**

確定 **MDM 使用者範圍** 已設定為 **部分** 或 **全部**（非 **無**）。 如果您選擇 [**部分**]，請在註冊後再進行註冊，然後選取 [**新式的工作場所]-** **群組** 的所有 Azure AD 群組，或針對所有 Microsoft 受管理的電腦使用者的同等群組。  請參閱[使用 Microsoft Intune 設定 Windows 裝置的註冊](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。

### <a name="ad-hoc-subscriptions"></a>專用訂閱

建議您如何檢查 (如果設定為 "false" 的設定 ) 可能會導致 Enterprise 狀態漫遊無法正常運作。

**公告**

確定 **AllowAdHocSubscriptions** 設定為 **True**。 否則，Enterprise 狀態漫遊可能無法運作。 如需詳細資訊，請參閱 [MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings)。


### <a name="enterprise-state-roaming"></a>企業狀態漫遊

Enterprise應啟用狀態漫遊。

**公告**

確定已針對 **所有** 或 **選取** 的群組啟用 Enterprise 狀態漫遊。 如需詳細資訊，請參閱[Enable Enterprise State 漫遊 in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable)。

### <a name="licenses"></a>授權

需要有許多授權才能使用 Microsoft 受管理的電腦。

**尚未準備好**

您沒有所有需要使用 Microsoft 受管理的電腦的授權。 如需詳細資訊，請參閱[Microsoft 受管理的電腦技術](../intro/technologies.md)和[有關授權的詳細](prerequisites.md#more-about-licenses)資訊。


### <a name="microsoft-managed-desktop-service-accounts"></a>Microsoft 受管理的電腦服務帳戶

某些帳戶名稱可能與 Microsoft 受管理的電腦所建立的帳戶名稱相衝突，以管理 Microsoft 受管理的電腦服務。

**未就緒**

您至少要有一個帳戶名稱與 Microsoft 受管理的電腦所建立的帳戶名稱產生衝突。 請與您的 Microsoft 帳戶代表合作，以排除這些帳戶名稱。 我們不會向公眾列出帳戶名稱，以儘量降低安全性風險。 


### <a name="security-administrator-roles"></a>安全性管理員角色

具有特定安全性角色的使用者必須在 Microsoft Defender for Endpoint 中指派這些角色。

**公告**

如果您已將使用者指派至 Azure AD 組織中的任何角色，請確定他們也在 Microsoft Defender for Endpoint 中指派這些角色。 否則，具有這些角色的系統管理員將無法存取管理員入口網站。

- 安全性操作員
- 全域讀取者

如需詳細資訊，請參閱 [建立及管理以角色為基礎的存取控制角色](/windows/security/threat-protection/microsoft-defender-atp/user-roles)。


### <a name="security-default"></a>安全性預設值

Azure Active Directory 中的安全性預設值會防止 Microsoft 受管理的電腦管理裝置。

**未就緒**

您已開啟安全性預設值。 關閉安全性預設值，並設定條件式存取原則。 如需詳細資訊，請參閱 [一般條件式存取原則](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。

### <a name="self-service-password-reset"></a>自助密碼重設

自助密碼重設 (SSPR) 可以針對所有 Microsoft 受管理的電腦使用者以外的 Microsoft 受管理的電腦服務帳戶啟用。 如需詳細資訊，請參閱[教學課程：讓使用者能夠使用 Azure Active Directory 自助密碼重設來解除鎖定帳戶或重設密碼](/azure/active-directory/authentication/tutorial-enable-sspr)。

**公告**

請確定 SSPR **選取** 的設定包括 Microsoft 受管理的電腦使用者，但不包括 Microsoft 受管理的電腦服務帳戶。 SSPR 啟用時，Microsoft 受管理的電腦服務帳戶無法如期運作。  


### <a name="standard-user-role"></a>標準使用者角色

除了為全域系統管理員和裝置管理員指派 Azure AD 角色的使用者以外，Microsoft 受管理的電腦使用者將是不具備本機系統管理員許可權的標準使用者。 當其他使用者啟動其 Microsoft 受管理的電腦裝置時，系統會將其指派為標準使用者角色。

**公告**

Microsoft 受管理的電腦使用者將不會在註冊後，在其 Microsoft 受管理的電腦裝置上具有本機系統管理員許可權。

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps 企業版

### <a name="onedrive"></a>OneDrive

[**僅允許在加入特定網域的 pc 上進行同步** 處理] 設定會與 Microsoft 受管理的電腦產生衝突。 您可以在 OneDrive 系統[管理中心](https://admin.onedrive.com)存取 OneDrive 設定。

**公告**

您正在使用 [ **僅允許在加入特定網域的電腦上同步** 處理] 設定。 此設定不會搭配 Microsoft 受管理的電腦使用。 停用此設定，而不是設定 OneDrive 使用條件式存取原則。 請參閱 [規劃設定條件式存取部署](/azure/active-directory/conditional-access/plan-conditional-access) 以取得協助。
