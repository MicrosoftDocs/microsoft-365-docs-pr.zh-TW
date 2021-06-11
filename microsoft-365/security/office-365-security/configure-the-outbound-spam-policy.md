---
title: 設定輸出垃圾郵件篩選
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何在 Exchange Online Protection (EOP) 中查看、建立、修改和刪除輸出垃圾郵件原則。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 13b25300b6e5b42c860c58546f9c084a244b5f1f
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878913"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>在 EOP 中設定輸出垃圾郵件篩選

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織若沒有 Exchange Online 信箱，則會自動檢查透過 EOP 傳送的輸出電子郵件是否有垃圾郵件和不尋常的傳送活動。

組織中使用者的外寄垃圾郵件通常表示已遭破壞的帳戶。 可疑的輸出郵件會標示為垃圾郵件 (不論垃圾郵件信賴等級或 SCL) 並透過[高風險傳遞集](high-risk-delivery-pool-for-outbound-messages.md)區路由傳送，以協助保護服務的信譽， (也就是保留 Microsoft 365 來源電子郵件伺服器，而不是 IP 封鎖清單) 。 系統管理員會自動收到可疑的輸出電子郵件活動，並透過 [警示原則](../../compliance/alert-policies.md)封鎖使用者。

EOP 使用輸出垃圾郵件原則做為組織的整體防禦垃圾郵件的一部分。 如需詳細資訊，請參閱[反垃圾郵件保護](anti-spam-protection.md)。

系統管理員可以查看、編輯和設定 (，但不會刪除預設的輸出垃圾郵件原則) 。 為了獲得更多細微性，您也可以建立適用于組織中特定使用者、群組或網域的自訂輸出垃圾郵件原則。 自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。

您可以在 Microsoft 365 Microsoft 365 Defender 入口網站] 或 PowerShell (Exchange Online PowerShell 中設定輸出垃圾郵件原則，以 Microsoft 365 Exchange Online 組織使用的信箱。組織的獨立 EOP PowerShell，不 Exchange Online 信箱) 。

EOP 中的外寄垃圾郵件原則基本元素為：

