---
title: 資料外洩防護概觀
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/12/2019
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何識別、監控和自動保護 Office 365 中貴組織中的敏感資訊。
ms.openlocfilehash: 7d526d5eeb74f0d31f375974824e7a76344bcd76
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925807"
---
# <a name="overview-of-data-loss-prevention"></a>資料外洩防護概觀
<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
<!-- move this note to a more appropriate place, no topic should start with a note -->
> [!NOTE]
> 針對已取得 Office 365 進階合規性授權的使用者，系統最近將資料外洩防護功能新增至 Microsoft Teams 聊天和頻道訊息，該功能可作為獨立選項提供，並包含在 Office 365 E5 和 Microsoft 365 E5 合規性中。 若要深入了解授權需求，請參閱 [Microsoft 365 租用戶層級服務授權指導方針](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)

為了符合企業標準和產業規定，組織必須保護敏感性資訊並防止意外洩漏。 敏感性資訊包括財務資料或個人識別資訊 (PII)，例如信用卡號碼、身分證字號或健康記錄。 透過 Office 365 安全性與合規性中心的資料外洩防護 (DLP) 原則，您可以識別、監控及自動保護整個 Office 365 的敏感性資訊。
  
採用 DLP 原則，您可以：
  
- **在多個位置識別敏感性資訊，例如 Exchange Online、SharePoint Online、商務用 OneDrive 及 Microsoft Teams。**
    
    例如，您可以識別任何含有商務用 OneDrive 網站所儲存信用卡號碼的文件，也可以只監視特定人員的 OneDrive 網站。
    
- **防止意外共用敏感性資訊**。 
    
    舉例來說，您可以使用文件或電子郵件中的健康記錄識別文件或電子郵件是否與組織外部人員共用，然後自動封鎖該文件的存取權，或是防止電子郵件傳送。
    
- **監視和保護 Excel、PowerPoint 和 Word 桌面版中的敏感性資訊。**
    
    如同在 Exchange Online、SharePoint Online 和商務用 OneDrive 中，這些 Office 桌面程式也包含識別敏感性資訊及套用 DLP 原則的相同功能。 DLP 可在多人共用這些 Office 程式中的內容時提供持續監視的功能。
    
- **協助使用者了解如何符合規範，而不中斷其工作流程。**
    
    您可以讓使用者了解 DLP 原則，協助他們符合規範，而不會封鎖其工作。 例如，如果某個使用者嘗試共用含有敏感資訊的文件，DLP 原則可以傳送電子郵件通知給他們，同時在文件庫的內容中顯示原則提示，允許他們因為正當商務理由而覆寫原則。 相同原則提示也會顯示在 Outlook 網頁版、Outlook、Excel、PowerPoint 及 Word。
    
- **檢視 DLP 警示和報告以了解有哪些內容符合貴組織的 DLP 原則。**
    
    若要檢視與您 DLP 原則相關的警示和中繼資料，您可以使用 [DLP 警示管理儀表板](dlp-configure-view-alerts-policies.md)。 您也可以檢視原則比對報告，以評估貴組織遵守 DLP 原則的方式。 如果 DLP 原則允許使用者覆寫原則提示並回報誤判，您也可以檢視使用者回報的內容
    
您可以在 Microsoft 365 合規性中心的 [資料外洩防護] 頁面上建立及管理 DLP 原則。
  
