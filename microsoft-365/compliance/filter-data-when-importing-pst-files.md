---
title: 匯入至 Office 365 的 PST 檔案時篩選資料
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
description: '使用 Office 365 匯入服務中的新的智慧型匯入功能，來篩選實際取得匯入至目標信箱的項目。 智慧型匯入可讓您主動決定何種資料匯入及要留下的項目。 智慧型匯入也可提供見解上您要匯入至 Office 365 的資料。 '
ms.openlocfilehash: 2e012159f7f278dc10db14b07531686b5d130fd9
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077027"
---
# <a name="filter-data-when-importing-pst-files-to-office-365"></a><span data-ttu-id="d0e90-105">匯入至 Office 365 的 PST 檔案時篩選資料</span><span class="sxs-lookup"><span data-stu-id="d0e90-105">Filter data when importing PST files to Office 365</span></span>

<span data-ttu-id="d0e90-106">使用 Office 365 匯入服務中的新的智慧型匯入功能，來篩選實際取得匯入至目標信箱的 PST 檔案中的項目。</span><span class="sxs-lookup"><span data-stu-id="d0e90-106">Use the new Intelligent Import feature in the Office 365 Import service to filter the items in PST files that actually get imported to the target mailboxes.</span></span> <span data-ttu-id="d0e90-107">以下為運作方式：</span><span class="sxs-lookup"><span data-stu-id="d0e90-107">Here's how it works:</span></span>
  
- <span data-ttu-id="d0e90-108">您可以建立及提交 PST 匯入工作之後，PST 檔案上傳至 Microsoft 雲端中的 Azure 儲存體] 區域中。</span><span class="sxs-lookup"><span data-stu-id="d0e90-108">After you create and submit a PST import job, PST files are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
    
- <span data-ttu-id="d0e90-109">Office 365 會分析安全無虞的方式，PST 檔案中的資料，藉由識別的保留天數的信箱項目和 PST 檔案中包含不同的郵件類型。</span><span class="sxs-lookup"><span data-stu-id="d0e90-109">Office 365 analyzes the data in the PST files, in a safe and secure manner, by identifying the age of the mailbox items and the different message types included in the PST files.</span></span>
    
