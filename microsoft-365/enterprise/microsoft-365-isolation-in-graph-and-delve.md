---
title: Microsoft Graph 和 Delve 中的 microsoft 365 租使用者隔離
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 在本文中，我們將尋找 Microsoft 365 租使用者隔離在 Office Graph 和 Delve 中的運作方式的說明。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab9b216656e076cc3ba02a4ef6c75b25b94547fe
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688587"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Microsoft Graph 和 Delve 中的 microsoft 365 租使用者隔離

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Microsoft Graph 中的租使用者隔離

Microsoft 365 服務中的 [Microsoft Graph](https://developer.microsoft.com/graph) 模型活動，包括 Exchange online、SharePoint Online、Yammer、商務用 Skype、Azure Active Directory 等等，以及外部服務（如其他 Microsoft 服務或協力廠商服務）中的活動。 Microsoft Graph 元件是用於整個 Microsoft 365。 Microsoft Graph 代表內容和活動的集合，以及跨整個 Office 套件所發生的關聯。 它會使用複雜的機器學習技巧，將人員連接至相關的內容、交談和人員。 例如，SharePoint Online 中的承租人索引具有 Microsoft Graph 索引，用來提供 Delve 查詢，則 SharePoint Online 中的 Analytics 處理引擎是用來儲存信號及計算洞察力，而 Exchange Online 會將每個使用者的收件者快取計算為租使用者分析的輸入。

Microsoft Graph 包含企業物件的相關資訊，例如人員和檔，以及這些物件之間的關聯性與互動。 關係和互動會以 *邊*來表示。 Microsoft Graph 是由租使用者所分割，這兩個邊界只能存在於相同租使用者之間的 *節點* 。 *節點*是具有統一資源識別項的實體 (URI) 、節點類型、存取控制清單，以及一組包含*中繼資料*和邊緣的層面。 每個節點都有相關聯的中繼資料和邊界，視常見知識模型中的 *小平面* 排列。 *中繼資料* 是儲存在節點上的命名屬性，可用於在 Microsoft Graph 內進行搜尋、篩選或分析。 一個 *方面* 是中繼資料的邏輯集合及節點上的邊界。 每個層面都描述節點的一個方位。 

Microsoft Graph 不會將所有資料移到單一存放庫中;相反地，它會儲存位於其他位置之資料的中繼資料和關聯性。 Microsoft Graph 由數個數據儲存區和處理元件所組成：

- 租使用者圖表存放區提供大量儲存優化，以進行高效分析。
- 使用中內容快取可提供主動節點和邊緣的快速隨機存取，以促進使用者體驗。
- 輸入路由器會將租使用者圖表變更的內部和外部變更通知給元件。

每個工作負載內的分析都會推匯出與租使用者範圍的計算相關的真知灼見，並將其推送至租使用者圖表。 租用中所有活動的承租人分析原因，以產生行為模式的洞察力。 例如，Exchange Online 會計算每位使用者的收件者快取，其可在每個使用者的信箱上有效地進行原因。 這些個別使用者分析會在每一位人員上產生一組 *RecipientCache 邊* ，進而會推入租使用者圖表。 這可讓分析處理盡可能盡可能接近來來源資料。

## <a name="tenant-isolation-in-delve"></a>Delve 中的租使用者隔離

如先前所述，Microsoft Graph 會幫您探索及共同處理企業中目前活動的經驗，並提供以實體為中心的平臺，以用於分析跨工作負載的內容和活動，以及超過 Microsoft 365 的原因。 Delve 是 Microsoft Graph 所提供的第一個此類經驗。
Delve 是 Microsoft 365 web 體驗，可透過 Microsoft Graph 將 Microsoft 365 和 Yammer Enterprise 的內容呈現給 Microsoft 365 使用者。 網頁體驗顯示不同的板卡，每個板都有特定的主題，例如「 *我的趨勢分析* 」或「 *我已修改的*資訊」。 每個電路板都是由多個檔卡片所組成，這些卡片會顯示檔中的摘要文字和圖片。 這張卡片可讓使用者做為開啟檔或檔的 Yammer 頁面等動作。 Microsoft 365 租使用者中的每個人都有一個頁面，顯示此人員最相關的檔，以及可呼叫 Exchange Online 或商務用 Skype 以與該人員互動的圖示。 因為 Delve 是以 Microsoft Graph API 為基礎，所以它會受限於該 API 的承租人型隔離。