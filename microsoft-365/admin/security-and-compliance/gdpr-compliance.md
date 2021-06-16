---
title: 'GDPR 簡化: 您的小型企業指引'
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 211c5c90-9719-4d73-9ad9-1925bb80f5f6
description: 瞭解 Microsoft 365 商務版如何協助執行一般資料保護規定 (GDPR) 程式。
ms.openlocfilehash: 147843fab8fcb8d2d1793a21f9bb897cb4a59672
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929464"
---
# <a name="gdpr-simplified-a-guide-for-your-small-business"></a>GDPR 簡化: 您的小型企業指引

 *使用 Microsoft 365 商務版來協助降低和管理 GDPR 合規性* 
  
一般資料保護規定 (GDPR) 是歐盟 (EU) 法規，規定組織處理個人資料的方式。 如果您的企業販賣、提供服務予或雇用歐盟公民，則 [GDPR](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en) 對您具有效力。 

作為小型企業系統管理員，您可能會詢問自己「這究竟該如何開始進行」？ 如果您的公司未將個人資料當做核心商務活動處理，或者您完全不熟悉 GDPR，則您可能特別容易有這樣的疑惑。

您可以從閱讀這篇文章開始，此文章旨在協助您瞭解何謂 GDPR、為何會有 GDPR 的存在，以及 Microsoft 365 商務版如何協助您的組織遵守 GDPR。

其中也包含小型企業可能擁有之 GDPR 常見問題的解答，並重點說明小型企業為準備 GDPR 可採取的步驟。

> [!IMPORTANT]
> 本文中的 Microsoft 365 解決方案和建議是可協助管理及保護資料的工具和資源，但並非 GDPR 合規性之保證。 您可以自行評估您的合規性狀態。 如有需要，請諮詢您自己的法律及/或專業顧問。 
  
## <a name="a-quick-overview-of-the-gdpr"></a>GDPR 的快速概觀

GDPR 是歐盟法規，為對 1995 年首次制定之較早的資料保護指示 (DPD) 所進行的更新和擴充內容。 GDPR 關心個人資料的隱私權，包括個人用戶端、客戶、員工或商務合作夥伴。 GDPR 的目標是為歐盟公民加強個人資料保護，無論是否身在歐盟國家或其他地方。 此法規會設定期望，並建議您如何達成這些期望。 組織必須擁有符合 GDPR 要求之措施。
  
GDPR 的重點在於資料及其使用方式。 假想資料具有其生命週期，進行思考。 該週期從您收集資料時開始、在您儲存並使用 (處理) 時持續存在，而當您從系統中將之完全刪除時結束。 
  
GDPR 與下列類型的資料類型有關： 
  
- **個人資料：** 如果您可以將資料連結至個人並加以識別，那麼該資料就 GDPR 規定而言，會被視為個人資料。 個人資料的範例包括名稱、地址、出生日期和 IP 位址。 GDPR 甚至會將編碼資訊 (也稱為「假名」資訊) 視為個人資料，無論該資料有多模糊或多具技術性，亦不論該資料是否可連結至個人。
    
- **敏感性個人資料** 這是為個人資料新增更多詳細資料的資料。 範例包括宗教、貿易聯盟成員資格、種族本源等等。 敏感性個人資料也包含生物特徵辨識資料和 DNA。 在 GDPR 規定下，敏感性資料的保護規則比個人資料更嚴格。 
    
## <a name="gdpr-terms"></a>GDPR 條款

在 GDPR 規定中，您會看到一些經常用以參照的條款。 瞭解這些條款很重要。
  
 **同意**
  
GDPR 指出：「處理個人資料應以服務人類為目的進行設計。」 GDPR 希望在處理個人資料時，使用同意書來達成此目標。 這可以是詢問客戶是否要接收來自您公司的電子郵件訊息的簡單行為。 這也表示當您想要使用資料進行行銷時，您的網站上便不會再顯示出選退核取方塊。 您必須使用「明確肯定的動作」以取得明確同意。 此外，您也需要保留取得或撤銷同意的記錄。
  
 **資料主體權利**
  
GDPR 會建立資料主體權利，即該權利在針對其個人資料，客戶、員工、商業合作夥伴、用戶端、承包商、學生、供應商等等上，有權：
  
- **收到其資料相關通知：** 您必須通知個人您對其資料的使用方式。 
    
- **獲得其資料存取權：** 您必須給予個人對於您所保留的其一切資料的存取權 (例如，透過使用帳戶存取或以某種手動方式進行存取)。 
    
