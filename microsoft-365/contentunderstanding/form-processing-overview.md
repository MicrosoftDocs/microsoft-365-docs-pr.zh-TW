---
title: 表單處理概覽（預覽）
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解 Project Cortex 中的表單處理。
ms.openlocfilehash: 9709c8170f5dc6ce0edbeb2d90cb4e1f6d759c64
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540055"
---
# <a name="form-processing-overview-preview"></a>表單處理概覽（預覽）
> [!Note]
> 本文內容適用于 Project Cortex 私人預覽。 [進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。

Project Cortex 使用 Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview)表單處理，以在 SharePoint 文件庫中建立模型。
您可以使用 AI Builder 表單處理建立 AI 模型，其使用電腦學習技術來識別及提取結構化或半結構化檔（如表單和發票）中的索引鍵值對和資料表資料。

公司通常會從各種來源（例如郵件、傳真、電子郵件或人員）收到大量發票。 處理這些檔並手動將其輸入資料庫中，可能需要相當長的時間。 使用 AI 提取文字、索引鍵/值組及檔中的表格，表單處理將會自動化此程式。 

例如，您可以建立表單處理模型，識別所有上傳至文件庫的採購訂單檔。 而且，您可以從每個購買訂單提取及顯示對您很重要的特定資料，例如*PO 號碼*、*日期*或*總成本*。

您可以使用範例檔案訓練模型及定義要從表單提取的資訊。 您可以透過訓練模型來瞭解檔的版面配置。 您只需要五個表單檔即可開始。 AI 大樓會分析索引鍵-值對的範例檔案，也可以手動識別可能未偵測到的範例檔案。  AI 產生器可讓您在範例檔案上測試模型的準確性。

訓練及發行模型之後，若要使用它，您可以在將檔案上傳至 SharePoint 文件庫時，建立將執行的[電源自動化流程](https://docs.microsoft.com/power-automate/getting-started)，並且提取已在模型中識別的資料。 解壓縮的資料會顯示在模型文件庫視圖中的欄中。

Office 365 系統管理員需要為 SharePoint 文件庫[啟用表單處理](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding)，讓使用者能夠在其中[建立表單處理模型](create-a-form-processing-model.md)。



## <a name="see-also"></a>另請參閱
  
[電源自動化檔](https://docs.microsoft.com/power-automate/)</br>
[建立表單處理模型](create-a-form-processing-model.md)</br>
[檔理解概述](document-understanding-overview.md)</br>
[訓練：使用 AI 產生器改進商務效能](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




