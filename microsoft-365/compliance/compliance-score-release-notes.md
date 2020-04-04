---
title: Microsoft 規範分數版本資訊
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
description: Microsoft 規範分數（預覽）的發行附注與已知問題，M365 規範中心的功能可協助簡化及自動化風險評估。
ms.openlocfilehash: dd7c99d2f0a86826be7803dc36e390250a4fc37b
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141548"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Microsoft 規範分數（預覽）發行附注

Microsoft 合規性分數的公開預覽可讓您及早存取即將推出的功能和更新。 請定期查看此頁面以瞭解新功能。

合規性分數是[Microsoft 365 規範中心](microsoft-365-compliance-center.md)中的新功能，可計算以風險為基礎的分數，衡量完成建議動作的進度，以協助降低法規遵從性風險。

## <a name="new-templates-for-assessments"></a>新的評估範本

新的預先設定的範本可在實際執行時發佈，以進行相容性分數（預覽）。 [在這裡檢查範本的完整清單](compliance-score.md#templates)。 最近新增的範本包括：

- 巴西一般資料保護法（LGPD）
- IRAP/澳大利亞政府 ISM （預覽）
- ISO 27701:2019
- SOC 1
- SOC 2

## <a name="improvements-in-managing-assessments"></a>管理評估的增強功能

2020年4月的相容性管理員的最新版本包括更新程式簡化了您建立及自訂評估的方式，並將其更新。 如需詳細資訊，請查看[合規性管理員版本](compliance-manager-release-notes.md)資訊。

## <a name="language-support"></a>語言支援

合規性分數現在可用於下列語言，除了英文：中文（簡體）、中文（繁體）、法文、德文、義大利文、日文、韓文、葡萄牙文（巴西）、俄文及西班牙文。

## <a name="common-actions-will-synch-status-across-groups"></a>一般動作會在群組間同步處理狀態

如果您的組織有多個評估群組，**技術**動作的行為（也就是影響整個組織的動作）已變更。 群組間的任何重複動作都已合併成一個單一動作。 單一巨集指令包含重複版本的所有上傳的記事及證據。 使用此變更，技術動作現在會如同屬於相同群組時的行為。 在一個群組或評估中對動作所做的任何變更現在都會反映在所有的實例中。 「 **實施」狀態**、「**實施日期**」、「**測試狀態**」及「**測試日期** 」會反映最新的更新。

## <a name="compliance-score-relationship-to-compliance-manager"></a>合規性分數與合規性管理員的關係

現在，在合規性管理員中處理的許多功能都可以在合規性分數中完成。 不過，某些功能仍會在合規性管理員中運作。 在公開預覽期間，當您使用合規性分數和合規性管理員時，請牢記下列幾點：

- **管理評估**：使用者可以在合規性分數中查看評估及其狀態詳細資料。 不過，使用者只能在合規性管理員中執行評估管理工作（[查看指示](working-with-compliance-manager.md#assessments)）。 這些工作的範例包括：
    - 建立及複製評估
    - 匯出評估
    - 封存評估
    - 查看封存的評估
 - **建立評估的範本**： 
   - 使用者必須移至合規性管理員，以建立新的範本並修改現有的[範本](working-with-compliance-manager.md#templates)。 
   - 建立範本時，您必須同時包含**產品**和憑證的維度 **，以**確保您的範本會以合規性分數顯示。
 - **設定許可權**：在合規性管理員中未具有許可權的使用者，必須在 Microsoft 365 規範中心內設定其許可權（[深入瞭解](compliance-score-setup.md#set-user-permissions-and-assign-roles)）。
- **資料傳輸**：具有合規性管理員中之資料的組織，將會看到相容性分數中的資料，也就是另一種方式，也是如此。
- **從合規性分數登入合規性管理員**：如果使用者已登入合規性分數，並選取連結以移至合規性管理員，使用者就不需要重新登入。 按一下連結後，在瀏覽器中會開啟一個新的索引標籤，其上會有一個對話方塊。 在標頭為「已是 Microsoft cloud services 客戶」的上方區段中？ 登入您的帳戶，選取 [登**入**] 按鈕，以自動登入合規性管理員。

## <a name="known-issues-in-compliance-score-preview"></a>合規性分數中的已知問題（預覽）

下列章節涵蓋相容性分數的發行版本本中，待解決的已知問題。

### <a name="long-load-times-for-non-admin-users"></a>非系統管理使用者的長載入時間
合規性分數當嘗試登入時，保留非系統管理員角色角色的使用者可能會經歷很長的載入時間。 重新整理瀏覽器將會解決此問題。 （深入瞭解[合規性分數角色](compliance-score-setup.md#set-user-permissions-and-assign-roles)）。

### <a name="supported-browsers"></a>支援的瀏覽器

- 支援最新版本的 Microsoft Edge、Chrome 和 Safari。
- 重新整理瀏覽器之後，有時候不會出現更新的資料。
- 不支援 Internet Explorer。
