---
title: 設定為 Microsoft 365 商務版使用者的進階的安全性原則
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 設定 Office 365 進階威脅防護，和保護機密資料。
ms.openlocfilehash: 4728e11a16fdf8a461f5687632df75699923f846
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2019
ms.locfileid: "33663630"
---
# <a name="set-up-advanced-security-policies"></a>設定進階的安全性原則

除了您可以在[系統管理中心](security-features.md#microsoft-365-business-admin-center-security-features)中設定的原則，您可以新增額外保護，防範網路威脅設定[Office 365 進階威脅防護](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)(ATP)。 您可以也保護敏感的資訊來設定[資料外洩防護](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)(DLP)、 Azure 資訊保護 (AIP)、 [Exchange Online 封存](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)，並也能管理您的裝置[Intune 入口網站](#go-to-intune-admin-center)中。

請參閱[上方的 10 種方法來保護 Microsoft 365 商務版計劃](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)的最重要的方式在其中您可以保護您的業務，包括使用 MFA 來建立第二個表單的登入概觀。

請參閱[保護您的企業開發人員訓練影片](https://support.office.com/article/e12187b8-216a-4490-9e3b-df34a06fb787)指示輕鬆依照指示進行。

## <a name="increase-email-malware-protection"></a>增加電子郵件的惡意程式碼保護

惡意程式碼是一種可能危害您的電腦或網路、 軟體、 可能竊取您，包括個人或客戶資訊的資料。 Microsoft 365 商務版包含防範惡意程式碼、 的基準層級，但您可以增加此保護設定其他設定。 如需相關指示[開啟惡意程式碼偵測](https://support.office.com/article/02b5783a-eea0-42e8-8856-62440718c3f0)訓練影片，請參閱。

## <a name="set-up-advanced-threat-protection-features"></a>設定進階威脅防護功能

- **不安全附件針對保護：** ATP 會識別惡意內容，藉由在虛擬環境中開啟電子郵件附件以及執行分析所產生的行為。 內容進行評估，以判斷其意圖 （無論是標準還是惡意），並且 ATP 封鎖不安全附件，傳遞致力於保護您抵禦網路釣魚配置和勒索軟體感染。 若要啟用附件保護，請參閱[設定 Office 365 ATP Safe Attachments](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775)協助文件，並[防止惡意檔案](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)簡短的訓練影片。
    
- **保護您的環境，當使用者按一下惡意連結：** ATP 也會在使用者按一下這些階段檢查電子郵件中的連結。 不安全連結時，使用者是警告未以瀏覽網站，或通知網站已被封鎖。 這有助於防止網路釣魚配置。 若要啟用此，請參閱[設定 Office 365 ATP Safe Links](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies)協助文件和[防範惡意網站](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)簡短訓練影片。

- **網路釣魚嘗試從保護您的環境：** ATP 防網路釣魚機器學習模型搭配模擬偵測演算法的一組套用於防止其他人正在嘗試從您擷取資訊，藉由假冒已知的網路釣魚攻擊的內送郵件請連絡。 若要啟用此，請參閱[設定 ATP 防網路釣魚](https://docs.microsoft.com/office365/securitycompliance/set-up-anti-phishing-policies)協助文件，並[防止網路釣魚嘗試](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)簡短的訓練影片。

## <a name="set-up-dlp-features"></a>設定 DLP 功能

如需有關如何設定的原則，以防止個人識別資訊 (PII) 的範例，請參閱[建立 DLP 原則範本中](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)。 
  
DLP 隨附許多不同的地區設定的許多準備-使用原則範本。 例如，澳洲財務資料、 加拿大個人資訊法案、 美國財務資料，等等。如需完整清單，請參閱[什麼的 DLP 原則範本包含](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)。 所有這些範本可啟用類似 PII 範本範例。 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>設定搭配 Exchange Online Archiving 的電子郵件保留

 **Exchange Online Archiving**授權功能可讓您維持合規性和法規的標準來保留電子郵件內容 eDiscovery 的目的。 它也可協助降低發生訴訟資料暫留時風險，並提供方法來復原資料安全性漏洞之後，或當您要復原刪除的項目。 若要啟用這些功能，您可以使用訴訟暫止來保留的所有使用者的內容，或使用更大的自訂保留原則。 
  
**訴訟資料暫留：** 您可以保留所有信箱內容，包括已刪除的項目依據] 將使用者的整個信箱放置於訴訟保留。 
    
若要將信箱置於訴訟暫止，在系統管理中心：
    
1. 在左側導覽中，移至 [**使用者** \> **作用中的使用者**。
    
2. 選取您想要置於 [訴訟暫止的信箱保留的使用者在使用者窗格中展開 [**郵件設定**和**其他設定**旁邊選擇 [**編輯 Exchange 屬性**。
    
3. 在使用者信箱] 頁面上，選擇 [* * 信箱功能 * * 在左側導覽中，然後選擇 [在 [**訴訟暫止**] 下的 [**啟用**] 連結。
    
4. 在**訴訟暫止狀態**對話方塊您可以指定訴訟保留期間在**訴訟暫止持續時間**] 欄位中，將欄位保留空白，如果您想要放置無限期的保留。 您也可以新增備忘稿並導向至網站，您可能必須將說明更多有關訴訟保留的郵件] 方塊中擁有者\>**儲存**。
    
**保留：** 您可以啟用自訂的保留原則，例如，若要保留經過一段時間，或在保留期間結束永久刪除內容。 若要深入了解，請參閱[保留原則的概觀](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。
## <a name="set-up-azure-information-protection-features"></a>設定 Azure 資訊保護功能

Azure 資訊保護 (AIP) 是雲端為基礎的解決方案，可協助組織，以分類，並選擇性地套用標籤，以保護其文件和電子郵件。 可由系統管理員定義規則和條件，以手動方式由使用者或提供使用者建議的組合會自動套用標籤。

能夠在網頁型 Outlook 中傳送電子郵件時，適用下列限制會自動啟用所有使用者：
  
- **不要轉寄**： 收件者可以讀取郵件，但他們無法轉寄、 列印或複製內容
    
- **加密**： 加密整封郵件。 收件者必須採取額外的步驟，以確認其身分識別存取加密的內容之前，且無法移除加密。
    
- **2 私人 3 機密**： 授與您的組織中的員工完整權限的電子郵件內容和附件，但不適用於您組織外的人員。 資料擁有者可以追蹤及撤銷的任何一點的內容。
    
- **高度機密**： 此限制可套用至高度機密資料，讓員工能夠檢視、 編輯和回覆，但不是轉寄、 列印或複製資料。 資料擁有者可以追蹤及撤銷的任何一點的內容。

### <a name="make-sure-azure-information-protection-is-activated"></a>請確定已啟動 Azure 資訊保護

若要確認 AIP 會在啟動：

1. 登入[Azure 入口網站](https://portal.azure.com/)。

2. *Azure 資訊保護*在**搜尋] 方塊**中，選取 [**所有服務**和類型。

3. 一旦顯示結果，請按一下 [下一步] **Azure 資訊保護**來使其成為我的最愛且更容易尋找稍後開始。

4. 選取 [ **Azure 資訊保護** \> **保護啟用**，並確定狀態設為啟用。 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>檢視 Azure 資訊保護原則和預設標籤 

標籤來檢視及修改，現有：

1. 在 [Azure 資訊保護儀表板中，選取 [**分類** \> **標籤**。 <br/>![標準的 Azure 資訊保護標籤。](media/AIPLabels.png)

2. 您可以選擇任何標籤來檢視的選項，您可以變更的顯示名稱、 色彩等等。
 
3. 請參閱[修改，並建立新的標籤](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2)如果您想要建立您自己。 

### <a name="install-the-azure-information-protection-client-manually"></a>以手動方式安裝 Azure 資訊保護用戶端

若要手動安裝 AIP 用戶端：

1. 從[Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=53018)下載**AzInfoProtection.exe** 。
 
2. 您可以確認安裝成功可以檢視 Word 文件，以確定可在 [**首頁**] 索引標籤上 [**保護**] 選項。 <br/>![保護索引標籤下拉式清單中的 Word 文件。](media/Word_Protect.png)

如需詳細資訊，請參閱[安裝用戶端](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)。

## <a name="go-to-intune-admin-center"></a>移至 Intune 系統管理中心

1. 登入[Azure 入口網站](https://portal.azure.com/)。

2. *Intune*中的 [**搜尋] 方塊**中，選取 [**所有服務**和類型。

3. 一旦顯示結果，請按一下 [下一步] 以使其最愛的**Microsoft Intune**且更容易尋找稍後開始。

除了系統管理中心中，您可以使用 Intune 來註冊並管理您組織的裝置。 如需詳細資訊，請參閱[功能由 Windows 裝置註冊方法](https://docs.microsoft.com/intune/enrollment-method-capabs)和[由 Intune 管理的裝置註冊選項](https://docs.microsoft.com/intune/enrollment-options)。

## <a name="microsoft-secure-score"></a>Microsoft 安全分數

