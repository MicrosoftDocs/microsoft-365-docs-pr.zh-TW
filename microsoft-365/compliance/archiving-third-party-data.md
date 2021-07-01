---
title: 封存第三方資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何從社交媒體平臺、立即訊息平臺及檔共同作業平臺匯入協力廠商資料，以 Microsoft 365 信箱。
ms.openlocfilehash: 6c15da7c21382f6ef286ec493ea3d696c02761f4
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227460"
---
# <a name="archive-third-party-data-in-microsoft-365"></a>在 Microsoft 365 中封存協力廠商資料

Microsoft 365 可讓系統管理員使用資料連線器，將協力廠商資料從社交媒體平臺、立即訊息平臺及檔共同作業平臺，匯入到您 Microsoft 365 組織中的信箱。 在 Microsoft 365 中，使用資料連線器匯入及封存協力廠商資料的主要好處是，您可以在匯入後，對其套用各種 Microsoft 365 規範解決方案。 這可協助您確保組織的非 Microsoft 資料符合影響組織的規章和標準。

## <a name="third-party-data-connectors"></a>協力廠商資料連接器

Microsoft 365 合規性中心提供來自 Microsoft 的原生協力廠商資料連線器，以從各種資料來源（如 LinkedIn、立即 Bloomberg 及 Twitter 及支援有問必答風險管理解決方案的資料連線器）匯入資料。 除了這些資料連線器之外，Microsoft 也可與下列協力廠商合作，以在 Microsoft 365 合規性中心中提供更多第三部分的資料連線器。 您的組織可以與這些夥伴合作，在 Microsoft 365 合規性中心中建立對應的資料連線器之前，先設定其封存服務。

