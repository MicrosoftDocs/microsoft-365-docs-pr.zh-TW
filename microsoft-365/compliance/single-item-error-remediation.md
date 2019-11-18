---
title: 單一項目錯誤補救
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
description: 您可以在進階電子文件探索中設定而不需要遵循大量錯誤修復程序檢閱文件中可修正處理錯誤。
ms.openlocfilehash: 922c0e4b0ab30bae6507fac7e97080a5951ea750
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/11/2019
ms.locfileid: "38685516"
---
# <a name="single-item-error-remediation"></a><span data-ttu-id="6cacc-103">單一項目錯誤補救</span><span class="sxs-lookup"><span data-stu-id="6cacc-103">Single item error remediation</span></span>

<span data-ttu-id="6cacc-104">錯誤修復進階電子文件的使用者可讓修正正確處理內容時，防止進階電子文件的資料問題。</span><span class="sxs-lookup"><span data-stu-id="6cacc-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="6cacc-105">例如，因為這些檔案已鎖定或加密，無法處理受到密碼保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="6cacc-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="6cacc-106">之前，您只可以使用[此工作流程](error-remediation-when-processing-data-in-advanced-ediscovery.md)修復大量的錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cacc-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="6cacc-107">但是，某些情況下，它並沒有任何意義要修復多個檔案中的錯誤，您不確定如果有任何這些檔案是回應這種情況時您正在調查。</span><span class="sxs-lookup"><span data-stu-id="6cacc-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="6cacc-108">它也可能不合理的修復錯誤之前已有機會檢閱檔案中繼資料 （例如檔案的位置或誰可以存取） 可以協助您建立服務有無反應的預付決策。</span><span class="sxs-lookup"><span data-stu-id="6cacc-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="6cacc-109">新功能，稱為*單一項目錯誤修復*電子文件探索管理員可讓檢視與處理錯誤的檔案的中繼資料，並視修復直接中檢閱設定的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="6cacc-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="6cacc-110">本文討論如何識別、 略過，並修復與處理錯誤檢閱集合中的檔案。</span><span class="sxs-lookup"><span data-stu-id="6cacc-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="6cacc-111">識別文件錯誤</span><span class="sxs-lookup"><span data-stu-id="6cacc-111">Identify documents with errors</span></span>

<span data-ttu-id="6cacc-112">處理錯誤檢閱集合中的文件現在會識別 （與橫幅）。</span><span class="sxs-lookup"><span data-stu-id="6cacc-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="6cacc-113">您可以修復或略過此錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cacc-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="6cacc-114">下列螢幕擷取畫面顯示 Word 文件的處理錯誤橫幅中受到密碼保護檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="6cacc-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="6cacc-115">也請注意，您可以檢視的文件處理錯誤的檔案中繼資料。</span><span class="sxs-lookup"><span data-stu-id="6cacc-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![顯示與處理錯誤的文件橫幅](media/SIERimage1.png)

