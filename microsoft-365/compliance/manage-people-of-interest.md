---
title: '管理資料調查中感興趣的人員 (預覽) '
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 瞭解如何管理關注搜尋範圍或查看其資訊的人員，例如連絡人、位置及活動記錄。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 58c590b2d72d7eb265dd4f90679effb7cdf68f79
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285579"
---
# <a name="manage-people-of-interest-in-data-investigations-preview"></a><span data-ttu-id="d85d2-103">管理資料調查中感興趣的人員 (預覽) </span><span class="sxs-lookup"><span data-stu-id="d85d2-103">Manage people of interest in Data Investigations (preview)</span></span>

<span data-ttu-id="d85d2-104">資料調查常常會包含感興趣的人員。</span><span class="sxs-lookup"><span data-stu-id="d85d2-104">Data investigations often involve people of interest.</span></span> <span data-ttu-id="d85d2-105">通常，他們是擁有您正在調查或想要補救之誤寫、機密或惡意資料的人員。</span><span class="sxs-lookup"><span data-stu-id="d85d2-105">Usually they are people who own the misplaced, sensitive, or malicious data that you're investigating or looking to remediate.</span></span> <span data-ttu-id="d85d2-106">在 [ \*\*資料調查 (預覽) \*\*] 中，您可以新增它們，以探索用於限定搜尋範圍的資料來源或查看其他資訊，例如連絡人、位置及活動記錄。</span><span class="sxs-lookup"><span data-stu-id="d85d2-106">In **Data Investigations (preview)**, you can add them to discover their data sources to use in scoping your search or view additional information such as contact, location, and activity logs.</span></span> 


## <a name="add-people-of-interest"></a><span data-ttu-id="d85d2-107">新增感興趣的人員</span><span class="sxs-lookup"><span data-stu-id="d85d2-107">Add people of interest</span></span>

<span data-ttu-id="d85d2-108">在 [ **興趣人** ] 索引標籤中，您可以新增感興趣的人員，並探索其資料來源，例如可用於限定搜尋範圍的 Exchange 信箱或商務網站 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="d85d2-108">In **People of interest** tab, you can add people of interest and discover their data sources such as Exchange mailboxes or OneDrive for Business site that you can use to scope your search.</span></span> <span data-ttu-id="d85d2-109">依興趣的人員劃分範圍時，搜尋會變得更高的性能及準確性，因為此工具會 reprocesses 任何未編制索引的資料，例如影像或不受支援的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="d85d2-109">When scoped down by people of interest, searches are more performant and accurate because the tool reprocesses any unindexed data such as images or unsupported file types.</span></span> <span data-ttu-id="d85d2-110">您也可以查看其連絡人資訊、位置資訊和活動記錄，您可以用來發起通訊或進一步調查其活動。</span><span class="sxs-lookup"><span data-stu-id="d85d2-110">You can also see their contact information, location information and activity logs that you can use to initiate communications or further investigate their activities.</span></span> 

<span data-ttu-id="d85d2-111">若要新增調查的興趣人員：</span><span class="sxs-lookup"><span data-stu-id="d85d2-111">To add people of interest to an investigation:</span></span>

1. <span data-ttu-id="d85d2-112">從 [ \*\*資料調查 (預覽) \*\* ] 頁面上，移至您的調查。</span><span class="sxs-lookup"><span data-stu-id="d85d2-112">From the **Data Investigations (preview)** page, go to your investigation.</span></span>
 
2. <span data-ttu-id="d85d2-113">選取調查後，請移至 [ **興趣人員** ] 索引標籤，然後按一下 [ **新增感興趣的人員**]。</span><span class="sxs-lookup"><span data-stu-id="d85d2-113">After you have selected an investigation, go to the **People of interest** tab and click **+ Add people of interest**.</span></span> 
 
