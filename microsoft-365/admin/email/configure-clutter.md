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
ms.openlocfilehash: ac68893bc0aeea5ab214698c54524921e2b1921d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915899"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="781f2-103">為您的組織設定混亂</span><span class="sxs-lookup"><span data-stu-id="781f2-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="781f2-104">[焦點收件](../setup/configure-focused-inbox.md) 匣即將取代雜亂的收件匣。</span><span class="sxs-lookup"><span data-stu-id="781f2-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="781f2-105">深入瞭解： [更新焦點收件匣和待過濾的計畫](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="781f2-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="781f2-106">身為系統管理員，您可能需要管理 Microsoft 365 中的雜亂功能。</span><span class="sxs-lookup"><span data-stu-id="781f2-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="781f2-107">若要開啟/關閉組織中使用者的雜亂功能，您必須使用 Exchange PowerShell。</span><span class="sxs-lookup"><span data-stu-id="781f2-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="781f2-108"> (個人可以使用這些指示將其開啟/關閉： [在 Outlook 中關閉/開啟雜亂功能](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)。</span><span class="sxs-lookup"><span data-stu-id="781f2-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="781f2-109">請參閱 [使用 PowerShell 搭配 Exchange online](/powershell/exchange/exchange-online-powershell) 並聯機 [至 exchange online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 以取得使用 exchange PowerShell 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="781f2-109">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="781f2-110">您必須具有至少具有 Exchange 服務系統管理員角色的帳戶，以及使用 PowerShell 連線至 Exchange Online 的許可權。</span><span class="sxs-lookup"><span data-stu-id="781f2-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="781f2-111">使用 Exchange PowerShell 開啟雜亂</span><span class="sxs-lookup"><span data-stu-id="781f2-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="781f2-112">您可以執行 [Set-Clutter](/powershell/module/exchange/set-clutter) Cmdlet，手動為信箱啟用雜亂功能。</span><span class="sxs-lookup"><span data-stu-id="781f2-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet.</span></span> <span data-ttu-id="781f2-113">您也可以執行 [Get-Clutter](/powershell/module/exchange/get-clutter) Cmdlet，以查看組織中信箱的雜亂設定。</span><span class="sxs-lookup"><span data-stu-id="781f2-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="781f2-114">針對名為 Allie 的單一使用者開啟雜亂 Bellew</span><span class="sxs-lookup"><span data-stu-id="781f2-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="781f2-115">使用 Exchange PowerShell 來關閉雜亂功能</span><span class="sxs-lookup"><span data-stu-id="781f2-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="781f2-116">您可以執行 [Set-Clutter](/powershell/module/exchange/set-clutter) Cmdlet，手動停用信箱的雜亂。</span><span class="sxs-lookup"><span data-stu-id="781f2-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet.</span></span> <span data-ttu-id="781f2-117">您也可以執行 [Get-Clutter](/powershell/module/exchange/get-clutter) Cmdlet，以查看組織中信箱的 **雜亂** 設定。</span><span class="sxs-lookup"><span data-stu-id="781f2-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="781f2-118">針對名為 Allie Bellew 的單一使用者關閉雜亂：</span><span class="sxs-lookup"><span data-stu-id="781f2-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="781f2-119">如果您使用 PowerShell 大量建立使用者，則必須針對每個使用者的信箱執行 [Set-Clutter](/powershell/module/exchange/set-clutter) ，以管理雜亂。</span><span class="sxs-lookup"><span data-stu-id="781f2-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](/powershell/module/exchange/set-clutter) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="781f2-120">何時會對網頁上的 Outlook 中的使用者顯示雜亂的「開/關」參數？</span><span class="sxs-lookup"><span data-stu-id="781f2-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="781f2-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="781f2-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="781f2-122">身為系統管理員，您可以使用 Exchange PowerShell 重新啟用雜亂功能。</span><span class="sxs-lookup"><span data-stu-id="781f2-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="781f2-123">完成此動作後，焦點收件匣會關閉，而雜亂的功能將會重新成為作用中。</span><span class="sxs-lookup"><span data-stu-id="781f2-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="781f2-124">**如果您使用的是 Microsoft 365 商務版 Premium 訂閱的 Outlook 網頁版：**</span><span class="sxs-lookup"><span data-stu-id="781f2-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="781f2-125">如果使用者目前已啟用雜亂功能：</span><span class="sxs-lookup"><span data-stu-id="781f2-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="781f2-126">會出現雜亂設定</span><span class="sxs-lookup"><span data-stu-id="781f2-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="781f2-127">如果使用者目前已啟用焦點收件匣：</span><span class="sxs-lookup"><span data-stu-id="781f2-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="781f2-128">不會出現雜亂設定</span><span class="sxs-lookup"><span data-stu-id="781f2-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="781f2-129">如果沒有啟用雜亂或焦點收件匣：</span><span class="sxs-lookup"><span data-stu-id="781f2-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="781f2-130">雜亂及焦點收件匣會顯示為使用者郵件設定中的選項</span><span class="sxs-lookup"><span data-stu-id="781f2-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="781f2-131">**如果您使用的是 Outlook.com：**</span><span class="sxs-lookup"><span data-stu-id="781f2-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="781f2-132">如果使用者目前已啟用雜亂功能：</span><span class="sxs-lookup"><span data-stu-id="781f2-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="781f2-133">會出現雜亂設定</span><span class="sxs-lookup"><span data-stu-id="781f2-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="781f2-134">如果使用者目前已啟用焦點收件匣：</span><span class="sxs-lookup"><span data-stu-id="781f2-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="781f2-135">不會出現雜亂設定</span><span class="sxs-lookup"><span data-stu-id="781f2-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="781f2-136">如果沒有啟用雜亂或焦點收件匣：</span><span class="sxs-lookup"><span data-stu-id="781f2-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="781f2-137">雜亂及焦點收件匣會顯示為使用者郵件設定中的選項</span><span class="sxs-lookup"><span data-stu-id="781f2-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="781f2-138">如果使用者在過去某點啟用焦點收件匣：</span><span class="sxs-lookup"><span data-stu-id="781f2-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="781f2-139">將永遠不會出現雜亂設定</span><span class="sxs-lookup"><span data-stu-id="781f2-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="781f2-140">否則</span><span class="sxs-lookup"><span data-stu-id="781f2-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="781f2-141">會出現雜亂設定</span><span class="sxs-lookup"><span data-stu-id="781f2-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="781f2-142">相關文章</span><span class="sxs-lookup"><span data-stu-id="781f2-142">Related articles</span></span>
<span data-ttu-id="781f2-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="781f2-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="781f2-144">使用雜亂排序 Outlook 中的低優先順序郵件</span><span class="sxs-lookup"><span data-stu-id="781f2-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="781f2-145">使用雜亂將 OWA 中的低優先順序郵件排序</span><span class="sxs-lookup"><span data-stu-id="781f2-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[<span data-ttu-id="781f2-146">關閉 Outlook 中的雜亂功能</span><span class="sxs-lookup"><span data-stu-id="781f2-146">Turn off Clutter in Outlook</span></span>](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
