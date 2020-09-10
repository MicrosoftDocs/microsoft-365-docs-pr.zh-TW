---
title: 刪除預約行事曆
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: 使用 Microsoft 365 系統管理中心或 Windows PowerShell 刪除預約行事曆。
ms.openlocfilehash: 3a1cb1c54f60247ab72056b3e39b56b0981228b7
ms.sourcegitcommit: eb3c30d53a5434d8bad7c8f48a5612f3e2675945
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422439"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="59610-103">在預訂中刪除預約行事曆</span><span class="sxs-lookup"><span data-stu-id="59610-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="59610-104">本文說明您可以如何刪除不需要的預約行事曆。</span><span class="sxs-lookup"><span data-stu-id="59610-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="59610-105">您可以在 Microsoft 365 系統管理中心刪除預約行事曆，也可以使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="59610-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="59610-106">「預定行事曆」是 Exchange Online 中的信箱，因此您可以刪除對應的使用者帳戶，以刪除預約行事曆。</span><span class="sxs-lookup"><span data-stu-id="59610-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59610-107">您必須使用本主題上的 PowerShell 指示刪除您在2017或之前所建立的所有預約行事曆。</span><span class="sxs-lookup"><span data-stu-id="59610-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="59610-108">在2018或之後所建立的所有預約行事曆，都可以在 Microsoft 365 系統管理中心中刪除。</span><span class="sxs-lookup"><span data-stu-id="59610-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="59610-109">預約行事曆是儲存預約行事曆和資料之相關資訊的位置，包括：</span><span class="sxs-lookup"><span data-stu-id="59610-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="59610-110">建立預約行事歷時新增的商務資訊、標誌和工作時間</span><span class="sxs-lookup"><span data-stu-id="59610-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="59610-111">建立預約行事歷時新增相關人員和服務</span><span class="sxs-lookup"><span data-stu-id="59610-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="59610-112">所有的預約和休假工作會在建立時新增至預約行事曆。</span><span class="sxs-lookup"><span data-stu-id="59610-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="59610-113">一旦刪除預約行事曆，此額外資訊也會永久刪除，且無法復原。</span><span class="sxs-lookup"><span data-stu-id="59610-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="59610-114">在 Microsoft 365 系統管理中心刪除預約行事曆</span><span class="sxs-lookup"><span data-stu-id="59610-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="59610-115">移至 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="59610-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="59610-116">In the Admin center, select **Users**.</span><span class="sxs-lookup"><span data-stu-id="59610-116">In the Admin center, select **Users**.</span></span>

   ![Microsoft 365 系統管理中心中使用者使用者介面的影像](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="59610-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span><span class="sxs-lookup"><span data-stu-id="59610-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Microsoft 365 系統管理中心中「刪除使用者 UI」的影像](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="59610-120">使用 Exchange Online PowerShell 刪除預約行事曆</span><span class="sxs-lookup"><span data-stu-id="59610-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="59610-121">請參閱連線 [至 Exchange online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 以取得連線至 exchange online PowerShell 的必要條件和指引。</span><span class="sxs-lookup"><span data-stu-id="59610-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="59610-122">若要執行這些步驟，您必須選擇 [以系統管理員身分執行] 選項，使用您所執行的 active Microsoft PowerShell 命令視窗。</span><span class="sxs-lookup"><span data-stu-id="59610-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="59610-123">輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="59610-123">Enter the following command:</span></span>

   ```PowerShell
    $user = get-credential
   ```

1. <span data-ttu-id="59610-124">出現提示時，請以租使用者系統管理員認證登入，以裝載您想要永久刪除之預定行事曆的 Microsoft 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="59610-124">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

1. <span data-ttu-id="59610-125">在 PowerShell 命令提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="59610-125">At the PowerShell command prompt, enter this command:</span></span>

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. <span data-ttu-id="59610-126">輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="59610-126">Enter the following command:</span></span>

   ```PowerShell
    Import-PSSession $s
   ```

1. <span data-ttu-id="59610-127">完成此命令的處理之後，請輸入下列命令，以取得您租使用者中的預約信箱清單：</span><span class="sxs-lookup"><span data-stu-id="59610-127">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. <span data-ttu-id="59610-128">輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="59610-128">Type the following command:</span></span>

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="59610-129">請務必輸入您要永久刪除之預定信箱別名的確切名稱。</span><span class="sxs-lookup"><span data-stu-id="59610-129">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

1. <span data-ttu-id="59610-130">若要確認是否已刪除行事曆，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="59610-130">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   <span data-ttu-id="59610-131">已刪除的行事曆不會出現在輸出中。</span><span class="sxs-lookup"><span data-stu-id="59610-131">The deleted calendar will not appear in the output.</span></span>
