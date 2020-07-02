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
ms.openlocfilehash: 6678ec03d2cd87a97244acaa55a15483d78dd632
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022190"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Microsoft 規範分數（預覽）發行附注

**本文內容：** 此頁面顯示[Microsoft 規範評分](compliance-score.md)的公開預覽中的**新**功能，可讓您及早存取新功能。

## <a name="assessment-creation-and-management-functionality"></a>評估建立和管理功能

2020年6月新增功能可讓使用者以相容性分數直接建立、刪除和管理其評估。 先前，所有評估管理都是在合規性管理員中。 當您以合規性分數建立或修改評估時，系統會在合規性管理員中呈現更新。 同樣地，在合規性管理員中執行的任何評估工作都會以相容性分數呈現。 瞭解如何[在合規性分數中管理評估](compliance-score-assessments.md)。 請注意，範本的建立及修改仍會在合規性管理員中進行管理。

## <a name="new-templates-for-assessments"></a>新的評估範本

新的準備好使用的範本可用於評估，在其可供使用時，會以符合性分數發行。 [在這裡檢查範本的完整清單](compliance-score-templates.md)。 最近新增：

- 杜拜資訊安全性解析（DGISR）

## <a name="compliance-score-relationship-to-compliance-manager"></a>合規性分數與合規性管理員的關係

現在，在合規性管理員中處理的許多功能都可以在合規性分數中完成。 不過，某些功能仍會在合規性管理員中運作。 在公開預覽期間，當您使用合規性分數和合規性管理員時，請牢記下列幾點：

 - **建立評估的範本**： 
   - 使用者必須移至合規性管理員，以[建立新的範本並修改現有的範本](working-with-compliance-manager.md#templates)。
   - 新的範本必須包含**產品****和憑證**的維度。
 - **設定許可權**：在合規性管理員中未具有許可權的使用者，必須在 Microsoft 365 規範中心內設定其許可權（[深入瞭解](compliance-score-setup.md#set-user-permissions-and-assign-roles)）。
- **資料傳輸**：具有合規性管理員中之資料的組織，將會看到相容性分數中的資料，也就是另一種方式，也是如此。
- **從合規性分數登入合規性管理員**：如果使用者已登入合規性分數，並選取連結以移至合規性管理員，使用者就不需要重新登入。 按一下連結後，在瀏覽器中會開啟一個新的索引標籤，其上會有一個對話方塊。 在標頭為「已是 Microsoft cloud services 客戶」的上方區段中？ 登入您的帳戶，選取 [登**入**] 按鈕，以自動登入合規性管理員。

## <a name="known-issues-in-compliance-score-preview"></a>合規性分數中的已知問題（預覽）

下列章節涵蓋相容性分數的發行版本本中，待解決的已知問題。

### <a name="long-load-times-for-non-admin-users"></a>非系統管理使用者的長載入時間
合規性分數當嘗試登入時，保留非系統管理員角色角色的使用者可能會經歷很長的載入時間。 重新整理瀏覽器將會解決此問題。 深入瞭解[合規性分數角色](compliance-score-setup.md#set-user-permissions-and-assign-roles)。

### <a name="supported-browsers"></a>支援的瀏覽器

- 支援最新版本的 Microsoft Edge、Chrome 和 Safari。
- 重新整理瀏覽器之後，有時候不會出現更新的資料。
- 不支援 Internet Explorer。
