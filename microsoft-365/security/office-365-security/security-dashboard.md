---
title: 安全性儀表板概述
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 使用新的安全性儀表板來複查 Office 365 威脅防護狀態，並查看並處理安全性警示。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1504c84f0657dd049b63908d56c4ec6cca4871de
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055154"
---
# <a name="security-dashboard-in-the-security--compliance-center"></a>安全性 & 規範中心的安全性儀表板

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>基本功能及如何開啟安全性儀表板

安全性 & 合規性中心， <https://protection.office.com> 可讓您的組織管理資料保護和符合性。 假設您有必要的許可權，安全性儀表板可讓您檢查威脅防護狀態，以及查看和處理安全性警示。

觀賞影片以取得概要，然後閱讀本文以深入瞭解。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

根據您組織的訂閱內容，安全性儀表板包含數個小元件，例如威脅管理摘要、威脅防護狀態、全球每週威脅偵測、惡意程式碼等，如下列各節所述。

若要在安全性 & 規範中心中查看安全性儀表板，請移至 [ **威脅管理** \> **儀表板**]。 若要直接移至 [安全性] 儀表板，請使用 <https://protection.office.com/searchandinvestigation/dashboard> 。

> [!NOTE]
> 您必須是全域系統管理員、安全性管理員或安全性讀者，才可查看安全性儀表板。 有些小元件需要其他許可權才能進行查看。 若要深入瞭解，請參閱 [安全性 & 規範中心 [中的許可權](permissions-in-the-security-and-compliance-center.md)。

## <a name="threat-management-summary"></a>威脅管理摘要

「威脅管理」摘要構件會告訴您組織如何抵禦過去 7 (7) 天的威脅。

![安全性儀表板-威脅管理摘要構件](../../media/SecDash-ThreatMgmtSummary.png)

威脅管理摘要中所看到的資訊取決於您的訂閱所包含的內容。 下表說明 Office 365 E3 和 Office 365 E5 所包含的資訊。

<br>

****

|Office 365 E3|Office 365 E5|
|---|---|
|封鎖惡意程式碼郵件<br>封鎖網路釣魚郵件<br>使用者所報告的郵件<br><br><br><br>|封鎖惡意程式碼郵件<br>封鎖網路釣魚郵件<br>使用者所報告的郵件<br>已封鎖零天惡意程式碼<br>偵測到的高級網路釣魚郵件<br>封鎖惡意 URLs|
|

若要查看或存取威脅管理摘要小工具，您必須具有查看 Office 365 報告之 Defender 的許可權。 若要深入瞭解，請參閱[查看 Office 365 報表的 Defender 時，所需的許可權為何？](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)。

## <a name="threat-protection-status"></a>威脅防護狀態

「威脅防護狀態」構件會透過網路釣魚和惡意程式碼的趨勢和詳細觀點，顯示威脅防護的有效性。

![威脅防護狀態構件](../../media/tpswidget.png)

詳細資料會視您的 Microsoft 365 訂閱是否包含[Exchange Online Protection](exchange-online-protection-overview.md) (EOP) ，含或不含[Microsoft Defender for Office 365](defender-for-office-365.md)。

<br>

****

|如果您的訂閱包括 .。。|您將會看到這些詳細資料|
|---|---|
|EOP，但不是 Microsoft Defender for Office 365|EOP 所偵測到並封鎖的惡意電子郵件。<p> 請參閱 [威脅防護狀態報表 (EOP) ](view-email-security-reports.md#threat-protection-status-report)。|
|適用於 Office 365 的 Microsoft Defender|EOP 和 Defender Office 365 偵測並封鎖惡意的內容和惡意電子郵件 <p> 反惡意程式碼引擎、[零小時自動清除](zero-hour-auto-purge.md)及 Office 365 功能的 defender 等的獨特電子郵件累計計數，包含 Office 365) 中的[保管庫連結](safe-links.md)、[保管庫附件](safe-attachments.md)和[防網路釣魚](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) (。 <p> 請參閱 [威脅防護狀態報表](view-reports-for-mdo.md#threat-protection-status-report)。|
|

若要查看或存取威脅防護狀態構件，您必須具有查看 Office 365 報告之 Defender 的許可權。 若要深入瞭解，請參閱[查看 Office 365 報表的 Defender 所需的許可權為何？](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="global-weekly-threat-detections"></a>全球每週威脅偵測

「全球每週威脅偵測」構件會顯示電子郵件中已偵測到超過7個 (7) 天的威脅數目。

![全球每週威脅偵測小工具](../../media/globalweeklythreatdetections.png)

度量單位如下表所述進行計算：

<br>

****

|計量|計算方式|
|---|---|
|掃描的郵件|已掃描的電子郵件數目乘以收件者數目|
|威脅已停止|識別為包含惡意軟體的電子郵件數目乘以收件者數目|
|封鎖[Office 365 的 Defender](defender-for-office-365.md)|Office 365 被 Defender 封鎖的電子郵件數目乘以收件者數目|
|傳遞後移除|以 [零小時自動清除](zero-hour-auto-purge.md) 乘以的收件者人數所移除的郵件數目|
|

## <a name="malware"></a>惡意程式碼

惡意程式碼小元件會顯示過去七 (7) 天內，惡意程式碼趨勢和惡意程式碼系列類型的詳細資料。

![惡意程式碼趨勢及系列類型](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>深入解析

Insights 不僅應該檢查 surface key 問題，也包含要考慮的建議和動作。

![Smart insights](../../media/smartinsights.png)

例如，您可能會發現網路釣魚電子郵件已傳遞，因為某些使用者已停用其垃圾郵件選項。 若要深入瞭解真知灼見的運作方式，請參閱 [安全性 & 規範中心中的報告與深入](reports-and-insights-in-security-and-compliance.md)瞭解。

## <a name="threat-investigation-and-response"></a>威脅調查及回應

如果貴組織的訂閱包含[Microsoft Defender for Office 365 Plan 2](office-365-ti.md)，則您的安全性儀表板中有一個區段，其中包含高級威脅調查和回應工具。 這些工具組括 [自動調查和回應功能](automated-investigation-response-office.md)。 自動調查和回應可能會非常有用，例如， [快速定址已遭破壞的使用者帳戶](address-compromised-users-quickly.md)。

若要深入瞭解，請參閱[Office 365 中的開始使用自動調查和回應 (AIR) ](office-365-air.md)。

## <a name="trends"></a>趨勢

靠近安全性儀表板底部的趨勢區段是一個 **趨勢** 區段，它會摘要組織的電子郵件流程趨勢。 報告提供有關歸類為垃圾郵件、惡意程式碼、網路釣魚企圖及良好電子郵件的電子郵件資訊。 按一下拼貼，以查看報告中的詳細資訊。

![趨勢區段會摘要組織的電子郵件流程趨勢](../../media/trends.png)

此外，如果貴組織的訂閱中包含 [Office 365 方案2的 Defender](office-365-ti.md)，您也會在本節中有一個 **最近的威脅管理警示** 報告，讓安全性小組能夠查看並對高優先順序的安全性警示採取動作。

若要查看或存取已傳送及已接收的電子郵件小工具，您必須具有查看 Office 365 報告之 Defender 的許可權。 若要深入瞭解，請參閱[查看 Office 365 報表的 Defender 時，所需的許可權為何？](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)。

若要查看或存取最近的威脅管理提醒小工具，您必須具有查看提醒的許可權。 若要深入瞭解，請參閱 [查看提醒所需的 RBAC 許可權](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)。

## <a name="related-articles"></a>相關文章

[檢視安全性與合規性中心內的電子郵件安全性報告](view-email-security-reports.md)

[View Office 365 的 Microsoft Defender 報告](view-reports-for-mdo.md)

[適用於 Office 365 的 Defender](defender-for-office-365.md)

[Office 365威脅調查和回應](office-365-ti.md)
