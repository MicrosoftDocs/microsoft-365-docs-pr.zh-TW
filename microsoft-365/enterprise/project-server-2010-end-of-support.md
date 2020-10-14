---
title: Project Server 2010 終止支援藍圖
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
description: Project Server 2010 的支援結束于4月13日（2021）。 使用本文做為升級至 Project Online 或更新版本 Project Server 內部部署的指南。
ms.openlocfilehash: 2cf18c5e91c095c92230a33f1b8a19fa26840777
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464321"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 終止支援藍圖

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Project Server 2010 將于 **年4月 13 2021 日**到達支援終止。 此日期已從去年10月 13 2020 日的支援日期延伸。 如果您目前使用的是 Project Server 2010，請注意，這些其他相關產品的支援日期會有下列各項：

|產品 |支援日期結束|
|---|---|
|Project 2010 Standard|2020 年 10 月 13 日|
|Project 2010 專業版|2020 年 10 月 13 日|

如需適用于 Office 2010 伺服器的詳細資訊，請參閱 [升級至 office 2010 伺服器和用戶端產品](plan-upgrade-previous-versions-office.md)。

## <a name="what-does-end-of-support-mean"></a>終止支援是什麼意思？

Project Server 與幾乎所有的 Microsoft 產品一樣，都有一個支援週期，我們提供了新功能、錯誤修正及安全性更新。 產品的生命週期從首次發行日期算起，通常會持續 10 年，而這個生命週期的結束就稱為產品支援結束。 當 Project Server 2010 達到其在2021年4月13日的支援時，Microsoft 將無法再提供：

- 可能發生問題的技術支援。

- 針對所探索之問題的錯誤修正，而且可能會影響伺服器的穩定性和可用性。

- 已發現之弱點的安全性修正程式，可能會導致伺服器遭受安全性破壞。

- 時區更新。

在此日期之後，Project Server 2010 的安裝會繼續執行。 不過，由於以上所列的變更，強烈建議您儘早從 Project Server 2010 進行遷移。

## <a name="what-are-my-options"></a>我有哪些選擇？

如果您使用的是 Project Server 2010，您必須探索遷移選項，其中包括：

- 遷移至 Project Online

- 遷移至較新的內部部署版本的 Project Server (最好的 Project Server 2019) 。

以下是您可以採取的兩種途徑，以避免 Project Server 2010 的支援結束。

