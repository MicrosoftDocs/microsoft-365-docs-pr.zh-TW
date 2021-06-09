---
title: 將 SharePoint 網站內容限制在地理位置
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
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: 在本文中，您將瞭解如何將 SharePoint 網站限制在多地理位置環境中的指定地理位置。
ms.openlocfilehash: 74255db19b2ecf9b333d33208c63da260b2bd747
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927261"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a><span data-ttu-id="59287-103">將 SharePoint 網站內容限制在地理位置</span><span class="sxs-lookup"><span data-stu-id="59287-103">Restrict SharePoint site content to a geo location</span></span>

<span data-ttu-id="59287-104">在某些情況下，您可以選擇強制將網站及其檔案內容保留在建立網站的地理位置，方法是防止網站移動或防止在另一個地理位置快取網站的檔案內容。</span><span class="sxs-lookup"><span data-stu-id="59287-104">Under some circumstances you may choose to enforce a site and its file content to remain in the geo location where the site was created, either by preventing the site from being moved or by preventing the caching of the site's file content in another geo location.</span></span>

<span data-ttu-id="59287-105">您使用 [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) cmdlet 搭配 **RestrictedToGeo** 參數來進行。</span><span class="sxs-lookup"><span data-stu-id="59287-105">You can do this by using the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) cmdlet with the **RestrictedToGeo** parameter.</span></span> <span data-ttu-id="59287-106">此參數預設值為 NULL，但您可以將它變更為下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="59287-106">This parameter has a default value of NULL, but you can change it to one of the following:</span></span>

|<span data-ttu-id="59287-107">Restriction</span><span class="sxs-lookup"><span data-stu-id="59287-107">Restriction</span></span>|<span data-ttu-id="59287-108">描述</span><span class="sxs-lookup"><span data-stu-id="59287-108">Description</span></span>|
|:----------|:----------|
|<span data-ttu-id="59287-109">NoRestriction</span><span class="sxs-lookup"><span data-stu-id="59287-109">NoRestriction</span></span>|<span data-ttu-id="59287-110">可將網站移至另一個地理位置。</span><span class="sxs-lookup"><span data-stu-id="59287-110">The site can be moved to another geo location.</span></span>|
|<span data-ttu-id="59287-111">BlockMoveOnly</span><span class="sxs-lookup"><span data-stu-id="59287-111">BlockMoveOnly</span></span>|<span data-ttu-id="59287-112">無法將網站移到另一個地理位置，但可以在其他地理位置快取網站內容。</span><span class="sxs-lookup"><span data-stu-id="59287-112">Site cannot be moved to another geo location, but site content can be cached in other geo locations.</span></span>|
|<span data-ttu-id="59287-113">BlockFull</span><span class="sxs-lookup"><span data-stu-id="59287-113">BlockFull</span></span>|<span data-ttu-id="59287-114">無法將網站移到另一個地理位置，也不可以在其他地理位置快取完整檔案內容。</span><span class="sxs-lookup"><span data-stu-id="59287-114">Site cannot be moved to another geo location, and full file content is not cached in other geo locations.</span></span> <span data-ttu-id="59287-115">仍可以在其他地理位置快取檔案的標題 (取自內容)、檔案名稱和檔案的其他內容。</span><span class="sxs-lookup"><span data-stu-id="59287-115">Files' title (harvested from the content), file name, and other properties of the file can still be cached in other geo-locations.</span></span><br><span data-ttu-id="59287-116">在設定為 BlockFull 之前儲存在網站中的內容可能會繼續在其他地理位置快取。</span><span class="sxs-lookup"><span data-stu-id="59287-116">Content stored in the site before it was configured to BlockFull, may continue to be cached in other geo locations.</span></span>|

<span data-ttu-id="59287-117">使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="59287-117">Use the following syntax:</span></span>

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

<span data-ttu-id="59287-118">例如：</span><span class="sxs-lookup"><span data-stu-id="59287-118">For example:</span></span>

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`