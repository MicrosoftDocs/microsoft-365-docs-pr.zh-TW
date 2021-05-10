---
title: 使用 Microsoft Defender 中 Office 365 的威脅瀏覽器的電子郵件安全性
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 查看並調查惡意程式碼釣魚企圖。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a2a6d3d10cfa21c0ad2da948bff130cb9336ebd8
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297618"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a>使用 Microsoft Defender 中 Office 365 的威脅瀏覽器的電子郵件安全性

本文內容：

- [查看電子郵件中偵測到的惡意程式碼](#view-malware-detected-in-email)
- [查看網路釣魚 URL，然後按一下 [已判定資料]](#view-phishing-url-and-click-verdict-data)
- [啟動自動調查及回應](#start-automated-investigation-and-response)

> [!NOTE]
> 這是 **威脅 Explorer (Explorer)**、**電子郵件安全性** 及 **Explorer 和即時** 偵測 (基礎的 **3 篇文章** 中的一部分，例如工具間的差異，以及操作) 所需的許可權。 此系列中的其他兩篇文章是威脅瀏覽器及[威脅瀏覽器和即時偵測基礎知識](real-time-detections.md)[中的威脅搜尋](threat-hunting-in-threat-explorer.md)。 

本文說明如何透過 Microsoft 365 的安全性功能，查看並調查電子郵件中偵測到的惡意程式碼和網路釣魚企圖。 

**適用於**

- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a>查看電子郵件中偵測到的惡意程式碼

若要查看以 Microsoft 365 技術排序的電子郵件中偵測到惡意程式碼，請使用 Explorer 的[電子郵件 > 惡意](threat-explorer-views.md#email--malware)代碼視圖 (或即時偵測) 。 惡意程式碼是預設的視圖，所以當您開啟 Explorer 時，可能會立即選取它。

1. 在 [安全性 & 規範中心] (<https://protection.office.com>) 中，選擇 [ **威脅管理** \> **瀏覽器** (] 或 [ **即時** 偵測]) 。  (本範例會使用 Explorer。如果您在 [收斂 Microsoft 365 安全性中心] 中，則 ) 使用 explorer (向 https://security.microsoft.com/) **電子郵件 & 協同**  >  **瀏覽器**。

   從這裡開始，在視圖中，選擇必要時要調查 (的特定時間框架) ，並依 [瀏覽器](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)的流覽方式，將篩選的重點放在一起。

2. 在 [ **視圖** ] 功能表中，選擇 [ **電子郵件** \> **惡意** 代碼]。

   > [!div class="mx-imgBorder"]
   > ![總管的檢視功能表](../../media/ExplorerViewEmailMalwareMenu.png)

3. 按一下 [ **寄件者**]，然後選擇 [ **基本** \> **偵測技術**]。

   您的偵測技術現在可做為報告的篩選器。

   > [!div class="mx-imgBorder"]
   > ![惡意程式碼偵測技術](../../media/ExplorerEmailMalwareDetectionTech.png)

4. 選擇 [選項]。 然後選取 [重新整理] **按鈕，套用** 該篩選。

   > [!div class="mx-imgBorder"]
   > ![選取的偵測技術](../../media/ExplorerEmailMalwareDetectionTechATP.png)

   報告會進行重新整理，以顯示惡意程式碼在電子郵件中偵測到的結果，並使用您選取的技術選項。 您可以從這裡進行進一步分析。 

## <a name="view-phishing-url-and-click-verdict-data"></a>查看網路釣魚 URL，然後按一下 [已判定資料]

您可以透過電子郵件中的 URLs 來查看網路釣魚嘗試，包括允許、封鎖和覆蓋的 URLs 清單。 若要識別所按一下的 URLs，必須設定 [安全連結](safe-links.md) 。 請確定您已設定 [安全連結原則](set-up-safe-links-policies.md) 的 [保護] 和 [記錄] 按一下 [安全連結] 中的 [verdicts]。

若要查看郵件中的網路釣魚 URLs，並按一下網路釣魚郵件中 URLs，請使用瀏覽器或即時偵測的 [**電子郵件**  >  **網路釣魚**](threat-explorer-views.md#email--phish)視圖。

1. 在 [安全性 & 規範中心] (<https://protection.office.com>) 中，選擇 [ **威脅管理** \> **瀏覽器** (] 或 [ **即時** 偵測]) 。 (此範例使用總管。)

2. 在 [ **視圖** ] 功能表中，選擇 [ **電子郵件** \> **釣魚網絡**]。

   > [!div class="mx-imgBorder"]
   > ![網路釣魚內容中瀏覽器的視圖功能表](../../media/ExplorerViewEmailPhishMenu.png)

3. 按一下 [ **寄件者**]，然後選擇 **URLs** \> **按一下 [判定**]。

4. 選取一個或多個選項（例如 **封鎖** 和 **封鎖**），然後在與套用該篩選的選項相同的列上選取 [重新整理 **] 按鈕。** (請勿重新整理瀏覽器視窗。)

   > [!div class="mx-imgBorder"]
   > ![URL 和按一下結果](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   報告會重新整理以在報告下的 [URL] 索引標籤上顯示兩個不同的 URL 表格：

   - **Top URLs** 是您篩選的郵件中 URLs，以及每個 URL 的電子郵件傳遞動作計數。 在網路釣魚電子郵件視圖中，此清單通常包含合法的 URLs。 攻擊者會在其郵件中混合使用良好和不良的 URLs，以嘗試傳遞，但它們會使惡意連結看起來更有趣。 URLs 的表格依總的電子郵件總數排序，但是此欄位是隱藏的，以簡化視圖。

   - **上** 指按一下的安全連結-包裝 URLs，依總按一下計數排序。 此欄位也不會顯示，以簡化視圖。 依資料行的總計數表示每個點擊過的 URL 的安全連結按一下結果計數。 在網路釣魚電子郵件視圖中，這些通常是可疑或惡意的 URLs。 不過，此視圖可以包含不是威脅的 URLs，但位於網路釣魚郵件中。 在這裡未顯示 URL 按一下已開啟的連結。

   這兩個 URL 表格會依照傳送動作和位置，顯示網路釣魚電子郵件中的最上層 URLs。 [！注意] 表格會顯示因警告而封鎖或訪問的 URL 按一下，因此您可以看到向使用者呈現的潛在不良連結，以及使用者所按一下的連結。 您可以從這裡進行進一步分析。 例如，在圖表下方，您可以在組織環境中所封鎖的電子郵件訊息中看到最上層 URLs。

   > [!div class="mx-imgBorder"]
   > ![已封鎖的總管 URL](../../media/ExplorerPhishClickVerdictURLs.png)

   選取 URL 以檢視更多詳細資訊。

   > [!NOTE]
   > 在 [URL 飛入] 對話方塊中，會移除電子郵件上的篩選，以顯示您環境中 URL 公開的完整視圖。 這可讓您在瀏覽器中篩選您關心的電子郵件訊息，找出潛在威脅的特定 URLs，然後透過 [URL 詳細資料] 對話方塊，展開您環境中的 URL 公開知識 () 而不必將 URL 篩選器新增至瀏覽器視圖本身。

### <a name="interpretation-of-click-verdicts"></a>按一下 verdicts 的轉譯

在電子郵件或 URL flyouts 中，按一下上方，在篩選體驗中，您會看到不同的按一下判定值：

- **無：** 無法捕獲 URL 的判定。 使用者可能已按一下透過 URL。
- **允許：** 允許使用者流覽至 URL。
- **封鎖：** 已封鎖使用者流覽至 URL。
- **擱置的判定：** 使用者呈現在引爆擱置的頁面上。
- **封鎖已被取代：** 封鎖使用者直接流覽至 URL。 但使用者 overrode 區塊以流覽至 URL。
- **擱置的判定略過：** 使用者呈現的是 [引爆] 頁面。 但使用者 overrode 郵件以存取 URL。
- **錯誤：** 使用者呈現錯誤頁面，或捕獲判定結果時發生錯誤。
- **失敗：** 捕獲判定時，發生未知的例外狀況。 使用者可能已按一下透過 URL。

## <a name="start-automated-investigation-and-response"></a>啟動自動調查及回應

> [!NOTE]
> 您可以在 *Microsoft Defender Office 365 方案 2* 和 *Office 365 E5* 中取得自動化調查和回應功能。

[自動化調查和回應](automated-investigation-response-office.md) 可儲存您的安全性運作小組時間和精力，以調查及緩解 cyberattacks。 除了設定會觸發安全性劇本的警示，您可以在總管中的檢視啟動自動化調查及回應程序。 如需詳細資訊，請參閱 [範例：安全性管理員會從瀏覽器觸發調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。

## <a name="other-articles"></a>其他文章

[使用電子郵件實體頁面調查電子郵件](mdo-email-entity-page.md)
