---
title: 設定垃圾郵件篩選原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 系統管理員可以了解如何在 Exchange Online Protection (EOP) 中檢視、建立、修改及刪除反垃圾郵件原則。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2214baa1c205d4e0f634c5a07f4d55522d2ad6b1
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822018"
---
# <a name="configure-anti-spam-policies-in-eop"></a>在 EOP 中設定反垃圾郵件原則

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在擁有 Exchange Online 信箱的 Microsoft 365 組織中或是沒有 Exchange Online 信箱的獨立 Exchange Online Protection (EOP) 組織中，EOP 會自動保護內送電子郵件，防止垃圾郵件。 EOP 使用反垃圾郵件原則 (也稱為垃圾郵件過篩選原則或內容篩選原則)，作為貴組織全面防範垃圾郵件的一環。 如需詳細資訊，請參閱[反垃圾郵件保護](anti-spam-protection.md)。

系統管理員可以檢視、編輯、設定 (但不能刪除) 預設的反垃圾郵件原則。 若要提高精確性，您也可以建立自訂的反垃圾郵件原則，並套用至貴組織中的特定使用者、群組或網域。 自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。

您可以在 Microsoft 365 安全性中心或在 PowerShell (在 Exchange Online 中有信箱的組織中為適用於 Microsoft 365 的 Exchange Online PowerShell；在沒有 Exchange Online 信箱的組織中則為獨立 EOP PowerShell) 中設定反垃圾郵件原則。

反垃圾郵件原則的基本元素有：

- **垃圾郵件篩選原則**：指定垃圾郵件篩選裁決的動作和通知選項。
- **垃圾郵件篩選規則**：指定垃圾郵件篩選原則的優先順序及收件者篩選器 (原則套用對象)。

當您在安全性中心管理反垃圾郵件原則時，上述兩個元素的差異不大：

- 當您建立ㄧ項反垃圾郵件原則時，其實只是以相同的名稱，同時建立垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則。
- 當您修改反垃圾郵件原則時，與名稱、優先順序、已啟用或已停用、收件者篩選相關的設定皆會修改垃圾郵件篩選規則。 所有其他設定都會修改相關聯的垃圾郵件篩選原則。
- 當您移除反垃圾郵件原則時，也會一併移除垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則。

在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，您可以個別管理原則和規則。 如需其他更多資訊，請參照本文章稍後的 [「使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定反垃圾郵件原則」](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) 章節。

每個組織都有一個名為「預設」的內建反垃圾郵件原則，且具有下列屬性：

- 即使沒有與此原則相關聯的垃圾郵件篩選規則 (收件者篩選器)，此原則仍會套用至組織中的所有收件者。
- 此原則的自訂優先順序值是 **最低的**，表示您無法進行任何修改（此原則ㄧ律到最後才會套用）。 任何您建立的自訂原則皆具有較高的優先順序。
- 此原則是預設的 (**IsDefault** 屬性具有`True`值)，且您無法刪除此項預設原則。

若要提高垃圾郵件篩選的效率，您可以建立自訂反垃圾郵件原則，以更嚴格的設定套用到特定使用者或使用者群組。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您可以開啟安全性中心，網址為 <https://security.microsoft.com>。 若要直接移至 [反垃圾郵件原則 **]** 頁面，請使用 <https://security.microsoft.com/antispam>。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：
  - 若要新增、修改、刪除反垃圾郵件原則，您必須是 **組織管理** 或 **安全性系統管理員** 角色群組的成員。
  - 若要唯讀存取反垃圾郵件原則，您必須是 **全域讀取者** 或 **安全性讀取者** 角色群組的成員。

  如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。

  **附註**：

  - 在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。

