---
title: 關閉或刪除案例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 瞭解當 eDiscovery 案例所支援的調查或法律案例已關閉或刪除時，會發生什麼事。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f91755e6d2aeba89e795a623cd1268af0a53e675
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035635"
---
# <a name="close-or-delete-a-case"></a><span data-ttu-id="777b5-103">關閉或刪除案例</span><span class="sxs-lookup"><span data-stu-id="777b5-103">Close or delete a case</span></span>

<span data-ttu-id="777b5-104">當 eDiscovery 案例支援的法律案例或調查完成時，您可以關閉案例。</span><span class="sxs-lookup"><span data-stu-id="777b5-104">When the legal case or investigation supported by an eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="777b5-105">以下是關閉案例時會發生的情況：</span><span class="sxs-lookup"><span data-stu-id="777b5-105">Here's what happens when you close a case:</span></span>

- <span data-ttu-id="777b5-106">如果案例包含保留的任何內容位置，將會關閉那些保留。</span><span class="sxs-lookup"><span data-stu-id="777b5-106">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="777b5-107">這可能會導致內容被使用者或自動化程式（如刪除原則）永久刪除或清除。</span><span class="sxs-lookup"><span data-stu-id="777b5-107">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="777b5-108">關閉案例只會關閉與該案例相關聯的保留。</span><span class="sxs-lookup"><span data-stu-id="777b5-108">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="777b5-109">在內容位置（例如訴訟暫止）上放置其他保留。</span><span class="sxs-lookup"><span data-stu-id="777b5-109">If other holds are place on a content location (such as a Litigation Hold.</span></span> <span data-ttu-id="777b5-110">保留原則，或不同 eDiscovery 案例中的保留原則）仍會保留這些保留。</span><span class="sxs-lookup"><span data-stu-id="777b5-110">a Preservation Policy, or a hold from a different eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="777b5-111">此案例仍會列在安全性 & 合規性中心的 eDiscovery 頁面上。</span><span class="sxs-lookup"><span data-stu-id="777b5-111">The case is still listed on the eDiscovery page in the Security & Compliance Center.</span></span> <span data-ttu-id="777b5-112">已關閉案例的詳細資料、保留、搜尋及成員都會保留。</span><span class="sxs-lookup"><span data-stu-id="777b5-112">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="777b5-113">您可以在關閉案例後進行編輯。</span><span class="sxs-lookup"><span data-stu-id="777b5-113">You can edit a case after it's closed.</span></span> <span data-ttu-id="777b5-114">例如，您可以在高級 eDiscovery 中新增或移除成員、建立搜尋、匯出搜尋結果，以及準備用於分析的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="777b5-114">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="777b5-115">使用中案例和關閉案例之間的主要差異是關閉案例時關閉保留狀態。</span><span class="sxs-lookup"><span data-stu-id="777b5-115">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="777b5-116">若要關閉案例：</span><span class="sxs-lookup"><span data-stu-id="777b5-116">To close a case:</span></span>

1. <span data-ttu-id="777b5-117">在 [**高級電子**檔探索] 頁面上，選取您要關閉的案例。</span><span class="sxs-lookup"><span data-stu-id="777b5-117">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="777b5-118">在 [**設定**] 索引標籤的 [**案例資訊**] 下，按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="777b5-118">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="777b5-119">按一下 [**關閉案例**]。</span><span class="sxs-lookup"><span data-stu-id="777b5-119">Click **Close case**.</span></span>

<span data-ttu-id="777b5-120">若要刪除案例：</span><span class="sxs-lookup"><span data-stu-id="777b5-120">To delete a case:</span></span>

1. <span data-ttu-id="777b5-121">在 [**高級電子**檔探索] 頁面上，選取您要刪除的案例。</span><span class="sxs-lookup"><span data-stu-id="777b5-121">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="777b5-122">在 [**設定**] 索引標籤的 [**案例資訊**] 下，按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="777b5-122">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="777b5-123">按一下 [**刪除案例**]。</span><span class="sxs-lookup"><span data-stu-id="777b5-123">Click **Delete case**.</span></span> 
