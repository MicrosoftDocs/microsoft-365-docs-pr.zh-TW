---
title: 關閉使用者的強式密碼需求
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何使用 Windows PowerShell 為使用者設定強式密碼需求。
ms.openlocfilehash: 87ba9e0323c379d8c2589dbb82c38c531dd9d047
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286264"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>關閉使用者的強式密碼需求

本文說明如何為您的使用者關閉強式密碼需求。 Microsoft 365 商務組織中，預設會開啟強式密碼需求。 您的組織可能會有停用強式密碼的需求。 請遵循下列步驟關閉強式密碼需求。 您必須使用 PowerShell 來完成這些步驟。

## <a name="before-you-begin"></a>在您開始之前

本文適用于管理企業、學校或非盈利性密碼原則的人員。 若要完成這些步驟，您必須使用 Microsoft 365 系統管理員帳戶登入。 [什麼是系統管理員帳戶？](/microsoft-365/business-video/admin-center-overview) 您必須是 [全域系統管理員或密碼系統管理員](about-admin-roles.md) ，才可執行這些步驟。

您也必須使用 PowerShell 連接至 Microsoft 365。

## <a name="set-strong-passwords"></a>設定強式密碼

1. [與 PowerShell Microsoft 365 的連線](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

2. 使用 PowerShell，您可以使用下列命令，為所有使用者關閉強式密碼需求：

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> UserPrincipalName 必須是網際網路樣式的登入格式，其中使用者名稱後面接 @ 符號 ( @ ) 和功能變數名稱。 例如： user@contoso.com。

## <a name="related-content"></a>相關內容

[如何使用 PowerShell 連接至 Microsoft 365](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[PowerShell Get-msoluser 命令的詳細資訊](/powershell/azure/active-directory/install-adv2)

[密碼原則的詳細資訊](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)
