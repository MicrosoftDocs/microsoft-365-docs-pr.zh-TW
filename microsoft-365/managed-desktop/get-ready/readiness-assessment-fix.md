---
title: 修正由整備評估工具發現的問題
description: 針對工具找到的每個問題採取的詳細動作
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f1af39a9b2a09908ecf5f5ff15b9fd6d764459d6
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921855"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>修正由整備評估工具發現的問題

工具會針對每項檢查報告四種可能的結果之一：


|結果  |意義  |
|---------|---------|
|就緒     | 完成註冊之前無需執行任何動作。        |
|諮詢    | 請遵循工具或本文中的步驟，以獲得最佳註冊和使用者體驗。 您可以 *完成* 註冊，但必須在部署第一個裝置之前修正這些問題。        |
|未就緒 | *如果您沒有修正這些問題，註冊將會失敗。* 請遵循工具或本文中的步驟來解決問題。        |
|錯誤 | 使用 Azure Active Director (AD) 角色沒有足夠的許可權可以執行這項檢查。 |

> [!NOTE]
> 這項工具報告的結果只會在執行此工具的特定時間點反映您的設定狀態。 如果您稍後對 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的策略進行任何變更，之前為「就緒」的專案可能會變成「尚未就緒」。 若要避免 Microsoft 管理桌面作業發生問題，請在變更任何策略之前，檢查本文所述的特定設定。

## <a name="microsoft-intune-settings"></a>Microsoft Intune 設定

