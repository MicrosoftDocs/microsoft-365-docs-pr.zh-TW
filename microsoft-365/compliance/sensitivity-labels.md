---
title: 敏感度標籤概觀
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 01/06/2020
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
description: 使用敏感度標籤，您可以分類並協助保護敏感內容，同時確保人員的生產力與共同作業能力不會受到阻礙。您可以使用敏感度標籤在標記的內容上套用保護設定 (包括加密和浮水印)。
ms.openlocfilehash: f85d94b918c96ea6505b9b52d386e7f30a3fe77a
ms.sourcegitcommit: 920bca353d16e9b1e5d4d268e0410ef179eced37
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2020
ms.locfileid: "40948868"
---
# <a name="overview-of-sensitivity-labels"></a>敏感度標籤概觀

為了完成其工作，組織中的人員會與組織內外的其他人員共同合作。這表示內容不總是在防火牆後，它會漫遊在裝置、應用程式和服務的各處。而您希望內容以符合組織的商務及合規性原則的安全、受保護的方式漫遊。

使用敏感度標籤，您可以分類並協助保護敏感性內容，不會阻礙人員的生產力與共同作業能力。

顯示敏感度標籤的範例：

![Excel 功能區和狀態列上的敏感度標籤](media/Sensitivity-label-in-Excel.png)

只有全域 (公開) 雲端的租用戶才支援敏感度標籤。 目前，其他雲端 (例如[國家/地區雲端](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud)) 中的租用戶不支援敏感度標籤。

若要套用敏感度標籤，使用者必須使用公司或學校帳戶登入 Office。

您可以使用敏感度標籤來：
  
- **在標記的內容上強制執行保護設定，例如加密或浮水印。** 例如，使用者可以將「機密」標籤套用至文件或電子郵件，該標籤即可加密內容，並套用「機密」浮水印。

- **保護不同平台和裝置之間 Office 應用程式中的內容。** 如需受支援應用程式的清單，請參閱 [Office App 中的敏感度標籤](sensitivity-labels-office-apps.md)。

- **防止敏感內容離開組織執行 Windows 的裝置**，方式是使用 Microsoft Intune 的端點保護。敏感度標籤套用至位於 Windows 裝置上的內容後，端點保護可以防止該內容複製到協力廠商應用程式，例如 Twitter 或 Gmail，或複製到卸除式儲存空間，如 USB 磁碟機。

- **使用 Microsoft Cloud App Security 保護協力廠商應用程式和服務中的內容。** 使用 Cloud App Security，您可以偵測、分類、標記並保護協力廠商應用程式和服務中的內容，例如 SalesForce、Box 或 DropBox，即使協力廠商應用程式或服務無法讀取或支援敏感度標籤亦然。

- **將敏感度標籤擴充至協力廠商應用程式和服務。** 使用 Microsoft 資訊保護 SDK，[這些平台](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)上的協力廠商應用程式就可以讀取敏感度標籤，並且套用保護設定。

- **不使用任何保護設定而將內容分類。** 您也可以直接將分類指派給內容 (例如貼圖)，該分類會在使用和共用時隨著內容保存和漫遊。 您可以使用這個分類來產生使用情況報告，並且查看敏感性內容的活動資料。 根據這項資訊，您一律可以選擇稍後套用保護設定。

在上述情況下，Office 365 中的敏感度標籤可協助您對正確的內容採取適當的動作。 您可以運用敏感度標籤分類組織的資料，並根據該分類強制執行保護設定。
  
當您在 Microsoft 365 合規性中心、Microsoft 365 安全性中心或是 Office 365 安全性與合規性中心底下的 [分類]**** >  [敏感度標籤]**** 建立敏感度標籤時，可以使用自動標籤設定。 這些敏感度標籤可供 Azure 資訊保護、Office 應用程式和 Office 365 服務使用。

