---
title: 匯入非 Office 365 進階電子文件探索分析內容
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: 如何步驟以匯入內容，不會儲存在 O365 到 Azure blob，讓它可以與 AeD 分析
ms.openlocfilehash: 7a06bff3abe70e58ab08edcc456bc167229b05f2
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072980"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a><span data-ttu-id="d2342-103">匯入非 Office 365 進階電子文件探索分析內容</span><span class="sxs-lookup"><span data-stu-id="d2342-103">Import non-Office 365 content for Advanced eDiscovery analysis</span></span>

<span data-ttu-id="d2342-104">並非所有文件，您可能需要與 Office 365 進階電子文件探索分析會存在於 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="d2342-104">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="d2342-105">使用非 Office 365 內容匯入您可以上傳文件，不到案例的連結、 Azure 儲存體 blob live （除了 PST 檔案） 的 Office 365 中並分析其與進階電子文件的進階電子文件中的功能。</span><span class="sxs-lookup"><span data-stu-id="d2342-105">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="d2342-106">此程序將示範如何將非 Office 365 文件移入進階電子文件探索進行分析。</span><span class="sxs-lookup"><span data-stu-id="d2342-106">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2342-p102">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="d2342-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d2342-109">您可以購買 Office 365 進階電子文件探索資料儲存空間] 附加元件訂閱的非 Office 365 內容。</span><span class="sxs-lookup"><span data-stu-id="d2342-109">You can purchase an Office 365 Advanced eDiscovery data storage add-on subscription for your non-Office 365 content.</span></span> <span data-ttu-id="d2342-110">這是專門供進行分析使用進階電子文件的內容。</span><span class="sxs-lookup"><span data-stu-id="d2342-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="d2342-111">請遵循[購買或編輯和商務用 Office 365 的附加元件形式](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6)中的步驟及購買 Office 365 進階電子文件探索儲存附加元件。</span><span class="sxs-lookup"><span data-stu-id="d2342-111">Follow the steps in [Buy or edit and add-on for Office 365 for business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) and purchase the Office 365 Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="d2342-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="d2342-112">Before you begin</span></span>

<span data-ttu-id="d2342-113">使用此程序所述的上傳非 Office 365 功能需要您：</span><span class="sxs-lookup"><span data-stu-id="d2342-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="d2342-114">使用進階合規性的附加元件或 E5 訂閱 Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="d2342-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription</span></span>
    
- <span data-ttu-id="d2342-115">將上傳其非 Office 365 內容的所有 custodians 都必須 E3 與進階合規性的附加元件或 E5 授權</span><span class="sxs-lookup"><span data-stu-id="d2342-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses</span></span>
    
- <span data-ttu-id="d2342-116">現有的 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="d2342-116">An existing eDiscovery case</span></span>
    
- <span data-ttu-id="d2342-117">上傳的所有檔案所都收集到資料夾，其中沒有 custodian 每一個資料夾，而且此格式*alias@domainname*中已有該資料夾的名稱。</span><span class="sxs-lookup"><span data-stu-id="d2342-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="d2342-118">*Alias@domainname*必須是 Office 365 的使用者別名及網域。</span><span class="sxs-lookup"><span data-stu-id="d2342-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="d2342-119">您可以收集所有*alias@domainname*資料夾到根資料夾。</span><span class="sxs-lookup"><span data-stu-id="d2342-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="d2342-120">根資料夾只能包含*alias@domainname*資料夾、 根資料夾中必須有任何鬆散檔案</span><span class="sxs-lookup"><span data-stu-id="d2342-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder</span></span> 
    
- <span data-ttu-id="d2342-121">EDiscovery 管理員 」 或 「 eDiscovery 系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="d2342-121">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>
    
