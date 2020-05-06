---
title: 封存第三方資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何將「社交媒體平臺」、「立即訊息平臺」及「檔共同作業平臺」的協力廠商資料匯入至 Microsoft 365 信箱。
ms.openlocfilehash: 0db7019b607388b7c62fe19210b85b8410083f32
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035481"
---
# <a name="archive-third-party-data"></a>封存第三方資料

Microsoft 365 可讓系統管理員從社交媒體平臺、立即訊息平臺及檔共同作業平臺，將協力廠商資料匯入並封存至您的 Microsoft 365 組織中的信箱。 您可以匯入 Microsoft 365 的協力廠商資料來源範例包含下列服務： 
  
- **社交：** Facebook、LinkedIn、Twitter 和 Yammer

- **立即訊息：** Yahoo Messenger 和 GoogleTalk

- **檔**共同作業：Box 及 DropBox

- **垂直行業：** 客戶關係管理（例如 Salesforce 交談）和金融服務（例如 Bloomberg 和 Thomson Reuters）

- **短信/文字訊息：** BlackBerry

匯入協力廠商資料後，您可以將 Microsoft 365 規範功能（例如訴訟暫止、eDiscovery、In-Place 封存、審核、通訊法規遵從性及保留原則）套用至此資料。 例如，當信箱處於訴訟暫止狀態時，會保留協力廠商資料。 您可以使用 Microsoft eDiscovery 工具來搜尋協力廠商資料。 或者，您可以將封存和保留原則套用至協力廠商資料，就像您可以使用 Microsoft 資料一樣。 簡而言之，封存 Microsoft 365 中的協力廠商資料可協助您的組織遵守政府和法規原則。

有兩種方法可匯入及封存 Microsoft 365 中的協力廠商資料：

- **在安全性 & 規範中心使用協力廠商資料連線器：** 使用 Microsoft 365 規範中心提供的自訂資料連線器。 在您設定及設定連接器之後，它會連線至協力廠商資料來源、將專案內容轉換為電子郵件訊息格式，然後將該專案匯入 Microsoft 365 中的信箱。 目前，您可以從 Facebook 商務頁面、公司 Twitter 帳戶、LinkedIn、立即 Bloomberg 及組織的人力資源（HR）資料中，執行連接器以匯入及封存資料。 如需設定這些連接器之一的逐步指示，請參閱：

   - **Facebook：** [使用連接器封存 Facebook 資料](archive-facebook-data-with-sample-connector.md)

   - **Twitter：** [使用連接器封存 Twitter 資料](archive-twitter-data-with-sample-connector.md)

   - **LinkedIn：** [設定連接器以封存 LinkedIn 資料](archive-linkedin-data.md)

   - **立即 Bloomberg：** [設定連接器以封存立即 Bloomberg 資料](archive-instant-bloomberg-data.md)

   - **人力資源資料：** [設定連接器以匯入 HR 資料](import-hr-data.md)

- **與 Microsoft Partner 搭配使用：** 您的組織與 Microsoft 合作夥伴合作，其提供自訂連接器，該連接器會設定為定期解壓縮協力廠商資料來源中的專案，然後以協力廠商 API 連線至 Microsoft 雲端，並將這些專案匯入 Microsoft 365。 夥伴連接器也會將專案的內容從協力廠商資料來源轉換成電子郵件，然後將其匯入 Microsoft 365 中的信箱。 如需您可以使用的合作夥伴清單及此方法的逐步程式，請參閱在[Microsoft 365 中封存協力廠商資料](work-with-partner-to-archive-third-party-data.md)的合作。
