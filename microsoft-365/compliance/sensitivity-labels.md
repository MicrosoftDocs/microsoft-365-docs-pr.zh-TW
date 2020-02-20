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
search.appverid:
- MOE150
- MET150
description: 從 Microsoft 資訊保護架構使用敏感度標籤來分類及保護組織的資料，同時確保使用者生產效率和共同作業能力不受影響。 這些標籤可套用保護設定以包含加密視覺標記，如頁尾和浮水印。
ms.openlocfilehash: 92bfb768cf044b6a4837e5dab6936c2d77424a25
ms.sourcegitcommit: ee18bdd08e85b1262b91c180ccf61df59c19dab2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42106826"
---
# <a name="learn-about-sensitivity-labels"></a>了解敏感度標籤

為了完成其工作，組織中的人員會與組織內外的其他人員共同合作。這表示內容不會停留在防火牆後，它會漫遊在裝置、應用程式和服務的各處。而您希望內容以符合組織的商務及合規性原則的安全、受保護的方式漫遊。

來自 Microsoft 資訊保護架構的敏感度標籤可讓您分類及保護組織的資料，同時確保使用者生產效率和共同作業能力不受影響。

從功能區上的 [首頁]**** 索引標籤顯示 Excel 中可用敏感度標籤的範例。 在此範例中，已套用的標籤會顯示在狀態列上：

![Excel 功能區和狀態列上的敏感度標籤](../media/Sensitivity-label-in-Excel.png)

只有全域 (公開) 雲端的租用戶才支援敏感度標籤。 目前，其他雲端 (例如[國家/地區雲端](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud)) 中的租用戶不支援敏感度標籤。

> [!NOTE]
> 敏感度標籤尚無法在美國政府社群 (GCC) 組織中使用。

若要套用敏感度標籤，使用者必須使用公司或學校帳戶登入 Office。

您可以使用敏感度標籤來：
  
- **在標記的內容上強制執行保護設定，例如加密或浮水印。** 例如，使用者可以將「機密」標籤套用至文件或電子郵件，該標籤即可加密內容，並套用「機密」浮水印。

- **保護不同平台和裝置之間 Office 應用程式中的內容。** 如需受支援應用程式的清單，請參閱[在 Office 應用程式中使用敏感度標籤](sensitivity-labels-office-apps.md)。

- 藉由在 Microsoft Intune 中使用端點保護，來**防止敏感內容從組織內執行 Windows 的裝置上流出**。 敏感度標籤套用至位於 Windows 裝置上的內容後，端點保護可以防止該內容複製到第三方應用程式，例如 Twitter 或 Gmail。 或複製到卸除式儲存空間，如 USB 磁碟機。

- 使用 Microsoft Cloud App Security **保護第三方應用程式和服務中的內容**。 使用 Cloud App Security，您可以偵測、分類、標記並保護協力廠商應用程式和服務中的內容，例如 SalesForce、Box 或 DropBox，即使協力廠商應用程式或服務無法讀取或支援敏感度標籤亦然。

- **將敏感度標籤延伸至第三方應用程式和服務。** 使用 Microsoft 資訊保護 SDK，第三方應用程式就可以讀取敏感度標籤以及套用保護設定。

- **不使用任何保護設定而將內容分類。** 您也可以直接將分類指派給內容 (例如貼圖)，該分類會在使用和共用時隨著內容保存和漫遊。 您可以使用這個分類來產生使用情況報告，並且查看敏感性內容的活動資料。 根據這項資訊，您一律可以選擇稍後套用保護設定。

在上述情況下，Microsoft 365 中的敏感度標籤可協助您對正確的內容採取適當的動作。 您可以運用敏感度標籤分類組織的資料，並根據該分類強制執行保護設定。

## <a name="what-a-sensitivity-label-is"></a>敏感度標籤是什麼

當您將敏感度標籤指派給文件或電子郵件，它就像一個戳記套用在內容上，並且是：

- **可自訂。** 您可以為組織中不同等級的敏感內容建立類別，例如個人、公用、一般、機密、高度機密。

