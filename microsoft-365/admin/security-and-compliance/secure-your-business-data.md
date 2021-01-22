---
title: 保護商務用 Microsoft 365 方案十大方式
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: '保護您的商務電子郵件和資料不受網路威脅，包括勒索軟體、網路釣魚和惡意附件。 '
ms.openlocfilehash: a329d2879309812a516191fdbd1858ad10e4beeb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926327"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>保護商務用 Microsoft 365 方案十大方式

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。

::: moniker-end

如果您是使用 Microsoft 商務方案之一的中小型企業組織，而且您的組織類型受到網路罪犯和駭客攻擊，請使用本文中的指引來提升貴組織的安全性。 此指引可協助貴組織達成 In The Handbook School [Cybersecurity Campaign Handbook 中所描述的目標](https://go.microsoft.com/fwlink/p/?linkid=2015598)。

Microsoft 建議您完成下表所列的工作，以套用至您的服務方案。

||工作|Microsoft 365 商務標準版|Microsoft 365 商務進階版|
|---|---|---|---|
|1 |[設定多重要素驗證](secure-your-business-data.md#setup)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2 |[訓練您的使用者](secure-your-business-data.md#train)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3|[使用專用系統管理員帳戶](secure-your-business-data.md#admin)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4 |[提高郵件中的惡意攻擊防護層級](secure-your-business-data.md#malware)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5 |[防範勒索軟體](secure-your-business-data.md#ransomware)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6 |[停止自動轉轉電子郵件](secure-your-business-data.md#forwarding)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7 |[使用 Office 郵件加密](secure-your-business-data.md#encryption)||![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8 |[保護您的電子郵件不受網路釣魚攻擊](secure-your-business-data.md#phishing)||![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9 |[使用安全附件防範惡意附件和檔案](secure-your-business-data.md#atp)||![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10 |[使用安全連結防範網路釣魚攻擊](secure-your-business-data.md#phishingatp)||![包含](../../media/d238e041-6854-4a78-9141-049224df0795.png)|

開始之前，請在 Microsoft [365](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) 資訊安全中心檢查您的 Microsoft 365 安全分數。 在集中式儀表板中，您可以監控並改善 Microsoft 365 身分驗證、資料、應用程式、裝置及基礎結構的安全性。 您可獲得點數，可進行建議的安全性功能、執行安全性相關工作 (例如檢視報告) ，或用協力廠商應用程式或軟體處理建議。 有了額外的深入見解，以及更多更多 Microsoft 產品和服務的可見度，您可以放心地報告貴組織的安全性健康情況。

![Microsoft 安全分數的螢幕擷取畫面](../../media/secure-score.png)

## <a name="1-set-up-multi-factor-authentication"></a>1：設定多重要素驗證
<a name="setup"> </a>

使用多重要素驗證是提高組織安全性最簡單且最有效的方法之一。 它比聲音簡單 -當您登入時，多重要素驗證表示您將從手機輸入代碼以存取 Microsoft 365。 這可以防止駭客在知道您的密碼時接管工作。 多重要素驗證又稱為兩步驟驗證。 個人可以輕鬆地將兩步驟驗證新增到大多數的帳戶，例如，加到他們的 Google 或 Microsoft 帳戶。 以下是將雙步驟驗證 [新增到您個人 Microsoft 帳戶的步驟](https://go.microsoft.com/fwlink/p/?linkid=2016403)。

針對使用 Microsoft 365 的企業，請新增要求您使用者使用多重要素驗證登入的設定。 當您進行這項變更時，系統會提示使用者在下次登入時，設定其電話進行雙因素驗證。
若要觀看如何設定 MFA 以及使用者如何完成設定的訓練影片，請參閱 [設定 MFA](https://support.microsoft.com/office/e12187b8-216a-4490-9e3b-df34a06fb787) 和 [使用者設定](https://support.microsoft.com/office/a32541df-079c-420d-9395-9d59354f7225)。

若要設定多重要素驗證，請開啟安全性預設值：

大部分的組織，安全性預設值皆提供有良好的額外登入安全性。 如需詳細資訊，請參閱[什麼是安全性預設？](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

如果您新訂閱，則系統可能會自動為您開啟安全性預設值。

您可以在 Azure 入口網站中的 Azure Active Directory (Azure AD) **屬性** 窗格中，啟用或停用安全性預設值。

1. 使用全域系統管理員憑證登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。
2. 在左側導覽中，請選擇 **[顯示所有]**，然後在 **[系統管理中心]** 底下，選擇 **[Azure Active Directory]**。
3. 在 **[Azure Active Directory 系統管理中心]** 選擇 **[Azure Active Directory** > **屬性]**。
4. 在頁面底部，選取 **[管理安全性預設]**。
5. 選擇 **[是]** 以啟用安全性預設，或 **[否]** 以停用安全性預設，然後選擇 **[儲存]**。

為組織設定多重要素驗證之後，您的使用者必須在其裝置上設定雙步驟驗證。 詳細資訊請參閱設定 [Microsoft 365 的兩步驟驗證](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)。

有關完整詳細資料及完整的建議，請參閱設定 [使用者的多重要素驗證](set-up-multi-factor-authentication.md)。

## <a name="2-train-your-users"></a>2：訓練您的使用者
<a name="train"> </a>

教育人員學校 [網路安全性活動手冊](https://go.microsoft.com/fwlink/p/?linkid=2015598) 提供在貴組織中建立強大安全性認知文化之絕佳指南，包括訓練使用者識別網路釣魚攻擊。

除了此指引外，Microsoft 建議您的使用者採取本文所述的動作：保護您的帳戶和裝置不受 [駭客和惡意程式碼威脅](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6)。 這些動作包括：

- 使用強式密碼

- 保護裝置

- 在 Windows 10 和 Mac PC 上啟用安全性功能

Microsoft 也建議使用者採取下列文章中的建議動作，以保護他們的個人電子郵件帳戶：

- [協助保護您的Outlook.com電子郵件帳戶](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [使用兩步驟驗證保護您的 Gmail 帳戶](https://go.microsoft.com/fwlink/p/?linkid=2015688&)

## <a name="3-use-dedicated-admin-accounts"></a>3：使用專用系統管理員帳戶
<a name="admin"> </a>

您用於管理 Microsoft 365 環境的系統管理帳戶包含較高的許可權。 這些是駭客和網路罪犯的寶貴目標。 請僅將系統管理員帳戶用於系統管理。 系統管理員應擁有另一個使用者帳戶，以用於一般非系統管理用途，而且只有在必要時才使用其系統管理帳戶來完成與工作功能相關的工作。 其他建議：

- 請確定系統管理帳戶也設定了多重要素驗證。

- 使用系統管理員帳戶之前，請關閉所有不相關的瀏覽器會話和應用程式，包括個人電子郵件帳戶。

- 完成系統管理工作後，請務必登出瀏覽器會話。

## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a>4：提高郵件中的惡意攻擊防護層級
<a name="malware"> </a>

您的 Microsoft 365 環境包含防範惡意攻擊的保護，但您可使用常用惡意攻擊的檔案類型封鎖附件，以提升防護能力。 若要加強電子郵件中的惡意程式碼防護，請觀看簡短的 [訓練影片](https://support.microsoft.com/office/02b5783a-eea0-42e8-8856-62440718c3f0)，或完成下列步驟：

1. 請前往 <https://protection.office.com> 您的系統管理員帳號憑證並登出。

2. 在安全性&規範中心的左側流覽窗格中，在威脅管理下選擇策略 **** \> **反惡意攻擊**。

3. 按兩下預設策略以編輯此全公司政策。

4. 選取 [設定]。

5. 在 **一般附件類型篩選下**，選取On。  封鎖的檔案類型會列在此控制項正下方的視窗中。 您可以稍後需要時新增或刪除檔案類型。

6. 選取儲存 **。**

詳細資訊請參閱 [EOP 中的反惡意攻擊防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection)。

## <a name="5-protect-against-ransomware"></a>5：防範勒索軟體
<a name="ransomware"> </a>

勒索軟體會加密檔案或鎖定電腦螢幕，以限制資料的存取。 然後，它嘗試以「勒索」的形式 ，通常以加密形式 ，例如為取得資料存取權，以試圖向他們勒索金錢。

您可以建立一或多個郵件流程規則來封鎖勒索軟體常用的副檔名，或警告在電子郵件中收到這些附件的使用者，以防範勒索軟體。 建立兩個規則是很好的起點：

- 開啟包含宏的 Office 檔案附件之前，先警告使用者。 勒索軟體可能隱藏在宏內，因此我們會警告使用者不要向不認識的人開啟這些檔案。

- 封鎖可能包含勒索軟體或其他惡意程式碼的檔案類型。 我們會從下表所列的可執行檔案清單 (一份可執行檔) 。 如果貴組織使用上述任何可執行檔類型，而且您預期這些可執行檔類型會以電子郵件送出，請將其新增到先前的規則， (警告) 。

若要建立郵件傳輸規則，請觀看簡短的 [訓練影片](https://support.microsoft.com/office/a9ecca03-42a6-4867-b9fd-38e3f6bb06ad)，或完成下列步驟：

1. 移至 [Exchange 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2059104)。

2. 在郵件 **流程類別中** ，選取 **規則**。

3. 選取 **+** ，然後 **建立新規則**。

4. 選取對話方塊底部的 *● 以查看完整的選項組。

5. 請針對每個規則，使用下表中的設定。 除非您要變更這些設定，否則其餘設定會保留預設。

6. 選取 [儲存]。
    
| 設定 | 開啟 Office 檔案附件之前警告使用者 | 封鎖可能包含勒索軟體或其他惡意程式碼的檔案類型 |
|:-----|:-----|:-----|
|姓名  <br/> |反勒索軟體規則：警告使用者  <br/> |反勒索軟體規則：封鎖檔案類型  <br/> |
|如果 . . .  <br/> |任何附件。 . . 副檔名符合。 . .  <br/> |任何附件。 . . 副檔名符合。 . .  <br/> |
|指定文字或片語  <br/> |新增這些檔案類型：  <br/> dotm， docm， xlsm， sltm， xla， xlam， xll， pptm， potm， ppam， ppsm， sldm  <br/> |新增這些檔案類型：  <br/> ade， adp， ani， bas， bat， chm， cmd， com， cpl， crt， hlp， ht， hta， inf， ins， isp， job， js， jse， lnk， mda， mdb， mde， mdz， msc， msi， msp， mst， pcd， reg， scr， sct， shs， url， vb， vbe， vbs， wsc， wsf， wsh， exe， pif  <br/> |
|執行下列操作。 . .  <br/> |在免責聲明之前  <br/> |封鎖訊息。 . . 拒絕訊息並包含說明  <br/> |
|提供郵件文字  <br/> |請勿開啟這些類型的檔案 ，除非您預期會開啟，因為檔案可能包含惡意程式碼，而且知道寄件者並不保證安全。  <br/> ||
   
> [!TIP]
> 您也可以在步驟 [4](#4-raise-the-level-of-protection-against-malware-in-mail)的反惡意代碼清單中新增您想要封鎖的檔案。

如需詳細資訊，請參閱：

- [勒索軟體：如何降低風險](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [還原您的 OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="6-stop-auto-forwarding-for-email"></a>6：停止自動轉轉電子郵件
<a name="forwarding"> </a>

取得使用者信箱存取權之駭客可以將信箱自動轉寄電子郵件，將郵件排去。 即使沒有使用者認知，也可能發生此情況。 您可以設置郵件流程規則，避免這種情況發生。

若要建立郵件傳輸規則：

1. 移至 [Exchange 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2059104)。

2. 在郵件 **流程類別中** ，選取 **規則**。

3. 選取 **+** ，然後 **建立新規則**。

4. 在 **對話方塊底部** 選取 [更多選項，以查看完整的選項組。

5. 請 Apply the settings in the following table. 除非您要變更這些設定，否則其餘設定會保留預設。

6. 選取 [儲存]。

|設定|拒絕自動轉轉電子郵件至外部網域|
|---|---|
|姓名|防止電子郵件自動轉置至外部網域|
|如果 ...|寄件者。 . . 是外部/內部。 . . 組織內部|
|新增條件|收件者。 . . 是外部/內部。 . . 組織外部|
|新增條件|郵件內容。 . . 包含訊息類型。 . . 自動轉轉|
|執行下列操作...|封鎖訊息。 . . 拒絕訊息並包含說明。|
|提供郵件文字|基於安全性考慮，會禁止自動轉轉此組織外部的電子郵件。|

## <a name="7-use-office-message-encryption"></a>7：使用 Office 郵件加密
<a name="encryption"> </a>

Office 郵件加密包含在 Microsoft 365 中。 已經設定好。 使用 Office 郵件加密，貴組織就可以在組織內外人員之間傳送及接收加密的電子郵件訊息。 Office 365 郵件加密適用于 Outlook.com、Yahoo！、Gmail 和其他電子郵件服務。 電子郵件加密可協助確保只有預定的收件者可以查看郵件內容。

Office 郵件加密在傳送郵件時提供兩種保護選項：

- 不要轉場

- 加密

貴組織可能已另外配置其他選項，將標籤適用于電子郵件，例如機密。

### <a name="to-send-protected-email"></a>傳送受保護的電子郵件

在 PC 電腦 Outlook **中，選取** 電子郵件中的選項，然後選擇 **許可權**。

![Outlook 中的電子郵件訊息加密](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)

在 Outlook.com中，選取 **電子郵件** 中的保護。 預設保護是不要 **轉場**。 若要變更為加密，請選取 **變更許可權** \> **加密**。

![電子郵件訊息加密功能Outlook.com](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)

### <a name="to-receive-encrypted-email"></a>若要接收加密的電子郵件

如果收件者有 Outlook 2013 或 Outlook 2016 和 Microsoft 電子郵件帳戶，就會在讀取窗格中看到該專案限制許可權的警示。 開啟郵件後，收件者可以如同其他收件者一樣查看郵件。

如果收件者是使用另一個電子郵件客戶程式或電子郵件帳戶 ，例如 Gmail 或 Yahoo，他們會看到一個連結，讓他們可以 Sign in to read the email message or request a-time 密碼，以在網頁瀏覽器中查看郵件。 如果使用者未收到電子郵件，請要求他們檢查其垃圾郵件資料夾。

詳細資訊請參閱 PC 電腦 Outlook 中的傳送、查看 [及回復加密的郵件](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980)。

## <a name="8-protect-your-email-from-phishing-attacks"></a>8. 保護您的電子郵件不受網路釣魚攻擊
<a name="phishing"> </a>

如果您已經針對 Microsoft 365 環境設定一或多個自訂網域，您可以設定目標防網路釣魚防護。 防網路釣魚保護是 Office 365 的 Microsoft Defender 的一部分，可協助保護貴組織不受惡意假冒型網路釣魚攻擊與其他網路釣魚攻擊。 如果您尚未安裝自訂網域，則不需要執行此操作。

我們建議您建立一個能保護您的最重要使用者和自訂網域之策略，以開始使用這項保護。

![在 Office 365 的 Microsoft Defender 中建立防網路釣魚政策](../../media/security-and-compliance-center.png)

若要在 Office 365 的 Defender 中建立防網路釣魚政策[](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)，請觀看簡短的訓練影片，或完成下列步驟：

1. 移至<https://protection.office.com>。

2. 在安全性&規範中心的左側流覽窗格中，選取威脅 **管理下的** 威脅管理。 

3. 在政策頁面上，選取 **防網路釣魚**。

4. 在防網路釣魚頁面上，選取 **+建立**。 精靈會啟動一個精靈，以完成您的防網路釣魚政策定義。

5. 請指定您政策的名稱、描述及設定，如下列圖表中的建議。 如需 [詳細資料，請參閱 Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies) 選項中的瞭解防網路釣魚政策。

6. 在您審查您的設定之後，請選取建立 **此政策** 或 **儲存**，如果適用。

|設定或選項|建議的設定|
|---|---|
|姓名|網域和最有價值行銷活動員工|
|說明|確保最重要的教職員和我們的網域不會遭到假冒。|
|新增要保護的使用者|選取 **+ 新增條件，收件者為**。 輸入使用者名稱，或輸入求職者、行銷活動經理及其他重要員工成員的電子郵件地址。 您最多可以新增 20 個要防止假冒的內部和外部地址。|
|新增要保護的網域|選取 **+ 新增條件，收件者網域為**。 輸入與 Microsoft 365 訂閱關聯的自訂網域 （如果您定義的話）。 您可以輸入多個網域。|
|選擇動作|如果電子郵件是由冒用的使用者所送出：選取將郵件重新導向至其他電子郵件地址，然後輸入安全性系統管理員的電子郵件地址;例如，securityadmin@contoso.com。 <br/> 如果電子郵件是由假冒網域所送出：選取 **隔離郵件**。|
|信箱情報|當您建立新的反網路釣魚原則時，系統會預設選取信箱情報。 請將此設定保留為 **[開啟]**，以獲得最佳結果。|
|新增受信任的寄件者與網域|在此範例中，請不要定義任何覆寫。|
|套用對象|請選取 **[收件者的網域是]**。 在 **[任一項]** 底下選取 **[選擇]**。 選取 **[+ 新增]**。 選取功能變數名稱旁的核取方塊，例如 contoso.com，然後選取新增。 選取 **[完成]**。|
|

詳細資訊請參閱在 [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies)的 Defender 中設定防網路釣魚政策。

## <a name="9-protect-against-malicious-attachments-and-files-with-safe-attachments"></a>9：使用安全附件防範惡意附件和檔案
<a name="atp"> </a>

人們經常傳送、接收及共用附件，例如文件、簡報和試算表等等。 只查看電子郵件訊息，不一定可輕易知道附件是否安全或有危害。 Microsoft Defender for Office 365 包含安全附件保護，但此保護預設不會開啟。 我們建議您建立新規則，以開始使用這項保護。 這項保護會延伸至 SharePoint、OneDrive 和 Microsoft Teams 中的檔案。

若要建立安全附件策略，請觀看簡短的 [訓練影片](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)，或完成下列步驟：

1. 請前往 <https://protection.office.com> 您的系統管理員帳戶並登出。

2. 在安全性&規範中心的左側流覽窗格中，選取威脅 **管理下的** 威脅管理。 

3. 在政策頁面上，選取安全 **附件**。

4. 在 [安全附件」 頁面上，選取 [開啟 **適用于 SharePoint、OneDrive** 和 Microsoft Teams 的 ATP 選項選項，以廣泛採用此保護。

5. 選取 **+** 以建立新策略。

6. 請 Apply the settings in the following table.

7. 在您審查您的設定之後，請選取建立 **此政策** 或 **儲存**，如果適用。

|設定或選項|建議的設定|
|---|---|
|姓名|封鎖目前和未來偵測到惡意程式碼的電子郵件。|
|說明|使用偵測到的惡意程式碼封鎖目前和未來的電子郵件和附件。|
|儲存未知的附件惡意攻擊回應|選取 **封鎖 - 封鎖目前和未來偵測到惡意程式碼的電子郵件和附件**。|
|偵測時重新導向附件|啟用重新導向 (選取此方塊)  <br/> 輸入系統管理帳戶或隔離的信箱設定。 <br/> 如果附件的惡意程式碼掃描過長或發生錯誤，請 (選取此方塊) 。|
|套用對象|收件者網域為 。 . . 選取您的網域。|
|

詳細資訊請參閱在 [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies)的 Defender 中設定防網路釣魚政策。

## <a name="10-protect-against-phishing-attacks-with-safe-links"></a>10：使用安全連結防範網路釣魚攻擊
<a name="phishingatp"> </a>

駭客有時會在電子郵件或其他檔案的連結中隱藏惡意網站。 安全連結是 Office 365 Microsoft Defender 的一部分，可協助保護貴組織，在電子郵件訊息和 Office 檔中提供網址 (url) 的按一下滑鼠右鍵驗證。 保護透過安全連結策略定義。

我們建議您執行下列操作：

- 修改預設策略以增加保護。

- 新增針對您網域中所有收件者的新策略。

若要取得安全連結，請觀看簡短的 [訓練影片](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)，或完成下列步驟：

1. 請前往 <https://protection.office.com> 您的系統管理員帳戶並登出。

2. 在安全性&規範中心的左側流覽窗格中，選取威脅 **管理下的** 威脅管理。 

3. 在政策頁面上，選取安全 **連結**。

若要修改預設策略：

1. 在 [安全連結頁面， under Policies that apply to the Policies that apply to整個 **organization，** double click **the Default** policy.

2. 在 **適用于 Office 365** 中內容的設定下，輸入要封鎖的 URL ，example.com _，然後_ 選取 **+** 。

3. 在 [設定， apply to content that apply to **a email，** select **Office 365 applications，** Do not track when users click safe **links，** and not let users click through **safe links to original URL.**

4. 選取 [儲存]。

若要建立針對您網域中所有收件者的新策略：

1. 在安全連結頁面上，于適用于 **特定收** 件者之原則下選取 **+** 以建立新原則。

2. 請 Apply the settings listed in the following table.

3. 選取 [儲存]。

|設定或選項|建議的設定|
|---|---|
|姓名|網域中所有收件者的安全連結政策|
|選取郵件中不明潛在惡意 URL 的動作|選取 **On - 使用者按一下** 連結時，系統將會重寫 URL，並針對已知惡意連結清單檢查 URL。|
|針對可疑的連結和指向檔案的連結套用即時 URL 掃描|選取此方塊。|
|套用對象|收件者網域為 . . . 選取您的網域。|
|

詳細資訊請參閱 Microsoft [Defender for Office 365 的安全連結](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)。
