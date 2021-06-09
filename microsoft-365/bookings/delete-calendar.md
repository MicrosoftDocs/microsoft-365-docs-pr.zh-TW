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
description: 使用 Microsoft 365 系統管理中心或 Windows PowerShell 以刪除預約行事曆。
ms.openlocfilehash: 21fc7b9994ffd7f76ed04000a50bd0ee8f7f167e
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51034088"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="43ba0-103">在預訂中刪除預約行事曆</span><span class="sxs-lookup"><span data-stu-id="43ba0-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="43ba0-104">本文說明您可以如何刪除不需要的預約行事曆。</span><span class="sxs-lookup"><span data-stu-id="43ba0-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="43ba0-105">您可以在 Microsoft 365 系統管理中心刪除預約行事曆，也可以使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="43ba0-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="43ba0-106">[行事曆] 是 Exchange Online 中的信箱，因此您可以刪除對應的使用者帳戶，以刪除預約行事曆。</span><span class="sxs-lookup"><span data-stu-id="43ba0-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43ba0-107">您必須使用本主題上的 PowerShell 指示刪除您在2017或之前所建立的所有預約行事曆。</span><span class="sxs-lookup"><span data-stu-id="43ba0-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="43ba0-108">您可以在 Microsoft 365 系統管理中心內刪除所有在2018或之後所建立的預約行事曆。</span><span class="sxs-lookup"><span data-stu-id="43ba0-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="43ba0-109">預約行事曆是儲存預約行事曆和資料之相關資訊的位置，包括：</span><span class="sxs-lookup"><span data-stu-id="43ba0-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="43ba0-110">建立預約行事歷時新增的商務資訊、標誌和工作時間</span><span class="sxs-lookup"><span data-stu-id="43ba0-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="43ba0-111">建立預約行事歷時新增相關人員和服務</span><span class="sxs-lookup"><span data-stu-id="43ba0-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="43ba0-112">所有的預約和休假工作會在建立時新增至預約行事曆。</span><span class="sxs-lookup"><span data-stu-id="43ba0-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="43ba0-113">一旦刪除預約行事曆，此額外資訊也會永久刪除，且無法復原。</span><span class="sxs-lookup"><span data-stu-id="43ba0-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="43ba0-114">在 Microsoft 365 系統管理中心刪除預約行事曆</span><span class="sxs-lookup"><span data-stu-id="43ba0-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="43ba0-115">移至 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="43ba0-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="43ba0-116">In the Admin center, select **Users**.</span><span class="sxs-lookup"><span data-stu-id="43ba0-116">In the Admin center, select **Users**.</span></span>

   ![Microsoft 365 系統管理中心的使用者 UI 影像](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="43ba0-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span><span class="sxs-lookup"><span data-stu-id="43ba0-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Microsoft 365 系統管理中心中刪除使用者 UI 的影像](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="43ba0-120">使用 Exchange Online PowerShell 刪除預約行事曆</span><span class="sxs-lookup"><span data-stu-id="43ba0-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="43ba0-121">請參閱[連線，以 Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps)的必要條件及連線到 Exchange Online PowerShell 的指引。</span><span class="sxs-lookup"><span data-stu-id="43ba0-121">See [Connect to Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="43ba0-122">若要執行這些步驟，您必須選擇 [以系統管理員身分執行] 選項，使用您所執行的 active Microsoft PowerShell 命令視窗。</span><span class="sxs-lookup"><span data-stu-id="43ba0-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="43ba0-123">在 PowerShell 視窗中，執行下列命令來載入 EXO V2 模組：</span><span class="sxs-lookup"><span data-stu-id="43ba0-123">In a PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > <span data-ttu-id="43ba0-124">如果您已經[安裝 EXO V2 模組](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module)，上一個命令將依照編寫的內容執行。</span><span class="sxs-lookup"><span data-stu-id="43ba0-124">If you've already [installed the EXO V2 module](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module), the previous command will work as written.</span></span>
   
2. <span data-ttu-id="43ba0-125">您需要執行的命令會使用下列語法:</span><span class="sxs-lookup"><span data-stu-id="43ba0-125">The command that you need to run uses the following syntax:</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - <span data-ttu-id="43ba0-126">_\<UPN\>_ 是以使用者主體名稱格式（例如 `john@contoso.com`）表示的您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="43ba0-126">_\<UPN\>_ is your account in user principal name format (for example, `john@contoso.com`).</span></span>

3. <span data-ttu-id="43ba0-127">出現提示時，請以租使用者系統管理員認證登入，以裝載要永久刪除之預定行事曆的 Microsoft 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="43ba0-127">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

4. <span data-ttu-id="43ba0-128">完成此命令的處理之後，請輸入下列命令，以取得您租使用者中的預約信箱清單：</span><span class="sxs-lookup"><span data-stu-id="43ba0-128">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

5. <span data-ttu-id="43ba0-129">輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="43ba0-129">Type the following command:</span></span>

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="43ba0-130">請務必輸入您要永久刪除之預定信箱別名的確切名稱。</span><span class="sxs-lookup"><span data-stu-id="43ba0-130">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

6. <span data-ttu-id="43ba0-131">若要確認是否已刪除行事曆，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="43ba0-131">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   <span data-ttu-id="43ba0-132">已刪除的行事曆不會出現在輸出中。</span><span class="sxs-lookup"><span data-stu-id="43ba0-132">The deleted calendar will not appear in the output.</span></span>
