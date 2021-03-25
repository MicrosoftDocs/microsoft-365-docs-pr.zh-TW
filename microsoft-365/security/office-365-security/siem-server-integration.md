---
title: SIEM server 與 Microsoft 365 服務與應用程式的整合
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: 深入瞭解安全性資訊和事件管理 (SIEM) 伺服器與您的 Microsoft 365 雲端服務和應用程式整合
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d060b3c12304f6a23ad9421bb43e54c4cd561af5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204844"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>安全性資訊和事件管理 (SIEM) 伺服器與 Microsoft 365 服務和應用程式整合

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>摘要

您的組織是使用或規劃在 SIEM) server (中取得安全性資訊和事件管理嗎？ 您可能會想知道它如何與 Microsoft 365 或 Office 365 整合。 本文提供您可以用來將 SIEM 伺服器與 Microsoft 365 服務和應用程式整合的資源清單。

> [!TIP]
> 如果您還沒有 SIEM 伺服器，且正在探索您的選項，請考慮使用 **[Microsoft Azure Sentinel](/azure/sentinel/overview)**。

## <a name="do-i-need-a-siem-server"></a>我需要 SIEM 伺服器嗎？

您是否需要 SIEM server 取決於許多因素，例如組織的安全性需求和您的資料所在的位置。 Microsoft 365 包含各種各樣的安全性功能，可滿足許多組織的安全性需求，不需要其他伺服器，例如 SIEM server。 有些組織需要使用 SIEM server 的特殊情況。 以下為一些範例：

- *Fabrikam* 在內部部署一些內容和應用程式，而在雲端中有些則 (他們有混合式雲端部署) 。 若要在其所有內容和應用程式中取得安全性報告，Fabrikam 已執行 SIEM 伺服器。

- *Contoso* 是一種金融服務組織，具有特別嚴格的安全性需求。 他們已將 SIEM 伺服器新增至其環境，以充分利用所需的額外安全性保護。

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM server 與 Microsoft 365 的整合

SIEM server 可以從各種各樣的 Microsoft 365 服務和應用程式接收資料。 下表列出數個 Microsoft 365 服務和應用程式，以及 SIEM server 輸入和資源以深入瞭解。

****

|Microsoft 365 服務或應用程式|SIEM 伺服器的輸入/方法|可深入了解的資源|
|---|---|---|
|[適用於 Office 365 的 Microsoft Defender](defender-for-office-365.md)|稽核記錄|[SIEM 與 Microsoft Defender for Office 365 的整合](siem-integration-with-office-365-ti.md)|
|[適用於端點的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/)|Azure 中主控的 HTTPS 端點 <p> REST API|[將提醒納入您的 SIEM 工具](../defender-endpoint/configure-siem.md)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)|記錄整合|[SIEM 與 Microsoft Cloud App Security 的整合](/cloud-app-security/siem)|
|

> [!TIP]
> 請看一下 [Azure Sentinel](/azure/sentinel/overview)。 Azure Sentinel 隨附 Microsoft 解決方案的連接器。 這些連接器可用於「現成」，並提供即時整合。 您可以搭配 Microsoft 365 Defender 解決方案和 Microsoft 365 服務使用 Azure Sentinel，包括 Office 365、Azure AD、Microsoft Defender 身分識別、Microsoft Cloud App Security 等等。

### <a name="audit-logging-must-be-turned-on"></a>必須開啟審核記錄

設定 SIEM server 整合之前，請確定已開啟審核記錄。

- 針對 SharePoint 線上、商務 OneDrive 和 Azure Active Directory， [在安全性 & 規範中心開啟審核記錄](../../compliance/turn-audit-log-search-on-or-off.md)。

- 針對 Exchange Online，請參閱 [管理信箱審核](../../compliance/enable-mailbox-auditing.md)。

## <a name="more-resources"></a>其他資源

[整合 Azure Defender 中的安全性解決方案](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[整合 Microsoft Graph 安全性 API 警示與 SIEM](/graph/security-integration)