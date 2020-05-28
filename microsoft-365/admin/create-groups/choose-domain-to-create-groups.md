---
title: 選擇建立 Microsoft 365 群組時要使用的網域
ms.reviewer: arvaradh
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: '透過設定電子郵件地址原則使用 PowerShell，瞭解如何選擇建立 Microsoft 365 群組時所使用的網域。 '
ms.openlocfilehash: 5569f42f15835be02a20166e64ce09a08b146dd7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44388206"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>選擇建立 Microsoft 365 群組時要使用的網域

 有些組織會使用不同的電子郵件網域來將業務區隔為不同部分。 您可以指定當使用者建立 Microsoft 365 群組時，應使用的網域。
  
如果您的組織需要使用者在公司預設的公認網域以外的其他網域中建立他們的群組，您可以使用 PowerShell 來設定電子郵件地址原則（EAPs），以允許做到這一點。
  
在您可以執行 PowerShell Cmdlet 之前，請下載並安裝可讓您與組織交談的模組。 [使用遠端 PowerShell 查看 [連線至 Exchange Online]](https://go.microsoft.com/fwlink/p/?LinkId=785881)。
  
## <a name="example-scenarios"></a>範例案例

假設您公司的主要網域是 Contoso.com。 不過，您組織的預設公認網域是 service.contoso.com。 這表示將會在 service.contoso.com 中建立群組（例如，jimsteam@service.contoso.com）。
  
假設您的組織中也有設定子域。 您也想要在這些網域中建立群組：
  
- 學生 students.contoso.com
    
- 教職員 faculty.contoso.com
    
下列兩個案例會說明如何完成此作業。
  
> [!NOTE]
> 當您有多個 EAPs 時，會以優先順序的順序評估。 值為1表示最高優先順序。 EAP 符合後，就不會再評估任何 EAP，而且在群組上加蓋標記的位址，都是根據相符的 EAP。 > 如果沒有 EAPs 符合指定的準則，群組便會在組織的預設公認網域中布建。 請參閱[管理 Exchange Online 中公認的網域](https://go.microsoft.com/fwlink/p/?LinkId=785428)，以取得如何新增公認的網域的詳細資料。 
  
### <a name="scenario-1"></a>案例 1

下列範例顯示如何在 groups.contoso.com 網域中布建組織中的所有 Microsoft 365 群組。
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>案例 2

假設您想要控制哪些子域中建立的 Microsoft 365 群組。 你想要：
  
- 在 students.groups.contoso.com 網域中，由學生（已將**部門**設定為**學生**的使用者）所建立的群組。 請使用下列命令：
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Faculty.groups.contoso.com 網域中由教職員 **（已設定**為**教職員或電子郵件地址**的使用者）所建立的群組。 請使用下列命令：
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Groups.contoso.com 網域中的所有其他使用者。 請使用下列命令：
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>變更電子郵件地址原則

若要變更現有 EAP 的優先順序或電子郵件地址範本，請使用 Set-EmailAddressPolicy Cmdlet。
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

變更 EAP 不會影響已布建的群組。
  
## <a name="delete-email-address-policies"></a>刪除電子郵件地址原則

若要刪除 EAP，請使用 Remove-EmailAddressPolicy Cmdlet。
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

變更 EAP 不會影響已布建的群組。
  
## <a name="hybrid-requirements"></a>混合需求

如果您的組織是在混合案例中設定，請參閱[使用內部部署 Exchange 混合式設定 Microsoft 365 群組](https://go.microsoft.com/fwlink/p/?LinkId=785430)，以確保您的組織符合建立 Microsoft 365 群組的需求。 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>使用電子郵件地址原則群組的其他資訊：

還有其他一些事項需要注意：
  
- 建立的速度群組取決於您組織中設定的 EAPs 數目。
    
- 管理員和使用者也可以在建立群組時修改網域。
    
- 使用者群組是使用已有的標準查詢（使用者屬性）決定。 請查看[-RecipientFilter 參數](https://go.microsoft.com/fwlink/p/?LinkId=785918)的可篩選內容，以取得支援的可篩選屬性。 
    
- 如果您未設定群組的任何 EAPs，則會選取預設的公認網域以建立群組。
    
- 如果您移除公認的網域，您應該先更新 EAPs，否則將會影響群組布建。
    
- 您可以為組織設定100電子郵件地址原則的上限。
    
## <a name="related-articles"></a>相關文章

[在系統管理中心建立 Microsoft 365 群組](create-groups.md)
