---
title: 提高商務用 Microsoft 365 威脅防護
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 設定 Microsoft Defender 以 Office 365 和保護機密資料，以防範網路釣魚、惡意程式碼和其他威脅。
ms.openlocfilehash: 4b5142efbf4392f017cd9b96f6a9c36ef2000bb7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245137"
---
# <a name="increase-threat-protection"></a>加強威脅防護

本文可協助您提高 Microsoft 365 訂閱中的保護，以防範網路釣魚、惡意程式碼和其他威脅。 這些建議適用于安全性增加的組織，例如法律辦事處和衛生保健診所的需求。

開始之前，請先檢查 Office 365 的安全分數。 Office 365安全分數會根據您的定期活動和安全性設定來分析貴組織的安全性，並指定分數。 請先記下您目前的分數。 若要增加您的分數，請完成本文中建議的動作。 目標不會達到最大分數，但請注意保護您的環境不會對使用者生產力造成不良影響的機會。

如需詳細資訊，請參閱 [Microsoft 安全分數](../security/defender/microsoft-secure-score.md)。

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>提升郵件中惡意程式碼的保護層級

您的 Office 365 或 Microsoft 365 環境包括防範惡意程式碼。 您可以使用常用於惡意程式碼的檔案類型來封鎖附件，以提升這種保護。 若要提高電子郵件的惡意程式碼保護：