您可以在 Microsoft Endpoint Manager 系統管理中心存取 Intune [設定](https://endpoint.microsoft.com)。

### <a name="autopilot-deployment-profile"></a>Autopilot 部署設定檔

您不應該有任何現有的 Autopilot 設定檔以 Microsoft 受管理之桌面裝置為目標指定或動態群組。 Microsoft Managed Desktop 會使用 Autopilot 來提供新裝置。

**未就緒**

您的 Autopilot 設定檔已指派給所有裝置。 有關步驟，請參閱使用 [Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)在 Intune 中註冊 Windows 裝置。 在 Microsoft 管理桌上型電腦註冊之後，設定您的 Autopilot 策略以排除新式工作場所裝置 **- 所有** Azure AD 群組。

**諮詢**

請確定您的 Autopilot 設定檔的目標為不包含 Microsoft 受管理桌面裝置之已指派或動態 Azure AD 群組。 有關步驟，請參閱使用 [Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)在 Intune 中註冊 Windows 裝置。 在 Microsoft 管理桌上型電腦註冊之後，設定您的 Autopilot 設定檔以排除新式工作場所裝置 **-所有** Azure AD 群組。


### <a name="certificate-connectors"></a>憑證連接器

如果您想要在 Microsoft Managed Desktop 中註冊的裝置會使用任何憑證連接器，則連接器不應有任何錯誤。 只有下列其中一個建議適用于您的情況，因此請仔細檢查。

**諮詢**

沒有憑證連接器存在。 您可能不需要任何連接器，但您應評估是否需要一些在 Microsoft 管理的桌面裝置上進行網路連接。 有關詳細資訊，請參閱 [準備 Microsoft Managed Desktop 的憑證和網路設定檔](certs-wifi-lan.md)。

**諮詢**

至少有一個憑證連接器發生錯誤。 如果您需要此連接器提供憑證給 Microsoft 受管理桌面裝置，您必須解決錯誤。 有關詳細資訊，請參閱 [準備 Microsoft Managed Desktop 的憑證和網路設定檔](certs-wifi-lan.md)。


**諮詢**

您至少有一個憑證連接器，而且沒有報告錯誤。 不過，在準備部署時，您可能需要建立設定檔，以重複使用 Microsoft 受管理之桌面裝置上的連接器。 有關詳細資訊，請參閱 [準備 Microsoft Managed Desktop 的憑證和網路設定檔](certs-wifi-lan.md)。


### <a name="conditional-access-policies"></a>條件式存取原則

Azure AD 組織的條件式存取策略不得以任何 Microsoft Manage Desktop 服務帳戶為目標。

**未就緒**

您至少有一個會以所有使用者為根據的條件式存取策略。 修改該策略以鎖定不包含將在註冊中建立之 Microsoft Managed Desktop 服務帳戶的 Azure AD 群組的特定 Azure AD 群組。 有關步驟，請參閱條件 [式存取：使用者和群組](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。

**諮詢**

請確定您擁有的任何條件式存取策略不包含新式 **工作場所服務帳戶** Azure AD 群組。 有關步驟，請參閱調整 [條件式存取](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)。 新式 **工作場所服務帳戶** Azure AD 群組是一個動態群組，我們在您註冊時為該服務建立。 註冊之後，您必須返回以排除此群組。 有關這些服務帳戶的更多資訊，請參閱 [標準作業程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**錯誤**

Intune 系統管理員角色沒有足夠的許可權可以執行這項檢查。 您也需要被指派任何 Azure AD 角色，以執行這項檢查：

- 安全性讀取者
- 安全性系統管理員
- 條件式存取系統管理員
- 全域讀取者
- 裝置系統管理員


### <a name="device-compliance-policies"></a>裝置合規性政策

您 Azure AD 組織的 Intune 裝置合規性政策可能會影響 Microsoft Managed Desktop 裝置。

**未就緒**

您至少有一個合規性政策會檢查所有使用者。 Microsoft Managed Desktop 包含以您 Microsoft 管理之桌面裝置為目標的合規性政策。  變更策略以鎖定不包括任何 Microsoft 受管理之桌面使用者或裝置的特定 Azure AD 群組。 相關步驟請參閱在 [Microsoft Intune 中建立合規性政策](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。

**諮詢**

請確定您未以任何 Microsoft 受管理之桌面使用者為目標的任何合規性政策。 相關步驟請參閱在 [Microsoft Intune 中建立合規性政策](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。



### <a name="device-configuration-profiles"></a>裝置組配置設定檔

您 Azure AD 組織的 Intune 裝置組組設定檔不得以任何 Microsoft 管理桌面裝置或使用者為目標。

**未就緒**

您至少有一個設定設定檔會同時針對所有使用者、所有裝置或兩者。 將設定檔重設為不包括任何 Microsoft Managed Desktop 裝置的特定 Azure AD 群組。 有關步驟，請參閱 [使用 Microsoft Intune 中的自訂設定建立設定檔](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。

**諮詢**

請確定您擁有的任何群組原則不包含任何 Microsoft 受管理的桌面裝置或使用者。 有關步驟，請參閱 [使用 Microsoft Intune 中的自訂設定建立設定檔](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。



### <a name="device-type-restrictions"></a>裝置類型限制

Microsoft 受管理桌面裝置必須允許在 Intune 註冊。

**未就緒**

您目前至少已針對一個註冊限制進行設置，以防止 Windows 裝置在 Intune 註冊。 請遵循針對每個 [](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set)會以 Microsoft 管理之桌面使用者為根據的註冊限制設定註冊限制中的步驟，將 **Windows (MDM**) 設為 **允許**。 不過，您可以將 MDM **中個人** 擁有的任何 Windows (**設定)****封鎖。** 


### <a name="enrollment-status-page"></a>註冊狀態頁面

您目前已啟用 ESP (註冊) 頁面。 如果您打算參與此功能的 Microsoft 受管理桌面公開預覽版，您可以忽略此專案。 詳細資訊請參閱 [Autopilot 的](../get-started/esp-first-run.md)首次執行體驗及註冊狀態頁面。

**未就緒**

您將 ESP 預設設定檔設定為 **顯示 App 和設定檔設定進度**。 停用此設定，或遵循設定註冊狀態頁面的步驟，確定指派給任何 Azure AD 群組的工作不包含 Microsoft Managed [Desktop 裝置](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。

**諮詢**

請確定沒有將具有顯示應用程式及設定檔設定進度設定的任何設定檔指派給任何包含 Microsoft 受管理桌面裝置之 Azure AD 群組。 詳細資訊請參閱設定註冊狀態 [頁面](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。

### <a name="microsoft-store-for-business"></a>商務用 Microsoft Store

我們使用商務用 Microsoft Store，在 Microsoft Managed Desktop 上部署公司入口網站應用程式，以允許使用者選擇性地安裝某些應用程式，例如 Microsoft Project 和 Microsoft Visio (在允許的情況下) 。

**未就緒**

商務用 Microsoft Store 未啟用或未與 Intune 同步處理。 有關詳細資訊，請參閱 [如何使用 Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) 從商務用 Microsoft Store 管理大量購買的應用程式，以及如何在裝置上安裝 [Intune 公司入口網站](../get-started/company-portal.md)。

### <a name="multifactor-authentication"></a>多重要素驗證

多重要素驗證不可適用于 Microsoft Managed Desktop 服務帳戶。


**未就緒**

針對指派給所有使用者的條件式存取策略，您將某些多重要素驗證策略設為必要的。 將設定變更為使用指派，以針對不包括任何 Microsoft Managed Desktop 服務帳戶的特定 Azure AD 群組。 詳細資訊請參閱條件式[存取策略](#conditional-access-policies)和[條件式存取：所有使用者需要 MFA。](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)

**諮詢**

請確定任何需要多重要素驗證的條件式存取策略不包含新式 **工作場所 -所有** Azure AD 群組。 詳細資訊請參閱條件式[存取策略](#conditional-access-policies)和[條件式存取：所有使用者需要 MFA。](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) 新式 **工作場所 - 所有** Azure AD 群組是一個動態群組，我們在您註冊 Microsoft Managed Desktop 時建立，因此您必須在註冊後返回排除此群組。

**錯誤**

Intune 系統管理員角色沒有足夠的許可權可以執行這項檢查。 您也需要被指派任何 Azure AD 角色，以執行這項檢查：

- 安全性讀取者
- 安全性系統管理員
- 條件式存取系統管理員
- 全域讀取者
- 裝置系統管理員


### <a name="powershell-scripts"></a>PowerShell 腳本

Windows PowerShell 腳本無法以 Microsoft Managed Desktop 裝置為目標的指派方式。  

**諮詢**

請確定您 Azure AD 組織的 Windows PowerShell 腳本未以任何 Microsoft 管理桌面裝置或使用者為目標。 請勿指派 PowerShell 腳本以鎖定所有使用者、所有裝置或兩者。 將群組原則變更為使用工作分派，該工作分派會針對不包括任何 Microsoft 受管理之桌面裝置或使用者的特定 Azure AD 群組。 詳細資訊請參閱 Intune 中 [Windows 10 裝置上的 PowerShell 腳本](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)。

### <a name="region"></a>地區

您的地區必須受到 Microsoft 管理桌面的支援。

**未就緒**

Microsoft Managed Desktop 目前不支援您的 Azure AD 組織地區。 詳細資訊請參閱 Microsoft [受管理的桌面支援地區和語言](../service-description/regions-languages.md)。

**諮詢**

Microsoft Managed Desktop 不支援您 Azure AD 組織所在的一或多個國家/地區。 詳細資訊請參閱 Microsoft [受管理的桌面支援地區和語言](../service-description/regions-languages.md)。


### <a name="security-baselines"></a>安全性比較基準

安全性比較基準不應該以任何 Microsoft 管理桌面裝置為目標。

**未就緒**

您的安全性比較基準設定檔會針對所有使用者、所有裝置或兩者。 將群組原則變更為使用指派，該工作分派會以不包括任何 Microsoft 受管理之桌面裝置的特定 Azure AD 群組為目標。 有關步驟，請參閱 [使用安全性比較基準在 Intune 中設定 Windows 10 裝置](https://docs.microsoft.com/mem/intune/protect/security-baselines)。

**諮詢**

請確定您排除 Microsoft 管理桌面裝置的任何安全性基準策略。 有關步驟，請參閱 [使用安全性比較基準在 Intune 中設定 Windows 10 裝置](https://docs.microsoft.com/mem/intune/protect/security-baselines)。 新式 **工作場所裝置 - 所有** Azure AD 群組是一個動態群組，我們在您註冊 Microsoft Managed Desktop 時建立，因此您註冊之後必須返回以排除此群組。


### <a name="windows-apps"></a>Windows 應用程式

請審查您希望 Microsoft 管理桌面使用者擁有的應用程式。

**諮詢**

您應準備 Microsoft 管理桌面使用者擁有的應用程式庫存。 由於 Intune 必須部署這些應用程式，請評估是否重新使用現有的 Intune 應用程式。 請考慮使用公司入口 (裝置上的安裝 [Intune](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) 公司入口網站，以及 ESP (註冊狀態) 以將應用程式散發給使用者。 詳細資訊請參閱 Microsoft [Managed Desktop](apps.md) 中的應用程式以及 [Autopilot](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)的首次執行體驗，以及註冊狀態頁面。

您可以要求 Microsoft 帳戶代表在 Microsoft Endpoint Configuration Manager 中查詢，以找出那些已準備好要遷移至 Intune 或需要調整的應用程式。


### <a name="windows-hello-for-business"></a>Windows Hello 企業版

Microsoft Managed Desktop 需要啟用商務用 Windows Hello。

**未就緒**

已停用商務用 Windows Hello。 遵循建立商務用 Windows [Hello 政策中的步驟來啟用](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**諮詢**

尚未設定商務用 Windows Hello。 請遵循建立商務用[Windows Hello 政策中的步驟來啟用。](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)


### <a name="windows-10-update-rings"></a>Windows 10 更新環

Intune 中的「Windows 10 更新環」策略不能以任何 Microsoft Managed Desktop 裝置為目標。

**未就緒**

您的「更新環」策略會以所有裝置、所有使用者或兩者同時執行。 將群組原則變更為使用工作分派，該工作分派會以不包括任何 Microsoft 受管理之桌面裝置的特定 Azure AD 群組為物件。 有關步驟，請參閱 [Intune 中的管理 Windows 10 軟體更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。

**諮詢**

請確定您擁有的任何更新鈴聲策略不包含新式工作場所裝置 **- 所有** Azure AD 群組。 如果您已經將 Azure AD 使用者群組指派給這些策略，請確定您也排除所有您新增 Microsoft 受管理之桌面使用者至 (或相同群組) 的新式工作場所 **-** 所有 Azure AD 群組。 有關步驟，請參閱 [Intune 中的管理 Windows 10 軟體更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。 新式工作場所裝置 **-** 全部與現代化 **工作場所 - 所有** Azure AD 群組都是我們在您註冊 Microsoft Managed Desktop 時所建立群組，因此您註冊之後必須返回以排除此群組。


## <a name="azure-active-directory-settings"></a>Azure Active Directory 設定

您可以在 Azure 入口網站存取 Azure Active Directory [設定](https://portal.azure.com)。

### <a name="intune-enrollment"></a>Intune 註冊

您 Azure AD 組織的 Windows 10 裝置必須能夠自動在 Intune 註冊。

**諮詢**

請確定 **MDM 使用者範圍已** 設定為部分或 **全部**，而非 **None。** 如果您選擇了一 **些**，請在註冊後返回，然後針對 **群組** 選取新式 **工作場所 -** 所有 Azure AD 群組，或以您所有 Microsoft Managed Desktop 使用者為目標的相同群組。  請參閱 [使用 Microsoft Intune 設定 Windows 裝置註冊](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。


### <a name="ad-hoc-subscriptions"></a>臨時訂閱

建議如何檢查設定， (設定為 「false」時) 企業狀態漫遊無法正確執行。

**諮詢**

請確定 **AllowAdHocSubscriptions 已** 設為 **True。** 否則，企業狀態漫遊可能無法使用。 詳細資訊請參閱[Set-MsolCompanySettings。](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)


### <a name="enterprise-state-roaming"></a>企業狀態漫遊

應啟用企業狀態漫遊。

**諮詢**

確認已針對所有群組或所選群組啟用企業狀態 **漫遊**。 詳細資訊請參閱在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)中啟用企業狀態漫遊。

### <a name="licenses"></a>授權

需要許多授權才能使用 Microsoft Managed Desktop。

**尚未就緒**

您沒有使用 Microsoft Managed Desktop 所需的所有授權。 詳細資訊請參閱 Microsoft [Managed Desktop 技術，](../intro/technologies.md) 以及 [更多授權資訊](prerequisites.md#more-about-licenses)。


### <a name="security-account-names"></a>安全性帳戶名稱

某些安全性帳戶名稱可能會與 Microsoft Managed Desktop 建立的安全性帳戶名稱相衝突。

**未就緒**

您至少有一個帳戶名稱會與 Microsoft Managed Desktop 建立的帳戶名稱相衝突。 請與 Microsoft 客戶代表合作，排除這些帳戶名稱。


### <a name="security-administrator-roles"></a>安全性系統管理員角色

具有特定安全性角色的使用者必須在 Microsoft Defender for Endpoint 中指派這些角色。

**諮詢**

如果您的 Azure AD 組織中已指派使用者至任何這些角色，請確定他們在 Microsoft Defender for Endpoint 中也指派了這些角色。 否則，具有這些角色的系統管理員將無法存取系統管理入口網站。

- 安全性操作員
- 全域讀取者

詳細資訊請參閱建立及 [管理角色型存取控制的角色](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)。


### <a name="security-default"></a>安全性預設值

Azure Active Directory 中的安全性預設值會防止 Microsoft 管理桌面管理您的裝置。

**未就緒**

您開啟了安全性預設值。 關閉安全性預設值並設定條件式存取策略。 有關詳細資訊，請參閱常見的 [條件式存取政策](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。

### <a name="self-service-password-reset"></a>自助密碼重設

自助密碼重設 (SSPR) 可以針對 Microsoft Managed Desktop 服務帳戶除外的所有 Microsoft Managed Desktop 使用者啟用。 有關詳細資訊，請參閱教學課程：讓使用者使用 Azure Active Directory 自助密碼重設來解除鎖定其帳戶或 [重設密碼](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。

**諮詢**

請確定 SSPR **選取** 的設定包含 Microsoft Managed Desktop 使用者，但不包含 Microsoft Managed Desktop 服務帳戶。 啟用 SSPR 時，Microsoft Managed Desktop 服務帳戶無法如預期般使用。  


### <a name="standard-user-role"></a>標準使用者角色

除了被指派全域系統管理員和裝置系統管理員 Azure AD 角色的使用者外，Microsoft Managed Desktop 使用者都是沒有本地系統管理員許可權的標準使用者。 所有其他使用者在啟動其 Microsoft Managed Desktop 裝置時，都會被指派標準使用者角色。

**諮詢**

註冊後，Microsoft 受管理桌面使用者將沒有 Microsoft 受管理桌面裝置上的系統管理員許可權。

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps 企業版

### <a name="onedrive"></a>OneDrive

只有 **加入特定網域設定之** PC 上的允許同步處理功能會與 Microsoft Managed Desktop 衝突。 您可以在 OneDrive 系統管理中心存取 OneDrive [設定](https://admin.onedrive.com)。

**諮詢**

您只在加入特定網域 **設定的電腦使用允許同步** 。 此設定無法與 Microsoft 管理桌上出版一同使用。 停用此設定，並改為設定 OneDrive 使用條件式存取策略。 請參閱 [規劃條件式存取部署以](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 取得協助。

