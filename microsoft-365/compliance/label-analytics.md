---
title: 利用標籤分析檢視標籤使用量
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 建立您的保留標籤和敏感度標籤後，您將想要查看租用戶間使用標籤的情況。 利用 Microsoft 365 合規性中心和 Microsoft 365 安全性中心中的標籤分析，您可以快速查看最常使用的標籤，以及套用標籤的位置。
ms.openlocfilehash: 3905b868ec3815fd9bf63ca131a20ceb1034f2c7
ms.sourcegitcommit: 252b1d1d8ae735b99bf46e27c08353afc330aef3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/14/2020
ms.locfileid: "44231986"
---
# <a name="view-label-usage-with-label-analytics"></a>利用標籤分析檢視標籤使用量

建立您的保留標籤和敏感度標籤後，您將想要查看租用戶間使用標籤的情況。 利用 Microsoft 365 合規性中心和 Microsoft 365 安全性中心中的標籤分析，您可以快速查看最常使用的標籤，以及套用標籤的位置。

比方說，利用標籤分析，您可以檢視：

- 套用至內容的保留標籤和敏感度標籤的總數。
- 最常使用的標籤和套用每個標籤的次數計數。
- 套用標籤的位置和每個位置的計數。
- 已變更或移除其保留標籤的檔案和資料夾的計數。

您可以在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/labelanalytics)或 [Microsoft 365 安全性中心](https://security.microsoft.com/labelanalytics) > 的 [分類]**** >  [標籤分析]**** 中找到標籤分析。

![標籤分析頁面](../media/label-analytics-page.png)

## <a name="sensitivity-label-usage"></a>敏感度標籤使用量

有關敏感度標籤使用量的資料是從 Azure 資訊保護的報告提取，如需詳細資訊，請參閱 [Azure 資訊保護的集中報告](https://docs.microsoft.com/azure/information-protection/reports-aip)。

請注意，Azure 資訊保護報告具有[先決條件](/azure/information-protection/reports-aip#prerequisites)，也適用於 Microsoft 365 合規性中心和 Microsoft 365 安全性中心中敏感度標籤的標籤分析。 比方說，您需要包含記錄分析的 Azure 訂閱，因為這些報告為根據 Azure Log Analytics 服務，從 Azure 資訊保護用戶端與掃描器傳送資訊保護稽核事件至集中位置的結果。

針對敏感度標籤使用量：

- 資料中沒有任何延遲。 這是即時的報告。
- 若要查看每個最常使用標籤的計數，請指向長條圖，然後讀取出現的工具提示。
- 報告會顯示每個 App 套用敏感度標籤的位置 (其中會顯示每個位置的保留標籤)。

![敏感度標籤使用量報告](../media/sensitivity-label-usage-report.png)

## <a name="retention-label-usage"></a>保留標籤使用量

此報告會顯示最常使用標籤為何和套用標籤位置的快速檢視。 如需 SharePoint 和 OneDrive 中的內容加標籤方式的詳細資訊，請參閱[檢視文件的標籤活動](view-label-activity-for-documents.md)。

針對保留標籤使用量：

- 資料會每週彙總，因此可能需要最多 7 天，資料才會顯示在報告中。
- 若要查看每個最常使用標籤的計數，請指向長條圖，然後讀取出現的工具提示。
- 報告會顯示每個位置套用保留標籤的位置 (其中會顯示每個 App 的敏感度標籤)。
- 針對保留標籤，這是您的租用戶中所有時間的資料摘要，未篩選至特定日期範圍。 相反地，[標籤活動總管][](view-label-activity-for-documents.md) 只會顯示過去 30 天的資料。

![保留標籤使用量報告](../media/retention-label-usage-report.png)

## <a name="view-all-content-with-a-specific-retention-label"></a>檢視具有特定保留標籤的所有內容

從保留標籤使用量報告中，您可以快速瀏覽套用了該標籤的所有內容。 (請注意，我們目前正在處理此功能，因此要檢視所有加標籤的內容，需要的步驟會較少。)

首先，選擇報告底端的 [檢視詳細資料]****。

![保留標籤使用量報告下方的 [檢視詳細資料] 選項](../media/retention-label-usage-view-details.png)

然後在右窗格中選擇 [保留標籤] > [探索項目]****。

![右窗格中的 [探索項目] 選項](../media/retention-label-usage-explore-items.png)

針對該標籤，您可以選擇 [活動]**** 索引標籤以依位置檢視具有該標籤的項目計數。

![保留標籤的 [活動] 索引標籤](../media/retention-label-usage-activity-tab.png)

您也可以選擇 [套用此標籤的項目]**** 索引標籤。然後可以深入了解特定位置：

- 針對 Exchange Online，您會看到信箱的清單，並含有每一個信箱中加標籤項目的計數。
- 針對 SharePoint Online 和商務用 OneDrive，您會看到網站集合和 OneDrive 帳戶的清單，並含有每個位置中加標籤項目的計數。

選擇信箱或網站集合時，您可以檢視該位置中具有該保留標籤的項目清單。

![[套用此標籤的項目] 索引標籤，顯示具有該保留標籤的所有項目](../media/retention-label-usage-content-explorer.png)

## <a name="permissions"></a>權限

若要檢視標籤分析，您必須獲指派 Azure Active Directory 中的下列其中一個角色：

- 全域系統管理員
- 合規性系統管理員
- 安全性系統管理員
- 安全性讀取者

此外，請注意，這類報告會使用 Azure 監視器將資料儲存在您的組織擁有的 Log Analytics 工作區。 因此，應該將使用者新增為保留資料的 Azure 監視工作區的讀取者。如需詳細資訊，請參閱 [Azure 資訊保護分析所需的權限](https://docs.microsoft.com/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics)。

