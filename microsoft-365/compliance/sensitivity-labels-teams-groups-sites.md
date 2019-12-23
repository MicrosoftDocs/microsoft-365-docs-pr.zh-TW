---
title: 對 Microsoft Teams、Office 365 群組和 SharePoint 網站使用敏感度標籤 (公開預覽)
ms.author: krowley
author: cabailey
manager: laurawi
ms.date: 12/13/2019
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
ms.openlocfilehash: edaa13a21d5eb9069c6e4dce509c13456dec3d89
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802876"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="cdac1-103">對 Microsoft Teams、Office 365 群組和 SharePoint 網站使用敏感度標籤 (公開預覽)</span><span class="sxs-lookup"><span data-stu-id="cdac1-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="cdac1-104">在 [Microsoft 365 合規性中心](https://protection.office.com/)中建立敏感度標籤時，您現在可以將它們套用至 Microsoft Teams、Office 365 群組和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="cdac1-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="cdac1-105">您可以將原則與標籤建立關聯，以控制：</span><span class="sxs-lookup"><span data-stu-id="cdac1-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="cdac1-106">公開/私密設定</span><span class="sxs-lookup"><span data-stu-id="cdac1-106">Public/private settings</span></span>
- <span data-ttu-id="cdac1-107">來賓存取</span><span class="sxs-lookup"><span data-stu-id="cdac1-107">Guest access</span></span>
- <span data-ttu-id="cdac1-108">從未受控裝置存取</span><span class="sxs-lookup"><span data-stu-id="cdac1-108">Access from unmanaged devices</span></span>

<span data-ttu-id="cdac1-109">當您將標籤套用至小組或群組，標籤會自動套用至連接的 SharePoint 小組網站，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="cdac1-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="cdac1-110">您現在也可以為 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-110">You can now also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="cdac1-111">如需詳細資訊，請參閱[對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤 (公開預覽)](sensitivity-labels-sharepoint-onedrive-files.md) (英文)。</span><span class="sxs-lookup"><span data-stu-id="cdac1-111">[Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md)</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="cdac1-112">關於 Microsoft Teams、Office 365 群組和 SharePoint 網站的公開預覽</span><span class="sxs-lookup"><span data-stu-id="cdac1-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="cdac1-113">Microsoft Teams、Office 365 群組和 SharePoint 網站的敏感度標籤會逐漸向租用戶推出，且可能在最終發行之前變更。</span><span class="sxs-lookup"><span data-stu-id="cdac1-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites are gradually rolling out to tenants and might change before final release.</span></span>

<span data-ttu-id="cdac1-114">此公開預覽不適用 Office 365 內容傳遞網路 (CDN)。</span><span class="sxs-lookup"><span data-stu-id="cdac1-114">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="overview"></a><span data-ttu-id="cdac1-115">概觀</span><span class="sxs-lookup"><span data-stu-id="cdac1-115">Overview</span></span>

<span data-ttu-id="cdac1-116">發佈敏感度標籤時，Office 365 中的使用者可以存取相同的標籤清單。</span><span class="sxs-lookup"><span data-stu-id="cdac1-116">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="cdac1-117">這些影像顯示：</span><span class="sxs-lookup"><span data-stu-id="cdac1-117">These images show:</span></span>

- <span data-ttu-id="cdac1-118">從 SharePoint 建立新的小組網站時，清單的顯示方式</span><span class="sxs-lookup"><span data-stu-id="cdac1-118">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="cdac1-119">在 Word 中檢視清單時</span><span class="sxs-lookup"><span data-stu-id="cdac1-119">When you view the list in Word</span></span>

<span data-ttu-id="cdac1-120">例如：</span><span class="sxs-lookup"><span data-stu-id="cdac1-120">For example:</span></span>

![從 SharePoint 建立小組網站時的敏感度標籤](media/sensitivity-label-new-team-site.png)

![Word 傳統型應用程式中顯示的敏感度標籤](media/sensitivity-label-word.png)

## <a name="enable-this-preview"></a><span data-ttu-id="cdac1-123">啟用此預覽</span><span class="sxs-lookup"><span data-stu-id="cdac1-123">Enable this preview</span></span>

<span data-ttu-id="cdac1-124">您必須使用 [Azure Active Directory PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) (模組名稱 **AzureADPreview**) 的預覽版本，才能在 Microsoft Teams、Office 365 群組和 SharePoint 網站上啟用敏感度標籤的此預覽：</span><span class="sxs-lookup"><span data-stu-id="cdac1-124">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) (module name **AzureADPreview**) to enable this preview of sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites:</span></span>