<span data-ttu-id="6cacc-117">您也可以使用**處理狀態**已處理錯誤的文件的搜尋條件時[查詢中檢閱文件集](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="6cacc-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![使用處理狀態條件來搜尋的錯誤文件](media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="6cacc-119">忽略錯誤</span><span class="sxs-lookup"><span data-stu-id="6cacc-119">Ignore errors</span></span>

<span data-ttu-id="6cacc-120">您可以忽略處理錯誤中的 [**略過**處理錯誤橫幅。</span><span class="sxs-lookup"><span data-stu-id="6cacc-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="6cacc-121">當您要略過錯誤時，請從[大量錯誤修復工作流程](error-remediation-when-processing-data-in-advanced-ediscovery.md)中移除文件。</span><span class="sxs-lookup"><span data-stu-id="6cacc-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="6cacc-122">忽略錯誤之後，文件橫幅變更色彩，並指出處理錯誤，已略過。</span><span class="sxs-lookup"><span data-stu-id="6cacc-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="6cacc-123">任何時候，您可以還原]，即可**還原**搜尋時忽略錯誤的決策。</span><span class="sxs-lookup"><span data-stu-id="6cacc-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![按一下 [略過略過處理錯誤](media/SIERimage3.png)

<span data-ttu-id="6cacc-125">您也可以搜尋已被略過時查詢的文件中的檢閱設定，請使用*略過處理錯誤*條件來處理錯誤的所有文件。</span><span class="sxs-lookup"><span data-stu-id="6cacc-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![用於處理錯誤條件 Ignored 略過的錯誤文件中搜尋](media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="6cacc-127">修復含有錯誤的文件</span><span class="sxs-lookup"><span data-stu-id="6cacc-127">Remediate a document with errors</span></span>

<span data-ttu-id="6cacc-128">有時候您可能需要在文件中的處理錯誤修復 （藉由移除密碼、 解密加密的檔案，或復原損毀的文件），然後將修復文件新增至檢閱組。</span><span class="sxs-lookup"><span data-stu-id="6cacc-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="6cacc-129">這可讓您檢視和匯出搭配檢閱集中的其他文件的文件時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cacc-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="6cacc-130">若要補救單一文件，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6cacc-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="6cacc-131">按一下 [**下載** > **下載原始**的檔案複本下載到本機電腦上。</span><span class="sxs-lookup"><span data-stu-id="6cacc-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![下載文件與處理錯誤](media/SIERimage5.png)

2. <span data-ttu-id="6cacc-133">修復檔離線中的錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cacc-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="6cacc-134">加密檔案，會需要解密軟體，以移除密碼保護，提供密碼，並將檔案儲存或使用密碼破解。</span><span class="sxs-lookup"><span data-stu-id="6cacc-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="6cacc-135">修復檔案之後，請移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="6cacc-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="6cacc-136">在檢閱設定，請選取與您修復處理錯誤的檔案和 [**修復**。</span><span class="sxs-lookup"><span data-stu-id="6cacc-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![按一下 [處理錯誤之文件橫幅中的 [修復](media/SIERimage6.png)


4. <span data-ttu-id="6cacc-138">按一下 [**瀏覽**，移至您的本機電腦上的修復檔案的位置，然後選取的檔案。</span><span class="sxs-lookup"><span data-stu-id="6cacc-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![按一下 [瀏覽]，然後選取 [本機電腦上的修復的檔案](media/SIERimage7.png)

    <span data-ttu-id="6cacc-140">選取後的修復的檔案，它是自動上傳至檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="6cacc-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="6cacc-141">您可以追蹤檔案的處理狀態。</span><span class="sxs-lookup"><span data-stu-id="6cacc-141">You can track the processing status of the file.</span></span>

    ![修復程序的狀態會顯示](media/SIERimage8.png)

   <span data-ttu-id="6cacc-143">處理完成後，您可以檢視修復文件。</span><span class="sxs-lookup"><span data-stu-id="6cacc-143">After processing is completed, you can view the remediated document.</span></span>

    ![您可以檢視修復的檔案中檢閱集內的原生格式](media/SIERimage9.png)

<span data-ttu-id="6cacc-145">如需修復文件時，會發生什麼情況的詳細資訊，請參閱[當檔案修復時，會發生什麼事](error-remediation.md#what-happens-when-files-are-remediated)。</span><span class="sxs-lookup"><span data-stu-id="6cacc-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="6cacc-146">修復文件中搜尋</span><span class="sxs-lookup"><span data-stu-id="6cacc-146">Search for remediated documents</span></span>

<span data-ttu-id="6cacc-147">您可以搜尋檢閱集合中所有已修復使用**關鍵字**條件並指定下列屬性： 值配對的文件： **IsFromErrorRemediation:true**。</span><span class="sxs-lookup"><span data-stu-id="6cacc-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="6cacc-148">此屬性時也可用匯出負載檔案中檢閱設定從匯出的文件。</span><span class="sxs-lookup"><span data-stu-id="6cacc-148">This property is also available in the export load file when you export documents from a review set.</span></span>