- **輸出垃圾郵件篩選原則**：指定輸出垃圾郵件篩選 verdicts 和通知選項的動作。
- **輸出垃圾郵件篩選規則**：指定原則套用至) 外寄垃圾郵件篩選原則的優先順序和收件者篩選 (。

當您在 Microsoft 365 Defender 入口網站中管理輸出垃圾郵件原則時，這兩個元素之間的差異並不明顯。

- 當您建立原則時，實際上是建立輸出垃圾郵件篩選規則和相關聯的輸出垃圾郵件篩選原則，同時為這兩者使用相同的名稱。
- 當您修改原則時，與名稱、優先順序、啟用或停用的設定或收件者篩選器相關的設定會修改外寄垃圾郵件篩選規則。 所有其他設定都會修改相關聯的輸出垃圾郵件篩選原則。
- 當您移除原則時，會移除輸出垃圾郵件篩選規則和相關聯的輸出垃圾郵件篩選原則。

在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，您可以個別管理原則和規則。 如需詳細資訊，請參閱本文稍後的[使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定輸出垃圾郵件原則](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies)一節。

每個組織都有一個名為 Default 的內建輸出垃圾郵件原則，具有下列屬性：

- 原則會套用至組織中的所有收件者，即使沒有輸出的垃圾郵件篩選規則 (收件者篩選器，) 與原則相關聯。
- 此原則的自訂優先順序值是 **最低的**，表示您無法進行任何修改（此原則ㄧ律到最後才會套用）。 任何自訂垃圾郵件原則的優先順序一律都高於名為「預設」的原則。
- 此原則是預設的 (**IsDefault** 屬性具有`True`值)，且您無法刪除此項預設原則。

若要增加輸出垃圾郵件篩選的效能，您可以使用套用至特定使用者或使用者群組的更嚴格設定來建立自訂輸出垃圾郵件原則。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您可以在中開啟 Microsoft 365 的 Defender 入口網站 <https://security.microsoft.com> 。 若要直接移至 [反垃圾郵件設定] 頁面，請使用 <https://security.microsoft.com/antispam>。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：
  - 若要新增、修改和刪除輸出垃圾郵件原則，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。
  - 若要唯讀的輸出垃圾郵件原則的存取權，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。

  如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。

  **附註**：

  - 在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。

- 如需輸出垃圾郵件原則的建議設定，請參閱 [EOP 呼出垃圾郵件篩選原則設定](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings)。

- 已 **超過名稱電子郵件傳送限制** 的預設 [警示原則](../../compliance/alert-policies.md)、已偵測 **到的可疑電子郵件**，以及 **限制傳送電子郵件的使用者** 已將電子郵件通知傳送給 **TenantAdmins** (**Global admins** 的成員。) 群組關於不尋常的外寄電子郵件活動，以及由於輸出垃圾郵件而封鎖的使用者。 如需詳細資訊，請參閱 [確認限制使用者的警示設定](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。 建議您使用這些警示原則，而不是在輸出垃圾郵件原則中使用通知選項。

## <a name="use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies"></a>使用 Microsoft 365 Defender 入口網站建立輸出垃圾郵件原則

在 Microsoft 365 Defender 入口網站中建立自訂的輸出垃圾郵件原則，會同時使用相同的名稱建立垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則。

1. 在 Microsoft 365 Defender 入口網站中，移至「**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則** 原則] \> 區段 \> **反垃圾郵件**。

2. 在 [ **反垃圾郵件原則** ] 頁面上，按一下 [建立 ![ 圖示 ](../../media/m365-cc-sc-create-icon.png) **建立原則** ]，然後從下拉式清單中選取 [ **輸出** ]。

3. 原則精靈隨即開啟。 在 [命名您的原則 **]** 頁面上，設定這些設定：
   - **名稱**：輸入原則的唯一描述性名稱。
   - **說明**：輸入原則的選擇性說明。

   完成後，按 [下一步 **]**。

4. 在顯示的 [使用者、群組和網域 **]** 頁面上，識別原則適用的內部收件者 (收件者條件)：
   - **使用者**：您組織中指定的信箱、郵件使用者或郵件連絡人。
   - **群組**：您組織中指定的通訊群組、啟用郵件功能的安全性群組或 Microsoft 365 群組。
   - **網域**：您組織中指定的 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件者。

   按一下適當的方塊，開始輸入值，然後從結果中選取您想要的值。 視需要重複此程序多次。 若要移除現有的值，請按一下 ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) 值旁邊的 [移除]。

   針對使用者或群組，您可以使用大部分識別碼 (名稱、顯示名稱、別名、電子郵件地址、帳戶名稱等)，但會在結果中顯示對應的顯示名稱。 針對使用者，接著輸入星號 (\*) 來查看所有可用的值。

   相同條件中的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。 不同的條件則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。

   - **排除這些使用者、群組和網域**：若要為原則適用的內部收件者新增例外 (收件者例外)，請選取此選項並設定例外。 設定和行為就像是條件。

   完成後，按 [下一步 **]**。

