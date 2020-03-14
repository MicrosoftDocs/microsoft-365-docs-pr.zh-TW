---
title: 建立及發佈敏感度標籤
f1.keywords:
- NOCSH
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
description: 所有 Microsoft 資訊保護解決方案的需求：建立、設定及發佈敏感度標籤，以便分類及保護貴組織的文件和電子郵件。
ms.openlocfilehash: b3f998ec7f52403c4b3676fb08976aacdc1f7d0f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42635181"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a>建立及設定敏感度標籤及其原則

所有 Microsoft 資訊保護解決方案 (有時候縮寫為 MIP) 是使用[敏感度標籤](sensitivity-labels.md)來實作。 若要建立及發佈這些標籤，請前往標籤系統管理中心，例如 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)。 您也可以使用 Microsoft 365 安全性中心，或 Office 365 安全性與合規性中心。

首先，建立並設定您要提供應用程式和其他服務使用的敏感度標籤。 例如，您希望使用者從 Office 應用程式看到和套用的標籤。 

然後，建立一或多個包含您所設定的標籤和原則設定的標籤原則。 這是為您所選的使用者和位置發佈標籤和設定的標籤原則。

## <a name="before-you-begin"></a>開始之前

組織的全域系統管理員擁有建立及管理敏感度標籤所有層面的完整權限。 如果您未以全域系統管理員身分登入，請參閱[建立和管理敏感度標籤所需的權限](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)。

## <a name="create-and-configure-sensitivity-labels"></a>建立及設定敏感度標籤

1. 在標籤系統管理中心中，導覽至敏感度標籤：
    
    - Microsoft 365 合規性中心： 
        - **解決方案** > **資訊保護**
        
        如果您沒有立即看到這個選項，請先選取 [全部顯示]****。 
    
    - Microsoft 365 安全性中心： 
        - **分類** > **敏感度標籤**
    
    - Office 365 安全性與合規性中心：
        - **分類** > **敏感度標籤**

2. 選取 [標籤]**** 索引標籤上的 [+ 建立標籤]****，以啟動 [新增敏感度標籤]**** 精靈。

