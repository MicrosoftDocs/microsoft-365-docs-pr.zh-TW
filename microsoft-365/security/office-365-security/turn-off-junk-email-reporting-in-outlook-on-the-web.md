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
ms.openlocfilehash: de0e5d1aa51ececafc0d344b9907f6751a613370
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441170"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>關閉 Outlook 網頁版中的垃圾郵件報告

您可以傳送垃圾郵件、 網路釣魚，並不是垃圾郵件給 Microsoft 上使用 Outlook 網頁 （原先稱為 Outlook Web App） 的垃圾郵件報告選項，在 [[回報垃圾郵件和網路釣魚詐騙網頁型 Outlook 中的](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)所述的分析。 如果您不想要使用這些選項，系統管理員可以關閉它們透過[Set-owamailboxpolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx)指令程式。 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？
<a name="sectionSection0"> </a>

- 預估完成時間：5 分鐘
    
- 您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要的權限，請參閱[Outlook 在網站權限](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp)主題中的 「 Outlook web 信箱原則 」 項目。 

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>關閉 [垃圾郵件、 網路釣魚和非垃圾郵件回報給 Microsoft
<a name="sectionSection1"> </a>

首先，執行下列命令，以取得名稱您可以使用的 Outlook web 上的信箱原則：
  
```
Get-OwaMailboxPolicy | Format-Table Name
```

接下來，啟用或停用垃圾郵件和非垃圾郵件回報給 Microsoft 網頁型 Outlook 中使用下列語法：
  
```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

本範例會關閉預設 Outlook web app 信箱原則中的報告：
  
```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

如需詳細的語法及參數資訊，請參閱[Get-owamailboxpolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx)和[Set-owamailboxpolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx)。

## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？
<a name="sectionSection2"> </a>

執行**Get-owamailboxpolicy**檢查參數值，然後再開啟 [受影響使用者在網頁型 Outlook （誰具有 [Outlook web 信箱原則上的套用至其），並確認 [回報垃圾郵件、 網路釣魚，並不是垃圾郵件的選項不提供。 您仍然會能夠將郵件標示為垃圾郵件、 網路釣魚和非垃圾郵件，但您無法它們報告。 
