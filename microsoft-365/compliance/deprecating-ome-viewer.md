---
title: 弃用 Office 365 消息加密查看器应用程序
ms.author: krowley
author: kccross
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
description: 2018 年 8 月 15 日，我们将从 Android 和 Apple 商店中删除 Office 365 消息加密 （OME） 查看器移动应用。 Office 365 消息加密查看器移动应用程序需要读取与 Apple 和 Android 手机上以前的 OME 版本加密的电子邮件和附件。 除了删除 OME 查看器应用外，我们不会对早期版本的 OME 进行任何其他更改。
ms.openlocfilehash: 3b5c92d4fa700a1ae8d7b104e33100301cf43506
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076358"
---
# <a name="deprecating-office-365-message-encryption-viewer-app"></a>弃用 Office 365 消息加密查看器应用程序

2018 年 8 月 15 日，我们从 Android 和 Apple 商店中删除了 Office 365 消息加密 （OME） 查看器移动应用。 Office 365 消息加密查看器移动应用程序需要读取与 Apple 和 Android 手机上以前的 OME 版本加密的电子邮件和附件。 除了删除 OME 查看器应用外，我们不会对早期版本的 OME 进行任何其他更改。
  
## <a name="changes-from-august-2018"></a>2018 年 8 月起更改

正如 2017 年 9 月宣布的那样，我们发布了新版本的[Office 365 消息加密，](https://aka.ms/ome2017)以便用户可以在无需移动应用要求的情况下向组织内外的任何人发送加密和受保护的消息。 此后，我们添加了其他功能：
  
- [仅加密模板](https://aka.ms/encryptonly)

- [控制解密附件](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
通过此更改，用户将无法从 8 月 1 日起下载 Office 365 消息加密查看器移动应用。 因此，邮件收件人可能无法在某些 Android 和 Apple 移动设备上读取使用早期版本的 OME 加密的邮件。 但是，他们仍然可以在个人计算机上（通过桌面浏览器）读取这些消息。 已下载应用的用户将继续能够使用它。
  
## <a name="why-this-change-was-made"></a>为什么进行此更改

新版本的 OME 不再需要移动应用来读取受保护的电子邮件和附件。 使用新的 OME 功能的 Office 365 客户可以在 Outlook 移动版中查看受保护的邮件，非 Office 365 客户可以在浏览器中查看受保护的邮件。
  
要求用户下载移动应用是客户查看受保护邮件的另一个障碍。 新的 Office 365 消息加密功能提供了更好的移动体验。
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>我能否仍然使用 Office 365 邮件加密的早期版本

Office 365 邮件加密的早期版本此时不会弃用，但是，我们对新版本的 Office 365 消息加密进行了重大增强，从而更易于加密，并有权保护任何人的敏感数据在任何设备上 - 包括 Office 365 用户直接在 Outlook（桌面、移动和 Web）中读取受保护邮件的功能。 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>我需要做什么来准备这种变化

如果您的组织当前向需要 OME 查看器应用的收件人发送加密附件，则应更新文档和培训资源。
  
我们建议更新现有的 Exchange 邮件流规则以使用当前版本的 OME，以便您的组织可以利用新的和改进的功能。 设置新的 OME 功能后，收件人将不需要 OME 查看器应用来读取移动设备上的加密邮件。
  
Microsoft 建议您在您的组织合理时尽快制定计划，以迁移到新的 OME 功能。 有关说明，请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。 如果要首先了解有关新功能工作方式的更多信息，请参阅[Office 365 邮件加密](ome.md)。
  

