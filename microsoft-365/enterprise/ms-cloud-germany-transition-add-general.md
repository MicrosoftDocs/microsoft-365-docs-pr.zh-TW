---
title: 從 Microsoft Cloud Deutschland 遷移的其他一般資訊
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：從 Microsoft Cloud (德國移至 Microsoft 雲端 Deutschland 時，服務的其他一般資訊，) 新德文 datacenter 區域中的 Office 365 服務。
ms.openlocfilehash: 93692200f2519dbc647bb4e81b4bd8c646815858
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558427"
---
# <a name="additional-general-information-for-the-migration-from-microsoft-cloud-deutschland"></a>從 Microsoft Cloud Deutschland 遷移的其他一般資訊

下列各節提供有關服務、準備工作考慮和客戶經驗的其他資訊。

## <a name="azure-active-directory"></a>Azure Active Directory

若要完成從 Azure 德文雲端移至 Azure public 雲端，建議您在 OpenID Connect (OIDC) 端點時，將應用程式的驗證端點、Azure Active Directory (Azure AD) 圖表和 MS Graph 端點更新為商業雲端端點，然後 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 開始報告商業性雲端端點。 
 
**我應該在何時進行此變更？**

當您的租使用者完成從德文雲端遷移至商業雲端時，您會在 Azure/Office 入口網站中收到通知。 收到此通知之後，您有30天的時間可完成這些更新，讓您的應用程式繼續適用于從 Azure 德國雲端遷移到 Azure Public 雲端的承租人。
 
更新您的登入授權有三個前置條件：

 - 您租使用者的 OIDC 探索端點會傳回 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` AZURE AD public cloud 端點。

 - 如果您的租使用者已設定同盟，則 Active Directory Federation Services (AD FS) 會更新，以與 Azure AD Public 同步處理。 您可以依照指示更新 Azure AD Connect 設定，以進行此變更。

 - 您的應用程式所使用的資源應用程式（如果有的話）會修改為接受 Azure AD 德國和 Azure AD 公用所簽署的權杖。
 
**什麼類型的應用程式？**

應用程式可能是下列其中一項：

- [單一頁面應用程式 (SPA) ](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [登入使用者的 Web 應用程式](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [呼叫 web APIs 的 web 應用程式](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [受保護的 web API](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [呼叫 web APIs 的 web API](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [桌面應用程式](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [後臺應用程式](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [行動應用程式](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> 當應用程式切換成您的授權使用時 `login.microsoftonline.com` ，會以這個新的授權單位簽署權杖。 如果您主控其他應用程式所撥打的任何資源應用程式，您將需要允許進行寬鬆的權杖驗證。 這表示您的應用程式必須允許 Azure AD 德國和 Azure AD 公用雲端所簽署的權杖。 除非所有呼叫您服務的用戶端應用程式都已完全遷移至 Azure AD public cloud，否則需要進行這種寬鬆的權杖驗證。 遷移之後，您的資源應用程式只需要接受由 Azure AD public 雲端簽署的權杖。

**我需要更新哪些專案？**

1. 如果您是在 Azure 德國用來驗證 Azure 德國或 Office 365 德國使用者的應用程式，請確定在 `https://login.microsoftonline.com` 驗證內容中做為授權使用。

    - 請參閱 Azure AD 驗證上下文。
    - 這兩者皆適用于您的應用程式的驗證，以及對您應用程式 (呼叫的任何 APIs 的驗證，也就是 Microsoft Graph，Azure AD Graph，Azure 資源管理員) 。

2. 將 Azure AD Graph 端點更新為 `https://graph.windows.net` 。

3. 將 MS Graph 端點更新為 `https://graph.microsoft.com` 。

4. 更新任何德國 cloud 端點 (例如 Exchange Online 和 SharePoint Online) 的使用者，這些端點是應用程式用來成為公用雲端的使用者。

5. 更新環境參數，使其 `AzurePublic` (，而不是 `AzureGermany`) 中的系統管理工具和腳本：

    - [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-2.8.0&viewFallbackFrom=azurermps-5.6.0)
    - [Azure AD PowerShell (MSOnline) ](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)
    - [Azure AD PowerShell (AzureAD) ](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)
    - [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)
 
**我發佈的應用程式為何？**

