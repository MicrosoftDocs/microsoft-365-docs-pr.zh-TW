---
title: 步驟 1： 使用 SharePoint Syntex 來識別合約檔案及提取資料
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何使用 SharePoint Syntex 來識別協定檔案，並使用 Microsoft 365 解決方案提取資料。
ms.openlocfilehash: e0d58164d1a12987a4606ef84c15fa3d20c0195f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281130"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a>步驟 1. 使用 SharePoint Syntex 來識別合約檔案及提取資料

您的組織需要從您接收的許多檔案中識別和分類所有合約檔的方法。 您也想能夠在每個識別 (的合約檔案中快速查看數個重要元素，例如， *客戶*、 *合同工* 和 *費用金額*) 。 若要這麼做，您可以使用[SharePoint Syntex](index.md)建立檔理解模型，並將其套用至文件庫。

檔[瞭解](document-understanding-overview.md)使用智慧 (AI) 模型，以自動化檔案的分類和資訊提取。 檔理解模型在從非結構化檔或半結構化檔中解壓縮資訊時也是最佳的方式，而您所需的資訊不會包含在表格或表單中（如合約）。

1. 首先，您必須尋找至少五個範例檔案，您可以用來 "訓練" 模型，以搜尋您嘗試識別 (合約) 之內容類型的特定特性。 

2. 使用 SharePoint Syntex，建立新的檔理解模型。 您必須先 [建立分類符](create-a-classifier.md)，才能使用您的範例檔案。 訓練分類器與範例檔案，您可以教它搜尋您在公司合同中所看到的特定特性。 例如， [建立一個 "釋義"](create-a-classifier.md#create-an-explanation) ，搜尋您的合約中的特定字串，例如 *服務合約*、 *合約條款* 和 *補償*。 您甚至可以訓練說明，以在檔的特定區段中尋找這些字串，或位於其他字串旁邊。 當您認為您已使用所需的資訊訓練您的分類程式時，您可以在範例檔案的範例集合上測試模型，以查看其效率。 測試完成之後，您可以視需要選擇變更您的說明，使其更有效率。 

3. 在您的模型中，您可以 [建立解壓縮程式](create-an-extractor.md) ，以從每個合約提取特定的資料片段。 例如，對於每個合約，您最關心的資訊是用戶端是誰、合同工的名稱，以及總成本。

4. 成功建立模型之後，請[將其套用至 SharePoint 文件庫](apply-a-model.md)。 當您將檔上傳至文件庫時，您的檔理解模型會執行，並會識別和分類所有符合您在模型中定義的合約內容類型的檔案。 分類為合約的所有檔案都會顯示在自訂文件庫視圖中。 檔案也會顯示您在解壓縮程式中所定義之每個合約的值。

   ![文件庫中的合約](../media/content-understanding/doc-lib-solution.png)

5. 此外，如果您有合約的保留需求，也可以使用您的模型套用 [保留標籤](apply-a-retention-label-to-a-model.md) ，以防止在指定的時間內刪除您的合約。

## <a name="next-step"></a>下一步

[步驟2。使用 Microsoft Teams 建立您的合約管理通道](solution-manage-contracts-step2.md)