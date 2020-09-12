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
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a><span data-ttu-id="e910a-103">使用特定的 PDL 建立 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="e910a-103">Create a Microsoft 365 Group with a specific PDL</span></span>

<span data-ttu-id="e910a-104">在多地理位置環境中的使用者建立 Microsoft 365 群組時，群組慣用資料位置會自動設定為使用者的使用者。</span><span class="sxs-lookup"><span data-stu-id="e910a-104">When users in a multi-geo environment create a Microsoft 365 Group, the group preferred data location is automatically set to that of the user.</span></span> <span data-ttu-id="e910a-105">全域、SharePoint 和 Exchange 系統管理員可以在他們所選的任何區域中建立群組。</span><span class="sxs-lookup"><span data-stu-id="e910a-105">Global, SharePoint, and Exchange Administrators can create groups in any region they select.</span></span> 

<span data-ttu-id="e910a-106">如果需要建立具有特定 PDL 的群組，則可以使用 SharePoint 系統管理中心或透過 Exchange Online New-UnifiedGroup Microsoft PowerShell Cmdlet 來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="e910a-106">If you need to create a group with a specific PDL, you can do that using from the SharePoint admin center or through the Exchange Online New-UnifiedGroup Microsoft PowerShell cmdlet.</span></span> <span data-ttu-id="e910a-107">如此一來，將在指定的 PDL 中佈建與該群組關聯的群組信箱和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="e910a-107">When you do this, both the group mailbox and SharePoint site associated with the group will be provisioned in the specified PDL.</span></span>

<span data-ttu-id="e910a-108">若要使用您指定的 PDL 建立 Microsoft 365 群組，請移至您要建立群組網站之地理位置的 SharePoint 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="e910a-108">To create a Microsoft 365 Group with the PDL that you specify, go to the SharePoint admin center in the geo location where you want to create the group site.</span></span>

<span data-ttu-id="e910a-109">例如：</span><span class="sxs-lookup"><span data-stu-id="e910a-109">For example:</span></span>

<span data-ttu-id="e910a-110">如果您要在澳洲位置建立群組網站，您可以移至 https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span><span class="sxs-lookup"><span data-stu-id="e910a-110">If you want to create a group site in your Australia location, you can go to https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span></span>

1. <span data-ttu-id="e910a-111">選取 [+ 建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e910a-111">Select **+ Create**.</span></span>
2. <span data-ttu-id="e910a-112">遵循程序來建立群組網站。</span><span class="sxs-lookup"><span data-stu-id="e910a-112">Follow the process to create a group site.</span></span>

<span data-ttu-id="e910a-113">您的群組網站將在與您從中啟動網站建立要求的 SharePoint 系統管理中心對應的地理位置中佈建。</span><span class="sxs-lookup"><span data-stu-id="e910a-113">Your group site will be provisioned in the geo location corresponding to the SharePoint admin center from which you initiated the site creation request.</span></span> 

<span data-ttu-id="e910a-114">使用 Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="e910a-114">Using Exchange PowerShell</span></span> 

<span data-ttu-id="e910a-115">連線至 Exchange Online PowerShell，並傳遞參數 *-MailBoxRegion* 與地理位置代碼。</span><span class="sxs-lookup"><span data-stu-id="e910a-115">Connect to Exchange Online PowerShell and pass the parameter *-MailBoxRegion* with the geo location code.</span></span>

<span data-ttu-id="e910a-116">例如：</span><span class="sxs-lookup"><span data-stu-id="e910a-116">For example:</span></span> 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![New-UnifiedGroup PowerShell cmdlet 以及語法的螢幕擷取畫面](../media/multi-geo-new-group-with-pdl-powershell.png)

<span data-ttu-id="e910a-118">請注意，SharePoint 群組網站佈建將依照需求。</span><span class="sxs-lookup"><span data-stu-id="e910a-118">Note that SharePoint group site provisioning is on-demand.</span></span> <span data-ttu-id="e910a-119">在群組擁有者或成員首次嘗試存取網站時，會對該網站進行佈建。</span><span class="sxs-lookup"><span data-stu-id="e910a-119">The site will be provisioned the first time a group owner or member attempts to access it.</span></span>

## <a name="geo-location-codes"></a><span data-ttu-id="e910a-120">地理位置代碼</span><span class="sxs-lookup"><span data-stu-id="e910a-120">Geo location codes</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a><span data-ttu-id="e910a-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="e910a-121">Related topics</span></span>

[<span data-ttu-id="e910a-122">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e910a-122">Connect to Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)
