---
title: 設定您的垃圾郵件篩選原則
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/05/2018
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
ms.openlocfilehash: 0fa597887a75ff71d768d4df0b1ac4f17fe9ef13
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857354"
---
# <a name="configure-your-spam-filter-policies"></a>設定您的垃圾郵件篩選原則
垃圾郵件篩選設定，包括識別為垃圾郵件所採取的選取郵件動作。 垃圾郵件篩選原則設定只會套用於內送郵件，並且有兩種類型：

  - 預設值：預設垃圾郵件篩選原則是用來設定全公司的垃圾郵件篩選設定。 此原則不能重新命名且永遠開啟。

  - 自訂：自訂垃圾郵件篩選原則可以細微，並套用至組織中的特定使用者、群組或網域。 自訂原則的優先順序永遠高於預設原則。 您可以通過變更每個自訂原則的優先順序來變更自訂原則執行的順序，不過如果多項原則符合準則集合時，只會套用最高的優先順序原則 (也就是最接近 0 的數字)。

## <a name="what-you-must-know-before-you-begin"></a>開始之前必須注意的事項

預估完成時間：30 分鐘

您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要的權限，請參閱 [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) 主題中的反垃圾郵件項目。

垃圾郵件篩選原則設定全部都在安全性與合規性中心 (SCC)。 如需詳細資訊，請參閱[前往 Office 365 安全性與合規性中心](../../compliance/go-to-the-securitycompliance-center.md)。 反垃圾郵件的設定頁面位於 SCC \> **威脅管理** \> **原則** \> **反垃圾郵件** 一節中。

## <a name="access-and-create-spam-filter-policies"></a>存取及建立垃圾郵件篩選原則

反垃圾郵件設定頁面中的預設設定可以在 [一般] 索引標籤中檢視。若要變更這些設定，請切換至 **[自訂]** 索引標籤。您可以在 [預設垃圾郵件篩選原則] 中查看並設定一些預設設定。

若要啟用更多自訂設定或新增自訂原則，請將 **[自訂設定] **選取器變更為 **[開啟]**，以啟用自訂的垃圾郵件篩選原則。 您可以從這裡開始檢視現有的自訂原則。

## <a name="configure-custom-spam-filter-policy-settings"></a>設定自訂的垃圾郵件篩選原則設定

1. 如果您正在編輯原則，請選取並按一下 **[編輯原則]**；否則，按一下 **[建立原則]**

2. 您可以為自訂原則指定唯一名稱，但無法重新命名預設值。 您也可以為任何原則指定更詳細的說明。

