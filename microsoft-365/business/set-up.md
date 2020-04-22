---
title: 設定 Microsoft 365 商務版 Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 探索 Microsoft 365 商務版 Premium 的設定步驟，包括新增網域和使用者、設定安全性原則等等。
ms.openlocfilehash: a34ede0002e7e78c5dc437c663fe527cf94e46c5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635757"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>在安裝精靈中設定 Microsoft 365 商務版 Premium

請觀看這段影片，以取得 Microsoft 365 商務版特優設定的概要。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

## <a name="add-your-domain-users-and-set-up-policies"></a>新增您的網域、使用者及設定原則

[![[標籤] 可讓您知道系統管理中心正在變更，您可以在 aka.ms/aboutM365preview 取得更多詳細資料。](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

當您購買 Microsoft 365 商務版特優功能時，您可以選擇使用您擁有的網域，或在[註冊](sign-up.md)期間購買一個網域。

- 如果您在註冊時購買了新的網域，您的網域就是全部設定，您可以移至 [新增[使用者] 和 [指派授權](#add-users-and-assign-licenses)]。

### <a name="add-your-domain-to-personalize-sign-in"></a>將您的網域新增至個人化登入

1. 使用您的全域系統管理員認證登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。 

2. 選擇 [**移至設定**] 以啟動嚮導。

    ![選取 [移至設定]。](../media/gotosetupinadmincenter.png)

3. 在 [**安裝您的 Office 應用程式**] 頁面上，您可以選擇性地在您自己的電腦上安裝應用程式。
    
4. 在 [**新增網域**] 步驟中，輸入您要使用的功能變數名稱（例如 contoso.com）。

    > [!IMPORTANT]
    > 如果您是在註冊時購買網域，您將不會在這裡看到 [**新增網域**] 步驟。 請改改為 [[新增使用者](#add-users-and-assign-licenses)]。

    ![個人化登入頁面的螢幕擷取畫面。](../media/adddomain.png)

    
4. 依照嚮導中的步驟，在任何可驗證您擁有網域之[Office 365 的 dns 主機服務提供者處建立 dns 記錄](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。 如果您知道網域主機，請參閱[主機特定指示](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)。

    如果您的主機服務提供者是 GoDaddy 或另一個以[網域](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)連線方式啟用的主機，程式就很容易，而且您將會自動要求您登入，並讓 Microsoft 代表您進行驗證。

    ![在 GoDaddy 確認存取] 頁面上，選取 [授權]。](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>新增使用者並指派授權

您可以在嚮導中新增使用者，但您也可以稍後在系統管理中心[新增使用者](add-users-m365b.md)。 此外，如果您有本機的網域控制站，您可以使用[AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)新增使用者。

#### <a name="add-users-in-the-wizard"></a>在嚮導中新增使用者

您在嚮導中新增的任何使用者會自動指派 Microsoft 365 商務版優質授權。

![嚮導中 [新增使用者] 頁面的螢幕擷取畫面](../media/addnewuserspage.png)

1. 如果您的 Microsoft 365 商務版訂閱有現有的使用者（例如，如果您使用 Azure AD Connect），您可以選擇立即將授權指派給他們。 請繼續進行，為他們新增授權。

2. 在您新增使用者之後，您也會看到一個選項，用來與您新增的新使用者共用認證。 您可以選擇列印認證、透過電子郵件傳送認證，或是下載認證。

### <a name="connect-your-domain"></a>連接您的網域

> [!NOTE]
> 如果您選擇使用 name.onmicrosoft.com17 網域，或使用 Azure AD Connect 來設定使用者，您就不會看到此步驟。
  
若要設定服務，您必須更新 DNS 主機或網域註冊機構中的某些記錄。
  
1. 設定精靈通常會偵測您的註冊機構，並提供您一個逐步指示連結，讓您更新在註冊機構網站上的 NS 記錄。 如果不是，請[變更名稱伺服器以設定 Office 365 與任何網域註冊](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)機構。 

    - 如果您有現有的 DNS 記錄（例如現有的網站），但您的 DNS 主機已啟用[網域](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)連線，請選擇 [**新增我的記錄**]。 在 [**選擇您的線上服務**] 頁面上，接受所有預設值，然後選擇 [**下一步]**，然後在您的 DNS 主機頁面上選擇 [**授權**]。
    - 如果您有現有的 DNS 記錄與其他 DNS 主機（未啟用網域連線），您會想要管理自己的 DNS 記錄，以確保現有的服務保持連線。 如需詳細資訊，請參閱[網域基礎知識](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)。

        ![開機記錄頁面。](../media/activaterecords.png)

2. 依照嚮導中的步驟進行，然後會為您設定電子郵件和其他服務。

### <a name="protect-your-organization"></a>保護您的組織 

您在嚮導中設定的原則會自動套用至稱為「*所有使用者*」的[安全性群組](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups)。 您也可以在系統管理中心建立其他群組，以指派原則。

1. 在 [**加強來自高級網路威脅的保護**] 中，建議您接受預設值，讓[Office 365 的高級威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)掃描 office 應用程式中的檔案和連結。

    ![[增加保護] 頁面的螢幕擷取畫面。](../media/increasetreatprotection.png)


2. 在 [**防止敏感性資料洩漏**] 頁面上，接受預設值以開啟 Office 365 資料遺失防護（DLP）以追蹤 office 應用程式中的機密資料，並防止在組織外意外共用這些資料。

3. 在 [**保護**行動裝置中的資料] 頁面上，將行動應用程式管理留給 [開啟]，展開設定並加以檢查，然後選取 [建立行動裝置**應用程式管理原則**]。

    ![在 [行動裝置] 頁面中保護資料的螢幕擷取畫面。](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>保護 Windows 10 電腦

在左側導覽中，選取 [**安裝**]，然後在 [**共同和安全性**] 底下，選擇 [**保護您的 Windows 10 電腦**]。 選擇 [View] （**查看**）立即開始。 請參閱[保護您的 Windows 10 電腦](secure-win-10-pcs.md)以取得完整的指示。

## <a name="deploy-office-365-client-apps"></a>部署 Office 365 用戶端應用程式

如果您選擇在設定期間自動安裝 Office 應用程式，當使用者從 Windows 裝置登入 Azure AD 時，將會在 Windows 10 裝置上安裝應用程式，並使用其工作認證。

若要在行動裝置 iOS 或 Android 裝置上安裝 Office，請參閱為[Microsoft 365 商務版使用者設定行動裝置](set-up-mobile-devices.md)。

您也可以個別安裝 Office。 請參閱[在 PC 或 Mac 上安裝 Office](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)以取得指示。

## <a name="see-also"></a>請參閱

[Microsoft 365 商務用訓練影片](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
