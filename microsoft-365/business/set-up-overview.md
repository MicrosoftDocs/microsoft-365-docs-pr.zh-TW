---
title: 步驟概觀
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 瞭解 Microsoft 365 商務版 Premium 的設定步驟，從訂閱、新增網域和使用者、設定安全性原則等等。
ms.openlocfilehash: fa9c02fa9546437c83b9cc6c1f1e6e0d723ec868
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306462"
---
# <a name="overview-of-setup"></a>步驟概觀

觀賞有關 Microsoft 365 商務版 Premium 設定的簡短影片。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

您可以在安裝精靈中執行大部分的設定步驟，但也會列出其他選項。

## <a name="step-1-add-your-domain-and-users"></a>步驟1：新增您的網域和使用者

   - **[新增您的網域](set-up.md#add-your-domain-to-personalize-sign-in)** (若您已在 [註冊](sign-up.md)時購買網域，此步驟已經完成。 ) 

   - **新增使用者**。 您可以以三種方式來新增使用者：
        - 在 [嚮導](set-up.md#add-users-in-the-wizard)中。
        - 如果您有內部部署 Active directory，請使用目錄同步處理以 [使用 AZURE AD Connect 新增使用者](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) 。
        - 您也可以稍後在系統管理中心 [新增使用者](add-users-m365b.md) 。
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>步驟2：設定安全性原則及設定裝置 

  - 使用 [設定向導](set-up.md#protect-your-organization) 來設定裝置原則。 
  - 您也可以在系統 [管理中心](view-policies-and-devices.md) 及 [Intune 入口網站](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)中新增更多內容或進行編輯。
  - 安裝精靈也會設定基本威脅防護和資料遺失防護設定。
  
  除了安裝精靈中的安全性設定之外，您還可以新增下列設定來增加您的安全性：

- **電子郵件惡意程式碼保護**
- **ATP 反網路釣魚**
- **Exchange Online 封存**
- **Azure 資訊保護 (Plan1**) 

若要開始，請參閱 [增加威脅防護](increase-threat-protection.md) 和 [設定規范功能](set-up-compliance.md)。

請參閱 [保護您的 Microsoft 365 商務版的十大方式](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) ，以取得最佳安全性作法的藍圖。

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>步驟3：設定及管理 Windows 10 裝置

在您執行設定向導之後，您會想要 proctect 您組織中的所有 Windwos 10 電腦。
  
- Windows 10 專業版是 Microsoft 365 商務版 [Premium 的必要條件](pre-requisites-for-data-protection.md) ，但如果您有 Windows 7 專業版、Windows 8 專業版或 Windows 8.1 專業人員，您的訂閱可讓您 [升級至 Windows 10 專業](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)版。
- 請遵循 [Secure Windows 10 電腦](secure-win-10-pcs.md) 中的步驟來設定 windows 10 裝置的原則。

當您將 Windows 10 裝置加入 Azure AD 時，您為 Windows 10 電腦所設定的原則會套用至該 AD。 如需詳細資訊，請參閱為 [Microsoft 365 使用者設定 Windows 裝置](set-up-windows-devices.md)。

## <a name="step-4-install-microsoft-365-apps-for-business"></a>步驟4：安裝 Microsoft 365 商務應用程式
- 您可以使用 [ [安裝精靈]](set-up.md#deploy-office-365-client-apps)，在 Windows 裝置中自動安裝 Office。
- 讓使用者安裝適用于 Windows 和裝置的 [Office 應用程式](https://docs.microsoft.com/office365/admin/setup/install-applications) 。
     
## <a name="advanced"></a>進階
- **使用 Autopilot 來設定新裝置**
            
     您可以使用 [Windows Autopilot](add-autopilot-devices-and-profile.md) 為使用者自動預先設定 **新** 的 Windows 10 裝置，但是取得可為您做這項作業的 [合作夥伴](https://www.microsoft.com/solution-providers/search) 會比較容易。 您也可以前往 [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)，並要求雲端技術專家設定您購買的新裝置。

- **存取內部部署的資料**

     - 如果您的組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 商務版 Premium 來保護您的 Windows 10 裝置，同時仍維持對需要本機驗證的內部部署資源的存取。 請遵循下列步驟，將已 [加入網域的 Windows 10 裝置設定為由 Microsoft 365 商務版管理](manage-windows-devices.md) ，以加以設定。 這是慣用的方法，而此狀態的裝置稱為混合式 Azure AD join 裝置。

    - 如果貴公司的本機 Active Directory 中包含某些內部部署資源 (例如檔案共用和印表機) ，您可以遵循下列步驟，將您的 Azure 已加入的裝置提供存取這些資源： [從 Microsoft 365 商務版 Premium 中的 Azure 已加入 Azure 裝置存取內部部署資源](access-resources.md)。

## <a name="see-also"></a>請參閱

[商務用 Microsoft 365 訓練影片](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
