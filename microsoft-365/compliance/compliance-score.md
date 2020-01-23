---
title: Microsoft 合規性分數
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
description: Microsoft 合規性分數可幫助組織簡化和自動化的風險評估，並建議建議的動作，以協助地址的風險。
ms.openlocfilehash: 27720412ee8d2b03869b96a1ff9fce68b2fe6eb4
ms.sourcegitcommit: 5fc0f2cd1f2596fd10299333c826c501936dcd98
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2020
ms.locfileid: "41261857"
---
# <a name="microsoft-compliance-score-preview"></a>Microsoft 合規性分數 （預覽）

Microsoft 合規性分數可協助簡化管理合規性，並減少透過方便使用經驗的合規性風險的方式。 合規性分數是現在適用於[Microsoft 365 合規性中心](microsoft-365-compliance-center.md)中公開預覽。

**本文中：** 閱讀本篇文章以了解合規性分數是什麼以及如何設定以為組織。

**了解如何更新：** 移至[合規性分數版本資訊](compliance-score-release-notes.md)請參閱什麼是新的和已知問題與合規性分數的預覽版本。

## <a name="what-is-compliance-score"></a>合規性分數是什麼

Microsoft 合規性分數是在 Microsoft 365 合規性中心，以協助您了解貴組織的合規性狀態的預覽功能。 它會計算測量中完成協助減少資料保護和法規的標準周圍的風險的動作您進行風險分數。

您可以使用合規性分數做為工具，以追蹤所有風險評定。 它提供可協助您有效率地完成您透過一般工具的風險評估工作流程功能。

如果您目前使用[合規性管理員中](compliance-manager-overview.md)，您會注意到合規性分數現在是獨立功能與更簡單，更方便使用的設計，可協助您更輕鬆地管理合規性。 

主要的合規性分數頁面是自訂儀表板。 它會顯示您目前的分數、 可協助您查看哪些需要注意，及引導您以動作，以改善您的分數。 合規性分數儀表板看起來像這樣：

![合規性分數-儀表板](media/compliance-score-dashboard.png "合規性分數儀表板")

### <a name="simplified-compliance-management"></a>簡化的合規性管理

合規性分數可協助簡化相符性管理提供：

- **連續評估**： 自動透過您的 Microsoft 365 環境，以偵測並監視您的系統中的資料保護控制項的效率掃描
- **建議的動作**： 提供建議和如何實作控制項的逐步指引，以最大化您的分數
-  **內建控制項的對應**： 協助您保持最新的不斷變化的合規性橫向藉由提供內建的通用控制項架構