- **純文字。** 由於標籤會以純文字形式儲存在內容的中繼資料中，因此第三方應用程式和服務可以讀取它，然後套用自己的保護動作 (如必要)。

- **持續性。** 將敏感度標籤套用至內容後，該標籤就會存放在該電子郵件或文件的中繼資料中。 這表示標籤會隨著內容 (包括保護設定) 漫遊，而此資料就變成套用和強制執行原則的基礎。

在 Office 應用程式中，敏感度標籤就像是在電子郵件或文件上讓使用者看的標記。

內容中的每個項目皆可套用單一敏感度標籤。項目可以同時套用單一敏感度標籤和單一[保留標籤](labels.md)。

> [!div class="mx-imgBorder"]
> ![套用至電子郵件的敏感度標籤](../media/Sensitivity-label-on-email.png)

## <a name="what-sensitivity-labels-can-do"></a>敏感度標籤的功能

> [!NOTE]
> 除了在 Office 應用程式中將標籤套用至電子郵件和文件以外，現在也能在下列公開預覽版中使用敏感度標籤：
> 
> - [對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤 (公開預覽)](sensitivity-labels-sharepoint-onedrive-files.md)
> - [對 Microsoft Teams、Office 365 群組和 SharePoint 網站使用敏感度標籤 (公開預覽)](sensitivity-labels-teams-groups-sites.md)

將敏感度標籤套用至電子郵件或文件後，將會對內容強制執行為該標籤設定的保護設定。 您可以使用敏感度標籤：

- 只**加密**電子郵件或電子郵件和文件。 您可以選擇哪些使用者或群組可以擁有權限來執行哪些動作，以及執行多久。 例如，您可以選擇允許另一個組織內特定群組中的使用者有權在標記內容後的 7 天內檢閱內容。 或者，可以讓使用者在套用標籤時，指派權限給內容，而不要使用系統管理員定義的權限。 
    
    如需建立或編輯敏感度標籤時**加密**設定的詳細資訊，請參閱[使用敏感度標籤中的加密來限制內容的存取](encryption-sensitivity-labels.md)。

