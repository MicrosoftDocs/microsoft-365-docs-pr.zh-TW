---
title: 設定輸出垃圾郵件篩選
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您將瞭解如何設定適用于組織中特定使用者、群組或網域的輸出垃圾郵件原則。
ms.openlocfilehash: 644ffb51c92f4d71d3ae2cde1eba408289573f48
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036785"
---
# <a name="configure-outbound-spam-filtering"></a>設定輸出垃圾郵件篩選

如果您是使用 Exchange Online 中的信箱或獨立 Exchange Online Protection （EOP）客戶但沒有 Exchange Online 信箱的 Microsoft 365 客戶，系統會自動檢查透過 EOP 傳送的輸出電子郵件是否有垃圾郵件和不尋常的傳送活動。

組織中使用者的外寄垃圾郵件通常表示已遭破壞的帳戶。 可疑的輸出郵件會標示為垃圾郵件（不論垃圾郵件信賴等級或 SCL 為何），並透過[高風險傳遞集](high-risk-delivery-pool-for-outbound-messages.md)區路由傳送，以協助保護服務的信譽（也就是說，保留 Microsoft 365 來源電子郵件伺服器，而非 IP 封鎖清單）。 系統管理員會自動收到可疑的輸出電子郵件活動，並透過[警示原則](../../compliance/alert-policies.md)封鎖使用者。

EOP 使用輸出垃圾郵件原則做為組織的整體防禦垃圾郵件的一部分。 如需詳細資訊，請參閱[反垃圾郵件保護](anti-spam-protection.md)。

系統管理員可以查看、編輯和設定（但不能刪除）預設輸出垃圾郵件原則。 為了獲得更多細微性，您也可以建立適用于組織中特定使用者、群組或網域的自訂輸出垃圾郵件原則。 自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。

您可以在安全性 & 合規性中心或 PowerShell （Microsoft 365 客戶的 Exchange Online PowerShell）中設定輸出垃圾郵件原則;Exchange Online Protection PowerShell 適用于獨立 EOP 客戶）。

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a>安全性 & 規範中心與 Exchange online PowerShell 或 Exchange Online Protection 中的輸出垃圾郵件原則 PowerShell

EOP 中的外寄垃圾郵件原則基本元素為：

- **輸出垃圾郵件篩選原則**：指定輸出垃圾郵件篩選 verdicts 和通知選項的動作。

- **輸出垃圾郵件篩選規則**：指定輸出垃圾郵件篩選器原則的優先順序和收件者篩選器（該原則適用于）。

當您在安全性 & 合規性中心管理輸出垃圾郵件原則時，這兩個元素之間的差異並不明顯。

- 當您在安全性 & 合規性中心建立輸出垃圾郵件原則時，實際上您實際上是使用相同的名稱建立輸出垃圾郵件篩選規則和相關聯的輸出垃圾郵件篩選原則。

- 當您在安全性 & 規範中心中修改輸出垃圾郵件原則時，與名稱、優先順序、啟用或停用的設定或收件者篩選器相關的設定會修改輸出垃圾郵件篩選規則。 所有其他設定都會修改相關聯的輸出垃圾郵件篩選原則。

- 當您從安全性 & 合規性中心移除輸出垃圾郵件原則時，會移除輸出垃圾郵件篩選規則和相關聯的輸出垃圾郵件篩選原則。

在 Exchange Online PowerShell 或獨立 Exchange Online Protection PowerShell 中，輸出垃圾郵件篩選原則和輸出垃圾郵件篩選規則之間的差異很明顯。 您可以使用** \*-HostedContentFilterPolicy** Cmdlet 來管理輸出垃圾郵件篩選原則，也可以使用** \*-disable-hostedcontentfilterrule** Cmdlet 來管理輸出垃圾郵件篩選規則。

- 在 PowerShell 中，您先建立輸出垃圾郵件篩選原則，然後建立輸出垃圾郵件篩選規則，以識別套用規則的原則。

