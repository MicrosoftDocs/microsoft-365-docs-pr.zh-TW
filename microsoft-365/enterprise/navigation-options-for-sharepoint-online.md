---
title: SharePoint Online 的導覽選項
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/7/2020
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: adb92b80-b342-4ecb-99a1-da2a2b4782eb
description: 本文說明 SharePoint 線上中啟用 SharePoint 發佈功能的導覽選項網站。
ms.openlocfilehash: b5989bf26ebf7bb1452f983af89a6e6739821d53
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923621"
---
# <a name="navigation-options-for-sharepoint-online"></a>SharePoint Online 的導覽選項

本文說明 SharePoint 線上中啟用 SharePoint 發佈功能的導覽選項網站。 導覽的選擇和設定會大幅影響 SharePoint Online 中網站的效能與擴充性。 只有在集中式入口網站需要時才會使用 SharePoint 發佈網站範本，而且發佈功能應該只在特定網站上啟用，而且只有在絕對需要時才會在使用不當時影響效能。

>[!NOTE]
>如果您使用的是新式 SharePoint 導覽選項（例如，您的百萬位元功能表、級聯導覽或 hub 導覽），本文不會套用到您的網站。 新式 SharePoint 網站架構利用更平展的網站階層和中樞輻射模型。 這可讓許多案例達到，而不需要使用 SharePoint 發佈功能。

## <a name="overview-of-navigation-options"></a>導覽選項的概述

導覽提供者設定會大幅影響整個網站的效能，而且必須慎重考慮，以挑選流覽提供者和設定，以有效地伸縮 SharePoint 網站的需求。 有兩個現成的導覽提供者和自訂導覽實現。