1. 移至 [https://protection.office.com](https://protection.office.com) 並以您的系統管理員帳號憑證登入。

2. 在安全性與 &amp; 合規性中心的左功能窗格中，在 [ **威脅管理**] 底下，選擇 [ **原則** \> **Anti-Malware**]。

3. 按兩下預設原則，以編輯此全公司原則。

4. 選取 [設定]。

5. 在 [ **一般附件類型篩選**] 底下，選取 [ **開啟**]。 封鎖的檔案類型會列在此控制項底下的視窗中。 請務必新增下列檔案類型：

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   如有必要，您可以稍後新增或刪除檔案類型。

6. 選取 [ **儲存]。**

如需詳細資訊，請參閱 [EOP 中的反惡意程式碼保護](../security/office-365-security/anti-malware-protection.md)。

## <a name="protect-against-ransomware"></a>防範勒索軟體

勒索軟體會以加密檔案或鎖定電腦畫面限制存取資料。 然後，它會要求「ransom」（通常是以 cryptocurrencies 如 Bitcoin 的形式） extort money，以供 exchange 存取資料。

若要防止勒索軟體，請建立一個或多個郵件流程規則，以封鎖勒索軟體常用的副檔名。  (您在 [在 [郵件中提升惡意程式碼的保護層級](#raise-the-level-of-protection-against-malware-in-mail) ] 步驟中新增這些規則。 ) 您也可以在電子郵件中警告接收這些附件的使用者。

除了您在上一個步驟中封鎖的檔案，在開啟包含宏的 Office 檔案附件之前，先建立規則來警告使用者，這是一種很好的作法。 勒索軟體可以隱藏在宏內，所以警告使用者不要從他們不知道的人開啟這些檔案。

若要建立郵件傳輸規則：

1. 移至 [系統管理中心] <https://admin.microsoft.com> ，然後選擇 [系統 **管理中心**] \> **Exchange**。

2. 在 [ **郵件流程** ] 類別中，選取 [ **規則**]。

3. 選取 [] **+** ，然後選取 [ **建立新規則**]。

4. 在對話方塊底部選取 [ **更多選項** ]，以查看完整的選項組。

5. 針對規則套用下表中的設定。 除非您想要變更預設值，否則請對其他設定使用預設值。

6. 選取 [儲存]。

|設定|開啟 Office 檔案的附件之前警告使用者||
|---|---|---|
|名稱|反內部的勒索軟體規則：警告使用者|
|將此規則套用至 if。 . .|任何附件。 . . 副檔名符合。 . .|
|指定字詞或片語|新增下列檔案類型：  <br/> .docm、xlsm、sltm、xla、xlam、xll、pptm、potm、ppam、ppsm、sldm|
|請執行下列動作。 . .|以郵件通知收件者|
|提供郵件文字|請勿從不知道的人開啟這些類型的檔案，因為這些人可能會包含惡意程式碼的宏。|

如需詳細資訊，請參閱：

- [勒索軟體：如何降低風險](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [還原您的 OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>停止電子郵件的自動轉寄功能

取得使用者信箱存取權的駭客可以透過將信箱設定為自動轉寄電子郵件，來竊取郵件。 即使沒有使用者的認知，也可能會發生這種情況。 若要避免發生這種情況，請設定郵件流程規則。

若要建立郵件傳輸規則，請觀看 [這段簡短的影片](../business-video/stop-email-auto-forward.md) ，或遵循下列步驟：

1. 在 Microsoft 365 系統管理中心 **，選取 [系統管理中心]** \> **Exchange**。

2. 在 [ **郵件流程** ] 類別中，選取 [ **規則**]。

3. 選取 [] **+** ，然後選取 [ **建立新規則**]。

4. 若要查看所有選項，請選取對話方塊底部的 [ **更多選項** ]。

5. 套用下表中的設定。 除非您想要變更預設值，否則請對其他設定使用預設值。

6. 選取 [儲存]。

|設定|開啟 Office 檔案的附件之前警告使用者|
|---|---|
|名稱|禁止將電子郵件自動轉寄轉送至外部網域|
|將此規則套用至 if .。。|寄件者。 . . 為外部/內部。 . . 組織內部|
|新增條件|郵件屬性。 . . 包含郵件類型。 . . 自動轉寄|
|請執行下列動作 .。。|封鎖郵件。 . . 拒絕郵件並包含說明。|
|提供郵件文字|由於安全性原因，禁止此組織外部的電子郵件的自動轉寄電子郵件。|


## <a name="protect-your-email-from-phishing-attacks"></a>保護您的電子郵件免受網路釣魚攻擊

如果您已為 Office 365 或 Microsoft 365 環境設定一或多個自訂網域，您可以設定目標的反網路釣魚防護。 防網路釣魚防護是 Microsoft Defender for Office 365 的一部分，可協助保護您的組織免受惡意模擬型網路釣魚攻擊和其他網路釣魚攻擊。 若尚未設定自訂網域，您不需要執行此動作。

建議您建立原則來保護您最重要的使用者和自訂網域，以開始使用這項保護。

若要在 Microsoft Defender 中為 Office 365 建立反網路釣魚原則，請觀看[這段簡短的訓練影片](../business-video/setup-anti-phishing.md)，或完成下列步驟：

1. 請移至 [https://protection.office.com](https://protection.office.com)。

2. 在安全性與 &amp; 合規性中心的左功能窗格中，選擇 [ **威脅管理**] 底下的 [ **原則**]。

3. 在 [ **原則** ] 頁面上，選擇 [ **反網路釣魚**]。

4. 在 [ **反網路釣魚** ] 頁面上，選取 [ **+ 建立**]。 嚮導會啟動以逐步逐步定義您的反網路釣魚原則。

5. 依照下表的建議，指定原則的名稱、描述及設定。 如需詳細資訊，請參閱[瞭解 Microsoft Defender 中的反網路釣魚原則以取得 Office 365 選項](../security/office-365-security/set-up-anti-phishing-policies.md)。

6. 檢查您的設定之後，請選擇 [ **建立這個原則** ] 或 [ **儲存**] （如適用）。

|設定或選項|建議的設定|
|---|---|
|名稱|網域和最有價值的活動人員|
|描述|確定最重要的人員和我們的網域未進行類比。|
|新增要保護的使用者|選取 **[+ 新增條件]，收件者是**。 輸入使用者名稱，或輸入候選人、活動管理員及其他重要員工成員的電子郵件地址。 您最多可以新增20個要從類比中保護的內部和外部地址。|
|新增要保護的網域|選取 **[+ 新增條件]，收件者網域是**。 輸入與 Microsoft 365 訂閱相關聯的自訂網域（如果您已定義的話）。 您可以輸入一個以上的網域。|
|選擇動作|如果模仿的使用者傳送電子郵件：選擇 [重新 **導向郵件至其他電子郵件地址**]，然後輸入安全性管理員的電子郵件地址。例如，*劉愛琳 <span> <span> @contoso .com*。 如果電子郵件來自冒充的網域：請選擇 **[隔離郵件]**。|
|信箱情報|當您建立新的反網路釣魚原則時，系統會預設選取信箱情報。 請將此設定保留為 **[開啟]**，以獲得最佳結果。|
|新增受信任的寄件者與網域|您可以在這裡新增您自己的網域或任何其他受信任的網域。|
|套用對象|請選取 **[收件者的網域是]**。 在 **[任一項]** 底下選取 **[選擇]**。 選取 **[+ 新增]**。 選取功能變數名稱（例如 contoso）旁的核取方塊 *。 <span> <span>com*，在清單中，然後選取 [**新增**]。 選取 **[完成]**。|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a>使用安全附件防範惡意附件和檔案

人們經常傳送、接收及共用附件，例如文件、簡報和試算表等等。 只查看電子郵件訊息，不一定可輕易知道附件是否安全或有危害。 適用于 Office 365 的 Microsoft Defender 包含安全附件保護，但預設不會開啟此保護。 建議您建立新的規則，以開始使用這種保護。 這項保護會延伸至 SharePoint、OneDrive 和 Microsoft Teams 中的檔案。

若要建立安全附件原則，請觀看 [這段簡短的影片](../business-video/safe-attachments.md)，或完成下列步驟：

1. 移至 [https://protection.office.com](https://protection.office.com) ，然後使用您的系統管理員帳戶登入。

2. 在安全性與 &amp; 合規性中心的左功能窗格中，選擇 [ **威脅管理**] 底下的 [ **原則**]。

3. 在 [原則] 頁面上，選擇 [ **安全附件**]。

4. 在 [安全附件] 頁面上，選取 [**開啟 SharePoint、OneDrive 及 Microsoft Teams 的 ATP** ] 核取方塊，廣泛套用此保護。

5. 選取 **+** 以建立新的原則。

6. 套用下表中的設定。

7. 檢查您的設定之後，請選擇 [ **建立這個原則** ] 或 [ **儲存**] （如適用）。

|設定或選項|建議的設定|
|---|---|
|名稱|使用偵測到的惡意程式碼封鎖目前和未來的電子郵件。|
|描述|使用偵測到的惡意程式碼封鎖目前和未來的電子郵件和附件。|
|儲存附件未知的惡意程式碼回應|Select **Block-封鎖目前和未來的電子郵件和附件偵測到的惡意** 代碼。|
|在偵測時重新導向附件|啟用重新導向 (選取此方塊) 輸入系統管理員帳戶或隔離的信箱設定。          若惡意程式碼掃描附件超時或發生錯誤，請套用上述選取範圍。 (選取此方塊) 。|
|套用對象|收件者網域是。 . . 選取您的網域。|

如需詳細資訊，請參閱[在 Microsoft Defender 中為 Office 365 設定反網路釣魚原則](../security/office-365-security/set-up-anti-phishing-policies.md)。

## <a name="protect-against-phishing-attacks-with-safe-links"></a>使用安全連結防禦網路釣魚攻擊

駭客有時候會在電子郵件或其他檔案的連結中隱藏惡意網站。 安全連結是 Office 365 的 Microsoft Defender 部分，可在電子郵件訊息中 (URLs) ，在電子郵件訊息和 Office 檔中提供網頁位址的驗證，以協助保護您的組織。 保護是透過安全連結原則定義。

我們建議您執行下列作業：

- 修改預設原則以提升保護。

- 新增針對您網域中所有收件者的新原則。

若要設定安全連結，請觀看 [這段簡短的訓練影片](../business-video/safe-links.md)，或完成下列步驟：

1. 移至 [https://protection.office.com](https://protection.office.com) ，然後使用您的系統管理員帳戶登入。

2. 在安全性與 &amp; 合規性中心的左功能窗格中，選擇 [ **威脅管理**] 底下的 [ **原則**]。

3. 在 [原則] 頁面上，選擇 [ **安全連結**]。

若要修改預設原則：

1. 在 [安全連結] 頁面上，于 [套用 **至整個組織的原則**] 底下，選取 **預設** 原則。

2. 在 [**電子郵件以外套用至內容的設定**] 底下，選取 [ **Microsoft 365 Apps 企業版]，Office iOS 和 Android**。

3. 選取 [儲存]。

若要建立新的原則針對您網域中的所有收件者：

1. 在 [安全連結] 頁面上，于 [套用 **至整個組織的原則**] 底下，選取 [ **+** 建立新原則]。

2. 套用下表所列的設定。

3. 選取 [儲存]。

|設定或選項|建議的設定|
|---|---|
|名稱|網域中所有收件者的安全連結原則|
|選取郵件中未知可能惡意 URLs 的動作|選取 **[URLs 會在使用者按一下連結時，重新寫入並檢查已知惡意連結的清單**。|
|使用安全附件掃描可下載的內容|選取此方塊。|
|套用對象|收件者網域是。 . . 選取您的網域。|

如需詳細資訊，請參閱 [安全連結](../security/office-365-security/safe-links.md)。

## <a name="go-to-intune-admin-center"></a>移至 Intune 系統管理中心

1. 登入 [Azure 入口網站](https://portal.azure.com/)。

2. 在 [**搜尋**] 方塊中選取 [**所有服務**]，然後輸入 *Intune* 。

3. 結果出現之後，請選取 [ **Microsoft Intune** ] 旁邊的 [開始]，讓它成為最愛，稍後便可輕鬆尋找。

除了系統管理中心之外，您還可以使用 Intune 來註冊和管理您組織的裝置。 如需詳細資訊，請參閱使用[Intune 管理之裝置](/intune/enrollment-options)Windows 裝置和註冊選項的[註冊方式功能](/intune/enrollment/enrollment-method-capab)。
