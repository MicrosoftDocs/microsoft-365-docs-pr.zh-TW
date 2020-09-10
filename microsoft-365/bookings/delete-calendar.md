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
# <a name="delete-a-booking-calendar-in-bookings"></a>在預訂中刪除預約行事曆

本文說明您可以如何刪除不需要的預約行事曆。 您可以在 Microsoft 365 系統管理中心刪除預約行事曆，也可以使用 PowerShell。 「預定行事曆」是 Exchange Online 中的信箱，因此您可以刪除對應的使用者帳戶，以刪除預約行事曆。

> [!IMPORTANT]
> 您必須使用本主題上的 PowerShell 指示刪除您在2017或之前所建立的所有預約行事曆。 在2018或之後所建立的所有預約行事曆，都可以在 Microsoft 365 系統管理中心中刪除。

預約行事曆是儲存預約行事曆和資料之相關資訊的位置，包括：

- 建立預約行事歷時新增的商務資訊、標誌和工作時間
- 建立預約行事歷時新增相關人員和服務
- 所有的預約和休假工作會在建立時新增至預約行事曆。

> [!WARNING]
> 一旦刪除預約行事曆，此額外資訊也會永久刪除，且無法復原。

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心刪除預約行事曆

1. 移至 Microsoft 365 系統管理中心。

1. In the Admin center, select **Users**.

   ![Microsoft 365 系統管理中心中使用者使用者介面的影像](../media/bookings-admin-center-users.png)

1. On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.

   ![Microsoft 365 系統管理中心中「刪除使用者 UI」的影像](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>使用 Exchange Online PowerShell 刪除預約行事曆

請參閱連線 [至 Exchange online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 以取得連線至 exchange online PowerShell 的必要條件和指引。

若要執行這些步驟，您必須選擇 [以系統管理員身分執行] 選項，使用您所執行的 active Microsoft PowerShell 命令視窗。

1. 輸入下列命令：

   ```PowerShell
    $user = get-credential
   ```

1. 出現提示時，請以租使用者系統管理員認證登入，以裝載您想要永久刪除之預定行事曆的 Microsoft 365 租使用者。

1. 在 PowerShell 命令提示字元處，輸入下列命令：

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. 輸入下列命令：

   ```PowerShell
    Import-PSSession $s
   ```

1. 完成此命令的處理之後，請輸入下列命令，以取得您租使用者中的預約信箱清單：

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. 輸入下列命令：

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > 請務必輸入您要永久刪除之預定信箱別名的確切名稱。

1. 若要確認是否已刪除行事曆，請輸入下列命令：

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   已刪除的行事曆不會出現在輸出中。
