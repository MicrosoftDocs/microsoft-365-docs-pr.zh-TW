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
ms.openlocfilehash: 6d16d222a97f309eafdd79a2b107978ce7b4f242
ms.sourcegitcommit: 0867495cb02d0b38b439b16bdce97e6eda483ba9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/18/2020
ms.locfileid: "49712494"
---
# <a name="microsoft-365-multi-geo"></a>Microsoft 365 多地理位置

使用 Microsoft 365 多地理位置，您的組織可以將 Microsoft 365 存在狀態擴展到現有租用戶中的多個地理區域和/或國家/地區。 聯繫您的 Microsoft 客戶小組，以註冊跨國公司的 Microsoft 365 多地理位置。
  
您可以使用 Microsoft 365 多地理位置，在您所選擇的地理位置佈建和儲存待用資料以符合資料落地要求，同時將現代化生產力體驗逐步拓展至您的員工。

如需 Microsoft 365 多地理位置的影片簡介，請參閱 [SharePoint Online 和 OneDrive 多地理位置，以控制資料存放處](https://www.youtube.com/watch?v=Do9U3JuROhk)。

## <a name="multi-geo-architecture"></a>多地理位置架構

在多地理位置環境中，Microsoft 365 租用戶包含一個中央位置(最初佈建 Microsoft 365 訂閱的位置) 和一個或多個衛星位置。 在多地理位置租用戶中，地理位置、群組和使用者資訊的相關資訊掌握在 Azure Active Directory (Azure AD) 中。 由於您的租用戶資訊會集中管理並同步到每個地理位置，若要共用及體驗，公司的每一位員工都必須擁有全域概念。

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

Microsoft 365 多地理位置是適用于企業合約客戶的下列 Microsoft 365 訂閱計畫的附加元件，其承租人中至少有250的 Microsoft 365 座位，至少有5% 的使用多地理位置。 使用者訂閱授權必須與多地理位置服務授權位於相同的 Enterprise 合約上。 如需詳細資訊，請連絡您的 Microsoft 帳戶小組。

- Microsoft 365 F1、F3、E3 或 E5
- Office 365 F3、E1、E3 或 E5
- Exchange Online 方案 1 或方案 2
- 商務用 OneDrive 方案 1 或方案 2
- SharePoint Online 方案 1 或方案 2

## <a name="microsoft-365-multi-geo-availability"></a>Microsoft 365 多地理位置可用性

目前在這些地區與國家中提供 Microsoft 365 多地理位置：

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a>快速入門

按照這些步驟來開始使用多地理位置：

1. 與您的帳戶團隊合作來新增「Microsoft 365 多地理位置功能」服務方案。 他們會引導您新增所需數量的授權。 多地理位置功能可供具有至少 250 個 Microsoft 365 訂閱的 EA 客戶使用。

   開始使用 Microsoft 365 多地理位置之前，Microsoft 必須先設定您的 Exchange Online 租用戶，以支援多地理位置。 當您訂購「Microsoft 365 中的多地理位置功能」服務方案，並於租用戶中顯示授權之後，將觸發此一次性設定程序。 當租使用者完成每項工作負載的設定程式後，您就會在 [microsoft 365 訊息中心](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) 收到工作負載特有的通知，然後您就可以開始設定和使用您的 Microsoft 365 多地理位置功能。 將租使用者設定為多地域位置支援所需的時間，會因租使用者而異，但大部分租使用者會在收到功能授權後的一個月內完成設定。 較大或較複雜的租使用者可能需要更多時間才能完成設定程式。 如需有關特定租使用者的詳細資料，請與您的帳戶小組聯繫。

2. 閱讀[規劃多地理位置環境](plan-for-multi-geo.md)。

3. 深入了解[管理多地理位置環境](administering-a-multi-geo-environment.md)與[使用者會遇到的環境](multi-geo-user-experience.md)。

4. 當您準備好設定 Microsoft 365 多地理位置，請[設定租用戶以支援多地理位置](multi-geo-tenant-configuration.md)。

5. [設定搜尋](configure-search-for-multi-geo.md)。

## <a name="see-also"></a>請參閱

[Exchange Online 和 OneDrive 中的多地理位置](https://Aka.ms/GoMultiGeo)

[OneDrive 和 SharePoint Online 中的多地理位置功能](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[Exchange Online 中的多地理位置功能](multi-geo-capabilities-in-exchange-online.md)

[多地理位置環境中的 Teams 體驗](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo)
