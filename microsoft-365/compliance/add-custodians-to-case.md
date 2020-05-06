---
title: 將保管人新增至高級 eDiscovery 案例
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
description: 瞭解如何在高級電子檔探索中使用內建的保管人管理工具，以協調您的工作流程，並在案例中識別相關的資料來源。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b0c85fb080faeeafd5909c033bc95ef14efc2c45
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034687"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="bf124-103">將保管人新增至高級 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="bf124-103">Add custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="bf124-104">使用高級 eDiscovery 中內建的保管人管理工具，讓您的工作流程與管理保管人的工作流程一致，並識別與案例相關聯的相關 custodial 資料來源。</span><span class="sxs-lookup"><span data-stu-id="bf124-104">Use the built-in custodian management tool in Advanced eDiscovery to coordinate your workflows around managing custodians and identifying relevant, custodial data sources associated with a case.</span></span> <span data-ttu-id="bf124-105">當您新增保管人時，系統會自動針對其 Exchange 信箱和 OneDrive 的商務帳戶，識別並保留其位置。</span><span class="sxs-lookup"><span data-stu-id="bf124-105">When you add a custodian, the system can automatically identify and place a hold on their Exchange mailbox and OneDrive for Business account.</span></span> <span data-ttu-id="bf124-106">在調查的探索過程中，您也可以識別保管人存取或貢獻的其他資料來源（例如信箱、網站或小組）。</span><span class="sxs-lookup"><span data-stu-id="bf124-106">During the discovery process of your investigation, you might also identify additional data sources (such as mailboxes, sites, or Teams) that a custodian accessed or contributed to.</span></span> <span data-ttu-id="bf124-107">在此情況下，您可以使用保管人管理工具，將這些資料來源關聯至特定的保管人。</span><span class="sxs-lookup"><span data-stu-id="bf124-107">In this situation, you can use the custodian management tool to associate those data sources will a specific custodian.</span></span> <span data-ttu-id="bf124-108">在您將保管人新增至案例並與其他資料來源建立關聯之後，您可以快速保存資料並搜尋 custodial 資料。</span><span class="sxs-lookup"><span data-stu-id="bf124-108">After you add custodians to a case and associate other data source with them, you can quickly preserve data and search the custodial data.</span></span>

<span data-ttu-id="bf124-109">使用下列工作流程在高級 eDiscovery 案例中新增及管理保管人。</span><span class="sxs-lookup"><span data-stu-id="bf124-109">Use the following workflow to add and manage custodians in Advanced eDiscovery cases.</span></span> 

![[管理員管理] 索引標籤](../media/CustodianMgtPage.png)

## <a name="before-you-begin"></a><span data-ttu-id="bf124-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="bf124-111">Before you begin</span></span>

<span data-ttu-id="bf124-112">若要將保管人新增至案例，您必須是 eDiscovery 管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="bf124-112">To add custodians to a case, you must be a member of the eDiscovery Manager role group.</span></span> <span data-ttu-id="bf124-113">這會為您提供必要的許可權，以將保管人新增至案例，並在 custodial 資料來源上進行保留。</span><span class="sxs-lookup"><span data-stu-id="bf124-113">This will provide you with the necessary permissions to add custodians to a case and place a hold on the custodial data sources.</span></span>


## <a name="step-1-add-potential-custodians"></a><span data-ttu-id="bf124-114">步驟1：新增可能的保管人</span><span class="sxs-lookup"><span data-stu-id="bf124-114">Step 1: Add potential custodians</span></span>

<span data-ttu-id="bf124-115">第一步是將保管人識別並新增至案例。</span><span class="sxs-lookup"><span data-stu-id="bf124-115">The first step is to identify and add custodians to the case.</span></span>

1. <span data-ttu-id="bf124-116">在「**高級 eDiscovery**首頁」上，按一下您要新增保管人的案例。</span><span class="sxs-lookup"><span data-stu-id="bf124-116">On the **Advanced eDiscovery** home page, click the case that you want to add custodians to.</span></span> 
 
