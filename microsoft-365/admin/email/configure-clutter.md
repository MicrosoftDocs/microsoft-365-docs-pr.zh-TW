---
title: 為您的組織設定混亂
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: '瞭解如何使用 Exchange PowerShell 來啟用或停用組織中所有或特定使用者的雜亂功能。 '
ms.openlocfilehash: 059fb8e626a0b05e0224fc89931453aaae43be0b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706105"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="1c617-103">為您的組織設定混亂</span><span class="sxs-lookup"><span data-stu-id="1c617-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="1c617-104">[焦點收件](../setup/configure-focused-inbox.md) 匣即將取代雜亂的收件匣。</span><span class="sxs-lookup"><span data-stu-id="1c617-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="1c617-105">深入瞭解： [更新焦點收件匣和待過濾的計畫](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="1c617-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="1c617-106">身為系統管理員，您可能需要在 Microsoft 365 中管理雜亂功能。</span><span class="sxs-lookup"><span data-stu-id="1c617-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="1c617-107">若要開啟/關閉組織中使用者的雜亂功能，您必須使用 Exchange PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1c617-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="1c617-108"> (個人可以使用這些指示將其開啟/關閉：[在 Outlook 中關閉/開啟雜亂功能](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)。</span><span class="sxs-lookup"><span data-stu-id="1c617-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="1c617-109">[使用具有 Exchange Online](/powershell/exchange/exchange-online-powershell)和連線的 PowerShell，查看[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) ，以取得使用 Exchange PowerShell 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1c617-109">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="1c617-110">您必須具有至少具備 Exchange 服務系統管理員角色的帳戶，以及使用 PowerShell 連線到 Exchange Online 的許可權。</span><span class="sxs-lookup"><span data-stu-id="1c617-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="1c617-111">使用 Exchange PowerShell 開啟雜亂</span><span class="sxs-lookup"><span data-stu-id="1c617-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="1c617-112">您可以執行 [Set-Clutter](/powershell/module/exchange/set-clutter) Cmdlet，手動為信箱啟用雜亂功能。</span><span class="sxs-lookup"><span data-stu-id="1c617-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet.</span></span> <span data-ttu-id="1c617-113">您也可以執行 [Get-Clutter](/powershell/module/exchange/get-clutter) Cmdlet，以查看組織中信箱的雜亂設定。</span><span class="sxs-lookup"><span data-stu-id="1c617-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="1c617-114">針對名為 Allie 的單一使用者開啟雜亂 Bellew</span><span class="sxs-lookup"><span data-stu-id="1c617-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="1c617-115">使用 Exchange PowerShell 關閉雜亂功能</span><span class="sxs-lookup"><span data-stu-id="1c617-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="1c617-116">您可以執行 [Set-Clutter](/powershell/module/exchange/set-clutter) Cmdlet，手動停用信箱的雜亂。</span><span class="sxs-lookup"><span data-stu-id="1c617-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet.</span></span> <span data-ttu-id="1c617-117">您也可以執行 [Get-Clutter](/powershell/module/exchange/get-clutter) Cmdlet，以查看組織中信箱的 **雜亂** 設定。</span><span class="sxs-lookup"><span data-stu-id="1c617-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="1c617-118">針對名為 Allie Bellew 的單一使用者關閉雜亂：</span><span class="sxs-lookup"><span data-stu-id="1c617-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="1c617-119">如果您使用 PowerShell 大量建立使用者，則必須針對每個使用者的信箱執行 [Set-Clutter](/powershell/module/exchange/set-clutter) ，以管理雜亂。</span><span class="sxs-lookup"><span data-stu-id="1c617-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](/powershell/module/exchange/set-clutter) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="1c617-120">何時會向網路上的 Outlook 中的使用者顯示雜亂的開啟/關閉參數？</span><span class="sxs-lookup"><span data-stu-id="1c617-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="1c617-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="1c617-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="1c617-122">身為系統管理員，您可以使用 Exchange PowerShell 重新啟用雜亂功能。</span><span class="sxs-lookup"><span data-stu-id="1c617-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="1c617-123">完成此動作後，焦點收件匣會關閉，而雜亂的功能將會重新成為作用中。</span><span class="sxs-lookup"><span data-stu-id="1c617-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="1c617-124">**如果您使用的是 Microsoft 365 商務進階版訂閱的網頁 Outlook：**</span><span class="sxs-lookup"><span data-stu-id="1c617-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="1c617-125">如果使用者目前已啟用雜亂功能：</span><span class="sxs-lookup"><span data-stu-id="1c617-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="1c617-126">會出現雜亂設定</span><span class="sxs-lookup"><span data-stu-id="1c617-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="1c617-127">如果使用者目前已啟用焦點收件匣：</span><span class="sxs-lookup"><span data-stu-id="1c617-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="1c617-128">不會出現雜亂設定</span><span class="sxs-lookup"><span data-stu-id="1c617-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="1c617-129">如果沒有啟用雜亂或焦點收件匣：</span><span class="sxs-lookup"><span data-stu-id="1c617-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="1c617-130">雜亂及焦點收件匣會顯示為使用者郵件中的選項設定</span><span class="sxs-lookup"><span data-stu-id="1c617-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="1c617-131">**如果您使用的是 Outlook .com：**</span><span class="sxs-lookup"><span data-stu-id="1c617-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="1c617-132">如果使用者目前已啟用雜亂功能：</span><span class="sxs-lookup"><span data-stu-id="1c617-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="1c617-133">會出現雜亂設定</span><span class="sxs-lookup"><span data-stu-id="1c617-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="1c617-134">如果使用者目前已啟用焦點收件匣：</span><span class="sxs-lookup"><span data-stu-id="1c617-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="1c617-135">不會出現雜亂設定</span><span class="sxs-lookup"><span data-stu-id="1c617-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="1c617-136">如果沒有啟用雜亂或焦點收件匣：</span><span class="sxs-lookup"><span data-stu-id="1c617-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="1c617-137">雜亂及焦點收件匣會顯示為使用者郵件中的選項設定</span><span class="sxs-lookup"><span data-stu-id="1c617-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="1c617-138">如果使用者在過去某點啟用焦點收件匣：</span><span class="sxs-lookup"><span data-stu-id="1c617-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="1c617-139">將永遠不會出現雜亂設定</span><span class="sxs-lookup"><span data-stu-id="1c617-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="1c617-140">否則</span><span class="sxs-lookup"><span data-stu-id="1c617-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="1c617-141">會出現雜亂設定</span><span class="sxs-lookup"><span data-stu-id="1c617-141">Clutter settings will appear</span></span>
    
## <a name="related-content"></a><span data-ttu-id="1c617-142">相關內容</span><span class="sxs-lookup"><span data-stu-id="1c617-142">Related content</span></span>

<span data-ttu-id="1c617-143">[使用雜亂 Outlook (文章中的低優先順序郵件進行排序](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)) </span><span class="sxs-lookup"><span data-stu-id="1c617-143">[Use Clutter to sort low priority messages in Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) (article)</span></span>\
<span data-ttu-id="1c617-144">使用雜亂專案 (文章) \[中排序低優先順序郵件](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)</span><span class="sxs-lookup"><span data-stu-id="1c617-144">[Use Clutter to sort low priority messages in OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) (article)\</span></span>
<span data-ttu-id="1c617-145">[在 Outlook (文章中關閉雜亂](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)) </span><span class="sxs-lookup"><span data-stu-id="1c617-145">[Turn off Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (article)</span></span>
