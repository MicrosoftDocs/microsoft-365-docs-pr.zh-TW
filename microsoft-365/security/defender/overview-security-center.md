---
title: Microsoft 365 Defender 概述，結合 MDO、MDE、MDI 及 MCAS
description: Microsoft 365 Defender 的優點，結合 microsoft defender for Office 365 (MDO) 和 microsoft defender for Endpoint (MDE) ，使用 Microsoft defender for Identity (MDI) 和 Microsoft Cloud App Security (MCAS) 。 本文概述管理員的 Microsoft 365 Defender 進步。
keywords: security，malware，Microsoft 365，M365，security center，monitor，report，identity，data，裝置，應用程式
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.date: 04/21/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 8e37572b07c6d81abc531e204a8cb060f1f6402c
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194984"
---
# <a name="microsoft-365-defender-overview"></a>Microsoft 365 Defender 概述

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [適用於 Office 365 的 Microsoft Defender](/microsoft-365/security/office-365-security/defender-for-office-365)

> 想要體驗 Microsoft 365 Defender 嗎？ 您可以[在實驗室環境中評估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[在生產環境中執行試驗專案](m365d-pilot.md?ocid=cx-evalpilot)。

**Microsoft 365 Defender** ([https://security.microsoft.com](https://security.microsoft.com)) 在中央入口網站中結合保護、偵測 *、* 調查 *電子郵件*、共同作業、身分 *識別* 及 *裝置* 威脅的回應。

Microsoft 365 Defender 會將現有 Microsoft 安全性入口網站的功能彙集在一起，如 Microsoft Defender 資訊安全中心和 Office 365 安全性 & 規範中心。 [安全性中心] 強調快速存取訊號、簡化版面配置，以及將相關資訊放在一起，以方便使用。 此中心包括：

- **[Microsoft Defender Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** 適用于 Office 365 的 Microsoft Defender 可協助組織使用一組預防、偵測和搜尋功能保護其企業，以保護電子郵件，並 Office 365 資源。
- **[Microsoft Defender For Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** 會為組織中的裝置提供預防性保護、入侵後偵測、自動調查和回應。
- **[Microsoft 365 Defender](microsoft-365-defender.md)** 是 Microsoft 的 *延伸偵測和回應* (XDR) 解決方案的一部分，利用 Microsoft 365 的安全性產品群組，可自動分析跨網域的威脅資料，並在單一儀表板上建立攻擊的圖片。

如果您需要 Office 365 安全性 & 規範中心或 Microsoft Defender 資訊安全中心中所做變更的相關資訊，請參閱：

- [Microsoft 365 Defender 中的適用於 Office 365 的 Defender](microsoft-365-security-center-mdo.md)
- [Microsoft 365 安全性中心中的適用於端點的 Defender](microsoft-365-security-center-mde.md)

> [!NOTE]
> Microsoft 365 安全性入口網站會使用並強制執行現有的角色型存取，並將每一種安全性模型移至統一入口網站。 每個收斂工作負載都有自己的角色型存取權。 產品中已有的角色將會自動收斂至 Microsoft 365 的安全性入口網站。 不過，MCAS 的角色和許可權仍會在 MCAS 中處理。

## <a name="what-to-expect"></a>預期的專案

在 Office 365 安全性與合規性中心 (protection.office.com) 和 Microsoft Defender security center (securitycenter.microsoft.com) 中所使用的所有安全性內容，現在都可以在 *Microsoft 365 Defender* 中找到。

Microsoft 365 Defender 可協助安全小組調查攻擊，方法是將不同工作負載的信號引入一組整合體驗：

- 事件 & 警示
- 搜捕
- 控制中心
- 威脅分析

Microsoft 365 Defender 會強調 *unity、清晰度及共同目標*，因為它會合並 microsoft defender for Office 365 和 microsoft defender for Endpoint。 合併是以下列所列的優先順序為基礎，而不犧牲每個安全性套件所加入的功能：

- 萬用群組建區塊
- 常見術語
- 一般實體
- 與其他工作負載的功能同位

> [!NOTE]
> Microsoft 365 Defender 可以存取，而不需要客戶進行遷移步驟或購買新的授權。 例如，具有 E3 訂閱的系統管理員可以存取這個新入口網站，就像使用 Microsoft Defender 做為 Office 365 方案1和方案2一樣）。不過，Office 365 方案1客戶的 Exchange Online Protection 或 Defender 只會看到其訂閱授權所支援的安全性功能。 新的中心目標是集中安全性。

## <a name="unified-investigations"></a>整合調查

彙聚安全性中心建立單一位置，以用於調查各 Microsoft 365 的安全性事件。 主要範例是 Microsoft 365 Defender 的快速啟動上之 **事件 & 警示** 的 **事件**。

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="Microsoft 365 Defender 中的 [事件] 頁面。":::

選取 [事件名稱] 會顯示一個頁面，其中會示範「整合」安全中心的價值。

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Microsoft 365 Defender 事件摘要頁面的範例":::

<!--
![Example of the Summary page for an incident in Microsoft 365 Defender](../../media/converged-incident-info-3.png)
--> 

在 [事件] 頁面的頂端，您會看到 **摘要**、 **警示**、 **裝置**、 **使用者**、 **信箱**、 **調查** 和 **證據** 索引標籤。 如需詳細資訊，請選取這些索引標籤。 例如，[**使用者**] 索引標籤會顯示聚合工作負載 (microsoft defender for Endpoint、microsoft defender 身分識別及 Microsoft Cloud App Security) 和來源範圍（如內部部署 Active Directory 網域服務 (AD DS) 、Azure Active Directory (Azure AD) 和協力廠商身分識別提供者）的使用者資訊。 如需詳細資訊，請參閱 [調查使用者](investigate-users.md)。

花時間複習您環境中的事件、深入查看這些索引標籤，並練習如何針對不同類型的威脅存取針對事件所提供的資訊。

如需詳細資訊，請參閱[Microsoft 365 Defender 中的事件](incidents-overview.md)。

## <a name="improved-processes"></a>改進的處理常式

常見的控制項和內容會出現在相同的位置，或是壓縮成一個資料摘要，使其更容易尋找。 例如，統一設定。

### <a name="unified-settings"></a>統一設定

![按一下 [Role]，然後開啟 [設定] 頁面，其中包括一般設定、許可權、APIs 和規則。 開啟許可權和角色。 顯示所有角色](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>許可權 & 角色

![& 角色] 頁面顯示端點角色的許可權 & 群組、角色和裝置群組。](../../media/converged-roles-5.png)

 使用 Azure Active Directory 通用角色或使用自訂角色設定 Microsoft 365 Defender 的存取權。 若為 Defender for Endpoint，請參閱[Assign user access to Microsoft Defender 資訊安全中心](/microsoft-365/security/defender-endpoint/assign-portal-access)。 若為 Office 365 的 Defender，請參閱[Microsoft 365 合規性中心和 Microsoft 365 Defender 中的許可權](../office-365-security/permissions-microsoft-365-compliance-security.md)。

- 深入瞭解如何[管理 Microsoft 365 Defender 的存取](m365d-permissions.md)
- 深入瞭解如何在 Microsoft 365 Defender 中[建立自訂角色](custom-roles.md)

> [!NOTE]
> Microsoft 365 Defender 中的 Microsoft Defender for Endpoint 可支援在[microsoft defender security center 中授](./mssp-access.md)與存取[受管理的安全性服務提供者 (MSSPs) ](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)的方式。

### <a name="integrated-reports"></a>整合報告

報表在 Microsoft 365 Defender 中也是統一的。 系統管理員可以從一般的安全性報告開始，並在特定報告中分支至相關的端點、電子郵件 & 協同作業。 此處的連結是根據工作負載設定動態產生。

### <a name="quickly-view-your-microsoft-365-environment"></a>快速查看您的 Microsoft 365 環境

**首頁** 會顯示許多安全小組需要的常見智慧卡。 名片和資料的組成取決於使用者角色。 因為 Microsoft 365 的安全性中心使用角色型存取控制，所以不同的角色會在日常工作中看到更有意義的卡片。  

這種一覽的資訊可協助您維持組織中的最新活動。 Microsoft 365 Defender 會將不同來源的信號彙集在一起，以呈現您 Microsoft 365 環境的整體觀點。

這些卡片分為下列類別：

- 身分 **識別-監視** 組織中的身分識別，並追蹤可疑或危險的行為。 [深入瞭解身分識別保護](/azure/active-directory/identity-protection/overview-identity-protection)。
- **Data** -Help 追蹤可能會導致未經授權的資料洩漏的使用者活動。
- **裝置** -在您的裝置上獲得最新資訊，提醒、違規活動及其他威脅。
- **App** -深入瞭解您的組織中使用雲端應用程式的方式。 [深入瞭解雲端 App 安全性探索的應用程式](/cloud-app-security/discovered-apps)。

## <a name="threat-analytics-with-better-data-coverage"></a>更好的資料覆蓋率進行威脅分析
使用下列 Microsoft 365 Defender 威脅分析整合體驗，追蹤並回應新興威脅：

- 在 microsoft defender for Endpoint 和 microsoft defender for Office 365 之間提供更佳的資料覆蓋率，使綜合的事件管理、自動調查、修復、預防或反應性的威脅搜尋都有可能。 
- microsoft defender 針對 Office 365 的電子郵件相關偵測和緩解，除了 microsoft defender for endpoint 中已提供的端點資料之外。
- 威脅相關事件的觀點，可將提醒彙集至 microsoft defender for Endpoint 和 microsoft defender for Office 365 中的端對端攻擊案例，以減少工作佇列，並簡化及加快調查速度。
- Microsoft 365 Defender 方案偵測到並封鎖攻擊企圖。 此外，您還可以使用可讓您用來驅動預防性動作的資料，緩解進一步披露及提高恢復的風險。 
- 增強型設計可將可行動的資訊放在聚光燈中，協助您快速識別從報告中即時關注、調查和利用的資料。

## <a name="a-centralized-learning-hub"></a>集中式 Learning Hub

Microsoft 365 的安全性中心包含的學習中樞可深入瞭解 microsoft 安全性博客、YouTube 上的 microsoft security 社區，以及 docs.microsoft.com 的官方檔等資源的官方指導方針。

在學習中樞內，電子郵件 & 共同作業 (microsoft defender for Office 365) 指引是與端點 (microsoft defender for endpoint) 和 Microsoft 365 Defender 教學資源的並列搭配。

學習中心隨即開啟，並以類似「如何使用 Microsoft 365 Defender 進行調查」主題所組織的 Learning 路徑來開啟？ 和「Microsoft Defender for Office 365 最佳作法》。 此區段目前是由 Microsoft 中的安全性產品群組策劃。 每個 Learning 路徑會反映所需的預測時間，以取得概念。 例如，預計 Microsoft Defender Office 365 使用者帳戶受到危害時所採取的步驟，將需要8分鐘，而且可以即時瞭解有價值的知識。

按一下內容之後，將此網站做成書簽並將書簽組織至 ' Security ' 或 ' 嚴重」資料夾可能會很有用。 若要查看所有 Learning 路徑，請按一下主面板中的 [全部顯示] 連結。

> [!NOTE]
> Microsoft 365 Defender 學習中樞的頂端有一些有説明的 **篩選**，可讓您在目前 Microsoft 365 Defender 的 (產品、microsoft defender for Endpoint 和 microsoft defender for Office 365) 之間進行選擇。 請注意，會列出每個區段的學習資源數目，可協助教學人員追蹤他們手頭的訓練和學習資源數目。
>
> 除了產品篩選、目前主題、 (從影片到網路研討會的資源類型) 、熟悉或經驗的安全性區域、安全性角色及產品功能的層級。

> [!TIP]
> 在 [Microsoft 中學](/e/learn/)中還有許多其他的學習機會。 您可以找到認證訓練，例如[課程500T02：實施 Microsoft 365 威脅防護](/learn/certifications/courses/ms-500t02)。

## <a name="send-us-your-feedback"></a>將您的意見傳送給我們

我們需要您的意見反應。 我們一定會尋求改進，因此如果您想要看到任何內容，請[傳送您的 Microsoft 365 Defender 意見](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)反應給我們。

您也可以留下本文的意見反應。 在「提交並查看意見反應」下方的「意見反應」區段中，選項是 *此產品* 或 *此頁面*。

針對 *產品* 回饋使用 **此產品** 按鈕：

1. 選取本文底部的 [ *本產品* ]。
    1. 如果您想要繼續閱讀這些指示，請在按鈕上按一下滑鼠右鍵，然後按一下 [在新索引標籤中開啟]。
2. 這會流覽至 **UserVoice 論壇**。
3. 您有2個選項：
    1. 向左下到文字方塊，*我們應如何改善法規遵從性，或在 Office 365 中更好地保護您的使用者*，並在 *Microsoft 365 Defender* 中貼上。 您可以搜尋結果與您的觀點，並向上-投票，或使用按鈕 **發佈新的觀點**。
    1. 如果您認為已經報告此問題，而且想要使用投票 (或投票) 提升其設定檔，請使用 UserVoice 右側的 [ *提供意見* 反應] 方塊。 搜尋 *Microsoft 365 Defender*、**找出問題，然後使用 [投票] 按鈕** 提升其狀態。

使用 *此頁面* 以取得文章本身的回饋。 感謝您的意見反應。 您的語音可協助我們改進產品。

### <a name="explore-what-the-security-center-has-to-offer"></a>探索「安全性中心」所提供的功能

繼續探索 Microsoft 365 Defender 中的功能：

- [管理事件及警示](manage-incidents.md)
- [使用威脅分析追蹤並回應新興威脅](threat-analytics.md)
- [控制中心](m365d-action-center.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕威脅](./advanced-hunting-query-emails-devices.md)
- [自訂偵測規則](./custom-detection-rules.md)
- [電子郵件與共同作業警示](../../compliance/alert-policies.md#default-alert-policies)
- [建立網路釣魚攻擊模擬](../office-365-security/attack-simulation-training.md) ，並 [建立訓練您的小組的負載](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>相關資訊
- [Microsoft 365 Defender 中的 Microsoft Defender Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 Defender 中的 Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)
- [將帳戶從 Microsoft Defender for Endpoint 重新導向至 Microsoft 365 Defender](microsoft-365-security-mde-redirection.md)