5. 在開啟的 [ **保護設定** ] 頁面上，設定下列設定：
   - **郵件限制**：此區段中的設定會設定從 **Exchange Online** 信箱傳出電子郵件的限制：
     - **設定外部郵件限制**：每小時的外部收件者數目上限。
     - **設定內部郵件限制**：每小時的最大內部收件者數目。
     - **設定每日郵件限制**：每日總收件者數目上限。

     有效的值為0到10000。 預設值為0，這表示使用服務預設值。 如需詳細資訊，請參閱傳送 [限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

    在方塊中輸入值，或使用方塊上的增加/減少箭號。

   - **對達到郵件限制之使用者的限制**：在 [ **保護設定** ] 區段中的任何限制超過時，從下拉式清單中選取動作。

     針對所有動作，使用者指定的收件者 **受到限制傳送電子郵件** 警示原則 (和現在的重複，如果由於此頁面稍後的傳送 **輸出垃圾郵件設定而封鎖，則會通知這些使用者和群組**) 接收電子郵件通知。

     - **限制使用者傳送郵件，直到下列日期為止**：此為預設值。 傳送電子郵件通知，而且在下一天（根據 UTC 時間）之後，使用者將無法再傳送一封以上的郵件。 系統管理員無法覆寫此區塊。
       - 名為「 **使用者限制傳送電子郵件** 的活動警示」會通知系統管理員 (透過電子郵件和「 **查看提醒** 」頁面) 。
       - **當寄件者因** 在原則中傳送輸出垃圾郵件設定而遭到封鎖時，在 [通知特定人員] 中指定的任何收件者也都會收到通知。
       - 在下一天之後，使用者將無法再傳送任何郵件到以 UTC 時間為基礎。 系統管理員無法覆寫此區塊。
     - **限制使用者傳送郵件**：電子郵件通知已傳送，使用者會新增至 Microsoft 365 Defender  <https://security.microsoft.com/restrictedusers> 入口網站中的限制使用者，而且使用者必須先將電子郵件從系統管理員的 **受限使用者** 移除，才能傳送電子郵件。系統管理員從清單中移除使用者後，該天的使用者將不會受到限制。 如需相關指示，請參閱 [在傳送垃圾郵件後移除受限使用者入口網站中的使用者](removing-user-from-restricted-users-portal-after-spam.md)。
     - **無動作，只發出警示**：已傳送電子郵件通知。

   - 轉寄 **規則**：使用本節中的設定來控制自動將電子郵件轉送 **Exchange Online 信箱** 傳送至外部寄件者。 如需詳細資訊，請參閱[在 Microsoft 365 中控制自動外部電子郵件轉接](external-email-forwarding.md)。

     > [!NOTE]
     > 停用自動轉寄功能時，收件者會收到未傳遞回報 (也稱為 NDR 或退回郵件) 如果外部寄件者將電子郵件傳送至已就地進行轉接的信箱。 如果郵件是由內部寄件者傳送 **，且** 轉寄方法是 [信箱](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) 轉寄 (又稱為 _SMTP 轉送_) ，則內部寄件者會收到 NDR。 如果因收件匣規則而發生轉接，內部寄件者不會收到 NDR。

     從 [ **自動轉送規則** ] 下拉式清單中選取下列其中一項動作：

     - **自動系統控制**：允許輸出垃圾郵件篩選控制自動外部電子郵件轉發。 這是預設值。
     - **On**：自動外部電子郵件轉寄功能未由原則停用。
     - **Off**：原則已停用所有自動外部電子郵件轉接。

   - **通知**：使用區段中的設定來設定其他收件者，該收件者應接收可疑輸出電子郵件訊息的副本及通知：

     - **傳送超過這些限制的可疑輸出的副本給這些使用者和群組**：此設定會將指定的收件者新增至可疑的輸出郵件的 [密件副本] 欄位。

       > [!NOTE]
       > 此設定僅適用于預設輸出垃圾郵件原則。 在您建立的自訂輸出垃圾郵件原則中無法運作。

       若要啟用此設定，請選取核取方塊。 在出現的方塊中，按一下方塊中，輸入有效的電子郵件地址，然後按 Enter 或選取方塊下方顯示的完整值。

       視需要重複此步驟多次。 若要移除現有的值，請按一下 ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) 值旁邊的 [移除]。

   - **如果寄件者因傳送輸出垃圾郵件而遭到封鎖，請通知這些使用者和群組**

     > [!IMPORTANT]
     >
     > - 此設定正從輸出垃圾郵件原則中被取代。
     >
     > - 名為「**使用者限制于傳送電子郵件** 的預設 [警示原則](../../compliance/alert-policies.md)」已將電子郵件通知傳送給 **TenantAdmins** (**Global admins**) 群組中的使用者，因為超過 [**收件者限制**] 區段中的限制時，已遭到封鎖。 **強烈建議您在輸出垃圾郵件原則中使用警示原則，而不是此設定，以通知系統管理員和其他使用者**。 如需相關指示，請參閱 [確認限制使用者的警示設定](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。

   完成後，按 [下一步 **]**。

6. 在顯示的 [檢閱 **]** 頁面上，檢閱您的設定。 您可以在每個區段中選取 [編輯 **]**，以修改該區段內的設定。 或者，您可以按一下 [上一步] 或在精靈中選取特定頁面。

   完成時，按一下 [建立 **]**。

7. 在顯示的確認頁面上，按一下 [完成 **]**。

## <a name="use-the-microsoft-365-defender-portal-to-view-outbound-spam-policies"></a>使用 Microsoft 365 Defender 入口網站來查看輸出垃圾郵件原則

1. 在 Microsoft 365 Defender 入口網站中，移至「**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則** 原則] \> 區段 \> **反垃圾郵件**。

