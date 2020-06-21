---
title: 與外部使用者共用行事曆
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: '瞭解如何讓您的使用者與外部使用者共用會議及約會的行事曆。 '
ms.openlocfilehash: 972e8376ae3d71b11205d4a6611dc6900c063ffe
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780058"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="fd123-103">與外部使用者共用行事曆</span><span class="sxs-lookup"><span data-stu-id="fd123-103">Share calendars with external users</span></span>

<span data-ttu-id="fd123-104">使用者通常需要與組織外部人員一同進行會議排程。</span><span class="sxs-lookup"><span data-stu-id="fd123-104">It's often necessary to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="fd123-105">為了簡化尋找相互 agreeable 會議時間的程式，Microsoft 365 可讓您將行事曆提供給「外部使用者」，而這些使用者必須查看空閒/忙碌時間，但沒有您的 Microsoft 365 環境的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="fd123-105">To simplify the process of finding mutually agreeable meeting times, Microsoft 365 enables you to make calendars available to "external users," those who need to see free/busy time but don't have user accounts for your Microsoft 365 environment.</span></span>
  
<span data-ttu-id="fd123-106">「行事曆共用」是一個全域設定，這表示您（系統管理員）可以針對承租人中的所有使用者啟用它。</span><span class="sxs-lookup"><span data-stu-id="fd123-106">Calendar sharing is a global setting, meaning that you, the admin, can enable it for all users in the tenant.</span></span> <span data-ttu-id="fd123-107">一旦啟用共用，使用者便可使用 Outlook Web App 與組織內外的任何人共用行事曆。</span><span class="sxs-lookup"><span data-stu-id="fd123-107">Once sharing is enabled, users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="fd123-108">組織內部人員可以並排檢視共用行事曆及其自己的行事曆。</span><span class="sxs-lookup"><span data-stu-id="fd123-108">People inside the organization can view the shared calendar side-by-side with their own.</span></span> <span data-ttu-id="fd123-109">組織外部人員會收到可用來檢視行事曆的 URL。</span><span class="sxs-lookup"><span data-stu-id="fd123-109">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="fd123-110">使用者決定共用時間、共用範圍以及何時保持其行事曆的私密性。</span><span class="sxs-lookup"><span data-stu-id="fd123-110">Users decide when to share, how much to share, and when to keep their calendars private.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fd123-111">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span><span class="sxs-lookup"><span data-stu-id="fd123-111">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="fd123-112">This is known as "federation" and must meet minimum software requirements.</span><span class="sxs-lookup"><span data-stu-id="fd123-112">This is known as "federation" and must meet minimum software requirements.</span></span> <span data-ttu-id="fd123-113">See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span><span class="sxs-lookup"><span data-stu-id="fd123-113">See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span> 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="fd123-114">使用 Microsoft 365 admin center 啟用行事曆共用</span><span class="sxs-lookup"><span data-stu-id="fd123-114">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="fd123-115">在系統管理中心中，移至 [**設定** \> **組織設定**]。</span><span class="sxs-lookup"><span data-stu-id="fd123-115">In the admin center, go to **Settings** \> **Org Settings**.</span></span> 
    
2. <span data-ttu-id="fd123-116">在 [**服務**] 索引標籤上，選取 [行事**曆**]。</span><span class="sxs-lookup"><span data-stu-id="fd123-116">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="fd123-117">在開啟的 [行事**曆**] 頁面上，選擇是否要讓您的使用者與組織外部的人員共用其行事曆（Microsoft 365 或 Exchange）。</span><span class="sxs-lookup"><span data-stu-id="fd123-117">On the **Calendar** page that opens, choose whether you want to let your users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span>
    
4. <span data-ttu-id="fd123-118">選擇您是否要允許匿名使用者（沒有登入認證的使用者）透過電子郵件邀請存取行事曆。</span><span class="sxs-lookup"><span data-stu-id="fd123-118">Choose whether you want to allow anonymous users (users without logon credentials) to access calendars via an email invitation.</span></span>

5. <span data-ttu-id="fd123-119">選擇可供使用者使用的行事曆資訊類型。</span><span class="sxs-lookup"><span data-stu-id="fd123-119">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="fd123-120">您可以允許所有資訊，或將其限制為僅限時間或時間、主題和位置。</span><span class="sxs-lookup"><span data-stu-id="fd123-120">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

    
## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="fd123-121">邀請人員存取行事曆</span><span class="sxs-lookup"><span data-stu-id="fd123-121">Invite people to access calendars</span></span>

<span data-ttu-id="fd123-122">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users.</span><span class="sxs-lookup"><span data-stu-id="fd123-122">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="fd123-123">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span><span class="sxs-lookup"><span data-stu-id="fd123-123">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span> 
  
