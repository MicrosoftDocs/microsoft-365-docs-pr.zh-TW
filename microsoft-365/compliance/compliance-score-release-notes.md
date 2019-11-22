---
title: Microsoft 合規性分數版本資訊
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
description: 版本資訊及已知的問題的 Microsoft 合規性分數 （預覽），可協助簡化和自動化風險評定 M365 合規性中心中的功能。
ms.openlocfilehash: d46e8a621b6f4daa1275a78b5cc1e6917e0a997c
ms.sourcegitcommit: 3eae8fe39cea912d29e211a1c9fd035d6b606f91
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793637"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Microsoft 合規性分數 （預覽） 版本資訊

Microsoft 合規性分數公開預覽為您提供搶先即將推出的功能和更新。

合規性分數是在[Microsoft 365 合規性中心](microsoft-365-compliance-center.md)，計算風險分數，測量向完成建議的動作，協助減少合規性風險您進行的新功能。

## <a name="compliance-score-and-compliance-manager-relationship"></a>合規性分數和合規性管理員中的關聯性

許多處理合規性管理員中的符合性功能現在可以完成合規性分數。 不過部分功能仍會保留僅限合規性管理員中，並公開預覽期間變更合規性管理員中的某些舊版功能。 

當您在公開預覽期間使用合規性分數和合規性管理員中，請記住以下幾點：

- **管理評估**： 使用者可以檢視 「 評估 」 以及其狀態的詳細資料合規性分數。 不過使用者只能在合規性管理員 （的[檢視指示](working-with-compliance-manager.md#assessments)），以及工作執行評定的管理工作，並受限於下列：
    - 上傳新的評估，但不是能修改現有 「 評估 」。 如果您要修改現有的評估，您將需要上傳新的範本。
    - 匯出評估
    - 封存評估
    - 檢視封存的評估
 - **建立範本的 「 評估 」**: 
   - 使用者必須移至合規性管理員中建立新的範本，並匯出現有範本。 
   - 無法自訂現有範本。 請閱讀[管理範本合規性管理員中](working-with-compliance-manager.md#templates)的指示。
   - 在建立範本時，您必須包含維度這兩個**產品**和**憑證**以確保您的範本會顯示在 [合規性分數。
 - **設定權限**： 不先前授與權限合規性管理員中的合規性分數使用者必須在 Microsoft 365 合規性中心中設定其權限。 使用合規性分數時，其角色先前設定合規性管理員中的使用者可以使用該相同層級的存取。
- **傳輸的資料**： 組織的合規性管理員中的資料將會看到的資料合規性分數，反之亦然。
- **登入到合規性管理員從合規性分數**： 如果使用者登入合規性分數，並選取連結移至合規性管理員中，使用者將不必再次登入。 按下連結之後, 的新索引標籤開啟瀏覽器主講人是舊檔] 對話方塊中。 在 [使用標頭 [top] 區段中，「 已 Microsoft 雲端服務客戶嗎？ 您的帳戶，登入]，選取 [自動登入到合規性管理員的**登入**] 按鈕。

## <a name="known-issues-in-compliance-score-preview"></a>在 [合規性分數 （預覽） 的已知的問題

下列各節涵蓋解析的合規性分數的未來版本的已知的問題。

### <a name="launch-now-links-in-certain-improvement-actions"></a>啟動現在特定改進動作中的連結

在某些改進的動作，選取 [**立即啟動**連結下方的實作指示出現會產生錯誤。 若要存取的適當的目的地，也就是 SharePoint 系統管理中心，請遵循下列步驟：

1. 移至[Microsoft 365 系統管理中心](https://admin.microsoft.com)。
2. 在左的導覽功能表上，選取 [**全部顯示**]。
3. 在**系統管理中心，** 選取 [ **SharePoint**]。

以下是受影響的改進的動作，所有位於**保護資訊**類別：
  - 將加密套用至 SharePoint 文件庫
  - 線上分類 SharePoint 中的資料
  - 設定到期的外部共用連結
  - 啟用版本設定的文件庫

### <a name="long-load-times-for-non-admin-users"></a>非管理員使用者的長載入時間
保留以外的系統管理員角色的角色的合規性分數使用者可能會遇到長載入時間時，嘗試登入。 重新整理瀏覽器可解決這個問題。 （深入了解[合規性分數角色](compliance-score-setup.md#set-user-permissions-and-assign-roles)。）

### <a name="supported-browsers"></a>支援的瀏覽器

- 支援最新版的 Microsoft Edge、 Chrome 和 Safari。
- 可能會有更新的資料不會在重新整理瀏覽器直到出現的執行個體。
- Microsoft Edge 的預覽版本不支援，但有任何已知的問題。
- 不支援 Internet Explorer。
 
### <a name="language-support"></a>語言支援

- 合規性分數是僅提供英文 （美國）。