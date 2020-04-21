---
title: 與外部使用者共用行事曆
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: '瞭解如何讓您的使用者與外部使用者共用會議及約會的行事曆。 '
ms.openlocfilehash: bd297fc2d684357d0500495e5a8263e5279efa39
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628037"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="a22f6-103">與外部使用者共用行事曆</span><span class="sxs-lookup"><span data-stu-id="a22f6-103">Share calendars with external users</span></span>

<span data-ttu-id="a22f6-104">使用者通常需要與組織外部人員一同進行會議排程。</span><span class="sxs-lookup"><span data-stu-id="a22f6-104">It's often necessary to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="a22f6-105">為了簡化尋找相互 agreeable 會議時間的程式，Microsoft 365 可讓您將行事曆提供給「外部使用者」，而這些使用者必須查看空閒/忙碌時間，但沒有您的 Microsoft 365 環境的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="a22f6-105">To simplify the process of finding mutually agreeable meeting times, Microsoft 365 enables you to make calendars available to "external users," those who need to see free/busy time but don't have user accounts for your Microsoft 365 environment.</span></span>
  
<span data-ttu-id="a22f6-106">「行事曆共用」是一個全域設定，這表示您（系統管理員）可以針對承租人中的所有使用者啟用它。</span><span class="sxs-lookup"><span data-stu-id="a22f6-106">Calendar sharing is a global setting, meaning that you, the admin, can enable it for all users in the tenant.</span></span> <span data-ttu-id="a22f6-107">一旦啟用共用，使用者便可使用 Outlook Web App 與組織內外的任何人共用行事曆。</span><span class="sxs-lookup"><span data-stu-id="a22f6-107">Once sharing is enabled, users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="a22f6-108">組織內部人員可以並排檢視共用行事曆及其自己的行事曆。</span><span class="sxs-lookup"><span data-stu-id="a22f6-108">People inside the organization can view the shared calendar side-by-side with their own.</span></span> <span data-ttu-id="a22f6-109">組織外部人員會收到可用來檢視行事曆的 URL。</span><span class="sxs-lookup"><span data-stu-id="a22f6-109">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="a22f6-110">使用者決定共用時間、共用範圍以及何時保持其行事曆的私密性。</span><span class="sxs-lookup"><span data-stu-id="a22f6-110">Users decide when to share, how much to share, and when to keep their calendars private.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a22f6-p103">如果您要與使用 Exchange Server 2013 (一種內部部署的解決方案) 的組織共用行事曆，Exchange 系統管理員必須與雲端之間設定驗證關聯。這就是「同盟」，它必須符合最基本的軟體需求。請參閱 [共用](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx)，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a22f6-p103">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span> 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="a22f6-114">使用 Microsoft 365 admin center 啟用行事曆共用</span><span class="sxs-lookup"><span data-stu-id="a22f6-114">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="a22f6-115">在系統管理中心中，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">服務] & 增益集</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a22f6-115">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services & add-ins</a> page.</span></span> 
    
  
2. <span data-ttu-id="a22f6-116">在 [**服務&amp;增益集**] 頁面上，選取 [行事**曆**]。</span><span class="sxs-lookup"><span data-stu-id="a22f6-116">On the **Services &amp; add-ins** page, select **Calendar**.</span></span>
  
3. <span data-ttu-id="a22f6-117">在開啟的 [行事**曆**] 頁面上，選擇是否要讓您的使用者與組織外部的人員共用其行事曆（Microsoft 365 或 Exchange）。</span><span class="sxs-lookup"><span data-stu-id="a22f6-117">On the **Calendar** page that opens, choose whether you want to let your users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span>
    
4. <span data-ttu-id="a22f6-118">選擇您是否要允許匿名使用者（沒有登入認證的使用者）透過電子郵件邀請存取行事曆。</span><span class="sxs-lookup"><span data-stu-id="a22f6-118">Choose whether you want to allow anonymous users (users without logon credentials) to access calendars via an email invitation.</span></span>

5. <span data-ttu-id="a22f6-119">選擇可供使用者使用的行事曆資訊類型。</span><span class="sxs-lookup"><span data-stu-id="a22f6-119">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="a22f6-120">您可以允許所有資訊，或將其限制為僅限時間或時間、主題和位置。</span><span class="sxs-lookup"><span data-stu-id="a22f6-120">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

    
## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="a22f6-121">邀請人員存取行事曆</span><span class="sxs-lookup"><span data-stu-id="a22f6-121">Invite people to access calendars</span></span>

<span data-ttu-id="a22f6-p105">一旦針對租用戶啟用共用，行事曆擁有者便可擴大邀請特定使用者。請參閱[在 Outlook Web App 中共用行事曆](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx)以取得相關說明。</span><span class="sxs-lookup"><span data-stu-id="a22f6-p105">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx) for instructions.</span></span> 
  