針對 Azure 資訊保護客戶，您可以使用其他系統管理中心的 Azure 資訊保護標籤，而如果您選擇執行額外或進階組態，標籤就會與 Azure 入口網站同步處理。 **Azure 資訊保護標籤與 Office 365 敏感度標籤完全彼此相容。** 這表示，比方說，如果您有使用 Azure 資訊保護加上標籤的內容，則不需將內容重新分類或重新加上標籤。

## <a name="what-a-sensitivity-label-is"></a>敏感度標籤是什麼

當您將敏感度標籤指派至文件或電子郵件，它就像標記：

- **可自訂。** 您可以為組織中不同等級的敏感內容建立類別，例如個人、公用、一般、機密、高度機密。

- **純文字。** 由於標籤會以純文字形式儲存在內容的中繼資料中，因此第三方應用程式和服務可以讀取它，然後套用自己的保護動作 (如必要)。

- **持續性。** 將敏感度標籤套用至內容後，該標籤就會保存在該電子郵件或文件的中繼資料中。 這表示標籤會隨著內容 (包括保護設定) 漫遊，而此資料就變成套用和強制執行原則的基礎。

在 Office 應用程式中，敏感度標籤在電子郵件或文件上只會顯示為標記。

內容中的每個項目皆可套用單一敏感度標籤。項目可以同時套用單一敏感度標籤和單一[保留標籤](labels.md)。

![套用至電子郵件的敏感度標籤](media/Sensitivity-label-on-email.png)

## <a name="what-sensitivity-labels-can-do"></a>敏感度標籤的功能

除了電子郵件和文件之外，在多個公開預覽版中也提供敏感度標籤。 如需如何可將敏感度標籤搭配檔案、團隊、群組及網站使用的詳細資訊，請參閱下列文章：

- [對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤 (公開預覽)](sensitivity-labels-sharepoint-onedrive-files.md)

- [對 Microsoft Teams、Office 365 群組和 SharePoint 網站使用敏感度標籤 (公開預覽)](sensitivity-labels-teams-groups-sites.md)

將敏感度標籤套用至電子郵件或文件後，將會對內容強制執行為該標籤設定的保護設定。 您可以使用敏感度標籤：

- 只**加密**電子郵件或電子郵件和文件。 您可以選擇哪些使用者或群組可以擁有權限來執行哪些動作，以及執行多久。 例如，您可以選擇允許組織外部特定網域中的使用者有權在標記內容後的 7 天內查看內容。 或者，不要自行指派權限，而是可以讓使用者在套用標籤時，指派權限給內容。 如需詳細資訊，請參閱[使用敏感度標籤中的加密來限制內容的存取](encryption-sensitivity-labels.md)。

- **標記內容**，將自訂浮水印、頁首或頁尾新增至已套用標籤的電子郵件或文件。 您只能將浮水印套用至文件 (而非電子郵件)，且限制為 255 個字元。 此外，頁首及頁尾限制為 1024 個字元 (Excel 中除外，在 Excel 中的限制為 255 個字元或較少，取決於文件是否包含其他頁首或頁尾以及其他因素)。

    ![套用至文件的浮水印和頁首](media/Sensitivity-label-watermark-header.png)

- 在 Intune 中開啟端點保護，**防止資料外洩**。 如果已下載敏感性內容，您可以協助防止 Windows 裝置的資料遺失。 例如，您無法將標籤的內容複製到 Dropbox、Gmail 或 USB 磁碟機。 在敏感度標籤能夠使用 Windows 資訊保護 (WIP) 之前，您必須先在 Azure 入口網站中建立應用程式保護原則。 如需詳細資訊，請參閱 [Windows 資訊保護如何使用敏感度標籤保護檔案](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)。

- **自動將標籤套用到包含敏感性資訊的內容。** 您可以選擇想要將標籤套用到哪些類型的敏感性資訊，以及自動套用標籤或您建議使用者套用標籤的提示。如果您有建議的標籤，提示會顯示您選擇的任何文字。如需詳細資訊，請參閱[自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)。

    ![指派必要標籤的提示](media/Sensitivity-label-Prompt-for-required-label.png)

在您建立敏感度標籤時，這所有選項都可供使用：

