---
title: 執行 Microsoft SharePoint Syntex 的試用版
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: 瞭解如何規劃及執行組織中 SharePoint Syntex 的試用試驗計畫。
ms.openlocfilehash: 2668c0c85d6b8c73d377ac9efffc7f777fc7add6
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327091"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a>執行 Microsoft SharePoint Syntex 的試用版

本文說明如何設定和執行試驗試驗計畫，以在您的組織中部署 SharePoint Syntex。 此外，它也會建議試用版的最佳作法。

## <a name="sign-up-for-a-trial"></a>註冊試用版

SharePoint Syntex 的試用版可讓300使用者存取30天。

> [!NOTE]
> 在試用版中，最多可包含300個使用者，以確保自動新增 1000000 AI 產生器信用。 您不需要包含300使用者的試用版，即可成功試用。

您可以從下列其中一個來源取得試用版：

- [SharePoint Syntex 產品頁面](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)

- [Microsoft 365 系統管理中心](https://admin.microsoft.com)
    1.  登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。
    2.  移至 **帳單**  >  **購買服務**。
    3.  向下捲動至 **[附加元件]** 區段。
    4.  在 [SharePoint Syntex] 麻將牌上，選取 [**詳細資料**]。
    5.  選取 **[取得免費試用版]**。
    6.  若要確認試用版，請遵循餘下的嚮導步驟。

您必須是 Microsoft 365 全域管理員或計費系統管理員，才能啟用試用版。

### <a name="who-should-be-involved-in-a-trial"></a>試用版中應包括神秘

|角色  |活動  |
|---------|---------|
|Microsoft 365 全域管理員或計費系統管理員    |     啟動試用和指派授權    |
|Microsoft 365 全域系統管理員或 SharePoint 系統管理員     |   設定 SharePoint Syntex 及建立內容中心      |
|商務使用者     |    模型建立及測試     |

### <a name="before-you-activate-a-trial"></a>啟動試用之前

若要成功規劃 SharePoint Syntex 試用版，請考慮下列因素：

- 在「實際世界」案例和資料中完成最有意義的測試。
- 每個租使用者僅能啟用一次 SharePoint Syntex 試用版。

測試或演示程式租使用者可以做為「幹即用」，以逐步進行啟用步驟和系統管理控制。 但最好是評估實際執行租使用者上的模型建立。

若要讓實際執行租使用者的試用的價值最大化，規劃和商務服務是必要的。 您應接洽一或多個商務區域，以識別可能由 SharePoint Syntex 解決的三至六使用案例。 這些使用案例應該：

- 包含可透過表單處理或檔理解模型解決的案例。
- 清楚瞭解任何解壓縮的中繼資料的用途;例如，使用 Power Automate 來查看格式設定或自動化。 雖然 SharePoint Syntex 專注于對檔進行分類及提取中繼資料，但要量化的值即為此中繼資料的啟用。
- 是以一組已定義的資料為基礎;例如，特定 SharePoint 網站或文件庫。 SharePoint Syntex 常見的誤解是一般用途模型可以套用到所有的組織內容。 更準確的觀點是建立模型，以協助解決目標位置中的特定業務問題。

所有這些使用案例可能不適合 SharePoint Syntex。 品質試用的目標不會證明 SharePoint Syntex 會符合所有案例。 相反地，這項試用版應該可協助您更進一步瞭解產品的價值。

針對每個計畫的使用案例，識別為相關內容或程式中的主題專家的使用者。 建立 SharePoint Syntex 模型是專注于內容中的網域專家，而不是 IT 專業人員或開發人員資源。

## <a name="activate-a-trial"></a>啟動試用版

當您啟動試用版時，您必須：

- 將授權指派給相關的使用者。
- 執行[SharePoint Syntex 的其他設定](set-up-content-understanding.md)。
    - 您可能想要 [建立其他內容中心](create-a-content-center.md)。

在啟動試用程式之後，您可以建立模型和處理檔。 請參閱 [建立模型的指導](create-a-content-center.md)方針。

## <a name="during-a-trial"></a>在試用期間

試用期是有限的，所以最初重點在於 SharePoint Syntex 模型是否可以分類檔，以及提取定義的使用案例的中繼資料。 試用期結束後，您就可以評估如何利用中繼資料。

## <a name="after-a-trial"></a>試用後

根據試用的結果，您可以決定是否要繼續使用 SharePoint Syntex 的生產。

### <a name="proceed-to-production-use"></a>繼續使用實際執行環境

為了確保服務的連續性，您必須購買必要數目的授權，並將這些授權指派給使用者。 試用期間結束時未獲得完整授權的試用使用者，將無法充分利用 SharePoint Syntex。

您可能需要估計您的表單處理的預期使用方式，並規劃預期的 AI 產生器信用量。 如需協助，請參閱 [預估適合您的 AI](https://powerapps.microsoft.com/ai-builder-calculator/)產生器容量。

### <a name="dont-proceed-to-production-use"></a>請勿繼續實際執行使用

如果您未在試用後購買授權：

- 您將無法建立新的模型。
- 執行模型的文件庫將不再自動分類檔案或提取模型。
- 任何先前分類的檔案或解壓縮的中繼資料都不會受到影響。 
- 內容中心和任何檔理解模型不會自動刪除。 如果您決定以後購買授權，這些功能仍可供使用。
- 表單處理模型會儲存在預設的 Power 平臺環境 (CD) 實例中的一般資料服務中。 您可以將這些功能與未來授權搭配使用，以供 SharePoint Syntex 或使用電源平臺中的 AI 產生器功能使用。

## <a name="see-also"></a>請參閱

[Microsoft SharePoint Syntex 採用：快速入門](adoption-getstarted.md)
