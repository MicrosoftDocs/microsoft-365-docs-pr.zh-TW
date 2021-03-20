---
title: 新增或移除地理位置系統管理員
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: 需要為每個地理位置設定個別的系統管理員嗎？ 了解如何在 Microsoft 365 多地理位置中新增或移除地理位置系統管理員。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 32fe5e934e6a3d6f18c802c3c427974e67c1b454
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905597"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a>在 Microsoft 365 多地理位置中新增或移除地理位置系統管理員

您可以為租用戶中的每個地理位置設定個別的系統管理員。 這些系統管理員將能存取專為其地理位置設定的 Sharepoint 和 OneDrive 設定。

某些服務 - 例如詞彙儲存庫- 可從中心位置進行管理並會複製到衛星位置。 中央位置的地理位置系統管理員可以存取這些服務，而衛星位置的地理位置系統管理員則無法存取。

全域系統管理員和 SharePoint Online 系統管理員可以繼續存取中心位置和所有衛星位置的設定。

## <a name="configuring-geo-administrators"></a>設定地理位置系統管理員

設定地理位置系統管理員需要 SharePoint Online PowerShell 模組。

使用 [Connect-SPOService](/powershell/module/sharepoint-online/Connect-SPOService) 連線到您想新增地理位置系統管理員之地理位置的系統管理中心。(例如，Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)

若要檢視某位置的現有地理位置系統管理員，請執行 `Get-SPOGeoAdministrator`

### <a name="adding-a-user-as-a-geo-admin"></a>將使用者新增為地理位置系統管理員

若要將使用者新增為地理位置系統管理員，請執行 `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`

若要在某位置將使用者的地理位置系統管理員身份移除，請執行 `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`

### <a name="adding-a-group-as-a-geo-admin"></a>將群組新增為地理位置系統管理員

您可以新增安全性群組或擁有郵件功能的安全性群組作為地理位置系統管理員。(不支援通訊群組與 Microsoft 365 群組。)

若要新增群組為地理位置系統管理員，請執行 `Add-SPOGeoAdministrator -GroupAlias <alias>`

若要移除群組的地理位置系統管理員身份，請執行 `Remove-SPOGeoAdministrator -GroupAlias <alias>`

請注意，並非所有安全性群組都有群組別名。 如果您要新增的安全性群組並沒有別名，請執行 [Get-MsolGroup](/powershell/module/msonline/get-msolgroup) 擷取群組清單、找出安全性群組 ObjectID，然後再執行：

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

若要使用 ObjectID 移除群組，請執行 `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`

## <a name="related-topics"></a>相關主題

[Add-SPOGeoAdministrator](/powershell/module/sharepoint-online/add-spogeoadministrator)

[Add-SPOGeoAdministrator](/powershell/module/sharepoint-online/get-spogeoadministrator)

[Remove-SPOGeoAdministrator](/powershell/module/sharepoint-online/remove-spogeoadministrator)

[為安全性群組設定別名 (MailNickName)](/powershell/module/azuread/set-azureadgroup)