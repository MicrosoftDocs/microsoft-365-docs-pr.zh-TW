---
title: 單一項目錯誤補救
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
description: 您可以在高級 eDiscovery 的審閱集中修正檔中的處理錯誤，而不必遵循大量的錯誤修正程式。
ms.openlocfilehash: 8e5d8d00f507dc5792a1beda018d4c76632b82f7
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751580"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a><span data-ttu-id="c13ce-103">高級 eDiscovery 中的單一專案錯誤修正</span><span class="sxs-lookup"><span data-stu-id="c13ce-103">Single item error remediation in Advanced eDiscovery</span></span>

<span data-ttu-id="c13ce-104">錯誤修正功能可讓高級 eDiscovery 使用者修正導致「高級 eDiscovery」無法正確處理內容的資料問題。</span><span class="sxs-lookup"><span data-stu-id="c13ce-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="c13ce-105">例如，無法處理受密碼保護的檔案，因為這些檔案已鎖定或已加密。</span><span class="sxs-lookup"><span data-stu-id="c13ce-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="c13ce-106">先前，您只能使用 [此工作流程](error-remediation-when-processing-data-in-advanced-ediscovery.md)大量修正錯誤。</span><span class="sxs-lookup"><span data-stu-id="c13ce-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="c13ce-107">不過，如果您不確定這些檔案中的任何檔案是否都回應您正在調查的案例，有時在多個檔案中修復錯誤就沒有意義。</span><span class="sxs-lookup"><span data-stu-id="c13ce-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="c13ce-108">在您有機會檢查檔案中繼資料 (例如檔案位置或誰具有存取權) ，以協助您進行回應的前期決策之前，也可能無法修正錯誤。</span><span class="sxs-lookup"><span data-stu-id="c13ce-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="c13ce-109">稱為 *單一專案錯誤修正* 的新功能可讓 eDiscovery 管理員以處理錯誤來查看檔案中繼資料，並在必要時直接在複查集中修正錯誤。</span><span class="sxs-lookup"><span data-stu-id="c13ce-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="c13ce-110">本文討論如何使用審閱集中的處理錯誤來識別、忽略和修正檔案。</span><span class="sxs-lookup"><span data-stu-id="c13ce-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="c13ce-111">識別錯誤的檔</span><span class="sxs-lookup"><span data-stu-id="c13ce-111">Identify documents with errors</span></span>

