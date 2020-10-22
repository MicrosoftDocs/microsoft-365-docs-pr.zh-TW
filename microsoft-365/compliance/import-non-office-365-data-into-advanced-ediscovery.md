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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be30daa35770247a9dd342b88093872083075547
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636950"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a><span data-ttu-id="ced84-103">匯入非 Microsoft 365 內容以取得 Advanced eDiscovery (傳統) 分析</span><span class="sxs-lookup"><span data-stu-id="ced84-103">Import non-Microsoft 365 content for Advanced eDiscovery (classic) analysis</span></span>

<span data-ttu-id="ced84-104">並非所有您需要使用高級 eDiscovery 進行分析的檔，都將會在 Microsoft 365 中活。</span><span class="sxs-lookup"><span data-stu-id="ced84-104">Not all documents that you may need to analyze with Advanced eDiscovery will live in Microsoft 365.</span></span> <span data-ttu-id="ced84-105">使用高級 eDiscovery 的非 Microsoft 365 內容匯入功能，您可以將不在 Microsoft (365 中的檔上傳) 至連結的情況下，Azure storage blob 和使用 Advanced eDiscovery 進行分析的情況下，則不會使用 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="ced84-105">With the Non-Microsoft 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Microsoft 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="ced84-106">此程式顯示如何將您的非 Microsoft 365 檔放入高級 eDiscovery 以進行分析。</span><span class="sxs-lookup"><span data-stu-id="ced84-106">This procedure shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ced84-p102">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="ced84-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ced84-109">您可以購買非 Microsoft 365 內容的高級 eDiscovery 資料儲存區訂閱。</span><span class="sxs-lookup"><span data-stu-id="ced84-109">You can purchase an Advanced eDiscovery data storage add-on subscription for your non-Microsoft 365 content.</span></span> <span data-ttu-id="ced84-110">這只適用于使用高級 eDiscovery 進行分析的內容。</span><span class="sxs-lookup"><span data-stu-id="ced84-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="ced84-111">遵循 [為商務用 Microsoft 365 購買或編輯附加](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) 元件中的步驟，並購買「Advanced eDiscovery 儲存」附加元件。</span><span class="sxs-lookup"><span data-stu-id="ced84-111">Follow the steps in [Buy or edit an add-on for Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) and purchase the Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="ced84-112">上傳非 Office 365 內容的需求</span><span class="sxs-lookup"><span data-stu-id="ced84-112">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="ced84-113">使用此程式所述的「上傳非 Office 365」功能，需要具備下列專案：</span><span class="sxs-lookup"><span data-stu-id="ced84-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="ced84-114">具有高級合規性附加元件或 E5 訂閱的 Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="ced84-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>
    
- <span data-ttu-id="ced84-115">所有非 Office 365 內容的保管人，都必須具備具有高級合規性附加元件或 E5 授權的 E3。</span><span class="sxs-lookup"><span data-stu-id="ced84-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>
    
- <span data-ttu-id="ced84-116">現有的 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="ced84-116">An existing eDiscovery case.</span></span>
    
- <span data-ttu-id="ced84-117">所有檔案，可將收集到的資料夾中，每個保管人都有一個資料夾，而且資料夾的名稱為  *alias@domainname*  的此格式。</span><span class="sxs-lookup"><span data-stu-id="ced84-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="ced84-118">*Alias@domainname*必須是使用者 Office 365 別名和網域。</span><span class="sxs-lookup"><span data-stu-id="ced84-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="ced84-119">您可以將所有  *alias@domainname*  資料夾收集至根資料夾。</span><span class="sxs-lookup"><span data-stu-id="ced84-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="ced84-120">根資料夾只能包含  *alias@domainname*  資料夾，根資料夾中一定沒有鬆散檔案。</span><span class="sxs-lookup"><span data-stu-id="ced84-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder.</span></span>
    
- <span data-ttu-id="ced84-121">電子檔探索管理員或 eDiscovery 管理員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="ced84-121">An account that is either an eDiscovery Manager or eDiscovery Administrator.</span></span>
    
