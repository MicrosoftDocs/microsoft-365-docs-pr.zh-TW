---
title: Microsoft 365 中的高級 eDiscovery 解決方案概述
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 深入瞭解 Microsoft 365 中的高級 eDiscovery 解決方案。 本文概要說明 Microsoft 365 中的高級 eDiscovery，這是協助您管理內部及外部調查的工具。 它也可讓您使用高級 eDiscovery 來管理法律調查的商業原因。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1b2fa0b42a7f439aa65ae53e76e377ded92f97b7
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840876"
---
# <a name="overview-of-microsoft-365-advanced-ediscovery"></a>Microsoft 365 Advanced eDiscovery 概述

Microsoft 365 中的「高級 eDiscovery 解決方案」是以現有的 Microsoft eDiscovery 和分析功能為基礎。 Advanced eDiscovery 提供端對端的工作流程，可保留、收集、分析、審閱、分析及匯出回應組織內部和外部調查的內容。 它也可讓法律團隊管理整個法律封存通知工作流程，以與案例中的保管人進行通訊。

「高級 eDiscovery」可協助您的組織透過發現其所在的資料來回應法律問題或內部調查。 您可以透過找出感興趣的人員及其資料來源，以無縫方式套用保留以保留資料，然後管理合法暫止通訊程式，以順利管理 eDiscovery 工作流程。 透過從來源收集資料，您可以搜尋即時的 Microsoft 365 平臺，以快速找到您需要的專案。 智慧、機器學習功能（如深入索引、電子郵件執行緒及近期重複偵測）也可協助您將大量資料降至相關的資料集。

下列各節說明這些高級 eDiscovery 功能可如何協助您的組織。

## <a name="discover-and-collect-data-in-place"></a>探索及收集就地資料

傳統上，依賴多個協力廠商 eDiscovery 解決方案的組織，需要從 Microsoft 365 複製大量的資料以處理，並必須存放重複的資料。 這項必要條件可增加尋找相關資料的時間，以及管理多個解決方案的風險、成本和複雜性。

Microsoft 365 中的「高級 eDiscovery」可讓您探索來源中的資料，並保持在您的 Microsoft 365 安全性和合規性界限內。  透過從即時系統收集資料，「高級 eDiscovery」可減少回到來源的摩擦，並減少需要找出遺失內容的不必要工作，這通常是在傳統 eDiscovery 解決方案中的日誌記錄滯後時發生。

在團隊、Yammer、SharePoint Online、商務 OneDrive 和 Exchange Online 中，資料的原生搜尋與收集功能會進一步增強資料探索。 例如，「高級 eDiscovery」：

- 重新建立小組交談 (，而不是傳回從交談) 中的個別郵件。

- 透過電子郵件訊息和團隊聊天中的連結或新式附件，收集與使用者共用的雲端式內容。

- 具有數百個非 Microsoft 365 檔案類型的內建支援。

- 會收集協力廠商來源的資料 (例如 Bloomberg、Facebook、寬限時間及縮放會議) ，這些會議是透過 [資料連線器](archiving-third-party-data.md)匯入和封存于 Microsoft 365。

## <a name="manage-ediscovery-workflow-in-one-platform"></a>在單一平臺中管理 eDiscovery 工作流程

「高級 eDiscovery」可協助您減少所需依賴的 eDiscovery 解決方案數目。 它提供簡化的端對端工作流程，所有這些工作流程都會在 Microsoft 365 內進行。 「高級 eDiscovery」會透過自動將唯一和共用資料來源對應至 (稱為 *保管人*) 的相關人員，以及在收集資料以進行分析和審閱之前，先提供報表和分析，以減少識別及收集相關資訊來源的摩擦。

此外，Microsoft Graph APIs 可協助您自動化 eDiscovery 工作流程，並擴充自訂解決方案的高級 eDiscovery。

## <a name="cull-data-intelligently"></a>智慧挑選資料

Advanced eDiscovery 中的智慧機學習功能可協助您減少要檢查的資料量。 這些智慧功能可協助您減少及挑選大量的資料至相關集。 例如，內建的審閱集查詢可識別重複的重複專案，以協助只為唯一的內容篩選。 這項功能可大幅減少要檢查的資料量。

