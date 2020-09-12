---
title: 使用 PowerShell 管理 Microsoft 365 群組
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: 在本文中，您將瞭解如何在 PowerShell 中執行 Microsoft 365 群組的常見管理工作。
ms.openlocfilehash: a02990b2890d9fdfd523209e1d912aafdaeac091
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547923"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>使用 PowerShell 管理 Microsoft 365 群組

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

本文提供執行 Microsoft PowerShell 中群組一般管理工作的步驟。 此外，它也會列出群組的 PowerShell Cmdlet。 如需管理 SharePoint 網站的相關資訊，請參閱 [Manage SharePoint Online sites using PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell)。

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>連結至您的 Microsoft 365 群組使用指導方針
<a name="BK_LinkToGuideLines"> </a>

當使用者 [在 Outlook 中建立或編輯群組](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)時，您可以向他們顯示組織使用指導方針的連結。 例如，如果您需要將特定的首碼或尾碼新增至群組名稱。

使用 Azure Active Directory (Azure AD) PowerShell 將使用者指向您組織的 Microsoft 365 群組使用原則。 請參閱 [Azure Active Directory Cmdlet 以設定群組設定](https://go.microsoft.com/fwlink/?LinkID=827484) ，並遵循在 **目錄層級的 [建立設定** ] 中的步驟，定義使用方式的超連結。 一旦您執行 AAD Cmdlet，當使用者在 Outlook 中建立或編輯群組時，會看到指導方針的連結。

![使用使用準則連結建立新的群組](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![按一下 [群組使用量指導方針]，以查看您的組織 Office 365 群組指導方針](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>允許使用者以 Microsoft 365 群組形式傳送
<a name="BK_LinkToGuideLines"> </a>

如果您想要讓 Microsoft 365 群組「傳送為」，請使用 [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) 和 [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) Cmdlet 來設定此設定。 一旦您啟用此設定，Microsoft 365 群組使用者便可使用 Outlook 或 Outlook 網頁版，以 Microsoft 365 群組的身分傳送和回復電子郵件。 使用者可以移至群組、建立新的電子郵件，然後將「傳送為」欄位變更為群組的電子郵件地址。

 ([您也可以在 Exchange 系統管理中心中執行此](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)動作。 ) 

使用下列腳本，並以 *\<GroupAlias\>* 您要更新之群組的別名取代，並 *\<UserAlias\>* 使用您要授與許可權的使用者別名進行取代。 [連接至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 以執行此腳本。

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

執行 Cmdlet 後，使用者可以透過將群組電子郵件地址新增至 [ **發件** 人] 欄位，移至要傳送為群組的 Outlook 或 outlook 網頁。

## <a name="create-classifications-for-office-groups-in-your-organization"></a>為您組織中的 Office 群組建立分類

您可以建立您組織中的使用者在建立 Microsoft 365 群組時所能設定的靈敏度標籤。 如果您想要分類群組，我們建議使用敏感度標籤，而不是「先前的群組分類」功能。 如需使用敏感度標籤的詳細資訊，請參閱 [使用敏感度標籤來保護 Microsoft 團隊、microsoft 365 群組和 SharePoint 網站中的內容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

> [!IMPORTANT]
> 如果您目前使用的是分類標籤，當啟用敏感度標籤之後，建立群組的使用者將無法再使用這些標籤。

您仍然可以使用「先前的群組分類」功能。 您可以建立組織中的使用者在建立 Office 365 群組時所能設定的分類。 例如，您可以允許使用者設定其所建立之群組上的「標準」、「機密」和「主要密碼」。 預設不會設定群組分類，您必須建立群組分類，使用者才能設定群組分類。 使用 Azure Active Directory PowerShell，將您的使用者指向您組織的 Office 365 群組使用指導方針。

請參閱 [Azure Active Directory Cmdlet 以設定群組設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) ，並遵循在 **目錄層級的 [建立設定** ] 中的步驟，定義 Office 365 群組的分類。

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

為了讓描述與每個分類產生關聯，您可以使用 settings 屬性  *ClassificationDescriptions* 來定義。

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

分類會符合 ClassificationList 中字串的位置。

範例：

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

在您執行上述 Azure Active Directory Cmdlet 以設定分類之後，如果您想要設定特定群組的分類，請執行 [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) Cmdlet。

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

或建立具有分類的新群組。

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

請參閱[使用 PowerShell 搭配 Exchange online 並聯機](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)[至 exchange online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) ，以取得更多有關使用 exchange online PowerShell 的詳細資料。

啟用這些設定之後，群組擁有者將可以從網頁和 Outlook 的 Outlook 的下拉式功能表中選擇分類，然後從 [ **編輯** 群組] 頁面進行儲存。

![選擇 Office 365 群組分類](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-office-365-groups-from-gal"></a>隱藏 GAL 中的 Office 365 群組
<a name="BKMK_CreateClassification"> </a>

您可以指定 Office 365 群組是否會顯示在全域通訊清單中 (GAL) 和組織中的其他清單。 例如，如果您有一個您不想要顯示在通訊清單中的法律部門群組，您可以停止該群組出現在 GAL 中。 執行設定整合群組指令程式，以從通訊清單中隱藏群組，如下所示：

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-office-365-group"></a>僅允許內部使用者傳送郵件至 Office 365 群組
<a name="BKMK_CreateClassification"> </a>

如果您不想讓其他組織的使用者將電子郵件傳送至 Office 365 群組，您可以變更該群組的設定。 它只允許內部使用者將電子郵件傳送至您的群組。 如果外部使用者嘗試傳送郵件給該群組，就會遭到拒絕。

執行 Set-UnifiedGroup Cmdlet 以更新此設定，如下所示：

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-the-office-365-groups"></a>將 MailTips 新增至 Office 365 群組
<a name="BKMK_CreateClassification"> </a>

當寄件者嘗試傳送電子郵件到 Office 365 群組時，會向他們顯示 MailTip。

執行設定整合群組 Cmdlet，將郵件提示新增至群組：

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

除了 MailTip 之外，您也可以設定 MailTipTranslations，以指定 MailTip 的其他語言。 假設您想要使用西班牙文翻譯，請執行下列命令：

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-display-name-of-the-office-365-group"></a>變更 Office 365 群組的顯示名稱

顯示名稱會指定 Office 365 群組的名稱。 您可以在 exchange 系統管理中心或 Microsoft 365 系統管理中心中看到此名稱。 您可以執行 Set-UnifiedGroup 命令，編輯群組的顯示名稱或指派顯示名稱至現有的 Office 365 群組：

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-office-365-groups-for-outlook-to-public-or-private"></a>將 Outlook 365 群組的預設設定變更為 [公用] 或 [私人]
<a name="BKMK_CreateClassification"> </a>

預設會建立 Outlook 中的 Office 365 群組為私人。 如果您的組織想要預設建立為 Public 的 Office 365 群組 (或回私人) ，請使用此 PowerShell Cmdlet 語法：

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

設為私人：

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

若要確認設定：

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

若要深入瞭解，請參閱 [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) 和 [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig)。

## <a name="office-365-groups-cmdlets"></a>Office 365 群組 Cmdlet

下列 Cmdlet 可搭配 Office 365 群組使用。

|**Cmdlet 名稱**|**描述**|
|:-----|:-----|
|[Set-unifiedgroup](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |使用此 Cmdlet 來查詢現有的 Office 365 群組，以及查看 group 物件的屬性  <br/> |
|[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |更新特定 Office 365 群組的屬性  <br/> |
|[新 Set-unifiedgroup](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |建立新的 Office 365 群組。 此 Cmdlet 提供一組最小的參數，用以設定擴充屬性的值使用 Set-UnifiedGroup 建立新群組之後  <br/> |
|[Remove-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |刪除現有的 Office 365 群組  <br/> |
|[UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |取得 Office 365 群組的成員資格及擁有者資訊  <br/> |
|[Add-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |將成百上千的使用者或新的擁有者新增至現有的 Office 365 群組  <br/> |
|[Remove-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |移除現有 Office 365 群組的擁有者和成員  <br/> |
|[UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |用來查看與帳戶相關聯之使用者相片的相關資訊。 使用者相片儲存在 Active Directory 中  <br/> |
|[UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |用於將使用者相片與帳戶產生關聯。 使用者相片儲存在 Active Directory 中  <br/> |
|[Remove-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |移除 Office 365 群組的相片  <br/> |

## <a name="related-topics"></a>相關主題

[將通訊群組清單升級至 Office 365 群組](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[管理可建立 Office 365 群組的人員](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[管理 Office 365 群組的來賓存取權](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[將靜態群組成員資格變更為動態的](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
