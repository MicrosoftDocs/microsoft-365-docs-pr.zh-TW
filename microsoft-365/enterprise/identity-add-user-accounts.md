---
title: 步驟 4：新增使用者帳戶
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 直接在雲端中，或透過與內部部署目錄同步處理來新增使用者帳戶和群組。
ms.openlocfilehash: 324d4662f868a4a92693b43c6bc0f75c11f20519
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633101"
---
# <a name="step-4-add-your-user-accounts"></a>步驟 4：新增使用者帳戶

![階段 2 - 身分識別](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-cloud-only"></a>
## <a name="create-your-user-accounts-for-cloud-only-identity"></a>為僅限雲端身分識別建立使用者帳戶

針對僅限雲端身分識別，在 Azure Active Directory (Azure AD) 中建立使用者和群組。 您可以使用：

- Microsoft 365 系統管理中心
- Azure 入口網站
- Azure PowerShell

<a name="identity-sync"></a>
## <a name="synchronize-identities-for-hybrid-identity"></a>同步處理混合式身分識別的身分識別

*此為混合式環境的必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

在這一節中，您會將內部部署 Active Directory 網域服務 (AD DS) 與 Office 365、Microsoft Intune 和 Microsoft 365 企業版隨附的其他雲端式服務所使用的 Azure AD 租用戶同步處理。

Azure AD Connect 是支援的 Microsoft 工具，可逐步引導您將單一或多個樹系 AD DS 環境之中您真正需要的身分識別，同步處理至 Azure AD 租用戶。 下圖顯示 Azure AD Connect 同步處理的基本程序。

![Azure AD Connect 如何同步處理內部部署目錄與 Azure AD ](../media/identity-add-user-accounts/azure-ad-connect.png)

1. 在伺服器上執行的 Azure AD Connect 會輪詢 AD DS 以了解帳戶、群組和連絡人是否有變更。
2. Azure AD Connect 會將這些變更傳送至 Microsoft 365 月租方案的 Azure AD 租用戶。

混合式身分識別解決方案中的第一個決策是驗證需求。選項如下：

- 使用**受控驗證**，Azure AD 會處理使用者登入的驗證程序。受控驗證有兩種方法： 
    - **密碼雜湊同步處理 (PHS)** [某些進階功能的建議和必要方法]。 這是最簡單的方法，可為 Azure AD 中的內部部署目錄物件啟用驗證功能。 Azure AD Connect 會從 AD DS 擷取雜湊的密碼、對密碼雜湊進行額外的安全性處理，並將其同步處理到 Azure AD。 如需詳細資訊，請參閱[使用 Azure AD Connect 同步實作密碼雜湊同步處理](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。
    - **傳遞驗證 (PTA)**，會針對以 Azure AD 為基礎的服務提供簡單的密碼驗證解決方案。 PTA 會使用在一或多個內部部署伺服器上執行的代理程式來直接向內部部署 AD DS 驗證使用者驗證。 如需詳細資訊，請參閱[使用 Azure Active Directory 傳遞驗證的使用者登入](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)。
- 使用**同盟驗證**，在使用者登入時，會透過身分識別同盟伺服器 (例如 Active Directory 同盟服務 (AD FS))，將驗證程序重新導向到另一個身分識別提供者。身分識別提供者可以提供額外的驗證方法，例如智慧卡驗證。如需詳細資訊，請參閱[針對 Azure Active Directory 混合式身分識別解決方案選擇正確的驗證方法](https://docs.microsoft.com/azure/security/azure-ad-choose-authn)。

請觀看這段影片，以大略了解 Microsoft 365 企業版的身分識別模型和驗證。

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

在您決定混合式身分識別解決方案之後，請下載並執行 [IdFix 目錄同步處理錯誤修復工具](https://www.microsoft.com/download/details.aspx?id=36832)來分析 AD DS 的問題。

解決由 IdFix 工具找出的所有問題之後，請參閱[使用 Azure AD Connect 同步來實作密碼雜湊同步處理](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization)，了解如何安裝 Azure AD Connect 工具、設定內部部署 AD DS 和 Microsoft 365 訂閱的 Azure AD 租用戶之間的目錄同步處理。 開始同步處理之後，您要使用內部部署身分識別提供者 (例如 AD DS) 維護使用者帳戶和群組。

Microsoft 會針對[身分識別與裝置存取](microsoft-365-policies-configurations.md)提供一組建議，以確保安全且具有生產力的員工。 

- 如需混合式環境的建議需求，請參閱[必要條件](identity-access-prerequisites.md#prerequisites)中的 [Active Directory 與密碼雜湊同步處理]**** 資料行。 

- 如需僅雲端環境的建議需求，請參閱[必要條件](identity-access-prerequisites.md#prerequisites)中的 [僅雲端]**** 資料行。

內部部署使用者和群組出現在 Azure AD 中之後，您就可以開始指派授權及使用生產力工作負載，例如商務用 OneDrive 和 Exchange Online。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：密碼雜湊同步處理](password-hash-sync-m365-ent-test-environment.md)<br> [測試實驗室指南：傳遞驗證](pass-through-auth-m365-ent-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到對應至這一節的[允出準則](identity-exit-criteria.md#crit-identity-sync)。

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a>監控同步處理健康情況

*此為選用步驟，且同時適用於 Microsoft 365 E3 和 E5 版本*

在這一節中，您會在每個內部部署 AD DS 網域控制站上安裝 Azure AD Connect Health 代理程式，以監控您的身分識別基礎結構，以及由 Azure AD Connect 提供的同步處理服務。 監控資訊會在 Azure AD Connect Health 入口網站提供，您可以在其中檢視警訊、效能監控、使用量分析及其他資訊。

![Azure AD Connect Health 的元件](../media/identity-add-user-accounts/identity-azure-ad-connect-health.png)

如何使用 Azure AD Connect Health 的關鍵設計決策取決於您如何使用 Azure AD Connect：

- 如果您使用的是**受管理的驗證**選項，請先從[使用 Azure AD Connect Health 搭配同步處理](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)開始，以了解並設定 Azure AD Connect Health。
- 如果您使用**同盟驗證**搭配 Active Directory 同盟服務 (AD FS) 來同步處理帳戶及群組名稱，請先從[使用 Azure AD Connect Health 搭配 AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) 開始，以了解並設定 Azure AD Connect Health。

完成這一節後的結果：

- 已在內部部署身分識別提供者伺服器上安裝 Azure AD Connect Health 代理程式。
- Azure AD Connect Health 入口網站會顯示您內部部署基礎結構和同步處理活動的目前狀態以及 Microsoft 365 訂閱的 Azure AD 租用戶。

作為過渡期的檢查點，您可以查看這一節的[允出準則](identity-exit-criteria.md#crit-identity-sync-health)。



<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a>簡化密碼更新

*此為混合式環境的選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

在這一節中，您會允許使用者透過 Azure Active Directory (Azure AD) 重設其密碼，然後複製到本機 Active Directory 網域服務 (AD DS)。 這個程序也稱為密碼回寫。 使用密碼回寫，使用者不需要透過使用者帳戶與其屬性儲存在其中的內部部署 AD DS 來更新其密碼。 對於沒有內部部署網路遠端存取連線的漫遊或遠端使用者而言，這非常有用。

為了充分利用 Azure AD Identity Protection 功能 (例如當偵測到高風險的帳戶洩露時，要求使用者變更其內部部署密碼)，需要密碼回寫。

如需詳細資訊和設定指示，請參閱 [Azure AD SSPR 密碼回寫](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)。

>[!Note]
>升級至最新版的 Azure AD Connect，以確保在新版本發行後能夠使用新功能並獲得最佳體驗。如需詳細資訊，請參閱 [Azure AD Connect 的自訂安裝](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)。
>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：密碼回寫](password-writeback-m365-ent-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-pw-writeback)。

|||
|:-------|:-----|
|![步驟 5](../media/stepnumbers/Step5.png)| [使用群組進行管理](identity-use-group-management.md) |