- 在 PowerShell 中，您可以分別修改輸出垃圾郵件篩選原則和輸出垃圾郵件篩選規則中的設定。

- 當您從 PowerShell 中移除輸出垃圾郵件篩選原則時，對應的輸出垃圾郵件篩選規則不會自動移除，反之亦然。

### <a name="default-outbound-spam-policy"></a>預設輸出垃圾郵件原則

每個組織都有一個名為 Default 的內建輸出垃圾郵件原則，具有下列屬性：

- 名為 Default 的輸出垃圾郵件篩選原則會套用至組織中的所有收件者，即使沒有與原則相關聯的外寄垃圾郵件篩選規則（收件者篩選器）。

- 名為「預設」的原則具有不能修改的自訂優先順序 **Lowest** (一律最後才會套用的原則)。 任何自訂垃圾郵件原則的優先順序一律都高於名為「預設」的原則。

- 名為「預設」的原則是預設的原則 (**IsDefault** 屬性具有值 `True`)，且您無法刪除預設原則。

若要增加輸出垃圾郵件篩選的效能，您可以使用套用至特定使用者或使用者群組的更嚴格設定來建立自訂輸出垃圾郵件原則。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [反垃圾郵件設定]**** 頁面，請使用 <https://protection.office.com/antispam>。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要連接至獨立版 Exchange Online Protection PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 您必須已獲指派權限，才能執行這些程序。 若要新增、修改和刪除輸出垃圾郵件原則，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。 若要唯讀的輸出垃圾郵件原則的存取權，您必須是**Security Reader**角色群組的成員。 如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱[安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。

- 如需輸出垃圾郵件原則的建議設定，請參閱[EOP 呼出垃圾郵件篩選原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)。