2. <span data-ttu-id="bf124-117">按一下 [**保管人**] 索引標籤，然後按一下 [ **+ 新增保管人**]。</span><span class="sxs-lookup"><span data-stu-id="bf124-117">Click the **Custodians** tab and then click **+ Add custodians**.</span></span>

3. <span data-ttu-id="bf124-118">尋找要新增至案例的保管人。</span><span class="sxs-lookup"><span data-stu-id="bf124-118">Find the custodians to add  to the case.</span></span> <span data-ttu-id="bf124-119">輸入人員名稱的第一個部分，以顯示組織之 Azure Active Directory 中的使用者。</span><span class="sxs-lookup"><span data-stu-id="bf124-119">Type the first part of a person's name to display users from your organization's Azure Active Directory.</span></span> <span data-ttu-id="bf124-120">找到正確的人員後，請按一下其名稱，將其新增至清單。</span><span class="sxs-lookup"><span data-stu-id="bf124-120">When you find the correct person, click their name to add them to the list.</span></span>

   ![識別潛在的保管人](../media/AddCustodianStep1.png)
 
4. <span data-ttu-id="bf124-122">新增所有相關保管人後，請按 **[下一步]** 以選取保管人的主要資料來源。</span><span class="sxs-lookup"><span data-stu-id="bf124-122">After added all the relevant custodians, click **Next** to select the custodians' primary data sources.</span></span>
  
## <a name="step-2-select-custodian-data-sources"></a><span data-ttu-id="bf124-123">步驟2：選取保管人資料來源</span><span class="sxs-lookup"><span data-stu-id="bf124-123">Step 2: Select custodian data sources</span></span>

<span data-ttu-id="bf124-124">在新增保管人之後，保管人工具會協助您識別每個系統管理員所擁有的主要資料來源。</span><span class="sxs-lookup"><span data-stu-id="bf124-124">After adding custodians, the custodian tool will help you identify the primary data sources owned by each custodian.</span></span> <span data-ttu-id="bf124-125">這些資料位置是管理員的 Exchange 信箱和 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="bf124-125">These data locations are the custodian's Exchange mailbox and OneDrive account.</span></span> 

<span data-ttu-id="bf124-126">若要識別保管人資料來源：</span><span class="sxs-lookup"><span data-stu-id="bf124-126">To identify custodian data sources:</span></span> 

