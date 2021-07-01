---
title: 深入了解資料外洩防護
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 瞭解如何使用 Microsoft 365 資料遺失防護原則及工具來保護您的機密資訊，並透過 DLP 生命週期進行導覽。
ms.openlocfilehash: 291a9ab09d14e24d58604644d77381d7f41214d6
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226848"
---
# <a name="learn-about-data-loss-prevention"></a>深入了解資料外洩防護

組織在其控制之下的敏感資訊，例如財務資料、專有資料、信用卡號碼、健康記錄或社會保險號碼。 為了協助保護這種敏感性資料，並降低風險，他們需要一種方式，以防止使用者不適當地與未安裝的人員共用。 這種作法稱為資料遺失防護 (DLP) 。

在 Microsoft 365 中，您可以定義及套用 DLP 原則，以執行資料遺失防護。 使用 DLP 原則，您可以識別、監視和自動保護不同的敏感專案：

- Microsoft 365 服務（如 Teams、Exchange、SharePoint 及 OneDrive）
- Office 的應用程式，例如 Word、Excel 及 PowerPoint
- Windows 10 端點
- 非 Microsoft cloud app
- 內部部署檔案共用和內部部署 SharePoint。

Microsoft 365 使用深入的內容分析來偵測敏感專案，而不只是簡單的文字掃描。 會透過評估正則運算式、內建函式驗證，以及與主要資料比對接近的次要資料比對，來分析主要資料符合關鍵字的內容。 除了該 DLP 之外，還會使用電腦學習演算法和其他方法，偵測符合您 DLP 原則的內容。

## <a name="dlp-is-part-of-the-larger-microsoft-365-compliance-offering"></a>DLP 是較大 Microsoft 365 規範服務的一部分

Microsoft 365DLP 只是其中一個 Microsoft 365 規範工具，可讓您在任何居住或旅行時，協助保護您的敏感專案。 您應該瞭解 Microsoft 365 規範工具集合中的其他工具，如何 interrelate，以及如何搭配一起運作。  請參閱， [Microsoft 365 規範工具](protect-information.md)以深入瞭解資訊保護程式。

## <a name="protective-actions-of-dlp-policies"></a>DLP 原則的保護性動作

Microsoft 365DLP 原則是指如何監控使用者對靜止專案所採取的活動、傳輸中的敏感專案，或使用中的敏感專案，以及採取保護動作。 例如，當使用者嘗試採取禁止的動作時（例如，將敏感專案複製到未核准的位置，或是在原則中所佈置的其他情況下）共用醫學資訊時，DLP 便可：

- 向使用者顯示彈出的原則提示，告知他們可能嘗試以不當的方式共用敏感專案
- 封鎖共用，並透過原則提示讓使用者覆寫封鎖，並捕獲使用者的合理性論證
- 封鎖不含覆寫選項的共用
- 針對靜態的資料，可鎖定敏感專案並將其移至安全的隔離位置
- 若為 Teams 聊天室，將不會顯示機密資訊。

所有 DLP 監控的活動預設都會記錄到[Microsoft 365 的審計記錄](search-the-audit-log-in-security-and-compliance.md)，並路由傳送至[活動瀏覽器](data-classification-activity-explorer.md)。 當使用者執行符合 DLP 原則條件的動作，並已設定警示時，DLP 會在 [dlp 警示管理儀表板](dlp-configure-view-alerts-policies.md)中提供警示。

## <a name="dlp-lifecycle"></a>DLP 生命週期

DLP 實施通常會遵循這些主要階段。

