---
title: Microsoft 合規性分數
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
description: Microsoft 合規性分數可協助組織簡化及自動化風險評估，並建議採取建議的動作以協助解決風險。
ms.openlocfilehash: 507ff021095dfc0b18cffb6db313009c22ad2693
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046271"
---
# <a name="microsoft-compliance-score-preview"></a>Microsoft 合規性分數（預覽）

[Microsoft 合規性分數](https://compliance.microsoft.com/compliancescore)可協助您簡化管理法規遵從性的方式，並透過方便使用的經驗降低法規遵從性風險。 [Microsoft 365 規範中心](microsoft-365-compliance-center.md)內的公開預覽適用的合規性分數。

**本文內容：** 請閱讀本文，以瞭解哪些相容性分數，以及如何為您的組織設定。

**深入瞭解更新：** 我們已于2020年4月發佈數個更新。 請造訪「[合規性分數版本](compliance-score-release-notes.md)資訊」，以查看「預覽」版本的合規性分數的新功能和已知問題。

## <a name="what-is-compliance-score"></a>合規性分數為何

Microsoft 合規性分數是 Microsoft 365 規範中心的預覽功能，可協助您瞭解組織的合規性狀況。 它會計算以風險為基礎的分數，用以衡量您在完成動作方面的進展，以協助降低資料保護和法規標準的風險。

您可以使用合規性分數做為工具，以追蹤所有風險評估。 它提供工作流程功能，協助您透過一般工具，有效地完成風險評估。

如果您目前使用[合規性管理員](compliance-manager-overview.md)，您會注意到「合規性分數」現在是獨立的功能，具有更簡單且便於使用的設計，可協助您更輕鬆地管理規範。 

主要合規性分數頁面是您的自訂儀表板。 它會顯示您目前的評分，協助您瞭解需要注意的事項，並指導您採取動作以提升您的分數。 您的合規性分數儀表板看起來像這樣：

![合規性分數-儀表板](../media/compliance-score-dashboard.png "合規性分數儀表板")

### <a name="simplified-compliance-management"></a>簡化的規範管理

合規性分數可提供下列功能，以簡化規範管理：

- **連續評估**：自動掃描您的 Microsoft 365 環境，以偵測和監視系統中資料保護控制項的效能
- **建議的動作**：提供建議，並逐步指導您如何執行控制以最大化排名
-  **內建的控制項對應**：透過提供內建的共同作業架構，協助您在不斷提高的規範環境中保持最新狀態

> [!IMPORTANT]
> 您不應將「合規性分數」和「合規性管理員」中的建議視為合規性的保證。 您可以根據法規環境評估和驗證客戶控制措施的效能。 這些服務目前是在預覽中，並受限於[線上服務條款](https://go.microsoft.com/fwlink/?linkid=2108910)中的條款及條件。 另請參閱[Microsoft 365 授權指南以取得安全性和合規性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="relationship-to-compliance-manager"></a>與合規性管理員的關係

請將合規性分數視為合規性管理員簡化版本。 雖然這兩者都存在於不同的整合式工具中，但遵從性分數可讓您更容易監視整體的相容性狀況，並採取步驟加以改善。

合規性分數與合規性管理員共用相同的後端，所以合規性管理員中您可能已具備的任何資料都會以相容性分數顯示。

在公開預覽期間，有些功能會維持在合規性管理員內，例如管理評估和建立範本。 建議您在合規性分數中開始所有符合性管理活動。 當您接觸合規性管理員所處理的功能時，系統會將您導向該工具。 基於此原因，本文中的一些檔會將您導向合規性管理員主題。

深入瞭解[合規性分數版本附注](compliance-score-release-notes.md)中的合規性分數和合規性管理員之間的關係。

## <a name="understanding-your-score"></a>瞭解您的分數

合規性分數為您提供以 Microsoft 365 資料保護基準為基礎的初始分數。 此基準是一組包含常見業界法規和標準的控制。 雖然這個分數是評估符合性狀況的好開端，但一旦您新增了與貴組織更為相關的評估，就會變得更強大。

例如，如果您的組織屬於金融服務行業，您可能會想要新增 FFIEC 評估。 如果您的組織屬於醫療保健行業，您可以新增 HIPAA/高科技評估。 瞭解如何[在合規性管理員中新增評估](working-with-compliance-manager.md#assessments)。

深入瞭解[如何計算和持續監控規範分數](compliance-score-methodology.md)。


## <a name="key-components-controls-assessments-templates-groups"></a>主要元件：控制項、評估、範本、群組

合規性分數使用多個元件，協助您管理相容性活動。 當您使用相容性分數指派、測試及監視合規性活動時，對重要元件有基本的瞭解是很有説明的：控制項、評估、範本和群組。

### <a name="controls"></a>控制項

控制項定義如何評估和管理系統設定、組織程式，以及負責滿足法規、標準或內部原則的特定需求的人員。

合規性分數追蹤兩種類型的控制項：

1. **Microsoft 受管理的控制項**： microsoft cloud services 的控制項，microsoft 負責執行這種服務
2. **客戶管理的控制項**：由您的組織管理的控制項，由您負責執行
 
### <a name="assessments"></a>評估

評估是一項範本評估，可對您的組織發起計分程式。 評估群組符合標準、法規或法律需求所需的動作。 例如，您可能會有一個評估，當您完成其中的所有動作時，您的 Office 365 設定會以 ISO 27001 的需求為依據。

合規性分數為您的組織提供以 Microsoft 365 資料保護基準為基礎的初始評估。 這種評估是降低資料保護和合規性風險的建議（[深入瞭解](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)）。

評估包含數個元件：

- **範圍內的服務**：適用于評估的特定 Microsoft 服務集合
- **Microsoft 管理控制項**： microsoft 所實施及測試的控制項
- **客戶管理的控制項**：您管理的控制項
- **評估分數**：完成該評估中的動作可取得的點數百分比

> [!NOTE]
> 合規性分數會顯示您的評估，以及它們如何影響您的整體分數。 不過，在公開預覽期間，系統會將您導向合規性管理員以管理評估。

[在合規性管理員中查看管理評估](working-with-compliance-manager.md#assessments)的詳細指示。

### <a name="templates"></a>範本

合規性分數可提供預先設定的範本進行評估。 您也可以新增您自己的控制項和動作，以自訂預先設定的範本。 例如，您可以為商務程式控制建立範本，或為區域資料保護或符合性標準（其中一個預先設定的範本尚未涵蓋）建立範本。 透過將您自己的範本引入合規性分數，您不僅可以追蹤 Microsoft 雲端評估，還可以追蹤組織範圍內任何其他風險評估。

符合性分數的預先設定範本如下：

1. [巴西一般資料保護法（LGPD）](https://go.microsoft.com/fwlink/?linkid=2115387)
2. [加州消費者隱私權法案（CCPA）](https://go.microsoft.com/fwlink/?linkid=2108871) （預覽）
3. [雲端安全性同盟（CSA） Cloud Controls 矩陣（CCM）3.0。1](https://go.microsoft.com/fwlink/?linkid=2109076)
4. [歐盟 GDPR](https://go.microsoft.com/fwlink/?linkid=2108870)
5. [聯邦金融機構檢查委員會（FFIEC）資訊安全性手冊](https://go.microsoft.com/fwlink/?linkid=2109077)
6. [FedRAMP 適中](https://go.microsoft.com/fwlink/?linkid=2108869)
7. [HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / 高[科技](https://go.microsoft.com/fwlink/?linkid=2109079)
8. [IRAP](https://go.microsoft.com/fwlink/?linkid=2113709) / [澳大利亞政府版 ISM](https://go.microsoft.com/fwlink/?linkid=2113024) （預覽）
9. [ISO 27001:2013](https://go.microsoft.com/fwlink/?linkid=2109073)
10. [ISO 27018:2014](https://go.microsoft.com/fwlink/?linkid=2109074)
11. [ISO 27701:2019](https://go.microsoft.com/fwlink/?linkid=2113025)
12. [Microsoft 365 資料保護基準](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)
13. [NIST 800-53 Rev 4](https://go.microsoft.com/fwlink/?linkid=2109075)
14. [NIST 800-171](https://go.microsoft.com/fwlink/?linkid=2108867)
15. [NIST Cybersecurity Framework （CSF）](https://go.microsoft.com/fwlink/?linkid=2108868)
16. [SOC 1](https://go.microsoft.com/fwlink/?linkid=2115184)
17. [SOC 2](https://go.microsoft.com/fwlink/?linkid=2115184)

針對在合規性管理員中所進行的範本，查看[建立範本的詳細指示](working-with-compliance-manager.md#templates)。

### <a name="groups"></a>群組

群組可讓您以合理的方式組織評估。 例如，您可以選擇依年、符合標準、服務、組織內的小組或其他方式來群組評估。

當同一個群組中的兩個不同評估共用客戶管理的動作時，在一個評估中對該動作執行詳細資料、測試及狀態所做的更新，會自動同步處理至群組中任何其他評估中的相同動作。 以這種方式同步處理動作會使指派的「改進」動作統一整個群組，並減少重複的工作。

瞭解如何[在合規性管理員中建立群組](working-with-compliance-manager.md#groups)。 一旦您建立群組，您就可以[篩選「合規性分數」儀表板](compliance-score-setup.md#filtering-your-dashboard-view)，以查看一或多個群組的分數。

## <a name="next-step-begin-setup"></a>後續步驟：開始安裝程式

瞭解如何登入、設定許可權，以及設定[相容性分數設定](compliance-score-setup.md)的更新及儀表板視圖。
