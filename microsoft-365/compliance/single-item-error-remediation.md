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
description: 您可以在進階電子文件探索中設定而不需要遵循大量錯誤修復程序檢閱文件中可修正處理錯誤。
ms.openlocfilehash: c049ce4b5d3f8fc12a015a61ea927b744ae76eb3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601490"
---
# <a name="single-item-error-remediation"></a>單一項目錯誤補救

錯誤修復進階電子文件的使用者可讓修正正確處理內容時，防止進階電子文件的資料問題。 例如，因為這些檔案已鎖定或加密，無法處理受到密碼保護的檔案。 之前，您只可以使用[此工作流程](error-remediation-when-processing-data-in-advanced-ediscovery.md)修復大量的錯誤。 但是，某些情況下，它並沒有任何意義要修復多個檔案中的錯誤，您不確定如果有任何這些檔案是回應這種情況時您正在調查。 它也可能不合理的修復錯誤之前已有機會檢閱檔案中繼資料 （例如檔案的位置或誰可以存取） 可以協助您建立服務有無反應的預付決策。 新功能，稱為*單一項目錯誤修復*電子文件探索管理員可讓檢視與處理錯誤的檔案的中繼資料，並視修復直接中檢閱設定的錯誤訊息。 本文討論如何識別、 略過，並修復與處理錯誤檢閱集合中的檔案。

## <a name="identify-documents-with-errors"></a>識別文件錯誤

處理錯誤檢閱集合中的文件現在會識別 （與橫幅）。 您可以修復或略過此錯誤。 下列螢幕擷取畫面顯示 Word 文件的處理錯誤橫幅中受到密碼保護檢閱設定。 也請注意，您可以檢視的文件處理錯誤的檔案中繼資料。

![顯示與處理錯誤的文件橫幅](media/SIERimage1.png)

您也可以使用**處理狀態**已處理錯誤的文件的搜尋條件時[查詢中檢閱文件集](review-set-search.md)。

![使用處理狀態條件來搜尋的錯誤文件](media/SIERimage2.png)

### <a name="ignore-errors"></a>忽略錯誤

您可以忽略處理錯誤中的 [**略過**處理錯誤橫幅。 當您要略過錯誤時，請從[大量錯誤修復工作流程](error-remediation-when-processing-data-in-advanced-ediscovery.md)中移除文件。 忽略錯誤之後，文件橫幅變更色彩，並指出處理錯誤，已略過。 任何時候，您可以還原]，即可**還原**搜尋時忽略錯誤的決策。

![按一下 [略過略過處理錯誤](media/SIERimage3.png)

您也可以搜尋已被略過時查詢的文件中的檢閱設定，請使用*略過處理錯誤*條件來處理錯誤的所有文件。

![用於處理錯誤條件 Ignored 略過的錯誤文件中搜尋](media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a>修復含有錯誤的文件

有時候您可能需要在文件中的處理錯誤修復 （藉由移除密碼、 解密加密的檔案，或復原損毀的文件），然後將修復文件新增至檢閱組。 這可讓您檢視和匯出搭配檢閱集中的其他文件的文件時發生錯誤。 

若要補救單一文件，請遵循下列步驟：

1. 按一下 [**下載** > **下載原始**的檔案複本下載到本機電腦上。

   ![下載文件與處理錯誤](media/SIERimage5.png)

2. 修復檔離線中的錯誤。 加密檔案，會需要解密軟體，以移除密碼保護，提供密碼，並將檔案儲存或使用密碼破解。 修復檔案之後，請移至下一個步驟。

3. 在檢閱設定，請選取與您修復處理錯誤的檔案和 [**修復**。

   ![按一下 [處理錯誤之文件橫幅中的 [修復](media/SIERimage6.png)


4. 按一下 [**瀏覽**，移至您的本機電腦上的修復檔案的位置，然後選取的檔案。

   ![按一下 [瀏覽]，然後選取 [本機電腦上的修復的檔案](media/SIERimage7.png)

    選取後的修復的檔案，它是自動上傳至檢閱設定。 您可以追蹤檔案的處理狀態。

    ![修復程序的狀態會顯示](media/SIERimage8.png)

   處理完成後，您可以檢視修復文件。

    ![您可以檢視修復的檔案中檢閱集內的原生格式](media/SIERimage9.png)

如需修復文件時，會發生什麼情況的詳細資訊，請參閱[當檔案修復時，會發生什麼事](error-remediation.md#what-happens-when-files-are-remediated)。

## <a name="search-for-remediated-documents"></a>修復文件中搜尋

您可以搜尋檢閱集合中所有已修復使用**關鍵字**條件並指定下列屬性： 值配對的文件： **IsFromErrorRemediation:true**。 此屬性時也可用匯出負載檔案中檢閱設定從匯出的文件。
