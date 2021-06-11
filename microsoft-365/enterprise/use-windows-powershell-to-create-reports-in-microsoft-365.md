---
title: 使用 PowerShell 建立 Microsoft 365 報告
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 1ea4d4ec-af89-496f-9678-701867f5a6fc
description: 摘要：使用 PowerShell 進行 Microsoft 365，以建立您無法在 Microsoft 365 系統管理中心內產生的報告。
ms.openlocfilehash: 9e3b90dcdd32f80125175ad2e15a852db51e17f8
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572738"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="c8fd8-103">使用 PowerShell 建立 Microsoft 365 報告</span><span class="sxs-lookup"><span data-stu-id="c8fd8-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="c8fd8-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="c8fd8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c8fd8-105">Microsoft 365 系統管理中心提供許多不同的報告。</span><span class="sxs-lookup"><span data-stu-id="c8fd8-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c8fd8-106">不過，這些報告只會提供如此多的資訊，而且有時候您需要更多。</span><span class="sxs-lookup"><span data-stu-id="c8fd8-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="c8fd8-107">當您需要 Microsoft 365 PowerShell 時。</span><span class="sxs-lookup"><span data-stu-id="c8fd8-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="c8fd8-108">這些文章說明如何使用 Microsoft 365 的 PowerShell，以從 Microsoft 365 承租人取得資訊：</span><span class="sxs-lookup"><span data-stu-id="c8fd8-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="c8fd8-109">開始使用 Microsoft 365 PowerShell 的報告：</span><span class="sxs-lookup"><span data-stu-id="c8fd8-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="c8fd8-110">為什麼您需要使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8fd8-110">Why you need to use PowerShell for Microsoft 365</span></span>](./why-you-need-to-use-microsoft-365-powershell.md)
    
    
- <span data-ttu-id="c8fd8-111">使用者帳戶和授權的報告：</span><span class="sxs-lookup"><span data-stu-id="c8fd8-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="c8fd8-112">使用 PowerShell，查看 Microsoft 365 授權和服務</span><span class="sxs-lookup"><span data-stu-id="c8fd8-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="c8fd8-113">使用 PowerShell，查看 Microsoft 365 授權和未經許可的使用者</span><span class="sxs-lookup"><span data-stu-id="c8fd8-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="c8fd8-114">使用 PowerShell，查看 Microsoft 365 帳戶授權與服務詳細資料</span><span class="sxs-lookup"><span data-stu-id="c8fd8-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="c8fd8-115">使用 PowerShell View Microsoft 365 使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="c8fd8-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="c8fd8-116">SharePoint Online 的報告：</span><span class="sxs-lookup"><span data-stu-id="c8fd8-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="c8fd8-117">開始使用 SharePoint Online 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="c8fd8-117">Get started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="c8fd8-118">Get-SPOSiteGroup-取得指定網站集合上的所有群組</span><span class="sxs-lookup"><span data-stu-id="c8fd8-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](/powershell/module/sharepoint-online/get-spositegroup)
    
- <span data-ttu-id="c8fd8-119">Exchange Online 的報告：</span><span class="sxs-lookup"><span data-stu-id="c8fd8-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="c8fd8-120">使用 Exchange Online PowerShell 顯示信箱</span><span class="sxs-lookup"><span data-stu-id="c8fd8-120">Use Exchange Online PowerShell to display mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/use-powershell-to-display-mailbox-information)
    
    
## <a name="related-articles"></a><span data-ttu-id="c8fd8-121">相關文章</span><span class="sxs-lookup"><span data-stu-id="c8fd8-121">Related articles</span></span>

[<span data-ttu-id="c8fd8-122">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c8fd8-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c8fd8-123">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8fd8-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c8fd8-124">使用 PowerShell 管理 SharePoint</span><span class="sxs-lookup"><span data-stu-id="c8fd8-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c8fd8-125">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="c8fd8-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