- <span data-ttu-id="cdac1-125">如果您之前尚未安裝任何版本的 Azure AD PowerShell 模組，請參閱[安裝 Azure AD 模組](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)，並遵循指示來安裝公開預覽版本。</span><span class="sxs-lookup"><span data-stu-id="cdac1-125">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="cdac1-126">如果您已安裝 Azure AD PowerShell 模組(AzureAD) 的通用版本 2.0，您必須先在 PowerShell 工作階段中執行 `Uninstall-Module AzureAD` 將其解除安裝，然後執行 `Install-Module AzureADPreview` 來安裝預覽版本。</span><span class="sxs-lookup"><span data-stu-id="cdac1-126">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="cdac1-127">如果您已安裝預覽版本，請執行 `Install-Module AzureADPreview` 以確定這是本模組的最新版本。</span><span class="sxs-lookup"><span data-stu-id="cdac1-127">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="cdac1-128">您現在可以開始啟用 Microsoft Teams、Office 365 群組和 SharePoint 網站的敏感度標籤預覽：</span><span class="sxs-lookup"><span data-stu-id="cdac1-128">You're now ready to enable the preview of sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites:</span></span>

1. <span data-ttu-id="cdac1-129">在 PowerShell 工作階段中，使用具備全域系統管理員權限的公司或學校帳戶連線到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="cdac1-129">In a PowerShell session, using a work or school account that has global admin privileges, connect to Azure Active Directory.</span></span> <span data-ttu-id="cdac1-130">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="cdac1-130">For example, run:</span></span>
    
        Connect-AzureAD
    
    <span data-ttu-id="cdac1-131">如需完整指示，請參閱[連線到 Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad)。</span><span class="sxs-lookup"><span data-stu-id="cdac1-131">For full instructions, see [Connect to Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad).</span></span>

