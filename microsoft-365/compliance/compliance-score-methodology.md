---
title: Microsoft 規範分數（預覽）計算
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
ms.openlocfilehash: 69b631dc355ff497d0f6042e0cce6aff3d70e557
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024673"
---
# <a name="compliance-score-preview-calculation"></a>合規性分數（預覽）計算

> [!IMPORTANT]
> 您不應將「合規性分數」和「合規性管理員」中的建議視為合規性的保證。 您可以根據法規環境評估和驗證客戶控制措施的效能。 這些服務目前是在預覽中，並受限於[線上服務條款](https://go.microsoft.com/fwlink/?linkid=2108910)中的條款及條件。 另請參閱[Microsoft 365 授權指南以取得安全性和合規性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="how-compliance-score-works"></a>合規性分數的運作方式

合規性分數儀表板會顯示分數，以度量您在控制項中完成改進動作的進度。 每個動作對您的分數有不同的影響，取決於可能的風險。 您的分數可協助您決定關注的動作，以改善您的整體相容性狀況。

在*整個分數中*，會以通過/失敗的方式，將控制項顯示的符合性分數值整體套用到總分。 控制項已執行並通過後續的評估測試，否則不會。 

當控制項具有下列專案時，會將點加入至您的規範分數。

- **實施狀態**等於 [已**實現**] 或 [**替代] 實施**，以及
- 已**通過****測試結果**equals。

控制項總分是採取改進動作所取得的點數總和。 您的控制分數總和是評估分數。 **您的評估分數總和是您的整體合規性分數。**

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>以 Microsoft 365 資料保護基準為基礎的初始分數
  
合規性分數為您提供以 Microsoft 365 資料保護基準為基礎的初始分數。 此基準是一組控制項，包含資料保護和一般資料控管的重要規章和標準。 此基準主要是從 NIST CSF （國家標準和技術協會 Cybersecurity Framework）和 ISO （國際標準組織的標準化 FedRAMP）和 GDPR （歐盟的一般資料保護法規）和（一般資料保護法規）中的專案來繪製要素。

資料保護基準評估（預設為所有組織提供）是在您設定其他評估之前，用來計算您的初始分數。 在您第一次造訪時，合規性分數已經從您的 Microsoft 365 解決方案中收集信號。 您將會很快看到組織相對於重要資料保護標準與法規的執行方式，並查看建議採取的改進動作。

由於每個組織都有特定需求，因此符合您的需求取決於您設定及管理您自己的評估，以協助盡可能縮小及緩解風險。

## <a name="how-compliance-score-continuously-assesses-controls"></a>合規性分數不斷評估控制措施的方式

合規性分數會透過您的 Microsoft 365 環境自動掃描，並偵測您的系統設定，持續並自動更新您的技術控制狀態。 安全評分是執行監控的基礎引擎。

您的控制狀態會在您的合規性分數儀表板上每隔24小時更新。 當您遵循執行控制項的建議後，您將會在下一天看到控制項狀態已更新。

例如，如果您在 Azure AD 入口網站中開啟多重要素驗證（MFA），合規性分數會偵測設定，並反映在控制存取解決方案的詳細資料中。 相反地，如果您未開啟 MFA，請將合規性分數旗標視為建議採取的動作。

在公開預覽期間，連續的評估可供部分控制項使用，但並非全部。

#### <a name="learn-more"></a>深入了解
[閱讀安全分數及其運作方式](../security/mtp/microsoft-secure-score-new.md)。
  
## <a name="action-types-and-points"></a>動作類型和點

合規性分數追蹤兩種類型的動作：您管理的動作，以及 Microsoft 所管理的動作。 這兩種類型的動作都會在完成時算作整體分數的點數：

1. **您的分數**取決於您的組織所管理的控制項的合規性分數。
2. **Microsoft 受管理點**根據 Microsoft 以雲端服務提供者所管理的動作來貢獻您的合規性分數。

會根據動作為強制或選擇性，以及是否為預防性、偵探或糾正動作，指派分數值。

### <a name="mandatory-and-discretionary-actions"></a>強制和自由的動作

 - 不能故意或無意中略過強制執行的**動作**。 範例是設定密碼長度、複雜性和到期設定需求的集中式管理密碼原則。 使用者必須遵循這些需求，才能存取系統。
  
 - **自由動作**視使用者來瞭解原則，並採取相應的動作。 例如，如果原則要求使用者在其保留時鎖定其電腦，則其為自由的動作，因為它會因使用者而異。
  
### <a name="preventative-detective-and-corrective-actions"></a>預防性、偵探和修正動作
  
 - **預防動作**會解決特定風險。 例如，使用加密來保護靜止的資訊，是防範攻擊和違規行為的預防措施。 劃分職責是一項預防性動作，可管理利益衝突並防範欺詐行為。
  
 - **偵探動作**主動監視系統，以找出未規律的條件或行為，以找出風險或可能用來偵測入侵或違規的行為。 範例包括系統存取審核和特權管理動作。 法規遵從性審核是一種可用於尋找處理常式問題的偵探動作類型。
  
- **糾正動作**會嘗試將安全性事件的不利影響降至最低，採取糾正動作來降低立即效果，並盡可能將損毀。 隱私權事件回應是一種糾正動作，可在損毀後，將損毀和還原系統限制在運作狀態。
  
每個動作都根據其所代表的風險，以合規性分數指派值：

|**類型**|**指派分數**|
|:-----|:-----|
| 預防性強制 | 7 |
| 預防自由 | 9  |
| 偵探強制 | 3  |
| 偵探自由 | 1  |
| 必要修正 | 3  |
| 隨機糾正 | 1  |
  
![合規性分數控制點值](../media/compliance-score-controls-scoring.png "合規性分數控制點值")