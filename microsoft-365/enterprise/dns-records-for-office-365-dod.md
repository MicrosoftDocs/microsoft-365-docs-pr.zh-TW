---
title: Office 365 DoD 的 DNS 記錄
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 摘要： Office 365 DoD 的 DNS 記錄
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688469"
---
# <a name="dns-records-for-office-365-dod"></a>Office 365 DoD 的 DNS 記錄

*本文適用于 Office 365 DoD 和 Microsoft 365 DoD*

加入 Office 365 DoD 的一部分，您必須將您的 SMTP 和 SIP 網域新增至您的線上服務租使用者。  您將使用 Azure AD PowerShell 中的 MsolDomain Cmdlet 來執行這項作業，或使用 [Azure 政府入口網站](https://portal.azure.us) 來開始新增網域及證明擁有權的程式。

當您將網域新增至租使用者並加以驗證之後，請使用下列指引為下列服務新增適當的 DNS 記錄。  您可能需要修改下表，以符合組織對輸入 MX 記錄 () s 的需求，以及您已具備的任何現有 Exchange 自動探索記錄 () 。  強烈建議您將這些 DNS 記錄與您的郵件小組協調，以避免任何中斷或錯誤傳送電子郵件。

## <a name="exchange-online"></a>Exchange Online

| Type (類型) | Priority (優先順序) | 主機名稱 | 指向 [位址] 或 [值] | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | * *mail.protection.office365.us (請參閱下方的其他詳細資料)  | 1 Hour |
| TXT | - | @ | v = spf1 包含: spf.protection.outlook.com office365。美國所有 | 1 小時 |
| CNAME | - | autodiscover | autodiscover-dod.office365.us | 1 Hour |

### <a name="exchange-autodiscover-record"></a>Exchange 自動探索記錄

如果您有 Exchange Server 內部部署，建議您在遷移至 Exchange Online 時保留現有的記錄，並在完成遷移時更新該記錄。

### <a name="exchange-online-mx-record"></a>Exchange Online MX 記錄

公認的網域的 MX 記錄值遵循如上所述的標準 *格式： mail.protection.office365.us*，以您的預設租使用者名稱的第一個部分取代 *承租人* 。

例如，如果您的租使用者名稱是 contoso.onmicrosoft.us，您可以使用 **contoso.mail.protection.office365.us** 做為 MX 記錄的值。

## <a name="skype-for-business-online"></a>商務用 Skype Online

### <a name="cname-records"></a>CNAME 記錄

| 類型 | 主機名稱 | 指向 [位址] 或 [值] | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.dod.skypeforbusiness.us | 1 小時 |
| CNAME | lyncdiscover | webdir.online.dod.skypeforbusiness.us | 1 Hour | 

### <a name="srv-records"></a>SRV 記錄

| Type (類型) | Service (服務) | Protocol (通訊協定) | Port (連接埠) | 字體粗細 | 優先順序 | 名稱 | Target (目標) | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_Tls | 443 | 1 | 100 | @ | sipdir.online.dod.skypeforbusiness.us | 1 Hour (1 小時) |
| SRV | \_sipfederationtls | \_Tcp | 5061 | 1 | 100 | @ | sipfed.online.dod.skypeforbusiness.us | 1 Hour |

## <a name="additional-dns-records"></a>其他 DNS 記錄

> [!IMPORTANT]
> 如果您的 DNS 區域中有現有的 *msoid* CNAME 記錄，您必須在這段時間內從 DNS **移除** 記錄。  Msoid 記錄與 Microsoft 365 企業版應用程式不相容 * (以前的 Office 365 ProPlus) * 而且會使啟用不再成功。
