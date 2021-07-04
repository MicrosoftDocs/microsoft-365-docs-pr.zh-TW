---
title: 使用 Microsoft 365 資料外洩防護內部部署掃描器 (預覽)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 了解如何使用 Microsoft 365 資料外洩防護內部部署掃描器安心掃描資料，並針對內部部署檔案共用和內部部署 SharePoint 資料夾和文件庫執行保護動作。
ms.openlocfilehash: b2512c47b82ab3624d892d349611dd3f1e5aed3c
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289172"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a>使用 Microsoft 365 資料外洩防護內部部署掃描器 (預覽)

為協助您熟悉 DLP 內部部署功能及其在 DLP 原則中的呈現方式，我們為您整理了一些可遵循的案例。

> [!IMPORTANT]
> 這些 DLP 內部部署案例非建立和調整 DLP 原則的正式程式。 當您需要在一般情況下使用 DLP 原則時，請參閱下列主題：
>
> - [深入了解資料外洩防護](dlp-learn-about-dlp.md)
> - [預設的 DLP 原則快速入門](get-started-with-the-default-dlp-policy.md)
> - [從範本建立 DLP 原則](create-a-dlp-policy-from-a-template.md)
> - [建立、測試及調整 DLP 原則](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a>案例：探索符合 DLP 規則的檔案

來自 DLP 內部部署掃描器的資料於數個區域出現

#### <a name="activity-explorer"></a>活動總管

 適用於內部部署的 Microsoft DLP 會偵測 DLP 規則相符項目，並將其回報給 [活動總管](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer)。

#### <a name="microsoft-365-audit-log"></a>Microsoft 365 稽核記錄

在公開預覽期間，DLP 規則相符項目可在稽核記錄 UI 中取得，請參閱 [在合規性中心內搜尋稽核記錄](search-the-audit-log-in-security-and-compliance.md) 或透過 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell 存取。

#### <a name="aip"></a>AIP

探索資料以 csv 格式的本機報表提供，儲存位置為：

**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv 報表**。

 請尋找下列欄：

- DLP 模式
- DLP 狀態
- DLP 註解
- DLP 規則名稱
- DLP 動作
- 擁有者
- 目前的 NTFS 權限 (SDDL)
- 套用的 NTFS 權限 (SDDL)
- NTFS 權限類型

### <a name="scenario-enforce-dlp-rule"></a>案例：強制執行 DLP 規則

如果您想要對掃描的檔案強制執行 DLP 規則，則必須在 AIP 中的內容掃描工作以及 DLP 中原則層級上啟用強制執行。

#### <a name="configure-dlp-to-enforce-policy-actions"></a>設定 DLP 以強制執行原則動作

1. 開啟 [資料外洩防護頁面](https://compliance.microsoft.com/datalossprevention?viewid=policies)，然後選取將您在 AIP 中所設定之內部部署位置存放庫作為目標的 DLP 策略。
2. 編輯原則。
3. 在 **測試或開啟原則** 頁面上，選取 **是，立即開啟**。

## <a name="see-also"></a>另請參閱

- [了解 DLP 內部部署掃描器 (預覽)](dlp-on-premises-scanner-learn.md)
- [開始使用 DLP 內部部署掃描器 (預覽)](dlp-on-premises-scanner-get-started.md)
- [深入了解資料外洩防護](dlp-learn-about-dlp.md)
- [建立、測試及調整 DLP 原則](create-test-tune-dlp-policy.md)
- [開始使用活動總管](data-classification-activity-explorer.md)
