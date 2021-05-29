---
title: 文件瞭解概觀
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 取得 Microsoft SharePoint Syntex 中文件瞭解的概覽。
ms.openlocfilehash: 7e5818a929fa0f4554a7ee4ece460b4fe0d691aa
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683820"
---
# <a name="document-understanding-overview"></a>文件瞭解概觀


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

文件瞭解使用人工智慧 (AI) 模型來自動分類檔案及擷取資訊。 它最適用於非結構化文件，如信件或合约。 這些文件必須具有可根據片語或模式識別的文字。 所識別的文字指定了檔案的類型（它的分類）和您想要擷取的內容（它的擷取器）。

> [!NOTE]
> 如需有關文件瞭解案例範例的詳細資訊，請參閱 [SharePoint Syntex 採用：入門指南](./adoption-getstarted.md)。

文件瞭解模型是在一種稱為 *内容中心* 的 SharePoint 網站中建立和管理的。 當套用至 SharePoint 文件庫時，模型與一個具有存儲所擷取資訊的欄的內容類型相關聯。 您建立的內容類型儲存在 SharePoint 內容類型庫中。 您也可以選擇使用現有內容類型來使用其架構。

> [!NOTE]
> 無法更新唯讀或封存內容類型，因此無法在模型中使用。

將 *分類器* 和 *擷取器* 新增至文件瞭解模型中，以執行以下動作： 

- 分類器用來識別和分類上傳至文件庫的文件。 例如，可以「訓練」分類器來識別上傳到文件庫的所有 *合同續約* 文件。 合同續約內容類型由您在建立分類器時定義。

- 擷取器從這些文件中選取資訊。 例如，對於文件庫中識別的所有合同續約文件，檢視中顯示的欄也顯示每個合同續約文件的 *服務開始日期* 和 *客戶*。 

您可以在模型中使用範例檔案來訓練和測試分類器和擷取器。 範例檔案向您的模型範例提供在嘗試從檔案中識別和擷取資料時要查找的內容。 例如，您會以貴公司使用的合同續約文件範例來訓練您的合同續約分類器和擷取器。 您也可以使用範例檔案來測試模型的有效性。

發佈模型之後，請使用內容中心將它套用到您有權存取的任何 SharePoint 文件庫。  

## <a name="file-limitations"></a>檔案限制

文件瞭解模型：使用光學字元辨識 (OCR) 技術，在您使用範例檔案訓練模型時以及當您針對文件庫中的檔案執行模型時，掃描 PDF、影像和 TIFF 檔案。

請注意有關於 Microsoft Office 文字型檔案與 OCR 掃描檔案 (PDF、影像或 TIFF) 的下列差異：

- Office 檔案：在 64,000 個字元處截斷 (在訓練中以及針對文件庫中的檔案執行時)。

- OCR 掃描檔案：頁面上限為 20 頁。  

### <a name="requirements"></a>需求

OCR 處理最適合處理符合下列需求的文件：

- JPG、PNG 或 PDF 格式 (文字或掃描文件)。 文字內嵌 PDF 效果更好，因為字元解壓縮和位置不會有任何錯誤。

- 如果您的 PDF 使用密碼鎖定，您必須先移除鎖定再提交。

- 每個集合中，用於訓練的文件總檔案大小不得超過 50 MB，PDF 文件不應超過 500 頁。

- 若是影像，尺寸必須介於 50 × 50 到 10,000 × 10,000 像素之間。
   > [!NOTE]
   > 在 OCR 處理中，非常寬或具有奇數尺寸 (例如樓層規劃) 的影像可能會被截斷，並失去正確性。
 
- 若是 PDF 檔案，尺寸最多必須為 17 x 17 吋，與 Legal 或 A3 紙張大小對應且較小。

- 如果從紙本文件掃描，應為高品質影像的掃描。

- 必須使用拉丁字母 (英文字元)。

> [!NOTE]
> AI Builder 目前不支援下列表單處理輸入資料類型：<br>- 核取方塊或選項按鈕<br>- 簽章<br>- 可填寫的 PDF

### <a name="supported-file-types"></a>支援的檔案類型

文件瞭解模型支援下列檔案類型：

- doc
- docx
- eml
- heic
- heif
- htm
- html
- jpeg
- jpg
- markdown
- md
- msg
- pdf
- png
- ppt
- pptx
- rtf
- tif
- tiff
- txt
- xls
- xlsx



## <a name="see-also"></a>另請參閱
[建立分類器](create-a-classifier.md)

[建立擷取器](create-an-extractor.md)

[建立內容中心](create-a-content-center.md)

[建立表單處理模型](create-a-form-processing-model.md)

[套用模型](apply-a-model.md)   

[文件瞭解和表單處理模型之間的差異](difference-between-document-understanding-and-form-processing-model.md)
  
[表單處理概觀](form-processing-overview.md)

[SharePoint Syntex 協助工具模式](accessibility-mode.md)