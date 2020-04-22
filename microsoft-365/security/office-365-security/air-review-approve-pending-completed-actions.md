---
title: 在自動調查和回應中複查及核准擱置的修復動作
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 深入瞭解 Office 365 Advanced 威脅防護方案2中自動化調查和回應功能的修復動作。
ms.openlocfilehash: d14b8827bd3c69461d832d66bb371b5d62d9802e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634637"
---
# <a name="view-pending-or-completed-remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="2ef24-104">在 Office 365 中進行自動調查後，查看擱置或已完成的修復動作</span><span class="sxs-lookup"><span data-stu-id="2ef24-104">View pending or completed remediation actions following an automated investigation in Office 365</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="2ef24-105">核准（或拒絕）暫止的動作</span><span class="sxs-lookup"><span data-stu-id="2ef24-105">Approve (or reject) pending actions</span></span>

![AIR 調查動作頁面](../../media/air-investigationactionspage.png)

<span data-ttu-id="2ef24-107">當您查看[調查的詳細資料](air-view-investigation-results.md)時，您可以核准或拒絕任何擱置的修復動作。</span><span class="sxs-lookup"><span data-stu-id="2ef24-107">While viewing the [details of an investigation](air-view-investigation-results.md), you can approve or reject any pending remediation actions.</span></span> <span data-ttu-id="2ef24-108">我們建議您儘快執行這種操作，以完成您的自動化調查。</span><span class="sxs-lookup"><span data-stu-id="2ef24-108">We recommend doing this as soon as possible so that your automated investigations complete.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ef24-109">核准或拒絕修正動作必須具有適當的許可權。</span><span class="sxs-lookup"><span data-stu-id="2ef24-109">Appropriate permissions are required to approve or reject remediation actions.</span></span> <span data-ttu-id="2ef24-110">請參閱[使用 AIR 功能所需的許可權](office-365-air.md#required-permissions-to-use-air-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="2ef24-110">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

1. <span data-ttu-id="2ef24-111">移至 [https://protection.office.com](https://protection.office.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="2ef24-111">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="2ef24-112">這樣會帶您前往安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="2ef24-112">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="2ef24-113">移至 [威脅管理]\*\*\*\*  >  [調查]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ef24-113">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="2ef24-114">在調查清單中，選取 [識別碼]\*\*\*\* 欄中的項目。</span><span class="sxs-lookup"><span data-stu-id="2ef24-114">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="2ef24-115">選取 [**動作**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2ef24-115">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="2ef24-116">選取清單中的項目。</span><span class="sxs-lookup"><span data-stu-id="2ef24-116">Select an item in the list.</span></span> <span data-ttu-id="2ef24-117">（這會啟用 [核准] 和 [拒絕] 按鈕。）</span><span class="sxs-lookup"><span data-stu-id="2ef24-117">(This activates the Approve and Reject buttons.)</span></span>

6. <span data-ttu-id="2ef24-118">查看您選取之專案的可用資訊，然後核准或拒絕動作。</span><span class="sxs-lookup"><span data-stu-id="2ef24-118">Review available information for the item(s) you selected, and then either approve or reject the action(s).</span></span> 
 - <span data-ttu-id="2ef24-119">**核准**允許開始修復。</span><span class="sxs-lookup"><span data-stu-id="2ef24-119">**Approve** allows remediation to begin.</span></span>
 - <span data-ttu-id="2ef24-120">**拒絕**不再採取任何動作</span><span class="sxs-lookup"><span data-stu-id="2ef24-120">**Reject** takes no further action</span></span>

## <a name="next-steps"></a><span data-ttu-id="2ef24-121">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2ef24-121">Next steps</span></span>

- [<span data-ttu-id="2ef24-122">Office 365 中自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="2ef24-122">Details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

- [<span data-ttu-id="2ef24-123">使用威脅瀏覽器</span><span class="sxs-lookup"><span data-stu-id="2ef24-123">Use Threat Explorer</span></span>](threat-explorer.md)