---
title: 管理 Microsoft Viva 主題中主題中心的主題
description: 如何管理主題中心的主題。
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: ergradel
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: f2429b0ffdd4a238bc9322ae9199eebbbfd407b5
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651151"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a>管理 Microsoft Viva 主題中主題中心的主題

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

在 Viva 主題主題中心，知識管理員可以查看「 **管理主題** 」頁面，以查看已在來源位置中識別的主題，如您的知識系統管理員所指定的主題。  

   ![主題中心](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a>主題階段

知識管理員會協助您透過各種主題週期階段來引導探索的主題： **建議**、 **確認**、 **發行** 及 **移除**。

   ![主題生命週期圖表](../media/knowledge-management/topic-lifecycle.png) 

- **建議**：AI 已識別主題，並且有足夠的支援資源、關聯和屬性。  (這些會標示為 UI 中的 **建議主題** 。 ) 

- 已 **確認**：已透過 AI 探索並已驗證的主題。 主題驗證會在下列其中一項：

   - 知識管理員會確認主題。 知識管理員會在 [**管理主題**] 頁面上 [確認主題](manage-topics.md#confirmed-topics)。

   - 多位使用者確認主題。 您必須從使用主題卡片上的意見反應機制來投票的使用者，收到兩封正投票的網路。 例如，如果一個使用者投票肯定的正負一個使用者的投票為負值，您仍需要兩個正值投票才能確認該主題。
 
- 已 **發佈**：已策劃的主題。 手動編輯是為了改善其品質，或是由使用者建立。

- **已移除**：已遭拒絕的主題，將不再對檢視器顯示。 您可以在任何狀態中移除主題 (建議、確認或發佈的) 。 移除主題時，會發生下列其中一項：

   - 知識管理員會移除一個主題。 知識管理員會移除 [ **管理主題** ] 頁面上的主題。

   - 多個使用者使用主題卡片上的意見反應機制來強制轉換負值投票。 若要移除的主題，必須從使用者收到兩個否定投票的淨值。 例如，如果一個使用者投票了負數，另一個使用者對某特定主題投票了肯定的，則您仍然需要兩個負的投票來移除該主題。

  移除已發佈的主題時，將需要透過主題中心的頁面庫手動刪除策劃詳細資料的頁面。

> [!Note] 
> 在 [ **管理主題** ] 頁面上，每個知識管理員只會看到可以存取相關主題之基礎檔案及頁面的主題。 此許可權修整會反映在 [ **建議**]、[已 **確認**]、[ **已發佈**] 及 [ **已移除** ] 索引標籤中出現的主題清單中。 不過，這個主題會計陣列織中的總數量，不論許可權為何。

## <a name="requirements"></a>需求

若要管理主題中心的主題，您必須：
- 擁有 Viva Topics 授權。

- 讓 [**神秘可以管理主題**](./topic-experiences-user-permissions.md)許可權。 知識系統管理員可以在 Viva Topics 主題權限設定中將此權限給予使用者。 

除非您有 **神秘可以管理主題** 許可權，否則您將無法在主題中心中查看「**管理主題**」頁面。

在主題中心，知識管理員可以查看已在您指定之來源位置中識別的主題，也可以確認或移除這些主題。 知識管理員也可以建立及發佈新的主題頁面（如果未在主題探索中找到的話），或編輯現有的主題頁面（如果需要更新）。

## <a name="review-suggested-topics"></a>查看建議的主題

在 [**管理主題**] 頁面上，在您指定的 SharePoint 來源位置中探索的主題會列在 [**建議**] 索引標籤上。如有需要，知識管理員可以查看未確認的主題，並選擇確認或移除。

   ![建議的主題](../media/knowledge-management/quality-score.png) 

若要查看建議的主題：

1. 在 [ **管理主題** ] 頁面上，選取 [ **建議** ] 索引標籤，然後選取主題，以開啟 [主題] 頁面。

2. 在 [主題] 頁面上，複查 [主題] 頁面，如果您需要對頁面進行任何變更，請選取 [ **編輯** ]。 發佈任何編輯都會將此主題移至 [ **發佈** ] 索引標籤。

3. 檢查主題之後，請回到 [ **管理主題** ] 頁面。 對於所選取的主題，您可以：

   - 選取核取記號來確認主題。
    
   - 如果您想要移除該主題，請選取 **x** 。

    已確認的主題將從 **建議** 的清單中移除，現在會顯示在 [已 **確認** ] 清單中。

    移除的主題會從 **建議** 的清單中移除，現在會顯示在 [ **已移除** ] 索引標籤中。

### <a name="quality-score"></a>品質分數

出現在 [ **建議** 主題] 頁面上的每個主題都有指派的品質分數。 品質分數是一般使用者將看到之相關資訊的資訊數量反映，請記住，每當使用者可能會看到更多或更少的資訊，原因是使用者可能會有或可能不會對主題中的資訊所做的許可權。 

品質分數可協助深入瞭解大部分資訊的主題，並可用於尋找可能需要手動編輯的主題。 例如，較低品質分數的主題可能是部分使用者未具有 AI 已包含在主題中的相關檔案或網站的 SharePoint 許可權所導致的結果。 參與者接著可以編輯主題以包含資訊 (適當時)，然後所有可以檢視主題的使用者都可以檢視這些資訊。

### <a name="impressions"></a>閱聽

「 **印記** 」欄會顯示主題向使用者顯示的次數。 這包括透過搜尋中的主題答案卡片及透過主題要聞。 它不會反映這些主題上的點擊式，但已顯示主題。 [**印象**] 欄會顯示在 [**管理主題**] 頁面上 **建議**、已 **確認**、**已發佈** 及 **已移除** 的索引標籤中的主題。

## <a name="confirmed-topics"></a>已確認主題

在 [**管理主題**] 頁面上，在您指定的 SharePoint 來源位置中發現的主題，並已由 net 兩位或更多位人員確認的知識管理員或 "crowdsourced" 確認。 (平衡否定使用者投票) 透過卡片意見反應機制，將會列于 [已 **確認**] 索引標籤中。如有需要，具有管理主題許可權的使用者可以查看已確認的主題，並選擇拒絕這些主題。

若要檢閱已確認的主題：

1. 在 **[已確認]** 索引標籤上，選取主題以開啟主題頁面。

2. 在 [主題] 頁面上，複查 [主題] 頁面，如果您需要對頁面進行任何變更，請選取 [ **編輯** ]。

請注意，您仍然可以選擇拒絕已確認的主題。 若要執行此動作，請移至 [已 **確認** ] 索引標籤上的選取主題，然後選取 **x** （如果您想要拒絕該主題）。

## <a name="published-topics"></a>已發佈主題

已發佈的主題已經過編輯，使特定資訊永遠會出現在頁面出現的任何處。 手動建立的主題也會列在這裡。

   ![管理主題](../media/knowledge-management/manage-topics-new.png)

## <a name="topic-count-dashboard"></a>主題計數儀表板

儀表板視圖中的此圖表可讓您看到 Viva 主題主題中心的主題數目。 圖表會顯示每個主題生命週期階段的主題計數，也會顯示主題計數在一段時間內的 trended。 知識管理員可以以視覺方式監視透過 AI 探索的新主題，以及主題在知識管理員或使用者動作中取得的確認或發佈速率。

知識管理員可能會在 [ **管理主題** ] 頁面的主題清單中看到不同于儀表板中所顯示主題的數目。 這是因為知識管理員可能無法存取所有主題。 在套用許可權修整之前，會先進行儀表板視圖中所呈現的計數。 

   ![主題計數儀表板的螢幕擷取畫面](../media/knowledge-management/topic-count-dashboard.png)
