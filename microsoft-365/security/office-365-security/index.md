---
title: Office 365 安全性，Microsoft Defender for Office 365，EOP，MSDO
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
- M365-security-compliance
- m365initiative-m365-defender
description: Office 365 的安全性，從 EOP 到 Defender for Office 365 方案1和2，Standard 與 Strict 安全性設定等等。 瞭解您擁有的內容，以及如何保護您的屬性。
ms.openlocfilehash: 84d7dcfc68ce78bfde92f3d7096cd4104355ce94
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616245"
---
# <a name="office-365-security-overview"></a>Office 365 安全性概述

本文將向您介紹雲端中的新安全性屬性。 不論您是安全運作中心的一部分，您是安全性管理員新的空間，或是您想要使用複習，讓我們開始吧！

> [!CAUTION]
> 如果您使用 **Outlook.com**、 **microsoft 365 系列** 或 **microsoft 365 個人**，且需要 *安全連結* 或 *安全附件* 資訊，請 **按一下此連結** _： [Microsoft 365 訂閱者的高級 Outlook.com 安全性](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

## <a name="office-365-security-spelled-out"></a>Office 365 安全性已拼寫出

每個 Office 365 訂閱隨附安全性功能。 您可以採取的目標和動作取決於這些不同訂閱的重點。 在 Office 365 的安全性中，有三個主要的安全性服務 (或產品) 與您的訂閱類型相關聯：

1. Exchange Online Protection (EOP) 
1. Microsoft Defender for Office 365 Plan 1 (Defender for Office P1) 
1. Microsoft Defender for Office 365 Plan 2 (Defender for Office P2) 

> [!NOTE]
> 如果您已購買您的訂閱，而且需要 _right 立即推出安全性功能 *，請跳至 [防護威脅](protect-against-threats.md) 文章中的步驟。 如果您是在訂閱中新的，且想要知道您的授權，再開始之前，請在 [Microsoft 365 系統管理中心](https://admin.microsoft.com/AdminPortal/#/homepage)中，流覽帳單 > 您的產品。

Office 365 的安全性是以 EOP 提供的核心保護為基礎。 EOP 位於可以找到 Exchange Online 信箱的任何訂閱中 (請記住，此處所述的所有安全性產品都是雲端架構) 。

您可能習慣查看以這種方式討論這三個元件：

|EOP|Microsoft Defender for Office 365 P1|Microsoft Defender for Office 365 P2|
|---|---|---|
|防止廣泛、大量、大量、已知的攻擊。|保護從零天惡意程式碼、網路釣魚和商務電子郵件受損的電子郵件和共同作業。|針對訓練) 新增破壞後調查、搜尋和回應，以及自動和類比 (。|
|

不過，根據架構的考慮，讓我們先將每個部分視為累計的安全性層級，每個都具有安全性重點。 更類似如下：

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP 和 Microsoft Defender for Office 365，並以服務強調方式與彼此的關聯，包括電子郵件驗證的附注。":::

雖然上述每項服務都強調「保護」、「偵測」、「調查」及「回應」中的目標，但 **所有** 的服務都可以執行 _*_任何_*_ 保護、偵測、調查和回應的目標。

Office 365 的核心安全性是 EOP protection。 Microsoft Defender for Office 365 P1 包含 EOP。 適用于 Office 的 Defender 365 P2 包含 P1 和 EOP。 結構為累計的。 如此一來，當您設定此產品時，您應該開始使用 EOP 並使用 Office 365 的 Defender。

雖然電子郵件驗證設定會在公用 DNS 中進行，但必須設定此功能，以協助防禦欺騙。 _如果您有 EOP，請使用 * ***您應 [設定電子郵件驗證](email-validation-and-authentication.md)**_。

如果您有 Office 365 E3 或更新版本，您可以使用 EOP，但可以選擇透過升級購買 Office 365 P1 的獨立版 Defender。 如果您有 Office 365 E5，表示您已具備 Office 365 P2 的 Defender。

> [!TIP]
> 如果您的訂閱不是 Office 365 E3 或 E5，您仍然可以查看是否可以選擇升級為 Office 365 P1 的 Microsoft Defender。 如果您對此網頁感興趣， [此網頁](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) 會列出適用于 Office 365 P1 升級的訂閱。 (檢查是否有精細列印) 頁面的結尾。

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>從 EOP 到 Microsoft Defender for Office 365 的 Office 365 安全性階梯

![EOP 和 Microsoft Defender for Office 365 及其安全性強調，從 [保護] 和 [偵測] 調查並加以回應。 電子郵件驗證設定 (至少應設定 EOP 和 DMARC) 的 DKIM 和。](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> 瞭解這些頁面的詳細資料： [Exchange Online Protection](exchange-online-protection-overview.md)和 [Defender for Office 365](office-365-atp.md)。

新增 Microsoft Defender for Office 365 方案後，純 EOP 威脅管理的優點很難看出乍一眼。 若要協助您的組織正確升級，請參閱下列各項產品的功能：

- 防止和偵測威脅
- 調查
- 回應

開頭為 _ * Exchange Online Protection * *：
<p>

|防止/偵測|調查|回覆|
|---|---|---|
|技術包括：<ul><li>垃圾郵件</li><li>釣魚</li><li>惡意 軟體</li><li>大宗郵件</li><li>假冒情報</li><li>類比偵測</li><li>系統管理員隔離</li><li>系統管理員和使用者送出的誤報和漏報</li><li>URLs 和檔案的允許/封鎖</li><li>報告</li></u1>|<li>稽核記錄檔搜尋</li><li>郵件追蹤</li>|<li>零小時自動清除 (ZAP) </li><li>精簡及測試允許和封鎖清單</li>|
|

如果您想要深入瞭解 EOP，請 **[跳至本文](exchange-online-protection-overview.md)**。

因為這些產品已累計，所以如果您評估 Microsoft Defender for Office 365 P1 並決定訂閱它，您將會新增這些功能。

使用 **Defender For Office 365，Plan 1** (至日期) ：
<p>

|防止/偵測|調查|回覆|
|---|---|---|
|技術包括 EOP 中的所有專案，以及：<u1><li>安全附件</li><li>安全連結<li>Microsoft Defender for Office 365 工作負載的保護 (ex。 SharePoint 商務) 的線上、小組 OneDrive</li><li>電子郵件、Office 用戶端和小組中的時間點擊保護</li><li>Office 365 的 Defender 中的反網路釣魚</li><li>使用者和網域類比保護</li><li>警示和 SIEM 整合 API 的警示</li>|<li>SIEM 的整合 API</li><li>**即時偵測工具**</li><li>URL 追蹤</li>|<li>相同</li></u1>

因此，Microsoft Defender for Office 365 P1 會在室內的 [*_防護_*] 一側展開，並新增額外的 _*_偵測_*_ 形式。

Microsoft Defender for Office 365 P1 也會新增 [*即時* 偵測] *，以供調查之用。 這項威脅搜尋工具的名稱是以粗體顯示，因為其明確表示 *您擁有* Office 365 P1 的 Defender。 它不會出現在 Office 365 P2 的 Defender 中。

使用 **適用于 Office 365 的 Defender，Plan 2** (至日期) ：
<p>

|防止/偵測|調查|回覆|
|---|---|---|
|技術包括 EOP 中的所有專案，以及 Microsoft Defender for Office 365 P1 plus：<u1><li>相同</li>|<li>**威脅總管**</li><li>威脅追蹤工具</li><li>市場即時檢視</li>|<li>自動調查和回應 (AIR) </li><li>來自威脅瀏覽器的空氣</li><li>受損使用者的空氣</li><li>SIEM 整合 API 以進行自動化調查</li>

因此，Microsoft Defender for Office 365 P2 擴充于房屋的「*_調查與回應_*」一側，並新增搜尋強度。 自動化。

在 Microsoft Defender for Office 365 P2 中，會呼叫主要搜尋工具 _ *威脅瀏覽器**，而不是即時偵測。 如果您在流覽至 [安全性中心] 時看到 [威脅瀏覽器]，表示您是在 Microsoft Defender for Office 365 P2。

若要深入瞭解 Microsoft Defender for Office 365 P1 和 P2，請 **[跳至本文](office-365-atp.md)**。

> [!TIP]
> EOP 和 Microsoft Defender for Office 365 在使用者面臨的情況時也是不同的。 在 EOP 和 Defender for Office 365 P1 中，焦點為 [ *知曉*]，所以這兩項服務會包含「 *報告訊息 Outlook 增益集* 」，讓使用者能夠報告他們發現可疑的電子郵件，以便進一步分析。 <p> 在 Office 365 P2 (中包含 EOP 及 P1) 中的所有專案時，焦點會切換至使用者的 *進一步訓練* ，所以安全性運作中心可以存取功能強大的 *威脅模擬器* 工具，以及它所提供的最終使用者衡量標準。

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender for Office 365 方案1與 Plan 2 平面紙

這項快速參考可協助您瞭解每個 Microsoft Defender for Office 365 訂閱所附帶的功能。 當您掌握 EOP 功能的知識時，可協助業務決策者決定最適合其需求的 Microsoft Defender Office 365。

|適用于 Office 的 Defender 365 方案1|適用于 Office 的 Defender 365 方案2|
|---|---|
|設定、保護和偵測功能： <ul><li>[安全附件](atp-safe-attachments.md)</li><li>[安全連結](atp-safe-links.md)</li><li>[適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP](atp-for-spo-odb-and-teams.md)</li><li>[在 Office 365 的 Defender 中的反網路釣魚保護](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[即時偵測](threat-explorer.md)</li></ul>|Office 365 的 Defender 方案1功能 <p> --- 以及 --- <p> 自動化、調查、補救和教育功能： <ul><li>[威脅追蹤工具](threat-trackers.md)</li><li>[威脅總管](threat-explorer.md)</li><li>[自動調查及回應](office-365-air.md)</li><li>[攻擊模擬器](attack-simulator.md)</li></ul>|
|

- Microsoft Defender for Office 365 方案2隨附于 Office 365 E5、Office 365 A5 和 Microsoft 365 E5。

- Microsoft Defender for Office 365 方案1隨附于 Microsoft 365 商務版 Premium。

- Microsoft Defender for Office 365 Plan 1 和 Defender for Office 365 方案2每個功能都可作為特定訂閱的附加元件。 若要深入瞭解，您可以 [在 Microsoft Defender For Office 365 方案](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)中提供另一個連結功能可用性。

- 「 [安全檔](safe-docs.md) 」功能僅適用于使用 Microsoft 365 E5 或 Microsoft 365 e5 安全性授權的使用者 (未包含在 microsoft Defender for Office 365 方案) 中。

- 如果您目前的訂閱不包含 Microsoft Defender for Office 365，而您想要使用它，請 [聯繫我們的銷售人員開始試用版](https://go.microsoft.com/fwlink/p/?LinkId=518644)，並瞭解在您的組織中，microsoft Defender for office 365 如何運作。

> [!TIP]
> ***有問必答秘訣**。 您可以使用 [docs.microsoft.com] 目錄來瞭解 EOP 和 Microsoft Defender for Office 365。 向後流覽至此頁面， [Office 365 安全性簡介](https://docs.microsoft.com/microsoft-365/security/office-365-security)，您會注意到 [目錄] 組織位於側面列中。 其開始的部署 (包括遷移) ，然後繼續進行防護、偵測、調查和回應。 <p> 這種結構已分割，所以安全性 **操作** 主題後面會有 _ *安全性管理** 主題。 如果您是工作角色的新成員，請使用此秘訣中的連結和您的目錄知識，協助您瞭解空間。 請記得使用反應 *連結* ，並在旅途中 *評價文章* 。 意見反應可協助我們改進我們為您提供的功能。

## <a name="where-to-go-next"></a>下一步

如果您是安全性管理員，您可能需要為您的郵件設定 DKIM 或 DMARC。 您可能想要為優先順序使用者推出「嚴格」安全性預設，或尋找產品的新功能。 或者，如果您是使用安全性運算元，您可能想要利用即時的偵測或威脅瀏覽器來調查和回應，或使用攻擊模擬器訓練使用者偵測。 無論是哪一種方式，以下都有一些額外的建議，供您參考。

[電子郵件驗證，包含 SPF、DKIM 及 DMARC (，具有全部三個) 設定的連結 ](email-validation-and-authentication.md)

[請參閱特定建議的「黃金](recommended-settings-for-eop-and-office365-atp.md) 」設定，並 [使用建議的預設來快速設定安全性原則](preset-security-policies.md)

請追趕 [Microsoft Defender For Office 365 (中的新功能，包括 EOP 發展) ](whats-new-in-office-365-atp.md)

[使用威脅瀏覽器或即時偵測](threat-explorer.md)

[在 Microsoft Defender For Office 365 中使用攻擊模擬器](attack-simulator.md)
