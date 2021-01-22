---
title: 規劃您的試驗 Microsoft 365 Defender 專案
description: 與專案關係人規劃您的試驗 Microsoft 365 Defender 專案，以管理期望並確保結果成功。
keywords: Microsoft 威脅防護試驗計畫試驗 Microsoft 威脅防護專案，在生產階段評估 Microsoft 威脅防護、Microsoft 威脅防護試驗專案、網路安全性、進一步持續性威脅、企業安全性、裝置、裝置、身分識別、使用者、資料、應用程式、事件、自動化調查與補救、進一步搜尋
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 8037b71fc41fb7fb0bdbfc829bad2ece1de6849b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930171"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>規劃您的試驗 Microsoft 365 Defender 專案 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

|![規劃](../../media/phase-diagrams/1-planning.png)<br/>規劃|[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[製備](prepare-mtpeval.md) | [![類比攻擊](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)<br/>[類比攻擊](mtp-pilot-simulate.md) | [![結束和摘要](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)<br/>[結束和摘要](mtp-pilot-close.md)|
|--|--|--|--|
|*您目前在這裡！*| | | |

您目前正在規劃階段。

為了確保您的試驗專案成功，您一開始必須徹底規劃並取得專案關係人核准。 規劃的元素包括識別範圍、使用案例、需求及成功準則。

本指南會逐步引導您逐步瞭解如何規劃試驗專案。 

>[!IMPORTANT]
>為獲得最佳結果，請盡可能遵循試驗指示。


## <a name="scope"></a>範圍

試驗範圍會根據您的環境和可接受的測試方法判斷測試範圍。 以下是一些要考慮的範例範圍：
- 開發或測試環境，包括端點、伺服器、網網域控制站。
- 使用 Microsoft 365、Azure、Active Directory 服務、端點和伺服器的生產環境

>[!NOTE]
>如果您還沒有完整的授權，您可以取得試用授權來評估 [Microsoft 365 Defender](https://aka.ms/mtp-trial-lab) - 規劃、準備、設定、設定及執行試驗專案。 您的專案關係人將扮演重要角色，協助從開始到完成整個程式。

要評估的作業系統類型也應該根據組織架構來定義。 這可能包括下列各項[：Mac 端點](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements)[、Linux 伺服器](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements)[、Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)端點[、Windows Server 2016。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)

## <a name="use-cases"></a>使用案例

使用案例代表測試控管如何供其預定使用者使用的語句。 這些可以從特定人員的觀點來視為使用者案例，例如 SOC 分析師。 例如：
- 我是 SOC 分析師，我需要查看、關聯、評估和管理各裝置、使用者和網路中信箱的警示和事件。 [事件管理]
- 我是 SOC 分析師，必須擁有能自動調查及回應網路惡意事件的工具與程式。 [自動 IR]
- 我是 SOC 分析師，我必須搜尋我環境的資料，以尋找已知和潛在威脅，以及可疑的活動。 [進位搜尋]

請記住，這些使用案例應在已定義範圍的參數內建立。 例如，如果測試範圍不包含 Microsoft Cloud App 安全性等工具評估，則不應該建立以此功能為資料來源的使用案例。

## <a name="requirements"></a>需求

從使用案例清單中，您可以開始建立需求。 需求包括工具必須符合使用案例的功能。 這些需求可以細分為類別，例如組式與維護、整合支援，以及搜尋能力及建立自訂警示等功能特定需求。

## <a name="test-plan"></a>測試計劃

視需求不同，可能適合使用不同的測試方法。 例如，如果要求要評估自動化補救的效益，測試計劃必須包含步驟來產生行為 (s) ，以觸發 Microsoft 365 Defender 內的自動化補救動作。 如果需求是偵測特定行為或攻擊，則測試可能會涉及更多步驟。 重點就是制定計畫，以正確測試您的需求。

## <a name="success-criteria"></a>成功準則

成功準則最終還是會設定成標準，以根據您測試的結果來進行評估。 無論您是要針對其他工具或本身測試 Microsoft 365 Defender (或其他任何相關技術) ，都必須有一些可量化的準則來判斷工具提供的值。 根據範圍、需求和測試計劃，成功準則會決定如何為測試打分數。 這應該不會是通過或失敗，而應根據您的需求而更重計算加權分數。 例如，為了成功，工具可能需要在所識別的某些重要區域打到 80% 以上。

## <a name="scorecard"></a>計分 卡

將計畫的所有元素彙集在一起的方法之一，就是建立計分卡。 請參閱下方的範例計分卡：

| 使用案例 | 需求 | 組配置需求 | 測試計劃 | 預期的結果 | 測試狀態 | 分數 | 注意事項 |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|事件管理|- Microsoft 365 Defender  </br></br>- Microsoft Defender for Identity </br></br>- Microsoft Defender 端點 </br></br>- Microsoft Cloud App 安全性 (選擇性) |請參閱 [準備](https://aka.ms/mtp-trial-lab) 、設定及設定的先決條件，以瞭解詳細資料 |[類比攻擊](mtp-pilot-simulate.md) <br></br>[調查事件](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |使用者可以瞭解事件的範圍和影響，並管理事件||||
|AutoIR|- Microsoft 365 Defender </br></br>- Microsoft Defender for Identity </br></br>- Microsoft Defender 端點 |請參閱 [準備](https://aka.ms/mtp-trial-lab) 、設定及設定的先決條件，以瞭解詳細資料 <br>啟用 AutoIR  |[類比攻擊](mtp-pilot-simulate.md) <br></br>[自動化調查](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#automated-investigation-and-remediation) |Microsoft 365 Defender 會自動修復警示和事件||||
|進階搜捕|- Microsoft 365 Defender </br></br>- Microsoft Defender for Endpoint </br></br>-Microsoft Defender for Office 365 |請參閱 [準備](https://aka.ms/mtp-trial-lab) 、設定及設定的先決條件，以瞭解詳細資料|[進位搜尋案例](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#advanced-hunting-scenario) |小動物可以透過進一步搜尋、樞紐分析受影響實體，以及建立自訂偵測來尋找資料||||



## <a name="next-step"></a>下一步
|![準備階段](../../media/mtp/prep.png) <br>[準備階段](prepare-mtpeval.md) | 準備您的 Microsoft 365 Defender 試驗環境
|:-------|:-----|
