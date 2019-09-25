---
title: DLP 如何在安全性與合規性中心和 Exchange 系統管理中心之間工作
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 了解安全&合规性中心的 DLP 如何与 Exchange 管理中心中的 DLP 和邮件流规则（传输规则）配合使用。
ms.openlocfilehash: 65df871361eca66dca543cd2a6dcb0a529446169
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076975"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>DLP 如何在安全性與合規性中心和 Exchange 系統管理中心之間工作

在 Office 365 中，您可以在两个不同的管理中心中创建数据丢失防护 （DLP） 策略：
  
- 在**安全&合规性中心**中，您可以创建单个 DLP 策略来帮助保护 SharePoint、OneDrive、Exchange 和现在的 Microsoft 团队中的内容。 如果可能，我们建议您在此处创建 DLP 策略。 有关详细信息，请参阅[安全&合规性中心中的 DLP。](data-loss-prevention-policies.md)
    
- 在**Exchange 管理中心**中，您可以创建 DLP 策略来帮助仅保护 Exchange 中的内容。 此策略可以使用 Exchange 邮件流规则（也称为传输规则），因此它具有特定于处理电子邮件的更多选项。 有关详细信息，请参阅[Exchange 管理中心中的 DLP。](https://go.microsoft.com/fwlink/?linkid=852311)
    
在这些管理中心创建的 DLP 策略并行工作 - 本主题说明如何。
  
![安全和合规中心和 Exchange 管理中心的 DLP 页面](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>安全&合规性中心的 DLP 如何与 Exchange 管理中心中的 DLP 和邮件流规则配合使用

在安全&合规性中心创建 DLP 策略后，该策略将部署到策略中包含的所有位置。 如果策略包括 Exchange Online，则策略在那里同步，并且执行的方式与在 Exchange 管理中心创建的 DLP 策略完全相同。 
  
如果您在 Exchange 管理中心中创建了 DLP 策略，则这些策略将继续与您在安全&合规性中心创建的电子邮件的任何策略并行工作。 但请注意，在 Exchange 管理中心创建的规则优先。 首先处理所有 Exchange 邮件流规则，然后处理安全&合规性中心的 DLP 规则。
  
这意味着：
  
- 在安全&合规性中心创建的 DLP 规则不会扫描被 Exchange 邮件流规则阻止的邮件。
    
- 如果 Exchange 邮件流规则修改邮件的方式使其与安全&合规性中心（如添加外部用户）中的 DLP 策略匹配，则 DLP 规则将检测此规则并根据需要强制实施策略。
    
另请注意，使用"停止处理"操作的 Exchange 邮件流规则不会影响安全&合规性中心中的 DLP 规则处理 - 它们仍将被处理。
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>安全&合规中心与 Exchange 管理中心的策略提示

策略提示既可用于在 Exchange 管理中心创建的 DLP 策略和邮件流规则，也可用于在安全&合规性中心创建的 DLP 策略，但不能同时使用这两种策略。 这是因为这些策略存储在不同的位置，但策略提示只能从单个位置提取。
  
如果您在 Exchange 管理中心中配置了策略提示，则在"安全&合规性中心"中配置的任何策略提示将不会在 Web 上的 Outlook 和 Outlook 2013 及更高版本中向用户显示，直到您关闭 Exchange 管理中心中的提示。 这可确保您当前的 Exchange 邮件流规则将继续工作，直到您选择切换到安全&合规中心。
  
请注意，虽然策略提示只能从单个位置提取，但始终会发送电子邮件通知，即使您在安全&合规中心和 Exchange 管理中心使用 DLP 策略也是如此。
  

