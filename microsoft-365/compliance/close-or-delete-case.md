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
description: " "
ms.openlocfilehash: 15b6327809b3557c4d0d90b6c10dc5568ba47f43
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595870"
---
# <a name="close-or-delete-a-case"></a><span data-ttu-id="ca104-102">關閉或刪除案例</span><span class="sxs-lookup"><span data-stu-id="ca104-102">Close or delete a case</span></span>

<span data-ttu-id="ca104-103">法律案件或調查的 eDiscovery 案例所支援完成時，您可以關閉案例。</span><span class="sxs-lookup"><span data-stu-id="ca104-103">When the legal case or investigation supported by an eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="ca104-104">以下是當您關閉案例時，會發生什麼事：</span><span class="sxs-lookup"><span data-stu-id="ca104-104">Here's what happens when you close a case:</span></span>

- <span data-ttu-id="ca104-105">如果這種情況中包含保留任何內容位置，將會關閉這些保留。</span><span class="sxs-lookup"><span data-stu-id="ca104-105">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="ca104-106">這可能會導致內容被永久刪除或清除，由使用者或自動化程序，例如刪除原則。</span><span class="sxs-lookup"><span data-stu-id="ca104-106">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="ca104-107">關閉案例只會關閉該案例相關聯的保留。</span><span class="sxs-lookup"><span data-stu-id="ca104-107">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="ca104-108">如果其他保留的位置上的內容位置 （例如訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="ca104-108">If other holds are place on a content location (such as a Litigation Hold.</span></span> <span data-ttu-id="ca104-109">保留原則或從不同的 eDiscovery 案例保留） 仍會維護這些保留。</span><span class="sxs-lookup"><span data-stu-id="ca104-109">a Preservation Policy, or a hold from a different eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="ca104-110">這種情況仍然會列在安全 & 與規範中心中的 [eDiscovery] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="ca104-110">The case is still listed on the eDiscovery page in the Security & Compliance Center.</span></span> <span data-ttu-id="ca104-111">會保留的詳細資訊、 保留、 搜尋，並關閉案例的成員。</span><span class="sxs-lookup"><span data-stu-id="ca104-111">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="ca104-112">會在關閉之後，您可以編輯案例。</span><span class="sxs-lookup"><span data-stu-id="ca104-112">You can edit a case after it's closed.</span></span> <span data-ttu-id="ca104-113">例如，您可以新增或移除成員，建立搜尋、 匯出搜尋結果，以及準備進階 eDiscovery 中分析的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="ca104-113">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="ca104-114">作用中及已關閉的情況下的主要差異在於，保留已關閉時關閉案例。</span><span class="sxs-lookup"><span data-stu-id="ca104-114">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="ca104-115">若要關閉案例：</span><span class="sxs-lookup"><span data-stu-id="ca104-115">To close a case:</span></span>

1. <span data-ttu-id="ca104-116">在 [**進階電子文件探索**] 頁面上，選取您想要關閉的案例。</span><span class="sxs-lookup"><span data-stu-id="ca104-116">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="ca104-117">在 [**設定**] 索引標籤上 [**案例資訊**，請按一下 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="ca104-117">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="ca104-118">按一下 [**關閉案例**。</span><span class="sxs-lookup"><span data-stu-id="ca104-118">Click **Close case**.</span></span>

<span data-ttu-id="ca104-119">若要刪除的案例：</span><span class="sxs-lookup"><span data-stu-id="ca104-119">To delete a case:</span></span>

1. <span data-ttu-id="ca104-120">在 [**進階電子文件探索**] 頁面上，選取您想要刪除的案例。</span><span class="sxs-lookup"><span data-stu-id="ca104-120">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="ca104-121">在 [**設定**] 索引標籤上 [**案例資訊**，請按一下 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="ca104-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="ca104-122">按一下 [**刪除案例**。</span><span class="sxs-lookup"><span data-stu-id="ca104-122">Click **Delete case**.</span></span> 
