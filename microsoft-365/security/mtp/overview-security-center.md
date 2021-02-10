---
title: Microsoft 365 安全性中心概觀
description: Microsoft 365 security center 中的優點，結合 Microsoft Defender for Office 365 (MDO) 和 Microsoft Defender for Endpoint (MDE) ，使用 Microsoft Defender for Identity (MDI) 和 Microsoft Cloud App Security (MCAS) 。 本文概述適用于系統管理員的 Microsoft 365 安全性中心提升。
keywords: 安全性，惡意程式碼，Microsoft 365，M365，security center，monitor，report，identity，data，裝置，應用程式
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.date: 02/02/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 89e72d703bd70647d6c2b00732315b8e5f015cc7
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167179"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>整合的 Microsoft 365 安全性中心概述

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

適用於：

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [適用於 Office 365 的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2148715)

> 想要體驗 Microsoft 365 Defender？ 您可以 [在實驗室環境中進行評估](https://aka.ms/mtp-trial-lab) ，或 [在實際執行中執行您的試驗專案](https://aka.ms/m365d-pilotplaybook)。

改良的 **Microsoft 365 security center** ([https://security.microsoft.com](https://security.microsoft.com)) 會將保護、偵測、調查和回應，加入中央入口網站中的 *電子郵件*、共同作業、身分 *識別* 及 *裝置* 威脅。

Microsoft 365 的安全性中心會將現有 Microsoft 安全性入口網站的功能，例如 Microsoft Defender 安全性中心和 Office 365 安全性 & 合規性中心。 [安全性中心] 強調快速存取訊號、簡化版面配置，以及將相關資訊放在一起，以方便使用。 此中心包括：

- **[Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Microsoft Defender for Office 365 可協助組織使用一組預防、偵測、調查和搜尋功能保護其企業，以保護電子郵件和 Office 365 資源。
- **[Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** 會為組織中的裝置提供預防性保護、入侵後偵測、自動調查和回應。
- **[Microsoft 365 Defender](microsoft-threat-protection.md)** 是 Microsoft 的 *延伸偵測和回應* (XDR) 解決方案的一部分，利用 microsoft 365 安全性產品群組自動分析跨網域的威脅資料，並在單一儀表板上建立攻擊的圖片。

如果您需要從 Office 365 Security & 合規性中心或 Microsoft Defender 安全中心變更之專案的相關資訊，請參閱：

- [Microsoft 365 安全性中心中的適用於 Office 365 的 Defender](microsoft-365-security-center-mdo.md)
- [Microsoft 365 安全性中心中的適用於端點的 Defender](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>預期的專案

您可以在 Office 365 安全性與合規性中心中使用的所有安全性內容 (protection.office.com) 和 Microsoft Defender security center (securitycenter.microsoft.com) 現在可以在 *microsoft 365 的安全性中心* 內找到。

Microsoft 365 的安全性中心可協助安全小組調查從不同工作負載的信號到單一整合體驗，以調查和回應攻擊 brining：

- 事件 & 警示
- 狩獵
- 重要訊息中心
- 威脅分析

Microsoft 365 的安全性中心強調 *unity、清晰度及共同目標* ，因為它會合並 microsoft Defender for Office 365 和 microsoft Defender for Endpoint。 合併是以下列所列的優先順序為基礎，而不犧牲每個安全性套件加入組合的功能：

- 萬用群組建區塊
- 常見術語
- 一般實體
- 與其他工作負載的功能同位

## <a name="unified-investigations"></a>整合調查

簡化安全性中心會建立單一窗格，以調查整個 Microsoft 365 組織中的任何事件。 主要範例是 Microsoft 365 安全性中心的快速啟動上的 [ **事件** ] 節點。

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="MDO 中的 [事件] 頁面。":::

例如，按兩下具有 **高** 嚴重性的事件名稱，會帶您前往示範彙聚中心優勢的頁面。

![針對多個端點的許可權提升的多階段事件，顯示查看16個受影響裝置和9個受影響的使用者。](../../media/converged-incident-info-3.png)

> [!TIP]
> [收斂 **使用者** ] 索引標籤是開始查詢的好地方。 這個單一頁面) 會從聚合工作負載 (Microsoft Defender for Endpoint，Microsoft Defender for Identity，以及 MCAS 的使用者呈現資訊，例如內部部署 Active Directory、Azure Active directory、同步處理、本機和協力廠商使用者等來源。 深入瞭解 [新的使用者經驗](investigate-users.md)。

事件資訊顯示使用者/身分識別資訊，以及存在風險的信箱旁的使用者/身分識別。 它也會與任何 **調查資訊** 及收集的 **證據** 相關。 這可讓系統管理員和安全性運作小組更輕鬆地從一個高風險的警示到受影響的使用者和信箱。 查看此頁面頂端的 [ **事件** ] 索引標籤，可從這個單一位置取得其他重要的安全性轉動。

> [!IMPORTANT]
> 在特定事件的任何頁面上方，您都會看到 **摘要**、 **警示**、 **裝置**、 **使用者**、 **信箱**、 **調查** 和 **證據** 索引標籤。

選取「 **調查** 」會開啟一個頁面，其中會提供分析所用的圖形，並列出狀態 (例如 **待決核准**) 以進行修正）。 花時間在您的環境中選取特定的事件，深入查看這些索引標籤，並練習建立不同類型威脅的設定檔。 熟悉將會受益于以後的任何調查。

## <a name="improved-processes"></a>改進的處理常式

常見的控制項和內容會出現在相同的位置，或是壓縮成一個資料摘要，使其更容易尋找。 例如，統一設定。

### <a name="unified-settings"></a>統一設定

![已按一下「Role」，並開啟 [設定] 頁面，其中包含一般設定、許可權、APIs 及規則。 開啟許可權和角色。 顯示所有角色](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>許可權 & 角色

![& 角色] 頁面顯示端點角色的許可權 & 群組、角色和裝置群組。](../../media/converged-roles-5.png)

 存取 Microsoft 365 的安全性中心是透過 Azure Active Directory 全域角色或使用自訂角色進行設定。 若為 Defender for Endpoint，請參閱 [將使用者存取指派給 Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access)。 若為 Office 365 的 Defender，請參閱 [microsoft 365 規範中心和 microsoft 365 security center 中的許可權](../office-365-security/permissions-microsoft-365-compliance-security.md)。

- 深入瞭解如何 [管理 Microsoft 365 Defender 的存取](mtp-permissions.md)
- 深入瞭解如何在 Microsoft 365 的安全性中心[建立自訂角色](custom-roles.md)

### <a name="integrated-reports"></a>整合報告

報表也是 Microsoft 365 安全中心的整合。 系統管理員可以從一般的安全性報告開始，並在特定報告中分支至相關的端點、電子郵件 & 協同作業。 此處的連結是根據工作負載設定動態產生。

### <a name="quickly-view-your-microsoft-365-environment"></a>快速查看您的 Microsoft 365 環境

**首頁** 會顯示許多安全小組需要的常見智慧卡。 名片和資料的組成取決於使用者角色。 因為 Microsoft 365 的安全性中心使用角色型存取控制，所以不同的角色會在日常工作中看到更有意義的卡片。  

這種一覽的資訊可協助您維持組織中的最新活動。 Microsoft 365 的安全性中心將不同來源的信號彙集在一起，以呈現您的 Microsoft 365 環境的整體視圖。

這些卡片分為下列類別：

- 身分 **識別-監視** 組織中的身分識別，並追蹤可疑或危險的行為。 [深入瞭解身分識別保護](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。
- **Data** -Help 追蹤可能會導致未經授權的資料洩漏的使用者活動。
- **裝置** -在您的裝置上獲得最新資訊，提醒、違規活動及其他威脅。
- **App** -深入瞭解您的組織中使用雲端應用程式的方式。 [深入瞭解已探索 Cloud App Security 的應用程式](https://docs.microsoft.com/cloud-app-security/discovered-apps)。

## <a name="threat-analytics-with-better-data-coverage"></a>更好的資料覆蓋率進行威脅分析
使用下列 Microsoft 365 Defender 威脅分析整合體驗，追蹤並回應新興威脅：

- 在 Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 之間提供更佳的資料覆蓋率，以盡可能進行綜合的事件管理、自動調查、修復，以及主動或被動威脅搜尋。 
- Microsoft Defender for Office 365 中的電子郵件相關偵測和緩解，除了 Microsoft Defender for Endpoint 中已提供的端點資料之外。
- 威脅相關事件的觀點，可將提醒彙集至 Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 的端對端攻擊案例，以減少工作佇列，並簡化並加速您的調查。
- Microsoft 365 Defender 解決方案所偵測到和封鎖的攻擊嘗試。 此外，您還可以使用可讓您用來驅動預防性動作的資料，緩解進一步披露及提高恢復的風險。 
- 增強型設計可將可行動的資訊放在聚光燈中，協助您快速識別從報告中即時關注、調查和利用的資料。

## <a name="a-centralized-learning-hub"></a>集中式學習中樞

Microsoft 365 的安全性中心包含一個教學中心，該中樞會從 Microsoft 安全性博客、YouTube 上的 Microsoft security 社區及官方檔，透過這些資源冒泡官方指導方針。

在學習中樞內，電子郵件 & 共同作業 (Microsoft Defender for Office 365 或 MDO) 指引是以端點 (Microsoft Defender for Endpoint 或 MDE) ，以及 Microsoft 365 Defender 教學資源的方式並排顯示。

學習中心隨即開啟，其所組織的教學路徑，如「如何使用 Microsoft 365 Defender 進行調查？」主題。 和「Microsoft Defender for Office 365 最佳作法」。 此區段目前是由 Microsoft 中的安全性產品群組策劃。 每個學習路徑會反映所需的預測時間，以取得概念。 例如，預計 Microsoft Defender for Office 365 使用者帳戶已受損時所採取的步驟，將需要8分鐘，而且可以即時學習。

按一下內容之後，將此網站做成書簽並將書簽組織至 ' Security ' 或 ' 嚴重」資料夾可能會很有用。 若要查看所有學習路徑，請按一下主面板中的 [全部顯示] 連結。

> [!NOTE]
> Microsoft 365 security center 教學中樞的最上層有一些有説明的 **篩選準則** ，可讓您在目前的 Microsoft 365 Defender、microsoft Defender for Endpoint 和 microsoft Defender for Office 365) 中，選擇 (的產品。 請注意，會列出每個區段的學習資源數目，可協助教學人員追蹤他們手頭的訓練和學習資源數目。
>
> 除了產品篩選、目前主題、 (從影片到網路研討會的資源類型) 、熟悉或經驗的安全性區域、安全性角色及產品功能的層級。

## <a name="send-us-your-feedback"></a>將您的意見傳送給我們

我們需要您的意見反應。 我們一定會尋求改進功能，因此，如果您想要看到任何內容，請 [傳送您的 Microsoft 365 Defender 意見](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)反應。

您也可以留下本文的意見反應。 在「提交並查看意見反應」下方的「意見反應」區段中，選項是 *此產品* 或 *此頁面*。

針對 *產品* 回饋使用 **此產品** 按鈕：

1. 選取本文底部的 [ *本產品* ]。
    1. 如果您想要繼續閱讀這些指示，請在按鈕上按一下滑鼠右鍵，然後按一下 [在新索引標籤中開啟]。
2. 這會流覽至 **UserVoice 論壇**。
3. 您有2個選項：
    1. 向左下到文字方塊， *我們應如何改善相容性或保護您的使用者 Office 365 中的更好* ，並在 *Microsoft 365 的安全性中心* 貼上。 您可以搜尋結果與您的觀點，並向上-投票，或使用按鈕 **發佈新的觀點**。
    1. 如果您認為已經報告此問題，而且想要使用投票 (或投票) 提升其設定檔，請使用 UserVoice 右側的 [ *提供意見* 反應] 方塊。 搜尋 *Microsoft 365 security center*， **找出問題，然後使用 [投票] 按鈕** 提升其狀態。

使用 *此頁面* 以取得文章本身的回饋。 感謝您的意見反應。 您的語音可協助我們改進產品。

### <a name="explore-what-the-security-center-has-to-offer"></a>探索「安全性中心」所提供的功能

繼續探索 Microsoft 365 security center 中的功能：

- [管理事件及警示](manage-incidents.md)
- [使用威脅分析追蹤並回應新興威脅](threat-analytics.md)
- [重要訊息中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [尋找跨裝置、電子郵件、應用程式和身分識別的威脅](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-query-emails-devices)
- [自訂偵測規則](https://docs.microsoft.com/microsoft-365/security/mtp/custom-detection-rules)
- [電子郵件 & 共同作業警示](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)
- [建立網路釣魚攻擊模擬](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training) ，並 [建立訓練您的小組的負載](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>相關資訊
- [Microsoft 365 安全性中心](overview-security-center.md)
- [Microsoft 365 security center 中的 microsoft Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 security center 中的 microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)
- [將帳戶從 Microsoft Defender for Endpoint 重新導向至 Microsoft 365 安全中心](microsoft-365-security-mde-redirection.md)
