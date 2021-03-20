---
title: 將組織的 PST 檔案匯入的概觀
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何在安全性與合規性中心使用[匯入]服務來將電子郵件資料 (PST 檔案) 大量匯入至使用者信箱。
ms.openlocfilehash: 6d0bca6d76a0eccb9bc8181e73f2c36c51acaf77
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911317"
---
# <a name="overview-of-importing-your-organizations-pst-files"></a><span data-ttu-id="19c4b-103">將組織的 PST 檔案匯入的概觀</span><span class="sxs-lookup"><span data-stu-id="19c4b-103">Overview of importing your organization's PST files</span></span>

> [!NOTE]
> <span data-ttu-id="19c4b-104">本文適用於系統管理員。</span><span class="sxs-lookup"><span data-stu-id="19c4b-104">This article is for administrators.</span></span> <span data-ttu-id="19c4b-105">您是否正嘗試匯入 PST 檔案到自己的信箱？</span><span class="sxs-lookup"><span data-stu-id="19c4b-105">Are you trying to import PST files to your own mailbox?</span></span> <span data-ttu-id="19c4b-106">請參閱[從 Outlook .pst 檔案匯入電子郵件、連絡人和行事曆](https://go.microsoft.com/fwlink/p/?LinkID=785075)。</span><span class="sxs-lookup"><span data-stu-id="19c4b-106">See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075).</span></span>

<span data-ttu-id="19c4b-107">您可以使用安全性與合規性中心的「匯入」服務將 PST 檔案快速大量匯入至組織中的 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="19c4b-107">You can use the Import service in the Security & Compliance Center to quickly bulk-import PST files to Exchange Online mailboxes in your organization.</span></span> <span data-ttu-id="19c4b-108">有兩種方法可將 PST 檔案匯入到 Office 365：</span><span class="sxs-lookup"><span data-stu-id="19c4b-108">There are two ways you can import PST files to Office 365:</span></span>

- <span data-ttu-id="19c4b-109">**網路上傳**![雲端上傳](../media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) - 透過網路將 PST 檔案上傳到 Microsoft Cloud 的暫時 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="19c4b-109">**Network upload** ![Cloud upload](../media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) - Upload the PST files over the network to a temporary Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="19c4b-110">然後，您可以使用 Office 365 匯入服務將 PST 資料匯入組織中的信箱。</span><span class="sxs-lookup"><span data-stu-id="19c4b-110">Then you use the Office 365 Import service to import the PST data to mailboxes in your organization.</span></span> 

- <span data-ttu-id="19c4b-111">**磁碟機寄送**![硬碟](../media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) - 將 PST 檔案複製到 BitLocker 加密硬碟，並實際寄送磁碟機給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="19c4b-111">**Drive shipping** ![Hard disk](../media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) - Copy the PST files to a BitLocker-encrypted hard drive and then physically ship the drive to Microsoft.</span></span> <span data-ttu-id="19c4b-112">當 Microsoft 收到硬碟時，資料中心人員會將資料上傳到 Microsoft Cloud 的暫時 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="19c4b-112">When Microsoft receives the hard drive, data center personnel upload the data to a temporary Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="19c4b-113">然後，使用 Office 365 匯入服務將資料匯入組織中的信箱。</span><span class="sxs-lookup"><span data-stu-id="19c4b-113">Then you use the Office 365 Import service to import the data to mailboxes in your organization.</span></span>

## <a name="step-by-step-instructions"></a><span data-ttu-id="19c4b-114">逐步指示</span><span class="sxs-lookup"><span data-stu-id="19c4b-114">Step-by-step instructions</span></span>
  
<span data-ttu-id="19c4b-115">請參閱下列其中一個主題以取得將組織 PST 檔案大量匯入至 Office 365 的詳細逐步指示。</span><span class="sxs-lookup"><span data-stu-id="19c4b-115">See one of the following topics for detailed, step-by-step instructions for bulk-importing your organization's PST files to Office 365.</span></span> 

- [<span data-ttu-id="19c4b-116">使用網路上傳將 PST 檔案匯入 Office 365</span><span class="sxs-lookup"><span data-stu-id="19c4b-116">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)

- [<span data-ttu-id="19c4b-117">使用磁碟機運送來匯入 PST 檔案</span><span class="sxs-lookup"><span data-stu-id="19c4b-117">Use drive shipping to import PST files</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a><span data-ttu-id="19c4b-118">匯入 PST 檔案的運作方式</span><span class="sxs-lookup"><span data-stu-id="19c4b-118">How importing PST files works</span></span>

<span data-ttu-id="19c4b-119">以下是完整 PST 匯入程序的圖例和說明。</span><span class="sxs-lookup"><span data-stu-id="19c4b-119">Here's an illustration and description of the complete PST import process.</span></span> <span data-ttu-id="19c4b-120">圖例顯示主要工作流程，並醒目提示網路上傳和磁碟機寄送方法之間的差異。</span><span class="sxs-lookup"><span data-stu-id="19c4b-120">The illustration shows the primary workflow and highlights the differences between the network upload and drive shipping methods.</span></span>
  
![PST 匯入程序的工作流程](../media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. <span data-ttu-id="19c4b-122">**將 PST 匯入工具和金鑰下載到私人 Azure 儲存體位置** - 第一個步驟是下載用於上傳 PST 檔案的工具和存取金鑰，或將它們複製到硬碟。</span><span class="sxs-lookup"><span data-stu-id="19c4b-122">**Download the PST import tools and key to private Azure Storage location** - The first step is to download the tool and access key used to upload the PST files or copy them to a hard drive.</span></span> <span data-ttu-id="19c4b-123">您可以從安全性與合規性中心的 **匯入** 頁面取得這些工具和便捷鍵。</span><span class="sxs-lookup"><span data-stu-id="19c4b-123">You obtain these from the **Import** page in the Security & Compliance Center.</span></span> <span data-ttu-id="19c4b-124">此金鑰提供您 (或在磁碟機寄送時提供給 Microsoft 資料中心人員) 將 PST 檔案上傳到私人且安全的 Azure 儲存體位置的必要權限。</span><span class="sxs-lookup"><span data-stu-id="19c4b-124">The key provides you (or Microsoft data center personnel in the case of drive shipping) with the necessary permissions to upload PST files to a private and secure Azure Storage location.</span></span> <span data-ttu-id="19c4b-125">此便捷鍵專屬於貴組織，並在 PST 檔案上傳到 Microsoft Cloud 後，協助防止未經授權存取 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="19c4b-125">This access key is unique to your organization and helps prevent unauthorized access to your PST files after they're uploaded to the Microsoft cloud.</span></span> <span data-ttu-id="19c4b-126">將 PST 檔案匯入至 Microsoft 365 時，您的組織無須具備個別的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="19c4b-126">Importing PST files to Microsoft 365 doesn't require your organization to have a separate Azure subscription.</span></span> 
    
2. <span data-ttu-id="19c4b-127">**上傳或複製的 PST 檔案** - 下一個步驟取決於您使用網路上傳或磁碟機寄送來匯入 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="19c4b-127">**Upload or copy the PST files** - The next step depends on whether you're using network upload or drive shipping to import PST files.</span></span> <span data-ttu-id="19c4b-128">在這兩種情況下，您會使用上一個步驟中取得的工具和安全儲存體金鑰。</span><span class="sxs-lookup"><span data-stu-id="19c4b-128">In both cases, you'll use the tool and secure storage key that you obtained in the previous step.</span></span>
    
    - <span data-ttu-id="19c4b-129">**網路上傳：** AzCopy.exe 工具 (於步驟 1 中下載) 用於上傳 PST 檔案並將其儲存在 Microsoft Cloud 中的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="19c4b-129">**Network upload:** The AzCopy.exe tool (downloaded in step 1) is used to upload and store your PST files in an Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="19c4b-130">上傳 PST 檔案的 Azure 存儲體位置，與組織位於相同的地區 Microsoft 資料中心。</span><span class="sxs-lookup"><span data-stu-id="19c4b-130">The Azure Storage location that you upload your PST files to is located in the same regional Microsoft datacenter as your organization.</span></span>
    
      <span data-ttu-id="19c4b-131">若要上傳，您想要匯入的 PST 檔案必須位於組織中的檔案共用或檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="19c4b-131">To upload them, the PST files that you want to import have to be located in a file share or file server in your organization.</span></span>
    
    - <span data-ttu-id="19c4b-132">**磁碟機寄送：** WAImportExport.exe 工具 (於步驟 1 下載) 是用於將 PST 檔案複製到硬碟。</span><span class="sxs-lookup"><span data-stu-id="19c4b-132">**Drive shipping:** The WAImportExport.exe tool (downloaded in step 1) is used to copy your PST files to the hard drive.</span></span> <span data-ttu-id="19c4b-133">此工具會以 BitLocker 加密硬碟，然後將 PST 複製到硬碟。</span><span class="sxs-lookup"><span data-stu-id="19c4b-133">This tool encrypts the hard drive with BitLocker and then copies the PSTs to the hard drive.</span></span> <span data-ttu-id="19c4b-134">如同網路上傳，您想要複製到硬碟的 PST 檔案必須位於組織中的檔案共用或檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="19c4b-134">Like network upload, the PST files that you want to copy to the hard drive have to be located in a file share or file server in your organization.</span></span>
    
3. <span data-ttu-id="19c4b-135">**建立 PST 匯入對應檔案** - PST 檔案上傳到 Azure 儲存體位置或複製到硬碟後，下一個步驟是建立逗點分隔值 (CSV) 檔案，以指定要匯入 PST 檔案的使用者信箱 (PST 檔案可匯入使用者的主要信箱或封存信箱)。</span><span class="sxs-lookup"><span data-stu-id="19c4b-135">**Create a PST import mapping file** - After the PST files have been uploaded to the Azure Storage location or copied to a hard drive, the next step is to create a comma-separated value (CSV) file that specifies which user mailboxes the PST files will be imported to (and a PST file can be imported to a user's primary mailbox or their archive mailbox).</span></span> <span data-ttu-id="19c4b-136">Office 365 匯入服務會使用此資訊匯入 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="19c4b-136">The Office 365 Import service will use the information to import the PST files.</span></span> 
    
4. <span data-ttu-id="19c4b-137">**建立 PST 匯入工作** - 下一個步驟是在安全性與合規性中心的 [匯入] 頁面建立 PST 匯入工作，然後提交上一個步驟中建立的 PST 匯入對應檔案。</span><span class="sxs-lookup"><span data-stu-id="19c4b-137">**Create a PST import job** - The next step is to create a PST import job on the **Import PST files** page in the Security & Compliance Center and submit the PST import mapping file created in the previous step.</span></span> <span data-ttu-id="19c4b-138">若為網路上傳 (因為 PST 檔案已上傳到 Azure)，Microsoft 365 會分析 PST 檔案中的資料，然後讓您設定篩選條件，以控制哪些資料會實際匯入 PST 匯入對應檔案中指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="19c4b-138">For network upload (because the PST files have been uploaded to Azure) Microsoft 365 analyzes the data in the PST files and then gives you an opportunity to set filters that control what data actually gets imported to the mailboxes specified in the PST import mapping file.</span></span> 
    
    <span data-ttu-id="19c4b-139">若為磁碟機寄送，此時程序中會發生一些其他事項。</span><span class="sxs-lookup"><span data-stu-id="19c4b-139">For drive shipping, a few additional things happen at this point in the process.</span></span>
    
    - <span data-ttu-id="19c4b-140">您實際將硬碟寄送給 Microsoft 資料中心 (建立匯入工作時，會顯示 Microsoft 資料中心的寄送地址)。</span><span class="sxs-lookup"><span data-stu-id="19c4b-140">You physically ship the hard drive to a Microsoft data center (the shipping address for the Microsoft data center is displayed when the import job is created).</span></span>
    
    - <span data-ttu-id="19c4b-141">Microsoft 收到硬碟之後，資料中心的人員會為貴組織將硬碟上的 PST 檔案上傳到 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="19c4b-141">When Microsoft receives the hard drive, data center personnel will upload the PST files on the hard drive to the Azure Storage location for your organization.</span></span> <span data-ttu-id="19c4b-142">如先前所述，您的 PST 檔案會上傳至組織所在的相同地區 Microsoft 資料中心的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="19c4b-142">As previously explained, your PST files are uploaded to a Azure Storage location that resides in the same regional Microsoft datacenter where your organization is located.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="19c4b-143">Microsoft 收到硬碟後，會在 7 到 10 個工作天內將硬碟上的 PST 檔案上傳至 Azure。</span><span class="sxs-lookup"><span data-stu-id="19c4b-143">The PST files on the hard drive are uploaded to Azure within 7 to 10 business days after Microsoft receives the hard drive.</span></span>

      <span data-ttu-id="19c4b-144">如同網路上傳程序，Microsoft 365 會分析 PST 檔案中的資料，然後讓您設定篩選條件，以控制哪些資料會實際匯入 PST 匯入對應檔案中指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="19c4b-144">Like the network upload process, Microsoft 365 then analyzes the data in the PST files and gives you an opportunity to set filters that control what data actually gets imported to the mailboxes specified in the PST import mapping file.</span></span>
    
    - <span data-ttu-id="19c4b-145">Microsoft 會將硬碟寄回給您。</span><span class="sxs-lookup"><span data-stu-id="19c4b-145">Microsoft ships the hard drive back to you.</span></span>
    
5. <span data-ttu-id="19c4b-146">**篩選將匯入到信箱的 PST 資料** - 建立匯入工作後 (且磁碟機寄送工作的 PST 檔案上傳到 Azure 儲存體位置後)，Microsoft 365 會透過找出項目的存留期和包括在 PST 檔案中的不同訊息類型，(以安全的方式) 分析 PST 檔案中的資料。</span><span class="sxs-lookup"><span data-stu-id="19c4b-146">**Filter the PST data that will be imported to mailboxes** - After the import job is created (and after the PST files from a drive shipping job are uploaded to the Azure Storage location) Microsoft 365 analyzes the data in the PST files (safely and securely) by identifying the age of the items and the different message types included in the PST files.</span></span> <span data-ttu-id="19c4b-147">分析完成且準備好匯入資料後，您可以選擇匯入 PST 檔案中所包含的所有資料，或設定控制匯入資料的篩選條件來調整要匯入的資料。</span><span class="sxs-lookup"><span data-stu-id="19c4b-147">When the analysis is completed and the data is ready to import, you have the option to import all the data contained in the PST files or you can trim the data that's imported by setting filters that control what data gets imported.</span></span> 
    
6. <span data-ttu-id="19c4b-148">**開始 PST 匯入工作** - 開始匯入工作後，Microsoft 365 會使用 PST 匯入對應檔案中的資訊，將 PST 檔案從 Azure 儲存體位置匯入至使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="19c4b-148">**Start the PST import job** - After the import job is started, Microsoft 365 uses the information in the PST import mapping file to import the PSTs files from the he Azure Storage location to user mailboxes.</span></span> <span data-ttu-id="19c4b-149">匯入工作的狀態資訊 (包括匯入的每個 PST 檔案的相關資訊) 會顯示在安全性與合規性中心的 [匯入 PST 檔案] 頁面。</span><span class="sxs-lookup"><span data-stu-id="19c4b-149">Status information about the import job (including information about each PST file being imported) is displayed on the **Import PST files** page in the Security & Compliance Center.</span></span> <span data-ttu-id="19c4b-150">匯入工作完成時，工作的狀態會設為 **完成**。</span><span class="sxs-lookup"><span data-stu-id="19c4b-150">When the import job is finished, the status for the job is set to **Complete**.</span></span>
  
## <a name="why-import-email-data-to-microsoft-365"></a><span data-ttu-id="19c4b-151">為什麼要將電子郵件資料匯入 Microsoft 365？</span><span class="sxs-lookup"><span data-stu-id="19c4b-151">Why import email data to Microsoft 365?</span></span>

- <span data-ttu-id="19c4b-152">這是將組織的封存訊息資料匯入 Microsoft 365 的好方法。</span><span class="sxs-lookup"><span data-stu-id="19c4b-152">It's a good way to import your organization's archival messaging data to Microsoft 365.</span></span>
    
- <span data-ttu-id="19c4b-153">您可以使用[智慧型匯入](filter-data-when-importing-pst-files.md)功能來篩選實際匯入目標信箱的 PST 檔案項目。</span><span class="sxs-lookup"><span data-stu-id="19c4b-153">You can use the [Intelligent Import](filter-data-when-importing-pst-files.md) feature to filter the items in PST files that actually get imported to the target mailboxes.</span></span> <span data-ttu-id="19c4b-154">這能讓您藉由設定控制匯入資料的篩選條件來調整要匯入的資料。</span><span class="sxs-lookup"><span data-stu-id="19c4b-154">This lets you trim the data that's imported by setting filters that control what data gets imported.</span></span> 
    
- <span data-ttu-id="19c4b-155">將電子郵件資料匯入至 Microsoft 365 可讓您利用下列方式解決組織的合規需求︰</span><span class="sxs-lookup"><span data-stu-id="19c4b-155">Importing email data to Microsoft 365 helps address compliance needs of your organization by letting you:</span></span>
    
  - <span data-ttu-id="19c4b-156">啟用[封存信箱](enable-archive-mailboxes.md)和[無限制封存](unlimited-archiving.md)以提供使用者額外的信箱儲存空間。</span><span class="sxs-lookup"><span data-stu-id="19c4b-156">Enable [archive mailboxes](enable-archive-mailboxes.md) and [unlimited archiving](unlimited-archiving.md) to give users additional mailbox storage space.</span></span> 
    
  - <span data-ttu-id="19c4b-157">將信箱置於[訴訟暫止](./create-a-litigation-hold.md)來保留內容。</span><span class="sxs-lookup"><span data-stu-id="19c4b-157">Place mailboxes on [Litigation Hold](./create-a-litigation-hold.md) to retain content.</span></span> 
    
  - <span data-ttu-id="19c4b-158">使用[內容搜尋工具](content-search.md)搜尋信箱內容。</span><span class="sxs-lookup"><span data-stu-id="19c4b-158">Use the [Content Search tool](content-search.md) to search for mailbox content.</span></span> 
    
  - <span data-ttu-id="19c4b-159">使用[電子文件探索案例](./get-started-core-ediscovery.md)來管理貴組織的法律調查</span><span class="sxs-lookup"><span data-stu-id="19c4b-159">Use [eDiscovery cases](./get-started-core-ediscovery.md) to manage your organization's legal investigations</span></span> 
    
  - <span data-ttu-id="19c4b-160">使用安全性與合規性中心的[保留原則](retention.md)來控制信箱內容的保留時間，並在保留期間結束後刪除內容。</span><span class="sxs-lookup"><span data-stu-id="19c4b-160">Use [retention policies](retention.md) in the Security & Compliance Center to control how long mailbox content is retained, and then delete content after the retention period expires.</span></span> 

  - <span data-ttu-id="19c4b-161">使用[通訊合規性原則](communication-compliance.md)檢查郵件，以確認郵件符合郵件標準的規範，並新增分類類型。</span><span class="sxs-lookup"><span data-stu-id="19c4b-161">Use [Communication compliance policies](communication-compliance.md) to examine messages to make sure they are compliant with message standards and add a classification type.</span></span>
    
- <span data-ttu-id="19c4b-162">將資料匯入 Microsoft 365 有助於防止資料遺失。</span><span class="sxs-lookup"><span data-stu-id="19c4b-162">Importing data to Microsoft 365 helps protect against data loss.</span></span> <span data-ttu-id="19c4b-163">匯入至 Microsoft 365 的電子郵件資料會繼承 Exchange Online 的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="19c4b-163">Email data that's imported to Microsoft 365 inherits the high availability features of Exchange Online.</span></span>
    
- <span data-ttu-id="19c4b-164">電子郵件資料儲存在雲端上，因此使用者從各種裝置都能取得資料。</span><span class="sxs-lookup"><span data-stu-id="19c4b-164">Email data is available to users from all devices because it's stored in the cloud.</span></span>
    
## <a name="importing-sharepoint-data-to-microsoft-365"></a><span data-ttu-id="19c4b-165">將 SharePoint 資料匯入至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="19c4b-165">Importing SharePoint data to Microsoft 365</span></span>

<span data-ttu-id="19c4b-166">您也可以將檔案和文件匯入至組織中的 SharePoint 網站和 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="19c4b-166">You can also import files and documents to SharePoint sites and OneDrive accounts in your organization.</span></span> <span data-ttu-id="19c4b-167">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="19c4b-167">For more information, see the following articles:</span></span>

- [<span data-ttu-id="19c4b-168">移轉至 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="19c4b-168">Migrate to SharePoint Online</span></span>](/sharepointmigration/migrate-to-sharepoint-online)

- [<span data-ttu-id="19c4b-169">SharePoint 移轉工具簡介</span><span class="sxs-lookup"><span data-stu-id="19c4b-169">Introducing the SharePoint Migration Tool</span></span>](/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [<span data-ttu-id="19c4b-170">使用 PowerShell 移轉至 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="19c4b-170">Migrate to SharePoint Online using PowerShell</span></span>](/sharepointmigration/overview-spmt-ps-cmdlets)

- [<span data-ttu-id="19c4b-171">使用 Azure 資料箱將檔案共用內容移轉至 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="19c4b-171">Migrate your file share content to SharePoint Online using the Azure Data Box</span></span>](/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)

## <a name="frequently-asked-questions-about-importing-pst-files"></a><span data-ttu-id="19c4b-172">匯入 PST 檔案的關於常見問題</span><span class="sxs-lookup"><span data-stu-id="19c4b-172">Frequently asked questions about importing PST files</span></span>
  
<span data-ttu-id="19c4b-173">以下是一些關於使用 Office 365 匯入服務將 PST 檔案大量匯入至 Microsoft 365 信箱的常見問題解答。</span><span class="sxs-lookup"><span data-stu-id="19c4b-173">Here are some frequently asked questions about using the Office 365 Import service to bulk-import PST files to Microsoft 365 mailboxes.</span></span> 
  
- [<span data-ttu-id="19c4b-174">使用網路上傳來匯入 PST 檔案</span><span class="sxs-lookup"><span data-stu-id="19c4b-174">Using network upload to import PST files</span></span>](#using-network-upload-to-import-pst-files)
  
- [<span data-ttu-id="19c4b-175">使用磁碟機寄送來匯入 PST 檔案</span><span class="sxs-lookup"><span data-stu-id="19c4b-175">Using drive shipping to import PST files</span></span>](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="19c4b-176">使用網路上傳來匯入 PST 檔案</span><span class="sxs-lookup"><span data-stu-id="19c4b-176">Using network upload to import PST files</span></span>

 <span data-ttu-id="19c4b-177">**必須具備哪些權限才能在 Office365 匯入服務中建立匯入工作？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-177">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="19c4b-178">您必須在 Exchange Online 中獲派信箱匯入匯出角色，才能將 PST 檔案匯入 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="19c4b-178">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="19c4b-179">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="19c4b-179">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="19c4b-180">You can add the Mailbox Import Export role to the Organization Management role group.</span><span class="sxs-lookup"><span data-stu-id="19c4b-180">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="19c4b-181">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span><span class="sxs-lookup"><span data-stu-id="19c4b-181">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="19c4b-182">如需詳細資訊，請參閱[管理 Exchange Online 中的角色](/Exchange/permissions-exo/role-groups)之＜新增角色至角色群組＞或＜建立角色群組＞一節。</span><span class="sxs-lookup"><span data-stu-id="19c4b-182">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups).</span></span>
  
<span data-ttu-id="19c4b-183">此外，若要在安全性與合規性中心建立匯入工作，必須符合以下其中一個條件：</span><span class="sxs-lookup"><span data-stu-id="19c4b-183">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="19c4b-184">您必須在 Exchange Online 中獲派郵件收件者角色。</span><span class="sxs-lookup"><span data-stu-id="19c4b-184">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="19c4b-185">根據預設，這個角色會指派給組織管理及收件者管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="19c4b-185">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>

    <span data-ttu-id="19c4b-186">或者</span><span class="sxs-lookup"><span data-stu-id="19c4b-186">Or</span></span>
    
- <span data-ttu-id="19c4b-187">您必須是組織中的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="19c4b-187">You have to be a global administrator in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="19c4b-188">建議您在 Exchange Online 中建立新的角色群組，專門用來將 PST 檔案匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="19c4b-188">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="19c4b-189">若要獲得匯入 PST 檔案所需的最低權限等級，請將信箱匯入匯出及郵件收件者角色指派到新的角色群組，然後新增成員。</span><span class="sxs-lookup"><span data-stu-id="19c4b-189">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="19c4b-190">**哪些地區提供網路上傳服務？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-190">**Where is network upload available?**</span></span>
  
<span data-ttu-id="19c4b-p121">網路上傳的服務範圍目前包括這些地區：美國、加拿大、巴西、英國、法國、德國、瑞士、挪威、歐洲、印度、東亞、東南亞、日本、南韓、澳洲和阿拉伯聯合大公國 (UAE)。我們會盡快在更多地區提供網路上傳服務。</span><span class="sxs-lookup"><span data-stu-id="19c4b-p121">Network upload is currently available in these regions: United States, Canada, Brazil, the United Kingdom, France, Germany, Switzerland, Norway, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, Australia, and United Arab Emirates (UAE). Network upload will be available in more regions soon.</span></span>
  
 <span data-ttu-id="19c4b-193">**使用網路上傳匯入 PST 檔案的費用為何？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-193">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="19c4b-194">Using network upload to import PST files is free.</span><span class="sxs-lookup"><span data-stu-id="19c4b-194">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="19c4b-195">這也表示 PST 檔案從 Azure 儲存體區域刪除之後，Microsoft 365 系統管理中心內完整匯入工作的檔案清單中就不會顯示這些檔案。</span><span class="sxs-lookup"><span data-stu-id="19c4b-195">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Microsoft 365 admin center.</span></span> <span data-ttu-id="19c4b-196">即使匯入工作仍然列在 **[將資料匯入 Office 365]** 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。</span><span class="sxs-lookup"><span data-stu-id="19c4b-196">Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span>
  
 <span data-ttu-id="19c4b-197">**哪些版本的 PST 檔案格式支援匯入 Office 365？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-197">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="19c4b-198">有兩個版本的 PST 檔案格式支援此作業：ANSI 和 Unicode。</span><span class="sxs-lookup"><span data-stu-id="19c4b-198">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="19c4b-199">我們建議您使用 Unicode PST 檔案格式來匯入檔案。</span><span class="sxs-lookup"><span data-stu-id="19c4b-199">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="19c4b-200">不過，使用 ANSI PST 檔案格式的檔案 (例如，使用雙位元組字元集 (DBCS) 語言的檔案) 也可以匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="19c4b-200">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365.</span></span> <span data-ttu-id="19c4b-201">如需有關匯入 ANSI PST 檔案的資訊，請參閱[使用網路上傳將 PST 檔案匯入 Office 365](./use-network-upload-to-import-pst-files.md) 中的步驟 4。</span><span class="sxs-lookup"><span data-stu-id="19c4b-201">For more information about importing ANSI PST files, see Step 4 in [Use network upload to import PST files to Office 365](./use-network-upload-to-import-pst-files.md).</span></span>
  
<span data-ttu-id="19c4b-202">此外，Outlook 2007 和更新版本的 PST 檔案也可以匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="19c4b-202">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="19c4b-203">**將我的 PST 檔案上傳到 Azure 儲存體區域之後，這些檔案會在 Azure 中保留多久的時間才會遭到刪除？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-203">**After I upload my PST files to the Azure Storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="19c4b-204">使用網路上傳方法匯入 PST 檔案，會將這些檔案上傳到名為 `ingestiondata` 的 Azure Blob 容器。</span><span class="sxs-lookup"><span data-stu-id="19c4b-204">When you use the network upload method to import PST files, you upload them to an Azure blob container named `ingestiondata`.</span></span> <span data-ttu-id="19c4b-205">如果安全性與合規性中心的 [匯入 PST 檔案] 頁面目前沒有進行中的匯入工作，則 Azure 中 `ingestiondata` 容器內的所有 PST 檔案都會在最近的匯入工作於安全性與合規性中心建立完成的後 30 天刪除。</span><span class="sxs-lookup"><span data-stu-id="19c4b-205">If there are no import jobs in progress on the **Import PST files** page in the Security & Compliance Center), then all PST files in the `ingestiondata` container in Azure are deleted 30 days after the most recent import job was created in the Security & Compliance Center.</span></span> <span data-ttu-id="19c4b-206">這也表示您必須在 PST 檔案上傳到 Azure 的 30 天內，在安全性與合規性中心建立新的匯入工作 (如網路上傳指示中的步驟 5 所述)。</span><span class="sxs-lookup"><span data-stu-id="19c4b-206">That also means you have to create a new import job in the Security & Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span>
  
<span data-ttu-id="19c4b-207">這也表示 PST 檔案從 Azure 儲存體區域刪除之後，安全性與合規性中心內完整匯入工作的檔案清單中就不會顯示這些檔案。</span><span class="sxs-lookup"><span data-stu-id="19c4b-207">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="19c4b-208">即使匯入工作仍然列在安全性與合規性中心的 [匯入 PST 檔案] 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。</span><span class="sxs-lookup"><span data-stu-id="19c4b-208">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span>
  
 <span data-ttu-id="19c4b-209">**需要多久的時間才能將 PST 檔案匯入信箱？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-209">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="19c4b-210">這取決於您的網路容量，但將每 TB 的資料上傳到貴組織的 Azure 儲存體區域通常需要幾個小時的時間。</span><span class="sxs-lookup"><span data-stu-id="19c4b-210">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure Storage area for your organization.</span></span> <span data-ttu-id="19c4b-211">將 PST 檔案複製到 Azure 儲存體區域之後，系統會以每天至少 24 GB 的速率將 PST 檔案匯入至 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="19c4b-211">After the PST files are copied to the Azure Storage area, a PST file is imported to a Microsoft 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="19c4b-212">如果這樣的速率不符您的需求，您可以考慮其他將電子郵件資料移轉到 Office 365 的方法。</span><span class="sxs-lookup"><span data-stu-id="19c4b-212">If this rate doesn't meet your needs, you might consider other methods to get email data into Office 365.</span></span> <span data-ttu-id="19c4b-213">如需詳細資訊，請參閱＜[將多個電子郵件帳戶移轉到 Office 365 的方法](/Exchange/mailbox-migration/mailbox-migration)＞。</span><span class="sxs-lookup"><span data-stu-id="19c4b-213">For more information, see [Ways to migrate multiple email accounts to Office 365](/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
<span data-ttu-id="19c4b-214">如果不同的 PST 檔案需匯入到不同的目標信箱，匯入程序會同時進行；換句話說，系統會同時匯入每個 PST/信箱組合。</span><span class="sxs-lookup"><span data-stu-id="19c4b-214">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="19c4b-215">同樣地，如果多個 PST 檔案匯入到相同的信箱，則會同時匯入。</span><span class="sxs-lookup"><span data-stu-id="19c4b-215">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="19c4b-216">PST 匯入處理程序如何處理重複的電子郵件項目?</span><span class="sxs-lookup"><span data-stu-id="19c4b-216">**How does the PST import process handle duplicate email items?**</span></span>

<span data-ttu-id="19c4b-217">PST 匯入處理程序會檢查重複的項目，如果目標資料夾、目標信箱或目標封存中已有相同項目，則不會將資料從 PST 檔案複製到信箱或封存。</span><span class="sxs-lookup"><span data-stu-id="19c4b-217">The PST import process checks for duplicate items and doesn't copy the items from a PST file to the mailbox or archive if a matching item exists in the target folder in the target mailbox or target archive.</span></span> <span data-ttu-id="19c4b-218">如果您重新匯入同一個 PST 檔案，並指定與前一個匯入工作指定之資料夾不同的目標資料夾 (使用 PST 匯入對應檔案中的 TargetRootFolder 屬性)，則 PST 檔案中的所有項目將會重新匯入。</span><span class="sxs-lookup"><span data-stu-id="19c4b-218">If you reimport the same PST file and specify a different target folder (using the TargetRootFolder property in the PST import mapping file) than the one you specified in a previous import job, all items in the PST file will be reimported.</span></span>
 
 <span data-ttu-id="19c4b-219">**匯入 PST 檔案時，是否有郵件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-219">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="19c4b-220">是。</span><span class="sxs-lookup"><span data-stu-id="19c4b-220">Yes.</span></span> <span data-ttu-id="19c4b-221">如果 PST 檔案包含大於 150 MB 的信箱項目，該項目會在匯入程序執行時略過。</span><span class="sxs-lookup"><span data-stu-id="19c4b-221">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="19c4b-222">**PST 檔案匯入 Microsoft 365 信箱時是否會保留訊息屬性 (例如訊息的傳送或接收時間、收件者清單、和其他屬性)？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-222">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to a Microsoft 365 mailbox?**</span></span>
  
<span data-ttu-id="19c4b-223">是。</span><span class="sxs-lookup"><span data-stu-id="19c4b-223">Yes.</span></span> <span data-ttu-id="19c4b-224">匯入程序不會變更任何原始的訊息中繼資料。</span><span class="sxs-lookup"><span data-stu-id="19c4b-224">The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="19c4b-225">**針對我要匯入至信箱的 PST 檔案，其資料夾階層數是否有上限？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-225">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="19c4b-p131">是。您無法匯入具有 300 或更多巢狀資料夾階層的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="19c4b-p131">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="19c4b-228">**我是否可以使用網路上傳將 PST 檔案匯入 Office 365 中的非作用中的信箱？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-228">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="19c4b-229">是，我們現已推出這項功能。</span><span class="sxs-lookup"><span data-stu-id="19c4b-229">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="19c4b-230">**我是否可以使用網路上傳將 PST 檔案匯入 Exchange 混合式部署中的線上封存信箱？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-230">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="19c4b-231">是，我們現已推出這項功能。</span><span class="sxs-lookup"><span data-stu-id="19c4b-231">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="19c4b-232">**我是否可以使用網路上傳方式將 PST 檔匯入 Exchange Online 的公用資料夾？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-232">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="19c4b-233">否，您無法將 PST 檔案匯入公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="19c4b-233">No, you can't import PST files to public folders.</span></span>
  
### <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="19c4b-234">使用磁碟機寄送來匯入 PST 檔案</span><span class="sxs-lookup"><span data-stu-id="19c4b-234">Using drive shipping to import PST files</span></span>

 <span data-ttu-id="19c4b-235">**必須具備哪些權限才能在 Office365 匯入服務中建立匯入工作？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-235">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="19c4b-236">您必須獲派信箱匯入匯出角色，才能將 PST 檔案匯入 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="19c4b-236">You have to be assigned the Mailbox Import Export role to import PST files to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="19c4b-237">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="19c4b-237">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="19c4b-238">You can add the Mailbox Import Export role to the Organization Management role group.</span><span class="sxs-lookup"><span data-stu-id="19c4b-238">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="19c4b-239">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span><span class="sxs-lookup"><span data-stu-id="19c4b-239">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="19c4b-240">如需詳細資訊，請參閱[管理 Exchange Online 中的角色](/Exchange/permissions-exo/role-groups)之＜新增角色至角色群組＞或＜建立角色群組＞一節。</span><span class="sxs-lookup"><span data-stu-id="19c4b-240">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups).</span></span>
  
<span data-ttu-id="19c4b-241">此外，若要在安全性與合規性中心建立匯入工作，必須符合以下其中一個條件：</span><span class="sxs-lookup"><span data-stu-id="19c4b-241">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="19c4b-242">您必須在 Exchange Online 中獲派郵件收件者角色。</span><span class="sxs-lookup"><span data-stu-id="19c4b-242">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="19c4b-243">根據預設，這個角色會指派給組織管理及收件者管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="19c4b-243">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="19c4b-244">或者</span><span class="sxs-lookup"><span data-stu-id="19c4b-244">Or</span></span>
    
- <span data-ttu-id="19c4b-245">您必須是組織中的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="19c4b-245">You have to be a global administrator in your organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="19c4b-246">建議您在 Exchange Online 中建立新的角色群組，專門用來將 PST 檔案匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="19c4b-246">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="19c4b-247">若要獲得匯入 PST 檔案所需的最低權限等級，請將信箱匯入匯出及郵件收件者角色指派到新的角色群組，然後新增成員。</span><span class="sxs-lookup"><span data-stu-id="19c4b-247">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="19c4b-248">**哪些地區提供磁碟機寄送服務？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-248">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="19c4b-249">磁碟機寄送的服務範圍目前包括美國、加拿大、巴西、英國、歐洲、印度、東亞、東南亞、日本、大韓民國和澳洲。</span><span class="sxs-lookup"><span data-stu-id="19c4b-249">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia.</span></span> <span data-ttu-id="19c4b-250">我們會盡快在更多地區提供磁碟機寄送服務。</span><span class="sxs-lookup"><span data-stu-id="19c4b-250">Drive shipping will be available in more regions soon.</span></span>

> [!NOTE]
> <span data-ttu-id="19c4b-251">目前在德國和瑞士不開放使用磁碟機寄送匯入 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="19c4b-251">At this time, drive shipping to import PST files is not available in Germany and Switzerland.</span></span> <span data-ttu-id="19c4b-252">當這些國家/地區開放磁碟機寄送時，將會更新此常見問題。</span><span class="sxs-lookup"><span data-stu-id="19c4b-252">This FAQ will be updated when drive shipping is available in these countries.</span></span>
  
 <span data-ttu-id="19c4b-253">**有哪些商業授權合約支援磁碟機寄送？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-253">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="19c4b-254">Microsoft Enterprise Agreement (EA) 提供將 PST 檔案匯入至 Microsoft 365 的磁碟機寄送服務。</span><span class="sxs-lookup"><span data-stu-id="19c4b-254">Drive shipping to import PST files to Microsoft 365 is available through a Microsoft Enterprise Agreement (EA).</span></span> <span data-ttu-id="19c4b-255">Microsoft Products and Services Agreement (MPSA) 則沒有提供磁碟機寄送。</span><span class="sxs-lookup"><span data-stu-id="19c4b-255">Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="19c4b-256">**使用磁碟機寄送將 PST 檔案匯入至 Microsoft 365 的費用為何？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-256">**What is the pricing for using drive shipping to import PST files to Microsoft 365?**</span></span>
  
<span data-ttu-id="19c4b-257">使用磁碟機寄送將 PST 檔案匯入至 Microsoft 365 信箱的費用為每 GB 的資料 $2 美元。</span><span class="sxs-lookup"><span data-stu-id="19c4b-257">The cost to use drive shipping to import PST files to Microsoft 365 mailboxes is $2 USD per GB of data.</span></span> <span data-ttu-id="19c4b-258">例如，假設您寄送的硬碟含有 1,000 GB (即 1 TB) 的 PST 檔案，則費用為 $2,000 美元。</span><span class="sxs-lookup"><span data-stu-id="19c4b-258">For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD.</span></span> <span data-ttu-id="19c4b-259">您可以與夥伴合作來支付匯入費用。</span><span class="sxs-lookup"><span data-stu-id="19c4b-259">You can work with a partner to pay the import fee.</span></span> <span data-ttu-id="19c4b-260">如需有關尋找合作夥伴的資訊，請參閱[尋找您的 Microsoft 365 合作夥伴或轉售商](../admin/manage/find-your-partner-or-reseller.md)。</span><span class="sxs-lookup"><span data-stu-id="19c4b-260">For information about finding a partner, see [Find your Microsoft partner or reseller](../admin/manage/find-your-partner-or-reseller.md).</span></span>
  
 <span data-ttu-id="19c4b-261">**哪些類型的硬碟支援磁碟機寄送？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-261">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="19c4b-262">Office 365 匯入服務只支援使用 2.5 吋固態硬碟 (SSD)，或是 2.5 吋或 3.5 吋 SATA II/III 內接式硬碟。</span><span class="sxs-lookup"><span data-stu-id="19c4b-262">Only 2.5-inch solid-state drives (SSDs) or 2.5 inch or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service.</span></span> <span data-ttu-id="19c4b-263">您可以使用最多 10 TB 的硬碟。</span><span class="sxs-lookup"><span data-stu-id="19c4b-263">You can use hard drives up to 10 TB.</span></span> <span data-ttu-id="19c4b-264">匯入作業時，只會處理硬碟上的第一個資料磁碟區。</span><span class="sxs-lookup"><span data-stu-id="19c4b-264">For import jobs, only the first data volume on the hard drive will be processed.</span></span> <span data-ttu-id="19c4b-265">資料磁碟區必須為 NTFS 格式。</span><span class="sxs-lookup"><span data-stu-id="19c4b-265">The data volume must be formatted with NTFS.</span></span> <span data-ttu-id="19c4b-266">若要將資料複製到硬碟，您可以直接使用 2.5 吋 SSD 或是 2.5 吋或 3.5 吋 SATA II/III 連接器進行連接，或者使用外接式 2.5 吋 SSD 或是 2.5 吋或 3.5 吋 SATA II/III USB 轉接頭進行外接。</span><span class="sxs-lookup"><span data-stu-id="19c4b-266">When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 inch or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 inch or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="19c4b-267">Office 365 匯入服務不支援隨附內建 USB 轉接頭的外接式硬碟。</span><span class="sxs-lookup"><span data-stu-id="19c4b-267">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service.</span></span> <span data-ttu-id="19c4b-268">此外，位於外部硬碟外殼內的碟無法使用。</span><span class="sxs-lookup"><span data-stu-id="19c4b-268">Additionally, the disk inside the casing of an external hard drive can't be used.</span></span> <span data-ttu-id="19c4b-269">請不要使用外接式硬碟。</span><span class="sxs-lookup"><span data-stu-id="19c4b-269">Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="19c4b-270">**可以寄送幾個硬碟來進行單一匯入工作？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-270">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="19c4b-271">最多可以寄送 10 個硬碟來進行單一匯入工作。</span><span class="sxs-lookup"><span data-stu-id="19c4b-271">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="19c4b-272">**寄送硬碟之後，需要多久的時間才會送達 Microsoft 資料中心？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-272">**After I ship my hard drive, how long does it take to get to the Microsoft datacenter?**</span></span>
  
<span data-ttu-id="19c4b-p141">這取決於幾個要素，例如您與 Microsoft 資料中心之間的距離，以及您使用什麼類型的運送選項來寄送硬碟 (例如，隔天送達、兩日送達或陸地運送)。大多數貨運公司提供追蹤號碼，讓您可以追蹤運送狀態。</span><span class="sxs-lookup"><span data-stu-id="19c4b-p141">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="19c4b-275">**硬碟送達 Microsoft 資料中心後，需要多久的時間才能將我的 PST 檔案上傳到 Azure？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-275">**After my hard drive arrives at the Microsoft datacenter, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="19c4b-276">硬碟送達 Microsoft 資料中心後，需要 7 到 10 個工作天，才能將 PST 檔案上傳到貴組織的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="19c4b-276">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Azure Storage location for your organization.</span></span> <span data-ttu-id="19c4b-277">PST 檔案會上傳到名為 `ingestiondata` 的 Azure Blob 容器。</span><span class="sxs-lookup"><span data-stu-id="19c4b-277">The PST files will be uploaded to an Azure blob container named `ingestiondata`.</span></span> 
  
 <span data-ttu-id="19c4b-278">**需要多久的時間才能將 PST 檔案匯入信箱？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-278">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="19c4b-279">PST 檔案上傳到 Azure 儲存體區域之後，Microsoft 365 會以安全的方式分析 PST 檔案中的資料，以識別 PST 檔案所含項目的存留期和各種訊息類型。</span><span class="sxs-lookup"><span data-stu-id="19c4b-279">After the PST files are uploaded to the Azure Storage area, Microsoft 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files.</span></span> <span data-ttu-id="19c4b-280">這項分析程序完成後，您就可以選擇匯入 PST 檔案中的所有資料，或設定篩選器來控制要匯入的資料。</span><span class="sxs-lookup"><span data-stu-id="19c4b-280">When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported.</span></span> <span data-ttu-id="19c4b-281">開始匯入工作之後，PST 會以每天至少 24 GB 的速率匯入至 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="19c4b-281">After you start the import job, a PST file is imported to a Microsoft 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="19c4b-282">如果這樣的速率不符您的需求，您可以考慮其他將電子郵件資料移轉到 Microsoft 365 的方法。</span><span class="sxs-lookup"><span data-stu-id="19c4b-282">If this rate doesn't meet your needs, you might consider other methods to get email data into Microsoft 365.</span></span> <span data-ttu-id="19c4b-283">如需詳細資訊，請參閱[將多個電子郵件帳戶移轉到 Microsoft 365 的方法](/Exchange/mailbox-migration/mailbox-migration)。</span><span class="sxs-lookup"><span data-stu-id="19c4b-283">For more information, see [Ways to migrate multiple email accounts to Microsoft 365](/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
<span data-ttu-id="19c4b-284">如果不同的 PST 檔案需匯入到不同的目標信箱，匯入程序會同時進行；換句話說，系統會同時匯入每個 PST/信箱組合。</span><span class="sxs-lookup"><span data-stu-id="19c4b-284">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="19c4b-285">同樣地，如果多個 PST 檔案匯入到相同的信箱，則會同時匯入。</span><span class="sxs-lookup"><span data-stu-id="19c4b-285">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="19c4b-286">**Microsoft 將我的 PST 檔案上傳到 Azure 之後，這些檔案會在 Azure 中保留多久的時間才會刪除？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-286">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="19c4b-287">貴組織的 Azure 儲存體位置 (儲存在名為 `ingestiondata` 的 Blob 容器) 中的所有 PST 檔案，會在最新的匯入工作於安全性與合規性中心的 [匯入 PST 檔案] 頁面上建立完成的 30 天後遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="19c4b-287">All PST files in the Azure Storage location for your organization (in blob container named `ingestiondata`), are deleted 30 days after the most recent import job was created on the **Import PST files** page in the Security & Compliance Center.</span></span> 
  
<span data-ttu-id="19c4b-288">這也表示 PST 檔案從 Azure 儲存體區域刪除之後，安全性與合規性中心內完整匯入工作的檔案清單中就不會顯示這些檔案。</span><span class="sxs-lookup"><span data-stu-id="19c4b-288">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="19c4b-289">即使匯入工作仍然列在安全性與合規性中心的 [匯入 PST 檔案] 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。</span><span class="sxs-lookup"><span data-stu-id="19c4b-289">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="19c4b-290">**哪些版本的 PST 檔案格式支援匯入至 Microsoft 365？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-290">**What version of the PST file format is supported for importing to Microsoft 365?**</span></span>
  
<span data-ttu-id="19c4b-291">有兩個版本的 PST 檔案格式支援此作業：ANSI 和 Unicode。</span><span class="sxs-lookup"><span data-stu-id="19c4b-291">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="19c4b-292">我們建議您使用 Unicode PST 檔案格式來匯入檔案。</span><span class="sxs-lookup"><span data-stu-id="19c4b-292">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="19c4b-293">不過，使用 ANSI PST 檔案格式的檔案 (例如，使用雙位元組字元集 (DBCS) 語言的檔案) 也可以匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="19c4b-293">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Microsoft 365.</span></span> <span data-ttu-id="19c4b-294">如需有關匯入 ANSI PST 檔案的詳細資訊，請參閱[使用磁碟機寄送將組織 PST 檔案匯入 Microsoft 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file) 中的步驟 3。</span><span class="sxs-lookup"><span data-stu-id="19c4b-294">For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import your organization PST files to Microsoft 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="19c4b-295">此外，Outlook 2007 和更新版本的 PST 檔案也可以匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="19c4b-295">Additionally, PST files from Outlook 2007 and later versions can be imported to Microsoft 365.</span></span>
  
 <span data-ttu-id="19c4b-296">**匯入 PST 檔案時，是否有郵件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-296">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="19c4b-297">是。</span><span class="sxs-lookup"><span data-stu-id="19c4b-297">Yes.</span></span> <span data-ttu-id="19c4b-298">如果 PST 檔案包含大於 150 MB 的信箱項目，該項目會在匯入程序執行時略過。</span><span class="sxs-lookup"><span data-stu-id="19c4b-298">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
  <span data-ttu-id="19c4b-299">PST 匯入處理程序如何處理重複的電子郵件項目?</span><span class="sxs-lookup"><span data-stu-id="19c4b-299">**How does the PST import process handle duplicate email items?**</span></span>

<span data-ttu-id="19c4b-300">PST 匯入處理程序會檢查重複的項目，如果目標資料夾、目標信箱或目標封存中已有相同項目，則不會將資料從 PST 檔案複製到信箱或封存。</span><span class="sxs-lookup"><span data-stu-id="19c4b-300">The PST import process checks for duplicate items and doesn't copy the items from a PST file to the mailbox or archive if a matching item exists in the target folder in the target mailbox or target archive.</span></span> <span data-ttu-id="19c4b-301">如果您重新匯入同一個 PST 檔案，並指定與前一個匯入工作指定之資料夾不同的目標資料夾 (使用 PST 匯入對應檔案中的 TargetRootFolder 屬性)，則 PST 檔案中的所有項目將會重新匯入。</span><span class="sxs-lookup"><span data-stu-id="19c4b-301">If you reimport the same PST file and specify a different target folder (using the TargetRootFolder property in the PST import mapping file) than the one you specified in a previous import job, all items in the PST file will be reimported.</span></span>
 
 <span data-ttu-id="19c4b-302">**PST 檔案匯入 Microsoft 365 信箱時是否會保留訊息屬性 (例如訊息的傳送或接收時間、收件者清單、和其他屬性)？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-302">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to a Microsoft 365 mailbox?**</span></span>
  
<span data-ttu-id="19c4b-303">是。</span><span class="sxs-lookup"><span data-stu-id="19c4b-303">Yes.</span></span> <span data-ttu-id="19c4b-304">匯入程序不會變更任何原始的訊息中繼資料</span><span class="sxs-lookup"><span data-stu-id="19c4b-304">The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="19c4b-305">**針對我要匯入至信箱的 PST 檔案，其資料夾階層數是否有上限？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-305">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="19c4b-p150">是。您無法匯入具有 300 或更多巢狀資料夾階層的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="19c4b-p150">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="19c4b-308">**我是否可以使用磁碟機寄送將 PST 檔案匯入至 Microsoft 365 中的非作用中的信箱？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-308">**Can I use drive shipping to import PST files to an inactive mailbox in Microsoft 365?**</span></span>
  
<span data-ttu-id="19c4b-309">是，我們現已推出這項功能。</span><span class="sxs-lookup"><span data-stu-id="19c4b-309">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="19c4b-310">**我是否可以使用磁碟機寄送將 PST 檔案匯入 Exchange 混合式部署中的線上封存信箱？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-310">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="19c4b-311">是，我們現已推出這項功能。</span><span class="sxs-lookup"><span data-stu-id="19c4b-311">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="19c4b-312">**我是否可以使用磁碟機寄送方式將 PST 檔案匯入 Exchange Online 的公用資料夾？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-312">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="19c4b-313">否，您無法將 PST 檔案匯入公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="19c4b-313">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="19c4b-314">**Microsoft 是否可以先將硬碟清空再寄回給我？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-314">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="19c4b-p151">否，Microsoft 無法先將硬碟清空再寄回給客戶。硬碟會以 Microsoft 當初收到的狀態寄回給您。</span><span class="sxs-lookup"><span data-stu-id="19c4b-p151">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="19c4b-317">**Microsoft 是否可以先將硬碟銷毀再寄回給我？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-317">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="19c4b-p152">否，Microsoft 不能破壞您的硬碟。硬碟會以 Microsoft 當初收到的狀態寄回給您。</span><span class="sxs-lookup"><span data-stu-id="19c4b-p152">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="19c4b-320">**哪些快遞服務支援將硬碟寄回客戶？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-320">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="19c4b-p153">如果您是位於美國或歐洲地區的客戶，Microsoft 會使用 FedEx 將硬碟寄回給您。針對所有其他區域，Microsoft 則會使用 DHL。</span><span class="sxs-lookup"><span data-stu-id="19c4b-p153">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="19c4b-323">**將硬碟寄回需要多少費用？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-323">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="19c4b-p154">實際的寄回費用取決於您將硬碟寄出的所在地區與 Microsoft 資料中心之間的距離。Microsoft 會從您的 FedEx 或 DHL 帳戶收取硬碟寄回費用。寄回費用需由您自行承擔。</span><span class="sxs-lookup"><span data-stu-id="19c4b-p154">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="19c4b-327">**我是否能使用自訂運送服務 (例如 FedEx 自訂運送) 將我的硬碟寄給 Microsoft？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-327">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="19c4b-328">是。</span><span class="sxs-lookup"><span data-stu-id="19c4b-328">Yes.</span></span>
  
 <span data-ttu-id="19c4b-329">**如果我需要將硬碟寄到其他國家/地區，我需要採取什麼動作嗎？**</span><span class="sxs-lookup"><span data-stu-id="19c4b-329">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="19c4b-p155">您寄給 Microsoft 的硬碟可能會跨國際邊界。在這種情況下，您必須負責確保硬碟和當中的資料可依據相關法律進口和/或出口。寄送硬碟之前，請與您的顧問確認磁碟機和當中的資料可以合法地寄到指定的 Microsoft 資料中心，以確保 Microsoft 能夠及時收到您的硬碟。</span><span class="sxs-lookup"><span data-stu-id="19c4b-p155">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>