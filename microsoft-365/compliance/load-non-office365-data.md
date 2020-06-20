---
title: 將非 Microsoft 365 資料載入至證據
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
description: 瞭解如何使用非 Office 365 內容匯入功能，將非 Office 365 檔上傳至資料調查中的證據。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 9bfebc6aad9bc37d7d78ec4a0d50e6de967ac7d1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815480"
---
# <a name="load-non-microsoft-365-data-into-evidence"></a><span data-ttu-id="75d4e-103">將非 Microsoft 365 資料載入至證據</span><span class="sxs-lookup"><span data-stu-id="75d4e-103">Load non-Microsoft 365 data into evidence</span></span>

<span data-ttu-id="75d4e-104">在資料調查中，您可能需要分析的所有檔都不會位於 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="75d4e-104">Not all documents that you may need to analyze in a data investigation will be located in Microsoft 365.</span></span> <span data-ttu-id="75d4e-105">使用非 Microsoft 365 內容匯入功能，您可以將不在 Microsoft 365 中的檔上傳至證據，以便在資料調查中進行分析。</span><span class="sxs-lookup"><span data-stu-id="75d4e-105">With the Non-Microsoft 365 content import feature you can upload documents that don't live in Microsoft 365 into evidence so they can be analyzed in a data investigation.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="75d4e-106">上傳非 Office 365 內容的需求</span><span class="sxs-lookup"><span data-stu-id="75d4e-106">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="75d4e-107">使用此程式中所述的 [上傳非 Microsoft 365] 功能，您必須具備下列要求：</span><span class="sxs-lookup"><span data-stu-id="75d4e-107">Using the upload Non-Microsoft 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="75d4e-108">Microsoft 365 或 Office 365 E5 訂閱。</span><span class="sxs-lookup"><span data-stu-id="75d4e-108">A Microsoft 365 or Office 365 E5 subscription.</span></span>

- <span data-ttu-id="75d4e-109">將上傳非 Microsoft 365 內容的所有興趣人員，必須具有適當的 E5 或 E5 附加元件授權。</span><span class="sxs-lookup"><span data-stu-id="75d4e-109">All people of interest whose non-Microsoft 365 content will be uploaded must have the appropriate E5 or E5 add-on license.</span></span>

- <span data-ttu-id="75d4e-110">現有的 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="75d4e-110">An existing eDiscovery case.</span></span>

- <span data-ttu-id="75d4e-111">所有檔案，可將收集到的資料夾中，每個保管人都有一個資料夾，而且資料夾的名稱為*alias@domainname*的此格式。</span><span class="sxs-lookup"><span data-stu-id="75d4e-111">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname*.</span></span> <span data-ttu-id="75d4e-112">*Alias@domainname*必須是使用者的別名和網域。</span><span class="sxs-lookup"><span data-stu-id="75d4e-112">The *alias@domainname* must be user's alias and domain.</span></span> <span data-ttu-id="75d4e-113">您可以將所有*alias@domainname*資料夾收集至根資料夾。</span><span class="sxs-lookup"><span data-stu-id="75d4e-113">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="75d4e-114">根資料夾只能包含*alias@domainname*資料夾，根資料夾中一定沒有鬆散檔案。</span><span class="sxs-lookup"><span data-stu-id="75d4e-114">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="75d4e-115">一種帳戶，既可以是 eDiscovery 管理員，也可以是在具有非 Microsoft 365 內容資料夾結構存取權的電腦上安裝的 eDiscovery 管理員 Microsoft Azure Storage Tools。</span><span class="sxs-lookup"><span data-stu-id="75d4e-115">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span>

