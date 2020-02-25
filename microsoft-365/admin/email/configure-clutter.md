---
title: 為您的組織設定待過濾郵件
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: '了解如何啟用或停用待過濾郵件功能的所有或使用 Exchange PowerShell 中您的組織，特定的使用者。 '
ms.openlocfilehash: 65aa614095ecbebaad3d7eb38af1e74166ce20ac
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251703"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="56147-103">為您的組織設定待過濾郵件</span><span class="sxs-lookup"><span data-stu-id="56147-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="56147-104">[焦點收件匣](../setup/configure-focused-inbox.md)將要取代待過濾郵件。</span><span class="sxs-lookup"><span data-stu-id="56147-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="56147-105">了解更多：[焦點收件匣和待過濾郵件我們計劃的更新](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="56147-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="56147-106">身為系統管理員，您可能要管理 Office 365 中的 [待過濾郵件] 功能。</span><span class="sxs-lookup"><span data-stu-id="56147-106">As an admin, you may have to manage the Clutter feature in Office 365.</span></span> <span data-ttu-id="56147-107">若要開啟開啟/關閉待過濾郵件功能的使用者在組織中，您必須使用 Exchange PowerShell。</span><span class="sxs-lookup"><span data-stu-id="56147-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="56147-108">(個人可以將它開啟開/關使用這些指示：[關閉/使用待過濾郵件在 Outlook 中開啟](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)。)</span><span class="sxs-lookup"><span data-stu-id="56147-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).)</span></span> 
  
<span data-ttu-id="56147-109">如需使用 Exchange PowerShell 的詳細資訊請參閱[Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831)和[Exchange Online PowerShell 連線到](https://go.microsoft.com/fwlink/?LinkID=722415)。</span><span class="sxs-lookup"><span data-stu-id="56147-109">Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="56147-110">您必須擁有帳戶至少具備 Exchange 服務系統管理員角色和能夠連線至 Exchange Online powershell。</span><span class="sxs-lookup"><span data-stu-id="56147-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="56147-111">使用 Exchange PowerShell 在開啟待過濾郵件</span><span class="sxs-lookup"><span data-stu-id="56147-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="56147-112">您可以啟用待過濾郵件手動信箱透過執行[Set-clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="56147-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="56147-113">您也可以執行[Get-clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet，來檢視您組織中的信箱的待過濾郵件設定。</span><span class="sxs-lookup"><span data-stu-id="56147-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="56147-114">開啟單一使用者名稱為 Allie Bellew 待過濾郵件</span><span class="sxs-lookup"><span data-stu-id="56147-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="56147-115">關閉待過濾郵件使用 Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="56147-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="56147-116">您可以停用待過濾郵件手動信箱執行[Set-clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="56147-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="56147-117">您也可以執行[Get-clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet，來檢視您組織中的信箱的**待過濾郵件**設定。</span><span class="sxs-lookup"><span data-stu-id="56147-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="56147-118">關閉單一使用者名稱為 Allie Bellew 待過濾郵件：</span><span class="sxs-lookup"><span data-stu-id="56147-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="56147-119">如果您使用 PowerShell 大量建立您的使用者，則您必須先執行[Set-clutter](https://go.microsoft.com/fwlink/?LinkID=834446)針對管理待過濾郵件的每位使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="56147-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="56147-120">開啟/關閉切換待過濾郵件時顯示在網頁型 Outlook 中的使用者？</span><span class="sxs-lookup"><span data-stu-id="56147-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="56147-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="56147-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="56147-122">身為系統管理員，您可以重新啟用待過濾郵件使用 Exchange PowerShell。</span><span class="sxs-lookup"><span data-stu-id="56147-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="56147-123">完成之後，將會關閉焦點收件匣和待過濾郵件是作用中一次。</span><span class="sxs-lookup"><span data-stu-id="56147-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="56147-124">**如果您使用網頁型 Outlook 與 Office 365 商務版訂閱：**</span><span class="sxs-lookup"><span data-stu-id="56147-124">**If you're using Outlook on the web with an Office 365 business subscription:**</span></span>
  
- <span data-ttu-id="56147-125">如果使用者目前已啟用的待過濾郵件：</span><span class="sxs-lookup"><span data-stu-id="56147-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="56147-126">會顯示待過濾郵件設定</span><span class="sxs-lookup"><span data-stu-id="56147-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="56147-127">如果使用者目前是否有焦點收件匣啟用：</span><span class="sxs-lookup"><span data-stu-id="56147-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="56147-128">將不會出現待過濾郵件設定</span><span class="sxs-lookup"><span data-stu-id="56147-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="56147-129">如果已啟用未待過濾郵件或焦點收件匣：</span><span class="sxs-lookup"><span data-stu-id="56147-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="56147-130">待過濾郵件與焦點收件匣會顯示為使用者的郵件設定] 中的選項</span><span class="sxs-lookup"><span data-stu-id="56147-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="56147-131">**如果您使用 Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="56147-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="56147-132">如果使用者目前已啟用的待過濾郵件：</span><span class="sxs-lookup"><span data-stu-id="56147-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="56147-133">會顯示待過濾郵件設定</span><span class="sxs-lookup"><span data-stu-id="56147-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="56147-134">如果使用者目前是否有焦點收件匣啟用：</span><span class="sxs-lookup"><span data-stu-id="56147-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="56147-135">將不會出現待過濾郵件設定</span><span class="sxs-lookup"><span data-stu-id="56147-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="56147-136">如果已啟用未待過濾郵件或焦點收件匣：</span><span class="sxs-lookup"><span data-stu-id="56147-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="56147-137">待過濾郵件與焦點收件匣會顯示為使用者的郵件設定] 中的選項</span><span class="sxs-lookup"><span data-stu-id="56147-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="56147-138">如果使用者在過去中有些時候啟用焦點收件匣：</span><span class="sxs-lookup"><span data-stu-id="56147-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="56147-139">永遠不會出現待過濾郵件設定</span><span class="sxs-lookup"><span data-stu-id="56147-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="56147-140">否則，</span><span class="sxs-lookup"><span data-stu-id="56147-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="56147-141">將會出現待過濾郵件設定</span><span class="sxs-lookup"><span data-stu-id="56147-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="56147-142">相關文章</span><span class="sxs-lookup"><span data-stu-id="56147-142">Related articles</span></span>
<span data-ttu-id="56147-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="56147-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="56147-144">若要排序低優先順序的郵件，在 Outlook 中使用待過濾郵件</span><span class="sxs-lookup"><span data-stu-id="56147-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.office.com/article/7755ebf5-4585-469b-b1ab-8b12425c6b6b.aspx)
    
[<span data-ttu-id="56147-145">用來排序低優先順序的郵件，在 OWA 中的待過濾郵件</span><span class="sxs-lookup"><span data-stu-id="56147-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[<span data-ttu-id="56147-146">關閉 Outlook 中的待過濾郵件</span><span class="sxs-lookup"><span data-stu-id="56147-146">Turn off Clutter in Outlook</span></span>](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

