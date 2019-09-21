---
title: 非 Office 365 資料載入辨識項
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
description: ''
ms.openlocfilehash: ee1e6f8a064567126d75b099cc3003e8a4d6a020
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077233"
---
# <a name="load-non-office-365-data-into-evidence"></a><span data-ttu-id="6e9af-102">非 Office 365 資料載入辨識項</span><span class="sxs-lookup"><span data-stu-id="6e9af-102">Load non-Office 365 data into evidence</span></span>

<span data-ttu-id="6e9af-103">並非所有文件，您可能需要與 Office 365 進階電子文件探索分析會存在於 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="6e9af-103">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="6e9af-104">使用非 Office 365 內容匯入您可以上傳文件與不存在於 Office 365 中插入工作集，它會使用進階電子文件探索分析的進階電子文件中的功能。</span><span class="sxs-lookup"><span data-stu-id="6e9af-104">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a working set so it is analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="6e9af-105">此程序將示範如何將非 Office 365 文件移入進階電子文件探索進行分析。</span><span class="sxs-lookup"><span data-stu-id="6e9af-105">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="6e9af-106">進階電子文件為您的組織需要與進階合規性附加元件或 E5 訂閱 Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="6e9af-106">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="6e9af-107">如果您不具有該計劃，並想要再試進階電子文件，您可以註冊 Office 365 企業版 E5 的試用版。</span><span class="sxs-lookup"><span data-stu-id="6e9af-107">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6e9af-108">開始之前</span><span class="sxs-lookup"><span data-stu-id="6e9af-108">Before you begin</span></span>
<span data-ttu-id="6e9af-109">使用此程序所述的上傳非 Office 365 功能需要您：</span><span class="sxs-lookup"><span data-stu-id="6e9af-109">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="6e9af-110">使用進階合規性的附加元件或 E5 訂閱 Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="6e9af-110">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="6e9af-111">將上傳其非 Office 365 內容的所有 custodians 必須都擁有 E3 的進階合規性的附加元件或 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="6e9af-111">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="6e9af-112">現有的 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="6e9af-112">An existing eDiscovery case.</span></span>

- <span data-ttu-id="6e9af-113">上傳的所有檔案所都收集到資料夾，其中沒有 custodian 每一個資料夾，而且此格式*alias@domainname*中已有該資料夾的名稱。</span><span class="sxs-lookup"><span data-stu-id="6e9af-113">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname* .</span></span> <span data-ttu-id="6e9af-114">*Alias@domainname*必須是 Office 365 的使用者別名及網域。</span><span class="sxs-lookup"><span data-stu-id="6e9af-114">The *alias@domainname* must be users Office 365 alias and domain.</span></span> <span data-ttu-id="6e9af-115">您可以收集所有*alias@domainname*資料夾到根資料夾。</span><span class="sxs-lookup"><span data-stu-id="6e9af-115">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="6e9af-116">根資料夾只能包含*alias@domainname*資料夾，必須有任何鬆散檔案的根資料夾中。</span><span class="sxs-lookup"><span data-stu-id="6e9af-116">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="6e9af-117">EDiscovery 管理員或 eDiscovery 管理員 Microsoft Azure 儲存體工具具有存取權的非 Office 365 內容的資料夾結構的電腦上安裝帳戶。</span><span class="sxs-lookup"><span data-stu-id="6e9af-117">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="6e9af-118">安裝 AzCopy，您可以從這裡：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="6e9af-118">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="6e9af-119">非 Office 365 內容上傳至進階電子文件</span><span class="sxs-lookup"><span data-stu-id="6e9af-119">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="6e9af-120">EDiscovery 管理員或 eDiscovery 系統管理員，以開啟 [進階電子文件，然後將上傳到非 Office 365 資料的案例]。</span><span class="sxs-lookup"><span data-stu-id="6e9af-120">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="6e9af-121">按一下 [**工作集**] 索引標籤，然後選取您想要將非 Office 365 資料載入工作集。</span><span class="sxs-lookup"><span data-stu-id="6e9af-121">Click the **Working sets** tab, then select the working set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="6e9af-122">如果您無法建立工作集，您可以立即執行。</span><span class="sxs-lookup"><span data-stu-id="6e9af-122">If you have not already created a working set, you can do so now.</span></span>  <span data-ttu-id="6e9af-123">最後，按一下 [**管理起步設定**然後非 Office 365 資料] 區段中的**檢視上傳**</span><span class="sxs-lookup"><span data-stu-id="6e9af-123">Finally, click **Manage workings set** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="6e9af-124">按一下 [**上傳檔案**] 按鈕來啟動非 Office 365 資料匯入精靈]。</span><span class="sxs-lookup"><span data-stu-id="6e9af-124">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![上傳檔案](media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="6e9af-126">在精靈中的第一個步驟只會準備要上傳檔案的安全 Azure blob。</span><span class="sxs-lookup"><span data-stu-id="6e9af-126">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="6e9af-127">一旦準備 compelted 之後，按一下 [**下一步： 將檔案上傳**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="6e9af-127">Once preparation is compelted, click the **Next: Upload files** button.</span></span>

![非 Office 365 匯入-準備](media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="6e9af-129">在 [**上傳檔案**] 步驟中，指定**的檔案位置路徑**] 中，這是您計劃匯入非 Office 365 資料所在的位置。</span><span class="sxs-lookup"><span data-stu-id="6e9af-129">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="6e9af-130">設定正確的位置可確保正確更新命令 AzCopy。</span><span class="sxs-lookup"><span data-stu-id="6e9af-130">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="6e9af-131">如果您未安裝 AzCopy，您可以從這裡：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="6e9af-131">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="6e9af-132">按一下 [**複製到剪貼簿**] 連結，將複製的預先定義的命令。</span><span class="sxs-lookup"><span data-stu-id="6e9af-132">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="6e9af-133">啟動 windows 命令提示字元中，貼上命令並按 enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="6e9af-133">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="6e9af-134">檔案就會上傳到安全的 Azure blob 儲存的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="6e9af-134">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![非-Office 365 匯入-上傳檔案](media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![非 Office 365 匯入-AzCopy](media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="6e9af-137">最後，傳回回到安全性 & 合規性，並按一下 [**下一步： 處理檔案**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="6e9af-137">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="6e9af-138">這將會引發處理、 文字擷取和編製索引的上傳的檔案。</span><span class="sxs-lookup"><span data-stu-id="6e9af-138">This will initiate processing, text extraction and indexing of the uploaded files.</span></span>  <span data-ttu-id="6e9af-139">您可以追蹤處理以下或在 [**工作**] 索引標籤中的進度。 完成之後，新的檔案則可在工作集。</span><span class="sxs-lookup"><span data-stu-id="6e9af-139">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the working set.</span></span>  <span data-ttu-id="6e9af-140">處理完成後，您可以關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="6e9af-140">Once processing is complete, you can dismiss the wizard.</span></span>

![非-Office 365 匯入的程序檔案](media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