2. 在 [**反垃圾郵件原則**] 頁面上，尋找下列其中一個值：
   - **Type** 值為 **自訂輸出垃圾郵件原則**
   - **名稱** 值為 **反垃圾郵件輸出原則 (預設)**

   反垃圾郵件原則清單中會顯示下列屬性：

   - **名稱**
   - **狀態**
   - **優先順序**
   - **類型**

3. 當您按一下名稱來選取輸出垃圾郵件原則時，會在飛入的視窗中顯示原則設定。

## <a name="use-the-microsoft-365-defender-portal-to-modify-outbound-spam-policies"></a>使用 Microsoft 365 Defender 入口網站修改輸出垃圾郵件原則

1. 在 Microsoft 365 Defender 入口網站中，移至「**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則** 原則] \> 區段 \> **反垃圾郵件**。

2. 在 [ **反垃圾郵件原則** ] 頁面上，按一下 [名稱]，從清單中選取外寄垃圾郵件原則：
   - 您在 [ **類型** ] 欄中的值為 **自訂輸出垃圾郵件原則** 時所建立的自訂原則。
   - 名為 **反垃圾郵件輸出原則的預設原則 (預設)**。

3. 在顯示的原則詳細資料飛出視窗中，在每個區段中選取 [編輯 **]**，以修改該區段內的設定。 如需這些設定的詳細資訊，請參閱本文的[使用 Microsoft 365 Defender 入口網站建立輸出垃圾郵件原則](#use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies)一節。

   針對預設輸出垃圾郵件原則，[套用 **至** ] 區段無法使用 (原則套用至所有人) ，而且您無法重新命名原則。

若要啟用或停用原則、設定原則優先順序順序、或設定使用者隔離通知，請參閱下列各節。

### <a name="enable-or-disable-custom-outbound-spam-policies"></a>啟用或停用自訂輸出垃圾郵件原則

您無法停用預設輸出垃圾郵件原則。

1. 在 Microsoft 365 Defender 入口網站中，移至「**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則** 原則] \> 區段 \> **反垃圾郵件**。

2. 在 [**反垃圾郵件原則**] 頁面上，按一下 [名稱]，從清單中選取 [**自訂輸出垃圾郵件原則** 的 **類型值**] 的原則。