![建立敏感度標籤的選項](media/Sensitivity-label-create-options.png)

### <a name="label-priority-order-matters"></a>標籤優先順序 (順序很重要)

在您的系統管理中心中建立敏感度標籤時，它們會顯示在 [標籤]**** 頁面的 [敏感度]**** 索引標籤上的清單中。 在此清單中，標籤的順序很重要，因為它反映的是其優先順序。 您想要讓最具限制性的敏感度標籤，例如 [高度機密性]，顯示在清單的最**底端**，以及最不具限制性的敏感度標籤，例如公用，顯示在最**上方**。

您只能將一個敏感度標籤套用至文件或電子郵件。 如果您要求使用者提供將標籤變更為較低分類的理由，則此清單的順序會識別分類下限。

標籤優先順序也適用子標籤。

![建立子標籤的選項](media/Sensitivity-label-sublabel-options.png)

### <a name="sublabels-grouping-labels"></a>子標籤 (分組標籤)

您可以使用子標籤將一或多個標籤分組在 Office 應用程式中的使用者可看到的上層標籤之下。 例如，在 [機密文件] 下，您的組織可能會使用不同的標籤來標示該分類的特定類型。 在此範例中，上層標籤 [機密文件] 只是沒有任何保護設定的文字標籤，且因為它有子標籤，所以無法套用至內容。 相反地，使用者必須選擇 [機密文件] 來查看子標籤，然後再選擇要套用到內容的子標籤。

子標籤是以邏輯群組方式向使用者呈現標籤的一個簡單方式。 子標籤不繼承其上層標籤的任何設定。 當您發佈使用者的子標籤時，該使用者就可以將該子標籤套用到內容，但不能只套用上層標籤。

請勿選擇上層標籤作為預設標籤，或將上層標籤設定為自動套用或建議的選項，因為上層標籤無法套用至使用 Azure 資訊保護整合標籤用戶端的 Office 應用程式中的內容。

子標籤如何對使用者顯示的範例：