- [Software](#veritas-data-connectors)

- [TeleMessage](#telemessage-data-connectors)

- [17a-4 LLC](#17a-4-data-connectors)

- [CellTrust](#celltrust-data-connectors)

在下一節中所列的協力廠商資料 (，除了用於 Microsoft 365 內部使用者風險管理解決方案) 的 HR 資料和實際聲譽徽章授予資料，也會匯入至使用者信箱。 支援協力廠商資料的 Microsoft 365 規範解決方案會套用至儲存資料的使用者信箱。

### <a name="microsoft-data-connectors"></a>Microsoft 資料連接器

下表列出 Microsoft 365 合規性中心中可用的原生協力廠商資料連線器。 在 Microsoft 365 中匯入及封存協力廠商資料後，表格也會摘要您可以套用的相容性解決方案。 請參閱 [支援協力廠商資料的相容性解決方案](#overview-of-compliance-solutions-that-support-third-party-data) 一節，以取得每個規範解決方案的詳細說明，以及它如何支援協力廠商資料。

按一下 **協力廠商資料** 欄中的連結，以取得針對該資料類型建立連接器的逐步指示。

|協力廠商資料  |訴訟暫止|電子文件探索  |保留設定  |記錄管理  |通訊合規性  |內部風險管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Bloomberg Message](archive-bloomberg-message-data.md)     |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|||
|[人力資源 (人力資源) ](import-hr-data.md) ||||||![核取記號](../media/checkmark.png)
|[ICE Chat](archive-icechat-data.md)     |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|||
|[實體聲譽徽章授予](import-physical-badging-data.md) ||||||![核取記號](../media/checkmark.png)|
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|||
||||||||

### <a name="veritas-data-connectors"></a>Veritas 資料連線器

本節中的表格列出與 Veritas 合作關係中可用的協力廠商資料連線器。 在 Microsoft 365 中匯入及封存後，該表也會摘要說明您可以套用至協力廠商資料的相容性解決方案。 請參閱 [支援協力廠商資料的相容性解決方案](#overview-of-compliance-solutions-that-support-third-party-data) 一節，以取得每個規範解決方案的詳細說明，以及它如何支援協力廠商資料。

在 Microsoft 365 中封存協力廠商資料之前，您必須與 Veritas 合作，為組織設定稱為 *Merge1*) 的封存服務 (。 如需詳細資訊，請按一下 **協力廠商資料** 欄中的連結，以取得針對該資料類型建立連接器的逐步指示。

|協力廠商資料  |訴訟暫止|電子文件探索  |保留設定  |記錄管理  |通訊合規性  |內部風險管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust](archive-celltrust-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[MS SQL 上的 Cisco Jabber](archive-ciscojabberonmssql-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Oracle 上的 Cisco Jabber](archive-ciscojabberonoracle-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[PostgreSQL 上的 Cisco Jabbe](archive-ciscojabberonpostgresql-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[EML](archive-eml-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|||
|[FX Connect](archive-fxconnect-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Jive](archive-jive-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[MS SQL 資料庫](archive-mssqldatabaseimporter-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|||
|[樞紐](archive-pivot-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Redtail Speak](archive-redtailspeak-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Reuters Dealing](archive-reutersdealing-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Reuters Eikon](archive-reuterseikon-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Reuters FX](archive-reutersfx-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Salesforce Chatter](archive-salesforcechatter-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|||
|[ServiceNow](archive-servicenow-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|||
|[Slack eDiscovery](archive-slack-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Symphony](archive-symphony-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[文字分隔](archive-text-delimited-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|||
|[Webex Teams](archive-webexteams-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[網頁](archive-webpagecapture-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|||
|[Facebook Workplace](archive-workplacefromfacebook-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[XIP](archive-xip-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[XSLT/XML](archive-xslt-xml-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|||
|[Yieldbroker](archive-yieldbroker-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Zoom Meetings](archive-zoommeetings-data.md)     |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
||||||||

### <a name="telemessage-data-connectors"></a>TeleMessage 資料連接器

本節中的表格列出與 TeleMessage 合作的協力廠商資料連線器。 在 Microsoft 365 中匯入及封存後，該表也會摘要說明您可以套用至協力廠商資料的相容性解決方案。 請參閱 [支援協力廠商資料的相容性解決方案](#overview-of-compliance-solutions-that-support-third-party-data) 一節，以取得每個規範解決方案的詳細說明，以及它如何支援協力廠商資料。

在 Microsoft 365 中封存協力廠商資料之前，您必須使用 TeleMessage 來為您的組織設定其封存服務。 如需詳細資訊，請按一下 **協力廠商資料** 欄中的連結，以取得針對該資料類型建立連接器的逐步指示。

TeleMessage 資料連線器也可在 Microsoft 365 美國政府雲端的 GCC 環境中取得。 如需詳細資訊，請參閱本文的美國政府雲端區段中的資料連線器。

|協力廠商資料  |訴訟暫止|電子文件探索  |保留設定  |記錄管理  |通訊合規性  |內部風險管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android](archive-android-archiver-data.md)     |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[&T 網路](archive-att-network-archiver-data.md)     |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Bell Network](archive-bell-network-data.md)     |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[企業編號](archive-enterprise-number-data.md)     |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[O2 Network](archive-o2-network-data.md)     |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[TELUS Network](archive-telus-network-data.md)    |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Verizon Network](archive-verizon-network-data.md)     |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[WeChat](archive-wechat-data.md)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[WhatsApp](archive-whatsapp-data.md)     |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
||||||||

### <a name="17a-4-data-connectors"></a>17a-4 資料連接器

本節中的表格列出與 17a-4 LLC 合作的協力廠商資料連線器。 在 Microsoft 365 中匯入及封存後，該表也會摘要說明您可以套用至協力廠商資料的相容性解決方案。 請參閱 [支援協力廠商資料的相容性解決方案](#overview-of-compliance-solutions-that-support-third-party-data) 一節，以取得每個規範解決方案的詳細說明，以及它如何支援協力廠商資料。

在 Microsoft 365 中封存協力廠商資料之前，您必須與 Veritas 合作，為組織設定稱為 *DataParser*) 的封存服務 (。 如需詳細資訊，請按一下 **協力廠商資料** 欄中的連結，以取得針對該資料類型建立連接器的逐步指示。

|協力廠商資料  |訴訟暫止|電子文件探索  |保留設定  |記錄管理  |通訊合規性  |內部風險管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[BlackBerry](archive-17a-4-blackberry-data.md)     |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[彭博](archive-17a-4-bloomberg-data.md)     |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Cisco Jabber](archive-17a-4-cisco-jabber-data.md)   |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Cisco Webex](archive-17a-4-webex-teams-data.md)   |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[FactSet](archive-17a-4-factset-data.md)    |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[引 信](archive-17a-4-fuze-data.md)    |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[FX Connect](archive-17a-4-fxconnect-data.md)    |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[ICE Chat](archive-17a-4-ice-im-data.md)    |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[InvestEdge](archive-17a-4-investedge-data.md)    |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[LivePerson 會話雲端](archive-17a-4-liveperson-data.md)    |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[妙語](archive-17a-4-quip-data.md)    |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Refinitiv Eikon Messenger](archive-17a-4-refinitiv-messenger-data.md)    |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[ServiceNow](archive-17a-4-servicenow-data.md)    |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Slack](archive-17a-4-slack-data.md)    |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[SQL](archive-17a-4-sql-database-data.md)    |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Symphony](archive-17a-4-symphony-data.md)    |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
|[Zoom](archive-17a-4-zoom-data.md)    |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
||||||||

### <a name="celltrust-data-connectors"></a>CellTrust 資料連線器

本節中的表格列出與 CellTrust 合作關係中的協力廠商資料連線器。 在 Microsoft 365 中匯入及封存後，該表也會摘要說明您可以套用至協力廠商資料的相容性解決方案。 請參閱 [支援協力廠商資料的相容性解決方案](#overview-of-compliance-solutions-that-support-third-party-data) 一節，以取得每個規範解決方案的詳細說明，以及它如何支援協力廠商資料。

在 Microsoft 365 中封存協力廠商資料之前，您必須使用 CellTrust，為您的組織設定稱為 *CellTrust SL2*) 的封存服務 (。 如需詳細資訊，請按一下 **協力廠商資料** 欄中的連結，以移至建立 CellTrust SL2 connector 的逐步指示。

|協力廠商資料  |訴訟暫止|電子文件探索  |保留設定  |記錄管理  |通訊合規性  |內部風險管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust SL2](archive-data-from-celltrustsl2.md)     |![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)|![核取記號](../media/checkmark.png)||
||||||||

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>支援協力廠商資料的相容性解決方案

下列各節說明 Microsoft 365 規範解決方案可協助您管理上表所列之協力廠商資料的一些事項。

### <a name="litigation-hold"></a>訴訟暫止

您在使用者信箱上進行 [訴訟暫](create-a-litigation-hold.md) 止，以保留協力廠商資料。 當您建立保留時，您可以指定保留期間 (也稱為以 *時間為基礎的保留*) ，如此一來，刪除及修改的協力廠商資料會保留指定的期間，然後從信箱中永久刪除。 或者，您可以只保留未 (稱為 *無限期保留*) 或移除訴訟暫止的內容。

### <a name="ediscovery"></a>電子文件探索

Microsoft 365 中的三個主要 eDiscovery 工具組括內容搜尋、核心 eDiscovery 和 Advanced eDiscovery。

- **[內容搜尋](content-search.md)。** 您可以使用內容搜尋工具，針對您匯入的協力廠商資料搜尋信箱。 您可以使用搜尋查詢和條件來縮小搜尋結果，以及匯出搜尋結果。

- **[核心 eDiscovery](get-started-core-ediscovery.md)。** 此工具是在基本搜尋和匯出功能上建立的，可讓您建立用來控制誰可以存取案例資料的案例、保留使用者信箱或符合搜尋準則的信箱內容。 這表示您可以在匯入至使用者信箱的協力廠商資料上放置 eDiscovery 暫止功能。

- **[Advanced eDiscovery](overview-ediscovery-20.md)。** 這項強大的工具可讓您將保管人新增至案例、將保管人的資料置於保留狀態，然後將系統管理員的協力廠商資料載入至評審，以進行進一步分析，例如主題和重複偵測，以擴充核心 eDiscovery 的案例功能。 將協力廠商資料載入到審閱集中之後，您可以查詢並篩選為窄的結果集。

   核心 eDiscovery 和 Advanced eDiscovery 可讓您管理可能與組織法律或內部調查相關的協力廠商資料。

### <a name="retention-settings"></a>保留設定

您可以將 [保留原則](retention.md) 套用至使用者信箱以保留，然後刪除協力廠商資料 (和其他信箱內容) 保留期限到期之後。 您也可以使用保留原則來刪除某段時間內的協力廠商資料，或 [使用保留標籤](disposition.md) ，當協力廠商資料的保留期間到期時，就會觸發處置檢查。

### <a name="records-management"></a>記錄管理

Microsoft 365 中的[記錄管理](records-management.md)功能可讓您將協力廠商資料宣告為記錄。 這可由套用保留標籤的使用者手動完成，以將信箱中的協力廠商資料標示為記錄。 或者，您可以在協力廠商資料中識別敏感資訊、關鍵字或內容類型，以自動套用保留標籤。

### <a name="communication-compliance"></a>通訊合規性

您可以使用 [通訊相容性](communication-compliance.md) 來檢查協力廠商資料，以確保其符合您組織的資料標準。 您可以為組織中的不適當郵件偵測、捕獲和採取修正動作，以執行此動作。 例如，您可以監視針對冒犯性語言、機密資訊和規章遵循所匯入的協力廠商資料。

### <a name="insider-risk-management"></a>內部風險管理

來自協力廠商資料（如選擇性 HR 資料）的信號可供「 [有問必答風險管理](insider-risk-management.md) 」解決方案使用，以在組織中偵測、調查與處理危險的活動，以盡可能降低內部風險。 例如，HR 資料連線器匯入的資料會用作風險標記，以協助偵測盜竊員工資料竊取。

## <a name="data-connectors-in-the-us-government-cloud"></a>美國政府雲端中的資料連線器

如先前所述，TeleMessage 提供的資料連線器可于美國政府雲端取得。 下表指出支援每個 TeleMessage 資料連線器的特定政府環境。 如需有關美國政府雲端的詳細資訊，請參閱[Microsoft 365 us 政府](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/microsoft-365-government-how-to-buy)。

|TeleMessage 資料連線器  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|Android 封存工具 | 是 | 否 | 否 |
|AT&T SMS/MMS 網路封存工具 | 是 | 否 | 否 |
|Bell SMS/MMS 網路封存工具 | 是 | 否 | 否 |
|企業編號封存工具 | 是 | 否 | 否 |
|O2 SMS 和語音網路歸檔器 | 是         | 否 | 否 |
|TELUS SMS 網路存檔器 | 是 | 否 | 否 |
|Verizon SMS/MMS 網路封存工具 | 是 | 否 | 否 |
|WhatsApp 保存程式 | 是 | 否 | 否 |
|||||

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>使用 Microsoft 合作夥伴封存協力廠商資料

匯入及封存協力廠商資料的另一個選擇是讓您的組織與 Microsoft 合作夥伴搭配使用。 如果 Microsoft 規範中心中提供的資料連線器不支援協力廠商資料型別，您可以使用可提供自訂連接器的合作夥伴，以便定期從協力廠商資料來源提取專案，然後以協力廠商 API 連線至 Microsoft 雲端，然後將這些專案匯入至 Microsoft 365。 夥伴連接器也會將專案的內容從協力廠商資料來源轉換成電子郵件，然後將其匯入 Microsoft 365 中的信箱。

如需您可以使用的合作夥伴清單及此方法的逐步程式，請參閱[在 Microsoft 365 中封存協力廠商資料](work-with-partner-to-archive-third-party-data.md)的合作。
