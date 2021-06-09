---
title: Microsoft 365Microsoft Graph 和 Delve 中的租使用者隔離
ms.author: robmazz
author: robmazz
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
description: 在本文中，將說明 Microsoft 365 租使用者隔離在 Office Graph 和 Delve 中的運作方式。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 966f02726a2cce18e30e4d5bc7ab0beb5db51a29
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332385"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Microsoft 365Microsoft Graph 和 Delve 中的租使用者隔離

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Microsoft Graph 中的租使用者隔離

[Microsoft Graph](https://developer.microsoft.com/graph)會在 Microsoft 365 服務中的活動模型，包括 Exchange Online、SharePoint 線上、Yammer、商務用 Skype、Azure Active Directory 等及外部服務，例如其他 Microsoft 服務或協力廠商服務。 Microsoft Graph 元件會在整個 Microsoft 365 中使用。 Microsoft Graph 代表內容和活動的集合，以及跨整個 Office 套件所發生的關聯。 它會使用複雜的機器學習技巧，將人員連接至相關的內容、交談和人員。 例如，SharePoint Online 中的承租人索引有用於服務 Delve 查詢的 Microsoft Graph 索引、SharePoint Online 中的 Analytics 處理引擎是用來儲存信號及計算真知灼見，Exchange Online 會將每一位使用者的收件者快取計算成租使用者分析的輸入。

[！附注] Microsoft Graph 包含企業物件的相關資訊，例如人員和檔，以及這些物件之間的關聯性與互動。 關係和互動會以 *邊* 來表示。 Microsoft Graph 是由租使用者所分割，這兩個邊界只能存在於相同租使用者之間的 *節點*。 *節點* 是具有統一資源識別項的實體 (URI) 、節點類型、存取控制清單，以及一組包含 *中繼資料* 和邊緣的層面。 每個節點都有相關聯的中繼資料和邊界，視常見知識模型中的 *小平面* 排列。 *中繼資料* 是儲存在節點上的命名屬性，可用於搜尋、篩選或分析 Microsoft Graph 內。 一個 *方面* 是中繼資料的邏輯集合及節點上的邊界。 每個層面都描述節點的一個方位。 

Microsoft Graph 不會將所有資料移到單一存放庫中;相反地，它會儲存位於其他位置之資料的中繼資料和關聯性。 Microsoft Graph 由數個數據儲存區和處理元件所組成：

- 租使用者 Graph 存放區提供大量儲存優化，以進行高效分析。
- 使用中內容快取可提供主動節點和邊緣的快速隨機存取，以促進使用者體驗。
- 輸入路由器會將租使用者圖表變更的內部和外部變更通知給元件。

每個工作負載內的分析都會推匯出與租使用者範圍的計算相關的真知灼見，並將其推送至租使用者圖表。 租用中所有活動的承租人分析原因，以產生行為模式的洞察力。 例如，Exchange Online 會針對每位使用者的信箱，計算每位使用者的收件者快取，以提高原因。 這些個別使用者分析會在每一位人員上產生一組 *RecipientCache 邊* ，進而會推入租使用者圖表。 這可讓分析處理盡可能盡可能接近來來源資料。

## <a name="tenant-isolation-in-delve"></a>Delve 中的租使用者隔離

如先前所述，Microsoft Graph 的功能體驗可協助使用者探索及共同處理其企業中目前的活動，並提供以實體為中心的平臺，以進行跨工作負載的內容和活動的分析，以及超過 Microsoft 365 的原因。 Delve 是 Microsoft Graph 所提供技術支援的第一種體驗。
Delve 是 Microsoft 365 網頁體驗，它會從 Microsoft 365 和 Yammer Enterprise 向 Microsoft 365 使用者透過 Microsoft Graph 來呈現內容。 網頁體驗顯示不同的板卡，每個板都有特定的主題，例如「 *我的趨勢分析* 」或「 *我已修改的* 資訊」。 每個電路板都是由多個檔卡片所組成，這些卡片會顯示檔中的摘要文字和圖片。 這張卡片可讓使用者做為開啟檔或檔 Yammer 頁面等動作。 Microsoft 365 承租人中每個人都有一個頁面，顯示此人員最相關的檔，以及可以叫用 Exchange Online 或商務用 Skype 以與該人員互動的圖示。 因為 Delve 是以 Microsoft Graph api 為基礎，所以它會受限於該 api 的承租人型隔離。