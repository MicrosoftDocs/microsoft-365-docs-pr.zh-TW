---
title: 從 Microsoft 365 商務版中已加入 Azure AD 的裝置存取內部部署資源
f1.keywords:
- NOCSH
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 瞭解如何從已加入 Azure Active Directory 的 Windows 10 裝置，存取內部部署資源（如商務線應用程式、檔案共用及印表機）。
ms.openlocfilehash: 9b83781afee746b06bbdf90962de0f55ffbcb118
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307486"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>從 Microsoft 365 商務版 Premium 中已加入 Azure AD 的裝置存取內部部署資源

本文適用于 Microsoft 365 商務版 Premium。

任何已加入 Azure Active Directory 的 Windows 10 裝置都能存取所有雲端架構資源（如您的 Microsoft 365 應用程式），並可由 Microsoft 365 商務版 Premium 進行保護。 您也可以像商務線 (LOB) 應用程式、檔案共用及印表機等方式，允許存取內部部署資源。 若要允許存取，請使用 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) ，將您的內部部署 Active Directory 與 Azure active directory 同步。 

若要深入瞭解，請參閱 [Azure Active Directory 中的裝置管理簡介](https://docs.microsoft.com/azure/active-directory/device-management-introduction)。
下列各節也會摘要說明這些步驟。

> [!IMPORTANT]
> 此程式僅適用于 OAuth 和 NTLM。 不支援 Kerberos。
 
## <a name="run-azure-ad-connect"></a>執行 Azure AD Connect

完成下列步驟，讓您組織的 Azure AD 加入裝置能夠存取內部部署資源。
  
1. 若要將您的使用者、群組和連絡人從本機 Active Directory 同步處理至 Azure Active Directory，請依照 [設定 Office 365 的目錄同步](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)處理中所述，執行目錄同步處理嚮導和 Azure AD Connect。
    
2. 目錄同步處理完成後，請確定您組織的 Windows 10 裝置已加入 Azure AD。 此步驟會在每個 Windows 10 裝置上進行個別的執行。 如需詳細資訊，請參閱 [為 Microsoft 365 商務版使用者設定 Windows 裝置](set-up-windows-devices.md) 。 
    
3. 在 Windows 10 裝置加入 Azure AD 後，每個使用者都必須重新開機其裝置，並使用 Microsoft 365 商務版優質認證登入。 所有裝置現在也可以存取內部部署資源。
    
不需要額外的步驟即可存取 Azure AD 已加入裝置的內部部署資源。 此功能已內置於 Windows 10。 

如果您已計畫登入 AADJ 裝置，但密碼方法（如 PIN 碼/Bio-公制）經由 WHFB 認證登入，則會存取內部部署資源 (共用、印表機）。etc) ，請遵循 https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
如果您的組織未準備好在上述 Azure AD 聯結裝置設定中進行部署，請考慮設定 [混合式 AZURE Ad join 裝置](manage-windows-devices.md)設定。
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>將 Windows 裝置加入 Azure AD 時的考慮

如果您 Azure 加入的 Windows 裝置先前已加入網域或在工作組中，請考慮下列限制：
  
- 當裝置 Azure AD 加入時，它會建立新的使用者，而不會參照現有的設定檔。 設定檔必須手動遷移。 使用者設定檔包含我的最愛、本機檔案、瀏覽器設定及「開始」功能表設定等資訊。 最佳方法是尋找協力廠商工具，將現有的檔案和設定對應至新的設定檔。

- 如果裝置使用的群組原則物件 (GPO) ，有些 Gpo 在 Intune 中可能沒有 (CSP) 的同等 [配置服務提供者](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) 。 執行 [MMAT 工具](https://www.microsoft.com/download/details.aspx?id=45520) ，尋找現有 gpo 的類似 csp。

- 使用者將無法對依存于 Active Directory 驗證的應用程式進行驗證。 評估繼承應用程式，並考慮更新至使用新式驗證的應用程式（如有可能）。

- Active Directory 印表機探索無法運作。 您可以為所有使用者提供直接印表機路徑，或使用 [混合式雲端列印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。
