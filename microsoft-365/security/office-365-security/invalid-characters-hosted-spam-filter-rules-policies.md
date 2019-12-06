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
ms.openlocfilehash: 5e6fa97a3f325b6fc6fdc449ba4a61282f67b644
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866715"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a><span data-ttu-id="e3e0e-103">避免在您的垃圾郵件篩選規則中的無效字元和垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="e3e0e-103">Avoid invalid characters in your spam filter rules and spam filter policy</span></span> 

<span data-ttu-id="e3e0e-104">先前，Office 365 系統管理員設定和使用 Exchange 系統管理中心 (EAC) 來設定垃圾郵件篩選規則和垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="e3e0e-104">Previously, Office 365 administrators set up and configured spam filter rules and the spam filter policy by using the Exchange admin center (EAC).</span></span> <span data-ttu-id="e3e0e-105">現在，您使用安全性&amp;合規性中心，以管理您的反垃圾郵件設定。</span><span class="sxs-lookup"><span data-stu-id="e3e0e-105">Now, you use the Security &amp; Compliance Center to manage the your anti-spam configuration.</span></span> <span data-ttu-id="e3e0e-106">下列字元所支援在 EAC 中，但不是支援使用安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="e3e0e-106">The following characters were supported in the EAC but are not supported for use in the Security &amp; Compliance Center.</span></span>  

<span data-ttu-id="e3e0e-107">**無效字元：**</span><span class="sxs-lookup"><span data-stu-id="e3e0e-107">**Invalid characters:**</span></span>
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

<span data-ttu-id="e3e0e-108">如果您的垃圾郵件篩選器規則或您的垃圾郵件篩選原則中包含任何無效的字元，您可能會發生任何或所有的這些問題：</span><span class="sxs-lookup"><span data-stu-id="e3e0e-108">If your spam filter rules or your spam filter policy contains any of the invalid characters, you might encounter any or all of these issues:</span></span>
- <span data-ttu-id="e3e0e-109">您可能會找不到的原則或規則安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="e3e0e-109">You might be unable to find the policy or rules in the Security &amp; Compliance Center.</span></span>
- <span data-ttu-id="e3e0e-110">嘗試使用 Windows PowerShell 取得的規則或原則時，您可能會收到錯誤。</span><span class="sxs-lookup"><span data-stu-id="e3e0e-110">You might receive errors when trying to get the rules or policy by using Windows PowerShell.</span></span>
- <span data-ttu-id="e3e0e-111">您可能會發現，原則或設定請勿執行，或如預期般執行。</span><span class="sxs-lookup"><span data-stu-id="e3e0e-111">You might find that the policy or settings do not run or perform as expected.</span></span>

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a><span data-ttu-id="e3e0e-112">移除無效的字元的垃圾郵件篩選原則和規則</span><span class="sxs-lookup"><span data-stu-id="e3e0e-112">Remove the invalid characters from the spam filter policy and rules</span></span>

<span data-ttu-id="e3e0e-113">一旦您已識別的原則和規則包含無效的字元，您可以使用 Windows PowerShell cmdlet 變更名稱。</span><span class="sxs-lookup"><span data-stu-id="e3e0e-113">Once you have identified the policy and rules that contain invalid characters, you can change the names by using the Windows PowerShell cmdlets.</span></span> 

1. <span data-ttu-id="e3e0e-114">[連線至 Exchange Online 使用遠端 PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e3e0e-114">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="e3e0e-115">若要變更垃圾郵件篩選器原則的名稱，執行 Set-hostedcontentfilterpolicy 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e3e0e-115">To change the name of the spam filter policy, run the Set-HostedContentFilterPolicy cmdlet as follows:</span></span>
    
    ```powershell
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. <span data-ttu-id="e3e0e-116">若要變更垃圾郵件篩選規則的名稱，執行 Set-hostedcontentfilterrule cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e3e0e-116">To change the name of a spam filter rule, run the Set-HostedContentFilterRule cmdlet as follows:</span></span>
    
    ```powershell
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a><span data-ttu-id="e3e0e-117">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="e3e0e-117">For more information</span></span>

[<span data-ttu-id="e3e0e-118">威脅管理安全性&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="e3e0e-118">Threat management in the Security &amp; Compliance Center</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="e3e0e-119">Set-hostedcontentfilterpolicy</span><span class="sxs-lookup"><span data-stu-id="e3e0e-119">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)

[<span data-ttu-id="e3e0e-120">Set-hostedcontentfilterrule</span><span class="sxs-lookup"><span data-stu-id="e3e0e-120">Set-HostedContentFilterRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule)
