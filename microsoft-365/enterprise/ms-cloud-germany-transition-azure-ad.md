---
title: 從 Microsoft Cloud Deutschland 遷移的其他 Azure Active Directory 資訊
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
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
description: 摘要：從 microsoft cloud 德國 (microsoft cloud Deutschland) 移至新德文 datacenter 區域中 Office 365 服務時的其他 Azure Active Directory 資訊。
ms.openlocfilehash: 0e7abd68945a9b685a33c120ff1e92fda62b2c56
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362723"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>從 Microsoft Cloud Deutschland 遷移的其他 Azure Active Directory 資訊

若要完成從 azure 德文雲端移至 azure public 雲端，建議您在 Graph OpenID 連線 OIDC (端點時，將應用程式的驗證端點、Azure Active Directory (Azure AD) Graph 及 MS) 端點更新為商業雲端的使用者，然後 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 開始報告商業性雲端端點。 
 
**我應該在何時進行此變更？**

當您的租使用者完成從德文雲端到商業雲端的遷移時，您會收到 Azure/Office 入口網站中的通知。 收到此通知之後，您有30天的時間可完成這些更新，讓您的應用程式繼續適用于從 Azure 德國雲端遷移到 Azure Public 雲端的承租人。
 
更新您的登入授權有三個前置條件：

 - 您租使用者的 OIDC 探索端點會傳回 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` AZURE AD public cloud 端點。

 - 如果您的租使用者已設定同盟，則 Active Directory Federation Services (AD FS) 會更新，以與 Azure AD Public 同步處理。 您可以依照指示更新 Azure AD 連線設定，以進行此變更。

 - 您的應用程式所使用的資源應用程式（如果有的話）會修改為接受 Azure AD 德國和 Azure AD 公用所簽署的權杖。
 
**什麼類型的應用程式？**

應用程式可能是下列其中一項：

- [單一頁面應用程式 (SPA) ](/azure/active-directory/develop/scenario-spa-overview)
- [登入使用者的 Web 應用程式](/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [呼叫 web APIs 的 web 應用程式](/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [受保護的 web API](/azure/active-directory/develop/scenario-protected-web-api-overview)
- [呼叫 web APIs 的 web API](/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [桌面應用程式](/azure/active-directory/develop/scenario-desktop-overview)
- [後臺應用程式](/azure/active-directory/develop/scenario-daemon-overview)
- [行動應用程式](/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> 當應用程式切換成您的授權使用時 `login.microsoftonline.com` ，會以這個新的授權單位簽署權杖。 如果您主控其他應用程式所撥打的任何資源應用程式，您將需要允許進行寬鬆的權杖驗證。 這表示您的應用程式必須允許 Azure AD 德國和 Azure AD 公用雲端所簽署的權杖。 除非所有呼叫您服務的用戶端應用程式都已完全遷移至 Azure AD public cloud，否則需要進行這種寬鬆的權杖驗證。 遷移之後，您的資源應用程式只需要接受由 Azure AD public 雲端簽署的權杖。

**我需要更新哪些專案？**

1. 如果您是在 azure 德國用來驗證 azure 德國或 Office 365 德國使用者的應用程式，請確定在 `https://login.microsoftonline.com` 驗證內容中做為授權使用。

    - 請參閱 Azure AD 驗證上下文。
    - 這兩者皆適用于您的應用程式的驗證，以及對您應用程式 (呼叫的任何 APIs 的驗證，也就是 Microsoft Graph，azure AD Graph，azure 資源管理員) 。

2. 將 Azure AD Graph 端點更新為 `https://graph.windows.net` 。

3. 將 MS Graph 端點更新為 `https://graph.microsoft.com` 。

4. 更新任何德國 cloud 端點 (例如 Exchange Online 和 SharePoint 線上) 所用的應用程式，讓應用程式成為公用雲端的端點。

5. 更新環境參數，使其 `AzurePublic` (，而不是 `AzureGermany`) 中的系統管理工具和腳本：

    - [Azure PowerShell](/powershell/azure/install-az-ps)
    - [Azure AD PowerShell (MSOnline) ](/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell (AzureAD) ](/powershell/azure/active-directory/install-adv2)
    - [Azure CLI](/cli/azure/install-azure-cli)
 
**我發佈的應用程式為何？**

如果您發佈的應用程式可供租使用者以外的使用者使用，您可能需要變更您的應用程式註冊，以確保持續性。 其他使用您應用程式的承租人的移動時間可能會與租使用者的時間不同。 為了確保使用者永遠無法存取應用程式，您需要同意將您的應用程式從 Azure 德國同步處理到 Azure 公用。

**如何在遷移期間新增多租使用者應用程式？**

如果您想要使用由其他組織發佈的新應用程式 (多租使用者應用程式) 您將在遷移過程中受到限制，無法在遷移過程中新增該應用程式 (階段2到階段 9) 。  當您的組織完成階段9，而且已完全轉換至 Azure 公用實例時，您可能會執行此工作。