- 如需反垃圾郵件原則的建議設定，請參閱 [EOP 反垃圾郵件原則設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。

## <a name="use-the-security-center-to-create-anti-spam-policies"></a>使用安全性中心來建立反垃圾郵件原則

在安全性中心建立自訂的反垃圾郵件原則時，是同時建立垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則，且為兩者使用相同的名稱。

1. 在安全性中心，移至 **電子郵件與共同作業** \> **原則與規則** \> **威脅原則** \> **原則** 選擇\> **反垃圾郵件**。

2. 在 **反垃圾郵件原則** 頁面，按一下![建立圖示](../../media/m365-cc-sc-create-icon.png) **建立原則**，然後從下拉式選單中選取 **輸入**。

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

5. 在 [大量電子郵件閾值與垃圾郵件屬性 **]** 頁面上，設定下列設定：

   - **大量電子郵件閾值**：針對您在下一個頁面上設定、會觸發 **大量** 垃圾郵件篩選決策指定動作的訊息，指定大量抱怨層級 (BCL)，(大於、不大於或等於指定的值)。 較高的值表示不太理想的郵件 (更可能像是垃圾郵件)。 預設值為 7。 如需詳細資訊，請參閱 [EOP 中的大量抱怨層級 (BCL)](bulk-complaint-level-values.md) 和[垃圾電子郵件與大量電子郵件之間有何不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)。

     根據預設，PowerShell 只會將反垃圾郵件原則中的 MarkAsSpamBulkMail 設定為 `On`。 此設定會大幅影響 **大量** 篩選決策的結果：

     - **_MarkAsSpamBulkMail_ 為 On**：大於閾值的 BCL 會轉換成 SCL 6 (對應到 **垃圾郵件** 篩選決策)，然後對郵件採取 **大量** 篩選決策的動作。
     - **_MarkAsSpamBulkMail_ 為 Off**：郵件會加上 BCL 戳記，但 _不會_ 對 **大量** 篩選決策執行任何動作。 實際上，BCL 閾值和 **大量** 篩選決策動作並不相關。

   - **增加垃圾郵件分數**、**標記為垃圾郵件**<sup>\*</sup>和 **測試模式**：包含預設關閉的進階垃圾郵件篩選 (ASF) 設定。 我們正逐漸淘汰 ASF 設定，其功能正併入篩選堆疊的其他部分。 建議您將反垃圾郵件原則中的所有 ASF 設定關閉。

     如需有關這些設定的詳細資訊，請參閱 [EOP 中的進階垃圾郵件篩選設定](advanced-spam-filtering-asf-options.md)。

      <sup>\*</sup> [包含特定語言 **]** 和 [來自這些國家/地區 **]** 不屬於 ASF 設定的一部分。

   - **包含特定語言**：按一下方塊，然後從下拉式清單中選取 [**開啟**] 或 [**關閉**]。 如果您將它開啟，會顯示一個方塊。 開始在方塊中輸入語言的名稱。 已篩選的支援語言清單將會顯示。 當您找到所需語言時，請選取該語言。 視需要重複此步驟多次。 若要移除現有的值，請按一下值旁邊的 ![移除圖示](../../media/m365-cc-sc-remove-selection-icon.png)。

   - **來自這些國家/地區**：按一下方塊，然後從下拉式清單中選取 [*開啟*]* 或 [**關閉**]。 如果您將它開啟，會顯示一個方塊。 開始在方塊中輸入國家/地區的名稱。 已篩選的支援國家/地區清單將會顯示。 當您找到您要尋找的國家/地區時，請選取它。 視需要重複此步驟多次。 若要移除現有的值，請按一下值旁邊的 ![移除圖示](../../media/m365-cc-sc-remove-selection-icon.png)。

   完成後，按 [下一步 **]**。

6. 在顯示的 [動作 **]** 頁面上，設定下列設定：

   - **郵件動作**：根據下列垃圾郵件篩選決策，來選取或檢閱要對郵件採取的動作：
     - **垃圾郵件**
     - **高信賴度的垃圾郵件**
     - **網路釣魚**
     - **高信賴度網路釣魚**
     - **大量**

     下表說明垃圾郵件篩選裁決可採取的動作。

     - 核取記號 ( ![核取記號](../../media/checkmark.png)) 表示可採取的動作 (並非所有的決策皆可採取所有動作)。
     - 核取記號之後有星號 (<sup>\*</sup>) 表示垃圾郵件篩選裁決的預設動作。

     <br>

     ****

     |動作|垃圾郵件|高<br>信賴度<br>垃圾郵件|網路釣魚|高<br>信賴度<br>網路釣魚|大量|
     |---|:---:|:---:|:---:|:---:|:---:|
     |**將郵件移至 [垃圾郵件] 資料夾**：郵件會傳送至信箱，並移至 [垃圾郵件] 資料夾。<sup>1</sup>|![核取記號](../../media/checkmark.png)<sup>\*</sup>|![核取記號](../../media/checkmark.png)<sup>\*</sup>|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)<sup>\*</sup>|
     |**新增 X 標頭**：在郵件標頭中新增 X 標頭，並將郵件傳送到信箱。 <p> 您稍後可以在 [新增此 X 標頭文字] 方塊中輸入 X 標頭欄位的名稱 (不是值)。 <p> 裁決為 **垃圾郵件** 和 **高信賴度垃圾郵件** 的郵件會移至 [垃圾郵件] 資料夾。<sup>1,2</sup>|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)||![核取記號](../../media/checkmark.png)<sup>\*</sup>|
     |**在主旨列前加上文字**：新增文字至郵件主旨列的開頭。 郵件會傳送至信箱，並移至 [垃圾郵件] 資料夾。<sup>1,2</sup> <p> 您稍後可以在 [在主旨列前加上此文字] 方塊中輸入文字。|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)||![核取記號](../../media/checkmark.png)|
     |**將郵件重新導向至電子郵件地址**：將郵件傳送給其他收件者，而不是預定收件者。 <p> 您稍後可以在 [重新導向到這個電子郵件地址] 方塊中指定收件者。|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|
     |**刪除郵件**：刪除整封郵件，包括所有附件。|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)||![核取記號](../../media/checkmark.png)|
     |**隔離郵件**：將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> 您稍後可以在 [隔離] 方塊中指定郵件要在隔離區保留多久。|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)<sup>\*</sup>|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|
     |**無動作**|||||![核取記號](../../media/checkmark.png)|
     |

     > <sup>1</sup> 在 Exchange Online 中，如果信箱已啟用垃圾郵件規則 (預設為啟用)，郵件會移至 [垃圾郵件] 資料夾。 如需詳細資訊，請參閱[設定 Exchange Online 信箱的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。
     >
     > 在 EOP 會保護內部部署 Exchange 信箱的混合式環境中，您必須在內部部署 Exchange 中設定郵件流程規則 (又稱為傳輸規則) 以轉譯 EOP 垃圾郵件篩選裁決，這樣垃圾郵件規則才可以將郵件移至 [垃圾郵件] 資料夾。 如需詳細資訊，請參閱[設定 EOP 以將垃圾郵件傳送到混合式環境中的垃圾郵件資料夾](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)。
     >
     > <sup>2</sup> 您可以使用此值做為郵件流程規則的條件，以便篩選或傳送郵件。

   - **在此天數內保留隔離的垃圾郵件**：指定當您選取 **隔離郵件** 做為垃圾郵件篩選決策的動作時，郵件將存放在隔離中要多久的時間。 時間到了之後，就會刪除郵件。 預設值是 30 天。 有效值是從 1 到 30 天。 如需隔離的相關資訊，請參閱下列主題：

     - [EOP 中的隔離郵件](quarantine-email-messages.md)
     - [在 EOP 中管理隔離的郵件與檔案](manage-quarantined-messages-and-files.md)
     - [在 EOP 中尋找及釋出隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)

   - **新增此 X 標題文字**：只有當您選取 [新增 X 標頭] 做為垃圾郵件篩選裁決的動作時，才會有此方塊，且是必要的設定。 您指定的值是郵件標頭「名稱」，會新增到郵件標頭中。 標題欄位的「值」一律是 `This message appears to be spam`。

     長度上限為 255 個字元，且值不能包含空格或冒號 (:)。

     例如，如果輸入 `X-This-is-my-custom-header` 值，則新增到郵件的 X 標頭為 `X-This-is-my-custom-header: This message appears to be spam.`。

     如果您輸入的值包含空格或冒號 (:)，系統會忽略您輸入的值，並在郵件中新增預設的 X 標頭 (`X-This-Is-Spam: This message appears to be spam.`)。

   - **在主旨列前加上此文字**：只有當您選取 [在主旨列前加上文字] 做為垃圾郵件篩選裁決的動作時，才會有此方塊，且是必要的設定。 輸入要新增至郵件主旨列開頭的文字。

   - **重新導向到這個電子郵件地址**：只有當您選取 [將郵件重新導向至電子郵件地址] 做為垃圾郵件篩選裁決的動作時，才會有此方塊，且是必要的設定。 輸入您要遞送郵件的電子郵件地址。 您可以輸入多個值並以分號 (;) 分隔。

   - **啟用安全提示**：預設會啟用安全提示，但您可以清除核取方塊加以停用。 如需有關安全性提示的詳細資訊，請參閱[電子郵件的安全提示](safety-tips-in-office-365.md)。

   - **啟用零時差自動清除 (ZAP)**：ZAP 會偵測傳送到 Exchange Online 信箱的郵件，並採取行動。 如需詳細資訊，請參閱[零時差自動清除 - 防範垃圾郵件和惡意程式碼](zero-hour-auto-purge.md)。

     ZAP 預設為開啟。 當 ZAP 開啟時，可以使用下列設定：

     - **針對網路釣魚郵件啟用 ZAP**：預設會啟用 ZAP 以偵測網路釣魚，但您可以清除核取方塊加以停用。
     - **針對垃圾郵件啟用 ZAP**：預設會啟用 ZAP 以偵測垃圾郵件，但您可以清除核取方塊加以停用。

   - **啟用使用者垃圾郵件通知**：如需詳細資訊，請參閱本主題稍後的 [設定使用者垃圾郵件通知](#configure-end-user-spam-notifications)一節。

   完成後，按 [下一步 **]**。

7. 在顯示的 [允許與封鎖清單 **]** 飛出視窗上，您可以根據允許略過垃圾郵件篩選的電子郵件地址或電子郵件網域來設定郵件寄件者。

   在 [允許 **]** 區段，您可以設定允許的寄件者和允許的網域。 在 [封鎖 **]** 區段，您可以新增封鎖的寄件者和封鎖的網域。

   > [!IMPORTANT]
   >
   > 在將網域新增到允許的網域清單之前，請仔細考慮。 如需詳細資訊，請參閱[在 EOP 中建立安全寄件者清單](create-safe-sender-lists-in-office-365.md)。
   >
   > 絕對不要將您自己的[公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)或一般網域 (例如 microsoft.com 或 office.com) 新增到允許的網域清單中。 如果允許這些網域略過垃圾郵件篩選，則會允許攻擊者輕鬆地將電子郵件傳送至您的組織。
   >
   > 將網域新增到封鎖的網域清單以手動封鎖網域並不危險，但會增加您的管理工作量。 如需詳細資訊，請參閱[在 EOP 中建立封鎖寄件者清單](create-block-sender-lists-in-office-365.md)。
   >
   > 有時我們的篩選器會錯過郵件、您不同意篩選決策，或者我們的系統需要時間才能跟上。 在這些情況下，允許清單和封鎖清單可用於取代目前的篩選決策。 但是，您應該謹慎且暫時使用這些清單：冗長的清單可能會變得無法管理，而我們的篩選堆疊應該執行它預期該執行的工作。 如果您要將允許的網域保留一段時間，您應該告訴寄件者驗證其網域是否經過驗證，如果未經驗證，則設為 DMARC 拒絕。

   將項目新增到任何清單的步驟都相同：

   1. 按一下要設定的清單連結：
      - **允許** \> **寄件者**：按一下 [管理 (nn) 寄件者 **]**。
      - **允許** \> **網域**：按一下 [允許網域 **]**。
      - **封鎖** \> **寄件者**：按一下 [管理 (nn) 寄件者 **]**。
      - **封鎖** \> **網域**：按一下 [封鎖網域 **]**。

   2. 在顯示的飛出視窗中，執行下列步驟：
      1. 按一下 ![建立圖示](../../media/m365-cc-sc-create-icon.png) [新增寄件者 **]** 或 [新增網域 **]**。
      2. 在 [新增寄件者 **]** 或 [新增網域 **]** 飛出視窗中，於 [寄件者 **]** 方塊或 [網域 **]** 方塊中輸入寄件者的電子郵件地址。 當您輸入時，值會顯示在方塊下方。 輸入完電子郵件地址或網域後，請選取方塊下方的值。
      3. 視需要重複先前的步驟多次。 若要移除現有的值，請按一下 ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) 值旁邊的 [移除]。

      完成後，請按一下 [新增寄件者 **]** 或 [新增網域 **]**。

      回到主要飛出頁面，頁面上會列出您新增的寄件者或網域。 若要從此頁面移除項目，請執行下列步驟：

      1. 從清單中選取一或多個項目。 您也可以使用 [搜尋 **]** 方塊來尋找清單中的值。
      2. 選取至少一個項目後，刪除圖示 ![[刪除] 圖示](../../media/m365-cc-sc-delete-icon.png) 隨即顯示。
      3. 按一下 [刪除] 圖示 ![[刪除] 圖示](../../media/m365-cc-sc-delete-icon.png) 以移除選取的項目。

      完成後，按一下 [完成 **]**。

      回到 [允許與封鎖清單 **]** 頁面，提示時請按 [下一步 **]** 以繼續。

8. 在顯示的 [檢閱 **]** 頁面上，檢閱您的設定。 您可以在每個區段中選取 [編輯 **]**，以修改該區段內的設定。 或者，您可以按一下 [上一步] 或在精靈中選取特定頁面。

   完成時，按一下 [建立 **]**。

9. 在顯示的確認頁面上，按一下 [完成 **]**。

## <a name="use-the-security-center-to-view-anti-spam-policies"></a>使用安全性中心來檢視反垃圾郵件原則

1. 在安全性中心，移至 **電子郵件與共同作業** \> **原則與規則** \> **威脅原則** \> **原則** 選擇\> **反垃圾郵件**。

2. 在 [**反垃圾郵件原則**] 頁面上，尋找下列其中一個值：
   - [類型 **]** 值為 [自訂反垃圾郵件原則 **]**
   - [名稱 **]** 值為 [反垃圾郵件輸入原則 (預設值)**]**

   反垃圾郵件原則清單中會顯示下列屬性：

   - **名稱**
   - **狀態**
   - **優先順序**
   - **類型**

3. 當您按一下名稱以選取反垃圾郵件原則時，該原則設定會顯示在飛出視窗中。

## <a name="use-the-security-center-to-modify-anti-spam-policies"></a>使用安全性中心來修改反垃圾郵件原則

1. 在安全性中心，移至 **電子郵件與共同作業** \> **原則與規則** \> **威脅原則** \> **原則** 選擇\> **反垃圾郵件**。

2. 在 [反垃圾郵件原則 **]** 頁面上，按一下清單中的名稱，以從中選取反垃圾郵件原則：
   - 您建立的自訂原則的 [類型 **]** 資料行中的值是 [自訂的反垃圾郵件原則 **]**。
   - 預設原則名為 **反垃圾郵件輸入原則 (預設值)**。

3. 在顯示的原則詳細資料飛出視窗中，在每個區段中選取 [編輯 **]**，以修改該區段內的設定。 如需設定的詳細資訊，請參閱本文章中的[使用安全性中心來建立反垃圾郵件原則](#use-the-security-center-to-create-anti-spam-policies)一節。

   若是預設反垃圾郵件原則，則無法使用 [套用至 **]** 區段 (原則會套用至每個人)，而且您無法重新命名原則。

若要啟用或停用原則、設定原則優先順序順序、或設定使用者隔離通知，請參閱下列各節。

### <a name="enable-or-disable-anti-spam-policies"></a>啟用或停用反垃圾郵件原則

您無法停用預設的反垃圾郵件原則。

1. 在安全性中心，移至 **電子郵件與共同作業** \> **原則與規則** \> **威脅原則** \> **原則** 選擇\> **反垃圾郵件**。

2. 在 [反垃圾郵件原則 **]** 頁面上，按一下名稱以從清單中選取具有 [類型值 **]** 為 [自訂反垃圾郵件 **]** 的規則。

3. 在顯示的原則詳細資料飛出視窗頂端，您會看到下列其中一個值：
   - **原則關閉**：若要開啟原則，請按一下 ![開啟圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [開啟 **]**。
   - **原則開啟**：若要關閉原則，請按一下 ![關閉圖示](../../media/m365-cc-sc-turn-on-off-icon.png) [關閉 **]**。

4. 在顯示的確認對話方塊中，按一下 [開啟 **]** 或 [關閉 **]**。

5. 按一下原則詳細資料飛出視窗中的 [關閉 **]**。

回到主要原則頁面，原則的 [狀態 **]** 值將會是 [開啟 **]** 或 [關閉 **]**。

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>設定自訂反垃圾郵件原則的優先順序

根據預設，系統是根據反垃圾郵件原則的建立順序給予優先順序 (較新原則的優先順序比較舊原則的優先順序低)。 較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。 不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。

若要變更原則的優先順序，請在原則內容中按一下 [增加優先順序 **]** 或 [降低優先順序 **]** (您無法在安全性中心直接修改 [優先順序 **]** 編號)。 只有在您有多個原則時，變更原則的優先順序才有意義。

 **附註**：

- 在安全性中心，您只能在建立反垃圾郵件原則後變更它的優先順序。 在 PowerShell 中，您可以在建立垃圾郵件篩選規則時覆寫預設優先順序 (這會影響現有規則的優先順序)。
- 反垃圾郵件原則會以其顯示的順序處理 (第一個原則的 **優先順序** 值為 0)。 預設反垃圾郵件原則的優先順序值為 **最低**，因此無法變更它。

1. 在安全性中心，移至 **電子郵件與共同作業** \> **原則與規則** \> **威脅原則** \> **原則** 選擇\> **反垃圾郵件**。

2. 在 [反垃圾郵件原則 **]** 頁面上，按一下名稱以從清單中選取具有 [類型值 **]** 為 [自訂反垃圾郵件 **]** 的規則。

3. 在顯示的原則詳細資料飛出視窗的頂端，根據目前的優先順序值和自訂原則數目，您會看到 [增加優先順序 **]** 或 [降低優先順序 **]**：
   - [優先順序 **]** 值為 **0** 的反垃圾郵件原則只有 [降低優先順序 **]** 選項可用。
   - 具有最低 [優先順序 **]** 值為 (例如 **3**) 的反垃圾郵件原則只有 [增加優先順序 **]** 選項可用。
   - 如果您有三個或多個反垃圾郵件原則，則最高與最低優先順序值之間的原則，其 [增加優先順序 **]** 和 [降低優先順序 **]** 選項會同時可用。

   按一下 ![增加優先順序圖示](../../media/m365-cc-sc-increase-icon.png) [增加優先順序 **]** 或 ![降低優先順序圖示](../../media/m365-cc-sc-decrease-icon.png) [降低優先順序 **]** 以變更 [優先順序 **]** 值。

4. 完成後，請按一下原則詳細資料飛出視窗中的 [關閉 **]**。

### <a name="configure-end-user-spam-notifications"></a>設定使用者垃圾郵件通知

當垃圾郵件篩選裁決要隔離郵件時，您可以設定使用者垃圾郵件通知，讓收件者知道寄給他們的郵件發生什麼事。 如需有關這些通知的詳細資訊，請參閱 [EOP 中的使用者垃圾郵件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。

1. 在安全性中心，移至 **電子郵件與共同作業** \> **原則與規則** \> **威脅原則** \> **原則** 選擇\> **反垃圾郵件**。

2. 在 [反垃圾郵件原則 **]** 頁面上，按一下清單中的名稱，以從中選取反垃圾郵件原則：
   - 您建立的自訂原則的 [類型 **]** 資料行中的值是 [自訂的反垃圾郵件原則 **]**。
   - 預設原則名為 **反垃圾郵件輸入原則 (預設值)**。

3. 在顯示的原則詳細資料飛出視窗中，按一下 [動作 **]** 中的 [編輯 **]**。 在顯示的 [動作 **]** 飛出視窗中，設定下列設定：

   - **啟用使用者垃圾郵件通知**：選取核取方塊以啟用通知，或清除核取方塊以停用通知。 選取核取方塊時，會顯示下列其他設定：

     - **傳送使用者垃圾郵件通知的頻率 (天)**：選取每隔幾天要傳送通知。 預設值是 3 天。 您可以輸入 1 到 15 天。

       在 24 小時期間內有 3 個使用者垃圾郵件通知週期，從下列時間開始：01:00 UTC、08:00 UTC 和 16:00 UTC。

       > [!NOTE]
       > 如果我們錯過了上一個週期的通知，後續週期會推播通知。 如此可能會在同一天內呈現多個通知。

     - **語言**：按一下下拉式清單並從中選取可用的語言。 預設值為 **[預設]**，也就是英文。

   完成後，按一下 [儲存]。

4. 回到原則詳細資料飛出視窗，按一下 [關閉 **]**。

## <a name="use-the-security-center-to-remove-custom-anti-spam-policies"></a>使用安全性中心來移除自訂的反垃圾郵件原則

若您使用安全性中心來移除自訂的反垃圾郵件原則時，會同時刪除垃圾郵件篩選規則與對應的垃圾郵件篩選原則。您無法移除預設的反垃圾郵件原則。

1. 在安全性中心，移至 **電子郵件與共同作業** \> **原則與規則** \> **威脅原則** \> **原則** 選擇\> **反垃圾郵件**。

2. 在 [反垃圾郵件原則 **]** 頁面上，按一下名稱以從清單中選取具有 [類型值 **]** 為 [自訂反垃圾郵件 **]** 的規則。 在顯示的原則詳細資料飛出視窗頂端，按一下 ![更多動作圖示](../../media/m365-cc-sc-more-actions-icon.png) [其他動作 **]** \> ![刪除原則圖示](../../media/m365-cc-sc-delete-icon.png) [刪除原則 **]**。

3. 在顯示的確認對話方塊中，按一下 [是 **]**。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>使用 Exchange Online PowerShell 或獨立版 EOP PowerShell 來設定反垃圾郵件原則

如先前所述，反垃圾郵件原則是由垃圾郵件篩選原則和垃圾郵件篩選規則組成的。

在 Exchange Online PowerShell 或獨立版 EOP PowerShell 中，垃圾郵件篩選原則與垃圾郵件篩選規則之間的差異很明顯。 您使用 **\*-HostedContentFilterPolicy** Cmdlet 來管理垃圾郵件篩選原則，但使用 **\*-HostedContentFilterRule** Cmdlet 來管理垃圾郵件篩選規則。

- 在 PowerShell 中，您要先建立垃圾郵件篩選原則，然後再建立垃圾郵件篩選規則來識別將套用規則的原則。
- 在 PowerShell 中，您可以分開修改垃圾郵件篩選原則和垃圾郵件篩選規則中的設定。
- 當您移除 PowerShell 中的垃圾郵件篩選原則時，對應的垃圾郵件篩選規則不會自動移除，反之亦然。

下列反垃圾郵件原則設定僅適用於 PowerShell：

- MarkAsSpamBulkMail 參數預設是 `On`。 此設定的效果已在本文章前面的[使用安全性中心來建立本反垃圾郵件原則](#use-the-security-center-to-create-anti-spam-policies)章節中說明。

- 使用者垃圾郵件隔離通知的下列設定：
  - DownloadLink 參數，用於顯示或隱藏 Outlook 的垃圾郵件報告工具連結。
  - EndUserSpamNotificationCustomSubject 參數，您可以用來自訂通知的主旨列。

### <a name="use-powershell-to-create-anti-spam-policies"></a>使用 PowerShell 來建立反垃圾郵件原則

在 PowerShell 中建立反垃圾郵件原則需執行兩個步驟：

1. 建立垃圾郵件篩選原則。
2. 建立垃圾郵件選規則，此規則會指定要套用規則的垃圾郵件篩選原則。

 **附註**：

- 您可以建立新的垃圾郵件篩選規則，並對其指派未關聯的現有垃圾郵件篩選原則。 垃圾郵件篩選規則無法與多個垃圾郵件篩選原則相關聯。
- 您可以使用 PowerShell 對安全性中心中還沒有的新垃圾郵件篩選原則進行下列設定，直到您建立原則為止：
  - 建立「停用」的新原則 (在 **New-HostedContentFilterRule** Cmdlet 中啟用 `$false`)。
  - 在建立期間設定原則的優先順序 (在 **New-HostedContentFilterRule** Cmdlet 使用 _Priority_ _\<Number\>_)。

- 您在 PowerShell 中建立的新垃圾郵件篩選原則不會顯示在安全性中心，直到您將該原則指派到垃圾郵件篩選規則。

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>步驟 1：使用 PowerShell 建立垃圾郵件篩選原則

使用下列語法建立垃圾郵件篩選原則：

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

本範例會建立名為 Contoso Executives 的垃圾郵件篩選原則，並使用下列設定：

- 當垃圾郵件篩選裁決為垃圾郵件或高信賴度垃圾郵件時隔離郵件。
- BCL 7、8 或 9 會觸發大量垃圾郵件篩選決策的動作。

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

如需詳細的語法及參數資訊，請參閱 [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)。

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a>步驟 2：使用 PowerShell 建立垃圾郵件篩選規則

使用下列語法建立垃圾郵件篩選規則：

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

此範例使用下列設定來建立名為 Contoso Executives 的新垃圾郵件篩選規則：

- 名為 Contoso Executives 的垃圾郵件篩選原則會與此規則相關聯。
- 此規則會套用至名為 ContosoExecutives Group 的群組成員。

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

如需詳細的語法及參數資訊，請參閱 [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule)。

### <a name="use-powershell-to-view-spam-filter-policies"></a>使用 PowerShell 檢視垃圾郵件篩選原則

若要傳回所有垃圾郵件篩選原則的摘要清單，請執行下列命令：

```PowerShell
Get-HostedContentFilterPolicy
```

若要傳回特定垃圾郵件篩選原則的詳細資訊，請使用下列語法：

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

此範例會傳回名為 Executives 的垃圾郵件篩選原則的所有屬性值。

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

如需詳細的語法及參數資訊，請參閱 [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)。

### <a name="use-powershell-to-view-spam-filter-rules"></a>使用 PowerShell 檢視垃圾郵件篩選規則

若要檢視現有的垃圾郵件篩選規則，請使用下列語法：

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

若要傳回所有垃圾郵件篩選規則的摘要清單，請執行下列命令：

```PowerShell
Get-HostedContentFilterRule
```

若要依啟用或停用篩選規則的清單，請執行下列命令：

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

若要傳回特定垃圾郵件篩選規則的詳細資訊，請使用下列語法：

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

此範例會傳回名為 Contoso Executives 的垃圾郵件篩選規則的所有屬性值。

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

如需詳細的語法及參數資訊，請參閱 [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule)。

### <a name="use-powershell-to-modify-spam-filter-policies"></a>使用 PowerShell 修改垃圾郵件篩選原則

除了下列項目外，當您如同本文章前面的[步驟 1：使用 PowerShell 建立垃圾郵件篩選原則](#step-1-use-powershell-to-create-a-spam-filter-policy) 章節所述在 PowerShell 中修改垃圾郵件篩選原則時，會出現相同的設定。

- MakeDefault 可將指定的原則轉換成預設原則 (套用至每個人，一律 **最低** 優先順序，且無法刪除)，但只有當您在 PowerShell 中修改垃圾郵件篩選原則時才能使用。
- 您無法重新命名垃圾郵件篩選原則(**Set-hostedcontentfilterpolicy** Cmdlet 沒有 Name 參數)。 當您在安全性中心中重新命名反垃圾郵件原則時，只會重新命名垃圾郵件篩選 _規則_。

使用下列語法修改垃圾郵件篩選原則：

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱 [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)。

### <a name="use-powershell-to-modify-spam-filter-rules"></a>使用 PowerShell 修改垃圾郵件篩選規則

當您用 PowerShell 修改垃圾郵件篩選規則時，唯一無法使用的設定為 Enabled 參數 (可讓您建立停用的規則)。 若要啟用或停用現有的垃圾郵件篩選規則，請看下一節。

另一方面，當您用 PowerShell 修改垃圾郵件篩選規則時，將無法使用其他設定。 當您如同本文章前面的 [步驟 2：使用 PowerShell 建立垃圾郵件篩選規則](#step-2-use-powershell-to-create-a-spam-filter-rule) 章節所述建立規則時，會出現相同的設定。

使用下列語法修改垃圾郵件篩選規則：

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

此範例會將名為 `{Fabrikam Spam Filter}` 的現有垃圾郵件篩選規則重新命名。

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

如需詳細的語法及參數資訊，請參閱 [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule)。

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a>使用 PowerShell 來啟用或停用垃圾郵件篩選規則

使用 PowerShell 啟用或停用垃圾郵件篩選規則，可啟用或停用整個反垃圾郵件原則 (垃圾郵件篩選規則和指派的垃圾郵件篩選原則)。 您無法啟用或停用預設的反垃圾郵件原則 (一定一律會套用至所有收件者)。

若要在 PowerShell 中啟用或停用垃圾郵件篩選規則，請使用下列語法：

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

此範例會停用名為 Marketing Department 的垃圾郵件篩選規則。

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

此範例會啟用相同規則。

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

如需詳細的語法和參數資訊，請參閱 [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule) 和 [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule)。

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a>使用 PowerShell 設定垃圾郵件篩選規則的優先順序

您可以對規則設定的最高優先順序值為 0。 您可以設定的最低值則取決於規則的數目。 例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。 變更現有規則的優先順序會對其他規則造成階層式影響。 例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。

若要在 PowerShell 中設定垃圾郵件篩選規則的優先順序，請使用下列語法：

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。 優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

**附註**：

- 若要在建立新規則時設定其優先順序，請使用 **New-HostedContentFilterRule** Cmdlet 上的 Priority 參數。
- 預設垃圾郵件篩選原則沒有對應的垃圾郵件篩選規則，且一律有不可修改的優先順序值 **Lowest**。

### <a name="use-powershell-to-remove-spam-filter-policies"></a>使用 PowerShell 移除垃圾郵件篩選原則

當您使用 PowerShell 來移除垃圾郵件篩選原則時，對應的垃圾郵件篩選規則不會遭到移除。

若要在 PowerShell 中移除垃圾郵件篩選原則，請使用下列語法：

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

此範例會移除名為 Marketing Department 的垃圾郵件篩選原則。

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

如需詳細的語法及參數資訊，請參閱 [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy)。

### <a name="use-powershell-to-remove-spam-filter-rules"></a>使用 PowerShell 移除垃圾郵件篩選規則

當您使用 PowerShell 來移除垃圾郵件篩選規則時，對應的垃圾郵件篩選原則不會遭到移除。

若要在 PowerShell 中移除垃圾郵件篩選規則，請使用下列語法：

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

此範例會移除名為 Marketing Department 的垃圾郵件篩選規則。

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

如需詳細的語法及參數資訊，請參閱 [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>傳送 GTUBE 訊息以測試您的垃圾郵件原則設定

> [!NOTE]
> 只有當傳送 GTUBE 訊息的電子郵件組織無法掃描輸出的垃圾郵件時，這些步驟才有用。如果會掃描，則您無法傳送測試郵件。

未經同意大量電子郵件的一般測試 (GTUBE) 是文字字串，可放入測試郵件中，用於確認貴組織的反垃圾郵件設定。 GTUBE 訊息類似於歐洲反電腦病毒協會 (EICAR) 用於測試惡意程式碼設定的文字檔。

請在電子郵件中，將下列 GTUBE 文字放在單一行上，不加任何空格或換行：

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```