3. <span data-ttu-id="d85d2-114">選擇您想要新增至調查的人員。</span><span class="sxs-lookup"><span data-stu-id="d85d2-114">Choose people that you want to add to the investigation.</span></span> <span data-ttu-id="d85d2-115">您可以從輸入搜尋並選取您組織的 Azure Active Directory 中的使用者。</span><span class="sxs-lookup"><span data-stu-id="d85d2-115">You can start by typing to search and select the users from your organization's Azure Active Directory.</span></span>
 
4. <span data-ttu-id="d85d2-116">完成感興趣的人員清單後，請按 **[下一步]** 以對應其資料來源。</span><span class="sxs-lookup"><span data-stu-id="d85d2-116">After you have finalized the list of people of interest, click **Next** to map their data sources.</span></span> 

5. <span data-ttu-id="d85d2-117">選針對每位人員，選取 [ **Exchange** ] 以新增人員的主要 Exchange 信箱，並 **OneDrive** 新增人員的主要 OneDrive 的商務網站。</span><span class="sxs-lookup"><span data-stu-id="d85d2-117">[Optional] For each person, select **Exchange** to add person's primary Exchange mailbox, and **OneDrive** to add person's primary OneDrive for Business site.</span></span>

6. <span data-ttu-id="d85d2-118">選按 **[下一步]** ，新增您要與感興趣的人員產生關聯的任何其他資料來源。</span><span class="sxs-lookup"><span data-stu-id="d85d2-118">[Optional] Click **Next** to add any additional data sources that you want to associate with your people of interest.</span></span>

7. <span data-ttu-id="d85d2-119">選選取 [ **更新** ]，將內容位置（例如信箱、網站及小組）指派給人員。</span><span class="sxs-lookup"><span data-stu-id="d85d2-119">[Optional] Select **Update** to assign content locations, like mailboxes, sites, and Teams to a person.</span></span> 

8. <span data-ttu-id="d85d2-120">選在浮出控制項中：</span><span class="sxs-lookup"><span data-stu-id="d85d2-120">[Optional] In the flyout:</span></span>
   
    -  <span data-ttu-id="d85d2-121">**Exchange 信箱** -按一下 **[選擇使用者、群組或小組** ]，然後再按一下 **[選擇使用者、群組或小組** ]。</span><span class="sxs-lookup"><span data-stu-id="d85d2-121">**Exchange Mailboxes** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again.</span></span> <span data-ttu-id="d85d2-122">若要新增更多信箱，請使用搜尋方塊尋找使用者信箱和通訊群組。</span><span class="sxs-lookup"><span data-stu-id="d85d2-122">To add more mailboxes, use the search box to find user mailboxes and distribution groups.</span></span> <span data-ttu-id="d85d2-123">您也可以新增用來儲存 Microsoft 365 群組或 Microsoft 小組資訊的信箱。</span><span class="sxs-lookup"><span data-stu-id="d85d2-123">You can also add mailboxes used to store a Microsoft 365 Group or a Microsoft Team information.</span></span> <span data-ttu-id="d85d2-124">選取 [使用者、群組、小組] 核取方塊，按一下 **[選擇**]，然後按一下 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="d85d2-124">Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="d85d2-125">當您按一下 [選擇使用者、群組或小組以指定信箱] 時，顯示的信箱選擇器會是空的。</span><span class="sxs-lookup"><span data-stu-id="d85d2-125">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty.</span></span> <span data-ttu-id="d85d2-126">這項設計的目的是提升效能。</span><span class="sxs-lookup"><span data-stu-id="d85d2-126">This is by design to enhance performance.</span></span> <span data-ttu-id="d85d2-127">若要將人員新增至此清單，請在搜尋方塊中輸入 (至少3個字元) 名稱。</span><span class="sxs-lookup"><span data-stu-id="d85d2-127">To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>
     
     - <span data-ttu-id="d85d2-128">**SharePoint 網站** -按一下 **[選擇網站** ]，然後按一下 **[選擇網站** ]，以指定您要新增至人員的商務網站的其他 SharePoint 和 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="d85d2-128">**SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify additional SharePoint and OneDrive for Business sites that you want to add to a person.</span></span> <span data-ttu-id="d85d2-129">您也可以為 Microsoft 365 群組或 Microsoft 團隊新增 SharePoint 網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="d85d2-129">You can also add the URL for the SharePoint site for a Microsoft 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="d85d2-130">輸入每個要指派之網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="d85d2-130">Type the URL for each site that you want to assign.</span></span> <span data-ttu-id="d85d2-131">按一下 **[選擇**]，然後按一下 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="d85d2-131">Click **Choose**, and then click **Done**.</span></span>
     - <span data-ttu-id="d85d2-132">**Microsoft 小組** –按一下 **[選擇小組** ]，然後按一下 **[選擇小組** ]，以查看人員目前隸屬的 Microsoft 小組群組清單。</span><span class="sxs-lookup"><span data-stu-id="d85d2-132">**Microsoft Teams** – Click **Choose Teams** and then click **Choose Teams** again to view a list of Microsoft Team groups that the person is a member of today.</span></span> <span data-ttu-id="d85d2-133">選取您要新增至人員的團隊。</span><span class="sxs-lookup"><span data-stu-id="d85d2-133">Select the Teams that you want to add to the person.</span></span> <span data-ttu-id="d85d2-134">選取之後，系統會自動識別 & 選取相關聯的 SharePoint 網站與該 Microsoft 團隊相關聯的群組信箱。</span><span class="sxs-lookup"><span data-stu-id="d85d2-134">Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team.</span></span> <span data-ttu-id="d85d2-135">按一下 **[選擇**]，然後按一下 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="d85d2-135">Click **Choose**, and then click **Done**.</span></span>
        
      > [!NOTE]
      > <span data-ttu-id="d85d2-136">若要新增其他 Microsoft 團隊，您必須以上述方式個別新增信箱和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="d85d2-136">To add additional Microsoft Teams, you will need to separately add the mailbox and SharePoint site as shown above.</span></span>

