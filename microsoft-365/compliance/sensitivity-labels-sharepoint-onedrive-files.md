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
ms.openlocfilehash: 656c8c12194119aa83d9b6b6897a7c43fede08df
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326579"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤

>*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

> [!NOTE]
> 目前的問題導致某些標籤和加密的檔案無法在 web 上的 Office 中開啟：
>
> 當我們調查與特定檔案屬性相關的問題時，您將無法在網頁上開啟許多 Office 檔案。 在您的桌上型電腦和行動裝置應用程式中，您可以繼續開啟及編輯這些檔案。 或者，請執行下列操作：
>
> 1. 在 Office 桌面應用程式中開啟檔案。
> 2. 移除套用加密的標籤。
> 3. 將檔案儲存在原始位置 (SharePoint 或 OneDrive) ，然後關閉桌面應用程式。
> 4. 在 web 上的 Office 中開啟檔案，並重新套用套用加密的原始標籤。
> 
> 僅在網頁上的 Office 中標示的檔案不會受到影響。

在 SharePoint 和 OneDrive 中啟用 Office 檔案的靈敏度標籤，讓使用者可以在您的 Office 中套用您的 [靈敏度卷](sensitivity-labels.md) 標。 啟用此功能時，使用者會看到功能區上的 **靈敏度** 按鈕，讓他們可以套用標籤，並在狀態列上查看任何已套用的標籤名稱。

啟用此功能也會導致 SharePoint，而且 OneDrive 可以處理使用敏感度標籤加密之檔案的內容。 標籤可以套用於用於 web 的 Office 或 Office 桌面應用程式中，並上傳或儲存在 SharePoint 和 OneDrive 中。 在您啟用此功能之前，這些服務無法處理加密的檔案，這表示合著、eDiscovery、資料遺失防護、搜尋及其他協同作業功能不適用於這些檔案。

在 SharePoint 和 OneDrive 中啟用 Office 檔案的靈敏度標籤之後，針對具有敏感度標籤的新增及變更的檔案，其敏感度標籤會以雲端型 (金鑰套用加密，而且不會使用 [雙金鑰加密](double-key-encryption.md)) ：

- 若為 Word、Excel 及 PowerPoint 檔案，SharePoint 和 OneDrive 會辨識標籤，而且現在可以處理加密檔案的內容。

- 當使用者從 SharePoint 或 OneDrive 中下載或存取這些檔案時，標籤的靈敏度標籤和任何加密設定都會強制執行，並保留在儲存的位置。 確定您提供使用者指引，只使用標籤來保護檔。 如需詳細資訊，請參閱 [資訊版權管理 (IRM) 選項和敏感度標籤](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)。

- 當使用者將已標記和加密的檔案上傳至 SharePoint 或 OneDrive 時，他們至少必須具有這些檔案的「查看」許可權。 例如，他們可以在 SharePoint 外開啟檔案。 如果使用者未使用此最小值，請上載成功，但服務無法辨識標籤，也無法處理檔案內容。

- 使用 Office for web (Word、Excel PowerPoint) 開啟及編輯具有套用加密之敏感度標籤的 Office 檔案。 會強制執行以加密指派的許可權。 您也可以對這些檔使用 [自動標籤](apply-sensitivity-label-automatically.md) 。

- 外部使用者可以使用 guest 帳戶存取以加密標記的檔。 如需詳細資訊，請參閱 [對外部使用者的支援和標示的內容](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content)。 

- Office 365 eDiscovery 支援這些檔案與資料遺失防護 (DLP) 原則支援這些檔案中的內容。

> [!NOTE]
> 如果已使用內部部署金鑰套用加密， (金鑰管理拓撲通常稱為「保留您自己的金鑰」或 HYOK) ，或是使用 [雙重金鑰加密](double-key-encryption.md)，處理檔內容的服務行為不會變更。 因此，這些檔案、共同作業、eDiscovery、資料遺失防護、搜尋及其他協同功能都無法運作。
>
> 對於這些位置中使用單一 Azure 型機碼標示的現有檔案，其 SharePoint 和 OneDrive 行為也不會變更。 若要在 SharePoint 和 OneDrive 中啟用 Office 檔案的靈敏度標籤之後，這些檔案才能從新功能受益，必須下載並重新上傳或編輯檔案。

在 SharePoint 和 OneDrive 中啟用 Office 檔案的靈敏度標籤之後，會有三個新的 [審計事件](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) 可用於監視 SharePoint 和 OneDrive 中的檔之敏感度標籤：
- **已將敏感度標籤套用到檔案**
- **已變更套用到檔案的敏感度標籤**
- **已將敏感度標籤從檔案移除**

