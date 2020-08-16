---
title: 調整 Exchange Online 效能
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: 本文包含的一般秘訣，以及其他資源的連結，可告訴您如何改善 Exchange Online 的效能。
ms.openlocfilehash: 495b662aa6ef247a5751febbf2d50e1c1f21a44e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688695"
---
# <a name="tune-exchange-online-performance"></a><span data-ttu-id="e8ebf-103">調整 Exchange Online 效能</span><span class="sxs-lookup"><span data-stu-id="e8ebf-103">Tune Exchange Online performance</span></span>

<span data-ttu-id="e8ebf-104">本文包含其他資源的一般秘訣和連結，可告訴您如何改善 Exchange Online 的效能，尤其是在遷移之前。</span><span class="sxs-lookup"><span data-stu-id="e8ebf-104">This article contains general tips and links to other resources that tell you how to improve performance of Exchange Online, particularly in front of a migration.</span></span> <span data-ttu-id="e8ebf-105">本文是 Office 365 專案的 [網路規劃和效能調整](https://aka.ms/tune) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="e8ebf-105">This article is part of the [Network planning and performance tuning for Office 365](https://aka.ms/tune) project.</span></span>
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a><span data-ttu-id="e8ebf-106">為了改善 Exchange Online 效能應考慮的事項</span><span class="sxs-lookup"><span data-stu-id="e8ebf-106">Things to consider in order to improve Exchange Online performance</span></span>

<span data-ttu-id="e8ebf-107">若要改善遷移速度並減少組織的 Exchange Online 頻寬限制，請考慮下列各項：</span><span class="sxs-lookup"><span data-stu-id="e8ebf-107">To improve the speed of migration and reduce your organization's bandwidth constraints for Exchange Online, consider the following:</span></span>
  
- <span data-ttu-id="e8ebf-108">**縮小信箱大小。**</span><span class="sxs-lookup"><span data-stu-id="e8ebf-108">**Reduce mailbox sizes.**</span></span> <span data-ttu-id="e8ebf-109">信箱大小較小會提升遷移速度。</span><span class="sxs-lookup"><span data-stu-id="e8ebf-109">Smaller mailbox size improves migration speed.</span></span> 
    
- <span data-ttu-id="e8ebf-110">**在 Exchange 混合式部署中使用信箱移動功能。**</span><span class="sxs-lookup"><span data-stu-id="e8ebf-110">**Use the mailbox move capabilities with an Exchange hybrid deployment.**</span></span> <span data-ttu-id="e8ebf-111">使用 Exchange 混合式部署時，離線郵件 (格式為。在遷移至 Exchange Online 時，不需要重新下載 .OST 檔案) 。</span><span class="sxs-lookup"><span data-stu-id="e8ebf-111">With an Exchange hybrid deployment, offline mail (in the form of .OST files) does not require re-download when migrating to Exchange Online.</span></span> <span data-ttu-id="e8ebf-112">這會大幅減少下載頻寬需求。</span><span class="sxs-lookup"><span data-stu-id="e8ebf-112">This significantly reduces your download bandwidth requirements.</span></span> 
    
- <span data-ttu-id="e8ebf-113">**在網際網路流量低和內部部署 Exchange 使用的情況下，排定信箱移動的時間。**</span><span class="sxs-lookup"><span data-stu-id="e8ebf-113">**Schedule mailbox moves to occur during periods of low Internet traffic and low on-premises Exchange use.**</span></span> <span data-ttu-id="e8ebf-114">當排程移動時，會將遷移要求提交至信箱複寫 proxy，而且不會立即進行。</span><span class="sxs-lookup"><span data-stu-id="e8ebf-114">When scheduling moves, migration requests are submitted to the mailbox replication proxy and may not take place immediately.</span></span> 
    
- <span data-ttu-id="e8ebf-115">**使用適用于網頁版 Outlook 的精益快顯。**</span><span class="sxs-lookup"><span data-stu-id="e8ebf-115">**Use lean popouts for Outlook on the web.**</span></span> <span data-ttu-id="e8ebf-116">精益快顯透過轉譯伺服器上的某些元件，在 Microsoft Edge 或 Internet Explorer 中提供較小、佔用大量記憶體的特定電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e8ebf-116">Lean popouts provide smaller, less memory-intensive versions of certain email messages in Microsoft Edge or Internet Explorer by rendering some components on the server.</span></span> <span data-ttu-id="e8ebf-117">如需詳細資訊，請參閱 [使用精益快顯減少讀取郵件訊息時使用的記憶體](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)。</span><span class="sxs-lookup"><span data-stu-id="e8ebf-117">For more information, see [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span></span>


## <a name="general-advice"></a><span data-ttu-id="e8ebf-118">一般建議</span><span class="sxs-lookup"><span data-stu-id="e8ebf-118">General advice</span></span>

- <span data-ttu-id="e8ebf-119">請確定 outlook.office.com 的 DNS 查閱會在您的位置的邏輯專案位置輸入 MS 資料中心。</span><span class="sxs-lookup"><span data-stu-id="e8ebf-119">Make certain that DNS lookup for outlook.office.com enters the MS-datacenter at a logical entry location for your location.</span></span>

- <span data-ttu-id="e8ebf-120">調研信箱快取，並選擇適當的選項 (re。</span><span class="sxs-lookup"><span data-stu-id="e8ebf-120">Research mailbox caching and choose the appropriate options (re.</span></span> <span data-ttu-id="e8ebf-121">快取週期、共用信箱快取等) 。</span><span class="sxs-lookup"><span data-stu-id="e8ebf-121">caching period, shared mailbox caching, et cetera).</span></span>

- <span data-ttu-id="e8ebf-122">讓您的 Outlook 資料在透過網際網路之前，可將 VPN 連線 (傳送到總公司) 。</span><span class="sxs-lookup"><span data-stu-id="e8ebf-122">Keep your Outlook data from passing over VPN connections (to a central office) before it goes over the Internet.</span></span>

- <span data-ttu-id="e8ebf-123">請確定您的信箱資料符合資料夾的限制，以及專案的數量。</span><span class="sxs-lookup"><span data-stu-id="e8ebf-123">Be sure your mailbox data adheres to the limitations on folder, and item, amounts.</span></span>
    
<span data-ttu-id="e8ebf-124">如需 Exchange 遷移效能的詳細資訊，請參閱 [Office 365 遷移效能和最佳作法](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)。</span><span class="sxs-lookup"><span data-stu-id="e8ebf-124">For more information about Exchange migration performance, see [Office 365 migration performance and best practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span></span>
  