- 已超過名為「**電子郵件傳送限制**」的預設[警示原則](../../compliance/alert-policies.md)、偵測**到的電子**郵件，以及限制傳送**電子郵件的使用者**已將電子郵件通知傳送給**TenantAdmins** （**全域系統管理員**）群組的成員，但由於輸出的垃圾郵件而封鎖的使用者。 如需詳細資訊，請參閱[確認限制使用者的警示設定](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。 建議您使用這些警示原則，而不是在輸出垃圾郵件原則中使用通知選項。

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>使用安全性 & 規範中心建立輸出垃圾郵件原則

在安全性 & 合規性中心建立自訂輸出垃圾郵件原則，會同時使用相同的名稱建立垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則。

1. 在安全性與合規性中心，移至 [威脅管理]**** \> [原則]**** \> [反垃圾郵件]****。

2. 在 [**反垃圾郵件設定**] 頁面上，按一下 [**建立輸出原則**]。

3. 在 [**輸出垃圾郵件篩選原則**] 的 [飛出開啟] 中，設定下列設定：

   - **名稱**：輸入原則的唯一描述性名稱。

   - **說明**：輸入原則的選擇性說明。

4. 選展開 [**通知**] 區段，設定其他應接收副本的使用者，以及可疑外寄電子郵件訊息的通知：

   - **將可疑的輸出電子郵件的複本傳送給特定人員**：此設定會將指定的使用者當做 Bcc 收件者新增至可疑的輸出郵件。 若要啟用此設定：

     a. 選取 [啟用] 設定的核取方塊。

     b. 按一下 [**新增人員**]。 在出現的 [**新增或移除**收件者] 浮出控制項中：

     c. 輸入寄件者的電子郵件地址。 您可以指定多個以分號分隔的電子郵件地址（;)或每行一位收件者。

     d. 按一下 ![新增圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 以加入收件者。

        視需要重複這些步驟。

        您新增的收件者會出現在飛入的 [**收件者清單**] 區段中。 若要刪除收件者![，請](../../media/scc-remove-icon.png)按一下 [移除] 按鈕。

     e. 完成後，按一下 [儲存]****。

     若要停用此設定，請清除核取方塊。

   - **如果寄件者因傳送輸出的垃圾郵件而遭到封鎖，請通知特定人員**：

     > [!NOTE]
     > 當使用者因超過 [**收件者限制**] 區段中的限制時[，已封鎖](../../compliance/alert-policies.md)使用者 TenantAdmins （全域系統管理員）群組的成員時，會將**電子郵件通知**傳送至**TenantAdmins** （**全域系統管理員**）群組的成員。 建議您在輸出垃圾郵件原則中使用警示原則，而不是此設定，以通知系統管理員和其他使用者。 如需相關指示，請參閱[確認限制使用者的警示設定](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。

     若要啟用此設定：

     a. 選取 [啟用] 設定的核取方塊。

     b. 按一下 [**新增人員**]。 在出現的 [**新增或移除**收件者] 浮出控制項中：

     c. 輸入寄件者的電子郵件地址。 您可以指定多個以分號分隔的電子郵件地址（;)或每行一位收件者。

     d. 按一下 ![新增圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 以加入收件者。

        視需要重複這些步驟。

        您新增的收件者會出現在飛入的 [**收件者清單**] 區段中。 若要刪除收件者![，請](../../media/scc-remove-icon.png)按一下 [移除] 按鈕。

     e. 完成後，按一下 [儲存]****。

     若要停用此設定，請清除核取方塊。

5. 選展開 [**收件者限制**] 區段，以設定可疑輸出電子郵件訊息的限制和動作：

   > [!NOTE]
   > 這些設定只適用于雲端架構信箱。
     
   - **每位使用者的收件者數目上限**

     有效的值為0到10000。 預設值為0，這表示使用服務預設值。 如需詳細資訊，請參閱[在 Microsoft 365 選項](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)中傳送限制。

     - **外部每小時限制**：每小時的外部收件者數目上限。

     - **內部每小時限制**：每小時內部收件者的數目上限。

     - **每日限制**：每日總收件者數目上限。

   - **當使用者超過上述限制時的動作**：設定超出任何一位**收件者限制**時所採取的動作。 針對所有動作，使用者指定的收件者**受到限制傳送電子郵件**提醒原則的收件者（**如果收件者由於**傳出垃圾郵件原則中傳送輸出垃圾郵件設定而遭到封鎖，則在現在的重複的通知特定人員）會收到電子郵件通知。

     - **限制使用者在下列日期之後傳送郵件**：此為預設值。 傳送電子郵件通知，而且在下一天（根據 UTC 時間）之後，使用者將無法再傳送一封以上的郵件。 系統管理員無法覆寫此區塊。

       - 名為**User 限制寄件者傳送電子郵件**的活動警示會通知系統管理員（透過電子郵件和 [**查看提醒**] 頁面）。

       - **當寄件者因**在原則中傳送輸出垃圾郵件設定而遭到封鎖時，在 [通知特定人員] 中指定的任何收件者也都會收到通知。

       - 在下一天之後，使用者將無法再傳送任何郵件到以 UTC 時間為基礎。 系統管理員無法覆寫此區塊。

     - **限制使用者傳送郵件**：已傳送電子郵件通知，使用者會新增至安全性 & 合規性中心內的 **[受限制的使用者]<https://sip.protection.office.com/restrictedusers> **入口網站，直到系統管理員將其從**受限使用者**入口網站中移除之後，使用者才會傳送電子郵件。系統管理員從清單中移除使用者後，該天的使用者將不會受到限制。 如需相關指示，請參閱[在傳送垃圾郵件後移除受限使用者入口網站中的使用者](removing-user-from-restricted-users-portal-after-spam.md)。

     - **無動作，只發出警示**：已傳送電子郵件通知。

6. 必備展開 [套用**至**] 區段，識別套用原則的內部寄件者。

    您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。 相同狀況或例外狀況或邏輯的多個值（例如， _ \<sender1\> _或_ \<sender2\>_）。 不同的條件或例外情況_ \<使用和邏輯（例如，\> _ _ \<group\>1 的成員_）。

    最簡單的方法是按一下 [新增條件]**** 三次，查看所有可用的條件。 您可以按一下 ![移除按鈕](../../media/scc-remove-icon.png)移除您不想要設定的條件。

    - **寄件者網域為**：指定 Office 365 中一或多個已設定公認的網域中的寄件者。 按一下 [新增標籤]**** 方塊，可查看並選取網域。 如果有不止一個網域，再次按一下 [新增標籤]**** 方塊可選取其他網域。

    - **寄件者為**：指定組織中的一或多個使用者。 在 [新增標籤]**** 內按一下，然後開始輸入以篩選清單。 再次按一下 [**新增標記**] 方塊，以選取其他寄件者。

    - **寄件者隸屬于**：指定組織中的一或多個群組。 在 [新增標籤]**** 內按一下，然後開始輸入以篩選清單。 再次按一下 [**新增標記**] 方塊，以選取其他寄件者。

    - **除了**：若要為規則新增例外情況，按一下 [新增條件]**** 三次，即可查看所有可用的例外。 設定和行為就像是條件。

7. 完成後，按一下 [儲存]****。

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>使用安全性 & 規範中心來查看輸出垃圾郵件原則

1. 在安全性與合規性中心，移至 [威脅管理]**** \> [原則]**** \> [反垃圾郵件]****。

2. 在 [**反垃圾郵件設定**] 頁面上![，按一下](../../media/scc-expand-icon.png) [展開圖示] 以展開輸出垃圾郵件原則：

   - 名為 [**輸出垃圾郵件篩選原則**] 的預設原則。

   - 您在 [**類型**] 欄中的值為**自訂輸出垃圾郵件原則**時所建立的自訂原則。

3. 原則設定會顯示在已展開的原則詳細資料中，您也可以按一下 [**編輯原則**]。

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>使用安全性 & 規範中心來修改輸出垃圾郵件原則

1. 在安全性與合規性中心，移至 [威脅管理]**** \> [原則]**** \> [反垃圾郵件]****。

2. 在 [**反垃圾郵件設定**] 頁面上![，按一下](../../media/scc-expand-icon.png) [展開圖示] 以展開輸出垃圾郵件原則：

   - 名為 [**輸出垃圾郵件篩選原則**] 的預設原則。

   - 您在 [**類型**] 欄中的值為**自訂輸出垃圾郵件原則**時所建立的自訂原則。

3. 按一下 [編輯原則]****。

若為自訂輸出垃圾郵件原則，快顯視窗中所述的可用設定與 [[使用安全性 & 規範中心建立輸出垃圾郵件原則](#use-the-security--compliance-center-to-create-outbound-spam-policies)] 區段中所述的設定相同。

針對名為「**輸出垃圾郵件篩選原則**」的預設輸出垃圾郵件原則，[套用**至**] 區段不可用（原則套用至 [所有人]），您無法重新命名原則。

若要啟用或停用原則、設定原則優先順序順序、或設定使用者隔離通知，請參閱下列各節。

### <a name="enable-or-disable-outbound-spam-policies"></a>啟用或停用輸出垃圾郵件原則

1. 在安全性與合規性中心，移至 [威脅管理]**** \> [原則]**** \> [反垃圾郵件]****。

2. 在 [**反垃圾郵件設定**] 頁面上![，按一下](../../media/scc-expand-icon.png) [展開圖示]，展開您建立的自訂原則（[**類型**] 欄中的值為 [**自訂輸出垃圾郵件原則**]）。

3. 在隨即出現的展開的原則詳細資料中，請注意**開啟**資料行的值。

   將切換開關向左移動以停用原則： ![關閉](../../media/scc-toggle-off.png)

   將切換開關向右移動以啟用原則： ![開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

您無法停用預設輸出垃圾郵件原則。

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>設定自訂輸出垃圾郵件原則的優先順序

根據預設，輸出垃圾郵件原則的優先順序會根據建立的順序而定（較舊的原則的優先順序較舊）。 較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。 不會有兩個原則的優先順序相同。

自訂輸出垃圾郵件原則會以處理的順序顯示（第一個原則的**Priority**值為0）。 預設的輸出垃圾郵件原則（名為**輸出垃圾郵件篩選原則**）的優先順序值是**最低**的，您無法變更。

若要變更原則的優先順序，請在清單中將原則上移或下移 (您無法在安全性與合規性中心直接修改 [優先順序]**** 數字)。

1. 在安全性與合規性中心，移至 [威脅管理]**** \> [原則]**** \> [反垃圾郵件]****。

2. 在 [**反垃圾郵件設定**] 頁面上，尋找 [**類型**] 欄中的值為 [**自訂輸出垃圾郵件原則**] 的原則。 請注意 [優先順序]**** 資料行中的值：

   - 具有最高優先順序的自訂輸出垃圾郵件原則， ![具有值向](../../media/ITPro-EAC-DownArrowIcon.png)中箭號圖示**0**。

   - 具有最低優先順序的自訂輸出垃圾郵件原則具有值![向上箭號](../../media/ITPro-EAC-UpArrowIcon.png) **n** （ ![例如向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png) **3**）。

   - 如果您有三個或多個自訂輸出垃圾郵件原則，則最高和最低優先順序![之間的原則](../../media/ITPro-EAC-UpArrowIcon.png)![會具有值](../../media/ITPro-EAC-DownArrowIcon.png)向上箭號圖示向下箭號](../../media/ITPro-EAC-UpArrowIcon.png)![圖示**n** （例如， ![向上鍵圖示向下箭號圖示](../../media/ITPro-EAC-DownArrowIcon.png) **2**）。

3. 按一下 ![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png) 或 ![向下箭號圖示](../../media/ITPro-EAC-DownArrowIcon.png) 在 [優先順序] 清單中，將自訂的輸出垃圾郵件原則上移或下移。

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>使用安全性 & 規範中心移除輸出垃圾郵件原則

1. 在安全性與合規性中心，移至 [威脅管理]**** \> [原則]**** \> [反垃圾郵件]****。

2. 在 [**反垃圾郵件設定**] 頁面上![，按一下](../../media/scc-expand-icon.png) [展開圖示] 以展開您要刪除的自訂原則（[**類型**] 欄是**自訂輸出垃圾郵件原則**）。

3. 在隨即出現的展開原則詳細資料中，按一下 [刪除原則]****。

4. 在隨即出現的警告對話方塊中，按一下 [是]****。

您無法移除預設原則。

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-outbound-spam-policies"></a>使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 設定輸出垃圾郵件原則

### <a name="use-powershell-to-create-outbound-spam-policies"></a>使用 PowerShell 建立輸出垃圾郵件原則

在 PowerShell 中建立輸出垃圾郵件原則的程式分為兩個步驟：

1. 建立輸出垃圾郵件篩選原則。

2. 建立輸出垃圾郵件篩選規則，以指定套用規則的輸出垃圾郵件篩選原則。

 **附註**：

- 您可以建立新的輸出垃圾郵件篩選規則，並將現有的未關聯輸出垃圾郵件篩選原則指派給它。 輸出垃圾郵件篩選規則無法與一個以上的輸出垃圾郵件篩選原則相關聯。

- 您可以在 PowerShell 中的新外寄垃圾郵件篩選原則上設定下列設定，而這些原則在安全性 & 規範中心內無法使用，直到您建立原則為止：

  - 建立新原則為停用（在**HostedOutboundSpamFilterRule** Cmdlet 上_啟用_ `$false` ）。

  - 設定在**HostedOutboundSpamFilterRule 指令程式**建立時的原則優先順序（_優先權_ _ \<編號\>_）。

- 在您將原則指派給垃圾郵件篩選規則之前，您在 PowerShell 中所建立的新輸出垃圾郵件篩選原則不會顯示在安全性 & 規範中心。

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>步驟1：使用 PowerShell 來建立輸出垃圾郵件篩選原則

若要建立輸出垃圾郵件篩選原則，請使用下列語法：

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

此範例會建立名為 Contoso 主管的新輸出垃圾郵件篩選原則，並提供下列設定：

- 收件者速率限制限制為預設值較小的值。 如需詳細資訊，請參閱[在 Microsoft 365 選項](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)中傳送限制。

- 達到其中一個限制之後，使用者就無法傳送郵件。

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

如需詳細的語法及參數資訊，請參閱[HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy)。

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>步驟2：使用 PowerShell 建立輸出垃圾郵件篩選規則

若要建立輸出垃圾郵件篩選規則，請使用下列語法：

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

此範例會使用下列設定建立名為 Contoso 主管的新輸出垃圾郵件篩選規則：

- 名為 Contoso 主管的輸出垃圾郵件篩選原則與規則相關聯。

- 此規則會套用至名為 ContosoExecutives Group 的群組成員。

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

如需詳細的語法及參數資訊，請參閱[HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule)。

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

如需詳細的語法及參數資訊，請參閱[Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>使用 PowerShell 來查看輸出垃圾郵件篩選規則

若要查看現有的輸出垃圾郵件篩選規則，請使用下列語法：

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
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

如需詳細的語法及參數資訊，請參閱[HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>使用 PowerShell 修改輸出垃圾郵件篩選原則

當您在本主題稍早的[步驟1：使用 PowerShell 建立外寄垃圾郵件篩選原則](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy)一節所述，在 PowerShell 中修改惡意程式碼篩選原則時，就可以使用相同設定。

**附注**：您無法重新命名外寄垃圾郵件篩選原則（ **Set-HostedOutboundSpamFilterPolicy** Cmdlet 沒有_Name_參數）。 當您在安全性 & 合規性中心重新命名輸出垃圾郵件原則時，您只是重新命名輸出垃圾郵件篩選_規則_。

若要修改輸出垃圾郵件篩選原則，請使用下列語法：

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱[Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>使用 PowerShell 修改輸出垃圾郵件篩選規則

當您在 PowerShell 中修改外寄垃圾郵件篩選規則時，唯一可用的設定是_Enabled_參數，可讓您建立已停用的規則。 若要啟用或停用現有的輸出垃圾郵件篩選規則，請參閱下一節。

否則，當您在 PowerShell 中修改外寄垃圾郵件篩選規則時，不會有其他設定可供使用。 當您建立一個規則時，如本主題稍早的[步驟2：使用 PowerShell 以建立輸出垃圾郵件篩選規則](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule)區段所述，您可以使用相同的設定。

若要修改輸出垃圾郵件篩選規則，請使用下列語法：

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱[Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>使用 PowerShell 來啟用或停用輸出垃圾郵件篩選規則

啟用或停用 PowerShell 中的外寄垃圾郵件篩選規則，可啟用或停用整個輸出垃圾郵件原則（輸出垃圾郵件篩選規則和指派的外寄垃圾郵件篩選器原則）。 您無法啟用或停用預設輸出垃圾郵件原則（永遠都是套用至所有收件者）。

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

如需詳細的語法及參數資訊，請參閱[Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule)和[Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule)。

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

- 若要在建立新規則時設定其優先順序，請改用**HostedOutboundSpamFilterRule** Cmdlet 上的_priority_參數。

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

如需詳細的語法及參數資訊，請參閱[Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy)。

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

如需詳細的語法及參數資訊，請參閱[Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule)。

## <a name="for-more-information"></a>如需詳細資訊

[從 [受限使用者] 入口網站中移除封鎖的使用者](removing-user-from-restricted-users-portal-after-spam.md)

[輸出郵件的高風險傳遞集區](high-risk-delivery-pool-for-outbound-messages.md)

[反垃圾郵件保護常見問題集](anti-spam-protection-faq.md)
