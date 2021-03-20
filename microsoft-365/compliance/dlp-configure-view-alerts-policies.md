---
title: 設定和檢視 DLP 原則的警示 (預覽)
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
description: 瞭解如何定義及管理 DLP 原則的警示。
ms.openlocfilehash: 0594cee5208049aef16dee6fa03954faae2a1cdd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917859"
---
# <a name="configure-and-view-alerts-for-dlp-polices-preview"></a>設定及查看 DLP 原則的警示 (預覽) 

本文說明如何定義與資料遺失防護 (DLP) 原則相關聯的各種警示原則。 您將會瞭解如何使用 [Microsoft 365 相容性中心](https://compliance.microsoft.com/) 的新 DLP 警示管理儀表板來查看警示、事件，以及與 DLP 原則違規相關聯的中繼資料。

## <a name="features"></a>功能

以下是此預覽的一部分功能：

-   **DLP 警示管理儀表板**：在 [Microsoft 365 規範中心](https://compliance.microsoft.com/)內，此儀表板會顯示在下列工作負載中強制執行之 DLP 原則的警示：

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   裝置
-   **高級警示設定選項**：這些選項是 DLP 原則撰寫流程的一部分。 使用它們來建立豐富的警示設定。 您可以根據事件數目或洩漏的資料大小，來建立單一事件警示或匯總警示。

## <a name="before-you-begin"></a>開始之前

開始之前，請確定您具備必要的必要條件：

-   DLP 警示管理儀表板的授權
-   警示設定選項的授權
-   角色

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>DLP 警示管理儀表板的授權

Office 365 DLP 所有合格租使用者皆可存取新的 DLP 警示管理儀表板。 若要開始，您應該具備適用于 Exchange Online、SharePoint 線上和商務 OneDrive 的 Office 365 DLP。 如需有關 Office 365 DLP 授權需求的詳細資訊，請參閱 [哪些授權可為使用者提供從服務受益的許可權？](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)。

參與 [端點 dlp](./endpoint-dlp-learn-about.md?view=o365-worldwide) 公開預覽或具備 [團隊 dlp](./dlp-microsoft-teams.md?view=o365-worldwide) 資格之使用者的客戶，將會看到其 Endpoint Dlp 原則警示和團隊 dlp 警示管理儀表板中的「dlp 原則警示」。

### <a name="licensing-for-alert-configuration-options"></a>警示設定選項的授權

-   **單一事件警示** 設定：具有 E1、F1 或 G1 訂閱或 E3 或 G3 訂閱的組織，只會建立在每次發生活動時觸發警示的警示原則。
-   **匯總的警示** 設定：若要根據臨界值來設定匯總警示原則，您必須具有下列任一設定：
    -   E5 或 G5 訂閱
    -   具有下列其中一項功能的 E1、F1 或 G1 訂閱或 E3 或 G3 訂閱：
        -   Office 365 進階威脅防護方案 2
        -   Microsoft 365 E5 合規性
        -   Microsoft 365 電子檔探索和審核附加元件授權

### <a name="roles"></a>角色

如果您想要查看 DLP 警示管理儀表板，或編輯 DLP 原則中的警示設定選項，您必須是下列其中一個角色群組的成員：

-   合規性系統管理員
-   合規性資料系統管理員
-   安全性系統管理員
-   安全性操作員
-   安全性讀取者

若要存取 DLP 警示管理儀表板，您需要「管理警示」角色及下列其中一個角色：

-   DLP 合規性管理
-   僅限檢視 DLP 合規性管理

## <a name="alert-configuration-experience"></a>警示設定經驗

如果您符合匯總的 [警示設定選項](#licensing-for-alert-configuration-options)，您可以在 DLP 原則製作體驗中看到下列內嵌選項。

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="螢幕擷取畫面顯示適用于已匯總警示設定選項之使用者的附隨報告選項。" border="false":::

您可以使用這些警示設定選項，設定定義在觸發警示之前可以進行 DLP 規則相符的頻率。 這項設定可讓您設定原則，以在每次活動符合原則條件時或超過特定臨界值時，根據活動數量或根據挾帶資料量的數量來產生警示。

如果您符合 [單一事件警示設定選項](#licensing-for-alert-configuration-options)，則會在 DLP 原則製作體驗中看到下列警示設定選項。 使用此選項，可建立每當 DLP 規則比對使用者活動發生時，每次都會引發的警示。

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="螢幕擷取畫面顯示適用于單一事件警示設定選項的使用者附隨報告選項。" border="false":::

## <a name="dlp-alert-management-dashboard"></a>DLP 警示管理儀表板

若要使用 DLP 警示管理儀表板：

1.  在 [Microsoft 365 規範中心](https://www.compliance.microsoft.com)內，移至 [ **資料遺失防護**]。

2.  選取 [ **警示** ] 索引標籤，以查看 [DLP 警示] 儀表板。

    -   選擇 [篩選] 以精煉警示清單。 選擇 [ **自訂欄位** ]，列出您要查看的屬性。 您也可以選擇在任何欄中，以遞增或遞減順序排序警示。
    -   選取警示以查看詳細資料：

        :::image type="content" source="../media/alert-details.png" alt-text="螢幕擷取畫面顯示 DLP 警示管理儀表板上的警示詳細資料。" border="false":::

1.  選取 [ **事件** ] 索引標籤，以查看與警示相關聯的所有事件。 您可以選擇特定的事件來查看其詳細資料。
    下表顯示一些事件的詳細資料。
    
    | 類別          | 屬性名稱                 | 描述                                                                | 適用的事件種類                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*事件詳細資料*||
    |      | 識別碼                            | 與事件相關聯的唯一識別碼                                        | 所有事件                               |
    |                   | 位置                      | 偵測到事件的工作負載                                      | 所有事件                               |
    |                   | 啟用時間              | 導致 DLP 違規之使用者活動的時間                    | 所有事件                               |
    |*受影響實體*||
    |  | 使用者                          | 導致 DLP 違規的使用者                                          | 所有事件                               |
    |                   | 主機名稱                      | 偵測到 DLP 侵犯之機器的主機名稱              | 裝置事件                           |
    |                   | IP 位址                    | 電腦的 IP 位址                                                  | 裝置事件                           |
    |                   | 檔案路徑                     | 與非法相關之檔案的絕對路徑                        | SharePoint、OneDrive 和裝置事件 |
    |                   | 電子郵件收件者              | 違反 DLP 原則的電子郵件收件者                       | Exchange 事件                          |
    |                   | 電子郵件主旨                 | 違反 DLP 原則的電子郵件主題                          | Exchange 事件                          |
    |                   | 電子郵件附件             | 違反 DLP 原則之電子郵件中的附件名稱         | Exchange 事件                          |
    |                   | 網站擁有人                    | 網站擁有者的名稱                                                     | SharePoint 和 OneDrive 事件           |
    |                   | 網站 URL                      | SharePoint 或 OneDrive 網站的完整 URL                                | SharePoint 和 OneDrive 事件           |
    |                   | 已建立檔案                  | 檔建立時間                                                      | SharePoint 和 OneDrive 事件           |
    |                   | 上次修改的檔案            | 上次修改檔案的時間                                  | SharePoint 和 OneDrive 事件           |
    |                   | 檔案大小                     | 檔案大小                                                           | SharePoint 和 OneDrive 事件           |
    |                   | 檔案擁有者                    | 檔案擁有者                                                          | SharePoint 和 OneDrive 事件           |
    |*原則詳細資料*||
    |     | 符合的 DLP 原則            | 符合的 DLP 原則名稱                                    | 所有事件                               |
    |                   | 符合規則                  | 已符合之 DLP 原則中的 DLP 規則名稱                    | 所有事件                               |
    |                   | 偵測到敏感資訊類型 | 以 DLP 原則的一部分偵測到的敏感資訊類型 | 所有事件                               |
    |                   | 採取的動作                 | 做為符合的 DLP 原則的一部分採取的動作                          | 所有事件                               |
    |                   | 使用者 overrode 原則          | 使用者是否透過原則提示來 overrode 原則                | 所有事件                               |
    |                   | 覆寫對齊文字   | 提供以覆寫原則提示的理由                          | 所有事件                               |
    
1.  選取 [ **敏感資訊類型** ] 索引標籤，以查看內容中偵測到的敏感資訊類型的詳細資料。 詳細資料包括自信和計數。

2.  調查警示之後，請選擇 [ **管理警示** **]，以變更狀態 (使用** 中、 **調查**、 **消除** 或 **解決**) 。 您也可以新增批註，並將提醒指派給組織中的某人。

    -   若要查看工作流程管理的史，請選擇 [ **記錄管理**]。
    -   針對警示採取必要的動作後，請將警示的狀態設定為 [ **已解決**]。