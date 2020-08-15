---
title: 復原使用者信箱中刪除的郵件
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: eb15194b-63ec-41b0-8d90-1823d3f558e4
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: 本文包含的資訊可讓系統管理員在未從使用者信箱中永久移除清除的專案時，協助他們加以復原。
ms.openlocfilehash: a4755e592182d93c37a241958ba37c95d1565cdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688339"
---
# <a name="recover-deleted-items-in-a-user-mailbox"></a><span data-ttu-id="51a68-103">復原使用者信箱中刪除的郵件</span><span class="sxs-lookup"><span data-stu-id="51a68-103">Recover deleted items in a user mailbox</span></span>

<span data-ttu-id="51a68-104">**本文適用于系統管理員。您是否正嘗試在您自己的信箱中復原刪除的郵件？**</span><span class="sxs-lookup"><span data-stu-id="51a68-104">**This article is for administrators. Are you trying to recover deleted items in your own mailbox?**</span></span> <span data-ttu-id="51a68-105">請嘗試下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="51a68-105">Try one of the following:</span></span>
- [<span data-ttu-id="51a68-106">在 Windows 版 Outlook 復原已刪除的項目</span><span class="sxs-lookup"><span data-stu-id="51a68-106">Recover deleted items in Outlook for Windows</span></span>](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)
- [<span data-ttu-id="51a68-107">復原 Outlook Web App 中刪除的郵件或電子郵件</span><span class="sxs-lookup"><span data-stu-id="51a68-107">Recover deleted items or email in Outlook Web App</span></span>](https://support.office.com/article/c3d8fc15-eeef-4f1c-81df-e27964b7edd4)
- [<span data-ttu-id="51a68-108">在 Outlook 網頁版中還原已刪除的電子郵件</span><span class="sxs-lookup"><span data-stu-id="51a68-108">Restore deleted email messages in Outlook on the web</span></span>](https://support.office.com/article/a8ca78ac-4721-4066-95dd-571842e9fb11)
- [<span data-ttu-id="51a68-109">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="51a68-109">Outlook.com</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=623435)
   
<span data-ttu-id="51a68-110">使用者是否永久刪除其 Outlook 信箱中的專案？</span><span class="sxs-lookup"><span data-stu-id="51a68-110">Did a user permanently delete items from their Outlook mailbox?</span></span> <span data-ttu-id="51a68-111">使用者想要回復，但無法復原。</span><span class="sxs-lookup"><span data-stu-id="51a68-111">The user wants them back but can't recover them.</span></span> <span data-ttu-id="51a68-112">如果清除的專案並未從使用者的信箱中永久移除，您可以復原這些專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-112">You may be able recover the purged items if they haven't been permanently removed from the user's mailbox.</span></span> <span data-ttu-id="51a68-113">您可以使用 Exchange Online 中的 In-Place eDiscovery 工具，在使用者的信箱中搜尋刪除的電子郵件及其他專案（例如連絡人、行事曆約會和工作）。</span><span class="sxs-lookup"><span data-stu-id="51a68-113">You do this by using the In-Place eDiscovery tool in Exchange Online to search for deleted email and other items—and such as contacts, calendar appointments, and tasks—in a user's mailbox.</span></span> <span data-ttu-id="51a68-114">如果您發現已刪除的郵件，您可以將其匯出至 PST 檔案 (又稱為 Outlook 資料檔案) ，使用者可以使用該檔案將專案還原至其信箱。</span><span class="sxs-lookup"><span data-stu-id="51a68-114">If you find the deleted items, you can export them to a PST file (also called an Outlook Data File), which the user can then use to restore the items back to their mailbox.</span></span>
  
<span data-ttu-id="51a68-115">以下是在使用者信箱中復原已刪除郵件的步驟。</span><span class="sxs-lookup"><span data-stu-id="51a68-115">Here are the steps for recovering deleted items in a user's mailbox.</span></span> <span data-ttu-id="51a68-116">這會花費多久時間？</span><span class="sxs-lookup"><span data-stu-id="51a68-116">How long will this take?</span></span> <span data-ttu-id="51a68-117">第一次可能需要20或30分鐘才能完成所有步驟，視您嘗試復原的專案數目而定。</span><span class="sxs-lookup"><span data-stu-id="51a68-117">The first time might take 20 or 30 minutes to complete all the steps, depending on how many items you're trying to recover.</span></span>
  
> [!NOTE]
> <span data-ttu-id="51a68-118">您必須是 Microsoft 365 中的 **Exchange 系統管理員** 或 **全域系統管理員** ，或是 exchange Online 中的「組織管理」角色群組的成員，才可執行本文中的步驟。</span><span class="sxs-lookup"><span data-stu-id="51a68-118">You have to be an **Exchange administrator** or **Global administrator** in Microsoft 365 or be a member of the Organization Management role group in Exchange Online to perform the steps in this article.</span></span> <span data-ttu-id="51a68-119">如需詳細資訊，請參閱[關於 Microsoft 365 系統管理員角色](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="51a68-119">For more information, see [About Microsoft 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span> 
  
## <a name="step-1-assign-yourself-ediscovery-permissions"></a><span data-ttu-id="51a68-120">步驟1：指派您自己的 eDiscovery 許可權</span><span class="sxs-lookup"><span data-stu-id="51a68-120">Step 1: Assign yourself eDiscovery permissions</span></span>
<span data-ttu-id="51a68-121"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="51a68-121"><a name="step1"> </a></span></span>

<span data-ttu-id="51a68-122">第一步是在 Exchange Online 中指派必要的許可權，讓您可以使用 In-Place eDiscovery 工具來搜尋使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="51a68-122">The first step is to assign yourself the necessary permissions in Exchange Online so you can use the In-Place eDiscovery tool to search a user's mailbox.</span></span> <span data-ttu-id="51a68-123">此操作只需執行一次。</span><span class="sxs-lookup"><span data-stu-id="51a68-123">You only have to do this once.</span></span> <span data-ttu-id="51a68-124">如果您必須在未來搜尋另一個信箱，您可以略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="51a68-124">If you have to search another mailbox in the future, you can skip this step.</span></span>
  
1. <span data-ttu-id="51a68-125">使用您的公司或學校帳戶登[入 Microsoft 365 以取得公司的位置](https://support.microsoft.com/office/where-to-sign-into-microsoft-365-for-business-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="51a68-125">[Where to sign in to Microsoft 365 for business](https://support.microsoft.com/office/where-to-sign-into-microsoft-365-for-business-e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span> 
    
2. <span data-ttu-id="51a68-126">![在左上方的 Microsoft 365 中，選取應用程式啟動器圖示， ](../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) 然後按一下 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-126">Select the app launcher icon ![The app launcher icon in Microsoft 365](../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) in the upper-left and click **Admin**.</span></span>
    
3. <span data-ttu-id="51a68-127">在 Microsoft 365 系統管理中心的左側導覽中，展開 [系統 **管理中心**]，然後按一下 [ **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-127">In the left navigation in the Microsoft 365 admin center, expand **Admin centers**, and then click **Exchange**.</span></span>
    
    ![Admin center 清單](../media/7d308eb7-ba63-4156-a845-3770facc5de4.PNG)
  
4. <span data-ttu-id="51a68-129">在 Exchange 系統管理中心中，按一下 [ **許可權**]，然後按一下 [ **管理角色**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-129">In the Exchange admin center, click **Permissions**, and then click **Admin roles**.</span></span>
    
5. <span data-ttu-id="51a68-130">在清單視圖中，選取 [**探索管理**]，然後按一下 [**編輯** ![ 編輯圖示] ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。</span><span class="sxs-lookup"><span data-stu-id="51a68-130">In the list view, select **Discovery Management**, and then click **Edit**![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
    ![將您本人新增至 EAC 中的 [探索管理] 角色群組](../media/e5c98e93-d6a0-40c5-a143-bac956eedaa7.png)
  
6. <span data-ttu-id="51a68-132">在 [**角色群組**] 的 [**成員**] 下，按一下 [**新增**] [新增] ![ 圖示 ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) 。</span><span class="sxs-lookup"><span data-stu-id="51a68-132">In **Role Group**, under **Members**, click **Add**![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif).</span></span>
    
7. <span data-ttu-id="51a68-133">在 [ **選取成員**] 的名稱清單中，按一下 [ **新增**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="51a68-133">In **Select Members**, select yourself from the list of names, click **Add**, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="51a68-134">您也可以新增您是隸屬的群組，例如「組織管理」或 TenantAdmins。</span><span class="sxs-lookup"><span data-stu-id="51a68-134">You can also add a group that you are a member of, such as Organization Management or TenantAdmins.</span></span> <span data-ttu-id="51a68-135">如果您新增群組，則會為群組的其他成員指派執行 In-Place eDiscovery 工具所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="51a68-135">If you add a group, other members of the group will be assigned the necessary permissions to run the In-Place eDiscovery tool.</span></span> 
  
8. <span data-ttu-id="51a68-136">在 [ **角色群組**] 中，按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-136">In **Role Group**, click **Save**.</span></span>
    
9. <span data-ttu-id="51a68-137">登出 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="51a68-137">Sign out of Microsoft 365.</span></span>
    
    <span data-ttu-id="51a68-138">您必須先登出，才能開始下一個步驟，使新的許可權生效。</span><span class="sxs-lookup"><span data-stu-id="51a68-138">You have to sign out before you start the next step so the new permissions will take effect.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="51a68-139">探索管理角色群組的成員可存取機密訊息內容。</span><span class="sxs-lookup"><span data-stu-id="51a68-139">Members of the Discovery Management role group can access sensitive message content.</span></span> <span data-ttu-id="51a68-140">這包括搜尋組織中的所有信箱、預覽搜尋結果 (和其他信箱專案) 、將結果複製到探索信箱，以及將搜尋結果匯出至 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="51a68-140">This includes searching all mailboxes in your organization, previewing the search results (and other mailbox items), copying the results to a discovery mailbox, and exporting the search results to a PST file.</span></span> 
  
[<span data-ttu-id="51a68-141">回到頁首</span><span class="sxs-lookup"><span data-stu-id="51a68-141">Return to top</span></span>](recover-deleted-items-in-a-mailbox.md)
  
## <a name="step-2-search-the-users-mailbox-for-deleted-items"></a><span data-ttu-id="51a68-142">步驟2：在使用者的信箱中搜尋刪除的專案</span><span class="sxs-lookup"><span data-stu-id="51a68-142">Step 2: Search the user's mailbox for deleted items</span></span>
<span data-ttu-id="51a68-143"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="51a68-143"><a name="step2"> </a></span></span>

<span data-ttu-id="51a68-144">當您執行 In-Place eDiscovery 搜尋時，搜尋中的信箱中的 [可復原的專案] 資料夾便會自動包含在搜尋中。</span><span class="sxs-lookup"><span data-stu-id="51a68-144">When you run an In-Place eDiscovery search, the Recoverable Items folder in the mailbox that you search is automatically included in the search.</span></span> <span data-ttu-id="51a68-145">[可復原的專案] 資料夾是指永久刪除的專案儲存位置，除非將其清除 (永久移除信箱中) 為止。</span><span class="sxs-lookup"><span data-stu-id="51a68-145">The Recoverable Items folder is where permanently deleted items are stored until they're purged (permanently removed) from the mailbox.</span></span> <span data-ttu-id="51a68-146">因此，如果專案尚未清除，您應該可以使用 In-Place eDiscovery 工具來找到它。</span><span class="sxs-lookup"><span data-stu-id="51a68-146">So, if an item hasn't been purged, you should be able to find it by using the In-Place eDiscovery tool.</span></span>
  
1. <span data-ttu-id="51a68-147">使用您的公司或學校帳戶登[入 Microsoft 365 以取得公司的位置](https://support.microsoft.com/office/where-to-sign-into-microsoft-365-for-business-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="51a68-147">[Where to sign in to Microsoft 365 for business](https://support.microsoft.com/office/where-to-sign-into-microsoft-365-for-business-e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span> 
    
2. <span data-ttu-id="51a68-148">![在左上方的 Microsoft 365 中，選取應用程式啟動器圖示， ](../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) 然後按一下 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-148">Select the app launcher icon ![The app launcher icon in Microsoft 365](../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) in the upper-left and click **Admin**.</span></span>
    
3. <span data-ttu-id="51a68-149">在 Microsoft 365 系統管理中心的左側導覽中，展開 [ **管理員**]，然後按一下 [ **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-149">In the left navigation in the Microsoft 365 admin center, expand **Admin**, and then click **Exchange**.</span></span>
    
4. <span data-ttu-id="51a68-150">在 Exchange 系統管理中心中，按一下 [**規範管理**]，按一下 [ **In-Place eDiscovery &amp; 保留**]，然後按一下 [**新增**] [新增] ![ 圖示 ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) 。</span><span class="sxs-lookup"><span data-stu-id="51a68-150">In the Exchange admin center, click **Compliance management**, click **In-Place eDiscovery &amp; Hold**, and then click **New**![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif).</span></span>
    
    ![在 EAC 的 [規範管理] 頁面上，按一下 [In-Place eDiscovery 和保留]。](../media/9d9ff0f5-b9be-45b8-8b5e-6037a856b0a8.png)
  
5. <span data-ttu-id="51a68-152">在 [ **名稱與描述** ] 頁面上，輸入搜尋 (的名稱，例如您要復原) 的電子郵件的使用者名稱、選用的描述，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="51a68-152">On the **Name and description** page, type a name for the search (such as the name of the user you're recovering email for), an optional description, and then click **Next**.</span></span>
    
6. <span data-ttu-id="51a68-153">在 [**信箱**] 頁面上，按一下 [**指定要搜尋的信箱**]，然後按一下 [**新增** ![ 加入圖示] ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) 。</span><span class="sxs-lookup"><span data-stu-id="51a68-153">On the **Mailboxes** page, click **Specify mailboxes to search**, and then click **Add**![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif).</span></span>
    
    ![按一下 [指定要搜尋的信箱] 搜尋 specifc 信箱](../media/83879a40-5e5c-49a8-be3b-c0023d197588.png)
  
7. <span data-ttu-id="51a68-155">尋找並選取您要復原已刪除之電子郵件的使用者名稱，按一下 [ **新增**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="51a68-155">Find and select the name of the user that you're recovering the deleted email for, click **Add**, and then click **OK**.</span></span>
    
8. <span data-ttu-id="51a68-156">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="51a68-156">Click **Next**.</span></span>
    
    <span data-ttu-id="51a68-157">隨即會顯示 [ **搜尋查詢** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="51a68-157">The **Search query** page is displayed.</span></span> <span data-ttu-id="51a68-158">您可以在此定義搜尋準則，以協助您找出使用者信箱中遺失的專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-158">This is where you define the search criteria that will help you find the missing items in user's mailbox.</span></span> 
    
9. <span data-ttu-id="51a68-159">在 [ **搜尋查詢** ] 頁面上，完成下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="51a68-159">On the **Search query** page, complete the following fields:</span></span> 
    
  - <span data-ttu-id="51a68-160">**包含所有內容** 選取此選項，可將使用者信箱中的所有內容包含在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="51a68-160">**Include all content** Select this option to include all content in the user's mailbox in the search results.</span></span> <span data-ttu-id="51a68-161">如果選取這個選項，便無法指定其他搜尋準則。</span><span class="sxs-lookup"><span data-stu-id="51a68-161">If you select this option, you can't specify additional search criteria.</span></span> 
    
  - <span data-ttu-id="51a68-162">**根據準則篩選** 選取此選項以指定搜尋準則，包含關鍵字、開始和結束日期、寄件者和收件者位址，以及郵件類型。</span><span class="sxs-lookup"><span data-stu-id="51a68-162">**Filter based on criteria** Select this option to specify the search criteria, including keywords, start and end dates, sender and recipient addresses, and message types.</span></span> 
    
    ![根據關鍵字、日期範圍、收件者和郵件類型等準則建立搜索](../media/ee47b833-9122-46a0-85e6-fcbe25be0dd5.png)
  
|<span data-ttu-id="51a68-164">**Field**</span><span class="sxs-lookup"><span data-stu-id="51a68-164">**Field**</span></span>|<span data-ttu-id="51a68-165">**使用此 .。。**</span><span class="sxs-lookup"><span data-stu-id="51a68-165">**Use this to...**</span></span>|
|:-----|:-----|
|![粉紅色圓圈中的數字 1](../media/a4da261d-2516-48c5-b58a-9c452b9086b8.png)           <br/> |<span data-ttu-id="51a68-167">指定關鍵字、日期範圍、收件者和郵件類型。</span><span class="sxs-lookup"><span data-stu-id="51a68-167">Specify keywords, date range, recipients, and message types.</span></span>  <br/> |
|![粉紅色圓圈中的數字 2。](../media/de3c1ab4-4f01-4026-b1ba-3265bdb32a89.png)           <br/> |<span data-ttu-id="51a68-169">搜尋包含關鍵字或片語的郵件，並使用邏輯運算子（例如 **and** 或 **or**）。</span><span class="sxs-lookup"><span data-stu-id="51a68-169">Search for messages with keywords or phrases, and use logical operators such as **AND** or **OR**.</span></span>  <br/> |
|![粉紅色圓圈中的數字 3。](../media/60fa378c-6ac1-4cbd-a782-2fa7ca619dc6.png)           <br/> |<span data-ttu-id="51a68-171">搜尋在日期範圍內傳送或接收的郵件。</span><span class="sxs-lookup"><span data-stu-id="51a68-171">Search for messages sent or received within a date range.</span></span>  <br/> |
|![粉紅色圓圈中的數字 4。](../media/1a0ff2ce-0942-405a-94e3-9bfeb1e5059e.png)           <br/> |<span data-ttu-id="51a68-173">搜尋接收或傳送給特定人員的郵件。</span><span class="sxs-lookup"><span data-stu-id="51a68-173">Search for messages received from or sent to specific people.</span></span>  <br/> |
|![粉紅色圓圈中的數位5。](../media/878cc815-0165-49ba-a1ee-9236e5980403.png)           <br/> |<span data-ttu-id="51a68-175">搜尋所有郵件類型或選取特定郵件類型。</span><span class="sxs-lookup"><span data-stu-id="51a68-175">Search for all message types or select specific ones.</span></span>  <br/> |
   
   > [!TIP]
   >  <span data-ttu-id="51a68-176">以下是一些有關如何建立搜尋查詢以尋找遺失的專案的秘訣。</span><span class="sxs-lookup"><span data-stu-id="51a68-176">Here are a few tips about how to build a search query to find missing items.</span></span> <span data-ttu-id="51a68-177">嘗試從使用者取得盡可能多的資訊，協助您建立搜尋查詢，以便您尋找您要尋找的專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-177">Try to get as much information from the user to help you create a search query so you can find what you're looking for.</span></span> <span data-ttu-id="51a68-178">如果您不確定如何找到遺失的郵件，請考慮使用 [ **包含所有內容** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="51a68-178">If you are not sure how to find a missing message, consider using the **Include all content** option.</span></span> <span data-ttu-id="51a68-179">搜尋結果會包含使用者的 [可復原的專案] 資料夾中的所有專案，包含使用者已清除之專案的隱藏資料夾 (稱為 [清除] 資料夾) 。</span><span class="sxs-lookup"><span data-stu-id="51a68-179">The search results will include all items in the user's Recoverable Items folder, including the hidden folder (called the Purges folder) that contain items that have been purged by the user.</span></span> <span data-ttu-id="51a68-180">然後，您可以移至步驟3，將結果複製到探索信箱，並查看隱藏資料夾中的郵件。</span><span class="sxs-lookup"><span data-stu-id="51a68-180">Then you can go to Step 3, copy the results to a discovery mailbox, and look at the message in the hidden folder.</span></span> <span data-ttu-id="51a68-181">如果您知道使用者最初是何時傳送或接收遺失的郵件，請使用 [ **指定開始日期** ] 和 [ **指定結束日期** ] 選項，以提供日期範圍。</span><span class="sxs-lookup"><span data-stu-id="51a68-181">If you know approximately when the missing message was originally sent or received by the user, use the **Specify start date** and **Specify end date** options to provide a date range.</span></span> <span data-ttu-id="51a68-182">這會傳回使用者在該日期範圍內傳送或接收的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="51a68-182">This will return all messages sent or received by the user within that date range.</span></span> <span data-ttu-id="51a68-183">指定日期範圍是縮小搜尋結果的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="51a68-183">Specifying a date range is a really good way to narrow the search results.</span></span> <span data-ttu-id="51a68-184">如果您知道誰送出了遺失的電子郵件，請使用 [ **發** 件人] 方塊來指定此寄件者。</span><span class="sxs-lookup"><span data-stu-id="51a68-184">If you know who sent the missing email, use the **From** box to specify this sender.</span></span> <span data-ttu-id="51a68-185">如果您想將搜尋結果縮小為不同類型的信箱專案，請按一下 [ **選取郵件類型**]，按一下 **[選取要搜尋的郵件類型**]，然後選擇要搜尋的特定郵件類型。</span><span class="sxs-lookup"><span data-stu-id="51a68-185">If you want to narrow the search results to different types of mailbox items, click **Select message types**, click **Select the message types to search**, and then choose a specific message type to search for.</span></span> <span data-ttu-id="51a68-186">例如，您只能搜尋行事曆專案或連絡人。</span><span class="sxs-lookup"><span data-stu-id="51a68-186">For example, you can search only for calendar items or contacts.</span></span> <span data-ttu-id="51a68-187">以下是您可以搜尋之不同郵件類型的螢幕擷取畫面。預設值為搜尋所有郵件類型。</span><span class="sxs-lookup"><span data-stu-id="51a68-187">Here's a screenshot of the different message types you can search for; the default is to search for all message types.</span></span> 
  
   <span data-ttu-id="51a68-188">當您完成**搜尋查詢**頁面時，按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="51a68-188">Click **Next** when you've completed the **Search query** page.</span></span> 
    
10. <span data-ttu-id="51a68-189">在 [ **In-Place 保留設定** ] 頁面上，按一下 **[完成]** 以開始搜尋。</span><span class="sxs-lookup"><span data-stu-id="51a68-189">On the **In-Place Hold settings** page, click **Finish** to start the search.</span></span> <span data-ttu-id="51a68-190">若要復原已刪除的電子郵件，則不需要將使用者的信箱保留在暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="51a68-190">To recover deleted email, there's no reason to place the user's mailbox on hold.</span></span> 
    
    <span data-ttu-id="51a68-191">開始搜尋之後，Exchange 會根據您指定的準則，顯示搜尋會傳回之總大小和專案數的預估。</span><span class="sxs-lookup"><span data-stu-id="51a68-191">After you start the search, Exchange will display an estimate of the total size and number of items that will be returned by the search based on the criteria you specified.</span></span>
    
11. <span data-ttu-id="51a68-192">選取您剛建立的搜尋，然後**按一下 [** 重新整理] ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) 以更新詳細資料窗格中顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="51a68-192">Select the search you just created and click **Refresh**![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the information displayed in the details pane.</span></span> <span data-ttu-id="51a68-193">[ **評估成功** ] 的狀態表示搜尋已經完成。</span><span class="sxs-lookup"><span data-stu-id="51a68-193">The status of **Estimate Succeeded** indicates that the search has finished.</span></span> <span data-ttu-id="51a68-194">Exchange 也會根據您在步驟9中指定的搜尋準則，顯示搜尋 (所找到的專案總數) 及其大小的預估。</span><span class="sxs-lookup"><span data-stu-id="51a68-194">Exchange also displays an estimate of the total number of items (and their size) found by the search based on the search criteria you specified in step 9.</span></span> 
    
12. <span data-ttu-id="51a68-195">在詳細資料窗格中，按一下 [ **預覽搜尋結果** ] 以查看找到的專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-195">In the details pane, click **Preview search results** to view the items that were found.</span></span> <span data-ttu-id="51a68-196">這可能會協助您識別所要尋找的專案 (s) 。</span><span class="sxs-lookup"><span data-stu-id="51a68-196">This might help you identify the item(s) that you're looking for.</span></span> <span data-ttu-id="51a68-197">如果您在嘗試復原時 (s) 專案，請移至步驟4，將搜尋結果匯出至 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="51a68-197">If you find the item(s) you're trying to recover, go to step 4 to export the search results to a PST file.</span></span> 
    
    ![按一下 [預覽搜尋結果] 以查看您要嘗試復原的專案](../media/a2cea921-dafa-45d6-97d4-ae45a226b8d3.png)
  
13. <span data-ttu-id="51a68-199">如果您找不到所要的專案，您可以選取搜尋，然後按一下 [**編輯** ![ 編輯圖示] ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ，再按一下 [**搜尋查詢**] 以修正您的搜尋準則。</span><span class="sxs-lookup"><span data-stu-id="51a68-199">If you don't find what you're looking for, you can revise your search criteria by selecting the search, clicking **Edit**![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif), and then clicking **Search query**.</span></span> <span data-ttu-id="51a68-200">變更搜尋準則，然後重新執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="51a68-200">Change the search criteria and then rerun the search.</span></span>
    
[<span data-ttu-id="51a68-201">回到頁首</span><span class="sxs-lookup"><span data-stu-id="51a68-201">Return to top</span></span>](recover-deleted-items-in-a-mailbox.md)
  
## <a name="optional-step-3-copy-the-search-results-to-a-discovery-mailbox"></a><span data-ttu-id="51a68-202"> (選用) 步驟3：將搜尋結果複製到探索信箱</span><span class="sxs-lookup"><span data-stu-id="51a68-202">(Optional) Step 3: Copy the search results to a discovery mailbox</span></span>
<span data-ttu-id="51a68-203"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="51a68-203"><a name="step3"> </a></span></span>

<span data-ttu-id="51a68-204">如果您無法透過預覽搜尋結果來找到專案，或若要查看使用者的 [可復原的專案] 資料夾中的專案，您可以將搜尋結果複製到稱為「探索信箱」的特殊信箱 () 然後在網頁的 Outlook 中開啟該信箱，以查看實際的專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-204">If you can't find an items by previewing the search results or if you want to see which items are in the user's Recoverable Items folder, then you can copy the search results to a special mailbox (called a discovery mailbox) and then open that mailbox in Outlook on the web to view the actual items.</span></span> <span data-ttu-id="51a68-205">複製搜尋結果的最佳原因是，您可以在使用者的 [可復原的專案] 資料夾中查看專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-205">The best reason to copy the search results is so you can view the items in the user's Recoverable Items folder.</span></span> <span data-ttu-id="51a68-206">您嘗試復原的專案可能會位於 [清除] 子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="51a68-206">More than likely, the item you're trying to recover is located in the Purges subfolder.</span></span> 
  
1. <span data-ttu-id="51a68-207">在 Exchange 系統管理中心中，移至 [ **規範管理**] \> **In-Place eDiscovery &amp; 保留**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-207">In the Exchange admin center, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="51a68-208">在搜尋清單中，選取您在步驟2中建立的搜尋。</span><span class="sxs-lookup"><span data-stu-id="51a68-208">In the list of searches, select the search that you created in Step 2.</span></span>
    
3. <span data-ttu-id="51a68-209">按一下 [**搜尋** ![ 搜尋] ](../media/c94e8591-7044-4650-a0d1-c57c0633ab4f.png) ，然後按一下下拉式清單中的 [**複製搜尋結果**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-209">Click **Search**![search](../media/c94e8591-7044-4650-a0d1-c57c0633ab4f.png), and then click **Copy search results** from the drop-down list.</span></span> 
    
    ![按一下 [搜尋]，然後按一下 [複製搜尋結果]。](../media/7888df82-94b4-4e44-8a53-f66854dc7c86.png)
  
4. <span data-ttu-id="51a68-211">在 [ **複製搜尋結果** ] 頁面上，按一下 **[流覽]**。</span><span class="sxs-lookup"><span data-stu-id="51a68-211">On the **Copy Search Results** page, click **Browse**.</span></span>
    
    ![復原已刪除的專案時，保留核取方塊未選取](../media/37f27999-a5b2-4fed-87e2-bad6dc23cdae.png)
  
5. <span data-ttu-id="51a68-213">在 [ **顯示名稱**] 下，按一下 [ **探索搜尋信箱**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="51a68-213">Under **Display Name**, click **Discovery Search Mailbox**, and then click **OK**.</span></span>
    
    ![將搜尋結果複製到預設探索搜尋信箱](../media/36e8ef47-0035-4982-9ed6-426719c5f9ec.png)
  
    > [!NOTE]
    > <span data-ttu-id="51a68-215">探索搜尋信箱是在您的 Microsoft 365 組織中自動建立的預設探索信箱。</span><span class="sxs-lookup"><span data-stu-id="51a68-215">The Discovery Search Mailbox is a default discovery mailbox that is automatically created in your Microsoft 365 organization.</span></span> 
  
6. <span data-ttu-id="51a68-216">回到 [ **複製搜尋結果** ] 頁面上，按一下 [ **複製** ] 以啟動處理常式，以將搜尋結果複製到探索搜尋信箱。</span><span class="sxs-lookup"><span data-stu-id="51a68-216">Back on the **Copy Search Results** page, click **Copy** to start the process to copy the search results to the Discovery Search Mailbox.</span></span> 
    
    ![按一下 [複製]，將搜尋結果複製到探索搜尋信箱](../media/71307a9d-f7a1-4e01-ae37-1d49040cc3fd.png)
  
7. <span data-ttu-id="51a68-218">按一下**Refresh**[重新整理] [重新整理] ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) 以更新詳細資料窗格中顯示的複製狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="51a68-218">Click **Refresh**![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the information about the copying status that is displayed in the details pane.</span></span> 
    
8. <span data-ttu-id="51a68-219">當複製完成時，按一下 [ **開啟** ] 以開啟 [探索搜尋] 信箱，以查看搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="51a68-219">When the copying is complete, click **Open** to open the Discovery Search Mailbox to view the search results.</span></span> 
    
    ![按一下 [開啟] 移至探索搜尋信箱以查看搜尋結果](../media/6cc81e0f-ceed-4464-9040-79b6f920de35.png)
  
    <span data-ttu-id="51a68-221">複製到探索搜尋信箱的搜尋結果，會放在與 In-Place eDiscovery 搜尋同名的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="51a68-221">The search results copied to the Discovery Search Mailbox are placed in a folder that has the same name as the In-Place eDiscovery search.</span></span> <span data-ttu-id="51a68-222">您可以按一下資料夾來顯示該資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-222">You can click a folder to display the items in that folder.</span></span>
    
    ![探索搜尋信箱中的搜尋結果;[清除] 資料夾中的專案只有系統管理員才能復原](../media/2ef8e5fb-3e63-4f62-938e-307efe9f6998.gif)
  
    <span data-ttu-id="51a68-224">當您執行搜尋時，也會搜尋使用者的 [可復原的專案] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="51a68-224">When you run a search, the user's Recoverable Items folder is also searched.</span></span> <span data-ttu-id="51a68-225">這表示如果 [可復原的專案] 資料夾中的專案符合搜尋準則，這些專案就會包含在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="51a68-225">That means if items in the Recoverable Items folder meet the search criteria, they are included in the search results.</span></span> <span data-ttu-id="51a68-226">「刪除專案」資料夾中的專案是指使用者從 [刪除的郵件] 資料夾中刪除專案，或選取並按下 **Shift+Delete**，永久刪除 (的專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-226">Items in the Deletions folder are items that the user permanently deleted (by deleting an item from the Deleted Items folder or by selecting it and pressing **Shift+Delete**.</span></span> <span data-ttu-id="51a68-227">使用者可以使用 Outlook 或 web 上 Outlook 中的 [復原刪除的郵件] 工具，復原 [刪除] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-227">A user can use the Recover Deleted Items tool in Outlook or Outlook on the web to recover items in the Deletions folder.</span></span> <span data-ttu-id="51a68-228">[清除] 資料夾中的專案是使用者使用「復原刪除的專案」工具清除的專案，或已套用至信箱的原則自動清除的專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-228">Items in the Purges folder are items that the user purged by using the Recover Deleted Items tool or items they were automatically purged by a policy applied to the mailbox.</span></span> <span data-ttu-id="51a68-229">在這兩種情況下，只有系統管理員可以復原 [清除] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-229">In either case, only an admin can recover items in the Purges folder.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="51a68-230">如果使用者無法使用 [可復原的專案] 工具找到刪除的專案，但是該專案仍可復原 (表示該專案並未從信箱) 中永久移除，則該專案很可能位於 [清除] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="51a68-230">If a user can't find a deleted item using the Recoverable Items tool, but that item is still recoverable (meaning that it hasn't been permanently removed from the mailbox), it's more than likely located in the Purges folder.</span></span> <span data-ttu-id="51a68-231">因此，請務必查看您要嘗試為使用者復原之已刪除專案的 [清除] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="51a68-231">So, be sure to look in the Purges folder for the deleted item you're trying to recover for a user.</span></span> 
  
[<span data-ttu-id="51a68-232">回到頁首</span><span class="sxs-lookup"><span data-stu-id="51a68-232">Return to top</span></span>](recover-deleted-items-in-a-mailbox.md)
  
## <a name="step-4-export-the-search-results-to-a-pst-file"></a><span data-ttu-id="51a68-233">步驟4：將搜尋結果匯出至 PST 檔案</span><span class="sxs-lookup"><span data-stu-id="51a68-233">Step 4: Export the search results to a PST file</span></span>
<span data-ttu-id="51a68-234"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="51a68-234"><a name="step4"> </a></span></span>

<span data-ttu-id="51a68-235">在您找到要為使用者復原的專案之後，下一步是將您在步驟2中所執行之搜尋的結果匯出至 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="51a68-235">After you find the item you're trying to recover for a user, the next step is to export the results from the search you ran in Step 2 to a PST file.</span></span> <span data-ttu-id="51a68-236">使用者將會在下一個步驟中使用此 PST 檔案，將刪除的專案還原到其信箱。</span><span class="sxs-lookup"><span data-stu-id="51a68-236">The user will use this PST file in the next step to restore the deleted item to their mailbox.</span></span>
  
1. <span data-ttu-id="51a68-237">在 Exchange 系統管理中心中，移至 [ **規範管理**] \> **In-Place eDiscovery &amp; 保留**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-237">In the Exchange admin center, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="51a68-238">在搜尋清單中，選取您在步驟2中建立的搜尋。</span><span class="sxs-lookup"><span data-stu-id="51a68-238">In the list of searches, select the search that you created in Step 2.</span></span>
    
3. <span data-ttu-id="51a68-239">按一下 [ **匯出成 PST**檔案]。</span><span class="sxs-lookup"><span data-stu-id="51a68-239">Click **Export to a PST file**.</span></span>
    
    ![按一下 [匯出成 PST 檔案]](../media/4e59ae17-4541-43f4-a6d1-1f8b9ba9404b.png)
  
4. <span data-ttu-id="51a68-241">如果系統提示您安裝 eDiscovery 匯出工具，請按一下 [ **執行**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-241">If you're prompted to install the eDiscovery Export Tool, click **Run**.</span></span>
    
5. <span data-ttu-id="51a68-242">在 [eDiscovery PST 匯出工具] 中，按一下 **[流覽]** 以指定您要下載 PST 檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="51a68-242">In the eDiscovery PST Export Tool, click **Browse** to specify the location where you want to download the PST file.</span></span> 
    
    ![EDiscovery PST 匯出工具](../media/17274d27-992e-4034-8133-8f793f554e6c.png)
  
    <span data-ttu-id="51a68-244">您可以忽略選項啟用重復資料刪除功能並包含無法搜尋的專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-244">You can ignore the options to enable deduplication and include unsearchable items.</span></span>
    
6. <span data-ttu-id="51a68-245">按一下 [ **開始** ]，將 PST 檔案下載到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="51a68-245">Click **Start** to download the PST file to your computer.</span></span> 
    
    <span data-ttu-id="51a68-246">**EDISCOVERY PST 匯出工具**會顯示匯出程式的狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="51a68-246">The **eDiscovery PST Export Tool** displays status information about the export process.</span></span> <span data-ttu-id="51a68-247">匯出完成時，您可以存取檔案的下載位置。</span><span class="sxs-lookup"><span data-stu-id="51a68-247">When the export is complete, you can access the file in the location where it was downloaded.</span></span> 
    
[<span data-ttu-id="51a68-248">回到頁首</span><span class="sxs-lookup"><span data-stu-id="51a68-248">Return to top</span></span>](recover-deleted-items-in-a-mailbox.md)
  
## <a name="step-5-restore-the-recovered-items-to-the-users-mailbox"></a><span data-ttu-id="51a68-249">步驟5：將復原的專案還原至使用者的信箱</span><span class="sxs-lookup"><span data-stu-id="51a68-249">Step 5: Restore the recovered items to the user's mailbox</span></span>
<span data-ttu-id="51a68-250"><a name="step5"> </a></span><span class="sxs-lookup"><span data-stu-id="51a68-250"><a name="step5"> </a></span></span>

<span data-ttu-id="51a68-251">最後一個步驟是使用在步驟4中匯出的 PST 檔案，將復原的專案還原至使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="51a68-251">The final step is to use the PST file that was exported in step 4 to restore the recovered items to the user's mailbox.</span></span> <span data-ttu-id="51a68-252">將 PST 檔案傳送給使用者之後，使用者會執行此步驟的其餘部分，以開啟 PST 檔案，然後將復原的專案移至其信箱中的另一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="51a68-252">After you send the PST file to the user, the remainder of this step is performed by the user to open the PST file and then move the recovered items to another folder in their mailbox.</span></span> <span data-ttu-id="51a68-253">如需逐步指示，您也可以將本主題的連結傳送給使用者： [開啟和關閉 Outlook 資料檔案 ( .pst) ](https://support.office.com/article/381b776d-7511-45a0-953a-0935c79d24f2)。</span><span class="sxs-lookup"><span data-stu-id="51a68-253">For step-by-step instructions, you can also send the user a link to this topic: [Open and close Outlook Data Files (.pst)](https://support.office.com/article/381b776d-7511-45a0-953a-0935c79d24f2).</span></span> <span data-ttu-id="51a68-254">或者，您可以使用下列的 PST 檔案區段，將 [ [還原已刪除的郵件](recover-deleted-items-in-a-mailbox.md#restoredeleteditems) ] 的連結傳送至信箱，並要求使用者執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="51a68-254">Or you can send the user a link to the [Restore deleted items to a mailbox using a PST file](recover-deleted-items-in-a-mailbox.md#restoredeleteditems) section below and ask them to perform these steps.</span></span> 
  
 <span data-ttu-id="51a68-255">**將 PST 檔案傳送給使用者**</span><span class="sxs-lookup"><span data-stu-id="51a68-255">**Send the PST file to the user**</span></span>
  
<span data-ttu-id="51a68-256">您需要執行的最後一個步驟是將在步驟4中匯出的 PST 檔案傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="51a68-256">The final step that you need to perform is sending the PST file that was exported in step 4 to the user.</span></span> <span data-ttu-id="51a68-257">有幾種方式可以執行此作業：</span><span class="sxs-lookup"><span data-stu-id="51a68-257">There are a few ways to do this:</span></span>
  
- <span data-ttu-id="51a68-258">將 PST 檔案附加到電子郵件。</span><span class="sxs-lookup"><span data-stu-id="51a68-258">Attach the PST file to an email message.</span></span> <span data-ttu-id="51a68-259">若將 Outlook 設定為封鎖 PST 檔案，則必須 ZIP 檔案，然後附加到郵件。</span><span class="sxs-lookup"><span data-stu-id="51a68-259">If Outlook is configured to block PST files, then you will have to zip the file and then attach it to the message.</span></span> <span data-ttu-id="51a68-260">方法如下：</span><span class="sxs-lookup"><span data-stu-id="51a68-260">Here's how:</span></span>
    
1. <span data-ttu-id="51a68-261">在 Windows Explorer 或檔案瀏覽器中，流覽至 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="51a68-261">In Windows Explorer or File Explorer, browse to the PST file.</span></span>
    
2. <span data-ttu-id="51a68-262">以滑鼠右鍵按一下檔案，然後選取 [ **傳送至** \> **壓縮 (zipped) 資料夾**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-262">Right-click the file, and then select **Send to** \> **Compressed (zipped) folder**.</span></span> <span data-ttu-id="51a68-263">Windows 會建立新的 zip 檔案，並將其名稱視為 PST 檔案相同。</span><span class="sxs-lookup"><span data-stu-id="51a68-263">Windows creates a new zip file and gives it an identical name as the PST file.</span></span>
    
3. <span data-ttu-id="51a68-264">將壓縮 PST 檔案附加到電子郵件，並將其傳送給使用者，然後使用者就可以按一下該檔案來解壓縮該檔案。</span><span class="sxs-lookup"><span data-stu-id="51a68-264">Attach the compressed PST file to an email message and send it to the user, who can then decompress the file just by clicking it.</span></span>
    
- <span data-ttu-id="51a68-265">將 PST 檔案複製到使用者可存取及取回的共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="51a68-265">Copy the PST file to a shared folder that the user can access and retrieve it.</span></span>
    
<span data-ttu-id="51a68-266">下一節中的步驟是由使用者執行，以將刪除的專案還原到其信箱。</span><span class="sxs-lookup"><span data-stu-id="51a68-266">The steps in the next section are performed by the user to restore the deleted items to their mailbox.</span></span>
  
 <a name="restoredeleteditems"></a>
<span data-ttu-id="51a68-267">**使用 PST 檔將刪除的郵件還原至信箱**</span><span class="sxs-lookup"><span data-stu-id="51a68-267">**Restore deleted items to a mailbox using a PST file**</span></span>
  
<span data-ttu-id="51a68-268">您必須使用 Outlook 桌面應用程式，以使用 PST 檔還原已刪除的專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-268">You have to use the Outlook desktop app to restore a deleted item by using a PST file.</span></span> <span data-ttu-id="51a68-269">您無法使用 Outlook Web App 或 Web 上的 Outlook 來開啟 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="51a68-269">You can't use Outlook Web App or Outlook on the web to open a PST file.</span></span>
  
1. <span data-ttu-id="51a68-270">在 Outlook 2013 或 Outlook 2016 **中，按一下 [檔案** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="51a68-270">In Outlook 2013 or Outlook 2016, click the **File** tab.</span></span> 
    
2. <span data-ttu-id="51a68-271">按一下 [ **開啟 &amp; 匯出**]，然後按一下 [ **開啟 Outlook 資料檔案**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-271">Click **Open &amp; Export**, and then click **Open Outlook Data File**.</span></span>
    
3. <span data-ttu-id="51a68-272">流覽至您儲存系統管理員所傳送之 PST 檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="51a68-272">Browse to the location where you saved the PST file that your administrator sent.</span></span>
    
4. <span data-ttu-id="51a68-273">選取 PST，然後按一下 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-273">Select the PST and then click **Open**.</span></span>
    
    <span data-ttu-id="51a68-274">PST 檔案會出現在 Outlook 的左導覽列中。</span><span class="sxs-lookup"><span data-stu-id="51a68-274">The PST file appears in the left-nav bar in Outlook.</span></span>
    
    ![PST 檔案會出現在 Outlook 的左導覽列中](../media/c9389392-d08a-4aa7-848c-4986d448b0f2.png)
  
5. <span data-ttu-id="51a68-276">按一下箭號以展開 PST 檔案及其底下的資料夾，以找出您想要復原的專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-276">Click the arrows to expand the PST file and the folders under it to locate the item you want to recover.</span></span>
    
    ![在 [清除] 資料夾中，尋找您想要復原的專案](../media/d4e372d9-ac23-4e95-8639-d8da690fefa7.png)
  
    > [!TIP]
    > <span data-ttu-id="51a68-278">查看您要復原之專案的 [清除] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="51a68-278">Look in the Purges folder for the item you want to recover.</span></span> <span data-ttu-id="51a68-279">這是已清除專案移至的隱藏資料夾。</span><span class="sxs-lookup"><span data-stu-id="51a68-279">This is a hidden folder that purged items are moved to.</span></span> <span data-ttu-id="51a68-280">您的系統管理員可能會在此資料夾中復原此專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-280">It's likely the item that your administrator recovered is in this folder.</span></span> 
  
6. <span data-ttu-id="51a68-281">以滑鼠右鍵按一下您要復原的專案，然後按一下 [ **移動** \> **其他資料夾**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-281">Right-click the item you want to recover and then click **Move** \> **Other Folder**.</span></span>
    
    ![按一下 [移動]，然後選取 [其他資料夾]](../media/090063df-2aa0-444a-8e47-abd6fe6cf7a8.png)
  
7. <span data-ttu-id="51a68-283">若要將專案移至收件匣，請按一下 [ **收件**匣]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="51a68-283">To move the item to your inbox, click **Inbox**, and then click **OK**.</span></span>
    
    <span data-ttu-id="51a68-284">**秘訣：** 若要復原其他類型的專案，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="51a68-284">**Tip:** To recover other types of items, do one of the following:</span></span> 
    
  - <span data-ttu-id="51a68-285">若要復原行事曆專案，請以滑鼠右鍵按一下它，然後按一下 [ **移動** \> **其他資料夾**行事 \> **曆**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-285">To recover a calendar item, right-click it, and then click **Move** \> **Other Folder** \> **Calendar**.</span></span>
    
  - <span data-ttu-id="51a68-286">若要復原連絡人，請在其上按一下滑鼠右鍵，然後按一下 [ **移動** \> **其他資料夾** \> **連絡人**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-286">To recover a contact, right-click it, and then click **Move** \> **Other Folder** \> **Contacts**.</span></span>
    
  - <span data-ttu-id="51a68-287">若要復原任務，請以滑鼠右鍵按一下它，然後按一下 [ **移動** \> **其他資料夾** \> **任務**]。</span><span class="sxs-lookup"><span data-stu-id="51a68-287">To recover a task, right-click it, and then click **Move** \> **Other Folder** \> **Tasks**.</span></span>
    
![選取資料夾以移動其他類型的專案](../media/f8290131-43f2-46f1-bc07-228c2d83b96c.png)
  
   > [!NOTE]
   > <span data-ttu-id="51a68-289">[行事曆專案]、[連絡人] 和 [工作] 直接位於 [清除] 資料夾中，而不是在 [行事曆]、[連絡人] 或 [任務] 子</span><span class="sxs-lookup"><span data-stu-id="51a68-289">Calendar items, contacts, and tasks are located directly in the Purges folder, and not in a Calendar, Contacts, or Tasks subfolder.</span></span> <span data-ttu-id="51a68-290">不過，您可以依 **類型** 排序，以分組類似的專案類型。</span><span class="sxs-lookup"><span data-stu-id="51a68-290">However, you can sort by **Type** to group similar types of items.</span></span> 
    
8. <span data-ttu-id="51a68-291">當您完成復原已刪除的專案時，請以滑鼠右鍵按一下左導覽列中的 PST 檔案，然後選取 **[關閉「pst 檔案的名稱**」。</span><span class="sxs-lookup"><span data-stu-id="51a68-291">When you're finished recovering deleted items, right-click the PST file in the left-nav bar and select **Close "name of PST file"**.</span></span>
    
[<span data-ttu-id="51a68-292">回到頁首</span><span class="sxs-lookup"><span data-stu-id="51a68-292">Return to top</span></span>](recover-deleted-items-in-a-mailbox.md)
  
## <a name="more-information"></a><span data-ttu-id="51a68-293">其他資訊</span><span class="sxs-lookup"><span data-stu-id="51a68-293">More information</span></span>
<span data-ttu-id="51a68-294"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="51a68-294"><a name="moreinfo"> </a></span></span>

- <span data-ttu-id="51a68-295">如果專案的已刪除專案保留期間尚未過期，則使用者可能會復原永久刪除的專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-295">It might be possible for a user to recover a permanently deleted item if the deleted item retention period for the item hasn't expired.</span></span> <span data-ttu-id="51a68-296">以系統管理員的身分，您可以指定 [可復原的專案] 資料夾中的專案可用於復原的時間。</span><span class="sxs-lookup"><span data-stu-id="51a68-296">As an admin you may have specified how long items in the Recoverable Items folder are available for recovery.</span></span> <span data-ttu-id="51a68-297">例如，可能有一個原則可刪除使用者的 [刪除的郵件] 資料夾中有30天的任何專案，還有另一個原則可讓使用者將 [可復原的專案] 資料夾中的專案復原到另一個14天。</span><span class="sxs-lookup"><span data-stu-id="51a68-297">For example, there might be a policy that deletes anything that's been in a user's Deleted Items folder for 30 days, and another policy that lets users recover items in the Recoverable Items folder for up to another 14 days.</span></span> <span data-ttu-id="51a68-298">不過，在這14天之後，您仍然可以使用本主題中的程式來復原使用者信箱中的專案。</span><span class="sxs-lookup"><span data-stu-id="51a68-298">However, after this 14 days, you may still be able to recover an item in a user's mailbox by using the procedures in this topic.</span></span>
    
- <span data-ttu-id="51a68-299">使用者可以復原已刪除的專案（如果未清除的話），以及該專案的刪除專案保留期間尚未過期。</span><span class="sxs-lookup"><span data-stu-id="51a68-299">Users can recover a deleted item if it hasn't been purged and if the deleted item retention period for that item hasn't expired.</span></span> <span data-ttu-id="51a68-300">若要協助使用者在其信箱中復原刪除的專案，請將其指向下列其中一個主題：</span><span class="sxs-lookup"><span data-stu-id="51a68-300">To help users recover deleted items in their mailbox, point them to one of the following topics:</span></span>
    
  - [<span data-ttu-id="51a68-301">在 Windows 版 Outlook 復原已刪除的項目</span><span class="sxs-lookup"><span data-stu-id="51a68-301">Recover deleted items in Outlook for Windows</span></span>](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)
    
  - [<span data-ttu-id="51a68-302">在 Outlook 2010 中復原已刪除的專案</span><span class="sxs-lookup"><span data-stu-id="51a68-302">Recover deleted items in Outlook 2010</span></span>](https://support.office.com/article/cd9dfe12-8e8c-4a21-bbbf-4bd103a3f1fe)
    
  - [<span data-ttu-id="51a68-303">復原 Outlook Web App 中刪除的郵件或電子郵件</span><span class="sxs-lookup"><span data-stu-id="51a68-303">Recover deleted items or email in Outlook Web App</span></span>](https://support.office.com/article/c3d8fc15-eeef-4f1c-81df-e27964b7edd4)
    
  - [<span data-ttu-id="51a68-304">在 Outlook 網頁版中還原已刪除的電子郵件</span><span class="sxs-lookup"><span data-stu-id="51a68-304">Restore deleted email messages in Outlook on the web</span></span>](https://support.office.com/article/a8ca78ac-4721-4066-95dd-571842e9fb11)
    
  - [<span data-ttu-id="51a68-305">在 Outlook 中復原已刪除的連絡人</span><span class="sxs-lookup"><span data-stu-id="51a68-305">Recover a deleted contact in Outlook</span></span>](https://support.office.com/article/51c83288-6888-4dcd-8c99-4932daabf643)
    
  - [<span data-ttu-id="51a68-306">還原 Outlook.com 中已刪除的電子郵件</span><span class="sxs-lookup"><span data-stu-id="51a68-306">Restore deleted email messages in Outlook.com</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=623435)
    
[<span data-ttu-id="51a68-307">回到頁首</span><span class="sxs-lookup"><span data-stu-id="51a68-307">Return to top</span></span>](recover-deleted-items-in-a-mailbox.md)
  

