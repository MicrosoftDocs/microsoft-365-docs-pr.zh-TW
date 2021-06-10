---
title: 規劃試驗 Microsoft 365 Defender 專案
description: 規劃您的試驗 Microsoft 365 與專案關係人的 Defender 專案，以管理期望並確保成功的結果。
keywords: Microsoft 365defender 試驗，規劃試驗 Microsoft 365 defender 專案，評估 Microsoft 365 的 defender 生產中，Microsoft 365 defender 試驗專案，網路安全性，高級持續性威脅，企業安全性，裝置，裝置，身分識別，使用者，資料，應用程式，事件，自動化調查和修正，高級搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 98f0c91a51cc2b73cc26e6fb53143a417a7a147e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932544"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>規劃試驗 Microsoft 365 Defender 專案 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

|![規劃](../../media/phase-diagrams/1-planning.png)<br/>規劃|[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[製備](prepare-m365d-eval.md) | [![類比攻擊](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)<br/>[類比攻擊](m365d-pilot-simulate.md) | [![結束和摘要](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)<br/>[結束和摘要](m365d-pilot-close.md)|
|--|--|--|--|
|*您在這裡！*| | | |

您目前正在規劃階段。

為了確保您的試驗專案順利完成，您必須在開始時充分規劃並取得您的利益關係人的核准。 規劃的元素包括識別範圍、使用案例、需求及成功準則。

本指南會引導您瞭解如何規劃試驗專案。 

>[!IMPORTANT]
>為了獲得最佳結果，請盡可能請盡可能遵循試驗指示。


## <a name="scope"></a>範圍

試驗的範圍會根據您的環境及可接受的測試方法，決定測試的範圍。 以下是一些需要考慮的範例範圍：
- 開發或測試環境，其中包含端點、伺服器、網域控制站。
- 使用 Microsoft 365、Azure、Active Directory 服務、端點和伺服器的實際執行環境

>[!NOTE]
>如果您還沒有完整的授權，您可以取得試用授權，[評估 Microsoft 365 Defender](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) –計畫、準備、安裝、設定及執行您的試驗專案。 您的利益關係人會在協助協助程式從開始到完成的過程中扮演重要角色。

若要評估的作業系統類型，也應根據組織組成的定義。 這可能包括下列各項： [Mac 端點](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements)、 [Linux 伺服器](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements)、 [Windows 10 端點](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions) [Windows Server 2016](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)。

## <a name="use-cases"></a>使用案例

使用案例代表所測試的工具應由其預定使用者使用的語句。 您可以從特定角色的觀點來表述使用者故事，例如 SOC 分析員。 例如：
- 在 SOC 分析員中，我需要在網路中的裝置、使用者和信箱之間，查看、關聯、評估和管理警示和事件。 [事件管理]
- 若為 SOC 分析員，我必須使用工具和程式來自動調查和回應我的網路中的惡意事件。 [自動 IR]
- 若為 SOC 分析員，我必須從環境搜尋資料，以找出已知和潛在威脅，以及可疑活動。 [高級搜尋]

請記住，這些使用案例應該在定義之範圍的參數中建立。 例如，如果測試的範圍不包括 Microsoft Cloud App Security 的工具評估，則不應建立以這做為資料來源的使用案例。

## <a name="requirements"></a>需求

您可以從使用案例清單中開始建立需求。 需求包含的功能必須具備工具才能滿足使用案例。 這些需求可以分解成諸如設定與維護、支援整合的類別，以及功能特有的需求，例如搜尋功能和建立自訂警示的能力。

## <a name="test-plan"></a>測試計劃

根據需求的不同，可能會適當的測試方法。 例如，如果需求是評估自動修復的 efficacy，則測試計劃必須包含一些步驟，以產生 Microsoft 365 Defender 內觸發自動修正動作 (s) 的行為。 如果需要偵測到特定行為或攻擊，測試可能需要更多步驟。 其重點是準備正確地測試您的需求。

## <a name="success-criteria"></a>成功準則

成功準則最後是設定為針對您要測試的專案進行度量的條碼。 不管您是要測試 Microsoft 365 Defender (或任何其他技術) 其他工具或其本身，都必須有一些可定量的準則，以判斷該工具所提供的值。 根據範圍、需求和測試計劃，成功的準則會決定如何對測試進行評分。 根據您的需求，這應該不會有較低的透過或失敗的加權計分。 例如，若要成功，工具可能需要在您識別的某些重要區域中排名超過80%。

## <a name="scorecard"></a>計分 卡

讓方案的所有元素一起使用的一種方式，也可以建立計分卡。 請參閱下方的範例計分卡：

| 使用案例 | 需求 | 設定需求 | 測試計劃 | 預期的結果 | 測試狀態 | 分數 | 附註 |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|事件管理|-Microsoft 365 Defender  </br></br>-Microsoft Defender 身分識別 </br></br>-Microsoft Defender for Endpoint </br></br>-Microsoft Cloud App Security (選用) |如需詳細資訊，請參閱 [預備課程](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 及設定準備工作 |[類比攻擊](m365d-pilot-simulate.md) <br></br>[調查事件](./m365d-pilot-simulate.md#investigate-an-incident) |調查人員可以瞭解該事件的範圍與影響，並管理該事件||||
|AutoIR|-Microsoft 365 Defender </br></br>-Microsoft Defender 身分識別 </br></br>-Microsoft Defender for Endpoint |如需詳細資訊，請參閱 [預備課程](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 及設定準備工作 <br>啟用 AutoIR  |[類比攻擊](m365d-pilot-simulate.md) <br></br>[自動調查](m365d-pilot-simulate.md#automated-investigation-and-remediation) |Microsoft 365 Defender 會自動修正警示和事件||||
|進階搜捕|-Microsoft 365 Defender </br></br>-Microsoft Defender for Endpoint </br></br>-Office 365 的 Microsoft Defender |如需詳細資訊，請參閱 [預備課程](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 及設定準備工作|[高級搜尋案例](./m365d-pilot-simulate.md#advanced-hunting-scenario) |調查人員可以透過高級搜尋、切換至受影響的實體，以及建立自訂的偵測，尋找資料||||



## <a name="next-step"></a>下一步
|![準備階段](../../media/mtp/prep.png) <br>[準備階段](prepare-m365d-eval.md) | 準備 Microsoft 365 的 Defender 試驗環境
|:-------|:-----|