![功能區上分組的子標籤](media/Sensitivity-label-grouped-labels.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a>編輯或刪除敏感度標籤

如果您刪除敏感度標籤，該標籤不會從內容中移除，且會繼續對內容強制執行任何保護設定。

如果您編輯敏感度標籤，則會對內容強制執行當初套用至內容的標籤版本。

## <a name="what-label-policies-can-do"></a>標籤原則的功能

建立敏感度標籤後，您需要發佈標籤，以供組織中的人員使用，這些人員可以接著將標籤套用至內容。與發佈到位置 (例如所有 Exchange 信箱) 的保留標籤不同，敏感度標籤會發佈給使用者或群組。敏感度標籤接著會為這些使用者和群組顯示在 Office 應用程式中。

使用標籤原則，您可以：

- **選擇哪些使用者和群組可以看見標籤。** 標籤可以發佈到任何電子郵件啟用的安全性群組、通訊群組、Office 365 群組或動態通訊群組。

- **套用預設標籤**至所有新文件和電子郵件，這些是由標籤原則中包含的使用者和群組所建立。此預設標籤可以設定您想要套用到所有內容的基礎層級保護設定。

- **需要變更標籤的理由。** 如果已將內容標示為「機密」，且使用者想要移除該標籤，或以較低的分類 (例如名為「公用」的標籤) 取代，您可以要求使用者在執行此動作時提供理由。 目前，理由尚未傳送到 [標籤分析](label-analytics.md) 以供系統管理員檢閱。 不過 [Azure 資訊保護整合標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)會將此資訊傳送至 [Azure 資訊保護分析](https://docs.microsoft.com/azure/information-protection/reports-aip)。

    ![提示使用者輸入理由](media/Sensitivity-label-justification-required.png)

- **要求使用者將標籤套用到他們的電子郵件和文件。** 如果您想要將所有使用者的內容套用標籤，您可以要求必須將標籤套用到所有已儲存的文件和傳送的電子郵件。基於自動或預設 (預設標籤選項如上所述) 指派的條件，使用者可以手動指派標籤。當使用者需要指派標籤時，Outlook 中會顯示提示。

    > [!NOTE]
    > 強制標籤需要具備 Azure 資訊保護訂閱。 若要使用此功能，您必須下載並安裝 [Azure 資訊保護用戶端](https://www.microsoft.com/download/details.aspx?id=53018) 或較新版本的 [Azure 資訊保護統一標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app)。 此外，用戶端僅能在 Windows 上執行，因此 Mac、iOS 和 Android 上尚不支援此功能。

    ![Outlook 中詢問使用者套用必要標籤的提示](media/sensitivity-labels-mandatory-prompt-aipv2-outlook.PNG)

- **提供自訂說明頁面的說明連結。** 如果使用者不確定敏感度標籤代表的意義或使用方式，您可以提供「深入了解」URL，其顯示在 Office 應用程式中 [敏感度標籤]**** 功能表的底部。

    ![功能區中 [敏感度] 按鈕上的「深入了解」連結](media/Sensitivity-label-learn-more.png)

建立標籤原則並將敏感度標籤指派給使用者和群組之後，這些人會在一小時內在 Office 應用程式中看到這些標籤。

您可以建立並發佈的敏感度標籤數量沒有任何限制，但有一個例外：如果標籤套用加密，則上限為 500 個標籤。 不過，為了將系統管理負擔降至最低，並為使用者減少複雜度，最佳做法是應試著將標籤數量保持最低。 實際情況的部署已證明，當使用者擁有五個以上的主要標籤，且每個主要標籤超過五個子標籤時，效果會降低。

### <a name="label-policy-priority-order-matters"></a>標籤原則優先順序 (順序很重要)

您會在敏感度標籤原則中發佈敏感度標籤，以將其提供給使用者使用，而標籤會顯示在 [標籤原則]**** 頁面上 [敏感度原則]**** 索引標籤的清單中。 正如同敏感度標籤 (請參閱[標籤原則優先順序 (順序很重要)](#label-priority-order-matters))，敏感度標籤原則的順序非常重要，因為順序反映的是優先順序。 優先順序最低的標籤原則會顯示在**上方**，而優先順序最高的標籤原則會顯示在**下方**。

標籤原則包含：

- 一組標籤。
- 標籤原則的範圍，表示原則中包含的使用者和群組。
- 以上所述標籤原則的設定 (預設標籤、對齊、強制標籤和說明連結)。

您可以將使用者包含在多個標籤原則中，該使用者即會看到來自這些原則的所有敏感度標籤。 不過，使用者只會看到來自具有最高優先順序標籤原則的原則設定。

如果您的組織中的使用者或群組看不到您需要的標籤原則中的選項，例如預設標籤或強制標籤，請檢查敏感度標籤原則的順序。 若要重新排序標籤原則，請選取 [敏感度標籤原則 > 選擇右側的省略符號 > [下移]**** 或 [上移]****。

![敏感度標籤原則頁面上的移動選項](media/sensitivity-label-policy-priority.png)

雖然敏感度標籤原則的優先順序很重要，對保留標籤原則而言，它卻**不**重要。 如[保留原則，哪一個優先？](labels.md#the-principles-of-retention-or-what-takes-precedence)中所述，內容可能會受限於多個保留原則。

## <a name="how-to-get-started-with-sensitivity-labels"></a>如何開始使用敏感度標籤

開始使用敏感度標籤的程序很快：

1. **定義標籤。** 首先，您要建立用於定義不同敏感度層級內容的分類法。 使用對您的使用者有意義的一般名稱或字詞。 例如，您可以從個人、公開、一般、機密和高度機密等標籤開始。 您可以使用子標籤，依類別將類似的標籤群組。 此外，建立標籤時會需要工具提示，它會在使用者將滑鼠指標移至功能區上的標籤選項時在 Office 應用程式中顯示。

2. **定義每個標籤的功能。** 然後設定您想要與每個標籤相關聯的保護設定。 例如，較低的敏感度內容 (如「一般」標籤) 可能只有套用頁首或頁尾，而較高敏感度內容 (如「機密」標籤) 可能會套用浮水印、加密及 WIP，以協助確保只有特殊權限使用者可以存取。

3. **定義誰可以看到標籤。** 定義組織的標籤後，您會在標籤原則中發佈標籤，此原則可控制哪些使用者和群組會看到這些標籤。單一標籤可重複使用 – 定義一次後，即可將標籤包含在指派給不同使用者的數個標籤原則中。但為了讓標籤可指派給內容，您必須先發佈該標籤，才能在 Office 應用程式及其他服務中使用。剛開始時，您可以先指定給一小部分人員以試驗您的敏感度標籤。

以下是系統管理員、使用者和 Office 應用程式執行項目以讓敏感度標籤運作的基本流程。

![敏感度標籤的工作流程圖](media/Sensitivity-label-flow.png)

## <a name="where-sensitivity-labels-can-appear"></a>敏感度標籤會顯示的位置

敏感度標籤會顯示在 Office 應用程式的 UI 中。 若要檢視特定應用程式和平台內建標籤的目前狀態，請使用下列表格：

- [在 Word、Excel 和 PowerPoint 中支援敏感度標籤功能](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-word-excel-and-powerpoint)

- [在 Outlook 中支援敏感度標籤功能](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-outlook)

如果您使用 Windows 電腦的 Azure 資訊保護整合標籤用戶端，則有其他功能可供敏感度標籤使用。 如需詳細資訊，請參閱[比較 Windows 電腦的標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)。 

### <a name="office-apps-on-windows"></a>Windows 上的 Office 應用程式

在執行 Windows 裝置上的 Office 應用程式中，敏感度標籤會顯示在功能區上 [常用]**** 索引標籤的 [敏感度]**** 按鈕中。 

當您使用內建的標籤時，套用的標籤也會出現在視窗底部的狀態列中：

![Windows 中 Excel 功能區上的敏感度按鈕](media/Sensitivity-label-Sensitivity-button.png)

### <a name="office-apps-on-the-web"></a>Office 網頁版應用程式

如需如何搭配敏感度標籤使用 Office 網頁版應用程式的詳細資訊，請參閱[在 Office 網頁版中將敏感度標籤套用至文件和電子郵件](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)。

### <a name="office-apps-on-mac"></a>Mac 上的 Office 應用程式

在 Mac 裝置上的 Office 應用程式中，敏感度標籤會顯示在功能區上 [常用]**** 索引標籤的 [敏感度]**** 按鈕中。 套用的標籤也會出現在視窗底部的狀態列中：

![Mac 中 Office 功能區上的敏感度按鈕](media/Sensitivity-label-on-Mac.png)

### <a name="office-apps-on-ios"></a>iOS 上的 Office 應用程式

在 iOS 裝置上的 Office 應用程式中，敏感度標籤會顯示在功能區上 [常用]**** 索引標籤的 [敏感度]**** 按鈕中。 套用的標籤也會出現在視窗底部的狀態列中：

![iOS 中 Office 功能區上的敏感度按鈕](media/Sensitivity-label-on-iOS.png)

### <a name="office-apps-on-android"></a>Android 上的 Office 應用程式

在 Android 裝置上的 Office 應用程式中，敏感度標籤會顯示在功能區上 [常用]**** 索引標籤的 [敏感度]**** 按鈕中。 套用的標籤也會出現在視窗底部的狀態列中：

![Android 中 Office 功能區上的敏感度按鈕](media/Sensitivity-label-on-Android.png)

### <a name="more-information-on-sensitivity-labels-in-office-apps"></a>Office 應用程式中敏感度標籤的詳細資訊

- [在 Office 中將敏感度標籤套用至您的文件和電子郵件](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
- [將敏感度標籤套用至 Office 檔案的已知問題](https://support.office.com/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)
- [Office 應用程式中的敏感度標籤](sensitivity-labels-office-apps.md)

## <a name="how-sensitivity-labels-work-with-existing-azure-information-protection-labels"></a>敏感度標籤如何搭配使用現有的 Azure 資訊保護標籤

Azure 資訊保護使用者可以使用 Azure 資訊保護整合標籤用戶端，在 Windows 上分類和標記內容。 現有的 Azure 資訊保護標籤可與新的敏感度標籤 (也稱為整合標籤) 緊密配合。 這表示您可以：

- 在文件和電子郵件上保留現有的 Azure 資訊保護標籤。
- 保留現有的 Azure 資訊保護標籤設定。

如果您因為您的租用戶尚不在[整合標籤平台](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)中而使用 Azure 資訊保護標籤，建議您避免在其他系統管理中心中建立新標籤，直到您啟用整合標籤為止。 如需此程序的詳細資訊，請參閱[如何將 Azure 資訊保護標籤移轉至整合敏感度標籤](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)。 

> [!NOTE]
>  Azure 入口網站中 Azure 資訊保護標籤的標籤管理功能即將在 **2021 年 3 月 31 日**淘汰。 在官方的[淘汰聲明](https://techcommunity.microsoft.com/t5/azure-information-protection/deprecation-notice-azure-information-protection-classic-client/ba-p/1092108)中深入了解。

## <a name="sensitivity-labels-and-the-azure-information-protection-client"></a>敏感度標籤和 Azure 資訊保護用戶端

如果已安裝 Azure 資訊保護用戶端，則 Office 365 專業增強版應用程式會自動關閉 Office Windows 應用程式中的敏感度標籤。
若要變更此預設行為，以便使用內建的標籤，請參閱[關於 Office 內建標籤用戶端](sensitivity-labels-office-apps.md#about-the-office-built-in-labeling-client)。

## <a name="protect-content-on-windows-devices-by-using-endpoint-protection-in-microsoft-intune"></a>使用 Microsoft Intune 中的端點保護來保護 Windows 裝置上的內容

建立敏感度標籤時，您可以選擇告知 Windows：當含有此標籤的檔案儲存在 Windows 裝置上時，需要保護此內容不遭受資料外洩。 此選項可協助您確保使用這個標籤的內容只能共用或複製到獲批准的位置，甚至是在端點上儲存時。 實際上，對敏感度標籤開啟此選項，會告知 Windows 這是極為重要的資料，需要提供額外的使用限制。

當您開啟此選項，Windows 可以讀取、了解及對文件中的敏感度標籤採取動作，並自動對內容套用 Windows 資訊保護 (WIP)，不論其如何觸及受管理的 Windows 裝置。在無論是否套用加密的情況下，這有助於防止標記的檔案發生意外洩漏。

比方說，Windows 可了解位於使用者電腦上的 Word 文件已套用「機密」標籤，且 WIP 可套用應用程式保護原則，以避免將資料複製或共用到該裝置的任何非工作位置 (例如個人 OneDrive、個人電子郵件帳戶、社群媒體或 USB 磁碟機)。

如果使用者嘗試將已標記的內容上傳到個人 Gmail 帳戶，他們會看到這則訊息。

![已標記內容的訊息無法複製到 Gmail](media/Sensitivity-label-WIP-Gmail.png)

而如果使用者嘗試將已標記的內容儲存到 USB 磁碟機，他們會看到下列訊息：

![已標記內容的訊息無法複製到 USB 磁碟機](media/Sensitivity-label-WIP-USB-drive.png)

### <a name="important-prerequisites-for-using-wip"></a>使用 WIP 的重要先決條件

在敏感度標籤可使用 WIP 之前，您必須先執行下文所述的先決條件：[Windows 資訊保護如何保護具有敏感度標籤的檔案](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)。本主題將說明下列先決條件：

- 請確定您執行的是 Windows 10，版本 1809 或更新版本。
- [設定 Microsoft Defender 進階威脅防護 (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/)，這會掃描標籤內容，並套用對應的 WIP 保護。 ATP 執行某些獨立於 WIP 的動作，例如報告異常狀況。
- 建立可套用至端點裝置的 Windows 資訊保護 (WIP) 原則。您可以在下列任何位置執行此作業：

  - [為 Microsoft Intune 使用 Azure 入口網站透過 MDM 建立 Windows 資訊保護 (WIP) 原則](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)
  - [使用 System Center Configuration Manager 建立及部署 Windows 資訊保護 (WIP) 原則](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-sccm)

## <a name="protect-content-in-third-party-apps-and-services-by-using-microsoft-cloud-app-security"></a>使用 Microsoft Cloud App Security 保護協力廠商應用程式和服務中的內容

使用 Cloud App Security (CAS) 保護協力廠商應用程式和服務中的內容。 您可以使用 CAS 來偵測、分類、加標籤，以及保護內容的第三方服務和應用程式 (例如 SalesForce、Box 或 Dropbox) 中的內容。 例如，Dropbox 可能無法了解敏感度標籤，但 CAS 可以取得並保護該位置中加標籤的內容。

如需詳細資訊，請參閱[自動套用 Azure 資訊保護分類標籤](https://docs.microsoft.com/cloud-app-security/use-case-information-protection)。

### <a name="important-prerequisites-for-using-cas"></a>使用 CAS 的重要先決條件

在敏感度標籤可使用 CAS 之前，您必須先執行下文所述的先決條件：[自動套用 Azure 資訊保護分類標籤](https://docs.microsoft.com/cloud-app-security/use-case-information-protection)。 本主題說明下列先決條件：

- 為您的租用戶[啟用 Cloud App Security 和 Azure 資訊保護](https://docs.microsoft.com/cloud-app-security/azip-integration)。
- [將應用程式連線](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)至 Cloud App Security。

## <a name="extend-sensitivity-labels-to-third-party-apps-and-services-by-using-the-microsoft-information-protection-sdk"></a>使用 Microsoft 資訊保護 SDK 將敏感度標籤擴充至協力廠商應用程式和服務

由於敏感度標籤在文件的中繼資料內保存為純文字，協力廠商應用程式和服務可以選擇支援識別及保護含有這類標籤的內容。其他應用程式和服務的支援已展開。

有了 [Microsoft 資訊防護 SDK](https://docs.microsoft.com/information-protection/develop/)，協力廠商應用程式和服務就可以讀取敏感度標籤和保護，並將其套用到文件。 SDK 支援[這些平台](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)上的應用程式。

使用 SDK，您可以標記及保護內容，並搭配其他 Microsoft 資訊保護應用程式和服務，如 Office 應用程式、Office 365 服務、Azure 資訊保護掃描器、Microsoft Cloud App Security，以及多種其他的合作夥伴解決方案。例如，深入了解 [Adobe Acrobat 中敏感度標籤的支援](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Starting-October-use-Adobe-Acrobat-Reader-for-PDFs-protected-by/ba-p/262738)。

若要深入了解 Microsoft 資訊保護 SDK，請參閱[技術社群部落格上的公告](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144)。您也可以了解[與 Microsoft 資訊保護整合的合作夥伴解決方案](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657)。

## <a name="permissions-required-to-create-sensitivity-labels"></a>建立敏感度標籤所需的權限

合規性小組成員會建立敏感度標籤，這些成員需要 Microsoft 365 合規性中心、Microsoft 365 安全性中心或 Office 365 安全性與合規性中心的權限。 根據預設，您的租用戶系統管理員可以存取這些系統管理中心，並且授與法務人員和其他人員存取權限，而不需授與他們租用戶系統管理員的所有權限。如需這個委派的受限系統管理員存取權，請移至其中一個系統管理中心的 [權限]**** 頁面，然後將成員新增至 [合規性系統管理員]**** 或 [安全性系統系統管理員]**** 角色群組。

如需詳細資訊，請參閱[授與使用者存取 Office 365 安全性與合規性中心的權限](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)。

需要這些權限才能建立及套用標籤和標籤原則。原則強制執行不需要內容的存取權。