3. 在顯示的原則詳細資料飛出視窗頂端，您會看到下列其中一個值：
   - **原則關閉**：若要開啟原則，請按一下 ![開啟圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [開啟 **]**。
   - **原則開啟**：若要關閉原則，請按一下 ![關閉圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [關閉 **]**。

4. 在顯示的確認對話方塊中，按一下 [開啟 **]** 或 [關閉 **]**。

5. 按一下原則詳細資料飛出視窗中的 [關閉 **]**。

回到主要原則頁面，原則的 [狀態 **]** 值將會是 [開啟 **]** 或 [關閉 **]**。

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>設定自訂輸出垃圾郵件原則的優先順序

根據預設，輸出垃圾郵件原則的優先順序會根據它們在 (較舊的原則中所建立的順序來降低優先順序) 。 較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。 不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。

若要變更原則的優先順序，請按一下 [**增加優先順序**] 或 [**降低優先順序**] 的原則 (您無法直接修改 Microsoft 365 Defender 入口網站) 中的 **優先順序** 號碼。 只有在您有多個原則時，變更原則的優先順序才有意義。

 **附註**：

- 在 Microsoft 365 Defender 入口網站中，您在建立輸出垃圾郵件原則之後，您只能變更其優先順序。 在 PowerShell 中，您可以在建立垃圾郵件篩選規則時覆寫預設優先順序 (這會影響現有規則的優先順序)。
- 輸出垃圾郵件原則的處理順序會依顯示的順序 (第一個原則的 **Priority** 值為 0) 。 預設輸出垃圾郵件原則的優先順序值為 **最低**，您無法變更。

1. 在 Microsoft 365 Defender 入口網站中，移至「**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則** 原則] \> 區段 \> **反垃圾郵件**。

2. 在 [**反垃圾郵件原則**] 頁面上，從清單中選取 [選取具有 **自訂輸出垃圾郵件原則** 的 **類型值** 的原則]，然後按一下名稱。

3. 在顯示的原則詳細資料飛出視窗的頂端，根據目前的優先順序值和自訂原則數目，您會看到 [增加優先順序 **]** 或 [降低優先順序 **]**：
   - **優先順序** 值為 **0** 的輸出垃圾郵件原則，只會有 [**降低優先順序**] 選項可用。
   - 具有最低 **優先順序** 值的輸出垃圾郵件原則 (例如， **3**) 只有 [ **增加優先順序** ] 選項可用。
   - 如果您有三個以上的輸出垃圾郵件原則，則最高和最低的優先順序值之間的原則都有可用的 [ **增加優先順序** ] 和 [ **降低優先順序** ] 選項。

   按一下 ![增加優先順序圖示](../../media/m365-cc-sc-increase-icon.png) [增加優先順序 **]** 或 ![降低優先順序圖示](../../media/m365-cc-sc-decrease-icon.png) [降低優先順序 **]** 以變更 [優先順序 **]** 值。

4. 完成後，請按一下原則詳細資料飛出視窗中的 [關閉 **]**。

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-outbound-spam-policies"></a>使用 Microsoft 365 Defender 入口網站來移除自訂輸出垃圾郵件原則

當您使用 Microsoft 365 Defender 入口網站移除自訂輸出垃圾郵件原則時，會同時刪除垃圾郵件篩選規則和對應的垃圾郵件篩選原則。 您無法移除預設的輸出垃圾郵件原則。

1. 在 Microsoft 365 Defender 入口網站中，移至「**電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則** 原則] \> 區段 \> **反垃圾郵件**。

2. 在 [**反垃圾郵件原則**] 頁面上，按一下 [名稱]，從清單中選取 [**自訂輸出垃圾郵件原則** 的 **類型值**] 的原則。 在顯示的原則詳細資料飛出視窗頂端，按一下 ![更多動作圖示](../../media/m365-cc-sc-more-actions-icon.png) [其他動作 **]** \> ![刪除原則圖示](../../media/m365-cc-sc-delete-icon.png) [刪除原則 **]**。

3. 在顯示的確認對話方塊中，按一下 [是 **]**。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定輸出垃圾郵件原則

如先前所述，輸出垃圾郵件原則是由輸出垃圾郵件篩選原則和外寄垃圾郵件篩選規則所組成。

在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，輸出垃圾郵件篩選原則和輸出垃圾郵件篩選規則之間的差異很明顯。 您可以使用 **\* -HostedOutboundSpamFilterPolicy** Cmdlet 來管理輸出垃圾郵件篩選原則，也可以使用 **\* -HostedOutboundSpamFilterRule** Cmdlet 來管理輸出垃圾郵件篩選規則。

