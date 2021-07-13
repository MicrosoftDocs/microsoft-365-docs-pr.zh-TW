---
title: 從 Microsoft 365 商務中 Azure 已加入 Azure 的裝置存取內部部署資源
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 瞭解如何從加入 Windows 10 裝置的 Azure Active Directory，取得內部部署資源（如商務用行應用程式、檔案共用及印表機）的存取權。
ms.openlocfilehash: 71d60e0187c917dffb7390afcedf22dc73f44008
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393452"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>從 Microsoft 365 商務進階版中已加入 Azure AD 的裝置存取內部部署資源

本文適用于 Microsoft 365 商務進階版。

任何 Azure Active Directory 加入的 Windows 10 裝置都能存取所有雲端架構資源（如您的 Microsoft 365 應用程式），並可透過 Microsoft 365 商務進階版加以保護。 您也可以像商務線 (LOB) 應用程式、檔案共用及印表機等方式，允許存取內部部署資源。 若要允許存取，請使用[Azure AD 連線](/azure/active-directory/connect/active-directory-aadconnect)與 Azure Active Directory 同步您的內部部署 Active Directory。

若要深入瞭解，請參閱[Azure Active Directory 中的裝置管理簡介](/azure/active-directory/device-management-introduction)。
下列各節也會摘要說明這些步驟。

## <a name="run-azure-ad-connect"></a>執行 Azure AD 連線

完成下列步驟，讓您組織的 Azure AD 加入裝置能夠存取內部部署資源。

1. 若要將您的使用者、群組和連絡人從本機 Active Directory 同步處理至 Azure Active Directory，請執行目錄同步處理嚮導和 Azure AD 連線，如[設定 Office 365 的目錄同步](../enterprise/set-up-directory-synchronization.md)處理中所述。

2. 目錄同步處理完成後，請確定您組織的 Windows 10 裝置已加入 Azure AD。 此步驟是在每個 Windows 10 裝置上個別執行。 如需詳細資訊，請參閱[設定 Microsoft 365 商務進階版使用者的 Windows 裝置](set-up-windows-devices.md)。

3. 在 Windows 10 裝置加入 Azure AD 後，每個使用者都必須重新開機其裝置，並以其 Microsoft 365 商務進階版認證登入。 所有裝置現在也可以存取內部部署資源。

不需要額外的步驟即可存取 Azure AD 已加入裝置的內部部署資源。 這種功能已內置於 Windows 10。

如果您計畫登入 AADJ 裝置以外的密碼方法（如 PIN/Bio-從 WHFB 認證登入），然後存取內部部署資源 (共用、印表機等等 ) ，請依照 [本文](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)所述進行。

如果您的組織未準備好在上述 Azure AD 聯結裝置設定中進行部署，請考慮設定 [混合式 AZURE Ad join 裝置](manage-windows-devices.md)設定。

### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>將 Windows 裝置加入 Azure AD 時的考慮

如果您 Azure 加入的 Windows 裝置先前已加入網域或在工作組中，請考慮下列限制：

- 當裝置 Azure AD 加入時，它會建立新的使用者，而不會參照現有的設定檔。 設定檔必須手動遷移。 使用者設定檔包含我的最愛、本機檔案、瀏覽器設定和 [開始] 功能表設定等資訊。 最佳方法是尋找協力廠商工具，將現有的檔案和設定對應至新的設定檔。

- 如果裝置使用的群組原則物件 (GPO) ，有些 Gpo 在 Intune 中可能沒有 (CSP) 的同等 [配置服務提供者](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) 。 執行 [MMAT 工具](https://www.microsoft.com/download/details.aspx?id=45520) ，尋找現有 gpo 的類似 csp。

- 使用者可能無法對依存于 Active Directory 驗證的應用程式進行驗證。 評估繼承應用程式，並考慮更新至使用新式驗證的應用程式（如有可能）。

- Active Directory 印表機探索無法運作。 您可以為所有使用者提供直接印表機路徑，或使用 [通用列印](/universal-print/)。

### <a name="related-articles"></a>相關文章

[Azure AD 連線的必要條件](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)
