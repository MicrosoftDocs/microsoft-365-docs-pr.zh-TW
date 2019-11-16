---
title: Microsoft 365 服務和應用程式的 SIEM 伺服器整合
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/15/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: 閱讀本篇文章以取得 Microsoft 365 的 SIEM 伺服器整合的概觀。
ms.openlocfilehash: bea6141022fef1275a7e291217f698f52613f170
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677506"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>Microsoft 365 服務和應用程式的 SIEM 伺服器整合

## <a name="summary"></a>摘要

如果您的組織使用的安全性資訊和事件管理 (SIEM) 伺服器，或如果您計劃要推出取得 SIEM 伺服器，您可能想知道如何，將會與 Microsoft 365 或 Office 365 整合。 本文提供的資源清單可用於設定您的 Microsoft 365 服務和應用程式的 SIEM 伺服器整合。

> [!TIP]
> 如果您沒有 SIEM 伺服器，並會瀏覽您的選項，請考慮**[Microsoft Azure 護衛巨像](https://docs.microsoft.com/azure/sentinel/overview)**。

## <a name="do-i-need-a-siem-server"></a>是否需要 SIEM 伺服器？

您是否需要 SIEM 伺服器取決於許多因素，例如貴組織的安全性需求及您的資料所在的位置。 Microsoft 365 也包含各種不同的安全性功能，可以滿足許多組織的安全性需求，沒有其他伺服器，例如 SIEM 伺服器。 某些組織基於要求 SIEM 伺服器使用的特殊情況。 以下為一些範例：

- *Fabrikam*上部署，而部分 （它們有混合式雲端部署） 在雲端中具有某些內容和應用程式。 若要取得所有其內容及應用程式之間的安全性報告，Fabrikam 已實作 SIEM 伺服器。 

- *Contoso*為金融服務組織具有特別嚴格的安全性需求。 若要利用其所需要的額外的安全性保護其環境已加入 SIEM 伺服器。

## <a name="siem-server-integration-with-microsoft-365"></a>Microsoft 365 的 SIEM 伺服器整合

SIEM 伺服器可以接收來自各種不同的 Microsoft 365 服務和應用程式的資料。 下表列出數個 Microsoft 365 服務與應用程式以及 SIEM 伺服器輸入和資源來深入了解 SIEM 伺服器整合。 

| Microsoft 365 服務或應用程式 | SIEM 伺服器輸入 | 可深入了解的資源 |
| --- | --- | --- |
| [Office 365 進階威脅防護](office-365-atp.md)  | 稽核記錄 | [Office 365 進階威脅防護的 SIEM 整合](siem-integration-with-office-365-ti.md) |
| [Windows Defender 進階威脅防護](https://docs.microsoft.com/windows/security/threat-protection/) | 裝載於 Azure 中的 HTTPS 端點 <br/>REST API| [提取提醒您 SIEM 工具](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | 記錄整合 | [Microsoft Cloud App Security 的 SIEM 整合](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> 請看一下[Azure 護衛巨像](https://docs.microsoft.com/azure/sentinel/overview)，隨附於數目超出] 方塊中，並且提供即時的整合，包括 Microsoft 威脅防護解決方案，以及 Microsoft 365 來源，包括 Office 365、 Azure AD，可使用的 Microsoft 解決方案連接器 Azure ATP，以及 Microsoft Cloud App Security，等等。

### <a name="audit-logging-must-be-turned-on"></a>必須先開啟稽核記錄

請確定您在設定 SIEM 伺服器整合之前，開啟稽核記錄。 

- OneDrive for Business 和 Azure Active Directory[稽核記錄在安全 & 合規性中心中已開啟](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)SharePoint online，版本。

- 針對 Exchange Online、[使用 Windows PowerShell 開啟稽核記錄](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)。
 
## <a name="additional-resources"></a>其他資源

[整合 Azure 資訊安全中心中的安全性解決方案](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[與 SIEM 整合 Microsoft Graph 安全性 API 提醒](https://docs.microsoft.com/graph/security-integration)