---
title: 合規性分數計算
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
description: 了解 Microsoft 合規性分數會根據 [地址風險採取的動作的個人化的分數的計算，並改善您的合規性狀態。
ms.openlocfilehash: ca8615f8c15264104faa71d155d2656cd788bd53
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078630"
---
# <a name="microsoft-compliance-score-preview-calculation"></a>Microsoft 合規性分數 （預覽） 計算

> [!IMPORTANT]
> 合規性分數不 express 與任何特定的標準或法規的組織符合性絕對量值。 它來表示您要採用的個人資料和個人隱私權降低風險的控制項的程度。 合規性分數和合規性管理員中的建議事項不應該解譯成保證郵件可以合規性。 這項服務目前處於預覽狀態，並受限於條款和條件[線上服務條款](https://go.microsoft.com/fwlink/?linkid=2108910)中。

## <a name="overview"></a>概觀

合規性分數儀表板會顯示措施的完成控制項內的改進動作進度的分數。 您點累當您完成動作。

您的分數是根據 Microsoft 受管理的動作和客戶管理動作完成計算。 每個巨集指令具有不同的影響您分數，根據所涉及的潛在風險，因此分數有助於排列優先順序的巨集指令，將焦點放入改善您的整體合規性狀態。

控制項的顯示合規性分數的值會套用]*其完整*您通過/失敗為基礎的總分數。 控制項實作並傳遞後續評估測試或沒有。 當控制項有指派的點新增到合規性分數：

- **實作狀態**等於**Implemented**或**替代實作**，
- **測試結果**等於**Passed**。

總和所採取的動作改進盈餘分析的資料點是控制項分數。 您控制分數的總和會評估分數。 評估分數的總和，是整體合規性分數

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>根據 Microsoft 365 的資料保護基準的初始分數
  
合規性分數可讓您根據 Microsoft 365 的資料保護基準，這是一組控制項包含重要的法規及標準的資料保護和一般資料控管的方塊出分數。 此基準線繪製元素，主要是從 NIST CSF （National Institute of Standards 和技術 Cybersecurity Framework） 和 ISO （國際標準組織），以及從 FedRAMP （聯邦風險與授權管理程式） 和 GDPR （歐盟地區的一般資料保護規定）。

## <a name="how-compliance-score-continuously-assesses-controls"></a>如何合規性分數持續評估控制項

合規性分數自動透過 Microsoft 365 環境掃描，並會偵測到您系統的設定，連續且自動更新您的技術控制項狀態。 合規性分數作為基礎引擎執行監控使用安全分數。 [解更多關於安全分數，以及如何運作](../security/mtp/microsoft-secure-score.md)。

控制項狀態會更新您的合規性分數儀表板上每隔 24 小時。 一旦您遵循建議實作控制項，您會看到控制項狀態更新的下一步] 一天。

例如，如果您啟用 Azure AD 入口網站中的多重要素驗證 (MFA)，合規性分數偵測設定，並會反映在控制存取的解決方案詳細資料。 相反地，如果您未啟用 MFA，合規性分數的旗標，為您要採取的建議動作。

公開預覽期間連續評估是控制項，其中的部分可用但非全部。
  
## <a name="control-types-and-points"></a>控制項類型和點

合規性分數追蹤兩種類型的控制項 — Microsoft 管理與客戶管理-每一種有參與您的整體分數的點：

1. **客戶管理點**參與合規性分數根據貴組織所受管理的控制項。
2. **Microsoft 受管理的點**參與您根據受管理的 microsoft 雲端服務提供者為控制項的合規性分數。

控制項會根據是否為強制或選擇性，以及他們是否已完成預防性、 偵查，或更正分數值指派給 — 如下所示。

### <a name="mandatory-and-discretionary-controls"></a>必要和選擇性控制項

 - **必要的控制項**都是刻意或意外無法略過的動作。 例如，設定的密碼長度、 複雜性和到期需求集中管理密碼原則。 使用者必須符合這些需求，才能存取系統。
  
 - **選擇性控制**依賴使用者了解原則，並採取適當動作。 例如，要求他們離開時鎖定其電腦的使用者原則是選擇性的控制項，因為它必須依賴使用者。
  
### <a name="preventative-detective-and-corrective-controls"></a>預防性、 偵測和修正的控制項
  
 - **完成預防性控制項**位址特定風險。 例如，保護使用加密的靜態的資訊是針對攻擊和外洩的預防性控制項。 責任的區隔是管理衝突的利益與防範詐騙的預防性控制項。
  
 - **偵測控制項**主動監控系統以識別不規則條件或代表風險或，可用來偵測侵入或決定若發生外洩的行為。 系統存取稽核和特殊權限的系統管理動作稽核是偵測監視控制項的類型。 法規遵循稽核是一種用來尋找程序問題的偵查控制項。
  
- **更正控制項**嘗試保留不良影響的安全性事件最小值、 採取更正動作來降低立即生效，並盡可能反向所造成的損害。 隱私權事件回應是更正控制項限制損害，並在外洩之後，還原至正常運作狀態的系統。
  
每個控制項具有指派的值，根據其所代表之風險的合規性分數：

|**類型**|**指派的分數**|
|:-----|:-----|
| 必要的預防性 | 27 |
| 選擇性的預防性 | 9  |
| 偵測必要 | 3  |
| 偵測選擇性 | 1  |
| 必要的矯正措施 | 3  |
| 修正了選擇性 | 1  |
  
