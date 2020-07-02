---
title: Microsoft 合規性分數（預覽）
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
description: Microsoft 合規性分數（預覽）可協助組織簡化及自動化風險評估，並建議採取的措施以協助解決風險。
ms.openlocfilehash: 0cb8bd0b5aa39be2a9a6e706afa21bb7dc53eadb
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016136"
---
# <a name="microsoft-compliance-score-preview"></a>Microsoft 合規性分數（預覽）

**本文內容：** 瞭解遵循的合規性分數、它如何協助簡化管理規範的方式，以及如何為您的組織加以設定。

**新功能：** 2020年6月的版本包含建立及管理評估的新功能，以及在合規性分數中查看控制項的功能。 請造訪「[合規性分數版本](compliance-score-release-notes.md)資訊」，以查看相容性分數公開預覽中的新功能。

## <a name="what-is-compliance-score"></a>合規性分數為何

[Microsoft 合規性分數](https://compliance.microsoft.com/compliancescore)是[microsoft 365 規範中心](microsoft-365-compliance-center.md)的預覽功能，可協助您瞭解組織的合規性狀況。 它會計算以風險為基礎的分數，用以衡量您在完成動作方面的進展，以協助降低資料保護和法規標準的風險。

您可以使用合規性分數做為工具，以追蹤所有風險評估。 它提供工作流程功能，協助您透過一般工具，有效地完成風險評估。

[合規性管理員](compliance-manager-overview.md)使用者會注意到「合規性分數」現在是獨立的功能，具有更簡單、更便於使用的設計，可協助組織更輕鬆地管理規範。

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

請將合規性分數視為合規性管理員簡化的體驗。 雖然這兩者都存在於不同的整合式工具中，但遵從性分數可讓您更容易監視整體的相容性狀況，並採取步驟加以改善。

合規性分數與合規性管理員分享相同的後端。 您在某項工具中執行的任何動作都會以其他工具呈現。

在公開預覽期間，評估與範本管理的某些功能仍會保留在合規性管理員中。 建議您在合規性分數中開始所有符合性管理活動。 當您接觸合規性管理員所處理的功能時，我們會在這裡為您提供指導。

#### <a name="learn-more"></a>深入了解

[瞭解合規性分數和合規性管理員之間的關係](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager)。

## <a name="understanding-your-score"></a>瞭解您的分數

合規性分數獎項您可以針對遵守法規、標準或原則所採取的措施進行積分。 每個動作對您的分數有不同的影響，取決於可能的風險。 您的分數可協助您決定關注的動作，以改善您的整體相容性狀況。

合規性分數為您提供以 Microsoft 365 資料保護基準為基礎的初始分數。  此基準是一組控制項，包含資料保護和一般資料控管的重要規章和標準。 此基準主要是從 NIST CSF （國家標準和技術協會 Cybersecurity Framework）和 ISO （國際標準組織的標準化 FedRAMP）和 GDPR （歐盟的一般資料保護法規）和（一般資料保護法規）中的專案來繪製要素。

資料保護基準評估是用來計算您的初始分數，然後再設定其他評估。 在您第一次造訪時，合規性分數已經從您的 Microsoft 365 解決方案中收集信號。 您將會很快看到組織相對於重要資料保護標準與法規的執行方式，並查看建議採取的改進動作。

由於每個組織都有特定需求，因此符合您的需求取決於您設定和管理您自己的評估，以更好地緩解風險。 例如，如果您的組織屬於金融服務行業，您可能會想要新增 FFIEC 評估。 如果您的組織屬於醫療保健行業，您可以新增 HIPAA/高科技評估。

#### <a name="learn-more"></a>深入了解

[瞭解如何計算和持續監控規範分數](compliance-score-methodology.md)。

[在合規性分數中建立及管理評估](compliance-score-assessments.md)。

## <a name="key-components-controls-assessments-templates-improvement-actions"></a>主要元件：控制項、評估、範本、改進動作

合規性分數使用多個元件，協助您管理相容性活動。 當您使用相容性分數指派、測試及監視合規性活動時，對重要元件具有基本的瞭解會很有説明：控制項、評估、範本及改進動作。

### <a name="controls"></a>控制項

控制項是法規、標準或原則的必要條件。 它會定義如何評估和管理系統設定、組織處理常式，以及負責滿足法規、標準或原則的特定需求的人員。

合規性分數追蹤兩種類型的控制項：

1. **Microsoft managed controls**： microsoft 雲端服務的控制項，microsoft 負責執行這種服務
2. **您的控制項**：有時候稱為客戶控制項，這些是由您的組織所實施及管理的控制項。

#### <a name="learn-more"></a>深入了解

[監視控制項的進度](compliance-score-assessments.md#monitor-assessment-progress-and-controls)。

### <a name="assessments"></a>評估

評估是指來自特定法規、標準或原則的控制項群組。 完成評估內的動作可協助您符合標準、法規或法律的需求。 例如，您可能會有一個評估，當您完成其中的所有動作時，會以 ISO 27001 需求為依據，使您的 Microsoft 365 設定成為線上。

評估包含數個元件：

- **範圍內的服務**：適用于評估的特定 Microsoft 服務集合
- **Microsoft managed controls**： microsoft 實施及測試的控制項
- **您的控制項**：您管理的控制項
- **評估分數**：完成該評估中的改進動作所能達到的點數百分比

在建立評估時，您會將其指派給**群組**。 您可以以組織最具邏輯的任何方式來設定群組。 例如，您可以依年、組織內的符合性標準、服務、小組或其他方式來群組評估。 一旦您建立群組，您就可以[篩選「合規性分數」儀表板](compliance-score-setup.md#filtering-your-dashboard-view)，以查看一或多個群組的分數。

#### <a name="learn-more"></a>深入了解

[在合規性分數中建立及管理評估](compliance-score-assessments.md)。

### <a name="templates"></a>範本

合規性分數提供可讓您快速建立評估的範本。 您可以修改這些範本，以依據您的需求建立評估優化。 您也可以使用自己的控制項和動作來開發您自己的範本，以建立自訂評估。 例如，您可能想要範本涵蓋內部的商務程式控制，或一個我們的範本未涵蓋的地區性資料保護標準。

建立您自己的範本，讓您不僅可以追蹤 Microsoft 雲端評估，還可以追蹤組織範圍內的任何其他風險評估。

#### <a name="learn-more"></a>深入了解

[在建立評估時，查看合規性分數中可用的範本](compliance-score-templates.md)。

[取得建立及修改範本合規性管理員的詳細指示](working-with-compliance-manager.md#templates)。

### <a name="improvement-actions"></a>改進動作

改進相容性活動的改進動作。 每個改進動作都提供詳細的執行指導，以協助您與資料保護法規和標準相符。 動作可指派給組織中的使用者，以執行實施和測試工作。 您也可以在改進動作中儲存檔、記事及記錄狀態更新。

#### <a name="learn-more"></a>深入了解

[使用提高的動作來管理您的合規性工作流程](compliance-score-improvement-actions.md)。

## <a name="next-steps-set-up-and-customize"></a>後續步驟：設定和自訂

瞭解如何登入、設定許可權和角色、設定安全分數更新，以及在[相容性分數設定](compliance-score-setup.md)時個人化儀表板視圖。

然後，[設定評估](compliance-score-assessments.md)以開始自訂群組織的合規性分數。