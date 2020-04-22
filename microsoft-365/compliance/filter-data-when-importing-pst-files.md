---
title: 匯入 PST 檔案時篩選資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
description: '使用 Office 365 Import service 中的新智慧匯入功能，篩選實際匯入至目標信箱的專案。 智慧匯入可讓您主動決定要匯入哪些資料和留下的內容。 智慧匯入也提供您要匯入至 Office 365 之資料的洞察力。 '
ms.openlocfilehash: cc34163c46639765331772aaa1f4a0ae956294e3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636229"
---
# <a name="filter-data-when-importing-pst-files"></a><span data-ttu-id="af38e-105">匯入 PST 檔案時篩選資料</span><span class="sxs-lookup"><span data-stu-id="af38e-105">Filter data when importing PST files</span></span>

<span data-ttu-id="af38e-106">使用 Office 365 Import service 中的新智慧匯入功能，篩選實際匯入至目標信箱的 PST 檔案中的專案。</span><span class="sxs-lookup"><span data-stu-id="af38e-106">Use the new Intelligent Import feature in the Office 365 Import service to filter the items in PST files that actually get imported to the target mailboxes.</span></span> <span data-ttu-id="af38e-107">以下為運作方式：</span><span class="sxs-lookup"><span data-stu-id="af38e-107">Here's how it works:</span></span>
  
- <span data-ttu-id="af38e-108">在您建立並送出 PST 匯入工作之後，PST 檔案會上傳至 Microsoft 雲端中的 Azure 儲存體區域。</span><span class="sxs-lookup"><span data-stu-id="af38e-108">After you create and submit a PST import job, PST files are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
    
- <span data-ttu-id="af38e-109">Microsoft 365 會以安全且安全的方式來分析 PST 檔案中的資料，方式是識別信箱專案的保留天數，以及 PST 檔案中包含的不同郵件類型。</span><span class="sxs-lookup"><span data-stu-id="af38e-109">Microsoft 365 analyzes the data in the PST files, in a safe and secure manner, by identifying the age of the mailbox items and the different message types included in the PST files.</span></span>
    
- <span data-ttu-id="af38e-110">分析完成且資料準備好匯入時，您可以選擇是否要將 PST 檔案中的所有資料當做原樣匯入，或透過設定篩選器來剪裁所匯入的資料，以控制要匯入的資料。</span><span class="sxs-lookup"><span data-stu-id="af38e-110">When the analysis is complete and the data is ready to import, you have the option to import all data in the PST files as is or trim the data that's imported by setting filters that control what data gets imported.</span></span> <span data-ttu-id="af38e-111">例如，您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="af38e-111">For example, you can choose to:</span></span>
    
  - <span data-ttu-id="af38e-112">只匯入某段時間內的專案。</span><span class="sxs-lookup"><span data-stu-id="af38e-112">Import only items of a certain age.</span></span>
    
  - <span data-ttu-id="af38e-113">匯入選取的郵件類型。</span><span class="sxs-lookup"><span data-stu-id="af38e-113">Import selected message types.</span></span>
    
  - <span data-ttu-id="af38e-114">排除特定人員所傳送或接收的郵件。</span><span class="sxs-lookup"><span data-stu-id="af38e-114">Exclude messages sent or received by specific people.</span></span>
    
- <span data-ttu-id="af38e-115">設定篩選設定之後，Microsoft 365 只會將符合篩選準則的資料匯入到匯入工作中指定的目標信箱。</span><span class="sxs-lookup"><span data-stu-id="af38e-115">After you configure the filter settings, Microsoft 365 imports only the data that meets the filtering criteria to the target mailboxes specified in the import job.</span></span>
    
<span data-ttu-id="af38e-116">下圖顯示智慧匯入程式，並強調 Office 365 所執行的工作。</span><span class="sxs-lookup"><span data-stu-id="af38e-116">The following graphic shows the Intelligent Import process, and highlights the tasks you perform and the tasks performed by Office 365.</span></span>
  