如果您發佈的應用程式可供租使用者以外的使用者使用，您可能需要變更您的應用程式註冊，以確保持續性。 其他使用您應用程式的承租人的移動時間可能會與租使用者的時間不同。 為了確保使用者永遠無法存取應用程式，您需要同意將您的應用程式從 Azure 德國同步處理到 Azure 公用。

### <a name="additional-considerations"></a>其他考量因素

以下是 Azure AD 的其他一些考慮：

- 對於同盟驗證：

  - 當租使用者轉換為處理過程中時，您不能建立、升級或降級同盟網域。 在完成 Azure AD 服務的遷移之後 (租使用者完全完成) ，您可以繼續管理同盟網域。

  - 如果您使用的同盟驗證使用的是 Active Directory Federation Services (AD FS) ，您不應該對發行人 URIs 所做的變更，以用於與您的內部部署 Active Directory 網域服務 (AD DS) 的所有驗證。 變更簽發者 URIs 會導致網域中的使用者驗證失敗。 簽發者 URIs 可以直接在 AD FS 中變更，也可以在將網域從 managed 轉換成同盟時變更，反之亦然。 Microsoft 建議客戶不要新增、移除或轉換要遷移之 Azure AD 租使用者中的同盟網域。 在遷移完全完成後，可以變更發行者 URIs。

- 若為網路：

  - 在 Azure 入口網站中，建立 IPv6 命名的網路無法運作 `http://portal.microsoftazure.de/` 。 使用 Azure 入口網站 `https://portal.azure.com` 建立 IPv6 命名的網路。
 
   - 您無法為 Azure Multi-Factor 驗證建立信任的 IP 位址範圍 (MFA) Microsoft Cloud Deutschland portal 中的服務設定。 使用 Azure AD portal for Office 365 服務來建立 Azure MFA 信任的 IP 位址範圍。