3. 在 [垃圾郵件與大量動作]**** 區段下：

   - 選取 [垃圾郵件]****、[高信賴度垃圾郵件]****、[高信賴度網路釣魚電子郵件]****、[網路釣魚電子郵件]**** 以及 [大量電子郵件]**** 類型的動作。 可用值包括：

     - **將郵件移至垃圾郵件資料夾**：將郵件傳送到指定收件者的垃圾郵件資料夾。 這是垃圾郵件、高信賴度的垃圾郵件，與大量郵件的預設動作。

       > [!NOTE]
       > 為了在內部部署信箱中啟用此動作，您必須在內部部署伺服器上設定兩個 Exchange 郵件流程規則 (亦即傳輸規則)，以偵測 EOP 所新增的垃圾郵件標頭。 如需詳細資訊，請參閱[確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 此步驟對獨立式 Exchange Online Protection (EOP) 客戶很重要。

     - **新增 X 標頭**：將郵件傳送給指定的收件者，但將 X 標頭文字新增至郵件標頭，以將該郵件識別為垃圾郵件。 使用這段文字做為識別碼之後，您可以建立收件匣規則，或使用下游裝置在郵件上操作。 預設的 X 標頭文字是 **[此郵件可能是垃圾郵件]**。
     
       您可以使用 **[新增此 X 標頭文字]** 輸入方塊，自訂 X 標頭文字。 如果您自訂了 X 標頭文字，請注意下列狀況：

       - 如果您只以 \< *標頭* \> 的格式指定標頭，且 \< * 標頭* \> 內沒有空格，則自訂文字將會附加冒號，後面再加上預設文字。 例如，如果您指定「This-is-my-custom-header」，則 X 標頭文字會顯示為「This-is-my-custom-header: 此郵件可能是垃圾郵件。」

       - 如果自訂標頭文字內包含空格，或您自行加上冒號，(例如「X This is my custom header」 或 「X-This-is-my-custom-header:」)，則 X 標頭文字會還原為預設值，變成 “X-This-Is-Spam: 此郵件可能是垃圾郵件。」

       - 您無法以 \<*標頭*\>:\<*值*\> 的格式指定標頭文字。 如果您這麼做，則冒號前後的值都會被忽略，而會呈現下列預設的 X 標頭文字：「X-This-Is-Spam: 此郵件可能是垃圾郵件。」

       - 請注意由於信箱垃圾郵件的設定，具有 X 標頭的郵件仍可能移至信箱垃圾郵件資料夾。 您可以停用 Set-MailboxJunkEmailConfiguration 的功能來變更此設定。

   - **在主旨行前加上文字：** 將郵件傳送給預定的收件者，但在主旨行前加上您在 **[在主旨行前加上此文字]** 輸入方塊中指定的文字。 使用這段文字做為識別碼之後，您可以視需要選擇建立篩選或傳送郵件的規則。
    
     > [!NOTE]
     > 郵件仍會傳送到垃圾郵件資料夾。

   - **將郵件重新導向到電子郵件地址：** 將郵件傳送到指定的電子郵件地址，而不是傳送給預定的收件者。 請在 **[重新導向到此電子郵件地址]** 輸入方塊中指定「重新導向」地址。

   - **刪除郵件：** 刪除整個郵件，包括所有附件。

   - **隔離郵件：** 將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 這是網路釣魚的預設動作。 If you select this option, in the **Retain spam for (days)** input box, specify the number of days during which the spam message will be quarantined. (時間過去之後會自動刪除。 預設值是 30 天，這也是最大值。 最小值為 1 天。)

     > [!TIP]
     > 如需系統管理員要如何管理隔離區內電子郵件訊息的相關資訊，請參閱[隔離](quarantine.md)和[在 Office 365 中以系統管理員身分管理隔離的郵件和檔案](manage-quarantined-messages-and-files.md)。 <br/><br/> 如需如何為使用者設定垃圾郵件通知訊息的相關資訊，請參閱[在 EOP 中設定使用者垃圾郵件通知](configure-end-user-spam-notifications-in-eop.md)或[在 Exchange Online 中設定使用者垃圾郵件通知](configure-end-user-spam-notifications-in-exchange-online.md)。

   - 設定 **[選取閾值]** 來判斷根據郵件的大量抱怨層級 (BCL)，要將大量電子郵件視為垃圾郵件的方法。 您可以選擇 1 - 9 的閾值設定，其中 1 將最大量的電子郵件表示為垃圾郵件，而 9 允許傳遞最大量的電子郵件。 服務則會執行已設定的動作 (例如將郵件傳送至收件者的 [垃圾郵件] 資料夾)。 如需詳細資訊，請參閱 [大量抱怨層級值](bulk-complaint-level-values.md) 和[垃圾郵件和大量電子郵件有什麼不同?](what-s-the-difference-between-junk-email-and-bulk-email.md)。

4. 在**垃圾郵件屬性**頁面上，您可以透過設定為原則設定測試模式選項：

   - **無** 不對郵件採取任何測試模式動作。 此為預設值。

   - **加上預設的測試 X 標頭文字** 選取此選項會將郵件傳送給指定的收件者，但也會在郵件加上特殊的 X 標頭，將其識別為符合特定的進階垃圾郵件篩選選項。

   - **傳送密件副本郵件到這個地址** 選取此選項會傳送郵件的密件副本到輸入方塊中指定的電子郵件地址。 <br/><br/>如需進階垃圾郵件篩選選項的相關資訊，包括每個選項的說明及各選項相關的X 標頭文字，請參閱[進階垃圾郵件篩選選項](advanced-spam-filtering-asf-options.md)。

5. 僅針對自訂原則，按一下 **[套用到]** 功能表項目，然後建立一個條件式規則，以指定要套用此原則的使用者、群組及 (或) 網域。 如果它們都是唯一，則可以建立多個條件。

   - 若要選取使用者，請選取 **[收件者是]**。 在後續的對話方塊中，從使用者選擇器清單中選取您公司的一或多位寄件者，然後按一下 **[新增]**。 若要新增不在清單上的寄件者，請輸入其電子郵件地址並按一下 **[檢查名稱]**。 在此方塊中，您也可以使用萬用字元來代表多個電子郵件地址 (例如：\*@ _網域名稱_)。 當您選取完畢時，按一下 **[確定]** 回到主畫面。

   - 若要選取群組，請選取** [收件者是以下的成員]**。 接著，在後續的對話方塊中，選取或指定群組。 按一下 **[確定]** 回到主畫面。

   - 若要選取網域，請選取 **[收件者的網域是]**。 接著，在後續的對話方塊中，新增網域。 按一下 **[確定]** 回到主畫面。

     您可以建立規則內的例外狀況。 例如您可以篩選來自某個網域以外之所有網域的郵件。 按一下 **[新增例外狀況]**，再像建立其他種條件一樣建立例外狀況條件。

     將垃圾郵件原則套用到群組的功能，僅支援 **[已啟用郵件的安全性群組]**。

6. 按一下 **[儲存]**。 原則設定的摘要隨即出現在右側窗格中。

您無法停用或刪除預設原則，且自訂的原則一律會優先於預設原則。 您可以選取或清除 **[已啟用]** 欄中的核取方塊，以啟用或停用您的自訂原則。 依預設，會啟用所有原則。 若要刪除自訂原則，請選取原則，再按一下 [刪除]**** ![刪除圖示](../../media/ITPro-EAC-DeleteIcon.gif)，然後確認想要刪除原則。

> [!TIP]
> 您可以變更自訂原則的優先順序 (執行順序)，按一下 ![[向上箭號圖示]](../../media/ITPro-EAC-UpArrowIcon.gif) 向上鍵和 ![[向下箭號圖示]](../../media/ITPro-EAC-DownArrowIcon.gif) 向下鍵。 **[優先順序]** 為 **0** 的原則會最先執行，接著是 **1**、**2**，依此類推。

## <a name="use-powershell-to-configure-spam-filter-policies"></a>使用 PowerShell 設定垃圾郵件篩選原則

您也可以在 PowerShell 中設定和套用垃圾郵件篩選原則。 若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterpolicy) 檢視您的垃圾郵件篩選設定。

