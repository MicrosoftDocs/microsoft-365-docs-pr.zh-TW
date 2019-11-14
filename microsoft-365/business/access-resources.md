---
title: 存取內部部署 Microsoft 365 商務版中的 Azure AD 加入裝置的資源
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 了解如何取得行商務應用程式]，檔案共用，例如在內部資源的存取權，以及從 Azure Active Directory 的印表機加入 Windows 10 裝置。
ms.openlocfilehash: fdc1eca6913ba6af4f6b65691fdee2165e7c827e
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2019
ms.locfileid: "38323388"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>存取內部部署 Microsoft 365 商務版中的 Azure AD 加入裝置的資源

任何已加入 Azure Active Directory 的 Windows 10 裝置有權存取所有的雲端式資源，例如您的 Office 365 應用程式，並會受到 Microsoft 365 商務版。 您也可以允許存取內部資源的企業營運 (LOB) 應用程式、 檔案共用和印表機的行，如。 若要允許存取，請使用[Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)與 Azure Active Directory 同步處理您的內部部署 Active Directory。 

若要深入了解，請參閱[在 Azure Active Directory 中的裝置管理的簡介](https://docs.microsoft.com/azure/active-directory/device-management-introduction)。
下列各節也摘要說明的步驟。

## <a name="run-azure-ad-connect"></a>執行 Azure AD Connect

完成下列步驟，以讓您的組織已加入 Azure AD 裝置能夠存取內部部署的資源。
  
1. 若要同步處理您的使用者，群組和連絡人從本機的 Active Directory 至 Azure Active Directory 中，執行 Azure AD Connect 與目錄同步處理精靈中[設定 Office 365 的目錄同步處理](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)所述。
    
2. 目錄同步處理完成後，請確定您組織的 Windows 10 裝置加入 Azure AD。 每個 Windows 10 裝置上分別執行此步驟。 如需詳細資訊，請參閱[為 Microsoft 365 商務版使用者的 Windows 裝置上設定](set-up-windows-devices.md)。 
    
3. 一旦 Windows 10 裝置加入 Azure AD，其裝置和以其 Microsoft 365 商務版認證登入，必須重新啟動每位使用者。 所有的裝置現在有以及內部資源的存取權。
    
沒有額外的步驟，才能取得已加入 Azure AD 裝置的存取內部部署資源。 這項功能是內建於 Windows 10。 
  
如果您的組織尚未準備好在上面所述的 Azure AD 加入的裝置組態中部署，請考慮[混合式 Azure AD Joined 裝置組態](manage-windows-devices.md)設定。
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>當您將 Windows 裝置加入 Azure AD 的考量

如果您的 Azure AD 加入的 Windows 裝置已先前已加入網域或工作群組中，請考慮下列限制：
  
- 當 Azure AD 裝置加入時，它會建立新的使用者，而不參照現有的設定檔。 必須以手動方式移轉設定檔。 使用者設定檔包含如我的最愛、 本機檔案、 瀏覽器設定，以及開始功能表中的設定。 最好的方法是尋找協力廠商工具，將現有的檔案和設定對應至新的設定檔。

- 如果裝置使用群組原則物件 (GPO)，有些 Gpo 可能沒有可以比較[設定服務提供者](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)(CSP) 在 Intune 中。 執行[MMAT 工具](https://www.microsoft.com/download/details.aspx?id=45520)，以尋找現有的 Gpo 相當於今年。

- 使用者將無法驗證依賴 Active Directory 驗證應用程式。 評估舊版應用程式，並考慮更新以盡可能使用新式驗證、 應用程式。

- Active Directory 印表機探索將無法運作。 您可以為所有使用者提供直接的印表機路徑，或使用[混合式雲端列印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。
