---
title: 從 Microsoft Cloud Deutschland 進行遷移時的 eDiscovery 體驗相關資訊
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：從 Microsoft Cloud Deutschland 進行遷移的 eDiscovery 遷移步驟。
ms.openlocfilehash: 0128c8563b2043e4ec41d2c5ab1b208bd3977511
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844247"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a>從 Microsoft Cloud Deutschland 進行遷移時的 eDiscovery 體驗相關資訊
下列各節提供從 microsoft cloud (德國 Deutschland) 到新德文 datacenter 區域中 Office 365 服務時，有關 eDiscovery 體驗的其他資訊。

## <a name="ediscovery-administration-until-phase-4"></a>eDiscovery 管理，直到第4階段
在第4階段之前，安全性與合規性中心會完全可用。 所有內容仍會保留在 Microsoft 雲端德國，而且可由 Microsoft Cloud 德國安全性與合規性中心 (加以管理 https://protection.office.de/) 。

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a>階段4之間的 eDiscovery 體驗，直到階段9結束
從第4階段開始直到階段9完成，「電子檔探索」搜尋會失敗，或是傳回已遷移之 SharePoint Online、商務用 OneDrive 及 Exchange Online 位置的0個結果。

> [!NOTE]
> 在遷移期間，客戶可以繼續在 [安全性 & 規範中心](/microsoft-365/compliance/manage-legal-investigations)（包括 [內容搜尋](/microsoft-365/compliance/search-for-content)）中建立案例、保留、搜尋和匯出。 不過，針對已遷移的 SharePoint 線上、商務用 OneDrive 和 Exchange Online 位置進行搜尋會傳回0個結果或產生錯誤。

在遷移期間，如果搜尋傳回零結果或發生錯誤，請在線上 SharePoint 執行下列動作：

- 遵循[從 OneDrive 或 SharePoint 下載檔案及資料夾](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)中的指示，直接從 SharePoint 線上或商務用 OneDrive 網站下載網站。 此方法將需要 SharePoint 線上系統管理員許可權或網站的唯讀許可權。
- 若超出限制（[從 OneDrive 或 SharePoint 下載檔案及資料夾](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)中所述），客戶可以遵循[SharePoint 同步處理的指導方針和 Teams 檔案與您的電腦](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)，使用商務用 OneDrive 同步處理用戶端。

- 如需詳細資訊，請參閱[Exchange Server 中的就地電子檔探索](/Exchange/policy-and-compliance/ediscovery/ediscovery)。


## <a name="ediscovery-administration-after-phase-9"></a>階段9之後的 eDiscovery 管理

**適用于：** 所有使用 eDiscovery 的客戶

在階段9中，移至新的德國資料中心區域的最後步驟將會完成。 在這個階段，將會遷移所有剩餘的服務元件。
在階段9之後，使用 Microsoft 雲端德國的安全性與合規性中心 (protection.office.de) 已不再支援。 請改為使用新的「 [安全中心](https://security.microsoft.com/) 」或「 [合規性中心](https://compliance.microsoft.com/) 」。 所有資料都已遷移至新的系統管理員入口網站。

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
|  所有 SharePoint 線上、商務用 OneDrive 和 Exchange Online 位置都與安全性與合規性中心 (SCC) 一起遷移。 | 所有 eDiscovery 活動都應該從世界租使用者執行。 搜尋現在會是100% 成功。 任何失敗或錯誤都應該遵循正常支援通道。 | 無 |
||||

### <a name="ediscovery-retention-policy"></a>eDiscovery 保留原則
**適用于：**  所有已套用保留原則的客戶做為預先遷移步驟的一部分

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 移除在遷移前步驟中建立的全組織保留原則 | 客戶可以移除在客戶的預先遷移工作中所建立的全組織保留原則。 | 無 |
||||
