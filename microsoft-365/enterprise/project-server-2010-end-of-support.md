---
title: Project伺服器2010的支援終止藍圖
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
description: Project Server 2010 的支援結束于2021年4月13日結束。 請使用本文做為升級至 Project Online 或 Project 伺服器內部部署的更新版本指南。
ms.openlocfilehash: 0ca37d00ee670a8a3f7c83d75864b5af19587951
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229752"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 終止支援藍圖

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Project伺服器2010會在 **2021 的4月13日** 到達支援服務。 此日期是從上一年10月13日的支援終止日（2020）延伸。 如果您目前使用 Project Server 2010，請注意，這些相關產品的支援終止日期如下：

|產品 |支援日期結束|
|---|---|
|Project 2010 Standard|2020 年 10 月 13 日|
|Project 2010 Professional|2020 年 10 月 13 日|

如需到達支援終止的詳細資訊，請參閱[從 Office 2010 伺服器及用戶端產品升級](plan-upgrade-previous-versions-office.md)。

## <a name="what-does-end-of-support-mean"></a>*支援終止的* 意義為何？

幾乎所有的 Microsoft 產品都有支援週期，在這種情況下，其可取得新功能、錯誤修正及安全性更新。 此生命週期一般會從產品的初始發行版本持續10年。 此週期的結尾稱為產品的支援終止。 在 Project Server 2010 在年4月 13 2021 日到達其支援終止後，Microsoft 將不再提供：

- 可能發生問題的技術支援。

- 針對所探索之問題的錯誤修正，而且可能會影響伺服器的穩定性和可用性。

- 已發現之弱點的安全性修正程式，可能會導致伺服器遭受安全性破壞。

- 時區更新。

Project Server 2010 的安裝會在此日期之後繼續執行。 不過，由於先前所列的變更，強烈建議您儘快從 Project Server 2010 進行遷移。

## <a name="what-are-my-options"></a>我有哪些選擇？

您的遷移選項包括：

- 遷移至 Project Online

- 遷移至更新的內部部署版本的 Project server (首選 Project Server 2019) 

以下是您可以採取的兩種途徑，以避免 Project Server 2010 的支援結束。