- <span data-ttu-id="d2342-122">具有非 Office 365 內容的資料夾結構的存取權的電腦上安裝[Microsoft Azure 儲存體工具](https://aka.ms/downloadazcopy)。</span><span class="sxs-lookup"><span data-stu-id="d2342-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="d2342-123">非 Office 365 內容上傳至進階電子文件</span><span class="sxs-lookup"><span data-stu-id="d2342-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>


1. <span data-ttu-id="d2342-124">EDiscovery 管理員或 eDiscovery 系統管理員，以開啟 [ **eDiscovery**]，並開啟非 Office 365 資料就會上傳到的案例。</span><span class="sxs-lookup"><span data-stu-id="d2342-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="d2342-125">如果您需要建立案例，請參閱[管理 Office 365 安全性中的 eDiscovery 案例&amp;合規性中心](ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="d2342-125">If you need to create a case, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md)</span></span>
    
2. <span data-ttu-id="d2342-126">按一下 [**切換至進階電子文件**</span><span class="sxs-lookup"><span data-stu-id="d2342-126">Click **Switch to Advanced eDiscovery**</span></span>
    
3. <span data-ttu-id="d2342-127">**來源類型**] 下選取 [**非 Office 365 資料**]。</span><span class="sxs-lookup"><span data-stu-id="d2342-127">Under **Source type** select **Non-Office 365 data**.</span></span>
    
4. <span data-ttu-id="d2342-128">按一下 [**新增] 容器**。</span><span class="sxs-lookup"><span data-stu-id="d2342-128">Click **Add container**.</span></span> <span data-ttu-id="d2342-129">名稱容器，並且新增描述。</span><span class="sxs-lookup"><span data-stu-id="d2342-129">Name the container and add a description.</span></span>
    
5. <span data-ttu-id="d2342-130">從其在容器清單中選取新加入的容器，然後複製出現在 [容器] 詳細資料窗格中，然後關閉 [] 窗格中的 URL</span><span class="sxs-lookup"><span data-stu-id="d2342-130">Select the newly added container from the container list and copy the URL that appears in the container details pane and then close the pane</span></span>
    
6. <span data-ttu-id="d2342-131">開啟命令提示字元以系統管理員身分，將目錄變更必須 AzCopy 安裝資料夾...</span><span class="sxs-lookup"><span data-stu-id="d2342-131">Open a command prompt as an administrator and change directory to folder where you have AzCopy installed..</span></span>
    
7. <span data-ttu-id="d2342-132">建構 AzCopy 命令列上傳的檔案，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d2342-132">Construct the AzCopy command line to upload the files like this:</span></span>
    
    <span data-ttu-id="d2342-133">AzCopy /Source: 「*在本機電腦上的根資料夾的完整路徑*」 /Dest: 「*容器 URL，但不是包括？*</span><span class="sxs-lookup"><span data-stu-id="d2342-133">AzCopy /Source:" *full path to root folder on local machine*  " /Dest:"  *container URL up to but not including the ?*</span></span>  <span data-ttu-id="d2342-134">「 /DestSAS: 「*其餘部分來自容器 url？結尾*"/ S</span><span class="sxs-lookup"><span data-stu-id="d2342-134">" /DestSAS:"  *remainder of the container url from the ? to the end*  " /S.</span></span> 
    
    <span data-ttu-id="d2342-135">例如，使用這些值：</span><span class="sxs-lookup"><span data-stu-id="d2342-135">For example, using these values:</span></span> 
    
  - <span data-ttu-id="d2342-136">根資料夾-C:\Collected 資料</span><span class="sxs-lookup"><span data-stu-id="d2342-136">root folder - C:\Collected Data</span></span> 
    
  - <span data-ttu-id="d2342-137">容器 url- https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp; sr = c&amp;si = NonOfficeData15 %7 C 0&amp;簽章 = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA %3d</span><span class="sxs-lookup"><span data-stu-id="d2342-137">container url - https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D</span></span>
    
    <span data-ttu-id="d2342-138">AzCopy 命令列語法為：</span><span class="sxs-lookup"><span data-stu-id="d2342-138">the AzCopy command line syntax would be:</span></span>
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    <span data-ttu-id="d2342-139">如需有關 Azcopy 語法，請參閱[傳輸與 windows AzCopy 的資料](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="d2342-139">For more information on Azcopy syntax see, [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="d2342-140">必須有一個每位使用者根資料夾和資料夾名稱必須是*alias@domainname*格式。</span><span class="sxs-lookup"><span data-stu-id="d2342-140">There must be one root folder per user and the folder name must be in the  *alias@domainname*  format.</span></span> 
  
8. <span data-ttu-id="d2342-141">一旦資料夾完成上傳，切換回進階電子文件。</span><span class="sxs-lookup"><span data-stu-id="d2342-141">Once the folders have finished uploading, switch back to Advanced eDiscovery.</span></span> <span data-ttu-id="d2342-142">在您上傳的資料夾中的內容已準備好在進階電子文件中處理。</span><span class="sxs-lookup"><span data-stu-id="d2342-142">The content in the folders you uploaded is now ready to be processed in Advanced eDiscovery.</span></span> <span data-ttu-id="d2342-143">選取的容器，然後按一下 [處理序] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d2342-143">Select the container and click the Process button.</span></span> <span data-ttu-id="d2342-144">如需詳細資訊，在 [進階電子文件上處理，請[執行處理序模組及載入 Office 365 進階電子文件探索中的資料](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="d2342-144">For more details on Advanced eDiscovery Processing see, [Run the Process module and load data in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d2342-145">一旦成功處理進階電子文件的容器，您將不再能夠將新的內容新增至 Azure 中的 SAS 儲存。</span><span class="sxs-lookup"><span data-stu-id="d2342-145">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="d2342-146">如果您收集其他內容，而且您想要將其新增至進階電子文件探索分析案例，您必須建立新的**非 Office 365 資料**容器，並重複此程序。</span><span class="sxs-lookup"><span data-stu-id="d2342-146">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="d2342-147">如果容器*不會處理成功由於資料夾命名問題*，而且您然後修正問題，您仍然必須建立新的容器，並重新連線並上傳一次使用本文中的程序。</span><span class="sxs-lookup"><span data-stu-id="d2342-147">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span>