- [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy) 編輯您的垃圾郵件篩選設定。

- [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterpolicy) 建立新的自訂垃圾郵件篩選原則。

- [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterpolicy) 刪除新的自訂垃圾郵件篩選原則。

若要將自訂垃圾郵件篩選原則套用至使用者、群組和 (或) 網域，請使用 [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterrule) Cmdlet (建立可套用至自訂原則的新篩選規則) 或 [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule) Cmdlet (編輯可套用至自訂原則的現有篩選規則)。使用 [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedcontentfilterrule) Cmdlet或 [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedcontentfilterrule) Cmdlet 可以啟用或停用對原則套用的規則。

## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確保已針對垃圾郵件進行適當偵測和採取行動，可以透過服務傳送 GTUBE 訊息。GTUBE 與 EICAR 防毒測試檔案類似，GTUBE 提供了一項測試，您可以用來確認服務正在偵測進入的垃圾郵件。GTUBE 訊息應該一律被垃圾郵件篩選器偵測為垃圾郵件，且對郵件執行的動作應該符合您進行的設定。

請在郵件訊息中，將下列 GTUBE 文字包含在單一行上，不加任何空格或換行：

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="fine-tuning-your-spam-filter-policy-to-prevent-false-positives-and-false-negatives"></a>調整您的垃圾郵件篩選原則，以避免誤判和漏報

