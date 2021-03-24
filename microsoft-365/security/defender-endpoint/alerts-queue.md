---
title: 查看和組織 Microsoft Defender ATP 警示佇列
description: 瞭解 Microsoft Defender ATP 警示佇列的運作方式，以及如何排序和篩選警示清單。
keywords: 警示，佇列，警示佇列，排序，順序，篩選，管理提醒，新增，進行中，已解決、最近、佇列中的時間、嚴重性、時間週期、microsoft 威脅專家警示
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 03/27/2020
ms.technology: mde
ms.openlocfilehash: e1c85db5afac70ec4f2520eed55dcc4f3773fd03
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060227"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a>查看和組織 Microsoft Defender for Endpoint 警示佇列

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-alertsq-abovefoldlink) 

**警示佇列** 顯示從您網路中的裝置標記的警示清單。 依預設，佇列會顯示過去30天的分組視圖中看到的警示。 最新的提醒會顯示在清單的頂端，可協助您先看到最近的警示。

> [!NOTE]
> 透過自動化調查和修正功能大幅減少警示佇列，讓安全性作業專家能夠將重點放在更複雜的威脅及其他高價值計畫上。 當警示包含自動調查的支援實體時 (例如，在具有支援之作業系統之裝置中的檔案) ，便可以開始進行自動調查和修正。 如需自動調查的詳細資訊，請參閱 [自動化調查的概述](automated-investigations.md)。

您可以選擇從多個選項自訂 [提醒] 佇列視圖。 

您可以在上方導覽上進行下列作業：

- 選取分組的 view 或 list view
- 自訂欄以新增或移除欄 
- 選取每頁顯示的專案
- 在頁面間流覽
- 套用篩選

![警示佇列的影像](images/alerts-queue-list.png)

## <a name="sort-filter-and-group-the-alerts-queue"></a>排序、篩選和群組警示佇列

您可以套用下列篩選器來限制警示清單，並取得更具焦點的查看警示。

### <a name="severity"></a>嚴重性

警示嚴重性 | 描述
:---|:---
高 </br> (Red)  | 與高級持續性威脅 (APT) 相關聯的警示。 這些警示指出高風險，因為它們可能會對裝置造成損毀。 一些範例包括：認證盜竊工具活動、未與任何群組相關聯的勒索軟體活動、篡改安全性感應器，或任何惡意活動表示的人體敵人。
中 </br> (橙色)  | Endpoint 偵測的警示，以及可能是「高級持續性」威脅 (APT) 部分的入侵後行為。 這包括常見的攻擊階段、反常登錄變更、可疑檔案執行等的觀察行為。 雖然有些可能是內部安全性測試的一部分，但它需要進行調查，因為它也可能是高級攻擊的一部分。
低 </br> (黃色)  | 與流行惡意程式碼相關聯的威脅警示。 例如，駭客的非惡意程式碼駭客工具（例如執行探索命令、清除記錄等）通常不表示組織的高級威脅。 它也可以來自組織中的使用者所進行的隔離安全性工具測試。
資訊 </br> (灰色)  | 可能不會被視為對網路有害，但可促進組織對潛在安全性問題的安全性意識的警示。

#### <a name="understanding-alert-severity"></a>瞭解警示嚴重性

Microsoft defender 防病毒 (Microsoft Defender AV) 和 Defender for Endpoint 警示嚴重性不同，因為它們代表不同的範圍。

Microsoft Defender AV 威脅嚴重性代表偵測到之威脅 (惡意程式碼) 中的絕對嚴重性，並根據個別裝置可能的潛在風險（如果受到感染）進行指派。

Defender for Endpoint alert 嚴重性代表偵測到的行為嚴重性、實際的裝置風險，但很重要的是組織的潛在風險。

因此，例如：

- 有關 Microsoft Defender AV 的 Defender for Endpoint 警示的嚴重性偵測到已完全避免但未感染裝置的威脅已分類為「資訊」，因為沒有實際的損毀。
- 執行時偵測到商業惡意程式碼的警示，但由於 Microsoft Defender AV 封鎖並修正，所以歸類為「低」，因為這可能會造成個別裝置的某些損毀，但不會造成任何組織威脅。
- 執行時偵測到惡意程式碼的警示，其可能不僅會對個別裝置造成威脅，也不論是否最後封鎖，都可能會排名為「中」或「高」。
- 未封鎖或修正的可疑行為警示，將會排名「低」、「中」或「高」，遵循相同的組織威脅考慮。

#### <a name="understanding-alert-categories"></a>瞭解警示類別