- <span data-ttu-id="75d4e-116">安裝 AzCopy，您可以從[AzCopy 開始使用](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="75d4e-116">Install AzCopy, which you can do from [Get started with AzCopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span>

## <a name="upload-non-microsoft-365-content-in-to-a-data-investigation"></a><span data-ttu-id="75d4e-117">將非 Microsoft 365 內容上傳至資料調查</span><span class="sxs-lookup"><span data-stu-id="75d4e-117">Upload non-Microsoft 365 content in to a data investigation</span></span>

1. <span data-ttu-id="75d4e-118">開啟**資料調查**，並前往將非 Microsoft 365 資料上傳至的調查。</span><span class="sxs-lookup"><span data-stu-id="75d4e-118">Open **Data Investigations** and go to the investigation that the non-Microsoft 365 data will be uploaded to.</span></span>  <span data-ttu-id="75d4e-119">按一下 [**證據**] 索引標籤，然後選取您想要將資料載入到其中的證據集。</span><span class="sxs-lookup"><span data-stu-id="75d4e-119">Click the **Evidence** tab, then select the evidence set you wish to load the data to.</span></span>  <span data-ttu-id="75d4e-120">如果您尚未建立證據集，現在可以這麼做。</span><span class="sxs-lookup"><span data-stu-id="75d4e-120">If you have not already created an evidence set, you can do so now.</span></span>  <span data-ttu-id="75d4e-121">最後，按一下 [**管理證據**]，然後在 [資料] 區段中**查看上傳**</span><span class="sxs-lookup"><span data-stu-id="75d4e-121">Finally, click **Manage evidence** then **View uploads** in the data section</span></span>

2. <span data-ttu-id="75d4e-122">按一下 [**上傳**檔案] 按鈕，以啟動非 Microsoft 365 資料匯入嚮導。</span><span class="sxs-lookup"><span data-stu-id="75d4e-122">Click the **Upload files** button to start the Non-Microsoft 365 data import wizard.</span></span>

![上傳檔案](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="75d4e-124">嚮導的第一個步驟只是為要上傳的檔案準備一個安全 Azure blob。</span><span class="sxs-lookup"><span data-stu-id="75d4e-124">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="75d4e-125">準備完成後，按一下 [**下一步：上傳檔案]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="75d4e-125">After the preparation is complete, click the **Next: Upload files** button.</span></span>

![準備非 Microsoft 365 的資料匯入](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="75d4e-127">在 [**上傳**檔案] 步驟中，指定檔案的**位置路徑**，這是您規劃匯入的非 Microsoft 365 資料所在的位置。</span><span class="sxs-lookup"><span data-stu-id="75d4e-127">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Microsoft 365 data you plan on importing is located.</span></span>  <span data-ttu-id="75d4e-128">設定正確的位置可確保 AzCopy 命令已正確更新。</span><span class="sxs-lookup"><span data-stu-id="75d4e-128">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="75d4e-129">若尚未安裝 AzCopy，您可以從下列進行：https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="75d4e-129">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="75d4e-130">按一下 [**複製至剪貼簿**] 連結，以複製預先定義的命令。</span><span class="sxs-lookup"><span data-stu-id="75d4e-130">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="75d4e-131">啟動 windows 命令提示字元，貼上命令，然後按 enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="75d4e-131">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="75d4e-132">將檔案上傳至安全 Azure blob 儲存區，以進行下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="75d4e-132">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![上傳非 Microsoft 365 資料匯入的檔案](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![使用 AzCopy 匯入非 Microsoft 365 資料](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="75d4e-135">最後，回到安全性 & 符合性，然後按一下 [**下一步：處理檔案]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="75d4e-135">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="75d4e-136">這會啟動上傳檔案的處理、文字提取及編制索引。</span><span class="sxs-lookup"><span data-stu-id="75d4e-136">This initiates processing, text extraction, and indexing of the uploaded files.</span></span>  <span data-ttu-id="75d4e-137">您可以在這裡或 [**工作**] 索引標籤中追蹤處理進度。 完成後，就會在證據集中使用新的檔案。</span><span class="sxs-lookup"><span data-stu-id="75d4e-137">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files are available in the evidence set.</span></span>  <span data-ttu-id="75d4e-138">處理完成後，您可以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="75d4e-138">After processing is complete, you can dismiss the wizard.</span></span>

![非 Microsoft 365 Import 處理檔案](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