## <a name="additional-considerations"></a>其他考量

以下是 Azure AD 的其他一些考慮：

- 對於同盟驗證：

  - 當租使用者轉換為處理過程中時，您不能建立、升級或降級同盟網域。 在完成 Azure AD 服務的遷移之後 (租使用者完全完成) ，您可以繼續管理同盟網域。

  - 如果您使用的同盟驗證使用的是 Active Directory Federation Services (AD FS) ，您不應該對發行人 URIs 所做的變更，以用於與您的內部部署 Active Directory 網域服務 (AD DS) 的所有驗證。 變更簽發者 URIs 會導致網域中的使用者驗證失敗。 簽發者 URIs 可以直接在 AD FS 中變更，也可以在將網域從 managed 轉換成同盟時變更，反之亦然。 Microsoft 建議客戶不要新增、移除或轉換要遷移之 Azure AD 租使用者中的同盟網域。 在遷移完全完成後，可以變更發行者 URIs。

- 若為網路：

  - 在 Azure 入口網站中，建立 IPv6 命名的網路無法運作 `http://portal.microsoftazure.de/` 。 使用 Azure 入口網站 `https://portal.azure.com` 建立 IPv6 命名的網路。
 
   - 您無法為 Azure Multi-Factor 驗證建立信任的 IP 位址範圍 (MFA) Microsoft Cloud Deutschland portal 中的服務設定。 使用 azure AD 入口網站以取得 Office 365 服務，以建立 Azure MFA 信任的 IP 位址範圍。


- 若為條件式存取： 

  - 在完成[Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized)遷移階段) 之後，才支援具有下列授與控制的條件式存取原則 (完成 Office 365 服務的遷移：

    - 需要相容的裝置
    - 需要核准的應用程式
    - 需要應用程式保護原則
    
  - 當租使用者啟用的安全性預設值為 [已停用] 或 [已存在租使用者的條件式存取原則] 時，條件式存取原則介面提供錯誤的警告。 您應該忽略警告，或使用 Office 365 服務入口網站來管理條件式存取原則。 

- 僅在租使用者遷移完成後（包括所有 office 工作負載遷移）之後，才會支援 Intune 案例。

- Microsoft Cloud Deutschland 使用行動代理程式更新方法進行 MFA 要求的使用者，可看到使用者 ObjectId (GUID) ，而不是) 應用程式中的使用者主體名稱 (UPN Microsoft Authenticator。 當 Azure AD 租使用者完成且裝載在 Office 365 服務中之後，新的 Microsoft Authenticator 啟用會顯示使用者的 upn。 現有的 Microsoft Authenticator 帳戶會繼續顯示使用者 ObjectId，但他們會繼續使用行動代理程式更新。 

- 針對10月 22 2019 日之後建立的承租人，當租使用者遷移至 Office 365 服務時，可能會為租使用者自動啟用安全性預設值。 租使用者管理員可以選擇讓安全性預設值保持啟用並登錄 MFA，也可以停用此功能。 如需詳細資訊，請參閱 [停用安全性預設值](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)。 

  > [!NOTE]
  > 在遷移期間，未自動啟用的組織可能會在未來自動註冊，因為啟用安全性預設值的功能會在 Office 365 服務中進行。 選擇明確停用或啟用安全性預設值的系統管理員可以更新 **Azure Active Directory > 屬性**] 底下的功能來執行此動作。 管理員明確啟用該功能之後，將不會自動啟用該功能。

- 當租使用者在進行遷移時，會出現有關 Office 365 德國入口網站中的 Azure AD 連線版本和 Office 365 入口網站的警告。 如果在遷移完成之後，版本警告不再顯示警告，可以忽略這種情況。 如果在遷移之前或之後有任何警告，請在任一入口網站中更新 Azure AD 連線。 警告訊息說：「我們偵測到您正在使用過期的目錄同步處理工具。 建議您移至 Microsoft 下載中心，以取得最新版的 Azure AD 連線。」

## <a name="more-information"></a>其他相關資訊

開始：

- [從 Microsoft Cloud Deutschland 遷移至新德國資料中心區域的 Office 365 服務](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移轉協助](https://aka.ms/germanymigrateassist)
- [如何選擇加入移轉](ms-cloud-germany-migration-opt-in.md)
- [遷移期間的客戶體驗](ms-cloud-germany-transition-experience.md)

在轉換中移動：

- [移轉階段的動作與影響](ms-cloud-germany-transition-phases.md)
- [其他預備工作](ms-cloud-germany-transition-add-pre-work.md)
- [AZURE AD](ms-cloud-germany-transition-azure-ad.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。

雲端應用程式：

- [Dynamics 365 的移轉程式資訊](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 移轉程式資訊](/power-bi/admin/service-admin-migrate-data-germany)
- [開始升級您的 Microsoft Teams](/microsoftteams/upgrade-start-here)
