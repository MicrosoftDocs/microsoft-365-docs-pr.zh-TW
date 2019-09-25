---
title: Office 365 中的加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 使用 Office 365，您的内容在静态和传输过程中使用最强的加密、协议和技术进行加密。 获取 Office 365 中加密的概述。
ms.openlocfilehash: 1dd31990e4a284c81ce9fa8b2aced45b8a06a0c6
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077080"
---
# <a name="encryption-in-office-365"></a>Office 365 中的加密

加密是文件保护和信息保护策略的重要组成部分。 本文概述了 Office 365 的加密。 获取有关加密任务的帮助，例如如何为组织设置加密以及如何对 Office 文档进行密码保护。
  
- 有关证书和技术（如 TLS）的信息，请参阅[Office 365 中有关加密的技术参考详细信息。](technical-reference-details-about-encryption.md)

- 有关如何为组织配置或设置加密的信息，请参阅[在 Office 365 企业版中设置加密。](set-up-encryption.md)

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>什么是加密，它在 Office 365 中如何工作？

加密过程将数据（称为纯文本）编码为密文。 与纯文本不同，除非和直到解密密文，否则人或计算机不能使用密文。 解密需要只有授权用户才能拥有的加密密钥。 加密有助于确保只有经过授权的收件人才能解密您的内容。 内容包括文件、电子邮件、日历条目等。
  
加密本身并不会阻止内容拦截。 加密是组织更大信息保护策略的一部分。 通过使用加密，有助于确保只有授权方才能使用加密数据。
  
您可以同时实施多层加密。 例如，您可以加密电子邮件以及电子邮件流经的通讯渠道。 使用 Office 365，您的数据在静态和传输过程中进行加密，使用多种强加密协议以及包括传输层安全/安全套接字层 （TLS/SSL）、Internet 协议安全 （IPSec） 和高级加密在内的技术标准 （AES）。
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>静态数据和传输中数据的加密

 **静止数据的示例**包括已上载到 SharePoint 库的文件、联机项目数据、在 Skype 业务会议中上载的文档、存储在 Office 365 文件夹中的电子邮件和附件邮箱，以及已上载到 OneDrive 的业务文件。
  
 **传输中的数据示例**包括正在传递的邮件消息或联机会议中发生的对话。 在 Office 365 中，每当用户的设备与 Office 365 服务器通信，或者当 Office 365 服务器与另一台服务器通信时，数据都会传输。
  
借助 Office 365，多层和多种加密协同工作来保护数据。 下表包含一些示例，其中包含指向其他信息的链接。
  
|**内容种类**|**加密技术**|**要了解更多信息的资源**|
|:-----|:-----|:-----|
|设备上的文件。 这些文件可以包括保存在文件夹中的电子邮件、保存在计算机、平板电脑或手机上的 Office 文档或保存到 Microsoft 云中的数据。  <br/> |微软数据中心中的 BitLocker。 BitLocker 也可用于客户端计算机，如 Windows 计算机和平板电脑  <br/> 微软数据中心中的分布式密钥管理器 （DKM）  <br/> Office 365 的客戶金鑰  <br/> |[Windows IT 中心：位锁](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [微软信任中心：加密](https://www.microsoft.com/en-us/TrustCenter/Security/Encryption) <br/> [云安全控制系列：静态加密数据](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Exchange Online 如何保護您的電子郵件機密資料](exchange-online-secures-email-secrets.md) <br/> [使用客戶金鑰控制 Office 365 中的資料](controlling-your-data-using-customer-key.md) <br/> |
|用户之间传输的文件。 这些文件可以包括 Office 文档或用户之间共享的 SharePoint 列表项。  <br/> |传输中文件的 TLS  <br/> |[商務用 OneDrive 和 SharePoint Online 中的資料加密](data-encryption-in-odb-and-spo.md) (英文) <br/> [业务在线 Skype：安全和存档](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|收件人之间正在传输的电子邮件。 此电子邮件包括由 Exchange 在线托管的电子邮件。  <br/> |Office 365 邮件加密，具有 Azure 权限管理、S/MIME 和 TLS，用于传输中的电子邮件  <br/> |[Office 365 郵件加密 (OME)](ome.md) <br/> [Office 365 中的電子郵件加密](email-encryption.md) <br/> [Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>如果我需要对加密进行更多控制以满足安全性和合规性要求，该怎么办？

Office 365 在 Office 365 中为卷加密、文件加密和邮箱加密提供了 Microsoft 管理的解决方案。 此外，Office 365 还提供您可以管理和控制的加密解决方案。 这些加密解决方案基于 Azure 构建。
  
要了解更多信息，请参阅以下资源：
  
- [什么是 Azure 权限管理？](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [在管理中心激活权限管理](https://support.office.com/article/5b6d3ac7-b1ac-428e-b03e-50e882f85a6e)

- [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)

- [使用客戶金鑰控制 Office 365 中的資料](controlling-your-data-using-customer-key.md)

## <a name="how-do-i"></a>我要如何...

|**完成此任务**|**查看这些资源**|
|:-----|:-----|
|为我的组织设置加密  <br/> |[設定 Office 365 企業版中的加密](set-up-encryption.md) <br/> |
|在 Office 365 中查看有关证书、技术和 TLS 密码套件的详细信息  <br/> |[有关 Office 365 中加密的技术详细信息](technical-reference-details-about-encryption.md) <br/> |
|在移动设备上处理加密邮件  <br/> |[在 Android 设备上查看加密邮件](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [在 iPhone 或 iPad 上查看加密邮件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|使用密码保护加密文档  <br/><br/>  在浏览器中的 Office 365 不支持密码保护。 使用桌面版本的 Word、Excel 和 PowerPoint 进行密码保护。 |[在文档、工作簿或演示文稿中添加或删除保护](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> 选择"**添加保护"** 部分，然后请参阅**使用密码加密**。  |
|从文档中删除加密  <br/> |[在文档、工作簿或演示文稿中添加或删除保护](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> 选择"**删除保护"** 部分，然后请参阅**删除密码加密**。  |

## <a name="related-topics"></a>相關主題

[规划 Office 365 安全和信息保护功能](plan-for-security-and-compliance.md)

[保护 Office 365 和 Microsoft 365 商业计划的十大方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data?view=o365-worldwide)
