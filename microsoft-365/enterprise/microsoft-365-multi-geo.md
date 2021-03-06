---
title: Microsoft 365 多地理位置
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: 我們將在本文中深入解釋如何使用 Microsoft 365 多地理位置，將 Microsoft 365 的目前狀態拓展至多個地理區域。
ms.openlocfilehash: 17fc2645f69a0d91c71c91718f321e5932d31bd2
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362759"
---
# <a name="microsoft-365-multi-geo"></a>Microsoft 365 多地理位置

使用 Microsoft 365 多地理位置，貴組織可以將 Microsoft 365 目前狀態拓展至您現有租用戶中的多個地理區域及/或國家。請連絡 Microsoft 帳戶小組以註冊 Microsoft 365 多地理位置的多國公司。
  
您可以使用 Microsoft 365 多地理位置，在您所選擇的地理位置佈建和儲存待用資料以符合資料落地要求，同時將現代化生產力體驗逐步拓展至您的員工。

如需 Microsoft 365 多地理位置的影片簡介，請參閱 [SharePoint Online 和 OneDrive 多地理位置，以控制資料存放處](https://www.youtube.com/watch?v=Do9U3JuROhk)。

## <a name="multi-geo-architecture"></a>多個地理位置架構

在適用多個地理位置中，Microsoft 365 租用戶包含中央位置 (即原始佈建 Microsoft 365 訂閱之處) 以及一或多個衛星位置。在多地理位置租用戶中，系統會在 Azure Active Directory (Azure AD) 中主控地理位置、群組和使用者資訊的相關資訊。因為您的租用戶資訊是集中管理且同步處理到每個地理位置，包含公司任何人的共用與體驗都會包含全域意識。

![SharePoint 系統管理中心內多地理位置地圖的螢幕擷取畫面](../media/multi-geo-world-map.png)

請注意，Microsoft 365 多地理位置不是為效能最佳化優化而設計，其主要設計目的在滿足資料落地要求。 如需 Microsoft 365 效能最佳化的詳細資訊，請參閱 [Microsoft 365 的網路規劃與效能調整](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848)或連絡客戶支援小組。

## <a name="terminology"></a>術語

以下是用於說明 Microsoft 365 多地理位置的重要詞彙：

- **中央位置** - 佈建租用戶的原始地理位置。
- **地理位置管理員** - 系統管理員，可以管理一或多個指定的衛星位置。
- **地理位置代碼** - 表示特定地理位置的三個字母代碼。
- **地理位置** – 用於在多地理位置租用戶中主控資料的地理位置，包括 Exchange 信箱以及 OneDrive 和 SharePoint 網站。
- **慣用的資料位置 (PDL)** - 由系統管理員設定的使用者屬性，表示應佈建使用者 Exchange 信箱和 OneDrive 的地理位置。 PDL 還可決定要在哪裡佈建使用者建立的 SharePoint 網站。
- **衛星位置** – 在多地理位置租用戶中啟用地理感知 Microsoft 365工作量 (SharePoint、OneDrive和 Exchange) 的地理位置。
- **租用戶** – 組織在 Microsoft 365 中的呈現方式，通常會有與其相關聯的一個或多個網域 (例如 contoso.com)。

## <a name="licensing"></a>授權

Microsoft 365 多地理位置可作為以下 Microsoft 365 訂閱方案的附加元件，這些 Enterprise 合約客戶的租用戶中至少有 250 個 Microsoft 365 基座，其中至少有 5% 使用多地理位置。 使用者訂閱授權必須位於與多地理位置服務授權相同的 Enterprise 合約上。 如需詳細資訊，請連絡您的 Microsoft 帳戶小組。

- Microsoft 365 F1、F3、E3 或 E5
- Office 365 F3、E1、E3 或 E5
- Exchange Online 方案 1 或方案 2
- 商務用 OneDrive 方案 1 或方案 2
- SharePoint Online 方案 1 或方案 2

如果授權指派給使用者但稍後移除，Teams 使用者聊天資料會排入佇列，等候移回中央位置。 不會移動 SharePoint 和 Exchange 資料。

## <a name="microsoft-365-multi-geo-availability"></a>Microsoft 365 多地理位置可用性

目前在這些地區與國家中提供 Microsoft 365 多地理位置：

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a>快速入門

按照這些步驟來開始使用多地理位置：

1. 與您的帳戶團隊合作來新增「Microsoft 365 多地理位置功能」服務方案。 他們會引導您新增所需數量的授權。 多地理位置功能可供具有至少 250 個 Microsoft 365 訂閱的 EA 客戶使用。

   開始使用 Microsoft 365 多地理位置之前，Microsoft 必須先設定您的 Exchange Online 租用戶，以支援多地理位置。 當您訂購「Microsoft 365 中的多地理位置功能」服務方案，並於租用戶中顯示授權之後，將觸發此一次性設定程序。 當您的租用戶完成每個工作負載的設定程式後，您就會在 [Microsoft 365 訊息中心](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093)中收到工作負載指定通知，然後您就可以開始設定並使用您的 Microsoft 365 多地理位置功能。 將租使用者設定為多地域位置支援所需的時間，會因租使用者而異，但大部分租使用者會在收到功能授權後的一個月內完成設定。 較大或較複雜的租使用者可能需要更多時間才能完成設定程式。 如需有關特定租使用者的詳細資料，請與您的帳戶小組聯繫。

2. 閱讀[規劃適用多個地理位置](plan-for-multi-geo.md)。

3. 深入了解[管理適用多個地理位置](administering-a-multi-geo-environment.md)與[使用者會遇到的環境](multi-geo-user-experience.md)。

4. 當您準備好設定 Microsoft 365 多地理位置，請[設定租用戶以支援多地理位置](multi-geo-tenant-configuration.md)。

5. [設定搜尋](configure-search-for-multi-geo.md)。

## <a name="see-also"></a>請參閱

[Exchange Online 和 OneDrive 中的多地理位置](https://Aka.ms/GoMultiGeo)

[OneDrive 和 SharePoint Online 中的多地理位置功能](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[Exchange Online 中的多地理位置功能](multi-geo-capabilities-in-exchange-online.md)

[適用多個地理位置中的 Teams 體驗](/microsoftteams/teams-experience-o365odb-spo-multi-geo)