- <span data-ttu-id="ced84-122">在具有非 Office 365 內容資料夾結構存取權的電腦上安裝[Microsoft Azure Storage Tool 工具](https://aka.ms/downloadazcopy)。</span><span class="sxs-lookup"><span data-stu-id="ced84-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="ced84-123">將非 Office 365 內容上傳至高級電子檔探索</span><span class="sxs-lookup"><span data-stu-id="ced84-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>


1. <span data-ttu-id="ced84-124">以 eDiscovery 管理員或 eDiscovery 管理員的身分開啟 **ediscovery**，然後開啟非 Office 365 資料將上傳至的情況。</span><span class="sxs-lookup"><span data-stu-id="ced84-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="ced84-125">如果您需要建立案例，請參閱在 [安全性與 &amp; 合規性中心管理 eDiscovery 案例](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="ced84-125">If you need to create a case, see [Manage eDiscovery cases in the Security &amp; Compliance Center](ediscovery-cases.md).</span></span>
    
2. <span data-ttu-id="ced84-126">按一下 [ **切換至高級 eDiscovery**]。</span><span class="sxs-lookup"><span data-stu-id="ced84-126">Click **Switch to Advanced eDiscovery**.</span></span>

3. <span data-ttu-id="ced84-127">從功能表中選取 [ **複查集** ]。</span><span class="sxs-lookup"><span data-stu-id="ced84-127">Select **Review Sets** from the menu.</span></span>

4. <span data-ttu-id="ced84-128">選取現有的複查集，或選擇 [ **新增複查集**]。</span><span class="sxs-lookup"><span data-stu-id="ced84-128">Select an existing Review Set or choose **Add Review Set**.</span></span>

5. <span data-ttu-id="ced84-129">選取 [ **管理審閱集**]。</span><span class="sxs-lookup"><span data-stu-id="ced84-129">Select **Manage review set**.</span></span>

6. <span data-ttu-id="ced84-130">在 [非 Office 365 數據卡] 中，選取 [ **View 上傳**]。</span><span class="sxs-lookup"><span data-stu-id="ced84-130">In the Non-Office 365 data card, select **View Uploads**.</span></span>

7. <span data-ttu-id="ced84-131">選擇 [ **上傳** 檔案] 以啟動 [檔案上傳] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="ced84-131">Choose **Upload files** to start the file upload wizard.</span></span>

8. <span data-ttu-id="ced84-132">第一個索引標籤為 **1。準備步驟**。</span><span class="sxs-lookup"><span data-stu-id="ced84-132">The first tab is **1. Prepare step**.</span></span> <span data-ttu-id="ced84-133">選取 **[下一步：上傳檔案]**。</span><span class="sxs-lookup"><span data-stu-id="ced84-133">Select **Next: Upload files**.</span></span>

9. <span data-ttu-id="ced84-134">在 **2。上傳** 檔案] 索引標籤若尚未這麼做，則會提示您下載 AzCopy.exe （如果尚未這麼做），然後提供檔案位置的路徑。</span><span class="sxs-lookup"><span data-stu-id="ced84-134">On the **2. Upload files** tab you will be prompted to download AzCopy.exe if you have not done so already, and then to provide the path to the file location.</span></span> <span data-ttu-id="ced84-135">例如， `C:\Upload`  將會提供執行 AzCopy.exe 的命令。</span><span class="sxs-lookup"><span data-stu-id="ced84-135">For example, `C:\Upload`  will give you the command to execute AzCopy.exe.</span></span> <span data-ttu-id="ced84-136">使用 `C:\Upload` ，您將會看到：</span><span class="sxs-lookup"><span data-stu-id="ced84-136">Using `C:\Upload`, you will see:</span></span>

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. <span data-ttu-id="ced84-137">開啟 [命令提示字元] 視窗，並執行 AzCopy.exe 命令，將資料匯入 Azure。</span><span class="sxs-lookup"><span data-stu-id="ced84-137">Open a command prompt window and execute the AzCopy.exe command to import the data into Azure.</span></span> <span data-ttu-id="ced84-138">一旦載入所有資料，請選取 **[下一步：處理檔案]**。</span><span class="sxs-lookup"><span data-stu-id="ced84-138">Once it has loaded all of the data, select **Next: Process files**.</span></span>

11. <span data-ttu-id="ced84-139">下一個 tab 鍵是 **3。處理** 檔案，您會看到擁有相關資料的保管人，也會顯示要匯入資料的進度。</span><span class="sxs-lookup"><span data-stu-id="ced84-139">The next tab is **3. Process files** where you will see the custodians that have data associated with them and will also show you the progress of the data being imported.</span></span>
        
    <span data-ttu-id="ced84-140">如需 Azcopy 語法的詳細資訊，請參閱 [使用 Windows 上的 AzCopy 傳輸資料](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="ced84-140">For more information on Azcopy syntax, see [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span> 
    
    <span data-ttu-id="ced84-141">如需有關高級 eDiscovery 處理的詳細資訊，請參閱在 [Advanced ediscovery (傳統) 中執行進程模組和載入資料 ](run-the-process-module-and-load-data-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="ced84-141">For more details on Advanced eDiscovery Processing, see [Run the Process module and load data in Advanced eDiscovery (classic)](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="ced84-142">每位使用者都必須有一個根資料夾，而且資料夾名稱必須是 <b>alias@domainname</b>  格式。</span><span class="sxs-lookup"><span data-stu-id="ced84-142">There must be one root folder per user and the folder name must be in the <b>alias@domainname</b>  format.</span></span> 
   
    > [!IMPORTANT]
    > <span data-ttu-id="ced84-143">在高級 eDiscovery 中成功處理容器後，您就無法再將新內容新增至 Azure 中的 SAS 儲存體。</span><span class="sxs-lookup"><span data-stu-id="ced84-143">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="ced84-144">如果您收集其他內容，而且想要將其新增至案例以進行高級 eDiscovery 分析，您必須建立新的 **非 Office 365 資料** 容器，並重複此程式。</span><span class="sxs-lookup"><span data-stu-id="ced84-144">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="ced84-145">如果容器  *由於資料夾命名問題而無法順利處理*  ，而您又修正問題，則您仍然需要使用本文中的程式建立新的容器，並重新連線並上傳。</span><span class="sxs-lookup"><span data-stu-id="ced84-145">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span>
