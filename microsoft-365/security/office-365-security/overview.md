---
title: Office 365 安全性, 適用於 Office 365 的 Microsoft Defender, EOP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Office 365 中的安全性，從 EOP 到適用於 Office 365 的 Defender 方案 1 和 2、標準與嚴格安全性組態等等。 了解您擁有哪些項目，以及如何保護您的屬性。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: db37718ce2feae9c79ff6b323eb22e30f24e72b2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203625"
---
# <a name="office-365-security-overview"></a>Office 365 安全性概觀

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)


本文將向您介紹雲端中新的安全性屬性。 無論您是安全性作業中心的一員、該空間的新安全性系統管理員，還是想要進修的人員，讓我們開始吧。

> [!CAUTION]
> 如果您使用 **Outlook.com**、**Microsoft 365 家用版** 或 **Microsoft 365 個人版**，並且需要 *安全連結* 或 *安全附件* 資訊，***按一下這個連結***：[適用於 Microsoft 365 訂閱者的進階 Outlook.com 安全性](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

## <a name="office-365-security-spelled-out"></a>闡明 Office 365 安全性

每個 Office 365 訂閱都隨附安全性功能。 您可以採取的目標與動作取決於這些不同訂閱的焦點。 在 Office 365 安全性中，有三個主要安全性服務 (或產品) 繫結至您的訂閱類型：

1. Exchange Online Protection (EOP)
1. 適用於 Office 365 的 Microsoft Defender 方案 1 (適用於 Office 的 Defender P1)
1. 適用於 Office 365 的 Microsoft Defender 方案 2 (適用於 Office 的 Defender P2)

> [!NOTE]
> 如果您購買了訂閱，而且需要 *「立即」* 推出安全性功能，請跳到 [防範威脅](protect-against-threats.md)一文中的步驟。 如果您是訂閱的新手，並且想在開始之前先知道您的授權，請瀏覽 [Microsoft 365 系統管理中心](https://admin.microsoft.com/AdminPortal/#/homepage)的 [計費] > [您的產品]。

Office 365 安全性建立在 EOP 提供的核心保護上。 EOP 存在於任何可找到 Exchange Online 信箱的訂閱中 (請記住，這裡討論的所有安全性產品都是雲端式)。

您可能會習慣以下列方式來討論這三個元件：

|EOP|適用於 Office 365 的 Microsoft Defender P1|適用於 Office 365 的 Microsoft Defender P2|
|---|---|---|
|防止廣泛、以大量為基礎的已知攻擊。|保護電子郵件和共同作業，避免零時差惡意程式碼、網路釣魚和商務電子郵件洩露。|新增入侵後調查、搜捕和回應，以及自動化和模擬 (適用於訓練)。|
|

但是就架構而言，讓我們先將每個部分視為累積式安全性層，每個都強調安全性。 更多類似項目：

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP 和適用於 Office 365 的 Microsoft Defender 及其彼此之間的關係，強調服務，包括電子郵件驗證的注意事項。":::

雖然這些服務都強調保護、偵測、調查及回應之間的目標，***所有** _ 服務都可以執行保護、偵測、調查及回應的 *_任何_** 目標。

Office 365 安全性的核心是 EOP 保護。 適用於 Office 365 的 Microsoft Defender P1 在其中包含 EOP。 適用於 Office 365 的 Defender P2 包含 P1 和 EOP。 結構是累積的。 這就是為什麼在設定此產品時，您應該從 EOP 開始，然後使用適用於 Office 365 的 Defender。

雖然電子郵件驗證組態是在公用 DNS 中執行，但設定此功能有助於防範詐騙， *如果您有 EOP，* ***您應該 [設定電子郵件驗證](email-validation-and-authentication.md)***。

如果您有 Office 365 E3 或以下版本，表示您擁有 EOP，但是可選擇透過升級購買獨立版適用於 Office 365 的 Defender P1。 如果您有 Office 365 E5，表示您已經有適用於 Office 365 的 Defender P2。

> [!TIP]
> 如果您的訂閱不是 Office 365 E3 或 E5，您仍然可以檢查您是否有升級至適用於 Office 365 的 Microsoft Defender P1 的選項。 如果您有興趣，[此網頁](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids)列出適用於 Office 365 的 Microsoft Defender P1 升級的訂閱 (請查看頁面結尾以取得詳細內文)。

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>Office 365 安全性階梯，從 EOP 到適用於 Office 365 的 Microsoft Defender

![EOP 和適用於 Office 365 的 Microsoft Defender 及其安全性強調，從保護與偵測到調查與回應。 應該針對 EOP 設定電子郵件驗證組態 (至少 DKIM 和 DMARC)。](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> 在以下頁面了解詳細資料：[Exchange Online Protection](exchange-online-protection-overview.md) 和[適用於 Office 365 的 Defender](defender-for-office-365.md)。

新增適用於 Office 365 的 Microsoft Defender 方案對於純粹 EOP 威脅管理是優點，乍看之下難以察覺。 為了協助找出適合貴組織的升級路徑，讓我們看看每個產品的功能：

- 防止和偵測威脅
- 調查
- 回應

從 **Exchange Online Protection** 開始：
<p>

|防止/偵測|調查|回應|
|---|---|---|
|技術包括：<ul><li>垃圾郵件</li><li>網路釣魚</li><li>惡意程式碼</li><li>大宗郵件</li><li>詐騙智慧</li><li>模擬偵測</li><li>系統管理員隔離</li><li>系統管理員和使用者提交的誤判和誤否定</li><li>允許/封鎖 URL 和檔案</li><li>報告</li></u1>|<li>稽核記錄搜尋</li><li>郵件追蹤</li>|<li>零時差自動清除 (ZAP)</li><li>允許和封鎖清單的精簡與測試</li>|
|

如果您想要深入了解 EOP，請 **[進入本文](exchange-online-protection-overview.md)**。

由於這些產品是累積的，因此如果您評估適用於 Office 365 的 Microsoft Defender P1 並決定訂閱，您將新增這些能力。

與 **適用於 Office 365 的 Defender 方案 1** 一併取得 (目前為止)：
<p>

|防止/偵測|調查|回應|
|---|---|---|
|技術包含 EOP 中的所有項目，再加上：<u1><li>安全附件</li><li>安全連結<li>適用於 Office 365 的 Microsoft Defender 工作負載保護 (例如 SharePoint Online、Teams、商務用 OneDrive)</li><li>電子郵件、Office 用戶端和 Teams 中的點擊時保護</li><li>適用於 Office 365 的 Defender 中的反網路釣魚</li><li>使用者和網域模擬保護</li><li>警示和警示的 SIEM 整合 API</li>|<li>適用於偵測的 SIEM 整合 API</li><li>**即時偵測工具**</li><li>URL 追蹤</li>|<li>相同</li></u1>

因此，適用於 Office 365 的 Microsoft Defender P1 會在房屋擴展 ***防止** _ 端，並且新增額外形式的 _*_偵測_**。

適用於 Office 365 的 Microsoft Defender P1 也會為調查新增 **即時偵測**。 此威脅搜捕工具的名稱是粗體，因為清楚標示即表示您 *知道* 您有適用於 Office 365 的 Defender P1。 它不會出現在適用於 Office 365 的 Defender P2 中。

與 **適用於 Office 365 的 Defender 方案 2** 一併取得 (目前為止)：
<p>

|防止/偵測|調查|回應|
|---|---|---|
|技術包括 EOP 中的所有項目和適用於 Office 365 的 Microsoft Defender P1，再加上：<u1><li>相同</li>|<li>**威脅總管**</li><li>威脅追蹤工具</li><li>行銷活動檢視</li>|<li>自動調查及回應 (AIR)</li><li>威脅總管的 AIR</li><li>適用於遭到入侵之使用者的 AIR</li><li>適用於自動化調查的 SIEM 整合 API</li>

因此，適用於 Office 365 的 Microsoft Defender P2 會擴展房屋的 ***調查與回應*** 端，並且新增新的搜捕強度。 自動化。

在適用於 Office 365 的 Microsoft Defender P2 中，主要搜捕工具稱為 **威脅總管**，而非即時偵測。 如果您在瀏覽至安全性中心時看到威脅總管，表示您位於適用於 Office 365 的 Microsoft Defender P2 中。

若要了解適用於 Office 365 的 Microsoft Defender P1 和 P2 的詳細資料，請 **[進入本文](defender-for-office-365.md)**。

> [!TIP]
> 對於使用者來說，EOP 和適用於 Office 365 的 Microsoft Defender 也不同。 在 EOP 和適用於 Office 365 的 Defender P1 中，焦點是 *感知*，因此這兩個服務包括 *報告訊息 Outlook 增益集*，讓使用者能夠報告發現可疑的電子郵件，以便進一步分析。 <p> 在適用於 Office 365 的 Defender P2 (其中包含 EOP 中的所有項目和 P1) 中，焦點會轉移到適用於使用者的 *進一步訓練*，因此安全性作業中心可以存取功能強大的 *威脅模擬器* 工具，以及它提供的使用者計量。

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>適用於 Office 365 的 Microsoft Defender 方案 1 與方案 2 速查表

此快速參考可協助您了解每個適用於 Office 365 的 Microsoft Defender 訂閱提供哪些功能。 結合您對於 EOP 功能的知識，它可以協助企業決策者判斷哪些適用於 Office 365 的 Microsoft Defender 最符合其需求。

|適用於 Office 365 的 Defender 方案 1|適用於 Office 365 的 Defender 方案 2|
|---|---|
|設定、保護和偵測功能： <ul><li>[安全附件](safe-attachments.md)</li><li>[安全連結](safe-links.md)</li><li>[適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件](mdo-for-spo-odb-and-teams.md)</li><li>[適用於 Office 365 的 Defender 中的反網路釣魚防護](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[即時偵測](threat-explorer.md)</li></ul>|適用於 Office 365 的 Defender 方案 1 的功能 <p> --- 以及 --- <p> 自動化、調查、補救和教育功能： <ul><li>[威脅追蹤工具](threat-trackers.md)</li><li>[威脅總管](threat-explorer.md)</li><li>[自動調查及回應](office-365-air.md)</li><li>[攻擊模擬器](attack-simulator.md)</li></ul>|
|

- 適用於 Office 365 的 Microsoft Defender 方案 2 隨附於 Office 365 E5、Office 365 A5 和 Microsoft 365 E5。

- 適用於 Office 365 的 Microsoft Defender 方案 1 隨附於 Microsoft 365 商務進階版。

- 適用於 Office 365 的 Microsoft Defender 方案 1 和適用於 Office 365 的 Defender 方案 2 均以附加元件形式為特定訂閱提供。 若要深入了解，請參閱另一個連結：[適用於 Office 365 的 Microsoft Defender 方案的功能可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

- [安全文件](safe-docs.md)功能僅可供具備 Microsoft 365 E5 或 Microsoft 365 E5 安全性授權 (未包含在適用於 Office 365 的 Microsoft Defender 方案中) 的使用者使用。

- 如果您目前的訂閱未包含適用於 Office 365 的 Microsoft Defender 而且您想要取得，請[與銷售人員連絡以開始試用](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)，並了解適用於 Office 365 的 Microsoft Defender 可以如何在您的組織中運作。

> [!TIP]
> ***測試人員提示** _. 您可以使用 docs.microsoft.com 目錄來了解 EOP 和適用於 Office 365 的 Microsoft Defender。 瀏覽回 [Office 365 安全性概觀](index.yml)這個頁面，您會注意到提要欄位中的目錄組織。 它會從部署 (包括移轉) 開始，然後繼續進行防護、偵測、調查及回應。 <p> 此結構會分成 _ *安全性管理** 主題，後面接著 **安全性作業** 主題。 如果您是任一作業角色的新成員，請使用此提示中的連結，以及您對於目錄的知識，來協助了解空間。 請記得在進行時使用 *意見反應連結* 並且 *為文章評分*。 意見反應可協助我們改進我們為您提供的項目。

## <a name="where-to-go-next"></a>接下來要前往何處

如果您是安全性系統管理員，您可能需要為郵件設定 DKIM 或 DMARC。 您可能會想要為優先使用者推出「嚴格」安全性預先設定，或尋找產品中的新功能。 或者，如果您使用安全性作業，您可能想要利用即時偵測或威脅總管來調查及回應，或使用攻擊模擬器來訓練使用者偵測。 無論是哪種方式，以下是一些接下來要查看的其他建議。

[電子郵件驗證，包括 SPF、DKIM 和 DMARC (包含全部三個設定的連結)](email-validation-and-authentication.md)

[查看特定建議的「黃金」設定](recommended-settings-for-eop-and-office365.md)和[使用建議的預設來快速設定安全性原則](preset-security-policies.md)

了解[適用於 Office 365 的 Microsoft Defender 新功能 (包括 EOP 開發)](whats-new-in-defender-for-office-365.md)

[使用威脅總管或即時偵測](threat-explorer.md)

使用[適用於 Office 365 的 Microsoft Defender 中的攻擊模擬器](attack-simulator.md)