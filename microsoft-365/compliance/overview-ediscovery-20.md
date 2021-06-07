---
title: Microsoft 365 中的 Advanced eDiscovery 解決方案概況
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
- m365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: 深入瞭解 Microsoft 365 中的 Advanced eDiscovery 解決方案。 本文概要說明 Microsoft 365 中的 Advanced eDiscovery，它是協助您管理內部及外部調查的工具。 它也可讓您使用 Advanced eDiscovery 來管理您的法律調查的商業原因。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ec5ea7b32abb03edd31ab69abc7b8d3044b1d353
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782786"
---
# <a name="overview-of-microsoft-365-advanced-ediscovery"></a>Microsoft 365 Advanced eDiscovery 概述

Microsoft 365 中的 Advanced eDiscovery 解決方案是針對現有的 Microsoft eDiscovery 和分析功能而建立的。 Advanced eDiscovery 提供的端對端工作流程，可保留、收集、分析、審閱及匯出回應組織內部和外部調查的內容。 此外也可讓您的法律小組管理整個法務保存措施工作流程，以與涉及案例的監管人通訊。

## <a name="advanced-ediscovery-capabilities"></a>Advanced eDiscovery 功能

Advanced eDiscovery 可協助您的組織透過發現其所在的資料來回應法律問題或內部調查。 您可以透過找出感興趣的人員及其資料來源，以無縫方式套用保留以保留資料，然後管理合法暫止通訊程式，以順利管理 eDiscovery 工作流程。 透過從來源收集資料，您可以搜尋 live Microsoft 365 平臺，以快速找到您需要的專案。 智慧、機器學習功能（如深入索引、電子郵件執行緒及近期重複偵測）也可協助您將大量資料降至相關的資料集。

下列各節說明這些 Advanced eDiscovery 功能可如何協助您的組織。

![Advanced eDiscovery 功能](../media/advanced-ediscovery-capabilities.png)

### <a name="discover-and-collect-data-in-place"></a>探索及收集就地資料

傳統上，依賴多個協力廠商 eDiscovery 解決方案的組織，需要從 Microsoft 365 複製大量資料，以處理及不得不存放重複的資料。 這項必要條件可增加尋找相關資料的時間，以及管理多個解決方案的風險、成本和複雜性。

Microsoft 365 中的 Advanced eDiscovery 可讓您探索來源中的資料，並保持在您的 Microsoft 365 安全性和合規性界限內。  透過從即時系統收集資料，Advanced eDiscovery 減少了回到來源的摩擦，並減少了不得不尋找遺失內容的不必要工作，這通常會在傳統 eDiscovery 解決方案中的日誌記錄滯後時進行。

在 Teams 中的資料、Yammer、SharePoint 線上、商務用 OneDrive 及 Exchange Online 的原生搜尋與收集功能可進一步增強資料探索。 例如，Advanced eDiscovery：

- 重新建立 Teams 交談 (，而不是傳回從交談) 中的個別郵件。

- 透過電子郵件訊息中的連結或新式附件，收集與使用者共用的雲端架構內容，並 Teams 聊天。

- 具有數百個非 Microsoft 365 檔案類型的內建支援。

- 會收集協力廠商 (來源的資料，例如 Bloomberg、Facebook、寬限時間及縮放會議) ，該會議會在[資料連線器](archiving-third-party-data.md)Microsoft 365 中匯入及封存。

### <a name="manage-ediscovery-workflow-in-one-platform"></a>在單一平臺中管理 eDiscovery 工作流程

Advanced eDiscovery 可協助您減少所需依賴的 eDiscovery 解決方案數目。 它提供簡化的端對端工作流程，全部都是在 Microsoft 365 內進行。 Advanced eDiscovery 會自動將唯一和共用資料來源對應至相關 (人員（稱為 *保管人*) ），並在收集它進行分析和審核之前，先提供可能相關資料的報告和分析，以降低識別及收集相關資訊來源的摩擦。

此外，Microsoft Graph APIs 可協助您自動化 eDiscovery 工作流程，並為自訂解決方案擴充 Advanced eDiscovery。

### <a name="cull-data-intelligently"></a>智慧挑選資料

Advanced eDiscovery 中的智慧機教學功能可協助您減少要檢查的資料量。 這些智慧功能可協助您減少及挑選大量的資料至相關集。 例如，內建的審閱集查詢可識別重複的重複專案，以協助只為唯一的內容篩選。 這項功能可大幅減少要檢查的資料量。

其他機器學習功能可進一步精煉及識別使用智慧標籤和技術協助審閱工具（如相關性模組）的相關資料。

## <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a>使用電子探索參考模型對齊 Advanced eDiscovery

Microsoft 365 中內建 Advanced eDiscovery 的內建工作流程會與「電子探索」參考模型 (EDRM) 所述的 eDiscovery 程式相符。

![「電子探索參考模型 (EDRM) ](../media/EDRMv1.png)

 (圖像來源 edrm.net。 來源影像可在 [創造性 Commons 歸屬 3.0 Unported 授權] 下取得。 ) 

