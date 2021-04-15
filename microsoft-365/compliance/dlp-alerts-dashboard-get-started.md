---
title: 開始使用資料遺失防護警示儀表板
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 開始定義及管理資料遺失防護原則的提醒。
ms.openlocfilehash: 7f070dd960cc00ad7899c75117cd2a3fcf679973
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760698"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a>開始使用資料遺失防護警示儀表板

資料遺失防護 (DLP) 原則可以採取保護性動作，以避免無意間共用機密專案。 針對敏感專案採取動作時，您可以設定 DLP 的警示來通知您。 本文說明如何定義與資料遺失防護 (DLP) 原則相關聯的各種警示原則。 您將會瞭解如何使用[Microsoft 365 合規性中心](https://compliance.microsoft.com/)的[DLP 警示管理儀表板](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)來查看警示、事件，以及與 DLP 原則違規相關聯的中繼資料。

如果您是新的 DLP 警示，請參閱 [瞭解資料遺失防護警示儀表板](dlp-alerts-dashboard-learn.md)

## <a name="before-you-begin"></a>開始之前

開始之前，請確定您具備必要的必要條件：

-   DLP 警示管理儀表板的授權
-   警示設定選項的授權
-   角色

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>DLP 警示管理儀表板的授權

Office 365 DLP 所有合格租使用者都可以存取 DLP 警示管理儀表板。 若要開始，您應該具備適用于 Exchange Online、SharePoint 線上和商務 OneDrive 的 Office 365 DLP。 如需有關 Office 365 DLP 授權需求的詳細資訊，請參閱 [哪些授權可為使用者提供從服務受益的許可權？](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)。

使用適用于[小組 dlp](dlp-microsoft-teams.md)之[端點 dlp](endpoint-dlp-learn-about.md)的客戶，將會看到其 endpoint Dlp 原則警示和團隊 dlp 警示管理儀表板中的 dlp 原則警示。

**內容預覽** 功能僅適用于這些授權：

- Microsoft 365 (E5)
- Office 365 (E5)
- 高級規範 (E5) 新增
- Microsoft 365 E5/A5 資訊保護和控管
- Microsft 365 E5/A5 相容性

### <a name="licensing-for-alert-configuration-options"></a>警示設定選項的授權

**單一事件警示** 設定：具有 E1、F1 或 G1 訂閱或 E3 或 G3 訂閱的組織，只會建立在每次發生活動時觸發警示的警示原則。

**匯總的警示** 設定：若要根據臨界值來設定匯總警示原則，您必須使用下列其中一種授權設定：

- E5 或 G5 訂閱
- 具有下列其中一項功能的 E1、F1 或 G1 訂閱或 E3 或 G3 訂閱：
    - Office 365 進階威脅防護方案 2
    - Microsoft 365 E5 合規性
    - Microsoft 365 電子檔探索和審核附加元件授權

### <a name="roles"></a>角色


如果您想要查看 DLP 警示管理儀表板，或編輯 DLP 原則中的警示設定選項，您必須是下列其中一個角色群組的成員：

- 合規性系統管理員
- 合規性資料系統管理員
- 安全性系統管理員
- 安全性操作員
- 安全性讀取者

若要存取 DLP 警示管理儀表板，您需要：

- 管理警示

下列兩個角色之一：

- DLP 合規性管理
- 僅限檢視 DLP 合規性管理

若要存取內容預覽功能以及符合的敏感內容和內容，您必須是下列專案的成員：

- 內容瀏覽器內容檢視器角色群組

已預先指派「資料分類內容檢視器」角色。

## <a name="dlp-alert-configuration"></a>DLP 警示設定

若要瞭解如何在 DLP 原則中設定警示，請參閱 [開始使用資料遺失防護的位置](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)。

### <a name="aggregate-event-alert-configuration"></a>匯總事件警示設定

如果您的組織授權使用 [匯總的警示設定選項](#licensing-for-alert-configuration-options)，當您建立或編輯 DLP 原則時，您會看到這些選項。

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="螢幕擷取畫面顯示適用于已匯總警示設定選項之使用者的附隨報告選項。" border="false":::

這項設定可讓您設定原則，以在每次活動符合原則條件時或超過特定臨界值時，根據活動數量或根據挾帶資料量的數量來產生警示。

### <a name="single-event-alert-configuration"></a>單一事件警示設定

如果您的組織已取得 [單一事件警示設定選項](#licensing-for-alert-configuration-options)的授權，當您建立或編輯 DLP 原則時，您會看到這些選項。 使用此選項，可建立每當 DLP 規則相符時，就會引發警示。

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="螢幕擷取畫面顯示適用于單一事件警示設定選項的使用者附隨報告選項。" border="false":::

## <a name="investigate-a-dlp-alert"></a>調查 DLP 警示

若要使用 DLP 警示管理儀表板：

1. 在 [Microsoft 365 規範中心](https://www.compliance.microsoft.com)內，移至 [ **資料遺失防護**]。
2. 選取 [ **警示** ] 索引標籤，以查看 [DLP 警示] 儀表板。
3. 選取警示以查看詳細資料：

:::image type="content" source="../media/alert-details.png" alt-text="螢幕擷取畫面顯示 DLP 警示管理儀表板上的警示詳細資料。" border="false":::

4. 選取 [ **事件** ] 索引標籤，以查看與警示相關聯的所有事件。 您可以選擇特定的事件來查看其詳細資料。 如需部分可用事件詳細資料的清單，請參閱， [瞭解資料遺失防護提醒儀表板](dlp-alerts-dashboard-learn.md)。
5. 選取 [ **詳細資料** ] 開啟警示的 [ **一覽表** ] 頁面。 [一覽表] 頁面提供摘要：
    1. 發生什麼事
    1. 誰執行導致原則相符的動作
    1. 相符原則的相關資訊，以及其他 

6. 選擇 [ **事件** ] 索引標籤，存取：
    1. 相關內容
    1. 符合的敏感資訊類型
    1. 元

7. 選取 [ **敏感資訊類型** ] 索引標籤，以查看內容中偵測到的敏感資訊類型的詳細資料。 詳細資料包括信賴、計數，以及符合敏感資訊類型的內容。

8. 在調查提醒後，請回到 [ **概述** ] 索引標籤，以供您管理會審及管理提醒的處理及新增批註。

- 若要查看工作流程管理的史，請選擇 [ **記錄管理**]。
- 針對警示採取必要的動作後，請將警示的狀態設定為 [ **已解決**]。

## <a name="see-also"></a>另請參閱

- [深入瞭解資料遺失防護警示及警示儀表板](dlp-alerts-dashboard-learn.md)
- [建立、測試及調整 DLP 原則](create-test-tune-dlp-policy.md)