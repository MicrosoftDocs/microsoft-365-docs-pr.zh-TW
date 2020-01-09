---
title: 將組織的 PST 檔案匯入至 Office 365 概觀
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: 適用於系統管理員：了解在安全性與合規性中心使用「匯入」服務來將電子郵件資料 (PST 檔案) 大量匯入至 Exchange Online 的使用者信箱。 本主題提供常見問題集，並說明 PST 匯入程序的運作方式。
ms.openlocfilehash: 4e58be4e90429c2d39bbcf4c5ef362e659764d63
ms.sourcegitcommit: cf7b0fd80ecfb7a216111a801269c5322794795e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "40995283"
---
# <a name="overview-of-importing-your-organizations-pst-files-to-office-365"></a><span data-ttu-id="cb527-104">將組織的 PST 檔案匯入至 Office 365 概觀</span><span class="sxs-lookup"><span data-stu-id="cb527-104">Overview of importing your organization's PST files to Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="cb527-105">本文適用於系統管理員。</span><span class="sxs-lookup"><span data-stu-id="cb527-105">This article is for administrators.</span></span> <span data-ttu-id="cb527-106">您是否正嘗試匯入 PST 檔案到自己的信箱？</span><span class="sxs-lookup"><span data-stu-id="cb527-106">Are you trying to import PST files to your own mailbox?</span></span> <span data-ttu-id="cb527-107">請參閱[從 Outlook .pst 檔案匯入電子郵件、連絡人和行事曆](https://go.microsoft.com/fwlink/p/?LinkID=785075)</span><span class="sxs-lookup"><span data-stu-id="cb527-107">See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)</span></span>

<span data-ttu-id="cb527-108">您可以使用安全性與合規性中心的「匯入」服務將 PST 檔案快速大量匯入到 Office 365 組織中的 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="cb527-108">You can use the Import service in the Security & Compliance Center to quickly bulk-import PST files to Exchange Online mailboxes in your Office 365 organization.</span></span> <span data-ttu-id="cb527-109">有兩種方法可將 PST 檔案匯入到 Office 365：</span><span class="sxs-lookup"><span data-stu-id="cb527-109">There are two ways you can import PST files to Office 365:</span></span>

- <span data-ttu-id="cb527-110">**網路上傳**![雲端上傳](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) - 透過網路將 PST 檔案上傳到 Microsoft Cloud 的暫時 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="cb527-110">**Network upload** ![Cloud upload](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) - Upload the PST files over the network to a temporary Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="cb527-111">然後使用 Office 365 匯入服務將 PST 資料匯入 Office 365 組織中的信箱。</span><span class="sxs-lookup"><span data-stu-id="cb527-111">Then you use the Office 365 Import service to import the PST data to mailboxes in your Office 365 organization.</span></span> 

- <span data-ttu-id="cb527-112">**磁碟機寄送**![硬碟](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) - 將 PST 檔案複製到 BitLocker 加密硬碟，並實際寄送磁碟機給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="cb527-112">**Drive shipping** ![Hard disk](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) - Copy the PST files to a BitLocker-encrypted hard drive and then physically ship the drive to Microsoft.</span></span> <span data-ttu-id="cb527-113">當 Microsoft 收到硬碟時，資料中心人員會將資料上傳到 Microsoft Cloud 的暫時 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="cb527-113">When Microsoft receives the hard drive, data center personnel upload the data to a temporary Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="cb527-114">然後使用 Office 365 匯入服務將資料匯入 Office 365 組織中的信箱。</span><span class="sxs-lookup"><span data-stu-id="cb527-114">Then you use the Office 365 Import service to import the data to mailboxes in your Office 365 organization.</span></span>

## <a name="step-by-step-instructions"></a><span data-ttu-id="cb527-115">逐步指示</span><span class="sxs-lookup"><span data-stu-id="cb527-115">Step-by-step instructions</span></span>
  
<span data-ttu-id="cb527-116">請參閱下列其中一個主題以取得將組織 PST 檔案大量匯入至 Office 365 的詳細逐步指示。</span><span class="sxs-lookup"><span data-stu-id="cb527-116">See one of the following topics for detailed, step-by-step instructions for bulk-importing your organization's PST files to Office 365.</span></span> 

- [<span data-ttu-id="cb527-117">使用網路上傳將 PST 檔案匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="cb527-117">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)

