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
description: 透過保留原則，您可以主動決定要保留內容、刪除內容，還是兩者 (保留然後刪除內容)；將單一原則套用到整個組織或套用到特定位置或使用者；以及將原則套用到所有內容或套用到符合特定條件的內容。
ms.openlocfilehash: 35c93ed6ee942f9553e196d3f15634e53c0bf25d
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352230"
---
# <a name="create-and-configure-retention-policies"></a><span data-ttu-id="62825-103">建立及設定保留原則</span><span class="sxs-lookup"><span data-stu-id="62825-103">Create and configure retention policies</span></span>

><span data-ttu-id="62825-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="62825-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="62825-105">使用保留原則主動決定是否要保留內容、刪除內容，還是兩者，即保留然後刪除內容。</span><span class="sxs-lookup"><span data-stu-id="62825-105">Use a retention policy to decide proactively whether to retain content, delete content, or both - retain and then delete the content.</span></span> 

<span data-ttu-id="62825-106">如需保留原則運作方式的相關資訊，請參閱[了解保留原則](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="62825-106">For information about how retention policies work, see [Learn about retention policies](retention-policies.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="62825-107">開始之前</span><span class="sxs-lookup"><span data-stu-id="62825-107">Before you begin</span></span>

<span data-ttu-id="62825-108">您的合規性團隊中負責建立和管理保留原則的成員，必須具備 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)的權限。</span><span class="sxs-lookup"><span data-stu-id="62825-108">Members of your compliance team who will create and manage retention policies need permissions to the [Microsoft 365 Compliance Center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="62825-109">根據預設，租用戶系統管理員將可存取此位置，並且可直接讓法務人員與其他人存取，而不需要為其提供租用戶系統管理員的所有權限。若要這麼做，我們建議您：移至 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)的 [權限]\*\*\*\* 頁面、編輯 [合規性系統管理員]\*\*\*\* 系統管理員角色，並將該成員新增到該角色群組。</span><span class="sxs-lookup"><span data-stu-id="62825-109">By default, your tenant admin has access to this location and can give compliance officers and other people access without giving them all the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the [Microsoft 365 Compliance Center](https://compliance.microsoft.com/), edit the **Compliance administrator** admin role, and add members to that role group.</span></span> 

<span data-ttu-id="62825-110">需要這些權限才能建立及套用保留原則。</span><span class="sxs-lookup"><span data-stu-id="62825-110">These permissions are required only to create and apply a retention policy.</span></span> <span data-ttu-id="62825-111">設定保留原則的人員不需要存取內容。</span><span class="sxs-lookup"><span data-stu-id="62825-111">The person configuring the retention policy doesn't require access to the content.</span></span>

## <a name="create-and-configure-a-retention-policy"></a><span data-ttu-id="62825-112">建立及設定保留原則</span><span class="sxs-lookup"><span data-stu-id="62825-112">Create and configure a retention policy</span></span>

1. <span data-ttu-id="62825-113">從 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 [原則]\*\*\*\*  >  [保留]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="62825-113">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="62825-114">選取 [新增保留原則]\*\*\*\* 或編輯現有的保留原則。</span><span class="sxs-lookup"><span data-stu-id="62825-114">Select **New retention policy** or edit an exiting retention policy.</span></span>

3. <span data-ttu-id="62825-115">針對 [設定]\*\*\*\*，先指定保留及刪除內容的設定選項。</span><span class="sxs-lookup"><span data-stu-id="62825-115">For **Settings**, first specify the configuration options for retaining and deleting content.</span></span> <span data-ttu-id="62825-116">您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。</span><span class="sxs-lookup"><span data-stu-id="62825-116">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="62825-117">如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定](#settings-for-retaining-and-deleting-content)：</span><span class="sxs-lookup"><span data-stu-id="62825-117">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page:</span></span>
    
    <span data-ttu-id="62825-118">然後決定應該將保留原則套用至所有內容，或套用至符合特定條件的內容。</span><span class="sxs-lookup"><span data-stu-id="62825-118">Then, decide whether the retention policy should apply to all content, or content that meets specific conditions.</span></span> <span data-ttu-id="62825-119">如需有關這些進階保留設定的詳細資訊，請參閱此頁面上的[用來識別符合特定條件內容的進階設定](#advanced-settings-to-identify-content-that-meets-specific-conditions)。</span><span class="sxs-lookup"><span data-stu-id="62825-119">For more information about these advanced retention settings, see [Advanced settings to identify content that meets specific conditions](#advanced-settings-to-identify-content-that-meets-specific-conditions) on this page.</span></span> 

4. <span data-ttu-id="62825-120">針對 [選擇位置]\*\*\*\* 頁面，選取保留原則是否應套用至組織中所有支援的位置，或您想要指定位置。</span><span class="sxs-lookup"><span data-stu-id="62825-120">For the **Choose locations** page, select whether the retention policy should apply to all supported locations across your organization, or you want to specify the locations.</span></span> <span data-ttu-id="62825-121">如果您選擇特定位置，則也可以指定包含和排除。</span><span class="sxs-lookup"><span data-stu-id="62825-121">If you choose specific locations, you can also specify includes and excludes.</span></span> 
    
    <span data-ttu-id="62825-122">若為 Microsoft Teams：</span><span class="sxs-lookup"><span data-stu-id="62825-122">For Microsoft Teams:</span></span> 
    - <span data-ttu-id="62825-123">如果您想要刪除或保留 Teams 頻道訊息或Teams 聊天，您必須選取選擇特定位置的選項。</span><span class="sxs-lookup"><span data-stu-id="62825-123">You must select the option to choose specific locations if you want to delete or retain Teams channel messages or Team chats.</span></span> <span data-ttu-id="62825-124">當您選取這些選項的其中一個做為位置時，即會自動排除其他位置，因為包含此 Teams 資料的保留原則不能包含其他位置。</span><span class="sxs-lookup"><span data-stu-id="62825-124">When you select either of these options as locations, the other locations are automatically excluded because a retention policy that includes this Teams data can't include other locations.</span></span> 
    - <span data-ttu-id="62825-125">請注意，針對 **Teams 頻道訊息**，會包含來自標準頻道的訊息，但不會包含[私人頻道](https://docs.microsoft.com/microsoftteams/private-channels)的訊息。</span><span class="sxs-lookup"><span data-stu-id="62825-125">Note that for **Teams channel messages**, message from standard channels but not [private channels](https://docs.microsoft.com/microsoftteams/private-channels) are included.</span></span> <span data-ttu-id="62825-126">當您選取 [Teams 聊天]\*\*\*\* 位置時，會將來自私人頻道的訊息包含為群組聊天。</span><span class="sxs-lookup"><span data-stu-id="62825-126">Messages from private channels are included for users as group chats when you select the **Teams chats** location.</span></span>
    
    <span data-ttu-id="62825-127">如需在組織的保留原則或特定位置之間選擇的詳細資訊，請參閱此頁面上的[將保留原則套用到整個組織或特定位置](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)。</span><span class="sxs-lookup"><span data-stu-id="62825-127">For more information about choosing between a retention policy for the organization or for specific locations, see [Applying a retention policy to an entire organization or specific locations](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations) on this page.</span></span>
    
    <span data-ttu-id="62825-128">如需 **Office 365 群組**和**商務用 Skype**的特定資訊，請參閱下列小節：[Microsoft 365 群組的設定資訊](#configuration-information-for-microsoft-365-groups)和[商務用 Skype 的設定資訊](#configuration-information-for-skype-for-business)。</span><span class="sxs-lookup"><span data-stu-id="62825-128">For information specific to **Office 365 groups** and **Skype for Business**, see the following sections, [Configuration information for Microsoft 365 groups](#configuration-information-for-microsoft-365-groups) and [Configuration information for Skype for Business](#configuration-information-for-skype-for-business).</span></span>

5. <span data-ttu-id="62825-129">完成精靈以儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="62825-129">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="62825-130">當您有多個保留原則時，請參閱[系統會優先處理保留原則嗎？](retention-policies.md#the-principles-of-retention-or-what-takes-precedence)</span><span class="sxs-lookup"><span data-stu-id="62825-130">When you have more than one retention policy, see [The principles of retention, or what takes precedence?](retention-policies.md#the-principles-of-retention-or-what-takes-precedence)</span></span>

### <a name="configuration-information-for-microsoft-365-groups"></a><span data-ttu-id="62825-131">Microsoft 365 群組的設定資訊</span><span class="sxs-lookup"><span data-stu-id="62825-131">Configuration information for Microsoft 365 groups</span></span>

<span data-ttu-id="62825-132">若要保留或刪除 Microsoft 365 群組 (先前稱為 Office 365 群組) 的內容，請在選擇保留原則的位置時，選取 [Office 365 群組]\*\*\*\* 位置。</span><span class="sxs-lookup"><span data-stu-id="62825-132">To retain or delete content for a Microsoft 365 group (formerly Office 365 group), select the **Office 365 groups** location when you choose locations for your retention policy.</span></span> <span data-ttu-id="62825-133">即使 Microsoft 365 群組有 Exchange 信箱，包含整個 **Exchange 電子郵件**位置的保留原則並不會包含 Microsoft 365 群組信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="62825-133">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="62825-134">此外，雖然 **Exchange 電子郵件**位置一開始會允許您指定要包含或排除的群組信箱，但是當您嘗試儲存保留原則時，您會收到 "RemoteGroupMailbox" 不是Exchange 位置的有效選項錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="62825-134">In addition, although the **Exchange email** location initially allows you to specify a group mailbox to be included or excluded, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>

<span data-ttu-id="62825-135">套用到 Microsoft 365 群組的保留原則同時包含群組信箱和網站。</span><span class="sxs-lookup"><span data-stu-id="62825-135">A retention policy applied to an Microsoft 365 group includes both the group mailbox and site.</span></span> <span data-ttu-id="62825-136">套用至 Microsoft 365 群組的保留原則可保護由 Microsoft 365 群組所建立的資源，其中包括 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="62825-136">A retention policy applied to a Microsoft 365 group protects the resources created by a Microsoft 365 group, which includes Microsoft Teams.</span></span>

### <a name="configuration-information-for-skype-for-business"></a><span data-ttu-id="62825-137">商務用 Skype 的設定資訊</span><span class="sxs-lookup"><span data-stu-id="62825-137">Configuration information for Skype for Business</span></span>

<span data-ttu-id="62825-138">不同於 Exchange 電子郵件，您無法將 Skype 位置的狀態切換為開啟以包含所有使用者，但當您開啟該位置時，可以手動選擇您想要保留其交談的使用者：</span><span class="sxs-lookup"><span data-stu-id="62825-138">Unlike Exchange email, you can't toggle the status of the Skype location on to include all users, but when you turn on that location, you then manually choose the users whose conversations you want to retain:</span></span>

![為保留原則選擇 Skype 位置](../media/skype-location-retention-policies.png)
  
<span data-ttu-id="62825-140">當您選取 [選擇使用者]\*\*\*\* 時，您可以選取欄標題中的 [名稱]\*\*\*\* 方塊，快速包含所有使用者。</span><span class="sxs-lookup"><span data-stu-id="62825-140">When you select **Choose users**, you can quickly include all users by selecting the **Name** box in the column header.</span></span> <span data-ttu-id="62825-141">不過，請務必了解，會將每個使用者算成原則中的一個特定包含。</span><span class="sxs-lookup"><span data-stu-id="62825-141">However, it's important to understand that each user counts as a specific inclusion in the policy.</span></span> <span data-ttu-id="62825-142">因此，如果您包含超過 1,000 個使用者，則會套用上一節提及的限制。</span><span class="sxs-lookup"><span data-stu-id="62825-142">Therefore, if you include over 1,000 users, the limits noted in the previous section apply.</span></span> <span data-ttu-id="62825-143">在這裡選取所有 Skype 使用者，和整個組織的原則能夠根據預設包含所有 Skype 使用者並不一樣。</span><span class="sxs-lookup"><span data-stu-id="62825-143">Selecting all Skype users here is not the same as if an org-wide policy were able to include all Skype users by default.</span></span> 
  
![選擇 Skype 使用者頁面](../media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
<span data-ttu-id="62825-p111">請注意，**交談歷程記錄** (Outlook 中的資料夾) 是與 Skype 封存無關的功能。使用者可以關閉**交談歷程記錄**，但會執行 Skype 的封存，方法為將 Skype 交談的複本儲存在使用者無法存取但電子文件探索可以使用的隱藏資料夾中。</span><span class="sxs-lookup"><span data-stu-id="62825-p111">Note that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving. **Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span>


## <a name="settings-for-retaining-and-deleting-content"></a><span data-ttu-id="62825-147">保留和刪除內容的設定</span><span class="sxs-lookup"><span data-stu-id="62825-147">Settings for retaining and deleting content</span></span>

<span data-ttu-id="62825-148">透過在保留原則中選擇用於保留和刪除內容的設定，您的保留原則會具有下列其中一個設定達一段指定的期間：</span><span class="sxs-lookup"><span data-stu-id="62825-148">By choosing the settings for retaining and deleting content in your retention policy, your retention policy will have one of the following configurations for a specified period of time:</span></span>

- <span data-ttu-id="62825-149">僅保留</span><span class="sxs-lookup"><span data-stu-id="62825-149">Retain-only</span></span>
- <span data-ttu-id="62825-150">保留然後刪除</span><span class="sxs-lookup"><span data-stu-id="62825-150">Retain and then delete</span></span>
- <span data-ttu-id="62825-151">僅刪除</span><span class="sxs-lookup"><span data-stu-id="62825-151">Delete-only</span></span>

### <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="62825-152">將內容保留特定的一段時間</span><span class="sxs-lookup"><span data-stu-id="62825-152">Retaining content for a specific period of time</span></span>

<span data-ttu-id="62825-153">設定保留原則時，您會選擇無限期保留內容，或將內容保留特定數天、數月或數年。</span><span class="sxs-lookup"><span data-stu-id="62825-153">When you configure a retention policy, you choose to retain content indefinitely or for a specific number of days, months, or years.</span></span> <span data-ttu-id="62825-154">保留內容的持續時間是從內容的存留期起算，而不是從套用保留原則的時間起算。</span><span class="sxs-lookup"><span data-stu-id="62825-154">The duration for how long content is retained is calculated from the age of the content, not from when the retention policy is applied.</span></span> <span data-ttu-id="62825-155">您可以選擇存留期是否要根據內容建立的時間，或前次修改的時間 (針對 OneDrive 和 SharePoint)。</span><span class="sxs-lookup"><span data-stu-id="62825-155">You can choose whether the age is based on when the content was created or (for OneDrive and SharePoint) when it was last modified.</span></span>

<span data-ttu-id="62825-156">範例：</span><span class="sxs-lookup"><span data-stu-id="62825-156">Examples:</span></span>
  
- <span data-ttu-id="62825-157">SharePoint：如果您在將網站集合中的內容自上次修改起保留七年，而該網站集合中的某文件已有六年未曾修改，如果後續仍未修改該文件，則只會再保留該文件一年。</span><span class="sxs-lookup"><span data-stu-id="62825-157">SharePoint: If you want to retain content in a site collection for seven years since it was last modified, and a document in that site collection hasn't been modified in six years, the document will be retained for only another year if it's not modified.</span></span> <span data-ttu-id="62825-158">如果該文件重新編輯，則其存留期將會從新的前次修改日期起算，因而會再保留七年。</span><span class="sxs-lookup"><span data-stu-id="62825-158">If the document is edited again, the age of the document is calculated from the new last modified date, and it will be retained for another seven years.</span></span>
  
- <span data-ttu-id="62825-159">Exchange：同樣地，如果您要讓信箱中的內容保留七年，而六年前已傳送過某封郵件，該郵件則只會再保留一年。</span><span class="sxs-lookup"><span data-stu-id="62825-159">Exchange: If you want to retain content in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year.</span></span> <span data-ttu-id="62825-160">若為 Exchange 內容，時限是以收到內送電子郵件的日期，或傳送外寄電子郵件的日期為基礎。</span><span class="sxs-lookup"><span data-stu-id="62825-160">For Exchange content, the age is based on the date received for incoming email, or the date sent for outgoing email.</span></span> <span data-ttu-id="62825-161">根據前次修改時間保留內容只會套用到 OneDrive 和 SharePoint 中的網站內容。</span><span class="sxs-lookup"><span data-stu-id="62825-161">Retaining content based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>
  
<span data-ttu-id="62825-162">在保留期間結束時，您會選擇是否要永久刪除內容：</span><span class="sxs-lookup"><span data-stu-id="62825-162">At the end of the retention period, you choose whether you want the content to be permanently deleted:</span></span>
  
![保留設定頁面](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="62825-164">刪除早於特定存留期的內容</span><span class="sxs-lookup"><span data-stu-id="62825-164">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="62825-165">保留原則可以保留然後刪除內容，或刪除舊內容而不保留它。</span><span class="sxs-lookup"><span data-stu-id="62825-165">A retention policy can both retain and then delete content, or delete old content without retaining it.</span></span>
  
<span data-ttu-id="62825-166">如果您的保留原則刪 內容，請務必了解，文件刪除原則所指定的期限並不是從指派原則的時間算起，而是從建立或修改內容的時間算起。</span><span class="sxs-lookup"><span data-stu-id="62825-166">If your retention policy deletes content, it's important to understand that the time period specified for a retention policy is calculated from the time when the content was created or modified, not the time since the policy was assigned.</span></span>
  
![刪除設定](../media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
<span data-ttu-id="62825-168">例如，假設您建立一個刪除超過三年時間之內容的保留原則，然後將該原則指派給所有 OneDrive 帳戶，而此帳戶包含許多四或五年前建立的內容。</span><span class="sxs-lookup"><span data-stu-id="62825-168">For example, suppose that you create a retention policy that deletes content after three years, and then assign that policy to all OneDrive accounts, which contain a lot of content that was created four or five years ago.</span></span> <span data-ttu-id="62825-169">在此情況下，第一次指派保留原則後，很快地許多內容將會遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="62825-169">In this case, a lot of content will be deleted soon after assigning the retention policy for the first time.</span></span> <span data-ttu-id="62825-170">基於這個原因，請務必了解，會刪除內容的保留原則會對您的內容造成相當大的影響。</span><span class="sxs-lookup"><span data-stu-id="62825-170">For this reason, it's important to understand that a retention policy that deletes content can have a considerable impact on your content.</span></span> 
  
<span data-ttu-id="62825-p116">因此，在第一次將保留原則指派給網站集合之前，您應先考量現有內容的存留期，以及原則對該內容可能造成的影響。您也可以在指派新原則之前先與使用者溝通，讓他們有時間評估可能的影響。請注意，只在您建立保留原則之前，檢閱其設定時才會出現此警告。</span><span class="sxs-lookup"><span data-stu-id="62825-p116">Therefore, before you assign a retention policy to a site collection for the first time, you should first consider the age of the existing content and how the policy may impact that content. You may also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact. Note this warning that appears when you review the settings for your retention policy just before creating it.</span></span>
  
![有關刪除內容的警告](../media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-to-identify-content-that-meets-specific-conditions"></a><span data-ttu-id="62825-175">用來識別符合特定條件內容的進階設定</span><span class="sxs-lookup"><span data-stu-id="62825-175">Advanced settings to identify content that meets specific conditions</span></span>

<span data-ttu-id="62825-176">保留原則可以套用至其包含之位置中的所有內容，或您可以選擇只將保留原則套用到包含特定關鍵字或[特定類型的敏感資訊](what-the-sensitive-information-types-look-for.md)的內容。</span><span class="sxs-lookup"><span data-stu-id="62825-176">A retention policy can apply to all content in the locations that it includes, or you can choose to apply a retention policy only to content that contains specific keywords or [specific types of sensitive information](what-the-sensitive-information-types-look-for.md).</span></span>
  
![進階保留選項](../media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="identify-content-that-contains-specific-keywords"></a><span data-ttu-id="62825-178">識別包含特定關鍵字的內容</span><span class="sxs-lookup"><span data-stu-id="62825-178">Identify content that contains specific keywords</span></span>

<span data-ttu-id="62825-179">您可以將保留原則套用到僅符合特定條件的內容，然後針對該內容執行保留動作。</span><span class="sxs-lookup"><span data-stu-id="62825-179">You can apply a retention policy only to content that meets specific conditions, and then take retention actions on just that content.</span></span> <span data-ttu-id="62825-180">可用的條件可支援將保留原則套用至包含特定字詞或詞組的內容。</span><span class="sxs-lookup"><span data-stu-id="62825-180">The conditions available support applying a retention policy to content that contains specific words or phrases.</span></span> <span data-ttu-id="62825-181">您可以使用 AND、OR 和 NOT 這類搜尋運算子來精簡您的查詢。</span><span class="sxs-lookup"><span data-stu-id="62825-181">You can refine your query by using search operators like AND, OR, and NOT.</span></span> <span data-ttu-id="62825-182">如需有關這些運算子的詳細資訊，請參閱[內容查詢的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="62825-182">For more information on these operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="62825-183">即將推出對新增可搜尋屬性 (例如 **subject:**) 的支援。</span><span class="sxs-lookup"><span data-stu-id="62825-183">Support for adding searchable properties (for example, **subject:**) is coming soon.</span></span>
  
<span data-ttu-id="62825-184">查詢型保留會使用搜尋索引來識別內容。</span><span class="sxs-lookup"><span data-stu-id="62825-184">Query-based retention uses the search index to identify content.</span></span>
  
![查詢編輯器](../media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="identify-content-that-contains-sensitive-information"></a><span data-ttu-id="62825-186">識別包含敏感性資訊的內容</span><span class="sxs-lookup"><span data-stu-id="62825-186">Identify content that contains sensitive information</span></span>

<span data-ttu-id="62825-p118">您也可以只將保留原則套用至包含[特定類型的敏感資訊](what-the-sensitive-information-types-look-for.md)的內容。例如，您可以選擇只將唯一的保留需求套用至包含個人識別資訊 (PII) 的內容，例如納稅人身分識別碼、社會安全編號或護照號碼。</span><span class="sxs-lookup"><span data-stu-id="62825-p118">You can also apply a retention policy only to content that contains [specific types of sensitive information](what-the-sensitive-information-types-look-for.md). For example, you can choose to apply unique retention requirements only to content that contains personally identifiable information (PII) such as taxpayer identification numbers, social security numbers, or passport numbers.</span></span>
  
![敏感資訊類型頁面](../media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
<span data-ttu-id="62825-190">附註：</span><span class="sxs-lookup"><span data-stu-id="62825-190">Notes:</span></span>
  
- <span data-ttu-id="62825-191">敏感資訊的進階保留不適用於 Exchange 公用資料夾或商務用 Skype，因為這些位置不支援敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="62825-191">Advanced retention for sensitive information doesn't apply to Exchange public folders or Skype for Business because those locations don't support sensitive information types.</span></span>
    
- <span data-ttu-id="62825-192">Exchange Online 使用郵件流程規則來識別敏感性資訊 (也稱為傳輸規則)，因此這只適用於傳輸過程中的郵件，而不是所有已儲存在信箱中的項目。</span><span class="sxs-lookup"><span data-stu-id="62825-192">Exchange Online uses mail flow rules (also known as transport rules) to identify sensitive information, so this works only on messages in transit — not on all items already stored in a mailbox.</span></span> <span data-ttu-id="62825-193">對於 Exchange Online，這表示保留原則可識別機密資訊，並只對在原則套用到信箱「之後」\*\*\*\* 收到的郵件執行保留動作。</span><span class="sxs-lookup"><span data-stu-id="62825-193">For Exchange Online, this means that a retention policy can identify sensitive information and take retention actions only on messages that are received **after** the policy is applied to the mailbox.</span></span> <span data-ttu-id="62825-194">上一節所述之以查詢為基礎的保留沒有此限制，因為它使用搜尋索引來識別內容。</span><span class="sxs-lookup"><span data-stu-id="62825-194">Query-based retention described in the previous section doesn't have this limitation because it uses the search index to identify content.</span></span> 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a><span data-ttu-id="62825-195">將保留原則套用到整個組織或特定位置</span><span class="sxs-lookup"><span data-stu-id="62825-195">Applying a retention policy to an entire organization or specific locations</span></span>

<span data-ttu-id="62825-196">您可以輕鬆地將保留原則套用到整個組織、整個位置，或只套用到特定位置或使用者。</span><span class="sxs-lookup"><span data-stu-id="62825-196">You can easily apply a retention policy to an entire organization, entire locations, or only to specific locations or users.</span></span>
  
### <a name="org-wide-policy"></a><span data-ttu-id="62825-197">全組織原則</span><span class="sxs-lookup"><span data-stu-id="62825-197">Org-wide policy</span></span>

<span data-ttu-id="62825-198">保留原則最強大的功能之一，就是它可套用至 Microsoft 365 中的各個位置，包括：</span><span class="sxs-lookup"><span data-stu-id="62825-198">One of the most powerful features of a retention policy is that it can apply to locations across Microsoft 365, including:</span></span>
  
- <span data-ttu-id="62825-199">Exchange 電子郵件</span><span class="sxs-lookup"><span data-stu-id="62825-199">Exchange email</span></span>
    
- <span data-ttu-id="62825-200">SharePoint 網站集合</span><span class="sxs-lookup"><span data-stu-id="62825-200">SharePoint site collections</span></span>
    
- <span data-ttu-id="62825-201">OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="62825-201">OneDrive accounts</span></span>
    
- <span data-ttu-id="62825-202">Microsoft 365 群組 (適用群組信箱和相關聯的 SharePoint 網站中的內容)。</span><span class="sxs-lookup"><span data-stu-id="62825-202">Microsoft 365 groups (applies to content in the group's mailbox and associated SharePoint site.)</span></span>
    
- <span data-ttu-id="62825-203">Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="62825-203">Exchange public folders</span></span>
    

![所有位置選項](../media/retention-policies-all-locations.png)

<span data-ttu-id="62825-205">全組織保留原則的其他重要功能包含：</span><span class="sxs-lookup"><span data-stu-id="62825-205">Other important features of an org-wide retention policy include:</span></span>
  
- <span data-ttu-id="62825-206">原則可以包含的信箱或網站數目沒有任何限制。</span><span class="sxs-lookup"><span data-stu-id="62825-206">There is no limit to the number of mailboxes or sites the policy can include.</span></span>
    
- <span data-ttu-id="62825-207">對於 Exchange，在套用原則後建立的任何新信箱都會自動繼承此原則。</span><span class="sxs-lookup"><span data-stu-id="62825-207">For Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>
  
### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="62825-208">套用到整個組織的原則</span><span class="sxs-lookup"><span data-stu-id="62825-208">A policy that applies to entire locations</span></span>

<span data-ttu-id="62825-209">當您選擇位置時，您可以輕鬆地包含或排除整個位置，例如 Exchange 電子郵件或 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="62825-209">When you choose locations, you can easily include or exclude an entire location, such as Exchange email or OneDrive accounts.</span></span> <span data-ttu-id="62825-210">若要這麼做，請將該位置的 [狀態]\*\*\*\* 切換到開啟或關閉。</span><span class="sxs-lookup"><span data-stu-id="62825-210">To do so, toggle the **Status** of that location on or off.</span></span> 
  
<span data-ttu-id="62825-211">就像整個組織的原則一樣，如果將原則套用到整個組織的任何組合，原則可包含的信箱或網站數量則沒有限制。</span><span class="sxs-lookup"><span data-stu-id="62825-211">Like an org-wide policy, if a policy applies to any combination of entire locations, there is no limit to the number of mailboxes or sites the policy can include.</span></span> 

<span data-ttu-id="62825-212">例如，如果原則包含所有 Exchange 電子郵件和所有 SharePoint 網站，無論有多少個網站和信箱都會全部包含。</span><span class="sxs-lookup"><span data-stu-id="62825-212">For example, if a policy includes all Exchange email and all SharePoint sites, all sites and mailboxes will be included, no matter how many.</span></span> <span data-ttu-id="62825-213">而對於 Exchange，在套用原則後建立的任何新信箱都會自動繼承原則。</span><span class="sxs-lookup"><span data-stu-id="62825-213">And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="62825-214">具有特定包含或排除的原則</span><span class="sxs-lookup"><span data-stu-id="62825-214">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="62825-215">您也可以將保留原則套用至特定使用者、特定 Microsoft 365 群組或特定網站。</span><span class="sxs-lookup"><span data-stu-id="62825-215">You can also apply a retention policy to specific users, specific Microsoft 365 groups, or specific sites.</span></span> <span data-ttu-id="62825-216">若要這麼做，請將該位置的 [狀態]\*\*\*\* 切換到開啟，然後使用連結來包含或排除特定使用者、Microsoft 365 群組或網站。</span><span class="sxs-lookup"><span data-stu-id="62825-216">To do so, toggle the **Status** of that location on, and then use the links to include or exclude specific users, Microsoft 365 groups, or sites.</span></span> 
  
<span data-ttu-id="62825-217">不過，使用此設定時，如果您的保留原則包含或排除超過 1,000 個特定位置，則會有一些限制：</span><span class="sxs-lookup"><span data-stu-id="62825-217">However, using this configuration, there are some limits when your retention policy includes or excludes over 1,000 specific locations:</span></span>
  
- <span data-ttu-id="62825-218">保留原則的數目上限：</span><span class="sxs-lookup"><span data-stu-id="62825-218">Maximum numbers for the retention policy:</span></span>
    - <span data-ttu-id="62825-219">1000 個信箱</span><span class="sxs-lookup"><span data-stu-id="62825-219">1,000 mailboxes</span></span>
    - <span data-ttu-id="62825-220">1,000 個 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="62825-220">1,000 Microsoft 365 groups</span></span>
    - <span data-ttu-id="62825-221">1000 個 Teams 私人聊天使用者</span><span class="sxs-lookup"><span data-stu-id="62825-221">1,000 users for Teams private chats</span></span>
    - <span data-ttu-id="62825-222">100 個網站 (OneDrive 或 SharePoint)</span><span class="sxs-lookup"><span data-stu-id="62825-222">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="62825-223">針對一個租用戶支援的原則數目上限：10,000 個。</span><span class="sxs-lookup"><span data-stu-id="62825-223">There is a maximum number of policies that are supported for a tenant: 10,000.</span></span> <span data-ttu-id="62825-224">這些項目包括保留原則、保留標籤原則，以及自動套用保留原則。</span><span class="sxs-lookup"><span data-stu-id="62825-224">These items include retention policies, retention label policies, and auto-apply retention policies.</span></span>

<span data-ttu-id="62825-225">如果您的保留原則可能受限於這些限制，請選擇適用於整個位置的設定選項，或使用整個組織的原則。</span><span class="sxs-lookup"><span data-stu-id="62825-225">If your retention policies are likely to be subject to these limitations, choose the configuration options that apply to entire locations, or use an org-wide policy.</span></span>

## <a name="updating-retention-policies"></a><span data-ttu-id="62825-226">更新保留原則</span><span class="sxs-lookup"><span data-stu-id="62825-226">Updating retention policies</span></span>

<span data-ttu-id="62825-227">如果您編輯保留原則，且內容已受限於保留原則中的原始設定，則除了新識別的內容以外，還會將您的更新設定自動套用至此內容。</span><span class="sxs-lookup"><span data-stu-id="62825-227">If you edit a retention policy and content is already subject to the original settings in your retention policy, your updated settings will be automatically applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="62825-228">此更新通常相當快，但可能需要數天的時間。</span><span class="sxs-lookup"><span data-stu-id="62825-228">Usually this update is fairly quick but can take several days.</span></span> <span data-ttu-id="62825-229">當您的 Microsoft 365 位置間的原則複寫完成時，您會在 Microsoft 365 合規性中心看到保留原則的狀態從**開啟 (處理中)** 變成**開啟 (成功)**。</span><span class="sxs-lookup"><span data-stu-id="62825-229">When the policy replication across your Microsoft 365 locations is complete, you'll see the status of the retention policy in the Microsoft 365 compliance center change from **On (Pending)** to **On (Success)**.</span></span>

## <a name="find-the-powershell-cmdlets-for-retention-policies"></a><span data-ttu-id="62825-230">尋找保留原則的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="62825-230">Find the PowerShell cmdlets for retention policies</span></span>

<span data-ttu-id="62825-231">若要使用保留原則 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="62825-231">To use the retention policies cmdlets:</span></span>
  
1. [<span data-ttu-id="62825-232">連接到 Office 365 安全性與合規性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="62825-232">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="62825-233">使用這些 Office 365 安全性與合規性中心 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="62825-233">Use these Office 365 Security & Compliance Center cmdlets:</span></span>
    
    - [<span data-ttu-id="62825-234">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="62825-234">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [<span data-ttu-id="62825-235">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="62825-235">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [<span data-ttu-id="62825-236">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="62825-236">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [<span data-ttu-id="62825-237">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="62825-237">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [<span data-ttu-id="62825-238">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="62825-238">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [<span data-ttu-id="62825-239">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="62825-239">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [<span data-ttu-id="62825-240">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="62825-240">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [<span data-ttu-id="62825-241">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="62825-241">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)


## <a name="lock-a-retention-policy-by-using-powershell"></a><span data-ttu-id="62825-242">使用 PowerShell 鎖定保留原則</span><span class="sxs-lookup"><span data-stu-id="62825-242">Lock a retention policy by using PowerShell</span></span>

<span data-ttu-id="62825-243">如果您需要使用[保留鎖定](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)才能符合法規要求，您必須使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="62825-243">You must use PowerShell if you need to need to use [Preservation Lock](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements) to comply with regulatory requirements.</span></span>

1. <span data-ttu-id="62825-244">[連線至 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="62825-244">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="62825-245">執行 `Get-RetentionCompliancePolicy` 來列出您的保留原則清單，並尋找您想要鎖定的原則名稱。</span><span class="sxs-lookup"><span data-stu-id="62825-245">List your retention policies and find the name of the policy that you want to lock by running `Get-RetentionCompliancePolicy`.</span></span>
    
    ![PowerShell 中保留原則的清單](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. <span data-ttu-id="62825-247">若要在保留原則上放置保留鎖定，請執行 `Set-RetentionCompliancePolicy` 時將 `RestrictiveRetention` 參數設為 True。</span><span class="sxs-lookup"><span data-stu-id="62825-247">To place a Preservation Lock on a retention policy, run `Set-RetentionCompliancePolicy` with the `RestrictiveRetention` parameter set to true.</span></span> <span data-ttu-id="62825-248">例如：</span><span class="sxs-lookup"><span data-stu-id="62825-248">For example:</span></span>
    
        Set-RetentionCompliancePolicy -Identity "<Name of Policy>" – RestrictiveRetention $true
    
    ![PowerShell 中的 RestrictiveRetention 參數](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
    <span data-ttu-id="62825-250">執行完該 Cmdlet 之後，請選擇 [全部皆是]\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="62825-250">After you run that cmdlet, choose **Yes to All**:</span></span>
    
    ![確認您在 PowerShell 想要鎖定保留原則的提示。](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="62825-252">保留鎖定現在放置於保留原則上。</span><span class="sxs-lookup"><span data-stu-id="62825-252">A Preservation Lock is now placed on the retention policy.</span></span> <span data-ttu-id="62825-253">如果您執行 `Get-RetentionCompliancePolicy`，`RestrictiveRetention` 參數會設為 true。</span><span class="sxs-lookup"><span data-stu-id="62825-253">If you run `Get-RetentionCompliancePolicy`, the `RestrictiveRetention` parameter is set to true.</span></span> <span data-ttu-id="62825-254">例如：</span><span class="sxs-lookup"><span data-stu-id="62825-254">For example:</span></span>

`Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl`

![PowerShell 中顯示所有參數的鎖定原則](../media/retention-policy-preservation-lock-locked-policy.PNG)
  

