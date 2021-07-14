---
title: 在 SharePoint Online 中規劃您的入口網站啟動向外推廣計畫
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: 本文說明如何在線上 SharePoint 中規劃入口網站啟動，以及成功啟動所需採取的步驟。
ms.openlocfilehash: 280aa76c41e7ef72d23b22877482a92d981fe29d
ms.sourcegitcommit: 69d28334e01ec757c794cf3f8b8c0d85713f975e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53424019"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>在 SharePoint Online 中規劃您的入口網站啟動向外推廣計畫

入口網站是內部網路上的 SharePoint 網站，具有許多網站檢視器，使用網站上的內容。 大型組織可能會有數個入口網站。 例如，公司入口網站及 HR 入口網站。 通常，入口網站建立及撰寫網站和內容的人相對較少。 大部分的訪客來到入口網站只會閱讀並取用內容。

本文說明如何規劃您的部署和外推行計畫，以 SharePoint 線上。 它也會提供在 SharePoint 線上上不允許傳統負載測試時遵循的方法。 SharePoint線上是一項雲端服務，且服務的負載、健康情況及總負載平衡是由 Microsoft 所管理。

若要協助建立成功的入口網站，請遵循[建立、啟動及維護健康入口網站](/sharepoint/portal-health)的基本原則、作法和建議 

部署方法會在下方反白顯示。

## <a name="portal-launch-scheduler"></a>入口網站啟動調度程式

使用入口網站啟動排程器，將您的入口網站發佈給組織中的使用者（排程階段）。 深入了解： 

行事![曆圖示](https://docs.microsoft.com/Office/media/icons/calendar.png "入口網站啟動調度程式")[入口網站啟動](https://docs.microsoft.com/microsoft-365/enterprise/portallaunchscheduler)排程器  



## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>SharePoint 線上的容量規劃概述
為了有效地使用容量並處理未預期的成長，在任何伺服器陣列中，我們都有追蹤某些使用案例的自動化。 在任何一個伺服器陣列中，任何一個承租人的實際成長都無法預測，而且總的要求總數可透過時間預測。 透過找出 SharePoint 線上中的成長趨勢，我們可以規劃未來的擴充。 如需詳細資訊[，請 SharePoint 線上的容量規劃和負載測試](capacity-planning-and-load-testing-sharepoint-online.md)。

成功啟動的關鍵區段是下文的「波形」或「逐步外滾」方式。 

## <a name="can-i-load-test-sharepoint-online"></a>我可以線上載入測試 SharePoint 嗎？
SharePoint線上是跨伺服器陣列進行平衡的共用多 tenanted 環境，並可在不斷調整規模。 負載測試環境（如 SharePoint Online），其縮放比例變更不只會給您未預期的結果，但不允許。 

深入瞭解：[容量規劃和負載測試 SharePoint 線上](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>遵循建議的指導方針以優化頁面
內部部署中部署的頁面不只是移至 SharePoint 線上，而不需針對線上 SharePoint 建議方針進行查看。 最佳的做法是，針對 SharePoint 中的任何網站或入口網站，一定要優化任何首頁，因為這是您組織中的大部分使用者將存取為網站 (s) 的起點的地方。

應該考慮的一些基本因素如下：
- 內部部署可以使用傳統的伺服器端快取，例如物件快取、輸出快取和 blob 快取。 在雲端的拓撲差異中，這些選項不一定可供您使用，因為大量的比例差異使其不太可行。
- 用於雲端消耗的任何頁面/功能/自訂，都應該針對較高的延遲和使用者的分散位置進行優化，這樣不同區域或地區的使用者便可獲得更一致的經驗。 雲端提供優化功能（如內容傳遞網路） (CDN) 以針對分散式使用者基礎和現代 SharePoint 進行優化，則我們可以從盒後的 OOTB (網頁元件使用最後一個已知良好的) LKG (。

### <a name="what-to-do"></a>要執行的動作：
 - 對於 SharePoint Online 中的所有網站頁面，都使用[頁面診斷工具](./page-diagnostics-for-spo.md)，這是協助分析和提供指引的 Chromium 擴充功能。 這可供網站擁有者、編輯器、管理員及開發人員使用，因為其設計是要成為分析和優化的起點。
 - 開發人員也應該在新式頁面上使用像是 F12 browser developer 工具和 CTRL-F12 等開發工具。 [Fiddler](https://www.telerik.com/download/fiddler) 也可以用來查看大小的長短 (頁面以 mb) 的大小，以及影響整體頁面負載的呼叫和元素數目。 

本節是優化頁面的簡短摘要。  若要深入瞭解，請參閱：  [建立、啟動及維護狀況良好的入口網站](/sharepoint/portal-health)。

## <a name="follow-a-wave--phased-roll-out-approach"></a>依照波形/分階段的外滾方式
針對網站發行的傳統大做法做法，將不會允許驗證自訂、外部來源、服務或處理常式已以適當的比例進行測試。 這種方法並不表示需要數月的時間來啟動，但建議您在至少數天內，取決於您的組織規模。 依照波形向外延展計畫，您可以選擇暫停及解決問題，再繼續進行下一個階段，進而降低受任何問題影響的潛在使用者數目。 SharePoint 為服務會根據使用量和預測使用量來調整您的容量，而不需要您通知我們您的產品發佈，您應該遵循指導方針以確保成功。
  
如下圖所示，受邀的使用者人數通常會遠遠高於實際使用網站的使用者數目。 此影像顯示如何推出版本的策略。 這個方法可協助您找出 SharePoint 網站的改善方式，讓使用者看不到。
  
![顯示受邀和作用中使用者的圖形](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
在試驗階段中，最好是取得組織信任和知道的使用者意見反應。 如此一來，就可以估量系統的使用方式及其執行方式。
  
在每個聲波期間，在每個部署浪潮期間收集功能和效能的使用者意見反應。 收集意見反應具有緩慢引進系統，並在系統獲得更多用途時進行改進的優勢。 這也可讓我們對增加的負載作出反應，因為網站會向其他使用者推出，並結合執行頁面優化的指導方針，以確保使用者取得積極的體驗。

### <a name="what-to-do"></a>要執行的動作：
- 決定每個階段的計時，並確定您有應急/暫停機會，應在繼續之前進行調整
- 規劃您想要啟用的第一組使用者，以確保您收到向前移動所需的意見反應。  如有可能，請選取可及時提供意見反應的使用中使用者群組。
- 當您規劃每個浪潮時，請嘗試使用小於5000使用者) 的小型使用者基底開始 (。 在您進行每個波形時，增加群組的大小。 透過建立交錯的方法，可讓您視需要更容易停頓機會。