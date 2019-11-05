---
title: 在 Microsoft Teams 中保護檔案
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: 摘要：在 Microsoft Teams 中保護檔案的設定建議。
ms.openlocfilehash: 1b4d5205836337b02c831341d5de65a87dba6fc5
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925752"
---
# <a name="secure-files-in-microsoft-teams"></a>在 Microsoft Teams 中保護檔案

本文提供在 Microsoft Teams 中設定小組及其基礎 SharePoint 網站，以在兼顧安全性與共同作業順暢性的前提下進行檔案保護的建議。 本文定義四種不同的設定，首先是組織內的公用網站，並搭配最開放的共用原則。 每項額外設定均代表有意識的保護升級，但對 Teams 內儲存的檔案進行存取和共同作業的能力，則會減少為僅限相關小組成員。 您可以使用這些建議作為起點，並依據組織需求調整設定。 
  
本文的設定符合 Microsoft 針對資料、身分識別和裝置的下列三層保護建議：
  
- 基準保護
    
- 敏感性保護
    
- 高度機密保護
    
如需這些層級和每道層級的建議功能詳細資訊，請參閱下列資源。 
  
- [Office 365 的身分識別與裝置保護](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#BKMK_O365IDP)
    
- [Office 365 的檔案保護方案](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#BKMK_O365fileprotect)
    
## <a name="capability-overview"></a>功能概觀

針對受保護的小組而提供的建議，依據各種不同 Microsoft 365 功能而定。 下圖顯示建議的設定。

![小組的建議設定](../media/secure-team-configurations.png)

如圖例所示：
  
- 基準保護包含公開小組和私人小組。 公開小組可供組織中的任何人探索及存取。 私人小組則僅供小組成員探索及存取。 這兩種設定都允許共用將檔案儲存在小組群組以外的基礎 SharePoint 網站。
 
- 敏感且受高度機密保護的小組是私人小組，此處會限制基礎網站的共用和存取要求。

    
- [保留標籤](../../compliance/labels.md)可用來分類基礎 SharePoint 網站內的檔案。 每個基礎 SharePoint 網站都會設為自動替文件庫中的檔案加上預設保留標籤。 此範例的標籤對應到四種小組網站設定，分別是「內部公開」、「私人」、「敏感性」與「高度機密」。 使用者可以變更個別檔案的標籤，但這種設定可確保所有檔案都收到預設標籤。
    
- 系統會針對「敏感性」和「高度機密」的保留標籤設定[資料外洩防護](../../compliance/data-loss-prevention-policies.md) (DLP) 原則，以在使用者嘗試將這類檔案傳送到組織外部時，對他們發出警告或阻止此動作。
    
- 如果在您的案例中有需要，您可以使用[敏感度標籤](../../compliance/sensitivity-labels.md)以使用加密與權限來保護高度機密檔案。 針對 Azure 資訊保護客戶，您可以使用 Microsoft 365 合規性中心的 Azure 資訊保護標籤，而如果您選擇執行額外或進階組態，標籤就會與 Azure 入口網站同步處理。 Azure 資訊保護標籤與 Office 365 敏感度標籤完全彼此相容。 這表示，比方說，如果您有使用 Azure 資訊保護加上標籤的內容，則不需將內容重新分類或重新加上標籤。 並非所有客戶都需要此層級的保護。 
    
## <a name="organization-wide-settings-for-sharepoint-and-onedrive"></a>SharePoint 和 OneDrive 的全組織設定

SharePoint 和 OneDrive 包含對所有網站與使用者皆有影響的全組織設定。 其中某些設定可以於網站層級進行調整，使其更加嚴格 (但不能更寬鬆)。 本節說明會影響安全性與共同作業的租用戶整體設定。 
  
### <a name="sharing"></a>共用

針對這個解決方案，我們建議使用下列全組織設定：
  
- 保留預設共用原則，以允許所有帳戶類型的共用作業，包括匿名共用。
    
- 您可視需要將匿名的連結設為過期。
    
- 將共用的預設連結類型變更為「內部」。 這有助於防止資料不慎洩漏到組織外部。
    
雖然允許外部共用似乎有悖常理，但相較於以電子郵件傳送檔案，此方法可以更充分地掌控檔案共用情況。 SharePoint 與 Outlook 一起運作，以提供安全的檔案共同作業。 
  
- 根據預設，Outlook 會共用檔案的連結，而非以電子郵件傳送檔案。 
    
- SharePoint 和 OneDrive 可讓您輕易地與組織內外的參與者共用檔案連結
    
您也可以使用相關控制來協助控管外部共用。 例如，您可以：
  
- 停用匿名訪客的連結。
    
- 撤銷使用者的網站存取權。
    
- 查看誰具有特定網站或文件的存取權。
    
- 將匿名共用連結設為過期 (租用戶設定)。
    
- 限制可在組織外部共用的人員 (租用戶設定)。
    
### <a name="use-external-sharing-together-with-data-loss-prevention-dlp"></a>搭配使用外部共用與資料外洩防護 (DLP)

如果您不允許外部共用，有業務需求的使用者就必須找到替代工具和方法。Microsoft 建議您結合外部共用與 DLP 原則來保護敏感性與高度機密檔案。
  
### <a name="device-access-settings"></a>裝置存取設定

SharePoint 和 OneDrive 的裝置存取設定可讓您決定要僅限瀏覽器存取 (無法下載檔案)，或是封鎖存取。 如需詳細資訊，請參閱[控制未受管理裝置的存取權](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)。 

若要使用裝置存取設定搭配 Azure Active Directory 中建議的條件式存取原則，請參閱[保護 SharePoint 網站和檔案的原則建議](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)。
  
請瀏覽這些設定，以決定是否要變更 OneDrive 的網站預設設定。 目前，會複製 SharePoint 系統管理中心的共用和裝置存取設定，並套用到這兩個環境。
  
## <a name="team-and-sharepoint-site-configuration"></a>小組和 SharePoint 網站設定

下表摘要說明本文先前所述的每個小組及其基礎 SharePoint 網站的設定。 您可以使用這些設定作為建議的起點，並依據組織需求調整網站類型與設定。 並非每個組織都需要所有類型的小組。 只有少數組織的小組會需要高度機密的保護。
  
||||||
|:-----|:-----|:-----|:-----|:-----|
||**基準保護 #1** <br/> |**基準保護 #2** <br/> |**敏感性保護** <br/> |**高度機密** <br/> |
|描述  <br/> |開放給組織內部探索及共同作業的公開小組。  <br/> |允許群組外部共用基礎 SharePoint 網站的私人小組。  <br/> |僅允許網站成員共用基礎 SharePoint 網站的私人小組。 當使用者嘗試將檔案傳送到組織外部時，DLP 會對其發出警告。  <br/> |檔案會隨附敏感度標籤以進行加密和權限授與的私人小組。 DLP 可防止使用者將檔案傳送到組織外部。  <br/> |
|私用或公用的小組網站  <br/> |公用  <br/> |Private  <br/> |Private  <br/> |Private  <br/> |
|誰可以存取？  <br/> |組織中所有人，包括 B2B 使用者。  <br/> |僅限網站的成員。 其他人可以要求存取權。  <br/> |僅限小組的成員。 其他人可要求存取基礎網站，由小組擁有者核准。  <br/> |僅限成員。 其他人無法要求存取基礎網站。  <br/> |
|網站層級的共用控制  <br/> |允許與任何人共用。 預設設定。  <br/> |允許與任何人共用。 預設設定。  <br/> |成員無法共用網站的存取權。  <br/> 非成員可要求存取網站，但這些要求需由小組的群組擁有者處理。  <br/> |成員無法共用網站的存取權。  <br/> 非成員無法要求存取網站或其內容。  <br/> |
|網站層級的裝置存取控制  <br/> |無額外控制。  <br/> |無額外控制。  <br/> |防止使用者下載檔案到不相容或非加入網域的裝置。如此一來，所有其他裝置僅可進行瀏覽器存取。  <br/> |封鎖將檔案下載至不相容或非加入網域的裝置。  <br/> |
|保留標籤  <br/> |內部公用  <br/> |Private  <br/> |敏感性  <br/> |高度機密  <br/> |
|DLP 原則  <br/> |||當使用者將標記為「敏感性」的檔案傳送到組織外部時，會對其發出警告。  <br/> 若要封鎖敏感性資料類型的外部共用，例如信用卡號碼或其他個人資料，您可以為這些資料類型 (包括您設定的自訂資料類型) 設定額外的 DLP 原則。  <br/> |封鎖使用者，使其無法將標示為高度機密的檔案傳送到組織外部。 允許使用者提供理由來覆寫這項預設，包括共用檔案的對象。  <br/> |
|敏感度標籤  <br/> ||||使用敏感度標籤可為檔案加密並授與其權限。 這項保護會隨附於檔案，以防檔案從基礎 SharePoint 網站中外洩。  <br/> |
   
如需此解決方案中四種不同小組類型的部署步驟，請參閱[部署三種檔案保護層級的小組](deploy-teams-three-tiers.md)。
  
## <a name="office-365-retention-labels"></a>Office 365 保留標籤

建議您在含有敏感性資料的環境中使用保留標籤。 設定並發佈保留標籤之後：
  
- 您可以將預設標籤套用至某小組的基礎 SharePoint 網站中的文件庫，讓該小組的 [檔案]**** 區段中所有的文件都具有預設標籤。 
    
- 您可以自動將標籤套用到內容 (如果內容符合特定條件的話)。
    
- 您可以套用以保留標籤為基礎的 DLP 原則。
    
- 組織中的人員可手動將標籤套用至 Outlook 網頁版、Outlook 2010 和更新版本、OneDrive、SharePoint 和 Office 365 群組中的內容。 使用者通常最清楚自己使用的內容類型，因此可以對其分類並套用適當的 DLP 原則。
    
如圖例所示，此解決方案包括建立下列保留標籤：
  
- 高度機密
    
- 敏感性
    
- Private
    
- 內部公用
    
這些標籤會對應到本文稍早的圖例與圖表中的建議網站。此解決方案建議您設定 DLP 原則，以協助避免標示為「敏感性」和「高度機密」的檔案外洩。
  
如需在此解決方案中設定保留標籤和 DLP 原則的步驟，請參閱[使用保留標籤與 DLP 來保護小組中的檔案](deploy-teams-retention-DLP.md)。
  
## <a name="sensitivity-labels"></a>敏感度標籤 

若您的安全性案例有需要，您可以使用敏感度標籤來套用可隨時追蹤檔案的保護。 Microsoft 365 合規性中心的敏感度標籤和 Azure 資訊保護標籤是相同的。 採用此解決方案時，建議您使用敏感度標籤或子標籤，來加密需要以最高安全性層級保護的檔案，和授與其權限。 

如需詳細資訊，請參閱[敏感度標籤概觀](../../compliance/sensitivity-labels.md)。

如需在此解決方案中設定敏感度標籤的步驟，請參閱[使用靈敏度標籤保護小組中的檔案](deploy-teams-sensitivity-labels.md)。
   
   
## <a name="see-also"></a>另請參閱
  
[雲端採用和混合式解決方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
