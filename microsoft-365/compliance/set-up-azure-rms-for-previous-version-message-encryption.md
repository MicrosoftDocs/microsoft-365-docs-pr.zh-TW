---
title: 設定舊版 Office 365 郵件加密的 Azure 版權管理
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: Office 365 邮件加密的早期版本依赖于 Microsoft Azure 权限管理（以前称为 Windows Azure 活动目录权限管理）。
ms.openlocfilehash: 84922a57c6245cf3214f17ba922417b5e025b796
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077393"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a>設定舊版 Office 365 郵件加密的 Azure 版權管理

本主题介绍激活并随后设置 Azure 权限管理 （RMS） 的步骤，这是 Azure 信息保护的一部分，以便与 Office 365 消息加密 （OME） 的早期版本一起使用。

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>本文仅适用于早期版本的 OME
如果您尚未将 Office 365 组织迁移到新的 OME 功能，但已部署 OME，则本文中的信息将应用于您的组织。 Microsoft 建议您在您的组织合理时尽快制定计划，以迁移到新的 OME 功能。 有关说明，请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。 如果要首先了解有关新功能工作方式的更多信息，请参阅[Office 365 邮件加密](ome.md)。 本文的其余部分是指在新的 OME 功能发布之前的 OME 行为。

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>使用早期版本的 Office 365 邮件加密的先决条件
<a name="warmprereqs"> </a>

Office 365 消息加密 （OME） （包括 IRM） 依赖于 Azure 权限管理 （Azure RMS）。 Azure RMS 是 Azure 信息保护所使用的保护技术。 要使用 OME，Office 365 组织必须包括 Exchange 联机或 Exchange 联机保护订阅，而该订阅又包括 Azure 权限管理订阅。
  
- 如果您不确定订阅包含的内容，请参阅[有关消息策略、恢复和合规性](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)的 Exchange 在线服务说明。

- 如果没有用于 Exchange 联机或 Exchange 联机保护的 Azure RMS 订阅，则必须先购买订阅并激活它。

    有关购买 Azure 权限管理的订阅的信息，请参阅[Azure 权限管理](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT)。 下節提供啟動 Azure Rights Management 的資訊。

- 如果您有 Azure 权限管理，但未为 Exchange 联机或 Exchange 联机保护设置，则本文介绍了如何激活 Azure 权限管理，然后介绍了设置 OME 以使用 Azure 权限管理的最佳方式。

- 如果已设置 OME 以使用 Azure 权限管理以进行联机交换或交换联机保护，具体取决于设置方式，则可以立即开始使用 OME 及其新功能。 本文介绍如何确定是否正确设置了 OME，如果需要更改设置该怎么办，以及选择不更改设置会发生什么情况。 例如，为了使用新功能，必须将 Azure RMS 与 OME 一起使用。 不能将新功能与本地活动目录 RMS 一起使用。

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>在 Office 365 中为早期版本的 OME 激活 Azure 权限管理

您需要激活 Azure 权限管理，以便组织中的用户可以对其发送的邮件应用信息保护，并打开受 Azure 权限管理服务保护的邮件和文件。 有关说明，请参阅[激活 Azure 权限管理](https://go.microsoft.com/fwlink/p/?LinkId=525775)。 完成激活后，请返回此处并继续执行本文中的任务。
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>通过导入受信任的发布域 （TLD），将早期版本的 OME 设置为使用 Azure RMS

TPD 是一个 XML 文件，其中包含有关组织权限管理设置的信息。 例如，TPD 包含有关用于签名和加密证书和许可证的服务器许可方证书 （SLC） 的信息、用于许可和发布的 URL 等。 使用 Windows PowerShell 将 TPD 导入 Office 365 组织。
  
> [!IMPORTANT]
> 以前，您可以选择将 TD 从活动目录权限管理服务 （AD RMS） 导入 Office 365 组织。 但是，这样做将阻止您使用新的 OME 功能，并且不建议这样做。 如果 Office 365 组织当前以这种方式配置，Microsoft 建议您创建计划，以便从本地活动目录 RMS 迁移到基于云的 Azure 信息保护。 有关详细信息，请参阅从[AD RMS 迁移到 Azure 信息保护](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。 在完成迁移到 Azure 信息保护之前，您将无法使用新的 OME 功能。
  
 **从 Azure RMS 导入 TD**
  
1. [使用远程电源外壳连接到在线交换。](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)

2. 选择与 Office 365 组织的地理位置对应的密钥共享 URL：

|**位置**|**密钥共享位置 URL**|
|:-----|:-----|
|北美  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|歐盟  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|亚洲  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|南美洲  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 for Government (政府社群雲端)  <br/> 此 RMS 密钥共享位置保留给已为政府 SKU 购买 Office 365 的客户。  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. 通过运行[Set-IRM 配置](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx)cmdlet 来配置密钥共享位置，如下所示： 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    例如，如果您的组织位于北美，则配置密钥共享位置：
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. 使用 -RMSOnline 开关运行[导入-RMS 信任发布域](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx)cmdlet 以从 Azure 权限管理导入 TPD： 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    其中*TPDName*是您要用于 TPD 的名称。 例如，"康托索北美 TPD"。 
    
5. 要验证是否成功配置了 Office 365 组织以使用 Azure 权限管理服务，请使用 -RMSOnline 开关运行[测试 IRM 配置](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx)cmdlet，如下所示： 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    除其他事项外，此 cmdlet 会检查与 Azure 权限管理服务的连接，下载 TPD 并检查其有效性。
    
6. 运行[Set-IRM 配置](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)cmdlet，如下所示，以禁用 Azure 权限管理模板在 Web 和 Outlook 上的 Outlook 中可用： 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. 按如下方式运行[Set-IRM 配置](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)cmdlet，为基于云的电子邮件组织启用 Azure 权限管理，并将其配置为对 Office 365 邮件加密使用 Azure 权限管理： 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. 要验证是否成功导入了 TPD 并启用了 Azure 权限管理，请使用测试 IRM 配置 cmdlet 来测试 Azure 权限管理功能。 有关详细信息，请参阅[测试 IRM 配置](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx)中的"示例 1"。
    
## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>我使用活动目录权限管理而不是 Azure 信息保护设置了早期版本的 OME，我该怎么办？
<a name="importTPDs"> </a>

您可以继续使用现有的 Office 365 邮件加密邮件流规则与活动目录权限管理，但您无法配置或使用新的 OME 功能。 相反，您需要迁移到 Azure 信息保护。 有关迁移及其对组织意味着什么的信息，请参阅从 AD [RMS 迁移到 Azure 信息保护](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)。
  
## <a name="next-steps"></a>後續步驟
<a name="importTPDs"> </a>

完成 Azure 权限管理设置后，如果要启用新的 OME 功能，请参阅[设置在 Azure 信息保护之上构建的新 Office 365 邮件加密功能。](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)
  
将组织设置为使用新的 OME 功能后，即可[定义邮件流规则，以使用新的 OME 功能保护电子邮件。](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="related-topics"></a>相關主題
<a name="importTPDs"> </a>

[Office 365 中的加密](encryption.md)
  
[關於 Office 365 中加密的技術參考細節](technical-reference-details-about-encryption.md)
  
[什么是 Azure 权限管理？](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  

