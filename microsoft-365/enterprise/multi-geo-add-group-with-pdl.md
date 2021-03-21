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
ms.openlocfilehash: 7f02a5eb6d8b30e8381c65d4735812675d35af2b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923741"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a><span data-ttu-id="be752-103">使用特定的 PDL 建立 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="be752-103">Create a Microsoft 365 Group with a specific PDL</span></span>

<span data-ttu-id="be752-104">在多地理位置環境中的使用者建立 Microsoft 365 群組時，群組慣用資料位置會自動設定為使用者的使用者。</span><span class="sxs-lookup"><span data-stu-id="be752-104">When users in a multi-geo environment create a Microsoft 365 Group, the group preferred data location is automatically set to that of the user.</span></span> <span data-ttu-id="be752-105">全域、SharePoint 和 Exchange 系統管理員可以在他們所選的任何區域中建立群組。</span><span class="sxs-lookup"><span data-stu-id="be752-105">Global, SharePoint, and Exchange Administrators can create groups in any region they select.</span></span> 

<span data-ttu-id="be752-106">如果需要建立具有特定 PDL 的群組，則可以使用 SharePoint 系統管理中心或透過 Exchange Online New-UnifiedGroup Microsoft PowerShell Cmdlet 來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="be752-106">If you need to create a group with a specific PDL, you can do that using from the SharePoint admin center or through the Exchange Online New-UnifiedGroup Microsoft PowerShell cmdlet.</span></span> <span data-ttu-id="be752-107">如此一來，將在指定的 PDL 中佈建與該群組關聯的群組信箱和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="be752-107">When you do this, both the group mailbox and SharePoint site associated with the group will be provisioned in the specified PDL.</span></span>

<span data-ttu-id="be752-108">若要使用您指定的 PDL 建立 Microsoft 365 群組，請移至您要建立群組網站之地理位置的 SharePoint 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="be752-108">To create a Microsoft 365 Group with the PDL that you specify, go to the SharePoint admin center in the geo location where you want to create the group site.</span></span>

<span data-ttu-id="be752-109">例如：</span><span class="sxs-lookup"><span data-stu-id="be752-109">For example:</span></span>

<span data-ttu-id="be752-110">如果您要在澳洲位置建立群組網站，您可以移至 https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span><span class="sxs-lookup"><span data-stu-id="be752-110">If you want to create a group site in your Australia location, you can go to https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span></span>

1. <span data-ttu-id="be752-111">選取 [+ 建立]。</span><span class="sxs-lookup"><span data-stu-id="be752-111">Select **+ Create**.</span></span>
2. <span data-ttu-id="be752-112">遵循程序來建立群組網站。</span><span class="sxs-lookup"><span data-stu-id="be752-112">Follow the process to create a group site.</span></span>

<span data-ttu-id="be752-113">您的群組網站將在與您從中啟動網站建立要求的 SharePoint 系統管理中心對應的地理位置中佈建。</span><span class="sxs-lookup"><span data-stu-id="be752-113">Your group site will be provisioned in the geo location corresponding to the SharePoint admin center from which you initiated the site creation request.</span></span> 

<span data-ttu-id="be752-114">使用 Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="be752-114">Using Exchange PowerShell</span></span> 

<span data-ttu-id="be752-115">連線至 Exchange Online PowerShell，並傳遞參數 *-MailBoxRegion* 與地理位置代碼。</span><span class="sxs-lookup"><span data-stu-id="be752-115">Connect to Exchange Online PowerShell and pass the parameter *-MailBoxRegion* with the geo location code.</span></span>

<span data-ttu-id="be752-116">例如：</span><span class="sxs-lookup"><span data-stu-id="be752-116">For example:</span></span> 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![New-UnifiedGroup PowerShell cmdlet 以及語法的螢幕擷取畫面](../media/multi-geo-new-group-with-pdl-powershell.png)

<span data-ttu-id="be752-118">請注意，SharePoint 群組網站佈建將依照需求。</span><span class="sxs-lookup"><span data-stu-id="be752-118">Note that SharePoint group site provisioning is on-demand.</span></span> <span data-ttu-id="be752-119">在群組擁有者或成員首次嘗試存取網站時，會對該網站進行佈建。</span><span class="sxs-lookup"><span data-stu-id="be752-119">The site will be provisioned the first time a group owner or member attempts to access it.</span></span>

## <a name="geo-location-codes"></a><span data-ttu-id="be752-120">地理位置代碼</span><span class="sxs-lookup"><span data-stu-id="be752-120">Geo location codes</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a><span data-ttu-id="be752-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="be752-121">Related topics</span></span>

[<span data-ttu-id="be752-122">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="be752-122">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)