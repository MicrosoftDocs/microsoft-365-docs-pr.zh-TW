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
ms.openlocfilehash: 00df8cff683701ce5ee38dca12b6f7af5b31c8b0
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351894"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="3049e-103">核心 eDiscovery 的限制</span><span class="sxs-lookup"><span data-stu-id="3049e-103">Limits in core eDiscovery</span></span>

<span data-ttu-id="3049e-104">下表列出核心 ediscovery 案例相關聯之核心 eDiscovery 案例和保留專案的限制。</span><span class="sxs-lookup"><span data-stu-id="3049e-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="3049e-105">如需核心 eDiscovery 的詳細資訊，請參閱[核心 Ediscovery 一覽](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="3049e-105">For more information about core eDiscovery, see [Overview of core eDiscovery](ediscovery-cases.md).</span></span>
    
  |<span data-ttu-id="3049e-106">**限制的描述**</span><span class="sxs-lookup"><span data-stu-id="3049e-106">**Description of limit**</span></span>|<span data-ttu-id="3049e-107">**限制**</span><span class="sxs-lookup"><span data-stu-id="3049e-107">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="3049e-108">組織的案例數目上限</span><span class="sxs-lookup"><span data-stu-id="3049e-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="3049e-109">無限制</span><span class="sxs-lookup"><span data-stu-id="3049e-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="3049e-110">組織的案例保留數目上限</span><span class="sxs-lookup"><span data-stu-id="3049e-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="3049e-111">10,000</span><span class="sxs-lookup"><span data-stu-id="3049e-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="3049e-112">單一案例保留中的信箱數目上限</span><span class="sxs-lookup"><span data-stu-id="3049e-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="3049e-113">1,000</span><span class="sxs-lookup"><span data-stu-id="3049e-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="3049e-114">單一案例保留中的商務網站 SharePoint 和 OneDrive 數目上限</span><span class="sxs-lookup"><span data-stu-id="3049e-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="3049e-115">100</span><span class="sxs-lookup"><span data-stu-id="3049e-115">100</span></span>  <br/> |
  |<span data-ttu-id="3049e-116">顯示在核心 eDiscovery 首頁上的案例數目上限，以及在案例中的 [保留]、[搜尋] 和 [匯出] 索引標籤上顯示的專案數上限。</span><span class="sxs-lookup"><span data-stu-id="3049e-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="3049e-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3049e-117"><sup>1</sup></span></span> |<span data-ttu-id="3049e-118">1,000</span><span class="sxs-lookup"><span data-stu-id="3049e-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="3049e-119"><sup>1</sup>若要查看超過1000案例、保留、搜尋或匯出的清單，您可以使用對應的 Office 365 安全性 & 合規性 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3049e-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlet:</span></span><br/> [<span data-ttu-id="3049e-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="3049e-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) <br/> [<span data-ttu-id="3049e-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="3049e-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)<br/> [<span data-ttu-id="3049e-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="3049e-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)<br/> [<span data-ttu-id="3049e-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="3049e-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
