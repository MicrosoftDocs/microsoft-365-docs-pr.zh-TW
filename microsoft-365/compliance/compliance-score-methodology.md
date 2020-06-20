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
description: 瞭解 Microsoft 合規性分數如何根據採取的措施來計算個人化分數，並改善您的相容性狀況。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cf8a691b558614896cc17207e761035e1f360280
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818072"
---
# <a name="microsoft-compliance-score-preview-calculation"></a>Microsoft 規範分數（預覽）計算

> [!IMPORTANT]
> 您不應將「合規性分數」和「合規性管理員」中的建議視為合規性的保證。 您可以根據法規環境評估和驗證客戶控制措施的效能。 這些服務目前是在預覽中，並受限於[線上服務條款](https://go.microsoft.com/fwlink/?linkid=2108910)中的條款及條件。 另請參閱[Microsoft 365 授權指南以取得安全性和合規性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="how-compliance-score-works"></a>合規性分數的運作方式

合規性分數儀表板會顯示分數，以度量您在控制項中完成改進動作的進度。 當您完成動作時，您的點數便會累算。

您的分數是根據 Microsoft 管理的動作和客戶管理的動作的完成而計算。 每個動作對您的分數有不同的影響，取決於可能的風險。 您的分數可協助您決定關注的動作，以改善您的整體相容性狀況。

在*整個分數中*，會以通過/失敗的方式，將控制項顯示的符合性分數值整體套用到總分。 控制項已執行並通過後續的評估測試，否則不會執行。 當控制項具有下列專案時，已指派的點會新增至符合性分數：

- **實施狀態**等於 [已**實現**] 或 [**替代] 實施**，以及
- 已**通過****測試結果**equals。

採取改進動作所取得的點數總和是控制分數。 您的控制分數總和是評估分數。 您的評估分數總和是您的整體合規性分數。

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>以 Microsoft 365 資料保護基準為基礎的初始分數
  
合規性分數可讓您根據 Microsoft 365 資料保護基準（一組包含重要的資料保護和一般資料控管的主要法規和標準），為您提供初始分數。 此基準主要是從 NIST CSF （國家標準和技術協會 Cybersecurity Framework）和 ISO （國際標準組織的標準化 FedRAMP）和 GDPR （歐盟的一般資料保護法規）和（一般資料保護法規）中的專案來繪製要素。

## <a name="how-compliance-score-continuously-assesses-controls"></a>合規性分數不斷評估控制措施的方式

合規性分數會透過您的 Microsoft 365 環境自動掃描，並偵測您的系統設定，持續並自動更新您的技術控制狀態。 安全評分是執行監控的基礎引擎。 [深入瞭解安全性分數及其運作方式](../security/mtp/microsoft-secure-score.md)。

您的控制狀態會在您的合規性分數儀表板上每隔24小時更新。 當您遵循執行控制項的建議後，您將會在下一天看到控制項狀態已更新。

例如，如果您在 Azure AD 入口網站中開啟多重要素驗證（MFA），合規性分數會偵測設定，並反映在控制存取解決方案的詳細資料中。 相反地，如果您未開啟 MFA，請將合規性分數旗標視為建議採取的動作。

在公開預覽期間，連續的評估可供部分控制項使用，但並非全部。
  
## <a name="control-types-and-points"></a>控制項類型和點

合規性分數追蹤兩種類型的控制項：「Microsoft 管理」和「客戶管理」，每個控制項都有分數可貢獻您的整體分數：

1. **客戶管理的點**會根據您的組織所管理的控制項，來貢獻您的合規性分數。
2. 根據 Microsoft 以雲端服務提供者所管理的控制項， **microsoft 受管理的點**會為您的合規性分數貢獻。

控制項會根據其是否為強制性或自由的，以及是否為預防性、偵探或糾正，指派分數值。

### <a name="mandatory-and-discretionary-controls"></a>強制和自由控制

 - **強制控制項**是指無法略過的動作，不論是有意或無意。 範例是設定密碼長度、複雜性和到期設定需求的集中式管理密碼原則。 使用者必須遵循這些需求，才能存取系統。
  
 - **自由的控制項**會依據使用者來瞭解原則，並採取相應的動作。 例如，如果原則要求使用者在其離開時鎖定其電腦，則其為自由控制項，因為它會因使用者而異。
  
### <a name="preventative-detective-and-corrective-controls"></a>預防性、偵探和修正控制措施
  
 - **預防控制措施**解決特定風險。 例如，使用加密來保護靜態資訊，是防範攻擊和違規行為的預防控制措施。 劃分職責是一種預防控制，可管理利益衝突，並防止欺詐。
  
 - **偵探控制**主動監視系統，以找出未規律的條件或行為，以找出風險或可能用來偵測入侵或違規的行為。 「系統存取審核」和「特權管理動作」審核是「偵探監控」控制項的類型。 法規遵從性審核是一種可用於尋找處理問題的偵探控制項類型。
  
- **修正控制**會嘗試將安全性事件的不利影響降至最低，採取糾正動作以減少立即影響，並在可能的情況下反轉損毀。 隱私權事件回應是一種修正控制，可在損毀後，將損毀和還原系統限制在運作狀態。
  
根據所代表的風險，每個控制項都有指派的合規性分數中的值：

|**類型**|**指派分數**|
|:-----|:-----|
| 預防性強制 | 7 |
| 預防自由 | 9  |
| 偵探強制 | 個 |
| 偵探自由 | 1  |
| 必要修正 | 個 |
| 隨機糾正 | 1  |
  
![合規性分數控制點值](../media/compliance-score-controls-scoring.png "合規性分數控制點值")