---
title: Microsoft 365 中的高級 eDiscovery 解決方案概述
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文概要說明 Microsoft 365 中的高級 eDiscovery，以及內部及外部調查的工具。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6225411bcd3051c19e22fcb205cc7dee92f99f82
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131026"
---
# <a name="overview-of-the-advanced-ediscovery-solution-in-microsoft-365"></a>Microsoft 365 中的高級 eDiscovery 解決方案概述

Microsoft 365 中的「高級 eDiscovery 解決方案」是以 Office 365 中現有的 eDiscovery 和分析功能為基礎。 這個新的解決方案稱為「 *高級 eDiscovery*」，提供了端對端工作流程，可保留、收集、審閱、分析及匯出回應組織內部和外部調查的內容。 它也可讓法律團隊管理整個法律封存通知工作流程，以與案例中的保管人進行通訊。 

> [!NOTE]
> 「高級 eDiscovery」需要 Office 365 或 Microsoft 365 E5 Enterprise 訂閱。 如需有關高級 eDiscovery 授權的詳細資訊，請參閱 [Microsoft 365 授權指南以取得安全性 & 合規性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-ediscovery)。

## <a name="alignment-with-edrm"></a>與 EDRM 對齊

Advanced eDiscovery 的內建工作流程會與「電子探索」參考模型 (EDRM) 所述的 eDiscovery 程式對齊。 

![「電子探索參考模型 (EDRM) ](../media/EDRMv1.png)

 (圖像來源 edrm.net。 來源影像可在 [創造性 Commons 歸屬 3.0 Unported 授權] 下取得。 ) 

在高層次上，以下是 Advanced eDiscovery 如何支援 EDRM 工作流程的方式：

- **識別。** 在您找出調查中潛在感興趣的人員之後，您可以將其新增為保管人 (也稱為「 *資料保管人*」，因為它們可能具有與調查) 相關的資訊，以供高級 eDiscovery 案例使用。 在您識別保管人並將其新增至案例之後，您可以輕鬆地保留、收集、審閱及分析相關聯的 custodial 資料。

- **保存。** 為了保留及保護與調查相關的資料，「高級 eDiscovery」可讓您在案例中對保管人相關聯的資料來源進行合法保留。 您也可以將非 custodial 資料置於保留狀態 (通常是共用群組資源，例如 SharePoint 網站或共用小組頻道) 。 Advanced eDiscovery 也有內建的通訊工作流程，因此您可以將法律封存通知傳送給保管人，並追蹤其確認。

- **收集。** 在您識別 (並選擇性地保留) 與調查相關的資料來源之後，您可以使用高級 eDiscovery 中的內建搜尋工具，在 custodial 資料來源 (和非 custodial 資料來源中搜尋即時資料，如果可能與案例相關的) 也適用。

- **處理。** 在您收集所有與案例相關的資料之後，下一步是處理它以進一步複查和分析。 在 [Advanced eDiscovery] 中，您在集合階段中所識別的就地資料會複製到 Azure 存放區位置， (稱為「 *複查集* 」) ，可為您提供案例資料的靜態視圖。

- **檢討。** 將資料新增至審閱集後，您就可以查看特定檔，並在評審集內執行其他查詢，以將資料降至最相關的檔。 您也可以批註及標記特定檔。

- **分析。** 「高級 eDiscovery」提供一組強大的整合分析工具，可協助您巧妙地挑選出不相關的資料與審查集，這可節約您的法律考評成本，其可節約實際生產的相關資料量。

- **生產** 及 **簡報。** 當您準備好時，您可以從審閱集中匯出檔，以進行法律考評。 您可以以 EDRM 指定的格式匯出檔，以便將其匯入協力廠商的審閱應用程式。

## <a name="advanced-ediscovery-architecture"></a>高級 eDiscovery 架構

以下是一種高級 eDiscovery 架構圖表，顯示單一地理位置環境和多地理位置環境中的端對端工作流程。 端對端的資料流程會與 EDRM 對齊。

