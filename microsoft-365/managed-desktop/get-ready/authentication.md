---
title: Microsoft 受管理電腦的準備內部部署資源的存取
description: 若要確保 Azure AD 可以與彼此內部部署的重要步驟 AD 以提供驗證
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: c4ebe0c7ad3d1e197cf90cc975366df61d3b0cb5
ms.sourcegitcommit: db52a11eb192a28dbec827c565e36ad4a81d8e3f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901207"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Microsoft 受管理電腦的準備內部部署資源的存取

在 Microsoft 受管理的電腦，裝置會自動加入至 Azure Active Directory (Azure AD)。 這表示，如果您使用內部部署 Active Directory，您必須檢查以確保裝置加入 Azure AD 可以與您在內部部署 Active Directory 通訊的一些事項。 

> [!NOTE]  
> *混合式*Microsoft 受管理的電腦不支援 azure AD 加入。

Azure Active Directory 可讓您利用的單一登入 (SSO)，這表示它們通常不需要提供認證，每次使用資源的使用者。

如需加入 Azure Active Directory 資訊，請參閱 < <b0>How to： 規劃您的 Azure AD 加入實作</b0>。 加入到 Azure AD 裝置上背景資訊關於單一登入 (SSO)，請參閱[如何在內部資源的 SSO 加入 Azure AD 裝置上運作](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)。


本主題說明您需要檢查以確保應用程式和其他資源，取決於本機 Active Directory 連線會搭配順暢 Microsoft 受管理電腦的事項。


## <a name="single-sign-on-for-on-premises-resources"></a>單一登入內部部署資源

Microsoft 受管理的電腦裝置上的預設會啟用單一登入 (SSO) 使用 UPN 和密碼。 但您的使用者也可以使用 Windows Hello 商務，需要一些額外設定步驟。 

### <a name="single-sign-on-by-using-upn-and-password"></a>單一登入使用 UPN 和密碼

在大多數的組織，您的使用者能夠使用 SSO 進行驗證的 UPN 與 Microsoft 受管理的電腦裝置上的密碼。 不過，若要確保這將會運作，您應該仔細檢查下列：

- 請先確認 Azure AD Connect 設定，並使用內部 Active Directory 伺服器上執行 Windows Server 2008 R2 或更新版本。
- 確認 Azure AD Connect 執行支援的版本，且設為同步處理與 Azure AD 這三個屬性： 
    - DNS 網域名稱 （使用者的所在位置） 的內部部署 Active directory
    - NetBIOS （使用者的所在位置） 您內部部署 Active directory
    - SAM 帳戶名稱的使用者


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>單一登入藉由使用 Windows Hello for Business

Microsoft 受管理的電腦裝置也可讓使用者快速、 passwordless 體驗採用 Windows Hello 企業版。 若要確保 Windows Hello 的商務正常沒有您不必提供各自的 UPN 與密碼的使用者，請造訪[設定 Azure AD 加入的內部部署單一登入使用 Windows Hello 企業版的裝置](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)檢查的需求，然後選取依照此處所提供的步驟。


## <a name="apps-and-resources-that-use-authentication"></a>應用程式和使用驗證的資源

Azure 內容設定的完整指南上設定應用程式，以使用 Azure Active Directory 中參照[的應用程式和資源的了解考量](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources)。 摘要： 中


- 如果您使用**雲端式應用程式**，例如新增至 Azure AD 應用程式庫中，大部分不需要任何進一步的準備來搭配 Microsoft 受管理的電腦。 不過，任何未使用 Web 帳戶管理員 (WAM) 的 Win32 應用程式可能仍提示使用者進行驗證。

- 是**裝載內部部署**的應用程式，請務必將這些應用程式新增至您的瀏覽器中的信任的網站清單。 這會啟用 Windows 驗證，才能順利地，而不提示輸入認證的使用者。 若要這麼做，請參閱[組態設定參照](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref)中的[信任的網站](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites)。

- 如果您使用 Active Directory 同盟服務，請檢查使用中的步驟，啟用 SSO[驗證和管理單一登入與 AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))。 

- 會**在內部部署和使用較舊的通訊協定**的應用程式，沒有額外的設定是必要的只要裝置擁有存取權來驗證內部部署網域控制站。 不過，若要提供安全存取這些應用程式，您應該部署 Azure AD 應用程式 Proxy。 如需詳細資訊，請參閱[遠端存取內部部署應用程式，透過 Azure Active Directory 的應用程式 Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)。

- 執行**內部部署和依賴機器驗證**的應用程式不支援，所以您應該考慮取代這些較新版本。

### <a name="network-shares-that-use-authentication"></a>使用驗證的網路共用

沒有額外的設定有使用者存取網路共用，只要裝置透過 UNC 路徑可以存取內部部署網域控制站。

### <a name="printers"></a>印表機

Microsoft 受管理的電腦裝置無法連線至已發佈至您的內部部署 Active Directory 中，除非您已設定[混合式雲端列印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)的印表機。

雖然印表機無法自動探索雲端唯一環境中，您的使用者可以使用內部部署印表機所使用的印表機路徑或印表機佇列路徑，，只要裝置擁有存取權的內部部署網域控制站。

<!--add fuller material on printers when available-->
