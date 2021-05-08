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
ms.openlocfilehash: 5b9484826f0d3a297dae47c7d140d93297473023
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259270"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>請參閱 Microsoft 365 中的 Microsoft 資訊保護。

>*[Microsoft 365 安全性與合規性的授權](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

實施 Microsoft 資訊保護 (MIP) 可協助您探索、分類及保護敏感性資訊，無論這些資料儲存在某處在或傳輸中。

MIP 功能隨附於 Microsoft 365 合規性中，並提供工具以 [了解您的資料](#know-your-data)、[保護您的資料](#protect-your-data)，以及[防止資料遺失](#prevent-data-loss)。

![MIP 如何協助您探索、分類及保護敏感性資料的影像](../media/powered-by-intelligent-platform.png)

:::image type="content" source="../media/data-table1-4638524-new.png" alt-text="了解您的資料":::

如需資料控管方式的相關資訊，請參閱 [Microsoft 365 中的 Microsoft 資訊控管](manage-Information-governance.md)。

## <a name="know-your-data"></a>了解您的資料

> [!NOTE]
> 如需在 Azure Purview 中分類資料和為資料加上標籤 (目前處於預覽) 的相關資訊，請參閱[在 Azure Purview 中自動為您的內容加上標籤](/azure/purview/create-sensitivity-label)。
> 
> 如需 Azure Purview 的發行公告，請參閱下列部落格文章：[Microsoft 資訊保護和 Microsoft Azure Purview：Better Together](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481) 和 [Azure Purview at Spring Ignite 2021](https://techcommunity.microsoft.com/t5/azure-purview/azure-purview-at-spring-ignite-2021/ba-p/2175919)。

若要深入了解您的資料環境，並識別混合式環境中的重要資料，請使用下列功能：

:::image type="content" source="../media/knowyourdata-new.png" alt-text="了解您的資料"::: 


|**功能**|**需要解決的問題是什麼？**|**開始使用**|**授權**|
|--|--|--|--|
|[敏感性資訊類型](sensitive-information-type-entity-definitions.md)| 您可以使用內建或自訂的規則運算式或函數來識別敏感性資料，以及包含關鍵字、信賴等級和鄰近的確切證據。 使用敏感資訊類型來識別貴組織的特定資料類型。 使用現成敏感性資訊類型來尋找標準類型的資料，例如護照號碼。 建立自訂資訊類型，以識別您的環境唯一的資訊，例如元件編號。 | [自訂內建的敏感性資訊類型](customize-a-built-in-sensitive-information-type.md)| |
|[可訓練分類器 (預覽)](classifier-learn-about.md)| 您可以使用內建的其中一個分類器為資料分類，或使用自己的內容來訓練分類器 | [開始使用可訓練分類器 (預覽)](classifier-get-started-with.md)| |
|[資料分類](data-classification-overview.md) | 識別具有敏感度標籤、保留標籤或已分類為貴組織敏感性資訊類型之項目，以及使用者對其採取之動作。  | [開始使用內容總管](data-classification-content-explorer.md)<br /><br /> [開始使用活動總管](data-classification-activity-explorer.md)| |



## <a name="protect-your-data"></a>保護您的資料

若要套用含有加密、存取限制和視覺標記的彈性保護動作，請使用下列功能：


:::image type="content" source="../media/protectyourdata-4638524-new.png" alt-text="保護您的資料":::

|**功能**|**需要解決的問題是什麼？**|**開始使用**|**授權**|
|--|--|--|--|
|[敏感度標籤](sensitivity-labels.md)| 應用程式、服務和裝置上的單一解決方案，可讓您的資料在組織內部和外部傳輸時進行標記和保護 <br /><br />範例案例：[在 Power BI 中套用和檢視敏感度標籤，並在匯出資料時加以保護](/power-bi/admin/service-security-apply-data-sensitivity-labels)|[開始使用敏感度標籤](get-started-with-sensitivity-labels.md) |
|[Microsoft 雲端 App 安全性](/cloud-app-security/what-is-cloud-app-security)| 探索、標記和保護位於雲端資料存放區中的敏感性資訊 | [探索、分類、標記及保護儲存在雲端的管制資料及敏感性資料](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Azure 資訊保護統一標籤掃瞄器](/azure/information-protection/deploy-aip-scanner)| 探索、標記和保護駐留於內部部署資料存放區中的敏感性資訊 | [設定和安裝 Azure 資訊保護統一標籤掃瞄器](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[活動總管]()||||


## <a name="transition-from-aip-to-mip"></a>從 AIP 轉換到 MIP
傳統 Azure 資訊保護系統管理體驗和用戶端會於明年初被取代。 建議您移至 Microsoft 資訊保護。這需要移轉您所有現有的標籤和原則。 

:::image type="content" source="../media/transition-aip2mip-4638524-new.png" alt-text="從 AIP 轉換到 MIP":::

## <a name="additional-capabilities"></a>其他功能
Microsoft 365 包含這些功能，可協助保護資料：

|**功能**|**需要解決的問題是什麼？**|**開始使用**|
|--|--|--|
| Office 365 郵件加密 (OME) | 將傳送給任何裝置上任何使用者的電子郵件訊息和附加文件加密，以便只有授權的收件者能讀取電子郵件中的資訊。 <br /><br /> 範例案例：撤銷由進階郵件加密所加密的電子郵件 | 設定全新的郵件加密功能 |
| 雙重金鑰加密 | 在所有情況下，只有您能解密受保護的內容，或因為法規要求，您必須在地理邊界內持有加密金鑰 | 部署雙重金鑰加密 |  
| 客戶金鑰服務加密 | 防止未經授權的系統或人員檢視資料，並補充 Microsoft 資料中心中的 BitLocker 磁碟機加密。 | 設定 Office 365 客戶金鑰 |
| SharePoint 資訊版權管理 (IRM) | 保護 SharePoint 清單和文件庫，以便當使用者取出文件時，下載的檔案受到保護，因此只有經授權者才能根據您指定的原則檢視和使用檔案。 | 在 SharePoint 系統管理中心中設定資訊版權管理 (IRM) |
| 版權管理連接器 | 僅保護使用 Exchange 或 SharePoint Server 和檔案分類基礎結構 (FCI) 的現有內部部署 | 部署 RMS 連接器的步驟 |



## <a name="prevent-data-loss"></a>防止資料遺失

若要協助防止意外分享敏感性資訊，請使用下列功能：

:::image type="content" source="../media/dlp-4638524-new.png" alt-text="防止資料遺失":::

|**步驟**|**描述**|**其他資訊**|
|--|--|--|
|[設計 DLP 原則](data-loss-prevention-policies.md)| 規劃識別資訊的模式 (敏感性資訊類型、標籤、其他) <br /><br /> 規劃將鎖定哪些原則 (服務、用戶端、協力廠商應用程式。) <br /><br /> 規劃原則提示，其他||
||||




|**功能**|**需要解決的問題是什麼？**|**開始使用**|
|--|--|--|
|[深入了解資料外洩防護](dlp-learn-about-dlp.md)| 協助防止意外共用敏感性項目。 | [預設的 DLP 原則快速入門](get-started-with-the-default-dlp-policy.md)|
|[深入了解端點資料外洩防護](endpoint-dlp-learn-about.md)| 將 DLP 功能延伸到在 Windows 10 電腦上使用及共用的項目。 | [開始使用端點資料外洩防護](endpoint-dlp-getting-started.md)|
|[了解 Microsoft 合規性擴充功能 (預覽)](dlp-chrome-learn-about.md) | 將 DLP 功能延伸至 Chrome 瀏覽器 | [開始使用 Microsoft 合規性擴充功能 (預覽)](dlp-chrome-get-started.md)|
|[深入了解 Microsoft 365 資料外洩防護內部部署掃描器 (預覽)](dlp-on-premises-scanner-learn.md)|將檔案活動的 DLP 監視以及這些檔案的保護動作延伸到內部部署檔案共用、SharePoint 資料夾和文件庫。|[開始使用 Microsoft 365 資料外洩防護內部部署掃描器 (預覽)](dlp-on-premises-scanner-get-started.md)|
|[保護 Microsoft Teams 中聊天和頻道訊息中的敏感性資訊](dlp-microsoft-teams.md) | 將部分 DLP 功能延伸至 Teams 聊天和頻道訊息 | [了解 Microsoft Teams 中的預設資料外洩防護原則 (預覽)](dlp-teams-default-policy.md)| 


## <a name="additional-resources"></a>其他資源

許多組織正在使用這些資訊保護功能來遵守資料隱私權法規。 為了協助您，我們設計工作流程來引導您完成端對端流程，以規劃及實施整個 Microsoft 365 的功能，包括安全存取、威脅防護、資訊保護和資料監管。 如需詳細資訊，請參閱 [以 Microsoft 365 針對資料隱私權法規部署資訊保護](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy)。 

此外，為了協助規劃整合式策略來實施資訊保護功能，請下載 *Microsoft 365 資訊保護和合規性功能* 圖例集。  您可以隨意使用這些圖例。

| 項目 | 描述 |
|:-----|:------------|
|[![模型海報：Microsoft 365 資訊保護和合規性功能](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> [下載為 PDF](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)\| [下載為 Visio](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> 日文：[下載為 PDF](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)\| [下載為 Visio](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> 2020 年 10 月更新|包含： <ul><li>  Microsoft 資訊保護和資料外洩防護</li><li>保留原則和保留標籤 </li><li>資訊屏障</li><li>通訊合規性</li><li>內部風險管理</li><li>協力廠商資料擷取</li>|

