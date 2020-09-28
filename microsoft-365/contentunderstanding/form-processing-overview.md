---
title: 表單處理概覽
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 深入瞭解 Microsoft SharePoint Syntex 中的表單處理
ms.openlocfilehash: 518bc13017762bbe21420a81726e89c9c327834d
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295173"
---
# <a name="form-processing-overview-preview"></a>窗 (預覽中的表單處理一覽) 

本文內容適用于 Project Cortex 私人預覽。 [進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。

Project Cortex 使用 Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) 表單處理，以在 SharePoint 文件庫中建立模型。

您可以使用 AI 建造器表單處理建立 AI 模型，使用電腦學習技術來識別及提取結構化或半結構化檔（如表單和發票）中的索引鍵-值對和資料表資料。

使用 AI Builder 表單處理建立 AI 模型，利用機器教學 (ML) 技術，識別及解壓縮結構化或半結構化檔（例如表單和發票）中的索引鍵值對和資料表資料。

組織通常會從各種來源（例如郵件、傳真、電子郵件等）接收大量的發票。處理這些檔並手動將其輸入資料庫中，可能需要相當長的時間。 透過 AI 提取文字、索引鍵/值組及檔中的表格，表單處理過程會自動化此程式。 

例如，您可以建立表單處理模型，識別所有上傳至文件庫的採購訂單檔。 您可以從每個購買訂單提取及顯示對您很重要的特定資料，例如 *PO 編號*、 *日期*或 *總成本*。

您也可以使用範例檔案訓練模型及定義要從表單提取的資訊。 您可以透過訓練模型來瞭解檔的版面配置。 您至少需要5個表單檔才能開始使用。 AI 大樓會分析索引鍵-值對的範例檔案，然後手動識別可能未偵測到的檔案。  AI 產生器可讓您在範例檔案上測試模型的準確性。

訓練及發行模型之後，請使用它來建立在檔案上傳至 SharePoint 文件庫之後所執行的 [電源自動化流程](https://docs.microsoft.com/power-automate/getting-started) 。 然後，它會解壓縮已在模型中識別的資料。 解壓縮的資料會顯示在模型文件庫視圖中的欄中。

您可以使用範例檔案訓練模型及定義要從表單提取的資訊。 您可以透過訓練模型來瞭解檔的版面配置。 您只需要五個表單檔即可開始。 AI 產生器會分析您的索引卷碼對的範例檔案，也可以手動識別可能未偵測到的範例檔案。  AI 產生器可讓您在範例檔案上測試模型的準確性。

訓練及發行模型之後，您可以使用它來建立 [電源自動化流程](https://docs.microsoft.com/power-automate/getting-started)。 當檔案上傳至 SharePoint 文件庫，並提取已在模型中識別的資料時，就會執行此流程。 解壓縮的資料會顯示在模型文件庫視圖中的欄中。

Office 365 系統管理員需要為 SharePoint 文件庫 [啟用表單處理](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) ，讓使用者能夠在其中 [建立表單處理模型](create-a-form-processing-model.md) 。

## <a name="see-also"></a>另請參閱
  
[電源自動化檔](https://docs.microsoft.com/power-automate/)</br>
[建立表單處理模型](create-a-form-processing-model.md)</br>
[檔理解概述](document-understanding-overview.md)</br>
[訓練：使用 AI 產生器改進商務效能](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
