---
title: 匯入非 Microsoft 365 內容以進行高級 eDiscovery 分析
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
description: 操作方法：將未儲存在 Microsoft 365 中的內容匯入 Azure blob，以便使用 AeD 來進行分析
ms.openlocfilehash: daafcf003ded35868413d99c11ec1bf3941dca9f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634155"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a><span data-ttu-id="3c895-103">匯入非 Microsoft 365 內容以取得 Advanced eDiscovery （傳統）分析</span><span class="sxs-lookup"><span data-stu-id="3c895-103">Import non-Microsoft 365 content for Advanced eDiscovery (classic) analysis</span></span>

<span data-ttu-id="3c895-104">並非所有您需要使用高級 eDiscovery 進行分析的檔，都將會在 Microsoft 365 中活。</span><span class="sxs-lookup"><span data-stu-id="3c895-104">Not all documents that you may need to analyze with Advanced eDiscovery will live in Microsoft 365.</span></span> <span data-ttu-id="3c895-105">使用高級 eDiscovery 的非 Microsoft 365 內容匯入功能，您可以將不在 Microsoft 365 中的檔（PST 檔除外）上傳至連結的情況下，Azure 儲存區 blob 和使用高級 eDiscovery 進行分析。</span><span class="sxs-lookup"><span data-stu-id="3c895-105">With the Non-Microsoft 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Microsoft 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="3c895-106">此程式顯示如何將您的非 Microsoft 365 檔放入高級 eDiscovery 以進行分析。</span><span class="sxs-lookup"><span data-stu-id="3c895-106">This procedure shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3c895-p102">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="3c895-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3c895-109">您可以購買非 Microsoft 365 內容的高級 eDiscovery 資料儲存區訂閱。</span><span class="sxs-lookup"><span data-stu-id="3c895-109">You can purchase an Advanced eDiscovery data storage add-on subscription for your non-Microsoft 365 content.</span></span> <span data-ttu-id="3c895-110">這只適用于使用高級 eDiscovery 進行分析的內容。</span><span class="sxs-lookup"><span data-stu-id="3c895-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="3c895-111">遵循[為商務用 Microsoft 365 購買或編輯附加](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6)元件中的步驟，並購買「Advanced eDiscovery 儲存」附加元件。</span><span class="sxs-lookup"><span data-stu-id="3c895-111">Follow the steps in [Buy or edit an add-on for Microsoft 365 for business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) and purchase the Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="3c895-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="3c895-112">Before you begin</span></span>

<span data-ttu-id="3c895-113">使用此程式所述的「上傳非 Office 365」功能，需要具備下列專案：</span><span class="sxs-lookup"><span data-stu-id="3c895-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="3c895-114">Office 365 E3 含高級合規性增益集或 E5 訂閱</span><span class="sxs-lookup"><span data-stu-id="3c895-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription</span></span>
    
- <span data-ttu-id="3c895-115">所有非 Office 365 內容的保管人，都必須具備具有高級合規性附加元件或 E5 授權的 E3。</span><span class="sxs-lookup"><span data-stu-id="3c895-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses</span></span>
    
- <span data-ttu-id="3c895-116">現有的 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="3c895-116">An existing eDiscovery case</span></span>
    
- <span data-ttu-id="3c895-117">所有檔案，可將收集到的資料夾中，每個保管人都有一個資料夾，而且資料夾的名稱為*alias@domainname*的此格式。</span><span class="sxs-lookup"><span data-stu-id="3c895-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="3c895-118">*Alias@domainname*必須是使用者 Office 365 別名和網域。</span><span class="sxs-lookup"><span data-stu-id="3c895-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="3c895-119">您可以將所有*alias@domainname*資料夾收集至根資料夾。</span><span class="sxs-lookup"><span data-stu-id="3c895-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="3c895-120">根資料夾只能包含*alias@domainname*資料夾，根資料夾中一定沒有鬆散檔案</span><span class="sxs-lookup"><span data-stu-id="3c895-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder</span></span> 
    
- <span data-ttu-id="3c895-121">既可以是 eDiscovery 管理員，也可以是 eDiscovery 管理員的帳戶</span><span class="sxs-lookup"><span data-stu-id="3c895-121">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>
    
