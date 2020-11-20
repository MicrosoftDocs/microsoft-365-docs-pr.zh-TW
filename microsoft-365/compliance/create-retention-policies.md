---
title: 建立及設定保留原則以自動保留或刪除內容
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 使用保留原則可以非常有效地控制使用者透過電子郵件、文件和交談所產生的內容。保留想要的內容，清除不想要的內容。
ms.openlocfilehash: 83f438b6a32ad56f1f239858d2f3fad61875c460
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357338"
---
# <a name="create-and-configure-retention-policies"></a><span data-ttu-id="bf0dc-104">建立及設定保留原則</span><span class="sxs-lookup"><span data-stu-id="bf0dc-104">Create and configure retention policies</span></span>

><span data-ttu-id="bf0dc-105">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="bf0dc-105">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="bf0dc-106">使用保留原則主動決定是否要保留內容、刪除內容，還是兩者，即保留然後刪除內容。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-106">Use a retention policy to decide proactively whether to retain content, delete content, or both - retain and then delete the content.</span></span>

<span data-ttu-id="bf0dc-p102">透過將相同的保留設定依照位置 (如網站或信箱層級) 的內容進行指派，保留原則可讓您工作的更有效率。如果您不確定是否要使用保留原則或保留標籤，可參閱[保留原則及保留標籤](retention.md#retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p102">A retention policy lets you do this very efficiently by assigning the same retention settings for content by location, at a site or mailbox level. If you're not sure whether to use a retention policy or a retention label, see [Retention policies and retention labels](retention.md#retention-policies-and-retention-labels).</span></span>

<span data-ttu-id="bf0dc-109">如需有關保留原則及其運作方式的詳細資訊，請參閱[了解保留原則和保留標籤](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-109">For more information about retention policies and how retention works, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bf0dc-110">開始之前</span><span class="sxs-lookup"><span data-stu-id="bf0dc-110">Before you begin</span></span>

<span data-ttu-id="bf0dc-p103">貴組織中的全域系統管理員擁有建立及編輯保留原則的完整權限。如果您未以全域系統管理員身分登入，請參閱[建立和管理保留原則和保留標籤所需權限。](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p103">The global admin for your organization has full permissions to create and edit retention policies. If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="create-and-configure-a-retention-policy"></a><span data-ttu-id="bf0dc-113">建立及設定保留原則</span><span class="sxs-lookup"><span data-stu-id="bf0dc-113">Create and configure a retention policy</span></span>

<span data-ttu-id="bf0dc-114">雖然保留原則可以支援多個位置，但您無法建立含括所有支援位置的單一個保留原則：</span><span class="sxs-lookup"><span data-stu-id="bf0dc-114">Although a retention policy can support multiple locations, you can't create a single retention policy that includes all the supported locations:</span></span>

- <span data-ttu-id="bf0dc-115">Exchange 電子郵件</span><span class="sxs-lookup"><span data-stu-id="bf0dc-115">Exchange email</span></span>
- <span data-ttu-id="bf0dc-116">SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="bf0dc-116">SharePoint site</span></span>
- <span data-ttu-id="bf0dc-117">OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="bf0dc-117">OneDrive accounts</span></span>
- <span data-ttu-id="bf0dc-118">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="bf0dc-118">Microsoft 365 groups</span></span>
- <span data-ttu-id="bf0dc-119">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="bf0dc-119">Skype for Business</span></span>
- <span data-ttu-id="bf0dc-120">Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="bf0dc-120">Exchange public folders</span></span>
- <span data-ttu-id="bf0dc-121">Teams 通道訊息</span><span class="sxs-lookup"><span data-stu-id="bf0dc-121">Teams channel messages</span></span>
- <span data-ttu-id="bf0dc-122">Teams 聊天</span><span class="sxs-lookup"><span data-stu-id="bf0dc-122">Teams chats</span></span>
- <span data-ttu-id="bf0dc-123">Yammer 社群訊息</span><span class="sxs-lookup"><span data-stu-id="bf0dc-123">Yammer community messages</span></span>
- <span data-ttu-id="bf0dc-124">Yammer 私人訊息</span><span class="sxs-lookup"><span data-stu-id="bf0dc-124">Yammer private messages</span></span>

<span data-ttu-id="bf0dc-p104">建立保留原則時若選取 Teams 或 Yammer 位置，系統會自動排除另一個位置。因此，應遵循的指示將取決於您是否需要包含 Teams 或 Yammer 位置而定：</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p104">If you select the Teams or Yammer locations when you create a retention policy, the other locations are automatically excluded. Therefore, which instructions to follow depends on whether you need to include the Teams or Yammer locations:</span></span>

- [<span data-ttu-id="bf0dc-127">Teams 位置保留原則的指示</span><span class="sxs-lookup"><span data-stu-id="bf0dc-127">Instructions for a retention policy for Teams locations</span></span>](#retention-policy-for-teams-locations)
- [<span data-ttu-id="bf0dc-128">Yammer 位置保留原則的指示</span><span class="sxs-lookup"><span data-stu-id="bf0dc-128">Instructions for a retention policy for Yammer locations</span></span>](#retention-policy-for-yammer-locations)
- [<span data-ttu-id="bf0dc-129">Teams 和 Yammer 以外位置保留原則的指示</span><span class="sxs-lookup"><span data-stu-id="bf0dc-129">Instructions for a retention policy for locations other than Teams and Yammer</span></span>](#retention-policy-for-locations-other-than-teams-and-yammer)

<span data-ttu-id="bf0dc-130">當您有多個保留原則，以及當您同時使用保留標籤時，請參閱[保留原則優先或以什麼為優先？](retention.md#the-principles-of-retention-or-what-takes-precedence)以了解在相同的內容上同時有多個保留設定套用時，會有什麼樣的結果。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-130">When you have more than one retention policy, and when you also use retention labels, see [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) to understand the outcome when multiple retention settings apply to the same content.</span></span>

### <a name="retention-policy-for-teams-locations"></a><span data-ttu-id="bf0dc-131">Teams 位置的保留原則</span><span class="sxs-lookup"><span data-stu-id="bf0dc-131">Retention policy for Teams locations</span></span>

1. <span data-ttu-id="bf0dc-132">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 **[原則]** >  **[保留]**。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-132">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="bf0dc-133">選取 **[新保留原則]** 以啟動 [建立保留原則] 精靈，並命名新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-133">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="bf0dc-134">對於 [選擇要套用原則的位置 **]** 頁面，請為 Teams 選取一個或兩個位置：**Teams 頻道訊息** 和 **Teams 聊天**。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-134">For the **Choose locations to apply the policy** page, select one or both of the locations for Teams: **Teams channel message** and **Teams chats**.</span></span>

   <span data-ttu-id="bf0dc-p105">針對 **Teams 頻道訊息**，會包含來自標準頻道的訊息，但不會包含 [私人頻道](https://docs.microsoft.com/microsoftteams/private-channels) (部分機器翻譯)。目前，保留原則尚未支援 [私人頻道]。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p105">For **Teams channel messages**, message from standard channels but not [private channels](https://docs.microsoft.com/microsoftteams/private-channels) are included. Currently, private channels aren't supported by retention policies.</span></span>

   <span data-ttu-id="bf0dc-137">根據預設，[所有小組和所有使用者都處於選中狀態](#a-policy-that-applies-to-entire-locations)，但您可以透過選取 [[選擇 **]** 和 [排除 **]** 選項](#a-policy-with-specific-inclusions-or-exclusions)以縮小範圍。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-137">By default, [all teams and all users are selected](#a-policy-that-applies-to-entire-locations), but you can refine this by selecting the [**Choose** and **Exclude** options](#a-policy-with-specific-inclusions-or-exclusions).</span></span>

4. <span data-ttu-id="bf0dc-138">在精靈的頁面上，如需 **決定是否要保留內容、刪除內容，或兩者皆可**，請指定保留及刪除內容的設定選項。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-138">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>

   <span data-ttu-id="bf0dc-p106">您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定 ](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p106">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time. For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="bf0dc-141">完成精靈以儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-141">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="bf0dc-142">如需 Teams 保留原則的詳細資訊，請參閱在 Teams 文件中的 [Microsoft Teams 的保留原則](https://docs.microsoft.com/microsoftteams/retention-policies)。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-142">For more information about retention policies for Teams, see [Retention policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies) from the Teams documentation.</span></span>

#### <a name="additional-retention-policy-needed-to-support-teams"></a><span data-ttu-id="bf0dc-143">支援 Teams 所需的其他保留原則</span><span class="sxs-lookup"><span data-stu-id="bf0dc-143">Additional retention policy needed to support Teams</span></span>

<span data-ttu-id="bf0dc-p107">Teams 不僅是提供聊天和頻道訊息功能，還有更多功能。如果您有透過 Microsoft 365 群組 (之前稱為 Office 365 群組) 建立的小組，您應該額外使用 [Microsoft 365 群組 **]** 位置來設定包含該 Microsoft 365 群組的保留原則。此保留原則適用於群組的信箱、網站和檔案中的內容。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p107">Teams is more than just chats and channel messages. If you have teams that were created from a Microsoft 365 group (formerly Office 365 group), you should additionally configure a retention policy that includes that Microsoft 365 group by using the **Microsoft 365 Groups** location. This retention policy applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="bf0dc-147">如果您有未與 Microsoft 365 群組連線的小組網站，您需要有可以包含 **SharePoint 網站** 或 **OneDrive 帳戶** 位置的保留原則，用以保留及刪除 Teams 中的檔案：</span><span class="sxs-lookup"><span data-stu-id="bf0dc-147">If you have team sites that aren't connected to a Microsoft 365 group, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations to retain and delete files in Teams:</span></span>

- <span data-ttu-id="bf0dc-148">在聊天中共用的檔案會儲存在共用檔案之使用者的 OneDrive 帳戶中。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-148">Files that are shared in chat are stored in the OneDrive account of the user who shared the file.</span></span>

- <span data-ttu-id="bf0dc-149">上傳至頻道的檔案則會儲存在團隊的 SharePoint 網站中。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-149">Files that are uploaded to channels are stored in the SharePoint site for the team.</span></span>

> [!TIP]
> <span data-ttu-id="bf0dc-150">當小組未連線至 Microsoft 365 群組時，您可以將保留原則套用到僅特定小組的檔案，方法是選取小組的 SharePoint 網站，以及小組中使用者的 OneDrive 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-150">You can apply a retention policy to the files of just a specific team when it's not connected to a Microsoft 365 group by selecting the SharePoint site for the team, and the OneDrive accounts of users in the Team.</span></span>

<span data-ttu-id="bf0dc-p108">套用至 Microsoft 365 群組、SharePoint 網站或 OneDrive 帳戶的保留原則有可能會刪除 Teams 聊天中參考的檔案，或在頻道訊息刪除前就將其刪除。在這種情況下，檔案仍會顯示在 Teams 訊息中，但是當使用者選取檔案時，會遇到「找不到檔案」錯誤。此行為並非保留原則特定，因此也可能在使用者從 SharePoint 或 OneDrive 中手動刪除檔案時發生。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p108">It's possible that a retention policy that's applied to Microsoft 365 groups, SharePoint sites, or OneDrive accounts could delete a file that's referenced in a Teams chat or channel message before those messages get deleted. In this scenario, the file still displays in the Teams message, but when users select the file, they get a "File not found" error. This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

### <a name="retention-policy-for-yammer-locations"></a><span data-ttu-id="bf0dc-154">Yammer 位置的保留原則</span><span class="sxs-lookup"><span data-stu-id="bf0dc-154">Retention policy for Yammer locations</span></span>

> [!NOTE]
> <span data-ttu-id="bf0dc-p109">Yammer 的保留原則已推出預覽版。如果您還沒有看到 Yammer 的新位置，請幾天後再試一次。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p109">Retention policies for Yammer are rolling out in preview. If you don't yet see the new locations for Yammer, try again in a few days.</span></span>
>
> <span data-ttu-id="bf0dc-157">若要使用此功能，您的 Yammer 網路必須處於[原生模式](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) (部分機器翻譯)，而非混合模式。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-157">To use this feature, your Yammer network must be [Native Mode](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode), not Hybrid Mode.</span></span>

1. <span data-ttu-id="bf0dc-158">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 **[原則]** >  **[保留]**。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-158">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="bf0dc-159">選取 **[新增保留原則]** 以建立新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-159">Select **New retention policy** to create a new retention policy.</span></span>

3. <span data-ttu-id="bf0dc-160">在精靈的頁面上，如需 **決定是否要保留內容、刪除內容，或兩者皆可**，請指定保留及刪除內容的設定選項。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-160">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span> 
    
    <span data-ttu-id="bf0dc-p110">您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定 ](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p110">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time. For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>
    
    <span data-ttu-id="bf0dc-163">請勿選取 [使用進階保留設定 **]**，因為 Yammer 位置不支援此選項。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-163">Do not select **Use advanced retention settings** because this option isn't supported for Yammer locations.</span></span> 

4. <span data-ttu-id="bf0dc-p111">在 [選擇位置 **]** 頁面上，選取 [讓我選擇特定位置 **]**。然後將 Yammer 的一個或兩個位置切換為開啟：**Yammer 社群訊息** 和 **Yammer 私人訊息**。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p111">For the **Choose locations** page, select **Let me choose specific locations**. Then toggle on one or both of the locations for Yammer: **Yammer community message** and **Yammer private messages**.</span></span>
    
    <span data-ttu-id="bf0dc-166">預設會選取所有社群和使用者，但是您可以指定要包含或排除的社群和使用者，以縮小範圍。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-166">By default, all communities and users are selected, but you can refine this by specifying communities and users to be included or excluded.</span></span>
    
    <span data-ttu-id="bf0dc-167">針對 Yammer 私人訊息：</span><span class="sxs-lookup"><span data-stu-id="bf0dc-167">For Yammer private messages:</span></span> 
    - <span data-ttu-id="bf0dc-168">如果您保留預設值 **全部**，將不會包含 Azure B2B 來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-168">If you leave the default at **All**, Azure B2B guest users are not included.</span></span> 
    - <span data-ttu-id="bf0dc-169">如果您選取 [選擇使用者 **]**，就可以將保留原則套用至外部使用者 (如果您知道其帳戶)。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-169">If you select **Choose user**, you can apply a retention policy to external users if you know their account.</span></span>

5. <span data-ttu-id="bf0dc-170">完成精靈以儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-170">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="bf0dc-171">如需保留原則對 Yammer 運作方式的詳細資訊，請參閱[了解 Yammer 的保留](retention-policies-yammer.md)。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-171">For more information about how retention policies work for Yammer, see [Learn about retention for Yammer](retention-policies-yammer.md).</span></span>

#### <a name="additional-retention-policies-needed-to-support-yammer"></a><span data-ttu-id="bf0dc-172">支援 Yammer 所需的額外保留原則</span><span class="sxs-lookup"><span data-stu-id="bf0dc-172">Additional retention policies needed to support Yammer</span></span>

<span data-ttu-id="bf0dc-p112">Yammer 不僅可提供社群訊息和私人訊息功能，還有更多功能。若要保留及刪除您 Yammer 網路的電子郵件，請使用 **Office 365 群組** 位置來設定額外的保留原則，其中包括用於 Yammer 的任何 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p112">Yammer is more than just community messages and private messages. To retain and delete email messages for your Yammer network, configure an additional retention policy that includes any Microsoft 365 groups that are used for Yammer, by using the **Microsoft 365 Groups** location.</span></span> 

<span data-ttu-id="bf0dc-175">若要保留及刪除 Yammer 中儲存的檔案，您需要包含 **SharePoint 網站** 或 **OneDrive 帳戶** 位置的保留原則：</span><span class="sxs-lookup"><span data-stu-id="bf0dc-175">To retain and delete files that are stored in Yammer, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations:</span></span>

- <span data-ttu-id="bf0dc-176">在私人訊息中共用的檔案會儲存在共用檔案之使用者的 OneDrive 帳戶中。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-176">Files that are shared in private messages are stored in the OneDrive account of the user who shared the file.</span></span> 

- <span data-ttu-id="bf0dc-177">上傳到社群的檔案會儲存在 Yammer 社群的 SharePoint 網站中。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-177">Files that are uploaded to communities are stored in the SharePoint site for the Yammer community.</span></span>

<span data-ttu-id="bf0dc-p113">套用至 SharePoint 網站或 OneDrive 帳戶的保留原則可能會在刪除 Yammer 訊息之前便刪除這些訊息中參考的檔案。在這種情況下，檔案仍會顯示在 Yammer 訊息中，但是當使用者選取檔案時，會遇到「找不到檔案」錯誤。此行為並非保留原則特定，因此也可能在使用者從 SharePoint 或 OneDrive 中手動刪除檔案時發生。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p113">It's possible that a retention policy that's applied to SharePoint sites or OneDrive accounts could delete a file that's referenced in a Yammer message before those messages get deleted. In this scenario, the file still displays in the Yammer message, but when users select the file, they get a "File not found" error. This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a><span data-ttu-id="bf0dc-181">Teams 和 Yammer 以外位置的保留原則</span><span class="sxs-lookup"><span data-stu-id="bf0dc-181">Retention policy for locations other than Teams and Yammer</span></span>

<span data-ttu-id="bf0dc-182">針對適用於下列任何服務的保留原則，使用下列指示：</span><span class="sxs-lookup"><span data-stu-id="bf0dc-182">Use the following instructions for retention policies that apply to any of these services:</span></span>

- <span data-ttu-id="bf0dc-183">Exchange：電子郵件和公用資料夾</span><span class="sxs-lookup"><span data-stu-id="bf0dc-183">Exchange: Email and public folders</span></span>
- <span data-ttu-id="bf0dc-184">SharePoint：網站</span><span class="sxs-lookup"><span data-stu-id="bf0dc-184">SharePoint: Sites</span></span>
- <span data-ttu-id="bf0dc-185">OneDrive：帳戶</span><span class="sxs-lookup"><span data-stu-id="bf0dc-185">OneDrive: Accounts</span></span>
- <span data-ttu-id="bf0dc-186">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="bf0dc-186">Microsoft 365 groups</span></span>
- <span data-ttu-id="bf0dc-187">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="bf0dc-187">Skype for Business</span></span>

1. <span data-ttu-id="bf0dc-188">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 **[原則]** >  **[保留]**。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-188">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="bf0dc-189">選取 [新保留原則 **]** 以啟動 [建立保留原則] 精靈，並命名新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-189">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="bf0dc-p114">針對 [選擇位置 **]** 頁面，開啟或關閉除 Teams 位置以外的任何位置。您也可以針對每個位置保留預設值，以 [將原則套用到整個位置](#a-policy-that-applies-to-entire-locations)，或 [指定包含和排除](#a-policy-with-specific-inclusions-or-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p114">For the **Choose locations** page, toggle on or off any of the locations except the locations for Teams. For each location, you can leave it at the default to [apply the policy to the entire location](#a-policy-that-applies-to-entire-locations), or [specify includes and excludes](#a-policy-with-specific-inclusions-or-exclusions).</span></span>

    <span data-ttu-id="bf0dc-192">位置專用資訊：</span><span class="sxs-lookup"><span data-stu-id="bf0dc-192">Information specific to locations:</span></span>
    - [<span data-ttu-id="bf0dc-193">Exchange 電子郵件和 Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="bf0dc-193">Exchange email and Exchange public folders</span></span>](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [<span data-ttu-id="bf0dc-194">SharePoint 網站和 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="bf0dc-194">SharePoint sites and OneDrive accounts</span></span>](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [<span data-ttu-id="bf0dc-195">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="bf0dc-195">Microsoft 365 Groups</span></span>](#configuration-information-for-microsoft-365-groups)
    - [<span data-ttu-id="bf0dc-196">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="bf0dc-196">Skype for Business</span></span>](#configuration-information-for-skype-for-business)

4. <span data-ttu-id="bf0dc-197">在精靈的頁面上，如需 **決定是否要保留內容、刪除內容，或兩者皆可**，請指定保留及刪除內容的設定選項。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-197">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>

    <span data-ttu-id="bf0dc-p115">您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定 ](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p115">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time. For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="bf0dc-200">完成精靈以儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-200">Complete the wizard to save your settings.</span></span>

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a><span data-ttu-id="bf0dc-201">Exchange 電子郵件和 Exchange 公用資料夾的設定資訊</span><span class="sxs-lookup"><span data-stu-id="bf0dc-201">Configuration information for Exchange email and Exchange public folders</span></span>

<span data-ttu-id="bf0dc-202">**Exchange 電子郵件** 位置透過套用信箱層級的保留設定，支援使用者的電子郵件、行事曆和其他信箱項目的保留。。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-202">The **Exchange email** location supports retention for users' email, calendar, and other mailbox items, by applying retention settings at the level of a mailbox.</span></span>

<span data-ttu-id="bf0dc-203">如需有關在設定 Exchange 保留設定時包含和排除哪些項目的詳細資訊，請參閱[保留與刪除包含的內容](retention-policies-exchange.md#whats-included-for-retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="bf0dc-203">For detailed information about which items are included and excluded when you configure retention settings for Exchange, see [What's included for retention and deletion](retention-policies-exchange.md#whats-included-for-retention-and-deletion)</span></span>

<span data-ttu-id="bf0dc-p116">請注意，即使 Microsoft 365 群組有 Exchange 信箱，包含整個 **Exchange 電子郵件** 位置的保留原則並不會包含 Microsoft 365 群組信箱中的內容。若要保留 Microsoft 365 群組的內容，請選取 **Microsoft 365 群組** 位置。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p116">Note that even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes. To retain content in these mailboxes, select the **Microsoft 365 Groups** location.</span></span>

<span data-ttu-id="bf0dc-206">**Exchange 公用資料夾** 位置會將保留設定套用至所有的公用資料夾，且無法在資料夾或信箱層級套用。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-206">The **Exchange public folders** location applies retention settings to all public folders and can't be applied at the folder or mailbox level.</span></span>

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a><span data-ttu-id="bf0dc-207">SharePoint 網站和 OneDrive 帳戶的設定資訊</span><span class="sxs-lookup"><span data-stu-id="bf0dc-207">Configuration information for SharePoint sites and OneDrive accounts</span></span>

<span data-ttu-id="bf0dc-p117">當您選擇 [SharePoint 網站 **]** 位置時，保留原則即可保留及刪除在 SharePoint 通訊網站中的文件、未由 Microsoft 365 群組連結的小組網站，以及傳統網站。此選項不支援由 Microsoft 365 群組連結的小組網站，而是使用 **Microsoft 365 群組** 位置套用至群組信箱、網站和檔案中的內容。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p117">When you choose the **SharePoint sites** location, the retention policy can retain and delete documents in SharePoint communication sites, team sites that aren't connected by Microsoft 365 groups, and classic sites. Team sites connected by Microsoft 365 groups aren't supported with this option and instead, use the **Microsoft 365 Groups** location that applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="bf0dc-p118">雖然保留原則可套用到網站層級，但只有文件會套用保留設定。如需有關在設定 SharePoint 和 OneDrive 保留設定時所包含和排除之內容的詳細資訊，請參閱[保留與刪除包含的內容](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion)。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p118">Although the retention policy is applied at the site level, only documents have retention settings applied to them. For detailed information about what's included and excluded when you configure retention settings for SharePoint and OneDrive, see [What's included for retention and deletion](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion).</span></span> 

<span data-ttu-id="bf0dc-p119">當您為 SharePoint 網站或 OneDrive 帳戶指定您的位置時，您不需要存取網站的權限，而當你在 [編輯位置 **]** 頁面上指定 URL 時也不會需要進行任何的驗證。不過，您指定的 SharePoint 網站會在精靈結束時進行檢查，以確認其存在。如果此檢查失敗，您會看到一則訊息，指出您輸入的 URL 驗證失敗，且精靈不會建立保留原則，直到驗證檢查通過為止。如果您看到這則訊息，請返回精靈並變更 URL 或從保留原則將網站移除。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p119">When you specify your locations for SharePoint sites or OneDrive accounts, you don't need permissions to access the sites and no validation is done at the time you specify the URL on the **Edit locations** page. However, the SharePoint sites that you specify are checked that they exist at the end of the wizard. If this check fails, you see a message that validation failed for the URL you entered, and the wizard won't create the retention policy until the validation check passes. If you see this message, go back in the wizard to change the URL or remove the site from the retention policy.</span></span>

<span data-ttu-id="bf0dc-216">若要特別指定包含或排除某個 OneDrive 帳戶，URL 的格式要求如下：`https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span><span class="sxs-lookup"><span data-stu-id="bf0dc-216">To specify individual OneDrive accounts to include or exclude, the URL has the following format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span></span>

<span data-ttu-id="bf0dc-217">例如，針對 contoso 租用戶中使用者名稱為 "rsimone" 的使用者：`https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="bf0dc-217">For example, for a user in the contoso tenant that has a user name of "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span></span>

<span data-ttu-id="bf0dc-218">若要驗證租用戶的語法並識別使用者的 URL，請參閱[取得組織中所有使用者的 OneDrive URL 清單](https://docs.microsoft.com/onedrive/list-onedrive-urls) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-218">To verify the syntax for your tenant and identify URLs for users, see [Get a list of all user OneDrive URLs in your organization](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span></span>

### <a name="configuration-information-for-microsoft-365-groups"></a><span data-ttu-id="bf0dc-219">Microsoft 365 群組的設定資訊</span><span class="sxs-lookup"><span data-stu-id="bf0dc-219">Configuration information for Microsoft 365 Groups</span></span>

<span data-ttu-id="bf0dc-p120">若要保留或刪除一個 Microsoft 365 群組 (之前稱為 Office 365 群組) 的內容，請使用 [Microsoft 365 群組 **]** 位置。即使 Microsoft 365 群組有 Exchange 信箱，包含整個 **Exchange 電子郵件** 位置的保留原則並不會包含 Microsoft 365 群組信箱中的內容。此外，雖然 **Exchange 電子郵件** 位置最初可讓您指定要包含或排除的群組信箱，但是當您嘗試儲存保留原則時，您會收到「RemoteGroupMailbox」不是 Exchange 位置的有效選取項目之錯誤。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p120">To retain or delete content for a Microsoft 365 group (formerly Office 365 group), use the **Microsoft 365 Groups** location. Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes. In addition, although the **Exchange email** location initially allows you to specify a group mailbox to be included or excluded, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>

<span data-ttu-id="bf0dc-p121">套用至 Microsoft 365 群組的保留原則包括群組信箱和 SharePoint 小組網站。儲存在 SharePoint 小組網站中的檔案會涵蓋這個位置，但沒有 Teams 聊天或 Teams 頻道訊息，並擁有自己的保留原則位置。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p121">A retention policy applied to a Microsoft 365 group includes the group mailbox and SharePoint teams site. Files stored in the SharePoint teams site are covered with this location, but not Teams chats or Teams channel messages that have their own retention policy locations.</span></span>

### <a name="configuration-information-for-skype-for-business"></a><span data-ttu-id="bf0dc-225">商務用 Skype 的設定資訊</span><span class="sxs-lookup"><span data-stu-id="bf0dc-225">Configuration information for Skype for Business</span></span>

<span data-ttu-id="bf0dc-226">不同於 Exchange 電子郵件，您無法將 Skype 位置的狀態切換為開啟以自動包含所有使用者，但當您開啟該位置時，必須手動選擇您想要保留其交談的使用者：</span><span class="sxs-lookup"><span data-stu-id="bf0dc-226">Unlike Exchange email, you can't toggle the status of the Skype location on to automatically include all users, but when you turn on that location, you must then manually choose the users whose conversations you want to retain:</span></span>

![為保留原則選擇 Skype 位置](../media/skype-location-retention-policies.png)

<span data-ttu-id="bf0dc-p122">當您選取 [選擇使用者 **]** 時，您可以選取 [全選 **]** 方塊，快速包含所有使用者。不過，請務必了解，會將每個使用者算成原則中的一個特定包含。因此如果您選取 [全選 **]** 方塊來包含 1000 位使用者，就如同您手動選取要包含 1000 位使用者一樣，這是商務用 Skype 支援的最大值。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p122">When you select **Choose user**, you can quickly include all users by selecting the **Select all** box. However, it's important to understand that each user counts as a specific inclusion in the policy. So if you include 1,000 users by selecting the **Select all** box, it's the same as if you manually selected 1,000 users to include, which is the maximum supported for Skype for Business.</span></span>

<span data-ttu-id="bf0dc-p123">請注意，[交談歷程記錄 **]** (Outlook 中的資料夾) 是與 Skype 封存無關的功能。使用者可以關閉 [交談歷程記錄 **]**，但會執行 Skype 的封存，方法為將 Skype 交談的複本儲存在使用者無法存取但電子文件探索可以使用的隱藏資料夾中。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p123">Be aware that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving. **Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span>

## <a name="settings-for-retaining-and-deleting-content"></a><span data-ttu-id="bf0dc-233">保留和刪除內容的設定</span><span class="sxs-lookup"><span data-stu-id="bf0dc-233">Settings for retaining and deleting content</span></span>

<span data-ttu-id="bf0dc-234">透過在保留原則中選擇用於保留和刪除內容的設定，您的保留原則會具有下列其中一個設定達一段指定的期間：</span><span class="sxs-lookup"><span data-stu-id="bf0dc-234">By choosing the settings for retaining and deleting content in your retention policy, your retention policy will have one of the following configurations for a specified period of time:</span></span>

- <span data-ttu-id="bf0dc-235">僅保留</span><span class="sxs-lookup"><span data-stu-id="bf0dc-235">Retain-only</span></span>

    <span data-ttu-id="bf0dc-p124">在此設定中，請選擇 [在特定期內保留項目 **]** 和 [在保留期結束時：不做任何處理 **]**。或者，選取 [永遠保留項目 **]**。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p124">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Do nothing**. Or, select **Retain items forever**.</span></span>

- <span data-ttu-id="bf0dc-238">保留然後刪除</span><span class="sxs-lookup"><span data-stu-id="bf0dc-238">Retain and then delete</span></span>

    <span data-ttu-id="bf0dc-239">在此設定中，請選擇 **[在特定期內保留項目]** 和 **在保留期結束時：自動刪除項目**。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-239">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Delete items automatically**.</span></span>

- <span data-ttu-id="bf0dc-240">僅刪除</span><span class="sxs-lookup"><span data-stu-id="bf0dc-240">Delete-only</span></span>

    <span data-ttu-id="bf0dc-241">在此設定中，選擇 **「只有項目達到特定存留期時才刪除它」**。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-241">For this configuration, choose **Only delete items when they reach a certain age**.</span></span>

### <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="bf0dc-242">將內容保留特定一段時間</span><span class="sxs-lookup"><span data-stu-id="bf0dc-242">Retaining content for a specific period of time</span></span>

<span data-ttu-id="bf0dc-p125">設定保留原則時，您可選擇將項目保留特定數天、數月或數年。或者永遠保留項目。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p125">When you configure a retention policy, you choose to retain items for a specific number of days, months, or years. Or alternatively, retain the items forever.</span></span>

<span data-ttu-id="bf0dc-p126">設定保留原則時，您可以選擇無限期保留內容，或將內容保留特定數天、數月或數年。保留時長是從內容的存留期起算，而不是從套用保留原則的時間起算。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p126">When you configure a retention policy, you can choose to retain content indefinitely or for a specific number of days, months, or years. The retention period is calculated from the age of the content, not from when the retention policy is applied.</span></span>

<span data-ttu-id="bf0dc-247">保留期開始時，您還可以選擇建立內容的時間，或者只支援檔案和 SharePoint、OneDrive 和 Office 365 位置的內容上次修改的時間。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-247">For the start of the retention period, you can also choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Office 365 locations, when the content was last modified.</span></span>

<span data-ttu-id="bf0dc-248">範例：</span><span class="sxs-lookup"><span data-stu-id="bf0dc-248">Examples:</span></span>

- <span data-ttu-id="bf0dc-p127">SharePoint：如果您想要將網站集合中的項目在此內容前次修改後保留七年，而且該網站集合中的某文件已有六年未曾修改，則若該文件後續仍未修改，則只會再保留一年。如果該文件重新編輯，則其存留期將會從新的前次修改日期算起，因而會再保留七年。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p127">SharePoint: If you want to retain items in a site collection for seven years after this content is last modified, and a document in that site collection hasn't been modified in six years, the document will be retained for only another year if it's not modified. If the document is edited again, the age of the document is calculated from the new last modified date, and it will be retained for another seven years.</span></span>

- <span data-ttu-id="bf0dc-p128">Exchange：如果您想要將信箱中的項目保留七年，而且六年前已傳送某郵件，則該郵件只會保留一年。對於 Exchange 項目，時間會根據接收電子郵件或寄出電子郵件的日期。根據前次修改時間保留項目只會套用到 OneDrive 和 SharePoint 中的網站內容。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p128">Exchange: If you want to retain items in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year. For Exchange items, the age is based on the date received for incoming email, or the date sent for outgoing email. Retaining items based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>

<span data-ttu-id="bf0dc-254">在保留期間結束時，您可選擇是否要永久刪除內容：</span><span class="sxs-lookup"><span data-stu-id="bf0dc-254">At the end of the retention period, you choose whether you want the content to be permanently deleted:</span></span>

![保留設定頁面](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="bf0dc-256">刪除早於特定存留期的內容</span><span class="sxs-lookup"><span data-stu-id="bf0dc-256">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="bf0dc-257">保留原則可以保留然後刪除項目，或刪除舊項目而不保留它們。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-257">A retention policy can both retain and then delete items, or delete old items without retaining them.</span></span>

<span data-ttu-id="bf0dc-258">在這兩種情況下，如果您的保留原則刪除項目，請務必了解，保留原則所指定的期限並不是從指派原則的時間算起，而是從建立或修改項目的時間算起。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-258">In both cases, if your retention policy deletes items, it's important to understand that the time period specified for a retention policy is calculated from the time when the item was created or modified, and not the time since the policy was assigned.</span></span>

<span data-ttu-id="bf0dc-p129">因此，在第一次指派保留原則之前，尤其是在該原則删除項目時，請首先考慮現有內容的期限以及該原則可能對該內容產生的影響。您也可以在指派新原則前先與使用者溝通，讓他們有足夠的時間來評估可能的影響。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p129">So before you assign a retention policy for the first time, and especially when that policy deletes items, first consider the age of the existing content and how the policy may impact that content. You might also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact.</span></span>

### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="bf0dc-261">套用到整個組織的原則</span><span class="sxs-lookup"><span data-stu-id="bf0dc-261">A policy that applies to entire locations</span></span>

<span data-ttu-id="bf0dc-262">當您選擇位置時，除了商務用 Skype，預設設定是當位置的狀態為 **開啟** 時的 **全部**。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-262">When you choose locations, with the exception of Skype for Business, the default setting is **All** when the status of the location is **On**.</span></span>

<span data-ttu-id="bf0dc-263">將保留原則套用至整個位置的任何組合時，原則可以包含的收件者、網站、帳戶、群組等的數量沒有限制。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-263">When a retention policy applies to any combination of entire locations, there is no limit to the number of recipients, sites, accounts, groups, etc., that the policy can include.</span></span>

<span data-ttu-id="bf0dc-p130">例如，如果原則包含所有 Exchange 電子郵件和所有 SharePoint 網站，無論有多少個網站和收件者都會全部包含。而對於 Exchange，在套用原則後建立的任何新信箱都會自動繼承原則。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p130">For example, if a policy includes all Exchange email and all SharePoint sites, all sites and recipients will be included, no matter how many. And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="bf0dc-266">具有特定包含或排除的原則</span><span class="sxs-lookup"><span data-stu-id="bf0dc-266">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="bf0dc-267">只有當您使用選用設定將保留設定限定為特定使用者、特定 Microsoft 365 群組或特定網站時，需要主要以下限制：</span><span class="sxs-lookup"><span data-stu-id="bf0dc-267">Only if you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits to be aware of:</span></span> 

- <span data-ttu-id="bf0dc-268">保留原則的數目上限：</span><span class="sxs-lookup"><span data-stu-id="bf0dc-268">Maximum numbers for a retention policy:</span></span>
  - <span data-ttu-id="bf0dc-269">1000 個信箱</span><span class="sxs-lookup"><span data-stu-id="bf0dc-269">1,000 mailboxes</span></span>
  - <span data-ttu-id="bf0dc-270">1,000 個 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="bf0dc-270">1,000 Microsoft 365 groups</span></span>
  - <span data-ttu-id="bf0dc-271">1000 個 Teams 私人聊天使用者</span><span class="sxs-lookup"><span data-stu-id="bf0dc-271">1,000 users for Teams private chats</span></span>
  - <span data-ttu-id="bf0dc-272">100 個網站 (OneDrive 或 SharePoint)</span><span class="sxs-lookup"><span data-stu-id="bf0dc-272">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="bf0dc-p131">針對一個租用戶支援的原則也有數目上限：10,000 個。這些項目包括保留原則、保留標籤原則，以及自動套用保留原則。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p131">There is also a maximum number of policies that are supported for a tenant: 10,000. These items include retention policies, retention label policies, and auto-apply retention policies.</span></span>

<span data-ttu-id="bf0dc-275">如果您的保留原則可能受這些限制制約，請使用適用於整個位置的預設設定，因為這些原則沒有任何限制。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-275">If your retention policies are likely to be subject to these limitations, use the default configuration that applies to the entire location because these policies don't have any limitations.</span></span>

<span data-ttu-id="bf0dc-276">若要使用選用設定限定保留設定範圍，請確保該位置的 [狀態 **]** 為 [開啟 **]**，然後使用連結來包含或排除特定使用者、Microsoft 365 群組或網站。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-276">To use the optional configuration to scope your retention settings, make sure the **Status** of that location is **On**, and then use the links to include or exclude specific users, Microsoft 365 groups, or sites.</span></span>

> [!WARNING]
> <span data-ttu-id="bf0dc-p132">如果您設定 [包含] 然後移除最後一個，則設定會還原為該位置的 [全部 **]**。儲存原則前，請確定這是您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p132">If you configure includes and then remove the last one, the configuration reverts to **All** for the location.  Make sure this is the configuration that you intend before you save the policy.</span></span>
>
> <span data-ttu-id="bf0dc-p133">例如，如果您指定一個 SharePoint 網站要包含在設定為刪除資料的保留原則中，然後移除單一網站，則預設所有 SharePoint 網站都會遵守永久刪除資料的保留原則。Exchange 收件者、OneDrive 帳戶、Teams 聊天使用者等都適用。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p133">For example, if you specify one SharePoint site to include in your retention policy that's configured to delete data, and then remove the single site, by default all SharePoint sites will then be subject to the retention policy that permanently deletes data. The same applies to includes for Exchange recipients, OneDrive accounts, Teams chat users etc.</span></span>
>
> <span data-ttu-id="bf0dc-p134">在這種情況下，如果您不想讓該位置的 [全部 **]** 設定遵守保留原則，可以將位置切換為 [關閉]。或者，指定 [排除] 以免於使用原則。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p134">In this scenario, toggle the location off if you don't want the **All** setting for the location to be subject to the retention policy. Alternatively, specify excludes to be exempt from the policy.</span></span>

## <a name="updating-retention-policies"></a><span data-ttu-id="bf0dc-283">更新保留原則</span><span class="sxs-lookup"><span data-stu-id="bf0dc-283">Updating retention policies</span></span>

<span data-ttu-id="bf0dc-284">如果您編輯保留原則，且項目已受限於保留原則中的原始設定，則除了新識別的項目以外，還會將您的更新設定自動套用至這些項目。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-284">If you edit a retention policy and items are already subject to the original settings in your retention policy, your updated settings will be automatically applied to these items in addition to items that are newly identified.</span></span>

<span data-ttu-id="bf0dc-p135">此更新通常相當快，但可能需要數天的時間。當您的 Microsoft 365 位置間的原則複寫完成時，您會在 Microsoft 365 合規性中心看到保留原則的狀態從 [開啟 (擱置)**]** 變更為 [開啟 (成功)**]**。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-p135">Usually this update is fairly quick but can take several days. When the policy replication across your Microsoft 365 locations is complete, you'll see the status of the retention policy in the Microsoft 365 compliance center change from **On (Pending)** to **On (Success)**.</span></span>

## <a name="locking-the-policy-to-prevent-changes"></a><span data-ttu-id="bf0dc-287">鎖定原則以防止變更</span><span class="sxs-lookup"><span data-stu-id="bf0dc-287">Locking the policy to prevent changes</span></span>

<span data-ttu-id="bf0dc-288">如果您需要確保沒有人可以關閉原則、刪除原則或放寬限制，請參閱 [使用「保留鎖定」來限制變更保留原則和保留標籤原則](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="bf0dc-288">If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>