**如果您開啟網站的結構式流覽** 快取，則第一個選項（[**結構導覽**](#using-structural-navigation-in-sharepoint-online)）是 SharePoint Online for 傳統 SharePoint 網站中的建議流覽選項。 此導覽提供者會顯示目前網站底下的流覽專案，並選擇性地顯示目前網站及其同輩。 它提供額外的功能，例如安全性修整和網站結構列舉。 如果停用快取，這會對效能及擴充性產生負面影響，而且可能會受到節流。

第二個選項是 [**managed (中繼資料) 導覽**](#using-managed-navigation-and-metadata-in-sharepoint-online)）代表使用受管理的中繼資料字片語流覽專案。 建議您先停用安全修整，除非需要。 啟用此導覽提供者的安全性調整為安全的預設設定;不過，許多網站不需要安全性調整的額外負荷，因為導覽元素通常對網站的所有使用者都是一致的。 使用建議的設定來停用安全修整時，此導覽提供者不需要列舉網站結構，高擴充性會影響到可接受的效能。

除了現成的導覽提供者以外，許多客戶都已成功實施替代的自訂導覽實現。 請參閱本文中 [的搜尋導向用戶端腳本](#using-search-driven-client-side-scripting) 。
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a>SharePoint 線上導覽選項的優點和缺點

下表摘要說明每個選項的優缺點。

|結構導覽  |受管理導覽  |搜尋導向導覽  |自訂導覽提供者  |
|---------|---------|---------|---------|
|優<br/><br/>易於維護<br/>已修整安全性<br/>在內容變更時于24小時內自動更新<br/>     |優<br/><br/>易於維護<br/>|優<br/><br/>已修整安全性<br/>新增網站時自動更新<br/>快速載入時間和本機快取導覽結構<br/>|優<br/><br/>可用選項的更寬選擇<br/>正確使用快取時的快速載入<br/>許多選項適用于快速回應頁面設計<br/>|
|缺點：<br/><br/>**停用緩衝時影響效能**<br/>受制于節流<br/>|缺點：<br/><br/>不會自動更新以反映網站結構<br/>在 **啟用安全修整** 或流覽流覽結構複雜時影響效能<br/>|缺點：<br/><br/>不能輕鬆地訂購網站<br/>需要自訂主版頁面 (所需的技術技能) <br/>|缺點：<br/><br/>需要自訂開發<br/>需要儲存外部資料源/快取（例如 Azure）<br/>|

網站最適合的選項取決於您的網站需求和您的技術能力。 如果您想要在內容變更時自動更新的易於設定導覽提供者，則 [啟用](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) 快取的結構導覽是一個不錯的選擇。

>[!NOTE]
>將整體網站結構簡化為新式的 SharePoint 網站，以套用相同的原則，可提高效能，並簡化移至現代 SharePoint 網站的效能。 這表示的含義是，不需要有數百個網站的單一網站集合 (子網站) ，更好的方法是有許多網站集合，但 (子網站) 很少的子網站。

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a>在 SharePoint Online 中分析導覽效能

[SharePoint 工具的頁面診斷](./page-diagnostics-for-spo.md)功能是 Microsoft Edge 和 Chrome 瀏覽器的瀏覽器擴充，可分析 SharePoint 線上新式入口網站和傳統發佈網站頁面。 此工具僅適用于線上 SharePoint，無法在 SharePoint 系統] 頁面上使用。

工具會針對每個已分析的頁面產生報表，顯示頁面如何針對預先定義的規則集執行，並在測試結果超出基線值時顯示詳細資訊。 SharePoint線上管理員和設計者可以使用工具來疑難排解效能問題，以確保新頁面在發佈之前已經過優化。

**SPRequestDuration** 特別是 SharePoint 處理頁面所需的時間。 大量導覽 (例如在導覽) 中包含頁面、複雜的網站階層，以及其他設定和拓撲選項，都可能會大幅增加持續時間。

## <a name="using-structural-navigation-in-sharepoint-online"></a>在 SharePoint Online 中使用結構導覽

這是預設使用的預置導覽，而且是最直接的解決方案。 不需要任何自訂，非技術使用者也可以輕鬆地新增專案、隱藏專案，以及從 [設定] 頁面中管理導覽。 建議您 [啟用](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)快取，否則會有昂貴的性能權衡。

### <a name="how-to-implement-structural-navigation-caching"></a>如何實施結構性導覽快取

在 [**網站設定** 的  >  **外觀與風格**  >  **導覽**] 底下，您可以驗證是否已選取全域導覽或目前導覽的結構導覽。 選取 [ **顯示頁面** 會對效能產生負面影響。

![選取 [顯示子網站] 的結構導覽](../media/SPONavOptionsStructuredShowSubsites.png)

您可以在網站集合層級或網站層級啟用或停用快取，且預設為啟用。 若要在網站集合層級啟用，請在 [**網站設定**  >  **網站集合管理**  >  **網站集合導覽**] 底下，選取 [**啟用** 快取] 方塊。

![在網站層級啟用快取](../media/structural-nav/structural-nav-caching-site-coll.png)

若要在網站層級啟用，請在 [**網站設定**  >  **導覽**] 底下，選取 [**啟用** 快取] 方塊。

![在網站層級啟用快取](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a>在 SharePoint Online 中使用受管理導覽和中繼資料

受管理導覽是另一個現成的現成選項，可讓您用來重新建立大部分與結構導覽相同的功能。 受管理的中繼資料可以設定為啟用或停用安全修整。 當設定安全性調整為停用時，受管理的導覽會非常有效率，因為它會載入具有大量伺服器呼叫的所有導覽連結。 不過，啟用安全修整會否定受管理導覽的一些效能優點。

如果您需要啟用安全修整，建議您執行下列動作：

- 將所有易記 URL 連結更新為簡單連結
- 將必要的安全性調整節點新增為易記 URLs
- 將導覽專案數目限制為不超過100，且不超過3層級深度

許多網站不需要安全性調整，因為導覽結構通常會一致網站的所有使用者。 如果停用安全性調整，而且在不是所有使用者都可以存取的情況下新增連結，則該連結仍會顯示，但會導致「拒絕存取」訊息。 沒有意外存取內容的風險。

### <a name="how-to-implement-managed-navigation-and-the-results"></a>如何執行受管理導覽和結果

關於受管理導覽的詳細資料，有數個 docs.microsoft.com 文章。 例如，請參閱[SharePoint Server 中受管理導覽的概述](/sharepoint/administration/overview-of-managed-navigation)。

為了實施受管理導覽，您可以使用與網站導覽結構相對應的 URLs 來設定字詞。 管理的導覽甚至可以手動策劃，以在許多情況下取代結構性導覽。 例如：

![SharePoint線上網站結構](../media/SPONavOptionsListOfSites.png))

## <a name="using-search-driven-client-side-scripting"></a>使用搜尋導向的用戶端腳本

自訂導覽實現的一個共同類別包含用戶端轉譯的設計模式，以儲存流覽節點的本機快取。

這些導覽提供者具有以下幾個主要優點：

- 它們通常適用于回應頁面設計。
- 它們的可擴充性和能力極高，因為它們在呈現時不需資源成本 (，而且在) 超時後會在背景中重新整理。
- 這些導覽提供者可以使用各種策略（從簡單靜態設定到不同動態資料提供者）來取得導覽資料。

資料提供者的範例是使用 **搜尋導向導覽**，這可讓您靈活地列舉流覽節點及有效處理安全性調整。

另外還有其他常見的選項可建立 **自訂導覽提供者**。 如需建立自訂導覽提供者的進一步指導，請參閱[SharePoint Online 入口網站的導覽解決方案](/sharepoint/dev/solution-guidance/portal-navigation)。

使用搜尋您可以使用連續編目，利用背景中所建立的索引。 搜尋結果會從搜尋索引中提取，而結果會進行安全修整。 在需要安全性調整時，這通常會比預置的流覽提供者更快速。 使用搜尋結構導覽，尤其是當您有複雜的網站結構時，會大幅加快頁面載入時間。 這透過受管理導覽的主要優點是您可以從安全性調整中受益。

這種方法包含建立自訂主版頁面，並以自訂 HTML 取代現成的導覽程式碼。 請遵循下列範例中所述的程式碼來取代檔案中的導覽程式碼 `seattle.html` 。 在此範例中，您將會開啟檔案 `seattle.html` ，並 `id="DeltaTopNavigation"` 以自訂的 HTML 程式碼取代整個元素。

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a>範例：取代主版頁面中的現成導覽代碼

1. 流覽至網站設定] 頁面。
2. 按一下 [ **主版頁面**] 以開啟主版頁面圖庫。
3. 您可以從這裡流覽文件庫，並下載檔案 `seattle.master` 。
4. 使用文字編輯器編輯程式碼，並刪除下列螢幕擷取畫面中的程式碼區塊。<br/>![刪除顯示的程式碼區塊](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. 移除 and 標記之間的程式碼 `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` ，並以下列程式碼片段取代它：<br/>

```javascript
<div id="loading">
  <!--Replace with path to loading image.-->
  <div style="background-image: url(''); height: 22px; width: 22px; ">
  </div>
</div>
<!-- Main Content-->
<div id="navContainer" style="display:none">
    <div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
        </a>
        <ul id="menu" data-bind="foreach: $data.children" style="padding-left:20px">
            <li class="static dynamic-children level1">
                <a class="static dynamic-children menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

                 <!-- ko if: children.length > 0-->
                    <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                <!-- ko if: children.length == 0-->
                    <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                </a>

                <!-- ko if: children.length > 0-->
                <ul id="menu"  data-bind="foreach: children;" class="dynamic  level2" >
                    <li class="dynamic level2">
                        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline  ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

          <!-- ko if: children.length > 0-->
          <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
           <!-- /ko -->
          <!-- ko if: children.length == 0-->
          <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
          <!-- /ko -->
                        </a>
          <!-- ko if: children.length > 0-->
         <ul id="menu" data-bind="foreach: children;" class="dynamic level3" >
          <li class="dynamic level3">
           <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
           </a>
          </li>
         </ul>
           <!-- /ko -->
                    </li>
                </ul>
                <!-- /ko -->
            </li>
        </ul>
    </div>
</div>
```

<br/>
6. 取代您網站集合中載入影像錨點標籤的 URL 中的 URL。 進行變更之後，請重新命名檔案，然後將其上傳至主版頁面圖庫。 這會產生新的 .master 檔案。<br/>
7. 此 HTML 是基本標記，會由 JavaScript 程式碼所傳回的搜尋結果填入。 您必須編輯程式碼，以變更 var root = "site 集合 URL" 的值，如下列程式碼片段所示：<br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. 結果會指派給自身的節點陣列，並使用 linq.js 將輸出指派給陣列 self 階層的物件。 此陣列是系結至 HTML 的物件。 若要在 toggleView () 函數中，將 self 物件傳遞給 applyBinding () 函數，即可完成此動作。<br/>這會使階層陣列系結至下列 HTML：<br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

及的事件處理 `mouseenter` 程式 `mouseexit` 會新增至最上層的導覽，以處理在該函數中所完成的子網站下拉式功能表 `addEventsToElements()` 。

在我們的複雜導覽範例中，沒有本機快取的全新頁面載入顯示伺服器上所花費的時間已從基準結構導覽中削減，以取得與受管理導覽方法類似的結果。

### <a name="about-the-javascript-file"></a>關於 JavaScript 檔案 .。。

>[!NOTE]
>如果使用自訂 JavaScript，請確定已啟用 public CDN，且檔案位於 CDN 位置。

整個 JavaScript 檔如下：

```javascript
//Models and Namespaces
var SPOCustom = SPOCustom || {};
SPOCustom.Models = SPOCustom.Models || {}
SPOCustom.Models.NavigationNode = function () {

    this.Url = ko.observable("");
    this.Title = ko.observable("");
    this.Parent = ko.observable("");

};

var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
var baseUrl = root + "/_api/search/query?querytext=";
var query = baseUrl + "'contentClass=\"STS_Web\"+path:" + root + "'&trimduplicates=false&rowlimit=300";

var baseRequest = {
    url: "",
    type: ""
};


//Parses a local object from JSON search result.
function getNavigationFromDto(dto) {
    var item = new SPOCustom.Models.NavigationNode();
    if (dto != undefined) {

        var webTemplate = getSearchResultsValue(dto.Cells.results, 'WebTemplate');

        if (webTemplate != "APP") {
            item.Title(getSearchResultsValue(dto.Cells.results, 'Title')); //Key = Title
            item.Url(getSearchResultsValue(dto.Cells.results, 'Path')); //Key = Path
            item.Parent(getSearchResultsValue(dto.Cells.results, 'ParentLink')); //Key = ParentLink
        }

    }
    return item;
}

function getSearchResultsValue(results, key) {

    for (i = 0; i < results.length; i++) {
        if (results[i].Key == key) {
            return results[i].Value;
        }
    }
    return null;
}

//Parse a local object from the serialized cache.
function getNavigationFromCache(dto) {
    var item = new SPOCustom.Models.NavigationNode();

    if (dto != undefined) {

        item.Title(dto.Title);
        item.Url(dto.Url);
        item.Parent(dto.Parent);
    }

    return item;
}

/* create a new OData request for JSON response */
function getRequest(endpoint) {
    var request = baseRequest;
    request.type = "GET";
    request.url = endpoint;
    request.headers = { ACCEPT: "application/json;odata=verbose" };
    return request;
};

/* Navigation Module*/
function NavigationViewModel() {
    "use strict";
    var self = this;
    self.nodes = ko.observableArray([]);
    self.hierarchy = ko.observableArray([]);;
    self.loadNavigatioNodes = function () {
        //Check local storage for cached navigation datasource.
        var fromStorage = localStorage["nodesCache"];
        if (false) {
            var cachedNodes = JSON.parse(localStorage["nodesCache"]);

            if (cachedNodes && timeStamp) {
                //Check for cache expiration. Currently set to 3 hrs.
                var now = new Date();
                var diff = now.getTime() - timeStamp;
                if (Math.round(diff / (1000 * 60 * 60)) < 3) {

                    //return from cache.
                    var cacheResults = [];
                    $.each(cachedNodes, function (i, item) {
                        var nodeitem = getNavigationFromCache(item, true);
                        cacheResults.push(nodeitem);
                    });

                    self.buildHierarchy(cacheResults);
                    self.toggleView();
                    addEventsToElements();
                    return;
                }
            }
        }
        //No cache hit, REST call required.
        self.queryRemoteInterface();
    };

    //Executes a REST call and builds the navigation hierarchy.
    self.queryRemoteInterface = function () {
        var oDataRequest = getRequest(query);
        $.ajax(oDataRequest).done(function (data) {
            var results = [];
            $.each(data.d.query.PrimaryQueryResult.RelevantResults.Table.Rows.results, function (i, item) {

                if (i == 0) {
                    //Add root element.
                    var rootItem = new SPOCustom.Models.NavigationNode();
                    rootItem.Title("Root");
                    rootItem.Url(root);
                    rootItem.Parent(null);
                    results.push(rootItem);
                }
                var navItem = getNavigationFromDto(item);
                results.push(navItem);
            });
            //Add to local cache
            localStorage["nodesCache"] = ko.toJSON(results);

            localStorage["nodesCachedAt"] = new Date().getTime();
            self.nodes(results);
            if (self.nodes().length > 0) {
                var unsortedArray = self.nodes();
                var sortedArray = unsortedArray.sort(self.sortObjectsInArray);

                self.buildHierarchy(sortedArray);
                self.toggleView();
                addEventsToElements();
            }
        }).fail(function () {
            //Handle error here!!
            $("#loading").hide();
            $("#error").show();
        });
    };
    self.toggleView = function () {
        var navContainer = document.getElementById("navContainer");
        ko.applyBindings(self, navContainer);
        $("#loading").hide();
        $("#navContainer").show();

    };
    //Uses linq.js to build the navigation tree.
    self.buildHierarchy = function (enumerable) {
        self.hierarchy(Enumerable.From(enumerable).ByHierarchy(function (d) {
            return d.Parent() == null;
        }, function (parent, child) {
            if (parent.Url() == null || child.Parent() == null)
                return false;
            return parent.Url().toUpperCase() == child.Parent().toUpperCase();
        }).ToArray());

        self.sortChildren(self.hierarchy()[0]);
    };


    self.sortChildren = function (parent) {

        // sjip processing if no children
        if (!parent || !parent.children || parent.children.length === 0) {
            return;
        }

        parent.children = parent.children.sort(self.sortObjectsInArray2);

        for (var i = 0; i < parent.children.length; i++) {
            var elem = parent.children[i];

            if (elem.children && elem.children.length > 0) {
                self.sortChildren(elem);
            }
        }
    };

    // ByHierarchy method breaks the sorting in chrome and firefox
    // we need to resort  as ascending
    self.sortObjectsInArray2 = function (a, b) {
        if (a.item.Title() > b.item.Title())
            return 1;
        if (a.item.Title() < b.item.Title())
            return -1;
        return 0;
    };


    self.sortObjectsInArray = function (a, b) {
        if (a.Title() > b.Title())
            return -1;
        if (a.Title() < b.Title())
            return 1;
        return 0;
    }
}

//Loads the navigation on load and binds the event handlers for mouse interaction.
function InitCustomNav() {
    var viewModel = new NavigationViewModel();
    viewModel.loadNavigatioNodes();
}

function addEventsToElements() {
    //events.
      $("li.level1").mouseover(function () {
          var position = $(this).position();
          $(this).find("ul.level2").css({ width: 100, left: position.left + 10, top: 50 });
      })
   .mouseout(function () {
     $(this).find("ul.level2").css({  left: -99999, top: 0 });
   
    });
   
     $("li.level2").mouseover(function () {
          var position = $(this).position();
          console.log(JSON.stringify(position));
          $(this).find("ul.level3").css({ width: 100, left: position.left + 95, top:  position.top});
      })
   .mouseout(function () {
     $(this).find("ul.level3").css({  left: -99999, top: 0 });
    });
} _spBodyOnLoadFunctionNames.push("InitCustomNav");

```

若要匯總上述函數中所示的 `jQuery $(document).ready` 程式碼已 `viewModel object` 建立，然後 `loadNavigationNodes()` 呼叫該物件上的函數。 此函數會載入先前在用戶端瀏覽器的 HTML5 本機儲存區中所建立的導覽階層，或其呼叫此函數 `queryRemoteInterface()` 。

`QueryRemoteInterface()``getRequest()`以腳本中所定義的查詢參數來建立要求，然後傳回伺服器的資料。 此資料基本上是網站集合中所有網站的陣列，都是以具有各種屬性的資料傳輸物件來表示。

然後，此資料會剖析成先前定義的 `SPO.Models.NavigationNode` 物件，用 `Knockout.js` 來建立可透過資料系結至我們先前所定義之 HTML 的可觀測的屬性。

然後將物件放入結果陣列中。 此陣列會使用挖空來剖析為 JSON，並儲存在本機瀏覽器儲存體中，以在今後的頁面載入時改善效能。

### <a name="benefits-of-this-approach"></a>這種方法的優點

[這種方法](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)的一個主要好處是，您可以使用 HTML5 本機儲存區，在下次載入此頁面時，系統會為使用者在本機上儲存導覽。 使用 search API for 結構性導覽，我們取得了重大效能的增強功能;不過，它需要一些技術功能才能執行及自訂此功能。

在 [範例的實施](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)中，網站的排序方式與現成的結構流覽的方式相同;字母順序。 如果您想要從這種順序中偏離，開發及維護的方式會比較複雜。 此外，此方法也需要您與支援的主版頁面的偏離。 如果未維護自訂主版頁面，您的網站將會錯過 Microsoft 對主版頁面所做的更新和改進功能。

上面的程式 [代碼](#about-the-javascript-file) 具有下列相依性：

- mobile https://jquery.com/
- KnockoutJS - https://knockoutjs.com/
- Linq.js https://linqjs.codeplex.com/ 或 github.com/neuecc/linq.js

目前的 LinqJS 版本不包含以上程式碼中使用的 ByHierarchy 方法，會中斷導覽程式碼。 若要修正此問題，請將下列方法新增至 Linq.js 檔案中的該行之前 `Flatten: function ()` 。

```javascript
ByHierarchy: function(firstLevel, connectBy, orderBy, ascending, parent) {
     ascending = ascending == undefined ? true : ascending;
     var orderMethod = ascending == true ? 'OrderBy' : 'OrderByDescending';
     var source = this;
     firstLevel = Utils.CreateLambda(firstLevel);
     connectBy = Utils.CreateLambda(connectBy);
     orderBy = Utils.CreateLambda(orderBy);

     //Initiate or increase level
     var level = parent === undefined ? 1 : parent.level + 1;

    return new Enumerable(function() {
         var enumerator;
         var index = 0;

        var createLevel = function() {
                 var obj = {
                     item: enumerator.Current(),
                     level : level
                 };
                 obj.children = Enumerable.From(source).ByHierarchy(firstLevel, connectBy, orderBy, ascending, obj);
                 if (orderBy !== undefined) {
                     obj.children = obj.children[orderMethod](function(d) {
                         return orderBy(d.item); //unwrap the actual item for sort to work
                     });
                 }
                 obj.children = obj.children.ToArray();
                 Enumerable.From(obj.children).ForEach(function(child) {
                     child.getParent = function() {
                         return obj;
                     };
                 });
                 return obj;
             };

        return new IEnumerator(

        function() {
             enumerator = source.GetEnumerator();
         }, function() {
             while (enumerator.MoveNext()) {
                 var returnArr;
                 if (!parent) {
                     if (firstLevel(enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }

                } else {
                     if (connectBy(parent.item, enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }
                 }
             }
             return false;
         }, function() {
             Utils.Dispose(enumerator);
         })
     });
 },

```
  
## <a name="related-topics"></a>相關主題

[SharePoint Server 中受管理導覽的概觀](/sharepoint/administration/overview-of-managed-navigation)

[結構導覽快取和效能](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)