---
title: 核心 eDiscovery 案例中的限制
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文說明核心 eDiscovery 案例中 Microsoft 365 的限制。
ms.openlocfilehash: e7b1013abd9fd94748baf3b83dd04efbc3831a1d
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311421"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="bffae-103">核心 eDiscovery 的限制</span><span class="sxs-lookup"><span data-stu-id="bffae-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="bffae-104">下表列出核心 ediscovery 案例相關聯之核心 eDiscovery 案例和保留專案的限制。</span><span class="sxs-lookup"><span data-stu-id="bffae-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="bffae-105">如需核心 eDiscovery 的詳細資訊，請參閱 [核心 Ediscovery 一覽](./get-started-core-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="bffae-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](./get-started-core-ediscovery.md).</span></span>
    
  | <span data-ttu-id="bffae-106">限制的描述</span><span class="sxs-lookup"><span data-stu-id="bffae-106">Description of limit</span></span> | <span data-ttu-id="bffae-107">限制</span><span class="sxs-lookup"><span data-stu-id="bffae-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="bffae-108">組織的案例數目上限。</span><span class="sxs-lookup"><span data-stu-id="bffae-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="bffae-109">無限制</span><span class="sxs-lookup"><span data-stu-id="bffae-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="bffae-110">組織的案例保留數目上限。</span><span class="sxs-lookup"><span data-stu-id="bffae-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="bffae-111">10,000</span><span class="sxs-lookup"><span data-stu-id="bffae-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="bffae-112">單一案例保留中的信箱數目上限。</span><span class="sxs-lookup"><span data-stu-id="bffae-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="bffae-113">此限制包括使用者信箱的組合總數，以及與 Microsoft 365 群組、Microsoft Teams 及 Yammer 群組相關聯的信箱。</span><span class="sxs-lookup"><span data-stu-id="bffae-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="bffae-114">1,000</span><span class="sxs-lookup"><span data-stu-id="bffae-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="bffae-115">單一案例保留中的網站數目上限。</span><span class="sxs-lookup"><span data-stu-id="bffae-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="bffae-116">此限制包括與 Microsoft 365 群組、Microsoft Teams 及 Yammer 群組相關聯的商務用 OneDrive 網站、SharePoint 網站和網站的綜合總數。</span><span class="sxs-lookup"><span data-stu-id="bffae-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="bffae-117">100</span><span class="sxs-lookup"><span data-stu-id="bffae-117">100</span></span>  <br/> |
  |<span data-ttu-id="bffae-118">顯示在核心 eDiscovery 首頁上的案例數目上限，以及在案例中的 [保留]、[搜尋] 和 [匯出] 索引標籤上顯示的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="bffae-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="bffae-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bffae-119"><sup>1</sup></span></span> |<span data-ttu-id="bffae-120">1,000</span><span class="sxs-lookup"><span data-stu-id="bffae-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="bffae-121"><sup>1</sup>若要查看超過1000案例、保留、搜尋或匯出的清單，您可以使用對應的 Office 365 安全性 & 相容性 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="bffae-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="bffae-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="bffae-122">Get-ComplianceCase</span></span>](/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="bffae-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="bffae-123">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="bffae-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="bffae-124">Get-ComplianceSearch</span></span>](/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="bffae-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="bffae-125">Get-ComplianceSearchAction</span></span>](/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="bffae-126">如需與核心 eDiscovery 案例相關聯之搜尋和匯出相關限制的相關資訊，請參閱 [內容搜尋和核心 ediscovery 的限制](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="bffae-126">For more information about limits related to searches and exports associated with a Core eDiscovery case, see [Limits for Content search and Core eDiscovery](limits-for-content-search.md).</span></span>