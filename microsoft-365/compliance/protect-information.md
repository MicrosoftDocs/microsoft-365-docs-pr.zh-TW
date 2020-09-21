---
title: Microsoft 365 中的 microsoft 資訊保護
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: High
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 實施 Microsoft 資訊保護 (MIP) 功能，方法是使用 Microsoft 365 符合性，協助您探索、分類及保護任何地方生活或傳播的敏感資訊。
ms.openlocfilehash: f867391243302d0ce912ae5d740ed761ea7317b7
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131963"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft 365 中的 microsoft 資訊保護

>*[Microsoft 365 安全性 & 規範的授權](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

使用 Microsoft 資訊保護 (MIP) ，協助您探索、分類及保護任何地方生活或傳播的機密資訊。

MIP 功能隨附于 Microsoft 365 規範中，並提供您用來 [瞭解資料](#know-your-data)、 [保護資料](#protect-your-data)，並 [防止資料遺失](#prevent-data-loss)的工具。

![知道您的資料，保護您的資料，避免資料遺失，管理您的資料](../media/powered-by-intelligent-platform.png)

如需有關管理資料的詳細資訊，請參閱 microsoft [365 中的 Microsoft 資訊管理](manage-Information-governance.md)。

## <a name="know-your-data"></a>瞭解您的資料

若要深入瞭解您的資料，並識別整個混合式環境中的重要資料，請使用下列功能：
 
|功能|它會解決什麼問題？|開始使用|
|:------|:------------|:--------------------|:-----------------------------|
|[敏感資訊類型](sensitive-information-type-entity-definitions.md)| 使用內建或自訂正則運算式或函數來識別敏感性資料，以及包含關鍵字、信賴層級及鄰近性的確切證據。| [自訂內建的敏感性資訊類型](customize-a-built-in-sensitive-information-type.md)|
|[Trainable 分類 (預覽) ](classifier-learn-about.md)| 使用內建的分類器之一為您分類資料，或使用您自己的內容訓練分類器 | [開始使用可訓練的分類器 (預覽)](classifier-get-started-with.md) |
|[資料分類](data-classification-overview.md) | 識別具有敏感度標籤、保留標籤，或已分類為組織中機密資訊類型的專案，以及您的使用者所採取的動作  | [開始使用內容總管](data-classification-content-explorer.md)<br /><br /> [開始使用活動瀏覽器](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>保護您的資料

若要套用包括加密、訪問限制和視覺標記的彈性保護動作，請使用下列功能：

|功能|它會解決什麼問題？|開始使用|
|:------|:------------|---------------------|:----------------------------|
|[敏感性標籤](sensitivity-labels.md)| 跨應用程式、服務和裝置的單一解決方案，以標籤及保護您的組織內部和外部的資料 <br /><br />範例案例：套用 [和查看 POWER BI 中的敏感度標籤，並在匯出資料時加以保護](https://docs.microsoft.com/power-bi/admin/service-security-data-protection-overview)|[ 開始使用敏感度標籤](get-started-with-sensitivity-labels.md) |
|[Azure 資訊保護統一標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| 針對 Windows 電腦，擴充敏感度標籤以取得其他功能，包括標記及保護所有檔案類型的檔案 Explorer 和 PowerShell<br /><br /> 範例其他功能： [Azure 資訊保護統一標籤用戶端的自訂](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)設定| [Azure 資訊保護統一標籤用戶端管理員指南](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[雙金鑰加密](double-key-encryption.md)| 在所有情況下，只有您可以解密受保護的內容或法規需求，您必須在地理界限內保留加密金鑰 | [部署雙重金鑰加密](double-key-encryption.md#deploy-double-key-encryption)|
|[Office 365 郵件加密](ome.md) (OME) | 加密傳送給任何裝置上任何使用者的電子郵件訊息和附加檔，因此只有授權的收件者可以讀取以電子郵件傳送的資訊  <br /><br />範例案例： [撤銷由高級郵件加密所加密的電子郵件](revoke-ome-encrypted-mail.md) | [開始使用 Office 365 郵件加密](set-up-new-message-encryption-capabilities.md)|
|[使用客戶金鑰的服務加密](customer-key-overview.md) | 防止未經授權的系統或人員查看資料，並補充 Microsoft 資料中心的 BitLocker 磁片加密。 | [設定 Office 365 客戶金鑰](customer-key-set-up.md)|
|[SharePoint Information Rights Management (IRM) ](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|保護 SharePoint 清單和文件庫，讓使用者在簽出檔時，已下載的檔案受到保護，所以只有經過授權的人員才能根據您指定的原則來查看和使用該檔案。 | [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)|
[版權管理連接器](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |保護-僅適用于使用 Exchange 或 SharePoint 伺服器的現有內部部署，或執行 Windows Server 和檔案分類基礎結構的檔案伺服器 (FCI)  | [部署 RMS 連接器的步驟](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure 資訊保護統一標記掃描器](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| 探索、標籤及保護位於內部部署的資料存放區中的機密資訊。 | [設定及安裝 Azure 資訊保護統一標記掃描器](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| 探索、標籤和保護位於雲端資料存放區中的機密資訊 | [探索、分類、標記和保護儲存在雲端中的控管和敏感性資料](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft 資訊保護 SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|將敏感度標籤擴充至協力廠商應用程式和服務  <br /><br /> 範例案例： [設定並取得敏感度標籤 (c + +) ](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Microsoft 資訊保護 (MIP) SDK 安裝和設定](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|

## <a name="prevent-data-loss"></a>防止資料遺失

若要協助防止意外 oversharing 機密資訊，請使用下列功能：


|功能|它會解決什麼問題？|開始使用|
|:------|:------------|:---------------------|:-----------------------------|
|[資料遺失防護](data-loss-prevention-policies.md) (DLP) | 協助防止意外共用機密專案 <br /><br />範例案例： [保護 Microsoft 小組聊天和通道訊息中的機密資訊](dlp-microsoft-teams.md) | [預設的 DLP 原則快速入門](get-started-with-the-default-dlp-policy.md)|
|[端點資料遺失防護 (預覽) ](endpoint-dlp-learn-about.md)| 將 DLP 功能延伸至 Windows 10 電腦上使用及共用的專案 | [開始使用端點資料外洩防護（預覽版）](endpoint-dlp-getting-started.md)|
