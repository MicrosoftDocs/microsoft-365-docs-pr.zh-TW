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
description: 使用敏感度標籤來保護 SharePoint 和 Microsoft Teams 網站與 Office 365 群組中的內容。
ms.openlocfilehash: 69ab8dcecf95f02965254928110802bfd0308b8b
ms.sourcegitcommit: b8aa905b7c9c59def56490670b928b0b7daa7d0c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2020
ms.locfileid: "43558762"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="8c70c-103">使用敏感度標籤來保護 Microsoft Teams、Office 365 群組和 SharePoint 網站中的內容 (公開預覽)</span><span class="sxs-lookup"><span data-stu-id="8c70c-103">Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

><span data-ttu-id="8c70c-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="8c70c-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="8c70c-105">在 [Microsoft 365 合規性中心](https://protection.office.com/)中建立敏感度標籤時，您現在可以將這些標籤套用至下列容器：Microsoft Teams 網站、Office 365 群組和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="8c70c-105">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to the following containers: Microsoft Teams sites, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="8c70c-106">使用下列標籤設定來協助保護這些容器中的內容：</span><span class="sxs-lookup"><span data-stu-id="8c70c-106">Use the following label settings to help protect the content in those containers:</span></span>

- <span data-ttu-id="8c70c-107">Office 365 群組連線小組網站的隱私權 (公開或私人)</span><span class="sxs-lookup"><span data-stu-id="8c70c-107">Privacy (public or private) of Office 365 group-connected teams sites</span></span>
- <span data-ttu-id="8c70c-108">外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="8c70c-108">External users access</span></span>
- <span data-ttu-id="8c70c-109">從未受控裝置存取</span><span class="sxs-lookup"><span data-stu-id="8c70c-109">Access from unmanaged devices</span></span> 

<span data-ttu-id="8c70c-110">當您將此標籤套用至支援的容器時，標籤會自動將已設定的選項套用至連線的網站或群組。</span><span class="sxs-lookup"><span data-stu-id="8c70c-110">When you apply this label to a supported container, the label automatically applies the configured options to the connected site or group.</span></span> 

<span data-ttu-id="8c70c-111">不過，這些容器中的內容不會繼承標籤名稱、視覺標記或加密等設定的標籤。</span><span class="sxs-lookup"><span data-stu-id="8c70c-111">Content in those containers however, do not inherit the labels for settings such as the label name, visual markings, or encryption.</span></span> <span data-ttu-id="8c70c-112">因此，使用者可以為其在 SharePoint 網站或小組網站中的文件加上標籤，請[對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-112">So that users can label their documents in SharePoint sites or team sites, [enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="8c70c-113">關於 Microsoft Teams、Office 365 群組和 SharePoint 網站的公開預覽</span><span class="sxs-lookup"><span data-stu-id="8c70c-113">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="8c70c-114">Microsoft Teams、Office 365 群組和 SharePoint 網站的敏感度標籤會逐漸向租用戶推出，且可能在最終發行之前變更。</span><span class="sxs-lookup"><span data-stu-id="8c70c-114">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites are in gradual rollout to tenants and might change before final release.</span></span> <span data-ttu-id="8c70c-115">此公開預覽不適用 Office 365 內容傳遞網路 (CDN)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-115">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

<span data-ttu-id="8c70c-116">啟用此預覽並設定新設定的敏感度標籤前，使用者可在其應用程式中查看並套用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="8c70c-116">Before you enable this preview and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="8c70c-117">例如，在 Word 中：</span><span class="sxs-lookup"><span data-stu-id="8c70c-117">For example, from Word:</span></span>

![Word 傳統型應用程式中顯示的敏感度標籤](../media/sensitivity-label-word.png)

<span data-ttu-id="8c70c-119">啟用並設定此預覽後，使用者可進一步查看並將敏感度標籤套用至 Microsoft Teams、Office 365 群組和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="8c70c-119">After you enable and configure this preview, users can additionally see and apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="8c70c-120">例如，從 SharePoint 建立新的小組網站時：</span><span class="sxs-lookup"><span data-stu-id="8c70c-120">For example, when you create a new team site from SharePoint:</span></span>

![從 SharePoint 建立小組網站時的敏感度標籤](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a><span data-ttu-id="8c70c-122">啟用此預覽並同步處理標籤</span><span class="sxs-lookup"><span data-stu-id="8c70c-122">Enable this preview and synchronize labels</span></span>

1. <span data-ttu-id="8c70c-123">由於此功能使用 Azure AD 功能，請依照 Azure AD 文件中的指示來啟用預覽：[將敏感度標籤指派到 Azure Active Directory 中的 Office 365 群組 (預覽)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-123">Because this feature uses Azure AD functionality, follow the instructions in the Azure AD documentation to enable the preview: [Assign sensitivity labels to Office 365 groups in Azure Active Directory (preview)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="8c70c-124">現在[連線至 Office 365 安全性與合規性中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-124">Now [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="8c70c-125">例如，在您以系統管理員身分執行的 PowerShell 工作階段中，使用全域系統管理員帳戶登入：</span><span class="sxs-lookup"><span data-stu-id="8c70c-125">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

3. <span data-ttu-id="8c70c-126">執行下列命令以將您的敏感度標籤同步處理到 Azure AD，以便與 Office 365 群組搭配使用：</span><span class="sxs-lookup"><span data-stu-id="8c70c-126">Run the following command to synchronize your sensitivity labels to Azure AD, so that they can be used with Office 365 groups:</span></span>
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="8c70c-127">如何在建立或編輯敏感度標籤時設定網站和群組設定</span><span class="sxs-lookup"><span data-stu-id="8c70c-127">How to configure site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="8c70c-128">您現在可以建立或編輯需要用於網站和群組的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="8c70c-128">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="8c70c-129">啟用預覽可在敏感度標籤精靈中顯示新頁面：**網站和群組設定**</span><span class="sxs-lookup"><span data-stu-id="8c70c-129">Enabling the preview makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="8c70c-130">如果您需要建立或編輯敏感度標籤的協助，請參閱[建立及設定敏感度標籤](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)的指示。</span><span class="sxs-lookup"><span data-stu-id="8c70c-130">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="8c70c-131">在這個新的**網站和群組設定**頁面上，設定以下設定：</span><span class="sxs-lookup"><span data-stu-id="8c70c-131">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="8c70c-132">**Office 365 群組連線小組網站**：[無 - 讓使用者選擇誰可以存取網站]\*\*\*\* 的預設設定目前正在向租用戶推出。</span><span class="sxs-lookup"><span data-stu-id="8c70c-132">**Privacy of Office 365 group-connected teams sites**: The default setting of **None - let user chose who can access the site** is currently rolling out to tenants.</span></span> <span data-ttu-id="8c70c-133">如果您想要使用敏感度標籤來保護容器中的內容，但仍讓使用者自行設定隱私權設定，則請保留此預設設定。</span><span class="sxs-lookup"><span data-stu-id="8c70c-133">Keep this default setting when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.</span></span>
    
    <span data-ttu-id="8c70c-134">將此標籤套用至容器時，請選取 [公用]\*\*\*\* 或 [私人]\*\*\*\* 來設定和鎖定隱私權設定。</span><span class="sxs-lookup"><span data-stu-id="8c70c-134">Select **Public** or**Private** to set and lock the privacy setting when you apply this label to the container.</span></span> <span data-ttu-id="8c70c-135">如果您希望組織中的任何人都能存取已套用此標籤的小組網站或群組，請選擇 [公用]\*\*\*\*，如果您想要限制只有組織中已通過核准的成員才能存取，請選擇 [私人]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8c70c-135">Choose **Public** if you want anyone in your organization to access the team site or group where this label is applied, or **Private** if you want access to be restricted to only approved members in your organization.</span></span> 
    
    <span data-ttu-id="8c70c-136">[公用]\*\*\*\* 或 [私人]\*\*\*\* 設定會取代先前為小組或群組設定的任何隱私權設定，並鎖定隱私權值，以便只有先移除容器的敏感度標籤才能變更隱私權設定。</span><span class="sxs-lookup"><span data-stu-id="8c70c-136">The **Public** or **Private** setting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container.</span></span> <span data-ttu-id="8c70c-137">移除敏感度標籤後，標籤的隱私權設定會保留，使用者現在便可再次變更隱私權設定。</span><span class="sxs-lookup"><span data-stu-id="8c70c-137">After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span></span>

- <span data-ttu-id="8c70c-138">**外部使用者存取**：控制群組擁有者是否可以[將來賓新增至群組](/office365/admin/create-groups/manage-guest-access-in-groups)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-138">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="8c70c-139">**未受管理的裝置**：針對[未受管理的裝置](/sharepoint/control-access-from-unmanaged-devices)，允許完全存取、僅限 Web 存取，或完全封鎖存取權。</span><span class="sxs-lookup"><span data-stu-id="8c70c-139">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> 

![網站和群組設定索引標籤](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="8c70c-141">將標籤套用至小組、群組或網站時，只有這些網站和群組設定會生效。</span><span class="sxs-lookup"><span data-stu-id="8c70c-141">Only these site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="8c70c-142">其他標籤設定，例如加密和內容標記，均不會套用至小組、群組或網站內的內容。</span><span class="sxs-lookup"><span data-stu-id="8c70c-142">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="8c70c-143">逐漸向租用戶推出：使用者在建立小組、群組和網站時，只有具有網站和群組設定的標籤才可供選取。</span><span class="sxs-lookup"><span data-stu-id="8c70c-143">Gradually rolling out to tenants: Only labels with the site and group settings will be available to select when users create teams, groups, and sites.</span></span> <span data-ttu-id="8c70c-144">如果您目前可以在標籤未啟用網站和群組設定時將標籤套用至容器，則會套用至容器的只有標籤名稱。</span><span class="sxs-lookup"><span data-stu-id="8c70c-144">If you can currently apply a label to a container when the label doesn't have the site and group settings enabled, only the label name is applied to the container.</span></span>

<span data-ttu-id="8c70c-145">如果您的敏感度標籤尚未發佈，現在請[將標籤新增至敏感度標籤原則](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)以進行發佈。</span><span class="sxs-lookup"><span data-stu-id="8c70c-145">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="8c70c-146">包含此標籤、獲指派敏感度標籤原則的使用者將可以為網站和群組選取它。</span><span class="sxs-lookup"><span data-stu-id="8c70c-146">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

<span data-ttu-id="8c70c-147">當您將此標籤套用至容器時，則標籤原則中適用的原則設定只有 [預設將此標籤套用至文件和電子郵件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8c70c-147">From the label policy, only the policy setting **Apply this label by default to documents and email** is applicable when you apply this label to containers.</span></span> <span data-ttu-id="8c70c-148">其他原則設定則不會套用，這些設定包括強制標記、需要使用者理由以及用來自訂說明頁面的連結。</span><span class="sxs-lookup"><span data-stu-id="8c70c-148">Other policy settings are not applied, which include mandatory labeling, requiring user justification, and a link to the custom help page.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="8c70c-149">敏感度標籤管理</span><span class="sxs-lookup"><span data-stu-id="8c70c-149">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="8c70c-150">建立、修改和刪除您用於 Microsoft Teams、Office 365 群組和 SharePoint 網站的敏感度標籤時，需要謹慎地就發佈標籤原則給使用者進行協調。</span><span class="sxs-lookup"><span data-stu-id="8c70c-150">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Office 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="8c70c-151">使用下列指南來避免可能影響所有使用者的網站和群組建立錯誤。</span><span class="sxs-lookup"><span data-stu-id="8c70c-151">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="8c70c-152">**建立及發佈標籤：**</span><span class="sxs-lookup"><span data-stu-id="8c70c-152">**Creating and publishing labels:**</span></span>

<span data-ttu-id="8c70c-153">建立並發佈敏感度標籤後，最多可能需要 24 小時的時間，標籤才會對小組、群組和網站中的使用者顯示。</span><span class="sxs-lookup"><span data-stu-id="8c70c-153">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="8c70c-154">使用下列步驟為租用戶中的所有使用者發佈標籤：</span><span class="sxs-lookup"><span data-stu-id="8c70c-154">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="8c70c-155">建立敏感度標籤，並只對租用戶中的一些使用者帳戶發佈。</span><span class="sxs-lookup"><span data-stu-id="8c70c-155">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="8c70c-156">等候 24 小時。</span><span class="sxs-lookup"><span data-stu-id="8c70c-156">Wait for 24 hours.</span></span>

3. <span data-ttu-id="8c70c-157">等候 24 小時之後，使用您在步驟 1 中指定的其中一個使用者帳戶來建立小組、Office 365 群組或 SharePoint 網站，並搭配您在步驟 1 中建立的標籤。</span><span class="sxs-lookup"><span data-stu-id="8c70c-157">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Office 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="8c70c-158">如果在步驟 3 的建立作業期間沒有發生任何錯誤，請對您的租用戶中的所有使用者發佈標籤。</span><span class="sxs-lookup"><span data-stu-id="8c70c-158">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="8c70c-159">如果發生錯誤，請連絡 [Microsoft 支援](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-159">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="8c70c-160">**修改及刪除已發佈的標籤：**</span><span class="sxs-lookup"><span data-stu-id="8c70c-160">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="8c70c-161">如果您修改或刪除已啟用網站和群組設定的敏感度標籤，且該標籤包含在一或多個標籤原則中，這些動作可能會導致所有小組、群組和網站建立失敗。</span><span class="sxs-lookup"><span data-stu-id="8c70c-161">If you modify or delete a sensitivity label with the site and group settings enabled, and that label is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="8c70c-162">若要避免此情況，請使用下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="8c70c-162">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="8c70c-163">從包含標籤的所有標籤原則中移除敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="8c70c-163">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="8c70c-164">等候 48 小時。</span><span class="sxs-lookup"><span data-stu-id="8c70c-164">Wait for 48 hours.</span></span>

3. <span data-ttu-id="8c70c-165">在等候 48 小時之後，請嘗試建立小組、群組或網站，並確認標籤已不再顯示。</span><span class="sxs-lookup"><span data-stu-id="8c70c-165">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="8c70c-166">如果敏感度標籤未顯示，您現在可以放心地修改或刪除標籤。</span><span class="sxs-lookup"><span data-stu-id="8c70c-166">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="8c70c-167">如果標籤仍顯示，請連絡 [Microsoft 支援](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-167">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="assign-sensitivity-labels-to-office-365-groups"></a><span data-ttu-id="8c70c-168">將敏感度標籤指派給 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="8c70c-168">Assign sensitivity labels to Office 365 groups</span></span>

<span data-ttu-id="8c70c-169">您現在可以將敏感度標籤或標籤套用至 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="8c70c-169">You're now ready to apply the sensitivity label or labels to Office 365 groups.</span></span> <span data-ttu-id="8c70c-170">如需指示，請返回 Azure AD 文件：</span><span class="sxs-lookup"><span data-stu-id="8c70c-170">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="8c70c-171">在 Azure 入口網站中將標籤指派至新群組</span><span class="sxs-lookup"><span data-stu-id="8c70c-171">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [<span data-ttu-id="8c70c-172">在 Azure 入口網站中將標籤指派至現有群組</span><span class="sxs-lookup"><span data-stu-id="8c70c-172">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="8c70c-173">[在 Azure 入口網站中將標籤從現有群組移除](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-173">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="8c70c-174">將敏感度標籤套用至新的小組</span><span class="sxs-lookup"><span data-stu-id="8c70c-174">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="8c70c-175">當使用者在 Microsoft Teams 中建立新小組時，可選取敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="8c70c-175">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="8c70c-176">當使用者從 [敏感度]\*\*\*\* 下拉式功能表中選取標籤時，隱私權設定可能會變更以反映標籤設定。</span><span class="sxs-lookup"><span data-stu-id="8c70c-176">When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration.</span></span> <span data-ttu-id="8c70c-177">根據您為標籤選取的外部使用者存取設定，使用者可以或無法將組織外部的人員新增至小組。</span><span class="sxs-lookup"><span data-stu-id="8c70c-177">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="8c70c-178">深入了解 Teams 的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="8c70c-178">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![建立新小組時的隱私權設定](../media/privacy-setting-new-team.png)

<span data-ttu-id="8c70c-180">建立小組之後，敏感度標籤會顯示在所有頻道的右上角。</span><span class="sxs-lookup"><span data-stu-id="8c70c-180">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![敏感度標籤顯示在小組上](../media/privacy-setting-teams.png)

<span data-ttu-id="8c70c-182">服務自動將相同的敏感度標籤套用至 Office 365 群組和連線的 SharePoint 小組網站。</span><span class="sxs-lookup"><span data-stu-id="8c70c-182">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="8c70c-183">在 Outlook 網頁版中將敏感度標籤套用至新的群組</span><span class="sxs-lookup"><span data-stu-id="8c70c-183">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="8c70c-184">在 Outlook 網頁版中，當您建立新的群組時，您可以選取或變更已發佈標籤的**敏感度**選項：</span><span class="sxs-lookup"><span data-stu-id="8c70c-184">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![建立群組並選取 [敏感度] 底下的選項](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="8c70c-186">將敏感度標籤套用至新的網站</span><span class="sxs-lookup"><span data-stu-id="8c70c-186">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="8c70c-187">系統管理員和使用者可以在[建立新式小組網站和通訊網站](/sharepoint/create-site-collection)時選取敏感度標籤，然後展開 [進階設定]\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="8c70c-187">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection), and expand **Advanced settings**:</span></span>

![建立網站並選取 [敏感度] 底下的選項](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="8c70c-189">下拉式方塊會顯示所選項目的標籤名稱，[說明] 圖示則會顯示所有標籤名稱及其工具提示，以協助使用者判斷所要套用的正確標籤。</span><span class="sxs-lookup"><span data-stu-id="8c70c-189">The dropdown box displays the label names for the selection, and the help icon displays all the label names with their tooltip, which can help users determine the correct label to apply.</span></span>

<span data-ttu-id="8c70c-190">當標籤已套用，且使用者瀏覽至網站時，其便可看到標籤的名稱和所套用的原則。</span><span class="sxs-lookup"><span data-stu-id="8c70c-190">When the label is applied, and users browse to the site, they see the name of the label and applied policies.</span></span> <span data-ttu-id="8c70c-191">例如，此網站已加上 [機密]\*\*\*\* 標籤，且隱私權設定設為 [私人]\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="8c70c-191">For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span></span>

![已套用敏感度標籤的網站](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="8c70c-193">在 SharePoint 系統管理中心檢視敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="8c70c-193">View sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="8c70c-194">若要檢視套用的敏感度標籤，請使用新 SharePoint 系統管理中心的 **[使用中網站]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="8c70c-194">To view the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="8c70c-195">您可能需要先新增 **[敏感度]** 欄：</span><span class="sxs-lookup"><span data-stu-id="8c70c-195">You might need to first add the **Sensitivity** column:</span></span>

![[使用中網站] 頁面上的 [敏感度] 欄](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="8c70c-197">[深入了解在新的 SharePoint 系統管理中心管理網站](/sharepoint/manage-sites-in-new-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-197">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="8c70c-198">變更標籤的網站和群組設定</span><span class="sxs-lookup"><span data-stu-id="8c70c-198">Change site and group settings for a label</span></span>

<span data-ttu-id="8c70c-199">每當您變更標籤的網站和群組設定時，您必須執行下列 PowerShell 命令，以便您的小組、網站和群組可以使用新的設定。</span><span class="sxs-lookup"><span data-stu-id="8c70c-199">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="8c70c-200">最佳做法是，不要在將敏感度標籤套用至數個小組、群組或網站之後，變更該標籤的網站和群組設定。</span><span class="sxs-lookup"><span data-stu-id="8c70c-200">As a best practice, don't the change site and group settings for a label after you've applied the sensitivity label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="8c70c-201">第一，[連接到 Office 365 安全性與合規性中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-201">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="8c70c-202">例如，在您以系統管理員身分執行的 PowerShell 工作階段中，使用全域系統管理員帳戶登入：</span><span class="sxs-lookup"><span data-stu-id="8c70c-202">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="8c70c-203">透過使用 [Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps) Cmdlet，取得敏感度標籤和其 GUID 的清單：</span><span class="sxs-lookup"><span data-stu-id="8c70c-203">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps) cmdlet:</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. <span data-ttu-id="8c70c-204">記下您已變更之標籤的 GUID。</span><span class="sxs-lookup"><span data-stu-id="8c70c-204">Make a note of the GUID for the label or labels you have changed.</span></span>

4. <span data-ttu-id="8c70c-205">現在[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-205">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
    <span data-ttu-id="8c70c-206">例如：</span><span class="sxs-lookup"><span data-stu-id="8c70c-206">For example:</span></span>
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```
    
5. <span data-ttu-id="8c70c-207">執行 [Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps) Cmdlet，指定您的標籤 GUID 來取代範例 GUID "e48058ea-98e8-4940-8db0-ba1310fd955e"：</span><span class="sxs-lookup"><span data-stu-id="8c70c-207">Run the [Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps) cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

6. <span data-ttu-id="8c70c-208">針對每個群組，重新套用敏感度標籤，然後指定您的標籤 GUID 來取代 "e48058ea-98e8-4940-8db0-ba1310fd955e" 的 GUID 範例：</span><span class="sxs-lookup"><span data-stu-id="8c70c-208">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a><span data-ttu-id="8c70c-209">支援敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="8c70c-209">Support for the sensitivity labels</span></span>

<span data-ttu-id="8c70c-210">您可以搭配下列應用程式和服務，使用您為網站和群組設定套用的敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="8c70c-210">You can use the sensitivity labels that you've configured for site and group settings with the following apps and services:</span></span>

- <span data-ttu-id="8c70c-211">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8c70c-211">SharePoint Online</span></span>
- <span data-ttu-id="8c70c-212">Teams</span><span class="sxs-lookup"><span data-stu-id="8c70c-212">Teams</span></span>
- <span data-ttu-id="8c70c-213">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="8c70c-213">Outlook on the web</span></span>
- <span data-ttu-id="8c70c-214">SharePoint 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="8c70c-214">SharePoint admin center</span></span>
- <span data-ttu-id="8c70c-215">Azure AD 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="8c70c-215">Azure AD admin center</span></span>

<span data-ttu-id="8c70c-216">目前無法使用您為網站和群組設定套用的敏感度標籤的其他應用程式和服務包括：</span><span class="sxs-lookup"><span data-stu-id="8c70c-216">Other apps and services that you can't currently use the sensitivity labels that you've configured for site and group settings include:</span></span>

- <span data-ttu-id="8c70c-217">Mac 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="8c70c-217">Outlook for the Mac</span></span>
- <span data-ttu-id="8c70c-218">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="8c70c-218">Outlook mobile</span></span>
- <span data-ttu-id="8c70c-219">適用於 Windows 的電腦版 Outlook</span><span class="sxs-lookup"><span data-stu-id="8c70c-219">Outlook desktop for Windows</span></span>
- <span data-ttu-id="8c70c-220">Forms</span><span class="sxs-lookup"><span data-stu-id="8c70c-220">Forms</span></span>
- <span data-ttu-id="8c70c-221">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8c70c-221">Dynamics 365</span></span>
- <span data-ttu-id="8c70c-222">Yammer</span><span class="sxs-lookup"><span data-stu-id="8c70c-222">Yammer</span></span>
- <span data-ttu-id="8c70c-223">Stream</span><span class="sxs-lookup"><span data-stu-id="8c70c-223">Stream</span></span>
- <span data-ttu-id="8c70c-224">Planner</span><span class="sxs-lookup"><span data-stu-id="8c70c-224">Planner</span></span>
- <span data-ttu-id="8c70c-225">Project</span><span class="sxs-lookup"><span data-stu-id="8c70c-225">Project</span></span>
- <span data-ttu-id="8c70c-226">PowerBI</span><span class="sxs-lookup"><span data-stu-id="8c70c-226">PowerBI</span></span>
- <span data-ttu-id="8c70c-227">Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="8c70c-227">Teams admin center</span></span>
- <span data-ttu-id="8c70c-228">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="8c70c-228">Microsoft 365 admin center</span></span>
- <span data-ttu-id="8c70c-229">Exchange 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="8c70c-229">Exchange admin center</span></span>


## <a name="classic-azure-ad-group-classification"></a><span data-ttu-id="8c70c-230">傳統 Azure AD 群組分類</span><span class="sxs-lookup"><span data-stu-id="8c70c-230">Classic Azure AD group classification</span></span>

<span data-ttu-id="8c70c-231">啟用此預覽時，Office 365 不再對新 Office 365 群組和 SharePoint 網站支援舊分類。</span><span class="sxs-lookup"><span data-stu-id="8c70c-231">Office 365 no longer supports the old classifications for new Office 365 groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="8c70c-232">不過，現有的群組和網站仍會顯示舊的分類值，除非您轉換它們以使用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="8c70c-232">However, existing groups and sites still display the old classification values unless you convert them to use sensitivity labels.</span></span>

<span data-ttu-id="8c70c-233">如需您先前可能使用的 SharePoint 舊群組分類範例，請參閱 [SharePoint 「新式」網站分類](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-233">As an example of how you might have used the old group classification for SharePoint, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="8c70c-234">這些分類是使用 Azure AD PowerShell 或 PnP 核心程式庫來設定，並定義 `ClassificationList` 設定的值。</span><span class="sxs-lookup"><span data-stu-id="8c70c-234">These classifications were configured by using Azure AD PowerShell or the PnP Core library and defining values for the `ClassificationList` setting.</span></span> <span data-ttu-id="8c70c-235">如果您的租用戶已定義分類值，當您從 [AzureADPreview PowerShell 模組](https://www.powershellgallery.com/packages/AzureADPreview)執行下列命令時，會顯示這些值：</span><span class="sxs-lookup"><span data-stu-id="8c70c-235">If your tenant has classification values defined, they are shown when you run the following command from the [AzureADPreview PowerShell module](https://www.powershellgallery.com/packages/AzureADPreview):</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="8c70c-236">若要將舊分類轉換成敏感度標籤，請執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-236">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="8c70c-237">使用現有的標籤：編輯已發佈的現有敏感度標籤，以指定網站和群組需要的標籤設定。</span><span class="sxs-lookup"><span data-stu-id="8c70c-237">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="8c70c-238">建立新標籤：建立及發佈與現有分類名稱相同的新敏感度標籤，以指定網站和群組需要的標籤設定。</span><span class="sxs-lookup"><span data-stu-id="8c70c-238">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="8c70c-239">然後：</span><span class="sxs-lookup"><span data-stu-id="8c70c-239">Then:</span></span> 

1. <span data-ttu-id="8c70c-240">使用 PowerShell，利用名稱對應將敏感度標籤套用至現有的 Office 365 群組和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="8c70c-240">Use PowerShell to apply the sensitivity labels to existing Office 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="8c70c-241">請參閱下一節的指示。</span><span class="sxs-lookup"><span data-stu-id="8c70c-241">See the next section for instructions.</span></span>

2. <span data-ttu-id="8c70c-242">移除現有群組和網站的舊分類。</span><span class="sxs-lookup"><span data-stu-id="8c70c-242">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="8c70c-243">雖然您無法防止使用者在尚未支援敏感度標籤的應用程式和服務中建立新群組，但您可以執行週期性 PowerShell 指令碼來尋找使用者使用舊分類建立的新群組，並將它們轉換成使用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="8c70c-243">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

#### <a name="use-powershell-to-convert-classifications-for-office-365-groups-to-sensitivity-labels"></a><span data-ttu-id="8c70c-244">使用 PowerShell 將 Office 365 群組的分類轉換成敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="8c70c-244">Use PowerShell to convert classifications for Office 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="8c70c-245">第一，[連接到 Office 365 安全性與合規性中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-245">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="8c70c-246">例如，在您以系統管理員身分執行的 PowerShell 工作階段中，使用全域系統管理員帳戶登入：</span><span class="sxs-lookup"><span data-stu-id="8c70c-246">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="8c70c-247">透過使用 [Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps) Cmdlet，取得敏感度標籤和其 GUID 的清單：</span><span class="sxs-lookup"><span data-stu-id="8c70c-247">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-label?view=exchange-ps) cmdlet:</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. <span data-ttu-id="8c70c-248">記下您要套用至 Office 365 群組的敏感度標籤 GUID。</span><span class="sxs-lookup"><span data-stu-id="8c70c-248">Make a note of the GUIDs for the sensitivity labels you want to apply to your Office 365 groups.</span></span>

4. <span data-ttu-id="8c70c-249">現在[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-249">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
    <span data-ttu-id="8c70c-250">例如：</span><span class="sxs-lookup"><span data-stu-id="8c70c-250">For example:</span></span>
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```

5. <span data-ttu-id="8c70c-251">執行 [Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps) Cmdlet，取得擁有您指定分類之一的 Office 365 群組清單。</span><span class="sxs-lookup"><span data-stu-id="8c70c-251">Run the [Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps) cmdlet to get the list of Office 365 groups that have one of the classifications you've specified.</span></span>
    
    <span data-ttu-id="8c70c-252">例如，若要取得具有「General」分類的 Office 365 群組清單：</span><span class="sxs-lookup"><span data-stu-id="8c70c-252">For example, to get a list of Office 365 groups that have the classification of "General":</span></span> 
    
    ```powershell
    $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
    ```

6. <span data-ttu-id="8c70c-253">針對每個群組，新增新的敏感度標籤 GUID。</span><span class="sxs-lookup"><span data-stu-id="8c70c-253">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="8c70c-254">例如：</span><span class="sxs-lookup"><span data-stu-id="8c70c-254">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. <span data-ttu-id="8c70c-255">針對其餘的群組分類重複步驟 5 和 6。</span><span class="sxs-lookup"><span data-stu-id="8c70c-255">Repeat steps 5 and 6 for your remaining group classifications.</span></span>

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="8c70c-256">稽核敏感度標籤活動</span><span class="sxs-lookup"><span data-stu-id="8c70c-256">Auditing sensitivity label activities</span></span>

<span data-ttu-id="8c70c-257">若某使用者將文件上傳到受敏感度標籤保護的網站，且文件的敏感度標籤[優先於](sensitivity-labels.md#label-priority-order-matters)網站的敏感度標籤，則不會封鎖此動作。</span><span class="sxs-lookup"><span data-stu-id="8c70c-257">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="8c70c-258">例如，您已將**一般**標籤套用至 SharePoint 網站，而某使用者上傳到此網站的文件標示為**機密**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-258">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="8c70c-259">由於優先順序較高的敏感度標籤會識別比優先順序較低的內容更具敏感度的內容，因此可能會造成安全性問題。</span><span class="sxs-lookup"><span data-stu-id="8c70c-259">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="8c70c-260">儘管動作並未遭到封鎖，但會受到稽核，因此您可以找出與標籤優先順序不一致的文件，並視需要採取行動。</span><span class="sxs-lookup"><span data-stu-id="8c70c-260">Although the action isn't blocked, it is audited, so you can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="8c70c-261">例如，從網站刪除或移動已上傳的文件。</span><span class="sxs-lookup"><span data-stu-id="8c70c-261">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="8c70c-262">如果文件套用的敏感度標籤，其優先順序低於網站所套用的敏感度標籤，則不會造成安全性問題。</span><span class="sxs-lookup"><span data-stu-id="8c70c-262">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="8c70c-263">例如，套用 **「一般」** 標籤的文件上傳到標記為 **「機密」** 的網站。</span><span class="sxs-lookup"><span data-stu-id="8c70c-263">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="8c70c-264">在此案例中，不會產生稽核事件。</span><span class="sxs-lookup"><span data-stu-id="8c70c-264">In this scenario, an auditing event isn't generated.</span></span>

<span data-ttu-id="8c70c-265">若要搜尋此事件的稽核記錄，請尋找 **[檔案與頁面活動]** 類別中的 **[偵測到的文件敏感度不相符]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-265">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="8c70c-266">當某使用者在網站或群組中新增或移除敏感度標籤時，這些活動也會受到稽核。</span><span class="sxs-lookup"><span data-stu-id="8c70c-266">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited.</span></span> <span data-ttu-id="8c70c-267">您可以在 [[敏感度標籤活動]](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) 類別中找到這些事件。</span><span class="sxs-lookup"><span data-stu-id="8c70c-267">These events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> 

<span data-ttu-id="8c70c-268">如需搜尋稽核記錄的指示，請參閱[在安全性與合規性中心搜尋稽核記錄](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-268">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="8c70c-269">疑難排解敏感度標籤部署</span><span class="sxs-lookup"><span data-stu-id="8c70c-269">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="8c70c-270">在使用 Microsoft Teams、Office 365 群組和 SharePoint 網站的敏感度標籤時遇到問題嗎？</span><span class="sxs-lookup"><span data-stu-id="8c70c-270">Having problems with sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites?</span></span> <span data-ttu-id="8c70c-271">請檢查下列項目：</span><span class="sxs-lookup"><span data-stu-id="8c70c-271">Check the following:</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="8c70c-272">發佈之後標籤無法顯示</span><span class="sxs-lookup"><span data-stu-id="8c70c-272">Labels not visible after publishing</span></span>
<span data-ttu-id="8c70c-273">如果您在啟用這些設定或修改敏感度標籤的名稱和工具提示後，於建立網站或 Office 365 群組時遇到問題，請先儲存標籤變更並等候幾小時，然後再嘗試重新建立小組或群組。</span><span class="sxs-lookup"><span data-stu-id="8c70c-273">If you experience issues when you create a site or Office 365 group after you enable these settings or modify a sensitivity label's name or tooltip, wait a few hours after saving the label changes, and then try to create the team or group again.</span></span> <span data-ttu-id="8c70c-274">如需詳細資訊，請參閱[排程在建立或變更敏感度標籤後推出](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-274">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="8c70c-275">如果您仍看不到來自 SharePoint Online 的新敏感度標籤，請連絡 [Microsoft 支援](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-275">If you still can't see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="8c70c-276">小組、群組或 SharePoint 網站建立錯誤</span><span class="sxs-lookup"><span data-stu-id="8c70c-276">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="8c70c-277">如果您在公開預覽期間遇到建立錯誤，則可以使用來自[啟用 PowerShell 中的敏感度標籤支援](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell)中的相同指示來關閉 Microsoft Teams、Office 365 群組和 SharePoint 網站的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="8c70c-277">If you experience creation errors during the public preview, you can turn off sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="8c70c-278">不過，若要停用預覽，請在步驟 5 中使用 `$setting["EnableMIPLabels"] = "False"` 來停用此功能。</span><span class="sxs-lookup"><span data-stu-id="8c70c-278">However, to disable the preview, in step 5, disable the feature by using `$setting["EnableMIPLabels"] = "False"`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8c70c-279">其他資源</span><span class="sxs-lookup"><span data-stu-id="8c70c-279">Additional resources</span></span>

<span data-ttu-id="8c70c-280">如需有關[透過 Microsoft Teams、O365 群組和 SharePoint Online 網站使用敏感度標籤](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380) (英文) 的資訊，請參閱網路研討會的記錄和回答的問題。</span><span class="sxs-lookup"><span data-stu-id="8c70c-280">See the webinar recording and answered questions for [Using Sensitivity labels with Microsoft Teams, O365 Groups and SharePoint Online sites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span></span>