- 若為條件式存取： 

  - 在完成 [AZURE AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 遷移階段) 之後，才支援具有下列授與控制的條件式存取原則 (完成 Office 365 服務的遷移：

    - 需要相容的裝置
    - 需要核准的應用程式
    - 需要應用程式保護原則
    
  - 當租使用者啟用的安全性預設值為 [已停用] 或 [已存在租使用者的條件式存取原則] 時，條件式存取原則介面提供錯誤的警告。 您應該忽略警告或使用 Office 365 服務入口網站來管理條件式存取原則。 

- 僅在租使用者遷移完成後（包括所有 office 工作負載遷移）之後，才會支援 Intune 案例。

- Microsoft Cloud Deutschland 使用行動代理程式更新方法進行 MFA 要求的使用者，可看到使用者 ObjectId (GUID) ，而不是 Microsoft 驗證應用程式中的使用者主體名稱 (UPN) 。 在 Office 365 服務中完成 Azure AD 租使用者的遷移後，新的 Microsoft 驗證者啟用會顯示使用者的 Upn。 現有的 Microsoft 驗證者帳戶會繼續顯示使用者 ObjectId，但他們會繼續使用行動代理程式更新。 

- 針對10月 22 2019 日之後建立的承租人，當租使用者遷移至 Office 365 服務時，可能會為租使用者自動啟用安全性預設值。 租使用者管理員可以選擇讓安全性預設值保持啟用並登錄 MFA，也可以停用此功能。 如需詳細資訊，請參閱 [停用安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)。 

  > [!NOTE]
  > 在遷移期間，未自動啟用的組織可能會在未來自動註冊，因為啟用安全性預設值的功能會在 Office 365 服務中推出。 選擇明確停用或啟用安全性預設值的系統管理員可以在 **Azure Active Directory > 屬性** 下更新功能來執行此動作。 管理員明確啟用該功能之後，將不會自動啟用該功能。

- 當租使用者在遷移後，就會有關于 Office 365 德國入口網站中的 Azure AD Connect 版本和 Office 365 入口網站版本的警告。 如果在遷移完成之後，版本警告不再顯示警告，可以忽略這種情況。 如果在遷移之前或之後有任何警告，請在任一入口網站中更新 Azure AD Connect。 警告訊息說：「我們偵測到您正在使用過期的目錄同步處理工具。 建議您移至 Microsoft 下載中心以取得最新版本的 Azure AD Connect。」

## <a name="exchange-online"></a>Exchange Online 

- `myaccount.msft.com` 只會在轉換 Office 365 之後運作。 連結會產生「發生錯誤」錯誤訊息，直到這段時間為止。

- 在其他環境中存取共用信箱的 Outlook Web App 使用者 (例如，德國環境中的使用者存取全域環境中的共用信箱) 會提示您第二次驗證。 使用者必須先驗證並存取其信箱 `outlook.office.de` ，然後開啟中的共用信箱 `outlook.office365.com` 。 當存取另一個服務中所主控的共用資源時，他們將需要第二次進行驗證。

- 針對現有的 Microsoft Cloud Deutschland 客戶或過渡中的客戶。使用檔案 > 資訊將共用信箱新增至 Outlook 時 **> 新增帳戶**，查看行事曆許可權可能會失敗 (Outlook 用戶端嘗試使用 Rest API `https://outlook.office.de/api/v2.0/Me/Calendars` 。 ) 客戶若要新增帳戶以查看行事曆許可權，您可以新增登錄機碼，如在 [outlook 中共用行事曆的使用者經驗變更](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 中所述，此動作會成功。 使用群組原則，可在整個組織中部署此登錄機碼。

- 在遷移階段，使用 PowerShell Cmdlet **New-new-migrationendpoint**、 **Set-MigrationEndpoint** 和 **MigrationsServerAvailability** 可能會導致 proxy) 上的錯誤 (錯誤。 當仲裁信箱已遷移至世界，但不是由系統管理員信箱遷移時，就會發生這種情況。 若要解決此問題，在建立租使用者 PowerShell 會話時，請使用仲裁信箱做為 **ConnectionUri** 中的路由提示。 例如：`New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- 如果您使用的是 Exchange Online 混合式：

    - 您必須先重新執行混合式設定向導 (HCW) 以在轉換之前更新 Microsoft Cloud Deutschland 的內部部署設定，然後在 Office 365 服務時重新執行 HCW。 如果您使用自訂網域，可能需要其他的 DNS 更新。

如需在此工作負載遷移階段中所需動作的相關資訊，或有關管理或使用影響的詳細資訊，請參閱 Exchange Online 中的 [遷移階段動作和影響](ms-cloud-germany-transition-phases.md#exchange-online)的章節。

## <a name="office-services"></a>Office 服務

Office 中最近使用 (MRU) 服務，是從德國服務切換至 Office 365 服務，而不是遷移。 從 Office.com 入口網站遷移後，只會顯示從 Office 365 服務端的 MRU 連結。 來自德國服務的 MRU 連結在 Office 365 服務中不會顯示為 MRU 連結。 在 Office 365 中，只有在完成承租人遷移後，才能存取 MRU 連結。

## <a name="sharepoint-online-and-onedrive"></a>線上 SharePoint 和 OneDrive

- 當 SharePoint Online 移轉到德國區域完成後，會重新建立資料索引。 與搜尋索引相依的功能可能會受到影響時重建索引完成。

- 如果您的組織仍然使用 SharePoint 2010 工作流程，他們將無法再在 2021 12 月31日之後運作。 SharePoint 2013 工作流程仍然受到支援，不過預設為從 2020 1 月1日開始的新承租人關閉。 在完成 SharePoint 線上服務的遷移之後，建議您移至 [電源自動化] 或其他支援的解決方案。

- OneDrive 遷移至德文地區後，就會重建資料索引。 在建立索引的過程中，取決於搜尋索引的功能可能會受到影響。


## <a name="more-information"></a>詳細資訊

開始：

- [從 Microsoft Cloud Deutschland 遷移至新德文 datacenter 區域中的 Office 365 服務](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移轉協助](https://aka.ms/germanymigrateassist)
- [如何選擇加入移轉](ms-cloud-germany-migration-opt-in.md)
- [遷移期間的客戶體驗](ms-cloud-germany-transition-experience.md)

在轉換中移動：

- [遷移階段的動作和影響](ms-cloud-germany-transition-phases.md)
- [其他預備工作](ms-cloud-germany-transition-add-pre-work.md)
- [服務](ms-cloud-germany-transition-add-general.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。

雲端應用程式：

- [Dynamics 365 的移轉程式資訊](https://aka.ms/d365ceoptin)
- [Power BI 移轉程式資訊](https://aka.ms/pbioptin)
- [開始升級您的 Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
