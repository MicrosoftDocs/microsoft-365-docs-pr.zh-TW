---
title: 關閉 Outlook 網頁版中的垃圾郵件報告
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: 身為 Office 365 系統管理員，您可以關閉的能力人員報告電子郵件為垃圾郵件。
ms.openlocfilehash: 46ce4de8fa6ea14c81041208864957cbc73aebf5
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871279"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="740fa-103">關閉 Outlook 網頁版中的垃圾郵件報告</span><span class="sxs-lookup"><span data-stu-id="740fa-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="740fa-104">您可以傳送垃圾郵件、 網路釣魚，並不是垃圾郵件給 Microsoft 上使用 Outlook 網頁 （原先稱為 Outlook Web App） 的垃圾郵件報告選項，在 [[回報垃圾郵件和網路釣魚詐騙網頁型 Outlook 中的](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)所述的分析。</span><span class="sxs-lookup"><span data-stu-id="740fa-104">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web (formerly known as Outlook Web App) junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span></span> <span data-ttu-id="740fa-105">如果您不想要使用這些選項，系統管理員可以關閉它們透過[Set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)指令程式。</span><span class="sxs-lookup"><span data-stu-id="740fa-105">If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) cmdlet.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="740fa-106">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="740fa-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="740fa-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="740fa-107"></span></span>

- <span data-ttu-id="740fa-108">預估完成時間：5 分鐘</span><span class="sxs-lookup"><span data-stu-id="740fa-108">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="740fa-109">您必須已獲指派權限，才能執行此程序或這些程序。</span><span class="sxs-lookup"><span data-stu-id="740fa-109">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="740fa-110">若要查看您需要的權限，請參閱[Exchange Online 的權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions)中的 「 Outlook web 信箱原則 」 項目。</span><span class="sxs-lookup"><span data-stu-id="740fa-110">To see what permissions you need, see the "Outlook on the web mailbox policies" entry in [Exchange Online permissions](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).</span></span>

- <span data-ttu-id="740fa-111">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="740fa-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="740fa-112">關閉 [垃圾郵件、 網路釣魚和非垃圾郵件回報給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="740fa-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="740fa-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="740fa-113"></span></span>

<span data-ttu-id="740fa-114">首先，執行下列命令，以取得名稱您可以使用的 Outlook web 上的信箱原則：</span><span class="sxs-lookup"><span data-stu-id="740fa-114">First, run the following command to get the names of your available Outlook on the web mailbox policies:</span></span>

```
Get-OwaMailboxPolicy | Format-Table Name
```

<span data-ttu-id="740fa-115">接下來，啟用或停用垃圾郵件和非垃圾郵件回報給 Microsoft 網頁型 Outlook 中使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="740fa-115">Next, use the following syntax to enable or disable junk and not junk reporting to Microsoft in Outlook on the web:</span></span>

```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

<span data-ttu-id="740fa-116">本範例會關閉預設 Outlook web app 信箱原則中的報告：</span><span class="sxs-lookup"><span data-stu-id="740fa-116">This example turns off reporting in the default Outlook web app mailbox policy:</span></span>

```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

<span data-ttu-id="740fa-117">如需詳細的語法及參數資訊，請參閱[Get-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy)和[Set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="740fa-117">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="740fa-118">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="740fa-118">How do you know this worked?</span></span>
<span data-ttu-id="740fa-119"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="740fa-119"></span></span>

<span data-ttu-id="740fa-120">執行**Get-owamailboxpolicy**檢查參數值，然後再開啟 [受影響使用者在網頁型 Outlook （誰具有 [Outlook web 信箱原則上的套用至其），並確認 [回報垃圾郵件、 網路釣魚，並不是垃圾郵件的選項不提供。</span><span class="sxs-lookup"><span data-stu-id="740fa-120">Run **Get-OWAMailboxPolicy** to check the parameter values, and then open Outlook on the web for an affected user (who has the Outlook on the web mailbox policy applied to them) and verify that the options to report junk, phishing, and not junk are not available.</span></span> <span data-ttu-id="740fa-121">您仍然會能夠將郵件標示為垃圾郵件、 網路釣魚和非垃圾郵件，但您無法它們報告。</span><span class="sxs-lookup"><span data-stu-id="740fa-121">You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span>
