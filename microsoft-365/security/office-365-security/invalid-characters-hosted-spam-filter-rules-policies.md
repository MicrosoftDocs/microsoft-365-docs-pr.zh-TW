---
title: 避免垃圾郵件篩選規則和垃圾郵件篩選原則中的無效字元
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/24/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 提供其反垃圾郵件組態中有無效的字元，並嘗試使用安全性時遇到問題的系統管理員的說明&amp;合規性中心。
ms.openlocfilehash: 96d81c17c33c5ecf6e7b88ebe5676336b963cb4e
ms.sourcegitcommit: 550ea6f093ec35182e7c65a2811e9bfb07ec7d01
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2019
ms.locfileid: "38039102"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a>避免在您的垃圾郵件篩選規則中的無效字元和垃圾郵件篩選原則 

先前，Office 365 系統管理員設定和使用 Exchange 系統管理中心 (EAC) 來設定垃圾郵件篩選規則和垃圾郵件篩選原則。 現在，您使用安全性&amp;合規性中心，以管理您的反垃圾郵件設定。 下列字元所支援在 EAC 中，但不是支援使用安全性&amp;合規性中心。  

**無效字元：**
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

如果您的垃圾郵件篩選器規則或您的垃圾郵件篩選原則中包含任何無效的字元，您可能會發生任何或所有的這些問題：
- 您可能會找不到的原則或規則安全性&amp;合規性中心。
- 嘗試使用 Windows PowerShell 取得的規則或原則時，您可能會收到錯誤。
- 您可能會發現，原則或設定請勿執行，或如預期般執行。

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a>移除無效的字元的垃圾郵件篩選原則和規則

一旦您已識別的原則和規則包含無效的字元，您可以使用 Windows PowerShell cmdlet 變更名稱。 

1. [連線至 Exchange Online 使用遠端 PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。
    
2. 若要變更垃圾郵件篩選器原則的名稱，執行 Set-hostedcontentfilterpolicy 指令程式，如下所示：
    
    ```powershell
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. 若要變更垃圾郵件篩選規則的名稱，執行 Set-hostedcontentfilterrule cmdlet，如下所示：
    
    ```powershell
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a>相關資訊

[威脅管理安全性&amp;合規性中心](protect-against-threats.md)
  
[Set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[Set-hostedcontentfilterrule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)
