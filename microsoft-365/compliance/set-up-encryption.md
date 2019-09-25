---
title: 設定 Office 365 企業版中的加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: 使用 Office 365 时，某些加密功能默认处于打开状态;因此，默认情况下，某些加密功能将处于打开状态。可以配置其他功能以满足某些合规性或法律要求。
ms.openlocfilehash: 3bb76d70bd364bd461721d6277516801b3675031
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077389"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>設定 Office 365 企業版中的加密

加密可以保护您的内容不被未经授权的用户读取。 由于[Office 365 中的加密](encryption.md)可以使用各种技术和方法完成，因此没有一个位置可以打开或设置加密。 本文提供有关作为信息保护策略的一部分设置或配置加密的各种方法的信息。
  
> [!TIP]
> 如果要了解有关加密的更多技术详细信息，请参阅[Office 365 中有关加密的技术参考详细信息。](technical-reference-details-about-encryption.md)
  
使用 Office 365 时，默认情况下可以使用多个加密功能。 可以配置其他加密功能以满足某些合规性或法律要求。 下表描述了针对不同方案的几种加密方法。
  
|**案例**|**加密方法**|
|:-----|:-----|
|文件保存在 Windows 计算机上  <br/> |可以在 Windows 设备上使用 BitLocker 在计算机级别进行加密。 作为企业管理员或 IT 专业版，您可以使用 Microsoft 部署工具包 （MDT） 进行设置。 请参阅[为 BitLocker 设置 MDT](https://go.microsoft.com/fwlink/?linkid=849282)。  <br/> |
|文件保存在移动设备上  <br/> |某些类型的移动设备对默认情况下保存到这些设备的文件进行加密。 借助[Office 365 的内置移动设备管理功能，](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0)您可以设置策略，以确定是否允许移动设备访问 Office 365 中的数据。 例如，您可以设置一个策略，该策略只允许加密内容的设备访问 Office 365 数据。 请参阅[创建和部署设备安全策略](https://support.office.com/article/d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)。  <br/> 为了进一步控制移动设备与 Office 365 交互的方式，可以考虑添加[Microsoft Intune](https://aka.ms/qzln04)。 请参阅[在 Office 365 和 Microsoft Intune 的 MDM 之间进行选择。](https://support.office.com/article/c93d9ab9-efb2-4349-9b93-30c30562ee22)  <br/> |
|您需要控制用于加密 Microsoft 数据中心中数据的加密密钥  <br/> | 作为 Office 365 管理员，您可以控制组织的加密密钥，然后将 Office 365 配置为使用它们在 Microsoft 数据中心中静态加密数据。  <br/> [使用客戶金鑰控制 Office 365 中的資料](controlling-your-data-using-customer-key.md) <br/> [Office 365 常见问题解答的客户密钥](service-encryption-with-customer-key-faq.md) <br/> |
|人们通过电子邮件进行交流（在线交流）  <br/> | 作为 Exchange 在线管理员，您有多种配置电子邮件加密的选项。 這些包括：  <br/>  将[Office 365 邮件加密 （OME）](set-up-new-message-encryption-capabilities.md)与 Azure 权限管理 （Azure RMS） 结合使用，使用户能够在组织内部或外部发送加密邮件  <br/>  使用[S/MIME 进行邮件签名和加密，](https://aka.ms/c6dozg)以加密和对电子邮件进行数字签名  <br/>  使用 TLS[设置连接器，以便与其他组织建立安全邮件流](https://aka.ms/hs809p) <br/>  请参阅[Office 365 中的电子邮件加密。](https://aka.ms/hic3f7)  <br/> |
|从团队网站或文档库访问文件（一个适用于企业或共享点联机）  <br/> |当用户处理保存到 OneDrive 的业务或共享点联机的文件时，将使用 TLS 连接。 这会自动内置到 Office 365 中。 请参阅[单一驱动器中的数据加密业务和共享点在线](https://go.microsoft.com/fwlink/?linkid=526379)。  <br/> |
|文件在联机会议和 IM 对话中共享（业务联机的 Skype）  <br/> |当用户使用 Skype 进行联机业务时，TLS 用于连接。 这会自动内置到 Office 365 中。 请参阅[安全和存档（业务在线的 Skype）。](https://aka.ms/nuq4ws)  <br/> |

## <a name="additional-information"></a>其他資訊

要了解有关包含加密选项的文件保护解决方案的详细信息，请参阅[Office 365 中的文件保护解决方案。](https://www.microsoft.com/en-us/download/details.aspx?id=55523)