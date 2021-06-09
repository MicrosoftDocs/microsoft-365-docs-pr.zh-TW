---
title: OneDrive 和 SharePoint Online 中的多地理位置功能
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: 使用 OneDrive Online 的多地理位置功能，將 Microsoft 365 的目前狀態拓展至多個地理區域。
ms.openlocfilehash: 8f42b071abef0602304f1a468190c33700fe3e82
ms.sourcegitcommit: 321610fd312e5c54ae8a757a71ab0c9fd2f1ac03
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/11/2020
ms.locfileid: "48995906"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a>OneDrive 和 SharePoint Online 中的多地理位置功能

OneDrive 和 SharePoint Online 中的多地理位置功能可讓您控制共用資源，例如 SharePoint 小組網站，以及儲存在全國或地區中的 Microsoft 365 群組信箱。

每個使用者、群組信箱和 SharePoint 網站會有慣用的資料位置 (PDL)，這表示儲存相關資料所在的地理位置。 使用者的個人資料 (Exchange 信箱和 OneDrive) 以及他們所建立的任何 Microsoft 365 群組或 SharePoint 網站，可以儲存在指定的地理位置，以滿足資料落地需求。 您可以[為每個地理位置指定不同的系統管理員](add-a-sharepoint-geo-admin.md)。

使用者使用 Microsoft 365 服務，包括 Office 應用程式、OneDrive 及搜尋時，可獲得順暢的體驗。 如需詳細資料，請參閱[多地理位置環境中的使用者體驗](multi-geo-user-experience.md)。

## <a name="onedrive"></a>OneDrive

每位使用者的 OneDrive 可以佈建在其中或根據使用者的 PDL [由系統管理員移動](move-onedrive-between-geo-locations.md)到衛星位置。 然後個人檔案會保存在該地理位置，不過可以與其他地理位置中的使用者共用這些檔案。

## <a name="sharepoint-sites-and-groups"></a>SharePoint 網站與群組

多地理位置功能的管理可透過 SharePoint 管理中心取得。 您可以在[對應的部落格文章](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)中找到詳細的資訊。

當使用者建立多重地理環境中 SharePoint 群組連接的網站時，其 PDL 可用來判斷建立網站和其相關聯群組信箱所在的地理位置。 (如果使用者的 PDL 值尚未設定，或是設為尚未設定為衛星位置的地理位置，則會在中央位置建立網站和信箱。)

Exchange、OneDrive 及 SharePoint 以外的 Microsoft 365 服務並非多地理位置。 不過，這些服務所建立的 Microsoft 365 群組會加上建立者的 PDL 戳記，並且會在對應的地理位置佈建其 Exchange 群組信箱和 SharePoint O365 群組網站。 

## <a name="managing-the-multi-geo-environment"></a>管理多地理環境

您會透過 SharePoint 系統管理中心來設定和管理您的多地理環境。 

![SharePoint 系統管理中心中地理位置頁面的螢幕擷取畫面](../media/sharepoint-multi-geo-admin-center.png)

(部分動作，例如移動 SharePoint 網站或 OneDrive 網站，需要使用 Microsoft PowerShell。)

## <a name="see-also"></a>另請參閱

[SharePoint 和 Microsoft 365 群組中的多地理位置](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[管理多地理位置環境](administering-a-multi-geo-environment.md)

[多地理位置環境中的 SharePoint 儲存空間配額](sharepoint-multi-geo-storage-quota.md)

[管理多地理位置環境中的 Exchange Online 信箱](administering-exchange-online-multi-geo.md)
