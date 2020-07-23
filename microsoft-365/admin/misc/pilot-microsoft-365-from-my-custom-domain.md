---
title: 從我的自訂網域試驗 Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何只用兩個測試帳戶來試驗自訂365網域的電子郵件功能。
ms.openlocfilehash: bfcb2bda4d560ab629ddebed88ac1d55e6224c05
ms.sourcegitcommit: 5f980a9eb5aca61cf3662ef0bc65dec215e21656
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/20/2020
ms.locfileid: "45186038"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a>從我的自訂網域試驗 Microsoft 365

您可以使用下列需求和限制試驗 Microsoft 365：

- 您目前的電子郵件提供方必須提供電子郵件轉寄功能。

- 您必須在 DNS 主機服務提供方上管理 Microsoft 365 DNS 記錄，而不是讓 Microsoft 365 為您管理這些記錄。

    如需深入了解，請[新增 DNS 記錄以連接您的網域](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。

- 其他電子郵件伺服器上的使用者無法使用空閒/忙碌資訊。

- 系統管理員無法從單一位置管理所有使用者帳戶。

- 使用者可能無法使用 Microsoft 365 垃圾郵件篩選。

## <a name="set-up-a-microsoft-365-pilot"></a>設定 Microsoft 365 試驗

按照下列步驟設定 Microsoft 365 試驗：

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a>步驟 1:登入 Microsoft 365 系統管理中心。

1. 使用您的工作或學校帳戶，登入 [[Microsoft 365 系統管理中心]](https://admin.microsoft.com)。

2. 選取左側功能窗格中的 **[設定]** > **[網域]**。

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a>步驟 2：確認您擁有要使用的網域

1. 在 **[網域]** 頁面上，選取 **[新增網域]**。

2. 在方塊中輸入網域名稱，選取 **[使用這個網域]**，然後選取 **[繼續]**。

3. 選取您要用網域測試的服務，例如 [電子郵件] 和 [即時訊息]。

5. 依照 **驗證** 網域頁面上的逐步指示，然後選取 **[驗證]**。

    DNS 變更生效的時間可能在幾分鐘到 72 小時之間。

    驗證成功後，會要求您修改您的 DNS 記錄。

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a>步驟 3：在 Exchange Online 中將網域標示為共用

1. 在 Exchange 系統管理中心的 **[郵件流程]** 區段中，選取 **[接受的網域]**，然後選取您要修改的網域。

2. 按兩下以開啟視窗，然後選取 **[內部轉送]**。 

3. 選取 **[儲存]**。

    此設定可能需要幾分鐘的時間才會生效。

### <a name="step-4-unblock-the-existing-email-server-optional"></a>步驟 4：解除封鎖現有的電子郵件伺服器 (選用)

Microsoft 365 使用 Exchange Online Protection （EOP）來保護垃圾郵件。 如果您目前的郵件伺服器會轉寄大量的垃圾郵件，EOP 可能會封鎖您現有的郵件伺服器。 如果您信任其他電子郵件提供方的垃圾郵件防護，您可以在 Microsoft 365 中解除封鎖伺服器。

> [!NOTE]
> 取消封鎖現有的電子郵件伺服器，就能讓透過您原始伺服器抵達的任何垃圾郵件被送達 Microsoft 365 信箱，而您無法評估 Microsoft 365 防止垃圾郵件的效果。

1. 在 Exchange 系統管理中心流覽窗格中，選取 **[保護]**，然後選取 **[連線篩選]**。

2. 在 **[IP允許清單]** 中，選擇**+**，然後新增目前電子郵件提供方的郵件伺服器 IP 位址。 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a>步驟 5：建立使用者帳戶並設定主要 (回覆) 地址

1. 在 Microsoft 365 系統管理中心，選取 **[使用者]** > **[作用中的使用者]**。

2. 新增兩個現有的使用者來建立兩個測試帳戶。

    針對每個帳戶，請選取 **+ 新增一名使用者**，並填寫要求的資訊，包含您想測試的密碼方式。

    要確保使用者的電子郵件一致，**[使用者名稱]** 欄位必須符合使用者目前的電子郵件地址。 

3. 選擇適當的授權，按一下 **[下一步]**，然後按一下 **[完成新增]**。 

4. 從 **[使用者名稱]** 旁的下拉式清單中，選取您的自訂網域名稱。 

5. 選取 **[建立]** > **[關閉]**。

### <a name="step-6-update-dns-records-at-your-dns-hosting-provider"></a>步驟 6：在 DNS 主機服務提供方上更新您 DNS 記錄

登入您的 DNS 主機服務提供方的網站，然後依照 [[新增 DNS 記錄以連結您的網域]](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) 指示進行操作。

**請將下列兩者列為例外：**

- 不建立新的 MX 記錄或變更現有的 MX 記錄。

- 如果您已經有先前電子郵件提供方的寄件者原則架構 (SPF) 記錄，則無需為 Exchange Online 建立新的 SPF (TXT) 記錄，只需新增 "include:spf.protection.outlook.com" 至目前的 TXT 記錄即可。

    例如， “v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all”。

    如果您還沒有 SPF 記錄，請修改 Microsoft 365 所建議的記錄，以包含您目前電子郵件提供方的網域，並新增 spf.protection.outlook.com。 這會從兩個電子郵件系統授權外寄郵件。

### <a name="step-7-set-up-email-forwarding-at-your-current-provider"></a>步驟 7：設定目前提供方的電子郵件轉寄功能

在目前的電子郵件提供方中，為您的使用者電子郵件帳戶設定轉寄至 onmicrosoft.com 網域：

- 轉寄使用者 A 信箱至 usera@yourcompany.onmicrosoft.com

- 轉寄使用者 B 信箱至 userb@yourcompany.onmicrosoft.com

當您完成此步驟時，所有傳送到 usera@yourcompany.com 和 userb@yourcompany.com 的電子郵件都可在 Microsoft 365 中使用。

> [!NOTE]
> 請連絡您目前的電子郵件提供方，以了解設定電子郵件轉寄的確切步驟。<br/>
> 您不需要在目前的電子郵件提供方中保留郵件複本。<br/>
> 大部分提供方轉寄的電子郵件都會原封不動地保留寄件者的 [回覆] 地址，因此回覆會寄給原始寄件者。

### <a name="step-8-test-mail-flow"></a>步驟 8：測試郵件流程

1. 使用使用者 A 的認證登入 Outlook 網頁應用程式。

2. 執行下列測試：

    - 將電子郵件（例如）傳送到使用者 B 來測試本地 Microsoft 電子郵件。系統會立即傳送電子郵件。 在此情況下，郵件不會傳送到原始伺服器上的使用者 B 信箱，因為 Microsoft 365 信箱為本機。

    - 透過向使用者，例如使用者 C，傳送電子郵件，以測試傳送電子郵件給現有電子郵件系統中的使用者效果。該電子郵件會傳送到您原始郵件伺服器上使用者 C 的信箱。

    - 請確認已從外部帳戶或從現有電子郵件系統的員工電子郵件帳戶正確設定轉寄。 例如，從使用者 C 或 Hotmail 帳戶的原始伺服器帳戶，向使用者 A 傳送電子郵件，並確認該電子郵件有到達使用者 A 的 Microsoft 365 信箱。

### <a name="step-9-move-mailbox-contents"></a>步驟 9：移動信箱內容

由於您只會移動兩個測試使用者，而使用者 A 和使用者 B 都使用 Outlook，因此您可以在新 Outlook 設定檔中開啟舊的 .PST 檔案，並複製其中郵件、行事曆專案、聯絡人等等，以移動電子郵件。 如需深入了解，請參閱[從 Outlook 的 .pst 檔案匯入電子郵件、連絡人和行事曆](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac)。

將檔案匯入至 Microsoft 365 信箱中的適當位置之後，您就可以從任何裝置隨時隨地存取這些專案。

當涉及更多信箱，或如果員工並未使用 Outlook 的話，您可以使用 Exchange 系統管理中心提供的遷移工具。 若要開始使用，請移至 Exchange 系統管理中心，並依照 [將電子郵件從 IMAP 伺服器遷移到 Exchange Online 信箱] 中的指示進行 - 我們需要新的文章資源]。