1. <span data-ttu-id="bf124-127">若要選取所有保管人的 Exchange 信箱，請選取欄上方的 [ **exchange** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bf124-127">To select the Exchange mailbox for all custodians, select the **Exchange** check box at the top of the column.</span></span> <span data-ttu-id="bf124-128">然後，您可以清除任何特定保管人的核取方塊，以將信箱移除為 custodial 位置。</span><span class="sxs-lookup"><span data-stu-id="bf124-128">You can then clear the check box for any specific custodian to remove a mailbox as a custodial location.</span></span> <span data-ttu-id="bf124-129">或者，您可以將**Exchange**核取方塊保留未選取的欄上方，然後選取個別保管人的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bf124-129">Alternatively, you can leave the **Exchange** check box at the top of the column unselected and then select the check box for individual custodians.</span></span> 
 
   ![選取 [Custodial 資料來源]](../media/AddCustodianStep2.png)
 
2. <span data-ttu-id="bf124-131">請對保管人的 OneDrive 帳戶重複相同的工作。</span><span class="sxs-lookup"><span data-stu-id="bf124-131">Repeat the same thing for the custodians' OneDrive accounts.</span></span> 

    <span data-ttu-id="bf124-132">在您選取保管人資料來源之後，系統會自動嘗試識別及驗證這些資料來源，然後將這些資料來源當做與保管人相關聯的資料來源新增至案例。</span><span class="sxs-lookup"><span data-stu-id="bf124-132">After you select the custodian data sources, the system automatically attempts to identify and verify these data sources, and then adds them to the case as data sources associated with the custodians.</span></span>
 
4. <span data-ttu-id="bf124-133">在案例中，按 **[下一步]** 開始將其他資料來源關聯至保管人。</span><span class="sxs-lookup"><span data-stu-id="bf124-133">Click **Next** to begin associating additional data sources to the custodians in the case.</span></span>

## <a name="step-3-associate-additional-data-sources-to-a-custodian"></a><span data-ttu-id="bf124-134">步驟3：將其他資料來源與保管人建立關聯</span><span class="sxs-lookup"><span data-stu-id="bf124-134">Step 3: Associate additional data sources to a custodian</span></span>

<span data-ttu-id="bf124-135">視您正在調查的案例而定，您可能也需要搜尋（和保留內容）365，因為系統管理員目前是管理員所存取的成員，或是管理員也存取的網站。</span><span class="sxs-lookup"><span data-stu-id="bf124-135">Depending on the case you're investigating, you may also need to search (and preserve content in) mailboxes that a specific custodian may have accessed, Microsoft 365 groups that a custodian is currently a member of, or sites that a custodian has also accessed.</span></span> <span data-ttu-id="bf124-136">因此，除了您在上一個步驟中所指定的主要保管人資料來源之外，您也可以在案例中將其他 Microsoft 資料來源與系統管理員相關聯。</span><span class="sxs-lookup"><span data-stu-id="bf124-136">So in addition to the primary custodian data sources that you specified in the previous step, you can also associate additional Microsoft data sources with a custodian in the case.</span></span> 

<span data-ttu-id="bf124-137">若要將信箱、網站或小組對應至特定保管人，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bf124-137">To map mailboxes, sites, or teams to a specific custodian:</span></span>

1. <span data-ttu-id="bf124-138">在 [**選取其他資料來源**] 頁面上，針對特定保管人按一下列中的 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="bf124-138">On the **Select additional data sources** page, click **Add** in the row for the specific custodian.</span></span> 
  
   ![對應其他資料來源](../media/AddCustodianStep3.PNG)

2. <span data-ttu-id="bf124-140">在飛入頁面上，您可以指定下列任何服務的資料來源：</span><span class="sxs-lookup"><span data-stu-id="bf124-140">On the flyout page, you can specify a data source from any of the following services:</span></span>
  
   -  <span data-ttu-id="bf124-141">**Exchange 電子郵件**-按一下 **[選擇使用者、群組或小組**]，然後再按一下 **[選擇使用者、群組或小組**]。</span><span class="sxs-lookup"><span data-stu-id="bf124-141">**Exchange email** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again.</span></span> <span data-ttu-id="bf124-142">使用 [搜尋] 方塊尋找要與保管人建立關聯的信箱。</span><span class="sxs-lookup"><span data-stu-id="bf124-142">Use the search box to find mailboxes to associate with the custodian.</span></span> <span data-ttu-id="bf124-143">若要指定要指派給選取的保管人的信箱，請使用搜尋方塊來尋找使用者信箱和通訊群組。</span><span class="sxs-lookup"><span data-stu-id="bf124-143">To specify mailboxes to assign to the selected custodian, use the search box to find user mailboxes and distribution groups.</span></span> <span data-ttu-id="bf124-144">您也可以為 Microsoft 365 群組或 Microsoft 小組指派相關聯的信箱。</span><span class="sxs-lookup"><span data-stu-id="bf124-144">You can also assign the associated mailbox for a Microsoft 365 group or a Microsoft Team.</span></span> <span data-ttu-id="bf124-145">選取 [使用者、群組、小組] 核取方塊，按一下 **[選擇**]，然後按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="bf124-145">Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="bf124-146">當您按一下 [選擇使用者、群組或小組以指定信箱] 時，顯示的信箱選擇器會是空的。</span><span class="sxs-lookup"><span data-stu-id="bf124-146">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty.</span></span> <span data-ttu-id="bf124-147">這項設計的目的是提升效能。</span><span class="sxs-lookup"><span data-stu-id="bf124-147">This is by design to enhance performance.</span></span> <span data-ttu-id="bf124-148">若要將信箱新增至此清單，請在 [搜尋] 方塊中輸入名稱或別名（至少3個字元）。</span><span class="sxs-lookup"><span data-stu-id="bf124-148">To add mailbox to this list, type a name or alias (a minimum of 3 characters) in the search box.</span></span>
     
     - <span data-ttu-id="bf124-149">**SharePoint 網站**-按一下 **[選擇網站**]，然後按一下 **[選擇網站**]，以顯示組織中 SharePoint 網站的清單。</span><span class="sxs-lookup"><span data-stu-id="bf124-149">**SharePoint sites** - Click **Choose sites** and then click **Choose sites** again to display a list of SharePoint sites in your organization.</span></span> <span data-ttu-id="bf124-150">若要建立網站與保管人的關聯，您可以在清單中選取網站，也可以輸入與 Microsoft 365 群組、Microsoft Team 或 OneDrive 帳戶相關聯的其他網站 URL 或網站。</span><span class="sxs-lookup"><span data-stu-id="bf124-150">To associate a site with the custodian, you can select a site in the list or you can type the URL of a different site or a site associated with a Microsoft 365 group, Microsoft Team, or a OneDrive account.</span></span>
     
     - <span data-ttu-id="bf124-151">**小組**–按一下 **[選擇小組**]，然後按一下 **[選擇小組**]，顯示保管人目前隸屬的 Microsoft 小組清單。</span><span class="sxs-lookup"><span data-stu-id="bf124-151">**Teams** – Click **Choose teams** and then click **Choose teams** again to display a list of Microsoft Teams that the custodian is currently a member of.</span></span> <span data-ttu-id="bf124-152">選取您想要新增至您的管理員的團隊。</span><span class="sxs-lookup"><span data-stu-id="bf124-152">Select the Teams that you would like to add to your custodian.</span></span> <span data-ttu-id="bf124-153">選取之後，系統會自動識別 & 選取相關聯的 SharePoint 網站與該 Microsoft 團隊相關聯的群組信箱。</span><span class="sxs-lookup"><span data-stu-id="bf124-153">Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team.</span></span> <span data-ttu-id="bf124-154">按一下 **[選擇**]，然後按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="bf124-154">Click **Choose**, and then click **Done**.</span></span>

       ![地圖資料來源](../media/AddCustodianStep4.PNG)
        
      > [!NOTE]
      > <span data-ttu-id="bf124-156">若要將其他小組與保管人建立關聯，您必須使用**Exchange mail**和**SharePoint 網站**位置，分開新增與小組相關的信箱和網站。</span><span class="sxs-lookup"><span data-stu-id="bf124-156">To associate an additional team with a custodian, you have to separately add the mailbox and site associated with the team by using the **Exchange mail** and **SharePoint sites** locations.</span></span>

<span data-ttu-id="bf124-157">完成建立其他資料來源與保管人的關聯之後，您可以在 [**選取其他資料來源] 頁面**上，查看與每位管理員相關聯的信箱、網站和團隊總數。</span><span class="sxs-lookup"><span data-stu-id="bf124-157">After you've finished associating additional data sources with the custodians, you can view the total number of mailboxes, sites, and teams associated with each custodian on the **Select additional data sources page**.</span></span> <span data-ttu-id="bf124-158">當您完成特定保管人的相關資料來源時，在 eDiscovery 工作流程中的收集、處理及審查階段期間，將會維護和使用此關聯性。</span><span class="sxs-lookup"><span data-stu-id="bf124-158">When you've finalized the relevant data sources for a specific custodian, this association will be maintained and used during the collection, processing, and review stages in eDiscovery workflow.</span></span>

## <a name="step-4-place-custodians-on-hold"></a><span data-ttu-id="bf124-159">步驟4：將保管人保留在暫止狀態</span><span class="sxs-lookup"><span data-stu-id="bf124-159">Step 4: Place custodians on hold</span></span>

<span data-ttu-id="bf124-160">完成保管人和資料來源以新增至案例後，您可以選擇性地將部分或所有保管人置於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="bf124-160">After you've finalized the custodians and data sources to add to the case, you can optionally place some or all of the custodians on hold.</span></span> <span data-ttu-id="bf124-161">當您放置保管人時，所有與保管人相關的內容位置中的所有內容都會保留，直到您移除保留或從保留中釋放系統管理員為止。</span><span class="sxs-lookup"><span data-stu-id="bf124-161">When you place a custodian on hold, all content in all content locations that are associated with the custodian is preserved until you remove the hold or release the custodian from the hold.</span></span> <span data-ttu-id="bf124-162">在某些情況下，您可能想要將保管人新增至案例，而不是將其保留。</span><span class="sxs-lookup"><span data-stu-id="bf124-162">In some cases, you may want to add custodians to a case without placing them on hold.</span></span>

<span data-ttu-id="bf124-163">若要將保管人和資料來源保持在狀態，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="bf124-163">To place the custodians and data sources on hold:</span></span>

1. <span data-ttu-id="bf124-164">在 [已**選取的保管人**] 頁面上的 [保留] 頁面上，選取欄上方的 [**保留**] 核取方塊，以將所有保管人保留。</span><span class="sxs-lookup"><span data-stu-id="bf124-164">On the **Place a hold on the selected custodians** page, select the **Hold** check box at the top of the column to place all custodians on hold.</span></span> <span data-ttu-id="bf124-165">然後，您可以清除任何特定保管人的核取方塊，以從保留中移除。</span><span class="sxs-lookup"><span data-stu-id="bf124-165">You can then clear the check box for any specific custodian to remove from the hold.</span></span> <span data-ttu-id="bf124-166">或者，您也可以在未選取的欄上方保留 [**保留**] 核取方塊，然後選取個別保管人的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bf124-166">Alternatively, you can leave the **Hold** check box at the top of the column unselected and then select the check box for individual custodians.</span></span> 
 
   ![就地保留](../media/AddCustodianStep5.PNG)

2. <span data-ttu-id="bf124-168">確認保管人保留選項，然後按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="bf124-168">Verify the custodian hold selections and then click **Complete**.</span></span>

<span data-ttu-id="bf124-169">如果您未在保管人上進行保留，則系統會將保管人及其相關聯的資料來源新增至案例，但這些資料來源中的內容將不會處於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="bf124-169">If you don't place a hold on a custodian, the custodian and their associated data sources will be added to the case but the content in those data sources won't be placed on hold.</span></span>

<span data-ttu-id="bf124-170">在保管人保留後，會自動建立包含所有 custodial 來源的保管人保留原則。</span><span class="sxs-lookup"><span data-stu-id="bf124-170">After a custodian is placed on hold, a custodian hold policy that contains all custodial sources will be automatically created.</span></span> <span data-ttu-id="bf124-171">若要查看這個原則：</span><span class="sxs-lookup"><span data-stu-id="bf124-171">To view this policy:</span></span>

1. <span data-ttu-id="bf124-172">在案例的**首頁**上，按一下 [**保留**] 索引標籤，然後按一下 [ **CustodianHold-Guid**]，</span><span class="sxs-lookup"><span data-stu-id="bf124-172">On the **Home** page of the case, click the **Holds** tab and then click **CustodianHold-Guid**,</span></span>  

2. <span data-ttu-id="bf124-173">在飛入頁面上，按一下 [**編輯保留**]，以查看置於保留狀態的所有保管人資料來源。</span><span class="sxs-lookup"><span data-stu-id="bf124-173">On the flyout page, click **Edit hold** to view all the custodian data sources that are placed on hold.</span></span>

