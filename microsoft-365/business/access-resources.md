---
title: 存取內部部署 Microsoft 365 商務版中的 Azure AD 加入裝置的資源
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 了解如何取得內部資源的存取權，例如線條的商務應用程式、 檔案共用及從 Azure Active Directory 的印表機加入 Windows 10 裝置。
ms.openlocfilehash: 212685bc229f519152e69b09d0a745bfac7a38cd
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276874"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>存取內部部署 Microsoft 365 商務版中的 Azure AD 加入裝置的資源

任何 Windows 10 裝置加入 Azure Active Directory，將有權存取所有雲端為基礎的資源，例如您的 Office 365 應用程式，並可由 Microsoft 365 商務版保護。 也允許存取內部資源的企業營運一行 (LOB) 應用程式、 檔案共用及印表機，您必須使用[Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)與 Azure Active Directory 同步您的內部部署 Active Directory。 若要了解更多的[Azure Active Directory 中的裝置管理簡介](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction)，請參閱。 
  
## <a name="run-azure-ad-connect"></a>執行 Azure AD Connect

完成下列步驟，以讓您的組織已加入 Azure AD 裝置能夠存取內部部署的資源。
  
1. 若要將您的使用者、 群組及連絡人從本機 Active Directory 同步處理到 Azure Active Directory，請執行目錄同步處理精靈，為 Azure AD Connect 所述[設定 Office 365 的目錄同步處理](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)。
    
2. 目錄同步作業完成之後，請確定您組織的 Windows 10 裝置加入 Azure AD。 每個 Windows 10 裝置上分別執行此步驟。 如需詳細資訊，請參閱[為 Microsoft 365 商務版使用者的 Windows 裝置上設定](set-up-windows-devices.md)。 
    
3. 一旦 Windows 10 裝置加入 Azure AD，每位使用者應該重新啟動其裝置並使用其 Microsoft 365 商務版認證登入。 所有的裝置現在有以及內部資源的存取權。
    
沒有額外的步驟，才能存取內部資源的 Azure AD 加入裝置。 這是 Windows 10 中可用的內建功能。 
  
如果您的組織尚未備妥要部署在 Azure AD 加入裝置組態前文所述，請考慮[混合式 Azure AD Joined 裝置組態](manage-windows-devices.md)設定。
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>您的 Windows 裝置加入 Azure AD 時的考量

如果您是加入先前已加入網域的 Windows 裝置的 Azure AD 或工作群組中，您需要考慮下列限制：
  
- 當 Azure AD 裝置加入時，它會建立新的使用者，而不參照現有的設定檔。 若要修正此問題，必須手動移轉設定檔。 使用者設定檔包含像是我的最愛、 本機檔案、 瀏覽器設定、 開始功能表中的設定等資訊。最好的作法是尋找協力廠商工具，將現有的檔案和設定對應至新的設定檔
    
- 如果裝置使用群組原則物件 (GPO)，有些 Gpo 可能沒有可以比較[設定服務提供者](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)(CSP) 在 Intune 中。 執行[MMAT 工具](https://www.microsoft.com/download/details.aspx?id=45520)，以尋找現有的 Gpo 相當於今年。 
    
- 使用者將無法驗證依賴 Active Directory 驗證應用程式。 若要處理這評估使用舊版的應用程式，並考慮更新以盡可能使用新式驗證的應用程式。
    
- Active Directory 印表機探索將無法運作。 若要修正此問題，提供直接的印表機路徑的所有使用者，或利用[混合式雲端列印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。
    

