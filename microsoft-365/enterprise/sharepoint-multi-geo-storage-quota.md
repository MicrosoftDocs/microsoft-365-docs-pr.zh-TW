---
title: 多地理位置環境中的 SharePoint 儲存空間配額
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
description: 深入瞭解在多地理位置環境中 SharePoint 儲存配額，以及如何由 SharePoint Online 系統管理員來管理配額。
ms.openlocfilehash: ec736a6bd6061f8b028fca7a1c34d5278a84db89
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688876"
---
# <a name="sharepoint-storage-quotas-in-multi-geo-environments"></a><span data-ttu-id="861a2-103">多地理位置環境中的 SharePoint 儲存空間配額</span><span class="sxs-lookup"><span data-stu-id="861a2-103">SharePoint storage quotas in multi-geo environments</span></span>

<span data-ttu-id="861a2-104">根據預設，多重地理環境的所有地理位置會共用可用的租用戶儲存空間配額。</span><span class="sxs-lookup"><span data-stu-id="861a2-104">By default, all geo locations of a multi-geo environment share the available tenant storage quota.</span></span>

<span data-ttu-id="861a2-105">使用 SharePoint 地理位置儲存空間配額設定，您可以管理每個地理位置的儲存空間配額。</span><span class="sxs-lookup"><span data-stu-id="861a2-105">With the SharePoint geo storage quota setting, you can manage the storage quota for each geo location.</span></span> <span data-ttu-id="861a2-106">為地理位置分配儲存空間配額時，它將成為該地理位置可用的最大儲存空間量，並會從可用的租用戶儲存空間配額中扣除。</span><span class="sxs-lookup"><span data-stu-id="861a2-106">When you allocate a storage quota for a geo location, it becomes the maximum amount of storage available for that geo location, and is deducted from the available tenant storage quota.</span></span> <span data-ttu-id="861a2-107">然後，會在針對尚未分配的特定儲存空間配額的已設定地理位置之間共用剩餘的可用租用戶儲存空間配額。</span><span class="sxs-lookup"><span data-stu-id="861a2-107">The remaining available tenant storage quota is then shared across the configured geo locations for which a specific storage quota has not been allocated.</span></span>

<span data-ttu-id="861a2-108">SharePoint Online 系統管理員可連線至中央位置，以分配任何地理位置的 SharePoint 儲存空間配額。</span><span class="sxs-lookup"><span data-stu-id="861a2-108">The SharePoint storage quota for any geo location can be allocated by the SharePoint Online administrator by connecting to the central location.</span></span> <span data-ttu-id="861a2-109">衛星位置的地理位置系統管理員可以檢視儲存空間配額，但無法進行分配。</span><span class="sxs-lookup"><span data-stu-id="861a2-109">Geo administrators for satellite locations can view the storage quota but cannot allocate it.</span></span>

## <a name="configure-a-storage-quota-for-a-geo-location"></a><span data-ttu-id="861a2-110">為地理位置設定儲存空間配額</span><span class="sxs-lookup"><span data-stu-id="861a2-110">Configure a storage quota for a geo location</span></span>

<span data-ttu-id="861a2-111">使用 [Microsoft SharePoint Online 模組](https://www.microsoft.com/download/details.aspx?id=35588 )，並連線至中央位置，以分配地理位置的儲存空間配額。</span><span class="sxs-lookup"><span data-stu-id="861a2-111">Use the [Microsoft SharePoint Online Module](https://www.microsoft.com/download/details.aspx?id=35588 ) and connect to the central location to allocate the storage quota for a geo location.</span></span> 

<span data-ttu-id="861a2-112">若要分配某個位置的儲存空間配額，請執行 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="861a2-112">To allocate Storage Quota for a location, run cmdlet:</span></span>

`Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB <value>`

<span data-ttu-id="861a2-113">若要檢視目前地理位置的儲存空間配額，請執行：</span><span class="sxs-lookup"><span data-stu-id="861a2-113">To view Storage Quota for the current geo location, run:</span></span>

`Get-SPOGeoStorageQuota`

![PowerShell 視窗的螢幕擷取畫面，顯示 Get-SPOGeoStorageQuota cmdlet](../media/multi-geo-storage-quota.png)

<span data-ttu-id="861a2-115">若要檢視所有地理位置的儲存空間配額，請執行：</span><span class="sxs-lookup"><span data-stu-id="861a2-115">To view Storage Quota for all geo locations, run:</span></span>

`Get-SPOGeoStorageQuota -AllLocations`

<span data-ttu-id="861a2-116">若要移除地理位置已分配的儲存空間配額，設定 `StorageQuota value = 0`：</span><span class="sxs-lookup"><span data-stu-id="861a2-116">To remove the allocated storage quota for a geo location, set `StorageQuota value = 0`:</span></span>

`Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB 0`