2. <span data-ttu-id="cdac1-132">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="cdac1-132">Run the following commands:</span></span>
    
    ```powershell
    $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
    if ($setting -eq $null)
    {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
    }
    else
    {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
    }
    ```
    
    > [!NOTE]
    > <span data-ttu-id="cdac1-133">啟用此預覽時，Office 365 不再對新群組和 SharePoint 網站使用舊分類。</span><span class="sxs-lookup"><span data-stu-id="cdac1-133">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="cdac1-134">如果您使用 [Azure AD 網站分類](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"])，現有的群組和網站仍會顯示舊的分類。</span><span class="sxs-lookup"><span data-stu-id="cdac1-134">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="cdac1-135">若要顯示新的分類，請進行轉換。</span><span class="sxs-lookup"><span data-stu-id="cdac1-135">To display the new classifications, convert them.</span></span> <span data-ttu-id="cdac1-136">如需有關如何轉換的詳細資訊，請參閱[如果您使用傳統 Azure AD 網站分類](#if-you-used-classic-azure-ad-site-classification)。</span><span class="sxs-lookup"><span data-stu-id="cdac1-136">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span> 

3. <span data-ttu-id="cdac1-137">在相同的 PowerShell 工作階段中，使用具備全域系統管理員權限的公司或學校帳戶連線至安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="cdac1-137">In the same PowerShell session, now connect to the Security & Compliance Center by using a work or school account that has global admin privileges.</span></span> <span data-ttu-id="cdac1-138">如需指示，請參閱[連線到 Office 365 安全性與合規性中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="cdac1-138">For instructions, see [Connect to Office 365 Security & Compliance Center PowerShell using multi-factor authentication](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

4. <span data-ttu-id="cdac1-139">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="cdac1-139">Run the following commands:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```
## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="cdac1-140">建立或編輯敏感度標籤時設定網站和群組設定</span><span class="sxs-lookup"><span data-stu-id="cdac1-140">Set site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="cdac1-141">啟用預覽之後，請使用下列步驟來建立或編輯敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-141">After you enable the preview, use the following steps to create or edit sensitivity labels.</span></span> <span data-ttu-id="cdac1-142">您必須完成這些步驟，新的敏感度標籤才能對網站和群組運作，即使您已定義標籤也一樣。</span><span class="sxs-lookup"><span data-stu-id="cdac1-142">You must complete these steps for the new sensitivity labels to work with sites and groups, even if you already have labels defined.</span></span> <span data-ttu-id="cdac1-143">對這些設定所做的變更最多可能需要 24 小時才能同步。</span><span class="sxs-lookup"><span data-stu-id="cdac1-143">Changes to these settings might take up to 24 hours to synchronize.</span></span>

1. <span data-ttu-id="cdac1-144">在 Microsoft 365 合規性中心中，選取 [分類]\*\*\*\*  >  [敏感度標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cdac1-144">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="cdac1-145">選取 [建立標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cdac1-145">Click **Create a label**.</span></span> <span data-ttu-id="cdac1-146">如果您已經有標籤，請跳至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="cdac1-146">If you already have a label, skip to the next step.</span></span>

3. <span data-ttu-id="cdac1-147">選取您要的選項，然後在 [網站與群組設定]\*\*\*\* 索引標籤上，選擇：</span><span class="sxs-lookup"><span data-stu-id="cdac1-147">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>
    
    - <span data-ttu-id="cdac1-148">隱私權 (公開/私密)：[私密] 表示只有組織中已獲核准的成員可以查看群組內的內容。</span><span class="sxs-lookup"><span data-stu-id="cdac1-148">Privacy (Public/Private): Private means that only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="cdac1-149">組織中的其他人都無法查看群組中的內容。</span><span class="sxs-lookup"><span data-stu-id="cdac1-149">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="cdac1-150">深入了解</span><span class="sxs-lookup"><span data-stu-id="cdac1-150">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="cdac1-151">來賓存取：您可以控制是否可以將來賓新增至群組。</span><span class="sxs-lookup"><span data-stu-id="cdac1-151">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="cdac1-152">了解如何管理 Office 365 群組的來賓存取</span><span class="sxs-lookup"><span data-stu-id="cdac1-152">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="cdac1-153">未受控的裝置：此設定可讓您封鎖或限制從未在 Intune 中混合式加入 AD 或合規的裝置存取 SharePoint 內容。</span><span class="sxs-lookup"><span data-stu-id="cdac1-153">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="cdac1-154">如果您選取 [未受控的裝置]，您必須移至 Azure AD 來完成原則的設定。</span><span class="sxs-lookup"><span data-stu-id="cdac1-154">If you select Unmanaged devices, you must go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="cdac1-155">如需資訊，請參閱[從未受控裝置控制存取](/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="cdac1-155">For more information, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>
    
    ![網站和群組設定索引標籤](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="cdac1-157">將標籤套用至小組、群組或網站時，只有網站和群組設定會生效。</span><span class="sxs-lookup"><span data-stu-id="cdac1-157">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="cdac1-158">其他設定，例如加密和內容標記，均不會套用至小組、群組或網站內的所有內容。</span><span class="sxs-lookup"><span data-stu-id="cdac1-158">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="cdac1-159">同樣地，如果您建立標籤，但未開啟網站和群組設定，當使用者建立小組、群組和網站時，標籤仍將可用，但會分類而不套用任何設定。</span><span class="sxs-lookup"><span data-stu-id="cdac1-159">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it will classify without applying any settings.</span></span>

[<span data-ttu-id="cdac1-160">深入了解發佈敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="cdac1-160">Learn more about publishing sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="sensitivity-label-management"></a><span data-ttu-id="cdac1-161">敏感度標籤管理</span><span class="sxs-lookup"><span data-stu-id="cdac1-161">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="cdac1-162">建立、修改和刪除您用於 Microsoft Teams、Office 365 群組和 SharePoint 網站的敏感度標籤時，需要謹慎地就發佈標籤原則給使用者進行協調。</span><span class="sxs-lookup"><span data-stu-id="cdac1-162">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Office 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="cdac1-163">使用下列指南來避免可能影響所有使用者的網站和群組建立錯誤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-163">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="cdac1-164">**建立及發佈標籤：**</span><span class="sxs-lookup"><span data-stu-id="cdac1-164">**Creating and publishing sensitivity labels to classify content.**</span></span>

<span data-ttu-id="cdac1-165">建立並發佈敏感度標籤後，最多可能需要 24 小時的時間，標籤才會對小組、群組和網站中的使用者顯示。</span><span class="sxs-lookup"><span data-stu-id="cdac1-165">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="cdac1-166">使用下列步驟為租用戶中的所有使用者發佈標籤：</span><span class="sxs-lookup"><span data-stu-id="cdac1-166">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="cdac1-167">建立敏感度標籤，並只對租用戶中的一些使用者帳戶發佈。</span><span class="sxs-lookup"><span data-stu-id="cdac1-167">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="cdac1-168">等候 24 小時。</span><span class="sxs-lookup"><span data-stu-id="cdac1-168">Wait for 24 hours.</span></span>

3. <span data-ttu-id="cdac1-169">等候 24 小時之後，使用您在步驟 1 中指定的其中一個使用者帳戶來建立小組、Office 365 群組或 SharePoint 網站，並搭配您在步驟 1 中建立的標籤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-169">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Office 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="cdac1-170">如果在步驟 3 的建立作業期間沒有發生任何錯誤，請對您的租用戶中的所有使用者發佈標籤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-170">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="cdac1-171">如果發生錯誤，請連絡 Microsoft 支援。</span><span class="sxs-lookup"><span data-stu-id="cdac1-171">If there are errors, contact Microsoft Support.</span></span>

<span data-ttu-id="cdac1-172">**修改及刪除已發佈的標籤：**</span><span class="sxs-lookup"><span data-stu-id="cdac1-172">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="cdac1-173">如果您修改或刪除包含在一或多個標籤原則中的敏感度標籤，這些動作可能會導致所有小組、群組和網站建立失敗。</span><span class="sxs-lookup"><span data-stu-id="cdac1-173">If you modify or delete a sensitivity label that is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="cdac1-174">若要避免此情況，請使用下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="cdac1-174">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="cdac1-175">從包含標籤的所有標籤原則中移除敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-175">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="cdac1-176">等候 48 小時。</span><span class="sxs-lookup"><span data-stu-id="cdac1-176">Wait for 48 hours.</span></span>

3. <span data-ttu-id="cdac1-177">在等候 48 小時之後，請嘗試建立小組、群組或網站，並確認標籤已不再顯示。</span><span class="sxs-lookup"><span data-stu-id="cdac1-177">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="cdac1-178">如果敏感度標籤未顯示，您現在可以放心地修改或刪除標籤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-178">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="cdac1-179">如果標籤仍顯示，請連絡 Microsoft 支援。</span><span class="sxs-lookup"><span data-stu-id="cdac1-179">If the label is still visible, contact Microsoft Support.</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="cdac1-180">疑難排解敏感度標籤部署</span><span class="sxs-lookup"><span data-stu-id="cdac1-180">Troubleshoot sensitivity label deployment</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="cdac1-181">發佈之後標籤無法顯示</span><span class="sxs-lookup"><span data-stu-id="cdac1-181">Labels not visible after publishing</span></span>
<span data-ttu-id="cdac1-182">如果您在啟用這些設定或修改敏感度標籤的描述之後，於建立小組或建立 Office 365 小組時遇到問題，請儲存標籤，等候幾小時，然後嘗試再次建立小組或群組。</span><span class="sxs-lookup"><span data-stu-id="cdac1-182">If you experience issues when you create a team or Office 365 group after you enable these settings or modify a sensitivity label's description, save the label, wait a few hours, and then try to create the team or group again.</span></span> <span data-ttu-id="cdac1-183">如需詳細資訊，請參閱[排程在建立或變更敏感度標籤後推出](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label)。</span><span class="sxs-lookup"><span data-stu-id="cdac1-183">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="cdac1-184">如果您仍看不到來自 SharePoint Online 的新敏感度標籤，請連絡 Microsoft 支援。</span><span class="sxs-lookup"><span data-stu-id="cdac1-184">If you are still not able to see the new sensitivity label from SharePoint Online, contact Microsoft Support.</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="cdac1-185">小組、群組或 SharePoint 網站建立錯誤</span><span class="sxs-lookup"><span data-stu-id="cdac1-185">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="cdac1-186">如果您在公開預覽期間遇到建立錯誤，您有兩個選擇：</span><span class="sxs-lookup"><span data-stu-id="cdac1-186">If you experience creation errors during the public preview, you have two options:</span></span>

- <span data-ttu-id="cdac1-187">請確定未對任何使用者強制使用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-187">Ensure that sensitivity labels are not mandatory for any user.</span></span>

- <span data-ttu-id="cdac1-188">您可以使用來自此頁面上[啟用此預覽](#enable-this-preview)一節中的指示，來關閉 Microsoft Teams、Office 365 群組和 SharePoint 網站的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-188">You can turn off sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites by using the same instructions from the [Enable this preview](#enable-this-preview) section on this page.</span></span> <span data-ttu-id="cdac1-189">不過，若要停用預覽，請搜尋此行 `$setting["EnableMIPLabels"] = "True"`，並將 **True** 值變更為 **False**。</span><span class="sxs-lookup"><span data-stu-id="cdac1-189">However, to disable the preview, search for the line `$setting["EnableMIPLabels"] = "True"`, and change the **True** value to **False**.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="cdac1-190">將敏感度標籤套用至新的小組</span><span class="sxs-lookup"><span data-stu-id="cdac1-190">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="cdac1-191">當使用者在 Microsoft Teams 中建立新小組時，可選取敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-191">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="cdac1-192">當使用者選取敏感度等級時，隱私權設定會視需要變更。</span><span class="sxs-lookup"><span data-stu-id="cdac1-192">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="cdac1-193">根據您為標籤選取的來賓存取設定，使用者可以或無法將組織外部的人員新增至小組。</span><span class="sxs-lookup"><span data-stu-id="cdac1-193">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="cdac1-194">深入了解 Teams 的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="cdac1-194">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![建立新小組時的隱私權設定](media/privacy-setting-new-team.png)

<span data-ttu-id="cdac1-196">建立小組之後，敏感度標籤會顯示在所有頻道的右上角。</span><span class="sxs-lookup"><span data-stu-id="cdac1-196">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![敏感度標籤顯示在小組上](media/privacy-setting-teams.png)

<span data-ttu-id="cdac1-198">服務自動將相同的敏感度標籤套用至 Office 365 群組和連線的 SharePoint 小組網站。</span><span class="sxs-lookup"><span data-stu-id="cdac1-198">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="cdac1-199">將敏感度標籤套用至新的群組</span><span class="sxs-lookup"><span data-stu-id="cdac1-199">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="cdac1-200">在 Outlook 網頁版中，新的 [敏感度]\*\*\*\* 方塊含有已發佈的標籤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-200">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="cdac1-201">如果使用者需要更多資訊，可以按一下 [說明] 圖示來閱讀可用標籤和相關聯原則的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cdac1-201">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![建立群組並選取 [敏感度] 底下的選項](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="cdac1-203">將敏感度標籤套用至新的網站</span><span class="sxs-lookup"><span data-stu-id="cdac1-203">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="cdac1-204">系統管理員和使用者可以在者建立新式小組網站和通訊網站時選取敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-204">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

[<span data-ttu-id="cdac1-205">深入了解如何在新的 SharePoint 系統管理中心建立網站</span><span class="sxs-lookup"><span data-stu-id="cdac1-205">Learn how to create and delete SharePoint Online site collections in the SharePoint admin center.</span></span>](/sharepoint/create-site-collection)

<span data-ttu-id="cdac1-206">當使用者建立新式小組和通訊網站，預設會選取某個敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-206">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="cdac1-207">使用者可以選取 [說明] 圖示來深入了解標籤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-207">Users can select the help icon to learn more about the labels.</span></span>

![建立網站並選取 [敏感度] 底下的選項](media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="cdac1-209">當使用者瀏覽至網站，他們可以看到標籤的名稱和套用的原則。</span><span class="sxs-lookup"><span data-stu-id="cdac1-209">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![已套用敏感度標籤的網站](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="cdac1-211">在 SharePoint 系統管理中心管理敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="cdac1-211">Manage sites in the SharePoint admin center</span></span>

<span data-ttu-id="cdac1-212">若要檢視及編輯標籤，請使用新 SharePoint 系統管理中心的 [使用中網站] 頁面。</span><span class="sxs-lookup"><span data-stu-id="cdac1-212">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

![[使用中網站] 頁面上的 [敏感度] 欄](media/manage-site-sensitivity-labels.png)

<span data-ttu-id="cdac1-214">[深入了解在新的 SharePoint 系統管理中心管理網站](/sharepoint/manage-sites-in-new-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="cdac1-214">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="cdac1-215">變更標籤的網站和群組設定</span><span class="sxs-lookup"><span data-stu-id="cdac1-215">Change site and group settings for a label</span></span>

<span data-ttu-id="cdac1-216">最佳做法是，在將標籤套用至數個小組、群組或網站之後，不要變更設定。</span><span class="sxs-lookup"><span data-stu-id="cdac1-216">As a best practice, don't change settings after you've applied a label to several teams, groups, or sites.</span></span> <span data-ttu-id="cdac1-217">如果您必須進行變更，您必須使用 Azure AD PowerShell 指令碼來手動套用更新。</span><span class="sxs-lookup"><span data-stu-id="cdac1-217">If you must make a change, you need to use an Azure AD PowerShell script to manually apply updates.</span></span> <span data-ttu-id="cdac1-218">此方法可確保所有現有的小組、網站和群組強制執行新的設定。</span><span class="sxs-lookup"><span data-stu-id="cdac1-218">This method ensures that all existing teams, sites, and groups enforce the new setting.</span></span>

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="cdac1-219">支援新的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="cdac1-219">Support for the new sensitivity labels</span></span>

<span data-ttu-id="cdac1-220">下列應用程式和服務支援此預覽中的敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="cdac1-220">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="cdac1-221">Microsoft 365 合規性中心</span><span class="sxs-lookup"><span data-stu-id="cdac1-221">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="cdac1-222">SharePoint</span><span class="sxs-lookup"><span data-stu-id="cdac1-222">SharePoint</span></span>
- <span data-ttu-id="cdac1-223">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="cdac1-223">Outlook on the web</span></span>
- <span data-ttu-id="cdac1-224">Teams</span><span class="sxs-lookup"><span data-stu-id="cdac1-224">Teams</span></span>
- <span data-ttu-id="cdac1-225">SharePoint 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="cdac1-225">SharePoint admin center</span></span>
- <span data-ttu-id="cdac1-226">Azure AD 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="cdac1-226">Choose the link for the Azure AD admin center.</span></span>

<span data-ttu-id="cdac1-227">您無法使用下列應用程式和服務來建立具有新敏感度標籤的 Office 365 群組：</span><span class="sxs-lookup"><span data-stu-id="cdac1-227">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="cdac1-228">Mac 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="cdac1-228">Outlook for Mac</span></span>
- <span data-ttu-id="cdac1-229">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="cdac1-229">Outlook Mobile</span></span>  
- <span data-ttu-id="cdac1-230">適用於 Windows 的電腦版 Outlook</span><span class="sxs-lookup"><span data-stu-id="cdac1-230">Outlook for Windows</span></span>
- <span data-ttu-id="cdac1-231">Forms</span><span class="sxs-lookup"><span data-stu-id="cdac1-231">Forms</span></span>  
- <span data-ttu-id="cdac1-232">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="cdac1-232">Dynamics 365</span></span>  
- <span data-ttu-id="cdac1-233">Yammer</span><span class="sxs-lookup"><span data-stu-id="cdac1-233">Yammer</span></span>  
- <span data-ttu-id="cdac1-234">Stream</span><span class="sxs-lookup"><span data-stu-id="cdac1-234">Stream</span></span>  
- <span data-ttu-id="cdac1-235">Planner</span><span class="sxs-lookup"><span data-stu-id="cdac1-235">Planner</span></span>  
- <span data-ttu-id="cdac1-236">Project</span><span class="sxs-lookup"><span data-stu-id="cdac1-236">Project</span></span>  
- <span data-ttu-id="cdac1-237">PowerBI</span><span class="sxs-lookup"><span data-stu-id="cdac1-237">PowerBI</span></span>  
- <span data-ttu-id="cdac1-238">Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="cdac1-238">Microsoft Teams admin center</span></span>  
- <span data-ttu-id="cdac1-239">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="cdac1-239">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="cdac1-240">Exchange 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="cdac1-240">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="cdac1-241">如果您使用傳統 Azure AD 網站分類</span><span class="sxs-lookup"><span data-stu-id="cdac1-241">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="cdac1-242">啟用此預覽時，Office 365 不再對新群組和 SharePoint 網站支援舊分類。</span><span class="sxs-lookup"><span data-stu-id="cdac1-242">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="cdac1-243">不過，現有的群組和網站仍會顯示舊的分類，除非您轉換它們。</span><span class="sxs-lookup"><span data-stu-id="cdac1-243">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="cdac1-244">舊的類別包括您設定的「新式」網站分類，可能是透過 Azure AD PowerShell 或 PnP 核心程式庫所設定，其中定義了 `ClassificationList` 設定的值。</span><span class="sxs-lookup"><span data-stu-id="cdac1-244">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="cdac1-245">例如，在 PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="cdac1-245">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="cdac1-246">如需舊分類方法的詳細資訊，請參閱 [SharePoint「新式」網站分類](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)。</span><span class="sxs-lookup"><span data-stu-id="cdac1-246">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="cdac1-247">根據您目前的部署，您有兩種選項可以將舊分類轉換成新的分類。</span><span class="sxs-lookup"><span data-stu-id="cdac1-247">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="cdac1-248">如果您不曾對檔案和電子郵件使用敏感度標籤 (整合式 Microsoft 資訊保護標籤)</span><span class="sxs-lookup"><span data-stu-id="cdac1-248">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="cdac1-249">我們建議您：</span><span class="sxs-lookup"><span data-stu-id="cdac1-249">We recommend that you:</span></span>

1. <span data-ttu-id="cdac1-250">在 Microsoft 365 合規性中心建立與您的現有分類使用相同名稱的新敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-250">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="cdac1-251">使用 PowerShell，利用名稱對應將新標籤套用至現有的 Office 365 群組和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="cdac1-251">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="cdac1-252">刪除舊的分類。</span><span class="sxs-lookup"><span data-stu-id="cdac1-252">Delete the old classifications.</span></span>

<span data-ttu-id="cdac1-253">支援新敏感度標籤的應用程式和服務會顯示這些資料。</span><span class="sxs-lookup"><span data-stu-id="cdac1-253">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="cdac1-254">您可以使用新的標籤建立新的小組、群組和網站。</span><span class="sxs-lookup"><span data-stu-id="cdac1-254">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="cdac1-255">使用者仍可以從不支援新標籤的應用程式和服務建立群組。</span><span class="sxs-lookup"><span data-stu-id="cdac1-255">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="cdac1-256">不過，使用者無法套用標籤到這些群組。</span><span class="sxs-lookup"><span data-stu-id="cdac1-256">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="cdac1-257">使用 PowerShell 將新的敏感度標籤套用至這些群組。</span><span class="sxs-lookup"><span data-stu-id="cdac1-257">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="cdac1-258">您可以保留您的舊分類，不過，我們強烈建議使用 PowerShell 將新的敏感度標籤套用至這些群組。</span><span class="sxs-lookup"><span data-stu-id="cdac1-258">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="cdac1-259">支援新敏感度標籤的應用程式和服務即會使用新標籤建立。</span><span class="sxs-lookup"><span data-stu-id="cdac1-259">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="cdac1-260">當使用者從不支援新標籤的應用程式和服務建立群組時，他們可以選取分類。</span><span class="sxs-lookup"><span data-stu-id="cdac1-260">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="cdac1-261">如果您曾對檔案和電子郵件使用敏感度標籤 (整合式 Microsoft 資訊保護標籤)</span><span class="sxs-lookup"><span data-stu-id="cdac1-261">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="cdac1-262">一旦啟用此預覽，請移至 Microsoft 365 合規性中心中的每個標籤，並套用您要對網站和群組使用的原則。</span><span class="sxs-lookup"><span data-stu-id="cdac1-262">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="cdac1-263">使用者會開始看到您可供網站和群組使用的現有標籤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-263">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="cdac1-264">重新標記 Office 365 群組之前準備 SharePoint Online 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="cdac1-264">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="cdac1-265">套用新標籤之前，請確認您執行的是最新的 SharePoint Online 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="cdac1-265">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="cdac1-266">如果您已經有最新版本，您可以繼續並[使用新的敏感度標籤重新標記 Office 365 群組](#relabel-office-365-groups-with-new-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="cdac1-266">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="cdac1-267">若要為預覽準備 SharePoint Online 管理命令介面：</span><span class="sxs-lookup"><span data-stu-id="cdac1-267">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="cdac1-268">如果您安裝的是舊版 SharePoint Online 管理命令介面，請移至 [新增或移除程式]\*\*\*\*，並解除安裝 [SharePoint Online 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="cdac1-268">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell”.</span></span>

2. <span data-ttu-id="cdac1-269">在網頁瀏覽器中，移至下載中心頁面，並[下載最新的 SharePoint Online 管理命令介面](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="cdac1-269">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="cdac1-270">選取語言，然後按一下 [下載]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cdac1-270">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="cdac1-271">在 x64 和 x86 .msi 檔案之間選擇。</span><span class="sxs-lookup"><span data-stu-id="cdac1-271">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="cdac1-272">如果您執行的是 64 位元版本的 Windows，請下載 x64 檔案；或如果您執行的是 32 位元版本，請下載 x86 檔案。</span><span class="sxs-lookup"><span data-stu-id="cdac1-272">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you’re run the 32-bit version.</span></span> <span data-ttu-id="cdac1-273">如果您不知道，請參閱[我正在執行哪個版本的 Windows 作業系統？](https://support.microsoft.com/help/13443/windows-which-operating-system)。</span><span class="sxs-lookup"><span data-stu-id="cdac1-273">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="cdac1-274">下載檔案之後，請執行檔案，並遵循安裝精靈中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="cdac1-274">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="cdac1-275">使用新的敏感度標籤重新標記 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="cdac1-275">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="cdac1-276">請確認您使用的是最新版 SharePoint Online 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="cdac1-276">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="cdac1-277">如需相關指示，請參閱[重新標記 Office 365 群組之前準備 SharePoint Online 管理命令介面](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="cdac1-277">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="cdac1-278">使用擁有 Office 365 中的全域系統管理員或 SharePoint 系統管理員權限的公司或學校帳戶，連線到 SharePoint Online 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="cdac1-278">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="cdac1-279">若要了解如何進行，請參閱[開始使用 SharePoint Online 管理命令介面](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="cdac1-279">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="cdac1-280">執行下列命令來取得敏感度標籤及其 GUID 的清單。</span><span class="sxs-lookup"><span data-stu-id="cdac1-280">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="cdac1-281">記下您要覆寫之標籤的 GUID。</span><span class="sxs-lookup"><span data-stu-id="cdac1-281">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="cdac1-282">例如，「一般」標籤。</span><span class="sxs-lookup"><span data-stu-id="cdac1-282">For example, the "General" label.</span></span>

5. <span data-ttu-id="cdac1-283">使用下列命令來取得具有「一般」分類的群組清單。</span><span class="sxs-lookup"><span data-stu-id="cdac1-283">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="cdac1-284">執行此命令時，您會連線到 Exchange Online PowerShell，並執行 Get-UnifiedGroup Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cdac1-284">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="cdac1-285">針對每個群組，新增新的敏感度標籤 GUID。</span><span class="sxs-lookup"><span data-stu-id="cdac1-285">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
