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
ms.openlocfilehash: c77898b58b58c6ae91492debd7ad66f395d80d52
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688596"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>在 Microsoft 365 中查看目錄同步處理狀態

如果您已整合內部部署 Active Directory 與 Azure AD，請同步處理內部部署環境與 Microsoft 365，您也可以檢查同步處理的狀態。
  
## <a name="view-directory-synchronization-status"></a>視目錄同步處理狀態

- 登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) ，然後選擇首頁上的 **DirSync 狀態** 。
- 或者，您可以移至 [**使用者**作用中使用者]， \> **Active users**然後在 [作用中**使用者**] 頁面上，選擇 [**更多** \> **目錄同步**處理]。 在 [ **目錄同步** 處理] 窗格中，選擇 [ **移至 DirSync 管理**]。

## <a name="information-on-the-manage-directory-synchronization-page"></a>「管理目錄同步處理」頁面上的資訊

下表列出您可以在頁面上取得相關資訊的功能。
  
如果您的目錄同步處理有問題，錯誤也會列在此頁面上。 如需您可能會遇到之不同錯誤的詳細資訊，請參閱 [識別 Microsoft 365 中的目錄同步處理錯誤](identify-directory-synchronization-errors.md)。
  
|**項目**|**功能**|
|:-----|:-----|
|**已驗證網域** | 您已驗證您的 Microsoft 365 租使用者中的網域數目。 |
|**未驗證的網域** | 您已新增但未驗證的網域。 |
|**已啟用目錄同步處理** |True 或 False。 指定是否已啟用目錄同步處理。 |
|**最新目錄同步處理** | 上次執行目錄同步處理的時間。 若上次同步處理超過三天以上，將會顯示警告及疑難排解工具的連結。 |
|**已啟用密碼同步處理** | True 或 False。 指定您的內部部署與 Microsoft 365 租使用者之間是否有密碼雜湊同步處理。 |
|**上次密碼同步處理** | 上次執行密碼雜湊同步處理的時間。 若上次同步處理超過三天以上，將會顯示警告及疑難排解工具的連結。 |
|**目錄同步處理用戶端版本** | 會包含下載連結，如果已發行新版本的 Azure AD Connect。 |
|**目錄同步處理服務帳戶** | 顯示 Microsoft 365 目錄同步服務帳戶的名稱。 |