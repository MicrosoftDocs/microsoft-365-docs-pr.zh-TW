---
title: 資訊屏障原則的屬性
description: 本文是 Azure Active Directory 使用者帳戶屬性的參考，您可以用來定義資訊屏障段。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee410bf455e770087da7999ad2019c17419a8e00
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919729"
---
# <a name="attributes-for-information-barrier-policies"></a>資訊屏障原則的屬性

Azure Active Directory 中的某些屬性可用於分割使用者。 在定義區段之後，就可以使用這些區段做為資訊屏障原則的篩選器。 例如，您可以使用 **部門** 在組織內依部門定義使用者的區段 (假設沒有任何人同時在兩個部門上運作) 。

本文說明如何使用具有資訊障礙的屬性，並提供可使用的屬性清單。 若要深入瞭解資訊障礙，請參閱下列資源：

- [資訊屏障](information-barriers.md)
- [在 Microsoft 小組中定義資訊障礙的原則](information-barriers-policies.md)
- [編輯 (或移除) 資訊屏障原則](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>如何使用資訊屏障原則中的屬性

本文所列的屬性可以用來定義或編輯使用者的區段。 在 [資訊屏障原則](information-barriers-policies.md)中，已定義的區段做為參數 (稱為 *UserGroupFilter* 值) 。

1. 決定要用來定義線段的屬性。  (請參閱本文中的 [參考](#reference) 一節。 ) 

2. 請確定使用者帳戶已填入值，以供您在步驟1中選取的屬性 (s) 。 查看使用者帳戶詳細資料，必要時，編輯使用者帳戶以包含屬性值。 

    - 若要編輯多個帳戶 (或使用 PowerShell 編輯單一帳戶) ，請參閱 [Configure user account properties With Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)。

    - 若要編輯單一帳戶，請參閱 [使用 Azure Active Directory 新增或更新使用者的設定檔資訊](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。

3. [使用 PowerShell 定義線段](information-barriers-policies.md#define-segments-using-powershell)，類似下列範例：

    |**範例**|**指令程式**|
    |:----------|:---------|
    | 使用部門屬性定義名為 Segment1 的區段 | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | 使用 MemberOf 屬性定義名為 SegmentA 的區段 (假設此屬性包含群組名稱，例如 "BlueGroup" )  | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | 使用 ExtensionAttribute1 定義名為 DayTraders 的區段 (假設此屬性包含職稱，例如 "DayTrader" )  | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > 當您定義區段時，請針對所有的區段使用相同的屬性。 例如，如果您使用 *部門* 定義部分區段，請使用 *部門* 定義所有的區段。 不要使用 *MemberOf* 來定義某些區段使用 *部門* 和其他。 請確定您的區段沒有交疊;每一位使用者都應該被指派為一個段落。

## <a name="reference"></a>參考

下表列出您可以與資訊障礙搭配使用的屬性。

|**Azure Active Directory 屬性名稱 <br/> (LDAP 顯示名稱)**|**Exchange 屬性名稱**|
|:---------------------------------------------------------------|:-------------------------|
| 顯 | 顯 |
| Company | Company |
| 部門 | 部門 |
| ExtensionAttribute1 | CustomAttribute1 |
| ExtensionAttribute2 | CustomAttribute2 |
| ExtensionAttribute3 | CustomAttribute3 |
| ExtensionAttribute4 | CustomAttribute4 |
| ExtensionAttribute5 | CustomAttribute5 |
| ExtensionAttribute6 | CustomAttribute6 |
| ExtensionAttribute7 | CustomAttribute7 |
| ExtensionAttribute8 | CustomAttribute8 |
| ExtensionAttribute9 | CustomAttribute9 |
| ExtensionAttribute10 | CustomAttribute10 |
| ExtensionAttribute11 | CustomAttribute11 |
| ExtensionAttribute12 | CustomAttribute12 |
| ExtensionAttribute13 | CustomAttribute13 |
| ExtensionAttribute14 | CustomAttribute14 |
| ExtensionAttribute15 | CustomAttribute15 |
| MSExchExtensionCustomAttribute1 | ExtensionCustomAttribute1 |
| MSExchExtensionCustomAttribute2 | ExtensionCustomAttribute2 |
| MSExchExtensionCustomAttribute3 | ExtensionCustomAttribute3 |
| MSExchExtensionCustomAttribute4 | ExtensionCustomAttribute4 |
| MSExchExtensionCustomAttribute5 | ExtensionCustomAttribute5 |
| MailNickname | 別名 |
| PhysicalDeliveryOfficeName | 辦公室 |
| PostalCode | PostalCode |
| ProxyAddresses | EmailAddresses |
| StreetAddress | StreetAddress |
| TargetAddress | ExternalEmailAddress |
| UsageLocation | UsageLocation |
| UserPrincipalName | UserPrincipalName |
| 郵件 | WindowsEmailAddress |
| 描述 | 描述 |
| MemberOf | MemberOfGroup |

## <a name="resources"></a>資源

- [在 Microsoft 小組中定義資訊障礙的原則](information-barriers-policies.md)
- [疑難排解資訊屏障](information-barriers-troubleshooting.md)
- [資訊屏障](information-barriers.md)