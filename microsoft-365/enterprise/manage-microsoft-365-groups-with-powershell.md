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
ms.openlocfilehash: a9c25fc4fbc2fb1f39c6e7b9e7e5de0e778fd513
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688384"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="d9756-103">使用 PowerShell 管理 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="d9756-103">Manage Microsoft 365 Groups with PowerShell</span></span>
 
<span data-ttu-id="d9756-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="d9756-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d9756-105">本文提供執行 Microsoft PowerShell 中群組一般管理工作的步驟。</span><span class="sxs-lookup"><span data-stu-id="d9756-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="d9756-106">此外，它也會列出群組的 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9756-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="d9756-107">如需管理 SharePoint 網站的相關資訊，請參閱 [Manage SharePoint Online sites using PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d9756-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="d9756-108">連結至您的 Microsoft 365 群組使用指導方針</span><span class="sxs-lookup"><span data-stu-id="d9756-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="d9756-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="d9756-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="d9756-110">當使用者 [在 Outlook 中建立或編輯群組](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)時，您可以向他們顯示組織使用指導方針的連結。</span><span class="sxs-lookup"><span data-stu-id="d9756-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="d9756-111">例如，如果您需要將特定的首碼或尾碼新增至群組名稱。</span><span class="sxs-lookup"><span data-stu-id="d9756-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>
  
<span data-ttu-id="d9756-112">使用 Azure Active Directory (Azure AD) PowerShell 將使用者指向您組織的 Microsoft 365 群組使用原則。</span><span class="sxs-lookup"><span data-stu-id="d9756-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="d9756-113">請參閱 [Azure Active Directory Cmdlet 以設定群組設定](https://go.microsoft.com/fwlink/?LinkID=827484) ，並遵循在 **目錄層級的 [建立設定** ] 中的步驟，定義使用方式的超連結。</span><span class="sxs-lookup"><span data-stu-id="d9756-113">Check out [Azure Active Directory cmdlets for configuring group settings](https://go.microsoft.com/fwlink/?LinkID=827484) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="d9756-114">一旦您執行 AAD Cmdlet，當使用者在 Outlook 中建立或編輯群組時，會看到指導方針的連結。</span><span class="sxs-lookup"><span data-stu-id="d9756-114">Once you run the AAD cmdlet, user's will see the link to your guidelines when they create or edit a group in Outlook.</span></span> 
  
![使用使用準則連結建立新的群組](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)
  
![按一下 [群組使用量指導方針]，以查看您的組織 Office 365 群組指導方針](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)
  
## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="d9756-117">允許使用者以 Microsoft 365 群組形式傳送</span><span class="sxs-lookup"><span data-stu-id="d9756-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="d9756-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="d9756-118"><a name="BK_LinkToGuideLines"> </a></span></span>
  
<span data-ttu-id="d9756-119">如果您想要讓 Microsoft 365 群組「傳送為」，請使用 [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/Add-RecipientPermission) 和 [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/Get-Recipient) Cmdlet 來設定此設定。</span><span class="sxs-lookup"><span data-stu-id="d9756-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/Add-RecipientPermission) and the [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/Get-Recipient) cmdlets to configure this.</span></span> <span data-ttu-id="d9756-120">一旦您啟用此設定，Microsoft 365 群組使用者便可使用 Outlook 或 Outlook 網頁版，以 Microsoft 365 群組的身分傳送和回復電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d9756-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="d9756-121">使用者可以移至群組、建立新的電子郵件，然後將「傳送為」欄位變更為群組的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d9756-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span> 

<span data-ttu-id="d9756-122"> ([您也可以在 Exchange 系統管理中心中執行此](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)動作。 ) </span><span class="sxs-lookup"><span data-stu-id="d9756-122">([You can also do this in the Exchange Admin Center](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>
  
<span data-ttu-id="d9756-123">使用下列腳本，並以 *\<GroupAlias\>* 您要更新之群組的別名取代，並 *\<UserAlias\>* 使用您要授與許可權的使用者別名進行取代。</span><span class="sxs-lookup"><span data-stu-id="d9756-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="d9756-124">[連接至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 以執行此腳本。</span><span class="sxs-lookup"><span data-stu-id="d9756-124">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"

$userAlias = "<UserAlias>"


$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="d9756-125">執行 Cmdlet 後，使用者可以透過將群組電子郵件地址新增至 [ **發件** 人] 欄位，移至要傳送為群組的 Outlook 或 outlook 網頁。</span><span class="sxs-lookup"><span data-stu-id="d9756-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span> 

## <a name="create-classifications-for-office-groups-in-your-organization"></a><span data-ttu-id="d9756-126">為您組織中的 Office 群組建立分類</span><span class="sxs-lookup"><span data-stu-id="d9756-126">Create classifications for Office groups in your organization</span></span>

<span data-ttu-id="d9756-127">您可以建立您組織中的使用者在建立 Microsoft 365 群組時所能設定的靈敏度標籤。</span><span class="sxs-lookup"><span data-stu-id="d9756-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="d9756-128">如果您想要分類群組，我們建議使用敏感度標籤，而不是「先前的群組分類」功能。</span><span class="sxs-lookup"><span data-stu-id="d9756-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="d9756-129">如需使用敏感度標籤的詳細資訊，請參閱 [使用敏感度標籤來保護 Microsoft 團隊、microsoft 365 群組和 SharePoint 網站中的內容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="d9756-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9756-130">如果您目前使用的是分類標籤，當啟用敏感度標籤之後，建立群組的使用者將無法再使用這些標籤。</span><span class="sxs-lookup"><span data-stu-id="d9756-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="d9756-131">您仍然可以使用「先前的群組分類」功能。</span><span class="sxs-lookup"><span data-stu-id="d9756-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="d9756-132">您可以建立組織中的使用者在建立 Office 365 群組時所能設定的分類。</span><span class="sxs-lookup"><span data-stu-id="d9756-132">You can create classifications that the users in your organization can set when they create an Office 365 group.</span></span> <span data-ttu-id="d9756-133">例如，您可以允許使用者設定其所建立之群組上的「標準」、「機密」和「主要密碼」。</span><span class="sxs-lookup"><span data-stu-id="d9756-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="d9756-134">預設不會設定群組分類，您必須建立群組分類，使用者才能設定群組分類。</span><span class="sxs-lookup"><span data-stu-id="d9756-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="d9756-135">使用 Azure Active Directory PowerShell，將您的使用者指向您組織的 Office 365 群組使用指導方針。</span><span class="sxs-lookup"><span data-stu-id="d9756-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Office 365 groups.</span></span>
  
<span data-ttu-id="d9756-136">請參閱 [Azure Active Directory Cmdlet 以設定群組設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) ，並遵循在 **目錄層級的 [建立設定** ] 中的步驟，定義 Office 365 群組的分類。</span><span class="sxs-lookup"><span data-stu-id="d9756-136">Check out [Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Office 365 groups.</span></span> 
  
```
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="d9756-137">為了讓描述與每個分類產生關聯，您可以使用 settings 屬性  *ClassificationDescriptions* 來定義。</span><span class="sxs-lookup"><span data-stu-id="d9756-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>
  
```
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="d9756-138">分類會符合 ClassificationList 中字串的位置。</span><span class="sxs-lookup"><span data-stu-id="d9756-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="d9756-139">範例：</span><span class="sxs-lookup"><span data-stu-id="d9756-139">Example:</span></span>
  
```
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="d9756-140">在您執行上述 Azure Active Directory Cmdlet 以設定分類之後，如果您想要設定特定群組的分類，請執行 [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9756-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span> 
  
```
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact> 
```

<span data-ttu-id="d9756-141">或建立具有分類的新群組。</span><span class="sxs-lookup"><span data-stu-id="d9756-141">Or create a new group with a classification.</span></span>
  
```
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public> 
```

<span data-ttu-id="d9756-142">請參閱[使用 PowerShell 搭配 Exchange online 並聯機](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)[至 exchange online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) ，以取得更多有關使用 exchange online PowerShell 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d9756-142">Check out [Using PowerShell with Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell) and [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span> 
  
<span data-ttu-id="d9756-143">啟用這些設定之後，群組擁有者將可以從網頁和 Outlook 的 Outlook 的下拉式功能表中選擇分類，然後從 [ **編輯** 群組] 頁面進行儲存。</span><span class="sxs-lookup"><span data-stu-id="d9756-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span> 
  
![選擇 Office 365 群組分類](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)
  
## <a name="hide-office-365-groups-from-gal"></a><span data-ttu-id="d9756-145">隱藏 GAL 中的 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="d9756-145">Hide Office 365 Groups from GAL</span></span>
<span data-ttu-id="d9756-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="d9756-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="d9756-147">您可以指定 Office 365 群組是否會顯示在全域通訊清單中 (GAL) 和組織中的其他清單。</span><span class="sxs-lookup"><span data-stu-id="d9756-147">You can specify whether an Office 365 group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="d9756-148">例如，如果您有一個您不想要顯示在通訊清單中的法律部門群組，您可以停止該群組出現在 GAL 中。</span><span class="sxs-lookup"><span data-stu-id="d9756-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in GAL.</span></span> <span data-ttu-id="d9756-149">執行設定整合群組指令程式，以從通訊清單中隱藏群組，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d9756-149">Run the Set-Unified Group cmdlet to hide the group from address list like this:</span></span>
  
```
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-office-365-group"></a><span data-ttu-id="d9756-150">僅允許內部使用者傳送郵件至 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="d9756-150">Allow only internal users to send message to Office 365 group</span></span>
<span data-ttu-id="d9756-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="d9756-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="d9756-152">如果您不想讓其他組織的使用者將電子郵件傳送至 Office 365 群組，您可以變更該群組的設定。</span><span class="sxs-lookup"><span data-stu-id="d9756-152">If you don't want users from other organization to send email to an Office 365 group, you can change the settings for that group.</span></span> <span data-ttu-id="d9756-153">它只允許內部使用者將電子郵件傳送至您的群組。</span><span class="sxs-lookup"><span data-stu-id="d9756-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="d9756-154">如果外部使用者嘗試傳送郵件給該群組，就會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="d9756-154">If external user try to send message to that group they will be rejected.</span></span>
  
<span data-ttu-id="d9756-155">執行 Set-UnifiedGroup Cmdlet 以更新此設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d9756-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-the-office-365-groups"></a><span data-ttu-id="d9756-156">將 MailTips 新增至 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="d9756-156">Add MailTips to the Office 365 Groups</span></span>
<span data-ttu-id="d9756-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="d9756-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="d9756-158">當寄件者嘗試傳送電子郵件到 Office 365 群組時，會向他們顯示 MailTip。</span><span class="sxs-lookup"><span data-stu-id="d9756-158">Whenever a sender tries to send an email to an Office 365 group, a MailTip can be shown to them.</span></span>
  
<span data-ttu-id="d9756-159">執行設定整合群組 Cmdlet，將郵件提示新增至群組：</span><span class="sxs-lookup"><span data-stu-id="d9756-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="d9756-160">除了 MailTip 之外，您也可以設定 MailTipTranslations，以指定 MailTip 的其他語言。</span><span class="sxs-lookup"><span data-stu-id="d9756-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="d9756-161">假設您想要使用西班牙文翻譯，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d9756-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>
  
```
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-display-name-of-the-office-365-group"></a><span data-ttu-id="d9756-162">變更 Office 365 群組的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="d9756-162">Change Display name of the Office 365 group</span></span>

<span data-ttu-id="d9756-163">顯示名稱會指定 Office 365 群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="d9756-163">Display name specifies the name of the Office 365 group.</span></span> <span data-ttu-id="d9756-164">您可以在 exchange 系統管理中心或 Microsoft 365 系統管理中心中看到此名稱。</span><span class="sxs-lookup"><span data-stu-id="d9756-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="d9756-165">您可以執行 Set-UnifiedGroup 命令，編輯群組的顯示名稱或指派顯示名稱至現有的 Office 365 群組：</span><span class="sxs-lookup"><span data-stu-id="d9756-165">You can edit the display name of the group or assign a display name to an existing Office 365 group by running the Set-UnifiedGroup command:</span></span>

```
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-office-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="d9756-166">將 Outlook 365 群組的預設設定變更為 [公用] 或 [私人]</span><span class="sxs-lookup"><span data-stu-id="d9756-166">Change the default setting of Office 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="d9756-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="d9756-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="d9756-168">預設會建立 Outlook 中的 Office 365 群組為私人。</span><span class="sxs-lookup"><span data-stu-id="d9756-168">Office 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="d9756-169">如果您的組織想要預設建立為 Public 的 Office 365 群組 (或回私人) ，請使用此 PowerShell Cmdlet 語法：</span><span class="sxs-lookup"><span data-stu-id="d9756-169">If your organization wants Office 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>
  
 `Set-OrganizationConfig -DefaultGroupAccessType Public`
  
<span data-ttu-id="d9756-170">設為私人：</span><span class="sxs-lookup"><span data-stu-id="d9756-170">To set to Private:</span></span>
  
 `Set-OrganizationConfig -DefaultGroupAccessType Private`
  
<span data-ttu-id="d9756-171">若要確認設定：</span><span class="sxs-lookup"><span data-stu-id="d9756-171">To verify the setting:</span></span> 
  
 `Get-OrganizationConfig | ft DefaultGroupAccessType`
  
<span data-ttu-id="d9756-172">若要深入瞭解，請參閱 [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) 和 [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/Get-OrganizationConfig)。</span><span class="sxs-lookup"><span data-stu-id="d9756-172">To learn more, see [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/Get-OrganizationConfig).</span></span>
  
## <a name="office-365-groups-cmdlets"></a><span data-ttu-id="d9756-173">Office 365 群組 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d9756-173">Office 365 Groups cmdlets</span></span>

<span data-ttu-id="d9756-174">下列 Cmdlet 可搭配 Office 365 群組使用。</span><span class="sxs-lookup"><span data-stu-id="d9756-174">The following cmdlets can be used with Office 365 Groups.</span></span>
  
|<span data-ttu-id="d9756-175">**Cmdlet 名稱**</span><span class="sxs-lookup"><span data-stu-id="d9756-175">**Cmdlet name**</span></span>|<span data-ttu-id="d9756-176">**描述**</span><span class="sxs-lookup"><span data-stu-id="d9756-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d9756-177">Set-unifiedgroup</span><span class="sxs-lookup"><span data-stu-id="d9756-177">Get-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |<span data-ttu-id="d9756-178">使用此 Cmdlet 來查詢現有的 Office 365 群組，以及查看 group 物件的屬性</span><span class="sxs-lookup"><span data-stu-id="d9756-178">Use this cmdlet to look up existing Office 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="d9756-179">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="d9756-179">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |<span data-ttu-id="d9756-180">更新特定 Office 365 群組的屬性</span><span class="sxs-lookup"><span data-stu-id="d9756-180">Update the properties of a specific Office 365 Group</span></span>  <br/> |
|[<span data-ttu-id="d9756-181">新 Set-unifiedgroup</span><span class="sxs-lookup"><span data-stu-id="d9756-181">New-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |<span data-ttu-id="d9756-182">建立新的 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="d9756-182">Create a new Office 365 group.</span></span> <span data-ttu-id="d9756-183">此 Cmdlet 提供一組最小的參數，用以設定擴充屬性的值使用 Set-UnifiedGroup 建立新群組之後</span><span class="sxs-lookup"><span data-stu-id="d9756-183">This cmdlet provides a minimal set of parameters, for setting values for extended properties use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="d9756-184">Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="d9756-184">Remove-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |<span data-ttu-id="d9756-185">刪除現有的 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="d9756-185">Delete an existing Office 365 Group</span></span>  <br/> |
|[<span data-ttu-id="d9756-186">UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="d9756-186">Get-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |<span data-ttu-id="d9756-187">取得 Office 365 群組的成員資格及擁有者資訊</span><span class="sxs-lookup"><span data-stu-id="d9756-187">Retrieve membership and owner information for an Office 365 Group</span></span>  <br/> |
|[<span data-ttu-id="d9756-188">Add-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="d9756-188">Add-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |<span data-ttu-id="d9756-189">將成百上千的使用者或新的擁有者新增至現有的 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="d9756-189">Add hundred or thousands of users, or new owners, to an existing Office 365 Group</span></span>  <br/> |
|[<span data-ttu-id="d9756-190">Remove-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="d9756-190">Remove-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |<span data-ttu-id="d9756-191">移除現有 Office 365 群組的擁有者和成員</span><span class="sxs-lookup"><span data-stu-id="d9756-191">Remove owners and members from an existing Office 365 Group</span></span>  <br/> |
|[<span data-ttu-id="d9756-192">UserPhoto</span><span class="sxs-lookup"><span data-stu-id="d9756-192">Get-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |<span data-ttu-id="d9756-193">用來查看與帳戶相關聯之使用者相片的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d9756-193">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="d9756-194">使用者相片儲存在 Active Directory 中</span><span class="sxs-lookup"><span data-stu-id="d9756-194">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="d9756-195">UserPhoto</span><span class="sxs-lookup"><span data-stu-id="d9756-195">Set-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |<span data-ttu-id="d9756-196">用於將使用者相片與帳戶產生關聯。</span><span class="sxs-lookup"><span data-stu-id="d9756-196">Used to associate a user photo with an account.</span></span> <span data-ttu-id="d9756-197">使用者相片儲存在 Active Directory 中</span><span class="sxs-lookup"><span data-stu-id="d9756-197">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="d9756-198">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="d9756-198">Remove-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |<span data-ttu-id="d9756-199">移除 Office 365 群組的相片</span><span class="sxs-lookup"><span data-stu-id="d9756-199">Remove the photo for an Office 365 group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="d9756-200">相關主題</span><span class="sxs-lookup"><span data-stu-id="d9756-200">Related topics</span></span>

[<span data-ttu-id="d9756-201">將通訊群組清單升級至 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="d9756-201">Upgrade distribution lists to Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="d9756-202">管理可建立 Office 365 群組的人員</span><span class="sxs-lookup"><span data-stu-id="d9756-202">Manage who can create Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[<span data-ttu-id="d9756-203">管理 Office 365 群組的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="d9756-203">Manage guest access to Office 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="d9756-204">將靜態群組成員資格變更為動態的</span><span class="sxs-lookup"><span data-stu-id="d9756-204">Change static group membership to dynamic in</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
