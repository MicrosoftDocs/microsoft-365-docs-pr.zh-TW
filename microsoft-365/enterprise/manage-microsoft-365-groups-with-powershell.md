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
ms.openlocfilehash: 22bf4d1f3187746483d8d904378e675562a62142
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730555"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="be302-103">使用 PowerShell 管理 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="be302-103">Manage Microsoft 365 Groups with PowerShell</span></span>

<span data-ttu-id="be302-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="be302-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="be302-105">本文提供執行 Microsoft PowerShell 中群組一般管理工作的步驟。</span><span class="sxs-lookup"><span data-stu-id="be302-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="be302-106">此外，它也會列出群組的 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="be302-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="be302-107">如需管理 SharePoint 網站的相關資訊，請參閱[Manage SharePoint Online sites using PowerShell](/sharepoint/manage-team-and-communication-sites-in-powershell)。</span><span class="sxs-lookup"><span data-stu-id="be302-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="be302-108">連結至您的 Microsoft 365 群組使用指導方針</span><span class="sxs-lookup"><span data-stu-id="be302-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="be302-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="be302-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="be302-110">當使用者[在 Outlook 中建立或編輯群組](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)時，您可以向他們顯示組織使用指導方針的連結。</span><span class="sxs-lookup"><span data-stu-id="be302-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="be302-111">例如，如果您需要將特定的首碼或尾碼新增至群組名稱。</span><span class="sxs-lookup"><span data-stu-id="be302-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>

<span data-ttu-id="be302-112">使用 Azure Active Directory (Azure AD) PowerShell，將您的使用者指向組織的 Microsoft 365 群組使用原則。</span><span class="sxs-lookup"><span data-stu-id="be302-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="be302-113">請參閱 [Azure Active Directory Cmdlet 以設定群組設定](/azure/active-directory/enterprise-users/groups-settings-cmdlets)，並遵循在 **目錄層級的 [建立設定**] 中的步驟，定義使用方式的超連結。</span><span class="sxs-lookup"><span data-stu-id="be302-113">Check out [Azure Active Directory cmdlets for configuring group settings](/azure/active-directory/enterprise-users/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="be302-114">一旦您執行 AAD Cmdlet，當使用者在 Outlook 中建立或編輯群組時，會看到指導方針的連結。</span><span class="sxs-lookup"><span data-stu-id="be302-114">Once you run the AAD cmdlet, users will see the link to your guidelines when they create or edit a group in Outlook.</span></span>