- [規劃 DLP](#plan-for-dlp)
- [準備 DLP](#prepare-for-dlp)
- [在生產環境中部署原則](#deploy-your-policies-in-production)


<!--ADD DIAGRAM OF THE DLP LIFECYCLE WORK ON WITH MAS-->

### <a name="plan-for-dlp"></a>規劃 DLP

Microsoft 365DLP 監控和保護是使用者每天使用之應用程式的原生。 這有助於保護組織的敏感專案免受危險的活動，即使您的使用者 unaccustomed 到資料遺失防護思考和作法也是一樣。 如果您的組織和使用者是資料遺失防護做法的新資料，則 DLP 採用可能需要變更您的商務程式，而且將為您的使用者提供文化的轉變。 不過，使用適當的規劃、測試及調整，您的 DLP 原則會保護您的機密專案，同時將任何潛在的業務程式中斷降到最低。

**DLP 的技術規劃**

請記住，DLP 為技術可以監視和保護靜態資料、使用中的資料，以及在 Microsoft 365 服務、Windows 10 裝置、內部部署檔案共用和內部部署 SharePoint 中的動作中的資料。 針對不同的位置、您想要監視和保護的資料類型，以及當原則相符時所採取的動作，都有一定的計畫含義。

**規劃 DLP 的商務程式**

DLP 原則可以封鎖禁止的活動，例如透過電子郵件不適當的敏感資訊共用。 當您規劃 DLP 原則時，您必須識別觸及機密專案的商務程式。 業務程式擁有人可協助您識別應允許的適當使用者行為，以及應保護的使用者行為不當。 您應該規劃您的原則，並以測試模式進行部署，並先評估其對 [活動瀏覽器](data-classification-activity-explorer.md) 的影響，再將其套用至更嚴格的模式。

**DLP 的組織文化環境規劃**

成功的 DLP 執行相當於讓您的使用者訓練有素並 acclimated 資料遺失防護做法，因為這是一項完善的規劃和調整原則。 由於您的使用者非常介入，因此請務必規劃訓練。 您可以在將原則強制從測試模式變更為限制性更高的模式之前，以策略性方式使用原則提示來提升使用者的知名度。

<!--For more information on planning for DLP, including suggestions for deployment based on your needs and resources, see [Planning for Microsoft 365 data loss prevention](dlp-plan-for-dlp.md).-->

### <a name="prepare-for-dlp"></a>準備 DLP

您可以將 DLP 原則套用到靜態資料、使用中的資料，以及位置中的動作資料，例如：

- Exchange Online 電子郵件
- SharePoint Online 網站
- OneDrive 帳戶
- Teams 聊天和頻道訊息
- Microsoft Cloud App Security
- Windows 10 裝置
- 內部部署存放庫

每個必備項都有不同的必要條件。 某些位置的機密專案（例如 Exchange 線上）可以透過在 DLP 傘底下進行，只需設定套用至這些專案的原則。 其他如內部部署檔案存放庫需要部署 Azure 資訊保護 (AIP) 掃描器。 在啟動任何封鎖動作之前，您需要準備您的環境、程式碼草稿原則，並加以徹底測試。

### <a name="deploy-your-policies-in-production"></a>在生產環境中部署原則

#### <a name="design-your-policies"></a>設計您的原則

請先定義您的控制目標，以及它們如何套用各個不同的工作負載。 起草包含您目標的原則。 您可以隨時從一個工作負載開始，也可以跨所有工作負載開始-尚無影響。

#### <a name="implement-policy-in-test-mode"></a>在測試模式中實施原則

在測試模式中以 DLP 原則實施，以評估控制措施的影響。 [！注意事項] 您可以將原則套用至測試模式中的所有工作負載，這樣您就可以取得完整的結果，但是您可以在需要時從一個工作負載開始。

#### <a name="monitor-outcomes-and-fine-tune-the-policy"></a>監視結果和微調原則

在測試模式中，監控原則的結果並微調它，使其符合您的控制目標，同時確保您不會對有效的使用者工作流程和生產力造成不良或不慎影響。 以下是一些需要微調的範例：

- 調整範圍內或範圍之外的位置和人員/位置
- 調整用於判斷專案及其執行專案與原則相符時所用的條件和例外狀況
- 敏感資訊定義/秒
- 的動作
- 限制層級
- 新增控制項
- 新增人員
- 新增受限制的應用程式
- 新增受限制的網站

#### <a name="enable-the-control-and-tune-your-policies"></a>啟用控制項並調整原則

一旦原則符合您的所有目標，請將其開啟。 繼續監視原則應用程式的結果，並視需要調整。 一般來說，原則會在開啟後的一小時內生效。

<!--See, LINK TO topic for SLAs for location specific  details-->

## <a name="dlp-policy-configuration-overview"></a>DLP 原則設定概述

您在建立和設定 DLP 原則方面具有彈性。 您可以從預先定義的範本開始，只需稍按幾下即可建立原則，或自行設計。 不論選擇哪一個，所有 DLP 原則都需要您所需的資訊。

1. **選擇您要監視** 的專案 Microsoft 365 隨附許多預先定義的原則範本，以協助您開始使用，也可以建立自訂原則。
    - 預先定義的原則範本：金融資料、醫療和健康情況資料、各種國家和地區的隱私權資料。
    - 使用可用的敏感資訊類型、保留標籤和敏感度標籤的自訂原則。
2. **選擇您要監視的位置** -您可以選擇一個或多個您想要 DLP 監控機密資訊的位置。 您可以監視：

位置 | 包含/排除依據|
|---------|---------|
|Exchange 電子郵件| 通訊群組|
|SharePoint 網站 |網站 |
|OneDrive 帳戶 |帳戶或通訊群組 |
|Teams 聊天和頻道訊息 |帳戶 |
|Windows 10 裝置 |使用者或群組 |
|Microsoft Cloud App Security |執行個體 |
|內部部署存放庫| 存放庫檔路徑|

3. **選擇要套用至專案的原則必須符合的條件** -您可以接受預先設定的條件或定義自訂條件。 部分範例如下：

- 專案包含在特定內容中所使用的機密資訊的指定類型。 例如，95社會保險號碼會以電子郵件傳送給組織外部的收件者。
- 專案具有指定的敏感度標籤
- 具有敏感資訊的專案會在內部或外部共用

4. **選擇符合原則條件時要採取的動作** -動作取決於發生活動的位置。  部分範例如下：

- SharePoint/Exchange/OneDrive：封鎖位於組織表單以外存取內容的人員。 向使用者顯示提示，並傳送電子郵件通知，告知他們採取的是 DLP 原則所禁止的動作。
- Teams聊天室及通道：封鎖在聊天或頻道中共用的敏感資訊
- Windows 10裝置：審核或限制將敏感專案複製到可拆卸的 USB 裝置
- Office應用程式：顯示快顯視窗，通知使用者他們正在進入危險的行為和封鎖或封鎖，但允許覆寫。
- 內部部署檔案共用：將檔案從儲存位置移至隔離資料夾

> [!NOTE]
> 條件和要採取的動作是定義在稱為規則的物件中。

<!--## Create a DLP policy

All DLP policies are created and maintained in the Microsoft 365 Compliance center. See, INSERT LINK TO ARTICLE THAT WILL START WALKING THEM THROUGH THE POLICY CREATION PROCEDURES for more information.-->

在規範中心建立 DLP 原則之後，它會儲存在中央原則存放區中，然後再同步處理至各種內容來源，包括：

- Exchange Online，再從這裡到 Outlook 網頁版和 Outlook。
- 商務用 OneDrive 網站。
- SharePoint Online 網站。
- Office 桌上型電腦程式 (Excel、PowerPoint 及 Word)。
- Microsoft Teams 頻道和聊天訊息。

原則同步處理至正確的位置之後，會開始評估內容並強制執行動作。

## <a name="viewing-policy-application-results"></a>查看原則應用程式結果

DLP 會將大量資訊從監控、原則比對和動作和使用者活動報告 Microsoft 365。 您必須使用該資訊並採取行動，以調整對機密專案所採取的原則及會審動作。 遙測會先處理[Microsoft 365 規範中心審核記錄](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log-in-the-compliance-center)檔，並將其方式用於不同的報表工具。 每個報告工具都有不同的用途。

### <a name="dlp-alerts-dashboard"></a>DLP 警示儀表板

當 DLP 對機密專案採取動作時，您可以透過可設定的警示通知該動作。 「規範中心」可讓 [您在信箱](dlp-configure-view-alerts-policies.md)中進行鎖定，而不是讓您在信箱中進行這些警示。 使用 [DLP 警示] 儀表板來設定警示、進行審閱、會審及追蹤 DLP 警示的解決方法。 以下是從 Windows 10 裝置中的原則相符和活動所產生之警示的範例。

> [!div class="mx-imgBorder"]
> ![警示資訊](../media/Alert-info-1.png)

您還可以在同一個儀表板中檢視具有豐富中繼資料的關聯事件的詳細資訊

> [!div class="mx-imgBorder"]
> ![事件資訊](../media/Event-info-1.png)

### <a name="reports"></a>報表

[DLP 報告](view-the-dlp-reports.md#view-the-reports-for-data-loss-prevention)會顯示隨時間的廣泛趨勢，並提供下列專案的特定見解：

- **DLP 原則符合** 時間，並依日期範圍、位置、原則或動作進行篩選
- **DLP 事件** 比對會隨著時間而顯示相符專案，但會在專案上轉動，而不是原則規則。
- **DLP false 正值和 overrides** 會顯示誤報計數，以及設定後的使用者覆寫（如果已設定）和使用者的理由。

### <a name="dlp-activity-explorer"></a>DLP 活動瀏覽器

DLP 頁面上的 [活動流覽] 索引標籤會將 *活動* 篩選器預先設定為 *DLPRuleMatch*。 使用此工具可查看與包含機密資訊或已套用標籤之內容相關的活動，例如變更的標籤、檔已修改，以及符合規則。

![DLPRuleMatch 範圍的活動瀏覽器的螢幕擷取畫面](../media/dlp-activity-explorer.png)

如需詳細資訊，請參閱 [活動瀏覽器快速入門](data-classification-activity-explorer.md)

若要深入瞭解 Microsoft 365 DLP，請參閱：

- [深入瞭解 Microsoft 365 端點資料外洩防護](endpoint-dlp-learn-about.md)
- [了解 Microsoft Teams 中的預設資料外洩防護原則 (預覽)](dlp-teams-default-policy.md)
- [深入了解 Microsoft 365 資料外洩防護內部部署掃描器 (預覽)](dlp-on-premises-scanner-learn.md)
- [了解 Microsoft 合規性擴充功能 (預覽)](dlp-chrome-learn-about.md)
- [了解資料外洩防護警示儀表板](dlp-alerts-dashboard-learn.md)

若要瞭解如何使用資料遺失防護來遵守資料隱私權規定，請參閱使用 Microsoft 365 (aka.ms/m365dataprivacy) [部署資料隱私權法規的資訊保護](../solutions/information-protection-deploy.md)。
