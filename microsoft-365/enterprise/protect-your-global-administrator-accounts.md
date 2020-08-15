---
title: 保護您的 Microsoft 365 全域管理員帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/15/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: 本文提供保護 Microsoft 365 訂閱之全域管理員存取的相關資訊。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 08e0960e7150395b2997dbd9ff0a1818822e17e2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695595"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>保護您的 Microsoft 365 全域管理員帳戶

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Microsoft 365 訂閱的安全性違規（包括資訊竊取和網路釣魚攻擊）通常會危及 Microsoft 365 全域管理員帳戶的認證。 雲端的安全性是您和 Microsoft 之間的合作關係：
  
- Microsoft 雲端服務是以信任和安全性的基礎來建立的。 Microsoft 提供的安全性控制和功能可協助您保護您的資料和應用程式。
    
- 您擁有資料和身分識別，以及保護它們的責任、內部部署資源的安全性，以及您所控制之雲端元件的安全性。
    
Microsoft 提供的功能可協助保護您的組織，但只有在您使用這些功能時，才會有效。 如果您不使用它們，可能會受到攻擊。 為了保護您的全域系統管理員帳戶，Microsoft 可在這裡協助您瞭解下列各專案的詳細指示：
  
1. 建立專屬的 Microsoft 365 全域管理員帳戶，並只在必要時使用。
    
2. 為您專屬的 Microsoft 365 全域管理員帳戶設定多重要素驗證，並使用最強形式的次要驗證。
    
> [!附注] 雖然此篇文章著重于全域管理員帳戶，但您應該考慮是否有其他具有廣域許可權的帳戶，以存取您訂閱中的資料（例如 eDiscovery 管理員或安全性或合規性管理員帳戶），應以相同的方式加以保護。 <br > 您可以建立全域管理員帳戶，而不需要新增任何授權。
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>步驟 1： 建立專屬的 Microsoft 365 全域管理員帳戶，並只在必要時加以使用

需要全域管理員許可權的系統管理工作相對較少，例如指派角色給使用者帳戶。 因此，請執行下列步驟，而不是使用已獲指派全域系統管理員角色的日常使用者帳戶：
  
1. 決定已指派全域系統管理員角色的使用者帳戶集。 您可以使用 Azure Active (Azure AD) Directory PowerShell for Graph] 命令來執行這項操作：
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. 使用已獲指派全域系統管理員角色的使用者帳戶，登入您的 Microsoft 365 訂閱。
    
3. 建立最多四個專用全域系統管理員使用者帳戶。 **使用強式密碼的長度至少12個字元。** 請參閱 [建立強式密碼](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) 以取得詳細資訊。 將新帳戶的密碼儲存在安全的位置。 
    
4. 將全域管理員角色指派給每個新的專屬全域系統管理員使用者帳戶。
    
5. 登出 Microsoft 365。
    
6. 使用其中一個新的專屬全域系統管理員使用者帳戶登入。
    
