---
title: 搜尋內部部署使用者的 Teams 聊天資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: 使用安全性與合規性中心的內容搜尋工具，在 Exchange 混合式部署中搜尋及匯出內部部署使用者的 Microsoft Teams 聊天資料。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 39951ce125f86748beab12cf1998075e26ad734b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917185"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a><span data-ttu-id="95218-103">搜尋內部部署使用者的 Teams 聊天資料</span><span class="sxs-lookup"><span data-stu-id="95218-103">Search for Teams chat data for on-premises users</span></span>

<span data-ttu-id="95218-104">如果貴組織使用 Exchange 混合式部署 (或將內部部署的 Exchange 組織與 Office 365 同步)，且已啟用 Microsoft Teams，則內部部署使用者可以使用 Teams 聊天應用程式傳遞立即訊息。</span><span class="sxs-lookup"><span data-stu-id="95218-104">If your organization has an Exchange hybrid deployment (or your organization synchronizes an on-premises Exchange organization with Office 365) and has enabled Microsoft Teams, on-premises users can use the Teams chat application for instant messaging.</span></span> <span data-ttu-id="95218-105">針對雲端式使用者，Teams 聊天資料 (又稱為 *1 對 1 或 1 對多聊天*) 會儲存到其主要雲端式信箱。</span><span class="sxs-lookup"><span data-stu-id="95218-105">For a cloud-based user, Teams chat data (also called *1x1 or 1xN chats*) is saved to their primary cloud-based mailbox.</span></span> <span data-ttu-id="95218-106">內部部署使用者使用 Teams 聊天應用程式時，其聊天訊息無法儲存在其主要信箱 (位於內部部署)。</span><span class="sxs-lookup"><span data-stu-id="95218-106">When an on-premises user uses the Teams chat application, their chat messages can't be stored in their primary mailbox, which is located on-premises.</span></span> <span data-ttu-id="95218-107">為了避免此限制，Microsoft 已發佈新功能，其中建立了雲端式儲存區，以便您可以使用電子文件探索工具來搜尋及匯出內部部署使用者的 Teams 聊天資料。</span><span class="sxs-lookup"><span data-stu-id="95218-107">To get around this limitation, Microsoft has released a new feature where a cloud-based storage area is created so that you use eDiscovery tools to search for and export Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="95218-108">以下是為內部部署使用者啟用雲端式儲存體的要求和限制：</span><span class="sxs-lookup"><span data-stu-id="95218-108">Here are the requirements and limitations for enabling cloud-based storage for on-premises users:</span></span>
  
- <span data-ttu-id="95218-109">內部部署目錄服務 (例如 Active Directory) 的使用者帳戶必須與 Azure Active Directory (Microsoft 365 中的目錄服務) 同步。</span><span class="sxs-lookup"><span data-stu-id="95218-109">The user accounts in your on-premises directory service (such as Active Directory) must be synchronized with Azure Active Directory, the directory service in Microsoft 365.</span></span> <span data-ttu-id="95218-110">這表示會在 Microsoft 365 中建立郵件使用者帳戶，並將該帳戶與主要信箱位於內部部署組織中的使用者相關聯。</span><span class="sxs-lookup"><span data-stu-id="95218-110">This means that a mail user account is created in Microsoft 365 and is associated with a user whose primary mailbox is located in the on-premises organization.</span></span>

- <span data-ttu-id="95218-111">主要信箱位於內部部署組織中的使用者必須受指派 Microsoft Teams 授權和 Exchange Online 方案 1 授權 (最低要求)。</span><span class="sxs-lookup"><span data-stu-id="95218-111">The user whose primary mailbox is located in the on-premises organization must be assigned a Microsoft Teams license and a minimum of an Exchange Online Plan 1 license.</span></span>

- <span data-ttu-id="95218-112">如果組織沒有 Exchange 混合式部署，則必須將內部部署 Exchange 結構描述同步處理至 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="95218-112">If your organization doesn't have an Exchange hybrid deployment, you must synchronize your on-premises Exchange schema to Azure Active Directory.</span></span> <span data-ttu-id="95218-113">如果您沒有這樣做，則可能會有為在內部部署 Exchange 組織中擁有信箱的使用者，於 Exchange Online 中建立重複的雲端式信箱的風險。</span><span class="sxs-lookup"><span data-stu-id="95218-113">If you don't do this, you might risk creating duplicate cloud-based mailboxes in Exchange Online for users that have a mailbox in your on-premises Exchange organization.</span></span>