其他機器學習功能可進一步精煉及識別使用智慧標籤和技術協助審閱工具（如相關性模組）的相關資料。

## <a name="advanced-ediscovery-architecture"></a>高級 eDiscovery 架構

以下是一種可顯示單一地理位置環境和多地理位置環境中的端對端工作流程的高級 eDiscovery 架構圖表，以及與「 [電子探索參考模型](advanced-ediscovery-edrm.md) 」（ (EDRM) ）對齊的端對端資料流程。

[![模型海報： Microsoft 365 中的高級 eDiscovery 架構](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[以影像形式查看](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[下載為 PDF 檔案](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[下載為 Visio 檔案](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)

如需有關在高級 eDiscovery 中的端對端工作流程的詳細資訊，請參閱這段 [Microsoft 的機械影片](https://go.microsoft.com/fwlink/?linkid=2066133)。

## <a name="advanced-ediscovery-workflow"></a>高級 eDiscovery 工作流程

下列各節說明 Microsoft 365 規範中心內的高級 eDiscovery 工具內建工作流程中的每個步驟。 下列螢幕擷取畫面顯示名為 *2020.11.03-Contoso v.* 案例的 [**一覽表**] 索引標籤。

![內建的高級 eDiscovery 工作流程中的索引標籤](../media/AeD-Case-Screenshot1.png)

如需詳細資訊，請參閱 [Manage The Advanced eDiscovery workflow](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)。

### <a name="managing-custodians-and-non-custodial-data-sources"></a>管理保管人和非 custodial 資料來源

您可以使用 [ **資料來源** ] 索引標籤，新增及管理您已在案例中的利益人員，以及可能未與保管人相關聯之其他資料來源的人員。 當您新增保管人或非 custodial 資料來源時，您可以快速執行諸如對保管人和非 custodial 資料來源進行合法保留、與保管人進行通訊，以及搜尋保管人和非 custodial 資料來源的動作，以收集與案例相關的內容。 隨著案例的進展，您可以輕鬆地新增保管人或非 custodial 日期來源，或從案例發行。 如需詳細資訊，請參閱使用 [保管人](managing-custodians.md)。

### <a name="managing-legal-hold-notifications"></a>管理合法保留通知

在案例中，使用 [ **通訊** ] 索引標籤來管理與保管人進行通訊的處理常式。 法律保留通知會指示保管人保留與案例相關的任何內容。 法律團隊必須能夠追蹤由保管人接收、讀取及認可的通知。 「高級 eDiscovery」中的通訊工作流程可讓您建立及傳送初始通知、提醒、發行通知，以及在保管人無法認可保留通知時進行升級。 如需詳細資訊，請參閱 [使用通訊](managing-custodian-communications.md)。

### <a name="managing-content-preservation"></a>管理內容保留

當您將系統管理員新增至案例時，您可以在 custodial 資料上進行保留。 使用 [ **保留** ] 索引標籤可管理在您新增保管人時所建立的保留，以及管理與案例相關的其他法律保留;例如，您可以識別並對非 custodial 資料來源進行保留。 您也可以編輯案例中的任何保留，並讓它成為查詢型保留，只保留符合查詢的內容。 例如，您可以將日期範圍新增至保留，只保留在特定日期範圍內建立的內容。 您也可以取得暫止內容的統計資料，並在不再與案例相關後移除保留，或加以刪除。 如需詳細資訊，請參閱 [管理保留](managing-holds.md)。

### <a name="indexing-custodian-data"></a>索引保管人資料

當您將保管人和對應的 custodial 資料來源新增至案例時，來自保管人資料來源的任何已編制索引的專案都會由稱為「 *高級索引*」的處理常式來重新編制索引。 這可讓您執行搜尋來收集資料時，custodial 內容（如影像、不支援的檔案類型，以及其他可能未編制索引的內容，以完全可供搜尋）。 使用 [ **處理** ] 索引標籤，監控高級索引的狀態，並使用稱為「 *錯誤修正*」的處理常式修正處理錯誤。 如需詳細資訊，請參閱 [修正處理錯誤](processing-data-for-case.md)。

### <a name="collecting-case-data"></a>收集案例資料

使用 [ **搜尋** ] 索引標籤來建立搜尋，以搜尋與案例相關之內容的就地 custodial 和非 custodial 資料來源。 您可以使用關鍵字和) 條件來建立及執行查詢型搜尋 (，以識別一組與案例相關的電子郵件訊息和檔，以及您想要在 eDiscovery 工作流程的後續步驟中進一步複查及分析的檔。 您可以建立一個或多個與案例相關聯的搜尋。 您也可以使用搜尋工具來預覽範例檔，並查看搜尋統計資料，以協助您優化和改善搜尋結果。 當您認為搜尋結果包含與案例相關的所有資料時，您可以將搜尋結果新增至審閱集，以便進一步複查、分析和剔除。 如需詳細資訊，請參閱 [收集案例的資料](collecting-data-for-ediscovery.md)。

### <a name="reviewing-and-analyzing-case-data"></a>檢查及分析案例資料

使用 [ **檢查集合** ] 索引標籤，以複查及分析您從即時系統收集到的內容，並將其新增至審閱集。 *審閱集* 是該資料的靜態集合，也就是資料的離線 () 複本 (，也就是您在 eDiscovery 工作流程的先前階段中收集的非 custodial 資料) （如果適用）。 當您將搜尋結果新增至審閱集時，會觸發處理常式以從容器提取檔案、提取中繼資料，以及提取文字。 完成此程式後，系統會為所有從保管人收集的資料建立新的索引，並將其新增至審閱集。 將資料新增至審閱集之後，您可以執行更多的查詢來縮小案例資料、以文字形式或原生檔案格式查看資料，以及在審閱集中批註、標記密文及標記檔。 您也可以執行高級分析，例如識別檔重複、電子郵件執行緒及主題。 在您只 culled 資料與案例相關的資料之後，您可以直接下載檔案或連同檔案中繼資料、批註及任何標記一起匯出。 如需詳細資訊，請參閱：

- [檢視檢閱集中的文件](view-documents-in-review-set.md)

- [查詢檢視集中的資料](review-set-search.md)

- [標記檢閱集中的文件](tagging-documents.md)

- [分析審閱集中的資料](analyzing-data-in-review-set.md)

### <a name="exporting-data-for-review-and-presentation"></a>匯出資料以供審閱及簡報

在您從複查集匯出資料後，請使用 [ **匯出** ] 索引標籤來管理匯出工作，並從審閱集中下載資料。 當您匯出審閱集時，會將資料上傳至 Microsoft 提供的 Azure 存放位置， (或您的組織所管理的 Azure 儲存體位置) 。 將其上傳至 Azure 後，它就可以下載到本機電腦。 您可以在 [ **匯出** ] 索引標籤上，取得下載匯出資料所需的儲存評估金鑰。如需詳細資訊，請參閱 [匯出案例資料](exporting-data-ediscover20.md)。

### <a name="managing-jobs"></a>管理工作

使用 [ **工作** ] 索引標籤，針對您已啟動的案例相關工作，監視長期執行的處理常式。 工作範例包括與重設索引、搜尋及匯出案例資料相關的範例。 例如，如果您在包含許多資料來源的 [ **搜尋** ] 索引標籤上建立搜尋，該搜尋程式的狀態將會顯示在 [ **工作** ] 索引標籤上。如需詳細資訊，請參閱 [管理工作](managing-jobs-ediscovery20.md)。

### <a name="configuring-case-settings"></a>設定案例設定

使用 [ **設定** ] 索引標籤來設定全案例設定。 這包括新增成員至案例、關閉或刪除案例，以及設定搜尋及分析設定。 如需詳細資訊，請參閱：

- [新增成員至案例](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

- [關閉或刪除案例](close-or-delete-case.md)

- [設定搜尋和分析設定](configure-search-and-analytics-settings-in-advanced-ediscovery.md)