- **要求資料修正：** 個人可以要求您修正不正確的資料。 
    
- **要求刪除資料：** 也稱為「清除權」，此權利允許個人要求公司在所有使用或共用其個人資料的系統上刪除其所收集的任何個人資料。 
    
- **要求受限處理：** 個人可以要求您隱藏或限制其資料。 不過，這只適用于特定情況。 
    
- **具有資料可攜性：** 個人可以要求將其資料轉移到另一家公司。 
    
- **反對：** 個人可以反對其資料被用於各種用途，包括直接行銷。 
    
- **要求不受制於自動化決策的規範，包括分析：** GDPR 對於使用資料來分析人員，以及根據該分析自動化決策有嚴格的規定。 


## <a name="steps-to-prepare-for-gdpr"></a>準備 GDPR 的步驟

本節說明小型企業可採取哪些步驟，協助其做好 GDPR 的準備。 這些步驟大部分的資訊是透過 [七個讓企業準備好使用 [一般資料保護規定] 的步驟](https://ec.europa.eu/info/sites/default/files/ds-02-18-544-en-n.pdf)所提供，這是歐盟出版物辦公室所提供的出版物。

小型企業開始使用 GDPR 的一個良好方式，是務必在收集個人資料時，採用下列主要原則：

- 收集具有明確定義之用途的個人資料，且勿將之用於其他用途。 例如，如果您請客戶提供他們的電子郵件地址，以便他們能收到您的新優惠或促銷資訊，則您只能將他們的電子郵件地址用於該特定用途。
- 請勿收集超過您所需的資料內容。 例如，如果您的公司需要郵寄地址來遞送商品，則您需要客戶的地址和名稱，但並不需要知道該客戶的婚姻狀況。


### <a name="step-1-know-the-personal-data-that-you-collect-and-use-within-your-business-and-the-reasons-you-need-it"></a>步驟 1：瞭解您於企業內所收集和使用的個人資料，以及您需要它的原因

做為小型企業，您應該採取的第一個步驟是將您在企業內所收集和使用的個人資料列成一份清單，並包含需要這些資料的原因。 這包括您員工和客戶的資料。

例如，根據雇用合約和法律因素 (例如，向美國國內稅務局報稅)，您可能需要的員工個人資料。

另一個範例是，您可以管理個別客戶清單，以傳送特殊優惠通知給對方 (如果得到其同意的話)。

#### <a name="microsoft-365-features-that-can-help"></a>可用以協助的 Microsoft 365 功能
[Microsoft 365 中的 Microsoft 資訊保護](/microsoft-365/compliance/information-protection) 可協助您於公司中探索、分類並保護敏感性資訊。 您可以使用可訓練分類器來協助識別並標示包含個人資料的檔案類型。 

### <a name="step-2-inform-your-customers-employees-and-other-individuals-when-you-need-to-collect-their-personal-data"></a>步驟 2：當您需要收集其個人資料時，請通知您的客戶、員工和其他個人

個人必須知道您會如何處理其個人資料，及其用途。 例如，如果客戶需要建立客戶設定檔以存取您公司的線上網站，請確保您明確說明了您打算如何使用其資訊。

但是，若個人已知道您將如何使用其資料時，則無須另行通知。 例如，當他們提供您其訂購商品之遞送住家住址時。

您也必須能夠在個人要求時，告知其您所保留的個人資料之資訊，並給予其存取其資料的權限。 如有需要，使用您的資料進行組織，可以更輕鬆地向其提供資料。 

### <a name="step-3-keep-personal-data-for-only-as-long-as-necessary"></a>步驟 3：僅在必要時保留個人資料

對於員工資料，只要雇用關係仍然存在，以及因應相關的法律義務仍然存續，則保留其資料。
對於客戶資料，只要客戶關係持續，以及相關的法律義務 (例如，稅務目的) 仍然存續，則保留其資料。
當收集資料的目的已不再需要該資料時，請刪除該資料。

#### <a name="microsoft-365-features-that-can-help"></a>可用以協助的 Microsoft 365 功能
[保留原則和標籤](/microsoft-365/compliance/retention) 可用來協助您將個人資料保留一段時間，並刪除不再需要的資料。


### <a name="step-4-secure-the-personal-data-you-are-processing"></a>步驟 4：保護您處理中個人資料之安全

如果您將個人資料儲存在 IT 系統上，請限制對包含資料的檔案之存取，例如，使用強式密碼。 定期更新系統的安全性設定。

> [!NOTE]
> GDPR 沒有規定使用特定的 IT 系統，但規定系統應具有適當的安全性層級。 請參閱 [[GDRP 文章 32：處理安全性]](https://gdpr.eu/article-32-security-of-processing/) 以獲得詳細資訊。

如果您使用個人資料儲存實體文件，請確保未經授權的人員無法存取這些文件。

如果您選擇將個人資料儲存在雲端 (例如透過 Microsoft 365)，則您具備安全性功能，例如可協助管理檔案和資料夾的許可權、集中式安全位置以儲存檔存檔案 (OneDrive 或 SharePoint 文件庫)，以及傳送或取回檔案時的資料加密。 

#### <a name="microsoft-365-features-that-can-help"></a>可用以協助的 Microsoft 365 功能
您可以使用 [Microsoft 資料外洩防護 (DLP)](/microsoft-365/business-video/set-up-dlp) 來協助保護您公司的敏感性資訊。 您可以 [設定使用 [GDPR 範本](/microsoft-365/compliance/what-the-dlp-policy-templates-include#general-data-protection-regulation-gdpr) 的 DLP 原則](/microsoft-365/compliance/create-a-dlp-policy-from-a-template)。

### <a name="step-5-keep-documentation-on-your-data-processing-activities"></a>步驟 5：在資料處理活動中保留文件

準備簡短文件，說明您保留哪些個人資料以及保留之原因。 您可能需要將文件提供給您的國家資料保護授權單位 (如有必要)。

這類文件應包含下列資訊。

| 資訊 | 範例 |
|---|---|
|資料處理之目的|提醒客戶特殊優惠，例如提供住家遞送服務；支付供應商；員工的薪資和社會保險涵蓋範圍|
|個人資料類型|客戶的連絡人詳細資料；供應商的連絡人詳細資料；員工資料|
|相關資料主體的類別|員工；客戶；供應商|
|收件者類別|勞工機構；稅務機關|
|儲存期間|員工個人資料，直到雇用合約 (以及相關的法律義務) 結束；客戶個人資料，直到客戶/合約關係結束|
|技術和組織安全性措施來保護個人資料|IT 系統解決方案會定期更新；安全位置；存取控制；資料加密；資料備份|
|個人資料是否傳輸給歐盟以外的收件者|使用歐盟外的處理器 (例如雲端中的儲存空間)；處理器的資料位置；合約承諾|

</br>

您可以在 [Microsoft Online Services 資料保護增訂合約](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=2&Keyword=DPA)中尋找 Microsoft 對於 GDPR 的合約承諾，該合約提供 Microsoft 的隱私權和安全性承諾、資料處理條款，以及客戶根據大量授權合約訂閱之 Microsoft 託管服務的 GDPR 條款。 


### <a name="step-6-make-sure-your-subcontractors-respect-the-rules"></a>步驟 6：確定您的轉包商遵守規則

如果您將個人資料的處理轉包給另一家公司，請只使用保證處理符合 GDPR 要求 (例如，安全措施) 的服務提供商。 



### <a name="step-7-assign-someone-to-oversee-personal-data-protection"></a>步驟 7：指派人員監督個人資料保護
 
為了加良好地保護個人資料，組織可能需要指派 <b>資料保護長 (DPO)</b>。 不過，如果處理個人資料不是您企業的核心部分，或者如果您是小型企業，您可能不需要指定資料保護長。 例如，如果您的公司只會收集客戶的資料以進行住家遞送服務，則無須指派 DPO。 即使您需要使用 DPO，這些職責也可以分配給現有員工，作為他/她的額外工作。 或者，您也可以選擇在該作業需要時，雇用外部顧問負責此工作。

您通常不需要執行 [[資料保護影響評估]](https://gdpr.eu/article-35-impact-assessment/)。 這是為那些對個人資料構成更大風險的企業所預留的功能 (例如，如果他們對可公開進入的區域進行大規模監控，例如視訊監控)。

如果您是管理員工薪資和用戶端清單的小型企業，則通常不需要執行 [資料保護影響評估]。  
 

    
## <a name="common-small-business-questions-about-the-gdpr"></a>關於 GDPR 的小型企業常見問題

### <a name="im-a-sole-proprietor---do-i-really-have-to-worry-about-the-gdpr"></a>我是單人公司，我是否真的有必要擔心 GDPR？

GDPR 的重點在於您所處理的資料，而非您所擁有的員工數目。 它會影響各種規模的公司，甚至是單人公司。 不過，員工人數少於 250 人的公司有一些豁免權利，例如減少記錄保留，但只有在您確定資料處理不會影響個人的權利且偶爾處理時。
  
例如，處理非個人資料的處理會豁免或需要減少措施。 不過，如果您處理任何被視為「特殊類別敏感性資料」的資料，則即使只是偶爾處理，您也必須記錄此資料處理。 「偶爾處理」的定義模糊不清，但應為一次性或很少使用的資料。
  
您也應該確定您所收集的個人資料受到保護。 這表示您需要對之進行加密，並確保至少使用密碼控制該資料的存取權。 將客戶資料保留在桌面的試算表中，而沒有保護措施，並不符合 GDPR 的期望。 
  
### <a name="how-can-i-tell-if-our-company-website-is-gdpr-compliant"></a>如何判斷公司網站是否符合 GDPR 規範？

要詢問自己的第一個問題是：您是否在網站的任何位置進行個人資料之收集？ 例如，您可能有一個要求姓名和電子郵件地址的連絡人表單。 如果您想要傳送行銷電子郵件，請確定您新增了一個能確切說明資料用途的「選入」核取方塊。 只有在收件者勾選該方塊時，您才能將他們的個人資料用於行銷用途。
  
此外，請檢查儲存資料的資料庫是否受到保護。 您的網站主機服務公司或雲端儲存空間廠商將可以提出此建議。 如果您使用 Microsoft 365 商務版，則儲存資料符合 GDPR 規範。 
  
### <a name="my-company-is-outside-europe-does-the-gdpr-really-affect-us"></a>我的公司位於歐洲以外地區。 GDPR 真的會影響到我們嗎？

GDPR 是保護歐盟公民的法規。 如果您的公司現在有與歐盟公民的交易，或您希望未來能與之交易，則會受到影響。 這適用于居住在歐盟國家與其他地方的歐盟公民。
  
請考慮下列範例：
  
- 一家向歐盟公民出租汽車的美國公司，在收集和處理客戶資料時，必須滿足 GDPR 要求。 當公司取得客戶的資料時，公司必須取得同意，並確保該資料安全地儲存。 他們也需要確保客戶可以套用其所有的資料主體權利。 
    
- 一家澳大利亞公司在線上銷售產品，而其使用者設定了線上帳戶。 GDPR 資料主體權利與同意將適用于開立了帳戶的歐盟公民。 該公司需要確保客戶可以套用其所有的資料主體權利。 
    
- 國際慈善組織會收集捐贈者的相關資料，並使用它來傳送更新和捐贈要求。 GDPR 聲稱：「...為直接行銷目的處理個人資料，可能會被視為出於合法利益而執行。」 不過，組織有責任證明他們的利益高於資料主體的利益。 公司 (或在此案例中為慈善組織) 務必應獲得知情、明確、選入性的同意。
    
如果客戶資料跨越邊界，則 GDPR 仍然適用。 如果您使用雲端運算來儲存資料，您必須確定服務完全符合 GDPR 規範。 如果資料儲存在資料保護記錄不佳的位置，情況可能會變複雜。 如果您使用 Microsoft 365 商務版，我們有正確的法律文件可涵蓋 GDPR 要求。
  
### <a name="sure-i-collect-data-but-some-other-company-stores-it-does-that-get-me-off-the-hook"></a>當然，我收集資料，但有些公司則會儲存資料。 這是否能讓我免於要求規範？

在 GDPR 規定下，如果您收集資料，您便會受到某種程度的影響。 GDPR 具有資料處理者和資料控制者的概念： 
  
- **資料控制者** ：由個人或組織 (您可以擁有聯合控制者) 決定資料收集之方式、內容及原因。 他們可能會使用另一家公司的雲端伺服器來儲存該資料。 例如，收集客戶資料的網站就是資料控制者。 
    
- **資料處理者：** 代表控制者儲存資料並根據要求處理這些資料的個人或組織。 例如，Microsoft 365 Apps 商務版資料儲存區可做為資料處理者，並且完全符合 GDPR 規範。 
    
    組織或系統可以同時做為資料控制者與資料處理者。 Microsoft 365 商務版可以同時做為兩者使用，並符合 GDPR 規範。
    
### <a name="can-i-still-send-out-marketing-emails-to-my-old-customers"></a>我仍然可以傳送行銷電子郵件給我的舊客戶嗎？

您必須確認您的客戶 (即使是多年老客戶) 已同意您使用其資料進行行銷。 您可能先前已取得同意，並具有記錄可顯示。 若是如此，您即可放心繼續行銷動作。 若非如此，則您必須取得客戶的許可權，才能繼續向該客戶進行行銷動作。 這通常涉及傳送電子郵件，要求客戶前往您的網站，並選取一個選項以同意收取之後的電子郵件。 
  
### <a name="do-i-have-to-worry-about-the-gdpr-when-i-recruit-new-employees-what-about-current-employees"></a>當我招募新員工時，是否需擔心 GDPR？ 那麼目前的員工呢？

GDPR 不只會影響客戶資料；其影響範圍也會延伸至員工資料。 新進員工通常是透過社交媒體平臺 (例如，LinkedIn) 招募。 請確定您未在未經其明確許可的情況下儲存任何潛在的招募資料。
  
對於現有員工和新員工合約，在合約末尾簽章不一定即表示同意，尤其是在合約中使用非肯定條款時。 在這種情況下，您必須以與該條款相關的明確方式取得其同意。 其取決於您的員工合約，但在某些情況下，您可以使用「合法利益」，並新增員工資料處理通知，以確保員工知道您將如何處理其資料。
  
## <a name="satisfy-privacy-concerns-using-microsoft-365-for-business"></a>使用 Microsoft 365 商務版，滿足隱私權問題

符合 GDPR 的規範是為確保個人資料受到保護。 GDPR 有一個被稱為「設計和預設隱私權」的概念。 這表示資料保護應該被「嵌入」到系統和產品中，如此一來，滿足隱私權問題才能自然成為其第二功能。 
  
與較大的企業一樣，小型企業需要在不犧牲安全性的情況下，獲有便利性。 Microsoft 365 商務版專為少於 300 名員工的公司所設計。 小型公司可以使用 Microsoft 雲端式工具來改善商務生產力。 使用 Microsoft 365 商務版，小型企業便可以管理電子郵件、文件，甚至是會議和活動。 它也有內建的安全性措施和裝置管理，這對於 GDPR 合規性至關重要。
  
Microsoft 365 商務版可以下列方式協助您進行 GDPR 流程：
  
- **探索：** GDPR 合規性的重要步驟是瞭解您所擁有的資料。 
    
- **管理：** 控制資料存取權和管理其使用方式是 GDPR 中不可或缺的一部分。 Microsoft 365 商務版會根據您想要套用至裝置的原則來保護商務資料。 在員工紛紛遠端工作的時代，裝置管理非常重要。 Microsoft 365 商務版包含裝置管理功能，確保資料在所有裝置上都受到保護。 例如，您可以指定公司中所有的 Windows 10 裝置都透過 Windows Defender 受到保護。 
    
- **保護：** Microsoft 365 商務版專為安全性所設計。 其裝置管理和資料保護控制可在整個企業網路 (包括遠端裝置) 上使用，協助確保資料安全。 Microsoft 365 商務版提供控制項，例如 Office 應用程式中的隱私權設定和文件加密。 使用 Microsoft 365 商務版，您可以執行 GDPR 合規性監控，以確保您設定了正確的保護層級。 
    
- **報告：** GDPR 非常強調報告。 即使是僅有單一員工的企業，如果該企業處理大量資料，一樣需要記錄並報告其程序。 Microsoft 365 商務版可省去較小型組織的報告要求。 
    
    稽核記錄等工具允許您追蹤及報告資料移動。 報告包括對您所收集和儲存的資料、資料的用途，以及資料的傳輸進行分類。 
    
客戶、員工和用戶端越來越瞭解資料隱私權的重要性，現在也希望公司或組織能尊重其隱私權。 Microsoft 365 商務版提供您在不為業務帶來巨大變化的情況下，達成和維護 GDPR 合規性所需的工具。



## <a name="next-steps"></a>後續步驟

若要準備好開始使用 GDPR，以下是一些要採取之後續步驟的建議：
  
- 使用 [責任整備檢查清單](/compliance/regulatory/gdpr-arc) 評估您的 GDPR 計劃。
    
- 調查 [Microsoft 365 商務版](/microsoft-365/business) ，以作為達成和維護 GDPR 合規性的解決方案。 
   

> [!IMPORTANT]
> 取得適合您公司或組織的法律建議。
  
## <a name="additional-resources"></a>其他資源

[Microsoft 信任中心 GDPR 概觀](https://www.microsoft.com/trust-center/privacy/gdpr-overview
)
  
官方 Microsoft 部落格： [Microsoft 對 GDPR 的承諾](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/)
  
歐盟委員會網站：
  
- [資料保護](https://ec.europa.eu/info/law/law-topic/data-protection)
    
- [2018 年歐盟資料保護規則改革](https://ec.europa.eu/commission/priorities/justice-and-fundamental-rights/data-protection/2018-reform-eu-data-protection-rules)
