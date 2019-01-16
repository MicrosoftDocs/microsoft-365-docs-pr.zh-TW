---
title: Microsoft 365 商務安全性功能
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: 了解 Microsoft 365 業務與安全性功能。
ms.openlocfilehash: 17bcc57d57e837f18b05f66cfd54185324f3cad8
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866431"
---
# <a name="microsoft-365-business-security-features"></a>Microsoft 365 商務安全性功能

Microsoft 365 商務提供簡化的安全性功能，可協助保護您的 Pc、 電話和平板電腦上的資料。
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Microsoft 365 Business admin center 安全性功能

您可以管理許多系統管理中心中，可讓您簡化的方式來開啟或關閉這些功能的 Microsoft 365 商務安全性功能。在管理中心中您可以執行下列動作：
  
![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
- [設定應用程式的管理設定 Android 或 iOS 裝置](app-protection-settings-for-android-and-ios.md)。 
    
    這些設定包括檔案刪除後某一段的非使用中的裝置、 加密工作檔案、 需要使用者設定 PIN] 等。
    
- [設定 Windows 10 裝置的應用程式保護設定](protection-settings-for-windows-10-devices.md)。 
    
    這些設定可以套用至上同時公司擁有的公司資料或個人擁有的裝置。
    
- [設定 Windows 10 裝置的裝置保護設定](protection-settings-for-windows-10-pcs.md)。 
    
    您可以啟用[BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405)加密以有助於保護資料以防遺失或竊、 裝置並啟用[Windows 利用 Guard](https://go.microsoft.com/fwlink/p/?linkid=871404)提供對 ransomware 的進階的保護。 
    
- [從裝置移除公司資料](remove-company-data.md)
    
    員工離職或裝置時遺失，竊，您可以從遠端擦去公司資料。
    
- [為其原廠值重設 Windows 10 裝置](reset-devices-to-factory-settings.md)。 
    
    您可以重設已套用至這些裝置保護設定任何 Windows 10 裝置。
    
## <a name="additional-security-features"></a>其他安全性功能 

Microsoft 365 Business 中的進階的功能可協助您保護您的企業網路威脅以及可保護敏感資訊。
  
- **[Office 365 進階威脅防護](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    進階威脅保護 (ATP) 可幫助保護您的業務針對複雜的網路釣魚和 ransomware 攻擊設計危害員工或客戶資訊。功能包括：
    
  - 複雜的附件掃描與電腦控制開機分析可偵測並捨棄危險的郵件。
    
  - 自動檢查來評估的電子郵件中的網頁連結之是否它們都是網路釣魚配置的一部分。這會保留您安全存取不安全的網站。
    
- **[資料外洩防護原則概觀](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)**(DLP)。 
    
    您可以設定 DLP 以自動偵測敏感資訊、 like 信用卡號碼、 社會安全號碼、 等以防止其由於意外共用您的公司外。
    
- **[Exchange Online 封存](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online 封存授權可輕鬆地使用連續的資料備份封存的訊息。它會儲存所有使用者的電子郵件，包括已刪除的項目、 他們探索或還原稍後時需要。此外，您可以使用不同的保留原則來保留電子郵件資料的訴訟保留 eDiscovery 或符合規範需求。
    
- **[Azure 資訊保護](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    資訊保護可幫助您控制存取電子郵件和文件中的機密資訊與控制項類似"不要轉寄"和"不要複製。 」您也可以用來分類為 「 2 私人 3 機密"的機密資訊並指定可在外共用機密的資訊的方式與公司內。企業級加密很容易套用至電子郵件和保持私人資訊的文件。Microsoft 365 商務包含之所有功能的[Azure 資訊保護計劃 1](https://go.microsoft.com/fwlink/p/?linkid=871407)。您也可以安裝 Azure 資訊保護用戶端增益集的 Office 應用程式。如需詳細資訊，請參閱[Azure 資訊保護用戶端管理員指南 》](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide)。
    
- **[Intune 中 Azure 入口網站的完整功能](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    存取 Azure 入口網站中的系統管理中心可讓您設定其他安全性功能，例如管理 MacOS 裝置、 iPhone 及 Android 裝置進階的裝置管理的 Windows Intune 的不可以透過 Microsoft365 商務系統管理中心。
    
下列各節說明如何管理這些功能安全性&amp;規範中心 」 和 「 Intune 管理中心 」。一段時間會簡化將控制項新增至 Microsoft 365 商務系統管理中心。
  
## <a name="set-up-advanced-threat-protection-features"></a>設定進階威脅保護功能

- **針對不安全的附件 Protect:** ATP 以在虛擬環境中開啟電子郵件附件識別惡意的內容而執行分析所產生的行為。若要判斷其目的 （是否正常或惡意） 評估內容，並 ATP 封鎖的不安全的附件傳送給協助保護您對網路釣魚配置和 ransomware 感染。若要啟用附件保護，請參閱[Set up Office 365 ATP 安全附件的原則](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775)。
    
- 當使用者按一下惡意連結保護您的環境： ATP 也在使用者按下這些時間檢查電子郵件中的連結。若不安全的連結，使用者會收到警告不適用於瀏覽網站或得知已封鎖網站。這有助於保護網路釣魚配置。您可以[設定 Office 365 ATP 安全連結原則](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc)或[Office 365 ATP 安全連結原則設定](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)。
    
## <a name="set-up-dlp-features"></a>設定 DLP 功能

如需如何設定原則以防止個人識別資訊 (PII) 請參閱[建立 DLP 原則範本中](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)。 
  
DLP 隨附的許多不同的地區設定的許多準備好用的原則範本。例如，澳洲財務資料、 加拿大個人資訊法案、 美國財務資料、 等等。請參閱[包含新 DLP 原則範本](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)的完整清單。所有這些範本可啟用類似 PII 範本範例。 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>與 Exchange Online 封存的電子郵件保留設定

 **Exchange Online 封存**授權功能可讓您為維持相容性和法規標準來保留電子郵件內容 eDiscovery 的用途。它也有助於降低風險發生訴訟資料暫留時，並提供一種方式來復原資料安全性缺口或復原已刪除的項目在需要時。若要啟用這些功能，可以使用訴訟暫止要保留的所有使用者的內容或更大的自訂使用保留原則。 
  
**訴訟資料暫留：** 您可以保留包括已刪除的項目依據] 將使用者的整個信箱置於訴訟保留的所有信箱內容。 
    
若要將信箱置於訴訟資料暫留，在系統管理中心：
    
1. 在左邊的巡覽移至**使用者** \> **作用中使用者**。
    
2. 選取您想要放置訴訟資料暫留在其的信箱保留的使用者在 [使用者] 窗格中展開 [**郵件設定**和**其他設定**旁選擇 [**編輯 Exchange 屬性**。
    
3. 在使用者的 [信箱] 頁面上選擇 [* * 信箱功能 * * 在左邊的巡覽，然後選擇 [**訴訟暫止狀態**的 [**啟用**] 連結。
    
4. 在**訴訟暫止狀態**對話方塊可以指定訴訟保留持續時間**訴訟保留持續時間**] 欄位中、 保留欄位空白如果您想要設為無限期保留。您也可以新增附註和引導您可能必須將說明更多有關訴訟保留的網站的郵件] 方塊中擁有者\>**儲存**。
    
**保留：** 您可以啟用自訂的保留原則，例如，若要保留為特定的時間長度或結尾處的保留期限永久刪除內容。若要深入了解，請參閱 ＜ [Overview of 保留原則](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。
## <a name="set-up-azure-information-protection-features"></a>設定 「 Azure 資訊保護功能

Azure 資訊保護 (AIP) 是可協助組織用來分類及 （選用） 來保護其文件和電子郵件套用標籤雲端式方案。可由系統管理員定義規則和條件，以手動方式的使用者或提供使用者建議的組合會自動套用標籤。

能夠在網路上的 Outlook 傳送電子郵件時，適用下列限制會自動啟用所有使用者：
  
- **不要轉寄**： 收件者可讀取郵件，但不能轉寄、 列印或複製內容
    
- **加密**： 整個郵件加密。收件者必須採用額外的步驟以確認其 identity 之前存取加密的內容並無法移除加密。
    
- **2 私人 3 機密**： 電子郵件的內容及附件，但未提供給組織外部人員提供在組織中的之員工完整的權限。資料擁有者可以追蹤及撤銷在任何時候的內容。
    
- **高度機密**： 這項限制可套用至高度機密資料，讓員工能夠檢視、 編輯和回覆，但不是轉寄、 列印或複製的資料。資料擁有者可以追蹤及撤銷在任何時候的內容。

### <a name="make-sure-azure-information-protection-is-activated"></a>請確定已啟動 Azure 資訊保護

若要確認已啟動 AIP：

1. 登入[Azure 入口網站](https://portal.azure.com/)。

2. *Azure 資訊保護*在**搜尋方塊**中選取**所有服務**和類型。

3. 一旦將結果顯示，請按一下 [下一步] 以使其成為我的最愛**Azure 資訊保護**且更容易尋找稍後開始。

4. 選取 [ **Azure 資訊保護** \> **保護啟用**及產生確定狀態設為已啟動。 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>檢視的 Azure 資訊保護原則和預設標籤 

標籤來檢視和修改、 現有：

1. Azure 資訊保護儀表板上選取 [**分類** \> **標籤**。 <br/>![標準 Azure 資訊保護的標籤。](media/AIPLabels.png)

2. 您可以選擇任何標籤來檢視選項，您可以變更顯示名稱、 色彩等。
 
3. 請參閱[修改並建立新的標籤](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2)如果您想要建立您自己。 

### <a name="install-the-azure-information-protection-client-manually"></a>手動安裝 Azure 資訊保護用戶端

若要以手動方式安裝 AIP 用戶端：

1. 從[Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=53018)下載**AzInfoProtection.exe** 。
 
2. 您可以確認安裝成功檢視 Word 文件，確定 [**保護**] 選項可在 [**首頁**] 索引標籤。 <br/>![保護] 下拉式清單中的 Word 文件索引標籤。](media/Word_Protect.png)

如需詳細資訊，請參閱[安裝用戶端](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)

## <a name="go-to-intune-admin-center"></a>移至 Intune 系統管理中心

1. 登入[Azure 入口網站](https://portal.azure.com/)。

2. *Intune*在**搜尋方塊**中選取**所有服務**和類型。

3. 一旦將結果顯示，請按一下 [下一步] 以使其成為我的最愛**Microsoft Intune**且更容易尋找稍後開始。
 
您可以使用 Intune 註冊並管理組織的裝置。如需詳細資訊，請參閱[Windows 裝置註冊方法的功能](https://docs.microsoft.com/intune/enrollment-method-capabs)和[管理 Intune 的裝置註冊選項](https://docs.microsoft.com/intune/enrollment-options)。
    
## <a name="faq"></a>常見問題集

 ### <a name="are-these-security-features-available-in-all-markets"></a>在所有市場是這些安全性功能吗？
  
是，這些功能都可在所有的市場 Microsoft 365 商務售出的位置。
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>如何尋找安全性&amp;規範中心？
  
1. [登入 Microsoft 365 商務](https://portal.microsoft.com/)使用系統管理認證。 
    
2. 在左邊的巡覽中找出**系統中心**，然後展開成員。 
    
    ![在 Microsoft 365 系統管理中心左側的巡覽、 選擇 [管理中心]。](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. 選擇 [**安全性&amp;規範**移至安全性&amp;規範中心。