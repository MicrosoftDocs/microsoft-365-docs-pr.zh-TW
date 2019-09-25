---
title: 保護資訊
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/26/2019
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 用于保护信息的登录页
ms.openlocfilehash: 77b4332ae4c5450f7464af660e3cda82ddbe18a5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077806"
---
# <a name="protect-information"></a>保護資訊

Microsoft 365 和 Office 365 包括可应用于特定类型数据以保护信息的功能。


|**功能**|**詳細資訊**|
|:-----|:-----|
|[敏感度標籤](sensitivity-labels.md) <br/> |通过敏感度标签，您可以对敏感内容进行分类并帮助保护您的敏感内容。 保护选项包括标签、水印和加密。 敏感度标签使用 Azure 信息保护。 如果使用 Azure 信息保护标签，现在我们建议您在完成迁移之前避免在其他管理中心创建新标签。 请参阅[Azure 信息保护迁移](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-migrate-labels)。 <br/> [保留标签](retention-policies.md)与灵敏度标签不同。 保留标签可帮助您根据定义的策略保留或删除内容。 这些帮助组织遵守行业法规和内部政策。|
|[数据丢失防护](data-loss-prevention-policies.md)（DLP）  <br/> |使用 DLP 策略，您可以识别、监视和自动保护 Office 365 中敏感信息。 数据丢失防护策略可以使用敏感度标签和敏感信息类型来标识敏感信息。 <br/> |
|[敏感資訊類型](what-the-sensitive-information-types-look-for.md) <br/> |Microsoft 365 包含许多敏感信息类型，可供您在 DLP 策略中使用，并可用于使用敏感度和保留标签的自动分类。 敏感信息类型还可用于[Azure 信息保护扫描程序，](https://docs.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner)以对本地文件进行分类和保护。 敏感信息类型定义自动过程如何识别特定信息类型，如运行状况服务编号和信用卡号。   <br/> |
|[Office 365 邮件加密](ome.md)（OME）  <br/> |借助 Office 365 邮件加密，您的组织可以在组织内外人员之间发送和接收加密的电子邮件。 Office 365 邮件加密适用于Outlook.com、雅虎、Gmail 和其他电子邮件服务。 电子邮件加密有助于确保只有目标收件人才能查看邮件内容。 <br/> |
|[Azure 資訊保護](https://docs.microsoft.com/en-us/azure/information-protection/)<br/> |Azure 信息保护（有时称为 AIP）可帮助组织对文档和电子邮件进行分类、标记和选择保护。 管理员可以通过定义规则和条件自动应用标签。 用户可以手动将标签应用于文件和邮件。 您还可以向用户提供有关何时应用标签的建议。<br/> 如果您使用的是敏感度标签或 Office 邮件加密，则表示您已经在使用分类和保护功能。 如果尚未将 Azure 信息保护标签迁移到 Office 365，请继续在 Azure 信息保护中管理这些标签。  <br/>您可以在本地运行[Azure 信息保护扫描程序，](https://docs.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner)以对 Windows 服务器、网络共享和 SharePoint 服务器站点和库中的文件进行分类和保护。 这可能是识别要迁移到 Office 365 的数据的第一步。
|使用客户托管加密密钥的 Azure 信息保护 <br/> |某些组织具有保留对加密密钥的控制的业务需求或合规性要求。 这是不常见的。 Azure 信息保护允许组织将您自己的密钥 （BYOK） 带到服务中。 有关详细信息，请参阅[自带 Azure 信息保护密钥 （BYOK）。](https://docs.microsoft.com/en-us/azure/information-protection/byok-price-restrictions) 另一个更复杂的选项是提供给客户谁有要求在本地保留加密密钥，称为持有自己的密钥 （HYOK）。  有关详细信息，请参阅[保留自己的密钥 （HYOK） 进行 Azure 信息保护](https://docs.microsoft.com/en-us/azure/information-protection/configure-adrms-restrictions)。 <br/> |
    