<span data-ttu-id="d85d2-137">完成將資料來源對應給感興趣的人員之後，您可以看到您剛新增的信箱、網站和團隊總數摘要。</span><span class="sxs-lookup"><span data-stu-id="d85d2-137">After you have finished mapping data sources to people of interest, you can see the summary of total mailboxes, sites, and Teams that you just added.</span></span> <span data-ttu-id="d85d2-138">如果您將任何其他資料來源對應到感興趣的人員，並將您的搜尋範圍限定在調查中，請將檔對應到其關注的利益人，這樣就能更輕鬆地組織證據或產生報表的相關人員。</span><span class="sxs-lookup"><span data-stu-id="d85d2-138">If you map any additional data sources to people of interest and scope your search by people of interest, the mapping of document to people of interest persist throughout the investigation, making it easier to organize evidence or generate report by people of interest.</span></span> 

## <a name="view-additional-people-of-interest-information"></a><span data-ttu-id="d85d2-139">查看其他感興趣資訊的人員</span><span class="sxs-lookup"><span data-stu-id="d85d2-139">View additional people of interest information</span></span>

<span data-ttu-id="d85d2-140">在 [ **興趣人** ] 索引標籤中，按一下您新增的人員。</span><span class="sxs-lookup"><span data-stu-id="d85d2-140">In **People of interest** tab, click on a person that you added.</span></span> <span data-ttu-id="d85d2-141">在飛入的視窗中，您將會看到：</span><span class="sxs-lookup"><span data-stu-id="d85d2-141">In a flyout, you'll see:</span></span>

