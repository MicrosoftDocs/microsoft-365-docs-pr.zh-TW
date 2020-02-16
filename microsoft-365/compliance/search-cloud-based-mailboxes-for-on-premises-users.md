---
title: 在 Office 365 中搜尋內部部署使用者的雲端式的信箱
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
localization_priority: Normal
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: 用於安全性 & 合規性中心的內容搜尋工具來搜尋並匯出在 Exchange 混合式部署中的內部部署使用者 MicrosoftTeams 聊天室資料 （稱為 1xN 聊天室）。
ms.openlocfilehash: 40439c338e00e7ae94ff82ec4be1af78a250acd6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42070006"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users-in-office-365"></a><span data-ttu-id="b1de5-103">在 Office 365 中搜尋內部部署使用者的雲端式的信箱</span><span class="sxs-lookup"><span data-stu-id="b1de5-103">Searching cloud-based mailboxes for on-premises users in Office 365</span></span>

<span data-ttu-id="b1de5-104">如果您的組織具有 Exchange 混合式部署，且已啟用 Microsoft Teams，使用者可以使用小組聊天應用程式的立即訊息。</span><span class="sxs-lookup"><span data-stu-id="b1de5-104">If your organization has an Exchange hybrid deployment and has enabled Microsoft Teams, users can use the Teams chat application for instant messaging.</span></span> <span data-ttu-id="b1de5-105">雲端型使用者，（也稱為*1xN 聊天*） 小組聊天資料會儲存至其主要的雲端式信箱。</span><span class="sxs-lookup"><span data-stu-id="b1de5-105">For the cloud-based user, the Teams chat data (also called *1xN chats*) is saved to their primary cloud-based mailbox.</span></span> <span data-ttu-id="b1de5-106">當內部部署使用者使用的小組聊天應用程式時，其主要信箱是位於的內部。</span><span class="sxs-lookup"><span data-stu-id="b1de5-106">When an on-premises user uses the Team chat application, their primary mailbox is located on-premises.</span></span> <span data-ttu-id="b1de5-107">若要解決這項限制，Microsoft 已發行位置 （稱為 「 內部部署使用者的基於雲端的信箱） 的雲端式存放裝置區域建立用來儲存內部部署使用者的小組聊天資料的新功能。</span><span class="sxs-lookup"><span data-stu-id="b1de5-107">To get around this limitation, Microsoft has released a new feature where a cloud-based storage area (called a cloud-based mailbox for on-premises users) is created to store Teams chat data for on-premises users.</span></span> <span data-ttu-id="b1de5-108">這可讓您在安全 & 與規範中心中使用內容搜尋工具來搜尋並匯出內部部署使用者的小組聊天資料。</span><span class="sxs-lookup"><span data-stu-id="b1de5-108">This lets you use the Content Search tool in the Security & Compliance Center to search and export Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="b1de5-109">以下是設定為內部部署使用者的雲端式信箱的限制與需求：</span><span class="sxs-lookup"><span data-stu-id="b1de5-109">Here are the requirements and limitations for setting up cloud-based mailboxes for on-premises users:</span></span>
  
- <span data-ttu-id="b1de5-110">您在內部部署目錄服務 （例如 Active Directory) 中的使用者帳戶必須與 Azure Active Directory，Office 365 中的目錄服務同步處理。</span><span class="sxs-lookup"><span data-stu-id="b1de5-110">The user accounts in your on-premises directory service (such as Active Directory) must be synchronized with Azure Active Directory, the directory service in Office 365.</span></span> <span data-ttu-id="b1de5-111">這表示郵件使用者帳戶在 Office 365 中建立，並為其主要信箱位於內部部署組織中的使用者相關聯。</span><span class="sxs-lookup"><span data-stu-id="b1de5-111">This means that a mail user account is created in Office 365 and is associated with a user whose primary mailbox is located in the on-premises organization.</span></span>

- <span data-ttu-id="b1de5-112">Microsoft Teams 授權和 Exchange Online Plan 1 授權的最小，必須指派其主要信箱位於內部部署組織中的使用者。</span><span class="sxs-lookup"><span data-stu-id="b1de5-112">The user whose primary mailbox is located in the on-premises organization must be assigned a Microsoft Teams license and a minimum of an Exchange Online Plan 1 license.</span></span>