- <span data-ttu-id="d0e90-110">當分析已完成，且可匯入資料時，您必須匯入或修剪匯入藉由設定篩選器來控制哪些資料取得匯入資料時的 PST 檔案中的所有資料的選項。</span><span class="sxs-lookup"><span data-stu-id="d0e90-110">When the analysis is complete and the data is ready to import, you have the option to import all data in the PST files as is or trim the data that's imported by setting filters that control what data gets imported.</span></span> <span data-ttu-id="d0e90-111">例如，您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="d0e90-111">For example, you can choose to:</span></span>
    
  - <span data-ttu-id="d0e90-112">匯入特定天數的項的目。</span><span class="sxs-lookup"><span data-stu-id="d0e90-112">Import only items of a certain age.</span></span>
    
  - <span data-ttu-id="d0e90-113">選取 [匯入訊息類型。</span><span class="sxs-lookup"><span data-stu-id="d0e90-113">Import selected message types.</span></span>
    
  - <span data-ttu-id="d0e90-114">排除特定人員所傳送或接收的郵件。</span><span class="sxs-lookup"><span data-stu-id="d0e90-114">Exclude messages sent or received by specific people.</span></span>
    
- <span data-ttu-id="d0e90-115">設定篩選設定之後，Office 365 匯入僅符合要匯入工作中所指定的目標信箱的篩選準則的資料。</span><span class="sxs-lookup"><span data-stu-id="d0e90-115">After you configure the filter settings, Office 365 imports only the data that meets the filtering criteria to the target mailboxes specified in the import job.</span></span>
    
<span data-ttu-id="d0e90-116">下圖顯示的智慧型匯入程序，並會醒目提示您執行的工作和 Office 365 所執行的工作。</span><span class="sxs-lookup"><span data-stu-id="d0e90-116">The following graphic shows the Intelligent Import process, and highlights the tasks you perform and the tasks performed by Office 365.</span></span>
  
![Office 365 中的智慧型匯入程序](media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="before-you-begin"></a><span data-ttu-id="d0e90-118">開始之前</span><span class="sxs-lookup"><span data-stu-id="d0e90-118">Before you begin</span></span>

- <span data-ttu-id="d0e90-119">本主題中的步驟假設您已建立 PST 匯入工作中的 Office 365 匯入服務透過網路上傳或磁碟機運送。</span><span class="sxs-lookup"><span data-stu-id="d0e90-119">The steps in this topic assume that you've created a PST import job in the Office 365 Import service by using network upload or drive shipping.</span></span> <span data-ttu-id="d0e90-120">逐步指示，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="d0e90-120">For step-by-step instructions, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="d0e90-121">使用網路上傳將 PST 檔案匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="d0e90-121">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
    
  - [<span data-ttu-id="d0e90-122">使用磁碟機運送將 PST 檔案匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="d0e90-122">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- <span data-ttu-id="d0e90-123">之後您可以使用網路上傳，合規性中心設為**在進行中的分析**，這表示 Office 365 會分析您上傳的 PST 檔案中的資料安全性 & [匯入] 頁面上匯入工作的狀態，以建立匯入工作。</span><span class="sxs-lookup"><span data-stu-id="d0e90-123">After you create an import job by using network upload, the status for the import job on the Import page in the Security & Compliance Center is set to **Analysis in progress**, which means that Office 365 is analyzing the data in the PST files that you uploaded.</span></span> <span data-ttu-id="d0e90-124">按一下 [**重新整理**![重新整理](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)更新匯入工作的狀態。</span><span class="sxs-lookup"><span data-stu-id="d0e90-124">Click **Refresh**![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the status for the import job.</span></span> 
    
- <span data-ttu-id="d0e90-125">磁碟機運送匯入工作，如資料會分析 Office 365 Microsoft 資料中心人員會收到您的硬碟機，並將 PST 檔案上傳至您的組織的 Azure 儲存體區域之後。</span><span class="sxs-lookup"><span data-stu-id="d0e90-125">For drive shipping import jobs, the data will be analyzed by Office 365 after Microsoft data center personnel receive your hard drive and upload the PST files to the Azure storage area for your organization.</span></span>
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a><span data-ttu-id="d0e90-126">篩選取得匯入至信箱的資料</span><span class="sxs-lookup"><span data-stu-id="d0e90-126">Filter data that gets imported to mailboxes</span></span>

<span data-ttu-id="d0e90-127">您已建立之後 PST 匯入工作，請遵循下列步驟之前進行篩選資料匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d0e90-127">After you've created a PST import job, follow these steps to filter the data before you import it to Office 365.</span></span>
  
1. <span data-ttu-id="d0e90-128">移至 [[https://protection.office.com/](https://protection.office.com/)並登入 Office 365 組織中系統管理員帳戶使用的認證。</span><span class="sxs-lookup"><span data-stu-id="d0e90-128">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="d0e90-129">按一下 [**資料控管** \> **匯入**。</span><span class="sxs-lookup"><span data-stu-id="d0e90-129">Click **Data governance** \> **Import**.</span></span>
    
    <span data-ttu-id="d0e90-130">貴組織的匯入工作會列在 [**匯入**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="d0e90-130">The import jobs for your organization are listed on the **Import** page.</span></span> <span data-ttu-id="d0e90-131">請注意，在 [**狀態**] 欄中的**分析完成**值表示有已由 Office 365 進行分析，並準備好讓您匯入的匯入工作。</span><span class="sxs-lookup"><span data-stu-id="d0e90-131">Note that the **Analysis completed** value in the **Status** column indicates the import jobs that have been analyzed by Office 365 and are ready for you to import.</span></span> 
    
    ![分析完成狀態表示 Office 365 已經分析 PST 檔案中的資料](media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. <span data-ttu-id="d0e90-133">您想要完成匯入工作，按一下 [**準備好匯入至 Office 365** 。</span><span class="sxs-lookup"><span data-stu-id="d0e90-133">Click **Ready to import to Office 365** for the import job that you want to complete.</span></span> 
    
    <span data-ttu-id="d0e90-134">飛入] 頁面上的會顯示 PST 檔案的相關資訊與匯入工作的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="d0e90-134">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
4. <span data-ttu-id="d0e90-135">按一下 [**匯入至 Office 365**。</span><span class="sxs-lookup"><span data-stu-id="d0e90-135">Click **Import to Office 365**.</span></span>
    
    <span data-ttu-id="d0e90-136">會顯示 [**篩選您的資料**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="d0e90-136">The **Filter your data** page is displayed.</span></span> <span data-ttu-id="d0e90-137">它包含在 PST 檔案匯入工作，包括資訊的資料保留資料的相關資料見解。</span><span class="sxs-lookup"><span data-stu-id="d0e90-137">It contains data insights about the data in the PST files for the import job, including information about the age of the data.</span></span> 
    
    ![篩選您的資料] 頁面上顯示資料見解的 PST 檔案匯入工作](media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. <span data-ttu-id="d0e90-139">根據您想要是否修剪匯入的資料到 Office 365，在**您想要篩選您的資料？**，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d0e90-139">Based on whether or not you want to trim the data that's imported to Office 365, under **Do you want to filter your data?**, do one of the following:</span></span>
    
    <span data-ttu-id="d0e90-140">a.</span><span class="sxs-lookup"><span data-stu-id="d0e90-140">a.</span></span> <span data-ttu-id="d0e90-141">按一下 [**是，我想要匯入之前先加以篩選**修剪您匯入的資料，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d0e90-141">Click **Yes, I want to filter it before importing** to trim the data that you import, and then click **Next**.</span></span>
    
    <span data-ttu-id="d0e90-142">[**匯入資料到 Office 365 頁面**] 頁面上會顯示與 Office 365 執行分析的觀點，詳細的資料。</span><span class="sxs-lookup"><span data-stu-id="d0e90-142">The **Import data to Office 365 page** page is displayed with detailed data insights from the analysis that Office 365 performed.</span></span> 
    
    ![Office 365 會顯示 PST 檔案的分析的觀點，詳細的資料](media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    <span data-ttu-id="d0e90-144">在此頁面上圖顯示將匯入的資料量。</span><span class="sxs-lookup"><span data-stu-id="d0e90-144">The graph on this page shows the amount of data that will be imported.</span></span> <span data-ttu-id="d0e90-145">圖形中顯示的 PST 檔案中，找到每個郵件類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d0e90-145">Information about each message type found in the PST files is displayed in the graph.</span></span> <span data-ttu-id="d0e90-146">您可以將游標停留每一列中顯示該郵件類型的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="d0e90-146">You can hover the cursor over each bar to display specific information about that message type.</span></span> <span data-ttu-id="d0e90-147">也是根據分析的 PST 檔案的不同的保留時間下限值下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="d0e90-147">There is also a drop-down list with different age values based on the analysis of the PST files.</span></span> <span data-ttu-id="d0e90-148">當您在下拉式清單中選取的保留天數時，此圖形會更新以顯示多少資料將會匯入所選的天數。</span><span class="sxs-lookup"><span data-stu-id="d0e90-148">When you select an age in the drop-down list, the graph is updated to show how much data will be imported for the selected age.</span></span> 
    
    <span data-ttu-id="d0e90-149">b.</span><span class="sxs-lookup"><span data-stu-id="d0e90-149">b.</span></span> <span data-ttu-id="d0e90-150">若要設定新增篩選器，以減少的匯入的資料量，請按一下 [**更多的篩選選項**。</span><span class="sxs-lookup"><span data-stu-id="d0e90-150">To configure addition filters to reduce the amount of data that's imported, click **More filtering options**.</span></span>
    
    ![修剪匯入的資料 [更多選項] 頁面上設定篩選器](media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    <span data-ttu-id="d0e90-152">您可以設定這些篩選器：</span><span class="sxs-lookup"><span data-stu-id="d0e90-152">You can configure these filters:</span></span>
    
      - <span data-ttu-id="d0e90-153">**保留時間下限**-選取要匯入保留天數，因此只有項目，會比指定使用期限。</span><span class="sxs-lookup"><span data-stu-id="d0e90-153">**Age** - Select an age so only items that are newer than the specified age will be imported.</span></span> <span data-ttu-id="d0e90-154">請參閱關於 Office 365 如何判斷**保留**篩選時代 bucket 描述[的詳細資訊](#more-information)一節。</span><span class="sxs-lookup"><span data-stu-id="d0e90-154">See the [More information](#more-information) section for a description about how Office 365 determines the age buckets for the **Age** filter.</span></span> 
    
      - <span data-ttu-id="d0e90-155">**Type** -此區段顯示匯入工作的 PST 檔案中找不到的所有郵件類型。</span><span class="sxs-lookup"><span data-stu-id="d0e90-155">**Type** - This section shows all the message types that were found in the PST files for the import job.</span></span> <span data-ttu-id="d0e90-156">您可以取消選取您想要排除的訊息類型旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="d0e90-156">You can uncheck a box next to a message type that you want to exclude.</span></span> <span data-ttu-id="d0e90-157">請注意，您不能排除的其他郵件類型。</span><span class="sxs-lookup"><span data-stu-id="d0e90-157">Note that you can't exclude the Other message type.</span></span> <span data-ttu-id="d0e90-158">請參閱清單[的詳細資訊](#more-information)一節所包含的其他類別中的信箱項目。</span><span class="sxs-lookup"><span data-stu-id="d0e90-158">See the [More information](#more-information) section for a list of mailbox items that are included in the Other category.</span></span> 
    
      - <span data-ttu-id="d0e90-159">**使用者**-您可以排除郵件已傳送或接收的特定對象。</span><span class="sxs-lookup"><span data-stu-id="d0e90-159">**Users** - You can exclude messages that are sent or received by specific people.</span></span> <span data-ttu-id="d0e90-160">若要排除人員出現在 [從:] 欄位中以:] 欄位中，] 或 [副本： 欄位的郵件，按一下該收件者類型旁的 [**排除的使用者**。</span><span class="sxs-lookup"><span data-stu-id="d0e90-160">To exclude people who appear in the From: field, To: field, or the Cc: field of messages, click **Exclude users** next to that recipient type.</span></span> <span data-ttu-id="d0e90-161">輸入該人員的電子郵件地址 （SMTP 地址），按一下 [**新增**![[新增] 圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)若要將其新增至該收件者類型，排除使用者清單，然後按一下 [**儲存**] 以儲存排除的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="d0e90-161">Type the email address (SMTP address) of the person, click **Add**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) to add them to the list of excluded users for that recipient type, and then click **Save** to save the list of excluded users.</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="d0e90-162">Office 365 不會顯示資料見解所得設定**人員**的篩選器。</span><span class="sxs-lookup"><span data-stu-id="d0e90-162">Office 365 doesn't show data insights that result from setting the **People** filter.</span></span> <span data-ttu-id="d0e90-163">不過，如果您將此篩選器，以排除特定人員所傳送或接收的郵件，這些郵件會排除在實際匯入程序期間。</span><span class="sxs-lookup"><span data-stu-id="d0e90-163">However, if you set this filter to exclude messages sent or received by specific people, those messages will be excluded during the actual import process.</span></span> 
  
    <span data-ttu-id="d0e90-164">c.</span><span class="sxs-lookup"><span data-stu-id="d0e90-164">c.</span></span> <span data-ttu-id="d0e90-165">**更多篩選選項**飛入] 以儲存您的篩選設定] 頁面中，按一下 [**套用]** 。</span><span class="sxs-lookup"><span data-stu-id="d0e90-165">Click **Apply** in the **More filtering options** fly out page to save your filter settings.</span></span> 
    
    <span data-ttu-id="d0e90-166">深入了解在**匯入資料到 Office 365** ] 頁面上會更新您篩選設定為基礎的資料，包括將匯入的資料總數根據篩選設定。</span><span class="sxs-lookup"><span data-stu-id="d0e90-166">The data insights on the **Import data to Office 365** page are updated based on your filter settings, including the total amount of data that will be imported based on the filter settings.</span></span> <span data-ttu-id="d0e90-167">請注意，也會顯示篩選器設定的摘要。</span><span class="sxs-lookup"><span data-stu-id="d0e90-167">Note that a summary of the filter settings is also shown.</span></span> <span data-ttu-id="d0e90-168">您可以**編輯**按一下旁的 [篩選器，視需要變更此設定。</span><span class="sxs-lookup"><span data-stu-id="d0e90-168">You can click **Edit** next to a filter to change the setting if necessary.</span></span> 
    
    ![根據您的篩選設定更新資料見解](media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    <span data-ttu-id="d0e90-170">d.</span><span class="sxs-lookup"><span data-stu-id="d0e90-170">d.</span></span> <span data-ttu-id="d0e90-171">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d0e90-171">Click **Next**.</span></span>
    
    <span data-ttu-id="d0e90-172">狀態] 頁面隨即顯示您篩選設定。</span><span class="sxs-lookup"><span data-stu-id="d0e90-172">A status page is displayed showing your filter settings.</span></span> <span data-ttu-id="d0e90-173">同樣地，您可以編輯的任何篩選器設定。</span><span class="sxs-lookup"><span data-stu-id="d0e90-173">Again, you can edit any of the filter settings.</span></span>
    
    <span data-ttu-id="d0e90-174">e.</span><span class="sxs-lookup"><span data-stu-id="d0e90-174">e.</span></span> <span data-ttu-id="d0e90-175">按一下 [開始匯入的 [**匯入資料**]。</span><span class="sxs-lookup"><span data-stu-id="d0e90-175">Click **Import data** to start the import .</span></span> <span data-ttu-id="d0e90-176">請注意，顯示總將匯入的資料量。</span><span class="sxs-lookup"><span data-stu-id="d0e90-176">Note that the total amount of data that will be imported is displayed.</span></span> 
    
    <span data-ttu-id="d0e90-177">或</span><span class="sxs-lookup"><span data-stu-id="d0e90-177">Or</span></span>
    
    <span data-ttu-id="d0e90-178">a.</span><span class="sxs-lookup"><span data-stu-id="d0e90-178">a.</span></span> <span data-ttu-id="d0e90-179">按一下 [**否，我想要匯入每個項目**匯入 Office 365 的 PST 檔案中的所有資料，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d0e90-179">Click **No, I want to import everything** to import all data in the PST files to Office 365, and then click **Next**.</span></span>
    
    <span data-ttu-id="d0e90-180">b.</span><span class="sxs-lookup"><span data-stu-id="d0e90-180">b.</span></span> <span data-ttu-id="d0e90-181">在 [**匯入資料到 Office 365** ] 頁面上，按一下 [開始匯入的 [**匯入資料**。</span><span class="sxs-lookup"><span data-stu-id="d0e90-181">On the **Import data to Office 365** page, click **Import data** to start the import.</span></span> <span data-ttu-id="d0e90-182">請注意，顯示總將匯入的資料量。</span><span class="sxs-lookup"><span data-stu-id="d0e90-182">Note that the total amount of data that will be imported is displayed.</span></span> 
    
6. <span data-ttu-id="d0e90-183">在 [**匯入**] 頁面上，按一下 [**重新整理**![重新整理](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)。</span><span class="sxs-lookup"><span data-stu-id="d0e90-183">On the **Import** page, click **Refresh** ![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png).</span></span> <span data-ttu-id="d0e90-184">匯入工作的狀態會顯示在 [**狀態**] 欄中。</span><span class="sxs-lookup"><span data-stu-id="d0e90-184">The status for the import job is displayed in the **Status** column.</span></span> 
    
7. <span data-ttu-id="d0e90-185">按一下 [匯入該工作以顯示更多詳細的資訊，例如每個 PST 檔案與您設定篩選設定的狀態。</span><span class="sxs-lookup"><span data-stu-id="d0e90-185">Click the import the job to display more detailed information, such as the status for each PST file and the filter settings that you configured.</span></span>

  
## <a name="more-information"></a><span data-ttu-id="d0e90-186">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d0e90-186">More information</span></span>

- <span data-ttu-id="d0e90-187">Office 365 如何判斷時代篩選器時，會遞增？</span><span class="sxs-lookup"><span data-stu-id="d0e90-187">How does Office 365 determine the increments for the age filter?</span></span> <span data-ttu-id="d0e90-188">當 Office 365 分析 PST 檔案時，它會尋找在每個項目的送出或收到的時間戳記 （如果項目有兩個傳送和接收的時間戳記，便會選取最舊的日期）。</span><span class="sxs-lookup"><span data-stu-id="d0e90-188">When Office 365 analyzes a PST file, it looks at the sent or received time stamp of each item (if an item has both a sent and received timestamp, the oldest date is selected).</span></span> <span data-ttu-id="d0e90-189">然後 Office 365 查看該時間戳記的年份值，並將其比較至判斷項目的存留期為目前日期。</span><span class="sxs-lookup"><span data-stu-id="d0e90-189">Then Office 365 looks at the year value for that timestamp and compares it to the current date to determine the age of the item.</span></span> <span data-ttu-id="d0e90-190">這些 ages 然後可用在下拉式清單中的值為**保留**篩選。</span><span class="sxs-lookup"><span data-stu-id="d0e90-190">These ages are then used as the values in the drop-down list for the **Age** filter.</span></span> <span data-ttu-id="d0e90-191">例如，如果 PST 檔案有來自 2016年、 2015年及 2014，然後**保留**篩選中的值會是**1 年**、 **2 年**及**3 年**。</span><span class="sxs-lookup"><span data-stu-id="d0e90-191">For example, if a PST file has messages from 2016, 2015, and 2014, then values in the **Age** filter would be **1 year**, **2 years**, and **3 years**.</span></span>
    
- <span data-ttu-id="d0e90-192">下表列出隨附的 [**其他**] 類別中**更多選項**飛入] 頁面上的**類型**篩選的郵件類型 （請參閱步驟 5b 前程序中的）。</span><span class="sxs-lookup"><span data-stu-id="d0e90-192">The following table lists the message types that are included in the **Other** category in the **Type** filter on the **More options** fly out page (see Step 5b in the previous procedure).</span></span> <span data-ttu-id="d0e90-193">目前，您無法在 Pst 匯入 Office 365 時，排除在 「 其他 」 類別中的項目。</span><span class="sxs-lookup"><span data-stu-id="d0e90-193">Currently, you can't exclude items in the "Other" category when you import PSTs to Office 365.</span></span> 
    
    |<span data-ttu-id="d0e90-194">**郵件類別識別項**</span><span class="sxs-lookup"><span data-stu-id="d0e90-194">**Message class ID**</span></span>|<span data-ttu-id="d0e90-195">**使用此郵件類別的信箱項目**</span><span class="sxs-lookup"><span data-stu-id="d0e90-195">**Mailbox items that use this message class**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="d0e90-196">IPM。活動</span><span class="sxs-lookup"><span data-stu-id="d0e90-196">IPM.Activity</span></span>  <br/> |<span data-ttu-id="d0e90-197">日誌項目</span><span class="sxs-lookup"><span data-stu-id="d0e90-197">Journal entries</span></span>  <br/> |
    |<span data-ttu-id="d0e90-198">IPM。文件</span><span class="sxs-lookup"><span data-stu-id="d0e90-198">IPM.Document</span></span>  <br/> |<span data-ttu-id="d0e90-199">文件及檔案 （不會附加至電子郵件）</span><span class="sxs-lookup"><span data-stu-id="d0e90-199">Documents and files (not attached to an email message)</span></span>  <br/> |
    |<span data-ttu-id="d0e90-200">IPM。檔案</span><span class="sxs-lookup"><span data-stu-id="d0e90-200">IPM.File</span></span>  <br/> |<span data-ttu-id="d0e90-201">（與 IPM 相同。文件）</span><span class="sxs-lookup"><span data-stu-id="d0e90-201">(same as IPM.Document)</span></span>  <br/> |
    |<span data-ttu-id="d0e90-202">IPM。Note.IMC.Notification</span><span class="sxs-lookup"><span data-stu-id="d0e90-202">IPM.Note.IMC.Notification</span></span>  <br/> |<span data-ttu-id="d0e90-203">以 Internet Mail Connect，這是網際網路的 Exchange Server 閘道傳送報告</span><span class="sxs-lookup"><span data-stu-id="d0e90-203">Reports sent by Internet Mail Connect, which is the Exchange Server gateway to the Internet</span></span>  <br/> |
    |<span data-ttu-id="d0e90-204">IPM。Note.Microsoft.Fax</span><span class="sxs-lookup"><span data-stu-id="d0e90-204">IPM.Note.Microsoft.Fax</span></span>  <br/> |<span data-ttu-id="d0e90-205">傳真訊息</span><span class="sxs-lookup"><span data-stu-id="d0e90-205">Fax messages</span></span>  <br/> |
    |<span data-ttu-id="d0e90-206">IPM。Note.Rules.Oof.Template.Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0e90-206">IPM.Note.Rules.Oof.Template.Microsoft</span></span>  <br/> |<span data-ttu-id="d0e90-207">不在辦公室的自動回覆郵件</span><span class="sxs-lookup"><span data-stu-id="d0e90-207">Out-of-office auto-reply messages</span></span>  <br/> |
    |<span data-ttu-id="d0e90-208">IPM。Note.Rules.ReplyTemplate.Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0e90-208">IPM.Note.Rules.ReplyTemplate.Microsoft</span></span>  <br/> |<span data-ttu-id="d0e90-209">收件匣規則所傳送的回覆</span><span class="sxs-lookup"><span data-stu-id="d0e90-209">Replies sent by an inbox rule</span></span>  <br/> |
    |<span data-ttu-id="d0e90-210">IPM。OLE。類別</span><span class="sxs-lookup"><span data-stu-id="d0e90-210">IPM.OLE.Class</span></span>  <br/> |<span data-ttu-id="d0e90-211">週期性系列的例外狀況</span><span class="sxs-lookup"><span data-stu-id="d0e90-211">Exceptions for a recurring series</span></span>  <br/> |
    |<span data-ttu-id="d0e90-212">IPM。Recall.Report</span><span class="sxs-lookup"><span data-stu-id="d0e90-212">IPM.Recall.Report</span></span>  <br/> |<span data-ttu-id="d0e90-213">郵件回收報告</span><span class="sxs-lookup"><span data-stu-id="d0e90-213">Message recall reports</span></span>  <br/> |
    |<span data-ttu-id="d0e90-214">IPM。遠端</span><span class="sxs-lookup"><span data-stu-id="d0e90-214">IPM.Remote</span></span>  <br/> |<span data-ttu-id="d0e90-215">遠端郵件</span><span class="sxs-lookup"><span data-stu-id="d0e90-215">Remote mail messages</span></span>  <br/> |
    |<span data-ttu-id="d0e90-216">IPM。報表</span><span class="sxs-lookup"><span data-stu-id="d0e90-216">IPM.Report</span></span>  <br/> |<span data-ttu-id="d0e90-217">項目狀態報表</span><span class="sxs-lookup"><span data-stu-id="d0e90-217">Item status reports</span></span>  <br/> |
