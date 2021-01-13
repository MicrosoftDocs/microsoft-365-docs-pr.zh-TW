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
description: 本文說明 Microsoft 365 核心 eDiscovery 案例中的限制。
ms.openlocfilehash: 43d267acdb0c1fee0202c74832b376e066241d7c
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799660"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="1e273-103">核心 eDiscovery 的限制</span><span class="sxs-lookup"><span data-stu-id="1e273-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="1e273-104">下表列出核心 ediscovery 案例相關聯之核心 eDiscovery 案例和保留專案的限制。</span><span class="sxs-lookup"><span data-stu-id="1e273-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="1e273-105">如需核心 eDiscovery 的詳細資訊，請參閱 [核心 Ediscovery 一覽](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="1e273-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](ediscovery-cases.md).</span></span>
    
  | <span data-ttu-id="1e273-106">限制的描述</span><span class="sxs-lookup"><span data-stu-id="1e273-106">Description of limit</span></span> | <span data-ttu-id="1e273-107">限制</span><span class="sxs-lookup"><span data-stu-id="1e273-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="1e273-108">組織的案例數目上限</span><span class="sxs-lookup"><span data-stu-id="1e273-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="1e273-109">無限制</span><span class="sxs-lookup"><span data-stu-id="1e273-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="1e273-110">組織的案例保留數目上限</span><span class="sxs-lookup"><span data-stu-id="1e273-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="1e273-111">10,000</span><span class="sxs-lookup"><span data-stu-id="1e273-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="1e273-112">單一案例保留中的信箱數目上限</span><span class="sxs-lookup"><span data-stu-id="1e273-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="1e273-113">1,000</span><span class="sxs-lookup"><span data-stu-id="1e273-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="1e273-114">單一案例保留中的商務網站 SharePoint 和 OneDrive 數目上限</span><span class="sxs-lookup"><span data-stu-id="1e273-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="1e273-115">100</span><span class="sxs-lookup"><span data-stu-id="1e273-115">100</span></span>  <br/> |
  |<span data-ttu-id="1e273-116">顯示在核心 eDiscovery 首頁上的案例數目上限，以及在案例中的 [保留]、[搜尋] 和 [匯出] 索引標籤上顯示的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="1e273-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="1e273-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1e273-117"><sup>1</sup></span></span> |<span data-ttu-id="1e273-118">1,000</span><span class="sxs-lookup"><span data-stu-id="1e273-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="1e273-119"><sup>1</sup> 若要查看超過1000案例、保留、搜尋或匯出的清單，您可以使用對應的 Office 365 安全性 & 合規性 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1e273-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="1e273-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="1e273-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="1e273-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="1e273-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="1e273-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="1e273-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="1e273-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="1e273-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="1e273-124">如需與核心 eDiscovery 案例相關聯之內容搜尋與匯出相關限制的相關資訊，請參閱 [內容搜尋和核心 ediscovery 的限制](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="1e273-124">For more information about limits related to content searches and exports associated with a Core eDiscovery case, see [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span></span>