- <span data-ttu-id="95218-114">只有與內部部署使用者相關聯的 Teams 聊天資料才會儲存在雲端式儲存區中。</span><span class="sxs-lookup"><span data-stu-id="95218-114">Only Teams chat data associated with an on-premises user is stored in the cloud-based storage area.</span></span> <span data-ttu-id="95218-115">內部部署使用者無法以任何方式存取此儲存區。</span><span class="sxs-lookup"><span data-stu-id="95218-115">An on-premises user can't access this storage area in any way.</span></span>

> [!NOTE]
> <span data-ttu-id="95218-116">Teams 頻道交談一律會儲存在與團隊相關聯的雲端式信箱中，這表示您可以搜尋頻道交談。</span><span class="sxs-lookup"><span data-stu-id="95218-116">Teams channel conversations are always stored in the cloud-based mailbox that's associated with the Team, which means you can search for channel conversations.</span></span> <span data-ttu-id="95218-117">如需有關搜尋 Teams 頻道交談的詳細資訊，請參閱[搜尋 Microsoft Teams 和 Microsoft 365 群組](content-search.md#searching-microsoft-teams-and-microsoft-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="95218-117">For more information about searching Teams channel conversations, see [Searching Microsoft Teams and Microsoft 365 Groups](content-search.md#searching-microsoft-teams-and-microsoft-365-groups).</span></span>
  
## <a name="how-it-works"></a><span data-ttu-id="95218-118">運作方式</span><span class="sxs-lookup"><span data-stu-id="95218-118">How it works</span></span>

<span data-ttu-id="95218-119">如果已啟用 Microsoft Teams 的使用者具有內部部署信箱，且其使用者帳戶/身分識別已同步到雲端，Microsoft 會建立雲端式儲存體來與內部部署使用者的 1 對多 Teams 聊天資料產生關聯。</span><span class="sxs-lookup"><span data-stu-id="95218-119">If a Microsoft Teams-enabled user has an on-premises mailbox and their user account/identity has been synched to the cloud, Microsoft creates cloud-based storage to associate the on-premises user's 1xN Teams chat data with.</span></span> <span data-ttu-id="95218-120">系統會為內部部署使用者的 Teams 聊天資料編製索引，以便搜尋。</span><span class="sxs-lookup"><span data-stu-id="95218-120">Teams chat data for on-premises users is indexed for search.</span></span> <span data-ttu-id="95218-121">這可讓您使用內容搜尋 (以及與核心和進階電子文件探索案例相關聯的搜尋) 來搜尋、預覽及匯出內部部署使用者的 Teams 聊天資料。</span><span class="sxs-lookup"><span data-stu-id="95218-121">This lets you Use Content Search (and searches associated with Core and Advanced eDiscovery cases) to search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="95218-122">您也可以使用安全性與合規性中心 PowerShell 中的 **\*ComplianceSearch** Cmdlet 搜尋內部部署使用者的 Teams 聊天資料。</span><span class="sxs-lookup"><span data-stu-id="95218-122">You can also use **\*ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="95218-123">下圖顯示搜尋、預覽及匯出內部部署使用者的 Teams 聊天資料的工作流程。</span><span class="sxs-lookup"><span data-stu-id="95218-123">The following graphic shows the workflow of how Teams chat data for on-premises users is available to search, preview, and export.</span></span>
  
![Microsoft Teams 內部部署使用者的雲端式儲存空間](../media/EHAMShard1.png)
  
<span data-ttu-id="95218-125">除了這項新功能，您仍然可以使用內容搜尋來搜尋、預覽及匯出小組中與每個 Microsoft Team 相關聯的雲端式 SharePoint 網站和 Exchange 信箱中的 Teams 內容，以及雲端式使用者 Exchange Online 信箱中的 1xN Teams 聊天資料。</span><span class="sxs-lookup"><span data-stu-id="95218-125">In addition to this new capability, you can still use Content Search to search, preview, and export Teams content in the cloud-based SharePoint site and Exchange mailbox associated with each Microsoft Team and 1xN Teams chat data in the Exchange Online mailbox for cloud-based users.</span></span>


### <a name="what-happens-after-this-feature-is-enabled"></a><span data-ttu-id="95218-126">啟用此功能後會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="95218-126">What happens after this feature is enabled?</span></span>