- [<span data-ttu-id="cb527-118">使用磁碟機寄送將 PST 檔案匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="cb527-118">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a><span data-ttu-id="cb527-119">匯入 PST 檔案的運作方式</span><span class="sxs-lookup"><span data-stu-id="cb527-119">How importing PST files works</span></span>

<span data-ttu-id="cb527-120">以下是完整 PST 匯入程序的圖例和說明。</span><span class="sxs-lookup"><span data-stu-id="cb527-120">Here's an illustration and description of the complete PST import process.</span></span> <span data-ttu-id="cb527-121">圖例顯示主要工作流程，並醒目提示網路上傳和磁碟機寄送方法之間的差異。</span><span class="sxs-lookup"><span data-stu-id="cb527-121">The illustration shows the primary workflow and highlights the differences between the network upload and drive shipping methods.</span></span>
  
![PST 匯入程序的工作流程](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. <span data-ttu-id="cb527-123">**將 PST 匯入工具和金鑰下載到私人 Azure 儲存體位置** - 第一個步驟是下載用於上傳 PST 檔案的工具和存取金鑰，或將它們複製到硬碟。</span><span class="sxs-lookup"><span data-stu-id="cb527-123">**Download the PST import tools and key to private Azure Storage location** - The first step is to download the tool and access key used to upload the PST files or copy them to a hard drive.</span></span> <span data-ttu-id="cb527-124">您可以從安全性與合規性中心的**匯入**頁面取得這些工具和便捷鍵。</span><span class="sxs-lookup"><span data-stu-id="cb527-124">You obtain these from the **Import** page in the Security & Compliance Center.</span></span> <span data-ttu-id="cb527-125">此金鑰提供您 (或在磁碟機寄送時提供給 Microsoft 資料中心人員) 將 PST 檔案上傳到私人且安全的 Azure 儲存體位置的必要權限。</span><span class="sxs-lookup"><span data-stu-id="cb527-125">The key provides you (or Microsoft data center personnel in the case of drive shipping) with the necessary permissions to upload PST files to a private and secure Azure Storage location.</span></span> <span data-ttu-id="cb527-126">此便捷鍵專屬於貴組織，並在 PST 檔案上傳到 Microsoft Cloud 後，協助防止未經授權存取 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="cb527-126">This access key is unique to your organization and helps prevent unauthorized access to your PST files after they're uploaded to the Microsoft cloud.</span></span> <span data-ttu-id="cb527-127">將 PST 檔案匯入至 Office 365 不會要求貴組織具有不同的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="cb527-127">Importing PST files to Office 365 doesn't require your organization to have a separate Azure subscription.</span></span> 
    
2. <span data-ttu-id="cb527-128">**上傳或複製的 PST 檔案** - 下一個步驟取決於您使用網路上傳或磁碟機寄送來匯入 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="cb527-128">**Upload or copy the PST files** - The next step depends on whether you're using network upload or drive shipping to import PST files.</span></span> <span data-ttu-id="cb527-129">在這兩種情況下，您會使用上一個步驟中取得的工具和安全儲存體金鑰。</span><span class="sxs-lookup"><span data-stu-id="cb527-129">In both cases, you'll use the tool and secure storage key that you obtained in the previous step.</span></span>
    
    - <span data-ttu-id="cb527-130">**網路上傳：** AzCopy.exe 工具 (於步驟 1 中下載) 用於上傳 PST 檔案並將其儲存在 Microsoft Cloud 中的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="cb527-130">**Network upload**The AzCopy.exe tool (downloaded in step 1) is used to upload and store your PST files in an Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="cb527-131">上傳 PST 檔案的 Azure 儲存體位置與 Office 365 組織所在的地區性 Microsoft 資料中心相同。</span><span class="sxs-lookup"><span data-stu-id="cb527-131">The Azure Storage location that you upload your PST files to resides in the same regional Microsoft datacenter where your Office 365 organization is located.</span></span>
    
      <span data-ttu-id="cb527-132">若要上傳，您想要匯入 Office 365 的 PST 檔案必須位於組織中的檔案共用或檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="cb527-132">To upload them, the PST files that you want to import to Office 365 have to be located in a file share or file server in your organization.</span></span>
    
    - <span data-ttu-id="cb527-133">**磁碟機寄送：** WAImportExport.exe 工具 (於步驟 1 下載) 是用於將 PST 檔案複製到硬碟。</span><span class="sxs-lookup"><span data-stu-id="cb527-133">**Drive shipping**The WAImportExport.exe tool (downloaded in step 1) is used to copy your PST files to the hard drive.</span></span> <span data-ttu-id="cb527-134">此工具會以 BitLocker 加密硬碟，然後將 PST 複製到硬碟。</span><span class="sxs-lookup"><span data-stu-id="cb527-134">This tool encrypts the hard drive with BitLocker and then copies the PSTs to the hard drive.</span></span> <span data-ttu-id="cb527-135">如同網路上傳，您想要複製到硬碟的 PST 檔案必須位於組織中的檔案共用或檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="cb527-135">Like network upload, the PST files that you want to copy to the hard drive have to be located in a file share or file server in your organization.</span></span>
    
3. <span data-ttu-id="cb527-136">**建立 PST 匯入對應檔案** - PST 檔案上傳到 Azure 儲存體位置或複製到硬碟後，下一個步驟是建立逗點分隔值 (CSV) 檔案，以指定要匯入 PST 檔案的使用者信箱 (PST 檔案可匯入使用者的主要信箱或封存信箱)。</span><span class="sxs-lookup"><span data-stu-id="cb527-136">**Create a PST import mapping file** - After the PST files have been uploaded to the Azure Storage location or copied to a hard drive, the next step is to create a comma-separated value (CSV) file that specifies which user mailboxes the PST files will be imported to (and a PST file can be imported to a user's primary mailbox or their archive mailbox).</span></span> <span data-ttu-id="cb527-137">Office 365 匯入服務會使用此資訊匯入 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="cb527-137">The Office 365 Import service will use the information to import the PST files.</span></span> 
    
4. <span data-ttu-id="cb527-138">**建立 PST 匯入工作** - 下一個步驟是在安全性與合規性中心的 [匯入]\*\*\*\* 頁面建立 PST 匯入工作，然後提交上一個步驟中建立的 PST 匯入對應檔案。</span><span class="sxs-lookup"><span data-stu-id="cb527-138">**Create a PST import job** - The next step is to create a PST import job on the **Import PST files** page in the Security & Compliance Center and submit the PST import mapping file created in the previous step.</span></span> <span data-ttu-id="cb527-139">若為網路上傳 (因為 PST 檔案已上傳到 Azure)，Office 365 會分析 PST 檔案中的資料，然後讓您設定篩選條件，以控制哪些資料會實際匯入 PST 匯入對應檔案中指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="cb527-139">For network upload (because the PST files have been uploaded to Azure) Office 365 analyzes the data in the PST files and then gives you an opportunity to set filters that control what data actually gets imported to the mailboxes specified in the PST import mapping file.</span></span> 
    
    <span data-ttu-id="cb527-140">若為磁碟機寄送，此時程序中會發生一些其他事項。</span><span class="sxs-lookup"><span data-stu-id="cb527-140">For drive shipping, a few additional things happen at this point in the process.</span></span>
    
    - <span data-ttu-id="cb527-141">您實際將硬碟寄送給 Microsoft 資料中心 (建立匯入工作時，會顯示 Microsoft 資料中心的寄送地址)。</span><span class="sxs-lookup"><span data-stu-id="cb527-141">You physically ship the hard drive to a Microsoft data center (the shipping address for the Microsoft data center is displayed when the import job is created).</span></span>
    
    - <span data-ttu-id="cb527-142">Microsoft 收到硬碟之後，資料中心的人員會為貴組織將硬碟上的 PST 檔案上傳到 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="cb527-142">When Microsoft receives the hard drive, data center personnel will upload the PST files on the hard drive to the Azure Storage location for your organization.</span></span> <span data-ttu-id="cb527-143">如先前所解釋，您的 PST 檔案會上傳至 Office 365 組織所在的相同地區性 Microsoft 資料中心的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="cb527-143">As previously explained, your PST files are uploaded to a Azure Storage location that resides in the same regional Microsoft datacenter where your Office 365 organization is located.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="cb527-144">Microsoft 收到硬碟後，會在 7 到 10 個工作天內將硬碟上的 PST 檔案上傳至 Azure。</span><span class="sxs-lookup"><span data-stu-id="cb527-144">The PST files on the hard drive are uploaded to Azure within 7 to 10 business days after Microsoft receives the hard drive.</span></span>

      <span data-ttu-id="cb527-145">如同網路上傳程序，Office 365 會分析 PST 檔案中的資料，然後讓您設定篩選條件，以控制哪些資料會實際匯入 PST 匯入對應檔案中指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="cb527-145">Like the network upload process, Office 365 then analyzes the data in the PST files and gives you an opportunity to set filters that control what data actually gets imported to the mailboxes specified in the PST import mapping file.</span></span>
    
    - <span data-ttu-id="cb527-146">Microsoft 會將硬碟寄回給您。</span><span class="sxs-lookup"><span data-stu-id="cb527-146">Microsoft ships the hard drive back to you.</span></span>
    
5. <span data-ttu-id="cb527-147">**篩選將匯入到信箱的 PST 資料** - 建立匯入工作後 (且磁碟機寄送工作的 PST 檔案上傳到 Azure 儲存體位置後)，Office 365 會透過找出項目的留存時間和包括在 PST 檔案中的不同訊息類型，(以安全的方式) 分析 PST 檔案中的資料。</span><span class="sxs-lookup"><span data-stu-id="cb527-147">**Filter the PST data that will be imported to mailboxes** - After the import job is created (and after the PST files from a drive shipping job are uploaded to the Azure Storage location) Office 365 analyzes the data in the PST files (safely and securely) by identifying the age of the items and the different message types included in the PST files.</span></span> <span data-ttu-id="cb527-148">分析完成且準備好匯入資料後，您可以選擇匯入 PST 檔案中所包含的所有資料，或設定控制匯入資料的篩選條件來調整要匯入的資料。</span><span class="sxs-lookup"><span data-stu-id="cb527-148">When the analysis is completed and the data is ready to import, you have the option to import all the data contained in the PST files or you can trim the data that's imported by setting filters that control what data gets imported.</span></span> 
    
6. <span data-ttu-id="cb527-149">**開始 PST 匯入工作** - 開始匯入工作後，Office 365 會使用 PST 匯入對應檔案中的資訊，將 PST 檔案從 Azure 儲存體位置匯入至使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="cb527-149">**Start the PST import job** - After the import job is started, Office 365 uses the information in the PST import mapping file to import the PSTs files from the he Azure Storage location to user mailboxes.</span></span> <span data-ttu-id="cb527-150">匯入工作的狀態資訊 (包括匯入的每個 PST 檔案的相關資訊) 會顯示在安全性與合規性中心的 [匯入 PST 檔案]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="cb527-150">Status information about the import job (including information about each PST file being imported) is displayed on the **Import PST files** page in the Security & Compliance Center.</span></span> <span data-ttu-id="cb527-151">匯入工作完成時，工作的狀態會設為**完成**。</span><span class="sxs-lookup"><span data-stu-id="cb527-151">When the import job is finished, the status for the job is set to **Complete**.</span></span>
  
## <a name="why-import-email-data-to-office-365"></a><span data-ttu-id="cb527-152">為什麼要將電子郵件資料匯入 Office 365？</span><span class="sxs-lookup"><span data-stu-id="cb527-152">Why import email data to Office 365?</span></span>

- <span data-ttu-id="cb527-153">這是將組織的封存訊息資料匯入 Office 365 的好方法。</span><span class="sxs-lookup"><span data-stu-id="cb527-153">It's a good way to import your organization's archival messaging data to Office 365.</span></span>
    
- <span data-ttu-id="cb527-154">您可以使用[智慧型匯入](filter-data-when-importing-pst-files.md)功能來篩選實際匯入目標信箱的 PST 檔案項目。</span><span class="sxs-lookup"><span data-stu-id="cb527-154">You can use the [Intelligent Import](filter-data-when-importing-pst-files.md) feature to filter the items in PST files that actually get imported to the target mailboxes.</span></span> <span data-ttu-id="cb527-155">這能讓您藉由設定控制匯入資料的篩選條件來調整要匯入的資料。</span><span class="sxs-lookup"><span data-stu-id="cb527-155">This lets you trim the data that's imported by setting filters that control what data gets imported.</span></span> 
    
- <span data-ttu-id="cb527-156">將電子郵件資料匯入至 Office 365 可讓您透過下列方式協助解決組織的法務遵循需求︰</span><span class="sxs-lookup"><span data-stu-id="cb527-156">Importing email data to Office 365 helps address compliance needs of your organization by letting you:</span></span>
    
  - <span data-ttu-id="cb527-157">啟用[封存信箱](enable-archive-mailboxes.md)和[無限制封存](unlimited-archiving.md)以提供使用者額外的信箱儲存空間。</span><span class="sxs-lookup"><span data-stu-id="cb527-157">Enable [archive mailboxes](enable-archive-mailboxes.md) and [unlimited archiving](unlimited-archiving.md) to give users additional mailbox storage space.</span></span> 
    
  - <span data-ttu-id="cb527-158">將信箱置於[訴訟暫止](https://go.microsoft.com/fwlink/?linkid=841243)來保留內容。</span><span class="sxs-lookup"><span data-stu-id="cb527-158">Place mailboxes on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=841243) to retain content.</span></span> 
    
  - <span data-ttu-id="cb527-159">使用[內容搜尋工具](content-search.md)搜尋信箱內容。</span><span class="sxs-lookup"><span data-stu-id="cb527-159">Use the [Content Search tool](content-search.md) to search for mailbox content.</span></span> 
    
  - <span data-ttu-id="cb527-160">使用[電子文件探索案例](ediscovery-cases.md)來管理貴組織的法律調查</span><span class="sxs-lookup"><span data-stu-id="cb527-160">Use [eDiscovery cases](ediscovery-cases.md) to manage your organization's legal investigations</span></span> 
    
  - <span data-ttu-id="cb527-161">使用安全性與合規性中心的[保留原則](retention-policies.md)來控制信箱內容的保留時間，並在保留期間結束後刪除內容。</span><span class="sxs-lookup"><span data-stu-id="cb527-161">Use [retention policies](retention-policies.md) in the Security & Compliance Center to control how long mailbox content is retained, and then delete content after the retention period expires.</span></span> 

  - <span data-ttu-id="cb527-162">使用[通訊合規性原則](communication-compliance.md)檢查郵件，以確認郵件符合郵件標準的規範，並新增分類類型。</span><span class="sxs-lookup"><span data-stu-id="cb527-162">Use [Communication compliance policies](communication-compliance.md) to examine messages to make sure they are compliant with message standards and add a classification type.</span></span>
    
- <span data-ttu-id="cb527-163">將資料匯入 Office 365 可協助防止資料遺失。</span><span class="sxs-lookup"><span data-stu-id="cb527-163">Importing data to Office 365 helps protect against data loss.</span></span> <span data-ttu-id="cb527-164">匯入 Office 365 的電子郵件資料會繼承 Exchange Online 的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="cb527-164">Email data that's imported to Office 365 inherits the high availability features of Exchange Online.</span></span>
    
- <span data-ttu-id="cb527-165">Office 365 的電子郵件資料儲存在雲端上，所以使用者從各種裝置都能取得資料。</span><span class="sxs-lookup"><span data-stu-id="cb527-165">Email data in Office 365 is available to users from all devices because it's stored in the cloud.</span></span>
    
## <a name="importing-sharepoint-data-to-office-365"></a><span data-ttu-id="cb527-166">將 SharePoint 資料匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="cb527-166">Importing SharePoint data to Office 365</span></span>

<span data-ttu-id="cb527-167">您也可以將檔案和文件匯入 Office 365 組織中的 SharePoint 網站和 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="cb527-167">You can also import files and documents to SharePoint sites and OneDrive accounts in your Office 365 organization.</span></span> <span data-ttu-id="cb527-168">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="cb527-168">For more information, see the following articles:</span></span>

- [<span data-ttu-id="cb527-169">移轉至 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb527-169">Migrate to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

- [<span data-ttu-id="cb527-170">SharePoint 移轉工具簡介</span><span class="sxs-lookup"><span data-stu-id="cb527-170">Introducing the SharePoint Migration Tool</span></span>](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [<span data-ttu-id="cb527-171">使用 PowerShell 移轉至 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb527-171">Migrate to SharePoint Online using PowerShell</span></span>](https://docs.microsoft.com/sharepointmigration/overview-spmt-ps-cmdlets)

- [<span data-ttu-id="cb527-172">使用 Azure 資料箱將檔案共用內容移轉至 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb527-172">Migrate your file share content to SharePoint Online using the Azure Data Box</span></span>](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a><span data-ttu-id="cb527-173">關於將 PST 檔案匯入至 Office 365 的常見問題</span><span class="sxs-lookup"><span data-stu-id="cb527-173">Frequently asked questions about importing PST files to Office 365</span></span>
  
<span data-ttu-id="cb527-174">以下是一些關於使用 Office 365 匯入服務將 PST 檔案大量匯入 Office 365 信箱的常見問題解答。</span><span class="sxs-lookup"><span data-stu-id="cb527-174">Here are some frequently asked questions about using the Office 365 Import service to bulk-import PST files to Office 365 mailboxes.</span></span> 
  
- [<span data-ttu-id="cb527-175">使用網路上傳來匯入 PST 檔案</span><span class="sxs-lookup"><span data-stu-id="cb527-175">Using network upload to import PST files</span></span>](#using-network-upload-to-import-pst-files)
  
- [<span data-ttu-id="cb527-176">使用磁碟機寄送來匯入 PST 檔案</span><span class="sxs-lookup"><span data-stu-id="cb527-176">Using drive shipping to import PST files</span></span>](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="cb527-177">使用網路上傳來匯入 PST 檔案</span><span class="sxs-lookup"><span data-stu-id="cb527-177">Using network upload to import PST files</span></span>

 <span data-ttu-id="cb527-178">**必須具備哪些權限才能在 Office365 匯入服務中建立匯入工作？**</span><span class="sxs-lookup"><span data-stu-id="cb527-178">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="cb527-179">您必須在 Exchange Online 中獲派信箱匯入匯出角色，才能將 PST 檔案匯入 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="cb527-179">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes.</span></span> <span data-ttu-id="cb527-180">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="cb527-180">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="cb527-181">You can add the Mailbox Import Export role to the Organization Management role group.</span><span class="sxs-lookup"><span data-stu-id="cb527-181">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="cb527-182">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span><span class="sxs-lookup"><span data-stu-id="cb527-182">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="cb527-183">如需詳細資訊，請參閱[管理 Exchange Online 中的角色](https://go.microsoft.com/fwlink/p/?LinkId=730688)之＜新增角色至角色群組＞或＜建立角色群組＞一節。</span><span class="sxs-lookup"><span data-stu-id="cb527-183">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="cb527-184">此外，若要在安全性與合規性中心建立匯入工作，必須符合以下其中一個條件：</span><span class="sxs-lookup"><span data-stu-id="cb527-184">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="cb527-185">您必須在 Exchange Online 中獲派郵件收件者角色。</span><span class="sxs-lookup"><span data-stu-id="cb527-185">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="cb527-186">根據預設，這個角色會指派給組織管理及收件者管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="cb527-186">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>

    <span data-ttu-id="cb527-187">或</span><span class="sxs-lookup"><span data-stu-id="cb527-187">Or</span></span>
    
- <span data-ttu-id="cb527-188">您必須是您 Office365 組織中的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="cb527-188">You have to be a global administrator in your Office 365 organization.</span></span>

> [!TIP]
> <span data-ttu-id="cb527-189">建議您在 Exchange Online 中建立新的角色群組，專門用來將 PST 檔案匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="cb527-189">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="cb527-190">若要獲得匯入 PST 檔案所需的最低權限等級，請將信箱匯入匯出及郵件收件者角色指派到新的角色群組，然後新增成員。</span><span class="sxs-lookup"><span data-stu-id="cb527-190">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="cb527-191">**哪些地區提供網路上傳服務？**</span><span class="sxs-lookup"><span data-stu-id="cb527-191">**Where is network upload available?**</span></span>
  
<span data-ttu-id="cb527-p122">網路上傳的服務範圍目前包括美國、加拿大、巴西、英國、歐洲、印度、東亞、東南亞、日本、大韓民國和澳洲。我們會盡快在更多地區提供網路上傳服務。</span><span class="sxs-lookup"><span data-stu-id="cb527-p122">Network upload is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Network upload will be available in more regions soon.</span></span>
  
 <span data-ttu-id="cb527-194">**使用網路上傳匯入 PST 檔案的費用為何？**</span><span class="sxs-lookup"><span data-stu-id="cb527-194">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="cb527-195">Using network upload to import PST files is free.</span><span class="sxs-lookup"><span data-stu-id="cb527-195">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="cb527-196">這也表示 PST 檔案從 Azure 儲存體區域刪除之後，Microsoft 365 系統管理中心內完整匯入工作的檔案清單中就不會顯示這些檔案。</span><span class="sxs-lookup"><span data-stu-id="cb527-196">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Microsoft 365 admin center.</span></span> <span data-ttu-id="cb527-197">即使匯入工作仍然列在 **[將資料匯入 Office 365]** 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。</span><span class="sxs-lookup"><span data-stu-id="cb527-197">Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span>
  
 <span data-ttu-id="cb527-198">**哪些版本的 PST 檔案格式支援匯入 Office 365？**</span><span class="sxs-lookup"><span data-stu-id="cb527-198">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="cb527-199">有兩個版本的 PST 檔案格式支援此作業：ANSI 和 Unicode。</span><span class="sxs-lookup"><span data-stu-id="cb527-199">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="cb527-200">我們建議您使用 Unicode PST 檔案格式來匯入檔案。</span><span class="sxs-lookup"><span data-stu-id="cb527-200">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="cb527-201">不過，使用 ANSI PST 檔案格式的檔案 (例如，使用雙位元組字元集 (DBCS) 語言的檔案) 也可以匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="cb527-201">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365.</span></span> <span data-ttu-id="cb527-202">如需有關匯入 ANSI PST 檔案的資訊，請參閱[使用網路上傳將 PST 檔案匯入 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074) 中的步驟 4。</span><span class="sxs-lookup"><span data-stu-id="cb527-202">For more information about importing ANSI PST files, see Step 4 in [Use network upload to import PST files to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074).</span></span>
  
<span data-ttu-id="cb527-203">此外，Outlook 2007 和更新版本的 PST 檔案也可以匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="cb527-203">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="cb527-204">**將我的 PST 檔案上傳到 Azure 儲存體區域之後，這些檔案會在 Azure 中保留多久的時間才會遭到刪除？**</span><span class="sxs-lookup"><span data-stu-id="cb527-204">**After I upload my PST files to the Azure Storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="cb527-205">使用網路上傳方法來匯入 PST 檔案會將這些檔案上傳到名為 **ingestiondata** 的 Azure Blob 容器。</span><span class="sxs-lookup"><span data-stu-id="cb527-205">When you use the network upload method to import PST files, you upload them to an Azure blob container named **ingestiondata**.</span></span> <span data-ttu-id="cb527-206">如果安全性與合規性中心的 [匯入 PST 檔案]\*\*\*\* 頁面目前沒有進行中的匯入工作，則 Azure 中 **ingestiondata** 容器內的所有 PST 檔案都會在最近的匯入工作於安全性與合規性中心建立完成的後 30 天刪除。</span><span class="sxs-lookup"><span data-stu-id="cb527-206">If there are no import jobs in progress on the **Import PST files** page in the Security & Compliance Center), then all PST files in the **ingestiondata** container in Azure are deleted 30 days after the most recent import job was created in the Security & Compliance Center.</span></span> <span data-ttu-id="cb527-207">這也表示您必須在 PST 檔案上傳到 Azure 的 30 天內，在安全性與合規性中心建立新的匯入工作 (如網路上傳指示中的步驟 5 所述)。</span><span class="sxs-lookup"><span data-stu-id="cb527-207">That also means you have to create a new import job in the Security & Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span>
  
<span data-ttu-id="cb527-208">這也表示 PST 檔案從 Azure 儲存體區域刪除之後，安全性與合規性中心內完整匯入工作的檔案清單中就不會顯示這些檔案。</span><span class="sxs-lookup"><span data-stu-id="cb527-208">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="cb527-209">即使匯入工作仍然列在安全性與合規性中心的 [匯入 PST 檔案]\*\*\*\* 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。</span><span class="sxs-lookup"><span data-stu-id="cb527-209">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span>
  
 <span data-ttu-id="cb527-210">**需要多久的時間才能將 PST 檔案匯入信箱？**</span><span class="sxs-lookup"><span data-stu-id="cb527-210">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="cb527-211">這取決於您的網路容量，但將每 TB 的資料上傳到貴組織的 Azure 儲存體區域通常需要幾個小時的時間。</span><span class="sxs-lookup"><span data-stu-id="cb527-211">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure Storage area for your organization.</span></span> <span data-ttu-id="cb527-212">將 PST 檔案複製到 Azure 儲存體區域之後，系統會以每天至少 24 GB 的速率將 PST 檔案匯入到 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="cb527-212">After the PST files are copied to the Azure Storage area, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="cb527-213">如果這樣的速率不符您的需求，您可以考慮其他將電子郵件資料移轉到 Office 365 的方法。</span><span class="sxs-lookup"><span data-stu-id="cb527-213">If this rate doesn't meet your needs, you might consider other methods to get email data into Office 365.</span></span> <span data-ttu-id="cb527-214">如需詳細資訊，請參閱＜[將多個電子郵件帳戶移轉到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)＞。</span><span class="sxs-lookup"><span data-stu-id="cb527-214">For more information, see [Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
<span data-ttu-id="cb527-215">如果不同的 PST 檔案需匯入到不同的目標信箱，匯入程序會同時進行；換句話說，系統會同時匯入每個 PST/信箱組合。</span><span class="sxs-lookup"><span data-stu-id="cb527-215">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="cb527-216">同樣地，如果多個 PST 檔案匯入到相同的信箱，則會同時匯入。</span><span class="sxs-lookup"><span data-stu-id="cb527-216">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="cb527-217">**匯入 PST 檔案時，是否有郵件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="cb527-217">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="cb527-218">是。</span><span class="sxs-lookup"><span data-stu-id="cb527-218">Yes.</span></span> <span data-ttu-id="cb527-219">如果 PST 檔案包含大於 150 MB 的信箱項目，該項目會在匯入程序執行時略過。</span><span class="sxs-lookup"><span data-stu-id="cb527-219">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="cb527-220">**PST 檔案匯入 Office 365 信箱時是否會保留訊息內容 (例如訊息的傳送或接收時間、收件者清單等等)？**</span><span class="sxs-lookup"><span data-stu-id="cb527-220">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="cb527-221">是。</span><span class="sxs-lookup"><span data-stu-id="cb527-221">Yes.</span></span> <span data-ttu-id="cb527-222">匯入程序不會變更任何原始的訊息中繼資料。</span><span class="sxs-lookup"><span data-stu-id="cb527-222">The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="cb527-223">**針對我要匯入至信箱的 PST 檔案，其資料夾階層數是否有上限？**</span><span class="sxs-lookup"><span data-stu-id="cb527-223">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="cb527-p131">是。您無法匯入具有 300 或更多巢狀資料夾階層的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="cb527-p131">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="cb527-226">**我是否可以使用網路上傳將 PST 檔案匯入 Office 365 中的非作用中的信箱？**</span><span class="sxs-lookup"><span data-stu-id="cb527-226">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="cb527-227">是，我們現已推出這項功能。</span><span class="sxs-lookup"><span data-stu-id="cb527-227">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="cb527-228">**我是否可以使用網路上傳將 PST 檔案匯入 Exchange 混合式部署中的線上封存信箱？**</span><span class="sxs-lookup"><span data-stu-id="cb527-228">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="cb527-229">是，我們現已推出這項功能。</span><span class="sxs-lookup"><span data-stu-id="cb527-229">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="cb527-230">**我是否可以使用網路上傳方式將 PST 檔匯入 Exchange Online 的公用資料夾？**</span><span class="sxs-lookup"><span data-stu-id="cb527-230">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="cb527-231">否，您無法將 PST 檔案匯入公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="cb527-231">No, you can't import PST files to public folders.</span></span>
  
### <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="cb527-232">使用磁碟機寄送來匯入 PST 檔案</span><span class="sxs-lookup"><span data-stu-id="cb527-232">Using drive shipping to import PST files</span></span>

 <span data-ttu-id="cb527-233">**必須具備哪些權限才能在 Office365 匯入服務中建立匯入工作？**</span><span class="sxs-lookup"><span data-stu-id="cb527-233">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="cb527-234">您必須獲派信箱匯入匯出角色才能將 PST 檔案匯入 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="cb527-234">You have to be assigned the Mailbox Import Export role to import PST files to Office 365 mailboxes.</span></span> <span data-ttu-id="cb527-235">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="cb527-235">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="cb527-236">You can add the Mailbox Import Export role to the Organization Management role group.</span><span class="sxs-lookup"><span data-stu-id="cb527-236">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="cb527-237">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span><span class="sxs-lookup"><span data-stu-id="cb527-237">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="cb527-238">如需詳細資訊，請參閱[管理 Exchange Online 中的角色](https://go.microsoft.com/fwlink/p/?LinkId=730688)之＜新增角色至角色群組＞或＜建立角色群組＞一節。</span><span class="sxs-lookup"><span data-stu-id="cb527-238">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="cb527-239">此外，若要在安全性與合規性中心建立匯入工作，必須符合以下其中一個條件：</span><span class="sxs-lookup"><span data-stu-id="cb527-239">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="cb527-240">您必須在 Exchange Online 中獲派郵件收件者角色。</span><span class="sxs-lookup"><span data-stu-id="cb527-240">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="cb527-241">根據預設，這個角色會指派給組織管理及收件者管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="cb527-241">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="cb527-242">或</span><span class="sxs-lookup"><span data-stu-id="cb527-242">Or</span></span>
    
- <span data-ttu-id="cb527-243">您必須是您 Office365 組織中的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="cb527-243">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="cb527-244">建議您在 Exchange Online 中建立新的角色群組，專門用來將 PST 檔案匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="cb527-244">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="cb527-245">若要獲得匯入 PST 檔案所需的最低權限等級，請將信箱匯入匯出及郵件收件者角色指派到新的角色群組，然後新增成員。</span><span class="sxs-lookup"><span data-stu-id="cb527-245">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="cb527-246">**哪些地區提供磁碟機寄送服務？**</span><span class="sxs-lookup"><span data-stu-id="cb527-246">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="cb527-247">磁碟機寄送的服務範圍目前包括美國、加拿大、巴西、英國、歐洲、印度、東亞、東南亞、日本、大韓民國和澳洲。</span><span class="sxs-lookup"><span data-stu-id="cb527-247">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia.</span></span> <span data-ttu-id="cb527-248">我們會盡快在更多地區提供磁碟機寄送服務。</span><span class="sxs-lookup"><span data-stu-id="cb527-248">Drive shipping will be available in more regions soon.</span></span>
  
 <span data-ttu-id="cb527-249">**有哪些商業授權合約支援磁碟機寄送？**</span><span class="sxs-lookup"><span data-stu-id="cb527-249">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="cb527-250">Microsoft Enterprise Agreement (EA) 提供將 PST 檔案匯入 Office 365 的磁碟機寄送服務。</span><span class="sxs-lookup"><span data-stu-id="cb527-250">Drive shipping to import PST files to Office 365 is available through a Microsoft Enterprise Agreement (EA).</span></span> <span data-ttu-id="cb527-251">Microsoft Products and Services Agreement (MPSA) 則沒有提供磁碟機寄送。</span><span class="sxs-lookup"><span data-stu-id="cb527-251">Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="cb527-252">**使用磁碟機寄送將 PST 檔案匯入 Office 365 的費用為何？**</span><span class="sxs-lookup"><span data-stu-id="cb527-252">**What is the pricing for using drive shipping to import PST files to Office 365?**</span></span>
  
<span data-ttu-id="cb527-253">使用磁碟機寄送將 PST 檔案匯入 Office 365 信箱的費用為每 GB 的資料 $2 美元。</span><span class="sxs-lookup"><span data-stu-id="cb527-253">The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data.</span></span> <span data-ttu-id="cb527-254">例如，假設您寄送的硬碟含有 1,000 GB (即 1 TB) 的 PST 檔案，則費用為 $2,000 美元。</span><span class="sxs-lookup"><span data-stu-id="cb527-254">For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD.</span></span> <span data-ttu-id="cb527-255">您可以與夥伴合作來支付匯入費用。</span><span class="sxs-lookup"><span data-stu-id="cb527-255">You can work with a partner to pay the import fee.</span></span> <span data-ttu-id="cb527-256">如需有關尋找合作夥伴的資訊，請參閱[尋找您的 Office 365 合作夥伴或轉售商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。</span><span class="sxs-lookup"><span data-stu-id="cb527-256">For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="cb527-257">**哪些類型的硬碟支援磁碟機寄送？**</span><span class="sxs-lookup"><span data-stu-id="cb527-257">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="cb527-258">Office 365 匯入服務只支援使用 2.5 吋固態硬碟 (SSD)，或是 2.5 吋或 3.5 吋 SATA II/III 內接式硬碟。</span><span class="sxs-lookup"><span data-stu-id="cb527-258">Only 2.5 inch solid-state drives (SSDs) or 2.5 inch or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service.</span></span> <span data-ttu-id="cb527-259">您可以使用最多 10 TB 的硬碟。</span><span class="sxs-lookup"><span data-stu-id="cb527-259">You can use hard drives up to 10 TB.</span></span> <span data-ttu-id="cb527-260">匯入作業時，只會處理硬碟上的第一個資料磁碟區。</span><span class="sxs-lookup"><span data-stu-id="cb527-260">For import jobs, only the first data volume on the hard drive will be processed.</span></span> <span data-ttu-id="cb527-261">資料磁碟區必須為 NTFS 格式。</span><span class="sxs-lookup"><span data-stu-id="cb527-261">The data volume must be formatted with NTFS.</span></span> <span data-ttu-id="cb527-262">若要將資料複製到硬碟，您可以直接使用 2.5 吋 SSD 或是 2.5 吋或 3.5 吋 SATA II/III 連接器進行連接，或者使用外接式 2.5 吋 SSD 或是 2.5 吋或 3.5 吋 SATA II/III USB 轉接頭進行外接。</span><span class="sxs-lookup"><span data-stu-id="cb527-262">When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 inch or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 inch or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cb527-263">Office 365 匯入服務不支援隨附內建 USB 轉接頭的外接式硬碟。</span><span class="sxs-lookup"><span data-stu-id="cb527-263">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service.</span></span> <span data-ttu-id="cb527-264">此外，位於外部硬碟外殼內的碟無法使用。</span><span class="sxs-lookup"><span data-stu-id="cb527-264">Additionally, the disk inside the casing of an external hard drive can't be used.</span></span> <span data-ttu-id="cb527-265">請不要使用外接式硬碟。</span><span class="sxs-lookup"><span data-stu-id="cb527-265">Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="cb527-266">**可以寄送幾個硬碟來進行單一匯入工作？**</span><span class="sxs-lookup"><span data-stu-id="cb527-266">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="cb527-267">最多可以寄送 10 個硬碟來進行單一匯入工作。</span><span class="sxs-lookup"><span data-stu-id="cb527-267">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="cb527-268">**寄送硬碟之後，需要多久的時間才會送達 Microsoft 資料中心？**</span><span class="sxs-lookup"><span data-stu-id="cb527-268">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="cb527-p140">這取決於幾個要素，例如您與 Microsoft 資料中心之間的距離，以及您使用什麼類型的運送選項來寄送硬碟 (例如，隔天送達、兩日送達或陸地運送)。大多數貨運公司提供追蹤號碼，讓您可以追蹤運送狀態。</span><span class="sxs-lookup"><span data-stu-id="cb527-p140">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="cb527-271">**硬碟送達 Microsoft 資料中心後，需要多久的時間才能將我的 PST 檔案上傳到 Azure？**</span><span class="sxs-lookup"><span data-stu-id="cb527-271">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="cb527-272">硬碟送達 Microsoft 資料中心後，需要 7 到 10 個工作天，才能將 PST 檔案上傳到貴組織的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="cb527-272">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Azure Storage location for your organization.</span></span> <span data-ttu-id="cb527-273">PST 檔案會上傳到名為 `ingestiondata` 的 Azure Blob 容器。</span><span class="sxs-lookup"><span data-stu-id="cb527-273">The PST files will be uploaded to an Azure blob container named `ingestiondata`.</span></span> 
  
 <span data-ttu-id="cb527-274">**需要多久的時間才能將 PST 檔案匯入信箱？**</span><span class="sxs-lookup"><span data-stu-id="cb527-274">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="cb527-275">PST 檔案上傳到 Azure 儲存體區域之後，Office 365 會以安全的方式分析 PST 檔案中的資料，來識別 PST 檔案所含項目的保存時間和各種訊息類型。</span><span class="sxs-lookup"><span data-stu-id="cb527-275">After the PST files are uploaded to the Azure Storage area, Office 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files.</span></span> <span data-ttu-id="cb527-276">這項分析程序完成後，您就可以選擇匯入 PST 檔案中的所有資料，或設定篩選器來控制要匯入的資料。</span><span class="sxs-lookup"><span data-stu-id="cb527-276">When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported.</span></span> <span data-ttu-id="cb527-277">始匯入工作之後，PST 會以每天至少 24 GB 的速率匯入到 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="cb527-277">After you start the import job, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="cb527-278">如果這樣的速率不符您的需求，您可以考慮其他將電子郵件資料移轉到 Office 365 的方法。</span><span class="sxs-lookup"><span data-stu-id="cb527-278">If this rate doesn't meet your needs, you might consider other methods to get email data into Office 365.</span></span> <span data-ttu-id="cb527-279">如需詳細資訊，請參閱＜[將多個電子郵件帳戶移轉到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)＞。</span><span class="sxs-lookup"><span data-stu-id="cb527-279">For more information, see [Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
<span data-ttu-id="cb527-280">如果不同的 PST 檔案需匯入到不同的目標信箱，匯入程序會同時進行；換句話說，系統會同時匯入每個 PST/信箱組合。</span><span class="sxs-lookup"><span data-stu-id="cb527-280">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="cb527-281">同樣地，如果多個 PST 檔案匯入到相同的信箱，則會同時匯入。</span><span class="sxs-lookup"><span data-stu-id="cb527-281">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="cb527-282">**Microsoft 將我的 PST 檔案上傳到 Azure 之後，這些檔案會在 Azure 中保留多久的時間才會刪除？**</span><span class="sxs-lookup"><span data-stu-id="cb527-282">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="cb527-283">貴組織的 Azure 儲存體位置 (儲存在名為 `ingestiondata` 的 Blob 容器) 中的所有 PST 檔案，會在最新的匯入工作於安全性與合規性中心的 [匯入 PST 檔案]\*\*\*\* 頁面上建立完成的 30 天後遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="cb527-283">All PST files in the Azure Storage location for your organization (in blob container named `ingestiondata`), are deleted 30 days after the most recent import job was created on the **Import PST files** page in the Security & Compliance Center.</span></span> 
  
<span data-ttu-id="cb527-284">這也表示 PST 檔案從 Azure 儲存體區域刪除之後，安全性與合規性中心內完整匯入工作的檔案清單中就不會顯示這些檔案。</span><span class="sxs-lookup"><span data-stu-id="cb527-284">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="cb527-285">即使匯入工作仍然列在安全性與合規性中心的 [匯入 PST 檔案]\*\*\*\* 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。</span><span class="sxs-lookup"><span data-stu-id="cb527-285">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="cb527-286">**哪些版本的 PST 檔案格式支援匯入 Office 365？**</span><span class="sxs-lookup"><span data-stu-id="cb527-286">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="cb527-287">有兩個版本的 PST 檔案格式支援此作業：ANSI 和 Unicode。</span><span class="sxs-lookup"><span data-stu-id="cb527-287">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="cb527-288">我們建議您使用 Unicode PST 檔案格式來匯入檔案。</span><span class="sxs-lookup"><span data-stu-id="cb527-288">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="cb527-289">不過，使用 ANSI PST 檔案格式的檔案 (例如，使用雙位元組字元集 (DBCS) 語言的檔案) 也可以匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="cb527-289">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365.</span></span> <span data-ttu-id="cb527-290">如需有關匯入 ANSI PST 檔案的詳細資訊，請參閱[使用磁碟機寄送將組織 PST 檔案匯入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)中的步驟 3。</span><span class="sxs-lookup"><span data-stu-id="cb527-290">For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import your organization PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="cb527-291">此外，Outlook 2007 和更新版本的 PST 檔案也可以匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="cb527-291">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="cb527-292">**匯入 PST 檔案時，是否有郵件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="cb527-292">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="cb527-293">是。</span><span class="sxs-lookup"><span data-stu-id="cb527-293">Yes.</span></span> <span data-ttu-id="cb527-294">如果 PST 檔案包含大於 150 MB 的信箱項目，該項目會在匯入程序執行時略過。</span><span class="sxs-lookup"><span data-stu-id="cb527-294">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="cb527-295">**PST 檔案匯入 Office 365 信箱時是否會保留訊息內容 (例如訊息的傳送或接收時間、收件者清單等等)？**</span><span class="sxs-lookup"><span data-stu-id="cb527-295">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="cb527-296">是。</span><span class="sxs-lookup"><span data-stu-id="cb527-296">Yes.</span></span> <span data-ttu-id="cb527-297">匯入程序不會變更任何原始的訊息中繼資料</span><span class="sxs-lookup"><span data-stu-id="cb527-297">The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="cb527-298">**針對我要匯入至信箱的 PST 檔案，其資料夾階層數是否有上限？**</span><span class="sxs-lookup"><span data-stu-id="cb527-298">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="cb527-p148">是。您無法匯入具有 300 或更多巢狀資料夾階層的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="cb527-p148">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="cb527-301">**我是否可以使用磁碟機寄送將 PST 檔案匯入 Office 365 中的非作用中的信箱？**</span><span class="sxs-lookup"><span data-stu-id="cb527-301">**Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="cb527-302">是，我們現已推出這項功能。</span><span class="sxs-lookup"><span data-stu-id="cb527-302">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="cb527-303">**我是否可以使用磁碟機寄送將 PST 檔案匯入 Exchange 混合式部署中的線上封存信箱？**</span><span class="sxs-lookup"><span data-stu-id="cb527-303">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="cb527-304">是，我們現已推出這項功能。</span><span class="sxs-lookup"><span data-stu-id="cb527-304">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="cb527-305">**我是否可以使用磁碟機寄送方式將 PST 檔案匯入 Exchange Online 的公用資料夾？**</span><span class="sxs-lookup"><span data-stu-id="cb527-305">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="cb527-306">否，您無法將 PST 檔案匯入公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="cb527-306">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="cb527-307">**Microsoft 是否可以先將硬碟清空再寄回給我？**</span><span class="sxs-lookup"><span data-stu-id="cb527-307">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="cb527-p149">否，Microsoft 無法先將硬碟清空再寄回給客戶。硬碟會以 Microsoft 當初收到的狀態寄回給您。</span><span class="sxs-lookup"><span data-stu-id="cb527-p149">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="cb527-310">**Microsoft 是否可以先將硬碟銷毀再寄回給我？**</span><span class="sxs-lookup"><span data-stu-id="cb527-310">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="cb527-p150">否，Microsoft 不能破壞您的硬碟。硬碟會以 Microsoft 當初收到的狀態寄回給您。</span><span class="sxs-lookup"><span data-stu-id="cb527-p150">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="cb527-313">**哪些快遞服務支援將硬碟寄回客戶？**</span><span class="sxs-lookup"><span data-stu-id="cb527-313">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="cb527-p151">如果您是位於美國或歐洲地區的客戶，Microsoft 會使用 FedEx 將硬碟寄回給您。針對所有其他區域，Microsoft 則會使用 DHL。</span><span class="sxs-lookup"><span data-stu-id="cb527-p151">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="cb527-316">**將硬碟寄回需要多少費用？**</span><span class="sxs-lookup"><span data-stu-id="cb527-316">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="cb527-p152">實際的寄回費用取決於您將硬碟寄出的所在地區與 Microsoft 資料中心之間的距離。Microsoft 會從您的 FedEx 或 DHL 帳戶收取硬碟寄回費用。寄回費用需由您自行承擔。</span><span class="sxs-lookup"><span data-stu-id="cb527-p152">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="cb527-320">**我是否能使用自訂運送服務 (例如 FedEx 自訂運送) 將我的硬碟寄給 Microsoft？**</span><span class="sxs-lookup"><span data-stu-id="cb527-320">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="cb527-321">是。</span><span class="sxs-lookup"><span data-stu-id="cb527-321">Yes.</span></span>
  
 <span data-ttu-id="cb527-322">**如果我需要將硬碟寄到其他國家/地區，我需要採取什麼動作嗎？**</span><span class="sxs-lookup"><span data-stu-id="cb527-322">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="cb527-p153">您寄給 Microsoft 的硬碟可能會跨國際邊界。在這種情況下，您必須負責確保硬碟和當中的資料可依據相關法律進口和/或出口。寄送硬碟之前，請與您的顧問確認磁碟機和當中的資料可以合法地寄到指定的 Microsoft 資料中心，以確保 Microsoft 能夠及時收到您的硬碟。</span><span class="sxs-lookup"><span data-stu-id="cb527-p153">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
