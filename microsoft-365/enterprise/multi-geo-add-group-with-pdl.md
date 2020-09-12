---
title: 使用特定的 PDL 建立 Microsoft 365 群組
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: 瞭解如何在多地理位置環境中，使用指定的慣用資料位置來建立 Microsoft 365 群組。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5af32827d11289f7a966311080d2c15197786799
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547731"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a>使用特定的 PDL 建立 Microsoft 365 群組

在多地理位置環境中的使用者建立 Microsoft 365 群組時，群組慣用資料位置會自動設定為使用者的使用者。 全域、SharePoint 和 Exchange 系統管理員可以在他們所選的任何區域中建立群組。 

如果需要建立具有特定 PDL 的群組，則可以使用 SharePoint 系統管理中心或透過 Exchange Online New-UnifiedGroup Microsoft PowerShell Cmdlet 來執行此動作。 如此一來，將在指定的 PDL 中佈建與該群組關聯的群組信箱和 SharePoint 網站。

若要使用您指定的 PDL 建立 Microsoft 365 群組，請移至您要建立群組網站之地理位置的 SharePoint 系統管理中心。

例如：

如果您要在澳洲位置建立群組網站，您可以移至 https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement

1. 選取 [+ 建立]****。
2. 遵循程序來建立群組網站。

您的群組網站將在與您從中啟動網站建立要求的 SharePoint 系統管理中心對應的地理位置中佈建。 

使用 Exchange PowerShell 

連線至 Exchange Online PowerShell，並傳遞參數 *-MailBoxRegion* 與地理位置代碼。

例如： 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![New-UnifiedGroup PowerShell cmdlet 以及語法的螢幕擷取畫面](../media/multi-geo-new-group-with-pdl-powershell.png)

請注意，SharePoint 群組網站佈建將依照需求。 在群組擁有者或成員首次嘗試存取網站時，會對該網站進行佈建。

## <a name="geo-location-codes"></a>地理位置代碼

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>相關主題

[連線到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)