7. 針對每個已指派步驟1之全域系統管理員角色的現有使用者帳戶：
    
  - 移除全域系統管理員角色。
    
  - 將系統管理員角色指派給適當于該使用者工作職能和責任的帳戶。 如需 Microsoft 365 中各種系統管理員角色的詳細資訊，請參閱 [關於系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。
    
8. 登出 Microsoft 365。
    
結果應該是：
  
- 您的訂閱中唯一擁有全域系統管理員角色的使用者帳戶，就是新建立的一組專用全域系統管理員帳戶。 使用下列 PowerShell 命令進行驗證：
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- 管理您訂閱的所有其他日常使用者帳戶擁有指派的系統管理員角色，這些角色會與他們的工作職責相關聯。
    
自現在起，您只需在需要全域系統管理員許可權的工作中登入專用全域管理員帳戶。 所有其他 Microsoft 365 管理都必須透過指派其他系統管理角色給使用者帳戶來執行。
  
> [!NOTE]
> 這需要其他步驟以您的日常使用者帳戶登出，並以專用全域管理員帳戶登入。 但是這只需要偶爾進行全域管理員作業。 請考慮在全域管理員帳戶遭到破壞之後復原 Microsoft 365 訂閱需要進行許多步驟。
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts-and-use-the-strongest-form-of-additional-verification"></a>步驟 2： 為專用的 Microsoft 365 全域管理員帳戶設定多重要素驗證，並使用最強的額外驗證形式

多重要素驗證 (MFA) 需要帳戶名稱和密碼以外的其他資訊。 Microsoft 365 支援下列其他驗證方法：
  
- Microsoft Authenticator 應用程式

- 電話
    
- 透過短信傳送的隨機產生的驗證程式代碼
    
- 智慧卡 (虛擬或實體)
    
- 生物特徵辨識裝置
    
>[!Note]
>針對必須遵守全國研究院標準及技術的組織 (NIST) 標準，會限制使用電話通話或以文字訊息為基礎的其他驗證方法。 如需詳細資訊，請按一下 [這裡](https://pages.nist.gov/800-63-FAQ/#q-b01) 。
>

如果您是一位小型企業，使用僅儲存在雲端中的使用者帳戶 (僅限雲端身分識別模型) ，請使用下列步驟，使用傳送至 smart phone 的來電或短信驗證碼，設定 MFA：
  
1. [設定 MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)。
    
2. [設定 Microsoft 365 的 MFA](https://support.office.com/article/Set-up-2-step-verification-for-Office-365-ace1d096-61e5-449b-a875-58eb3d74de14) ，以設定電話通話或短信的各個專屬全域管理員帳戶為驗證方法。 
    
如果您是較大的組織，且使用的是 Microsoft 365 混合式身分識別模型，您會有更多驗證選項。 如果您已將安全性基礎結構放在適當的次要驗證方法中，請使用下列步驟：
  
1. [設定 MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)。
    
2. 為[您的新全域管理員帳戶設定 MFA](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14) ，以設定每個專用全域管理員帳戶的適當驗證方法。 
    
如果所需強驗證方法的安全性基礎結構不存在，且無法在 Microsoft 365 MFA 中運作，我們強烈建議您使用 Microsoft 驗證程式應用程式、電話通話或為全域系統管理員帳戶傳送至智慧型電話的電子郵件驗證碼，設定具有 MFA 的專屬全域管理員帳戶，以作為過渡的安全性度量單位。 請勿留下專屬全域管理員帳戶，除非 MFA 提供額外的保護。
  
如需詳細資訊，請參閱 [規劃 Microsoft 365 部署的多重要素驗證](https://docs.microsoft.com/office365/admin/security-and-compliance/multi-factor-authentication-plan)。
  
若要使用 MFA 和 PowerShell 連接至 Microsoft 365 服務，請參閱下列文章：

- [針對使用者帳戶、群組和授權的 Microsoft 365 PowerShell](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
- [Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-by-using-mfa)
- [SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [商務用 skype Online] 管理-使用中商務用 skype-線上-365-a-a-a-a-a-a-a-a-a-a-a-a-a a-a-a) -a-a

## <a name="additional-protections-for-enterprise-organizations"></a>企業組織的其他保護

步驟1和2之後，請使用這些額外的方法，以確保您的全域系統管理員帳戶和您使用它執行的設定盡可能安全。
  
### <a name="privileged-access-workstation"></a>許可權存取工作站

為了確保高特權工作的執行盡可能安全，請使用一種特殊許可權存取工作站 (PAW) 。 PAW 是一種專用的電腦，只用于機密設定工作，例如要求全域管理員帳戶的 Microsoft 365 設定。 由於這部電腦不會在每日使用網際網路流覽或傳送電子郵件，因此可從網際網路攻擊和威脅中獲得更好的保護。
  
如需如何設定 PAW 的指示，請參閱 [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw) 。
  
### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

您可以使用 Azure AD 特權身分識別管理 (PIM) ，以在需要時立即為全域系統管理員角色指派，而不是讓全域系統管理員帳戶永久指派全域系統管理員角色。
  
而非全域系統管理員帳戶是永久管理員，他們會變成合格的系統管理員。 全域系統管理員角色會停用，直到某人需要為止。 然後，您會完成啟用程式，將全域系統管理員角色新增到全域管理員帳戶中的預先決定的時間長度。 當時間到期時，PIM 會從全域管理員帳戶移除全域系統管理員角色。
  
使用 PIM 和此程式可大幅減少全域管理員帳戶受到惡意使用者攻擊和使用的時間量。

PIM 可與 Azure AD Premium P2 搭配使用，其隨附于 Microsoft 365 企業版 E5 或 Enterprise 可移動性 + Security (EMS) E5，您也可以為全域系統管理員帳戶購買個別的授權。
  
如需詳細資訊，請參閱 [AZURE AD 特權身分識別管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。
  
### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>Microsoft 365 記錄的安全性資訊和事件管理 (SIEM) 軟體

在伺服器上執行的 SIEM 軟體會即時分析應用程式和網路硬體所建立的安全性警示和事件。 若要讓您的 SIEM 伺服器在其分析和報告功能中包含 Microsoft 365 的安全性警示和事件，請整合 Azure AD 至您的 SEIM。 請參閱 [Azure 記錄整合簡介](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview)。

## <a name="next-step"></a>下一步

如果您正在設定 Microsoft 365 訂閱的身分識別，請參閱：

- [僅限雲端](cloud-only-identities.md) 身分識別（如果您使用僅限雲端身分識別）
- 如果您使用的是混合身分識別，[準備目錄同步](prepare-for-directory-synchronization.md)處理

  
## <a name="see-also"></a>請參閱

[Microsoft 365 安全性藍圖](https://docs.microsoft.com/office365/securitycompliance/security-roadmap)。