- <span data-ttu-id="b1de5-113">內部部署使用者的雲端架構信箱是使用唯一的存放區小組聊天資料。</span><span class="sxs-lookup"><span data-stu-id="b1de5-113">The cloud-based mailbox for on-premises users is used only store Teams chat data.</span></span> <span data-ttu-id="b1de5-114">內部部署使用者無法登入的雲端架構信箱或任何的方式存取。</span><span class="sxs-lookup"><span data-stu-id="b1de5-114">An on-premises user can't sign in to the cloud-based mailbox or access in any way.</span></span> <span data-ttu-id="b1de5-115">它不能用來傳送或接收電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="b1de5-115">It can't be used to send or receive email messages.</span></span> 

- <span data-ttu-id="b1de5-116">您必須將要求提交給 Microsoft 支援服務以啟用您的組織中搜尋的小組聊天資料內部部署使用者的雲端式信箱。</span><span class="sxs-lookup"><span data-stu-id="b1de5-116">You have to submit a request to Microsoft Support to enable your organization to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="b1de5-117">本文中，請參閱[歸檔啟用這項功能的 Microsoft 支援服務要求](#filing-a-request-with-microsoft-support-to-enable-this-feature)。</span><span class="sxs-lookup"><span data-stu-id="b1de5-117">See [Filing a request with Microsoft Support to enable this feature](#filing-a-request-with-microsoft-support-to-enable-this-feature) in this article.</span></span> 

> [!NOTE]
> <span data-ttu-id="b1de5-118">小組通道交談一律會儲存在小組與相關聯的雲端式信箱。</span><span class="sxs-lookup"><span data-stu-id="b1de5-118">Teams channel conversations are always stored in the cloud-based mailbox that's associated with the Team.</span></span> <span data-ttu-id="b1de5-119">這表示您可以使用內容搜尋來搜尋通道交談沒有對支援服務歸檔。</span><span class="sxs-lookup"><span data-stu-id="b1de5-119">That means you can use Content Search to search channel conversations without have to file a support request.</span></span> <span data-ttu-id="b1de5-120">如需關於搜尋小組通道交談，請參閱[搜尋 Microsoft Teams 和 Office 365 群組](content-search.md#searching-microsoft-teams-and-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="b1de5-120">For more information about searching Teams channel conversations, see [Searching Microsoft Teams and Office 365 Groups](content-search.md#searching-microsoft-teams-and-office-365-groups).</span></span>
  
## <a name="how-it-works"></a><span data-ttu-id="b1de5-121">運作方式</span><span class="sxs-lookup"><span data-stu-id="b1de5-121">How it works</span></span>

<span data-ttu-id="b1de5-122">如果 Microsoft Teams 功能的使用者具有內部部署信箱，而且具有 /int/ 其使用者帳戶/身分識別同步處理至雲端，Microsoft 會建立雲端式信箱來存儲 1xN 小組聊天資料。</span><span class="sxs-lookup"><span data-stu-id="b1de5-122">If a Microsoft Teams-enabled user has an on-premises mailbox and their user account/identity has been synched to the cloud, Microsoft creates a cloud-based mailbox to store 1xN Teams chat data.</span></span> <span data-ttu-id="b1de5-123">小組聊天資料會儲存在雲端架構信箱之後，它會編入搜尋索引。</span><span class="sxs-lookup"><span data-stu-id="b1de5-123">After the Teams chat data is stored in the cloud-based mailbox, it's indexed for search.</span></span> <span data-ttu-id="b1de5-124">這可讓您使用內容搜尋 （和 eDiscovery 案例相關聯的搜尋） 若要搜尋，預覽，並匯出內部部署使用者的小組聊天資料。</span><span class="sxs-lookup"><span data-stu-id="b1de5-124">This lets you Use Content Search (and searches associated with eDiscovery cases) to search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="b1de5-125">您也可以使用**\*ComplianceSearch**安全性 & 搜尋團隊的合規性中心 PowerShell 中的指令程式聊天室內部部署使用者的資料。</span><span class="sxs-lookup"><span data-stu-id="b1de5-125">You can also use **\*ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="b1de5-126">下圖顯示如何小組聊天內部部署使用者的資料的工作流程的可搜尋、 預覽，並匯出。</span><span class="sxs-lookup"><span data-stu-id="b1de5-126">The following graphic shows the workflow of how Teams chat data for on-premises users is available to search, preview, and export.</span></span>
  
![Microsoft Teams 中的內部部署使用者的雲端儲存空間](../media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
<span data-ttu-id="b1de5-128">除了這項新功能，您仍然可以使用內容搜尋搜尋、 預覽，並匯出雲端型 SharePoint 網站及 Exchange 信箱中的內容相關聯每個 Microsoft 小組及 1xN Teams 中的 Exchange Online 信箱的聊天室資料的小組雲端型使用者。</span><span class="sxs-lookup"><span data-stu-id="b1de5-128">In addition to this new capability, you can still use Content Search to search, preview, and export Teams content in the cloud-based SharePoint site and Exchange mailbox associated with each Microsoft Team and 1xN Teams chat data in the Exchange Online mailbox for cloud-based users.</span></span>

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a><span data-ttu-id="b1de5-129">若要啟用此功能與 Microsoft 支援服務要求歸檔</span><span class="sxs-lookup"><span data-stu-id="b1de5-129">Filing a request with Microsoft Support to enable this feature</span></span>

<span data-ttu-id="b1de5-130">您必須將歸檔與 Microsoft 支援服務，讓您的組織使用圖形化使用者介面中安全性 & 規範中心搜尋內部部署使用者的雲端式信箱中的小組聊天資料。</span><span class="sxs-lookup"><span data-stu-id="b1de5-130">You must file a request with Microsoft Support to enable your organization to use the graphical user interface in the Security & Compliance Center to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="b1de5-131">在安全性 & 合規性中心 PowerShell 中使用這項功能。</span><span class="sxs-lookup"><span data-stu-id="b1de5-131">This feature is available in Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="b1de5-132">您不需要將支援要求提交給使用 PowerShell 來搜尋內部部署使用者的小組聊天資料。</span><span class="sxs-lookup"><span data-stu-id="b1de5-132">You don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="b1de5-133">當您將要求提交給 Microsoft 支援服務時，請包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="b1de5-133">Include the following information when you submit the request to Microsoft Support:</span></span>
  
- <span data-ttu-id="b1de5-134">Office 365 組織的預設網域名稱。</span><span class="sxs-lookup"><span data-stu-id="b1de5-134">The default domain name of your Office 365 organization.</span></span>
    
- <span data-ttu-id="b1de5-135">租用戶名稱與您的 Office 365 組織租用戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="b1de5-135">The tenant name and tenant ID of your Office 365 organization.</span></span> <span data-ttu-id="b1de5-136">您可以找到這些在 Azure Active Directory 入口網站 (在 [**管理**] 下\>**屬性**)。</span><span class="sxs-lookup"><span data-stu-id="b1de5-136">You can find these in the Azure Active Directory portal (under **Manage** \> **Properties**).</span></span> <span data-ttu-id="b1de5-137">請參閱[尋找您的 Office 365 租用戶識別碼](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b)。</span><span class="sxs-lookup"><span data-stu-id="b1de5-137">See [Find your Office 365 tenant ID](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>
    
- <span data-ttu-id="b1de5-138">下列的標題或支援要求的用途的描述: [啟用應用程式內容搜尋的內部部署使用者]。</span><span class="sxs-lookup"><span data-stu-id="b1de5-138">The following title or description of the purpose of the support request: "Enable Application Content Search for On-premises Users".</span></span> <span data-ttu-id="b1de5-139">這有助於將要求路由傳送至 Office 365 電子文件探索工程團隊會實作要求者。</span><span class="sxs-lookup"><span data-stu-id="b1de5-139">This helps route the request to the Office 365 eDiscovery engineering team who will implement the request.</span></span> 
    
<span data-ttu-id="b1de5-140">工程變更後，Microsoft 支援服務會傳送給您評估的部署的日期。</span><span class="sxs-lookup"><span data-stu-id="b1de5-140">After the engineering change is made, Microsoft Support will send you an estimated deployment date.</span></span> <span data-ttu-id="b1de5-141">部署程序通常需要 2 – 3 週後您提交支援要求。</span><span class="sxs-lookup"><span data-stu-id="b1de5-141">The deployment process usually takes 2–3 weeks after you submit the support request.</span></span> 
  
### <a name="what-happens-after-this-feature-is-enabled"></a><span data-ttu-id="b1de5-142">啟用此功能後，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="b1de5-142">What happens after this feature is enabled?</span></span>

<span data-ttu-id="b1de5-143">這項功能在 Office 365 組織中部署之後，在內容搜尋和安全性 & 規範中心的 eDiscovery 案例相關聯的搜尋中，會進行下列變更：</span><span class="sxs-lookup"><span data-stu-id="b1de5-143">After this feature is deployed in your Office 365 organization, the following changes are made in Content Search and in searches associated with an eDiscovery case in the Security & Compliance Center:</span></span>
  
- <span data-ttu-id="b1de5-144">在內容搜尋的**位置**會新增至**內部部署使用者的加入 Office 應用程式內容**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b1de5-144">The **Add Office app content for on-premises users** checkbox is added under the **Locations** in Content Search.</span></span> 
    
    ![「 新增內部部署使用者的 Office 應用程式內容 」] 核取方塊新增至 「 內容搜尋 UI](../media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- <span data-ttu-id="b1de5-146">在您用來選取要搜尋的使用者信箱的內容位置選擇器中會顯示內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="b1de5-146">On-premises users are displayed in the content locations picker that you use to select user mailboxes to search.</span></span> 

## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="b1de5-147">搜尋內容的內部部署使用者的雲端式信箱中的小組聊天</span><span class="sxs-lookup"><span data-stu-id="b1de5-147">Searching for Teams chat content in cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="b1de5-148">啟用此功能之後，您可以使用安全性 & 規範中心的內容搜尋來搜尋內部部署使用者的雲端式信箱中的小組聊天資料。</span><span class="sxs-lookup"><span data-stu-id="b1de5-148">After the feature has been enabled, you can use Content Search in the Security & Compliance Center to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span> 
  
1. <span data-ttu-id="b1de5-149">在 [安全性 & 合規性中心，移至**搜尋** \> **內容搜尋**</span><span class="sxs-lookup"><span data-stu-id="b1de5-149">In the Security & Compliance Center, go to **Search** \> **Content search**</span></span>
    
2. <span data-ttu-id="b1de5-150">在 [**搜尋**] 頁面上，按一下 [![加入圖示](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新的搜尋**。</span><span class="sxs-lookup"><span data-stu-id="b1de5-150">On the **Search** page, click ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span>
    
    <span data-ttu-id="b1de5-151">如先前所述，**內部部署使用者的加入 Office 應用程式內容**] 核取方塊會顯示在 [**位置**] 下。</span><span class="sxs-lookup"><span data-stu-id="b1de5-151">As previously explained, the **Add Office app content for on-premises users** checkbox is displayed under **Locations**.</span></span> <span data-ttu-id="b1de5-152">預設會選取它。</span><span class="sxs-lookup"><span data-stu-id="b1de5-152">It's selected by default.</span></span>
    
3. <span data-ttu-id="b1de5-153">建立關鍵字查詢，並將條件新增至搜尋查詢，必要時。</span><span class="sxs-lookup"><span data-stu-id="b1de5-153">Create the keyword query and add conditions to the search query if necessary.</span></span> <span data-ttu-id="b1de5-154">只搜尋的小組聊天資料，您可以在 [**關鍵字**] 方塊中新增下列查詢：</span><span class="sxs-lookup"><span data-stu-id="b1de5-154">To only search for Team chats data, you can add the following query in the **Keywords** box:</span></span> 

    ```text
    kind:im
    ```

4. <span data-ttu-id="b1de5-155">此時，您可以選擇下列其中一個**位置**] 下的下列選項：</span><span class="sxs-lookup"><span data-stu-id="b1de5-155">At this point, you can choose one of the following options under **Locations**:</span></span>

    - <span data-ttu-id="b1de5-156">**所有位置：** 選取此選項可搜尋組織中的所有使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="b1de5-156">**All locations:** Select this option to search the mailboxes of all users in your organization.</span></span> <span data-ttu-id="b1de5-157">選取核取方塊時，也可搜尋的內部部署使用者的所有雲端式信箱。</span><span class="sxs-lookup"><span data-stu-id="b1de5-157">When the checkbox is selected, all cloud-based mailboxes for on-premises users will also be searched.</span></span> 

    - <span data-ttu-id="b1de5-158">**特定位置：** 選取此選項，然後按一下 [**修改**\>選擇使用者、 群組或小組來搜尋特定的信箱。</span><span class="sxs-lookup"><span data-stu-id="b1de5-158">**Specific locations:** Select this option and then click **Modify** \> Choose user, groups, or teams to search specific mailboxes.</span></span> <span data-ttu-id="b1de5-159">如先前所述，位置選擇器可讓您搜尋內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="b1de5-159">As previously explained, the locations picker lets you search for on-premises users.</span></span> 
    
5. <span data-ttu-id="b1de5-160">儲存並執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="b1de5-160">Save and run the search.</span></span> <span data-ttu-id="b1de5-161">從內部部署使用者的雲端式信箱的任何搜尋結果可以像任何其他的搜尋結果預覽。</span><span class="sxs-lookup"><span data-stu-id="b1de5-161">Any search results from the cloud-based mailboxes for on-premises users can be previewed like any other search results.</span></span> <span data-ttu-id="b1de5-162">您也可以將 （包括任何小組聊天資料） 的搜尋結果匯出至 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="b1de5-162">You can also export the search results (including any Teams chat data) to a PST file.</span></span> <span data-ttu-id="b1de5-163">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b1de5-163">For more information, see:</span></span> 

    - [<span data-ttu-id="b1de5-164">Create a search</span><span class="sxs-lookup"><span data-stu-id="b1de5-164">Create a search</span></span>](content-search.md#create-a-search)

    - [<span data-ttu-id="b1de5-165">Preview search results</span><span class="sxs-lookup"><span data-stu-id="b1de5-165">Preview search results</span></span>](content-search.md#preview-search-results)

    - [<span data-ttu-id="b1de5-166">匯出內容搜尋結果</span><span class="sxs-lookup"><span data-stu-id="b1de5-166">Export Content Search results</span></span>](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="b1de5-167">使用 PowerShell 來搜尋小組聊天資料中的內部部署使用者的雲端式信箱</span><span class="sxs-lookup"><span data-stu-id="b1de5-167">Using PowerShell to search for Teams chat data in cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="b1de5-168">您可以使用**New-compliancesearch**和**Set-compliancesearch** cmdlet 安全性 & 合規性中心 PowerShell 中，搜尋內部部署使用者的雲端式信箱。</span><span class="sxs-lookup"><span data-stu-id="b1de5-168">You can use the **New-ComplianceSearch** and **Set-ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search the cloud-based mailbox for on-premises users.</span></span> <span data-ttu-id="b1de5-169">如先前所述，您不需要將支援要求提交給使用 PowerShell 來搜尋內部部署使用者的小組聊天資料。</span><span class="sxs-lookup"><span data-stu-id="b1de5-169">As previously explained, you don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
1. <span data-ttu-id="b1de5-170">[連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b1de5-170">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="b1de5-171">執行下列 PowerShell 命令來建立搜尋內部部署使用者的雲端式信箱的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="b1de5-171">Run the following PowerShell command to create a content search that searches the cloud-based mailboxes of on-premises users.</span></span>

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    <span data-ttu-id="b1de5-172">*IncludeUserAppContent*參數用來指定使用者或*ExchangeLocation*參數所指定的使用者的雲端式信箱。</span><span class="sxs-lookup"><span data-stu-id="b1de5-172">The *IncludeUserAppContent*  parameter is used to specify the cloud-based mailbox for the user or users who are specified by the  *ExchangeLocation*  parameter.</span></span> <span data-ttu-id="b1de5-173">*AllowNotFoundExchangeLocationsEnabled*允許雲端式信箱的內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="b1de5-173">The  *AllowNotFoundExchangeLocationsEnabled*  allows cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="b1de5-174">當您使用`$true`值，此參數，請搜尋不會嘗試之前，先執行驗證信箱是否存在。</span><span class="sxs-lookup"><span data-stu-id="b1de5-174">When you use the `$true` value for this parameter, the search doesn't try to validate the existence of the mailbox before it runs.</span></span> <span data-ttu-id="b1de5-175">這是必要搜尋內部部署使用者的基於雲端的信箱，因為這些類型的信箱不解決與一般信箱。</span><span class="sxs-lookup"><span data-stu-id="b1de5-175">This is required to search the cloud-based mailboxes for on-premises users because these types of mailboxes don't resolve as regular mailboxes.</span></span> 

    <span data-ttu-id="b1de5-176">下列範例會搜尋小組聊天 （也就是立即訊息），包含關鍵字 「 redstone 」 中的雲端架構信箱的 Sara Davis，身為內部部署組織中的使用者 Contoso。</span><span class="sxs-lookup"><span data-stu-id="b1de5-176">The following example searches for Teams chats (which are instant messages) that contain keyword "redstone" in the cloud-based mailbox of Sara Davis, who is an on-premises user in the Contoso organization.</span></span>
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   <span data-ttu-id="b1de5-177">建立搜尋之後，請務必使用**Start-compliancesearch** cmdlet 來執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="b1de5-177">After you create a search, be sure to use the **Start-ComplianceSearch** cmdlet to run the search.</span></span> 
  
<span data-ttu-id="b1de5-178">使用這些 cmdlet 的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b1de5-178">For more information using these cmdlets, see:</span></span>
  
- [<span data-ttu-id="b1de5-179">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="b1de5-179">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)

- [<span data-ttu-id="b1de5-180">Set-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="b1de5-180">Set-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)

- [<span data-ttu-id="b1de5-181">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="b1de5-181">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)

## <a name="known-issues"></a><span data-ttu-id="b1de5-182">已知問題</span><span class="sxs-lookup"><span data-stu-id="b1de5-182">Known issues</span></span>

- <span data-ttu-id="b1de5-183">目前，您可以搜尋、 預覽，並匯出內部部署使用者的雲端式信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="b1de5-183">Currently, you can search, preview, and export content in cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="b1de5-184">您也可以為內部使用者的雲端架構信箱置於保留的 eDiscovery 案例相關聯和小組聊天或通道訊息保留原則套用至雲端架構信箱的內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="b1de5-184">You can also place a cloud-based mailbox for an on-premises user on a hold associated with an eDiscovery case, and apply a retention policy for Teams chats or channel messages to cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="b1de5-185">不過在這個階段中，您無法將其他其他內容的位置 （例如 Exchange 信箱和 SharePoint 網站） 的保留原則套用到雲端式信箱的內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="b1de5-185">However at this time, you can't apply a retention policy for other other content locations (such as Exchange mailboxes and SharePoint sites) to cloud-based mailboxes for on-premises users.</span></span> 


## <a name="frequently-asked-questions"></a><span data-ttu-id="b1de5-186">常見問題集</span><span class="sxs-lookup"><span data-stu-id="b1de5-186">Frequently asked questions</span></span>

 <span data-ttu-id="b1de5-187">**內部部署使用者的雲端架構信箱位於何處？**</span><span class="sxs-lookup"><span data-stu-id="b1de5-187">**Where are cloud-based mailboxes for on-premises users located?**</span></span>
  
<span data-ttu-id="b1de5-188">建立並儲存在相同的資料中心，為您的 Office 365 組織中的雲端架構信箱。</span><span class="sxs-lookup"><span data-stu-id="b1de5-188">Cloud-based mailboxes are created and stored in the same datacenter as your Office 365 organization.</span></span> 
  
 <span data-ttu-id="b1de5-189">**是否有任何非提交支援要求的其他需求？**</span><span class="sxs-lookup"><span data-stu-id="b1de5-189">**Are there any other requirements other than submitting a support request?**</span></span>
  
 <span data-ttu-id="b1de5-190">如先前所述，具有內部部署信箱的使用者的身分識別必須同步處理至雲端式組織，讓每個內部部署使用者帳戶在 Office 365 中建立對應的郵件使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b1de5-190">As previously explained, the identities of users with on-prem mailboxes must be synchronized to your cloud-based organization so that a corresponding mail user account is created for each on-premises user account in Office 365.</span></span> <span data-ttu-id="b1de5-191">您的組織也必須擁有 Office 365 企業版訂閱，例如 Office 365 企業版 E1、 E3 或 E5 訂閱。</span><span class="sxs-lookup"><span data-stu-id="b1de5-191">Your organization must also have an Office 365 enterprise subscription, such as an Office 365 Enterprise E1, E3, or E5 subscription.</span></span> 
  
 <span data-ttu-id="b1de5-192">**是否有遺失小組聊天資料，如果使用者的內部部署信箱移轉到雲端的風險？**</span><span class="sxs-lookup"><span data-stu-id="b1de5-192">**Is there a risk of losing the Teams chat data if the user's on-premises mailbox is migrated to the cloud?**</span></span>
  
<span data-ttu-id="b1de5-193">否。</span><span class="sxs-lookup"><span data-stu-id="b1de5-193">No.</span></span> <span data-ttu-id="b1de5-194">當您的內部部署使用者主要信箱遷移至雲端時，該使用者的小組聊天資料會移轉至其新雲端式主要信箱。</span><span class="sxs-lookup"><span data-stu-id="b1de5-194">When you migrate the primary mailbox of an on-premises user to the cloud, the Teams chat data for that user will be migrated to their new cloud-based primary mailbox.</span></span>
  
 <span data-ttu-id="b1de5-195">**可以我套用 eDiscovery 保留或 Office 365 保留原則至內部部署使用者？**</span><span class="sxs-lookup"><span data-stu-id="b1de5-195">**Can I apply an eDiscovery hold or Office 365 retention policies to on-premises users?**</span></span>
  
<span data-ttu-id="b1de5-196">是。</span><span class="sxs-lookup"><span data-stu-id="b1de5-196">Yes.</span></span> <span data-ttu-id="b1de5-197">您可以將 eDiscovery 保留 」 或 「 小組聊天和通道訊息的保留原則套用至雲端架構信箱的內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="b1de5-197">You can apply eDiscovery holds or retention policies for Teams chats and channel messages to cloud-based mailboxes for on-premises users.</span></span>
  
 <span data-ttu-id="b1de5-198">**可以較舊的小組聊天內部部署使用者的時間之前我的組織的內容搜尋尋找提交要求以啟用這項功能嗎？**</span><span class="sxs-lookup"><span data-stu-id="b1de5-198">**Can Content Search find older Teams chats for on-premises users before the time my organization submitted the request to enable this feature?**</span></span>
  
<span data-ttu-id="b1de5-199">Microsoft 已啟動的內部部署使用者的小組聊天資料儲存於 2018 年 1 月 31 日。</span><span class="sxs-lookup"><span data-stu-id="b1de5-199">Microsoft started storing the Teams chat data for on-premises users on January 31, 2018.</span></span> <span data-ttu-id="b1de5-200">的話，如果此日期之後，已之間 Active Directory 和 Azure Active Directory 同步內部部署 microsoft Teams 使用者的身分識別，然後其小組聊天資料儲存在雲端式信箱中，而且可搜尋使用內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="b1de5-200">So, if the identity of an on-premises Teams user has been synched between Active Directory and Azure Active Directory since this date, then their Teams chat data is stored in a cloud-based mailbox and is searchable using Content Search.</span></span> <span data-ttu-id="b1de5-201">Microsoft 也將從 2018 年 1 月 31 日之前的小組聊天資料儲存在內部部署使用者的雲端式信箱中運作。</span><span class="sxs-lookup"><span data-stu-id="b1de5-201">Microsoft is also working on storing Teams chat data from prior to January 31, 2018 in the cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="b1de5-202">有關此的詳細資訊將會推出。</span><span class="sxs-lookup"><span data-stu-id="b1de5-202">More information about this will be available soon.</span></span>

 <span data-ttu-id="b1de5-203">**內部部署使用者需要授權才能小組聊天資料儲存在雲端架構信箱嗎？**</span><span class="sxs-lookup"><span data-stu-id="b1de5-203">**Do on-premises users need a license to store Teams chat data in a cloud-based mailbox?**</span></span>
  
<span data-ttu-id="b1de5-204">是。</span><span class="sxs-lookup"><span data-stu-id="b1de5-204">Yes.</span></span> <span data-ttu-id="b1de5-205">若要在雲端式信箱中儲存內部部署使用者的小組聊天資料，使用者必須具有 Microsoft Teams 授權和 Exchange Online 計劃授權 Office 365 （或 Microsoft 365） 中。</span><span class="sxs-lookup"><span data-stu-id="b1de5-205">To store Teams chat data for an on-premises user in a cloud-based mailbox, the user must be assigned a Microsoft Teams license and an Exchange Online Plan license in Office 365 (or Microsoft 365).</span></span>
