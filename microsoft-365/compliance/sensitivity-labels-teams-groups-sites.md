---
title: 對 Microsoft Teams、Office 365 群組和 SharePoint 網站使用敏感度標籤 (公開預覽)
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 您可以將標籤套用至 Microsoft Teams、Office 365 群組和 SharePoint 網站。
ms.openlocfilehash: 350e1906e4d645c444d772b1ade9a2ff9c850992
ms.sourcegitcommit: 1b1425142ae06deae3da10a7d30dce4db029d6d3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/27/2020
ms.locfileid: "42313798"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="d3d7f-103">對 Microsoft Teams、Office 365 群組和 SharePoint 網站使用敏感度標籤 (公開預覽)</span><span class="sxs-lookup"><span data-stu-id="d3d7f-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="d3d7f-104">在 [Microsoft 365 合規性中心](https://protection.office.com/)中建立敏感度標籤時，您現在可以將它們套用至下列容器：Microsoft Teams、Office 365 群組和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to the following containers: Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="d3d7f-105">使用標籤設定來控制下列容器的選項：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-105">Use label settings to control the following options for these containers:</span></span>

- <span data-ttu-id="d3d7f-106">Office 365 群組連線小組網站的隱私權 (公開或私人)</span><span class="sxs-lookup"><span data-stu-id="d3d7f-106">Privacy (public or private) of Office 365 group-connected teams sites</span></span>
- <span data-ttu-id="d3d7f-107">外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="d3d7f-107">External users access</span></span>
- <span data-ttu-id="d3d7f-108">從未受控裝置存取</span><span class="sxs-lookup"><span data-stu-id="d3d7f-108">Access from unmanaged devices</span></span> 

<span data-ttu-id="d3d7f-109">當您將此標籤套用至支援的其中一個容器時，標籤會自動將已設定的選項套用到連線的 SharePoint 網站或小組網站。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-109">When you apply this label to one of the supported containers, the label automatically applies the configured options to the connected SharePoint site or team site.</span></span> 

