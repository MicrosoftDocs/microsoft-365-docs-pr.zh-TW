---
title: 了解資料外洩防護警示儀表板
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
description: 深入瞭解資料遺失防護警示和警示儀表板。
ms.openlocfilehash: b6fd698e535e006149f6ce3a2a5bc57d0c92c7e2
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760702"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a>了解資料外洩防護警示儀表板

當資料遺失防護中的準則 (DLP) 原則與使用者對機密專案所採取的動作相符時，該原則就會產生警示。 這可能會產生大量的警示。 DLP 警示會收集于警示儀表板中。 [警示] 儀表板為您提供單一位置，可對原則相符的所有詳細資料執行深入調查。  

<!-- [Microsoft 365 compliance center](https://compliance.microsoft.com/)-->

## <a name="workloads"></a>工作負載

[dlp 警示管理儀表板](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)的[Microsoft 365 規範中心](https://compliance.microsoft.com/)] 顯示這些工作負載上 dlp 原則的警示：

- Exchange
- SharePoint
- OneDrive
- Teams
- Windows 10 裝置 

> [!TIP]
> 使用適用于[Teams DLP](dlp-microsoft-teams.md)之[endpoint dlp](endpoint-dlp-learn-about.md)的客戶，將會看到其 endpoint dlp 原則警示，並 Teams dlp 警示管理儀表板中的 dlp 原則警示。

## <a name="single-alert-and-aggregate-alert"></a>單一警示和匯總警示

您可以在 DLP 原則中設定兩種警示類型。

**單一事件警示** 一般用於監視低大量的高敏感度事件的原則，例如單一電子郵件，包含10個或更多用戶端在組織外傳送的信用卡號碼。

**匯總-事件警報** 一般用於監視在一段時間內的較高磁片區中發生之事件的原則。 例如，當10個個別電子郵件每個具有一個客戶信用卡號碼的電子郵件在您的組織超過48小時之後傳送時，就會觸發匯總警示。

## <a name="types-of-events"></a>事件種類

以下是與警示相關的一些事件。 在 UI 中，您可以選擇特定的事件來查看其詳細資料。 

### <a name="event-details"></a>事件詳細資料

|屬性名稱  |描述  |事件種類  |
|---------|---------|---------|
|ID |與事件相關聯的唯一識別碼 |所有事件 |
|位置 |偵測到事件的工作負載|所有事件 |
|啟用時間     |符合 DLP 原則之準則的使用者啟用時間 |

### <a name="impacted-entities"></a>受影響實體

|屬性名稱 |描述| 事件種類|
|---------|---------|---------|
|使用者 | 採取導致原則符合之動作的使用者 | 所有事件|
|主機 名 | 發生 DLP 原則比對之電腦的主機名稱 | 裝置事件|
|IP 位址 | 發生 DLP 原則比對之電腦的 IP 位址 | 裝置事件|
|sha1 |檔 SHA-1 雜湊 | 裝置事件|
|sha256 | 檔 SHA-256 雜湊 | 裝置事件|
|MDATP 裝置識別碼 | 端點裝置 MDATP 識別碼|
|檔案大小 | 檔案大小| SharePoint、OneDrive 和裝置事件|
|檔案路徑 | 與 DLP 原則相符相關之專案的絕對路徑 | SharePoint、OneDrive 和裝置事件|
|電子郵件收件者 |如果電子郵件是符合 DLP 原則的敏感專案，此欄位會包含該電子郵件的收件者。| Exchange 事件|
|電子郵件主題 |符合 DLP 原則的電子郵件主題 |Exchange 事件|
|電子郵件附件 | 符合 DLP 原則之電子郵件中的附件名稱| Exchange 事件|
|網站擁有者 |網站擁有者的名稱| SharePoint 和 OneDrive 事件|
|網站 URL |已發生 DLP 原則的 SharePoint 或 OneDrive 網站的完整 URL |SharePoint 和 OneDrive 事件|
|已建立檔 |建立符合 DLP 原則的檔案時的時間 |SharePoint 和 OneDrive 事件|
|上次修改的檔案 | 已變更符合 DLP 原則的檔案的最後時間 | SharePoint 和 OneDrive 事件|
|檔案大小 | 符合 DLP 原則的檔案大小 |SharePoint 和 OneDrive 事件|
|檔案擁有者 |符合 DLP 原則的檔案擁有者 |SharePoint 和 OneDrive 事件|  

### <a name="policy-details"></a>原則詳細資料

|屬性名稱 |描述 |事件種類 |
|---------|---------|---------|
|符合的 DLP 原則 |相符的 DLP 原則名稱 |所有事件|
|符合規則 |符合的 DLP 原則規則名稱 |所有事件|
|偵測到)  (SIT 的敏感資訊類型|以 DLP 原則相符的一部分偵測到的 |所有事件|
|採取的動作 |導致 DLP 原則相符所採取的動作| 所有事件|
|侵犯動作 | 引發 DLP 警示之端點裝置上的動作| 裝置事件 | 
|使用者 overrode 原則 |使用者已透過原則提示覆寫原則 | 所有事件|
|使用覆寫對齊 |使用者為覆寫所提供的原因文字 | 所有事件|   

## <a name="see-also"></a>另請參閱

- [開始使用資料外洩防護警示儀表板](dlp-alerts-dashboard-get-started.md)
- [從資料遺失防護開始的位置](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)