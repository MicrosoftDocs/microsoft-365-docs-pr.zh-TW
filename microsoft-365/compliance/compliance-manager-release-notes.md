---
title: Microsoft 合規性管理員版本資訊
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合規性管理員是 Microsoft 服務信任入口網站中免費的工作流程型風險評估工具。 合規性管理員可讓您追蹤、指派及驗證與 Microsoft 雲端服務相關的法規遵從性活動。
ms.openlocfilehash: de69d4c7e5938d8bfd3fed74b9ae44288e48019c
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141538"
---
# <a name="microsoft-compliance-manager-preview-release-notes"></a>Microsoft 合規性管理員（預覽）發行附注

合規性管理員的公開預覽可讓您及早存取即將推出的功能和更新。 此頁面包含目前版本的新功能、改進功能和已知問題的更新。

您可以在[服務信任入口網站](https://servicetrust.microsoft.com)上使用[合規性管理員](https://servicetrust.microsoft.com/ComplianceManager)工具，以追蹤、指派及驗證與 Microsoft 雲端服務相關的法規遵從性活動。

## <a name="improved-template-creation-and-update-process"></a>改進範本的建立和更新程式

我們已更新用來匯入、匯出及修改評估範本的程式。 新的簡化體驗可讓您更輕鬆地將自己的評估帶入您的工作流程中並保持更新。

### <a name="the-old-process"></a>舊進程

在合規性管理員中建立範本的方式有兩種。 您可以複製現有的範本，或將範本資料從 Excel 試算表匯入新的範本。 您可以從 [**範本**] 頁面中，選取 [**新增範本**]，以建立全新的範本，方法是輸入名稱、選取 [維度]，並上傳具有特定格式及架構的 Excel 檔案。 或者，您可以選取 [**從現有範本複製**] 方塊中，選取要複製的範本，然後驗證維度。 設計自訂您的範本需要執行多步驟程式，方法是在建立範本後選取 [**新增自訂控制項**]。

### <a name="the-new-process"></a>新進程

我們使您建立新的範本變得更容易。 在單一步驟**擴充**過程中，您可以將動作和控制項的試算表新增至現有的 Microsoft 範本，以製作您自己的自訂版本。 在 [合規性管理員] 的 [**範本**] 頁面上，選取 [ **+ 新增範本**]。 在 [**範本**] 飛入窗格上，選取 [**從通用範本建立副檔名**] 核取方塊。 您可以使用比上一個複雜的新 Excel 格式，新增自訂。 這個新程式會取代**現有範本**的先前副本，並**新增自訂控制項**函數。

每次使用下列所述的版本設定程式更新原始評估時，您的自訂評估會繼承這些更新，並保留您的自訂控制項。

此外，您也可以輕鬆修改您自己的現有範本。 您可以匯出範本，在相同的活頁簿中進行變更，然後使用儲存的編輯匯入。

查看使用此新程式[建立範本](working-with-compliance-manager.md#templates)的詳細指示。

## <a name="versioning-notice-and-control"></a>版本設定通知和控制

您的組織已于2020年4月發行的合規性管理員中收到更新的評估，以協助您對齊認證和法規更新。 向前發展，我們將為您提供一種方法，讓您瞭解並透過版本設定**警示**接受所有未來的更新。

每當可用於評估範本或改進動作的更新時，提醒圖示會通知您已準備好更新。 當您按一下該圖示時，會快顯視窗來說明更新，並提示您接受。 選取警示圖示會顯示彈出窗格，說明更新並提示您接受。 深入瞭解[接受評估的更新](working-with-compliance-manager.md#versioning-alerts-for-assessment-updates)。

## <a name="common-actions-will-synch-status-across-groups"></a>一般動作會在群組間同步處理狀態

如果您的組織有多個評估群組，**技術**動作的行為（也就是影響整個組織的動作）已變更。 群組間的任何重複動作都已合併成一個單一動作。 單一巨集指令包含重複版本的所有上傳的記事及證據。 使用此變更，技術動作現在會如同屬於相同群組時的行為。 在一個群組或評估中對動作所做的任何變更現在都會反映在所有的實例中。 「**實施」狀態**、「**實施日期**」、「**測試狀態**」及「**測試日期**」會反映最新的更新。

## <a name="language-support"></a>語言支援

合規性管理員現在可用於下列語言，除了英文：中文（簡體）、中文（繁體）、法文、德文、義大利文、日文、韓文、葡萄牙文（巴西）、俄文及西班牙文。

## <a name="known-issues-in-compliance-manager-preview"></a>合規性管理員中的已知問題（預覽）

下列章節涵蓋合規性管理員目前版本中的已知問題。

### <a name="compliance-score"></a>合規性分數

- 對於標示為**Not In 範圍**的動作專案，指派給交辦事項的分數不會從相容性分數計算中排除。 標記為**Not In 範圍的**動作專案不會提升您的合規性分數。

### <a name="secure-score"></a>安全分數

- 在某些 Microsoft 365 和 Office 365 訂閱中，有些動作專案無法使用安全分數結果。 在這些情況下，**無法偵測到**安全分數結果。
- 有時候會為對應的原則及未完成的動作專案傳回安全分數結果。
- 針對新承租人，會自動開啟所有動作的安全分數更新。 全域管理員可以將安全計分連續更新切換為 [關閉]，這樣會關閉所有動作的更新。
  - **附注**：當組織第一次部署 Microsoft 365 或 Office 365 時，會花大約7天的時間進行安全的評分，以完全收集資料，並將其劃分為您的分數。 在這段時間內，將安全計分連續更新參數設定為**Off** ，並手動設定所要**執行**的動作，就會將該動作計算為您的分數。 在最初7天后，開啟安全分數連續更新會啟用從該點繼續進行監視。
- 當安全分數更新開啟時，安全分數會積極監控動作，不過動作的測試日期不會更新以反映監控。
- 當建立新的評估時，會自動包含 Microsoft 受管理的控制分數和安全分數整合。
- 安全分數整合不支援的任何動作都可以手動實施。 手動執行將會考慮該動作群組的分數。

### <a name="export"></a>匯出

- 當範本的狀態設定為 [匯**入**] 或 [**待處理核准**] 時，範本匯出至 JSON 失敗。

### <a name="supported-browsers"></a>支援的瀏覽器

- 支援最新版本的 Microsoft Edge、Chrome 和 Safari。
- 在您的瀏覽器重新整理之前，可能會出現更新的資料不會出現的情況。
- 不支援預覽版本的 Microsoft Edge，但沒有已知問題。
- 不支援 Internet Explorer。

### <a name="session-timeout"></a>會話超時

- 當會話超時時，可能會出現「發生錯誤」錯誤。 若要解決此問題，請移至 [[合規性管理員](https://servicetrust.microsoft.com/ComplianceManager)]，然後再登入。