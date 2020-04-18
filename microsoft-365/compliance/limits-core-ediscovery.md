---
title: 核心 eDiscovery 案例中的限制
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
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
ms.openlocfilehash: 4d91b81caee31e693ce29c6d8d629d563d973ae7
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551399"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="49820-103">核心 eDiscovery 的限制</span><span class="sxs-lookup"><span data-stu-id="49820-103">Limits in core eDiscovery</span></span>

<span data-ttu-id="49820-104">下表列出核心 ediscovery 案例相關聯之核心 eDiscovery 案例和保留專案的限制。</span><span class="sxs-lookup"><span data-stu-id="49820-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="49820-105">如需核心 eDiscovery 的詳細資訊，請參閱[核心 Ediscovery 一覽](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="49820-105">For more information about core eDiscovery, see [Overview of core eDiscovery](ediscovery-cases.md).</span></span>
    
  |<span data-ttu-id="49820-106">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="49820-106">**Description of limit**</span></span>|<span data-ttu-id="49820-107">**限制**</span><span class="sxs-lookup"><span data-stu-id="49820-107">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="49820-108">組織的案例數目上限</span><span class="sxs-lookup"><span data-stu-id="49820-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="49820-109">無限制</span><span class="sxs-lookup"><span data-stu-id="49820-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="49820-110">組織的案例保留數目上限</span><span class="sxs-lookup"><span data-stu-id="49820-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="49820-111">10,000</span><span class="sxs-lookup"><span data-stu-id="49820-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="49820-112">單一案例保留中的信箱數目上限</span><span class="sxs-lookup"><span data-stu-id="49820-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="49820-113">1,000</span><span class="sxs-lookup"><span data-stu-id="49820-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="49820-114">單一案例保留中的商務網站 SharePoint 和 OneDrive 數目上限</span><span class="sxs-lookup"><span data-stu-id="49820-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="49820-115">100</span><span class="sxs-lookup"><span data-stu-id="49820-115">100</span></span>  <br/> |
  |<span data-ttu-id="49820-116">顯示在核心 eDiscovery 首頁上的案例數目上限，以及在案例中的 [保留]、[搜尋] 和 [匯出] 索引標籤上顯示的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="49820-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="49820-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="49820-117"><sup>1</sup></span></span> |<span data-ttu-id="49820-118">1,000</span><span class="sxs-lookup"><span data-stu-id="49820-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="49820-119"><sup>1</sup>若要查看超過1000案例、保留、搜尋或匯出的清單，您可以使用對應的 Office 365 安全性 & 合規性 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="49820-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlet:</span></span><br/> [<span data-ttu-id="49820-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="49820-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase) <br/> [<span data-ttu-id="49820-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="49820-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)<br/> [<span data-ttu-id="49820-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="49820-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch)<br/> [<span data-ttu-id="49820-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="49820-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)