<span data-ttu-id="d3d7f-110">不過，這些容器中的內容不會繼承標籤名稱、視覺標記或加密等設定的標籤。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-110">Content in those containers however, do not inherit the labels for settings such as the label name, visual markings, or encryption.</span></span> <span data-ttu-id="d3d7f-111">若要在 SharePoint 網站或小組網站中的檔案加上標籤，請[對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md) (英文版)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-111">To label files in SharePoint sites or team sites, [enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="d3d7f-112">關於 Microsoft Teams、Office 365 群組和 SharePoint 網站的公開預覽</span><span class="sxs-lookup"><span data-stu-id="d3d7f-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="d3d7f-113">Microsoft Teams、Office 365 群組和 SharePoint 網站的敏感度標籤會逐漸向租用戶推出，且可能在最終發行之前變更。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites are gradually rolling out to tenants and might change before final release.</span></span> <span data-ttu-id="d3d7f-114">此公開預覽不適用 Office 365 內容傳遞網路 (CDN)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-114">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

<span data-ttu-id="d3d7f-115">啟用此預覽並設定新設定的敏感度標籤前，使用者可在其應用程式中查看並套用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-115">Before you enable this preview and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="d3d7f-116">例如，在 Word 中：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-116">For example, from Word:</span></span>

![Word 傳統型應用程式中顯示的敏感度標籤](../media/sensitivity-label-word.png)

<span data-ttu-id="d3d7f-118">啟用並設定此預覽後，使用者可進一步查看並將敏感度標籤套用至 Microsoft Teams、Office 365 群組和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-118">After you enable and configure this preview, users can additionally see and apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="d3d7f-119">例如，從 SharePoint 建立新的小組網站時：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-119">For example, when you create a new team site from SharePoint:</span></span>

![從 SharePoint 建立小組網站時的敏感度標籤](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a><span data-ttu-id="d3d7f-121">啟用此預覽並同步處理標籤</span><span class="sxs-lookup"><span data-stu-id="d3d7f-121">Enable this preview and synchronize labels</span></span>

1. <span data-ttu-id="d3d7f-122">由於此功能使用 Azure AD 功能，請依照 Azure AD 文件中的指示來啟用預覽：[將敏感度標籤指派到 Azure Active Directory 中的 Office 365 群組 (預覽)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels) (英文版)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-122">Because this feature uses Azure AD functionality, follow the instructions in the Azure AD documentation to enable the preview: [Assign sensitivity labels to Office 365 groups in Azure Active Directory (preview)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="d3d7f-123">在 PowerShell 工作階段中，使用具備全域系統管理員權限的公司或學校帳戶連線至安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-123">In a PowerShell session, connect to the Security & Compliance Center by using a work or school account that has global admin privileges.</span></span> <span data-ttu-id="d3d7f-124">如需指示，請參閱[連線到 Office 365 安全性與合規性中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-124">For instructions, see [Connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="d3d7f-125">執行下列命令以將您的標籤同步處理到 Azure AD，以便與 Office 365 群組搭配使用：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-125">Run the following commands to synchronize your labels to Azure AD, so that they can be used with Office 365 groups:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="d3d7f-126">如何在建立或編輯敏感度標籤時設定網站和群組設定</span><span class="sxs-lookup"><span data-stu-id="d3d7f-126">How to configure site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="d3d7f-127">您現在可以建立或編輯需要用於網站和群組的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-127">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="d3d7f-128">啟用預覽可在敏感度標籤精靈中顯示新頁面：**網站和群組設定**</span><span class="sxs-lookup"><span data-stu-id="d3d7f-128">Enabling the preview makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="d3d7f-129">如果您需要建立或編輯敏感度標籤的協助，請參閱[建立及設定敏感度標籤](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)的指示。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-129">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="d3d7f-130">在這個新的**網站和群組設定**頁面上，設定以下設定：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-130">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="d3d7f-131">**Office 365 群組連線小組網站**：系統會自動選取預設設定**公開**，這表示貴組織中的任何人都能存取套用此標籤的小組網站。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-131">**Privacy of Office 365 group-connected teams sites**: The default setting of **Public** is automatically selected, which means anyone in your organization can access the team site where this label is applied.</span></span> <span data-ttu-id="d3d7f-132">如果只想要讓貴組織中的核准成員存取群組的小組網站，請選取 [**私人**]。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-132">Select **Private** when you want only approved members in your organization to access the group's team site.</span></span> 
    
    <span data-ttu-id="d3d7f-133">選取的設定會取代先前為群組設定的隱私權設定，並鎖定隱私權值，所以只能先移除小組網站或群組的敏感度標籤才能變更。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-133">The setting selected replaces a previous privacy setting that might be configured for the group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the team site or group.</span></span> <span data-ttu-id="d3d7f-134">移除敏感度標籤後，標籤的隱私權設定會保留，您可以視需要變更。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-134">After you remove the sensitivity label, the privacy setting from the label remains and you can now change it if necessary.</span></span>

- <span data-ttu-id="d3d7f-135">**外部使用者存取**：控制群組擁有者是否可以[將來賓新增至群組](/office365/admin/create-groups/manage-guest-access-in-groups)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-135">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="d3d7f-136">**未受管理的裝置**：針對[未受管理的裝置](/sharepoint/control-access-from-unmanaged-devices)，允許完全存取、僅限 Web 存取，或完全封鎖存取權。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-136">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> 

![網站和群組設定索引標籤](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="d3d7f-138">將標籤套用至小組、群組或網站時，只有這些網站和群組設定會生效。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-138">Only these site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="d3d7f-139">其他標籤設定，例如加密和內容標記，均不會套用至小組、群組或網站內的內容。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-139">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="d3d7f-140">同樣地，如果您建立標籤，但未開啟這些網站和群組設定，當使用者建立小組、群組和網站時，標籤仍將可用，但只會套用標籤名稱。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-140">Similarly, if you create a label and don't turn on these site and group settings, the label will still be available when users create teams, groups, and sites, but only the label name will be applied.</span></span>

<span data-ttu-id="d3d7f-141">如果您的標籤還未發佈，現在請[將標籤新增至標籤原則](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)以進行發佈。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-141">If your label isn't already published, now publish it by [adding it to a label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="d3d7f-142">敏感度標籤管理</span><span class="sxs-lookup"><span data-stu-id="d3d7f-142">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="d3d7f-143">建立、修改和刪除您用於 Microsoft Teams、Office 365 群組和 SharePoint 網站的敏感度標籤時，需要謹慎地就發佈標籤原則給使用者進行協調。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-143">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Office 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="d3d7f-144">使用下列指南來避免可能影響所有使用者的網站和群組建立錯誤。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-144">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="d3d7f-145">**建立及發佈標籤：**</span><span class="sxs-lookup"><span data-stu-id="d3d7f-145">**Creating and publishing labels:**</span></span>

<span data-ttu-id="d3d7f-146">建立並發佈敏感度標籤後，最多可能需要 24 小時的時間，標籤才會對小組、群組和網站中的使用者顯示。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-146">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="d3d7f-147">使用下列步驟為租用戶中的所有使用者發佈標籤：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-147">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="d3d7f-148">建立敏感度標籤，並只對租用戶中的一些使用者帳戶發佈。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-148">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="d3d7f-149">等候 24 小時。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-149">Wait for 24 hours.</span></span>

3. <span data-ttu-id="d3d7f-150">等候 24 小時之後，使用您在步驟 1 中指定的其中一個使用者帳戶來建立小組、Office 365 群組或 SharePoint 網站，並搭配您在步驟 1 中建立的標籤。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-150">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Office 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="d3d7f-151">如果在步驟 3 的建立作業期間沒有發生任何錯誤，請對您的租用戶中的所有使用者發佈標籤。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-151">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="d3d7f-152">如果發生錯誤，請連絡 [Microsoft 支援](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-152">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="d3d7f-153">**修改及刪除已發佈的標籤：**</span><span class="sxs-lookup"><span data-stu-id="d3d7f-153">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="d3d7f-154">如果您修改或刪除包含在一或多個標籤原則中的敏感度標籤，這些動作可能會導致所有小組、群組和網站建立失敗。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-154">If you modify or delete a sensitivity label that is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="d3d7f-155">若要避免此情況，請使用下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-155">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="d3d7f-156">從包含標籤的所有標籤原則中移除敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-156">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="d3d7f-157">等候 48 小時。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-157">Wait for 48 hours.</span></span>

3. <span data-ttu-id="d3d7f-158">在等候 48 小時之後，請嘗試建立小組、群組或網站，並確認標籤已不再顯示。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-158">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="d3d7f-159">如果敏感度標籤未顯示，您現在可以放心地修改或刪除標籤。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-159">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="d3d7f-160">如果標籤仍顯示，請連絡 [Microsoft 支援](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-160">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="assign-sensitivity-labels-to-office-365-groups"></a><span data-ttu-id="d3d7f-161">將敏感度標籤指派給 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="d3d7f-161">Assign sensitivity labels to Office 365 groups</span></span>

<span data-ttu-id="d3d7f-162">您現在可以將敏感度標籤或標籤套用至 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-162">You're now ready to apply the sensitivity label or labels to Office 365 groups.</span></span> <span data-ttu-id="d3d7f-163">如需指示，請返回 Azure AD 文件：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-163">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="d3d7f-164">在 Azure 入口網站中將標籤指派至新群組</span><span class="sxs-lookup"><span data-stu-id="d3d7f-164">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [<span data-ttu-id="d3d7f-165">在 Azure 入口網站中將標籤指派至現有群組</span><span class="sxs-lookup"><span data-stu-id="d3d7f-165">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="d3d7f-166">[在 Azure 入口網站中將標籤從現有群組移除](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-166">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="d3d7f-167">將敏感度標籤套用至新的小組</span><span class="sxs-lookup"><span data-stu-id="d3d7f-167">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="d3d7f-168">當使用者在 Microsoft Teams 中建立新小組時，可選取敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-168">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="d3d7f-169">當使用者選取敏感度等級時，隱私權設定會視需要變更。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-169">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="d3d7f-170">根據您為標籤選取的外部使用者存取設定，使用者可以或無法將組織外部的人員新增至小組。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-170">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="d3d7f-171">深入了解 Teams 的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="d3d7f-171">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![建立新小組時的隱私權設定](../media/privacy-setting-new-team.png)

<span data-ttu-id="d3d7f-173">建立小組之後，敏感度標籤會顯示在所有頻道的右上角。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-173">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![敏感度標籤顯示在小組上](../media/privacy-setting-teams.png)

<span data-ttu-id="d3d7f-175">服務自動將相同的敏感度標籤套用至 Office 365 群組和連線的 SharePoint 小組網站。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-175">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="d3d7f-176">在 Outlook 網頁版中將敏感度標籤套用至新的群組</span><span class="sxs-lookup"><span data-stu-id="d3d7f-176">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="d3d7f-177">在 Outlook 網頁版中，當您建立新的群組時，您可以選取或變更已發佈標籤的**敏感度**選項：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-177">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![建立群組並選取 [敏感度] 底下的選項](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="d3d7f-179">將敏感度標籤套用至新的網站</span><span class="sxs-lookup"><span data-stu-id="d3d7f-179">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="d3d7f-180">系統管理員和使用者可以在[建立新式小組網站和通訊網站](/sharepoint/create-site-collection)時選取敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-180">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection).</span></span>

<span data-ttu-id="d3d7f-181">當使用者建立新式小組和通訊網站，預設會選取某個敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-181">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="d3d7f-182">使用者可以選取 [說明] 圖示來深入了解標籤。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-182">Users can select the help icon to learn more about the labels.</span></span>

![建立網站並選取 [敏感度] 底下的選項](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="d3d7f-184">當使用者瀏覽至網站，他們可以看到標籤的名稱和套用的原則。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-184">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![已套用敏感度標籤的網站](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="d3d7f-186">在 SharePoint 系統管理中心檢視敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="d3d7f-186">View sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="d3d7f-187">若要檢視套用的敏感度標籤，請使用新 SharePoint 系統管理中心的 **[使用中網站]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-187">To view the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="d3d7f-188">您可能需要先新增 **[敏感度]** 欄：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-188">You might need to first add the **Sensitivity** column:</span></span>

![[使用中網站] 頁面上的 [敏感度] 欄](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="d3d7f-190">[深入了解在新的 SharePoint 系統管理中心管理網站](/sharepoint/manage-sites-in-new-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-190">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="d3d7f-191">變更標籤的網站和群組設定</span><span class="sxs-lookup"><span data-stu-id="d3d7f-191">Change site and group settings for a label</span></span>

<span data-ttu-id="d3d7f-192">每當您變更標籤的網站和群組設定時，您必須執行下列 PowerShell 命令，以便您的小組、網站和群組可以使用新的設定。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-192">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="d3d7f-193">最佳做法是，不要在將標籤套用至數個小組、群組或網站之後，變更網站和群組設定。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-193">As a best practice, don't the change site and group settings for a label after you've applied the label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="d3d7f-194">執行下列命令以連線至 Office 365 安全性與合規性中心 PowerShell，並取得敏感度標籤及其 GUID 清單。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-194">Run the following commands to connect to Office 365 Security & Compliance Center PowerShell and get the list of sensitivity labels and their GUIDs.</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. <span data-ttu-id="d3d7f-195">記下您已變更之標籤的 GUID。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-195">Make a note of the GUID for the label or labels you have changed.</span></span>

3. <span data-ttu-id="d3d7f-196">現在連線到 Exchange Online PowerShell 並執行 Set-unifiedgroup Cmdlet，然後指定您的標籤 GUID 來取代 "e48058ea-98e8-4940-8db0-ba1310fd955e" 的 GUID 範例：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-196">Now connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. <span data-ttu-id="d3d7f-197">針對每個群組，重新套用敏感度標籤，然後指定您的標籤 GUID 來取代 "e48058ea-98e8-4940-8db0-ba1310fd955e" 的 GUID 範例：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-197">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a><span data-ttu-id="d3d7f-198">支援敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="d3d7f-198">Support for the sensitivity labels</span></span>

<span data-ttu-id="d3d7f-199">您可以搭配下列應用程式和服務，使用您為網站和群組設定套用的敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-199">You can use the sensitivity labels that you've configured for site and group settings with the following apps and services:</span></span>

- <span data-ttu-id="d3d7f-200">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d3d7f-200">SharePoint Online</span></span>
- <span data-ttu-id="d3d7f-201">Teams</span><span class="sxs-lookup"><span data-stu-id="d3d7f-201">Teams</span></span>
- <span data-ttu-id="d3d7f-202">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="d3d7f-202">Outlook on the web</span></span>
- <span data-ttu-id="d3d7f-203">SharePoint 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d3d7f-203">SharePoint admin center</span></span>
- <span data-ttu-id="d3d7f-204">Azure AD 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d3d7f-204">Azure AD admin center</span></span>

<span data-ttu-id="d3d7f-205">目前無法使用您為網站和群組設定套用的敏感度標籤的其他應用程式和服務包括：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-205">Other apps and services that you can't currently use the sensitivity labels that you've configured for site and group settings include:</span></span>

- <span data-ttu-id="d3d7f-206">Mac 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="d3d7f-206">Outlook for the Mac</span></span>
- <span data-ttu-id="d3d7f-207">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="d3d7f-207">Outlook mobile</span></span>
- <span data-ttu-id="d3d7f-208">適用於 Windows 的電腦版 Outlook</span><span class="sxs-lookup"><span data-stu-id="d3d7f-208">Outlook desktop for Windows</span></span>
- <span data-ttu-id="d3d7f-209">Forms</span><span class="sxs-lookup"><span data-stu-id="d3d7f-209">Forms</span></span>
- <span data-ttu-id="d3d7f-210">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d3d7f-210">Dynamics 365</span></span>
- <span data-ttu-id="d3d7f-211">Yammer</span><span class="sxs-lookup"><span data-stu-id="d3d7f-211">Yammer</span></span>
- <span data-ttu-id="d3d7f-212">Stream</span><span class="sxs-lookup"><span data-stu-id="d3d7f-212">Stream</span></span>
- <span data-ttu-id="d3d7f-213">Planner</span><span class="sxs-lookup"><span data-stu-id="d3d7f-213">Planner</span></span>
- <span data-ttu-id="d3d7f-214">Project</span><span class="sxs-lookup"><span data-stu-id="d3d7f-214">Project</span></span>
- <span data-ttu-id="d3d7f-215">PowerBI</span><span class="sxs-lookup"><span data-stu-id="d3d7f-215">PowerBI</span></span>
- <span data-ttu-id="d3d7f-216">Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d3d7f-216">Teams admin center</span></span>
- <span data-ttu-id="d3d7f-217">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d3d7f-217">Microsoft 365 admin center</span></span>
- <span data-ttu-id="d3d7f-218">Exchange 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d3d7f-218">Exchange admin center</span></span>


## <a name="classic-azure-ad-site-classification"></a><span data-ttu-id="d3d7f-219">傳統 Azure AD 網站分類</span><span class="sxs-lookup"><span data-stu-id="d3d7f-219">Classic Azure AD site classification</span></span>

<span data-ttu-id="d3d7f-220">啟用此預覽時，Office 365 不再對新群組和 SharePoint 網站支援舊分類。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-220">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="d3d7f-221">不過，現有的群組和網站仍會顯示舊的分類，除非您轉換它們以使用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-221">However, existing groups and sites still display the old classifications unless you convert them to use sensitivity labels.</span></span> <span data-ttu-id="d3d7f-222">舊的類別包括您設定的「新式」網站分類，可能是透過 Azure AD PowerShell 或 PnP 核心程式庫所設定，其中定義了 `ClassificationList` 設定的值。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-222">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="d3d7f-223">例如，在 PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-223">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="d3d7f-224">如需舊分類方法的詳細資訊，請參閱 [SharePoint「新式」網站分類](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-224">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="d3d7f-225">若要將舊分類轉換成敏感度標籤，請執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-225">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="d3d7f-226">使用現有的標籤：編輯已發佈的現有敏感度標籤，以指定網站和群組需要的標籤設定。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-226">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="d3d7f-227">建立新標籤：建立及發佈與現有分類名稱相同的新敏感度標籤，以指定網站和群組需要的標籤設定。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-227">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="d3d7f-228">然後：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-228">Then:</span></span> 

1. <span data-ttu-id="d3d7f-229">使用 PowerShell，利用名稱對應將敏感度標籤套用至現有的 Office 365 群組和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-229">Use PowerShell to apply the sensitivity labels to existing Office 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="d3d7f-230">請參閱下一節的指示。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-230">See the next section for instructions.</span></span>

2. <span data-ttu-id="d3d7f-231">移除現有群組和網站的舊分類。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-231">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="d3d7f-232">雖然您無法防止使用者在尚未支援敏感度標籤的應用程式和服務中建立新群組，但您可以執行週期性 PowerShell 指令碼來尋找使用者使用舊分類建立的新群組，並將它們轉換成使用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-232">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

#### <a name="use-powershell-to-convert-classifications-for-office-365-groups-to-sensitivity-labels"></a><span data-ttu-id="d3d7f-233">使用 PowerShell 將 Office 365 群組的分類轉換成敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="d3d7f-233">Use PowerShell to convert classifications for Office 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="d3d7f-234">請確認執行 SharePoint Online 管理命令介面版本 16.0.19418.12000 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-234">Ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="d3d7f-235">如果您已有最新版本，請跳到步驟 4。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-235">If you already have the latest version, skip to step 4.</span></span>

2. <span data-ttu-id="d3d7f-236">如果您已安裝來自 PowerShell 資源庫的舊版 SharePoint Online 管理命令介面，您可以執行下列 Cmdlet 來更新模組。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-236">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>
    
    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

3. <span data-ttu-id="d3d7f-237">如果您安裝的是來自 Microsoft 下載中心的舊版 SharePoint Online 管理命令介面，請移至 **[新增或移除程式]**，並解除安裝 [SharePoint Online 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-237">If you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span> <span data-ttu-id="d3d7f-238">然後，從[下載中心](https://go.microsoft.com/fwlink/p/?LinkId=255251)下載 SharePoint Online 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-238">Then, install the latest SharePoint Online Management Shell from the [Download Center](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="d3d7f-239">使用擁有 Office 365 中的全域系統管理員或 SharePoint 系統管理員權限的公司或學校帳戶，連線到 SharePoint Online 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-239">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="d3d7f-240">若要了解如何進行，請參閱[開始使用 SharePoint Online 管理命令介面](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-240">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

5. <span data-ttu-id="d3d7f-241">執行下列命令來取得敏感度標籤及其 GUID 的清單。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-241">Run the following commands to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

6. <span data-ttu-id="d3d7f-242">記下您要套用至 Office 365 群組的敏感度標籤 GUID。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-242">Make a note of the GUIDs for the sensitivity labels you want to apply to your Office 365 groups.</span></span>

7. <span data-ttu-id="d3d7f-243">使用下列命令做為範例，以取得目前具有「一般」分類的群組清單：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-243">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="d3d7f-244">針對每個群組，新增新的敏感度標籤 GUID。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-244">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="d3d7f-245">例如：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-245">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="d3d7f-246">稽核敏感度標籤活動</span><span class="sxs-lookup"><span data-stu-id="d3d7f-246">Auditing sensitivity label activities</span></span>

<span data-ttu-id="d3d7f-247">若某使用者將文件上傳到受敏感度標籤保護的網站，且文件的敏感度標籤[優先於](sensitivity-labels.md#label-priority-order-matters)網站的敏感度標籤，則不會封鎖此動作。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-247">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="d3d7f-248">例如，您已將**一般**標籤套用至 SharePoint 網站，而某使用者上傳到此網站的文件標示為**機密**。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-248">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="d3d7f-249">由於優先順序較高的敏感度標籤會識別比優先順序較低的內容更具敏感度的內容，因此可能會造成安全性問題。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-249">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="d3d7f-250">儘管動作並未遭到封鎖，但會受到稽核，因此您可以找出與標籤優先順序不一致的文件，並視需要採取行動。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-250">Although the action isn't blocked, it is audited, so you can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="d3d7f-251">例如，從網站刪除或移動已上傳的文件。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-251">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="d3d7f-252">如果文件套用的敏感度標籤，其優先順序低於網站所套用的敏感度標籤，則不會造成安全性問題。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-252">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="d3d7f-253">例如，套用 **「一般」** 標籤的文件上傳到標記為 **「機密」** 的網站。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-253">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="d3d7f-254">在此案例中，不會產生稽核事件。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-254">In this scenario, an auditing event isn't generated.</span></span>

<span data-ttu-id="d3d7f-255">若要搜尋此事件的稽核記錄，請尋找 **[檔案與頁面活動]** 類別中的 **[偵測到的文件敏感度不相符]**。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-255">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="d3d7f-256">當某使用者在網站或群組中新增或移除敏感度標籤時，這些活動也會受到稽核。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-256">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited.</span></span> <span data-ttu-id="d3d7f-257">您可以在 [[敏感度標籤活動]](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) 類別中找到這些事件。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-257">These events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> 

<span data-ttu-id="d3d7f-258">如需搜尋稽核記錄的指示，請參閱[在安全性與合規性中心搜尋稽核記錄](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-258">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="d3d7f-259">疑難排解敏感度標籤部署</span><span class="sxs-lookup"><span data-stu-id="d3d7f-259">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="d3d7f-260">在使用 Microsoft Teams、Office 365 群組和 SharePoint 網站的敏感度標籤時遇到問題嗎？</span><span class="sxs-lookup"><span data-stu-id="d3d7f-260">Having problems with sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites?</span></span> <span data-ttu-id="d3d7f-261">請檢查下列項目：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-261">Check the following:</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="d3d7f-262">發佈之後標籤無法顯示</span><span class="sxs-lookup"><span data-stu-id="d3d7f-262">Labels not visible after publishing</span></span>
<span data-ttu-id="d3d7f-263">如果您在啟用這些設定或修改敏感度標籤的描述之後，於建立小組或建立 Office 365 小組時遇到問題，請儲存標籤變更並等候幾小時，然後嘗試再次建立小組或群組。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-263">If you experience issues when you create a team or Office 365 group after you enable these settings or modify a sensitivity label's description, wait a few hours after saving the label changes, and then try to create the team or group again.</span></span> <span data-ttu-id="d3d7f-264">如需詳細資訊，請參閱[排程在建立或變更敏感度標籤後推出](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-264">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="d3d7f-265">如果您仍看不到來自 SharePoint Online 的新敏感度標籤，請連絡 [Microsoft 支援](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-265">If you are still not able to see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="d3d7f-266">小組、群組或 SharePoint 網站建立錯誤</span><span class="sxs-lookup"><span data-stu-id="d3d7f-266">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="d3d7f-267">如果您在公開預覽期間遇到建立錯誤，您有兩個選擇：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-267">If you experience creation errors during the public preview, you have two options:</span></span>

- <span data-ttu-id="d3d7f-268">請確定未對任何使用者強制使用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-268">Ensure that sensitivity labels are not mandatory for any user.</span></span>

- <span data-ttu-id="d3d7f-269">您可以使用來自[啟用 PowerShell 中的敏感度標籤支援](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell)中的相同指示來關閉 Microsoft Teams、Office 365 群組和 SharePoint 網站的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-269">You can turn off sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="d3d7f-270">不過，若要停用預覽，請在步驟 5 中使用 `$setting["EnableMIPLabels"] = "False"` 來停用此功能。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-270">However, to disable the preview, in step 5, disable the feature by using `$setting["EnableMIPLabels"] = "False"`.</span></span>