![Project Server 2010 升級路徑](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|為什麼我想要遷移至 Project Server 2019？|為什麼我想要遷移至 Project Online？|
|---|---|
|商務規則限制我在雲端中運作我的公司。  <br/>  我需要控制環境的更新。|我有行動電話或遠端使用者。  <br/>  遷移內部部署伺服器所需的成本是一個很重要的問題 (硬體、軟體、時間與工作的實施，等等 ) 。  <br/>  遷移後，維護環境所需的成本是一個很重要的問題 (例如，自動更新、保證的時間，等等 ) 。|

> [!NOTE]
> 如需從您的 Office 2010 伺服器移動選項的詳細資訊，請參閱 [協助您從 office 2010 伺服器及用戶端升級的資源](upgrade-from-office-2010-servers-and-products.md)。 請注意，Project Server 不支援混合式設定，因為 Project Server 和 Project Online 無法共用相同的資源集區。

### <a name="what-are-my-options-for-project-client"></a>我的 Project 用戶端選項為何？

如果您使用的是 Project Professional 2010 或 Project Standard 2010，且想要探索您的遷移選項，您可以選擇下列其中一項：

- 移至較新版本的 Project Professional 或 Project Standard。
- 移至線上方案，例如 Project Online 或 Web 專案。

#### <a name="moving-to-a-newer-version-of-project-client"></a>移至較新版本的 Project 用戶端

如果您是從 Project Standard 2010 遷移，您可以將專案 standard 2016 或 Project standard 2019) 的更新版本遷移至新的版本 (。  建議您移至最新的版本，以充分利用最新的功能。 此外，遷移至最新的版本 (Project Standard 2016) 表示您必須儘早從這個版本開始遷移，因為它的支援日期會隨之結束。

同樣地，如果您要從 Project Professional 2010 進行遷移，您可以選擇將版本遷移至較新的版本 (Project Professional 2019 或 Project Professional 2016) 。 建議您盡可能移至最新版本。  如果您使用 Project Professional 來連線至 Project Server，請確定您已遷移至 Project Professional 的版本，該版本支援與您所用之 Project Server 版本連線。

Project Professional 2010 使用者也可以選擇將遷移至 Project Online 桌面用戶端。 它是訂閱型版本的 Project Professional 2019，並包含在專案方案3和專案方案5訂閱中。

#### <a name="moving-to-an-online-solution"></a>移至線上方案

您也可以選擇從 Project Professional 2010 或 Project Standard 2010 遷移至專案的訂閱型線上解決方案。 這兩個專案方案3和方案5都包括 Project Online 及最新的雲端方案（ [適用于 web](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1)）。 這兩者都提供許多新的功能和優點。

如需兩者中所包含之功能的詳細資訊，以及其所包含的專案計劃授權，請參閱 [Microsoft Project service 描述](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description)。

## <a name="important-considerations-you-need-to-make-when-planning-to-migrate-from-project-server-2010"></a>規劃從 Project Server 2010 進行遷移時，所需注意的事項

當您規劃從 Project Server 2010 遷移時，您必須考慮下列事項：

- **從 Microsoft 解決方案供應商取得協助** -從 Project Server 2010 升級可能是一項挑戰，需要進行大量的準備與規劃。 如果您不是最初安裝及設定 Project Server 2010 的方式，可能特別有挑戰性。 值得慶倖的是，您可以將 Microsoft 解決方案供應商變成誰在生活中執行這項作業，不論您計畫要遷移至 Project Server 2019 或 Project Online。 您可以搜尋 Microsoft 解決方案供應商，協助您在 [microsoft 解決方案供應商中心](https://go.microsoft.com/fwlink/p/?linkid=841249)進行遷移。

- **規劃自訂** -請注意，遷移至 project server 2019 或 project Online 時，許多您在 Project server 2010 環境中所使用的自訂功能可能無法運作。 在不同版本之間的 Project Server 架構，以及支援的作業系統、資料庫伺服器及用戶端網頁瀏覽器之間，都有很大的差異，可與更新的版本搭配使用。 針對您在新環境中所需的自訂進行測試或重建的計畫。 規劃升級也是一種很好的機會，可在您向前推進時，確認是否真的需要特定的自訂專案。 [在升級期間建立目前自訂專案的計畫 SharePoint 2013]( https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013) 在升級時，有一些有關評估及規劃目前自訂專案的極佳一般資訊。

- **時間和耐心** 升級的規劃、執行及測試需要很長的時間和精力，尤其是當您要升級至 Project Server 2019 時。 例如，如果您要從 Project Server 2010 遷移至 Project Server 2019，您必須先從 Project Server 2010 遷移至 Project Server 2013，然後檢查您的資料，當您將每個後續版本 (遷移至 Project Server 2016，然後再進行) 的 Project Server 2019 時，請執行相同的動作。 您可能會想要與 Microsoft 解決方案提供者核對評估成本，使其達到估計成本的時間，以及其成本。

## <a name="migrate-to-project-online"></a>遷移至 Project Online

如果您選擇從 Project Server 2010 遷移至 Project Online，您可以執行下列動作以手動遷移專案計劃資料：

1. 將專案方案從 Project Server 2010 儲存至。MPP 格式。

2. 使用 Project Professional 2016、Project Professional 2019 或 Project Online 桌面用戶端，開啟每個副檔名檔案，然後將其儲存併發布到 Project Online。

您可以在 Project Online 中以手動方式建立 PWA 設定 (例如，重新建立任何必要的自訂欄位或企業行事曆) 。 Microsoft 解決方案供應商也可協助您進行這種情況。

主要資源：

|資源|描述|
|---|---|
|[Project Online 快速入門](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|如何設定和使用 Project Online。|
|[Project Online 服務說明](https://go.microsoft.com/fwlink/p/?linkid=829088)|可供您使用之不同 Project Online 方案的相關資訊。|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>遷移至較新的內部部署版本的 Project Server

雖然我們極力相信您可以透過遷移至 Project Online，獲得最佳價值和使用者經驗，我們也會瞭解某些組織必須將專案資料保留在內部部署環境中。 如果您選擇將專案資料保留在內部部署中，您可以將 Project Server 2010 環境遷移至 Project Server 2013、Project Server 2016 或 Project Server 2019。

如果您無法遷移至 Project Online，建議您將遷移至 Project Server 2019。 Project Server 2019 包含舊版 Project Server 隨附的功能和增強功能，以及與 Project Online 搭配使用的經驗最為接近的功能 (不過某些功能只有在 Project Online) 中才能使用。

完成每個遷移後，您應該檢查資料，以確定其已成功遷移。

> [!NOTE]
> 如果您僅考慮遷移至 Project Server 2013 （如果您僅限內部部署解決方案），請務必注意，左側只會有幾年的支援。 Project Server 2013 Service Pack 2 結束支援日期為10/13/2023。 如需有關支援日期結束的詳細資訊，請參閱 [Microsoft 產品生命週期原則](https://go.microsoft.com/fwlink/p/?linkid=842066)。

### <a name="how-do-i-migrate-to-project-server-2019"></a>如何遷移至 Project Server 2019？

Project Server 2010 與 Project Server 2019 之間的架構差異，可防止直接遷移路徑。 這表示，您必須將 Project Server 2010 資料移轉至下一個後續的 Project Server 版本，直到您升級至 Project Server 2019 為止。

您必須執行下列步驟，將 Project Server 2010 升級為 Project Server 2019：

1. 遷移至 Project Server 2013。

2. 從 Project 將2013遷移至 Project Server 2016。

3. 從 Project Server 2016 遷移至 Project Server 2019。

完成每個遷移後，您應該檢查資料，以確定其已成功遷移。


### <a name="step-1-migrate-to-project-server-2013"></a>步驟1：遷移至 Project Server 2013

將 Project Server 2010 資料移轉至 Project server 2019 的第一步，是先遷移至 Project Server 2013。

若要全面瞭解從 Project Server 2010 升級至 Project Server 2013 所需執行的工作，請參閱 [升級至 Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)。

主要資源：

- [Project Server 2013 升級程式概述](https://go.microsoft.com/fwlink/p/?linkid=841822)

  深入瞭解從 Project Server 2010 升級至 Project Server 2013 所需執行的動作。
- [規劃升級到 Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823)

  請查看從 Project Server 2010 升級至 Project Server 2013 時所需進行的規劃考慮，包括系統需求。

[Project Server 2013 升級的新功能](https://go.microsoft.com/fwlink/p/?linkid=841824) 會告訴您，在此版本中升級的一些重要變更，最為明顯的：

- 沒有就地升級至 Project Server 2013。 資料庫附加方法是唯一支援的方法，可從 Project Server 2010 升級至 Project Server 2013。

- 升級程式不僅會將您的 Project Server 2010 資料轉換成 Project Server 2013 格式，還會將這四個 Project Server 2010 資料庫合併成單一 Project Web App 資料庫。

- SharePoint Server 2013 和 Project Server 2013 都變更為先前版本的宣告式驗證。 如果您使用的是傳統驗證，則必須考慮進行升級。 如需詳細資訊，請參閱＜[在 SharePoint 2013 中從傳統模式移轉至宣告式驗證]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013)＞。

主要資源：

- [升級到 Project Server 2013 的升級程序概觀](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [升級您的資料庫與 Project Web App 網站集合 (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [Microsoft Project Server 升級過程圖表](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [極佳的資料庫整合，Project Server 2010 至2013遷移，8個簡單的步驟](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>步驟2：遷移至 Project Server 2016

在遷移至 Project Server 2013 並確認您的資料已成功遷移後，下一步是將您的資料移轉至 Project Server 2016。

若要全面瞭解從 Project Server 2013 升級至 Project Server 2016 所需執行的工作，請參閱 [升級至 Project server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)。

主要資源：

- [Project Server 2016 升級程序概觀](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  深入瞭解從 Project Server 2013 升級至 Project Server 2016 所需執行的動作。

- [規劃升級到 Project Server 2016](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  請參閱從 Project Server 2013 升級至 Project Server 2016 時，所需的規劃考慮。

[您需要瞭解的 Project Server 2016 升級相關事項](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) ，可告訴您一些重要的變更可升級至此版本，其中包括：

- 當您建立要遷移 Project Server 2013 資料的 Project Server 2016 環境時，請注意，Project Server 2016 安裝檔會包含在 SharePoint Server 2016 中。 如需詳細資訊，請參閱 [部署 Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829)。

- 資源計劃在 Project Server 2016 中已被取代。 您的 Project Server 2013 資源計劃將遷移至 Project Server 2016 和 Project Online 中的資源預訂。 如需詳細資訊，請參閱 [綜述： Resource 預訂](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 。

### <a name="step-3-migrate-to-project-server-2019"></a>步驟3：遷移至 Project Server 2019

在遷移至 Project Server 2016 並確認您的資料已成功遷移後，下一步是將您的資料移轉至 Project Server 2019。

若要全面瞭解從 Project Server 2016 升級至 Project Server 2019 所需執行的工作，請參閱 [升級至 Project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)。

主要資源：

- [Project Server 2019 升級程式概述](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  深入瞭解從 Project Server 2013 升級至 Project Server 2016 所需執行的動作。

- [規劃升級至 Project Server 2019](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  請參閱從 Project Server 2016 升級至 Project Server 2019 時，所需的規劃考慮。

[您需要瞭解的 Project Server 2019 升級相關事項](https://go.microsoft.com/fwlink/p/?linkid=841827) ，可告訴您一些重要的變更可升級至此版本，其中包括：

- 升級程式會將您的資料從 Project Server 2016 資料庫移轉至 SharePoint 伺服器2019內容資料庫。  Project Server 2019 將不再在 SharePoint 伺服器陣列中建立自己的 Project Server 資料庫。

- 升級之後，請留意 Project Web App 中的數項變更。  如需這些功能的說明，請參閱 [Project Server 2019 的新功能](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)。

**其他資源**：

- [Project Online 服務說明](https://go.microsoft.com/fwlink/p/?linkid=841280)：請參閱 project Server 2016 和 Project Online Premium 隨附的公事包管理功能。

- [Microsoft Office 專案公事包伺服器2010遷移指南](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>適用於 Office 2010 用戶端與伺服器和 Windows 7 的選項摘要

如需適用於 Office 2010 用戶端與伺服器和 Windows 7 的升級、移轉和移至雲端選項的視覺摘要，請參閱[終止支援海報](../downloads/Office2010Windows7EndOfSupport.pdf)。

[![Office 2010 用戶端與伺服器和 Windows 7 終止支援海報的影像](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

這張單頁海報可讓您快速了解可以採取的各種方法，以防止Office 2010 用戶端與伺服器產品以及 Windows 7 進入終止支援，而海報上也會強調顯示 Microsoft 365 企業版中慣用的方式和選項支援。

您可以[下載](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf)此海報，並以 Letter、Legal 或 Tabloid (11 x 17) 格式列印此海報。

## <a name="related-topics"></a>相關主題

[從 SharePoint 2010 升級](upgrade-from-sharepoint-2010.md)

[從 Office 2010 伺服器與用戶端升級](upgrade-from-office-2010-servers-and-products.md)
