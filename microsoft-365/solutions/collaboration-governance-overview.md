---
title: Microsoft 365 中的共同作業管理
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 瞭解如何在 Microsoft 365 群組、小組、SharePoint 及 Yammer 中管理相關的功能。
ms.openlocfilehash: b217dc089eb150d01eed9cd720b2caa290d54bf1
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950709"
---
# <a name="overview-of-collaboration-governance-in-microsoft-365"></a>Microsoft 365 中的共同作業管理

Microsoft 365 有一套豐富的工具，可實施組織可能需要的任何控管功能。 本文將引導 IT 專業人員要求適當的問題，以判斷其控管需求，以及如何根據組織設定檔來符合這些需求。

## <a name="what-are-microsoft-365-groups"></a>何謂 Microsoft 365 群組？

我們知道目前的組織使用不同的工具集。 使用團隊聊天的開發人員小組、主管電子郵件，以及透過企業社交的整個組織。 因為每個群組都是唯一的，且具有自身的功能需求和工作樣式，所以使用多個協同作業工具。 有些只會使用電子郵件，有些人會主要在聊天中生活。 

如果使用者感覺其所提供的工具不符合其需求，他們就可能會下載其最愛的使用者應用程式，以支援其案例。 雖然此程式可讓使用者快速開始，但在組織中有多個登入、難於共用，而且沒有任何單一位置可供查看內容時，可讓整個組織的使用者體驗變得令人沮喪。 這個概念稱為「陰影 IT」，並對組織帶來極大的風險。 它可減少統一管理使用者存取、確保安全性和服務合規性需求的能力。

Microsoft 365 群組、小組和 Yammer 等服務可讓使用者，並提供共同作業所需的工具，以降低陰影的風險。 Microsoft 365 群組可讓您選擇您想要共同作業的一組人員，並輕鬆地設定要共用之人員的資源集合。 新增成員至群組時，會自動授與群組所提供之所有資產的必要許可權。 兩個小組和 Yammer 都使用 Microsoft 365 群組來管理其成員資格。

![顯示 Microsoft 365 群組和相關服務的圖表](../media/microsoft-365-groups-hub-spoke.png)

Microsoft 365 群組包含各種控管控制項，包括到期原則、命名慣例和封鎖的字詞原則，以協助您管理組織中的群組。 如需詳細資訊，請參閱 [規劃組織及生命週期管理的 microsoft 365 群組和 Microsoft 團隊](plan-organization-lifecycle-governance.md) 。

## <a name="technical-architecture"></a>技術架構

Microsoft 365 支援三種主要通訊方法：

- Outlook：透過使用共用群組收件匣和行事曆的電子郵件進行協同作業
- Microsoft 小組：一種持續聊天的工作區，您可以在其中以特定子群組為基礎的各種主題，進行非正式、即時的交談
- Yammer：共同作業的企業社交體驗

> [!NOTE]
> 透過其他團隊合作應用程式建立新的群組（例如，SharePoint、Planner 或 Stream），將會建立具有 Outlook 收件匣的群組，以及連接到小組的功能。

根據建立群組的位置，會自動布建特定資源，例如：
- [收件](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) 匣-群組成員之間的電子郵件交談。 此收件匣具有電子郵件地址，可以設定為接受來自群組以外的人員，甚至是組織外的郵件，與傳統的通訊群組清單非常類似。
 - 行事[曆](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a)–用於排程與群組相關的事件
- [SharePoint 小組網站](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e) –中央存放庫，提供與群組相關的資訊、連結和內容。
- [OneNote 筆記本](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97) –用於收集創意、調查和資訊
- [Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) –用於指派及管理群組成員中的專案工作
- [Yammer 群組](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) –具有交談及共用資訊的常見位置
- 小組– Microsoft 365 中的聊天工作區
- Stream-影片傳送服務

> [!NOTE]
> 透過 Yammer 或小組建立新的 Office 365 群組時，群組不會出現在 Outlook 或通訊錄中，因為這些使用者之間的主要通訊會在各自的用戶端中發生。 Yammer 群組無法連線至團隊。

## <a name="collaboration-options"></a>協同作業選項

在 Microsoft 365 內有多個地方共同作業和進行交談。 瞭解開始交談的位置可協助您定義通訊策略。

![圖表顯示何時使用團隊、Yammer 和 Outlook](../media/inner-loop-outer-loop.png)

- 小組：以聊天為基礎的工作區 (高速度共同作業) –內環
  - 專為與您每天使用的人員共同作業
  - 以單一體驗將資訊放在使用者的手邊
  - 新增索引標籤、連接器和 bot
  - 即時聊天、音訊/視訊會議、記錄的會議

- Yammer：跨組織 (enterprise 社交) –外部迴圈
  - 業務部的社區，其共同共同感興趣或專業知識的人員跨職能群組，但不一定要在日常運作中協同運作。
  - 領導能力，學習社區，以角色為基礎的社區

- 信箱和行事曆 (電子郵件型共同作業) 
  - 用於與一組人員進行目標通訊
  - 與其他群組成員的會議共用行事曆
 
每個群組都取得連線的 SharePoint 小組網站，讓使用者可以共用內容、建立自訂頁面和作者新聞。 您也可以 [將現有的 SharePoint 小組網站連線到新的 Microsoft 365 群組](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview)。

## <a name="illustrations"></a>插圖

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>適用於 IT 結構設計師的 Microsoft 365 中的Microsoft Teams 和相關生產力服務
使用 Microsoft Teams 領導，Microsoft 365 中生產力服務的邏輯架構。

|**項目**|**描述**|
|:-----|:-----|
|[![Teams 邏輯架構海報的縮圖影像](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>更新日期：2019 年 4 月   |Microsoft 提供一套生產力服務，共同合作來提供資料管理、安全性和法規遵循功能的共同作業體驗。 <br/> <br/>這系列的圖例可為企業結構設計師提供生產力服務邏輯架構使用 Microsoft Teams 引導的檢視。|


### <a name="groups-in-microsoft-365-for-it-architects"></a>適用於 IT 結構設計師的 Microsoft 365 中的群組
對於 Microsoft 365 中的群組，IT 結構設計師需要知道的事項

|**項目**|**描述**|
|:-----|:-----|
|[![群組資訊圖的縮圖影像](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> 更新日期：2019 年 6 月|這些圖例會詳細說明不同類型的群組、如何建立及管理群組，以及一些控管建議。|

## <a name="conference-sessions"></a>會議會話

觀看這些會議會話，以深入瞭解 Microsoft 365 群組和小組的管理。

**基礎**

深入瞭解 Microsoft 365 群組中的基礎和新創新，包括規模的管理和控管，以及驅動使用狀況和採用方式的最佳作法，以及自助服務。

- [接納 Microsoft 365 群組](https://www.youtube.com/watch?v=dAamBF1gb7M)

**管理**

瞭解如何設定您的群組到期生命週期、命名原則、分類標籤、與外部來賓的共同作業，以及管理群組建立許可權。

- [使用 Office 365 群組轉換共同作業及抵制陰影](https://www.youtube.com/watch?v=Bhf_bKx3lAg)

**客戶範例**

請參閱幕後的範例，說明 Microsoft 365 群組、SharePoint、小組和 Yammer 如何共同運作，以提供全球協同作業平臺。

- [使用 Office 365 群組、SharePoint、小組和 Yammer 尋找共同作業的最擅長點](https://www.youtube.com/watch?v=Rx9eVwqXeQk)
