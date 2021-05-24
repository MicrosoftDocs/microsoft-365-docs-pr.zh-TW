---
title: 開始使用 Microsoft 365 資料外洩防護內部部署掃描器 (預覽)
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
description: 設定 Microsoft 365 資料外洩防護內部部署掃描器
ms.openlocfilehash: b21474f3a9e045bf353d62ef6c7c8d4174801a1b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623830"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner-preview"></a>開始使用資料外洩防護內部部署掃描器 (預覽)

本文會逐步引導您完成 Microsoft 365 資料外洩防護內部部署掃描器的必要條件和設定。

## <a name="before-you-begin"></a>開始之前

### <a name="skusubscriptions-licensing"></a>SKU/訂閱授權

開始使用 DLP 內部部署掃描器之前，您應先確認 [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)以及任何附加元件。 若要參與預覽，設定 DLP 規則的系統管理員帳戶必須指派下列其中一個授權：

- Microsoft 365 E5
- Microsoft 365 E5 合規性
- Microsoft 365 E5 資訊保護和控管 


如需完整授權的詳情，請參閱：[Microsoft 365 安全性與合規性的授權指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

### <a name="permissions"></a>權限


可在 [活動總管](data-classification-activity-explorer.md) 中檢視來自 DLP 內部部署掃描器的資料。 有四個角色可以將權限授與活動總管，您用來存取資料的帳戶必須是其中任一的成員。

- 全域系統管理員
- 合規性系統管理員
- 安全性系統管理員
- 合規性資料管理員

### <a name="dlp-on-premises-scanner-prerequisites"></a>DLP 內部部署掃描器必要條件

- Azure 資訊保護 (AIP) 掃描器會執行 DLP 原則配對和原則強制執行。此掃描器會安裝為 AIP 用戶端的一部分，因此您的安裝必須符合 AIP、AIP 用戶端和 AIP 統一標籤掃描器的所有必要條件。
- 部署 AIP 用戶端和掃描器。 如需深入了解 [安裝 AIP 統一標籤用戶端](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) 和 []，請參閱 [設定和安裝 Azure 資訊保護統一標籤掃描器](/azure/information-protection/deploy-aip-scanner-configure-install)。
- 即使您的所有偵測規則都只以敏感資訊類型為基礎，租用戶中仍至少必須發佈一個標籤和原則。

## <a name="deploy-the-dlp-on-premises-scanner"></a>部署 DLP 內部部署掃描器

1. 請遵循 [ 安裝 AIP 統一標籤用戶端](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) 中的步驟。 
2. 請遵循 [設定和安裝 Azure 資訊保護統一標籤掃描器](/azure/information-protection/deploy-aip-scanner-configure-install) 中的步驟以完成掃描器安裝。
    1. 網路探索工作設定是選擇性的步驟。 您可以略過它，並定義內容掃描工作要掃描的特定存放庫。
    2. 您必須建立內容掃描工作，並指定裝載著需由 DLP 引擎評估之檔案的存放庫。
    3. 在建立的內容掃描工作中啟用 DLP 規則，並將 **強制** 選項設定 為 **關閉**，但若您要直接進入 DLP 強制階段則例外。
3. 請驗證您的內容掃描工作已指派至正確的叢集。如果您仍未建立內容掃描工作，請建立新工作，並將它指派給包含執行公開預覽版本的掃描器節點的叢集。

4. 連接至 [Azure 入口網站中的 Azure 資訊保護延伸模組](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) ，並將您的存放庫新增到將執行掃描的內容掃描工作。

5. 執行下列其中一項操作以執行掃描：
    1. 設定掃描器排程
    1. 使用入口網站中的手動 **立即掃描** 選項
    1. 或執行 **Start-AIPScan** PowerShell Cmdlet

   > [!IMPORTANT]
   > 請記住，掃描器預設會執行存放庫的差異掃描，且除非檔案已變更或您初始化完整重新掃描，否則將會略過先前掃描週期中已掃描的檔案。 您可以使用 UI 中的 **重新掃描所有檔案** 選項，或執行 **Start-AIPScan-Reset** 來起始完整重新掃描。

6.  在 Microsoft 365 合規性中心開啟 [資料外洩防護頁面](https://compliance.microsoft.com/datalossprevention?viewid=policies)。

7. 選擇 **建立原則** ，然後建立測試 DLP 原則。 如果您需要協助建立原則。請參閱 [從範本建立 DLP 原則](create-a-dlp-policy-from-a-template.md)。 請務必在測試中執行，直到您熟悉這項功能。 針對您的原則使用這些參數：
    1. 如有必要，將 DLP 內部部署掃描器規則的範圍縮小到特定位置。 如果您將範圍 **位置** 設為 **所有**，掃描器所掃描的所有檔案都會受到 DLP 規則配對和強制執行。
    1. 指定位置時，您可以使用排除或包含清單。 在公開預覽期間，您無法同時設定這兩者。 您可以將規則定義為只與包含清單中所列的其中一個模式相符的路徑相關，或是所有檔案，但符合包含清單中所列模式的檔案除外。 不支援任何本機路徑。 以下是一些有效路徑的範例：
      - \\\server\share
      - \\\server\share\folder1\subfolderabc
      - \*\\folder1
      - \*secret\*.docx
      - \*secret\*.\*
      - https:// sp2010.local/sites/HR
      - https://\*/HR 
    3. 以下是一些不被接受的值範例：
      - \*
      - \*\\a
      - Aaa
      - c:\
      - C:\test

> [!IMPORTANT]
> 排除清單優先於包含清單。

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a>在 DLP 警示管理儀表板中檢視DLP 內部部署掃描器警示

1. 在 Microsoft 365 合規性中心開啟 [資料外洩防護頁面](https://compliance.microsoft.com/datalossprevention?viewid=policies) 然後選取 **警示**。

2. 請參閱[如何設定和檢視 DLP 原則的警示](dlp-configure-view-alerts-policies.md)中的程序，以檢視您端點 DLP 原則的警示。

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a>在活動總管和稽核記錄中檢視 DLP 內部部署掃描器

> [!NOTE]
> 內部部署掃描器要求啟用稽核。 在 Microsoft 365 中，稽核預設為啟用。

1. 在 Microsoft 365 合規性中心開啟您網域的 [資料分類頁面](https://compliance.microsoft.com/dataclassification?viewid=overview)，然後選取活動總管。

2. 請參閱 [開始使用活動總管](data-classification-activity-explorer.md) 中的程序，以存取及篩選您內部部署掃描器位置的所有資料。

3. 開啟 [合規性中心裡的稽核記錄](https://security.microsoft.com/auditlogsearch)。 在公開預覽期間，DLP 規則相符項目可在稽核記錄 UI 中取得，或可透過 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell 存取。 


## <a name="next-steps"></a>後續步驟
現在您已為 DLP 內部部署位置部署了測試原則，且可以在活動總管中檢視活動資料，您已準備好開始建立可保護您敏感性項目之 DLP 原則的下一個步驟。

- [使用 DLP 內部部署 (預覽)](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>請參閱

- [了解 DLP 內部部署掃描器 (預覽)](dlp-on-premises-scanner-learn.md)
- [使用 DLP 內部部署掃描器 (預覽)](dlp-on-premises-scanner-use.md)
- [深入了解資料外洩防護](dlp-learn-about-dlp.md)
- [建立、測試及調整 DLP 原則](create-test-tune-dlp-policy.md)
- [開始使用活動總管](data-classification-activity-explorer.md)
- [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)