如果想要使用積極的垃圾郵件篩選方法，您可以啟用進階的垃圾郵件篩選技術。 如需套用至整個組織的一般垃圾郵件設定，請參閱[如何在 Office 365 中防止好的電子郵件被標示為垃圾郵件](prevent-email-from-being-marked-as-spam.md) (部分機器翻譯)，或[使用 Office 365 垃圾郵件篩選器封鎖垃圾郵件以避免漏報問題](reduce-spam-email.md)。 如果您有系統管理員層級的控制權，且您想要避免誤判或漏報，這些內容很有幫助。

## <a name="allowblock-lists"></a>允許/封鎖清單

有時我們的篩選器會錯過郵件，或者我們的系統需要時間才能完成目標。 在此情況下，反垃圾郵件原則提供 [允許] 和 [封鎖] 清單來提供覆寫目前的結果。 請盡量不要使用此選項。因為暫時我們的篩選堆疊應該執行該做的事，而清單可能因此變得無法管理。

[允許] 和 [封鎖] 清單都設定為所有客戶之反垃圾郵件原則的一部分：

1. 在 **[允許清單] ** 區段上，您可以指定一律會傳遞到收件匣的項目，例如寄件者或網域。 來自這些項目的電子郵件不會由垃圾郵件篩選器處理。

   - 將受信任的寄件者新增到寄件者允許清單。 按一下 **[編輯]** ![[新增圖示]](../../media/ITPro-EAC-AddIcon.gif)，然後在選取範圍對話方塊中新增您想要允許的寄件者地址。 您可以使用分號或新行區隔多個項目。 按一下 **[確定]** 回到 **[允許清單]** 頁面。

   - 將受信任的網域新增到網域允許清單。 按一下 **[編輯]** ![[新增圖示]](../../media/ITPro-EAC-AddIcon.gif)，然後在選取範圍對話方塊中新增您想要允許的網域。 您可以使用分號或新行區隔多個項目。 按一下 **[確定]** 回到 **[允許清單]** 頁面。

   > [!CAUTION]
   > 請勿將公認的網域 (您擁有的網域)，或一般如 Microsoft.com、office.com 等網域列入允許清單。 如此可以避免詐騙者無限制地傳送郵件到您的組織。

2. 在 [**封鎖清單**] 頁面上，您可以指定一律會標記為垃圾郵件的項目，例如寄件者或網域。此服務將會在符合這些項目的電子郵件上套用高信賴垃圾郵件動作。

   - 將不想要的寄件者新增到 [寄件者封鎖清單]。 按一下 **[編輯]** ![[新增圖示]](../../media/ITPro-EAC-AddIcon.gif)，然後在選取範圍對話方塊中新增您想要封鎖的寄件者地址。 您可以使用分號或新行區隔多個項目。 按一下 **[確定]** 回到 **[封鎖清單]** 頁面。

   - 將不想要的網域新增到 [網域封鎖清單]。 按一下 **[編輯]** ![[新增圖示]](../../media/ITPro-EAC-AddIcon.gif)，然後在選取範圍對話方塊中新增您想要封鎖的網域。 您可以使用分號或新行區隔多個項目。 按一下 **[確定]** 回到 **[封鎖清單]** 頁面。
   
     > [!NOTE]
     > 您可以在垃圾郵件篩選原則中封鎖整個網域或特定寄件者，但不能使用萬用字元 (\*)。 

> [!TIP]
> 在某些情況下，有時您的組織可能不同意服務所提供的結果。 如果這樣，您可能希望永久保留 [允許] 或 [封鎖] 清單。 不過，如果您要長期將網域放在 [允許]清單上，請告知寄件者先確認他們使用已驗證的網域；如果不是則將遭 DMARC 拒絕。

## <a name="for-more-information"></a>如需詳細資訊
<a name="sectionSection6"> </a>

[設定 DMARC 網域](use-dmarc-to-validate-email.md)

[隔離區](quarantine.md)

[如何在 Office 365 中防止好的電子郵件被標示為垃圾郵件](prevent-email-from-being-marked-as-spam.md)

[如何減少 Office 365 中的垃圾郵件](reduce-spam-email.md)

[垃圾郵件信賴等級](spam-confidence-levels.md)