- <span data-ttu-id="3c895-122">在具有非 Office 365 內容資料夾結構存取權的電腦上安裝[Microsoft Azure Storage Tool 工具](https://aka.ms/downloadazcopy)。</span><span class="sxs-lookup"><span data-stu-id="3c895-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="3c895-123">將非 Office 365 內容上傳至高級電子檔探索</span><span class="sxs-lookup"><span data-stu-id="3c895-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>


1. <span data-ttu-id="3c895-124">以 eDiscovery 管理員或 eDiscovery 管理員的身分開啟**ediscovery**，然後開啟非 Office 365 資料將上傳至的情況。</span><span class="sxs-lookup"><span data-stu-id="3c895-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="3c895-125">如果您需要建立案例，請參閱[在安全性&amp;與合規性中心管理 eDiscovery 案例](ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="3c895-125">If you need to create a case, see [Manage eDiscovery cases in the Security &amp; Compliance Center](ediscovery-cases.md)</span></span>
    
2. <span data-ttu-id="3c895-126">按一下 [**切換至高級 eDiscovery** ]</span><span class="sxs-lookup"><span data-stu-id="3c895-126">Click **Switch to Advanced eDiscovery**</span></span>
    
3. <span data-ttu-id="3c895-127">在 [**來源類型**] 下，選取 [**非 Office 365 資料**]。</span><span class="sxs-lookup"><span data-stu-id="3c895-127">Under **Source type** select **Non-Office 365 data**.</span></span>
    
4. <span data-ttu-id="3c895-128">按一下 [**新增容器**]。</span><span class="sxs-lookup"><span data-stu-id="3c895-128">Click **Add container**.</span></span> <span data-ttu-id="3c895-129">命名容器並新增描述。</span><span class="sxs-lookup"><span data-stu-id="3c895-129">Name the container and add a description.</span></span>
    
5. <span data-ttu-id="3c895-130">從容器清單中選取新加入的容器，然後複製容器詳細資料窗格中顯示的 URL，然後關閉窗格</span><span class="sxs-lookup"><span data-stu-id="3c895-130">Select the newly added container from the container list and copy the URL that appears in the container details pane and then close the pane</span></span>
    
6. <span data-ttu-id="3c895-131">以系統管理員身分開啟命令提示字元，並將目錄變更為已安裝 AzCopy 的資料夾。</span><span class="sxs-lookup"><span data-stu-id="3c895-131">Open a command prompt as an administrator and change directory to folder where you have AzCopy installed..</span></span>
    
7. <span data-ttu-id="3c895-132">構造 AzCopy 命令列，將檔案上傳如下：</span><span class="sxs-lookup"><span data-stu-id="3c895-132">Construct the AzCopy command line to upload the files like this:</span></span>
    
    <span data-ttu-id="3c895-133">AzCopy/Source：「*本機電腦上根資料夾的完整路徑，* "/Dest："*容器 URL，但未包含？*</span><span class="sxs-lookup"><span data-stu-id="3c895-133">AzCopy /Source:" *full path to root folder on local machine*  " /Dest:"  *container URL up to but not including the ?*</span></span>  <span data-ttu-id="3c895-134">"/DestSAS："*來自「？」的容器 url 的其餘部分。至結束*"/S。</span><span class="sxs-lookup"><span data-stu-id="3c895-134">" /DestSAS:"  *remainder of the container url from the ? to the end*  " /S.</span></span> 
    
    <span data-ttu-id="3c895-135">例如，使用這些值：</span><span class="sxs-lookup"><span data-stu-id="3c895-135">For example, using these values:</span></span> 
    
  - <span data-ttu-id="3c895-136">根資料夾-C:\Collected 資料</span><span class="sxs-lookup"><span data-stu-id="3c895-136">root folder - C:\Collected Data</span></span> 
    
  - <span data-ttu-id="3c895-137">容器 url- https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp; sr = c&amp;Si = NonOfficeData15% 7C0&amp;sig = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3d</span><span class="sxs-lookup"><span data-stu-id="3c895-137">container url - https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D</span></span>
    
    <span data-ttu-id="3c895-138">AzCopy 命令列語法如下：</span><span class="sxs-lookup"><span data-stu-id="3c895-138">the AzCopy command line syntax would be:</span></span>
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    <span data-ttu-id="3c895-139">如需 Azcopy 語法的詳細資訊，請參閱[使用 Windows 上的 AzCopy 傳輸資料](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="3c895-139">For more information on Azcopy syntax see, [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="3c895-140">每位使用者都必須有一個根資料夾，而且資料夾名稱必須是*alias@domainname*格式。</span><span class="sxs-lookup"><span data-stu-id="3c895-140">There must be one root folder per user and the folder name must be in the  *alias@domainname*  format.</span></span> 
  
8. <span data-ttu-id="3c895-141">完成上傳資料夾後，請切換回「高級電子檔探索」。</span><span class="sxs-lookup"><span data-stu-id="3c895-141">Once the folders have finished uploading, switch back to Advanced eDiscovery.</span></span> <span data-ttu-id="3c895-142">您上傳的資料夾內容現在可以在高級 eDiscovery 中處理。</span><span class="sxs-lookup"><span data-stu-id="3c895-142">The content in the folders you uploaded is now ready to be processed in Advanced eDiscovery.</span></span> <span data-ttu-id="3c895-143">選取容器，然後按一下 [處理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="3c895-143">Select the container and click the Process button.</span></span> <span data-ttu-id="3c895-144">如需有關高級 eDiscovery 處理的詳細資訊，請參閱，[在高級 ediscovery 中執行 Process module 和 load data](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="3c895-144">For more details on Advanced eDiscovery Processing see, [Run the Process module and load data in Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3c895-145">在高級 eDiscovery 中成功處理容器後，您就無法再將新內容新增至 Azure 中的 SAS 儲存體。</span><span class="sxs-lookup"><span data-stu-id="3c895-145">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="3c895-146">如果您收集其他內容，而且想要將其新增至案例以進行高級 eDiscovery 分析，您必須建立新的**非 Office 365 資料**容器，並重複此程式。</span><span class="sxs-lookup"><span data-stu-id="3c895-146">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="3c895-147">如果容器*由於資料夾命名問題而無法順利處理*，而您又修正問題，則您仍然需要使用本文中的程式建立新的容器，並重新連線並上傳。</span><span class="sxs-lookup"><span data-stu-id="3c895-147">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span>
