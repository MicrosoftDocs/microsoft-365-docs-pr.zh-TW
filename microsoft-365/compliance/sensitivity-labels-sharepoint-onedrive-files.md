---
title: 對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 管理員可以在 SharePoint 和 OneDrive 中啟用 Word、Excel 及 PowerPoint 檔案的敏感度標籤支援。
ms.openlocfilehash: ee6f89db7758140ac8e4c2752d8a2883cc0990db
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780716"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

在 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤之前，您無法將您的[靈敏度卷](sensitivity-labels.md)標套用至網頁上的 office。 您不會在功能區上看到 [**靈敏度**] 按鈕，或在狀態列上看到已套用的標籤名稱。 此外，如果您使用桌面應用程式來標示您的檔案，然後將檔案儲存在 SharePoint 或 OneDrive 上，如果標籤已套用加密，服務就無法處理這些檔案的內容。 在這些情況下，合著、eDiscovery、資料遺失防護、搜尋及其他協同功能無法運作。

當您在 SharePoint 和 OneDrive 中啟用 Office 檔案的靈敏度標籤時，會啟用所有這些功能。 除了為使用者顯示敏感度標籤之外，針對已套用敏感度標籤（包含以雲端為基礎的金鑰進行加密）的新檔和變更的檔案：

- 若為 Word、Excel 及 PowerPoint 檔案，SharePoint 會辨識標籤，現在可以處理加密檔的內容。

- 當您從 SharePoint 或 OneDrive 下載或存取這些檔案時，標籤的靈敏度標籤和所有的加密設定都會強制執行，並保留在儲存的位置。 確定您提供使用者指引，只使用標籤來保護檔。 如需詳細資訊，請參閱[資訊版權管理（IRM）選項和敏感度標籤](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)。

- 當使用者將已標記和加密的檔案上傳至 SharePoint 時，他們至少必須具有這些檔案的「查看」許可權。 例如，他們可以在 SharePoint 外開啟檔案。 如果使用者未使用此最小值，請上載成功，但 SharePoint 無法辨識標籤，也無法處理檔內容。

- 使用網頁上的 Office （Word、Excel、PowerPoint）開啟及編輯具有敏感度標籤的 Office 檔案，以套用加密。 會強制執行以加密指派的許可權。 透過網頁上的 Word，您也可以在編輯這些檔時使用自動標籤。

- 外部使用者可以使用 guest 帳戶存取以加密標記的檔。 如需詳細資訊，請參閱[對外部使用者的支援和標示的內容](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content)。 

- Office 365 eDiscovery 支援這些檔案的全文搜尋。 資料遺失防護（DLP）原則支援這些檔案中的內容。

> [!NOTE]
> 若尚未使用雲端型金鑰（內部部署金鑰）套用加密，通常稱為「保留您自己的金鑰」（HYOK）的金鑰管理拓撲，處理檔內容的 SharePoint 行為不會改變。
>
> SharePoint 行為也不會變更 SharePoint 中的現有標籤和加密檔。 為了讓這些檔案受益于新功能，在您執行此命令以啟用 SharePoint 和 OneDrive 的靈敏度標籤之後，必須下載並上傳或編輯這些檔案。 SharePoint 可以處理這些檔案。 例如，他們會在搜尋和 eDiscovery 結果中傳回。

在 SharePoint 和 OneDrive 中啟用 Office 檔案的靈敏度標籤之後，會有三個新的[審計事件](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)可用於監視 SharePoint 和 OneDrive 中的檔之敏感度標籤：
- **已將敏感度標籤套用到檔案**
- **已變更套用到檔案的敏感度標籤**
- **已將敏感度標籤從檔案移除**

觀賞下列影片（無音訊），以查看動作中的新功能：

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

在 SharePoint 和 OneDrive 中，您可以隨時停用 Office 檔案的靈敏度標籤（隨時[自願退出）](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out) 。

