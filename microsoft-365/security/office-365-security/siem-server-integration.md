---
title: Microsoft 365 的 SIEM 伺服器整合
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 06/17/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: 摘要： 閱讀本篇文章以取得 Microsoft 365 的 SIEM 伺服器整合的概觀。
ms.openlocfilehash: 97f1c1d1f1862d140e014b4460ac9f40cb1934bb
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078242"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>Microsoft 365 服務和應用程式的 SIEM 伺服器整合

## <a name="overview"></a>概觀

如果您的組織使用的安全性資訊和事件管理 (SIEM) 伺服器，或如果您計劃要推出取得 SIEM 伺服器，您可能想知道如何，將您的 Microsoft 365，包括 Office 365 E5 與整合。 您是否需要 SIEM 伺服器取決於許多因素，例如貴組織的安全性需求。 Microsoft 365 提供各種不同的安全性功能;不過，如果您的組織有內容和應用程式內部部署和雲端 （如混合式雲端部署的大小寫） 中，您可能會考慮新增額外的保護 SIEM 伺服器。 或者，如果您的組織有必須符合的特別嚴格的安全性需求，您可以考慮將 SIEM 伺服器新增至您的環境。

## <a name="siem-server-integration-microsoft-365"></a>SIEM 伺服器整合 Microsoft 365

SIEM 伺服器可以接收來自各種不同的 Microsoft 365 服務和應用程式的資料。 下表列出數個 Microsoft 365 服務和應用程式以及 SIEM 伺服器的輸入和移至深入了解 SIEM 伺服器整合的位置。 

| Microsoft 365 服務或應用程式 | SIEM 伺服器輸入 | 若要了解更多的資源 |
| --- | --- | --- |
| [Office 365 進階威脅防護](office-365-atp.md) <br/>或<br/>[Office 365 威脅情報](office-365-ti.md) | 稽核記錄 | [Office 365 進階威脅防護的 SIEM 整合](siem-integration-with-office-365-ti.md) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | 記錄整合 | [Microsoft Cloud App Security 的 SIEM 整合](https://docs.microsoft.com/cloud-app-security/siem) |
| [Microsoft 威脅防護](https://docs.microsoft.com/windows/security/threat-protection/) | 記錄整合 | [提取提醒您 SIEM 工具](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Azure 資訊安全中心](https://docs.microsoft.com/azure/security-center/security-center-intro)（威脅保護和威脅偵測） | 警示 | [Azure 安全性資料匯出至 SIEM-管線組態-預覽](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
|[Azure 的進階的威脅分析](https://docs.microsoft.com/azure/security/azure-threat-detection) | Azure 的監視器 | [（部落格）使用 Azure 監視器來整合與 SIEM 工具](https://azure.microsoft.com/blog/use-azure-monitor-to-integrate-with-siem-tools) |
|[Azure Active Directory 身分識別保護](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) |記錄整合 |[與 SIEM 整合 Microsoft Graph 安全性 API 提醒](https://docs.microsoft.com/graph/security-siemintegration) |


## <a name="audit-logging-must-be-turned-on"></a>必須先開啟稽核記錄

請確定您在設定 SIEM 伺服器整合之前，開啟稽核記錄。 

- OneDrive for Business 和 Azure Active Directory[稽核記錄在安全 & 合規性中心中已開啟](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)SharePoint online，版本。

- 針對 Exchange Online、[使用 Windows PowerShell 開啟稽核記錄](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)。
 
## <a name="see-also"></a>另請參閱

[雲端採用和混合式解決方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[雲端採用測試實驗室指南 (TLG)](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