- <span data-ttu-id="d85d2-142">連絡人資訊</span><span class="sxs-lookup"><span data-stu-id="d85d2-142">Contact information</span></span>

  - <span data-ttu-id="d85d2-143">**顯示名稱**：顯示在通訊錄中的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="d85d2-143">**Display Name**: The person's name displayed in the address book.</span></span> <span data-ttu-id="d85d2-144">這通常是名字、中間名首字母和姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="d85d2-144">This is usually the combination of first name, middle initial, and last name.</span></span>
  - <span data-ttu-id="d85d2-145">**Mail/SMTP**：人員的 SMTP 位址，例如，jeff@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="d85d2-145">**Mail/SMTP**: The SMTP address of the person, for example, jeff@contoso.onmicrosoft.com.</span></span>  
  - <span data-ttu-id="d85d2-146">**職稱**：職稱。</span><span class="sxs-lookup"><span data-stu-id="d85d2-146">**Title**: Job title.</span></span>
  - <span data-ttu-id="d85d2-147">**部門**：人員在其中運作之部門的名稱。</span><span class="sxs-lookup"><span data-stu-id="d85d2-147">**Department**: The name of the department in which the person works.</span></span>
  - <span data-ttu-id="d85d2-148">**管理員**：人員的主管。</span><span class="sxs-lookup"><span data-stu-id="d85d2-148">**Manager**: The person's manager.</span></span> <span data-ttu-id="d85d2-149">管理員接收此人員的任何升級通訊。</span><span class="sxs-lookup"><span data-stu-id="d85d2-149">Manager receives any escalation communications for this person.</span></span>
  
- <span data-ttu-id="d85d2-150">位置資訊</span><span class="sxs-lookup"><span data-stu-id="d85d2-150">Location information</span></span>

  - <span data-ttu-id="d85d2-151">**City**：人員所在的城市。</span><span class="sxs-lookup"><span data-stu-id="d85d2-151">**City**: The city in which the person is located.</span></span>
  - <span data-ttu-id="d85d2-152">**州**：人員所在的省或市。</span><span class="sxs-lookup"><span data-stu-id="d85d2-152">**State**: The state or province in which the person is located.</span></span>
  - <span data-ttu-id="d85d2-153">**國家/地區**：人員所在的國家/地區;例如 "US" 或 "UK"。</span><span class="sxs-lookup"><span data-stu-id="d85d2-153">**Country/Region**: The country/region in which the person is located; for example, "US" or "UK".</span></span>
  - <span data-ttu-id="d85d2-154">**Office**：人員的辦公室地點。</span><span class="sxs-lookup"><span data-stu-id="d85d2-154">**Office**: The office location of the person.</span></span>

- <span data-ttu-id="d85d2-155">處理狀態</span><span class="sxs-lookup"><span data-stu-id="d85d2-155">Processing status</span></span>

  - <span data-ttu-id="d85d2-156">**索引狀態**：深入索引資料來源的狀態</span><span class="sxs-lookup"><span data-stu-id="d85d2-156">**Indexing status**: Status of deep indexing the data sources</span></span>
  - <span data-ttu-id="d85d2-157">**索引上次更新時間**：上次觸發深層索引工作的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="d85d2-157">**Indexing Last Updated Time**: Timestamp of when the deep indexing job was last triggered.</span></span>
  - <span data-ttu-id="d85d2-158">**資料來源**：顯示對應至人員的信箱、網站及小組計數</span><span class="sxs-lookup"><span data-stu-id="d85d2-158">**Data sources**: Shows the count of mailboxes, sites, and Teams mapped to the person</span></span>

- <span data-ttu-id="d85d2-159">更新索引</span><span class="sxs-lookup"><span data-stu-id="d85d2-159">Update index</span></span>
    - <span data-ttu-id="d85d2-160">您可以將此人的資料來源重新編制索引。</span><span class="sxs-lookup"><span data-stu-id="d85d2-160">You can reindex this person's data sources.</span></span> 

- <span data-ttu-id="d85d2-161">View activity</span><span class="sxs-lookup"><span data-stu-id="d85d2-161">View activity</span></span> 

    - <span data-ttu-id="d85d2-162">您可以查看和搜尋使用者的活動記錄。</span><span class="sxs-lookup"><span data-stu-id="d85d2-162">You can view and search user's activity logs.</span></span> <span data-ttu-id="d85d2-163">如需詳細資訊，請參閱 [View 計息人員活動](view-people-of-interest-activity.md)</span><span class="sxs-lookup"><span data-stu-id="d85d2-163">For more information, see [View people of interest activity](view-people-of-interest-activity.md)</span></span> 
