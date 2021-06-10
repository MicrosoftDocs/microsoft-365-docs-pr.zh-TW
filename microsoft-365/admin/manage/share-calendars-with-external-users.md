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
description: 啟用 Microsoft 365 系統管理中心的行事曆共用，讓使用者能與組織內部或外部的任何人共用他們的行事曆。
ms.openlocfilehash: ee2b48182efec3e8bc22f47fd1657cd123ec65f8
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635807"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="f7ed7-103">與外部使用者共用行事曆</span><span class="sxs-lookup"><span data-stu-id="f7ed7-103">Share calendars with external users</span></span>

<span data-ttu-id="f7ed7-104">有時候，您的使用者必須與組織外部的人員排程會議。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="f7ed7-105">若要簡化尋找常見會議時間的程式，Microsoft 365 可讓您為這些人員提供行事曆。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="f7ed7-106">這些是必須查看組織中使用者空閒和忙碌時間的人員，但沒有 Microsoft 365 組織的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="f7ed7-107">您可以針對組織中的所有使用者，啟用 Microsoft 365 系統管理中心的行事曆共用。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f7ed7-108">啟用共用之後，您的使用者就可以使用 Outlook Web App，與組織內部或外部的任何人共用其行事曆。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="f7ed7-109">組織內部的人員可以查看共用的行事曆及其自己的行事曆。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="f7ed7-110">組織外部人員會收到可用來檢視行事曆的 URL。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="f7ed7-111">組織中的使用者決定何時共用和共用多少。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="f7ed7-112">如果您要與使用 Exchange Server 2013 (一種內部部署的解決方案) 的組織共用行事曆，Exchange 系統管理員必須與雲端之間設定驗證關聯。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="f7ed7-113">這稱為同盟，且必須符合最低軟體需求。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="f7ed7-114">請參閱 [共用](/exchange/sharing-exchange-2013-help)，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-114">See [Sharing](/exchange/sharing-exchange-2013-help) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="f7ed7-115">啟用使用 Microsoft 365 系統管理中心的行事曆共用</span><span class="sxs-lookup"><span data-stu-id="f7ed7-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="f7ed7-116">在系統管理中心中，移至 **設定** \> **Org 設定**。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="f7ed7-117">在 [ **服務** ] 索引標籤上，選取 [行事 **曆**]。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="f7ed7-118">在 [行事 **曆**] 頁面上，選擇是否要讓使用者與組織外部的人員共用他們的行事曆，以 Microsoft 365 或 Exchange。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="f7ed7-119">選擇您是否要允許未獲認證的匿名使用者 (使用者) 透過電子郵件邀請存取行事曆。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="f7ed7-120">選擇可供使用者使用的行事曆資訊類型。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="f7ed7-121">您可以允許所有資訊，或將其限制為僅限時間或時間、主題和位置。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="f7ed7-122">邀請人員存取行事曆</span><span class="sxs-lookup"><span data-stu-id="f7ed7-122">Invite people to access calendars</span></span>

<span data-ttu-id="f7ed7-123">一旦啟用共用，行事曆擁有者便可將邀請擴充至特定使用者。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="f7ed7-124">如需相關指示，請參閱[在 Outlook Web App 中共用您](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5)的行事曆。</span><span class="sxs-lookup"><span data-stu-id="f7ed7-124">For instructions, see [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5).</span></span>

## <a name="related-content"></a><span data-ttu-id="f7ed7-125">相關內容</span><span class="sxs-lookup"><span data-stu-id="f7ed7-125">Related content</span></span>

<span data-ttu-id="f7ed7-126">[開啟或關閉網站](/sharepoint/change-external-sharing-site) (文章) \ 的外部共用</span><span class="sxs-lookup"><span data-stu-id="f7ed7-126">[Turn external sharing on or off for a site](/sharepoint/change-external-sharing-site) (article)\</span></span>
<span data-ttu-id="f7ed7-127">[Microsoft 365 系統管理中心 (影片的概覽](../../business-video/admin-center-overview.md)) </span><span class="sxs-lookup"><span data-stu-id="f7ed7-127">[Overview of the Microsoft 365 admin center](../../business-video/admin-center-overview.md) (video)\</span></span>
<span data-ttu-id="f7ed7-128">[管理電子郵件和行事曆](../email/index.yml) (連結頁面) </span><span class="sxs-lookup"><span data-stu-id="f7ed7-128">[Manage email and calendars](../email/index.yml) (link page)</span></span>