![Office 365 中的智慧匯入程式](../media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="before-you-begin"></a><span data-ttu-id="af38e-118">開始之前</span><span class="sxs-lookup"><span data-stu-id="af38e-118">Before you begin</span></span>

- <span data-ttu-id="af38e-119">本主題中的步驟假設您已使用「網路上傳」或「磁片磁碟機運送」，在 Office 365 匯入服務中建立 PST 匯入工作。</span><span class="sxs-lookup"><span data-stu-id="af38e-119">The steps in this topic assume that you've created a PST import job in the Office 365 Import service by using network upload or drive shipping.</span></span> <span data-ttu-id="af38e-120">如需逐步指示，請參閱下列其中一個主題：</span><span class="sxs-lookup"><span data-stu-id="af38e-120">For step-by-step instructions, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="af38e-121">使用網路上傳將 PST 檔案匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="af38e-121">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
    
  - [<span data-ttu-id="af38e-122">使用磁碟機寄送將 PST 檔案匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="af38e-122">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- <span data-ttu-id="af38e-123">使用 [網路上傳] 建立匯入工作之後，安全性 & 合規性中心的 [匯入] 頁面上的匯入工作狀態會設為 [**正在進行分析**]，這表示 Microsoft 365 正在分析您所上傳的 PST 檔案中的資料。</span><span class="sxs-lookup"><span data-stu-id="af38e-123">After you create an import job by using network upload, the status for the import job on the Import page in the Security & Compliance Center is set to **Analysis in progress**, which means that Microsoft 365 is analyzing the data in the PST files that you uploaded.</span></span> <span data-ttu-id="af38e-124">按一下 [重新](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)整理重新整理] 以更新匯入工作的狀態。 **Refresh** ![</span><span class="sxs-lookup"><span data-stu-id="af38e-124">Click **Refresh**![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the status for the import job.</span></span> 
    
- <span data-ttu-id="af38e-125">針對磁片磁碟機運送的匯入工作，microsoft 365 會在 Microsoft 資料中心人員收到您的硬碟並上傳 PST 檔案至您組織的 Azure 儲存體區域之後，進行資料分析。</span><span class="sxs-lookup"><span data-stu-id="af38e-125">For drive shipping import jobs, the data will be analyzed by Microsoft 365 after Microsoft datacenter personnel receive your hard drive and upload the PST files to the Azure storage area for your organization.</span></span>
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a><span data-ttu-id="af38e-126">篩選匯入至信箱的資料</span><span class="sxs-lookup"><span data-stu-id="af38e-126">Filter data that gets imported to mailboxes</span></span>

<span data-ttu-id="af38e-127">在您建立 PST 匯入工作之後，請遵循下列步驟，在將資料匯入 Office 365 之前先加以篩選。</span><span class="sxs-lookup"><span data-stu-id="af38e-127">After you've created a PST import job, follow these steps to filter the data before you import it to Office 365.</span></span>
  
1. <span data-ttu-id="af38e-128">移至[https://protection.office.com/](https://protection.office.com/)並使用您組織中的系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="af38e-128">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your organization.</span></span> 
    
2. <span data-ttu-id="af38e-129">按一下 [**資訊管理** \>匯**入** \> **PST**檔案]。</span><span class="sxs-lookup"><span data-stu-id="af38e-129">Click **Information governance** \> **Import** \> **Import PST files**.</span></span>
    
    <span data-ttu-id="af38e-130">您的組織的匯入工作會列于 [匯**入 PST**檔案] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="af38e-130">The import jobs for your organization are listed on the **Import PST files** page.</span></span> <span data-ttu-id="af38e-131">請注意，[**狀態**] 欄中的 [**分析已完成**] 值會指出已由 Microsoft 365 進行分析且已準備好要匯入的匯入工作。</span><span class="sxs-lookup"><span data-stu-id="af38e-131">Note that the **Analysis completed** value in the **Status** column indicates the import jobs that have been analyzed by Microsoft 365 and are ready for you to import.</span></span> 
    
    ![分析完成狀態表示 Microsoft 365 已分析 PST 檔案中的資料](../media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. <span data-ttu-id="af38e-133">針對您想要完成的匯入工作，按一下 [已**準備好匯入 Office 365** ]。</span><span class="sxs-lookup"><span data-stu-id="af38e-133">Click **Ready to import to Office 365** for the import job that you want to complete.</span></span> 
    
    <span data-ttu-id="af38e-134">隨即會顯示彈出頁面，以及關於該匯入工作的 PST 檔案資訊和其他資訊。</span><span class="sxs-lookup"><span data-stu-id="af38e-134">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
4. <span data-ttu-id="af38e-135">按一下 [匯**入至 Office 365**]。</span><span class="sxs-lookup"><span data-stu-id="af38e-135">Click **Import to Office 365**.</span></span>
    
    <span data-ttu-id="af38e-136">隨即會顯示 [篩選您的資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="af38e-136">The **Filter your data** page is displayed.</span></span> <span data-ttu-id="af38e-137">它包含有關匯入工作之 PST 檔案中資料的相關資訊，包括資料時期的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="af38e-137">It contains data insights about the data in the PST files for the import job, including information about the age of the data.</span></span> 
    
    ![[篩選您的資料] 頁面會顯示匯入工作之 PST 檔案的資料洞察力](../media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. <span data-ttu-id="af38e-139">根據是否要裁切匯入至 Microsoft 365 的資料，在 [**是否要篩選資料？**] 下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="af38e-139">Based on whether or not you want to trim the data that's imported to Microsoft 365, under **Do you want to filter your data?**, do one of the following:</span></span>
    
    <span data-ttu-id="af38e-140">a.</span><span class="sxs-lookup"><span data-stu-id="af38e-140">a.</span></span> <span data-ttu-id="af38e-141">按一下 **[是，我想要在匯入之前加以篩選]** ，以裁切您匯入的資料，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="af38e-141">Click **Yes, I want to filter it before importing** to trim the data that you import, and then click **Next**.</span></span>
    
    <span data-ttu-id="af38e-142">[匯**入資料到 Office 365] 頁面**會顯示從 Microsoft 365 執行之分析的詳細資料洞察力。</span><span class="sxs-lookup"><span data-stu-id="af38e-142">The **Import data to Office 365 page** page is displayed with detailed data insights from the analysis that Microsoft 365 performed.</span></span> 
    
    ![Microsoft 365 顯示來自其 PST 檔案分析的詳細資料洞察力](../media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    <span data-ttu-id="af38e-144">此頁面上的圖形會顯示要匯入的資料量。</span><span class="sxs-lookup"><span data-stu-id="af38e-144">The graph on this page shows the amount of data that will be imported.</span></span> <span data-ttu-id="af38e-145">在 PST 檔案中的每一封郵件類型的相關資訊都會顯示在圖形中。</span><span class="sxs-lookup"><span data-stu-id="af38e-145">Information about each message type found in the PST files is displayed in the graph.</span></span> <span data-ttu-id="af38e-146">您可以將游標懸停于每個橫條圖上方，以顯示該郵件類型的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="af38e-146">You can hover the cursor over each bar to display specific information about that message type.</span></span> <span data-ttu-id="af38e-147">根據 PST 檔的分析，也有一個具有不同 age 值的下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="af38e-147">There is also a drop-down list with different age values based on the analysis of the PST files.</span></span> <span data-ttu-id="af38e-148">當您在下拉式清單中選取年齡時，會更新圖形以顯示所選取的年齡要匯入的資料量。</span><span class="sxs-lookup"><span data-stu-id="af38e-148">When you select an age in the drop-down list, the graph is updated to show how much data will be imported for the selected age.</span></span> 
    
    <span data-ttu-id="af38e-149">b.</span><span class="sxs-lookup"><span data-stu-id="af38e-149">b.</span></span> <span data-ttu-id="af38e-150">若要設定額外篩選以減少匯入的資料量，請按一下 [**更多篩選選項**]。</span><span class="sxs-lookup"><span data-stu-id="af38e-150">To configure addition filters to reduce the amount of data that's imported, click **More filtering options**.</span></span>
    
    ![在 [其他選項] 頁面上設定篩選，以裁切匯入的資料](../media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    <span data-ttu-id="af38e-152">您可以設定這些篩選器：</span><span class="sxs-lookup"><span data-stu-id="af38e-152">You can configure these filters:</span></span>
    
      - <span data-ttu-id="af38e-153">**Age** -選取年齡，只會匯入比指定的年齡更新的專案。</span><span class="sxs-lookup"><span data-stu-id="af38e-153">**Age** - Select an age so only items that are newer than the specified age will be imported.</span></span> <span data-ttu-id="af38e-154">請參閱[詳細資訊](#more-information)一節，以取得 Microsoft 365 如何判斷**年齡**篩選的年齡桶的描述。</span><span class="sxs-lookup"><span data-stu-id="af38e-154">See the [More information](#more-information) section for a description about how Microsoft 365 determines the age buckets for the **Age** filter.</span></span> 
    
      - <span data-ttu-id="af38e-155">**類型**-此區段會顯示在匯入工作的 PST 檔案中找到的所有郵件類型。</span><span class="sxs-lookup"><span data-stu-id="af38e-155">**Type** - This section shows all the message types that were found in the PST files for the import job.</span></span> <span data-ttu-id="af38e-156">您可以在要排除的郵件類型旁取消勾選方塊。</span><span class="sxs-lookup"><span data-stu-id="af38e-156">You can uncheck a box next to a message type that you want to exclude.</span></span> <span data-ttu-id="af38e-157">請注意，您無法排除其他郵件類型。</span><span class="sxs-lookup"><span data-stu-id="af38e-157">Note that you can't exclude the Other message type.</span></span> <span data-ttu-id="af38e-158">請參閱[More information](#more-information)一節以取得其他類別中包含的信箱專案清單。</span><span class="sxs-lookup"><span data-stu-id="af38e-158">See the [More information](#more-information) section for a list of mailbox items that are included in the Other category.</span></span> 
    
      - <span data-ttu-id="af38e-159">**使用者**-您可以排除特定人員所傳送或接收的郵件。</span><span class="sxs-lookup"><span data-stu-id="af38e-159">**Users** - You can exclude messages that are sent or received by specific people.</span></span> <span data-ttu-id="af38e-160">若要排除出現在 [寄件者：] 欄位、[收件者：] 欄位或郵件 [副本：] 欄位中的人員，請按一下該收件者類型旁的 [**排除使用者**]。</span><span class="sxs-lookup"><span data-stu-id="af38e-160">To exclude people who appear in the From: field, To: field, or the Cc: field of messages, click **Exclude users** next to that recipient type.</span></span> <span data-ttu-id="af38e-161">輸入人員的電子郵件地址（SMTP 位址） **，按一下 [**![新增圖示](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) ]，將其新增至該收件者類型的排除使用者清單，然後按一下 [**儲存**] 以儲存排除的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="af38e-161">Type the email address (SMTP address) of the person, click **Add**![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) to add them to the list of excluded users for that recipient type, and then click **Save** to save the list of excluded users.</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="af38e-162">Microsoft 365 不會顯示設定**人員**篩選所產生的資料洞察力。</span><span class="sxs-lookup"><span data-stu-id="af38e-162">Microsoft 365 doesn't show data insights that result from setting the **People** filter.</span></span> <span data-ttu-id="af38e-163">不過，如果您將此篩選器設定為排除特定人員所傳送或接收的郵件，則會在實際的匯入程式期間排除這些郵件。</span><span class="sxs-lookup"><span data-stu-id="af38e-163">However, if you set this filter to exclude messages sent or received by specific people, those messages will be excluded during the actual import process.</span></span> 
  
    <span data-ttu-id="af38e-164">c.</span><span class="sxs-lookup"><span data-stu-id="af38e-164">c.</span></span> <span data-ttu-id="af38e-165">按一下 [**其他篩選選項**] [**飛入]** 頁面中的 [套用]，以儲存篩選設定。</span><span class="sxs-lookup"><span data-stu-id="af38e-165">Click **Apply** in the **More filtering options** fly out page to save your filter settings.</span></span> 
    
    <span data-ttu-id="af38e-166">[匯**入資料到 Office 365** ] 頁面上的資料洞察力會根據您的篩選設定進行更新，包括根據篩選設定所匯入的總數據量。</span><span class="sxs-lookup"><span data-stu-id="af38e-166">The data insights on the **Import data to Office 365** page are updated based on your filter settings, including the total amount of data that will be imported based on the filter settings.</span></span> <span data-ttu-id="af38e-167">請注意，也會顯示篩選設定的摘要。</span><span class="sxs-lookup"><span data-stu-id="af38e-167">Note that a summary of the filter settings is also shown.</span></span> <span data-ttu-id="af38e-168">您可以按一下篩選旁邊的 [**編輯**]，以視需要變更設定。</span><span class="sxs-lookup"><span data-stu-id="af38e-168">You can click **Edit** next to a filter to change the setting if necessary.</span></span> 
    
    ![資料洞察力會根據您的篩選設定進行更新](../media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    <span data-ttu-id="af38e-170">d.</span><span class="sxs-lookup"><span data-stu-id="af38e-170">d.</span></span> <span data-ttu-id="af38e-171">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="af38e-171">Click **Next**.</span></span>
    
    <span data-ttu-id="af38e-172">隨即會顯示 [狀態] 頁面，顯示篩選設定。</span><span class="sxs-lookup"><span data-stu-id="af38e-172">A status page is displayed showing your filter settings.</span></span> <span data-ttu-id="af38e-173">同樣的，您也可以編輯任何篩選設定。</span><span class="sxs-lookup"><span data-stu-id="af38e-173">Again, you can edit any of the filter settings.</span></span>
    
    <span data-ttu-id="af38e-174">e.</span><span class="sxs-lookup"><span data-stu-id="af38e-174">e.</span></span> <span data-ttu-id="af38e-175">按一下 [匯**入資料**] 以開始匯入。</span><span class="sxs-lookup"><span data-stu-id="af38e-175">Click **Import data** to start the import .</span></span> <span data-ttu-id="af38e-176">請注意，會顯示要匯入的總數據量。</span><span class="sxs-lookup"><span data-stu-id="af38e-176">Note that the total amount of data that will be imported is displayed.</span></span> 
    
    <span data-ttu-id="af38e-177">或</span><span class="sxs-lookup"><span data-stu-id="af38e-177">Or</span></span>
    
    <span data-ttu-id="af38e-178">a.</span><span class="sxs-lookup"><span data-stu-id="af38e-178">a.</span></span> <span data-ttu-id="af38e-179">按一下 [**否，我要**匯入所有內容]，將 PST 檔案中的所有資料匯入 Office 365，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="af38e-179">Click **No, I want to import everything** to import all data in the PST files to Office 365, and then click **Next**.</span></span>
    
    <span data-ttu-id="af38e-180">b.</span><span class="sxs-lookup"><span data-stu-id="af38e-180">b.</span></span> <span data-ttu-id="af38e-181">在 [匯**入資料到 Office 365** ] 頁面上，按一下 [匯**入資料**] 以開始匯入。</span><span class="sxs-lookup"><span data-stu-id="af38e-181">On the **Import data to Office 365** page, click **Import data** to start the import.</span></span> <span data-ttu-id="af38e-182">請注意，會顯示要匯入的總數據量。</span><span class="sxs-lookup"><span data-stu-id="af38e-182">Note that the total amount of data that will be imported is displayed.</span></span> 
    
6. <span data-ttu-id="af38e-183">在 [匯**入 PST**檔案] 頁面上 **，按一下** ![[重新整理重新整理]](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)。</span><span class="sxs-lookup"><span data-stu-id="af38e-183">On the **Import PST files** page, click **Refresh** ![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png).</span></span> <span data-ttu-id="af38e-184">[**狀態**] 欄中會顯示匯入工作的狀態。</span><span class="sxs-lookup"><span data-stu-id="af38e-184">The status for the import job is displayed in the **Status** column.</span></span> 
    
7. <span data-ttu-id="af38e-185">按一下 [匯入工作]，以顯示更詳細的資訊，例如每個 PST 檔案的狀態，以及您設定的篩選設定。</span><span class="sxs-lookup"><span data-stu-id="af38e-185">Click the import the job to display more detailed information, such as the status for each PST file and the filter settings that you configured.</span></span>

  
## <a name="more-information"></a><span data-ttu-id="af38e-186">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="af38e-186">More information</span></span>

- <span data-ttu-id="af38e-187">Microsoft 365 如何判斷年齡篩選的增量？</span><span class="sxs-lookup"><span data-stu-id="af38e-187">How does Microsoft 365 determine the increments for the age filter?</span></span> <span data-ttu-id="af38e-188">當 Microsoft 365 分析 PST 檔案時，它會查看每個專案的傳送或接收時間戳記（如果專案同時有傳送和接收的時間戳記，則會選取最舊的日期）。</span><span class="sxs-lookup"><span data-stu-id="af38e-188">When Microsoft 365 analyzes a PST file, it looks at the sent or received time stamp of each item (if an item has both a sent and received timestamp, the oldest date is selected).</span></span> <span data-ttu-id="af38e-189">然後，Microsoft 365 會查看該時間戳記的 year 值，並將它與目前的日期進行比較，以判斷專案的年齡。</span><span class="sxs-lookup"><span data-stu-id="af38e-189">Then Microsoft 365 looks at the year value for that timestamp and compares it to the current date to determine the age of the item.</span></span> <span data-ttu-id="af38e-190">然後，這些年齡會做為**時期**篩選的下拉式清單中的值使用。</span><span class="sxs-lookup"><span data-stu-id="af38e-190">These ages are then used as the values in the drop-down list for the **Age** filter.</span></span> <span data-ttu-id="af38e-191">例如，如果 PST 檔案有來自2016、2015及2014的郵件，則**Age**篩選中的值會是**1 年**、 **2 年**和**3 年**。</span><span class="sxs-lookup"><span data-stu-id="af38e-191">For example, if a PST file has messages from 2016, 2015, and 2014, then values in the **Age** filter would be **1 year**, **2 years**, and **3 years**.</span></span>
    
- <span data-ttu-id="af38e-192">下表列出 [其他**選項**] [飛出] 頁面上的 [**類型**篩選] 中的 [**其他**類別] 類別中所包含的郵件類型（請參閱上一個程式中的步驟5b）。</span><span class="sxs-lookup"><span data-stu-id="af38e-192">The following table lists the message types that are included in the **Other** category in the **Type** filter on the **More options** fly out page (see Step 5b in the previous procedure).</span></span> <span data-ttu-id="af38e-193">目前，當您匯入 Pst 至 Office 365 時，無法排除 "Other" 類別中的專案。</span><span class="sxs-lookup"><span data-stu-id="af38e-193">Currently, you can't exclude items in the "Other" category when you import PSTs to Office 365.</span></span> 
    
    |<span data-ttu-id="af38e-194">**郵件類別識別項**</span><span class="sxs-lookup"><span data-stu-id="af38e-194">**Message class ID**</span></span>|<span data-ttu-id="af38e-195">**使用此郵件類別的信箱專案**</span><span class="sxs-lookup"><span data-stu-id="af38e-195">**Mailbox items that use this message class**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="af38e-196">Ipm。活動</span><span class="sxs-lookup"><span data-stu-id="af38e-196">IPM.Activity</span></span>  <br/> |<span data-ttu-id="af38e-197">日誌項目</span><span class="sxs-lookup"><span data-stu-id="af38e-197">Journal entries</span></span>  <br/> |
    |<span data-ttu-id="af38e-198">Ipm。文檔</span><span class="sxs-lookup"><span data-stu-id="af38e-198">IPM.Document</span></span>  <br/> |<span data-ttu-id="af38e-199">檔和檔案（未附加至電子郵件訊息）</span><span class="sxs-lookup"><span data-stu-id="af38e-199">Documents and files (not attached to an email message)</span></span>  <br/> |
    |<span data-ttu-id="af38e-200">Ipm。檔</span><span class="sxs-lookup"><span data-stu-id="af38e-200">IPM.File</span></span>  <br/> |<span data-ttu-id="af38e-201">（與 IPM 相同。Document</span><span class="sxs-lookup"><span data-stu-id="af38e-201">(same as IPM.Document)</span></span>  <br/> |
    |<span data-ttu-id="af38e-202">Ipm。記事。 IMC 通知</span><span class="sxs-lookup"><span data-stu-id="af38e-202">IPM.Note.IMC.Notification</span></span>  <br/> |<span data-ttu-id="af38e-203">Internet Mail Connect 所傳送的報告，也就是網際網路的 Exchange Server 閘道</span><span class="sxs-lookup"><span data-stu-id="af38e-203">Reports sent by Internet Mail Connect, which is the Exchange Server gateway to the Internet</span></span>  <br/> |
    |<span data-ttu-id="af38e-204">Ipm。記事： Microsoft。 Fax</span><span class="sxs-lookup"><span data-stu-id="af38e-204">IPM.Note.Microsoft.Fax</span></span>  <br/> |<span data-ttu-id="af38e-205">傳真訊息</span><span class="sxs-lookup"><span data-stu-id="af38e-205">Fax messages</span></span>  <br/> |
    |<span data-ttu-id="af38e-206">Ipm。記事： Oof 範本。 Microsoft</span><span class="sxs-lookup"><span data-stu-id="af38e-206">IPM.Note.Rules.Oof.Template.Microsoft</span></span>  <br/> |<span data-ttu-id="af38e-207">外出自動回復郵件</span><span class="sxs-lookup"><span data-stu-id="af38e-207">Out-of-office auto-reply messages</span></span>  <br/> |
    |<span data-ttu-id="af38e-208">Ipm。記事。 ReplyTemplate</span><span class="sxs-lookup"><span data-stu-id="af38e-208">IPM.Note.Rules.ReplyTemplate.Microsoft</span></span>  <br/> |<span data-ttu-id="af38e-209">收件匣規則所傳送的回復</span><span class="sxs-lookup"><span data-stu-id="af38e-209">Replies sent by an inbox rule</span></span>  <br/> |
    |<span data-ttu-id="af38e-210">Ipm。Ole。類</span><span class="sxs-lookup"><span data-stu-id="af38e-210">IPM.OLE.Class</span></span>  <br/> |<span data-ttu-id="af38e-211">定期系列的例外狀況</span><span class="sxs-lookup"><span data-stu-id="af38e-211">Exceptions for a recurring series</span></span>  <br/> |
    |<span data-ttu-id="af38e-212">Ipm。召回。報告</span><span class="sxs-lookup"><span data-stu-id="af38e-212">IPM.Recall.Report</span></span>  <br/> |<span data-ttu-id="af38e-213">郵件回收報告</span><span class="sxs-lookup"><span data-stu-id="af38e-213">Message recall reports</span></span>  <br/> |
    |<span data-ttu-id="af38e-214">Ipm。遠端</span><span class="sxs-lookup"><span data-stu-id="af38e-214">IPM.Remote</span></span>  <br/> |<span data-ttu-id="af38e-215">遠端郵件訊息</span><span class="sxs-lookup"><span data-stu-id="af38e-215">Remote mail messages</span></span>  <br/> |
    |<span data-ttu-id="af38e-216">Ipm。報告</span><span class="sxs-lookup"><span data-stu-id="af38e-216">IPM.Report</span></span>  <br/> |<span data-ttu-id="af38e-217">專案狀態報表</span><span class="sxs-lookup"><span data-stu-id="af38e-217">Item status reports</span></span>  <br/> |
