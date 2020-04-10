---
title: 設定垃圾郵件篩選原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 基本的垃圾郵件篩選設定，包括識別為垃圾郵件所採取的選取郵件動作。
ms.openlocfilehash: f77a4f52e045c96a0538b140022ebee846cb1996
ms.sourcegitcommit: 8a88b7526e6a3a907f33a8567e0d25b74fe60d80
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43204097"
---
# <a name="configure-anti-spam-policies-in-office-365"></a>設定 Office 365 的反垃圾郵件原則

如果您是 Office 365 客戶並且有 Exchange Online 信箱，或是獨立版 Exchange Online Protection (EOP) 客戶且沒有 Exchange Online 信箱，則輸入的電子郵件會自動受到 EOP 的保護。 EOP 使用反垃圾郵件原則 (也稱為垃圾郵件過篩選原則或內容篩選原則)，作為貴組織全面防範垃圾郵件的一環。 如需詳細資訊，請參閱 [Office 365 中的反垃圾郵件保護](anti-spam-protection.md)。

系統管理員可以檢視、編輯、設定 (但不能刪除) 預設的反垃圾郵件原則。 若要提高精確性，您也可以建立自訂的反垃圾郵件原則，並套用至貴組織中的特定使用者、群組或網域。 自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (執行順序)。

您可以在 Office 365 安全性與合規性中心設定反垃圾郵件原則，或在 PowerShell 設定反垃圾郵件原則 (Office 365 客戶使用 Exchange Online PowerShell，獨立版 EOP 客戶使用 Exchange Online Protection PowerShell)。

## <a name="anti-spam-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a>Office 365 安全性與合規性中心和 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的反垃圾郵件原則

EOP 中反垃圾郵件原則的基本元素有：

- **垃圾郵件篩選原則**：指定垃圾郵件篩選裁決的動作和通知選項。

- **垃圾郵件篩選規則**：指定垃圾郵件篩選原則的優先順序及收件者篩選器 (原則套用對象)。

當您在安全性與合規性中心管理反垃圾郵件原則時，上述兩個元素的差異不大：

- 當您在安全性與合規性中心建立反垃圾郵件原則時，其實是同時在建立垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則，只是為兩者使用相同的名稱。

- 當您修改安全性與合規性中心中的反垃圾郵件原則時，與名稱、優先順序、已啟用或已停用、收件者篩選相關的設定皆會修改垃圾郵件篩選規則。 所有其他設定都會修改相關聯的垃圾郵件篩選原則。

- 當您從安全性與合規性中心移除反垃圾郵件原則時，垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則都會被移除。

在 Exchange Online PowerShell 或獨立版 Exchange Online Protection PowerShell 中，垃圾郵件篩選原則與垃圾郵件篩選規則之間的差異很明顯。 您使用 **\*-HostedContentFilterPolicy** Cmdlet 來管理垃圾郵件篩選原則，但使用 **\*-HostedContentFilterRule** Cmdlet 來管理垃圾郵件篩選規則。

- 在 PowerShell 中，您要先建立垃圾郵件篩選原則，然後再建立垃圾郵件篩選規則來識別將套用規則的原則。

- 在 PowerShell 中，您可以分開修改垃圾郵件篩選原則和垃圾郵件篩選規則中的設定。

- 當您移除 PowerShell 中的垃圾郵件篩選原則時，對應的垃圾郵件篩選規則不會自動移除，反之亦然。

### <a name="default-anti-spam-policy"></a>預設的反垃圾郵件原則

每個組織都有一個名為「預設」的內建反垃圾郵件原則，其中包含下列屬性：

- 名為「預設」垃圾郵件篩選原則適用於組織中所有的收件者，即使沒有與原則相關聯的垃圾郵件篩選規則 (收件者篩選器)。

- 名為「預設」的原則具有不能修改的自訂優先順序 **Lowest** (一律最後才會套用的原則)。 任何自訂垃圾郵件原則的優先順序一律都高於名為「預設」的原則。

- 名為「預設」的原則是預設的原則 (**IsDefault** 屬性具有值 `True`)，且您無法刪除預設原則。

