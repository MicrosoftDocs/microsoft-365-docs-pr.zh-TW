---
title: 在您的衛星地理位置啟用 SharePoint 多地理位置
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: 本文為全球或 SharePoint 系統管理員提供有關在衛星地理位置啟用 SharePoint 多地理位置的資訊。
ms.openlocfilehash: 78f0e925a333dd48a6016bc749459b13e1ac21c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688826"
---
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a>在您的衛星地理位置啟用 SharePoint 多地理位置

本文件的目標對象是於 2019 年 3 月 27 日 SharePoint 多重地理位置正式推出 **之前** 已建立多地理位置衛星位置的全域或 SharePoint 系統管理員，以及尚未在其衛星地理位置中啟用 SharePoint 多地理位置的使用者。 

>[!Note]
>如果您於 **3 月 27 日之後** 新增了新的地理位置，則不需要執行下列指示，因為您的新地理位置將已針對 OneDrive 和 SharePoint 多地理位置啟用。

這些指示可讓您在您的衛星位置啟用 SharePoint，使得多地理位置衛星使用者可以同時利用 O365 中的 OneDrive 與 SharePoint 多地理位置功能。 

>[!IMPORTANT]
>請注意，這是單向的啟用。 一旦您設定 SPO 模式，您無法在不向支援人員尋求協助的情況下，將租用戶還原為 OneDrive 僅限多地理位置模式。 

## <a name="to-set-a-geo-location-into-spo-mode"></a>將地理位置設定為 SPO 模式

若要將地理位置設定為 SPO 模式，請連線到您想要設定使用 SPO 模式的地理位置：

1.    開啟您的 SharePoint Online 管理命令介面 
2.    Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential
3.    Set-SPOMultiGeoExperience</br></br>
![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)
4.    在我們於服務中執行各種發佈工作並為您的租用戶重新加戳記時，此作業通常需要約一個小時的時間。 在至少 1 小時之後，請執行 Get-SPOMultiGeoExperience。  這將顯示此地理位置是否處於 SPO 模式。</br></br>
![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)

 
 
 
>[!Note]
>服務中的特定快取會每 24 小時更新，所以，可能有一段時間 (最多 24 小時)，您的衛星地理位置可能間歇性地以仍在 ODB 模式般運作。 此情況不會導致任何技術問題。 
 
如需有關 SharePoint 多地理位置的其他資訊，請參閱 [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)


