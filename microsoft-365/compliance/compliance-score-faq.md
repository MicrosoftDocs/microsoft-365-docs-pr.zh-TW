---
title: Microsoft 合規性分數常見問題
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
description: 尋找 Microsoft 合規性分數的常見問題解答，協助組織簡化及自動化風險評估。
ms.openlocfilehash: 942de8f8cc9eeb958cb7f8e96c9e7038447ce3f1
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141558"
---
# <a name="microsoft-compliance-score-preview-frequently-asked-questions"></a>Microsoft 合規性分數（預覽）常見的常見問題

## <a name="what-is-compliance-score"></a>合規性分數為何？

Microsoft 合規性分數是[microsoft 365 規範中心](microsoft-365-compliance-center.md)的預覽功能，可協助您瞭解組織的合規性狀況。 它會計算以風險為基礎的分數，用以衡量您在完成動作方面的進展，以協助降低資料保護和法規標準的風險。 合規性分數提供內建的控制項對應，可協助在重要的規章和標準之間連接一般控制項，因此您可以採取一個動作來同時滿足多種需求，以及更好地擴充您的合規性計畫。

## <a name="how-do-i-access-compliance-score"></a>如何存取合規性分數？

請移至[microsoft 365 規範中心](https://compliance.microsoft.com/)，並以 microsoft 365 全域管理員、合規性管理員或合規性資料系統管理員角色登**入**。 在左導覽窗格上選取 [**合規性分數**]。 您應該會看到您[的評分分數儀表板與您的分數](compliance-score-setup.md#understand-the-compliance-score-dashboard)。 如果您沒有適當的角色存取權，您組織的全域系統管理員可以授與您的許可權。

## <a name="what-roles-or-permissions-are-needed-to-use-compliance-score"></a>使用合規性分數所需的角色或許可權為何？

合規性分數使用以角色為基礎的存取控制（RBAC）許可權模型，您可以執行的動作取決於指派給您的角色類型。 貴組織的 Microsoft 365 全域系統管理員是可以執行安裝程式功能，並在合規性分數中管理角色的人員。 使用者至少需要**AZURE AD 全域讀卡機**角色，才能以合規性分數讀取資料。 若要深入瞭解，請參閱[相容性分數設定](compliance-score-setup.md)的許可權、角色及設定程式。

## <a name="what-is-the-difference-between-compliance-score-and-compliance-manager"></a>合規性分數和合規性管理員之間的差異為何？

合規性分數和合規性管理員共用相同的後端，但是它們位於兩個不同的位置（合規性分數是在 Microsoft 365 規範中心內，而合規性管理員是在 Microsoft 服務信任入口網站中）。 請將合規性分數視為合規性管理員簡化版本，讓您能更完整地瞭解組織目前的相容性狀況，以及您可以採取的步驟加以改善。 雖然您可以直接在合規性分數內執行許多動作，但現在仍存在合規性管理員中的部分功能。 閱讀相關的[相容性分數和合規性管理員之間的關係](compliance-score.md#relationship-to-compliance-manager)。

## <a name="who-should-use-compliance-score-and-who-should-use-compliance-manager"></a>誰應該使用合規性評分，誰應該使用合規性管理員？

合規性分數適用于組織中扮演監控規範中角色的所有人員，並採取行動以協助遵守法規標準。 遵循合規性分數，您不需要熟悉法規和標準，以協助改善組織的資料保護。 合規性分數是所有使用者的最佳開始位置。 在這裡，您可以看到您的相容性分數，瞭解哪些建議動作可協助將風險降至最低，在許多情況下，請從正確啟動至解決方案以採取這些動作。

現在，「合規性管理員」是使用者可管理評估及建立自訂範本以建立評估的位置。 深入瞭解在公開預覽期間，[只有合規性管理員才能支援哪些動作](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager)。

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>如果我有高分，是否表示我完全相容？

否。 您的相容性分數會衡量您在完成建議的動作時所進行的進展，以協助降低資料保護和法規標準的風險。 它不會表達組織符合任何特定標準或法規的絕對度量。 合規性分數不應以任何方式轉譯為保證。

## <a name="what-regulations-and-standards-does-compliance-score-monitor"></a>合規性分數監控的規章和標準為何？

合規性分數可讓您根據 Microsoft 365 資料保護基準（包括常見的行業法規和標準的一組控制項），為您提供初始分數。 此基準主要是從 NIST CSF （國家標準和技術協會 Cybersecurity Framework）和 ISO （國際標準組織的標準化 FedRAMP）和 GDPR （歐盟的一般資料保護法規）和（一般資料保護法規）中的專案來繪製要素。

組織可以建立及新增與其組織更相關的自訂評估。 使用合規性分數的[預先設定的範本](compliance-score.md#templates)之一、使用您自己的控制項和動作自訂 Microsoft 範本，或建立您自己的範本。 閱讀有關如何[使用範本的](working-with-compliance-manager.md#templates)詳細資料。

瞭解[相容性分數如何計算您的分數](compliance-score-methodology.md)。

## <a name="what-is-the-difference-between-compliance-score-and-secure-score"></a>合規性分數與安全評分之間的差異為何？

合規性分數提供組織的資料保護和合規性狀況的廣泛觀點。 合規性分數也提供內建工作流程工具;它可讓組織將工作指派給使用者、追蹤控制項的實施和測試狀態，以及上傳證據及建立審核報告。

Microsoft Secure 得分是一種安全分析工具，可協助您瞭解安全性狀況。 [深入瞭解安全性分數及其運作方式](../security/mtp/microsoft-secure-score.md)。

## <a name="which-cloud-services-are-covered-by-compliance-score"></a>合規性分數涵蓋了哪些雲端服務？

合規性分數目前提供 Office 365 和 Intune 的評估。 未來的版本中預期已展開的覆蓋範圍，並將在「[合規性分數版本附注](compliance-score-release-notes.md)」中注明。

## <a name="can-i-use-compliance-score-for-non-microsoft-products"></a>我是否可以使用非 Microsoft 產品的相容性分數？

雖然合規性分數只會針對 Microsoft 雲端服務提供連續監控和建議的動作，但您可以在內部部署、協力廠商服務的合規性管理員中新增自訂評估。 如此一來，您可以使用 Microsoft 合規性分數做為 SaaS 合規性管理工具，協助您管理數位資產中的所有控制項。

您可以使用合規性分數的[預先設定的範本](compliance-score.md#templates)之一來建立特定標準的評估，或[建立您自己的範本](working-with-compliance-manager.md#create-a-template)。

## <a name="how-do-i-delete-a-template-or-assessment-i-no-longer-need"></a>如何刪除不再需要的範本或評估？

您無法刪除評估或範本，但可將其從您的視圖中隱藏。 查看[隱藏評估的指示](working-with-compliance-manager.md#hide-a-template-or-an-assessment)。

## <a name="what-test-procedures-does-microsoft-follow-for-controls"></a>Microsoft 針對控制項所遵循的測試程式為何？

Microsoft 參與每年的控制項審核。 您可以從可從[Microsoft 服務信任入口網站](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3)下載的審計員複查審計報告。

## <a name="why-are-some-controls-tested-annually-and-others-tested-every-three-years"></a>為何有些控制項每年都會經過測試，而其他每三年會進行測試？

FedRAMP 評估是案例原因的範例。 每年執行一次，並測試主要控制系列之間的控制項橫截面。 FedRAMP 將控制項分類為**核心**，當其非常重要，需要年度測試時。 指定為非核心的控制項每三年測試一次。 每年會測試橫跨所有主要控制系列的控制項子集。 如此一來，每年的審計都會查看整個董事會的案例，以確保解決方案的健全。 如需詳細資訊，請參閱[FedRAMP 年度評估流程](https://www.fedramp.gov/annual-assessment-guidance/)。
