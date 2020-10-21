---
title: 對 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站使用敏感度標籤
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
description: 使用敏感度標籤來保護 SharePoint 和 Microsoft Teams 網站與 Microsoft 365 群組中的內容。
ms.openlocfilehash: 7f8337d368c5c9de7cf1d9ff90831777c0811b87
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600468"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="72732-103">使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容</span><span class="sxs-lookup"><span data-stu-id="72732-103">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

><span data-ttu-id="72732-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="72732-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="72732-p101">In addition to using [sensitivity labels](sensitivity-labels.md) to classify and protect documents and emails, you can also use sensitivity labels to protect content in the following containers: Microsoft Teams sites, Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), and SharePoint sites. For this container-level classification and protection, use the following label settings:</span><span class="sxs-lookup"><span data-stu-id="72732-p101">In addition to using [sensitivity labels](sensitivity-labels.md) to classify and protect documents and emails, you can also use sensitivity labels to protect content in the following containers: Microsoft Teams sites, Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), and SharePoint sites. For this container-level classification and protection, use the following label settings:</span></span>

- <span data-ttu-id="72732-107">Teams 網站和 Microsoft 365 群組的隱私權 (公用或私人)</span><span class="sxs-lookup"><span data-stu-id="72732-107">Privacy (public or private) of teams sites and Microsoft 365 groups</span></span>
- <span data-ttu-id="72732-108">外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="72732-108">External user access</span></span>
- <span data-ttu-id="72732-109">從未受管理的裝置存取</span><span class="sxs-lookup"><span data-stu-id="72732-109">Access from unmanaged devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72732-p102">The **Access from unmanaged devices** setting works in conjunction with the SharePoint feature to [control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices). You must configure this dependent SharePoint feature to use a sensitivity label that has this setting configured. Additional information is included in the instructions that follow.</span><span class="sxs-lookup"><span data-stu-id="72732-p102">The **Access from unmanaged devices** setting works in conjunction with the SharePoint feature to [control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices). You must configure this dependent SharePoint feature to use a sensitivity label that has this setting configured. Additional information is included in the instructions that follow.</span></span>

<span data-ttu-id="72732-113">當您將此敏感度標籤套用至支援的容器時，標籤會自動將分類和設定的保護設定套用至網站或群組。</span><span class="sxs-lookup"><span data-stu-id="72732-113">When you apply this sensitivity label to a supported container, the label automatically applies the classification and configured protection settings to the site or group.</span></span>

