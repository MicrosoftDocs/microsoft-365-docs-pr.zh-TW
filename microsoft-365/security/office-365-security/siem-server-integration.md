---
title: " Microsoft 365 服務與應用程式的安全性資訊和事件管理 (SIEM) server 整合"
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: 取得與 Microsoft 365 雲端服務和應用程式的安全性資訊和事件管理 (SIEM) 伺服器整合的概觀
ms.openlocfilehash: d5adf0a72ac78475cb47f06732375ce01c0d72be
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082192"
---
#  <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Microsoft 365 服務與應用程式的安全性資訊和事件管理 (SIEM) server 整合

## <a name="summary"></a>摘要

是您的組織使用或規劃以取得安全性資訊和事件管理 (SIEM) 伺服器？ 您可能會想知道如何與 Microsoft 365 或 Office 365 整合。 本文提供的資源可用來將 SIEM 伺服器整合的 Microsoft 365 服務和應用程式的清單。

> [!TIP]
> 如果您沒有 SIEM 伺服器，並會瀏覽您的選項，請考慮**[Microsoft Azure 護衛巨像](https://docs.microsoft.com/azure/sentinel/overview)**。

## <a name="do-i-need-a-siem-server"></a>是否需要 SIEM 伺服器？

您是否需要 SIEM 伺服器取決於許多因素，例如貴組織的安全性需求及您的資料所在的位置。 Microsoft 365 也包含各種不同的安全性功能，可以滿足許多組織的安全性需求，沒有其他伺服器，例如 SIEM 伺服器。 某些組織基於要求 SIEM 伺服器使用的特殊情況。 以下為一些範例：

- *Fabrikam*上部署，而部分 （它們有混合式雲端部署） 在雲端中具有某些內容和應用程式。 若要取得所有其內容及應用程式之間的安全性報告，Fabrikam 已實作 SIEM 伺服器。 

- *Contoso*為金融服務組織具有特別嚴格的安全性需求。 若要利用其所需要的額外的安全性保護其環境已加入 SIEM 伺服器。

## <a name="siem-server-integration-with-microsoft-365"></a>Microsoft 365 的 SIEM 伺服器整合

SIEM 伺服器可以接收來自各種不同的 Microsoft 365 服務和應用程式的資料。 下表列出數個 Microsoft 365 服務和應用程式，以及 SIEM 伺服器的輸入和了解更多的資源。 

| Microsoft 365 服務或應用程式 | SIEM 伺服器的輸入/方法 | 可深入了解的資源 |
| --- | --- | --- |
| [Office 365 進階威脅防護](office-365-atp.md)  | 稽核記錄 | [Office 365 進階威脅防護的 SIEM 整合](siem-integration-with-office-365-ti.md) |
| [Windows Defender 進階威脅防護](https://docs.microsoft.com/windows/security/threat-protection/) | 裝載於 Azure 中的 HTTPS 端點 <br/>REST API| [提取提醒您 SIEM 工具](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | 記錄整合 | [Microsoft Cloud App Security 的 SIEM 整合](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> 看看[Azure 護衛巨像](https://docs.microsoft.com/azure/sentinel/overview)。 Azure 警示隨附於 Microsoft 解決方案的連接器。 這些連接器可供 「 現成 」，而且提供即時的整合。 您可以使用 Azure 護衛巨像您的 Microsoft 威脅防護解決方案和 Microsoft 365 服務，包括 Office 365、 Azure AD，Azure ATP、 Microsoft Cloud App Security，等等。

### <a name="audit-logging-must-be-turned-on"></a>必須先開啟稽核記錄

請確定之前設定 SIEM 伺服器整合，開啟稽核記錄。 

- OneDrive for Business 和 Azure Active Directory[稽核記錄在安全 & 合規性中心中已開啟](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)SharePoint online，版本。

- 針對 Exchange Online、[使用 Windows PowerShell 開啟稽核記錄](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)。
 
## <a name="more-resources"></a>其他資源

[整合 Azure 資訊安全中心中的安全性解決方案](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[與 SIEM 整合 Microsoft Graph 安全性 API 提醒](https://docs.microsoft.com/graph/security-integration)
