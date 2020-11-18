---
title: 請參閱 Microsoft 365 中的 Microsoft 資訊保護。
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
description: 實施 Microsoft 資訊保護 (MIP) 可協助您保護敏感性資訊，無論這些資料儲存在某處在或傳輸中。
ms.openlocfilehash: 4f98adbcee2b3daf4b347a16137d61cc0e790486
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087190"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>請參閱 Microsoft 365 中的 Microsoft 資訊保護。

>*[Microsoft 365 安全性與合規性的授權](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)* (部分機器翻譯)

實施 Microsoft 資訊保護 (MIP) 可協助您探索、分類及保護敏感性資訊，無論這些資料儲存在某處在或傳輸中。

MIP 功能隨附於 Microsoft 365 合規性中，並提供工具以 [了解您的資料](#know-your-data)、[保護您的資料](#protect-your-data)，以及[防止資料遺失](#prevent-data-loss)。

![MIP 如何協助您探索、分類及保護敏感性資料的影像](../media/powered-by-intelligent-platform.png)

如需資料控管方式的相關資訊，請參閱 [Microsoft 365 中的 Microsoft 資訊控管](manage-Information-governance.md)。

## <a name="know-your-data"></a>了解您的資料

若要深入了解您的資料環境，並識別混合式環境中的重要資料，請使用下列功能：
 
|功能|需要解決的問題是什麼？|快速入門|
|:------|:------------|:--------------------|:-----------------------------|
|[敏感性資訊類型](sensitive-information-type-entity-definitions.md)| 您可以使用內建或自訂的規則運算式或函數來識別敏感性資料，以及包含關鍵字、信賴等級和鄰近的確切證據。| [自訂內建的敏感性資訊類型](customize-a-built-in-sensitive-information-type.md)|
|[可訓練分類器 (預覽)](classifier-learn-about.md)| 您可以使用內建的其中一個分類器為資料分類，或使用自己的內容來訓練分類器 | [開始使用可訓練分類器 (預覽)](classifier-get-started-with.md) |
|[資料分類](data-classification-overview.md) | 識別具有敏感度標籤、保留標籤或已分類為貴組織敏感性資訊類型之項目，以及使用者對其採取之動作。  | [開始使用內容總管](data-classification-content-explorer.md)<br /><br /> [開始使用活動總管](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>保護您的資料

若要套用含有加密、存取限制和視覺標記的彈性保護動作，請使用下列功能：

|功能|需要解決的問題是什麼？|快速入門|
|:------|:------------|---------------------|:----------------------------|
|[敏感度標籤](sensitivity-labels.md)| 應用程式、服務和裝置上的單一解決方案，可讓您的資料在組織內部和外部傳輸時進行標記和保護 <br /><br />範例案例：[在 Power BI 中套用和檢視敏感度標籤，並在匯出資料時加以保護](https://docs.microsoft.com/power-bi/admin/service-security-apply-data-sensitivity-labels)|[開始使用敏感度標籤](get-started-with-sensitivity-labels.md) |
|[Azure 資訊保護統一標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) (部分機器翻譯)| 針對 Windows 電腦，擴充敏感度標籤以瞭解其他功能，包括從檔案瀏覽器和 PowerShell 中標記和保護所有檔案類型。<br /><br /> 範例其他功能：[Azure 資訊保護統一標記用戶端的自訂設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) (部分機器翻譯)| [Azure 資訊保護統一標籤用戶端系統管理員指南](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide) (部分機器翻譯)|
|[雙重金鑰加密](double-key-encryption.md)| 在所有情況下，只有您能解密受保護的內容，或因為法規要求，您必須在地理邊界內持有加密金鑰 | [部署雙重金鑰加密](double-key-encryption.md#deploy-dke)|
|[Office 365 郵件加密 (OME)](ome.md)| 將傳送給任何裝置上任何使用者的電子郵件訊息和附加文件加密，以便只有授權的收件者能讀出電子郵件中的資訊  <br /><br />範例案例：[撤銷由進階郵件加密所加密的電子郵件](revoke-ome-encrypted-mail.md) | [設定全新的郵件加密功能](set-up-new-message-encryption-capabilities.md)|
|[客戶金鑰服務加密](customer-key-overview.md) | 防止未經授權的系統或人員檢視資料，並補充 Microsoft 資料中心中的 BitLocker 磁碟機加密。 | [設定 Office 365 客戶金鑰](customer-key-set-up.md)|
|[SharePoint 資訊版權管理 (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|保護 SharePoint 清單和文件庫，以便當使用者取出文件時，下載的檔案受到保護，因此只有授權人員才能根據您指定的原則檢視和使用檔案。 | [在 SharePoint 系統管理中心中設定資訊版權管理 (IRM)](set-up-irm-in-sp-admin-center.md)|
[版權管理連接器](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) (部分機器翻譯) |僅限使用 Exchange 或 SharePoint Server 的現有內部部署來部署，或執行 Windows Server 和檔案分類基礎結構的檔案伺服器 (FCI) | [部署 RMS 連接器的步驟](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure 資訊保護統一標籤掃瞄器](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) (部分機器翻譯)| 探索、標記和保護駐留於內部部署資料存放區中的敏感性資訊 | [設定和安裝 Azure 資訊保護統一標籤掃瞄器](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install) (部分機器翻譯)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| 探索、標記和保護位於雲端資料存放區中的敏感性資訊 | [探索、分類、標記及保護儲存在雲端的管制資料及敏感性資料](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft 資訊保護 SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|將敏感度標籤延伸至第三方應用程式和服務  <br /><br /> 範例案例：[設定和取得敏感度標籤 (C++)](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Microsoft 資訊保護 (MIP) SDK 安裝和設定](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|

## <a name="prevent-data-loss"></a>防止資料遺失

若要協助防止意外分享敏感性資訊，請使用下列功能：


|功能|需要解決的問題是什麼？|快速入門|
|:------|:------------|:---------------------|:-----------------------------|
|[資料外洩防護 (DLP)](data-loss-prevention-policies.md)| 有助於防止意外共用敏感性項目 <br /><br />範例案例：[保護 Microsoft Teams 中聊天和頻道訊息的敏感性資訊](dlp-microsoft-teams.md) | [預設的 DLP 原則快速入門](get-started-with-the-default-dlp-policy.md)|
|[深入了解端點資料外洩防護](endpoint-dlp-learn-about.md)| 將 DLP 功能延伸到在 Windows 10 電腦上使用及共用的項目 | [開始使用端點資料外洩防護](endpoint-dlp-getting-started.md)|
