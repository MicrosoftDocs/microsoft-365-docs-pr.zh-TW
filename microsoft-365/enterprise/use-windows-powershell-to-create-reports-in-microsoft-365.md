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
description: 摘要：使用 Microsoft 365 PowerShell 來建立您無法在 Microsoft 365 系統管理中心內產生的報告。
ms.openlocfilehash: 99aa86b1b58b15c63803e1b71d071cbde5c38492
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688580"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="96a77-103">使用 PowerShell 建立 Microsoft 365 報告</span><span class="sxs-lookup"><span data-stu-id="96a77-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="96a77-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="96a77-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="96a77-105">Microsoft 365 系統管理中心內有許多不同的報表可供使用。</span><span class="sxs-lookup"><span data-stu-id="96a77-105">There are many different reports available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="96a77-106">不過，這些報告只提供如此多的資訊，但有時候您需要更多。</span><span class="sxs-lookup"><span data-stu-id="96a77-106">However, these reports only provide so much information and sometimes you need more.</span></span> <span data-ttu-id="96a77-107">如果您需要 Microsoft 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="96a77-107">That's when you need PowerShell for Microsoft 365</span></span>
  
<span data-ttu-id="96a77-108">這些文章說明如何使用 Microsoft 365 的 PowerShell 來從您的 Microsoft 365 租使用者取得資訊：</span><span class="sxs-lookup"><span data-stu-id="96a77-108">These articles that describe how to use PowerShell for Microsoft 365 to obtain information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="96a77-109">使用 Microsoft 365 的 PowerShell 快速入門報告：</span><span class="sxs-lookup"><span data-stu-id="96a77-109">Getting started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="96a77-110">Microsoft 365 的 PowerShell 會顯示您在系統管理中心看不到的其他資訊</span><span class="sxs-lookup"><span data-stu-id="96a77-110">PowerShell for Microsoft 365 can reveal additional information that you cannot see with the Admin center</span></span>](https://technet.microsoft.com/library/dn568034.aspx#reveal)
    
  - [<span data-ttu-id="96a77-111">Microsoft 365 的 PowerShell 非常適合篩選資料</span><span class="sxs-lookup"><span data-stu-id="96a77-111">PowerShell for Microsoft 365 is great at filtering data</span></span>](https://technet.microsoft.com/library/dn568034.aspx#filter)
    
  - [<span data-ttu-id="96a77-112">Microsoft 365 的 PowerShell 可讓您輕鬆地列印或儲存資料</span><span class="sxs-lookup"><span data-stu-id="96a77-112">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>](https://technet.microsoft.com/library/dn568034.aspx#printsave)
    
- <span data-ttu-id="96a77-113">使用者帳戶和授權的報告：</span><span class="sxs-lookup"><span data-stu-id="96a77-113">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="96a77-114">使用 PowerShell 查看 Microsoft 365 授權和服務</span><span class="sxs-lookup"><span data-stu-id="96a77-114">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="96a77-115">使用 PowerShell 查看已授權和未經許可之使用者的 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="96a77-115">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="96a77-116">使用 PowerShell 來查看 Microsoft 365 帳戶授權與服務詳細資料</span><span class="sxs-lookup"><span data-stu-id="96a77-116">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="96a77-117">使用 PowerShell 來查看 Microsoft 365 使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="96a77-117">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="96a77-118">SharePoint Online 的報告：</span><span class="sxs-lookup"><span data-stu-id="96a77-118">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="96a77-119">開始使用 SharePoint Online 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="96a77-119">Get started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="96a77-120">使用 PowerShell 管理 SharePoint Online 網站群組</span><span class="sxs-lookup"><span data-stu-id="96a77-120">Manage SharePoint Online site groups with PowerShell</span></span>](https://technet.microsoft.com/library/122f4099-c78d-4cce-bab0-4343b04596ae.aspx)
    
- <span data-ttu-id="96a77-121">Exchange Online 的報告：</span><span class="sxs-lookup"><span data-stu-id="96a77-121">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="96a77-122">使用 PowerShell 顯示 Exchange Online 信箱資訊</span><span class="sxs-lookup"><span data-stu-id="96a77-122">Display Exchange Online mailbox information with PowerShell</span></span>](https://technet.microsoft.com/library/13843002-56ca-4b75-81c5-84386522b01b.aspx)
    
  - [<span data-ttu-id="96a77-123">使用 PowerShell 顯示 Exchange Online 報告</span><span class="sxs-lookup"><span data-stu-id="96a77-123">Display Exchange Online reports with PowerShell</span></span>](https://technet.microsoft.com/library/4873a063-9fc4-4ed9-826a-6e935fef61d4.aspx)
    
## <a name="related-topics"></a><span data-ttu-id="96a77-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="96a77-124">Related topics</span></span>

[<span data-ttu-id="96a77-125">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="96a77-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="96a77-126">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="96a77-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="96a77-127">使用 PowerShell 管理 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="96a77-127">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="96a77-128">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="96a77-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
