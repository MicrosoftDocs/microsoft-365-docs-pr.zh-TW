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
ms.openlocfilehash: 6baca2e24e50bd3ee418da994adcfbe7fca8338c
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694398"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="a3747-103">使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容</span><span class="sxs-lookup"><span data-stu-id="a3747-103">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

><span data-ttu-id="a3747-104">*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="a3747-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="a3747-105">除了使用[敏感度標籤](sensitivity-labels.md)來分類及保護文件和電子郵件，您也可以使用敏感度標籤來保護下列容器中的內容：Microsoft Teams 網站、Microsoft 365 群組 ([之前的 Office 365 群組](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) 和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="a3747-105">In addition to using [sensitivity labels](sensitivity-labels.md) to classify and protect documents and emails, you can also use sensitivity labels to protect content in the following containers: Microsoft Teams sites, Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), and SharePoint sites.</span></span> <span data-ttu-id="a3747-106">針對此容器層級分類和保護，使用下列標籤設定：</span><span class="sxs-lookup"><span data-stu-id="a3747-106">For this container-level classification and protection, use the following label settings:</span></span>

- <span data-ttu-id="a3747-107">小組網站和 Microsoft 365 群組的隱私權（公用或私人）</span><span class="sxs-lookup"><span data-stu-id="a3747-107">Privacy (public or private) of teams sites and Microsoft 365 groups</span></span>
- <span data-ttu-id="a3747-108">外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="a3747-108">External user access</span></span>
- <span data-ttu-id="a3747-109">透過 SharePoint 網站進行外部共用</span><span class="sxs-lookup"><span data-stu-id="a3747-109">External sharing from SharePoint sites</span></span>
- <span data-ttu-id="a3747-110">從未受管理的裝置存取</span><span class="sxs-lookup"><span data-stu-id="a3747-110">Access from unmanaged devices</span></span>
- <span data-ttu-id="a3747-111">驗證內容 (預覽)</span><span class="sxs-lookup"><span data-stu-id="a3747-111">Authentication contexts (in preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3747-112">未管理裝置和驗證內容設定可與 Azure Active Directory 條件式存取一起使用。</span><span class="sxs-lookup"><span data-stu-id="a3747-112">The settings for unmanaged devices and authentication contexts work in conjunction with Azure Active Directory Conditional Access.</span></span> <span data-ttu-id="a3747-113">如果您想要針對這些設定使用敏感度標籤，必須設定此相依功能。</span><span class="sxs-lookup"><span data-stu-id="a3747-113">You must configure this dependent feature if you want to use a sensitivity label for these settings.</span></span> <span data-ttu-id="a3747-114">下列指示中包含其他資訊。</span><span class="sxs-lookup"><span data-stu-id="a3747-114">Additional information is included in the instructions that follow.</span></span>

<span data-ttu-id="a3747-115">當您將此敏感度標籤套用至支援的容器時，標籤會自動將分類和配置的保護設定套用至網站或群組。</span><span class="sxs-lookup"><span data-stu-id="a3747-115">When you apply this sensitivity label to a supported container, the label automatically applies the classification and configured protection settings to the site or group.</span></span>

<span data-ttu-id="a3747-116">不過，這些容器中的內容不會繼承分類的標籤或檔案和電子郵件的設定 (如視覺標記或加密)。</span><span class="sxs-lookup"><span data-stu-id="a3747-116">Content in these containers however, do not inherit the labels for the classification or settings for files and emails, such as visual markings and encryption.</span></span> <span data-ttu-id="a3747-117">因此，使用者可以為其在 SharePoint 網站或小組網站中的文件加上標籤，請確定已[對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="a3747-117">So that users can label their documents in SharePoint sites or team sites, make sure you've [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a3747-118">容器的敏感度標籤不支援使用 Office 365 內容傳遞網路 (CDN)。</span><span class="sxs-lookup"><span data-stu-id="a3747-118">Sensitivity labels for containers aren't supported with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="using-sensitivity-labels-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="a3747-119">在對 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站使用敏感度標籤時遇到問題嗎？</span><span class="sxs-lookup"><span data-stu-id="a3747-119">Using sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="a3747-p104">啟用容器的敏感度標籤並配置新設定的敏感度標籤前，使用者可在其應用程式中查看並套用敏感度標籤。例如，從 Word：</span><span class="sxs-lookup"><span data-stu-id="a3747-p104">Before you enable sensitivity labels for containers and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps. For example, from Word:</span></span>

![Word 傳統型應用程式中顯示的敏感度標籤](../media/sensitivity-label-word.png)

<span data-ttu-id="a3747-123">啟用並設定容器的敏感度標籤後，使用者可進一步查看並將敏感度標籤套用至 Microsoft 小組網站、Microsoft 365 群組和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="a3747-123">After you enable and configure sensitivity labels for containers, users can additionally see and apply sensitivity labels to Microsoft team sites, Microsoft 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="a3747-124">例如，從 SharePoint 建立新的小組網站時：</span><span class="sxs-lookup"><span data-stu-id="a3747-124">For example, when you create a new team site from SharePoint:</span></span>

![從 SharePoint 建立小組網站時的敏感度標籤](../media/sensitivity-labels-new-team-site.png)

## <a name="how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels"></a><span data-ttu-id="a3747-126">如何為容器啟用敏感度標籤以及同步處理標籤</span><span class="sxs-lookup"><span data-stu-id="a3747-126">How to enable sensitivity labels for containers and synchronize labels</span></span>

<span data-ttu-id="a3747-127">如果您尚未啟用容器的敏感度標籤，請以單次程序執行下列一組步驟：</span><span class="sxs-lookup"><span data-stu-id="a3747-127">If you haven't yet enabled sensitivity labels for containers, do the following set of steps as a one-time procedure:</span></span>

1. <span data-ttu-id="a3747-128">由於此功能使用 Azure AD 功能，請依照 Azure AD 文件中的指示來啟用敏感度標籤支援：[將敏感度標籤指派到 Azure Active Directory 中的 Microsoft 365 群組](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="a3747-128">Because this feature uses Azure AD functionality, follow the instructions from the Azure AD documentation to enable sensitivity label support: [Assign sensitivity labels to Microsoft 365 groups in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="a3747-129">您現在需要將敏感度標籤同步處理至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="a3747-129">You now need to synchronize your sensitivity labels to Azure AD.</span></span> <span data-ttu-id="a3747-130">首先，[連線到安全性與合規性中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a3747-130">First, [connect to Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="a3747-131">例如，在您以系統管理員身分執行的 PowerShell 工作階段中，使用全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="a3747-131">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account.</span></span>

3. <span data-ttu-id="a3747-132">然後執行下列命令，以確保您的敏感度標籤可以搭配 Microsoft 365 群組使用：</span><span class="sxs-lookup"><span data-stu-id="a3747-132">Then run the following command to ensure your sensitivity labels can be used with Microsoft 365 groups:</span></span>

    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-groups-and-site-settings"></a><span data-ttu-id="a3747-133">如何設定網站和群組設定</span><span class="sxs-lookup"><span data-stu-id="a3747-133">How to configure groups and site settings</span></span>

<span data-ttu-id="a3747-134">如上節所述啟用容器的敏感度標籤之後，您可以在 [敏感度標籤] 精靈中設定群組和網站的保護設定。</span><span class="sxs-lookup"><span data-stu-id="a3747-134">After sensitivity labels are enabled for containers as described in the previous section, you can then configure protection settings for groups and sites in the sensitivity labeling wizard.</span></span> <span data-ttu-id="a3747-135">在啟用容器的敏感度標籤之前，精靈中會顯示這些設定，但無法進行設定。</span><span class="sxs-lookup"><span data-stu-id="a3747-135">Until sensitivity labels are enabled for containers, the settings are visible in the wizard but you can't configure them.</span></span>

1. <span data-ttu-id="a3747-136">遵循一般指示以 [建立或編輯敏感度標籤](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)，並確認已針對標籤的範圍選取 **[群組和網站]**：</span><span class="sxs-lookup"><span data-stu-id="a3747-136">Follow the general instructions to [create or edit a sensitivity label](create-sensitivity-labels.md#create-and-configure-sensitivity-labels) and make sure you select **Groups & sites** for the label's scope:</span></span> 
    
    ![檔案和電子郵件的敏感度標籤範圍選項](../media/groupsandsites-scope-options-sensitivity-label.png)
    
    <span data-ttu-id="a3747-138">若標籤只選取這個範圍時，標籤就不會顯示在支援靈敏度標籤的 Office 應用程式中，且無法套用到檔案和電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a3747-138">When only this scope is selected for the label, the label won't be displayed in Office apps that support sensitivity labels and can't be applied to files and emails.</span></span> <span data-ttu-id="a3747-139">將標籤分開可讓使用者和系統管理員使用，但也會增加標籤部署的複雜程度。</span><span class="sxs-lookup"><span data-stu-id="a3747-139">Having this separation of labels can be helpful for both users and administrators, but can also add to the complexity of your label deployment.</span></span>
    
    <span data-ttu-id="a3747-140">例如，您必須仔細地檢查您的[標籤排序](sensitivity-labels.md#label-priority-order-matters)，因為 SharePoint 會在標示的文件上傳到標示的網站時進行偵測。</span><span class="sxs-lookup"><span data-stu-id="a3747-140">For example, you need to carefully review your [label ordering](sensitivity-labels.md#label-priority-order-matters) because SharePoint detects when a labeled document is uploaded to a labeled site.</span></span> <span data-ttu-id="a3747-141">在此案例中，當文件具有較網站的標籤更高的優先順序敏感度標籤時，系統會自動產生稽核事件和電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a3747-141">In this scenario, an audit event and email are automatically generated when the document has a higher priority sensitivity label than the site's label.</span></span> <span data-ttu-id="a3747-142">如需詳細資訊，請參閱本頁面上的[稽核敏感度標籤活動](#auditing-sensitivity-label-activities)一節。</span><span class="sxs-lookup"><span data-stu-id="a3747-142">For more information, see the [Auditing sensitivity label activities](#auditing-sensitivity-label-activities) section on this page.</span></span> 

2. <span data-ttu-id="a3747-143">然後，在 **定義群組和網站的保護設定** 頁面上，選取其中一個或兩個皆適用的可用選項：</span><span class="sxs-lookup"><span data-stu-id="a3747-143">Then, on the **Define protection settings for groups and sites** page, select one or both of the available options:</span></span>
    
    - <span data-ttu-id="a3747-144">[隱私權和外部使用者存取權設定 **]** 可設定 [隱私權 **]** 和 [外部使用者存取 **]** 設定。</span><span class="sxs-lookup"><span data-stu-id="a3747-144">**Privacy and external user access settings** to configure the **Privacy** and **External users access** settings.</span></span> 
    - <span data-ttu-id="a3747-145">[外部共用和條件式存取設定 **]** 設定 [從已套用標籤的 SharePoint 網站控制外部共用 **]** 和 [使用 Azure AD 條件式存取來保護已套用標籤的 SharePoint 網站 **]** 設定。</span><span class="sxs-lookup"><span data-stu-id="a3747-145">**External sharing and Conditional Access settings** to configure the **Control external sharing from labeled SharePoint sites** and **Use Azure AD Conditional Access to protect labeled SharePoint sites** setting.</span></span>

3. <span data-ttu-id="a3747-146">如果已選取 [隱私權和外部使用者存取權設定 **]**，請設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="a3747-146">If you selected **Privacy and external user access settings**, now configure the following settings:</span></span>
    
    - <span data-ttu-id="a3747-147">**隱私權**：如果您希望組織中的所有人都能存取套用此標籤的小組網站或群組，請保留 **公用** 的預設值。</span><span class="sxs-lookup"><span data-stu-id="a3747-147">**Privacy**: Keep the default of **Public** if you want anyone in your organization to access the team site or group where this label is applied.</span></span>
        
        <span data-ttu-id="a3747-148">如果您希望僅限組織中經核准的成員能存取，請選取 **[私人]**。</span><span class="sxs-lookup"><span data-stu-id="a3747-148">Select **Private** if you want access to be restricted to only approved members in your organization.</span></span>
        
        <span data-ttu-id="a3747-149">如果您想要使用敏感度標籤來保護容器中的內容，但仍讓使用者自行設定隱私權設定，則選取 **[無]**。</span><span class="sxs-lookup"><span data-stu-id="a3747-149">Select **None** when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.</span></span>
        
        <span data-ttu-id="a3747-150">將此標籤套用至容器時，請選取 [公用] 或 [私人] 設定來設定和鎖定隱私權設定。</span><span class="sxs-lookup"><span data-stu-id="a3747-150">The settings of **Public** or **Private** set and lock the privacy setting when you apply this label to the container.</span></span> <span data-ttu-id="a3747-151">您選擇的設定會取代先前為小組或群組設定的任何隱私權設定，並鎖定隱私權值，因此必須先移除容器的敏感度標籤才能變更隱私權設定。</span><span class="sxs-lookup"><span data-stu-id="a3747-151">Your chosen setting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container.</span></span> <span data-ttu-id="a3747-152">移除敏感度標籤後，標籤的隱私權設定會保留，使用者現在便可再次變更隱私權設定。</span><span class="sxs-lookup"><span data-stu-id="a3747-152">After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span></span>
    
    - <span data-ttu-id="a3747-153">**外部使用者存取權**：控制群組擁有者是否可以 [將來賓新增至群組](/office365/admin/create-groups/manage-guest-access-in-groups)。</span><span class="sxs-lookup"><span data-stu-id="a3747-153">**External user access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

4. <span data-ttu-id="a3747-154">如果已選取 [裝置外部共用和裝置存取設定 **]**，現在請進行下列設定：</span><span class="sxs-lookup"><span data-stu-id="a3747-154">If you selected **Device external sharing and device access settings**, now configure the following settings:</span></span>
    
    - <span data-ttu-id="a3747-155">**從已套用標籤的 SharePoint 網站控制外部共用**：選取這個選項，然後為任何人、新的及現有的來賓、現有的來賓，或僅限您組織中的人員選取外部共用。</span><span class="sxs-lookup"><span data-stu-id="a3747-155">**Control external sharing from labeled SharePoint sites**: Select this option to then select either external sharing for anyone, new and existing guests, existing guests, or only people in your organization.</span></span> <span data-ttu-id="a3747-156">如需有關此組態和設定的詳細資訊，請參閱 SharePoint 文件：[開啟或關閉網站的外部共用](/sharepoint/change-external-sharing-site)。</span><span class="sxs-lookup"><span data-stu-id="a3747-156">For more information about this configuration and settings, see the SharePoint documentation, [Turn external sharing on or off for a site](/sharepoint/change-external-sharing-site).</span></span>
    
    - <span data-ttu-id="a3747-157">**使用 Azure AD 條件式存取來保護已套用標籤的 SharePoint 網站**：只有在您的組織已設定並使用 [Azure Active Directory 條件式存取](/azure/active-directory/conditional-access/overview)時，才選取此選項。</span><span class="sxs-lookup"><span data-stu-id="a3747-157">**Use Azure AD Conditional Access to protect labeled SharePoint sites**: Select this option only if your organization has configured and is using [Azure Active Directory Conditional Access](/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="a3747-158">然後，請選取下列其中一個設定：</span><span class="sxs-lookup"><span data-stu-id="a3747-158">Then, select one of the following settings:</span></span>
    
        - <span data-ttu-id="a3747-159">**決定使用者是否可以從未受管理的裝置存取 SharePoint 網站**：此選項使用 Azure AD 條件式存取的 SharePoint 功能，或者封鎖或限制從未受管理的裝置存取 SharePoint 和 OneDrive 內容。</span><span class="sxs-lookup"><span data-stu-id="a3747-159">**Determine whether users can access SharePoint sites from unmanaged devices**: This option uses the SharePoint feature that uses Azure AD Conditional Access to block or limit access to SharePoint and OneDrive content from unmanaged devices.</span></span> <span data-ttu-id="a3747-160">如需詳細資訊，請參閱 SharePoint 文件中的[控制從未受管理的裝置存取](/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="a3747-160">For more information, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices) from the SharePoint documentation.</span></span> <span data-ttu-id="a3747-161">您為此標籤設定所指定的選項相當於執行網站的 PowerShell 命令，如 SharePoint 指示的[封鎖或限制存取特定 SharePoint 網站或 OneDrive](/sharepoint/control-access-from-unmanaged-devices#block-or-limit-access-to-a-specific-sharepoint-site-or-onedrive) 一節中的步驟 3-5 所述。</span><span class="sxs-lookup"><span data-stu-id="a3747-161">The option you specify for this label setting is the equivalent of running a PowerShell command for a site, as described in steps 3-5 from the [Block or limit access to a specific SharePoint site or OneDrive](/sharepoint/control-access-from-unmanaged-devices#block-or-limit-access-to-a-specific-sharepoint-site-or-onedrive) section from the SharePoint instructions.</span></span>
            
            <span data-ttu-id="a3747-162">如需其他設定資訊，請參閱本節結尾的[有關未受管理裝置選項相依性的詳細資訊](#more-information-about-the-dependencies-for-the-unmanaged-devices-option)。</span><span class="sxs-lookup"><span data-stu-id="a3747-162">For additional configuration information, see [More information about the dependencies for the unmanaged devices option](#more-information-about-the-dependencies-for-the-unmanaged-devices-option) at the end of this section.</span></span>
            
        - <span data-ttu-id="a3747-163">**選擇現有的驗證內容**：目前處於預覽階段，此選項可讓您在使用者存取已套用此標籤的 SharePoint 網站時，強制執行更嚴格的存取條件。</span><span class="sxs-lookup"><span data-stu-id="a3747-163">**Choose an existing authentication context**: Currently in preview, this option lets you enforce more stringent access conditions when users access SharePoint sites that have this label applied.</span></span> <span data-ttu-id="a3747-164">當您選取已針對貴組織的條件式存取部署建立和發佈的現有驗證內容時，會強制執行這些條件。</span><span class="sxs-lookup"><span data-stu-id="a3747-164">These conditions are enforced when you select an existing authentication context that has been created and published for your organization's Conditional Access deployment.</span></span> <span data-ttu-id="a3747-165">如果使用者不符合已設定的條件，或者他們使用不支援驗證內容的應用程式，則拒絕他們存取。</span><span class="sxs-lookup"><span data-stu-id="a3747-165">If users don't meet the configured conditions or if they use apps that don't support authentication contexts, they are denied access.</span></span>
            
            <span data-ttu-id="a3747-166">如需其他設定資訊，請參閱本節結尾的[有關驗證內容選項相依性的詳細資訊](#more-information-about-the-dependencies-for-the-authentication-context-option)。</span><span class="sxs-lookup"><span data-stu-id="a3747-166">For additional configuration information, see [More information about the dependencies for the authentication context option](#more-information-about-the-dependencies-for-the-authentication-context-option) at the end of this section.</span></span>
            
            <span data-ttu-id="a3747-167">此標籤設定的範例：</span><span class="sxs-lookup"><span data-stu-id="a3747-167">Examples for this label configuration:</span></span>
            
             - <span data-ttu-id="a3747-168">您選擇設定為需要[多重要素驗證 (MFA)](/azure/active-directory/conditional-access/untrusted-networks) 的驗證內容。</span><span class="sxs-lookup"><span data-stu-id="a3747-168">You choose an authentication context that is configured to require [multi-factor authentication (MFA)](/azure/active-directory/conditional-access/untrusted-networks).</span></span> <span data-ttu-id="a3747-169">接著，此標籤會套用到包含高度機密項目的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="a3747-169">This label is then applied to a SharePoint site that contains highly confidential items.</span></span> <span data-ttu-id="a3747-170">因此，當來自不受信任網路的使用者嘗試存取此網站中的文件時，會看到 MFA 提示，要求他們必須完成才能存取文件。</span><span class="sxs-lookup"><span data-stu-id="a3747-170">As a result, when users from an untrusted network attempt to access a document in this site, they see the MFA prompt that they must complete before they can access the document.</span></span>
             
             - <span data-ttu-id="a3747-171">您可以選擇針對 [使用規定 (ToU)](/azure/active-directory/conditional-access/terms-of-use) 設定的驗證內容。</span><span class="sxs-lookup"><span data-stu-id="a3747-171">You choose an authentication context that is configured for [terms of use (ToU) policies](/azure/active-directory/conditional-access/terms-of-use).</span></span> <span data-ttu-id="a3747-172">接著，此標籤會套用到包含因法律或合規性理由而需要接受使用條款之項目的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="a3747-172">This label is then applied to a SharePoint site that contains items that require a terms of use acceptance for legal or compliance reasons.</span></span> <span data-ttu-id="a3747-173">因此，當使用者嘗試存取此網站中的文件時，會看到使用規定文件，要求他們必須接受才能存取原始文件。</span><span class="sxs-lookup"><span data-stu-id="a3747-173">As a result, when users attempt to access a document in this site, they see a terms of use document that they must accept before they can access the original document.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3747-174">將標籤套用至小組、群組或網站時，只有這些網站和群組設定會生效。</span><span class="sxs-lookup"><span data-stu-id="a3747-174">Only these site and group settings take effect when you apply the label to a team, group, or site.</span></span> <span data-ttu-id="a3747-175">假如 [標籤範圍](sensitivity-labels.md#label-scopes) 包含檔案和電子郵件，其他標籤設定例如加密和內容標記，均不會套用至小組、群組或網站內的內容。</span><span class="sxs-lookup"><span data-stu-id="a3747-175">If the [label's scope](sensitivity-labels.md#label-scopes) includes files and emails, other label settings such as encryption and content marking aren't applied to the content within the team, group, or site.</span></span>

<span data-ttu-id="a3747-176">如果您的敏感度標籤尚未發佈，現在請[將標籤新增至敏感度標籤原則](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)以進行發佈。</span><span class="sxs-lookup"><span data-stu-id="a3747-176">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="a3747-177">包含此標籤、獲指派敏感度標籤原則的使用者將可以為網站和群組選取它。</span><span class="sxs-lookup"><span data-stu-id="a3747-177">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

##### <a name="more-information-about-the-dependencies-for-the-unmanaged-devices-option"></a><span data-ttu-id="a3747-178">關於 [未受管理裝置] 選項的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="a3747-178">More information about the dependencies for the unmanaged devices option</span></span>

<span data-ttu-id="a3747-179">如果您未設定 SharePoint 相關條件式存取原則如 [使用應用程式強制性限制](/sharepoint/app-enforced-restrictions) 中所述，您在此處指定的選項將不會產生任何影響。</span><span class="sxs-lookup"><span data-stu-id="a3747-179">If you don't configure the dependent conditional access policy for SharePoint as documented in [Use app-enforced restrictions](/sharepoint/app-enforced-restrictions), the option you specify here will have no effect.</span></span> <span data-ttu-id="a3747-180">此外，如果其限制低於租用戶層級所設定的設定，則不會產生任何影響。</span><span class="sxs-lookup"><span data-stu-id="a3747-180">Additionally, it will have no effect if it's less restrictive than a configured setting at the tenant level.</span></span> <span data-ttu-id="a3747-181">如果您已為非受管理的裝置設定全組織的設定，請選擇相同或具有更多限制的標籤設定。</span><span class="sxs-lookup"><span data-stu-id="a3747-181">If you have configured an organization-wide setting for unmanaged devices, choose a label setting that's either the same or more restrictive</span></span>

<span data-ttu-id="a3747-182">例如，如果您的租使用者設定為 **允許有限的、僅限網頁存取**，則允許完全存取的標籤設定將不會產生任何影響，因為其限制較少。</span><span class="sxs-lookup"><span data-stu-id="a3747-182">For example, if your tenant is configured for **Allow limited, web-only access**, the label setting that allows full access will have no effect because it's less restrictive.</span></span> <span data-ttu-id="a3747-183">針對此租使用者層級設定，請選擇標籤設定，以封鎖存取 {具有更多限制} 或限制存取 (與租使用者設定相同) 的標籤設定。</span><span class="sxs-lookup"><span data-stu-id="a3747-183">For this tenant-level setting, choose the label setting to block access (more restrictive) or the label setting for limited access (the same as the tenant setting).</span></span>

<span data-ttu-id="a3747-184">由於您可以在標籤設定外獨立設定 SharePoint 設定，因此在敏感度標籤精靈中依存關係部分不會顯示為勾選。</span><span class="sxs-lookup"><span data-stu-id="a3747-184">Because you can configure the SharePoint settings separately from the label configuration, there's no check in the sensitivity label wizard that the dependencies are in place.</span></span> <span data-ttu-id="a3747-185">您可以在建立和發佈標籤之後，甚至在套用標籤之後設定這些相關性。</span><span class="sxs-lookup"><span data-stu-id="a3747-185">These dependencies can be configured after the label is created and published, and even after the label is applied.</span></span> <span data-ttu-id="a3747-186">不過，如果已經套用標籤，在使用者下次驗證之前，標籤設定將不會生效。</span><span class="sxs-lookup"><span data-stu-id="a3747-186">However, if the label is already applied, the label setting won't take effect until after the user next authenticates.</span></span>

##### <a name="more-information-about-the-dependencies-for-the-authentication-context-option"></a><span data-ttu-id="a3747-187">關於驗證內容選項相依性的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="a3747-187">More information about the dependencies for the authentication context option</span></span>

<span data-ttu-id="a3747-188">若要顯示在選取項目下拉式清單中，您必須在 Azure Active Directory 條件式存取設定中建立、設定和發佈驗證內容。</span><span class="sxs-lookup"><span data-stu-id="a3747-188">To display in the drop-down list for selection, authentication contexts must be created, configured, and published as part of your Azure Active Directory Condition Access configuration.</span></span> <span data-ttu-id="a3747-189">有關詳細資訊和指示，請參閱 Azure AD 條件式存取文件中的[設定驗證內容](/azure/active-directory/conditional-access/concept-conditional-access-cloud-apps#configure-authentication-contexts)一節。</span><span class="sxs-lookup"><span data-stu-id="a3747-189">For more information and instructions, see the [Configure authentication contexts](/azure/active-directory/conditional-access/concept-conditional-access-cloud-apps#configure-authentication-contexts) section from the Azure AD Conditional Access documentation.</span></span>

<span data-ttu-id="a3747-p123">並非所有應用程式都支援驗證內容。如果應用程式不受支援的使用者連線到針對驗證內容所設定的網站，他們會看到拒絕存取的訊息，或提示他們進行驗證但遭到拒絕。目前支援驗證內容的應用程式：</span><span class="sxs-lookup"><span data-stu-id="a3747-p123">Not all apps support authentication contexts. If a user with an unsupported app connects to the site that's configured for an authentication context, they see either an access denied message or they are prompted to authenticate but rejected. The apps that currently support authentication contexts:</span></span>

- <span data-ttu-id="a3747-193">Office 網頁版，其中包含 Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="a3747-193">Office for the web, which includes Outlook for the web</span></span>

- <span data-ttu-id="a3747-194">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="a3747-194">Microsoft Planner</span></span>

- <span data-ttu-id="a3747-195">適用於 Word、Excel 和 PowerPoint 的 Microsoft 365 Apps；最低版本：</span><span class="sxs-lookup"><span data-stu-id="a3747-195">Microsoft 365 Apps for Word, Excel, and PowerPoint; minimum versions:</span></span>
    - <span data-ttu-id="a3747-196">Windows：2103</span><span class="sxs-lookup"><span data-stu-id="a3747-196">Windows: 2103</span></span>
    - <span data-ttu-id="a3747-197">macOS：16.45.1202</span><span class="sxs-lookup"><span data-stu-id="a3747-197">macOS: 16.45.1202</span></span>
    - <span data-ttu-id="a3747-198">iOS：2.48.303</span><span class="sxs-lookup"><span data-stu-id="a3747-198">iOS: 2.48.303</span></span>
    - <span data-ttu-id="a3747-199">Android：16.0.13924.10000</span><span class="sxs-lookup"><span data-stu-id="a3747-199">Android: 16.0.13924.10000</span></span>

- <span data-ttu-id="a3747-200">適用於 Outlook 的 Microsoft 365 Apps；最低版本：</span><span class="sxs-lookup"><span data-stu-id="a3747-200">Microsoft 365 Apps for Outlook; minimum versions:</span></span>
    - <span data-ttu-id="a3747-201">Windows：2103</span><span class="sxs-lookup"><span data-stu-id="a3747-201">Windows: 2103</span></span>
    - <span data-ttu-id="a3747-202">macOS：16.45.1202</span><span class="sxs-lookup"><span data-stu-id="a3747-202">macOS: 16.45.1202</span></span>
    - <span data-ttu-id="a3747-203">iOS：4.2109.0</span><span class="sxs-lookup"><span data-stu-id="a3747-203">iOS: 4.2109.0</span></span>
    - <span data-ttu-id="a3747-204">Android：4.2025.1</span><span class="sxs-lookup"><span data-stu-id="a3747-204">Android: 4.2025.1</span></span>

- <span data-ttu-id="a3747-205">OneDrive 同步處理應用程式，最低版本：</span><span class="sxs-lookup"><span data-stu-id="a3747-205">OneDrive sync app, minimum versions:</span></span>
    - <span data-ttu-id="a3747-206">Windows：21.002</span><span class="sxs-lookup"><span data-stu-id="a3747-206">Windows: 21.002</span></span>
    - <span data-ttu-id="a3747-207">macOS：21.002</span><span class="sxs-lookup"><span data-stu-id="a3747-207">macOS: 21.002</span></span>
    - <span data-ttu-id="a3747-208">iOS：在 12.30 中推出</span><span class="sxs-lookup"><span data-stu-id="a3747-208">iOS: Rolling out in 12.30</span></span>
    - <span data-ttu-id="a3747-209">Android：尚未支援</span><span class="sxs-lookup"><span data-stu-id="a3747-209">Android: Not yet supported</span></span>

<span data-ttu-id="a3747-210">此預覽的已知問題：</span><span class="sxs-lookup"><span data-stu-id="a3747-210">Known limitations for this preview:</span></span>

- <span data-ttu-id="a3747-211">這項功能仍在向部分租用戶推出。</span><span class="sxs-lookup"><span data-stu-id="a3747-211">This feature is still rolling out to some tenants.</span></span> <span data-ttu-id="a3747-212">如果使用者存取網站時，具有所選驗證內容的條件式存取原則未生效，您可以使用 PowerShell 確認您的設定正確且符合所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="a3747-212">If the Conditional Access policy with your selected authentication context is not taking effect when a user accesses the site, you can use PowerShell to confirm that your configuration is correct and all prerequisites are met.</span></span> <span data-ttu-id="a3747-213">您必須從網站移除敏感度標籤，然後從目前的 [SharePoint Online 管理命令殼層](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)使用 [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) Cmdlet，以設定驗證內容的網站。</span><span class="sxs-lookup"><span data-stu-id="a3747-213">You'll need to remove the sensitivity label from the site and then configure the site for the authentication context by using the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) cmdlet from the current [SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span> <span data-ttu-id="a3747-214">如果這個方法可行，請先等待幾天，再嘗試重新套用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="a3747-214">If this method works, wait a few more days before you try to apply the sensitivity label again.</span></span>
    
    <span data-ttu-id="a3747-215">若要使用 PowerShell 測試驗證內容：</span><span class="sxs-lookup"><span data-stu-id="a3747-215">To test the authentication context by using PowerShell:</span></span>
    
    ```powershell
    Set-SPOSite -Identity <site url> -ConditionalAccessPolicy AuthenticationContext -AuthenticationContextName "Name of authentication context"
    ```
    
    <span data-ttu-id="a3747-216">若要移除驗證內容，以便再次嘗試套用敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="a3747-216">To remove the authentication context so you can try to apply the sensitivity label again:</span></span>
    
    ```powershell
    Set-SPOSite -Identity <site url> -ConditionalAccessPolicy AuthenticationContext -AuthenticationContextName ""
    ```

- <span data-ttu-id="a3747-217">針對 OneDrive 同步處理應用程式，僅支援 OneDrive，不支援其他網站。</span><span class="sxs-lookup"><span data-stu-id="a3747-217">For the OneDrive sync app, supported for OneDrive only and not for other sites.</span></span>

- <span data-ttu-id="a3747-218">下列功能和應用程式可能與驗證內容不相容，因此，我們建議您確認這些功能與應用程式在使用者使用驗證內容成功存取網站之後是否仍可繼續運用：</span><span class="sxs-lookup"><span data-stu-id="a3747-218">The following features and apps might be incompatible with authentication contexts, so we encourage you to check that these continue to work after a user successfully accesses  a site by using an authentication context:</span></span>
    
    - <span data-ttu-id="a3747-219">使用 PowerApps 或 Power Automate 的工作流程</span><span class="sxs-lookup"><span data-stu-id="a3747-219">Workflows that use PowerApps or Power Automate</span></span>
    - <span data-ttu-id="a3747-220">協力廠商應用程式</span><span class="sxs-lookup"><span data-stu-id="a3747-220">Third-party apps</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="a3747-221">敏感度標籤管理</span><span class="sxs-lookup"><span data-stu-id="a3747-221">Sensitivity label management</span></span>

<span data-ttu-id="a3747-222">建立、修改或刪除為網站和群組設定的敏感度標籤時，請使用下列指導方針。</span><span class="sxs-lookup"><span data-stu-id="a3747-222">Use the following guidance for when you create, modify, or delete sensitivity labels that are configured for sites and groups.</span></span>

### <a name="creating-and-publishing-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="a3747-223">建立及發佈針對網站和群組設定的標籤</span><span class="sxs-lookup"><span data-stu-id="a3747-223">Creating and publishing labels that are configured for sites and groups</span></span>

<span data-ttu-id="a3747-224">建立並發佈新敏感度標籤後，在一個小時內小組、群組和網站中的使用者就會看到該標籤。</span><span class="sxs-lookup"><span data-stu-id="a3747-224">When a new sensitivity label is created and published, it's visible for users in teams, groups, and sites within one hour.</span></span> <span data-ttu-id="a3747-225">不過，如果您修改現有的標籤，最多需要等候 24 小時。</span><span class="sxs-lookup"><span data-stu-id="a3747-225">However, if you modify an existing label, allow up to 24 hours.</span></span> <span data-ttu-id="a3747-226">當標籤時是針對網站和群組進行設定時，請使用下列指導方針來為您的使用者發佈該標籤：</span><span class="sxs-lookup"><span data-stu-id="a3747-226">Use the following guidance to publish a label for your users when that label is configured for site and group settings:</span></span>

1. <span data-ttu-id="a3747-227">建立及設定敏感度標籤之後，請將此標籤新增至只適用一些測試使用者的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="a3747-227">After you create and configure the sensitivity label, add this label to a label policy that applies to just a few test users.</span></span>

2. <span data-ttu-id="a3747-228">等候複寫變更：</span><span class="sxs-lookup"><span data-stu-id="a3747-228">Wait for the change to replicate:</span></span>

   - <span data-ttu-id="a3747-229">新標籤：等待 1 小時。</span><span class="sxs-lookup"><span data-stu-id="a3747-229">New label: Wait for one hour.</span></span>
   - <span data-ttu-id="a3747-230">現有標籤：等候 24 小時。</span><span class="sxs-lookup"><span data-stu-id="a3747-230">Existing label: Wait for 24 hours.</span></span>

3. <span data-ttu-id="a3747-231">在此等候期間之後，請使用其中一個測試使用者帳戶來建立小組、Microsoft 365 群組或 SharePoint 網站，並搭配您在步驟 1 中建立的標籤。</span><span class="sxs-lookup"><span data-stu-id="a3747-231">After this wait period, use one of the test user accounts to create a team, Microsoft 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="a3747-232">如果在此建立作業期間沒有發生任何錯誤，您便知道可以安全地將標籤發佈給租用戶中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="a3747-232">If there are no errors during this creation operation, you know it's safe to publish the label to all users in your tenant.</span></span>

### <a name="modifying-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="a3747-233">修改針對網站和群組設定的已發佈標籤</span><span class="sxs-lookup"><span data-stu-id="a3747-233">Modifying published labels that are configured for sites and groups</span></span>

<span data-ttu-id="a3747-234">最佳做法是，不要在將標籤套用至小組、群組或網站之後，變更敏感度標籤的網站和群組設定。</span><span class="sxs-lookup"><span data-stu-id="a3747-234">As a best practice, don't change the site and group settings for a sensitivity label after the label has been applied to teams, groups, or sites.</span></span> <span data-ttu-id="a3747-235">如果您這麼做，請等候最多 24 小時的時間，讓變更複寫至已套用標籤的所有容器。</span><span class="sxs-lookup"><span data-stu-id="a3747-235">If you do, remember to wait for 24 hours for the changes to replicate to all containers that have the label applied.</span></span>

<span data-ttu-id="a3747-236">此外，如果您的變更包括 [外部使用者存取] 設定：</span><span class="sxs-lookup"><span data-stu-id="a3747-236">In addition, if your changes include the **External users access** setting:</span></span>

- <span data-ttu-id="a3747-237">新設定會套用至新使用者，但不會套用至現有使用者。</span><span class="sxs-lookup"><span data-stu-id="a3747-237">The new setting applies to new users but not to existing users.</span></span> <span data-ttu-id="a3747-238">例如，如果先前已選取此設定，且因此來賓使用者可存取網站，在標籤設定中清除此設定之後，這些來賓使用者仍然可以存取網站。</span><span class="sxs-lookup"><span data-stu-id="a3747-238">For example, if this setting was previously selected and as a result, guest users accessed the site, these guest users can still access the site after this setting is cleared in the label configuration.</span></span>

- <span data-ttu-id="a3747-239">群組屬性 hiddenMembership 和 roleEnabled 的隱私權設定不會更新。</span><span class="sxs-lookup"><span data-stu-id="a3747-239">The privacy settings for the group properties hiddenMembership and roleEnabled aren't updated.</span></span>

### <a name="deleting-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="a3747-240">刪除針對網站和群組設定的已發佈標籤</span><span class="sxs-lookup"><span data-stu-id="a3747-240">Deleting published labels that are configured for sites and groups</span></span>

<span data-ttu-id="a3747-241">如果您刪除已啟用網站和群組設定的敏感度標籤，且該標籤包含在一或多個標籤原則中，此動作可能會導致新小組、群組和網站建立失敗。</span><span class="sxs-lookup"><span data-stu-id="a3747-241">If you delete a sensitivity label that has the site and group settings enabled, and that label is included in one or more label policies, this action can result in creation failures for new teams, groups, and sites.</span></span> <span data-ttu-id="a3747-242">若要避免此情況，請使用下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="a3747-242">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="a3747-243">從包含標籤的所有標籤原則中移除敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="a3747-243">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="a3747-244">請等候 1 小時。</span><span class="sxs-lookup"><span data-stu-id="a3747-244">Wait for one hour.</span></span>

3. <span data-ttu-id="a3747-245">在此等候期間之後，請嘗試建立小組、群組或網站，並確認標籤已不再顯示。</span><span class="sxs-lookup"><span data-stu-id="a3747-245">After this wait period, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="a3747-246">如果敏感度標籤未顯示，您現在可以放心地刪除標籤。</span><span class="sxs-lookup"><span data-stu-id="a3747-246">If the sensitivity label isn't visible, you can now safely delete the label.</span></span>

## <a name="how-to-apply-sensitivity-labels-to-containers"></a><span data-ttu-id="a3747-247">如何將敏感度標籤套用至容器</span><span class="sxs-lookup"><span data-stu-id="a3747-247">How to apply sensitivity labels to containers</span></span>

<span data-ttu-id="a3747-248">您現在可以將敏感度標籤或標籤套用至下列容器：</span><span class="sxs-lookup"><span data-stu-id="a3747-248">You're now ready to apply the sensitivity label or labels to the following containers:</span></span>

- [<span data-ttu-id="a3747-249">Azure AD 中的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="a3747-249">Microsoft 365 group in Azure AD</span></span>](#apply-sensitivity-labels-to-microsoft-365-groups)
- [<span data-ttu-id="a3747-250">Microsoft Teams 小組網站</span><span class="sxs-lookup"><span data-stu-id="a3747-250">Microsoft Teams team site</span></span>](#apply-a-sensitivity-label-to-a-new-team)
- [<span data-ttu-id="a3747-251">Outlook 網頁版中的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="a3747-251">Microsoft 365 group in Outlook on the web</span></span>](#apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web)
- [<span data-ttu-id="a3747-252">SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="a3747-252">SharePoint site</span></span>](#apply-a-sensitivity-label-to-a-new-site)

<span data-ttu-id="a3747-253">如果您需要[將敏感度標籤套用至多個網站](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites)，您可以使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a3747-253">You can use PowerShell if you need to [apply a sensitivity label to multiple sites](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites).</span></span>

### <a name="apply-sensitivity-labels-to-microsoft-365-groups"></a><span data-ttu-id="a3747-254">將敏感度標籤套用至 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="a3747-254">Apply sensitivity labels to Microsoft 365 groups</span></span>

<span data-ttu-id="a3747-255">您現在可以將敏感度標籤或標籤套用至 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="a3747-255">You're now ready to apply the sensitivity label or labels to Microsoft 365 groups.</span></span> <span data-ttu-id="a3747-256">如需指示，請返回 Azure AD 文件：</span><span class="sxs-lookup"><span data-stu-id="a3747-256">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="a3747-257">在 Azure 入口網站中將標籤指派至新群組</span><span class="sxs-lookup"><span data-stu-id="a3747-257">Assign a label to a new group in Azure portal</span></span>](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

- [<span data-ttu-id="a3747-258">在 Azure 入口網站中將標籤指派至現有群組</span><span class="sxs-lookup"><span data-stu-id="a3747-258">Assign a label to an existing group in Azure portal</span></span>](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

- <span data-ttu-id="a3747-259">[在 Azure 入口網站中將標籤從現有群組移除](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="a3747-259">[Remove a label from an existing group in Azure portal](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="a3747-260">將敏感度標籤套用至新的小組</span><span class="sxs-lookup"><span data-stu-id="a3747-260">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="a3747-261">當使用者在 Microsoft Teams 中建立新小組時，可選取敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="a3747-261">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="a3747-262">當使用者從 [敏感度] 下拉式功能表中選取標籤時，隱私權設定可能會變更以反映標籤設定。</span><span class="sxs-lookup"><span data-stu-id="a3747-262">When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration.</span></span> <span data-ttu-id="a3747-263">根據您為標籤選取的外部使用者存取設定，使用者可以或無法將組織外部的人員新增至小組。</span><span class="sxs-lookup"><span data-stu-id="a3747-263">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="a3747-264">深入了解 Teams 的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="a3747-264">Learn more about sensitivity labels for Teams</span></span>](/microsoftteams/sensitivity-labels)

![建立新小組時的隱私權設定](../media/privacy-setting-new-team.png)

<span data-ttu-id="a3747-266">建立小組之後，敏感度標籤會顯示在所有頻道的右上角。</span><span class="sxs-lookup"><span data-stu-id="a3747-266">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![敏感度標籤顯示在小組上](../media/privacy-setting-teams.png)

<span data-ttu-id="a3747-268">服務自動將相同的敏感度標籤套用至 Microsoft 365 群組和連線的 SharePoint 小組網站。</span><span class="sxs-lookup"><span data-stu-id="a3747-268">The service automatically applies the same sensitivity label to the Microsoft 365 group and the connected SharePoint team site.</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="a3747-269">在 Outlook 網頁版中將敏感度標籤套用至新的群組</span><span class="sxs-lookup"><span data-stu-id="a3747-269">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="a3747-270">在 Outlook 網頁版中，當您建立新的群組時，您可以選取或變更已發佈標籤的 **敏感度** 選項：</span><span class="sxs-lookup"><span data-stu-id="a3747-270">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![建立群組並選取 [敏感度] 底下的選項](../media/sensitivity-label-new-group.png)

### <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="a3747-272">將敏感度標籤套用至新的網站</span><span class="sxs-lookup"><span data-stu-id="a3747-272">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="a3747-273">系統管理員和使用者可以在[建立新式小組網站和通訊網站](/sharepoint/create-site-collection)時選取敏感度標籤，然後展開 [進階設定]：</span><span class="sxs-lookup"><span data-stu-id="a3747-273">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection), and expand **Advanced settings**:</span></span>

![建立網站並選取 [敏感度] 底下的選項](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="a3747-275">下拉式方塊會顯示所選項目的標籤名稱，[說明] 圖示則會顯示所有標籤名稱及其工具提示，以協助使用者判斷所要套用的正確標籤。</span><span class="sxs-lookup"><span data-stu-id="a3747-275">The dropdown box displays the label names for the selection, and the help icon displays all the label names with their tooltip, which can help users determine the correct label to apply.</span></span>

<span data-ttu-id="a3747-276">當標籤已套用，且使用者瀏覽至網站時，其便可看到標籤的名稱和所套用的原則。</span><span class="sxs-lookup"><span data-stu-id="a3747-276">When the label is applied, and users browse to the site, they see the name of the label and applied policies.</span></span> <span data-ttu-id="a3747-277">例如，此網站已加上 [機密] 標籤，且隱私權設定設為 [私人]：</span><span class="sxs-lookup"><span data-stu-id="a3747-277">For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span></span>

![已套用敏感度標籤的網站](../media/sensitivity-label-site.png)

### <a name="use-powershell-to-apply-a-sensitivity-label-to-multiple-sites"></a><span data-ttu-id="a3747-279">使用 PowerShell 將敏感度標籤套用至多個網站</span><span class="sxs-lookup"><span data-stu-id="a3747-279">Use PowerShell to apply a sensitivity label to multiple sites</span></span>

<span data-ttu-id="a3747-280">您可以從目前的 [SharePoint Online 管理命令介面](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 使用 [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) 和 [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) Cmdlet 搭配 *SensitivityLabel* 參數，將敏感度標籤套用至許多網站。</span><span class="sxs-lookup"><span data-stu-id="a3747-280">You can use the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) and [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) cmdlet with the *SensitivityLabel* parameter from the current [SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) to apply a sensitivity label to many sites.</span></span> <span data-ttu-id="a3747-281">網站可以是任何 SharePoint 網站集合，或 OneDrive 網站。</span><span class="sxs-lookup"><span data-stu-id="a3747-281">The sites can be any SharePoint site collection, or a OneDrive site.</span></span>

<span data-ttu-id="a3747-282">確定您有 SharePoint Online 管理命令介面的版本 16.0.19418.12000 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="a3747-282">Make sure you have version 16.0.19418.12000 or later of the SharePoint Online Management Shell.</span></span>

1. <span data-ttu-id="a3747-283">使用 [以系統管理員身分執行] 選項開啟 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="a3747-283">Open a PowerShell session with the **Run as Administrator** option.</span></span>

2. <span data-ttu-id="a3747-284">如果您不知道標籤 GUID：[連線至安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)，並取得敏感度標籤及其 GUID 清單。</span><span class="sxs-lookup"><span data-stu-id="a3747-284">If you don't know your label GUID: [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and get the list of sensitivity labels and their GUIDs.</span></span>

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. <span data-ttu-id="a3747-285">現在[連線至 SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)，並將標籤 GUID 儲存為變數。</span><span class="sxs-lookup"><span data-stu-id="a3747-285">Now [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and store your label GUID as a variable.</span></span> <span data-ttu-id="a3747-286">例如：</span><span class="sxs-lookup"><span data-stu-id="a3747-286">For example:</span></span>

   ```powershell
   $Id = [GUID]("e48058ea-98e8-4940-8db0-ba1310fd955e")
   ```

4. <span data-ttu-id="a3747-287">建立可找出在其 URL 中有共同識別字串的多個網站的新變數。</span><span class="sxs-lookup"><span data-stu-id="a3747-287">Create a new variable that identifies multiple sites that have an identifying string in common in their URL.</span></span> <span data-ttu-id="a3747-288">例如：</span><span class="sxs-lookup"><span data-stu-id="a3747-288">For example:</span></span>

   ```powershell
   $sites = Get-SPOSite -IncludePersonalSite $true -Limit all -Filter "Url -like 'documents"
   ```

5. <span data-ttu-id="a3747-289">執行下列命令，將標籤套用至這些網站。</span><span class="sxs-lookup"><span data-stu-id="a3747-289">Run the following command to apply the label to these sites.</span></span> <span data-ttu-id="a3747-290">使用我們的範例：</span><span class="sxs-lookup"><span data-stu-id="a3747-290">Using our examples:</span></span>

   ```powershell
   $sites | ForEach-Object {Set-SPOTenant $_.url -SensitivityLabel $Id}
   ```

<span data-ttu-id="a3747-291">這一系列命令可讓您以相同的敏感度標籤為租用戶中的多個網站標籤，這就是使用 Set-SPOTenant Cmdlet 的原因，而不是針對每個網站設定的 Set-SPOSite Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a3747-291">This series of commands lets you label multiple sites across your tenant with the same sensitivity label, which is why you use the Set-SPOTenant cmdlet, rather than the Set-SPOSite cmdlet that's for per-site configuration.</span></span> <span data-ttu-id="a3747-292">不過，當您需要針對每個網站重複下列命令，將不同的標籤套用至特定網站時，請使用 Set-SPOSite Cmdlet：`Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span><span class="sxs-lookup"><span data-stu-id="a3747-292">However, use the Set-SPOSite cmdlet when you need to apply a different label to specific sites by repeating the following command for each of these sites: `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span></span>

## <a name="view-and-manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="a3747-293">在 SharePoint 系統管理中心檢視和管理敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="a3747-293">View and manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="a3747-294">若要檢視、排序和搜尋套用的敏感度標籤，請使用新 SharePoint 系統管理中心的 [使用中網站] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a3747-294">To view, sort, and search the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="a3747-295">您可能需要先新增 **[敏感度]** 欄：</span><span class="sxs-lookup"><span data-stu-id="a3747-295">You might need to first add the **Sensitivity** column:</span></span>

![[使用中網站] 頁面上的 [敏感度] 欄](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="a3747-297">如需從 [作用中網站] 頁面管理網站的詳細資訊，包括如何新增欄，請參閱[在新的 SharePoint 系統管理中心管理網站](/sharepoint/manage-sites-in-new-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="a3747-297">For more information about managing sites from the Active sites page, including how to add a column, see [Manage sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

<span data-ttu-id="a3747-298">您也可以從本頁面變更及套用標籤：</span><span class="sxs-lookup"><span data-stu-id="a3747-298">You can also change and apply a label from this page:</span></span>

1. <span data-ttu-id="a3747-299">選取網站名稱以開啟詳細資料窗格。</span><span class="sxs-lookup"><span data-stu-id="a3747-299">Select the site name to open the details pane.</span></span>

2. <span data-ttu-id="a3747-300">選取 [原則] 索引標籤，然後選取 [敏感度] 設定的 [編輯]。</span><span class="sxs-lookup"><span data-stu-id="a3747-300">Select the **Policies** tab, and then select **Edit** for the **Sensitivity** setting.</span></span>

3. <span data-ttu-id="a3747-301">從 [編輯敏感度設定] 窗格中，選取您要套用至網站的敏感度標籤，然後選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="a3747-301">From the **Edit sensitivity setting** pane, select the sensitivity label you want to apply to the site, and then select **Save**.</span></span>

## <a name="support-for-sensitivity-labels"></a><span data-ttu-id="a3747-302">支援敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="a3747-302">Support for sensitivity labels</span></span>

<span data-ttu-id="a3747-303">下列應用程式與服務支援針對網站和群組進行設定的敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="a3747-303">The following apps and services support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="a3747-304">系統管理中心：</span><span class="sxs-lookup"><span data-stu-id="a3747-304">Admin centers:</span></span>

  - <span data-ttu-id="a3747-305">SharePoint 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="a3747-305">SharePoint admin center</span></span>
  - <span data-ttu-id="a3747-306">Azure Active Directory 入口網站</span><span class="sxs-lookup"><span data-stu-id="a3747-306">Azure Active Directory portal</span></span>
  - <span data-ttu-id="a3747-307">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="a3747-307">Microsoft 365 admin center</span></span>
  - <span data-ttu-id="a3747-308">Microsoft 365 合規性中心、Microsoft 365 安全性中心、安全性與合規性中心</span><span class="sxs-lookup"><span data-stu-id="a3747-308">Microsoft 365 compliance center, Microsoft 365 security center, Security & Compliance Center</span></span>

- <span data-ttu-id="a3747-309">使用者應用程式與服務：</span><span class="sxs-lookup"><span data-stu-id="a3747-309">User apps and services:</span></span>

  - <span data-ttu-id="a3747-310">SharePoint</span><span class="sxs-lookup"><span data-stu-id="a3747-310">SharePoint</span></span>
  - <span data-ttu-id="a3747-311">Teams</span><span class="sxs-lookup"><span data-stu-id="a3747-311">Teams</span></span>
  - <span data-ttu-id="a3747-312">Outlook 網頁版和 Windows 版、macOS 版、iOS 版及 Android 版</span><span class="sxs-lookup"><span data-stu-id="a3747-312">Outlook on the web and for Windows, macOS, iOS, and Android</span></span>
  - <span data-ttu-id="a3747-313">Forms</span><span class="sxs-lookup"><span data-stu-id="a3747-313">Forms</span></span>
  - <span data-ttu-id="a3747-314">Stream</span><span class="sxs-lookup"><span data-stu-id="a3747-314">Stream</span></span>
  - <span data-ttu-id="a3747-315">Planner</span><span class="sxs-lookup"><span data-stu-id="a3747-315">Planner</span></span> 

<span data-ttu-id="a3747-316">下列應用程式與服務目前不支援針對網站和群組進行設定的敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="a3747-316">The following apps and services don't currently support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="a3747-317">系統管理中心：</span><span class="sxs-lookup"><span data-stu-id="a3747-317">Admin centers:</span></span>

  - <span data-ttu-id="a3747-318">Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="a3747-318">Teams admin center</span></span>
  - <span data-ttu-id="a3747-319">Exchange 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="a3747-319">Exchange admin center</span></span>

- <span data-ttu-id="a3747-320">使用者應用程式與服務：</span><span class="sxs-lookup"><span data-stu-id="a3747-320">User apps and services:</span></span>

  - <span data-ttu-id="a3747-321">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a3747-321">Dynamics 365</span></span>
  - <span data-ttu-id="a3747-322">Yammer</span><span class="sxs-lookup"><span data-stu-id="a3747-322">Yammer</span></span>
  - <span data-ttu-id="a3747-323">Project</span><span class="sxs-lookup"><span data-stu-id="a3747-323">Project</span></span>
  - <span data-ttu-id="a3747-324">Power BI</span><span class="sxs-lookup"><span data-stu-id="a3747-324">Power BI</span></span>

## <a name="classic-azure-ad-group-classification"></a><span data-ttu-id="a3747-325">傳統 Azure AD 群組分類</span><span class="sxs-lookup"><span data-stu-id="a3747-325">Classic Azure AD group classification</span></span>

<span data-ttu-id="a3747-326">啟用容器的敏感度標籤之後，Microsoft 365 不再針對新的 Microsoft 365 群組和 SharePoint 網站支援舊分類。</span><span class="sxs-lookup"><span data-stu-id="a3747-326">Microsoft 365 no longer supports the old classifications for new Microsoft 365 groups and SharePoint sites after you enable sensitivity labels for containers.</span></span> <span data-ttu-id="a3747-327">不過，支援敏感度標籤的現有的群組和網站仍會顯示舊的分類值，直到您轉換它們以使用敏感度標籤為止。</span><span class="sxs-lookup"><span data-stu-id="a3747-327">However, existing groups and sites that support sensitivity labels still display the old classification values until you convert them to use sensitivity labels.</span></span>

<span data-ttu-id="a3747-328">如需您先前可能使用的 SharePoint 舊群組分類範例，請參閱 [SharePoint 新式網站分類](/sharepoint/dev/solution-guidance/modern-experience-site-classification)。</span><span class="sxs-lookup"><span data-stu-id="a3747-328">As an example of how you might have used the old group classification for SharePoint, see [SharePoint "modern" sites classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="a3747-329">這些分類是使用 Azure AD PowerShell 或 PnP 核心程式庫來設定，並定義 `ClassificationList` 設定的值。</span><span class="sxs-lookup"><span data-stu-id="a3747-329">These classifications were configured by using Azure AD PowerShell or the PnP Core library and defining values for the `ClassificationList` setting.</span></span> <span data-ttu-id="a3747-330">如果您的租用戶已定義分類值，當您從 [AzureADPreview PowerShell 模組](https://www.powershellgallery.com/packages/AzureADPreview)執行下列命令時，會顯示這些值：</span><span class="sxs-lookup"><span data-stu-id="a3747-330">If your tenant has classification values defined, they are shown when you run the following command from the [AzureADPreview PowerShell module](https://www.powershellgallery.com/packages/AzureADPreview):</span></span>

```powershell
($setting["ClassificationList"])
```

<span data-ttu-id="a3747-331">若要將舊分類轉換成敏感度標籤，請執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="a3747-331">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="a3747-332">使用現有的標籤：編輯已發佈的現有敏感度標籤，以指定網站和群組需要的標籤設定。</span><span class="sxs-lookup"><span data-stu-id="a3747-332">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="a3747-333">建立新標籤：建立及發佈與現有分類名稱相同的新敏感度標籤，以指定網站和群組需要的標籤設定。</span><span class="sxs-lookup"><span data-stu-id="a3747-333">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="a3747-334">然後：</span><span class="sxs-lookup"><span data-stu-id="a3747-334">Then:</span></span>

1. <span data-ttu-id="a3747-335">使用 PowerShell，利用名稱對應將敏感度標籤套用至現有的 Microsoft 365 群組和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="a3747-335">Use PowerShell to apply the sensitivity labels to existing Microsoft 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="a3747-336">請參閱下一節的指示。</span><span class="sxs-lookup"><span data-stu-id="a3747-336">See the next section for instructions.</span></span>

2. <span data-ttu-id="a3747-337">移除現有群組和網站的舊分類。</span><span class="sxs-lookup"><span data-stu-id="a3747-337">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="a3747-338">雖然您無法防止使用者在尚未支援敏感度標籤的應用程式和服務中建立新群組，但您可以執行週期性 PowerShell 指令碼來尋找使用者使用舊分類建立的新群組，並將它們轉換成使用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="a3747-338">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span>

<span data-ttu-id="a3747-339">若要協助您管理網站和群組的敏感度標籤與 Azure AD 分類的共存，請參閱 [Microsoft 365 群組的 Azure Active Directory 分類和敏感度標籤](migrate-aad-classification-sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="a3747-339">To help you manage the coexistence of sensitivity labels and Azure AD classifications for sites and groups, see [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](migrate-aad-classification-sensitivity-labels.md).</span></span>

### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a><span data-ttu-id="a3747-340">使用 PowerShell 將 Microsoft 365 群組的分類轉換成敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="a3747-340">Use PowerShell to convert classifications for Microsoft 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="a3747-341">首先，[連線到安全性與合規性中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a3747-341">First, [connect to Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="a3747-342">例如，在您以系統管理員身分執行的 PowerShell 工作階段中，使用全域系統管理員帳戶登入：</span><span class="sxs-lookup"><span data-stu-id="a3747-342">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>

2. <span data-ttu-id="a3747-343">透過使用 [Get-Label](/powershell/module/exchange/get-label) Cmdlet，取得敏感度標籤和其 GUID 的清單：</span><span class="sxs-lookup"><span data-stu-id="a3747-343">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](/powershell/module/exchange/get-label) cmdlet:</span></span>

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. <span data-ttu-id="a3747-344">記下您要套用至 Microsoft 365 群組的敏感度標籤 GUID。</span><span class="sxs-lookup"><span data-stu-id="a3747-344">Make a note of the GUIDs for the sensitivity labels you want to apply to your Microsoft 365 groups.</span></span>

4. <span data-ttu-id="a3747-345">現在，在不同的 Windows PowerShell 視窗中 [連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a3747-345">Now [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a separate Windows PowerShell window.</span></span>

5. <span data-ttu-id="a3747-346">使用下列命令做為範例，以取得目前具有「一般」分類的群組清單：</span><span class="sxs-lookup"><span data-stu-id="a3747-346">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="a3747-p141">針對每個群組，新增新的敏感度標籤 GUID。例如：</span><span class="sxs-lookup"><span data-stu-id="a3747-p141">For each group, add the new sensitivity label GUID. For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. <span data-ttu-id="a3747-349">針對其餘的群組分類重複步驟 5 和 6。</span><span class="sxs-lookup"><span data-stu-id="a3747-349">Repeat steps 5 and 6 for your remaining group classifications.</span></span>

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="a3747-350">稽核敏感度標籤活動</span><span class="sxs-lookup"><span data-stu-id="a3747-350">Auditing sensitivity label activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3747-351">如果您使用標籤分離，只選擇保護容器的 **群組和網站** 標籤範圍：由於 **偵測到的檔案敏感度等級不符合** 本節內容所述的稽核活動及電子郵件，須 [將這些標籤排序](sensitivity-labels.md#label-priority-order-matters) 在具有 **檔案和電子郵件** 範圍的標籤之前。 </span><span class="sxs-lookup"><span data-stu-id="a3747-351">If you use label separation by selecting just the **Groups & sites** scope for labels that protect containers: Because of the **Detected document sensitivity mismatch** audit event and email described in this section, consider [ordering these labels](sensitivity-labels.md#label-priority-order-matters) before labels that have a scope for **Files & emails**.</span></span> 

<span data-ttu-id="a3747-352">若某使用者將文件上傳到受敏感度標籤保護的網站，且文件的敏感度標籤[優先於](sensitivity-labels.md#label-priority-order-matters)網站的敏感度標籤，則不會封鎖此動作。</span><span class="sxs-lookup"><span data-stu-id="a3747-352">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="a3747-353">例如，您已將 **一般** 標籤套用至 SharePoint 網站，而某使用者上傳到此網站的文件標示為 **機密**。</span><span class="sxs-lookup"><span data-stu-id="a3747-353">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="a3747-354">由於優先順序較高的敏感度標籤會識別比優先順序較低的內容更具敏感度的內容，因此可能會造成安全性問題。</span><span class="sxs-lookup"><span data-stu-id="a3747-354">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="a3747-355">儘管系統不會封鎖該動作，但會稽核，且會產生電子郵件給上傳文件的人員和網站系統管理員。</span><span class="sxs-lookup"><span data-stu-id="a3747-355">Although the action isn't blocked, it is audited and automatically generates an email to the person who uploaded the document and the site administrator.</span></span> <span data-ttu-id="a3747-356">因此使用者和系統管理員可以找出與標籤優先順序不一致的文件，並視需要採取行動。</span><span class="sxs-lookup"><span data-stu-id="a3747-356">As a result, both the user and administrators can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="a3747-357">例如，從網站刪除或移動已上傳的文件。</span><span class="sxs-lookup"><span data-stu-id="a3747-357">For example, delete or move the uploaded document from the site.</span></span>

<span data-ttu-id="a3747-358">如果文件套用的敏感度標籤，其優先順序低於網站所套用的敏感度標籤，則不會造成安全性問題。</span><span class="sxs-lookup"><span data-stu-id="a3747-358">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="a3747-359">例如，套用 **「一般」** 標籤的文件上傳到標記為 **「機密」** 的網站。</span><span class="sxs-lookup"><span data-stu-id="a3747-359">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="a3747-360">在此案例中，不會產生稽核事件和電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a3747-360">In this scenario, an auditing event and email aren't generated.</span></span>

<span data-ttu-id="a3747-361">若要搜尋此事件的稽核記錄，請尋找 **[檔案與頁面活動]** 類別中的 **[偵測到的文件敏感度不相符]**。</span><span class="sxs-lookup"><span data-stu-id="a3747-361">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span>

<span data-ttu-id="a3747-362">自動產生電子郵件的 [主旨] 為 **偵測到不相容敏感度標籤**，而電子郵件訊息則會有上傳文件和網站連結的標記不相符說明。</span><span class="sxs-lookup"><span data-stu-id="a3747-362">The automatically generated email has the subject **Incompatible sensitivity label detected** and the email message explains the labeling mismatch with a link to the uploaded document and site.</span></span> <span data-ttu-id="a3747-363">它也包含說明使用者可如何變更敏感度標籤的文件連結。</span><span class="sxs-lookup"><span data-stu-id="a3747-363">It also contains a documentation link that explains how users can change the sensitivity label.</span></span> <span data-ttu-id="a3747-364">目前無法停用或自訂這些自動電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a3747-364">Currently, these automated emails cannot be disabled or customized.</span></span>

<span data-ttu-id="a3747-365">當某人在網站或群組間新增或移除敏感度標籤時，系統也會稽核這些活動，但不會自動產生電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a3747-365">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited but without automatically generating an email.</span></span>

<span data-ttu-id="a3747-366">您可以在 [[敏感度標籤活動]](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) 類別中找到所有這些稽核事件。</span><span class="sxs-lookup"><span data-stu-id="a3747-366">All these auditing events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> <span data-ttu-id="a3747-367">如需搜尋稽核記錄的指示，請參閱[在安全性與合規性中心搜尋稽核記錄](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="a3747-367">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="how-to-disable-sensitivity-labels-for-containers"></a><span data-ttu-id="a3747-368">如何停用容器的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="a3747-368">How to disable sensitivity labels for containers</span></span>

<span data-ttu-id="a3747-369">您可以使用來自[啟用 PowerShell 中的敏感度標籤支援](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell)中的相同指示來關閉 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="a3747-369">You can turn off sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="a3747-370">不過，若要停用此功能，請在步驟 5 中指定 `$setting["EnableMIPLabels"] = "False"`。</span><span class="sxs-lookup"><span data-stu-id="a3747-370">However, to disable the feature, in step 5, specify `$setting["EnableMIPLabels"] = "False"`.</span></span>

<span data-ttu-id="a3747-371">除了在建立或編輯敏感度標籤時隱藏所有的群組和網站設定 ，此動作會還原容器用於其設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="a3747-371">In addition to making all the settings unavailable for groups and sites when you create or edit sensitivity labels, this action reverts which property the containers use for their configuration.</span></span> <span data-ttu-id="a3747-372">為 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站啟用敏感度標籤，會將使用的屬性從 [分類] (用於 [Azure AD 群組分類](#classic-azure-ad-group-classification)) 切換為 [敏感度]。</span><span class="sxs-lookup"><span data-stu-id="a3747-372">Enabling sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites switches the property used from **Classification** (used for [Azure AD group classification](#classic-azure-ad-group-classification)) to **Sensitivity**.</span></span> <span data-ttu-id="a3747-373">停用容器的敏感度標籤時，容器會忽略 [敏感度] 屬性，並再次使用 [分類] 屬性。</span><span class="sxs-lookup"><span data-stu-id="a3747-373">When you disable sensitivity labels for containers, the containers ignore the Sensitivity property and use the Classification property again.</span></span>

<span data-ttu-id="a3747-374">這表示來自網站和群組、先前套用至容器的任何標籤設定都不會強制執行，而容器則不再顯示標籤。</span><span class="sxs-lookup"><span data-stu-id="a3747-374">This means that any label settings from sites and groups previously applied to containers won't be enforced, and containers no longer display the labels.</span></span>

<span data-ttu-id="a3747-375">如果這些容器已套用 Azure AD 分類值，則容器會再次還原為使用分類。</span><span class="sxs-lookup"><span data-stu-id="a3747-375">If these containers have Azure AD classification values applied to them, the containers revert to using the classifications again.</span></span> <span data-ttu-id="a3747-376">請注意，啟用功能之後所建立的任何新網站或群組都不會顯示標籤或具有分類。</span><span class="sxs-lookup"><span data-stu-id="a3747-376">Be aware that any new sites or groups that were created after enabling the feature won't display a label or have a classification.</span></span> <span data-ttu-id="a3747-377">針對這些容器以及任何新容器，您現在可以套用分類值。</span><span class="sxs-lookup"><span data-stu-id="a3747-377">For these containers, and any new containers, you can now apply classification values.</span></span> <span data-ttu-id="a3747-378">如需詳細資訊，請參閱 [SharePoint「新式」網站分類](/sharepoint/dev/solution-guidance/modern-experience-site-classification)和[為組織中的 Office 群組建立分類](../enterprise/manage-microsoft-365-groups-with-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="a3747-378">For more information, see [SharePoint "modern" sites classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) and [Create classifications for Office groups in your organization](../enterprise/manage-microsoft-365-groups-with-powershell.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a3747-379">其他資源</span><span class="sxs-lookup"><span data-stu-id="a3747-379">Additional resources</span></span>

<span data-ttu-id="a3747-380">如需有關[透過 Microsoft Teams、O365 群組和 SharePoint Online 網站使用敏感度標籤](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380) 的資訊，請參閱網路研討會的記錄和回答的問題。</span><span class="sxs-lookup"><span data-stu-id="a3747-380">See the webinar recording and answered questions for [Using Sensitivity labels with Microsoft Teams, O365 Groups and SharePoint Online sites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span></span>

<span data-ttu-id="a3747-381">此網路研討會錄製時該功能仍處於預覽，因此您可能會發現 UI 中有部分差異。</span><span class="sxs-lookup"><span data-stu-id="a3747-381">This webinar was recorded when the feature was still in preview, so you might notice some discrepancies in the UI.</span></span> <span data-ttu-id="a3747-382">不過，此功能的資訊仍會是正確的，且此頁面上會記載任何新功能。</span><span class="sxs-lookup"><span data-stu-id="a3747-382">However, the information for this feature is still accurate, with any new capabilities documented on this page.</span></span>