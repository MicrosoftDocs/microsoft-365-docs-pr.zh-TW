---
title: 設定的概觀
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 商務版的步驟設定概觀 >。
ms.openlocfilehash: f156d236a783942ec06d457c9b7ca087d12d6f58
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288568"
---
# <a name="overview-of-setup"></a>安裝程式的概觀

可以在安裝程式精靈] 完成大部分的設定步驟，但也會列出其他選項。


## <a name="step-1-add-your-domain-and-users"></a>步驟 1： 加入您的網域和使用者

   - **[新增您的網域](set-up.md#add-your-domain-to-personalize-sign-in)**（如果您在[註冊](sign-up.md)購買您的網域，為已完成這個步驟。）

    - **新增使用者**。 您可以在任何的三種方式：
        - 在[精靈](set-up.md#add-users-in-the-wizard)中。
        - 如果您有內部部署 Active directory，請使用新增[的使用者使用 Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)目錄同步處理。
        - 您也可以在系統管理中心的 [[新增使用者更新版本](add-users-m365b.md)。
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>步驟 2： 設定安全性原則和設定裝置 

  - 使用[安裝精靈](set-up.md#set-up-security-policies-and-device-configurations)來設定裝置和安全性原則。 
  - 您也可以新增更多，或稍後在[系統管理中心](view-policies-and-devices.md)和[Intune 入口網站](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)中加以編輯。
  - 除了在安裝精靈中的安全性設定，您可以藉由新增下列設定值增加您的安全性：

      - **電子郵件的惡意程式碼保護**
      - **進階的威脅防護 (ATP) 的安全連結**
      - **ATP 安全附件**
      - **ATP 防網路釣魚**
      - **Exchange Online 封存**
      - **Data Loss Prevention (DLP)**
      - **Azure 資訊保護 (Plan1**)

          若要取得啟動，請參閱[設定進階的安全性原則](set-up-advanced-security.md)。

        另請參閱[上方的 10 種方法來保護您的 Microsoft 365 商務版](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)的最佳安全性作法藍圖。

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>步驟 3： 設定及管理 Windows 10 裝置

   當您在 Windows 10 裝置加入 Azure AD 時，取得套用您在[步驟 2](#step-2-set-up-security-policies-and-configure-devices)中設定的原則。

   - Windows 10 專業版是 Microsoft 365 商務版的[必要條件](pre-requisites-for-data-protection.md)，但如果您有 Windows 7 專業版、 Windows 8 專業版或 Windows 8.1 專業版，您的訂閱賦與您[升級至 Windows 10 專業版](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)。
    - 使用[安裝精靈](set-up.md#set-up-security-policies-and-device-configurations)來設定 Windows 10 裝置原則。

## <a name="stes-4-install-office-365-business"></a>Stes 4： 安裝 Office 365 商務版
- 您可以使用[安裝精靈](set-up.md#deploy-office-365-client-apps)，在 Windows 裝置上自動安裝 Office。
- 從自動[安裝 Office](auto-install-or-uninstall-office.md)系統管理中心。
- Windows 和裝置，可讓使用者[安裝 Office 應用程式](https://docs.microsoft.com/office365/admin/setup/install-applications)。
     
## <a name="advanced"></a>進階
- **使用 Autopilot 來設定新裝置**
            
     您可以使用[Windows Autopilot](add-autopilot-devices-and-profile.md)來自動預先設定**新**的 Windows 10 裝置的使用者，但它可能會比較容易取得[合作夥伴](https://www.microsoft.com/solution-providers/search)可以執行這項操作您。 您也可以移至[Microsoft 網上商店](https://go.microsoft.com/fwlink/?linkid=874598)，並要求您購買您的新裝置上設定雲端技術專家。

- **存取內部部署資源**

     - 如果您的組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 商務版來保護 Windows 10 裝置，同時仍維持需要本機驗證的內部部署資源的存取權。 請遵循[啟用由 Microsoft 365 商務版來管理已加入網域的 Windows 10 裝置](manage-windows-devices.md)設定此案例中的步驟。 這是慣用的方法，在此狀態的裝置稱為混合式 Azure AD 加入的裝置。

    - 如果貴公司有本機 Active Directory，其中包含一些內部資源 （例如檔案共用和印表機），您可以授與您的 Azure AD 加入的裝置存取這些資源遵循以下步驟：[存取內部部署資源Microsoft 365 商務版中的 azure AD 加入裝置](access-resources.md)。

  