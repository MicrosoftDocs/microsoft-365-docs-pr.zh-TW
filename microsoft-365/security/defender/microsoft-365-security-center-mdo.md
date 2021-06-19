---
title: Microsoft 365 Defender 中的 Microsoft Defender Office 365
description: 瞭解從 Office 365 安全性與合規性中心到 Microsoft 365 Defender 的變更。
keywords: Microsoft 365 安全性，已開始使用 Microsoft 365 Defender，microsoft defender for Office 365，microsoft defender for Endpoint，MDO，MDE，單一窗格的玻璃，新的安全性入口網站，新的 Defender 安全性入口網站
ms.date: 02/21/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.prod: m365-security
ms.technology: m365d
ms.openlocfilehash: 15b1b152966c9c09bf77bea15b9b651f739c3566
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028952"
---
# <a name="microsoft-defender-for-office-365-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的 Microsoft Defender Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- [Microsoft 365 Defender](microsoft-365-defender.md)
- [適用於 Office 365 的 Microsoft Defender](/microsoft-365/security/office-365-security/defender-for-office-365)

## <a name="quick-reference"></a>快速參考

下表列出 Office 365 安全性 & 規範中心及 Microsoft 365 Defender 之間的導覽變更。

<br>

****

|[Office 365安全性 & 合規性](https://protection.office.com)|[Microsoft 365 Defender](https://security.microsoft.com)|[Microsoft 365 合規性中心](https://compliance.microsoft.com/homepage)|[Exchange 系統管理中心](https://admin.exchange.microsoft.com/#/)|
|---|---|---|---|
|警示|<ul><li>[警示原則](https://security.microsoft.com/alertpolicies)</li><li>[事件 & 警示](https://security.microsoft.com/alerts)</li></ul>|[提醒頁面](https://compliance.microsoft.com/homepage)||
|分類||請參閱[Microsoft 365 合規性中心](https://compliance.microsoft.com/homepage)||
|資料外洩防護||請參閱[Microsoft 365 合規性中心](https://compliance.microsoft.com/homepage)||
|記錄管理||請參閱[Microsoft 365 合規性中心](https://compliance.microsoft.com/homepage)||
|資訊控管||請參閱[Microsoft 365 合規性中心](https://compliance.microsoft.com/homepage)||
|威脅管理|[電子郵件 & 協同作業](https://security.microsoft.com/homepage)|||
|權限|[許可權 & 角色](https://security.microsoft.com/emailandcollabpermissions)|請參閱[Microsoft 365 合規性中心](https://compliance.microsoft.com/homepage)||
|郵件流程|||請參閱[Exchange 系統管理中心](https://admin.exchange.microsoft.com/#/)|
|資料隱私權||請參閱[Microsoft 365 合規性中心](https://compliance.microsoft.com/homepage)||
|搜尋|[稽核](https://security.microsoft.com/auditlogsearch?viewid=Async%20Search)|搜尋 (內容搜尋) ||
|報告|[報告](https://security.microsoft.com/emailandcollabreport)|||
|服務保證||請參閱[Microsoft 365 合規性中心](https://compliance.microsoft.com/homepage)||
|監督||請參閱[Microsoft 365 合規性中心](https://compliance.microsoft.com/homepage)||
|電子文件探索||請參閱[Microsoft 365 合規性中心](https://compliance.microsoft.com/homepage)||

[Microsoft 365 Defender](./overview-security-center.md) <https://security.microsoft.com> 結合現有 Microsoft 安全性入口網站的安全性功能，包括 Office 365 安全性 & 規範中心。 此改善的中心可協助安全性小組更有效且有效率地地保護其組織免受威脅。

如果您熟悉 Office 365 安全性與合規性入口網站 (protection.office.com) ，本文將說明 Microsoft 365 Defender 中的一些變更與改進。

深入瞭解好處： [Microsoft 365 Defender 綜述](overview-security-center.md)

如果您要尋找合規性相關的項目，請瀏覽 [Microsoft 365 合規性中心](https://compliance.microsoft.com/homepage)。

## <a name="new-and-improved-capabilities"></a>新功能與改進功能

左側瀏覽或快速啟動列看起來會很熟悉。 不過，此安全性中心有一些新的和更新的元素。

利用整合的 Microsoft 365 Defender 解決方案，您可以將威脅信號結合在一起，判斷威脅的完整範圍和影響，以及它目前對組織的影響。

:::image type="content" source="../../media/M365-defender-converge-experience.png" alt-text="Microsoft 365 Defender 收斂體驗的影像":::

Office 365 的使用者可以保護您的組織免受電子郵件訊息、連結 (URLs) 及共同作業工具帶來的惡意威脅。

:::image type="content" source="../../media/Defender-for-O365.png" alt-text="Office 365 的 Defender 影像":::

### <a name="incidents-and-alerts"></a>事件和警示

將橫跨電子郵件、裝置和身分識別的事件和警示管理結合在一起。 警示現在可在 [調查] 節點下取得，並有助於提供攻擊更廣泛的檢視。 警示頁面透過結合攻擊訊號來建構詳細的案例，提供警示的完整內容。 之前，警示是不同工作負載所特有。 全新、整合的體驗現在將不同工作負載的警示結合在一致的檢視中。 您可以快速分類、調查並採取有效動作。

- [深入了解調查](incidents-overview.md)
- [深入了解管理警示](/windows/security/threat-protection/microsoft-defender-atp/review-alerts)

![警示與動作快速啟動列](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>搜捕

使用[進階搜捕查詢](advanced-hunting-overview.md)來主動搜尋端點、Office 365 信箱等的威脅、惡意程式碼和惡意活動。 這些功能強大的查詢可用來找出並檢查已知和潛在威脅的威脅指示器和實體。

[自訂偵測規則](/windows/security/threat-protection/microsoft-defender-atp/custom-detection-rules) 可以從先進的搜尋查詢中建立，以協助您主動留意可能表示遭到破壞活動和配置錯誤裝置的事件。

以下是 Microsoft Defender for Office 365 中的[高級搜尋範例](advanced-hunting-example.md)。  

### <a name="action-center"></a>控制中心

控制中心會顯示已由自動化調查及回應功能所建立的調查。 Microsoft 365 Defender 中的這個自動化、自我修復功能會透過自動回應特定事件來協助安全性小組。

深入瞭解 [操作中心](m365d-action-center.md)。

#### <a name="threat-analytics"></a>威脅分析

從專業的 Microsoft 安全性研究工具取得威脅情報。 威脅分析可協助安全性小組在面對新興威脅時更有效率。 威脅分析包括：

- 適用於 Office 365 的 Microsoft Defender 的電子郵件相關偵測和緩和措施。 這是已可透過適用於端點的 Microsoft Defender 取得的端點資料的增加項目。
- 與威脅相關的事件檢視。
- 用於快速識別及使用報告中可採取動作資訊的增強體驗。

您可以從 Microsoft 365 Defender 的上方左導覽列中存取威脅分析，或是從顯示組織之主要威脅的專用儀表板卡存取。

深入瞭解如何 [使用威脅分析追蹤和回應新興威脅](./threat-analytics.md)。

### <a name="email--collaboration"></a>電子郵件與共同作業

追蹤和調查對您使用者的電子郵件的威脅、追蹤行銷活動等等。 如果您曾使用 Office 365 安全性與合規性中心，則這會是熟悉的。

:::image type="content" source="../../media/converge-3-email-and-collab-new.png" alt-text="電子郵件 & 的 [快速啟動] 功能表上 (或 MSDO) ，位於 Microsoft 365 Defender 左邊。":::

#### <a name="email-entity-page"></a>電子郵件實體頁面 

「 [電子郵件實體」頁面](../office-365-security/mdo-email-entity-page.md)已 *統一* 分散于過去不同頁面或視圖上的電子郵件資訊。 調查電子郵件是否有威脅和趨勢將會 *集中*。 標頭資訊和電子郵件預覽可透過相同的電子郵件頁面來存取，還有其他實用的電子郵件相關資訊。 同樣地，您可以在相同頁面的分頁上找到惡意檔案附件或 URL 的引爆狀態。 電子郵件實體頁面讓系統管理員和安全性作業小組能夠快速了解電子郵件威脅及其狀態，然後快速採取行動以判斷處理方式。

### <a name="access-and-reports"></a>存取和報告

檢視報告、變更您的設定，以及修改使用者角色。

:::image type="content" source="../../media/converge-4-access-and-reporting-new.png" alt-text="在 [安全性中心] 的左側 Microsoft 365 Defender 許可權與報告的 [快速啟動] 功能表。":::

> [!NOTE]
> DomainKeys 識別的郵件 (DKIM) 可確保目的地電子郵件系統信任從您的自訂網域傳送輸出的郵件。
> 針對 Office 365 使用者的 Defender，您現在可以透過 Microsoft 365 Defender *管理及輪替* DKIM 機碼， <https://security.microsoft.com/threatpolicy> 或流覽至 **原則 & 規則** \> **威脅原則** \> **DKIM**。
> 
> 如需詳細資訊，請參閱 [使用 DKIM 驗證從您的自訂網域傳送的輸出電子郵件](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email)。

## <a name="whats-changed"></a>變更的項目

此表格是威脅管理的快速參考，在 **安全性 & 規範中心** 與 **Microsoft 365 Defender** 入口網站之間發生變更。 按一下連結以閱讀更多有關這些區域的相關資訊。

<br>

****

|區域|變更描述|
|---|---|
|[調查](../office-365-security/office-365-air.md#changes-are-coming-soon-in-your-microsoft-365-defender-portal)|將[適用於 Office 365 的 Defender](/microsoft-365/security/office-365-security/defender-for-office-365) 和[適用於端點的 Defender](../defender-endpoint/automated-investigations.md) 的 AIR 功能結合在一起。 有了這些更新與改善功能，您的安全性作業小組就能在單一位置檢視電子郵件、共同作業內容、使用者帳戶和裝置上的自動化調查和補救動作的詳細資訊。|
|[警示佇列](../../compliance/alert-policies.md)|Office 安全性與合規性中心中的「**查看提醒**」彈出窗格現在包含 Microsoft 365 Defender 的連結。 按一下 [**開啟警示] 頁面** 連結，然後 Microsoft 365 Defender 隨即開啟。 您可以按一下 [警示] 佇列中的任何 Office 365 警示來存取 [檢視警示 **]** 頁面。|
|[攻擊模擬訓練](../office-365-security/attack-simulation-training-insights.md)|使用攻擊模擬訓練在組織中執行真實化的攻擊案例。 這些模擬攻擊可協助在真實的攻擊影響您的組織之前訓練您的員工。 攻擊模擬訓練包括更多選項、增強的報告，以及改善的訓練流程，可協助讓您的攻擊模擬與訓練案例更易於傳遞和管理。|
|

這些區域沒有變更：

- [總管](../office-365-security/threat-explorer.md)
- [原則與規則](../../compliance/alert-policies.md)
- [行銷活動](../office-365-security/campaigns.md)
- [提交](../office-365-security/admin-submission.md)
- [檢閱](./m365d-action-center.md)
- [威脅追蹤程式](../office-365-security/threat-trackers.md)

此外，請查看本文底部的 **相關資訊** 一節。

> [!IMPORTANT]
> Microsoft 365 Defender 入口網站 (<https://security.microsoft.com>) 結合中的安全性功能 <https://securitycenter.windows.com> 和 <https://protection.office.com> 。 不過，您會看到的項目將取決於您的訂閱。 例如，如果您只有適用於 Office 365 的 Microsoft Defender 方案 1 或 2，以獨立訂閱形式，您就不會看到有關適用於端點的安全性的功能，而適用於 Office 的 Defender 方案 1 客戶不會看到威脅分析之類的項目。

> [!TIP]
> 所有 Exchange Online Protection (的 EOP) 函數將會包含 Microsoft 365 Defender，因為 EOP 是 Office 365 的 Defender 核心元素。

## <a name="microsoft-365-defender-home-page"></a>Microsoft 365 Defender首頁

入口網站的首頁會針對您 Microsoft 365 環境的安全性狀態，呈現重要的摘要資訊。

您可以使用 **導覽** 來快速導覽端點或電子郵件與共同作業頁面。 請注意，您會在這裡的項目將取決於您是否擁有適用於 Office 365 的 Defender 和/或適用於端點的 Defender 授權。

也包含 **Office 365 安全性與合規性中心** 的連結供比較。 最後一個是描述最近的更新的 **新功能** 頁面的連結。

## <a name="related-information"></a>相關資訊

- [將 Office 365 安全性與合規性中心重新導向至 Microsoft 365 Defender](microsoft-365-security-mdo-redirection.md)
- [控制中心](./m365d-action-center.md)
- [電子郵件與共同作業警示](../../compliance/alert-policies.md#default-alert-policies)
- [自訂偵測規則](/microsoft-365/security/defender-endpoint/custom-detection-rules)
- [建立網路釣魚攻擊模擬](../office-365-security/attack-simulation-training.md)並[建立用於訓練您的人員的承載](../office-365-security/attack-simulation-training-payloads.md)
