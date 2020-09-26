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
ms.openlocfilehash: c318148900d891304ebcb9b4a88abfe52f43c05e
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285839"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a>高級 eDiscovery 中的單一專案錯誤修正

錯誤修正功能可讓高級 eDiscovery 使用者修正導致「高級 eDiscovery」無法正確處理內容的資料問題。 例如，無法處理受密碼保護的檔案，因為這些檔案已鎖定或已加密。 先前，您只能使用 [此工作流程](error-remediation-when-processing-data-in-advanced-ediscovery.md)大量修正錯誤。 不過，如果您不確定這些檔案中的任何檔案是否都回應您正在調查的案例，有時在多個檔案中修復錯誤就沒有意義。 在您有機會檢查檔案中繼資料 (例如檔案位置或誰具有存取權) ，以協助您進行回應的前期決策之前，也可能無法修正錯誤。 稱為 *單一專案錯誤修正* 的新功能可讓 eDiscovery 管理員以處理錯誤來查看檔案中繼資料，並在必要時直接在複查集中修正錯誤。 本文討論如何使用審閱集中的處理錯誤來識別、忽略和修正檔案。

## <a name="identify-documents-with-errors"></a>識別錯誤的檔

在審閱集中處理錯誤的檔現在會以橫幅) 識別 (。 您可以修正或略過錯誤。 下列螢幕擷取畫面顯示 Word 檔的處理錯誤橫幅，其為密碼保護的審閱集。 此外，請注意，您可以透過處理錯誤來查看檔的中繼資料。

![針對含處理錯誤的檔顯示橫幅](../media/SIERimage1.png)

您也可以在[審閱集中查詢檔](review-set-search.md)時使用**處理狀態**條件，搜尋處理錯誤的檔。

![使用處理狀態條件來搜尋錯誤檔](../media/SIERimage2.png)

### <a name="ignore-errors"></a>忽略錯誤

您可以按一下處理錯誤橫幅中的 [ **略** 過]，忽略處理錯誤。 當您忽略錯誤時，該檔會從 [大量錯誤修正工作流程](error-remediation-when-processing-data-in-advanced-ediscovery.md)中移除。 在忽略錯誤之後，檔橫幅會變更色彩，並指出忽略處理錯誤。 您可以隨時按一下 [ **還原**]，恢復決定忽略錯誤。

![按一下 [忽略] 忽略處理錯誤。](../media/SIERimage3.png)

您也可以搜尋包含處理錯誤的所有檔，以在審閱集中查詢檔時使用「 *忽略處理錯誤* 」條件忽略。

![使用忽略的處理錯誤條件來搜尋忽略的錯誤檔](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a>修正含有錯誤的檔

在某些情況下，您可能需要在檔 (中修復處理錯誤，方法是移除密碼、解密加密的檔案或復原損毀的檔) 然後將修正檔新增至審閱集。 這可讓您檢查及匯出錯誤檔，以及審閱集中的其他檔。 

若要修正單一檔，請遵循下列步驟：

1. 按一下 [**下載**原始檔案]，將檔案的  >  **Download original**複本下載到本機電腦。

   ![下載包含處理錯誤的檔](../media/SIERimage5.png)

2. 在離線修正檔中的錯誤。 若為加密檔案，則需要解密軟體，以移除密碼保護，請提供密碼並儲存檔案或使用密碼破解程式。 修正檔後，請移至下一個步驟。

3. 在 [檢查] 集中，選取具有修正處理錯誤的檔案，然後按一下 [ **修復**]。

   ![在具有處理錯誤的檔旗標中按一下 [修正]](../media/SIERimage6.png)


4. 按一下 **[流覽]**，移至您本機電腦上已修正檔案的位置，然後選取檔案。

   ![按一下 [流覽]，然後選取本機電腦上的修正檔案。](../media/SIERimage7.png)

    選取修正的檔案之後，它會自動上傳至審閱集。 您可以追蹤檔的處理狀態。

    ![顯示修復程式的狀態](../media/SIERimage8.png)

   處理完成後，您可以查看修正的檔。

    ![您可以在「審閱集」中以原生格式查看修正的檔案。](../media/SIERimage9.png)

如需修正檔時的詳細資訊，請參閱修正檔案時會 [發生什麼情況](error-remediation.md#what-happens-when-files-are-remediated)。

## <a name="search-for-remediated-documents"></a>搜尋修正的檔

您可以使用 **關鍵字** 條件，並指定下列屬性，搜尋審閱集中已修正的所有檔：值配對： **IsFromErrorRemediation： true**。 當您從審閱集匯出檔時，也會在匯出載入檔案中使用此屬性。
