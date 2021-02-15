---
title: 表單處理概觀
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 了解 Microsoft SharePoint Syntex 中的表單處理
ms.openlocfilehash: 4a6ecc9e6eaca6f0b61f8c04b67eabb29674f6bd
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242443"
---
# <a name="form-processing-overview"></a>表單處理概觀

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

Microsoft SharePoint Syntex 使用 Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) 表單處理在 SharePoint 文件庫中建立模型。

您可以使用 AI Builder 表單處理來建立 AI 模型，這些模型使用機器學習技術從結構化或半結構化文件（如表單和發票）中識別和擷取機碼值對和表格資料。

組織通常從各種來源收到大量發票，如郵件、傳真、電子郵件等。處理這些文件並將其手動輸入資料庫可能需要相當長的時間。 透過使用 AI 來擷取文件中的文字、鑰匙/值對和表格，表單處理就能自動化這個流程。 

> [!NOTE]
> 如需有關表單處理案例範例的詳細資訊，請參閱 [SharePoint Syntex 採用：入門指南](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example)。

例如，可以建立一個識別上傳到文件庫的所有採購訂單文件的表單處理模型。 然後，您可以從每個採購訂單中擷取並顯示對您很重要的特定資料，例如 *採購單號*、*日期* 或 *總成本*。

![文件庫檢視](../media/content-understanding/doc-lib-done.png)</br>  

您使用範例檔案訓練模型，並定義要從表單中擷取的資訊。 文件的版面配置是透過訓練模型來學習的。 您只需五份表單文件即可開始使用。 AI Builder 將分析您範例檔案中的機碼值對，您也可以手動識別那些可能沒有偵測到的項。  AI Builder 讓您在範例檔案上測試模型的正確性。

訓練併發布模型之後，您的模型會建立 [Power Automate 流程](https://docs.microsoft.com/power-automate/getting-started)。 文件上傳至 SharePoint 文件庫時，將執行流程，並擷取在模型中識別的資料。 擷取的資料會顯示在模型文件庫檢視中的欄中。

Office 365 系統管理員需要為 SharePoint 文件庫[啟用表單處理](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding)，以便用戶能够在其中[建立表單處理模型](create-a-form-processing-model.md)。 您可以在設定期間選取網站，或之後在管理設定中進行設定。

### <a name="file-limitations"></a>檔案限制

使用表單處理模型時，請務必記得[檔案使用量的需求和限制](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)。



## <a name="see-also"></a>另請參閱
  
[Power Automate 文件](https://docs.microsoft.com/power-automate/)

[建立表單處理模型](create-a-form-processing-model.md)

[文件瞭解概觀](document-understanding-overview.md)

[訓練：使用 AI Builder 改善商務效能](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