<span data-ttu-id="c13ce-112">在審閱集中處理錯誤的檔現在會以橫幅) 識別 (。</span><span class="sxs-lookup"><span data-stu-id="c13ce-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="c13ce-113">您可以修正或略過錯誤。</span><span class="sxs-lookup"><span data-stu-id="c13ce-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="c13ce-114">下列螢幕擷取畫面顯示 Word 檔的處理錯誤橫幅，其為密碼保護的審閱集。</span><span class="sxs-lookup"><span data-stu-id="c13ce-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="c13ce-115">此外，請注意，您可以透過處理錯誤來查看檔的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="c13ce-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![針對含處理錯誤的檔顯示橫幅](../media/SIERimage1.png)

<span data-ttu-id="c13ce-117">您也可以在 [審閱集中查詢檔](review-set-search.md)時使用 **處理狀態** 條件，搜尋處理錯誤的檔。</span><span class="sxs-lookup"><span data-stu-id="c13ce-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![使用處理狀態條件來搜尋錯誤檔](../media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="c13ce-119">忽略錯誤</span><span class="sxs-lookup"><span data-stu-id="c13ce-119">Ignore errors</span></span>

<span data-ttu-id="c13ce-120">您可以按一下處理錯誤橫幅中的 [ **略** 過]，忽略處理錯誤。</span><span class="sxs-lookup"><span data-stu-id="c13ce-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="c13ce-121">當您忽略錯誤時，該檔會從 [大量錯誤修正工作流程](error-remediation-when-processing-data-in-advanced-ediscovery.md)中移除。</span><span class="sxs-lookup"><span data-stu-id="c13ce-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="c13ce-122">在忽略錯誤之後，檔橫幅會變更色彩，並指出忽略處理錯誤。</span><span class="sxs-lookup"><span data-stu-id="c13ce-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="c13ce-123">您可以隨時按一下 [ **還原**]，恢復決定忽略錯誤。</span><span class="sxs-lookup"><span data-stu-id="c13ce-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![按一下 [忽略] 忽略處理錯誤。](../media/SIERimage3.png)

<span data-ttu-id="c13ce-125">您也可以搜尋包含處理錯誤的所有檔，以在審閱集中查詢檔時使用「 *忽略處理錯誤* 」條件忽略。</span><span class="sxs-lookup"><span data-stu-id="c13ce-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![使用忽略的處理錯誤條件來搜尋忽略的錯誤檔](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="c13ce-127">修正含有錯誤的檔</span><span class="sxs-lookup"><span data-stu-id="c13ce-127">Remediate a document with errors</span></span>

<span data-ttu-id="c13ce-128">在某些情況下，您可能需要在檔 (中修復處理錯誤，方法是移除密碼、解密加密的檔案或復原損毀的檔) 然後將修正檔新增至審閱集。</span><span class="sxs-lookup"><span data-stu-id="c13ce-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="c13ce-129">這可讓您檢查及匯出錯誤檔，以及審閱集中的其他檔。</span><span class="sxs-lookup"><span data-stu-id="c13ce-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="c13ce-130">若要修正單一檔，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="c13ce-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="c13ce-131">按一下 [**下載** 原始檔案]，將檔案的  >  複本下載到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="c13ce-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![下載包含處理錯誤的檔](../media/SIERimage5.png)

2. <span data-ttu-id="c13ce-133">在離線修正檔中的錯誤。</span><span class="sxs-lookup"><span data-stu-id="c13ce-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="c13ce-134">若為加密檔案，則需要解密軟體，以移除密碼保護，請提供密碼並儲存檔案或使用密碼破解程式。</span><span class="sxs-lookup"><span data-stu-id="c13ce-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="c13ce-135">修正檔後，請移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="c13ce-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="c13ce-136">在 [檢查] 集中，選取具有修正處理錯誤的檔案，然後按一下 [ **修復**]。</span><span class="sxs-lookup"><span data-stu-id="c13ce-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![在具有處理錯誤的檔旗標中按一下 [修正]](../media/SIERimage6.png)


4. <span data-ttu-id="c13ce-138">按一下 **[流覽]**，移至您本機電腦上已修正檔案的位置，然後選取檔案。</span><span class="sxs-lookup"><span data-stu-id="c13ce-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![按一下 [流覽]，然後選取本機電腦上的修正檔案。](../media/SIERimage7.png)

    <span data-ttu-id="c13ce-140">選取修正的檔案之後，它會自動上傳至審閱集。</span><span class="sxs-lookup"><span data-stu-id="c13ce-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="c13ce-141">您可以追蹤檔的處理狀態。</span><span class="sxs-lookup"><span data-stu-id="c13ce-141">You can track the processing status of the file.</span></span>

    ![顯示修復程式的狀態](../media/SIERimage8.png)

   <span data-ttu-id="c13ce-143">處理完成後，您可以查看修正的檔。</span><span class="sxs-lookup"><span data-stu-id="c13ce-143">After processing is completed, you can view the remediated document.</span></span>

    ![您可以在「審閱集」中以原生格式查看修正的檔案。](../media/SIERimage9.png)

<span data-ttu-id="c13ce-145">如需修正檔時的詳細資訊，請參閱修正檔案時會 [發生什麼情況](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated)。</span><span class="sxs-lookup"><span data-stu-id="c13ce-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="c13ce-146">搜尋修正的檔</span><span class="sxs-lookup"><span data-stu-id="c13ce-146">Search for remediated documents</span></span>

<span data-ttu-id="c13ce-147">您可以使用 **關鍵字** 條件，並指定下列屬性，搜尋審閱集中已修正的所有檔：值配對： **IsFromErrorRemediation： true**。</span><span class="sxs-lookup"><span data-stu-id="c13ce-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="c13ce-148">當您從審閱集匯出檔時，也會在匯出載入檔案中使用此屬性。</span><span class="sxs-lookup"><span data-stu-id="c13ce-148">This property is also available in the export load file when you export documents from a review set.</span></span>
