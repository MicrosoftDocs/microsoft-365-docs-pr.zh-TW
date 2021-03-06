---
title: 請參閱 Microsoft 365 中的 Microsoft 資訊保護。
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
recommendations: false
description: 實施 Microsoft 資訊保護 (MIP) 可協助您保護敏感性資訊，無論這些資料儲存在某處在或傳輸中。
ms.openlocfilehash: bca6ce0dabaa9db2444da374b5d3ee166154fdd8
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226536"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>請參閱 Microsoft 365 中的 Microsoft 資訊保護。

>*[Microsoft 365 安全性與合規性的授權](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

實施 Microsoft 資訊保護 (MIP) 可協助您探索、分類及保護敏感性資訊，無論這些資料儲存在某處在或傳輸中。

MIP 功能隨附於 Microsoft 365 合規性中，並提供工具以 [了解您的資料](#know-your-data)、[保護您的資料](#protect-your-data)，以及[防止資料遺失](#prevent-data-loss)。

![MIP 如何協助您探索、分類及保護敏感性資料的影像](../media/powered-by-intelligent-platform.png)

如需資料控管方式的相關資訊，請參閱 [Microsoft 365 中的 Microsoft 資訊控管](manage-Information-governance.md)。

## <a name="know-your-data"></a>了解您的資料

> [!NOTE]
> 如需在 Azure Purview 中分類資料和為資料加上標籤 (目前處於預覽) 的相關資訊，請參閱[在 Azure Purview 中自動為您的內容加上標籤](/azure/purview/create-sensitivity-label)。

若要深入了解您的資料環境，並識別混合式環境中的重要資料，請使用下列功能：

|功能|需要解決的問題是什麼？|快速入門|
|:------|:------------|:--------------------|
|[敏感性資訊類型](sensitive-information-type-learn-about.md)| 您可以使用內建或自訂的規則運算式或函數來識別敏感性資料。包括關鍵字、信賴等級和鄰近性的確切證據。| [自訂內建的敏感性資訊類型](customize-a-built-in-sensitive-information-type.md)|
|[可訓練分類器](classifier-learn-about.md)| 使用您感興趣的資料範例，而不是項目內的識別元素 (模式比對) 進行識別敏感性資料。 您可以使用內建的分類器，或使用自己的內容訓練分類器。| [開始使用可訓練分類器](classifier-get-started-with.md) |
|[資料分類](data-classification-overview.md) | 貴組織中的項目圖形識別碼具有敏感度標籤、保留標籤，或已分類完成。 您也可以使用這項資訊取得深入解析您的使用者對這些項目所採取的動作。 | [開始使用內容總管](data-classification-content-explorer.md) <p> [開始使用活動總管](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>保護您的資料

若要套用含有加密、存取限制和視覺標記的彈性保護動作，請使用下列功能：

|功能|需要解決的問題是什麼？|快速入門|
|:------|:------------|---------------------|
|[敏感度標籤](sensitivity-labels.md)| 應用程式、服務和裝置上的單一解決方案，可讓您的資料在組織內部和外部傳輸時進行標記和保護。 <p> 範例案例： <p> [管理 Office 應用程式的敏感度標籤](sensitivity-labels-office-apps.md) <p> [加密文件和電子郵件](encryption-sensitivity-labels.md) <p> [套用和查看 Power BI 中的標籤](/power-bi/admin/service-security-apply-data-sensitivity-labels) <p> 如需敏感度標籤的案例完整清單，請參閱 [開始使用文件]。|[開始使用敏感度標籤](get-started-with-sensitivity-labels.md) |
|[Azure 資訊保護統一標籤用戶端](/azure/information-protection/rms-client/aip-clientv2)| 針對 Windows 電腦，擴充敏感度標籤以瞭解其他功能，包括從檔案瀏覽器和 PowerShell 中標記和保護所有檔案類型。 <p> 範例其他功能：[Azure 資訊保護統一標記用戶端的自訂設定](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Azure 資訊保護統一標籤用戶端系統管理員指南](/azure/information-protection/rms-client/clientv2-admin-guide)|
|[雙重金鑰加密](double-key-encryption.md)| 在所有情況下，只有貴組織能解密受保護的內容，或因為法規要求，您必須在地理邊界內持有加密金鑰。 | [部署雙重金鑰加密](double-key-encryption.md#deploy-dke)|
|[Office 365 郵件加密 (OME)](ome.md)| 將傳送給任何裝置上任何使用者的電子郵件訊息和附加文件加密，以便只有授權的收件者能讀取電子郵件中的資訊。 <p> 範例案例：[撤銷由進階郵件加密所加密的電子郵件](revoke-ome-encrypted-mail.md) | [設定全新的郵件加密功能](set-up-new-message-encryption-capabilities.md)|
|[客戶金鑰服務加密](customer-key-overview.md) | 防止未經授權的系統或人員檢視資料，並補充 Microsoft 資料中心中的 BitLocker 磁碟機加密。 | [設定 Office 365 客戶金鑰](customer-key-set-up.md)|
|[SharePoint 資訊版權管理 (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|保護 SharePoint 清單和文件庫，以便當使用者取出文件時，下載的檔案受到保護，因此只有授權人員才能根據您指定的原則檢視和使用檔案。 | [在 SharePoint 系統管理中心中設定資訊版權管理 (IRM)](set-up-irm-in-sp-admin-center.md)|
[版權管理連接器](/azure/information-protection/deploy-rms-connector) |僅限使用 Exchange 或 SharePoint Server 的現有內部部署來部署，或執行 Windows Server 和檔案分類基礎結構的檔案伺服器 (FCI)。 | [部署 RMS 連接器的步驟](/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure 資訊保護統一標籤掃瞄器](/azure/information-protection/deploy-aip-scanner)| 探索、標記和保護駐留於內部部署資料存放區中的敏感性資訊。 | [設定和安裝 Azure 資訊保護統一標籤掃瞄器](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft 雲端 App 安全性](/cloud-app-security/what-is-cloud-app-security)| 探索、標記和保護位於雲端資料存放區中的敏感性資訊。 | [探索、分類、標記及保護儲存在雲端的管制資料及敏感性資料](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft 資訊保護 SDK](/information-protection/develop/overview#microsoft-information-protection-sdk)|將敏感度標籤延伸至第三方應用程式和服務。 <p> 範例案例：[設定和取得敏感度標籤 (C++)](/information-protection/develop/quick-file-set-get-label-cpp) |[Microsoft 資訊保護 (MIP) SDK 安裝和設定](/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>防止資料遺失

若要協助防止意外分享敏感性資訊，請使用下列功能：


|功能|需要解決的問題是什麼？|快速入門|
|:------|:------------|:---------------------|
|[資料外洩防護](dlp-learn-about-dlp.md)| 協助防止意外共用敏感性項目。 | [預設的 DLP 原則快速入門](get-started-with-the-default-dlp-policy.md)|
|[端點資料外洩防護](endpoint-dlp-learn-about.md)| 將 DLP 功能延伸到在 Windows 10 電腦上使用及共用的項目。 | [開始使用端點資料外洩防護](endpoint-dlp-getting-started.md)|
|[Microsoft 合規性延伸模組](dlp-chrome-learn-about.md) | 將 DLP 功能延伸至 Chrome 瀏覽器 | [開始使用 Microsoft 合規性延伸模組](dlp-chrome-get-started.md)|
|[Microsoft 365 資料外洩防護內部部署掃描器 (預覽)](dlp-on-premises-scanner-learn.md)|將檔案活動的 DLP 監視以及這些檔案的保護動作延伸到內部部署檔案共用、SharePoint 資料夾和文件庫。|[開始使用 Microsoft 365 資料外洩防護內部部署掃描器 (預覽)](dlp-on-premises-scanner-get-started.md)|
|[保護 Microsoft Teams 中聊天和頻道訊息中的敏感性資訊](dlp-microsoft-teams.md) | 將部分 DLP 功能延伸至 Teams 聊天和頻道訊息 | [了解 Microsoft Teams 中的預設資料外洩防護原則 (預覽)](dlp-teams-default-policy.md)|

## <a name="licensing-requirements"></a>授權需求

MIP 的授權需求取決於您使用的情況和功能，而不是針對本頁所列的每個功能設定授權需求。 若要了解 MIP 的授權需求和選項，請參閱 Microsoft 365 授權文件中的[資訊防護](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)小節，並下載相關的 PDF 或 Excel。
