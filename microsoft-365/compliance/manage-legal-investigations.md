---
title: 管理 Office 365 中的法律調查
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
description: 在 Office 365 安全性 & 合規性中心] 中使用 eDiscovery 案例，來管理貴組織的法律調查。 如果您有 E5 訂閱，您可以進一步分析案例資料，藉由使用文字分析、 機器學習和進階電子文件的預測式編碼功能。
ms.openlocfilehash: f3d51fbd0df6d4bf4c88f5efef53a3c7f11e190c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600530"
---
# <a name="manage-legal-investigations-in-office-365"></a>管理 Office 365 中的法律調查

組織有許多原因可回應涉及特定主管或組織中的其他員工的法律案件。 這可能需要快速尋找及保留需進一步調查特定電子郵件、 文件、 立即訊息對話和日常工作中的人員所使用的其他內容位置中的資訊。 您可以在安全性與合規性中心使用 eDiscovery 案例工具來執行這些結構元件及其他許多類似的活動。
  
**想知道如何 Microsoft 管理其電子文件探索調查嗎？** 以下是[技術白皮書：](https://go.microsoft.com/fwlink/?linkid=852161)您可以下載說明我們如何使用相同的 Office 365 搜尋和調查工具來管理我們的內部的 eDiscovery 工作流程。
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>管理法律調查與 eDiscovery 案例

eDiscovery 案例可讓您控制可以建立、 存取及管理組織中的 eDiscovery 案例。 若要新增成員並控制哪些類型的動作，他們可以執行、 保留內容位置相關的法律案件，以及使用內容搜尋 」 工具來搜尋位置保留的內容，可能會回應您的案例使用案例。 然後您也可以匯出及下載進一步外部的檢閱者所使用的結果。
  
- 若要進行的[管理您的 eDiscovery 工作流程](ediscovery-cases.md)來建立和使用 eDiscovery 案例的每個法律調查您的組織有 
    
- [指派 eDiscovery 權限](assign-ediscovery-permissions.md)控制可以建立及管理組織中的 eDiscovery 案例 
    
- [設定合規性界限](tagging-and-assessment-in-advanced-ediscovery.md)來控制可搜尋電子文件探索管理員的使用者內容位置 
    
- 在您的組織中[搜尋的內容](search-for-content.md) 
    
### <a name="use-scripts-for-advanced-scenarios"></a>在進階案例中使用指令碼

如前一節所列的內容搜尋案例指令碼，我們也建立了一些安全性 & 合規性中心 PowerShell 指令碼，以協助您管理 eDiscovery 案例。
  
- [建立 eDiscovery 保留報告](create-a-report-on-holds-in-ediscovery-cases.md)，其中包含所有的資訊保留組織中的 eDiscovery 案例相關聯 
    
- [新增信箱和 OneDrive 位置](use-a-script-to-add-users-to-a-hold-in-ediscovery.md)之清單使用者 eDiscovery 保留 
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>管理法律調查與 Microsoft 365 進階電子文件方案

在 Microsoft 365 進階電子文件方案為基礎的現有的 eDiscovery 和 Office 365 中的分析功能。 這個新的解決方案，名為*Advanced eDiscovery*，提供的端對端工作流程，以保留、 收集、 檢閱、 分析和匯出回應您的組織內部和外部調查的內容。 它也可讓管理整個合法持有通知工作流程與 custodians 參與案例進行通訊的法律小組。

進階電子文件需要 E5 訂用帳戶為您的 Office 365 或 Microsoft 365 組織。 或者，使用版 E3 授權的使用者需要進階合規性附加元件訂閱，所以您可以為 custodians 進階電子文件探索案例中進行管理。

以下是在進階電子文件中的內建工作流程的快速概觀。 如需詳細資訊，請參閱 [Microsoft 365 中的進階電子文件探索解決方案概觀](overview-ediscovery-20.md)。

- 若要開始[建立案例](create-new-ediscovery-case.md)

- 它們的成員[管理 custodians](managing-custodians.md)將它們新增至案例，並將合法持有放置在其信箱、 OneDrive 帳戶及 Microsoft Teams 中的內容

- [管理通訊](managing-custodian-communications.md)以透過自動化法律 custodians 保留通知程序

- [索引 custodian 資料](processing-data-for-case.md)和錯誤編製索引，因此您可以有效地進行您調查收集資料的修正程式

- [收集資料](collecting-data-for-ediscovery.md)的情況下，並新增進一步調查[新增它來檢閱設定](collecting-data-for-ediscovery.md#adding-search-results-to-a-review-set)

- [檢視](view-documents-in-review-set.md)文件、[查詢](review-set-search.md)資料，並檢閱集中[標記](tagging-documents.md)項目

- 使用進階的分析工具的[分析案例資料](analyzing-data-in-review-set.md)

- 檢閱由外部顧問[匯出案例資料](exporting-data-ediscover20.md)

- 進階電子文件中的[管理長時間執行的工作](managing-jobs-ediscovery20.md)
