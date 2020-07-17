---
title: 在 Microsoft 365 的安全性中心建立及追蹤 ServiceNow 入場券
description: 瞭解如何在 Microsoft 365 安全中心的 ServiceNow 中建立及追蹤票證。
keywords: 安全性，Microsoft 365，M365，安全分數，安全性中心，ServiceNow，票證，任務
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 16ee37b1c7bf33c902db35af2d29744f42830ea7
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094831"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="9049f-104">在 Microsoft 365 的安全性中心建立及追蹤 ServiceNow 入場券</span><span class="sxs-lookup"><span data-stu-id="9049f-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

<span data-ttu-id="9049f-105">[Microsoft 365 的安全性中心](overview-security-center.md)已增強，可在 ServiceNow 中以本機方式建立及追蹤票證。</span><span class="sxs-lookup"><span data-stu-id="9049f-105">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="9049f-106">深入瞭解 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="9049f-106">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="9049f-107">在 [安全性中心] 中，安全性管理員可以直接傳送[Microsoft Secure 得分](microsoft-secure-score.md)改進動作來 ServiceNow 和建立票證。</span><span class="sxs-lookup"><span data-stu-id="9049f-107">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="9049f-108">您可以建立事件管理和變更管理票證。</span><span class="sxs-lookup"><span data-stu-id="9049f-108">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="9049f-109">然後，您可以在 [安全性中心] 首頁中追蹤它們，然後 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="9049f-109">They can then be tracked in the security center home page, and ServiceNow.</span></span>

- [<span data-ttu-id="9049f-110">**深入瞭解必要條件、資料交換及疑難排解**</span><span class="sxs-lookup"><span data-stu-id="9049f-110">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="9049f-111">**在規範中心管理 ServiceNow 入場券** (即將推出) </span><span class="sxs-lookup"><span data-stu-id="9049f-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="9049f-112">將 Microsoft 365 的安全性中心連線至 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="9049f-112">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="9049f-113">流覽至 Microsoft 365 的「安全性中心」首頁，以查看 ServiceNow 連接卡。</span><span class="sxs-lookup"><span data-stu-id="9049f-113">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![您使用 ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="9049f-115">選取 [連線至 ServiceNow] 以移至 [ServiceNow 設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9049f-115">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="9049f-116">依照指示授權 Microsoft 365 連接器應用程式。</span><span class="sxs-lookup"><span data-stu-id="9049f-116">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="9049f-117">在您授權 Microsoft 365 security center 和 ServiceNow 之間的連線之前，請確定您使用您在安裝步驟中建立的整合使用者登入和密碼。</span><span class="sxs-lookup"><span data-stu-id="9049f-117">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="9049f-118">請勿使用您的個人認證。</span><span class="sxs-lookup"><span data-stu-id="9049f-118">Do not use your personal credentials.</span></span>

<span data-ttu-id="9049f-119">在您遵循指示和授權連線之後，請在 Microsoft 365 [安全性中心] 連線頁面和 ServiceNow Microsoft 365 票證發放連接器應用程式體驗中查看線上狀態。</span><span class="sxs-lookup"><span data-stu-id="9049f-119">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="9049f-120">現在，您已全部設定為開始建立任務！</span><span class="sxs-lookup"><span data-stu-id="9049f-120">Now you are all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="9049f-121">疑難排解</span><span class="sxs-lookup"><span data-stu-id="9049f-121">Troubleshooting</span></span>

<span data-ttu-id="9049f-122">瞭解您在連線過程中可能會遇到的常見錯誤，以及如何在[疑難排解區段](tickets.md#troubleshooting)中加以緩解。</span><span class="sxs-lookup"><span data-stu-id="9049f-122">Learn common errors you may encounter in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="9049f-123">建立任務並將其共用至 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="9049f-123">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="9049f-124">整合設定後，根據特定的[Microsoft 安全分數](microsoft-secure-score.md)改進動作建立 ServiceNow 工作。</span><span class="sxs-lookup"><span data-stu-id="9049f-124">Once the integration is set up, create ServiceNow tasks based on specific [Microsoft Secure Score](microsoft-secure-score.md) improvement actions.</span></span> <span data-ttu-id="9049f-125">請移至 Microsoft 365 安全性中心入口網站中安全評分的任何改進動作，然後選取 [**共用**]。</span><span class="sxs-lookup"><span data-stu-id="9049f-125">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select **Share**.</span></span> <span data-ttu-id="9049f-126">其中一個 dropdown 選項是 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="9049f-126">One of the dropdown options is ServiceNow.</span></span>

<span data-ttu-id="9049f-127">工作會產生，您可以在其中設定優先順序及編輯名稱、描述或到期日。</span><span class="sxs-lookup"><span data-stu-id="9049f-127">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="9049f-128">填寫所有必要欄位後，將工作傳送至 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="9049f-128">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="9049f-129">這項工作會顯示在 ServiceNow 成為 Microsoft 365 安全性和設定變更要求。</span><span class="sxs-lookup"><span data-stu-id="9049f-129">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="9049f-130">追蹤票據</span><span class="sxs-lookup"><span data-stu-id="9049f-130">Track tickets</span></span>

<span data-ttu-id="9049f-131">一旦 ServiceNow 變更管理和事件管理票證已建立，便會顯示在 Microsoft 365 安全中心首頁的卡片上。</span><span class="sxs-lookup"><span data-stu-id="9049f-131">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="9049f-132">您可以從這些卡片建立票證、查看所有票證或管理 ServiceNow 設定。</span><span class="sxs-lookup"><span data-stu-id="9049f-132">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow 變更管理票證](../../media/change-management-375.png)  ![ServiceNow 事件管理票證](../../media/incident-management-375.png)

<span data-ttu-id="9049f-135">若要在 Microsoft 365 的安全性中心重新布建或管理您的 ServiceNow 整合，請選取 [管理任何卡片上的**ServiceNow**設定]。</span><span class="sxs-lookup"><span data-stu-id="9049f-135">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="9049f-136">從那裡移除目前的 ServiceNow 連線，並自訂票證狀態名稱。</span><span class="sxs-lookup"><span data-stu-id="9049f-136">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="9049f-137">使用 Microsoft 365 security center 中顯示的 ServiceNow 入場券，您的工作可以在一個位置進行追蹤，並依據其他安全性儀表板專案進行處理。</span><span class="sxs-lookup"><span data-stu-id="9049f-137">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="9049f-138">資源</span><span class="sxs-lookup"><span data-stu-id="9049f-138">Resources</span></span>

- [<span data-ttu-id="9049f-139">深入瞭解必要條件、資料交換及疑難排解</span><span class="sxs-lookup"><span data-stu-id="9049f-139">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="9049f-140">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="9049f-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md)