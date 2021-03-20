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
description: 瞭解如何讓您的使用者與外部使用者共用會議及約會的行事曆。
ms.openlocfilehash: 5fc80965ae277e66dfbf73de80618dec03d26759
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915047"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="96e3c-103">與外部使用者共用行事曆</span><span class="sxs-lookup"><span data-stu-id="96e3c-103">Share calendars with external users</span></span>

<span data-ttu-id="96e3c-104">有時候，您的使用者必須與組織外部的人員排程會議。</span><span class="sxs-lookup"><span data-stu-id="96e3c-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="96e3c-105">為了簡化尋找常見會議時間的程式，Microsoft 365 可讓您為這些人員提供行事曆。</span><span class="sxs-lookup"><span data-stu-id="96e3c-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="96e3c-106">這些是必須查看組織中使用者空閒和忙碌時間的人員，但沒有 Microsoft 365 組織的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="96e3c-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="96e3c-107">您可以為組織中的所有使用者啟用「行事曆共用」的 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="96e3c-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="96e3c-108">啟用共用之後，您的使用者就可以使用 Outlook Web App 與組織內部或外部的任何人共用其行事曆。</span><span class="sxs-lookup"><span data-stu-id="96e3c-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="96e3c-109">組織內部的人員可以查看共用的行事曆及其自己的行事曆。</span><span class="sxs-lookup"><span data-stu-id="96e3c-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="96e3c-110">組織外部人員會收到可用來檢視行事曆的 URL。</span><span class="sxs-lookup"><span data-stu-id="96e3c-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="96e3c-111">組織中的使用者決定何時共用和共用多少。</span><span class="sxs-lookup"><span data-stu-id="96e3c-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="96e3c-112">如果您要與使用 Exchange Server 2013 (一種內部部署的解決方案) 的組織共用行事曆，Exchange 系統管理員必須與雲端之間設定驗證關聯。</span><span class="sxs-lookup"><span data-stu-id="96e3c-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="96e3c-113">這稱為同盟，且必須符合最低軟體需求。</span><span class="sxs-lookup"><span data-stu-id="96e3c-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="96e3c-114">請參閱 [共用](/exchange/sharing-exchange-2013-help)，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="96e3c-114">See [Sharing](/exchange/sharing-exchange-2013-help) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="96e3c-115">使用 Microsoft 365 admin center 啟用行事曆共用</span><span class="sxs-lookup"><span data-stu-id="96e3c-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="96e3c-116">在系統管理中心中，移至 [ **設定** \> **組織設定**]。</span><span class="sxs-lookup"><span data-stu-id="96e3c-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="96e3c-117">在 [ **服務** ] 索引標籤上，選取 [行事 **曆**]。</span><span class="sxs-lookup"><span data-stu-id="96e3c-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="96e3c-118">在 [行事 **曆** ] 頁面上，選擇是否要讓使用者與組織外部的人員共用他們的行事曆，以 Microsoft 365 或 Exchange。</span><span class="sxs-lookup"><span data-stu-id="96e3c-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="96e3c-119">選擇您是否要允許未獲認證的匿名使用者 (使用者) 透過電子郵件邀請存取行事曆。</span><span class="sxs-lookup"><span data-stu-id="96e3c-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="96e3c-120">選擇可供使用者使用的行事曆資訊類型。</span><span class="sxs-lookup"><span data-stu-id="96e3c-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="96e3c-121">您可以允許所有資訊，或將其限制為僅限時間或時間、主題和位置。</span><span class="sxs-lookup"><span data-stu-id="96e3c-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="96e3c-122">邀請人員存取行事曆</span><span class="sxs-lookup"><span data-stu-id="96e3c-122">Invite people to access calendars</span></span>

<span data-ttu-id="96e3c-123">一旦啟用共用，行事曆擁有者便可將邀請擴充至特定使用者。</span><span class="sxs-lookup"><span data-stu-id="96e3c-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="96e3c-124">請參閱[在 Outlook Web App 中共用行事曆](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5)以取得相關說明。</span><span class="sxs-lookup"><span data-stu-id="96e3c-124">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span>