觀看下列影片 (無音訊) 以查看新的動作功能：

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

在 SharePoint 中，您可以隨時停用 Office 檔案的靈敏度標籤，OneDrive ([自願退出](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)) 。

如果您目前使用 SharePoint 資訊版權管理 (IRM) 來保護 SharePoint 中的檔，請務必檢查此頁面上的 [ [SharePoint 的資訊版權管理 (IRM) 和敏感度標籤](#sharepoint-information-rights-management-irm-and-sensitivity-labels) ] 區段。 

## <a name="requirements"></a>需求

這些新功能僅適用于 [敏感度標籤](sensitivity-labels.md) 。 如果您目前已具備 Azure 資訊保護標籤，請先將它們遷移至靈敏度標籤，讓您可以針對您上傳的新檔案啟用這些功能。 如需說明，請參閱[如何將 Azure 資訊保護標籤移轉至統一的敏感度標籤](/azure/information-protection/configure-policy-migrate-labels)。

使用 Windows 上的 OneDrive 同步處理應用程式版本19.002.0121.0008 或更新版本，以及 Mac 版19.002.0107.0008 或更新版本。 這兩個版本都發行于2019年1月28日，而且目前已發佈給所有的振鈴。 如需詳細資訊，請參閱 [OneDrive 發行附注](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。 在 SharePoint 和 OneDrive 中啟用 Office 檔案的靈敏度標籤之後，會提示執行舊版本的 sync 應用程式的使用者進行更新。

## <a name="limitations"></a>限制

- SharePoint 和 OneDrive 不會自動將敏感度標籤套用至您已使用 Azure 資訊保護標籤加密的現有檔案。 相反地，當您在 SharePoint 和 OneDrive 中啟用 Office 檔案的靈敏度標籤之後，這些功能才能運作：
    
    1. 確定您已將 [Azure 資訊保護標籤遷移](/azure/information-protection/configure-policy-migrate-labels) 至靈敏度標籤，並已從 Microsoft 365 規範中心（或對等標上的標記系統管理中心） [發行](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) 。
    2. 下載檔案，然後將檔案上傳至 SharePoint。

- 當套用加密的標籤有下列任何 [加密](encryption-sensitivity-labels.md#configure-encryption-settings)設定時，SharePoint 和 OneDrive 無法處理加密的檔案：
    - **讓使用者在套用標籤時指派權限**，且核取方塊 **在 Word、PowerPoint 與 Excel 中提示使用者指定權限** 為選取狀態。 此設定有時稱為「使用者定義的許可權」。
    - **使用者的內容存取權到期日** 設定為 **永不** 以外的值。
    - **使用雙重金鑰加密** 已選取。
    
    針對具有上述任何加密設定的標籤，使用者不會向 Office 中的網站顯示標籤。 此外，新功能也無法與已有這些加密設定的已標記檔一起使用。 例如，即使更新這些檔，這些檔也不會在搜尋結果中傳回。

- 使用者可能會在下列另存為案例中體驗開啟加密檔的延遲：使用桌上出版本的 Office，使用者選擇 [另存新檔]，以用於具有敏感度標籤以套用加密的檔。 使用者選取該位置的 SharePoint 或 OneDrive，然後立即嘗試在該網頁的 Office 中開啟該檔。 如果服務仍在處理加密，使用者會看到一則訊息，指出必須在其桌面應用程式中開啟檔。 如果他們在幾分鐘後再試一次，該檔就會在 Office 中成功地開啟網頁。 

- 對於加密檔，不支援列印。

- 針對授與使用者編輯許可權的加密檔，在 Office 應用程式的 web 版本中無法封鎖複製。

- 根據預設，Office 桌面應用程式和行動應用程式不支援共同撰寫以加密標記的檔案。 這些應用程式會繼續以獨佔編輯模式開啟標籤和加密的檔案。
    
    > [!NOTE]
    > 現在預覽中支援共同撰寫。 如需詳細資訊，請參閱對 [使用敏感度標籤加密的檔案啟用共同撰寫](sensitivity-labels-coauthoring.md)。

- 如果系統管理員變更已套用至使用者同步處理用戶端之檔案的已發行標籤設定，則使用者可能無法在其 OneDrive Sync 資料夾中儲存對檔案所做的變更。 此案例適用于以加密標示標籤的檔案，也就是從沒有套用加密標籤的標籤所做的標籤變更時。 使用者看到 [紅色圓圈時出現白色的交叉圖示錯誤](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)，並且要求您將新的變更儲存為個別的副本。 相反地，他們可以關閉並重新開啟檔案，或使用 Office for web。

- 如果已標示的檔上傳至 SharePoint 或 OneDrive，且標籤是使用服務主體名稱中的帳戶來套用加密，則無法在 Office 中開啟該檔。 範例案例包括 Microsoft Cloud App Security，以及透過電子郵件傳送給小組的檔案。

- 使用者可能會在離線或轉入睡眠模式後遇到儲存問題，而不是使用 web Office 時，他們會使用桌面和行動應用程式進行 Word、Excel 或 PowerPoint。 針對這些使用者，當他們繼續其 Office 應用程式會話並嘗試儲存變更時，會看到上傳失敗訊息，並有一個選項可儲存副本，而不是儲存原始檔案。 

- 以下列方式加密的檔無法在網頁版 Office 中開啟：
    - 使用內部部署金鑰 ( 「保留您自己的金鑰」或 HYOK) 的加密
    - 使用[雙重金鑰加密](double-key-encryption.md)所套用的加密
    - 獨立于標籤所套用的加密，例如直接套用 Rights Management protection 範本。

- 不支援為 [其他語言](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-center-powershell) 設定的標籤，而且只會顯示原始語言。

- 無法防止加密檔的螢幕抓隨。 如需詳細資訊，請參閱[Rights Management 是否可防止螢幕抓](/azure/information-protection/faqs-rms#can-rights-management-prevent-screen-captures)即用？

- 如果您刪除的標籤已套用至 SharePoint 或 OneDrive 中的檔，而不是從適當的標籤原則中移除標籤，則下載時將不會標記或加密檔。 相比之下，如果標籤的檔儲存在 SharePoint 或 OneDrive 之外，當標籤刪除時，該檔仍會保持加密狀態。 請注意，雖然您可以在測試階段刪除標籤，但很少需要在實際執行環境中刪除標籤。

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>如何在 SharePoint 和 OneDrive (自願加入) 中啟用敏感度標籤

您可以使用 Microsoft 365 規範中心或使用 PowerShell 來啟用新功能。 隨著 SharePoint 和 OneDrive 的所有租使用者層級設定變更，此變更大約需要15分鐘的時間才能生效。

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>使用規範中心來啟用敏感度標籤支援

這個選項是為 SharePoint 和 OneDrive 啟用敏感度標籤的最簡單方式，但是您必須以您租使用者的全域管理員身分登入。

1. 以全域管理員身分登入 [Microsoft 365 規範中心](https://compliance.microsoft.com/)，並流覽至 **解決方案**  >  **資訊保護**
    
    如果您沒有立即看到這個選項，請先選取 [全部顯示]。 

2. 如果您看到可在 Office online 檔案中處理內容之功能的訊息，請選取 [ **立即開啟**]：
    
    ![開啟 [立即開啟] 按鈕，以啟用 Office Online 的敏感度標籤](../media/sensitivity-labels-turn-on-banner.png)
    
    命令會立即執行，並在下一次重新整理頁面時，您就不會再看到訊息或按鈕。

> [!NOTE]
> 如果您有 Microsoft 365 多地理位置，您必須使用 PowerShell 來啟用所有地理位置的功能。 如需詳細資料，請參閱下一節。

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>使用 PowerShell 啟用敏感度標籤支援

除了使用規範中心之外，您還可以使用 [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) Cmdlet 從 SharePoint 線上 PowerShell 中，啟用敏感度標籤支援。 

如果您有 Microsoft 365 多地理位置，您必須使用 PowerShell 來啟用所有地理位置的支援。

#### <a name="prepare-the-sharepoint-online-management-shell"></a>準備 SharePoint 線上管理命令介面

在您執行 PowerShell 命令以啟用 SharePoint 和 OneDrive 中的 Office 檔案敏感度標籤之前，請確定您執行 SharePoint 線上管理命令介面版本16.0.19418.12000 或更新版本。 如果您已有最新版本，則可以略過 [下一個](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) 程式執行 PowerShell 命令。

1. 如果您已安裝來自 PowerShell 資源庫的舊版 SharePoint Online 管理命令介面，您可以執行下列 Cmdlet 來更新模組。

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. 或者，如果您已從 Microsoft 下載中心安裝舊版的 SharePoint Online 管理命令介面，您也可以移至 [ **新增或移除程式** ]，並卸載 SharePoint 線上管理命令介面。

3. 在網頁瀏覽器中，移至下載中心頁面，並[下載最新的 SharePoint Online 管理命令介面](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

4. 選取語言，然後按一下 [下載]。

5. 在 x64 和 x86 .msi 檔案之間選擇。 如果您執行的是64位版本的 Windows 或 x86 檔案（如果您執行32位版本），請下載 x64 檔案。 如果您不知道，請參閱 [我要執行哪一個 Windows 作業系統版本？](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. 下載檔案之後，請執行檔，然後依照安裝精靈中的步驟進行。

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>執行 PowerShell 命令以啟用敏感度標籤支援

若要啟用新功能，請搭配使用 [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) Cmdlet 搭配 *EnableAIPIntegration* 參數：

1. 在 Microsoft 365 中使用具有全域系統管理員或 SharePoint 系統管理員許可權的工作或學校帳戶，連接至 SharePoint。 若要了解如何進行，請參閱[開始使用 SharePoint Online 管理命令介面](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。
    
    附注：如果您有 Microsoft 365 多地理位置，請搭配使用-Url 參數和 [Connect-SPOService](/powershell/module/sharepoint-online/connect-sposervice)，並指定其中一個地理位置的 [SharePoint] 線上管理中心網站 Url。

2. 執行下列命令，然後按 **Y** 確認：

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```
3. 針對 Microsoft 365 多地理位置：針對您餘下的地理位置重複步驟1和2。

## <a name="publishing-and-changing-sensitivity-labels"></a>發佈和變更敏感度標籤

當您使用敏感度標籤與 SharePoint 和 OneDrive 時，請記住，當您發佈新的靈敏度標籤或更新現有的靈敏度標籤時，您必須允許的複寫時間。 這對套用加密的新標籤尤其重要。

例如：您可以建立及發行套用加密的新敏感度標籤，而且會很快出現在使用者的桌面應用程式中。 使用者將此標籤套用至檔，然後將其上傳至 SharePoint 或 OneDrive。 如果服務的標籤複寫尚未完成，則上載時不會將新功能套用至該檔。 因此，在 [搜尋] 或 [eDiscovery] 中不會傳回檔，而且無法在 Office 中為 web 開啟檔。  

下列變更會在一小時內複寫：新增和刪除的敏感度標籤，以及包含哪些標籤位於原則中的靈敏度標籤原則設定。

下列變更會在24小時內複製：現有標籤的靈敏度標籤設定變更。

由於每個新敏感度標籤的複寫延遲只為一小時，因此您不會在範例中執行案例。 但作為一種保護措施，我們建議您先將新標籤發佈到少數測試使用者，等候一小時，然後在 SharePoint 和 OneDrive 上驗證標籤行為。 最後一個步驟是將更多使用者新增至現有標籤原則，或將標籤新增至現有的標籤原則，以供更多使用者使用。 當您的標準使用者看到標籤時，它已經同步處理至 SharePoint 和 OneDrive。

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint Information Rights Management (IRM) 和敏感度標籤

[SharePoint Information Rights Management (IRM) ](set-up-irm-in-sp-admin-center.md) 是一種較舊的技術，可在下載檔案時套用加密和限制，以保護清單和文件庫層級的檔案。 這種舊版保護技術的設計是為了防止未經授權的使用者在 SharePoint 之外的地方開啟檔案。

在比較中，敏感度標籤會提供視覺標記的保護設定 (頁首、頁尾、水位線) 除了加密之外。 加密設定支援所有的 [使用權力](/azure/information-protection/configure-usage-rights) ，以限制使用者可對內容執行的動作， [許多案例](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels)也支援相同的靈敏度標籤。 在不同的工作負載和應用程式中使用具有一致設定的相同保護方法，會產生一致的保護原則。

不過，您可以同時使用這兩種保護解決方案，行為如下： 

- 如果您上傳的檔案包含套用加密的靈敏度標籤，則 SharePoint 無法處理這些檔案的內容，因此這些檔案不支援合著、eDiscovery、DLP 和 search。

- 如果您使用 Office 為 web 標記檔案，則會強制執行標籤的任何加密設定。 支援這些檔案、共同撰寫、eDiscovery、DLP 及搜尋。

- 如果您下載的檔案是使用 Office for web 進行標記，則會保留標籤，並強制執行標籤的任何加密設定，而不是 IRM 限制設定。

- 如果您下載未使用敏感度標籤加密的 Office 或 PDF 檔案，則會套用 IRM 設定。

- 如果您已啟用任何其他 IRM 程式庫設定（包括防止使用者上傳不支援 IRM 的檔），則會強制執行這些設定。

使用此行為時，您可以保證所有的 Office 和 PDF 檔案在下載時受到保護，即使未進行標記，也能避免未經授權的存取。 不過，已上傳的已標示檔案不會受益于新功能。


## <a name="search-for-documents-by-sensitivity-label"></a>依敏感度標籤搜尋檔

您可以使用 managed 屬性 **InformationProtectionLabelId** ，在具有特定敏感度標籤的 SharePoint 或 OneDrive 中尋找所有檔。 請使用下列語法： `InformationProtectionLabelId:<GUID>`

例如，若要搜尋所有已標示為「機密」的檔，且該標籤的 GUID 為 "8faca7b8-8d20-48a3-8ea2-0f96310a848e"，請在搜尋方塊中輸入：

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`    

若要取得敏感度標籤的 Guid，請使用「 [取得標籤](/powershell/module/exchange/get-label) 」 Cmdlet：    

1. 第一，[連接到 Office 365 安全性與合規性中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。 
   
    例如，在您以系統管理員身分執行的 PowerShell 工作階段中，使用全域系統管理員帳戶登入。    

2. 然後執行下列命令：  

    ```powershell   
    Get-Label |ft Name, Guid    
    ``` 

如需使用 managed 屬性的詳細資訊，請參閱 [管理 SharePoint 中的搜尋架構](/sharepoint/manage-search-schema)。

## <a name="remove-encryption-for-a-labeled-document"></a>移除標籤檔的加密

當 SharePoint 管理員需要從 SharePoint 中儲存的檔中移除加密時，可能會發生極少的情況。 對該檔指派「匯出」或「完全控制」 [許可權](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) 的任何使用者，都可以移除 Azure Rights Management Service 從 Azure 資訊保護所套用的加密。 例如，使用任一種使用許可權的使用者都可以取代以未加密的標籤來套用加密的標籤。 或者， [超級使用者](/azure/information-protection/configure-super-users) 可以下載檔案，並在不加密的情況下儲存本機副本。

另外，全域管理員或 [SharePoint 管理員](/sharepoint/sharepoint-admin-role) 可以執行 [SPOSensitivityLabelEncryptedFile 指令程式](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) ，該 Cmdlet 會同時移除敏感度標籤和加密。 即使系統管理員沒有網站或檔案的存取權限，或 Azure Rights Management 服務無法使用，此 Cmdlet 也會執行。 

例如：

```powershell
Unlock-SPOSensitivityLabelEncryptedFile -FileUrl "https://contoso.com/sites/Marketing/Shared Documents/Doc1.docx" -JustificationText "Need to decrypt this file"
```

需求：

- SharePoint 線上管理命令介面版本16.0.20616.12000 或更新版本。

- 加密已由具有系統管理員定義加密設定的靈敏度標籤所套用 ([指派許可權現在](encryption-sensitivity-labels.md#assign-permissions-now) 標籤設定) 。 此 Cmdlet 不支援[雙金鑰加密](encryption-sensitivity-labels.md#double-key-encryption)。

調整文字會新增至 **已移除敏感度標籤從** 檔案中的「[審核」事件](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)，解密動作也會記錄在 [Azure 資訊保護的保護使用方式記錄](/azure/information-protection/log-analyze-usage)中。

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>如何停用 SharePoint 和 OneDrive (自願退出) 的敏感度標籤

如果您停用這些新功能，當您為 SharePoint 和 OneDrive 啟用敏感度標籤之後，您上傳的檔案會繼續受到標籤的保護，因為標籤設定會繼續強制執行。 當您停用這些新功能之後，當您將敏感度標籤套用至新的檔案時，全文搜尋、eDiscovery 和合著將不再運作。

若要停用這些新功能，您必須使用 PowerShell。 使用 SharePoint 線上管理命令介面和 [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant)指令程式，指定與 [使用 PowerShell 以啟用敏感度標籤](#use-powershell-to-enable-support-for-sensitivity-labels)] 區段中所述的相同 *EnableAIPIntegration* 參數。 不過這段時間，請將參數值設為 false，然後按 **Y** 確認：

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

如果您有 Microsoft 365 多地理位置，您必須針對每個地理位置執行此命令。

## <a name="next-steps"></a>後續步驟

在 SharePoint 和 OneDrive 中為 Office 檔案啟用敏感度標籤之後，請考慮使用自動標記原則自動標記這些檔案。 如需詳細資訊，請參閱 [自動將敏感度標籤套用至內容](apply-sensitivity-label-automatically.md)。

需要與組織外的人員共用您的已套用標籤且加密之文件嗎？  請參閱[與外部用戶共用加密文件](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users)。