> [!IMPORTANT] 
> 合規性分數不 express 與任何特定的標準或法規的組織符合性絕對量值。 它來表示您要採用的個人資料和個人隱私權降低風險的控制項的程度。 合規性分數和合規性管理員中的建議事項不應該解譯成保證郵件可以合規性。 這項服務目前處於預覽狀態，並受限於條款和條件[線上服務條款](https://go.microsoft.com/fwlink/?linkid=2108910)中。

## <a name="relationship-to-compliance-manager"></a>關聯到合規性管理員

將視為的簡化版合規性管理員的合規性分數。 雖然這兩個存在於不同尚未整合式工具，合規性分數容易監視您的整體合規性狀態，並採取步驟來改善它。

合規性分數共用相同的後端與合規性管理員中，因此您可能已經有合規性管理員中的任何資料將會顯示在 [合規性分數。

期間公開預覽版，某些功能會維持察覺合規性管理員中，例如管理的評估和建立範本。 建議開始所有您合規性管理中的活動合規性分數。 當您回到函式處理由合規性管理員中時，您將會引導該工具。 基於這個理由，部分這份文件會引導您合規性管理員中的主題。

深入了解合規性分數與[合規性分數版本資訊](compliance-score-release-notes.md)中的合規性管理員之間的關係。

## <a name="understanding-your-score"></a>了解您的分數

合規性分數可讓您根據 Microsoft 365 的資料保護基準初始分數。 此基準線是一組控制項包含一般產業法規及標準。 雖然此分數是不錯的起點的評估您的合規性狀態，但合規性分數會變成功能更強大，一旦您新增至您的組織更相關的評估。

例如，如果您的組織屬於金融服務產業，可能會想要新增 FFIEC 評估。 如果您的組織屬於醫療保健產業，您可以新增 HIPAA/HITECH 評估。 了解如何[新增評估合規性管理員中](working-with-compliance-manager.md#assessments)。

深入了[解您的合規性分數是計算](compliance-score-methodology.md)和持續受到監視。


## <a name="key-components-controls-assessments-templates-groups"></a>主要元件： 控制項、 評估、 範本、 群組

合規性分數會使用數個元件，可協助您管理您的合規性活動。 當您可以使用合規性分數指派、 測試和監視合規性活動，很有幫助有基本了解這些重要元件。 此圖顯示它們之間的關係：

![合規性管理員第 3 版中的關聯性](media/compliance-manager-relationships.png "合規性分數元件")

### <a name="controls"></a>控制項

控制項定義如何評估及管理系統組態，組織的程序，以符合規定，標準，或內部原則的特定需求的人員責任。

合規性分數追蹤兩種類型的控制項：

1. **Microsoft 管理控制措施**： 控制項的 Microsoft 雲端服務，Microsoft 是負責實作
2. **客戶管理控制措施**： 由您的組織，您必須負責實作受管理的控制項
 
### <a name="assessments"></a>「 評估 」

評估是範本的用來評估的起始貴組織的計分程序。 評估群組以符合需求的標準、 規定或法律規定所需的動作。 例如，您可能需要評估，當您完成所有動作內，將帶您的 Office 365 設定內嵌 ISO 27001 需求。

根據預設，合規性分數會提供根據 Microsoft 365 資料保護比較基準，建議減少 （[了解更多](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)） 您的資料保護和合規性風險評估您的組織。

評估包含數個元件：

- **範圍內的服務**： 一組特定的 Microsoft 服務適用於評估
- **Microsoft 管理控制措施**： Microsoft 實作和測試控制項
- **客戶管理控制措施**： 您管理的控制項
- **評估分數**： 達到完成動作內該評定的點的百分比

> [!NOTE]
> 合規性分數會顯示您評估和他們因素入您的整體分數的方式。 不過，在公開預覽期間會將您導向到合規性管理員來管理您評估。

檢視[使用評估合規性管理員中](working-with-compliance-manager.md#assessments)的詳細的指示。

### <a name="templates"></a>範本

合規性分數提供評估預先設定的範本。 合規性分數也可讓您建立您自己的評估，以符合您需求的範本。 例如，您可以建立商務程序控制項、 範本或範本區域資料保護或合規性標準，未涵蓋的其中一個預先設定的範本。  藉由建立您自己的範本，您可以建立自訂的評估，以確保合規性分數追蹤 Microsoft 雲端評估，不僅也任何其他的風險評估在貴組織的範圍內。

藉由複製現有的範本，或由 Excel 檔案匯入控制項的資訊，您可以建立新的範本。 檢視[建立範本合規性管理員中](working-with-compliance-manager.md#templates)的詳細的指示。

預先設定的範本的合規性分數是：

1. [巴西一般資料保護 Law (LGPD)](https://go.microsoft.com/fwlink/?linkid=2115387)
2. [加州消費者隱私權法案 (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) （預覽）
3. [雲端安全聯盟 (CSA) 雲端控制項矩陣 (CCM) 3.0.1](https://go.microsoft.com/fwlink/?linkid=2109076)
4. [歐盟 GDPR](https://go.microsoft.com/fwlink/?linkid=2108870)
5. [聯邦金融機構檢查委員會 (FFIEC) 的資訊安全性手冊](https://go.microsoft.com/fwlink/?linkid=2109077)
6. [FedRAMP 中度](https://go.microsoft.com/fwlink/?linkid=2108869)
7. [HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / [HITECH](https://go.microsoft.com/fwlink/?linkid=2109079)
8. [次](https://go.microsoft.com/fwlink/?linkid=2113709) / [澳洲政府 ISM](https://go.microsoft.com/fwlink/?linkid=2113024) （預覽）
9. [ISO 27001: 2013](https://go.microsoft.com/fwlink/?linkid=2109073)
10. [ISO 27018:2014](https://go.microsoft.com/fwlink/?linkid=2109074)
11. [ISO 27701:2019](https://go.microsoft.com/fwlink/?linkid=2113025)
12. [Microsoft 365 的資料保護基準](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)
13. [NIST 800-53 修訂 4](https://go.microsoft.com/fwlink/?linkid=2109075)
14. [NIST 800-171](https://go.microsoft.com/fwlink/?linkid=2108867)
15. [NIST Cybersecurity Framework (CSF)](https://go.microsoft.com/fwlink/?linkid=2108868)
16. [SOC 1](https://go.microsoft.com/fwlink/?linkid=2115184)
17. [SOC 2](https://go.microsoft.com/fwlink/?linkid=2115184)

> [!NOTE]
> 期間公開預覽，請移至合規性管理員中建立及管理自己的範本。

### <a name="groups"></a>群組

群組可讓您組織的方式，是邏輯給您的評估。 例如，您可以依年份，合規性標準，選擇群組評估服務，您的組織或其他方法中的 teams。

當兩個不同的 「 評估 」 在相同的群組共用客戶管理動作時，完成的實作詳細資料、 測試和一個評估巨集指令的狀態會自動同步處理至群組中的任何其他評估中的相同動作。 此統整指派的改進動作跨群組，並減少複製的工作。

了解如何[建立群組合規性管理員中](working-with-compliance-manager.md#groups)。 一旦您建立的群組，您可以[篩選您合規性分數儀表板](compliance-score-setup.md#filtering-your-dashboard-view)來檢視您的分數，由一或多個群組。

## <a name="next-step-begin-setup"></a>下一步： 開始安裝

登入、 設定權限，並了解在[合規性分數安裝](compliance-score-setup.md)您合規性分數儀表板。