<span data-ttu-id="95218-127">在貴組織中部署此功能後，便會在安全性與合規性中心的內容搜尋和與電子文件探索案例相關聯的搜尋中進行下列變更：</span><span class="sxs-lookup"><span data-stu-id="95218-127">After this feature is deployed in your organization, the following changes are made in Content Search and in searches associated with an eDiscovery case in the Security & Compliance Center:</span></span>
  
- <span data-ttu-id="95218-128">**[為內部部署使用者新增 Office App 內容]** 核取方塊會新增到內容搜尋中的 **[位置]** 底下。</span><span class="sxs-lookup"><span data-stu-id="95218-128">The **Add Office app content for on-premises users** checkbox is added under the **Locations** in Content Search.</span></span>

    ![[為內部部署使用者新增 Office App 內容] 核取方塊會新增到內容搜尋 UI](../media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- <span data-ttu-id="95218-130">內部部署使用者會顯示在用於選取要搜尋的使用者信箱的內容位置選擇器中。</span><span class="sxs-lookup"><span data-stu-id="95218-130">On-premises users are displayed in the content locations picker that you use to select user mailboxes to search.</span></span>

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a><span data-ttu-id="95218-131">搜尋內部部署使用者的 Teams 聊天內容</span><span class="sxs-lookup"><span data-stu-id="95218-131">Searching for Teams chat content for on-premises users</span></span>

<span data-ttu-id="95218-132">啟用此功能後，您可以使用安全性與合規性中心的內容搜尋來搜尋內部部署使用者的 Teams 聊天資料。</span><span class="sxs-lookup"><span data-stu-id="95218-132">After the feature has been enabled, you can use Content Search in the Security & Compliance Center to search for Teams chat data for on-premises users.</span></span>
  
1. <span data-ttu-id="95218-133">在安全性與合規性中心內，移至 **[搜尋]** \> **[內容搜尋]**。</span><span class="sxs-lookup"><span data-stu-id="95218-133">In the Security & Compliance Center, go to **Search** \> **Content search**</span></span>

2. <span data-ttu-id="95218-134">在 **[搜尋]** 頁面上，按一下![新增圖示](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **新增搜尋**。</span><span class="sxs-lookup"><span data-stu-id="95218-134">On the **Search** page, click ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span>

    <span data-ttu-id="95218-135">如先前所述，**[為內部部署使用者新增 Office App 內容]** 核取方塊會顯示在 **[位置]** 底下。</span><span class="sxs-lookup"><span data-stu-id="95218-135">As previously explained, the **Add Office app content for on-premises users** checkbox is displayed under **Locations**.</span></span> <span data-ttu-id="95218-136">此為預設選取的選項。</span><span class="sxs-lookup"><span data-stu-id="95218-136">It's selected by default.</span></span>

3. <span data-ttu-id="95218-137">視需要建立關鍵字查詢，並將條件新增至搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="95218-137">Create the keyword query and add conditions to the search query if necessary.</span></span> <span data-ttu-id="95218-138">若只要搜尋 Team 聊天資料，您可以在 **[關鍵字]** 方塊中新增下列查詢：</span><span class="sxs-lookup"><span data-stu-id="95218-138">To only search for Team chats data, you can add the following query in the **Keywords** box:</span></span>

    ```text
    kind:im
    ```

4. <span data-ttu-id="95218-139">此時，您可以在 **[位置]** 底下選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="95218-139">At this point, you can choose one of the following options under **Locations**:</span></span>

    - <span data-ttu-id="95218-140">**所有位置：** 選取此選項以搜尋貴組織中所有使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="95218-140">**All locations:** Select this option to search the mailboxes of all users in your organization.</span></span> <span data-ttu-id="95218-141">勾選此核取方塊時，系統也會搜尋內部部署使用者的 Teams 聊天資料的所有雲端式儲存體。</span><span class="sxs-lookup"><span data-stu-id="95218-141">When the checkbox is selected, all cloud-based storage of Teams chat data for on-premises users will also be searched.</span></span>

    - <span data-ttu-id="95218-142">**特定位置：** 勾選此選項，然後按一下 [修改 **]** \> 選擇使用者、群組或團隊來搜尋特定信箱。</span><span class="sxs-lookup"><span data-stu-id="95218-142">**Specific locations:** Select this option and then click **Modify** \> Choose user, groups, or teams to search specific mailboxes.</span></span> <span data-ttu-id="95218-143">如先前所述，位置選擇器可讓您搜尋內部部署使用者的 Teams 聊天資料。</span><span class="sxs-lookup"><span data-stu-id="95218-143">As previously explained, the locations picker lets you search for Teams chat data for on-premises users.</span></span>

5. <span data-ttu-id="95218-144">儲存並執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="95218-144">Save and run the search.</span></span> <span data-ttu-id="95218-145">任何內部部署使用者的搜尋結果都可以像其他搜尋結果一樣預覽。</span><span class="sxs-lookup"><span data-stu-id="95218-145">Any search results for on-premises users can be previewed like any other search results.</span></span> <span data-ttu-id="95218-146">您也可以將搜尋結果 (包括任何 Teams 聊天資料) 匯出至 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="95218-146">You can also export the search results (including any Teams chat data) to a PST file.</span></span> <span data-ttu-id="95218-147">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="95218-147">For more information, see:</span></span>

    - [<span data-ttu-id="95218-148">建立搜尋</span><span class="sxs-lookup"><span data-stu-id="95218-148">Create a search</span></span>](content-search.md#create-a-search)

    - [<span data-ttu-id="95218-149">預覽搜尋結果</span><span class="sxs-lookup"><span data-stu-id="95218-149">Preview search results</span></span>](content-search.md#preview-search-results)

    - [<span data-ttu-id="95218-150">匯出內容搜尋結果</span><span class="sxs-lookup"><span data-stu-id="95218-150">Export Content Search results</span></span>](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a><span data-ttu-id="95218-151">使用 PowerShell 來搜尋內部部署使用者的 Teams 聊天資料</span><span class="sxs-lookup"><span data-stu-id="95218-151">Using PowerShell to search for Teams chat data for on-premises users</span></span>

<span data-ttu-id="95218-152">您可以在安全性與合規性中心 PowerShell 中使用 **New-ComplianceSearch** 和 **Set-ComplianceSearch** Cmdlet 來搜尋內部部署使用者的 Teams 聊天資料。</span><span class="sxs-lookup"><span data-stu-id="95218-152">You can use the **New-ComplianceSearch** and **Set-ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span> <span data-ttu-id="95218-153">如先前所述，您不需要提交支援要求，即可使用 PowerShell 來搜尋內部部署使用者的 Teams 聊天資料。</span><span class="sxs-lookup"><span data-stu-id="95218-153">As previously explained, you don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span>
  
1. <span data-ttu-id="95218-154">[連線到安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="95218-154">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="95218-155">執行下列 PowerShell 命令來建立可搜尋內部部署使用者 Teams 聊天資料的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="95218-155">Run the following PowerShell command to create a content search that searches for Teams chat data for on-premises users.</span></span>

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    <span data-ttu-id="95218-156">*IncludeUserAppContent* 參數是用於為 *ExchangeLocation* 參數指定的一位或多位使用者指定雲端式儲存體。</span><span class="sxs-lookup"><span data-stu-id="95218-156">The *IncludeUserAppContent*  parameter is used to specify the cloud-based storage for the user or users who are specified by the  *ExchangeLocation*  parameter.</span></span> <span data-ttu-id="95218-157">*AllowNotFoundExchangeLocationsEnabled* 能讓您為內部部署使用者搜尋雲端式儲存區。</span><span class="sxs-lookup"><span data-stu-id="95218-157">The *AllowNotFoundExchangeLocationsEnabled*  allows you to search the cloud-based storage for on-premises users.</span></span> <span data-ttu-id="95218-158">使用此參數的 `$true` 值時，搜尋在執行前不會嘗試驗證信箱是否存在。</span><span class="sxs-lookup"><span data-stu-id="95218-158">When you use the `$true` value for this parameter, the search doesn't try to validate the existence of the mailbox before it runs.</span></span> <span data-ttu-id="95218-159">這是搜尋內部部署使用者的雲端式儲存區所需，因為此雲端式儲存區無法解析為一般的雲端式信箱。</span><span class="sxs-lookup"><span data-stu-id="95218-159">This is required to search the cloud-based storage for on-premises users because this cloud-based storage doesn't resolve as a regular cloud-based mailbox.</span></span>

    <span data-ttu-id="95218-160">下列範例會在 Sara Davis 的雲端式儲存體中搜尋包含關鍵字 "redstone" 的 Teams 聊天 (立即訊息)，Sara Davis 是 Contoso 組織的內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="95218-160">The following example searches for Teams chats (which are instant messages) that contain keyword "redstone" in the cloud-based storage for Sara Davis, who is an on-premises user in the Contoso organization.</span></span>
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   <span data-ttu-id="95218-161">建立搜尋後，請務必使用 **Start-ComplianceSearch** Cmdlet 執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="95218-161">After you create a search, be sure to use the **Start-ComplianceSearch** cmdlet to run the search.</span></span> 
  
<span data-ttu-id="95218-162">如需使用這些 Cmdlet 的相關資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="95218-162">For more information using these cmdlets, see:</span></span>
  
- [<span data-ttu-id="95218-163">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="95218-163">New-ComplianceSearch</span></span>](/powershell/module/exchange/new-compliancesearch)

- [<span data-ttu-id="95218-164">Set-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="95218-164">Set-ComplianceSearch</span></span>](/powershell/module/exchange/set-compliancesearch)

- [<span data-ttu-id="95218-165">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="95218-165">Start-ComplianceSearch</span></span>](/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a><span data-ttu-id="95218-166">已知問題</span><span class="sxs-lookup"><span data-stu-id="95218-166">Known issues</span></span>

- <span data-ttu-id="95218-167">目前，您可以搜尋、預覽及匯出內部部署使用者的 Teams 聊天資料。</span><span class="sxs-lookup"><span data-stu-id="95218-167">Currently, you can search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="95218-168">您也可以將內部部署使用者的 Teams 聊天資料置於與核心或進階電子文件探索案例相關聯的保留中，並為內部部署使用者的 Teams 聊天或頻道訊息套用保留原則。</span><span class="sxs-lookup"><span data-stu-id="95218-168">You can also place the Teams chat data for an on-premises user on a hold associated with a Core or Advanced eDiscovery case, and apply a retention policy for Teams chats or channel messages for on-premises users.</span></span> <span data-ttu-id="95218-169">不過，目前無法為內部部署使用者套用其他內容位置 (例如 Exchange 信箱和 SharePoint 網站) 的保留原則。</span><span class="sxs-lookup"><span data-stu-id="95218-169">However at this time, you can't apply a retention policy for other content locations (such as Exchange mailboxes and SharePoint sites) for on-premises users.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="95218-170">常見問題集</span><span class="sxs-lookup"><span data-stu-id="95218-170">Frequently asked questions</span></span>

<span data-ttu-id="95218-171">**內部部署使用者的雲端儲存區位在何處？**</span><span class="sxs-lookup"><span data-stu-id="95218-171">**Where is the cloud-based storage for on-premises users located?**</span></span>
  
<span data-ttu-id="95218-172">Teams 交談資料會儲存在內部部署使用者的慣用資料位置 (PDL)。</span><span class="sxs-lookup"><span data-stu-id="95218-172">Teams chat data is stored in the Preferred Data Location (PDL) for an on-premises user.</span></span> <span data-ttu-id="95218-173">PDL 可在單一地理位置和多地理位置環境中採用。</span><span class="sxs-lookup"><span data-stu-id="95218-173">The PDL is honored in both Single-Geo and Multi-Geo environments.</span></span> <span data-ttu-id="95218-174">如需詳細資訊，請參閱 [Microsoft 365 多地理位置](../enterprise/microsoft-365-multi-geo.md)。</span><span class="sxs-lookup"><span data-stu-id="95218-174">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>
  
 <span data-ttu-id="95218-175">**除了提交支援要求外，還有其他需求嗎？**</span><span class="sxs-lookup"><span data-stu-id="95218-175">**Are there any other requirements other than submitting a support request?**</span></span>
  
<span data-ttu-id="95218-176">如先前所述，內部部署信箱的使用者身分識別必須同步到雲端式組織，以便為 Office 365 中每個內部部署使用者帳戶建立對應的郵件使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="95218-176">As previously explained, the identities of users with on-prem mailboxes must be synchronized to your cloud-based organization so that a corresponding mail user account is created for each on-premises user account in Office 365.</span></span> <span data-ttu-id="95218-177">貴組織還必須具有 Office 365 企業版訂閱，例如 Office 365 企業版 E1、E3 或 E5 訂閱。</span><span class="sxs-lookup"><span data-stu-id="95218-177">Your organization must also have an Office 365 enterprise subscription, such as an Office 365 Enterprise E1, E3, or E5 subscription.</span></span>
  
 <span data-ttu-id="95218-178">**如果使用者的內部部署信箱已移轉至雲端，是否有遺失 Teams 聊天資料的風險？**</span><span class="sxs-lookup"><span data-stu-id="95218-178">**Is there a risk of losing the Teams chat data if the user's on-premises mailbox is migrated to the cloud?**</span></span>
  
<span data-ttu-id="95218-179">否。</span><span class="sxs-lookup"><span data-stu-id="95218-179">No.</span></span> <span data-ttu-id="95218-180">將內部部署使用者的主要信箱移轉到雲端時，該使用者的 Teams 聊天資料就會移轉至新的雲端式主要信箱。</span><span class="sxs-lookup"><span data-stu-id="95218-180">When you migrate the primary mailbox of an on-premises user to the cloud, the Teams chat data for that user will be migrated to their new cloud-based primary mailbox.</span></span>
  
 <span data-ttu-id="95218-181">**可以將電子文件探索保留或保留原則套用至內部部署使用者嗎？**</span><span class="sxs-lookup"><span data-stu-id="95218-181">**Can I apply an eDiscovery hold or retention policies to on-premises users?**</span></span>
  
<span data-ttu-id="95218-182">是。</span><span class="sxs-lookup"><span data-stu-id="95218-182">Yes.</span></span> <span data-ttu-id="95218-183">您可以為內部部署使用者的 Teams 聊天和頻道訊息套用電子文件探索保留或保留原則。</span><span class="sxs-lookup"><span data-stu-id="95218-183">You can apply eDiscovery holds or retention policies for Teams chats and channel messages of on-premises users.</span></span>
  
 <span data-ttu-id="95218-184">**在組織提交啟用此功能的要求之前，內容搜尋是否能找到內部部署使用者較早的 Teams 聊天資料？**</span><span class="sxs-lookup"><span data-stu-id="95218-184">**Can Content Search find older Teams chat data for on-premises users before the time my organization submitted the request to enable this feature?**</span></span>
  
<span data-ttu-id="95218-185">Microsoft 於 2018 年 1 月 31 日開始儲存內部部署使用者的 Teams 聊天資料。</span><span class="sxs-lookup"><span data-stu-id="95218-185">Microsoft started storing the Teams chat data for on-premises users on January 31, 2018.</span></span> <span data-ttu-id="95218-186">因此，如果內部部署 Teams 使用者的身分識別已在 Active Directory 和 Azure Active Directory 之間同步，則自該日起，其 Teams 聊天資料會儲存在雲端，並可使用內容搜尋來搜尋。</span><span class="sxs-lookup"><span data-stu-id="95218-186">So, if the identity of an on-premises Teams user has been synched between Active Directory and Azure Active Directory since this date, then their Teams chat data is stored in the cloud and is searchable using Content Search.</span></span> <span data-ttu-id="95218-187">此外，Microsoft 正致力於為內部部署使用者將 2018 年 1 月 31 日前的 Teams 聊天資料儲存於雲端式儲存體中。</span><span class="sxs-lookup"><span data-stu-id="95218-187">Microsoft is also working on storing Teams chat data from prior to January 31, 2018 in the cloud-based storage for on-premises users.</span></span> <span data-ttu-id="95218-188">我們即將提供更多相關資訊。</span><span class="sxs-lookup"><span data-stu-id="95218-188">More information about this will be available soon.</span></span>

 <span data-ttu-id="95218-189">**內部部署使用者是否需要授權，才能在雲端中儲存其 Teams 聊天資料？**</span><span class="sxs-lookup"><span data-stu-id="95218-189">**Do on-premises users need a license to store their Teams chat data in the cloud?**</span></span>
  
<span data-ttu-id="95218-190">是。</span><span class="sxs-lookup"><span data-stu-id="95218-190">Yes.</span></span> <span data-ttu-id="95218-191">若要在雲端式儲存體中儲存內部部署使用者的 Teams 聊天資料，必須在 Office 365 (或 Microsoft 365) 中為該使用者指派 Microsoft Teams 授權和 Exchange Online 方案授權。</span><span class="sxs-lookup"><span data-stu-id="95218-191">To store Teams chat data for an on-premises user in a cloud-based storage, the user must be assigned a Microsoft Teams license and an Exchange Online Plan license in Office 365 (or Microsoft 365).</span></span>