若要提高垃圾郵件篩選的效率，您可以建立自訂反垃圾郵件原則，以更嚴格的設定套用到特定使用者或使用者群組。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [反垃圾郵件設定]**** 頁面，請使用 <https://protection.office.com/antispam>。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要連接至獨立版 Exchange Online Protection PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 您必須已獲指派權限，才能執行這些程序。 若要新增、修改、刪除反垃圾郵件原則，您必須是**組織管理**或**安全性系統管理員**角色群組的成員。 若要唯讀存取反垃圾郵件原則，您必須是**安全性讀取者**角色群組的成員。 如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱 [Office 365 安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。

- 如需反垃圾郵件原則的建議設定，請參閱 [EOP 反垃圾郵件原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings) (英文)。

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a>使用安全性與合規性中心來建立反垃圾郵件原則

在安全性與合規性中心建立自訂的反垃圾郵件原則時，是同時建立垃圾郵件篩選規則和相關聯的垃圾郵件篩選原則，且為兩者使用相同的名稱。

1. 在安全性與合規性中心，移至 [威脅管理]**** \> [原則]**** \> [反垃圾郵件]****。

2. 在 [反垃圾郵件設定]**** 頁面上，按一下 [建立原則]****。

3. 在隨即開啟的 [新增垃圾郵件篩選原則]**** 飛出視窗中進行下列設定：

   - **名稱**：輸入原則的唯一描述性名稱。 請勿使用下列字元：`\ % & * + / = ? { } | < > ( ) ; : , [ ] "`。

      如果您先前在 Exchange 系統管理中心 (EAC) 中建立的反垃圾郵件原則包含這些字元，您應用 PowerShell 重新命名該反垃圾郵件原則。 如需相關指示，請參閱本主題稍後的[使用 PowerShell 修改垃圾郵件篩選規則](#use-powershell-to-modify-spam-filter-rules)一節。

   - **說明**：輸入原則的選擇性說明。

4. (選用) 展開 [垃圾郵件和大量動作]**** 區段，然後確認或設定如下設定：

   - **選取對內送的垃圾郵件和大量電子郵件要採取的動作**：根據下列垃圾郵件篩選裁決，選取或檢查對郵件要採取的動作：

     - **垃圾郵件**
     - **高信賴度的垃圾郵件**
     - **網路釣魚電子郵件**
     - **高信賴度的網路釣魚電子郵件**
     - **大量電子郵件**

     下表說明垃圾郵件篩選裁決可採取的動作。

     - 核取記號 ( ![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)) 表示可採取的動作 (並非所有的垃圾郵件篩選裁決皆可採取所有動作)。
     - 核取記號之後有星號 (<sup>\*</sup>) 表示垃圾郵件篩選裁決的預設動作。

    |||||||
    |:---|:---:|:---:|:---:|:---:|:---:|
    ||**垃圾郵件**|**高信賴度<br/>垃圾郵件<br/>**|**網路釣魚<br/>電子郵件**|**高信賴度<br/>網路釣魚<br/>電子郵件<br/>**|**大量<br/>電子郵件**|
    |**將郵件移至 [垃圾郵件] 資料夾**：郵件會傳送至信箱，並移至 [垃圾郵件] 資料夾。<sup>1</sup>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
    |**新增 X 標頭**：在郵件標頭中新增 X 標頭，並將郵件傳送到信箱。 <br/> 您稍後可以在 [新增此 X 標頭文字]**** 方塊中輸入 X 標頭欄位的名稱 (不是值)。 <br/><br/> 裁決為**垃圾郵件**和**高信賴度垃圾郵件**的郵件會移至 [垃圾郵件] 資料夾。<sup>1,2</sup>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
    |**在主旨列前加上文字**：新增文字至郵件主旨列的開頭。 郵件會傳送至信箱，並移至 [垃圾郵件] 資料夾。<sup>1,2</sup> <br/> 您稍後可以在 [在主旨列前加上此文字]**** 方塊中輸入文字。|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |**將郵件重新導向至電子郵件地址**：將郵件傳送給其他收件者，而不是預定收件者。 <br/> 您稍後可以在 [重新導向到這個電子郵件地址]**** 方塊中指定收件者。|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |**刪除郵件**：刪除整封郵件，包括所有附件。|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |**隔離郵件**：將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/> 您稍後可以在 [隔離]**** 方塊中指定郵件要在隔離區保留多久。|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |**無動作**|||||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |

    > <sup>1</sup> 在 Exchange Online 中，如果信箱已啟用垃圾郵件規則 (預設為啟用)，郵件會移至 [垃圾郵件] 資料夾。 如需詳細資訊，請參閱[在 Office 365中設定 Exchange Online 信箱的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。<br/>在獨立版 EOP 環境中，EOP 會保護內部部署 Exchange 信箱，您必須在內部部署 Exchange 中設定郵件流程規則 (又稱為傳輸規則) 以轉譯 EOP 垃圾郵件篩選裁決，這樣垃圾郵件規則才可以將郵件移至 [垃圾郵件] 資料夾。 如需詳細資訊，請參閱[設定獨立版 EOP 將垃圾郵件傳送到混合式環境中的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。<br/><br/><sup>2</sup> 您可以使用此值做為郵件流程規則 (又稱為傳輸規則) 的條件，以便篩選或傳送郵件。

   - **選取閾值**：針對會觸發**大量電子郵件**垃圾郵件篩選裁決指定動作的訊息，指定大量抱怨層級 (BCL)，(大於、不大於或等於指定的值)。 較高的值表示不太理想的郵件 (更可能像是垃圾郵件)。 預設值為 7。 如需詳細資訊，請參閱 [Office 365 中的大量抱怨層級 (BCL)](bulk-complaint-level-values.md) 和[垃圾電子郵件與大量電子郵件之間有何不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)。

     根據預設，PowerShell 只會將反垃圾郵件原則中的 MarkAsSpamBulkMail__ 設定為 `On`。 這項設定會嚴重影響**大量電子郵件**篩選的裁決：

     - **MarkAsSpamBulkMail__ 為 On**：大於閾值的 BCL 會轉換成 SCL 6 (對應到**垃圾郵件**篩選裁決)，然後對郵件採取**大量電子郵件**篩選裁決的動作。

     - **MarkAsSpamBulkMail__ 為 Off**：郵件會加蓋 BCL 戳記，但**大量電子郵件**篩選裁決不會執行任何動作__。 實際上，BCL 閾值和**大量電子郵件**篩選裁決動作並不相關。

   - **隔離**：指定當您選取**隔離郵件**做為垃圾郵件篩選裁決的動作時，郵件將存放在隔離中要多久的時間。 時間到了之後，就會刪除郵件。 預設值是 30 天。 有效值是從 1 到 30 天。 如需隔離的相關資訊，請參閱下列主題：

     - [Office 365 中的隔離區](quarantine-email-messages.md)
     - [以 Office 365 系統管理員身分管理隔離的郵件與檔案](manage-quarantined-messages-and-files.md)
     - [以 Office 365 使用者身分尋找及釋出隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)

   - **新增此 X 標題文字**：只有當您選取 [新增 X 標頭]**** 做為垃圾郵件篩選裁決的動作時，才會有此方塊，且是必要的設定。 您指定的值是郵件標頭「名稱」**，會新增到郵件標頭中。 標題欄位的「值」** 一律是 `This message appears to be spam`。

     長度上限為 255 個字元，且值不能包含空格或冒號 (:)。

     例如，如果輸入 `X-This-is-my-custom-header` 值，則新增到郵件的 X 標頭為 `X-This-is-my-custom-header: This message appears to be spam.`。

     如果您輸入的值包含空格或冒號 (:)，系統會忽略您輸入的值，並在郵件中新增預設的 X 標頭 (`X-This-Is-Spam: This message appears to be spam.`)。

   - **在主旨列前加上此文字**：只有當您選取 [在主旨列前加上文字]**** 做為垃圾郵件篩選裁決的動作時，才會有此方塊，且是必要的設定。 輸入要新增至郵件主旨列開頭的文字。

   - **重新導向到這個電子郵件地址**：只有當您選取 [將郵件重新導向至電子郵件地址]**** 做為垃圾郵件篩選裁決的動作時，才會有此方塊，且是必要的設定。 輸入您要遞送郵件的電子郵件地址。 您可以輸入多個值並以分號 (;) 分隔。

   - **安全提示**：預設會啟用安全提示，但您可以清除 [開啟]**** 核取方塊加以停用。 如需有關安全性提示的詳細資訊，請參閱 [Office 365 中的電子郵件安全提示](safety-tips-in-office-365.md)。

   **零時差自動清除**設定：ZAP 會偵測傳送到 Exchange Online 信箱的郵件，並採取行動。 如需有關 ZAP 的詳細資訊，請參閱[零時差自動清除 - 防範垃圾郵件和惡意程式碼](zero-hour-auto-purge.md)。

   - **垃圾郵件 ZAP**：預設會啟用 ZAP 以偵測垃圾郵件，但您可以清除 [開啟]**** 核取方塊加以停用。

   - **網路釣魚 ZAP**：預設會啟用 ZAP 以偵測網路釣魚，但您可以清除 [開啟]**** 核取方塊加以停用。

5. (選用) 展開 [允許清單]**** 區段，依據允許跳過垃圾郵件篩選的電子郵件地址或電子郵件網域，來設定郵件寄件人：

   > [!CAUTION]
   > <ul><li>在此新增網域前請仔細考慮。 如需詳細資訊，請參閱[在 Office 365 中建立安全寄件者清單](create-safe-sender-lists-in-office-365.md)。</li><li>絕對不要將接受的網域 (您擁有的網域) 或一般網域 (例如 microsoft.com 或 office.com) 新增到允許的網域清單中。 這會讓攻擊者能夠略過垃圾郵件篩選將電子郵件送進您的貴組織。</li></ul>

   - **允許寄件者**：按一下 [編輯]****。 在 [允許的寄件者清單]**** 飛出視窗中：

      a. 輸入寄件者的電子郵件地址。 您可以指定多個電子郵件地址並以分號 (;) 隔開。

      b. 按一下 ![新增圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 以新增寄件者。

      視需要重複這些步驟。

      您新增的寄件者會出現在飛出視窗的 [允許的寄件者]**** 區段中。 若要刪除寄件者，按一下 ![移除圖示](../../media/scc-remove-icon.png)。

      完成後，按一下 [儲存]****。

   - **允許網域**：按一下 [編輯]****。 在隨即出現的 [允許的網域清單]**** 飛出視窗中，執行下列步驟：

      a. 輸入網域。 您可以指定多個網域並以分號 (;) 隔開的。

      b. 按一下 ![新增圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 以新增網域。

      視需要重複這些步驟。

      您新增的網域會出現在飛出視窗的 [允許的網域]**** 區段中。 若要刪除網域，按一下 ![移除圖示](../../media/scc-remove-icon.png)。

      完成後，按一下 [儲存]****。

6. (選用) 展開 [封鎖清單]**** 區段，依據將一律標示為「高信賴度的垃圾郵件」的電子郵件地址或電子郵件網域，來設定郵件寄件人：

   > [!NOTE]
   > 手動封鎖網域並不危險，但會增加您的管理工作量。 如需詳細資訊，請參閱[在 Office 365 中建立封鎖寄件者清單](create-block-sender-lists-in-office-365.md)。

   - **封鎖寄件者**：按一下 [編輯]****。 在隨即出現的 [封鎖的寄件者清單]**** 飛出視窗中，執行下列步驟：

      a. 輸入寄件者的電子郵件地址。 您可以指定多個電子郵件地址並以分號 (;) 隔開。 不可使用萬用字元 (*)。

      b. 按一下 ![新增圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 以新增寄件者。

      視需要重複這些步驟。

      您新增的寄件者會出現在飛出視窗的 [封鎖的寄件者]**** 區段中。 若要刪除寄件者，按一下 ![移除按鈕](../../media/scc-remove-icon.png)。

      完成後，按一下 [儲存]****。

   - **封鎖網域**：按一下 [編輯]****。 在隨即出現的 [封鎖的網域清單]**** 飛出視窗中：

      a. 輸入網域。 您可以指定多個網域並以分號 (;) 隔開的。 不可使用萬用字元 (*)。

      b. 按一下 ![新增圖示](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 以新增網域。

      視需要重複這些步驟。

      您新增的網域會顯示在飛出視窗的 [封鎖的網域]**** 清單中。 若要刪除網域，按一下 ![移除按鈕](../../media/scc-remove-icon.png)。

      完成後，按一下 [儲存]****。

7. (選用) 展開 [國際垃圾郵件]**** 區段，根據垃圾郵件篩選會封鎖的電子郵件語言或來源國家/地區，來設定電子郵件語言：

   - **篩選以下列語言撰寫的電子郵件**：預設會停用此設定 ([狀態： 關閉]****)。 按一下 [編輯]****。 在隨即出現的 [國際垃圾郵件設定]**** 飛出視窗中，進行下列設定：

     - **篩選以下列語言撰寫的電子郵件**：選取核取方塊以啟用此功能。 清除核取方塊可停用此設定。

     - 在方塊中按一下，然後開始輸入語言的「名稱」**。 將會顯示篩選過的支援語言清單，以及對應的 ISO 639-2 語言代碼。 當您找到所需語言時，請選取該語言。 視需要重複此步驟多次。

       您選取的語言清單會顯示在飛出視窗中。 若要刪除語言，按一下 ![移除按鈕](../../media/scc-remove-icon.png)。

     完成後，按一下 [儲存]****。

   - **篩選從下列國家或地區傳送的電子郵件**：預設會停用此設定 ([狀態：關閉]****)。 若要啟用，按一下 [編輯]****。 在隨即出現的 [國際垃圾郵件設定]**** 飛出視窗中，進行下列設定：

     - **篩選從下列國家或地區傳送的電子郵件**：選取核取方塊以啟用此設定。 清除核取方塊可停用此設定。

     - 在方塊中按一下，然後開始輸入國家或地區的「名稱」**。 將會顯示篩選過的支援國家/地區清單，以及對應的 ISO 3166-1 雙字母國碼。 當您找到您要尋找的國家或地區時，請選取它。 視需要重複此步驟多次。

       您選取的國家/地區清單會顯示在飛出視窗中。 若要刪除國家或地區，按一下 ![移除按鈕](../../media/scc-remove-icon.png)。

     完成後，按一下 [儲存]****。

8. 選用的 [垃圾郵件屬性]**** 區段中有的進階垃圾郵件篩選 (ASF) 設定，預設為關閉。 我們正逐漸淘汰 ASF 設定，其功能正併入篩選堆疊的其他部分。 建議您將反垃圾郵件原則中的所有 ASF 設定關閉。

   如需有關這些設定的詳細資訊，請參閱 [Office 365 中的進階垃圾郵件篩選設定](advanced-spam-filtering-asf-options.md)。

9. (必要) 展開 [套用至]**** 區段，找出原則所套用的內部收件者。

    您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。 相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。 不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<群組 1 的成員\>_)。

    最簡單的方法是按一下 [新增條件]**** 三次，查看所有可用的條件。 您可以按一下 ![移除按鈕](../../media/scc-remove-icon.png)移除您不想要設定的條件。

    - **收件者網域為**：指定 Office 365 中一個或多個接受網域 (已設定) 中的收件者。 按一下 [新增標籤]**** 方塊，可查看並選取網域。 如果有不止一個網域，再次按一下 [新增標籤]**** 方塊可選取其他網域。

    - **收件者是**：指定您組織中的一或多個信箱、郵件使用者或郵件連絡人。 在 [新增標籤]**** 內按一下，然後開始輸入以篩選清單。 再次按一下 [新增標籤]**** 方塊以選取其他收件者。

    - **收件者以成員的身分存在於**：指定您組織中的一或多個群組。 在 [新增標籤]**** 內按一下，然後開始輸入以篩選清單。 再次按一下 [新增標籤]**** 方塊以選取其他收件者。

    - **除了**：若要為規則新增例外情況，按一下 [新增條件]**** 三次，即可查看所有可用的例外。 設定和行為就像是條件。

10. 完成後，按一下 [儲存]****。

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a>使用安全性與合規性中心來檢視反垃圾郵件原則

1. 在安全性與合規性中心，移至 [威脅管理]**** \> [原則]**** \> [反垃圾郵件]****。

2. 在 [反垃圾郵件設定]**** 頁面上，按一下![展開圖示](../../media/scc-expand-icon.png)以展開反垃圾郵件原則：

   - 預設原則名為**預設的垃圾郵件篩選原則**。

   - 您建立的自訂原則的 [類型]**** 資料行中的值是 [自訂的反垃圾郵件原則]****。

3. 重要的原則設定會顯示在展開的原則詳細資料中。 若要查看更多詳細資料，按一下 [編輯原則]****。

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a>使用安全性與合規性中心來修改反垃圾郵件原則

1. 在安全性與合規性中心，移至 [威脅管理]**** \> [原則]**** \> [反垃圾郵件]****。

2. 在 [反垃圾郵件設定]**** 頁面上，按一下![展開圖示](../../media/scc-expand-icon.png)以展開反垃圾郵件原則：

   - 預設原則名為**預設的垃圾郵件篩選原則**。

   - 您建立的自訂原則的 [類型]**** 資料行中的值是 [自訂的反垃圾郵件原則]****。

3. 按一下 [編輯原則]****。

若是自訂的反垃圾郵件原則，隨即出現的飛出視窗中顯示的設定會和[使用安全性與合規性中心來建立反垃圾郵件原則](#use-the-security--compliance-center-to-create-anti-spam-policies)一節所述的完全相同。

若是名為**預設的垃圾郵件篩選原則**的預設反垃圾郵件原則，則無法使用 [套用至]**** 區段 (原則套用至每個人)，而且您無法重新命名原則。

若要啟用或停用原則、設定原則優先順序順序、或設定使用者隔離通知，請參閱下列各節。

### <a name="enable-or-disable-anti-spam-policies"></a>啟用或停用反垃圾郵件原則

1. 在安全性與合規性中心，移至 [威脅管理]**** \> [原則]**** \> [反垃圾郵件]****。

2. 在 [反垃圾郵件設定]**** 頁面上，按一下![展開圖示](../../media/scc-expand-icon.png)以展開您所建立的自訂原則 (其 [類型]**** 資料行的值是 [自訂的反垃圾郵件原則]****)。

3. 在隨即出現的展開的原則詳細資料中，請注意**開啟**資料行的值。

   將切換開關向左移動以停用原則： ![關閉](../../media/scc-toggle-off.png)

   將切換開關向右移動以啟用原則： ![開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

您無法停用預設的反垃圾郵件原則。

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>設定自訂反垃圾郵件原則的優先順序

根據預設，系統是根據反垃圾郵件原則的建立順序給予優先順序 (較新原則的優先順序比較舊原則的優先順序低)。 較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。 不會有兩個原則的優先順序相同。

自訂反垃圾郵件原則會以其處理順序顯示 (第一個原則的**優先順序**值為 0)。 名為**預設的垃圾郵件篩選原則**的預設反垃圾郵件原則具有 **Lowest** 優先順序值，且無法變更。

 **附註**：在安全性與合規性中心中，只能在建立反垃圾郵件原則後變更它的優先順序。 在 PowerShell 中，您可以在建立垃圾郵件篩選規則時覆寫預設優先順序 (會影響現有規則的優先順序)。

若要變更原則的優先順序，請在清單中將原則上移或下移 (您無法在安全性與合規性中心直接修改 [優先順序]**** 數字)。

1. 在安全性與合規性中心，移至 [威脅管理]**** \> [原則]**** \> [反垃圾郵件]****。

2. 在 [反垃圾郵件設定]**** 頁面上，找到 [類型]**** 資料行的值為[自訂的反垃圾郵件原則]**** 的原則。 請注意 [優先順序]**** 資料行中的值：

   - 優先順序最高的自訂反垃圾郵件原則的值是 ![向下箭號圖示](../../media/ITPro-EAC-DownArrowIcon.png) **0**。

   - 優先順序最低的自訂反垃圾郵件原則的值是 ![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png) **n** (例如，![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png) **3**)。

   - 如果有三個以上的自訂反垃圾郵件原則，則最高和最低優先順序之間的原則的值會是 ![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png)![向下鍵圖示](../../media/ITPro-EAC-DownArrowIcon.png) **n** (例如，![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png)![向下箭號圖示](../../media/ITPro-EAC-DownArrowIcon.png) **2**)。

3. 按一下 ![向上箭號圖示](../../media/ITPro-EAC-UpArrowIcon.png) 或 ![向下箭號圖示](../../media/ITPro-EAC-DownArrowIcon.png) 可在優先順序清單中，將自訂反垃圾郵件原則往上或向下移動。

### <a name="configure-end-user-spam-notifications"></a>設定使用者垃圾郵件通知

當垃圾郵件篩選裁決要隔離郵件時，您可以設定使用者垃圾郵件通知，讓收件者知道寄給他們的郵件發生什麼事。 如需有關這些通知的詳細資訊，請參閱 [Office 365 中的使用者垃圾郵件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。

1. 在安全性與合規性中心，移至 [威脅管理]**** \> [原則]**** \> [反垃圾郵件]****。

2. 在 [反垃圾郵件設定]**** 頁面上，按一下![展開圖示](../../media/scc-expand-icon.png)以展開反垃圾郵件原則：

   - 預設原則名為**預設的垃圾郵件篩選原則**。

   - 您建立的自訂原則的 [類型]**** 資料行中的值是 [自訂的反垃圾郵件原則]****。

3. 在隨即出現的展開的原則詳細資料中，按一下 [設定使用者垃圾郵件通知]****。

4. 在隨即開啟的 **[\<原則名稱\>]** 視窗中，進行設定下列設定：

   - **啟用使用者垃圾郵件通知**：選取核取方塊以啟用通知。 清除核取方塊以停用通知。

   - **傳送使用者垃圾郵件通知的頻率 (天)**：選取每隔幾天要傳送通知。 預設值是 3 天。 您可以輸入 1 到 15 天。

   - **通知語言**：按一下下拉式清單並從中選取可用的語言。 預設值為 [預設]****，表示使用者隔離通知使用 EOP 組織的預設語言。

   完成後，按一下 [儲存]****。

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a>使用安全性與合規性中心來移除反垃圾郵件原則

1. 在安全性與合規性中心，移至 [威脅管理]**** \> [原則]**** \> [反垃圾郵件]****。

2. 在 [反垃圾郵件設定]**** 頁面上，按一下![展開圖示](../../media/scc-expand-icon.png)以展開您想要刪除的自訂原則 (其 [類型]**** 資料行的值是 [自訂的反垃圾郵件原則]****)。

3. 在隨即出現的展開原則詳細資料中，按一下 [刪除原則]****。

4. 在隨即出現的警告對話方塊中，按一下 [是]****。

您無法移除預設原則。

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-anti-spam-policies"></a>使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 來設定反垃圾郵件原則

下列反垃圾郵件原則設定僅適用於 PowerShell：

- MarkAsSpamBulkMail__ 參數預設是 `On`。 此設定的效果已在本主題前面的 [使用安全性與合規性中心來建立本反垃圾郵件原則](#use-the-security--compliance-center-to-create-anti-spam-policies) 一節中說明。

- 使用者垃圾郵件隔離通知的下列設定：

  - DownloadLink__ 參數，用於顯示或隱藏 Outlook 的垃圾郵件報告工具連結。

  - EndUserSpamNotificationCustomSubject__ 參數，您可以用來自訂通知的主旨列。

### <a name="use-powershell-to-create-anti-spam-policies"></a>使用 PowerShell 來建立反垃圾郵件原則

在 PowerShell 中建立反垃圾郵件原則需執行兩個步驟：

1. 建立垃圾郵件篩選原則。

2. 建立垃圾郵件選規則，此規則會指定要套用規則的垃圾郵件篩選原則。

 **附註**：

- 您可以建立新的垃圾郵件篩選規則，並對其指派未關聯的現有垃圾郵件篩選原則。 垃圾郵件篩選規則無法與多個垃圾郵件篩選原則相關聯。

- 您可以使用 PowerShell 對安全性與合規性中心中還沒有的新垃圾郵件篩選原則進行下列設定，直到您建立原則為止：

  - 建立「停用」的新原則 (在 **New-HostedContentFilterRule** Cmdlet 中啟用__ `$false`)。

  - 在建立期間設定原則的優先順序 (在 **New-HostedContentFilterRule** Cmdlet 使用 _Priority_ _\<Number\>_)。

- 您在 PowerShell 中建立的新垃圾郵件篩選原則不會顯示在安全性與合規性中心中，直到您將該原則指派到垃圾郵件篩選規則。

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>步驟 1：使用 PowerShell 建立垃圾郵件篩選原則

使用下列語法建立垃圾郵件篩選原則：

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

本範例會建立名為 Contoso Executives 的垃圾郵件篩選原則，並使用下列設定：

- 當垃圾郵件篩選裁決為垃圾郵件或高信賴度垃圾郵件時隔離郵件。

- BCL 6 會觸發大量垃圾郵件篩選裁決的動作。

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> **Set-hostedcontentfilterpolicy** 和 **Set-Set-hostedcontentfilterpolicy** 有較舊的 ZapEnabled__ 參數，以及較新的 PhishZapEnabled__ 和 SpamZapEnabled__ 參數。 ZapEnabled__ 參數已在 2020 年 2 月淘汰。 PhishZapEnabled__ 和 SpamZapEnabled__ 參數則用來繼承 ZapEnabled__ 參數的值。 不過，如果您在命令中使用 PhishZapEnabled__ 和 SpamZapEnabled__ 參數，或是在安全性與合規性中心中的反垃圾郵件原則中使用 [垃圾郵件 ZAP]**** 或 [網路釣魚 ZAP]**** 設定，系統就會忽略 ZapEnabled__ 參數的值。 換句話說，請勿使用 ZapEnabled__ 參數，改用 PhishZapEnabled__ 和 SpamZapEnabled__ 參數。

如需詳細的語法及參數資訊，請參閱 [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterpolicy)。

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

如需詳細的語法及參數資訊，請參閱 [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterrule)。

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

如需詳細的語法及參數資訊，請參閱 [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterpolicy)。

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

如需詳細的語法及參數資訊，請參閱 [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterrule)。

### <a name="use-powershell-to-modify-spam-filter-policies"></a>使用 PowerShell 修改垃圾郵件篩選原則

除了下列項目外，當您如同本主題前面的[步驟 1：使用 PowerShell 建立垃圾郵件篩選原則](#step-1-use-powershell-to-create-a-spam-filter-policy) 一節所述在 PowerShell 中修改惡意程式碼篩選原則時，會出現相同的設定。

- MakeDefault__ 可將指定的原則轉換成預設原則 (套用至每個人，一律**最低**優先順序，且無法刪除)，但只有當您在 PowerShell 中修改垃圾郵件篩選原則時才能使用。

- 您無法重新命名垃圾郵件篩選原則(**Set-hostedcontentfilterpolicy** Cmdlet 沒有 Name__ 參數)。 當您在安全性與合規性中心中重新命名反垃圾郵件原則時，只會重新命名垃圾郵件篩選「規則」__。

使用下列語法修改垃圾郵件篩選原則：

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

如需詳細的語法及參數資訊，請參閱 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)。

### <a name="use-powershell-to-modify-spam-filter-rules"></a>使用 PowerShell 修改垃圾郵件篩選規則

當您用 PowerShell 修改垃圾郵件篩選規則時，唯一無法使用的設定為 Enabled__ 參數 (可讓您建立停用的規則)。 若要啟用或停用現有的垃圾郵件篩選規則，請看下一節。

另一方面，當您用 PowerShell 修改垃圾郵件篩選規則時，將無法使用其他設定。 當您如同本主題前面的 [步驟 2：使用 PowerShell 建立垃圾郵件篩選規則](#step-2-use-powershell-to-create-a-spam-filter-rule)一節所述建立規則時，會出現相同的設定。

使用下列語法修改垃圾郵件篩選規則：

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

此範例會替可能導致安全性與合規性中心出問題的現有垃圾郵件篩選規則 `{Fabrikam Spam Filter}` 重新命名。

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

如需詳細的語法及參數資訊，請參閱 [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule)。

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

如需詳細的語法和參數資訊，請參閱 [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedcontentfilterrule) 和 [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedcontentfilterrule)。

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

- 若要在建立新規則時設定其優先順序，請使用 **New-HostedContentFilterRule** Cmdlet 上的 Priority__ 參數。

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

如需詳細的語法及參數資訊，請參閱 [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterpolicy)。

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

如需詳細的語法及參數資訊，請參閱 [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterrule)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>傳送 GTUBE 訊息以測試您的垃圾郵件原則設定

> [!NOTE]
> 只有當寄出 GTUBE 訊息的電子郵件組織無法掃描輸出的垃圾郵件時，這些步驟才有用。 如果能掃描，則無法傳送測試郵件。

未經同意大量電子郵件的一般測試 (GTUBE) 是文字字串，可放入測試郵件中，用於確認貴組織的反垃圾郵件設定。 GTUBE 訊息類似於歐洲反電腦病毒協會 (EICAR) 用於測試惡意程式碼設定的文字檔。

請在電子郵件中，將下列 GTUBE 文字放在單一行上，不加任何空格或換行：

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a>允許/封鎖清單

有時我們的篩選器會錯過郵件，或者我們的系統需要時間才能完成目標。 在此情況下，反垃圾郵件原則提供 [允許] 和 [封鎖] 清單來提供覆寫目前的結果。 請盡量不要使用此選項。因為暫時我們的篩選堆疊應該執行該做的事，而清單可能因此變得無法管理。

> [!TIP]
> 在某些情況下，有時您的組織可能不同意服務所提供的結果。 如果這樣，您可能希望永久保留 [允許] 或 [封鎖] 清單。 不過，如果您要長期將網域放在 [允許]清單上，請告知寄件者先確認他們使用已驗證的網域；如果不是則將遭 DMARC 拒絕。