以高層級來說，以下是進階電子文件探索支援 EDRM 工作流程的方式：

- **識別。** 在您找出調查中的潛在可疑人員之後，您可以將他們新增為進階電子文件探索案例的監管人 (也稱為 *資料監管人*，因為他們可能擁有與調查相關的資訊)。 將使用者新增為監管人之後，就可以輕鬆保存、收集及檢視監管人文件。

- **保存。** 若要保留及保護與調查相關的資料，進階電子文件探索可讓您對案例中與監管人相關聯的資料來源執行法務保存措施。 您也可以保留非監管資料。 進階電子文件探索也有內建的通訊工作流程，因此您可以將法務保存通知傳送給監管人，並追蹤其是否知道。

- **收集。** 識別 (並保留) 與調查相關的資料來源之後，您可以使用進階電子文件探索搜尋中的內建搜尋工具，並從可能與案例相關的監管資料來源 (以及非監管資料來源 ，如果適用) 中收集即時資料。

- **處理。** 在您收集所有與案例相關的資料之後，下一個步驟就是處理該資料以進一步檢視和分析。 在進階電子文件探索中，您於收集階段中找到的就地資料會複製到 Azure 儲存體位置 (稱為 *檢閱集*)，其中可提供您案例資料的靜態檢視。 

- **檢討。** 將資料新增至審閱集後，您就可以查看特定的檔，並執行額外的查詢，將資料縮小至與案例最為相關的資料。 此外，也可以為特定文件加批註和標記。

- **分析。** 進階電子文件探索提供整合式分析工具，可協助您從判斷與調查不相關的檢閱集進一步收集資料。 除了減少相關的資料量之外，進階電子文件探索也可協助您節省法律審查花費，讓您整理內容以使檢閱程序更輕鬆且更有效率。

- **生產** 及 **簡報。** 當您準備就緒，可以從檢閱集匯出文件以供法律審查。 您可以匯出原生格式或 EDRM 指定格式的文件，以便將它們匯入協力廠商審查應用程式。

## <a name="subscriptions-and-licensing"></a>訂閱與授權

Advanced eDiscovery 授權要求適當的組織訂閱和每一使用者授權。

- **組織訂閱：** 若要存取 Microsoft 365 規範中心的 Advanced eDiscovery，您的組織必須具備下列其中一項：

  - Microsoft 365 E5 或 Office 365 E5 訂閱
  
  - 含 E5 合規性附加元件的 Microsoft 365 E3 訂閱

  - 具有 E5 eDiscovery 及 Audit 附加元件的 Microsoft 365 E3 訂閱

  - Microsoft 365 教育版a5 或 Office 365 教育版 a5 訂閱

   如果您沒有現有的 Microsoft 365 E5 計畫，且想要嘗試 Advanced eDiscovery，您可以[將 Microsoft 365 新增](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)至現有的訂閱或註冊 Microsoft 365 E5 的[試用版](https://www.microsoft.com/microsoft-365/enterprise)。

- **每位使用者授權：** 若要在預先 eDiscovery 案例中將使用者新增為系統管理員，該使用者必須根據您的組織訂閱，被指派下列其中一個授權：

  - Microsoft 365：必須對使用者指派 Microsoft 365 E5 授權、e5 符合性附加元件授權或 e5 eDiscovery 和審核附加元件授權。 Microsoft 365 教育版使用者必須被指派為 A5 授權。

  - Office 365：使用者必須被指派 Office 365 E5 或 Office 365 教育版 A5 授權。

   如需如何指派授權的詳細資訊，請參閱 [將授權指派給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

> [!NOTE]
> 使用者只需要 E5 或 A5 授權 (或適當的附加元件授權) 新增至 Advanced eDiscovery 案例。 IT 系統管理員、eDiscovery 管理員、律師、paralegals 或調查人員，使用 Advanced eDiscovery 來管理案例及審閱案例資料不需要 E5、A5 或附加元件授權。

## <a name="get-started-with-advanced-ediscovery"></a>開始使用進階電子文件探索

開始使用 Advanced eDiscovery 有兩個快速快捷的步驟。

![工作流程快速入門 Advanced eDiscovery](../media/get-started-AeD.png)

|步驟  |描述  |
|:---------|:---------|
|[設定進階電子文件探索](get-started-with-advanced-ediscovery.md)| 驗證訂閱和授權需求之後，您可以指派許可權，並設定組織範圍的設定，以開始使用 Advanced eDiscovery。|
|[建立及管理案例](create-and-manage-advanced-ediscoveryv2-case.md) | 建立案例以管理組織中所有法律和其他調查類型的 Advanced eDiscovery 工作流程。|
|||

## <a name="advanced-ediscovery-architecture"></a>Advanced eDiscovery 架構

以下是一種 Advanced eDiscovery 架構圖，顯示單一地理位置環境和多地理位置環境中的端對端工作流程，以及與[EDRM](#advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model)對齊的端對端資料流程。

[![模型海報： Microsoft 365 中的 Advanced eDiscovery 架構](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[以影像形式查看](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[下載為 PDF 檔案](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[下載成 Visio 檔](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)