- 在 PowerShell 中，您先建立輸出垃圾郵件篩選原則，然後建立輸出垃圾郵件篩選規則，以識別套用規則的原則。
- 在 PowerShell 中，您可以分別修改輸出垃圾郵件篩選原則和輸出垃圾郵件篩選規則中的設定。
- 當您從 PowerShell 中移除輸出垃圾郵件篩選原則時，對應的輸出垃圾郵件篩選規則不會自動移除，反之亦然。

### <a name="use-powershell-to-create-outbound-spam-policies"></a>使用 PowerShell 建立輸出垃圾郵件原則

在 PowerShell 中建立輸出垃圾郵件原則的程式分為兩個步驟：

1. 建立輸出垃圾郵件篩選原則。
2. 建立輸出垃圾郵件篩選規則，以指定套用規則的輸出垃圾郵件篩選原則。

   **附註**：

   - 您可以建立新的輸出垃圾郵件篩選規則，並將現有的未關聯輸出垃圾郵件篩選原則指派給它。 輸出垃圾郵件篩選規則無法與一個以上的輸出垃圾郵件篩選原則相關聯。
   - 您可以在建立原則之前，于 Microsoft 365 Defender 入口網站中無法使用 PowerShell 中的新外寄垃圾郵件篩選原則上設定下列設定：
     - _在_ `$false` **HostedOutboundSpamFilterRule** Cmdlet) 上，建立新原則做為已停用 (。
     - 在 _\<Number\>_ **HostedOutboundSpamFilterRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。
   - 在您將原則指派給外寄垃圾郵件篩選規則之前，您在 PowerShell 中建立的新輸出垃圾郵件篩選原則不會顯示在 Microsoft 365 Defender 入口網站中。

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>步驟1：使用 PowerShell 來建立輸出垃圾郵件篩選原則

若要建立輸出垃圾郵件篩選原則，請使用下列語法：

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

此範例會建立名為 Contoso 主管的新輸出垃圾郵件篩選原則，並提供下列設定：

- 收件者速率限制限制為預設值較小的值。 如需詳細資訊，請參閱[在 Microsoft 365 選項](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)中傳送限制。

- 達到其中一個限制之後，使用者就無法傳送郵件。

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

如需詳細的語法及參數資訊，請參閱 [HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)。

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>步驟2：使用 PowerShell 建立輸出垃圾郵件篩選規則

若要建立輸出垃圾郵件篩選規則，請使用下列語法：

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

此範例會使用下列設定建立名為 Contoso 主管的新輸出垃圾郵件篩選規則：

- 名為 Contoso 主管的輸出垃圾郵件篩選原則與規則相關聯。
- 此規則會套用至名為 ContosoExecutives Group 的群組成員。

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

如需詳細的語法及參數資訊，請參閱 [HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>使用 PowerShell 來查看輸出垃圾郵件篩選原則

若要傳回所有輸出垃圾郵件篩選原則的摘要清單，請執行下列命令：

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

若要傳回特定輸出垃圾郵件篩選原則的詳細資訊，請使用下列語法：

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

本範例會傳回名為「主管」的輸出垃圾郵件篩選原則的所有屬性值。

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

如需詳細的語法及參數資訊，請參閱 [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>使用 PowerShell 來查看輸出垃圾郵件篩選規則

若要查看現有的輸出垃圾郵件篩選規則，請使用下列語法：

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

若要傳回所有輸出垃圾郵件篩選規則的摘要清單，請執行下列命令：

```PowerShell
Get-HostedOutboundSpamFilterRule
```

若要依啟用或停用篩選規則的清單，請執行下列命令：

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

若要傳回特定輸出垃圾郵件篩選規則的詳細資訊，請使用下列語法：

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

此範例會傳回名為 Contoso 主管的輸出垃圾郵件篩選規則的所有屬性值。

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

如需詳細的語法及參數資訊，請參閱 [HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>使用 PowerShell 修改輸出垃圾郵件篩選原則

當您在 PowerShell 中修改惡意程式碼篩選原則時，如您依照「 [步驟1：使用 PowerShell 建立外寄垃圾郵件篩選原則](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) 」一節所述，您在建立原則時，可以使用相同的設定。

> [!NOTE]
> 您無法重新命名外寄垃圾郵件篩選原則 (**Set-HostedOutboundSpamFilterPolicy** 指令程式沒有 _Name_ 參數) 。 當您在 Microsoft 365 Defender 入口網站中重新命名外寄垃圾郵件原則時，您只是重新命名輸出垃圾郵件篩選 _規則_。

若要修改輸出垃圾郵件篩選原則，請使用下列語法：

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱 [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>使用 PowerShell 修改輸出垃圾郵件篩選規則

當您在 PowerShell 中修改外寄垃圾郵件篩選規則時，唯一可用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。 若要啟用或停用現有的輸出垃圾郵件篩選規則，請參閱下一節。

否則，當您在 PowerShell 中修改外寄垃圾郵件篩選規則時，不會有其他設定可供使用。 當您建立規則時，如您在本文稍早的 [步驟2：使用 PowerShell 建立輸出垃圾郵件篩選規則](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 區段中所述，您可以使用相同的設定。

若要修改輸出垃圾郵件篩選規則，請使用下列語法：

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱 [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>使用 PowerShell 來啟用或停用輸出垃圾郵件篩選規則

啟用或停用 PowerShell 中的外寄垃圾郵件篩選規則，可啟用或停用輸出垃圾郵件篩選規則和指派的外寄垃圾郵件篩選原則) 的整體輸出垃圾郵件原則 (。 您無法啟用或停用預設輸出垃圾郵件原則 (永遠永遠套用至所有收件者) 。

若要啟用或停用 PowerShell 中的外寄垃圾郵件篩選規則，請使用下列語法：

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

本範例會停用名為「行銷部門」的輸出垃圾郵件篩選規則。

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

此範例會啟用相同規則。

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

如需詳細的語法及參數資訊，請參閱 [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) 和 [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>使用 PowerShell 設定輸出垃圾郵件篩選規則的優先順序

您可以對規則設定的最高優先順序值為 0。 您可以設定的最低值則取決於規則的數目。 例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。 變更現有規則的優先順序會對其他規則造成階層式影響。 例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。

若要設定 PowerShell 中的外寄垃圾郵件篩選規則的優先順序，請使用下列語法：

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。 優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

**附註**：

- 若要在建立新規則時設定其優先順序，請改用 **HostedOutboundSpamFilterRule** Cmdlet 上的 _priority_ 參數。
- 外寄的預設垃圾郵件篩選原則沒有對應的垃圾郵件篩選規則，它永遠具有「不可修改的優先順序 **」值。**

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>使用 PowerShell 移除輸出垃圾郵件篩選原則

當您使用 PowerShell 來移除輸出垃圾郵件篩選原則時，並不會移除對應的輸出垃圾郵件篩選規則。

若要在 PowerShell 中移除輸出垃圾郵件篩選原則，請使用下列語法：

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

此範例會移除名為 Marketing 部門的輸出垃圾郵件篩選原則。

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

如需詳細的語法及參數資訊，請參閱 [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>使用 PowerShell 移除輸出垃圾郵件篩選規則

當您使用 PowerShell 移除外寄垃圾郵件篩選規則時，並不會移除對應的輸出垃圾郵件篩選原則。

若要移除 PowerShell 中的外寄垃圾郵件篩選規則，請使用下列語法：

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

此範例會移除名為 Marketing 部門的輸出垃圾郵件篩選規則。

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

如需詳細的語法及參數資訊，請參閱 [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)。

## <a name="for-more-information"></a>如需詳細資訊

[從 [受限使用者] 入口網站中移除封鎖的使用者](removing-user-from-restricted-users-portal-after-spam.md)

[輸出郵件的高風險傳遞集區](high-risk-delivery-pool-for-outbound-messages.md)

[反垃圾郵件保護常見問題集](anti-spam-protection-faq.yml)

[自動轉寄訊息的報告](mfi-auto-forwarded-messages-report.md)