3. 按照標籤設定的提示進行。
    
    如需有關標籤設定的詳細資訊，請參閱概觀資訊中的[敏感度標籤的功能](sensitivity-labels.md#what-sensitivity-labels-can-do)。

4. 重複這些步驟以建立更多標籤。 不過，如果您想要建立子標籤，請先選取父標籤，並選取 **[...]** 以取得 **[其他動作]**，然後選取 **[新增子標籤]**。

5. 建立好所有需要的標籤後，請檢查其順序，並視需要將它們上下移動。 若要變更標籤的順序，請選取 **...** 以取得 [其他動作]****，然後選取 [上移]**** 或 [下移]****。 如需詳細資訊，請參閱概覽資訊中的[標籤優先順序 (順序很重要)](sensitivity-labels.md#label-priority-order-matters) (英文)。

若要編輯現有的標籤，請將其選取，然後選取 [編輯標籤]****。 這會啟動 [編輯敏感度標籤]**** 精靈，它可讓您變更步驟 3 中的所有標籤設定。 

> [!NOTE]
> 如果您編輯已使用標籤原則發佈的標籤，當完成精靈後便不需要額外的步驟。 例如，您不需要將其新增到新的標籤原則中，就能讓變更供相同的使用者使用。 不過，請允許最多 24 小時的時間讓變更複寫到使用者和服務。

在您發佈標籤之前，無法在應用程式中或為服務選取標籤。 若要發佈標籤，必須先[將標籤新增至標籤原則](#publish-sensitivity-labels-by-creating-a-label-policy)。

> [!IMPORTANT]
> 在此 [標籤]**** 索引標籤上，請勿選取 [發佈標籤]**** 索引標籤 (也不要在編輯標籤時選取 [發佈標籤]**** 按鈕)，除非您需要建立新的標籤原則。 只有當使用者需要不同的標籤或不同的原則設定時，才需要多個標籤原則。 盡可能建立較少的標籤原則，只建立一個標籤原則的組織也是很常見的。

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a>Office 365 安全性與合規性中心 PowerShell 的其他標籤設定

您可以從 [Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) 使用 [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) Cmdlet 取得其他標籤設定。

對跨國部署使用 *LocaleSettings* 參數，以便使用者能夠利用本地語言查看標籤名稱和工具提示。 如需設定範例，請參閱下一節。 

使用此 Cmdlet，您同時可以為 Azure 資訊保護整合標籤用戶端指定 [[進階設定]](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)。 這些進階設定包括設定標籤色彩，以及在套用標籤時套用自訂屬性。 如需完整清單，請參閱[標籤原則可用的進階設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)。 

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a>設定不同語言敏感度標籤的設定範例

下列範例顯示名為「公開」標籤的 PowerShell 設定，其中包含工具提示的預留位置文字。 在此範例中，標籤名稱和工具提示文字設定為法文、義大利文和德文。

由於這項設定，若使用者具有使用這些顯示語言的 Office 應用程式，則會以相同的語言查看其標籤名稱和工具提示。 同樣地，如果您已安裝 Azure 資訊保護的整合標籤用戶端，以在檔案瀏覽器中為檔案加上標籤，則擁有這些語言版本 Windows 的使用者就能在使用滑鼠右鍵進行標記時，以本地語言查看其標籤名稱和工具提示。

針對需要支援的語言，請使用 Office [語言識別項](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (又稱為語言標籤)，然後為標籤名稱和工具提示指定自己的翻譯。

在 PowerShell 中執行命令之前，您必須先[連線至 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。


```powershell
$Languages = @("fr-fr","it-it","de-de")
$DisplayNames=@("Publique","Publico","Oeffentlich")
$Tooltips = @("Texte Français","Testo italiano","Deutscher text")
$label = "Public"
$DisplayNameLocaleSettings = [PSCustomObject]@{LocaleKey='DisplayName';
Settings=@(
@{key=$Languages[0];Value=$DisplayNames[0];}
@{key=$Languages[1];Value=$DisplayNames[1];}
@{key=$Languages[2];Value=$DisplayNames[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $DisplayNameLocaleSettings -Depth 3 -Compress)
$TooltipLocaleSettings = [PSCustomObject]@{LocaleKey='Tooltip';
Settings=@(
@{key=$Languages[0];Value=$Tooltips[0];}
@{key=$Languages[1];Value=$Tooltips[1];}
@{key=$Languages[2];Value=$Tooltips[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $TooltipLocaleSettings -Depth 3 -Compress)
```

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a>建立標籤原則來發佈敏感度標籤

1. 在標籤系統管理中心中，導覽至敏感度標籤：
    
    - Microsoft 365 合規性中心： 
        - **解決方案** > **資訊保護**
        
        如果您沒有立即看到這個選項，請先選取 [全部顯示]****。 
    
    - Microsoft 365 安全性中心： 
        - **分類** > **敏感度標籤**
    
    - Office 365 安全性與合規性中心：
        - **分類** > **敏感度標籤**

2. 選取 **[標籤原則]** 索引標籤。

3. 選取 **[發佈標籤]** 以啟動 **[建立原則精靈]**。

4. 選取 **[選擇要發佈的敏感度標籤]**。 選取您要在應用程式和服務中提供使用的標籤，然後選取 **[新增]**。

5. 檢閱選取的標籤，若要進行任何變更，請選取 **[編輯]**。 否則請選取 **[下一步]**。

6. 遵循提示來設定原則設定。
    
    如需有關設定的詳細資訊，請參閱概觀資訊中的[標籤原則的功能](sensitivity-labels.md#what-label-policies-can-do) (英文)。

7. 如果不同的使用者或位置需要不同的原則設定，請重複這些步驟。 例如，您需要一組使用者有其他標籤，或使用者的子集有不同的預設標籤。

8. 如果您建立可能會導致使用者或位置發生衝突的多個標籤原則，請檢閱原則順序，並視需要將它們上下移動。 若要變更標籤原則的順序，請選取 **...** 以取得 **[其他動作]**，然後選取 **[上移]** 或 **[下移]**。 如需詳細資訊，請參閱概觀資訊中的 [標籤原則優先順序 (順序很重要)](sensitivity-labels.md#label-policy-priority-order-matters) (英文)。

完成精靈即會自動發佈標籤原則。 若要對已發佈的原則進行變更，只要編輯即可。 沒有特定的發佈或重新發佈動作可供您選取。

若要編輯現有的標籤原則，請將其選取，然後選取 **[編輯原則]**。 這會啟動 **[建立原則]** 精靈，讓您編輯要包含的標籤和標籤設定。 完成精靈時，任何變更都會自動複寫到選取的使用者和服務。

通常，使用者會在幾小時內在其 Office App 中看到標籤。 不過，請允許最多 24 小時的時間讓您的標籤原則及任何其他所做變更複寫到所有使用者和服務。

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a>Office 365 安全性與何規性中心 PowerShell 的其他標籤原則設定

您可以使用來自 [Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) 的 [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) Cmdlet 取得其他標籤原則設定。

使用此 Cmdlet，您可以為 Azure 資訊保護整合標籤用戶端指定 [[進階設定]](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)。 這些進階設定包括為 Outlook 設定不同的預設標籤，以及在 Outlook 中實作可警告、證明或封鎖要傳送的電子郵件的快顯訊息。 如需完整清單，請參閱[標籤可用的進階設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)。 

您也可以使用此 Cmdlet 往返標籤原則來新增和移除標籤。

## <a name="removing-and-deleting-labels"></a>移除並刪除標籤

在生產環境中，您不太可能需要從標籤原則移除敏感度標籤，或刪除敏感度標籤。 在初始測試階段，您可能需要執行下列其中一項動作。 請務必了解當您執行這些動作時，會發生什麼情況。

從標籤原則移除標籤比刪除標籤的風險小，您可以在日後需要時，隨時將它新增回標籤原則：

- 當您從標籤原則中移除標籤以使該標籤不再發佈給最初指定的使用者時，下次重新整理標籤原則時，使用者將不會在 Office 應用程序中看到要選取的標籤。 不過，如果您已將標籤套用至文件或電子郵件，則不會從該內容移除標籤。 標籤所套用的任何加密都會保留，而基礎保護範本仍然會發佈。 

- 針對已移除但之前已套用至內容的標籤，使用 Word、Excel 和 PowerPoint 的內建標籤的使用者仍會在狀態列上看到已套用的標籤名稱。 同樣，已刪除且已套用至 SharePoint 網站的標籤仍會在 [敏感度]**** 欄中顯示標籤名稱。

相比之下，當您刪除標籤時：

- 如果標籤已套用加密，則會封存基礎保護範本，以便仍可開啟先前受保護的內容。 由於此已封存保護範本，您將無法使用相同名稱建立新標籤。 雖然您可以使用 [PowerShell](https://docs.microsoft.com/powershell/module/aipservice/remove-aipservicetemplate) 來刪除保護範本，但請不要這麼做，除非您確定不需要開啟使用封存範本加密的內容。

- 針對桌面應用程式：中繼資料中的標籤資訊會保留，但由於無法再將標籤識別碼標示為名稱，使用者就不會看到已套用的標籤名稱 (例如，在狀態列上)，因此使用者會假設內容未加上標籤。 如果標籤已套用加密，則會保留加密，而在內容開啟時使用者仍可看到目前封存保護範本的名稱與描述。

- 針對 Office 網頁版：使用者在狀態列或 [敏感度]**** 欄中不會看到標籤名稱。 只有當標籤未套用加密時，中繼資料中的標籤資訊才會保留。 如果標籤已套用加密，而且您已啟用 SharePoint 和 Onedrive 的 [敏感度標籤][](sensitivity-labels-sharepoint-onedrive-files.md)，則會移除中繼資料中的標籤資訊，並將加密移除。 

## <a name="next-steps"></a>後續步驟

若要針對特定案例設定和使用敏感度標籤，請使用下列文章：

- [使用敏感度標籤中的加密來限制內容的存取](encryption-sensitivity-labels.md)

- [自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)

- [對團隊、群組和網站使用敏感度標籤](sensitivity-labels-teams-groups-sites.md)

- [對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)

若要監視標籤的使用方式，請參閱[利用標籤分析檢視標籤使用量](label-analytics.md) (英文)。
