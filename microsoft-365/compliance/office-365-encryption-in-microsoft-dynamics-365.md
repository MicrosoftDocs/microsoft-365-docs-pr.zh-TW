---
title: 微软动态 365 中的 Office 365 加密
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要：了解微软动态365中的加密。
ms.openlocfilehash: 7c2a352dd712b0db9d2ad623745f854b863dd2e0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077859"
---
# <a name="office-365-encryption-in-microsoft-dynamics-365"></a>微软动态 365 中的 Office 365 加密

Microsoft 使用加密技术在 Microsoft 数据库中静态时保护 Dynamics 365 中的客户数据，并在用户设备和数据中心之间传输。 客户和 Microsoft 数据中心之间建立的连接经过加密，所有公共终结点都使用行业标准 TLS 进行保护。 TLS 有效地建立了安全增强的浏览器到服务器连接，以帮助确保桌面和数据中心之间的数据机密性和完整性。 激活数据加密后，无法将其关闭。 有关详细信息，请参阅[字段级数据加密](https://msdn.microsoft.com/en-us/library/dn481562.aspx)。

Dynamics 365 对一组包含敏感信息（如用户名和电子邮件密码）的默认实体属性使用标准的 Microsoft SQL Server 单元级加密。 此功能可帮助组织满足与 FIPS 140-2 相关的合规性要求。 字段级数据加密在利用[Microsoft Dynamics CRM 电子邮件路由器](https://technet.microsoft.com/en-us/library/hh699800.aspx)的方案中尤其重要，该路由器必须存储用户名和密码，才能在 Dynamics 365 实例和电子邮件服务之间实现集成。 

Dynamics 365 的所有实例都使用[Microsoft SQL Server 透明数据加密](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017)（TDE） 在写入磁盘（静态）时对数据执行实时加密。 TDE 加密 SQL 服务器、Azure SQL 数据库和 Azure SQL 数据仓库数据文件。 默认情况下，Microsoft 会存储和管理 Dynamics 365 实例的数据库加密密钥。 （Dynamics 365 用于财务的密钥由 .NET 框架数据保护 API 生成。 

Dynamics 365 管理中心中的管理密钥功能使管理员能够自行管理与 Dynamics 365 实例关联的数据库加密密钥。 （自管数据库加密密钥仅在 Microsoft Dynamics 365 的 2017 年 1 月更新中可用，可能无法用于更高版本。 有关详细信息，请参阅管理[Dynamics 365（联机）实例的加密密钥。](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-encryption-keys-instance)密钥管理功能同时支持 PFX 和 BYOK 加密密钥文件，例如存储在 HSM 中的文件。 （有关通过 Internet 生成和传输受 HSM 保护的密钥的详细信息，请参阅[如何为 Azure 密钥保管库生成和传输受 HSM 保护的密钥。](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys) 

要使用上载加密密钥选项，您需要公共加密密钥和私有加密密钥。

密钥管理功能通过使用 Azure 密钥保管库安全地存储加密密钥，从而从加密密钥管理中排除了复杂性。 Azure 密钥保管库有助于保护云应用程序和服务使用的加密密钥和机密。 密钥管理功能不要求您具有 Azure 密钥保管库订阅，在大多数情况下，无需访问保管库中用于 Dynamics 365 的加密密钥。
