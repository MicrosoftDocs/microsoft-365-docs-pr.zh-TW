---
title: 為 Microsoft 受管理的電腦準備備內部部署資源存取權
description: 確定 Azure AD 可以與內部部署 AD 通訊以提供驗證的重要步驟
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 6df23e0d7e3ea0ecd7ebacd96f00cb47b9e0aa84
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574592"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>為 Microsoft 受管理的電腦準備備內部部署資源存取權

在 Microsoft 受管理的電腦中，裝置會自動加入 Azure Active Directory (Azure AD) 。 因此，如果您使用內部部署 Active Directory，您必須檢查一些事項，以確保加入 Azure AD 的裝置可以與您的內部部署 Active Directory 通訊。 

> [!NOTE]  
> *混合* Microsoft 受管理的電腦不支援 Azure AD join。

Azure Active Directory 可讓您的使用者利用單一 Sign-On (SSO) ，這表示在每次使用資源時，通常不需要提供認證。

如需加入 Azure Active Directory 的詳細資訊，請參閱 how [to： Plan a Azure AD join 實現](/azure/active-directory/devices/azureadjoin-plan)。 如需有關加入 Azure AD 之裝置上的單一 Sign-On (SSO) 的背景資訊，請參閱 [在 AZURE ad join 裝置上如何運作 sso 與內部部署資源的運作方式](/azure/active-directory/devices/azuread-join-sso#how-it-works)。


本文說明您必須檢查哪些專案，以確保依存于本機 Active Directory 連線的應用程式和其他資源能夠與 Microsoft 受管理的電腦順利運作。


## <a name="single-sign-on-for-on-premises-resources"></a>內部部署資源的單一 Sign-On

單一 Sign-On (SSO) 使用 UPN 和密碼預設會在 Microsoft 受管理的電腦裝置上啟用。 不過，您的使用者也可以使用 Windows Hello 企業版，需要一些額外的設定步驟。 

### <a name="single-sign-on-by-using-upn-and-password"></a>使用 UPN 及密碼的單一 Sign-On

在大多數的組織中，您的使用者將可以使用 SSO，在 Microsoft 受管理的電腦裝置上以 UPN 和密碼進行驗證。 不過，為了確保此函數能夠運作，您應該仔細檢查下列專案：

- 確認已設定 Azure AD 連線，並使用執行 Windows server 2008 R2 或更新版本的內部部署 Active Directory 伺服器。
- 確認 Azure AD 連線執行的是支援的版本，且設定為與 Azure AD 同步處理這三個屬性： 
    - 使用者所在之內部部署 Active Directory (的 DNS 功能變數名稱) 
    - 使用者所在的內部部署 Active Directory (NetBIOS) 
    - SAM 帳戶的使用者名稱


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>使用 Windows Hello 企業版的單一 Sign-On

Microsoft 受管理的電腦裝置也會透過使用 Windows Hello 企業版，為您的使用者提供快速、passwordless 的體驗。 為了確保您的使用者在不需要提供各自的 UPN 和密碼的情況下可運作 Windows Hello 企業版，請參閱[Configure the Azure AD join 裝置 for 內部部署 Single-Sign 使用 Windows Hello 企業版](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)以檢查需求，然後遵循這裡提供的步驟。


## <a name="apps-and-resources-that-use-authentication"></a>使用驗證的應用程式和資源

請參閱 Azure 內容組中[應用程式和資源的瞭解考慮](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources)，以取得設定使用 Azure Active Directory 之應用程式的完整指導方針。 總結：


- 如果您使用 **雲端式應用程式**，例如新增至 Azure AD 應用程式庫的應用程式，則不需要進一步準備使用 Microsoft 受管理的電腦。 不過，任何未使用網頁帳戶管理員的 Win32 應用程式 (WAM) 可能仍然會提示使用者進行驗證。

- 若為 **內部部署所主控** 的應用程式，請務必將這些應用程式新增至您的瀏覽器中的 [信任的網站] 清單。 此步驟可讓 Windows 驗證順利運作，而不會提示使用者輸入認證。 若要新增應用程式，請參閱[可設定的設定參考](../working-with-managed-desktop/config-setting-ref.md)中的[信任網站](../working-with-managed-desktop/config-setting-ref.md#trusted-sites)。

- 如果您使用的是 Active Directory 同盟服務，請檢查是否已啟用 SSO，方法是使用 [ [驗證] 和 [管理單一登入與 AD FS](/previous-versions/azure/azure-services/jj151809(v=azure.100))] 中的步驟。 

- 若為 **內部部署和使用舊版通訊協定** 的應用程式，則不需要額外設定，只要裝置可以存取內部部署網域控制站以進行驗證。 不過，若要提供這些應用程式的安全存取，您應該部署 Azure AD 應用程式 Proxy。 如需詳細資訊，請參閱[透過 Azure Active Directory 的應用程式 Proxy 遠端存取內部部署應用程式](/azure/active-directory/manage-apps/application-proxy)。

- **在內部部署和依賴機器驗證** 的應用程式不受支援，因此您應該考慮將它們取代為更新的版本。

### <a name="network-shares-that-use-authentication"></a>使用驗證的網路共用

只要裝置具有使用 UNC 路徑的內部部署網域控制站存取權，使用者才能存取網路共用，不需要額外的設定。

### <a name="printers"></a>印表機

除非您已設定[混合式雲端列印](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)，否則 Microsoft 受管理的電腦裝置無法連接至發佈至內部部署 Active Directory 的印表機。

雖然無法在僅雲端環境中自動探索印表機，但只要裝置具有內部部署網域控制站的存取權，您的使用者就可以使用印表機路徑或印表機佇列路徑來使用內部部署印表機。

<!--add fuller material on printers when available-->
## <a name="steps-to-get-ready"></a>準備就緒的步驟

1. 審查[Microsoft 受管理的電腦的必要條件](prerequisites.md)。
2. 使用 [準備工作評估工具](readiness-assessment-tool.md)。
3. [來賓帳戶的先決條件](guest-accounts.md)
4. [Microsoft 受管理的電腦的網路設定](network.md)
5. [為 Microsoft 受管理的電腦準備認證和網路設定檔](certs-wifi-lan.md)
6. [準備 Microsoft 受管理的電腦 (本文的內部部署資源存取權](authentication.md)) 
7. [Microsoft 受管理的電腦中的應用程式](apps.md)
8. [為 Microsoft 受管理的電腦準備對應磁碟機](mapped-drives.md)
9. [為 Microsoft 受管理的電腦準備列印資源](printing.md)