- 將浮水印、頁首或頁尾新增至已套用標籤的電子郵件或文件，以在使用 Office 應用程式時**標記內容**。 浮水印可以套用至文件 (而非電子郵件)。 頁首和浮水印範例：
    
    ![套用至文件的浮水印和頁首](../media/Sensitivity-label-watermark-header.png)
    
    需要檢查何時套用內容標記？ 請參閱 [Office 365 何時將內容標記和加密套用到內容 ](sensitivity-labels-office-apps.md#when-office-365-applies-content-marking-and-encryption)。
    
    字串長度：浮水印限制為 255 個字元。 頁首和頁尾均受限於 1024 個字元，但 Excel 除外。 對於頁首及頁尾，Excel 的總限制為 255 個字元，但此限制包含看不見的字元，例如格式代碼。 如果達到該限制，您輸入的字串就不會顯示在 Excel 中。

- 在 Intune 中開啟端點保護，**防止資料外洩**。 如果已下載敏感性內容，您可以協助防止 Windows 裝置的資料遺失。 例如，您無法將標籤的內容複製到 Dropbox、Gmail 或 USB 磁碟機。 在敏感度標籤能夠使用 Windows 資訊保護 (WIP) 之前，您必須先在 Azure 入口網站中建立應用程式保護原則。 
    
    如需有關當您建立或編輯敏感度標籤 (包括重要的先決條件) 時**端點資料外洩防護**設定的詳細資訊，請參閱 [Windows 資訊保護如何使用敏感度標籤保護檔案](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)。

- 當您加入預覽以[在 Microsoft Teams、Office 365 群組和 SharePoint 網站 (公開預覽版) 中搭配使用敏感度標籤時](sensitivity-labels-teams-groups-sites.md)，**保護容器中的內容，例如網站和群組**。
    
    在您選擇預覽版之前，不會顯示 [網站和群組設定]**** 的設定選項。 請注意，此標籤設定並不會導致文件字動加上標籤，相反的，標籤設定會控制儲存文件的容器存取權，以保護內容。 這些設定包括隱私權層級，Office 365 群組擁有者是否可以將來賓新增至群組，以及授權給非管理裝置的存取層級。

- **在 Office 應用程式中自動套用標籤，或建議標籤。** 您可以選擇您要標示的敏感資訊類型，且可以自動套用標籤，或提示使用者套用您建議的標籤。 如果您建議使用某個標籤，提示會顯示您選擇的任何文字。 例如：
    
    ![指派必要標籤的提示](../media/Sensitivity-label-Prompt-for-required-label.png)
    
    如需有關當您建立或編輯敏感度標籤時 **Office 應用程式的自動標籤**設定的詳細資訊，請參閱[自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)。

### <a name="label-priority-order-matters"></a>標籤優先順序 (順序很重要)

在您的系統管理中心中建立敏感度標籤時，它們會顯示在 [標籤]**** 頁面的 [敏感度]**** 索引標籤上的清單中。 在此清單中，標籤的順序很重要，因為它反映的是其優先順序。 您想要讓最具限制性的敏感度標籤，例如 [高度機密性]，顯示在清單的最**底端**，以及最不具限制性的敏感度標籤，例如公用，顯示在最**上方**。

您只能將一個敏感度標籤套用至文件或電子郵件。 如果您設定一個選項，要求使用者提供將標籤變更為較低分類的理由，則此清單的順序會識別分類下限。 不過，此選項不適用子標籤。

不過，子標籤的排序會搭配[自動標記](apply-sensitivity-label-automatically.md)使用。 將標籤設定為自動套用或建議時，可能對多個標籤造成相符項目。 若要判斷要套用或建議的標籤，會使用標籤順序：選取最後一個敏感度標籤，然後在適用時使用最後一個子標籤。

![建立子標籤的選項](../media/Sensitivity-label-sublabel-options.png)

### <a name="sublabels-grouping-labels"></a>子標籤 (分組標籤)

您可以使用子標籤將一或多個標籤分組在 Office 應用程式中的使用者可看到的上層標籤之下。 例如，在 [機密文件] 下，您的組織可能會使用不同的標籤來標示該分類的特定類型。 在此範例中，上層標籤 [機密文件] 只是沒有任何保護設定的文字標籤，且因為它有子標籤，所以無法套用至內容。 相反地，使用者必須選擇 [機密文件] 來查看子標籤，然後再選擇要套用到內容的子標籤。

子標籤是以邏輯群組方式向使用者呈現標籤的一個簡單方式。 子標籤不繼承其上層標籤的任何設定。 當您發佈使用者的子標籤時，該使用者就可以將該子標籤套用到內容，但不能只套用上層標籤。

請勿選擇上層標籤作為預設標籤，或將上層標籤設定為自動套用或建議的選項，因為上層標籤無法套用至使用 Azure 資訊保護整合標籤用戶端的 Office 應用程式中的內容。

子標籤如何對使用者顯示的範例：

![功能區上分組的子標籤](../media/Sensitivity-label-grouped-labels2.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a>編輯或刪除敏感度標籤

如果您從系統管理中心刪除敏感度標籤，此標籤並未從內容中自動移除，且所有保護設定都會繼續在套用該標籤的內容上強制執行。

如果您編輯敏感度標籤，則會對內容強制執行當初套用至內容的標籤版本。

## <a name="what-label-policies-can-do"></a>標籤原則的功能

在您建立敏感度標籤之後，您必須發佈這些標籤，使其可供組織中的人員和服務使用。 然後可以將敏感度標籤套用至文件和電子郵件。 不同於保留標籤 (發佈到諸如所有 Exchange 信箱的位置)，會對使用者或群組發佈敏感度標籤。 敏感度標籤接著就會出現在這些使用者和群組的 Office 應用程式中。

使用標籤原則，您可以：

- **選擇可看見標籤的使用者和群組。** 您可以將標籤發佈至已啟用電子郵件功能的任何安全性群組、Office 365 群組或動態通訊群組。

- **套用預設標籤**到標籤原則中包含的使用者和群組所建立所有新文件和的電子郵件。 請考慮使用預設標籤來設定您想套用到所有內容中的基本保護設定等級。 不過，若沒有使用者訓練和其他控制項，這項設定也可能導致不正確的標記。 

- **需要變更標籤的理由。** 如果已將內容標示為「機密」，且使用者會試著移除該標籤，或以較低的分類 (例如名為「公用」的標籤) 取代，您可以要求使用者提供執行此動作的理由。 目前，理由尚未傳送到 [標籤分析](label-analytics.md) 以供系統管理員檢閱。 不過 [Azure 資訊保護整合標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)會將此資訊傳送至 [Azure 資訊保護分析](https://docs.microsoft.com/azure/information-protection/reports-aip)。

    ![提示使用者輸入理由](../media/Sensitivity-label-justification-required.png)

- **要求使用者在其電子郵件和文件中套用標籤。** 也稱為強制標記，您可以要求必須先套用標籤，使用者才能儲存文件和傳送電子郵件。 使用此選項來協助增加您的標記涵蓋範圍。 標籤可由使用者手動指派、由於您設定的條件而自動指派，或依預設指派 (如上所述的預設標籤選項)。 當使用者需要指派標籤時，Outlook 中顯示的提示：

    ![Outlook 中詢問使用者套用必要標籤的提示](../media/sensitivity-labels-mandatory-prompt-aipv2-outlook.PNG)
    
    > [!NOTE]
    > 強制標籤需要具備 Azure 資訊保護訂閱。 若要使用此功能，您必須安裝 [Azure 資訊保護整合標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app)。 此用戶端僅能在 Windows 上執行，因此 Mac、iOS 和 Android 上尚不支援此功能。

- **提供自訂說明頁面的說明連結。** 如果使用者不確定敏感度標籤代表的意義或使用方式，您可以提供「深入了解」URL，其顯示在 Office 應用程式中 [敏感度標籤]**** 功能表的底部：

    ![功能區中 [敏感度] 按鈕上的「深入了解」連結](../media/Sensitivity-label-learn-more.png)

建立可將敏感度標籤指派給使用者和群組的標籤原則之後，需要允許最多 24 小時的時間，這些使用者才會在他們的 Office 應用程式中看到該標籤。

您可以建立並發佈的敏感度標籤數量沒有任何限制，但有一個例外：如果標籤套用加密，則上限為 500 個標籤。 不過，為了降低系統管理負擔並為使用者減少複雜度，最佳做法是試著保持最少的標籤數量。 實際情況的部署已證明，當使用者擁有五個以上的主要標籤，或每個主要標籤有超過五個子標籤時，效果會明顯地降低。

### <a name="label-policy-priority-order-matters"></a>標籤原則優先順序 (順序很重要)

您會在敏感度標籤原則中發佈敏感度標籤，以將其提供給使用者使用，而標籤會顯示在 [標籤原則]**** 頁面上 [敏感度原則]**** 索引標籤的清單中。 正如同敏感度標籤 (請參閱[標籤原則優先順序 (順序很重要)](#label-priority-order-matters))，敏感度標籤原則的順序非常重要，因為順序反映的是優先順序。 優先順序最低的標籤原則會顯示在**上方**，而優先順序最高的標籤原則會顯示在**下方**。

標籤原則包含：

- 一組標籤。
- 標籤原則的範圍，表示原則中包含的使用者和群組。
- 以上所述標籤原則的設定 (預設標籤、對齊、強制標籤和說明連結)。

您可以將使用者包含在多個標籤原則中，該使用者即會看到來自這些原則的所有敏感度標籤。 不過，使用者只會取得來自具有最高優先順序標籤原則的原則設定。

如果您沒有看到使用者或群組應有的標籤或標籤原則設定，且已等待 24 小時，請檢查敏感度標籤原則的順序。 若要重新排序標籤原則，請選取 [敏感度標籤原則 > 選擇右側的省略符號 > [下移]**** 或 [上移]****。

![敏感度標籤原則頁面上的移動選項](../media/sensitivity-label-policy-priority.png)

如果除了敏感度標籤，您還使用保留標籤，請務必記住敏感度標籤原則的優先順序問題，但不適用於[保留標籤原則](labels.md#the-principles-of-retention-or-what-takes-precedence)。

## <a name="sensitivity-labels-and-azure-information-protection"></a>敏感度標籤和 Azure 資訊保護

如果您已使用 Azure 資訊保護部署標籤，請在開始使用敏感度標籤之前，先使用下列各節中的指引。

### <a name="azure-information-protection-labels"></a>Azure 資訊保護標籤

如果您因為您的租用戶尚不在[整合標籤平台](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)中而使用 Azure 資訊保護標籤，建議您在您啟用整合標籤前，避免建立敏感度標籤。 在此情況下，您在 Azure 入口網站中看到的標籤是 Azure 資訊保護標籤，而不是敏感度標籤。 這些標籤可由 Windows 電腦上的 Azure 資訊保護用戶端 (傳統) 使用，但不能由執行 macOS、iOS 或 Android 的裝置使用。 若要解決此問題，請[將這些標籤遷移](/azure/information-protection/configure-policy-migrate-labels)至敏感度標籤。 

這兩組標籤所套用的中繼資料彼此相容，因此您不須在完成移轉時，重新標記文件和電子郵件。

### <a name="azure-information-protection-clients"></a>Azure 資訊保護用戶端

當您在 Windows 電腦上的 Office 365 專業增強版應用程式中使用敏感度標籤時，您可以選擇使用 Azure 資訊保護用戶端，或使用 Office 內建的標記功能。

根據預設，安裝 Azure 資訊保護用戶端時，這些應用程式中的內建標記功能會關閉。 如需詳細資訊，包括如何變更此預設行為，請參閱 [Office 內建標籤用戶端和 Azure 資訊保護用戶端](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client)。

即使是在 Office 應用程式中使用內建標籤時，也可以為下列項目使用 Azure 資訊保護的整合標籤用戶端，搭配敏感度標籤：

- 掃描器，以探索儲存在內部部署的敏感性資訊，然後選擇性為該內容加上標籤

- 檔案總管中的右鍵選項，讓使用者對所有檔案類型套用標籤

- 檢視器，以顯示文字、影像或 PDF 文件的加密檔案

- PowerShell 模組，以探索內部部署檔案中的敏感性資訊，並對這些檔案套用或移除標籤和加密。

如果您是 Azure 資訊保護的新使用者，或您是剛移轉標籤的現有 Azure 資訊保護客戶，請參閱來自 Azure 資訊保護文件的[選擇要用於 Windows 電腦的標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)。

## <a name="sensitivity-labels-and-microsoft-cloud-app-security"></a>敏感性標籤和 Microsoft Cloud App Security

您可以使用 Cloud App Security (CAS) 來探索、分類、加標籤，以及保護內容的第三方服務和應用程式 (例如 SalesForce、Box 或 Dropbox) 中的內容。 

Cloud App Security 適用於 Azure 資訊保護標籤和敏感度標籤：

- 如果標籤系統管理中心已將一或多個敏感度標籤[發佈](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)給至少一個使用者：使用敏感度標籤。

- 如果標籤系統管理中心未發佈敏感度標籤：使用 Azure 資訊保護標籤。

如需有關使用 Cloud App Security 搭配這些標籤的指示，請參閱 [Azure 資訊保護整合](https://docs.microsoft.com/cloud-app-security/azip-integration)。

## <a name="sensitivity-labels-and-the-microsoft-information-protection-sdk"></a>敏感度標籤和 Microsoft 資訊保護 SDK

由於敏感度標籤是以純文字儲存在文件的中繼資料中，因此協力廠商的應用程式和服務都可讀取和寫入此標籤中繼資料，以補充您的標籤部署。 此外，軟體開發人員可以使用 [Microsoft 資訊保護 SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)，完全支援跨多個平臺的標籤和加密功能。 若要深入了解，請參閱[技術社群部落格上的正式版本公告](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144)。 

您也可以了解[與 Microsoft 資訊保護整合的合作夥伴解決方案](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657)。

## <a name="deployment-guidance"></a>部署指導方針

請參閱[開始使用敏感度標籤](get-started-with-sensitivity-labels.md)。

