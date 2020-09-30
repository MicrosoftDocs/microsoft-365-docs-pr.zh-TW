---
title: Office 365 安全性
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- microsoft-365-docs-pr
description: Office 365 中的安全性（從 EOP 到 ATP 方案1和2）、標準與嚴格的安全性設定等等，因此您可以瞭解您擁有的內容，以及如何保護您的屬性。
ms.openlocfilehash: 680066f58850f59523ae6fb8a8168459dd813fc1
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304843"
---
# <a name="office-365-security-outline"></a>Office 365 安全性大綱

本文將向您介紹雲端中的新安全性屬性。 不論您是安全運作中心的一部分，您是安全性管理員新的空間，或是您想要使用複習，讓我們開始吧！

> [!CAUTION]
> 你好。 如果您使用的是 **Outlook.com**、 **microsoft 365 系列**或 **microsoft 365 個人**，且需要 *安全連結* 或 *安全附件* 資訊，請 ***按一下此連結***： [Microsoft 365 訂閱者的高級 Outlook.com 安全性](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。 謝謝！

## <a name="office-365-security-spelled-out"></a>Office 365 安全性已拼寫出

每個 Office 365 訂閱隨附安全性功能。 您可以採取的目標和動作取決於這些不同訂閱的重點。 在 Office 365 的安全性中，有三個主要的安全性服務 (或產品) 與您的訂閱類型相關聯：

1. Exchange Online Protection (EOP) 
1. 高級威脅防護，方案 1 (ATP P1) 
1. 高級威脅防護，Plan 2 (ATP P2) 

> [!NOTE]
> 如果您已購買您的訂閱，但 *現在必須立即*推出安全性功能，請跳至 [防護威脅](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide) 文章中的步驟。 如果您是在訂閱中新的，且想要知道您的授權，再開始之前，請在 [Microsoft 365 系統管理中心](https://admin.microsoft.com/AdminPortal/#/homepage)中，流覽帳單 > 您的產品。

Office 365 的安全性是以 EOP 提供的核心保護為基礎。 EOP 位於可以找到 Exchange Online 信箱的任何訂閱中 (請記住，此處所述的所有安全性產品都是雲端架構) 。

您可能習慣查看以這種方式討論這三個元件：

|EOP  | ATP P1 | ATP P2  |
|---------|---------|---------|
|防止廣泛、大量、大量、已知的攻擊。    |  保護從零天惡意程式碼、網路釣魚和商務電子郵件受損的電子郵件和共同作業。       | 針對訓練) 新增破壞後調查、搜尋和回應，以及自動和類比 (。         |

不過，根據架構的考慮，讓我們先將每個部分視為累計的安全性層級，每個都具有安全性重點。 更類似如下：

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_EOPandATPGraphic.png" alt-text="Placeholder graphic":::

雖然每個服務都會著重強調「保護」、「偵測」、「調查」及「回應」中的特定目標， ***所有*** 服務都可以執行 ***任何*** 保護、偵測、調查及回應的目標。

Office 365 的核心安全性是 EOP protection。 ATP P1 包含 EOP。 ATP P2 包含 P1 和 EOP。 結構為累計的。 如此一來，設定 ATP 時，應該會從 EOP 開始，並在各層中工作。

雖然電子郵件驗證設定會在公用 DNS 中進行，但必須設定此功能，以協助防禦欺騙。 *如果您有 EOP，* ***則應該 [設定電子郵件驗證](https://docs.microsoft.com/microsoft-365/security/office-365-security/email-validation-and-authentication?view=o365-worldwide)***。

如果您有 Office 365 E3 或更新版本，您可以使用 EOP，但可以選擇透過升級購買獨立的 ATP P1。 如果您有 Office 365 E5，表示您已有 ATP P2。

> [!TIP]
> 如果您的訂閱不是 Office 365 E3 或 E5，您仍然可以查看是否有升級為 ATP P1 的選項。 如果您感興趣， [此網頁](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) 會列出適用于 ATP P1 升級的訂閱 (檢查是否有精細列印) 頁面的結尾。

## <a name="the-office-365-security-ladder-from-eop-to-atp"></a>從 EOP 到 ATP 的 Office 365 安全性階梯

:::image type="content" source="../../media/tp_EOPATPEmailAuth4.gif" alt-text="Placeholder graphic":::

> [!IMPORTANT]
> 瞭解這些頁面的詳細資料： [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview?view=o365-worldwide)及 [高級威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)。

將 ATP 方案新增至純 EOP 威脅管理的優點，在第一眼中可能很難看出。 若要協助您的組織正確升級，請參閱下列各項產品的功能：

 - 防止和偵測威脅
 - 調查
 - 回應

從 **Exchange Online Protection**開始：
<p>

|防止/偵測  |調查  |回應  |
|---------|---------|---------|
| 技術包括：<ul><li>垃圾郵件</li><li>釣魚</li><li>惡意 軟體</li><li>大宗郵件</li><li>假冒情報</li><li>類比偵測</li><li>系統管理員隔離</li><li>系統管理員和使用者送出的誤報和漏報</li><li>URLs 和檔案的允許/封鎖</li><li>報告</li></u1>|<li>稽核記錄檔搜尋</li><li>郵件追蹤</li>|<li>零小時自動清除 (ZAP) </li><li>精簡及測試允許和封鎖清單</li>|

如果您想要深入瞭解 EOP，請 **[跳至本文](https://review.docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview?view=o365-21vianet&branch=tp_EOPOverview)**。

因為這些產品為累計性，所以如果您評估 ATP P1 並決定訂閱它，您將會新增這些功能。

透過「 **高級威脅防護」取得，Plan 1** (至日期) ：
<p>

|防止/偵測  |調查  |回應  |
|---------|---------|---------|
| 技術包括 EOP 中的所有專案，以及：<u1><li>安全附件</li><li>安全連結<li>工作負載的 ATP 保護 (ex。 SharePoint 商務) 的線上、小組 OneDrive</li><li>電子郵件、Office 用戶端和小組中的時間點擊保護</li><li>ATP 反網路釣魚</li><li>使用者和網域類比保護</li><li>警示和 SIEM 整合 API 的警示</li>|<li>SIEM 的整合 API</li><li>**即時偵測工具**</li><li>URL 追蹤</li>|<li>相同</li></u1>

因此，ATP P1 會擴充于房屋的 ***防護*** 端，並新增額外的 ***偵測***形式。

ATP P1 也會新增 **即時** 偵測以進行調查。 這項威脅搜尋工具的名稱是以粗體顯示，因為這是 *知道* 您有 ATP P1 的明確手段。 它不會出現在 ATP P2 中。

透過「 **高級威脅防護」取得，Plan 2** (至日期) ：
<p>

|防止/偵測  |調查  |回應  |
|---------|---------|---------|
| 技術包括 EOP 中的所有專案，以及 ATP P1 加上：<u1><li>相同</li>|<li>**威脅總管**</li><li>威脅追蹤工具</li><li>市場即時檢視</li>|<li>自動調查和回應 (AIR) </li><li>來自威脅瀏覽器的空氣</li><li>受損使用者的空氣</li><li>SIEM 整合 API 以進行自動化調查</li>

因此，ATP P2 會在房屋的 ***調查和回應*** 一側展開，並新增搜尋強度。 自動化。

在 ATP P2 中，主要搜尋工具稱為 **威脅瀏覽器** ，而不是即時偵測。 如果您在流覽至 [安全性中心] 時看到 [威脅瀏覽器]，表示您正在 ATP P2。

若要深入瞭解 ATP P1 和 P2 的詳細資料，請 **[跳至本文](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)**。

> [!TIP]
> 當使用者對使用者而言，EOP 和 ATP 也是不同的。 在 EOP 和 ATP P1 中，重點是「 *認知*」，所以這兩項服務會包含「 *報告訊息 Outlook 增益集* 」，讓使用者能夠報告他們發現可疑的電子郵件，以便進一步分析。 <p> 在包含 EOP 及 P1) 中的所有專案的 ATP P2 (中，焦點會切換至使用者的 *進一步訓練* ，所以安全性運作中心可以存取功能強大的 *威脅模擬器* 工具，以及它所提供的最終使用者衡量標準。

## <a name="office-365-atp-plan-1-vs-plan-2-cheat-sheet"></a>Office 365 ATP 方案1與 Plan 2 平面紙

這項快速參考可協助您瞭解每個 ATP 訂閱附帶的功能。 結合 EOP 功能的知識時，可協助業務決策者判斷最適合其需求的 ATP。

|Office 365 ATP 方案 1|Office 365 ATP 方案 2|
|---|---|
|<br/>設定、保護和偵測功能： <ul><li>[安全附件](atp-safe-attachments.md)</li><li>[安全連結](atp-safe-links.md)</li><li>[適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP](atp-for-spo-odb-and-teams.md)</li><li>[ATP 防網路釣魚保護](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)</li><li>[即時偵測](threat-explorer.md)</li></ul>|Office 365 ATP 方案 1 功能<br/>--- 以及 ---<br/>自動化、調查、補救和教育功能：</li><li>[威脅追蹤工具](threat-trackers.md)</li><li>[威脅總管](threat-explorer.md)</li><li>[自動調查及回應](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</li><li>[攻擊模擬器](attack-simulator.md)</li></ul>|
|

- Office 365 ATP 方案 2 包含在 Office 365 E5、Office 365 A5 和 Microsoft 365 E5 中。

- Office 365 ATP 方案 1 包含在 Microsoft 365 商務進階版中。

- Office 365 ATP 方案 1 和 Office 365 ATP 方案 2 各以某些訂閱附加元件的形式提供使用。 若要深入瞭解，請參閱以下的另一個連結 [功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

- 只有 Microsoft 365 E5 或 Microsoft 365 E5 安全性授權的使用者才能使用[安全文件](safe-docs.md)功能 (不包含在 Office 365 ATP 方案中)。

- 如果您目前的訂閱不包含 Office 365 ATP，且您想要，請與銷售人員合作， [以開始試用版](https://go.microsoft.com/fwlink/p/?LinkId=518644)，並瞭解在您的組織中 ATP 的運作方式。

> [!TIP]
> ***有問必答提示***。 您可以使用 [docs.microsoft.com] 目錄來瞭解 EOP 和 ATP。 流覽至 [Office 365 的安全性](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap?view=o365-worldwide) 文章，您會注意到，目錄組織會從評估與部署 (開始，包含遷移) ，然後繼續進行防護、偵測、調查和回應。 <p> 這種結構會加以分割，以便 **安全性管理** 主題遵循 **安全性操作** 主題。 如果您是工作角色的新成員，請使用此秘訣中的連結和您的目錄知識，協助您瞭解空間。 請記得使用反應 *連結* ，並在旅途中 *評價文章* 。 意見反應可協助我們改進我們為您提供的功能。