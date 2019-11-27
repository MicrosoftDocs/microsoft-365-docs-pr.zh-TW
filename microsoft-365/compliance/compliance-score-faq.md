---
title: Microsoft 合規性分數常見問題集
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
description: 尋找關於 Microsoft 合規性分數，可協助組織常見問題的答案簡化和自動化風險評定。
ms.openlocfilehash: bc0ddfe71a3de2bbfa2c9c9a0fdc507a540daf90
ms.sourcegitcommit: 3eae8fe39cea912d29e211a1c9fd035d6b606f91
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2019
ms.locfileid: "39625396"
---
# <a name="microsoft-compliance-score-preview-frequently-asked-questions"></a>Microsoft 合規性分數 （預覽） 的常見問題集

## <a name="what-is-compliance-score"></a>合規性分數是什麼？

Microsoft 合規性分數是在[Microsoft 365 合規性中心](microsoft-365-compliance-center.md)，可協助您了解貴組織的合規性狀態的預覽功能。 它會計算測量中完成協助減少資料保護和法規的標準周圍的風險的動作您進行風險分數。 它也會提供協助連線常見的控制項之間金鑰法規和標準，所以您可能需要一個動作來滿足多個需求在此同時，並更妥善地調整您的合規性程式的內建控制項對應。

## <a name="how-do-i-access-compliance-score"></a>如何存取合規性分數？

移至[Microsoft 365 合規性中心](https://compliance.microsoft.com/)和**登入**與 Microsoft 365 全域系統管理員、 符合性系統管理員或規範資料的系統管理員角色。 左側的導覽窗格上，選取 [**合規性分數**。 您應該會看到您的[合規性分數儀表板與您的分數](compliance-score-setup.md#understand-the-compliance-score-dashboard)。 如果您沒有適當的角色存取權，貴組織的全域系統管理員可以授與您的權限。

## <a name="what-roles-or-permissions-are-needed-to-use-compliance-score"></a>使用合規性分數所需的角色或權限為何？

合規性分數使用角色型存取控制 (RBAC) 權限模型，以及您可以執行的動作取決於角色指派給您的類型。 貴組織的 Microsoft 365 全域系統管理員是可以執行安裝程式功能並管理中合規性分數角色的人員。 在最低限度下，使用者會需要**Azure AD 全域讀者**角色，才能讀取資料合規性分數。 深入了解權限、 角色和[合規性分數安裝程式](compliance-score-setup.md)在安裝程序。

## <a name="what-is-the-difference-between-compliance-score-and-compliance-manager"></a>合規性分數和合規性管理員之間的差異為何？

合規性分數和合規性管理員共用相同的後端]，但可在兩個不同的位置 （合規性分數是在 Microsoft 365 合規性中心，而合規性管理員在 Microsoft 服務信任入口網站）。 合規性分數視為簡化的合規性管理員版本，讓您更完整檢視您的組織目前合規性狀態並改善其時可採取的步驟。 雖然您可以執行許多動作，直接在合規性分數，某些功能會現在位於合規性管理員中。 閱讀的有關[合規性分數和合規性管理員之間的關聯性](compliance-score.md#relationship-to-compliance-manager)的詳細資訊。

## <a name="who-should-use-compliance-score-and-who-should-use-compliance-manager"></a>誰應使用合規性分數，以及誰應使用合規性管理員？

合規性分數是適合貴組織使用者所扮演的角色監視合規性和 save 為了遵守法規標準活動中的每個人。 使用合規性分數，您不需要先熟悉法規和標準，可協助改善貴組織的資料保護。 合規性分數是最佳的起始位置的所有使用者。 從這裡開始，您可以看到您的合規性分數，了解哪些建議的動作可協助降低風險，並在許多情況下，啟動從右到解決方案來執行這些動作。

現在，合規性管理員是讓使用者可以管理評估及建立自訂範本，以建立 「 評估 」 的位置。 深入了解[哪些動作支援僅由合規性管理員](compliance-score-release-notes.md#compliance-score-and-compliance-manager-relationship)期間公開預覽。

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>如果我有較高的分數，意思我已經完全相容？

否。 合規性分數測量您在完成建議的動作，協助減少資料保護和法規的標準周圍的風險的進度。 它不會不 express 與任何特定的標準或法規的組織符合性絕對量值。 合規性分數不應該解譯成保證郵件可以以任何方式。

## <a name="what-regulations-and-standards-does-compliance-score-monitor"></a>哪些法規和標準沒有合規性分數監視？

合規性分數可讓您根據 Microsoft 365 的資料保護基準，這是一組控制項包含一般產業法規及標準初始分數。 此基準線繪製元素，主要是從 NIST CSF （National Institute of Standards 和技術 Cybersecurity Framework） 和 ISO （國際標準組織），以及從 FedRAMP （聯邦風險與授權管理程式） 和 GDPR （歐盟地區的一般資料保護規定）。

組織可以建立並新增至其組織更相關的自訂評估。 您可以使用下列其中一個合規性分數[的方塊出範本](compliance-score.md#templates)來建立評估特定標準，或[建立自己的範本](working-with-compliance-manager.md#create-a-template-1)。

閱讀的有關[合規性分數的分數的計算方式](compliance-score-methodology.md)的詳細資訊。

## <a name="what-is-the-difference-between-compliance-score-and-secure-score"></a>合規性分數和安全分數之間的差異為何？

合規性分數提供廣泛的檢視貴組織的資料保護和合規性狀態。 合規性分數也提供內建工作流程的工具;它可讓組織將工作指派給使用者、 追蹤控制項實作和測試狀態，並上傳的辨識項，並建立稽核報告。

Microsoft 安全分數是協助了解您的安全性狀態安全性分析工具。 [解更多關於安全分數，以及如何運作](../security/mtp/microsoft-secure-score.md)。

## <a name="which-cloud-services-are-covered-by-compliance-score"></a>合規性分數所涵蓋的雲端服務？

合規性分數目前提供 Office 365 和 Intune 的評估。 展開的涵蓋範圍在未來版本中，為預期中，將述[合規性分數版本資訊](compliance-score-release-notes.md)。

## <a name="can-i-use-compliance-score-for-non-microsoft-products"></a>可以使用合規性分數非 Microsoft 產品？

雖然合規性分數提供持續監視，以及建議的動作僅適用於 Microsoft 雲端服務，您可以新增自訂的評估合規性管理員中您內部部署，第三方服務。 如此一來，您可以使用 Microsoft 合規性分數為 SaaS 規範管理工具，可協助您透過您的數位資產管理的所有控制項。

您可以使用下列其中一個合規性分數[的方塊出範本](compliance-score.md#templates)來建立評估特定標準，或[建立自己的範本](working-with-compliance-manager.md#create-a-template-1)。

## <a name="how-do-i-delete-a-template-or-assessment-i-no-longer-need"></a>如何刪除的範本或不再需要的評定？

您無法刪除評估或範本，但您可以將它們隱藏從檢視。 檢閱[隱藏 「 評估 」 的指示](working-with-compliance-manager.md#hide-a-template-or-an-assessment)。