![使用使用準則連結建立新的群組](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![按一下 [群組使用量指導方針]，以查看您的組織 Office 365 群組指導方針](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="be302-117">允許使用者以 Microsoft 365 群組形式傳送</span><span class="sxs-lookup"><span data-stu-id="be302-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="be302-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="be302-118"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="be302-119">如果您想要讓您的 Microsoft 365 群組「傳送為」，請使用[Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission)和[Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) Cmdlet 來設定此設定。</span><span class="sxs-lookup"><span data-stu-id="be302-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) and [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) cmdlets to configure this.</span></span> <span data-ttu-id="be302-120">一旦您啟用此設定，Microsoft 365 群組使用者便可使用 Outlook 或 Outlook 網頁，以傳送電子郵件，並回復為 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="be302-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="be302-121">使用者可以移至群組、建立新的電子郵件，然後將「傳送為」欄位變更為群組的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="be302-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span>

<span data-ttu-id="be302-122"> ([您也可以在 Exchange 系統管理中心執行此](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)動作。 ) </span><span class="sxs-lookup"><span data-stu-id="be302-122">([You can also do this in the Exchange Admin Center](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>

<span data-ttu-id="be302-123">使用下列腳本，並以 *\<GroupAlias\>* 您要更新之群組的別名取代，並 *\<UserAlias\>* 使用您要授與許可權的使用者別名進行取代。</span><span class="sxs-lookup"><span data-stu-id="be302-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="be302-124">[連線 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)執行這個腳本。</span><span class="sxs-lookup"><span data-stu-id="be302-124">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="be302-125">執行 Cmdlet 後，使用者可以透過將群組電子郵件地址新增至 [**發件** 人] 欄位，移至要傳送為群組的網頁 Outlook 或 Outlook。</span><span class="sxs-lookup"><span data-stu-id="be302-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span>

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a><span data-ttu-id="be302-126">建立組織中 Microsoft 365 群組的分類</span><span class="sxs-lookup"><span data-stu-id="be302-126">Create classifications for Microsoft 365 Groups in your organization</span></span>

<span data-ttu-id="be302-127">您可以建立您組織中的使用者在建立 Microsoft 365 群組時所能設定的靈敏度標籤。</span><span class="sxs-lookup"><span data-stu-id="be302-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="be302-128">如果您想要分類群組，我們建議使用敏感度標籤，而不是「先前的群組分類」功能。</span><span class="sxs-lookup"><span data-stu-id="be302-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="be302-129">如需使用敏感度標籤的詳細資訊，請參閱[使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容](../compliance/sensitivity-labels-teams-groups-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="be302-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be302-130">如果您目前使用的是分類標籤，當啟用敏感度標籤之後，建立群組的使用者將無法再使用這些標籤。</span><span class="sxs-lookup"><span data-stu-id="be302-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="be302-131">您仍然可以使用「先前的群組分類」功能。</span><span class="sxs-lookup"><span data-stu-id="be302-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="be302-132">您可以建立組織中的使用者在建立 Microsoft 365 群組時所能設定的分類。</span><span class="sxs-lookup"><span data-stu-id="be302-132">You can create classifications that the users in your organization can set when they create an Microsoft 365 Group.</span></span> <span data-ttu-id="be302-133">例如，您可以允許使用者設定其所建立之群組上的「標準」、「機密」和「主要密碼」。</span><span class="sxs-lookup"><span data-stu-id="be302-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="be302-134">預設不會設定群組分類，您必須建立群組分類，使用者才能設定群組分類。</span><span class="sxs-lookup"><span data-stu-id="be302-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="be302-135">使用 Azure Active Directory PowerShell 將使用者指向您組織的 Microsoft 365 群組使用原則。</span><span class="sxs-lookup"><span data-stu-id="be302-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Microsoft 365 Groups.</span></span>

<span data-ttu-id="be302-136">請參閱 [Azure Active Directory Cmdlet 以設定群組設定](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)，並依照在 **目錄層級建立設定** 中的步驟，定義 Microsoft 365 群組的分類。</span><span class="sxs-lookup"><span data-stu-id="be302-136">Check out [Azure Active Directory cmdlets for configuring group settings](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Microsoft 365 Groups.</span></span>

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="be302-137">為了讓描述與每個分類產生關聯，您可以使用 settings 屬性  *ClassificationDescriptions* 來定義。</span><span class="sxs-lookup"><span data-stu-id="be302-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="be302-138">分類會符合 ClassificationList 中字串的位置。</span><span class="sxs-lookup"><span data-stu-id="be302-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="be302-139">範例：</span><span class="sxs-lookup"><span data-stu-id="be302-139">Example:</span></span>

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="be302-140">在您執行上述 Azure Active Directory Cmdlet 以設定分類之後，如果您想要設定特定群組的分類，請執行[Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="be302-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span>

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

<span data-ttu-id="be302-141">或建立具有分類的新群組。</span><span class="sxs-lookup"><span data-stu-id="be302-141">Or create a new group with a classification.</span></span>

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

<span data-ttu-id="be302-142">請[使用 PowerShell 搭配 Exchange Online](/powershell/exchange/exchange-online-powershell)和[連線 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) ，以取得更多有關使用 Exchange Online PowerShell 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="be302-142">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span>

<span data-ttu-id="be302-143">啟用這些設定之後，群組擁有者將可以從 Outlook Outlook 網頁上的下拉式功能表選擇分類，並從 [**編輯** 群組] 頁面進行儲存。</span><span class="sxs-lookup"><span data-stu-id="be302-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span>

![選擇 Microsoft 365 群組分類](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a><span data-ttu-id="be302-145">從全域通訊清單中隱藏 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="be302-145">Hide Microsoft 365 Groups from the global address list.</span></span>
<span data-ttu-id="be302-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="be302-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="be302-147">您可以指定 Microsoft 365 群組是否會出現在全域通訊清單 (GAL) 和組織中的其他清單。</span><span class="sxs-lookup"><span data-stu-id="be302-147">You can specify whether a Microsoft 365 Group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="be302-148">例如，如果您有一個您不想要顯示在通訊清單中的法律部門群組，您可以停止該群組出現在 GAL 中。</span><span class="sxs-lookup"><span data-stu-id="be302-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in the GAL.</span></span> <span data-ttu-id="be302-149">執行 Set-Unified Group 資訊清單，以在通訊清單中隱藏群組，如下所示：</span><span class="sxs-lookup"><span data-stu-id="be302-149">Run the Set-Unified Group cmdlet to hide the group from the address list like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a><span data-ttu-id="be302-150">只允許內部使用者將郵件傳送至 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="be302-150">Allow only internal users to send message to Microsoft 365 Groups</span></span>
<span data-ttu-id="be302-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="be302-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="be302-152">如果您不想讓其他組織的使用者將電子郵件傳送至 Microsoft 365 群組，您可以變更該群組的設定。</span><span class="sxs-lookup"><span data-stu-id="be302-152">If you don't want users from other organizations to send emails to a Microsoft 365 Group, you can change the settings for that group.</span></span> <span data-ttu-id="be302-153">它只允許內部使用者將電子郵件傳送至您的群組。</span><span class="sxs-lookup"><span data-stu-id="be302-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="be302-154">如果外部使用者嘗試傳送郵件給該群組，它會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="be302-154">If an external user tries to send a message to that group, it will be rejected.</span></span>

<span data-ttu-id="be302-155">執行 Set-UnifiedGroup Cmdlet 以更新此設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="be302-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a><span data-ttu-id="be302-156">將 MailTips 新增至 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="be302-156">Add MailTips to Microsoft 365 Groups</span></span>
<span data-ttu-id="be302-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="be302-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="be302-158">當寄件者嘗試將電子郵件傳送至 Microsoft 365 群組時，會向他們顯示 MailTip。</span><span class="sxs-lookup"><span data-stu-id="be302-158">Whenever a sender tries to send an email to a Microsoft 365 Group, a MailTip can be shown to them.</span></span>

<span data-ttu-id="be302-159">執行 Set-Unified Group 指令，將郵件提示新增至群組：</span><span class="sxs-lookup"><span data-stu-id="be302-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="be302-160">除了 MailTip 之外，您也可以設定 MailTipTranslations，以指定 MailTip 的其他語言。</span><span class="sxs-lookup"><span data-stu-id="be302-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="be302-161">假設您想要使用西班牙文翻譯，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="be302-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a><span data-ttu-id="be302-162">變更 Microsoft 365 群組的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="be302-162">Change the display name of the Microsoft 365 Group</span></span>

<span data-ttu-id="be302-163">顯示名稱會指定 Microsoft 365 群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="be302-163">The display name specifies the name of the Microsoft 365 Group.</span></span> <span data-ttu-id="be302-164">您可以在 exchange 系統管理中心或 Microsoft 365 系統管理中心中看到此名稱。</span><span class="sxs-lookup"><span data-stu-id="be302-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="be302-165">您可以執行 Set-UnifiedGroup 命令，編輯群組的顯示名稱或指派顯示名稱給現有的 Microsoft 365 群組：</span><span class="sxs-lookup"><span data-stu-id="be302-165">You can edit the display name of the group or assign a display name to an existing Microsoft 365 Group by running the Set-UnifiedGroup command:</span></span>

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="be302-166">將 Microsoft 365 群組的預設設定變更為 Public 或 Private Outlook</span><span class="sxs-lookup"><span data-stu-id="be302-166">Change the default setting of Microsoft 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="be302-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="be302-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="be302-168">Microsoft 365預設會將 Outlook 中的群組建立為私人。</span><span class="sxs-lookup"><span data-stu-id="be302-168">Microsoft 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="be302-169">如果您的組織想要 Microsoft 365 群組建立為公開的預設 (或回私人) ，請使用此 PowerShell Cmdlet 語法：</span><span class="sxs-lookup"><span data-stu-id="be302-169">If your organization wants Microsoft 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

<span data-ttu-id="be302-170">設為私人：</span><span class="sxs-lookup"><span data-stu-id="be302-170">To set to Private:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

<span data-ttu-id="be302-171">若要確認設定：</span><span class="sxs-lookup"><span data-stu-id="be302-171">To verify the setting:</span></span>

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

<span data-ttu-id="be302-172">若要深入瞭解，請參閱 [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) 和 [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig)。</span><span class="sxs-lookup"><span data-stu-id="be302-172">To learn more, see [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig).</span></span>

## <a name="microsoft-365-groups-cmdlets"></a><span data-ttu-id="be302-173">Microsoft 365群組 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="be302-173">Microsoft 365 Groups cmdlets</span></span>

<span data-ttu-id="be302-174">下列 Cmdlet 可搭配 Microsoft 365 群組使用。</span><span class="sxs-lookup"><span data-stu-id="be302-174">The following cmdlets can be used with Microsoft 365 Groups.</span></span>

|<span data-ttu-id="be302-175">**Cmdlet 名稱**</span><span class="sxs-lookup"><span data-stu-id="be302-175">**Cmdlet name**</span></span>|<span data-ttu-id="be302-176">**描述**</span><span class="sxs-lookup"><span data-stu-id="be302-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="be302-177">Set-unifiedgroup</span><span class="sxs-lookup"><span data-stu-id="be302-177">Get-UnifiedGroup</span></span>](/powershell/module/exchange/get-unifiedgroup) <br/> |<span data-ttu-id="be302-178">使用此 Cmdlet 來查詢現有的 Microsoft 365 群組，以及查看 group 物件的屬性</span><span class="sxs-lookup"><span data-stu-id="be302-178">Use this cmdlet to look up existing Microsoft 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="be302-179">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="be302-179">Set-UnifiedGroup</span></span>](/powershell/module/exchange/set-unifiedgroup) <br/> |<span data-ttu-id="be302-180">更新特定 Microsoft 365 群組的屬性</span><span class="sxs-lookup"><span data-stu-id="be302-180">Update the properties of a specific Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="be302-181">新 Set-unifiedgroup</span><span class="sxs-lookup"><span data-stu-id="be302-181">New-UnifiedGroup</span></span>](/powershell/module/exchange/new-unifiedgroup) <br/> |<span data-ttu-id="be302-182">建立新的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="be302-182">Create a new Microsoft 365 Group.</span></span> <span data-ttu-id="be302-183">此 Cmdlet 提供一組基本的參數。</span><span class="sxs-lookup"><span data-stu-id="be302-183">This cmdlet provides a minimal set of parameters.</span></span> <span data-ttu-id="be302-184">若要設定擴充屬性的值，請在建立新群組之後使用 Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="be302-184">To set values for extended properties, use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="be302-185">Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="be302-185">Remove-UnifiedGroup</span></span>](/powershell/module/exchange/remove-unifiedgroup) <br/> |<span data-ttu-id="be302-186">刪除現有的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="be302-186">Delete an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="be302-187">UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="be302-187">Get-UnifiedGroupLinks</span></span>](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |<span data-ttu-id="be302-188">取得 Microsoft 365 群組的成員資格及擁有者資訊</span><span class="sxs-lookup"><span data-stu-id="be302-188">Retrieve membership and owner information for a Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="be302-189">Add-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="be302-189">Add-UnifiedGroupLinks</span></span>](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |<span data-ttu-id="be302-190">將成員、擁有者和訂閱者新增至現有的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="be302-190">Add members, owners, and subscribers to an existing Microsoft 365 Group</span></span> <br/> |
|[<span data-ttu-id="be302-191">Remove-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="be302-191">Remove-UnifiedGroupLinks</span></span>](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |<span data-ttu-id="be302-192">從現有的 Microsoft 365 群組中移除擁有者和成員</span><span class="sxs-lookup"><span data-stu-id="be302-192">Remove owners and members from an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="be302-193">UserPhoto</span><span class="sxs-lookup"><span data-stu-id="be302-193">Get-UserPhoto</span></span>](/powershell/module/exchange/get-userphoto) <br/> |<span data-ttu-id="be302-194">用來查看與帳戶相關聯之使用者相片的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="be302-194">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="be302-195">使用者相片儲存在 Active Directory 中</span><span class="sxs-lookup"><span data-stu-id="be302-195">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="be302-196">UserPhoto</span><span class="sxs-lookup"><span data-stu-id="be302-196">Set-UserPhoto</span></span>](/powershell/module/exchange/set-userphoto) <br/> |<span data-ttu-id="be302-197">用於將使用者相片與帳戶產生關聯。</span><span class="sxs-lookup"><span data-stu-id="be302-197">Used to associate a user photo with an account.</span></span> <span data-ttu-id="be302-198">使用者相片儲存在 Active Directory 中</span><span class="sxs-lookup"><span data-stu-id="be302-198">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="be302-199">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="be302-199">Remove-UserPhoto</span></span>](/powershell/module/exchange/remove-userphoto) <br/> |<span data-ttu-id="be302-200">移除 Microsoft 365 群組的相片</span><span class="sxs-lookup"><span data-stu-id="be302-200">Remove the photo for an Microsoft 365 Group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="be302-201">相關主題</span><span class="sxs-lookup"><span data-stu-id="be302-201">Related topics</span></span>

[<span data-ttu-id="be302-202">將通訊群組清單升級至 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="be302-202">Upgrade distribution lists to Microsoft 365 Groups</span></span>](/office365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="be302-203">管理能建立 Microsoft 365 群組的使用者</span><span class="sxs-lookup"><span data-stu-id="be302-203">Manage who can create Microsoft 365 Groups</span></span>](/office365/admin/create-groups/manage-creation-of-groups)

[<span data-ttu-id="be302-204">管理 Microsoft 365 群組的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="be302-204">Manage guest access to Microsoft 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="be302-205">將靜態群組成員資格變更為動態的</span><span class="sxs-lookup"><span data-stu-id="be302-205">Change static group membership to dynamic in</span></span>](/azure/active-directory/users-groups-roles/groups-change-type)
