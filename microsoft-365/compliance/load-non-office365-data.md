---
title: 非 Office 365 資料載入辨識項
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
description: ''
ms.openlocfilehash: 4db0b40d485c4c1107bdcb0d49616cadb15b1915
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072151"
---
# <a name="load-non-office-365-data-into-evidence"></a><span data-ttu-id="7e071-102">非 Office 365 資料載入辨識項</span><span class="sxs-lookup"><span data-stu-id="7e071-102">Load non-Office 365 data into evidence</span></span>

<span data-ttu-id="7e071-103">您可能需要在資料調查中分析的並非所有文件將會位於 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7e071-103">Not all documents that you may need to analyze in a data investigation will be located in Office 365.</span></span> <span data-ttu-id="7e071-104">使用非 Office 365 內容匯入的功能，您可以上傳文件與不存在於 Office 365 中插入辨識項讓他們可以在資料調查分析。</span><span class="sxs-lookup"><span data-stu-id="7e071-104">With the Non-Office 365 content import feature you can upload documents that don't live in Office 365 into evidence so they can be analyzed in a data investigation.</span></span>

>[!Note]
><span data-ttu-id="7e071-105">資料調查為您的組織需要與進階合規性附加元件或 E5 訂閱 Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="7e071-105">Data investigation requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="7e071-106">如果您不具有該計劃，並想要再試進階電子文件，您可以註冊 Office 365 企業版 E5 的試用版。</span><span class="sxs-lookup"><span data-stu-id="7e071-106">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7e071-107">開始之前</span><span class="sxs-lookup"><span data-stu-id="7e071-107">Before you begin</span></span>

<span data-ttu-id="7e071-108">使用此程序所述的上傳非 Office 365 功能需要您：</span><span class="sxs-lookup"><span data-stu-id="7e071-108">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="7e071-109">使用進階合規性的附加元件或 E5 訂閱 Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="7e071-109">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="7e071-110">將上傳其非 Office 365 內容的所有 custodians 必須都擁有 E3 的進階合規性的附加元件或 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="7e071-110">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="7e071-111">現有的 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="7e071-111">An existing eDiscovery case.</span></span>

- <span data-ttu-id="7e071-112">上傳的所有檔案所都收集到資料夾，其中沒有 custodian 每一個資料夾，而且此格式*alias@domainname*中已有該資料夾的名稱。</span><span class="sxs-lookup"><span data-stu-id="7e071-112">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname*.</span></span> <span data-ttu-id="7e071-113">*Alias@domainname*必須是 Office 365 的使用者別名及網域。</span><span class="sxs-lookup"><span data-stu-id="7e071-113">The *alias@domainname* must be users Office 365 alias and domain.</span></span> <span data-ttu-id="7e071-114">您可以收集所有*alias@domainname*資料夾到根資料夾。</span><span class="sxs-lookup"><span data-stu-id="7e071-114">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="7e071-115">根資料夾只能包含*alias@domainname*資料夾，必須有任何鬆散檔案的根資料夾中。</span><span class="sxs-lookup"><span data-stu-id="7e071-115">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="7e071-116">EDiscovery 管理員或 eDiscovery 管理員 Microsoft Azure 儲存體工具具有存取權的非 Office 365 內容的資料夾結構的電腦上安裝帳戶。</span><span class="sxs-lookup"><span data-stu-id="7e071-116">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="7e071-117">安裝 AzCopy，您可以從這裡：https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="7e071-117">Install AzCopy, which you can do from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-in-to-a-data-investigation"></a><span data-ttu-id="7e071-118">中的非 Office 365 內容上傳資料調查</span><span class="sxs-lookup"><span data-stu-id="7e071-118">Upload non-Office 365 content in to a data investigation</span></span>

1. <span data-ttu-id="7e071-119">開啟 \* \* \* 資料調查 \* \*，則非 Office 365 資料就會上傳到調查。</span><span class="sxs-lookup"><span data-stu-id="7e071-119">Open \*\*\*\*Data Investigations\*\*, then the investigation that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="7e071-120">然後選取 [辨識項設定您想要載入的非 Office 365 資料，請按一下 [**證據**] 索引標籤]。</span><span class="sxs-lookup"><span data-stu-id="7e071-120">Click the **Evidence** tab, then select the evidence set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="7e071-121">如果您未建立辨識項集合，您可以立即執行。</span><span class="sxs-lookup"><span data-stu-id="7e071-121">If you have not already created an evidence set, you can do so now.</span></span>  <span data-ttu-id="7e071-122">最後，按一下 [**管理辨識項**，然後在 [非 Office 365 資料] 區段中的**檢視上傳**</span><span class="sxs-lookup"><span data-stu-id="7e071-122">Finally, click **Manage evidence** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="7e071-123">按一下 [**上傳檔案**] 按鈕來啟動非 Office 365 資料匯入精靈]。</span><span class="sxs-lookup"><span data-stu-id="7e071-123">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![上傳檔案](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="7e071-125">在精靈中的第一個步驟只會準備要上傳檔案的安全 Azure blob。</span><span class="sxs-lookup"><span data-stu-id="7e071-125">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="7e071-126">準備已完成之後，按一下 [**下一步： 將檔案上傳**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7e071-126">After the preparation is complete, click the **Next: Upload files** button.</span></span>

![準備非 Office 365 資料匯入](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="7e071-128">在 [**上傳檔案**] 步驟中，指定**的檔案位置路徑**] 中，這是您計劃匯入非 Office 365 資料所在的位置。</span><span class="sxs-lookup"><span data-stu-id="7e071-128">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="7e071-129">設定正確的位置可確保正確更新命令 AzCopy。</span><span class="sxs-lookup"><span data-stu-id="7e071-129">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="7e071-130">如果您未安裝 AzCopy，您可以從這裡：https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="7e071-130">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="7e071-131">按一下 [**複製到剪貼簿**] 連結，將複製的預先定義的命令。</span><span class="sxs-lookup"><span data-stu-id="7e071-131">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="7e071-132">啟動 windows 命令提示字元中，貼上命令並按 enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="7e071-132">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="7e071-133">檔案就會上傳到安全的 Azure blob 儲存的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="7e071-133">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![上傳非 Office 365 資料匯入的檔案](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![使用 AzCopy 匯入非 Office 365 資料](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="7e071-136">最後，傳回回到安全性 & 合規性，並按一下 [**下一步： 處理檔案**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7e071-136">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="7e071-137">這會初始化處理、 文字擷取和編製索引的上傳的檔案。</span><span class="sxs-lookup"><span data-stu-id="7e071-137">This initiates processing, text extraction, and indexing of the uploaded files.</span></span>  <span data-ttu-id="7e071-138">您可以追蹤處理以下或在 [**工作**] 索引標籤中的進度。 完成之後，就有一個新的檔案可辨識項集合中。</span><span class="sxs-lookup"><span data-stu-id="7e071-138">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files are available in the evidence set.</span></span>  <span data-ttu-id="7e071-139">處理皆完成之後，您可以關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="7e071-139">After processing is complete, you can dismiss the wizard.</span></span>

![非 Office 365 匯入程序檔案](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

