---
title: 通訊合規性計畫
description: 深入瞭解在組織中使用通訊規範的規劃。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 4c44610f4d74fe9ebf3c8e549692d9cc7cc6cb34
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597420"
---
# <a name="plan-for-communication-compliance"></a>通訊合規性計畫

您的組織中的[通訊合規性](communication-compliance.md)開始之前，必須先閱讀您的資訊技術和合規性管理小組所需的重要規劃活動和考慮。 在下列各項中徹底瞭解及規劃部署，可協助確保您的實施和使用通訊合規性功能，並與解決方案的最佳作法保持一致。

## <a name="work-with-stakeholders-in-your-organization"></a>與組織中的專案關係人合作

在您的組織中識別適當的利益關係人，以共同作業，以在通訊相容性警示上採取行動。 有些建議的專案關係人會考慮納入初始規劃，以及端對端[通訊規範工作流程](communication-compliance.md#workflow)的人員來自組織的下列領域：

- 資訊技術
- 合規性
- 隱私權
- 安全性
- 人力資源
- 法務

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>規劃調查和修正工作流程

選取 [專屬的利益關係人]，以在[Microsoft 365 規範中心](https://compliance.microsoft.com/)內的定期節奏上監視和審閱警示和案例。 請確定您將如何將不同的通訊合規性角色指派給組織中的專案關係人。

視您想要管理通訊原則及警示的方式而定，您將需要為系統管理員、檢閱者和調查人員建立一個或多個新的角色群組。 您可以選擇將使用者指派給特定角色群組，以管理不同的通訊相容性功能組。 或者，您也可以決定建立一個角色群組，並將所有通訊規範角色指派給群組。 建立單一角色群組或多個群組，以最大程度符合您的規範管理需求。

當您設定通訊合規性角色群組時，規劃從這些角色選項中選擇：

|**角色**|**角色權限**|
|:-----|:-----|
| **通訊合規性管理** | 指派此角色的使用者可以建立、讀取、更新和刪除通訊符合性原則、全域設定和角色群組指派。 指派此角色的使用者無法查看郵件警示。 |
| **通訊相容性分析** | 指派此角色的使用者可以查看指派為檢閱者的原則、查看郵件中繼資料 (非郵件內容) 、升級至其他檢閱者，或傳送通知給使用者。 分析員無法解析待處理的警示。 |
| **通訊相容性調查** | 指派此角色的使用者可以查看郵件中繼資料和內容、升級至其他檢閱者、升級至高級 eDiscovery 案例、將通知傳送給使用者，以及解決警示。 |
| **通訊規範檢視器** | 指派此角色的使用者可以存取通訊合規性首頁上的所有報告元件，並可以查看所有的通訊符合性報告。 |
| **通訊規範案例管理** | 指派此角色的使用者可以管理案例並對提醒採取行動。 為管理員、分析員和調查人員建立自訂角色群組時，需要此角色。 自訂群組的檢視器不需要指派此角色。 |

## <a name="plan-for-policies"></a>規劃原則

使用冒犯性語言、機密資訊和法規遵從性的[預先定義範本](communication-compliance-feature-reference.md#policy-templates)，快速且輕鬆建立通訊相容性原則。 自訂通訊合規性原則可讓您彈性地偵測和調查組織和需求的相關問題。

規劃通訊相容性原則時，請考慮下列各項：

- 請考慮將組織中的所有使用者新增為您的通訊相容性原則的範圍。 在某些情況下，將特定使用者識別成範圍內的個別原則是很有用的，不過大多陣列織都應該將所有使用者都包含在已針對騷擾或歧視偵測優化的通訊合規性原則中。
- 若要簡化您的設定，請考慮為需要查看其通訊的使用者建立群組。 如果您使用的是群組，則為您可能需要數個。 例如，如果您想要掃描兩個不同的使用者群組之間的通訊，或是想要指定未監督的群組。
- 設定要在100% 檢查的通訊百分比，以確保原則能夠捕捉組織中的所有相關問題。
- 您可以從[協力廠商來源](communication-compliance-feature-reference.md#supported-communication-types)掃描通訊，以用於將資料匯入至 Microsoft 365 組織中的信箱。 若要在這些平臺中包含通訊的複查，您必須先設定這些服務的連接器，然後通訊原則才能監視郵件會議原則條件。
- 在自訂通訊合規性原則中，原則可以支援非英文的監控語言。 使用您選擇的語言建立冒犯性文字的[自訂關鍵字字典](communication-compliance-feature-reference.md#custom-keyword-dictionaries)，或使用 Microsoft 365 中的[trainable 分類](classifier-getting-started-with.md)程式建立您自己的機器學習模型。
- 所有組織都有不同的通訊標準和原則需求。 使用通訊相容性[原則條件](communication-compliance-feature-reference.md#conditional-settings)，或利用[自訂敏感資訊類型](create-a-custom-sensitive-information-type.md)監控特定類型的資訊，監視特定關鍵字。

## <a name="ready-to-get-started"></a>準備好開始使用了嗎？

若要設定 Microsoft 365 組織的通訊相容性，請參閱[設定 microsoft 365 的通訊相容](communication-compliance-configure.md)性，[以及如何](communication-compliance-case-study.md)快速設定通訊相容性原則，以監視 Microsoft 小組、Exchange Online 和 Yammer 通訊中的冒犯性語言。
