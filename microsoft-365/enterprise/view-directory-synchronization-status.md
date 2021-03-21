---
title: 在 Microsoft 365 中查看目錄同步處理狀態
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: 在本文中，您可以瞭解如何檢查 Office 365 中目錄同步處理的狀態。
ms.openlocfilehash: cbaae8bbd31f6124c2b0f4984b9a625ffbde538f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924657"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>在 Microsoft 365 中查看目錄同步處理狀態

如果您已整合內部部署 Active Directory 網域服務 (AD DS) 與 Azure Active Directory (Azure AD) ，只需要同步處理內部部署環境與 Microsoft 365，您也可以檢查同步處理的狀態。
  
## <a name="view-directory-synchronization-status"></a>檢視目錄同步處理狀態

- 登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) ，然後選擇首頁上的 **DirSync 狀態** 。
- 或者，您可以移至 [**使用者** 作用中使用者]， \> 然後在 [作用中 **使用者**] 頁面上，選擇 [**更多** \> **目錄同步** 處理]。 在 [ **目錄同步** 處理] 窗格中，選擇 [ **移至 DirSync 管理**]。

## <a name="information-on-the-manage-directory-synchronization-page"></a>「管理目錄同步處理」頁面上的資訊

下表列出您可以在頁面上取得相關資訊的功能。
  
如果您的目錄同步處理有問題，錯誤也會列在此頁面上。 如需您可能會遇到之不同錯誤的詳細資訊，請參閱 [識別 Microsoft 365 中的目錄同步處理錯誤](identify-directory-synchronization-errors.md)。
  
|項目|功能|
|:-----|:-----|
|**已驗證網域** | 您已驗證您的 Microsoft 365 租使用者中的網域數目。 |
|**未驗證的網域** | 您已新增但未驗證的網域。 |
|**已啟用目錄同步處理** |TRUE 或 FALSE。 指定是否已啟用目錄同步處理。 |
|**最新目錄同步處理** | 上次執行目錄同步處理的時間。 若上次同步處理超過三天以上，將會顯示警告及疑難排解工具的連結。 |
|**已啟用密碼同步處理** | TRUE 或 FALSE。 指定您的內部部署與 Microsoft 365 租使用者之間是否有密碼雜湊同步處理。 |
|**上次密碼同步處理** | 上次執行密碼雜湊同步處理的時間。 若上次同步處理超過三天以上，將會顯示警告及疑難排解工具的連結。 |
|**目錄同步處理用戶端版本** | 會包含下載連結，如果已發行新版本的 Azure AD Connect。 |
|**目錄同步處理服務帳戶** | 顯示 Microsoft 365 目錄同步服務帳戶的名稱。 |
|||

## <a name="monitor-synchronization-health"></a>監控同步處理健康情況

在這一節中，您會在每個內部部署 AD DS 網域控制站上安裝 Azure AD Connect Health 代理程式，以監控您的身分識別基礎結構，以及由 Azure AD Connect 提供的同步處理服務。 監控資訊會在 Azure AD Connect Health 入口網站提供，您可以在其中檢視警訊、效能監控、使用量分析及其他資訊。

如何使用 Azure AD Connect Health 的關鍵設計決策取決於您如何使用 Azure AD Connect：

- 如果您使用的是 **受管理的驗證** 選項，請先從 [使用 Azure AD Connect Health 搭配同步處理](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)開始，以了解並設定 Azure AD Connect Health。
- 如果您使用 **同盟驗證** 搭配 Active Directory 同盟服務 (AD FS) 來同步處理帳戶及群組名稱，請先從 [使用 Azure AD Connect Health 搭配 AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) 開始，以了解並設定 Azure AD Connect Health。

完成後，您將會有：

- 已在內部部署身分識別提供者伺服器上安裝 Azure AD Connect Health 代理程式。
- Azure AD Connect Health 入口網站會顯示您內部部署基礎結構和同步處理活動的目前狀態以及 Microsoft 365 訂閱的 Azure AD 租用戶。