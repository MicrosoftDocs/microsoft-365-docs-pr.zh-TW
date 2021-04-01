---
title: 了解敏感度標籤
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 使用 Microsoft 資訊保護 (MIP) 中的敏感度標籤，以分類及保護機密內容。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: a540529c174cc12b0e037be4af4e08c29e3835ea
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408598"
---
# <a name="learn-about-sensitivity-labels"></a>了解敏感度標籤

>*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

> [!NOTE]
> 如果您要尋找在 Office 應用程式中看到的敏感度標籤相關資訊，請參閱[在 Office 中將敏感度標籤適用於您的檔案和電子郵件](https://support.microsoft.com/topic/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)。
>
> 此頁面上的資訊適用於可建立及設定這些標籤的 IT 系統管理員。

為了完成其工作，組織中的人員會與組織內外的其他人員共同合作。這表示內容不再會停留在防火牆後，它會漫遊在裝置、應用程式和服務的各處。而當內容漫遊時，您會希望以符合組織的商務及合規性原則的安全、受保護的方式漫遊。

來自 Microsoft 資訊保護解決方案的敏感度標籤可讓您分類及保護組織的資料，同時確保使用者生產效率和共同作業能力不受影響。

顯示 Excel 中可用敏感度標籤的範例，從功能區上的 [首頁 **]** 索引標籤。 在此範例中，已套用的標籤會顯示在狀態列上：

![Excel 功能區和狀態列上的敏感度標籤](../media/Sensitivity-label-in-Excel.png)

若要套用敏感度標籤，使用者必須使用 Microsoft 365 公司或學校帳戶登入。

> [!NOTE]
> 針對美國政府租用戶，敏感度標籤[現在支援 GCC 和 GCC High 環境](/officeupdates/current-channel#version-2101-january-26)，並且目前正針對 DoD 環境推出。
>
> 如果您對這些環境使用 Azure 資訊保護的整合式標記用戶端和掃描器，請參閱 [Azure 資訊保護 Premium 政府服務描述](/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)。

您可以使用敏感度標籤來：
  
- **提供包含加密和內容標記的保護設定。** 例如，將「機密」標籤套用至文件或電子郵件，而該標籤會將內容加密並套用「機密」浮水印。 內容標記包括頁首、頁尾以及浮水印，而加密也可以限制授權人員可對內容採取的動作。

- **保護不同平台和裝置之間 Office 應用程式中的內容。** Word、Excel、PowerPoint 和 Office 桌面應用程式和 Office 網頁版 Outlook 皆支援該功能。 支援 Windows、macOS、iOS 和 Android。

- 使用 Microsoft Cloud App Security **保護第三方應用程式和服務中的內容**。 使用 Cloud App Security，您可以偵測、分類、標記並保護協力廠商應用程式和服務中的內容，例如 SalesForce、Box 或 DropBox，即使協力廠商應用程式或服務無法讀取或支援敏感度標籤亦然。

- **保護容器**，其中包括 Teams、Microsoft 365 群組和 SharePoint 網站。 例如，設定隱私權設定、外部使用者存取和外部共用，以及從未受管理的裝置存取。

- **將敏感度標籤延伸至 Power BI**：當您開啟此功能時，您可以套用和查看 Power BI 標籤，並在資料儲存在服務以外時加以保護。

- **將敏感度標籤延伸至 Azure Purview 中的資產**：開啟目前處於預覽的此功能時，您可以將敏感度標籤套用至資產，例如 SQL 資料行、Azure Blob 儲存體中的檔案等等。 

- **將敏感度標籤延伸至第三方應用程式和服務。** 使用 Microsoft 資訊保護 SDK，第三方應用程式就可以讀取敏感度標籤以及套用保護設定。

- **不使用任何保護設定而將內容分類。** 您也可以直接指派標籤，以分類內容。 這可讓使用者以視覺方式將分類對應到貴組織的標籤名稱，而且可以使用標籤來產生使用狀況報告，並查看您機密內容的活動資料。 根據這項資訊，您一律可以選擇稍後套用保護設定。

在上述情況下，Microsoft 365 中的敏感度標籤可協助您對正確的內容採取適當的動作。 您可以運用敏感度標籤分類組織的資料，並根據該分類強制執行保護設定。

如需有關這些和敏感度標籤支援之其他案例的詳細資訊，請參閱 [敏感度標籤的常見案例](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels)。 我們目前正在開發支援敏感度標籤的新功能，因此您可能會認為 [Microsoft 365 藍圖](https://aka.ms/MIPC/Roadmap) 參照資料非常有用。

## <a name="what-a-sensitivity-label-is"></a>敏感度標籤是什麼

當您將敏感度標籤指派給內容時，它就像一個套用的戳記，並且是：

- **可自訂。** 針對貴組織和商務需求，您可以針對組織中的不同敏感度內容之層級建立類別。 例如，個人、公開、一般、機密和高度機密。

- **純文字。** 由於標籤會以純文字形式儲存在檔案和電子郵件的中繼資料中，因此第三方應用程式和服務可以讀取它，然後套用自己的保護動作 (如必要)。

- **持續性。** 由於標籤會儲存在檔案和電子郵件的中繼資料中，因此無論儲存位置或存放處為何，標籤都會與內容相伴儲存。 唯一的標籤識別碼會成為套用並強制執行您設定之原則的基礎。

當使用者進行查看時，敏感度標籤會以標籤形式顯示在所使用的應用程式上，並可輕鬆整合至現有的工作流程。

支援敏感度標籤的每個項目都可以套用單一敏感度標籤。 文件和電子郵件可以同時套用敏感度標籤和[保留標籤](retention.md#retention-labels)。

> [!div class="mx-imgBorder"]
> ![套用至電子郵件的敏感度標籤](../media/Sensitivity-label-on-email.png)

## <a name="what-sensitivity-labels-can-do"></a>敏感度標籤的功能

將敏感度標籤套用至電子郵件或文件後，將會對內容強制執行為該標籤設定的保護設定。 您可以設定敏感度標籤以：

- **加密** 電子郵件和文件，以防止未經授權的人員存取此資料。 您可以另行選擇哪些使用者或群組可以擁有權限來執行哪些動作，以及執行多久。 例如，您可以選擇允許貴組織中的所有使用者修改文件，而另一個組織中的特定群組只能瀏覽該文件。 或者，可以讓使用者在套用標籤時，指派權限給內容，而不要使用系統管理員定義的權限。 
    
    如需建立或編輯敏感度標籤時 **加密** 設定的詳細資訊，請參閱 [使用敏感度標籤中的加密來限制內容的存取](encryption-sensitivity-labels.md)。

- 將浮水印、頁首或頁尾新增至已套用標籤的電子郵件或文件，以在使用 Office 應用程式時 **標記內容**。 浮水印可以套用至文件 (而非電子郵件)。 頁首和浮水印範例：
    
    ![套用至文件的浮水印和頁首](../media/Sensitivity-label-watermark-header.png)
    
    需要檢查何時套用內容標記？ 請參閱 [Office 應用程式何時套用內容標記和加密](sensitivity-labels-office-apps.md#when-office-apps-apply-content-marking-and-encryption)。
    
    某些 (但並非全部) 應用程式會使用變數來支援動態標記。 例如，將標籤名稱或文件名稱插入頁首、頁尾或浮水印。 如需詳細資訊，請參閱[使用變數動態標記](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)。
    
    字串長度：浮水印限制為 255 個字元。 頁首和頁尾均受限於 1024 個字元，但 Excel 除外。 對於頁首及頁尾，Excel 的總限制為 255 個字元，但此限制包含看不見的字元，例如格式代碼。 如果達到該限制，您輸入的字串就不會顯示在 Excel 中。

- 當您啟用功能，以 [在 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中使用敏感度標籤](sensitivity-labels-teams-groups-sites.md)時，**保護容器中的內容，例如網站和群組**。
    
    您無法設定群組和網站的保護設定，除非您啟用此功能。 此標籤設定並不會導致文件或電子郵件自動加標籤，相反的，標籤設定會透過控制可儲存內容所在容器的存取權，以保護內容。 這些設定包括設定隱私權設定、外部使用者存取和外部共用，以及從未受管理的裝置存取。

- **在檔案和電子郵件中自動套用標籤，或建議標籤。** 選擇如何辨識您要標記的敏感資訊，這樣就可以自動套用標籤，或提示使用者套用您建議的標籤。 如果您建議使用某個標籤，提示會顯示您選擇的任何文字。 例如：
    
    ![指派必要標籤的提示](../media/Sensitivity-label-Prompt-for-required-label.png)
    
    如需有關當您建立或編輯敏感度標籤時 **自動標籤檔案和電子郵件** 設定的詳細資訊，請參閱針對 Office 應用程式 [自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)，和 [自動標籤您在 Azure Purview 的資料](/azure/purview/create-sensitivity-label)。

### <a name="label-scopes"></a>標籤範圍

建立敏感度標籤時，系統會要求您設定標籤的範圍，其可決定兩個項目：
- 您可以針對該標籤設定的標籤設定
- 標籤將向使用者顯示的位置

此範圍設定可讓您有僅適用文件和電子郵件的敏感度標籤，而無法為容器選取。 同樣地，僅適用容器的敏感度標籤，亦無法為文件和電子郵件選取。 新增且目前處於預覽的功能，您也可以選取 Azure Purview 資產的範圍：

![敏感度標籤的範圍選項](../media/sensitivity-labels-scopes.png)

預設會一律選取 [檔案和電子郵件 **]** 範圍。 其他範圍則是在為您的租用戶啟用功能時預設選取：

- **群組和網站**：[為容器啟用敏感度標籤以及同步處理標籤](sensitivity-labels-teams-groups-sites.md#how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels)

- **Azure Purview 資產 (預覽)**：[在 Azure Purview 中自動為您的內容加上標籤](/azure/purview/create-sensitivity-label)

如果您變更預設值，使得並未選取所有範圍，則會看到您未選取範圍之組態設定的第一頁，但您無法進行設定。 例如，如果未選取檔案和電子郵件的範圍，您就無法在下一頁選取選項：

![敏感度標籤的無法使用選項](../media/sensitivity-labels-unavailable-settings.png)

針對有無法使用選項的這些頁面，請選取 [下一步 **]** 以繼續。 或者，選取 [上一步 **]** 來變更標籤的範圍。

### <a name="label-priority-order-matters"></a>標籤優先順序 (順序很重要)

在您的系統管理中心中建立敏感度標籤時，它們會顯示在 [標籤] 頁面的 [敏感度] 索引標籤上的清單中。 在此清單中，標籤的順序很重要，因為它反映的是其優先順序。 您想要讓最具限制性的敏感度標籤，例如 [高度機密性]，顯示在清單的最 **底端**，以及最不具限制性的敏感度標籤，例如公用，顯示在最 **上方**。

您只能將一個敏感度標籤套用至一個項目，例如文件、電子郵件或容器。 如果您設定一個選項，要求使用者提供將標籤變更為較低分類的理由，則此清單的順序會識別分類下限。 不過，此選項不適用子標籤。

不過，子標籤的排序會搭配[自動標記](apply-sensitivity-label-automatically.md)使用。 將標籤設定為自動套用或建議時，可能對多個標籤造成相符項目。 若要判斷要套用或建議的標籤，會使用標籤順序：選取最後一個敏感度標籤，然後在適用時使用最後一個子標籤。

![建立子標籤的選項](../media/Sensitivity-label-sublabel-options.png)

### <a name="sublabels-grouping-labels"></a>子標籤 (分組標籤)

您可以使用子標籤將一或多個標籤分組在 Office 應用程式中的使用者可看到的上層標籤之下。 例如，在 [機密文件] 下，您的組織可能會使用不同的標籤來標示該分類的特定類型。 在此範例中，上層標籤 [機密文件] 只是沒有任何保護設定的文字標籤，且因為它有子標籤，所以無法套用至內容。 相反地，使用者必須選擇 [機密文件] 來查看子標籤，然後再選擇要套用到內容的子標籤。

子標籤是以邏輯群組方式向使用者呈現標籤的一個簡單方式。 子標籤不繼承其上層標籤的任何設定。 當您發佈使用者的子標籤時，該使用者就可以將該子標籤套用到內容，但不能只套用上層標籤。

請勿將上層籤選為預設標籤，或將上層標籤設定為自動套用 (或建議使用)。 如果這麼做，系統就不會將上層標籤套用至內容。

子標籤如何對使用者顯示的範例：

![功能區上分組的子標籤](../media/Sensitivity-label-grouped-labels2.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a>編輯或刪除敏感度標籤

如果您從系統管理中心刪除敏感度標籤，此標籤並未從內容中自動移除，且所有保護設定都會繼續在套用該標籤的內容上強制執行。

如果您編輯敏感度標籤，則當初套用至內容的標籤版本會在內容上強制執行。

## <a name="what-label-policies-can-do"></a>標籤原則的功能

建立敏感度標籤之後，您必須發佈這些標籤，才能讓其可供組織中的人員和服務使用。 然後可以將敏感度標籤套用至 Office 文件和電子郵件，以及支援敏感度標籤的其他項目。 

與會發佈到所有 Exchange 信箱之類位置的保留標籤不同，敏感度標籤會對使用者或群組發佈。 支援敏感度標籤的應用程式之後可以將這些標籤，以已套用的標籤或可套用的標籤形式向這些使用者和群組顯示。

當您設定標籤原則時，您可以：

- **選擇可看見標籤的使用者和群組。** 可以在 Azure AD 中將標籤發佈到任何特定的使用者或啟用電子郵件功能的安全性群組、通訊群組或 Microsoft 365 群組 (可以有 [動態成員資格](/azure/active-directory/users-groups-roles/groups-create-rule))。

- **套用預設標籤** 至由標籤原則中包含的所有使用者和群組所建立的新文件和未標籤電子郵件，以及將相同或不同的預設標籤套用至容器 (如果您 [已為 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站啟用敏感度標籤](sensitivity-labels-teams-groups-sites.md))。 使用這項設定，Azure 資訊保護統一標籤用戶端也會將預設標籤套用至未標記的現有文件。 如果使用者的文件或電子郵件不是正確的標籤，使用者可以隨時變更預設標籤。
    
    請考慮使用預設標籤來設定您想套用到所有內容中的基本保護設定等級。 不過，若沒有使用者訓練和其他控制項，這項設定也可能導致不正確的標記。 選取將套用加密作為對文件之預設標籤的標籤並不是個好主意。 例如，許多組織需要將文件傳送與共用給外部使用者，而這些使用者可能沒有支援加密的應用程式，或可能不會使用可授權的帳戶。 如需此案例的詳細資訊，請參閱 [與外部使用者共用加密檔](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users)。

- **需要變更標籤的理由。** 如果使用者嘗試移除標籤，或以較低順序編號的標籤取代其，您可以要求使用者提供理由來執行此動作。 例如，使用者開啟標示為 [機密] (順序編號 3) 的文件，並將該標籤取代為 [公開] (順序編號 1)。 系統管理員可以閱讀 [活動瀏覽器](data-classification-activity-explorer.md) 中的理由及標籤變更。

    ![提示使用者輸入理由](../media/Sensitivity-label-justification-required.png)

- **要求使用者套用標籤**，一個選項用於電子郵件和文件，另一個用於容器。 這些選項也稱為強制標籤，可確保使用者必須先套用標籤才能儲存文件和傳送電子郵件以及建立新群組或網站。
    
    若為文件和電子郵件，使用者可手動指派標籤、根據您設定的條件而自動指派，或依預設指派 (如上所述的預設標籤選項)。 當使用者需要指派標籤時，Outlook 中顯示的提示範例：

    ![Outlook 中的提示，要求使用者套用必要標籤](../media/sensitivity-labels-mandatory-prompt-aipv2-outlook.PNG)
    
    > [!NOTE]
    > 並非所有應用程式或所有平台都提供文件及電子郵件適用的強制標籤。 如需詳細資訊，請參閱[要求使用者在電子郵件和文件中套用標籤](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) (部分機器翻譯)。
    
    若為容器，您必須在建立群組或網站時指派標籤。
    
    請考慮使用此選項來協助增加您的標記涵蓋範圍。 不過，若沒有使用者訓練，這些設定可能導致不正確的標記。 此外，除非您也設定對應的預設標籤，否則強制標籤的常見提示可能會讓使用者感到無益。

- **提供自訂說明頁面的說明連結。** 如果使用者不確定敏感度標籤代表的意義或使用方式，您可以提供顯示在 Office 應用程式中 **[敏感度標籤]** 功能表底部的 [深入了解] URL：

    ![功能區中 [敏感度] 按鈕上的「深入了解」連結](../media/Sensitivity-label-learn-more.png)

建立可將新敏感度標籤指派給使用者和群組的標籤原則之後，使用者會開始在他們的 Office 應用程式中看到這些標籤。 最多可獲得 24 小時的時間，在您的整個組織中複製最新的變更。

您可以建立並發佈的敏感度標籤數量沒有任何限制，但有一個例外：如果標籤套用加密，則您可建立的標籤數上限為 500。 不過，為了降低系統管理負擔並為使用者減少複雜度，最佳做法是試著保持最少的標籤數量。 實際情況的部署已證明，當使用者擁有五個以上的主要標籤，或每個主要標籤有超過五個子標籤時，效果會明顯地降低。

### <a name="label-policy-priority-order-matters"></a>標籤原則優先順序 (順序很重要)

您會在敏感度標籤原則中發佈敏感度標籤，以將其提供給使用者使用，而標籤會顯示在 [標籤原則] 頁面上 [敏感度原則] 索引標籤的清單中。 正如同敏感度標籤 (請參閱[標籤原則優先順序 (順序很重要)](#label-priority-order-matters))，敏感度標籤原則的順序非常重要，因為順序反映的是優先順序。 優先順序最低的標籤原則會顯示在 **上方**，而優先順序最高的標籤原則會顯示在 **下方**。

標籤原則包含：

- 一組標籤。
- 將獲指派具有標籤之原則的使用者和群組。
- 該範圍的原則和原則設定的範圍 (例如檔案和電子郵件的預設標籤)。

您可以將使用者包含在多個標籤原則中，該使用者即會看到來自這些原則的所有敏感度標籤。 不過，使用者只會取得來自具有最高優先順序標籤原則的原則設定。

如果您沒有看到使用者或群組應有的標籤或標籤原則設定，請檢查敏感度標籤原則的順序。 若要重新排序標籤原則，請選取 [敏感度標籤原則] > 選擇右側的省略符號 > **[下移]** 或 **[上移]**。

![敏感度標籤原則頁面上的移動選項](../media/sensitivity-label-policy-priority.png)

如果您除了使用敏感度標籤，還使用了保留標籤，請務必記住優先順序對於敏感度標籤原則，但對於[保留標籤原則](retention.md#the-principles-of-retention-or-what-takes-precedence)則否。

## <a name="sensitivity-labels-and-azure-information-protection"></a>敏感度標籤和 Azure 資訊保護

如果您已使用 Azure 資訊保護部署標籤，請在開始使用敏感度標籤之前，先使用下列各節中的指引。

### <a name="azure-information-protection-labels"></a>Azure 資訊保護標籤

> [!NOTE]
> Azure 入口網站中 Azure 資訊保護標籤的標籤管理功能即將在 **2021 年 3 月 31 日** 淘汰。 請透過官方的[淘汰聲明](https://techcommunity.microsoft.com/t5/azure-information-protection/announcing-timelines-for-sunsetting-label-management-in-the/ba-p/1226179)深入了解。

如果您因為您的租用戶尚不在[整合標籤平台](/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)中而使用 Azure 資訊保護標籤，建議您在您啟用整合標籤前，避免建立敏感度標籤。 在此情況下，您在 Azure 入口網站中看到的標籤是 Azure 資訊保護標籤，而不是敏感度標籤。 這些標籤可由 Windows 電腦上的 Azure 資訊保護用戶端 (傳統) 使用，但不能由執行 macOS、iOS 或 Android 的裝置使用。 若要解決此問題，請[將這些標籤遷移](/azure/information-protection/configure-policy-migrate-labels)至敏感度標籤。 

這兩組標籤所套用的中繼資料彼此相容，因此您不須在完成移轉時，重新標記文件和電子郵件。

### <a name="azure-information-protection-clients"></a>Azure 資訊保護用戶端

當您在 Windows 電腦上的 Microsoft 365 Apps 企業版應用程式中使用敏感度標籤時，您可以選擇使用 Azure 資訊保護用戶端，或使用 Office 內建的標記功能。

根據預設，安裝 Azure 資訊保護用戶端時，這些應用程式中的內建標記功能會關閉。 如需詳細資訊，包括如何變更此預設行為，請參閱 [Office 內建標籤用戶端和 Azure 資訊保護用戶端](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client)。

即使是在 Office 應用程式中使用內建標籤時，也可以為下列項目使用 Azure 資訊保護的整合標籤用戶端，搭配敏感度標籤：

- 掃描器，以探索儲存在內部部署的敏感性資訊，然後選擇性為該內容加上標籤

- 檔案總管中的右鍵選項，讓使用者對所有檔案類型套用標籤

- 檢視器，以顯示文字、影像或 PDF 文件的加密檔案

- PowerShell 模組，以探索內部部署檔案中的敏感性資訊，並對這些檔案套用或移除標籤和加密。

如果您是 Azure 資訊保護的新使用者，或您是剛轉移標籤的現有 Azure 資訊保護客戶，請參閱來自 Azure 資訊保護文件的[選擇要用於 Windows 電腦的標籤用戶端](/azure/information-protection/rms-client/use-client#choose-your-windows-labeling-solution)。

## <a name="sensitivity-labels-and-microsoft-cloud-app-security"></a>敏感性標籤和 Microsoft Cloud App Security

您可以使用 Cloud App Security (CAS) 來探索、分類、加標籤，以及保護內容的第三方服務和應用程式 (例如 SalesForce、Box 或 Dropbox) 中的內容。 

Cloud App Security 適用於 Azure 資訊保護標籤和敏感度標籤：

- 如果標籤系統管理中心已將一或多個敏感度標籤[發佈](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)給至少一個使用者：使用敏感度標籤。

- 如果標籤系統管理中心未發佈敏感度標籤：使用 Azure 資訊保護標籤。

如需有關使用 Cloud App Security 搭配這些標籤的指示，請參閱 [Azure 資訊保護整合](/cloud-app-security/azip-integration)。

## <a name="sensitivity-labels-and-the-microsoft-information-protection-sdk"></a>敏感度標籤和 Microsoft 資訊保護 SDK

由於敏感度標籤是以純文字儲存在文件的中繼資料中，因此協力廠商的應用程式和服務都可讀取和寫入此標籤中繼資料，以補充您的標籤部署。 此外，軟體開發人員可以使用 [Microsoft 資訊保護 SDK](/information-protection/develop/overview#microsoft-information-protection-sdk)，完全支援跨多個平臺的標籤和加密功能。 若要深入了解，請參閱[技術社群部落格上的正式版本公告](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144)。 

您也可以了解[與 Microsoft 資訊保護整合的合作夥伴解決方案](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657)。

## <a name="deployment-guidance"></a>部署指導方針

如需部署規劃和指導方針，其中包含授權資訊、權限、部署策略，以及支援的案例和使用者文件的清單，請參閱[開始使用敏感度標籤](get-started-with-sensitivity-labels.md)。