如果您目前使用 SharePoint 資訊版權管理（IRM）保護 SharePoint 中的檔，請務必檢查此頁面上的 [ [SharePoint 資訊版權管理（irm）和敏感度標籤](#sharepoint-information-rights-management-irm-and-sensitivity-labels)] 區段。 

## <a name="requirements"></a>需求

這些新功能僅適用于[敏感度標籤](sensitivity-labels.md)。 如果您目前已具備 Azure 資訊保護標籤，請先將它們遷移至靈敏度標籤，讓您可以針對您上傳的新檔案啟用這些功能。 如需相關指示，請參閱 how [to 將 Azure 資訊保護標籤遷移至統一敏感度標籤](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

使用 Windows 上的 OneDrive 同步處理應用程式版本19.002.0121.0008 或更新版本，以及 Mac 版19.002.0107.0008 或更新版本。 這兩個版本都發行于2019年1月28日，而且目前已發佈給所有的振鈴。 如需詳細資訊，請參閱[OneDrive 發行附注](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。 在 SharePoint 和 OneDrive 中啟用 Office 檔案的靈敏度標籤之後，會提示執行舊版本的 sync 應用程式的使用者進行更新。

## <a name="limitations"></a>限制

- SharePoint 不會自動將敏感度標籤套用至您已使用 Azure 資訊保護標籤加密的現有檔案。 相反地，若要在 SharePoint 和 OneDrive 中啟用 Office 檔案的靈敏度標籤之後，取得功能，請完成下列工作：
    
    1. 確定您已將[Azure 資訊保護標籤遷移](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)至靈敏度標籤，並已從 Microsoft 365 規範中心（或對等標上的標記系統管理中心）[發行](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)。
    
    2. 下載檔案，然後將檔案上傳至 SharePoint。

- 當套用加密的標籤有下列兩種[加密](encryption-sensitivity-labels.md#configure-encryption-settings)設定時，SharePoint 無法處理加密的檔案：
    - **讓使用者在套用標籤**和 [ **Word、PowerPoint 及 Excel 中**的核取方塊時，指定許可權，並選取 [提示使用者指定許可權]。 此設定有時稱為「使用者定義的許可權」。
    - 對**內容到期的使用者存取權**設定為**永不**值以外的值。
    
    如果是具有上述任一種加密設定的標籤，則網頁上的 Office 使用者不會看到標籤。 此外，新功能也無法與已有這些加密設定的已標記檔一起使用。 例如，即使更新這些檔，這些檔也不會在搜尋結果中傳回。

- 針對授與使用者編輯許可權的加密檔，在 Office 應用程式的 web 版本中無法封鎖複製。

- 不支援 Azure 資訊保護檔追蹤網站。

- Office 桌面應用程式和行動應用程式不支援共同撰寫以加密標示的檔案。 這些應用程式會繼續以獨佔編輯模式開啟標籤和加密的檔案。

- 如果系統管理員變更已套用至使用者同步處理用戶端之檔案的已發行標籤設定，則使用者可能無法在其 OneDrive Sync 資料夾中儲存對檔案所做的變更。 此案例適用于以加密標示標籤的檔案，也就是從沒有套用加密標籤的標籤所做的標籤變更時。 使用者看到[紅色圓圈時出現白色的交叉圖示錯誤](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)，並且要求您將新的變更儲存為個別的副本。 相反地，他們可以關閉並重新開啟檔案，或在網頁上使用 Office。

- 如果已標示的檔上傳至 SharePoint，而標籤是使用服務主體名稱中的帳戶來套用加密，則無法在網頁上的 Office 中開啟該檔。 範例案例包括 Microsoft Cloud App Security，以及透過電子郵件傳送給小組的檔案。

- 使用者可能會在離線或轉入睡眠模式後遇到儲存問題，而不是使用 web Office 時，他們會使用桌面和行動應用程式進行 Word、Excel 或 PowerPoint。 針對這些使用者，當他們繼續其 Office 應用程式會話並嘗試儲存變更時，會看到上傳失敗訊息，並有一個選項可儲存副本，而不是儲存原始檔案。 

- 以下列方式加密的檔無法在 web 上的 Office 中開啟：
    - 使用內部部署機碼的加密（「保留您自己的金鑰」或 HYOK）
    - 獨立于標籤所套用的加密，例如直接套用 Rights Management protection 範本。

- 如果您刪除的標籤已套用至 SharePoint 中的檔，而不是從適當的標籤原則中移除標籤，則下載的檔不會標示或加密。 相比之下，如果標籤的檔儲存在 SharePoint 之外，當標籤刪除時，該檔仍會保持加密狀態。 請注意，雖然您可以在測試階段刪除標籤，但很少需要在實際執行環境中刪除標籤。

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>如何啟用 SharePoint 和 OneDrive 的敏感度標籤（自願加入）

您可以使用 Microsoft 365 規範中心或使用 PowerShell 來啟用新功能。

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>使用規範中心來啟用敏感度標籤支援

這個選項是為 SharePoint 和 OneDrive 啟用敏感度標籤的最簡單方式。

組織的全域系統管理員擁有建立及管理敏感度標籤所有層面的完整權限。 如果您未以全域系統管理員身分登入，請參閱[建立和管理敏感度標籤所需的權限](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)。

1. 登入[Microsoft 365 規範中心](https://compliance.microsoft.com/)，並流覽至**解決方案**  >  **資訊保護**
    
    如果您沒有立即看到這個選項，請先選取 [全部顯示]****。 

2. 如果您看到可在 Office online 檔案中處理內容之功能的訊息，請選取 [**立即開啟**]：
    
    ![開啟 [立即開啟] 按鈕，以啟用 Office Online 的敏感度標籤](../media/sensitivity-labels-turn-on-banner.png)
    
    命令會立即執行，並在下一次重新整理頁面時，您就不會再看到訊息或按鈕。 

> [!NOTE]
> 如果您有 Microsoft 365 多地理位置，您必須使用 PowerShell 來啟用所有地理位置的功能。 如需詳細資料，請參閱下一節。

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>使用 PowerShell 啟用敏感度標籤支援

除了使用規範中心之外，您還可以使用[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) Cmdlet 從 SharePoint 線上 PowerShell 中，啟用敏感度標籤支援。 

如果您有 Microsoft 365 多地理位置，您必須使用 PowerShell 來啟用所有地理位置的支援。

#### <a name="prepare-the-sharepoint-online-management-shell"></a>準備 SharePoint 線上管理命令介面

在您執行 PowerShell 命令以啟用 SharePoint 和 OneDrive 中的 Office 檔案敏感度標籤之前，請確定您執行 SharePoint 線上管理命令介面版本16.0.19418.12000 或更新版本。 如果您已有最新版本，則可以略過[下一個](#run-the-powershell-command-to-enable-support-for-sensitivity-labels)程式執行 PowerShell 命令。

1. 如果您已安裝來自 PowerShell 資源庫的舊版 SharePoint Online 管理命令介面，您可以執行下列 Cmdlet 來更新模組。

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. 或者，如果您已從 Microsoft 下載中心安裝舊版的 SharePoint Online 管理命令介面，您也可以移至 [**新增或移除程式**]，並卸載 SharePoint 線上管理命令介面。

3. 在網頁瀏覽器中，移至下載中心頁面，並[下載最新的 SharePoint Online 管理命令介面](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

4. 選取語言，然後按一下 [下載]****。

5. 在 x64 和 x86 .msi 檔案之間選擇。 如果您執行的是64位版本的 Windows 或 x86 檔案（如果您執行32位版本），請下載 x64 檔案。 如果您不知道，請參閱[我要執行哪一個 Windows 作業系統版本？](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. 下載檔案之後，請執行檔，然後依照安裝精靈中的步驟進行。

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>執行 PowerShell 命令以啟用敏感度標籤支援

若要啟用新功能，請搭配使用[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) Cmdlet 搭配*EnableAIPIntegration*參數：

1. 在 Microsoft 365 中使用具有全域系統管理員或 SharePoint 系統管理員許可權的工作或學校帳戶，連接至 SharePoint。 若要了解如何進行，請參閱[開始使用 SharePoint Online 管理命令介面](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。
    
    附注：如果您有 Microsoft 365 多地理位置，請搭配使用-Url 參數和[Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)，並指定其中一個地理位置的 [SharePoint] 線上管理中心網站 Url。

2. 執行下列命令，然後按**Y**確認：

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```
3. 針對 Microsoft 365 多地理位置：針對您餘下的地理位置重複步驟1和2。

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a>在您建立或變更靈敏度標籤之後排程部署

在 Microsoft 365 規範中心內建立或變更靈敏度標籤之後，請分階段發佈。 如果您發佈尚未完全同步處理的標籤，當使用者將標籤套用至檔案，並將其上傳至 SharePoint 時，就無法在網頁版的 Office 應用程式中開啟檔案。 搜尋和 eDiscovery 也不適用於檔案。

我們建議您遵循下列步驟：

1. 僅將新的或修改過的敏感度標籤發佈給一或兩個人。

2. 在初始出版物過後等候至少24小時。 確認標籤已完全同步處理。

3. 更廣泛地發佈標籤。

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint 資訊版權管理（IRM）和敏感度標籤

[SharePoint 資訊版權管理（IRM）](set-up-irm-in-sp-admin-center.md)是一種較舊的技術，可在下載檔案時套用加密和限制，以保護清單和文件庫層級的檔案。 這種舊版保護技術的設計是為了防止未經授權的使用者在 SharePoint 之外的地方開啟檔案。

在比較中，敏感度標籤會提供視覺標記（標頭、頁尾、浮水印）的保護設定，以及加密。 加密設定支援所有的[使用權力](https://docs.microsoft.com/azure/information-protection/configure-usage-rights)，以限制使用者可對內容執行的動作，[許多案例](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels)也支援相同的靈敏度標籤。 在不同的工作負載和應用程式中使用具有一致設定的相同保護方法，會產生一致的保護原則。

不過，您可以同時使用這兩種保護解決方案，行為如下： 

- 如果您上傳的檔案包含套用加密的靈敏度標籤，則 SharePoint 無法處理此檔案，因此不會針對此檔案使用合著、eDiscovery、DLP 和 search。

- 如果您使用 web 上的 Office 來標記檔案，則會強制執行標籤的任何加密設定。 支援這些檔案、共同撰寫、eDiscovery、DLP 及搜尋。

- 如果您下載使用網頁上的 Office 標示的檔案，則會保留標籤，並強制執行標籤的任何加密設定，而不是 IRM 限制設定。

- 如果您下載未使用敏感度標籤加密的 Office 或 PDF 檔案，則會套用 IRM 設定。

- 如果您已啟用任何其他 IRM 程式庫設定（包括防止使用者上傳不支援 IRM 的檔），則會強制執行這些設定。

使用此行為時，您可以保證所有的 Office 和 PDF 檔案在下載時受到保護，即使未進行標記，也能避免未經授權的存取。 不過，已上傳的已標示檔案不會受益于新功能。

## <a name="search-for-documents-by-sensitivity-label"></a>依敏感度標籤搜尋檔

您可以使用 managed 屬性**InformationProtectionLabelId** ，在具有特定敏感度標籤的 SharePoint 或 OneDrive 中尋找所有檔。 請使用下列語法：`InformationProtectionLabelId:<GUID>`

例如，若要搜尋所有已標示為「機密」的檔，且該標籤的 GUID 為 "8faca7b8-8d20-48a3-8ea2-0f96310a848e"，請在搜尋方塊中輸入：

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`

若要取得敏感度標籤的 Guid，請使用「[取得標籤](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps)」 Cmdlet：
    
1. 第一，[連接到 Office 365 安全性與合規性中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。 
    
    例如，在您以系統管理員身分執行的 PowerShell 工作階段中，使用全域系統管理員帳戶登入：
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. 然後執行下列命令：
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

如需使用 managed 屬性的詳細資訊，請參閱[管理 SharePoint 中的搜尋架構](https://docs.microsoft.com/sharepoint/manage-search-schema)。

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>如何停用 SharePoint 和 OneDrive 的敏感度標籤（自願拉出）

如果您停用這些新功能，當您為 SharePoint 和 OneDrive 啟用敏感度標籤之後，您上傳的檔案會繼續受到標籤的保護，因為標籤設定會繼續強制執行。 當您停用這些新功能之後，當您將敏感度標籤套用至新的檔案時，全文搜尋、eDiscovery 和合著將不再運作。

若要停用這些新功能，您必須使用 PowerShell。 使用 SharePoint 線上管理命令介面和[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps)指令程式，指定與[使用 PowerShell 以啟用敏感度標籤](#use-powershell-to-enable-support-for-sensitivity-labels)] 區段中所述的相同*EnableAIPIntegration*參數。 不過這段時間，請將參數值設為 false，然後按**Y**確認：

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

如果您有 Microsoft 365 多地理位置，您必須針對每個地理位置執行此命令。

## <a name="next-steps"></a>後續步驟

在 SharePoint 和 OneDrive 中為 Office 檔案啟用敏感度標籤之後，請考慮使用自動標記原則自動標記這些檔案。 如需詳細資訊，請參閱[自動將敏感度標籤套用至內容](apply-sensitivity-label-automatically.md)。