<span data-ttu-id="72732-p103">Content in these containers however, do not inherit the labels for the classification or settings for files and emails, such as visual markings and encryption. So that users can label their documents in SharePoint sites or team sites, make sure you've [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="72732-p103">Content in these containers however, do not inherit the labels for the classification or settings for files and emails, such as visual markings and encryption. So that users can label their documents in SharePoint sites or team sites, make sure you've [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

> [!NOTE]
> <span data-ttu-id="72732-116">容器的敏感度標籤不支援使用 Office 365 內容傳遞網路 (CDN)。</span><span class="sxs-lookup"><span data-stu-id="72732-116">Sensitivity labels for containers aren't supported with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="using-sensitivity-labels-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="72732-117">在對 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站使用敏感度標籤時遇到問題嗎？</span><span class="sxs-lookup"><span data-stu-id="72732-117">Using sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="72732-p104">Before you enable sensitivity labels for containers and configure sensitivity labels for the new settings, users could see and apply sensitivity labels in their apps. For example, from Word:</span><span class="sxs-lookup"><span data-stu-id="72732-p104">Before you enable sensitivity labels for containers and configure sensitivity labels for the new settings, users could see and apply sensitivity labels in their apps. For example, from Word:</span></span>

![Word 傳統型應用程式中顯示的敏感度標籤](../media/sensitivity-label-word.png)

<span data-ttu-id="72732-p105">After you enable and configure sensitivity labels for containers, users can additionally see and apply sensitivity labels to Microsoft team sites, Microsoft 365 groups, and SharePoint sites. For example, when you create a new team site from SharePoint:</span><span class="sxs-lookup"><span data-stu-id="72732-p105">After you enable and configure sensitivity labels for containers, users can additionally see and apply sensitivity labels to Microsoft team sites, Microsoft 365 groups, and SharePoint sites. For example, when you create a new team site from SharePoint:</span></span>

![從 SharePoint 建立小組網站時的敏感度標籤](../media/sensitivity-labels-new-team-site.png)

## <a name="how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels"></a><span data-ttu-id="72732-124">如何為容器啟用敏感度標籤以及同步處理標籤</span><span class="sxs-lookup"><span data-stu-id="72732-124">How to enable sensitivity labels for containers and synchronize labels</span></span>

1. <span data-ttu-id="72732-125">由於此功能使用 Azure AD 功能，請依照 Azure AD 文件中的指示來啟用敏感度標籤支援：[將敏感度標籤指派到 Azure Active Directory 中的 Microsoft 365 群組](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="72732-125">Because this feature uses Azure AD functionality, follow the instructions from the Azure AD documentation to enable sensitivity label support: [Assign sensitivity labels to Microsoft 365 groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="72732-p106">You now need to synchronize your sensitivity labels to Azure AD. First, [connect to Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="72732-p106">You now need to synchronize your sensitivity labels to Azure AD. First, [connect to Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="72732-128">例如，在您以系統管理員身分執行的 PowerShell 工作階段中，使用全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="72732-128">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account.</span></span>

3. <span data-ttu-id="72732-129">然後執行下列命令，以確保您的敏感度標籤可以搭配 Microsoft 365 群組使用：</span><span class="sxs-lookup"><span data-stu-id="72732-129">Then run the following command to ensure your sensitivity labels can be used with Microsoft 365 groups:</span></span>

    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-groups-and-site-settings"></a><span data-ttu-id="72732-130">如何設定群組和網站設定</span><span class="sxs-lookup"><span data-stu-id="72732-130">How to configure groups and site settings</span></span>

<span data-ttu-id="72732-p107">Enabling sensitivity labels for containers means that you can now configure protection settings for groups and sites in the sensitivity labeling wizard. Until you enable this support, the settings are visible in the wizard but you can't configure them.</span><span class="sxs-lookup"><span data-stu-id="72732-p107">Enabling sensitivity labels for containers means that you can now configure protection settings for groups and sites in the sensitivity labeling wizard. Until you enable this support, the settings are visible in the wizard but you can't configure them.</span></span>

1. <span data-ttu-id="72732-133">遵循一般指示以[建立或編輯敏感度標籤](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)，並確認已針對標籤的範圍選取 **[群組和網站]**：</span><span class="sxs-lookup"><span data-stu-id="72732-133">Follow the general instructions to [create or edit a sensitivity label](create-sensitivity-labels.md#create-and-configure-sensitivity-labels) and make sure you select **Groups & sites** for the label's scope:</span></span> 
    
    ![檔案和電子郵件的敏感度標籤範圍選項](../media/groupsandsites-scope-options-sensitivity-label.png)
    
    <span data-ttu-id="72732-p108">When only this scope is selected for the label, the label won't be displayed in Office apps that support sensitivity labels and can't be applied to files and emails. Having this separation of labels can be helpful for both users and administrators, but can also add to the complexity of your label deployment.</span><span class="sxs-lookup"><span data-stu-id="72732-p108">When only this scope is selected for the label, the label won't be displayed in Office apps that support sensitivity labels and can't be applied to files and emails. Having this separation of labels can be helpful for both users and administrators, but can also add to the complexity of your label deployment.</span></span>
    
    <span data-ttu-id="72732-p109">For example, you need to carefully review your [label ordering](sensitivity-labels.md#label-priority-order-matters) because SharePoint detects when a labeled document is uploaded to a labeled site. In this sceanrio, an audit event and email is automatically generated when the document has a higher priority sensitivity label than the site's label. For more information, see the [Auditing sensitivity label activities](#auditing-sensitivity-label-activities) section on this page.</span><span class="sxs-lookup"><span data-stu-id="72732-p109">For example, you need to carefully review your [label ordering](sensitivity-labels.md#label-priority-order-matters) because SharePoint detects when a labeled document is uploaded to a labeled site. In this sceanrio, an audit event and email is automatically generated when the document has a higher priority sensitivity label than the site's label. For more information, see the [Auditing sensitivity label activities](#auditing-sensitivity-label-activities) section on this page.</span></span> 

2. <span data-ttu-id="72732-140">然後，在 **定義群組和網站的保護設定** 頁面上，選取其中一個或兩個皆適用的可用選項：</span><span class="sxs-lookup"><span data-stu-id="72732-140">Then, on the **Define protection settings for groups and sites** page, select one or both of the available options:</span></span>
    
    - <span data-ttu-id="72732-141">**隱私權和外部使用者存取設定**可設定 **[隱私權]** 和 **[外部使用者存取]** 設定。</span><span class="sxs-lookup"><span data-stu-id="72732-141">**Privacy and external user access settings** to configure the **Privacy** and **External users access** settings.</span></span> 
    - <span data-ttu-id="72732-142">**裝置存取和外部共用設定** 設定 **從未受管理的裝置存取** 的設定。</span><span class="sxs-lookup"><span data-stu-id="72732-142">**Device access and external sharing settings** to configure the **Access from unmanaged devices** setting.</span></span>

3. <span data-ttu-id="72732-143">如果您已選取 **[隱私權與外部使用者存取設定]**，請設置下列設定：</span><span class="sxs-lookup"><span data-stu-id="72732-143">If you selected **Privacy and external user access settings**, now configure the following settings:</span></span>
    
    - <span data-ttu-id="72732-144">**隱私權**：如果您希望組織中的所有人都能存取套用此標籤的小組網站或群組，請保留 **公用** 的預設值。</span><span class="sxs-lookup"><span data-stu-id="72732-144">**Privacy**: Keep the default of **Public** if you want anyone in your organization to access the team site or group where this label is applied.</span></span>
        
        <span data-ttu-id="72732-145">如果您希望僅限組織中經核准的成員能存取，請選取 **[私人]**。</span><span class="sxs-lookup"><span data-stu-id="72732-145">Select **Private** if you want access to be restricted to only approved members in your organization.</span></span>
        
        <span data-ttu-id="72732-146">如果您想要使用敏感度標籤來保護容器中的內容，但仍讓使用者自行設定隱私權設定，則選取 **[無]**。</span><span class="sxs-lookup"><span data-stu-id="72732-146">Select **None** when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.</span></span>
        
        <span data-ttu-id="72732-p110">The settings of **Public** or **Private** set and lock the privacy setting when you apply this label to the container. Your chosen setting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container. After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span><span class="sxs-lookup"><span data-stu-id="72732-p110">The settings of **Public** or **Private** set and lock the privacy setting when you apply this label to the container. Your chosen setting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container. After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span></span>
    
    - <span data-ttu-id="72732-150">**外部使用者存取**：控制群組擁有者是否可以[將來賓新增至群組](/office365/admin/create-groups/manage-guest-access-in-groups)。</span><span class="sxs-lookup"><span data-stu-id="72732-150">**External user access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

4. <span data-ttu-id="72732-151">如果您已選取 **[裝置存取與外部使用者共用設定]**，請設置下列設定：</span><span class="sxs-lookup"><span data-stu-id="72732-151">If you selected **Device access and external sharing setting**, now configure the following setting:</span></span>
    
    - <span data-ttu-id="72732-p111">**從未受管理的裝置存取**：此選項透過使用 Azure AD 條件式存取的 SharePoint 功能，以封鎖或限制從未受管理裝置存取 SharePoint 和 OneDrive 內容。如需詳細資訊，請參閱 SharePoint 文件中的[從未受管理的裝置控制存取](/sharepoint/control-access-from-unmanaged-devices)。您針對此標籤設定所指定的選項，相當於對網站執行 PowerShell 命令，如 SharePoint 指示的[封鎖或限制特定 SharePoint 網站或 OneDrive 的存取](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices#block-or-limit-access-to-a-specific-sharepoint-site-or-onedrive) \(部分機器翻譯\) 一節中的步驟 3-5 所述。</span><span class="sxs-lookup"><span data-stu-id="72732-p111">**Access from unmanaged devices**: This option uses the SharePoint feature that uses Azure AD conditional access to block or limit access to SharePoint and OneDrive content from unmanaged devices. For more information, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices) from the SharePoint documentation. The option you specify for this label setting is the equivalent of running a PowerShell command for a site, as described in steps 3-5 from the [Block or limit access to a specific SharePoint site or OneDrive](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices#block-or-limit-access-to-a-specific-sharepoint-site-or-onedrive) section from the SharePoint instructions.</span></span>
        
        <span data-ttu-id="72732-155">如需其他資訊，請參閱本節末尾的 [有關非管理裝置的依賴性的詳細資訊](#more-information-about-the-dependencies-for-the-unmanaged-devices-option)。</span><span class="sxs-lookup"><span data-stu-id="72732-155">For additional information, see [More information about the dependencies for the unmanaged devices option](#more-information-about-the-dependencies-for-the-unmanaged-devices-option) at the end of this section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72732-p112">Only these site and group settings take effect when you apply the label to a team, group, or site. If the [label's scope](sensitivity-labels.md#label-scopes) includes files and emails, other label settings such as encryption and content marking aren't applied to the content within the team, group, or site.</span><span class="sxs-lookup"><span data-stu-id="72732-p112">Only these site and group settings take effect when you apply the label to a team, group, or site. If the [label's scope](sensitivity-labels.md#label-scopes) includes files and emails, other label settings such as encryption and content marking aren't applied to the content within the team, group, or site.</span></span>

<span data-ttu-id="72732-p113">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy). The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span><span class="sxs-lookup"><span data-stu-id="72732-p113">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy). The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

##### <a name="more-information-about-the-dependencies-for-the-unmanaged-devices-option"></a><span data-ttu-id="72732-160">關於 [未受管理裝置] 選項的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="72732-160">More information about the dependencies for the unmanaged devices option</span></span>

<span data-ttu-id="72732-p114">If you don't configure the dependent conditional access policy for SharePoint as documented in [Use app-enforced restrictions](https://docs.microsoft.com/sharepoint/app-enforced-restrictions), the option you specify here will have no effect. Additionally, it will have no effect if it's less restrictive than a configured setting at the tenant level. If you have configured an organization-wide setting for unmanaged devices, choose a label setting that's either the same or more restrictive</span><span class="sxs-lookup"><span data-stu-id="72732-p114">If you don't configure the dependent conditional access policy for SharePoint as documented in [Use app-enforced restrictions](https://docs.microsoft.com/sharepoint/app-enforced-restrictions), the option you specify here will have no effect. Additionally, it will have no effect if it's less restrictive than a configured setting at the tenant level. If you have configured an organization-wide setting for unmanaged devices, choose a label setting that's either the same or more restrictive</span></span>

<span data-ttu-id="72732-p115">For example, if your tenant is configured for **Allow limited, web-only access**, the label setting that allows full access will have no effect because it's less restrictive. For this tenant-level setting, choose the label setting to block access (more restrictive) or the label setting for limited access (the same as the tenant setting).</span><span class="sxs-lookup"><span data-stu-id="72732-p115">For example, if your tenant is configured for **Allow limited, web-only access**, the label setting that allows full access will have no effect because it's less restrictive. For this tenant-level setting, choose the label setting to block access (more restrictive) or the label setting for limited access (the same as the tenant setting).</span></span>

<span data-ttu-id="72732-p116">Because you can configure the SharePoint settings separately from the label configuration, there's no check in the sensitivity label wizard that the dependencies are in place. These dependencies can be configured after the label is created and published, and even after the label is applied. However, if the label is already applied, the label setting won't take effect until after the user next authenticates.</span><span class="sxs-lookup"><span data-stu-id="72732-p116">Because you can configure the SharePoint settings separately from the label configuration, there's no check in the sensitivity label wizard that the dependencies are in place. These dependencies can be configured after the label is created and published, and even after the label is applied. However, if the label is already applied, the label setting won't take effect until after the user next authenticates.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="72732-169">敏感度標籤管理</span><span class="sxs-lookup"><span data-stu-id="72732-169">Sensitivity label management</span></span>

<span data-ttu-id="72732-170">建立、修改或刪除為網站和群組設定的敏感度標籤時，請使用下列指導方針。</span><span class="sxs-lookup"><span data-stu-id="72732-170">Use the following guidance for when you create, modify, or delete sensitivity labels that are configured for sites and groups.</span></span>

### <a name="creating-and-publishing-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="72732-171">建立及發佈針對網站和群組設定的標籤</span><span class="sxs-lookup"><span data-stu-id="72732-171">Creating and publishing labels that are configured for sites and groups</span></span>

<span data-ttu-id="72732-p117">When a new sensitivity label is created and published, it's visible for users in teams, groups, and sites within one hour. However, if you modify an existing label, allow up to 24 hours. Use the following guidance to publish a label for your users when that label is configured for site and group settings:</span><span class="sxs-lookup"><span data-stu-id="72732-p117">When a new sensitivity label is created and published, it's visible for users in teams, groups, and sites within one hour. However, if you modify an existing label, allow up to 24 hours. Use the following guidance to publish a label for your users when that label is configured for site and group settings:</span></span>

1. <span data-ttu-id="72732-175">建立及設定敏感度標籤之後，請將此標籤新增至只適用一些測試使用者的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="72732-175">After you create and configure the sensitivity label, add this label to a label policy that applies to just a few test users.</span></span>

2. <span data-ttu-id="72732-176">等候複寫變更：</span><span class="sxs-lookup"><span data-stu-id="72732-176">Wait for the change to replicate:</span></span>

   - <span data-ttu-id="72732-177">新標籤：等待 1 小時。</span><span class="sxs-lookup"><span data-stu-id="72732-177">New label: Wait for one hour.</span></span>
   - <span data-ttu-id="72732-178">現有標籤：等候 24 小時。</span><span class="sxs-lookup"><span data-stu-id="72732-178">Existing label: Wait for 24 hours.</span></span>

3. <span data-ttu-id="72732-179">在此等候期間之後，請使用其中一個測試使用者帳戶來建立小組、Microsoft 365 群組或 SharePoint 網站，並搭配您在步驟 1 中建立的標籤。</span><span class="sxs-lookup"><span data-stu-id="72732-179">After this wait period, use one of the test user accounts to create a team, Microsoft 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="72732-180">如果在此建立作業期間沒有發生任何錯誤，您便知道可以安全地將標籤發佈給租用戶中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="72732-180">If there are no errors during this creation operation, you know it's safe to publish the label to all users in your tenant.</span></span>

### <a name="modifying-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="72732-181">修改針對網站和群組設定的已發佈標籤</span><span class="sxs-lookup"><span data-stu-id="72732-181">Modifying published labels that are configured for sites and groups</span></span>

<span data-ttu-id="72732-p118">As a best practice, don't change the site and group settings for a sensitivity label after the label has been applied to teams, groups, or sites. If you do, remember to wait for 24 hours for the changes to replicate to all containers that have the label applied.</span><span class="sxs-lookup"><span data-stu-id="72732-p118">As a best practice, don't change the site and group settings for a sensitivity label after the label has been applied to teams, groups, or sites. If you do, remember to wait for 24 hours for the changes to replicate to all containers that have the label applied.</span></span>

<span data-ttu-id="72732-184">此外，如果您的變更包括 [外部使用者存取]\*\*\*\* 設定：</span><span class="sxs-lookup"><span data-stu-id="72732-184">In addition, if your changes include the **External users access** setting:</span></span>

- <span data-ttu-id="72732-p119">The new setting applies to new users but not to existing users. For example, if this setting was previously selected and as a result, guest users accessed the site, these guest users can still access the site after this setting is cleared in the label configuration.</span><span class="sxs-lookup"><span data-stu-id="72732-p119">The new setting applies to new users but not to existing users. For example, if this setting was previously selected and as a result, guest users accessed the site, these guest users can still access the site after this setting is cleared in the label configuration.</span></span>

- <span data-ttu-id="72732-187">群組屬性 hiddenMembership 和 roleEnabled 的隱私權設定不會更新。</span><span class="sxs-lookup"><span data-stu-id="72732-187">The privacy settings for the group properties hiddenMembership and roleEnabled aren't updated.</span></span>

### <a name="deleting-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="72732-188">刪除針對網站和群組設定的已發佈標籤</span><span class="sxs-lookup"><span data-stu-id="72732-188">Deleting published labels that are configured for sites and groups</span></span>

<span data-ttu-id="72732-p120">If you delete a sensitivity label that has the site and group settings enabled, and that label is included in one or more label policies, this action can result in creation failures for new teams, groups, and sites. To avoid this situation, use the following guidance:</span><span class="sxs-lookup"><span data-stu-id="72732-p120">If you delete a sensitivity label that has the site and group settings enabled, and that label is included in one or more label policies, this action can result in creation failures for new teams, groups, and sites. To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="72732-191">從包含標籤的所有標籤原則中移除敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="72732-191">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="72732-192">請等候 1 小時。</span><span class="sxs-lookup"><span data-stu-id="72732-192">Wait for one hour.</span></span>

3. <span data-ttu-id="72732-193">在此等候期間之後，請嘗試建立小組、群組或網站，並確認標籤已不再顯示。</span><span class="sxs-lookup"><span data-stu-id="72732-193">After this wait period, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="72732-194">如果敏感度標籤未顯示，您現在可以放心地刪除標籤。</span><span class="sxs-lookup"><span data-stu-id="72732-194">If the sensitivity label isn't visible, you can now safely delete the label.</span></span>

## <a name="how-to-apply-sensitivity-labels-to-containers"></a><span data-ttu-id="72732-195">如何將敏感度標籤套用至容器</span><span class="sxs-lookup"><span data-stu-id="72732-195">How to apply sensitivity labels to containers</span></span>

<span data-ttu-id="72732-196">您現在可以將敏感度標籤或標籤套用至下列容器：</span><span class="sxs-lookup"><span data-stu-id="72732-196">You're now ready to apply the sensitivity label or labels to the following containers:</span></span>

- [<span data-ttu-id="72732-197">Azure AD 中的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="72732-197">Microsoft 365 group in Azure AD</span></span>](#apply-sensitivity-labels-to-microsoft-365-groups)
- [<span data-ttu-id="72732-198">Microsoft Teams 小組網站</span><span class="sxs-lookup"><span data-stu-id="72732-198">Microsoft Teams team site</span></span>](#apply-a-sensitivity-label-to-a-new-team)
- [<span data-ttu-id="72732-199">Outlook 網頁版中的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="72732-199">Microsoft 365 group in Outlook on the web</span></span>](#apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web)
- [<span data-ttu-id="72732-200">SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="72732-200">SharePoint site</span></span>](#apply-a-sensitivity-label-to-a-new-site)

<span data-ttu-id="72732-201">如果您需要[將敏感度標籤套用至多個網站](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites)，您可以使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="72732-201">You can use PowerShell if you need to [apply a sensitivity label to multiple sites](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites).</span></span>

### <a name="apply-sensitivity-labels-to-microsoft-365-groups"></a><span data-ttu-id="72732-202">將敏感度標籤套用至 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="72732-202">Apply sensitivity labels to Microsoft 365 groups</span></span>

<span data-ttu-id="72732-p121">You're now ready to apply the sensitivity label or labels to Microsoft 365 groups. Return to the Azure AD documentation for instructions:</span><span class="sxs-lookup"><span data-stu-id="72732-p121">You're now ready to apply the sensitivity label or labels to Microsoft 365 groups. Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="72732-205">在 Azure 入口網站中將標籤指派至新群組</span><span class="sxs-lookup"><span data-stu-id="72732-205">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

- [<span data-ttu-id="72732-206">在 Azure 入口網站中將標籤指派至現有群組</span><span class="sxs-lookup"><span data-stu-id="72732-206">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

- <span data-ttu-id="72732-207">[在 Azure 入口網站中將標籤從現有群組移除](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="72732-207">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="72732-208">將敏感度標籤套用至新的小組</span><span class="sxs-lookup"><span data-stu-id="72732-208">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="72732-p122">Users can select sensitivity labels when they create new teams in Microsoft Teams. When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration. Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span><span class="sxs-lookup"><span data-stu-id="72732-p122">Users can select sensitivity labels when they create new teams in Microsoft Teams. When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration. Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="72732-212">深入了解 Teams 的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="72732-212">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![建立新小組時的隱私權設定](../media/privacy-setting-new-team.png)

<span data-ttu-id="72732-214">建立小組之後，敏感度標籤會顯示在所有頻道的右上角。</span><span class="sxs-lookup"><span data-stu-id="72732-214">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![敏感度標籤顯示在小組上](../media/privacy-setting-teams.png)

<span data-ttu-id="72732-216">服務自動將相同的敏感度標籤套用至 Microsoft 365 群組和連線的 SharePoint 小組網站。</span><span class="sxs-lookup"><span data-stu-id="72732-216">The service automatically applies the same sensitivity label to the Microsoft 365 group and the connected SharePoint team site.</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="72732-217">在 Outlook 網頁版中將敏感度標籤套用至新的群組</span><span class="sxs-lookup"><span data-stu-id="72732-217">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="72732-218">在 Outlook 網頁版中，當您建立新的群組時，您可以選取或變更已發佈標籤的**敏感度**選項：</span><span class="sxs-lookup"><span data-stu-id="72732-218">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![建立群組並選取 [敏感度] 底下的選項](../media/sensitivity-label-new-group.png)

### <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="72732-220">將敏感度標籤套用至新的網站</span><span class="sxs-lookup"><span data-stu-id="72732-220">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="72732-221">系統管理員和使用者可以在[建立新式小組網站和通訊網站](/sharepoint/create-site-collection)時選取敏感度標籤，然後展開 [進階設定]\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="72732-221">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection), and expand **Advanced settings**:</span></span>

![建立網站並選取 [敏感度] 底下的選項](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="72732-223">下拉式方塊會顯示所選項目的標籤名稱，[說明] 圖示則會顯示所有標籤名稱及其工具提示，以協助使用者判斷所要套用的正確標籤。</span><span class="sxs-lookup"><span data-stu-id="72732-223">The dropdown box displays the label names for the selection, and the help icon displays all the label names with their tooltip, which can help users determine the correct label to apply.</span></span>

<span data-ttu-id="72732-p123">When the label is applied, and users browse to the site, they see the name of the label and applied policies. For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span><span class="sxs-lookup"><span data-stu-id="72732-p123">When the label is applied, and users browse to the site, they see the name of the label and applied policies. For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span></span>

![已套用敏感度標籤的網站](../media/sensitivity-label-site.png)

### <a name="use-powershell-to-apply-a-sensitivity-label-to-multiple-sites"></a><span data-ttu-id="72732-227">使用 PowerShell 將敏感度標籤套用至多個網站</span><span class="sxs-lookup"><span data-stu-id="72732-227">Use PowerShell to apply a sensitivity label to multiple sites</span></span>

<span data-ttu-id="72732-p124">You can use the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) and [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) cmdlet with the *SensitivityLabel* parameter from the current [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) to apply a sensitivity label to many sites. The sites can be any SharePoint site collection, or a OneDrive site.</span><span class="sxs-lookup"><span data-stu-id="72732-p124">You can use the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) and [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) cmdlet with the *SensitivityLabel* parameter from the current [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) to apply a sensitivity label to many sites. The sites can be any SharePoint site collection, or a OneDrive site.</span></span>

<span data-ttu-id="72732-230">確定您有 SharePoint Online 管理命令介面的版本 16.0.19418.12000 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="72732-230">Make sure you have version 16.0.19418.12000 or later of the SharePoint Online Management Shell.</span></span>

1. <span data-ttu-id="72732-231">使用 [以系統管理員身分執行]\*\*\*\* 選項開啟 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="72732-231">Open a PowerShell session with the **Run as Administrator** option.</span></span>

2. <span data-ttu-id="72732-232">如果您不知道標籤 GUID：[連線至安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)，並取得敏感度標籤及其 GUID 清單。</span><span class="sxs-lookup"><span data-stu-id="72732-232">If you don't know your label GUID: [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and get the list of sensitivity labels and their GUIDs.</span></span>

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. <span data-ttu-id="72732-p125">Now [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and store your label GUID as a variable. For example:</span><span class="sxs-lookup"><span data-stu-id="72732-p125">Now [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and store your label GUID as a variable. For example:</span></span>

   ```powershell
   $Id = [GUID]("e48058ea-98e8-4940-8db0-ba1310fd955e")
   ```

4. <span data-ttu-id="72732-p126">Create a new variable that identifies multiple sites that have an identifying string in common in their URL. For example:</span><span class="sxs-lookup"><span data-stu-id="72732-p126">Create a new variable that identifies multiple sites that have an identifying string in common in their URL. For example:</span></span>

   ```powershell
   $sites = Get-SPOSite -IncludePersonalSite $true -Limit all -Filter "Url -like 'documents"
   ```

5. <span data-ttu-id="72732-p127">Run the following command to apply the label to these sites. Using our examples:</span><span class="sxs-lookup"><span data-stu-id="72732-p127">Run the following command to apply the label to these sites. Using our examples:</span></span>

   ```powershell
   $sites | ForEach-Object {Set-SPOTenant $_.url -SensitivityLabel $Id}
   ```

<span data-ttu-id="72732-239">若要將不同的標籤套用至不同的網站，請針對每個網站重複下列命令：`Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span><span class="sxs-lookup"><span data-stu-id="72732-239">To apply different labels to different sites, repeat the following command for each site: `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span></span>

## <a name="view-and-manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="72732-240">在 SharePoint 系統管理中心檢視和管理敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="72732-240">View and manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="72732-p128">To view, sort, and search the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center. You might need to first add the **Sensitivity** column:</span><span class="sxs-lookup"><span data-stu-id="72732-p128">To view, sort, and search the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center. You might need to first add the **Sensitivity** column:</span></span>

![[使用中網站] 頁面上的 [敏感度] 欄](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="72732-244">如需從 [作用中網站] 頁面管理網站的詳細資訊，包括如何新增欄，請參閱[在新的 SharePoint 系統管理中心管理網站](/sharepoint/manage-sites-in-new-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="72732-244">For more information about managing sites from the Active sites page, including how to add a column, see [Manage sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

<span data-ttu-id="72732-245">您也可以從本頁面變更及套用標籤：</span><span class="sxs-lookup"><span data-stu-id="72732-245">You can also change and apply a label from this page:</span></span>

1. <span data-ttu-id="72732-246">選取網站名稱以開啟詳細資料窗格。</span><span class="sxs-lookup"><span data-stu-id="72732-246">Select the site name to open the details pane.</span></span>

2. <span data-ttu-id="72732-247">選取 [原則]\*\*\*\* 索引標籤，然後選取 [敏感度]\*\*\*\* 設定的 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="72732-247">Select the **Policies** tab, and then select **Edit** for the **Sensitivity** setting.</span></span>

3. <span data-ttu-id="72732-248">從 [編輯敏感度設定]\*\*\*\* 窗格中，選取您要套用至網站的敏感度標籤，然後選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="72732-248">From the **Edit sensitivity setting** pane, select the sensitivity label you want to apply to the site, and then select **Save**.</span></span>

## <a name="support-for-sensitivity-labels"></a><span data-ttu-id="72732-249">支援敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="72732-249">Support for sensitivity labels</span></span>

<span data-ttu-id="72732-250">下列應用程式與服務支援針對網站和群組進行設定的敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="72732-250">The following apps and services support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="72732-251">系統管理中心：</span><span class="sxs-lookup"><span data-stu-id="72732-251">Admin centers:</span></span>

  - <span data-ttu-id="72732-252">SharePoint 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="72732-252">SharePoint admin center</span></span>
  - <span data-ttu-id="72732-253">Azure Active Directory 入口網站</span><span class="sxs-lookup"><span data-stu-id="72732-253">Azure Active Directory portal</span></span>
  - <span data-ttu-id="72732-254">Microsoft 365 合規性中心、Microsoft 365 安全性中心、安全性與合規性中心</span><span class="sxs-lookup"><span data-stu-id="72732-254">Microsoft 365 compliance center, Microsoft 365 security center, Security & Compliance Center</span></span>

- <span data-ttu-id="72732-255">使用者應用程式與服務：</span><span class="sxs-lookup"><span data-stu-id="72732-255">User apps and services:</span></span>

  - <span data-ttu-id="72732-256">SharePoint</span><span class="sxs-lookup"><span data-stu-id="72732-256">SharePoint</span></span>
  - <span data-ttu-id="72732-257">Teams</span><span class="sxs-lookup"><span data-stu-id="72732-257">Teams</span></span>
  - <span data-ttu-id="72732-258">Outlook 網頁版和 Windows 版、MacOS 版、iOS 版及 Android 版</span><span class="sxs-lookup"><span data-stu-id="72732-258">Outlook on the web and for Windows, MacOS, iOS, and Android</span></span>
  - <span data-ttu-id="72732-259">Forms</span><span class="sxs-lookup"><span data-stu-id="72732-259">Forms</span></span>
  - <span data-ttu-id="72732-260">Stream</span><span class="sxs-lookup"><span data-stu-id="72732-260">Stream</span></span>

<span data-ttu-id="72732-261">下列應用程式與服務目前不支援針對網站和群組進行設定的敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="72732-261">The following apps and services don't currently support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="72732-262">系統管理中心：</span><span class="sxs-lookup"><span data-stu-id="72732-262">Admin centers:</span></span>

  - <span data-ttu-id="72732-263">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="72732-263">Microsoft 365 admin center</span></span>
  - <span data-ttu-id="72732-264">Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="72732-264">Teams admin center</span></span>
  - <span data-ttu-id="72732-265">Exchange 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="72732-265">Exchange admin center</span></span>

- <span data-ttu-id="72732-266">使用者應用程式與服務：</span><span class="sxs-lookup"><span data-stu-id="72732-266">User apps and services:</span></span>

  - <span data-ttu-id="72732-267">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="72732-267">Dynamics 365</span></span>
  - <span data-ttu-id="72732-268">Yammer</span><span class="sxs-lookup"><span data-stu-id="72732-268">Yammer</span></span>
  - <span data-ttu-id="72732-269">Planner</span><span class="sxs-lookup"><span data-stu-id="72732-269">Planner</span></span>
  - <span data-ttu-id="72732-270">Project</span><span class="sxs-lookup"><span data-stu-id="72732-270">Project</span></span>
  - <span data-ttu-id="72732-271">Power BI</span><span class="sxs-lookup"><span data-stu-id="72732-271">Power BI</span></span>

## <a name="classic-azure-ad-group-classification"></a><span data-ttu-id="72732-272">傳統 Azure AD 群組分類</span><span class="sxs-lookup"><span data-stu-id="72732-272">Classic Azure AD group classification</span></span>

<span data-ttu-id="72732-p129">Microsoft 365 no longer supports the old classifications for new Microsoft 365 groups and SharePoint sites after you enable sensitivity labels for containers. However, existing groups and sites that support sensitivity labels still display the old classification values until you convert them to use sensitivity labels.</span><span class="sxs-lookup"><span data-stu-id="72732-p129">Microsoft 365 no longer supports the old classifications for new Microsoft 365 groups and SharePoint sites after you enable sensitivity labels for containers. However, existing groups and sites that support sensitivity labels still display the old classification values until you convert them to use sensitivity labels.</span></span>

<span data-ttu-id="72732-275">如需您先前可能使用的 SharePoint 舊群組分類範例，請參閱 [SharePoint 新式網站分類](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)。</span><span class="sxs-lookup"><span data-stu-id="72732-275">As an example of how you might have used the old group classification for SharePoint, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="72732-p130">These classifications were configured by using Azure AD PowerShell or the PnP Core library and defining values for the `ClassificationList` setting. If your tenant has classification values defined, they are shown when you run the following command from the [AzureADPreview PowerShell module](https://www.powershellgallery.com/packages/AzureADPreview):</span><span class="sxs-lookup"><span data-stu-id="72732-p130">These classifications were configured by using Azure AD PowerShell or the PnP Core library and defining values for the `ClassificationList` setting. If your tenant has classification values defined, they are shown when you run the following command from the [AzureADPreview PowerShell module](https://www.powershellgallery.com/packages/AzureADPreview):</span></span>

```powershell
($setting["ClassificationList"])
```

<span data-ttu-id="72732-278">若要將舊分類轉換成敏感度標籤，請執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="72732-278">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="72732-279">使用現有的標籤：編輯已發佈的現有敏感度標籤，以指定網站和群組需要的標籤設定。</span><span class="sxs-lookup"><span data-stu-id="72732-279">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="72732-280">建立新標籤：建立及發佈與現有分類名稱相同的新敏感度標籤，以指定網站和群組需要的標籤設定。</span><span class="sxs-lookup"><span data-stu-id="72732-280">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="72732-281">然後：</span><span class="sxs-lookup"><span data-stu-id="72732-281">Then:</span></span>

1. <span data-ttu-id="72732-p131">Use PowerShell to apply the sensitivity labels to existing Microsoft 365 groups and SharePoint sites by using name mapping. See the next section for instructions.</span><span class="sxs-lookup"><span data-stu-id="72732-p131">Use PowerShell to apply the sensitivity labels to existing Microsoft 365 groups and SharePoint sites by using name mapping. See the next section for instructions.</span></span>

2. <span data-ttu-id="72732-284">移除現有群組和網站的舊分類。</span><span class="sxs-lookup"><span data-stu-id="72732-284">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="72732-285">雖然您無法防止使用者在尚未支援敏感度標籤的應用程式和服務中建立新群組，但您可以執行週期性 PowerShell 指令碼來尋找使用者使用舊分類建立的新群組，並將它們轉換成使用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="72732-285">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span>

<span data-ttu-id="72732-286">若要協助您管理網站和群組的敏感度標籤與 Azure AD 分類的共存，請參閱 [Microsoft 365 群組的 Azure Active Directory 分類和敏感度標籤](migrate-aad-classification-sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="72732-286">To help you manage the coexistence of sensitivity labels and Azure AD classifications for sites and groups, see [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](migrate-aad-classification-sensitivity-labels.md).</span></span>

### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a><span data-ttu-id="72732-287">使用 PowerShell 將 Microsoft 365 群組的分類轉換成敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="72732-287">Use PowerShell to convert classifications for Microsoft 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="72732-288">首先，[連線到安全性與合規性中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="72732-288">First, [connect to Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="72732-289">例如，在您以系統管理員身分執行的 PowerShell 工作階段中，使用全域系統管理員帳戶登入：</span><span class="sxs-lookup"><span data-stu-id="72732-289">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>

2. <span data-ttu-id="72732-290">透過使用 [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label) Cmdlet，取得敏感度標籤和其 GUID 的清單：</span><span class="sxs-lookup"><span data-stu-id="72732-290">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label) cmdlet:</span></span>

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. <span data-ttu-id="72732-291">記下您要套用至 Microsoft 365 群組的敏感度標籤 GUID。</span><span class="sxs-lookup"><span data-stu-id="72732-291">Make a note of the GUIDs for the sensitivity labels you want to apply to your Microsoft 365 groups.</span></span>

4. <span data-ttu-id="72732-292">現在，在不同的 Windows PowerShell 視窗中 [連線到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="72732-292">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) in a separate Windows PowerShell window.</span></span>

5. <span data-ttu-id="72732-293">使用下列命令做為範例，以取得目前具有「一般」分類的群組清單：</span><span class="sxs-lookup"><span data-stu-id="72732-293">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="72732-p132">For each group, add the new sensitivity label GUID. For example:</span><span class="sxs-lookup"><span data-stu-id="72732-p132">For each group, add the new sensitivity label GUID. For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. <span data-ttu-id="72732-296">針對其餘的群組分類重複步驟 5 和 6。</span><span class="sxs-lookup"><span data-stu-id="72732-296">Repeat steps 5 and 6 for your remaining group classifications.</span></span>

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="72732-297">稽核敏感度標籤活動</span><span class="sxs-lookup"><span data-stu-id="72732-297">Auditing sensitivity label activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72732-298">如果您使用標籤分離，只選擇保護容器的 **群組和網站**標籤範圍：由於 **偵測到的檔案敏感度等級不符合** 本節內容所述的稽核活動及電子郵件，須 [將這些標籤排序](sensitivity-labels.md#label-priority-order-matters) 在具有 **檔案和電子郵件** 範圍的標籤之前。 </span><span class="sxs-lookup"><span data-stu-id="72732-298">If you use label separation by selecting just the **Groups & sites** scope for labels that protect containers: Because of the **Detected document sensitivity mismatch** audit event and email described in this section, consider [ordering these labels](sensitivity-labels.md#label-priority-order-matters) before labels that have a scope for **Files & emails**.</span></span> 

<span data-ttu-id="72732-p133">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked. For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**. Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span><span class="sxs-lookup"><span data-stu-id="72732-p133">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked. For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**. Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="72732-p134">Although the action isn't blocked, it is audited and automatically generates an email to the person who uploaded the document and the site administrator. As a result, both the user and administrators can identify documents that have this misalignment of label priority and take action if needed. For example, delete or move the uploaded document from the site.</span><span class="sxs-lookup"><span data-stu-id="72732-p134">Although the action isn't blocked, it is audited and automatically generates an email to the person who uploaded the document and the site administrator. As a result, both the user and administrators can identify documents that have this misalignment of label priority and take action if needed. For example, delete or move the uploaded document from the site.</span></span>

<span data-ttu-id="72732-p135">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site. For example, a document labeled **General** is uploaded to a site labeled **Confidential**. In this scenario, an auditing event and email aren't generated.</span><span class="sxs-lookup"><span data-stu-id="72732-p135">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site. For example, a document labeled **General** is uploaded to a site labeled **Confidential**. In this scenario, an auditing event and email aren't generated.</span></span>

<span data-ttu-id="72732-308">若要搜尋此事件的稽核記錄，請尋找 **[檔案與頁面活動]** 類別中的 **[偵測到的文件敏感度不相符]**。</span><span class="sxs-lookup"><span data-stu-id="72732-308">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span>

<span data-ttu-id="72732-p136">The automatically generated email has the subject **Incompatible sensitivity label detected** and the email message explains the labeling mismatch with a link to the uploaded document and site. It also contains a documentation link that explains how users can change the sensitivity label. Currently, these automated emails cannot be disabled or customized.</span><span class="sxs-lookup"><span data-stu-id="72732-p136">The automatically generated email has the subject **Incompatible sensitivity label detected** and the email message explains the labeling mismatch with a link to the uploaded document and site. It also contains a documentation link that explains how users can change the sensitivity label. Currently, these automated emails cannot be disabled or customized.</span></span>

<span data-ttu-id="72732-312">當某人在網站或群組間新增或移除敏感度標籤時，系統也會稽核這些活動，但不會自動產生電子郵件。</span><span class="sxs-lookup"><span data-stu-id="72732-312">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited but without automatically generating an email.</span></span>

<span data-ttu-id="72732-p137">All these auditing events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category. For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="72732-p137">All these auditing events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category. For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="how-to-disable-sensitivity-labels-for-containers"></a><span data-ttu-id="72732-315">如何停用容器的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="72732-315">How to disable sensitivity labels for containers</span></span>

<span data-ttu-id="72732-p138">You can turn off sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell). However, to disable the feature, in step 5, specify `$setting["EnableMIPLabels"] = "False"`.</span><span class="sxs-lookup"><span data-stu-id="72732-p138">You can turn off sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell). However, to disable the feature, in step 5, specify `$setting["EnableMIPLabels"] = "False"`.</span></span>

<span data-ttu-id="72732-p139">In addition to making all the settings unavailable for groups and sites when you create or edit sensitivity labels, this action reverts which property the containers use for their configuration. Enabling sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites switches the property used from **Classification** (used for [Azure AD group classification](#classic-azure-ad-group-classification)) to **Sensitivity**. When you disable sensitivity labels for containers, the containers ignore the Sensitivity property and use the Classification property again.</span><span class="sxs-lookup"><span data-stu-id="72732-p139">In addition to making all the settings unavailable for groups and sites when you create or edit sensitivity labels, this action reverts which property the containers use for their configuration. Enabling sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites switches the property used from **Classification** (used for [Azure AD group classification](#classic-azure-ad-group-classification)) to **Sensitivity**. When you disable sensitivity labels for containers, the containers ignore the Sensitivity property and use the Classification property again.</span></span>

<span data-ttu-id="72732-321">這表示來自網站和群組、先前套用至容器的任何標籤設定都不會強制執行，而容器則不再顯示標籤。</span><span class="sxs-lookup"><span data-stu-id="72732-321">This means that any label settings from sites and groups previously applied to containers won't be enforced, and containers no longer display the labels.</span></span>

<span data-ttu-id="72732-p140">If these containers have Azure AD classification values applied to them, the containers revert to using the classifications again. Be aware that any new sites or groups that were created after enabling the feature won't display a label or have a classification. For these containers, and any new containers, you can now apply classification values. For more information, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification) and [Create classifications for Office groups in your organization](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell).</span><span class="sxs-lookup"><span data-stu-id="72732-p140">If these containers have Azure AD classification values applied to them, the containers revert to using the classifications again. Be aware that any new sites or groups that were created after enabling the feature won't display a label or have a classification. For these containers, and any new containers, you can now apply classification values. For more information, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification) and [Create classifications for Office groups in your organization](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="72732-326">其他資源</span><span class="sxs-lookup"><span data-stu-id="72732-326">Additional resources</span></span>

<span data-ttu-id="72732-327">如需有關[透過 Microsoft Teams、O365 群組和 SharePoint Online 網站使用敏感度標籤](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380) (英文) 的資訊，請參閱網路研討會的記錄和回答的問題。</span><span class="sxs-lookup"><span data-stu-id="72732-327">See the webinar recording and answered questions for [Using Sensitivity labels with Microsoft Teams, O365 Groups and SharePoint Online sites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span></span>

<span data-ttu-id="72732-p141">This webinar was recorded when the feature was still in preview, so you might notice some discrepancies in the UI. However, the information for this feature is still accurate, with any new capabilities documented on this page.</span><span class="sxs-lookup"><span data-stu-id="72732-p141">This webinar was recorded when the feature was still in preview, so you might notice some discrepancies in the UI. However, the information for this feature is still accurate, with any new capabilities documented on this page.</span></span>
