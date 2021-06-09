---
title: 診斷 SharePoint Online 的效能問題
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
audience: Admin
ms.topic: troubleshooting
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
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: 本文說明如何使用 Internet Explorer 開發人員工具來診斷 SharePoint Online 網站的常見問題。
ms.openlocfilehash: 6a29b8b2df54d74d8237418828a7aa89efdbcfaf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927609"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a>診斷 SharePoint Online 的效能問題

本文說明如何使用 Internet Explorer 開發人員工具來診斷 SharePoint Online 網站的常見問題。
  
您可以使用三種不同的方式，識別出 SharePoint Online 網站上的頁面對自訂產生效能問題。
  
- F12 工具條網路監視器

- 比較非自訂基準

- SharePoint線上回應標頭度量

本主題說明如何使用上述每一種方法來診斷效能問題。 當您瞭解問題的原因之後，您可以使用改進 SharePoint 效能的相關文章，對解決方案進行工作 https://aka.ms/tune 。
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a>使用 F12 工具列在 SharePoint Online 中診斷效能
<a name="F12ToolInfo"> </a>

在本文中，我們使用 Internet Explorer 11。 其他瀏覽器上的 F12 開發人員工具的版本具有類似的功能，但看起來可能稍有不同。 如需 F12 開發人員工具的詳細資訊，請參閱：
  
- [F12 工具的新功能](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))

- [使用 F12 開發人員工具](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))

若要顯示開發人員工具，請按 **F12** ，然後按一下 Wi-Fi 圖示：
  
![F12 開發人員工具 WIFI 圖示的螢幕擷取畫面](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
在 [ **網路** ] 索引標籤上，按綠色的 [播放] 按鈕載入頁面。 工具會傳回瀏覽器要求的所有檔案，以便取得您要求的頁面。 下列螢幕擷取畫面顯示一個這類清單。
  
![使用頁面要求所傳回之檔案清單的螢幕擷取畫面。](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
您也可以在右側看到檔案的下載時間（如螢幕擷取畫面所示）。
  
![圖表顯示從 SharePoint 載入要求頁面所需的時間](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
這可讓您以視覺方式表示檔載入所需的時間。 綠色線代表瀏覽器準備呈現頁面的時間。 這可讓您快速查看可能導致網站上頁面負載變慢的不同檔案。
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a>設定 SharePoint 線上的非自訂基準
<a name="F12ToolInfo"> </a>

若要判斷您的網站效能薄弱點，最好的方法是在 SharePoint Online 中設定完全現成的網站集合。 如此一來，您可以將網站的各個層面與您在頁面上沒有自訂的內容進行比較。 商務用 OneDrive 首頁是不太可能具有任何自訂之個別網站集合的很好的範例。
  
## <a name="viewing-sharepoint-response-header-information"></a>查看 SharePoint 回應標頭資訊
<a name="F12ToolInfo"> </a>

在 SharePoint Online 中，您可以在每個檔案的回應標頭中，存取傳送回瀏覽器的資訊。 診斷效能問題最實用的價值是 **SPRequestDuration**，它會顯示要求處理伺服器時所花費的時間量。 這可協助判斷要求是否非常繁重和資源密集。 這是您在伺服器上處理頁面時所能執行的工作程度最佳的洞察力。

### <a name="to-view-sharepoint-response-header-information"></a>若要查看 SharePoint 回應標頭資訊
  
1. 確定您已安裝 F12 工具。 如需下載及安裝這些工具的詳細資訊，請參閱 [F12 工具的新功能](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))。

2. 在 [F12 工具] 的 [ **網路** ] 索引標籤上，按綠色的 [播放] 按鈕載入頁面。

3. 按一下工具傳回的其中一個 .aspx 檔，然後按一下 [ **詳細資料**]。

    ![顯示回應標頭的詳細資料](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. 按一下 [ **回應標頭**]。

    ![圖表顯示回應標頭的 URL](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a>線上 SharePoint 導致效能問題的原因為何？
<a name="F12ToolInfo"> </a>

[SharePoint Online 的文章導覽選項](navigation-options-for-sharepoint-online.md)顯示使用 SPRequestDuration 值的範例，以判斷複雜的結構流覽是否導致頁面在伺服器上處理很長的時間。 在沒有自訂) 的情況下，為基準網站取值 (，可以判斷是否有任何指定的檔案需要很長的時間才能載入。 [SharePoint Online 的導覽選項](navigation-options-for-sharepoint-online.md)中使用的範例是主 .aspx 檔案。 該檔案包含大多數為頁面載入執行的 ASP.NET 程式碼。 視您使用的網站範本而定，當您自訂首頁時，可能會啟動 .aspx、首頁、default.aspx 或其他名稱。 如果此數位的數目遠遠高於您的基準網站，表示頁面上發生效能問題的情況很好。
  
在您識別網站特有的問題之後，建議的方式是找出導致效能不良的原因，以消除所有可能的原因（如頁面自訂），然後再將其新增回網站一。 當您移除頁面執行良好的足夠自訂之後，即可逐個新增特定的自訂。
  
例如，如果您有非常複雜的導覽，請嘗試將導覽變更為 [不顯示子網站]，然後檢查開發人員工具，以查看是否有差異。 或者，如果您有大量的內容試妥，請嘗試從您的頁面中移除這些內容，然後查看是否有改進。 如果您消除所有可能的原因，並一次將其新增回一次，您可以輕鬆識別哪些功能是最大的問題，然後再向方案中取得作用。