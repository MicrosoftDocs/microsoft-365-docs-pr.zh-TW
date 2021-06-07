---
title: 向 Bookings 新增員工
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
description: 使用此頁面可建立您的教職員工清單，以及管理職員詳細資料，例如姓名、電話號碼和電子郵件地址。
ms.openlocfilehash: 23757c492986936125eff1203e6a99231164da22
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768942"
---
# <a name="add-staff-to-bookings"></a>向 Bookings 新增員工

在 [預約] 中的 [人員] 頁面是您建立人員名單的所在位置，可管理人員姓名、電話號碼和電子郵件地址等人員成員詳細資料。 您也可以在這裡設定每個教職員工成員的工作時間。

## <a name="before-you-begin"></a>開始之前

雖然預約是 Microsoft 365 的功能，但並非所有的教職員工成員都必須具備 Microsoft 365 帳戶。 所有教職員工成員必須具有有效的電子郵件地址，才能接收預約及排程變更。

## <a name="watch-add-your-staff-to-bookings"></a>觀賞：將教職員工新增至預定

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

## <a name="steps"></a>步驟

1. 移至 [[管理人員] 頁面](https://outlook.office.com/bookings/staff)，然後選取 [**新增人員**]

2. 選取 [ **新增教職員工** ] 按鈕。

3. 當您從組織中新增職員時，請在 [ **新增人員** ] 欄位中輸入他們的名稱，然後在下拉式功能表中出現這些職員時加以選取。 其他欄位將會自動填入。

    新增教職員工成員之後，您可以選取其名稱旁邊的 **x** ，然後編輯 [ **新增人員** ] 欄位，以編輯顯示在所有預約通訊上的名稱。 如果您想讓教職員工成員為客戶顯示特定標題或名稱，例如列出 Adele Vance 為 "Vance，MD"，這會很有用。

4. 若要從組織外部新增人員，請手動填入其電子郵件及其他資訊。

    > [!NOTE]
    > 您租使用者以外的人員將無法與預約共用空閒/忙碌資訊。

5. 針對每個教職員工成員，選取角色：系統管理員、Viewer 或 Guest。
    - **管理員** 可以編輯所有設定、新增及移除人員，以及建立、編輯或刪除預定。
    - **查看者** 可以在行事曆上看到所有的預約，但他們無法修改或刪除。 他們擁有設定的唯讀存取權。
    - 可將 **來賓** 指派給預約，但無法開啟預約信箱。

6. 若要 **建立或變更指派給他們的預約** 以啟用人員電子郵件，請選取 [以電子郵件通知所有人員]。 以下是電子郵件範例：

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="預定電子郵件通知":::

7. 如果您想要從員工成員的行事曆取得空閒/忙碌資訊，以透過預約對預約服務的可用性產生影響，請選取 **Office 365 行事曆中的事件**。

    例如，如果教職員工成員在星期三為3pm 排定小組會議或個人約會，則預約會顯示該職員成員無法在該時隙中預約。 在 [預定的行事曆] 視圖中，該時間會顯示為 [忙碌] 或 [暫定]，如以下範例所示。

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="預定行事曆的視圖":::

> [!IMPORTANT]
> 強烈建議您在預設會開啟此設定 () 以避免雙重預約，並優化教職員工成員的可用性。

8. 選取 [ **使用上班時間** ]，將教職員工成員的所有 bookable 時間設定為僅限您在 [商務時間] 頁面上的 [ **上班時間** ] 區段中設定的上班時間內。

    一旦您取消選擇此方塊，員工便可獲得自訂的時數，以進一步限制可預約。 這對於教職員工成員可能只在網站週二和星期三的情況，或其上午一種約會類型的方式，以及其 afternoons 其他類型的情況十分有用。

    > [!NOTE]
    > 當您將教職員工成員指派給服務時，只會顯示您新增至 [員工] 頁面的前1名人員成員。

## <a name="make-a-bookings-user-a-super-user-without-adding-them-as-staff-in-bookings"></a>讓預約使用者成為超級使用者，而不是將其新增為預定員工

您可能想要在預約中新增人員至您的職員清單，而不讓客戶或用戶端使用。 當您將其設為超級使用者後，他們就會成為預約信箱的管理員。 做為預約信箱的管理員，會定義為具有預約信箱的完整存取權及「代理傳送」許可權。

> [!NOTE]
> 只有在所加入的使用者尚未在預約中指派 **檢視器** 角色時，這些步驟才會運作。

1. [與 PowerShell Microsoft 365 的連線](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

2. 使用 PowerShell，使用下列命令指派完全存取：

    ```powershell
    Add-MailboxPermission -Identity <bookingmailbox@emailaddress> -User <adminusers@emailaddress> -AccessRights FullAccess -Deny:$false
    ```

3. 然後執行此命令指派「傳送為」許可權。

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

以下是將 Allie Bellew 新增至 Contoso daycare 預約信箱 PowerShell 命令的範例。

1. 請先執行此命令：

    ```powershell
    Add-MailboxPermission -Identity "daycare@contoso.com" -User "Allie Bellew" -AccessRights FullAccess -InheritanceType All
    ```

2. 然後執行下列命令：

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

**Allie Bellew** 現在具有管理員存取權，但在預約中未顯示為 bookable 人員。
