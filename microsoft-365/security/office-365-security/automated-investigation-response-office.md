---
title: Microsoft Defender for Office 365 的自動化調查和回應運作方式
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: 自動化的事件回應、調查、修正及威脅防護
ms.date: 01/29/2021
description: 請參閱 Office 365 的 Microsoft Defender 中的自動化調查和回應功能的運作方式
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5a1384208141a42459c009952f89d18498cc21e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287922"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 的自動化調查和回應運作方式

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

在觸發安全性警示時，您的安全性運作小組會檢查這些警示，並採取步驟來保護您的組織。 在某些情況下，安全性作業小組可能感覺到所觸發的警示數量所淹沒。 Microsoft Defender for Office 365 中 (AIR) 功能的自動化調查和回應可提供協助。

AIR 可讓您的安全性運作小組更有效率地運作。 AIR 功能包括自動調查處理程式，以回應目前存在的已知威脅。 適當的修正動作等待核准，讓您的安全性作業小組能夠回應偵測到的威脅。

本文說明 AIR 如何透過數個範例運作。 當您準備好開始使用 AIR 時，請參閱 [自動調查和回應威脅](office-365-air.md)。

- [範例1：使用者報告的網路釣魚郵件啟動調查行動手冊](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [範例2：安全性管理員會觸發來自威脅瀏覽器的調查](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [範例3：安全操作小組使用 Office 365 管理活動 API，將 AIR 與其 SIEM 整合](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>範例：使用者報告的網路釣魚郵件啟動調查行動手冊

假設組織中的使用者收到他們認為是網路釣魚企圖的電子郵件。 使用者在報告這類訊息時，會使用 [報告訊息增益集](enable-the-report-message-add-in.md) 或 [報告網路釣魚增益集](enable-the-report-phish-add-in.md) 將其傳送至 Microsoft 進行分析。 提交也會傳送至您的系統，而且會顯示在 **提交** 視圖中 (先前稱為 **使用者報告** 的 view) 。 此外，使用者報告的訊息現在會觸發以系統為基礎的資訊性警示，這會自動啟動調查行動手冊。

在根調查階段中，會評估電子郵件的各個層面。 這些方面包括：

- 決定可能的威脅類型;
- 誰送出;
- 電子郵件傳送來源的 (傳送基礎結構) ;
- 電子郵件的其他實例是否已傳遞或封鎖;
- 我們分析員的評估;
- 電子郵件是否與任何已知的市場活動相關聯;
- 等等。

完成根調查之後，「行動手冊」會提供建議執行的動作清單，以供原始電子郵件和與其相關聯的實體使用。

接下來，會執行數個威脅調查和搜尋步驟：

- 類似的電子郵件會透過電子郵件聚簇搜尋加以識別。
- 此信號是與其他平臺（例如 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)）共用。
- 決定是否任何使用者已透過可疑電子郵件訊息中的任何惡意連結進行按一下。
- 在 Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) 和 ([Microsoft Defender for Office 365](office-365-atp.md)) 中進行檢查，以查看使用者是否已報告任何其他類似的郵件。
- 會執行檢查以查看使用者是否遭到破壞。 這種檢查會利用跨 Office 365、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)和 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)的信號，以關聯任何相關的使用者活動異常。

在搜尋階段中，會將風險和威脅指派給各種搜尋步驟。

修正是行動手冊的最後階段。 在此階段中，會根據調查和搜尋階段採取補救措施。

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>範例：安全性管理員會觸發來自威脅瀏覽器的調查

除了警示所觸發的自動調查之外，您的組織的安全性運作小組也可在 [威脅瀏覽器](threat-explorer.md)的視圖中觸發自動調查。  這種調查也會建立警示，使 Microsoft Defender 事件和外部 SIEM 工具可以查看已觸發此調查。

例如，假設您在瀏覽器中使用 **惡意** 代碼視圖。 您可以使用圖表下方的索引標籤，選取 [ **電子郵件** ] 索引標籤。如果您選取清單中的一或多個專案，則會啟動 **+ 動作** 按鈕。

![具有選取郵件的 Explorer](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

您可以使用 [ **動作** ] 功能表，選取 [ **觸發調查**]。

![選取郵件的動作功能表](../../media/explorer-malwareview-selectedemails-actions.jpg)

類似于警示所觸發的行動行動方式，從瀏覽器中的視圖觸發的自動調查包括根調查、識別和關聯威脅的步驟，以及緩解這些威脅的建議動作。

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>範例：使用 Office 365 管理活動 API，安全性運作小組與其 SIEM 整合 AIR

Microsoft Defender for Office 365 中的 AIR 功能包括 [報告 & 詳細資料](air-view-investigation-results.md) ，安全性作業小組可用以監視和處理威脅。 不過，您也可以整合 AIR 功能與其他解決方案。 範例包括安全性資訊和事件管理 (SIEM) 系統、案例管理系統或自訂報告解決方案。 您可以使用 [Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)來完成這些類型的整合。

例如，在最近，組織會設定安全性作業小組的方式，以查看已由 AIR 處理的使用者報告網路釣魚警報。 其解決方案會將相關的警示與組織的 SIEM 伺服器及其案例管理系統整合在一起。 此解決方案大幅減少誤報的數目，讓他們的安全性運作小組能夠專注于實際威脅的時間和工作。 若要深入瞭解此自訂解決方案，請參閱 [技術社區博客：使用 Microsoft Defender For Office 365 和 O365 管理 API，改善 SOC 的效能](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。

## <a name="next-steps"></a>後續步驟

- [開始使用 AIR](office-365-air.md)
- [查看擱置中或已完成的修復動作](air-review-approve-pending-completed-actions.md)