[![模型海報： Microsoft 365 中的高級 eDiscovery 架構](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[以影像形式查看](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[下載為 PDF 檔案](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[下載為 Visio 檔案](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)

如需有關在高級 eDiscovery 中的端對端工作流程的詳細資訊，請參閱這段 [Microsoft 的機械影片](https://go.microsoft.com/fwlink/?linkid=2066133)。

下列各節將說明在高級 eDiscovery 中內建工作流程中的每個步驟。 下列螢幕擷取畫面顯示名為 *2020.11.03-Contoso v.* 案例的 [**一覽表**] 索引標籤。

![內建的高級 eDiscovery 工作流程中的索引標籤](../media/AeD-Case-Screenshot1.png)

## <a name="managing-custodians-and-non-custodial-data-sources"></a>管理保管人和非 custodial 資料來源

您可以使用 [ **資料來源** ] 索引標籤，新增及管理您已在案例中的利益人員，以及可能未與保管人相關聯之其他資料來源的人員。 當您新增保管人或非 custodial 資料來源時，您可以快速執行諸如對保管人和非 custodial 資料來源進行合法保留、與保管人進行通訊，以及搜尋保管人和非 custodial 資料來源的動作，以收集與案例相關的內容。 隨著案例的進展，您可以輕鬆地新增保管人或非 custodial 資料來源，或從案例發行。 如需詳細資訊，請參閱 [Advanced eDiscovery 中的使用保管人](managing-custodians.md)。

## <a name="managing-legal-hold-notifications"></a>管理合法保留通知

在案例中，使用 [ **通訊** ] 索引標籤來管理與保管人進行通訊的處理常式。 法律保留通知會指示保管人保留與案例相關的任何內容。 法律團隊必須追蹤由保管人接收、讀取及認可的通知。 「高級 eDiscovery」中的通訊工作流程可讓您建立及傳送初始通知、提醒、發行通知，以及在保管人無法認可保留通知時進行升級。 如需詳細資訊，請參閱使用 [高級 eDiscovery 中的通訊](managing-custodian-communications.md)。

## <a name="managing-content-preservation"></a>管理內容保留

當您將系統管理員新增至案例時，您可以在 custodial 資料上進行保留。 使用 [ **保留** ] 索引標籤可管理當您新增保管人和管理其他與案例相關的法律封存時所建立的保留;例如，您可以識別並對非 custodial 資料來源進行保留。 您也可以編輯案例中的任何保留，並讓它成為查詢型保留，只保留符合查詢的內容。 例如，您可以將日期範圍新增至保留，只保留在特定日期範圍內建立的內容。 您也可以取得暫止內容的統計資料，並在不再與案例相關後移除保留，或加以刪除。 如需詳細資訊，請參閱 [Manage 封存 In Advanced eDiscovery](managing-holds.md)。

## <a name="indexing-custodian-data"></a>索引保管人資料

當您將保管人和對應的 custodial 資料來源新增至案例時，來自保管人資料來源的任何已編制索引的專案都會由稱為「 *高級索引*」的處理常式來重新編制索引。 這可讓您執行搜尋來收集資料時，custodial 內容（如影像、不支援的檔案類型，以及其他可能未編制索引的內容，以完全可供搜尋）。 使用 [ **處理** ] 索引標籤，監控高級索引的狀態，並使用稱為「 *錯誤修正*」的處理常式修正處理錯誤。 如需詳細資訊，請參閱 [在高級 eDiscovery 中修正處理錯誤](processing-data-for-case.md)。

## <a name="collecting-case-data"></a>收集案例資料

使用 [ **搜尋** ] 索引標籤來建立搜尋，以搜尋與案例相關之內容的就地 custodial 和非 custodial 資料來源。 您可以使用關鍵字和) 條件來建立及執行查詢型搜尋 (，以識別一組與案例相關的電子郵件訊息和檔，以及您想要在 eDiscovery 工作流程的後續步驟中進一步複查及分析的檔。 您可以建立一個或多個與案例相關聯的搜尋。 您也可以使用搜尋工具來預覽範例檔，並查看搜尋統計資料，以協助您優化和改善搜尋結果。 在搜尋及收集所有與案例相關的資料之後，您可以將搜尋結果新增至審閱集，以便進一步複查、分析和剔除。 如需詳細資訊，請參閱 [在高級 eDiscovery 中收集案例的資料](collecting-data-for-ediscovery.md)。

## <a name="reviewing-and-analyzing-case-data"></a>檢查及分析案例資料

使用 [ **檢查集合** ] 索引標籤，以複查及分析您從即時系統收集到的內容，並將其新增至審閱集。 *審閱集* 是該資料的靜態集合，也就是資料的離線 () 複本 (，也就是您在 eDiscovery 工作流程的先前階段中收集的非 custodial 資料) （如果適用）。 當您將搜尋結果新增至審閱集時，會觸發處理常式以從容器提取檔案、提取中繼資料，以及提取文字。 完成此程式後，系統會為所有從保管人收集的資料建立新的索引，並將其新增至審閱集。 將資料新增至審閱集之後，您可以執行更多的查詢來縮小案例資料、以文字形式或原生檔案格式查看資料，以及在審閱集中批註、標記密文及標記檔。 您也可以執行高級分析，例如識別檔重複、電子郵件執行緒及主題。 在您只 culled 資料與案例相關的資料之後，您可以直接下載檔案或連同檔案中繼資料、批註及任何標記一起匯出。 如需詳細資訊，請參閱：

- [檢視檢閱集中的文件](view-documents-in-review-set.md)

- [查詢檢視集中的資料](review-set-search.md)

- [標記檢閱集中的文件](tagging-documents.md)

- [分析審閱集中的資料](analyzing-data-in-review-set.md)

## <a name="exporting-data-for-review-and-presentation"></a>匯出資料以供審閱及簡報

在您從複查集匯出資料後，請使用 [ **匯出** ] 索引標籤來管理匯出工作，並從審閱集中下載資料。 當您匯出審閱集時，會將資料上傳至 Microsoft 提供的 Azure 存放位置， (或您的組織所管理的 Azure 儲存體位置) 。 將其上傳至 Azure 後，它就可以下載到本機電腦。 您可以在 [ **匯出** ] 索引標籤上，取得下載匯出資料所需的儲存存取機碼。如需詳細資訊，請參閱 [在高級電子檔探索中匯出案例資料](exporting-data-ediscover20.md)。

## <a name="managing-jobs"></a>管理工作

使用 [ **工作** ] 索引標籤，針對您已啟動的案例相關工作，監視長期執行的處理常式。 工作範例包括與重設索引、搜尋及匯出案例資料相關的範例。 例如，如果您在包含許多資料來源的 [ **搜尋** ] 索引標籤上建立搜尋，該搜尋程式的狀態將會顯示在 [ **工作** ] 索引標籤上。如需詳細資訊，請參閱 [在高級 eDiscovery 中管理工作](managing-jobs-ediscovery20.md)。

## <a name="configuring-case-settings"></a>設定案例設定

使用 [ **設定** ] 索引標籤來設定全案例設定。 這包括新增成員至案例、關閉或刪除案例，以及設定搜尋及分析設定。
