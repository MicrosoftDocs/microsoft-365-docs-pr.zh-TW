---
title: Microsoft SharePoint Syntex 採用：快速入門
description: 瞭解如何在組織中使用和執行 SharePoint Syntex，以協助您解決業務問題。
ms.author: samanro
author: samanro
manager: pamgreen
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
ms.openlocfilehash: 62e65f9be25e2c482cca78577048d504ee93097a
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698973"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Microsoft SharePoint Syntex 採用：快速入門

請將 SharePoint Syntex 中可用的智慧內容服務看作有三個部分：

- **內容瞭解：** 建立無程式碼的 AI 模型，以分類及提取內容中的資訊，以自動套用中繼資料以進行知識探索和重複使用。 深入瞭解 [內容瞭解](document-understanding-overview.md)。
- **內容處理：** 自動化內容的捕獲、攝取和分類，並使用 Power Automate 簡化以內容為中心的流程。 深入瞭解 [內容處理](form-processing-overview.md)。
- **內容規範：** 控制和管理內容，以改進安全性和管理與 Microsoft 資訊保護的整合。

透過全新的 AI 服務和功能，您可以使用 SharePoint Syntex，將內容瞭解和分類應用程式直接組建至內容管理流程。 有兩種不同的方式可以瞭解您的內容。 您使用的模型類型是以檔案格式和使用案例為基礎：

| 表單處理 | 文件瞭解 |
|:-------|:-------|
| 從文件庫建立。 | 在內容中心建立，SharePoint Syntex 的一部分。 |
| 在 [AI 產生器] 中建立的模型。 | 在原生介面中建立的模型。 |
| 用於半結構化檔案格式。 | 用於非結構化檔案格式。 |
| 可設定的分類器。 | Trainable 具有選用擷取器的分類器。 |
| 限制于單一文件庫。 | 可以適用於多個文件庫。 |
| 在 PDF，JPG，PNG 格式，總 50 MB/500 pp 進行訓練。 | 訓練 5 到 10 個 PDF、Office 或電子郵件檔案，包括負面範例。 |

如需更完整的功能比較，請參閱 [檔瞭解和表單處理模型之間的差異](difference-between-document-understanding-and-form-processing-model.md)。

## <a name="identify-pilot-business-scenarios-to-optimize"></a>識別試驗性商務案例以進行優化

若要準備在組織中使用 SharePoint Syntex，您必須先瞭解其有用的案例。 「原因」會協助決定所需的模型，以及如何根據模型套用的位置來組織組織。 以下是一些檔理解可協助貴組織的案例：

- **內容處理：** 處理合約、工作說明及其他類似表單的檔。 使用表單，訓練模型以瞭解和對應欄位，然後執行表單以自動收集資料。 如需詳細資訊，請參閱 [表單處理一覽](form-processing-overview.md)。
- **發票分析：** 從發票拔出相關的詳細資料，確定他們遵循原則或進行適當處理。

請思考 SharePoint Syntex 可如何協助您的組織的方式：

- 自動化商務程式
- 提高搜尋精確度
- 管理規範風險

當您考慮要考慮的商務案例時，請詢問您下列問題：

- 是否會解決實際的問題？
- 是否會廣泛使用或會影響整體效果？
- 是否可獲得？
- 您可以衡量是否成功？

根據影響和簡化的執行排定案例的優先順序。 讓您的初始焦點區域可輕鬆實施，也是較高的影響案例。 取消的優先順序較低的影響案例很難實施。

使用[範例案例和使用案例](adoption-scenarios.md)，提示您如何在組織中使用 SharePoint Syntex。

## <a name="identify-roles--responsibilities"></a>識別角色 & 責任

決定貴組織中誰將建立及管理模型？ 可能包含下列角色：

| SharePoint/Knowledge 系統管理員 | 電源平臺管理員 | 知識管理員 | 模型擁有者 |
|:-------|:-------|:-------|:-------|
| AAD 角色| AAD 角色 | AAD 角色 | 風雲人物 |
| 設定表單處理 | 設定一般資料服務環境進行表單處理 | 收集使用案例 | 收集商務使用案例 |
| 管理內容中心和許可權| 購買及分派 AIB 學分 | 建立最佳作法並回顧模型分析 | 建立及套用模型 |

知識管理員、商務程式擁有人和內容模型擁有者建立組織的範例模型和冠軍採用。
其他可能參與的人員：合規性管理員、分類法管理員。

他們會在何處建立及套用模型？ 是否有現有的進程或存放庫可以增強？

- 表單處理：決定將取得表單處理動作的網站。
- 檔瞭解：您可以為不同的業務區域建立多個內容中心。

## <a name="strategic-positioning"></a>戰略定位

與相關者合作，確定他們已對齊使用 SharePoint Syntex 的策略。 調查並提供下列資源，以協助此位置：

- 商務成果：
  - 潛在的會計結果
  - 潛在的靈活性結果
  - 商務成果範本
- 專案關係人/Exec 承辦人購買/對齊
  - 業務案例卡座
  - 財務模型
  - 公司就緒性-文化

## <a name="identify-stakeholders"></a>識別專案關係人

識別您專案的專案關係人。

|角色 |責任 |部門 |
|:-------|:-------|:--------|
| 執行贊助者 (s)    | 向公司傳達高階願景和價值   |  執行領導   |
| Project 潛在客戶 (s)  | 監督整個啟動的執行和推出程序 | 專案管理 |
| 知識系統管理員| 建立及管理內容中心 | IT 或其他部門|
| 內容管理員和模型擁有人| 收集使用案例及建立及套用模型 | 任何部門|
| 風雲人物 | 協助宣傳及管理異議處理 | 任何部門 (員工) |
| 租用戶系統管理員 | 設定租用戶層級設定 | IT 部門|
| Power Platform 系統管理員| 設定一般資料服務環境 | IT 部門|

> [!Note]
> 雖然我們建議您在整個部署中完成上述每個角色，但您可能會發現您不需要所有這些角色即可開始使用已識別的解決方案。

## <a name="readiness-checklist"></a>準備工作表

若要準備好執行 SharePoint Syntex，您必須執行下列作業：

![內容瞭解的準備工作](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. 規劃結束狀態
    - 檔理解模型是指這種方式，而不是結束。
    - 規劃如何利用下列各項所提取之中繼資料的價值：
      - 搜尋
      - 篩選和查看格式設定
      - 合規性
      - 自動化
2. 識別
    - 瞭解現有的資訊架構和內容管理功能使用。
    - 是否有任何現有的內容類型適合模型？
    - 中繼資料會改善哪些現有的處理常式？
3. 設計
    - 設計您的資訊架構、受管理的中繼資料和內容類型的方法
    - 設計定義、建立、管理的程式。

## <a name="engage-your-organization"></a>與您的組織合作

1. 找出有序的持有者、確認案例，以及制定專案計劃。
1. 設定並套用授權。
1. 開始認知與訓練–招聘冠軍。
1. 分階段進行。  
1. 收集意見反應並進行迴圈。
1. 根據需要，隨著流量成長對任何 AI 產生器的使用。

## <a name="see-also"></a>另請參閱

[SharePoint Syntex 的案例和使用案例](adoption-scenarios.md)