![Project伺服器2010升級路徑](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|為什麼我想要遷移至 Project Server 2019？|為什麼我想要遷移至 Project Online？|
|---|---|
|商務規則限制我在雲端中運作我的公司。  <br/><br/>  我需要控制環境的更新。|我有行動電話或遠端使用者。<br/><br/>  遷移內部部署伺服器所需的成本是 (硬體、軟體、時間和工作執行的重要考慮，如此等等。 ) 。 <br/><br/>  遷移後，維護環境所需的成本為 (的考慮，例如，自動更新、保證的執行時間等等) 。|

> [!NOTE]
> 如需遷移選項的詳細資訊，請參閱可[協助您從 Office 2010 伺服器及用戶端升級的資源](upgrade-from-office-2010-servers-and-products.md)。 請注意，Project server 不支援混合式設定，因為 Project Server 和 Project Online 不能共用相同的資源集區。

### <a name="what-are-my-options-for-project-client"></a>Project 用戶端有哪些選項？

如果您使用 Project 專業版2010或 Project 標準版2010，您的選項如下：

- 移至較新版本的 Project 專業版或 Project 標準版
- 移至線上方案，例如 web 的 Project Online 或 Project

#### <a name="move-to-a-newer-version-of-project-client"></a>移至較新版本的 Project 用戶端

如果您是從 Project 標準版2010遷移，您可以移至較新版本的 Project 標準版 (Project 標準版2016或 Project 標準版 2019) 。 建議您移至最新的版本，以充分利用最新的功能。 Project 標準版 2016) 遷移至目前的版本 (，也意味著您需要更快地遷移。

同樣地，如果您是從 Project 專業版2010遷移，您可以移至較新的版本 (Project 專業版2019或 Project 專業版 2016) 。 另外，請盡可能移至最新版本。 如果您使用 Project 專業版來連線至 Project 伺服器，請確定您要遷移至與您使用之 Project 伺服器版本連接的 Project 專業版版本。

Project 專業版2010使用者也可以遷移到 Project Online 的桌面用戶端，這是 Project 專業版2019的訂閱版本。 它包含在 Project 方案3和 Project 方案5訂閱中。

#### <a name="move-to-an-online-solution"></a>移至線上方案

您也可以從 Project 專業版2010或 Project 標準版2010遷移至 Project 訂閱型線上解決方案。 Project 方案3及 Plan 5 都包含 Project Online 和最新的雲端產品方案， [Project 網頁](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1)。 兩者都提供值得探索的新功能和優點。

如需功能和授權的詳細資訊，請參閱[Microsoft Project 服務描述](/office365/servicedescriptions/project-online-service-description/project-online-service-description)。

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>從 Project Server 2010 進行遷移時的重要考慮

當您規劃從 Project Server 2010 進行遷移時，請考慮下列事項：

- **從 Microsoft 解決方案供應商取得協助**-從 Project Server 2010 升級可能是一項挑戰。 它需要大量的準備工作和規劃。 如果您不是最初設定 Project Server 2010 的人員，可能特別有挑戰性。 您可以使用 Microsoft 解決方案提供者來協助您，是否要遷移至 Project Server 2019 或 Project Online。 在 [Microsoft 解決方案供應商中心](https://go.microsoft.com/fwlink/p/?linkid=841249)搜尋解決方案提供者。

- 在您的 Project Server 2010 環境中 **規劃自訂**-自訂專案時，當您遷移至 Project 伺服器2019或 Project Online 時，可能無法運作。 不同版本之間的 Project 伺服器架構有明顯的差異。 此外，使用版本的必要作業系統、資料庫伺服器及網頁瀏覽器也不同。 規劃如何在新環境中測試或重建自訂專案。 採取此機會判斷是否仍需要特定的自訂專案。 如需詳細資訊，請參閱＜[Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013)＞。

- **時間和耐心** 升級的規劃、執行及測試需要相當長的時間和精力，尤其是升級至 Project Server 2019。 若要從 Project server 2010 進行遷移，以 Project 伺服器2019，您必須先遷移至 Project Server 2013，檢查您的資料，然後遷移至 Project Server 2016，然後 Project 伺服器2019。 您可能想要與 Microsoft 解決方案提供者聯繫以取得協助的時間範圍和預估成本。

## <a name="migrate-to-project-online"></a>遷移至 Project Online

如果您選擇從 Project Server 2010 遷移至 Project Online，您可以遵循下列步驟手動遷移專案計劃資料：

1. 將專案方案從 Project Server 2010 儲存為 mpp 格式。

2. 使用 Project 專業版2016、Project 專業版2019或 Project Online 的桌面用戶端，開啟每一個 mpp 檔案，然後將它儲存併發布到 Project Online。

您可以在 (Project Online 中以手動方式建立 PWA 設定，例如，重新建立任何必要的自訂欄位或企業行事曆) 。 Microsoft 解決方案供應商也可協助您進行此程式。

主要資源：

|資源|描述|
|---|---|
|[Project Online 快速入門](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|如何設定及使用 Project Online|
|[Project Online 服務說明](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|可用之不同 Project Online 方案的相關資訊|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>遷移至更新的內部部署版本的 Project 伺服器

我們強烈相信您會透過遷移至 Project Online，取得最佳的價值和使用者經驗。 不過，我們也瞭解部分組織必須將專案資料保留在內部部署中。 如果您選擇將專案資料保留在內部部署中，您可以將 Project server 2010 環境遷移成 Project 伺服器2013、Project Server 2016 或 Project server 2019。

如果您無法遷移至 Project Online，建議您將遷移至 Project Server 2019。 Project伺服器2019包含舊版 Project Server 中的大部分重要功能。 而且它與 Project Online 搭配使用的體驗非常接近，不過某些功能只可用於 Project Online。

完成每項遷移後，請確定您的資料已順利遷移。

> [!NOTE]
> 如果您局限于內部部署解決方案，而且只考慮遷移至 Project Server 2013，請注意，此版本只會有幾年以上的支援。 Project Server 2013，含 Service Pack 2 十月13，2023的支援日期結束。 如需終止支援日期的詳細資訊，請參閱 [Microsoft 產品生命週期原則](/lifecycle/)。

### <a name="how-do-i-migrate-to-project-server-2019"></a>如何遷移至 Project 伺服器2019？

Project Server 2010 和 Project Server 2019 之間的架構差異，會防止直接的遷移路徑。 因此，您必須將 Project 的伺服器2010資料移轉至 Project 伺服器的每個連續版本，直到您進入 Project Server 2019 為止。 將 Project Server 2010 升級成 Project 伺服器2019的步驟：

1. 遷移至 Project Server 2013。

2. 從 Project 將2013遷移至 Project Server 2016。

3. 從 Project Server 2016 遷移至 Project 伺服器2019。

完成每項遷移後，請確定您的資料已順利遷移。

### <a name="step-1-migrate-to-project-server-2013"></a>步驟1：遷移至 Project Server 2013

如需從 Project Server 2010 升級至 Project 伺服器2013的完整資訊，請參閱[Upgrade to Project Server 2013](/project/upgrade-to-project-server-2016)。

主要資源：

- [Project Server 2013 升級程式的概述](/project/upgrade-to-project-server-2016)

  取得如何從 Project Server 2010 升級至 Project 伺服器2013的高階概述。
- [規劃升級為 Project Server 2013](/project/plan-for-upgrade-to-project-server-2016)

  從 Project Server 2010 升級至 Project 伺服器2013（包括系統需求）時，請查看規劃的考慮。

- [Project Server 2013 升級的新功能](/project/what-s-new-in-project-server-2013-upgrade)涵蓋此版本的重要變更，包括：

  - 沒有 Project Server 2013 的就地升級。 資料庫附加方法是唯一支援的方法，可以從 Project Server 2010 升級為 Project Server 2013。

  - 升級程式不會只會將 Project server 2010 資料轉換成 Project 伺服器2013格式，但也會將四個 Project Server 2010 資料庫合併成單一 Project Web App 資料庫。

  - SharePoint server 2013 和 Project Server 2013 都變更為先前版本的宣告式驗證。 如果您使用的是傳統驗證，當您升級時，必須考慮這一點。 如需詳細資訊，請參閱＜[在 SharePoint 2013 中從傳統模式移轉至宣告式驗證](/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013)＞。

主要資源：

- [升級到 Project Server 2013 的升級程序概觀](/project/overview-of-the-project-server-2016-upgrade-process)

- [升級您的資料庫與 Project Web App 網站集合 (Project Server 2013)](/project/upgrading-to-project-server-2016)

- [Microsoft Project伺服器升級過程圖表](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [卓越的資料庫整合，以8個簡單的步驟 Project Server 2010 至2013遷移](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>步驟2：遷移至 Project Server 2016

當您移至 Project Server 2013，並確認您的資料已成功遷移後，下一步是遷移至 Project Server 2016。

如需詳細資訊，請參閱[Upgrade to Project Server 2016](/Project/upgrade-to-project-server-2016)。

主要資源：

- [Project Server 2016 升級程序概觀](/Project/overview-of-the-project-server-2016-upgrade-process)

  瞭解從 Project Server 2013 升級為 Project Server 2016 所需執行的工作。

- [規劃升級到 Project Server 2016](/Project/plan-for-upgrade-to-project-server-2016)

  請參閱從 Project Server 2013 升級至 Project Server 2016 時所要進行的規劃考慮。

[Project Server 2016 升級所需注意的事項](/project/plan-for-upgrade-to-project-server-2016#thingknow)涵蓋升級至此版本的重要變更，包括：

- 當您建立 Project Server 2016 環境時，請注意，SharePoint Server 2016 中包含 Project Server 2016 安裝檔案。 如需詳細資訊，請參閱[Deploy Project Server 2016](/project/deploy-project-server-2016)。

- 資源計劃在 Project Server 2016 中已被取代。 您的 Project Server 2013 資源計劃將會遷移到 Project Server 2016 和 Project Online 中的資源預訂。 如需詳細資訊，請參閱 [綜述： Resource 預訂](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 。

### <a name="step-3-migrate-to-project-server-2019"></a>步驟3：遷移至 Project Server 2019

在您遷移至 Project Server 2016，並確認資料移轉成功之後，下一步是將資料移轉至 Project 伺服器2019。

若要瞭解從 Project Server 2016 升級為 Project Server 2019 所需的執行專案，請參閱[upgrade to Project Server 2019](/Project/upgrade-to-project-server-2016)。

主要資源：

- [Project Server 2019 升級程式的概述](/project/overview-of-the-project-server-2019-upgrade-process)

  深入瞭解從 Project Server 2013 升級為 Project Server 2016 時所需執行的動作。

- [規劃升級至 Project Server 2019](/project/plan-for-upgrade-to-project-server-2019)

  請參閱從 Project Server 2016 升級至 Project Server 2019 的規劃考慮。

- [Project Server 2019 升級所需注意的事項](/project/plan-for-upgrade-to-project-server-2016)<br/><br/>深入瞭解升級至此版本的重要變更，包括：

  - 升級程式會將您的資料從 Project Server 2016 資料庫移轉至 SharePoint Server 2019 內容資料庫。  Project伺服器2019將不再在 SharePoint 伺服器陣列中建立自己的 Project 伺服器資料庫。

  - 升級之後，請留意 Project Web App 中的數項變更。  如需詳細資訊，請參閱[Project Server 2019 的新功能](/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)。

**其他資源**：

- [Project Online 服務描述](/office365/servicedescriptions/project-online-service-description/project-online-service-description)：請參閱包含 Project Server 2016 和 Project Online 進階版的產品群組管理功能。

- [Microsoft Office Project 產品群組伺服器2010遷移指南](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>適用於 Office 2010 用戶端與伺服器和 Windows 7 的選項摘要

如需適用於 Office 2010 用戶端與伺服器和 Windows 7 的升級、移轉和移至雲端選項的視覺摘要，請參閱[終止支援海報](../downloads/Office2010Windows7EndOfSupport.pdf)。

[![Office 2010 用戶端和伺服器及 Windows 7 海報的支援結束](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

此海報說明您可以採取的各種途徑，以避免 Office 2010 用戶端和伺服器產品的支援終止，並 Windows 7，且 Microsoft 365 企業版反白顯示的慣用路徑和選項支援。

您也可以 [下載](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) 此標牌，並以 letter、法律或卡片 (11 x 17) 格式來列印。

## <a name="related-topics"></a>相關主題

[從 SharePoint 2010 升級](upgrade-from-sharepoint-2010.md)

[從 Office 2010 伺服器與用戶端升級](upgrade-from-office-2010-servers-and-products.md)
