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
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a><span data-ttu-id="9ab6e-103">在您的衛星地理位置啟用 SharePoint 多地理位置</span><span class="sxs-lookup"><span data-stu-id="9ab6e-103">Enabling SharePoint Multi-Geo in your satellite geo location</span></span>

<span data-ttu-id="9ab6e-104">本文件的目標對象是於 2019 年 3 月 27 日 SharePoint 多重地理位置正式推出**之前**已建立多地理位置衛星位置的全域或 SharePoint 系統管理員，以及尚未在其衛星地理位置中啟用 SharePoint 多地理位置的使用者。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-104">This article is for Global or SharePoint administrators who have created a Multi-Geo satellite location **before** SharePoint Multi-Geo capabilities became generally available on March 27, 2019, and who have not enabled SharePoint Multi-Geo in their satellite geo location(s).</span></span> 

>[!Note]
><span data-ttu-id="9ab6e-105">如果您於 **3 月 27 日之後**新增了新的地理位置，則不需要執行下列指示，因為您的新地理位置將已針對 OneDrive 和 SharePoint 多地理位置啟用。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-105">If you have added a new geo location **after March 27th**, you do not need to perform these instructions, as your new geo location will already be enabled for OneDrive and SharePoint Multi-Geo.</span></span>

<span data-ttu-id="9ab6e-106">這些指示可讓您在您的衛星位置啟用 SharePoint，使得多地理位置衛星使用者可以同時利用 O365 中的 OneDrive 與 SharePoint 多地理位置功能。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-106">These instructions will allow you to enable SharePoint in your satellite location, so your Multi-Geo satellite users can take advantage of both OneDrive and SharePoint Multi-Geo capabilities in O365.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="9ab6e-107">請注意，這是單向的啟用。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-107">Please note that this is a one way enablement.</span></span> <span data-ttu-id="9ab6e-108">一旦您設定 SPO 模式，您無法在不向支援人員尋求協助的情況下，將租用戶還原為 OneDrive 僅限多地理位置模式。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-108">Once you set SPO mode, you will not be able to revert your tenant to OneDrive only Multi-Geo mode without an escalation with support.</span></span> 

## <a name="to-set-a-geo-location-into-spo-mode"></a><span data-ttu-id="9ab6e-109">將地理位置設定為 SPO 模式</span><span class="sxs-lookup"><span data-stu-id="9ab6e-109">To set a geo location into SPO Mode</span></span>

<span data-ttu-id="9ab6e-110">若要將地理位置設定為 SPO 模式，請連線到您想要設定使用 SPO 模式的地理位置：</span><span class="sxs-lookup"><span data-stu-id="9ab6e-110">To set a geo location into SPO mode, connect to the geo location you want to set in SPO Mode:</span></span>

1.    <span data-ttu-id="9ab6e-111">開啟您的 SharePoint Online 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="9ab6e-111">Open your SharePoint Online Management Shell</span></span> 
2.    <span data-ttu-id="9ab6e-112">Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential</span><span class="sxs-lookup"><span data-stu-id="9ab6e-112">Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential</span></span>
3.    <span data-ttu-id="9ab6e-113">Set-SPOMultiGeoExperience</span><span class="sxs-lookup"><span data-stu-id="9ab6e-113">Set-SPOMultiGeoExperience</span></span></br></br>
<span data-ttu-id="9ab6e-114">![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)</span><span class="sxs-lookup"><span data-stu-id="9ab6e-114">![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)</span></span>
4.    <span data-ttu-id="9ab6e-115">在我們於服務中執行各種發佈工作並為您的租用戶重新加戳記時，此作業通常需要約一個小時的時間。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-115">This operation usually takes about an hour while we perform various publish backs in the service and re-stamp your tenant.</span></span> <span data-ttu-id="9ab6e-116">在至少 1 小時之後，請執行 Get-SPOMultiGeoExperience。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-116">After at least 1 hour, please perform a Get-SPOMultiGeoExperience.</span></span>  <span data-ttu-id="9ab6e-117">這將顯示此地理位置是否處於 SPO 模式。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-117">This will show you whether this geo location is in SPO mode.</span></span></br></br>
<span data-ttu-id="9ab6e-118">![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)</span><span class="sxs-lookup"><span data-stu-id="9ab6e-118">![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)</span></span>

 
 
 
>[!Note]
><span data-ttu-id="9ab6e-119">服務中的特定快取會每 24 小時更新，所以，可能有一段時間 (最多 24 小時)，您的衛星地理位置可能間歇性地以仍在 ODB 模式般運作。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-119">Certain caches in the service update every 24 hours, so it is possible that for a period of up to 24 hours, your satellite geo may intermittently behave as if it was still in ODB mode.</span></span> <span data-ttu-id="9ab6e-120">此情況不會導致任何技術問題。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-120">This does not cause any technical issues.</span></span> 
 
<span data-ttu-id="9ab6e-121">如需有關 SharePoint 多地理位置的其他資訊，請參閱 [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="9ab6e-121">For additional information regarding SharePoint Multi-Geo, please refer to [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)</span></span>


