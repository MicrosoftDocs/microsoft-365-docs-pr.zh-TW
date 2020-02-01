---
title: 關閉 Outlook 網頁版中的垃圾郵件報告
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 0bca03786d0335c24e48340e588510f09d6f6a7e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598120"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>關閉 Outlook 網頁版中的垃圾郵件報告

您可以傳送垃圾郵件、 網路釣魚，並不是垃圾郵件給 Microsoft 上使用 Outlook 網頁 （原先稱為 Outlook Web App） 的垃圾郵件報告選項，在 [[回報垃圾郵件和網路釣魚詐騙網頁型 Outlook 中的](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)所述的分析。 如果您不想要使用這些選項，系統管理員可以關閉它們透過[Set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)指令程式。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？
<a name="sectionSection0"> </a>

- 預估完成時間：5 分鐘

- 您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要的權限，請參閱[Exchange Online 的權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions)中的 「 Outlook web 信箱原則 」 項目。

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

如需詳細的語法及參數資訊，請參閱[Get-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy)和[Set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)。

## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？
<a name="sectionSection2"> </a>

執行**Get-owamailboxpolicy**檢查參數值，然後再開啟 [受影響使用者在網頁型 Outlook （誰具有 [Outlook web 信箱原則上的套用至其），並確認 [回報垃圾郵件、 網路釣魚，並不是垃圾郵件的選項不提供。 您仍然會能夠將郵件標示為垃圾郵件、 網路釣魚和非垃圾郵件，但您無法它們報告。