我們已重新定義警示類別，使其符合[MITRE ATT&CK matrix](https://attack.mitre.org/)中的[企業攻擊戰術](https://attack.mitre.org/tactics/enterprise/)。 新的類別名稱會套用至所有新的警示。 現有的提醒會保留先前的類別名稱。

下表列出目前的類別，以及它們通常對應至先前類別的方式。 

| 新增類別       | API 類別名稱   | 偵測到的威脅活動或元件                                                                                                 |
|----------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| 集合           | 集合          | 尋找及收集 exfiltration 的資料                                                                                         |
| 命令和控制項  | CommandAndControl   | 連接攻擊者控制的網路基礎結構以轉送資料或接收命令                                          |
| 認證存取    | CredentialAccess    | 取得有效的認證，以在網路中擴充裝置和其他資源的控制權                                       |
| 國防規避      | DefenseEvasion      | 避免安全性控制，例如，關閉安全性應用程式、刪除 implants，以及執行 rootkit                        |
| 發現            | 發現           | 收集重要裝置和資源的相關資訊，例如系統管理員電腦、網域控制站及檔案伺服器  |
| 執行            | 執行           | 啟動攻擊者工具和惡意程式碼（包括 Rat 和後門程式）                                                             |
| Exfiltration         | Exfiltration        | 將網路中的資料解壓縮至外部的受攻擊者控制的位置                                                         |
| 利用              | 利用             | 攻擊程式碼和可能的攻擊活動                                                                                       |
| 初始存取       | InitialAccess       | 取得目標網路的初始專案，通常涉及密碼猜測、入侵或網路釣魚電子郵件                      |
| 橫向移動     | LateralMovement     | 在目標網路中的裝置間移動，以達到重要資源或取得網路暫留                                |
| 惡意程式碼              | 惡意程式碼             | 後門程式、特洛伊木馬程式和其他類型的惡意程式碼                                                                                 |
| 堅持          | 堅持         | 建立 autostart 擴充點 (ASEPs) 保持使用中且可經受系統重新開機                                        |
| 許可權提升 | PrivilegeEscalation | 在特權程式或帳戶的上下文中執行程式碼，以取得更高的許可權層級                         |
| 軟體           | 軟體          | 惡意程式碼會加密檔案和 extorts 付款以還原存取                                                                     |
| 可疑活動  | SuspiciousActivity  | 可能成為惡意程式碼或部分攻擊的非典型活動                                                                 |
| 不需要的軟體    | UnwantedSoftware    | 影響生產力和使用者經驗的低信譽應用程式和應用程式偵測到可能有害的應用程式 (PUAs)  |

### <a name="status"></a>狀態

您可以選擇根據其狀態來限制警示清單。

### <a name="investigation-state"></a>調查狀態

會對應至自動調查狀態。

### <a name="category"></a>類別

您可以選擇篩選佇列以顯示特定類型的惡意活動。

### <a name="assigned-to"></a>指派給

您可以選擇顯示指派給您或自動化的警示。

### <a name="detection-source"></a>偵測來源

選取觸發警示偵測的來源。 Microsoft 威脅專家預覽參與者現在可以篩選並查看新威脅專家管理之搜尋服務中的偵測結果。

>[!NOTE]
>只有在裝置使用 Microsoft Defender 防病毒作為預設即時防護反惡意軟體產品時，才會顯示防病毒篩選器。

| 偵測來源                  | API 值                  |
|-----------------------------------|----------------------------|
| 協力廠商感應器                 | ThirdPartySensors          |
| 防毒                         | WindowsDefenderAv          |
| 自動調查           | AutomatedInvestigation     |
| 自訂偵測                  | CustomDetection            |
| 自訂 TI                         | CustomerTI                 |
| EDR                               | WindowsDefenderAtp         |
| Microsoft 365 Defender            | 具有 MTP 之                        |
| 適用於 Office 365 的 Microsoft Defender | OfficeATP                  |
| Microsoft 威脅專家          | ThreatExperts              |
| SmartScreen                       | WindowsDefenderSmartScreen |

### <a name="os-platform"></a>作業系統平臺

選取您要調查的作業系統平臺，以限制提醒佇列查看。

### <a name="device-group"></a>裝置群組

如果您有想要檢查的特定裝置群組，您可以選取群組來限制警示佇列的顯示。 

### <a name="associated-threat"></a>相關威脅

使用此篩選器，將重點放在與高設定檔威脅相關的警示上。 您可以在 [威脅分析](threat-analytics.md)中看到高設定檔威脅的完整清單。

## <a name="related-topics"></a>相關主題

- [管理 Microsoft Defender for Endpoint 警示](manage-alerts.md)
- [調查 Microsoft Defender for Endpoint 警示](investigate-alerts.md)
- [調查與 Microsoft Defender for Endpoint alert 相關聯的檔案](investigate-files.md)
- [調查 Microsoft Defender for Endpoint Devices 清單中的裝置](investigate-machines.md)
- [調查與 Microsoft Defender for Endpoint 警示相關聯的 IP 位址](investigate-ip.md)
- [調查與 Microsoft Defender for Endpoint alert 相關聯的網域](investigate-domain.md)
- [調查 Microsoft Defender for Endpoint 中的使用者帳戶](investigate-user.md)
