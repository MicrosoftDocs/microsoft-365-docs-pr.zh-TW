---
title: 選擇建立 Office 365 群組時要使用的網域
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: '了解如何選擇藉由設定電子郵件地址原則使用 PowerShell 建立 Office 365 群組時要使用的網域。 '
ms.openlocfilehash: 55fc99cd201e66166e7da164777cfba2f763609c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239235"
---
# <a name="choose-the-domain-to-use-when-creating-office-365-groups"></a>選擇建立 Office 365 群組時要使用的網域

 有些組織會使用不同的電子郵件網域來將業務區隔為不同部分。當您的使用者要建立 Office 365 群組時，您可以指定應使用哪一個網域。
  
如果您的組織需要使用者在非預設的網域中建立其群組之公認的網域，您的業務，您可以允許此行為設定電子郵件地址原則 (EAPs) 使用 PowerShell。
  
您可以執行的 PowerShell cmdlet 之前，請下載並安裝模組，將可讓您洽詢您的 Office 365 組織。 請參閱[Connect to Exchange Online 使用遠端 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881)。
  
## <a name="example-scenarios"></a>範例案例

例如，假設貴公司的主要網域是 Contoso.com。 但您的組織預設的公認的網域是 service.contoso.com。 這表示會在 service.contoso.com (例如，jimsteam@service.contoso.com) 中建立群組。
  
例如，假設您也必須設定組織中的子網域。 您想太建立這些網域中的群組：
  
- 學生的 students.contoso.com
    
- 適用於教師成員 faculty.contoso.com 的郵件
    
下列兩個案例將說明如何您會完成這項作業。
  
> [!NOTE]
> 當您有多個站 EAPs 時，會評估定義優先順序。 值是 1 表示最高的優先順序。 一旦 EAP 符合，沒有進一步的 EAP 會評估，並取得加上戳記，群組的地址是根據符合 EAP。 如果沒有 EAPs 符合指定的準則，則群組取得中組織的預設佈建 > 公認的網域。 請參閱[管理公認的網域在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428)的 how to： 新增公認的網域的詳細資訊。 
  
### <a name="scenario-1"></a>案例 1

下列範例會示範如何佈建 groups.contoso.com 網域中您組織中的所有 Office 365 群組。
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>案例 2

例如，假設您想要控制子網域的 Office 365 群組中的建立。 您想要：
  
- 學生 （有**部門**設**學生**的使用者） 建立 students.groups.contoso.com 網域中的群組。 請使用下列命令：
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- 教師成員所建立的群組 (使用者有**部門**設**教職人員或電子郵件地址包含 faculty.contoso.com 的郵件)**) faculty.groups.contoso.com 網域中。 請使用下列命令：
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- 所有其他網域中的使用者 groups.contoso.com。 請使用下列命令：
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>變更電子郵件地址原則

若要變更現有的 EAP 優先順序或電子郵件地址範本，請使用 Set-emailaddresspolicy cmdlet。
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

變更 EAP 具有已佈建的群組不會影響。
  
## <a name="delete-email-address-policies"></a>刪除電子郵件地址原則

若要刪除 EAP，使用 Remove-emailaddresspolicy cmdlet。
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

變更 EAP 具有已佈建的群組不會影響。
  
## <a name="hybrid-requirements"></a>混合需求

如果您的組織設定混合式案例，請參閱若要確保您的組織符合建立 Office 365 群組的需求[設定 Office 365 群組與內部部署 Exchange 混合式](https://go.microsoft.com/fwlink/p/?LinkId=785430)。 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>使用相關的其他資訊電子郵件地址原則群組：

有幾個更多的須知事項：
  
- 如何快速建立群組，取決於您組織中設定的 EAPs 數目。
    
- 系統管理員和使用者也可以修改網域在建立群組時。
    
- 使用者群組會決定使用已可以使用標準查詢 （使用者內容）。 請參閱[-RecipientFilter 參數的可篩選內容](https://go.microsoft.com/fwlink/p/?LinkId=785918)的支援的可篩選 pproperties。 
    
- 如果您未設定任何 EAPs 群組，然後預設的公認的網域選取群組建立。
    
- 如果您移除公認的網域，您應該先更新 EAPs，否則群組佈建將會受到影響。
    
- 上限為 100 的電子郵件地址原則可為組織設定。
    
## <a name="related-articles"></a>相關文章

[在系統管理中心建立 Office 365 群組](create-groups.md)