![Office 365 安全性與合規性中心內的資料外洩防護頁面](../media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a>DLP 原則的內容

DLP 原則包含一些基本事項：
  
- 要保護內容的位置：**位置**，例如 Exchange Online、SharePoint Online 和商務用 OneDrive 網站，以及 Microsoft Teams 聊天和頻道訊息。 
    
- 何時及如何藉由執行強制包含下列要素的 **規則** 來保護內容： 
    
  - **條件**：內容必須符合，才會強制執行規則。 例如，規則可能設定為僅尋找包含身分證號碼並與組織外部人員共用的內容。 
    
  - 您要原則在找到符合條件的內容時自動採取的 **動作**。 例如規則可能設定為封鎖文件的存取，以及傳送電子郵件通知給使用者和法務人員。 
    
您可以使用規則以符合特定的保護需求，然後使用 DLP 原則將常見保護需求分成一組，例如所有需要遵守特定法規的規則。
  
例如，您的 DLP 原則可能協助您偵測是否存在受到健康保險流通與責任法案 (HIPAA) 的資訊。 此 DLP 原則可尋找任何含有此敏感性資訊並與組織外部人員共用的文件 (條件)，然後封鎖此文件的存取並傳送通知 (動作)，進而協助保護所有 SharePoint Online 網站與所有商務用 OneDrive 網站 (位置) 的 HIPAA 資料 (內容)。 這些需求會儲存為個別規則並分組為 DLP 原則，以簡化管理和報告。
  
![圖表顯示 DLP 原則包含位置和規則](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a>位置

DLP 原則套用於跨 Microsoft 365 位置的敏感性項目，並且可以如本表格所述進一步限定範圍。


|位置 | 包含/排除依據|
|---------|---------|
|Exchange 電子郵件| 通訊群組|
|SharePoint 網站 |網站 |
|OneDrive 帳戶 |帳戶 |
|Teams 聊天和頻道訊息 |帳戶 |
|Windows 10 裝置 |使用者或群組 |
|Microsoft Cloud App Security |執行個體 |


 如果您選擇在 Exchange 中包含特定通訊群組，DLP 原則將只會限定至該群組的成員。 類似地排除通訊群組會從原則評估中排除該通訊群組的所有成員。 您可以選擇將原則限定至通訊清單、動態通訊群組和安全性群組的成員。 DLP 原則最多可包含 50 項此類的包含和排除。

如果您選擇包含或排除特定 SharePoint 網站或 OneDrive 帳戶，則 DLP 原則只能包含不超過 100 項此類包含或排除。 雖然有這個限制，但您可以套用全組織原則或套用到整個位置的原則來超過這些限制。
  
### <a name="rules"></a>規則

> [!NOTE]
> 沒有設定警報時，DLP 原則的預設行為是不會警示或觸發。 這僅適用於預設資訊類型。 對於自訂資訊類型，即使原則中未定義任何動作，系統仍會發出警示。

用來對貴組織內容強制執行您的商務需求的，就是規則。 一項原則包含一或多個規則，而每個規則是由條件和動作所組成。 對每個規則而言，條件符合時，就會自動採取動作。 規則會依序執行，從每個原則中最高優先順序的規則開始。
  
規則也會提供通知選項，以通知使用者 (透過原則提示和電子郵件通知) 和系統管理員 (透過電子郵件事件報告) 內容符合規則。
  
規則的組成元件及個別說明如下。
  
![DLP 規則編輯器的區段](../media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a>條件

條件很重要，因為它們會決定您要尋找的資訊類型，以及何時採取動作。 例如，您可以選擇略過包含護照號碼的內容，除非內容中包含超過 10 個這類號碼，並與組織外部人員共用。
  
條件著重於 **內容** (例如您要尋找哪些類型的敏感性資訊)，也著重於 **內容** (例如文件與誰共用)。 您可以使用條件對不同的風險層級指派不同的動作。 例如，相較於與組織外部人員共用的敏感性內容，內部共用的敏感性內容風險可能較低，所需的動作也較少。 
  
![清單會顯示可用的 DLP 條件](../media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
目前可用的條件可以判斷：
  
- 內容是否包含機密資訊。
    
- 內容是否包含標籤。 如需詳細資訊，請參閱下一節的[將保留標籤做為 DLP 原則的條件](#using-a-retention-label-as-a-condition-in-a-dlp-policy)。
    
- 內容是否與組織外部或內部人員共用。

  > [!NOTE]
  > 在主持組織 Active Directory 或 Azure Active Directory 租用戶中擁有非來賓帳戶的使用者，將視為組織內部人員。
    
#### <a name="types-of-sensitive-information"></a>敏感性資訊類型

DLP 原則有助於保護敏感性資訊 (已定義為 **敏感性資訊類型**)。 Microsoft 365 包含許多不同區域多種常見敏感資訊類型可供您使用，例如信用卡號碼、銀行帳戶號碼、身分證號碼和護照號碼。 
  
![可用的敏感性資訊類型清單](../media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
DLP 原則在尋找信用卡號碼等敏感性資訊類型時，並不只是尋找 16 位數的數字。 使用下列各項的組合可定義和偵測每種敏感資訊類型：
  
- 關鍵字。
    
- 驗證總和檢查碼或結構的內部函數。
    
- 用以尋找模式相符項目的規則運算式評估。
    
- 其他內容檢查。
    
這有助於 DLP 偵測達到高度準確性，同時減少可能造成工作中斷的誤判數。
  
#### <a name="actions"></a>動作

當內容符合規則中的條件時，就可以套用動作以自動保護內容。
  
![可用的 DLP 動作清單](../media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
您現在可以採取的動作如下：
  
- **限制內容存取權**：根據您的需求，您可以透過三種方式限制內容存取權：

  1. 限制所有人存取內容。
  2. 限制組織外部人員存取內容。
  3. 限制「有連結的任何人」存取。

  針對網站內容，這表示文件的權限除了主要網站集合系統管理員、文件擁有者以及最後修改文件的人員以外，所有人都受到限制。 這些人員可以移除文件中的敏感性資訊或採取改善動作。 當文件符合合規性時，將會自動還原原始權限。 當文件的存取權遭到封鎖時，文件會在網站的文件庫中顯示，帶有特殊原則提示圖示。 
    
  ![顯示文件存取的原則提示被封鎖](../media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
  若是電子郵件內容，這個動作會禁止郵件傳送。 取決於 DLP 規則的設定，寄件者會看到 NDR 或 (若規則使用通知) 原則提示及/或電子郵件通知。
    
  ![未授權收件者必須從郵件中移除的警告](../media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a>使用者通知和使用者覆寫

您可以使用通知和覆寫，讓使用者了解 DLP 原則，協助他們符合規範，而不會封鎖其工作。 例如，如果某個使用者嘗試共用含有敏感資訊的文件，DLP 原則可以傳送電子郵件通知給他們，同時在文件庫的內容中顯示原則提示，允許他們因為正當商務理由而覆寫原則。
  
![DLP 原則編輯器的使用者通知和使用者覆寫區段](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
電子郵件可以通知傳送、共用或上次修改內容的人員；若是網站內容，還會另外通知主要網站集合系統管理員和文件擁有者。 此外，您可以從電子郵件通知中新增或移除人員。
  
除了傳送電子郵件通知以外，使用者通知也會顯示原則提示：
  
- Outlook 和 Outlook 網頁版中。
    
- 針對 SharePoint Online 或商務用 OneDrive 網站上的文件。
    
- 當文件儲存在 DLP 原則所包含的網站上時，則在 Excel、PowerPoint 及 Word 中。
    
電子郵件通知和原則提示會說明內容與 DLP 原則衝突的原因。 經選擇後，電子郵件通知和原則提示將可讓使用者藉由回報為誤判或提供正當業務理由來覆寫規則。 這可協助您將 DLP 原則正確的相關資訊傳達給使用者，並強制執行這些原則而不會妨礙到其正常工作。 覆寫及誤判的相關資訊也會記錄並回報 (請參閱以下關於 DLP 報告的資訊)，並納入事件報告中 (下一節)，以便法務人員可以定期檢閱此資訊。
  
以下是商務用 OneDrive 帳戶中的原則提示外觀。
  
![OneDrive 帳戶中的文件原則提示](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 若要深入了解 DLP 原則中的使用者通知和原則提示，請參閱 [使用通知和原則提示](use-notifications-and-policy-tips.md)。

#### <a name="alerts-and-incident-reports"></a>警示和事件報告

規則相符時，您可以將含有警示詳細資料的警示電子郵件傳送給您的法務人員 (或是您選擇的任何人)。 這份警示電子郵件將帶有 [DLP 警示管理儀表板](dlp-configure-view-alerts-policies.md)的連結，法務人員可以打開連結以檢視警示和活動的詳細資料。 儀表板包含觸發警示的事件詳細資料，以及相符的 DLP 原則詳細資料和已偵測到的敏感性內容。

此外，您也可以傳送事件詳細資料的事件報告。 這份報告包含相符項目的相關資訊、符合規則的實際內容，以及上次修改內容的人員名稱。 若是電子郵件訊息，報告則會以附件的方式提供與 DLP 原則相符的原始郵件。
  
![設定事件報告的頁面](../media/Alerts-and-incident-report.png)

DLP 掃描電子郵件的方式不同於 SharePoint Online 或商務用 OneDrive 中的項目。 在 SharePoint Online 和商務用 OneDrive 中，DLP 會掃描現有項目以及新的項目，並在發現相符項目時產生警示和事件報告。 在 Exchange Online 中，DLP 僅會掃描新的電子郵件訊息，並在原則相符時產生報告。 DLP ***不會*** 掃描或比對信箱或封存內儲存的既有電子郵件項目。
  
## <a name="grouping-and-logical-operators"></a>群組和邏輯運算子

DLP 原則通常都有簡單的需求，例如識別包含美國社會安全號碼的所有內容。 不過，在其他情況下，DLP 原則可能需要識別出粗略定義的資料。
  
例如，若要識別受限於美國健康保險資訊流通及責任法案 (HIPAA) 的內容，您需要尋找：
  
- 包含特定類型之機密資訊的內容，例如美國社會安全號碼或藥物管理局 (DEA) 編號。
    
    AND
    
- 更難以識別的內容，例如病患的照護通訊或提供的醫療服務描述。 要識別此種內容，需要將關鍵字與極大的關鍵字清單比對，例如國際疾病分類 (ICD-9-CM 或 ICD-10-CM)。
    
您可以使用群組和邏輯運算子 (AND、OR) 輕鬆識別此類粗略定義的資料。 您在建立 DLP 原則時可以：
  
- 群組機密資訊類型。
    
- 選擇群組內機密資訊類型之間和群組本身之間的邏輯運算子。
    
### <a name="choosing-the-operator-within-a-group"></a>選擇群組內的運算子

在群組內，您可以選擇是只要滿足群組中的任一條件還是必須滿足所有條件，以便將內容視為符合規則。
  
![顯示群組之內運算子的群組](../media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a>新增群組

您可以快速新增具有自己本身之條件和運算子的群組。
  
![[新增群組] 按鈕](../media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a>選擇群組之間的運算子

在群組之間，您可以選擇只要滿足一個群組中的條件，還是必須滿足所有群組的條件，才能將內容視為符合規則。
  
例如，內建的美國 HIPAA 原則中有一個規則在群組之間使用 **AND** 運算子，以識別包含以下群組的內容： 
  
- 來自 **[PII 識別碼]** 群組 (至少有一個社會安全號碼或 DEA 編號) 
    
    **和**
    
- 來自 **[醫療術語]** 群組 (至少有一個 ICD-9-CM 關鍵字或 ICD-10-CM 關鍵字) 
    
![顯示群組之間運算子的群組](../media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a>處理規則的優先順序

當您在原則中建立規則時，每個規則都會根據建立時間指派優先順序，也就是說，第一個建立的規則具有第一優先順序，第二個建立的規則具有第二優先順序，依此類推。 
  
![依優先順序排列的規則](../media/dlp-rules-in-priority-order.png)
  
您設定一個以上的 DLP 原則之後，可以變更一或多個原則的優先順序。 若要這樣做，請選取原則，選擇 **[編輯原則]**，然後使用 **[優先順序]** 清單來指定優先順序。

![設定原則的優先順序](../media/dlp-set-policy-priority.png)

以規則評估內容時，系統會依優先順序處理規則。 如果內容符合多條規則，系統會依優先順序進行處理，並強制執行限制最嚴苛的動作。 舉例來說，如果內容符合下列所有規則，系統會強制執行規則 3，因為它是優先順序最高、最嚴格的規則：
  
- 規則 1：只通知使用者
    
- 規則 2：通知使用者、限制存取且允許使用者覆寫
    
- 規則 3：通知使用者、限制存取且不允許使用者覆寫
    
- 規則 4：只通知使用者
    
- 規則 5：限制存取
    
- 規則 6：通知使用者、限制存取且不允許使用者覆寫
    
請注意，在此範例中雖然只強制執行了最嚴格的那項規則，但所有符合規則的項目都會記錄在稽核記錄中，並顯示於 DLP 報告。
  
關於原則提示，請注意：
  
- 只會顯示最高優先順序、最嚴格規則的原則提示。 例如，會封鎖內容存取權的規則與僅傳送通知的規則，只會顯示前者的原則提示。 這樣可避免使用者看到重疊顯示的原則提示。
    
- 如果最嚴格規則中的原則提示允許人員覆寫規則，則覆寫此規則也將會覆寫內容符合的任何其他規則。
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a>調整規則以讓它們更容易或更難符合

在建立並開啟 DLP 原則後，有時候會遇到下列問題：
  
- 太多 **非** 敏感性資訊的內容符合規則，換句話說就是太多誤判。 
    
- 太少內容 **是** 敏感性資訊符合規則。 換句話說，不會對敏感性資訊強制執行保護動作。 
    
若要解決這些問題，您可以調整規則的執行個體計數及比對精確度，使得內容更難或更易於符合規則。 規則中使用的每個機密資訊類型都同時具有執行個體計數及比對精確度。
  
### <a name="instance-count"></a>執行個體計數

執行個體計數指的是特定敏感性資訊類型必須在內容中出現多少次才能符合規則的次數。 例如，如果識別出 1 到 9 個之間的不重複美國或英國護照號碼， 內容就符合以下顯示的規則。
  
請注意，執行個體計數僅包含符合敏感性資訊類型的 **不重複** 關鍵字。 例如，如果有一封電子郵件內出現 10 次同一組信用卡號碼，這 10 次只會採計為該信用卡號碼出現一次。 
  
使用執行個體計數來調整規則的指導方針非常簡單：
  
- 若要讓規則更容易符合，請減少 **[最小]** 計數及/或增加 **[最大]** 計數。 您也可以刪除 **[最大]** 中的數值以將它設定成 **[任意]**。 
    
- 若要讓規則更難符合，請增加 **[最小]** 計數。 
    
一般而言，您會在執行個體計數較低 (例如 1 到 9) 的規則中使用較不具限制性的動作，例如傳送使用者通知。 並在執行個體計數較高 (例如 10 到任意) 的規則中使用較多限制的動作，例如限制存取內容且不允許使用者覆寫。
  
![規則編輯器中的執行個體計數](../media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a>比對精確度

如上所述，機密資訊類型會由不同類型證據所形成的組合來定義與偵測。 一般而言，機密資訊類型會由多種這樣的組合 (稱為模式) 所定義。 證據需求較低的模式具有較低的比對精確度 (或信賴等級)，而證據需求較高的模式，其比對精確度 (或信賴等級) 則較高。 若要深入了解各機密資訊類型實際使用的模式及信賴等級，請參閱[敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)。
  
例如，名為 [信用卡號碼] 的機密資訊類型是由兩種模式所定義：
  
- 一個 65% 信賴度的模式，所需證據為：
    
  - 一組信用卡號碼形式的數字。
    
  - 一組通過總和檢查碼的數字。
    
- 一個 85% 信賴度的模式，所需證據為：
    
  - 一組信用卡號碼形式的數字。
    
  - 一組通過總和檢查碼的數字。
    
  - 格式正確的關鍵字或到期日。
    
您可以在自己的規則中使用這些信賴等級 (或比對精確度)。 一般而言，您會在比對精確度較低的規則中使用較不具限制性的動作，例如傳送使用者通知。 並在比對精確度較高的規則中使用較多限制的動作，例如限制存取內容且不允許使用者覆寫。
  
請務必記得，當在內容中辨識出特定機密資訊類型 (例如信用卡號碼) 時，系統只會傳回一個信賴等級：
  
- 如果所有符合項目都是來自同一個模式，那麼會傳回該模式的信賴等級。
    
- 如果符合的模式不只一個 (亦即有兩種不同信賴等級的相符項目)，則會傳回單一模式中最大的信賴等級。 這部分就有點複雜了。 以信用卡為例，如果同時符合了 65% 和 85% 的模式，該機密資訊傳回的信賴等級會大於 90%，因為證據越多代表信賴度越高。
    
因此，如果您想要為信用卡建立兩個互斥規則，一個比對精確度為 65%，另一個為 85%，那麼比對精確度的範圍會像下面這樣。 第一個規則只會挑選與模式 65% 相符的項目。 第二個規則至少會挑選 85% 相符的項目，並可能會有其他較低信賴度的相符項目。 
  
![兩個比對精確度範圍不同的規則](../media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
由於這些原因，建立具有不同比對精確度之規則的指導方針為：
  
- 最低信賴等級的 **[最小]** 和 **[最大]** 值通常會使用同一個值 (而不是一個範圍)。 
    
- 最高的信賴等級通常會是一個稍高於最低信賴等級到 100 的範圍。
    
- 任何介於中間的信賴等級則通常是一個稍高於最低信賴等級，到稍低於最高信賴等級之間的範圍。
    
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>使用保留標籤作為 DLP 原則的條件

當您在 DLP 原則中使用先前建立及發佈的[保留標籤](retention.md#retention-labels)做為條件時，請注意下列事項：

- 您必須先建立並發佈保留標籤，然後才能嘗試將它做為 DLP 原則中的條件。
- 已發佈的保留標籤會在一到七天內進行同步處理。如需詳細資訊，關於保留原則中已發佈的保留標籤請參閱 [當保留標籤可以使用時](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) ，關於自動發佈的保留標籤請參閱 [保留標籤要多久才會生效](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect)。
- **僅 SharePoint 和 OneDrive 中的項目才支援***在原則中使用保留標籤。

  ![做為條件的標籤](../media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

  如果您的項目受保留與處置的限制，且您也想要對這些項目套用其他控制，則可以在 DLP 原則中使用保留標籤，例如：

  - 您發佈了一個名為 **2018 年稅務** 的保留標籤，該保留標籤會套用至儲存在 SharePoint 中 2018 年的稅務文件，保留 10 年，然後加以處置。 您也不想要在組織外共用這些項目，則可以使用 DLP 原則執行此動作。

  > [!IMPORTANT]
  > 如果您指定保留標籤做為 DLP 原則的條件，且也將 Exchange 和/或 Teams 包含為位置，您會遇到此錯誤：**「不支援保護電子郵件與小組訊息內套用標籤的內容。請移除下列標籤或關閉 Exchange 與 Teams 做為位置。」** 這是因為 Exchange 傳輸不會在提交與傳遞郵件期間評估標籤中繼資料。 

### <a name="using-a-sensitivity-label-as-a-condition-in-a-dlp-policy"></a>使用敏感度標籤做為 DLP 原則的條件

使用敏感度標籤做為 DLP 原則的條件目前處於預覽階段。 [深入了解](./dlp-sensitivity-label-as-condition.md)。
  
### <a name="how-this-feature-relates-to-other-features"></a>這項功能與其他功能的關係

有多項功能可以套用到含有敏感性資訊的內容：
  
- [保留標籤和保留原則](retention.md) 都能對內容強制執行 **保留** 動作。 
    
- DLP 原則可以對內容強制執行 **「保護」** 動作。 您不僅要為內容設定標籤，還要讓內容滿足其他條件，DLP 原則才能強制執行這些動作。 
    
![可對敏感性資訊執行的功能圖表](../media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
請注意，DLP 原則的偵測功能比套用到敏感性資訊的任何標籤或保留原則來得強大。 DLP 原則可以針對含有敏感性資訊的內容強制執行保護動作。如果敏感性資訊已從內容中移除，就可以在系統再次掃描內容後復原相關的保護動作。 但是，如果保留原則或標籤套用到含有敏感性資訊的內容，就是一次性動件。之後即使移除敏感性資訊，也無法復原。
  
如果將標籤做為 DLP 原則的條件，就可以針對設有該標籤的內容來強制執行保留和保護動作。 設有標籤的內容就像是含有敏感性資訊的內容，標籤和敏感性資訊類型都是用來分類內容的屬性，您可以藉此針對內容強制執行動作。
  
![將標籤做為條件的 DLP 原則的圖表](../media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a>簡單設定和進階設定的比較

建立 DLP 原則時，您可選擇簡單或進階設定：
  
- **簡單設定** 可讓您輕鬆建立最常見的 DLP 原則，而不使用規則編輯器來建立或修改規則。 
    
- **進階設定** 會使用規則編輯器，提供您 DLP 原則設定的完整控制權。 
    
別擔心，除了設定方式以外，簡單設定與進階設定的運作方式完全相同，皆會強制執行由條件及動作構成的原則，唯一的差別在於使用簡單設定時，您不會看見規則編輯器。 最快的方式便是建立 DLP 原則。
  
### <a name="simple-settings"></a>簡單設定

目前，最常見的 DLP 情境是建立原則以協助保護含有敏感性資訊的內容，避免組織外部的人員共用這類內容，並採取自動修正動作，如限制可存取內容的對象、傳送使用者或系統管理員通知，並稽核事件以便日後調查。 採用 DLP 的人員可協助避免敏感性資訊不當外洩。
  
若要以更簡單的方式達成這個目標，請在建立 DLP 原則時，選擇 **[使用簡單設定]**。 這些設定會提供執行最常見 DLP 原則所需的項目，讓您不必進入規則編輯器。
  
![用於顯示簡易和進階設定的 DLP 選項](../media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a>進階設定

如果您要建立更多自訂 DLP 原則，您可以選擇 **[使用進階設定]**。
  
使用進階設定即可顯示規則編輯器。在編輯器中，您擁有所有選項的完整控制權，包括每個規則的執行個體計數及相符準確度 (信賴層級)。
  
若要快速移至某個區段，只要按一下規則編輯器頂端瀏覽區中的項目，即可移至下方的該區段。
  
![DLP 規則編輯器的頂端瀏覽功能表](../media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a>DLP 原則範本

建立 DLP 原則的第一步是選擇要保護的資訊。 從 DLP 範本開始，您就省去從頭建立新規則集，以及釐清應依預設包含資訊類型的工作。 接著，您可以新增或修改這些需求以微調規則，達到組織的特定需求。
  
預先設定的原則範本可協助您偵測特定的敏感性資訊類型，例如 HIPAA 資料、PCI-DSS 資料、Gramm-Leach-Bliley 金融服務業現代化法案資料，或甚至是特定地區設定的個人識別資訊 (PII)。 為了讓您能輕鬆地尋找並保護常見的敏感資訊類型，Microsoft 365 中包含的原則範本納入了最常見的敏感資訊類型，讓您快速著手使用。
  
![資料外洩防護原則的範本清單，重點在於針對美國的範本愛國者法案](../media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
貴組織也可能設有專屬需求，在這種情況下，您可以選擇 **[自訂原則]** 選項從頭建立 DLP 原則。 自訂原則中不會有任何內容，也不含預先製作的規則。 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a>以測試模式逐漸推出 DLP 原則

建立 DLP 原則時，您應考慮逐漸推出這些原則，以便在完全強制執行之前評估其影響及測試其效果。 例如，您不希望新的 DLP 原則不慎封鎖數千份完成工作所需之文件的存取。
  
如果您正在建立的 DLP 原則可能有重大影響，建議依照下列順序進行：
  
1. **以測試模式啟動但不顯示原則提示**，然後使用 DLP 報告和任何事件報告來評估影響。 您可以使用 DLP 報告來檢視原則相符項目的號碼、位置、類型和嚴重性。 根據結果，您可以視需要微調規則。 在測試模式中，DLP 原則不會影響您的組織中工作人員的生產力。 
    
2. **移至測試模式並顯示通知和原則提示**，以便您開始教導使用者相關規範原則及熟悉即將套用的規則。在這個階段，您也可以要求使用者回報誤判，以便您進一步調整規則。 
    
3. **開始完整強制執行原則**，以便套用規則中的動作，並保護內容。 繼續監視 DLP 報告以及任何事件報告或通知，確保得到您想要的結果。 

    ![使用測試模式和開啟原則的選項](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    您可以隨時關閉 DLP 原則，關閉會影響原則中的所有規則。 不過，也可以藉由在規則編輯器中切換每個規則的狀態來個別關閉規則。

    ![在原則中關閉規則的選項](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    您也可以變更原則中多個規則的優先順序。 若要這樣做，請開啟原則進行編輯。 在規則列中，選擇省略符號 (**...**)，然後選擇一個選項，例如 **[下移]** 或 **[移至最後]**。

    ![設定規則優先順序](../media/dlp-set-rule-priority.png)
  
## <a name="dlp-reports"></a>DLP 報告

建立並開啟您的 DLP 原則之後，您會想要確認原則是否達到您想要的效果並有助於您符合規範。 透過 DLP 報告，您可以快速檢視一段時間內的 DLP 原則和規則相符項目的數目，以及誤判和覆寫的數目。 針對每份報告，您可以依據位置、時間範圍篩選這些相符項目，甚至將其範圍縮小到特定原則、規則或動作。
  
透過 DLP 報告，您將可取得深入的商業資訊，並且：
  
- 將重點放在特定時段，以了解尖峰和趨勢的原因。
    
- 探索違反貴組織規範原則的商務程序。
    
- 了解 DLP 原則帶來的任何業務影響。
    
此外，您可以使用 DLP 報告來微調您所執行的 DLP 原則。
  
![安全性與合規性中心中的報表儀表板](../media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a>DLP 原則的運作方式

DLP 會使用深度內容分析 (不只是簡單的文字掃描) 來偵測敏感資訊。此深度內容分析會使用關鍵字比對、字典比對、規則運算式評估、內部函數和其他方法來偵測符合 DLP 原則的內容。可能只有一小部分的資料會被視為敏感資訊。DLP 原則可識別、監視和自動保護該項資料，而不會妨礙或影響到使用其餘內容的人員。
  
### <a name="policies-are-synced"></a>原則會同步處理

在安全性與合規性中心中建立 DLP 原則之後，原則會儲存在中央原則存放區中，然後再同步處理至各種內容來源，包括：
  
- Exchange Online，再從這裡到 Outlook 網頁版和 Outlook。
    
- 商務用 OneDrive 網站。
    
- SharePoint Online 網站。
    
- Office 桌上型電腦程式 (Excel、PowerPoint 及 Word)。

- Microsoft Teams 頻道和聊天訊息。
    
原則同步處理至正確的位置之後，會開始評估內容並強制執行動作。
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a>商務用 OneDrive 和 SharePoint Online 網站中的原則評估

在您所有的 SharePoint Online 網站和商務用 OneDrive 網站上，文件都會持續變動 — 文件會不斷地建立、編輯、共用等等。 這表示文件可能會隨時違反或符合 DLP 原則。 例如，人員可以將不含敏感資訊文件上傳到小組網站，而後另一個人可以編輯同一份文件並在其中加入敏感資訊。
  
因此，DLP 原則會頻繁地在背景中檢查文件是否有原則相符項目。 您可以將此視為非同步原則評估。
<!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a>運作方式
 
當使用者新增或變更其網站中的文件時，搜尋引擎會掃描內容，使您可以在稍後搜尋。 執行這個動作時，也會掃描內容的敏感性資訊，並檢查它是否為共用。 找到的任何敏感性資訊會安全地儲存在搜尋索引中，只有合規性小組能夠存取，一般使用者無法存取。 您已開啟的每個 DLP 原則會在背景執行 (以非同步方式)，頻繁地對於符合原則的任何內容檢查搜尋，並套用動作以防止意外的資料外洩。
  
![顯示 DLP 原則如何以非同步的方式評估內容的圖表](../media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording --> 最後，文件可能會違反 DLP 原則，但也可能會符合 DLP 原則。例如，如果人員在文件中加入信用卡號碼，有可能會導致 DLP 原則自動封鎖文件的存取。但如果人員稍後移除敏感資訊，則會在下次依據原則進行評估時自動復原動作 (在此案例中為封鎖)。
  
DLP 會評估可編製索引的任何內容。 若要進一步了解依預設會對哪些檔案類型進行編目，請參閱 [SharePoint Server 中的預設編目副檔名和剖析檔案類型](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)。

> [!NOTE]
> 預設會封鎖 SharePoint中新檔案的外部共用，除非至少有一個DLP原則對新項目進行掃描。 如需詳細資訊，請參閱 [透過預設，將新檔案標示為敏感檔案](/sharepoint/sensitive-by-default)。 
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a>Exchange Online、Outlook 和 Outlook 網頁版中的原則評估

當您建立 DLP 原則，其中包含 Exchange Online 作為位置時，原則會從 Office 365 安全性與合規性中心同步到 Exchange Online，然後從 Exchange Online 同步到 Outlook 網頁版和 Outlook。
  
在 Outlook 中撰寫郵件時，若使用者撰寫的內容經評估後判定違反 DLP 原則，就會看見原則提示。 郵件送出時，系統會在一般郵件流程中進行 DLP 原則評估，此外也會一併執行 Exchange 系統管理中心中建立的 Exchange 郵件流程規則 (也稱為傳輸規則) 和 DLP 原則。 DLP 原則會掃描郵件和所有附件。
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a>Office 桌上型電腦程式中的原則評估

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
Excel、PowerPoint 和 Word 都具有與 SharePoint Online 和商務用 OneDrive 相同的功能，可識別敏感資訊並套用 DLP 原則。 這些 Office 程式會直接從中央原則存放區同步處理其 DLP 原則，並在有人使用從 DLP 原則所包含的網站開啟的文件時，持續根據 DLP 原則來評估內容。
  
Office 中的 DLP 原則評估依設計並不會影響程式的效能或內容使用者的產能。 如果他們正在處理大型文件，或使用者的電腦忙碌中，可能需要幾秒鐘才會顯示原則提示。

### <a name="policy-evaluation-in-microsoft-teams"></a>Microsoft Teams 中的原則評估
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

當您建立 DLP 原則，其中包含 Microsoft Teams 作為位置時，原則會從 Office 365 安全性與合規性中心同步到使用者帳戶與 Microsoft Teams 頻道和聊天訊息。 根據 DLP 原則的設定方式，當有人嘗試在 Microsoft Teams 聊天或頻道訊息中共用敏感性資訊時，可以封鎖或撤銷訊息。 此外，若文件包含敏感性資訊且與來賓 (外部使用者) 共用，則不會對這些使用者開放。 若要深入了解，請參閱[資料外洩防護和 Microsoft Teams](dlp-microsoft-teams.md)。
 
## <a name="permissions"></a>權限

您的合規性小組中將建立 DLP 原則的成員必須具備安全性與合規性中心的權限。 根據預設，您的租用戶系統管理員具備安全性與合規性中心的存取權，且能夠將權限授與法務人員和其他人員，而不必將租用戶系統管理員的所有權限授與他們。若要這樣做，建議您：
  
1. 在 Microsoft 365 中建立一個群組，並將法務人員新增至此群組。
    
2. 在安全性與合規性中心的 **[權限]** 頁面上建立角色群組。 

3. 建立角色群組時，請使用 [選擇角色] 區段，將下列角色新增至角色群組: [DLP 合規性管理]。
    
4. 使用 [選擇成員] 區段，將您建立的 Microsoft 365 群組新增至角色群組。

您也可以透過授予 [僅限檢視 DLP 合規性管理] 角色，來建立擁有 DLP 原則和 DLP 報告的僅限檢視權限角色群組。

如需詳細資訊，請參閱[授與使用者存取 Office 365 合規性中心的權限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。
  
需要這些權限才能建立及套用 DLP 原則。 原則強制執行不需要內容的存取權。
  
## <a name="find-the-dlp-cmdlets"></a>尋找 DLP Cmdlet

若要對安全性與合規性中心使用大部分 Cmdlet，您必須：
  
1. [使用遠端 PowerShell 連線到 Office 365 安全性與合規性中心](/powershell/exchange/connect-to-scc-powershell)。
    
2. 使用任何 [policy-and-compliance-dlp Cmdlet](/powershell/module/exchange/export-dlppolicycollection)。
    
不過，DLP 報告需要從整個 Microsoft 365 擷取資料，包含 Exchange Online。 有鑑於此，**DLP 報告的 Cmdlet 可在 Exchange Online PowerShell 中使用，但安全性與合規性中心 PowerShell 則不行**。 因此，若要為 DLP 報告使用 Cmdlet，您需要︰
  
1. [使用遠端 PowerShell 連線到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。
    
2. 為 DLP 報告使用下列任何 Cmdlet：
    
    - [Get-DlpDetectionsReport](/powershell/module/exchange/Get-DlpDetectionsReport)

    - [Get-DlpDetailReport](/powershell/module/exchange/Get-DlpDetailReport)
    
## <a name="more-information"></a>詳細資訊

- [從範本建立 DLP 原則](create-a-dlp-policy-from-a-template.md)
    
- [傳送通知並顯示 DLP 原則的原則秘訣](use-notifications-and-policy-tips.md)
    
- [建立 DLP 原則來保護具有 FCI 或其他屬性的文件](protect-documents-that-have-fci-or-other-properties.md)
    
- [DLP 原則範本包含哪些內容](what-the-dlp-policy-templates-include.md)
    
- [敏感性資訊類型實體定義](sensitive-information-type-entity-definitions.md)
    
- [DLP 功能所尋找的項目](what-the-dlp-functions-look-for.md)
    
- [建立自訂的敏感性資訊類型](create-a-custom-sensitive-information-type.md)