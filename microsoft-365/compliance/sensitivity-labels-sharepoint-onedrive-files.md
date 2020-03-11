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
ms.openlocfilehash: ba65624d0c7a67eb4a5be55a7f3e08c217039e83
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583140"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a>對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤 (公開預覽)

在此預覽之前，當您套用對儲存在 SharePoint 和 OneDrive 中的 Office 檔案所加入的靈敏度標籤時，服務無法處理這些檔案的內容。 在這些情況下，合著、eDiscovery、資料遺失防護、搜尋、Delve 及其他協同功能無法運作。 此預覽可針對已套用敏感度標籤（包含以雲端為基礎的金鑰進行加密）的新檔和變更的檔案，啟用這些功能：

- SharePoint 會辨識套用至 Word、Excel 及 PowerPoint 檔案中 SharePoint 及 OneDrive 的敏感度標籤：當檔案儲存在 SharePoint 中時，會移除來自 Azure 資訊保護的加密，以便處理檔案內容。 如需如何在 SharePoint 儲存檔時保護檔的相關資訊，請參閱[OneDrive For Business and SharePoint Online 中的資料加密](data-encryption-in-odb-and-spo.md)。

- 當您從 SharePoint 或 OneDrive 中下載或存取此檔案時，標籤的靈敏度標籤及標籤的任何加密設定會重新與檔案一起使用，而且在儲存檔的任何地方都會保留這些設定的強制執行。 由於這種行為，請確定您提供使用者指導，以獨佔方式使用標籤來保護檔。 如需詳細資訊，請參閱[資訊版權管理（邊緣）選項和敏感度標籤](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)。

- 若要 SharePoint 在上傳時從檔案中移除加密，上傳已標記及已加密檔案的使用者，必須至少要有查看檔案的使用許可權。 如果使用者無法在 SharePoint 外開啟檔案，SharePoint 不會從檔案中移除加密。

- 使用網頁上的 Office （Word、Excel、PowerPoint）開啟及編輯具有敏感度標籤的 Office 檔案，以套用加密。 會強制執行以加密指派的許可權。 透過網頁上的 Word，您也可以在編輯這些檔時使用自動標籤。

- Office 365 eDiscovery 支援這些檔案的全文搜尋。 資料遺失防護（DLP）原則涵蓋這些檔案中的內容。

- 有三個新的[審計事件](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)可供使用網頁上的 Office 來監視敏感度標籤：
  - **已將敏感度標籤套用到檔案**
  - **已變更套用到檔案的敏感度標籤**
  - **已將敏感度標籤從檔案移除**

> [!NOTE]
> 若尚未使用雲端型金鑰（內部部署金鑰）套用加密，則主要的管理拓撲通常稱為「保留您自己的金鑰」（HYOK），SharePoint 行為不會隨此預覽而變更。
>
> 在您啟用預覽之前，SharePoint 行為也不會針對 SharePoint 中的現有標籤和加密檔變更。 若要讓這些檔案受益于新功能，必須下載並上傳這些檔案，或在啟用預覽之後加以編輯。 例如，他們會在搜尋和 eDiscovery 結果中傳回。

現在您也可以將敏感度標籤套用至 Microsoft 團隊、Office 365 群組和 SharePoint 網站。 如需此個別預覽的詳細資訊，請參閱[使用敏感度標籤與 Microsoft 團隊、Office 365 群組和 SharePoint 網站（公開預覽）](sensitivity-labels-teams-groups-sites.md)。

您隨時都可以選擇自願退出此預覽。

觀賞下列影片（無音訊）以查看這些新功能的動作：

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a>需求

這些功能僅適用于[敏感度標籤](sensitivity-labels.md)。 如果您目前已具備 Azure 資訊保護標籤，請先將它們遷移至靈敏度標籤，讓您可以針對您上傳的新檔案啟用這些功能。 如需相關指示，請參閱 how [to 將 Azure 資訊保護標籤遷移至統一敏感度標籤](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

在此預覽中，請在 Windows 上使用 OneDrive 同步處理應用程式版本19.002.0121.0008 或更新版本，在 Mac 上使用19.002.0107.0008 或更新版本。 這兩個版本都發行于2019年1月28日，而且目前已發佈給所有的振鈴。 如需詳細資訊，請參閱[OneDrive 發行附注](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。 啟用此預覽後，系統會提示執行舊版本的 sync 應用程式的使用者進行更新。

## <a name="limitations"></a>限制

- 當您啟用此預覽時，在 OneDrive 同步處理資料夾中的檔案上變更標籤的使用者，可能無法儲存對檔案所做的其他變更。  使用者看到[紅色圓圈時出現白色的交叉圖示錯誤](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)，並且要求您將新的變更儲存為個別的副本。  除了使用者所初始化的標籤變更之外，如果系統管理員變更已套用至使用者同步處理用戶端之檔案的已發行標籤設定，就會發生相同的行為。
    
    若要避免這些案例中的工作遺失，請執行下列其中一項動作：
    - 若要套用標籤，請使用 web 版本的 Office 應用程式。
    - 套用標籤後關閉檔案，然後重新開啟檔案以進行其他變更。

- SharePoint 不會自動將敏感度標籤套用至您已使用 Azure 資訊保護標籤加密的現有檔案。 相反地，若要在啟用此預覽後取得功能，請完成下列工作：
    
    1. 確定您已將 Azure 資訊保護標籤遷移至靈敏度標籤，並已從 Microsoft 365 規範中心（或對等標上的標記系統管理中心）發行。
    
    2. 下載檔案，然後將檔案上傳至 SharePoint。

- 當套用加密的標籤有下列兩種加密設定時，SharePoint 無法處理加密的檔案：
    - **讓使用者在套用標籤**和 [ **Word、PowerPoint 及 Excel 中**的核取方塊時，指定許可權，並選取 [提示使用者指定許可權]。 此設定有時稱為「使用者定義的許可權」。
    - 對**內容到期的使用者存取權**設定為**永不**值以外的值。
    
    如果是具有上述任一種加密設定的標籤，則網頁上的 Office 使用者不會看到標籤。 此外，此預覽的新功能也無法用於已經具有這些加密設定的已標記檔。 例如，即使更新這些檔，這些檔也不會在搜尋結果中傳回。

- 針對授與使用者編輯許可權的加密檔，在 Office 應用程式的 web 版本中無法封鎖複製。

- 不支援 Azure 資訊保護檔追蹤網站。

- Office 桌面應用程式和行動應用程式不支援共同撰寫。 相反地，這些應用程式會繼續以獨佔編輯模式開啟檔案。

- 如果已標示的檔上傳至 SharePoint，而標籤是使用服務主體名稱中的帳戶來套用加密，則無法在網頁上的 Office 中開啟該檔。 範例案例包括 Microsoft Cloud App Security，以及透過電子郵件傳送給小組的檔案。

- 使用者可能會在離線或轉入睡眠模式後遇到儲存問題，而不是使用 web Office 時，他們會使用桌面和行動應用程式進行 Word、Excel 或 PowerPoint。 針對這些使用者，當他們繼續其 Office 應用程式會話並嘗試儲存變更時，會看到上傳失敗訊息，並有一個選項可儲存副本，而不是儲存原始檔案。 

- 以下列方式加密的檔無法在 web 上的 Office 中開啟：
    - 使用內部部署機碼的加密（「保留您自己的金鑰」或 HYOK）
    - 獨立于標籤所套用的加密，例如直接套用 Rights Management protection 範本。

- 如果您刪除的標籤已套用至 SharePoint 中的檔，而不是從適當的標籤原則中移除標籤，則下載的檔不會標示或加密。 相比之下，如果標籤的檔儲存在 SharePoint 之外，當標籤刪除時，該檔仍會保持加密狀態。 請注意，雖然您可以在測試階段刪除標籤，但很少需要在實際執行環境中刪除標籤。

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a>為預覽準備 SharePoint Online 管理命令介面

啟用預覽之前，請確定您正在執行 SharePoint 線上管理命令介面版本16.0.19418.12000 或更新版本。 如果您已有最新版本，則可以繼續進行並啟用預覽。

1. 如果您已安裝來自 PowerShell 資源庫的舊版 SharePoint Online 管理命令介面，您可以執行下列 Cmdlet 來更新模組。

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. 或者，如果您已從 Microsoft 下載中心安裝舊版的 SharePoint Online 管理命令介面，您也可以移至 [**新增或移除程式**]，並卸載 SharePoint 線上管理命令介面。

3. 在網頁瀏覽器中，移至下載中心頁面，並[下載最新的 SharePoint Online 管理命令介面](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

4. 選取語言，然後按一下 [下載]****。

5. 在 x64 和 x86 .msi 檔案之間選擇。 如果您執行的是64位版本的 Windows 或 x86 檔案（如果您執行32位版本），請下載 x64 檔案。 如果您不知道，請參閱[我要執行哪一個 Windows 作業系統版本？](https://support.microsoft.com/help/13443/windows-which-operating-system)


6. 下載檔案之後，請執行檔，然後依照安裝精靈中的步驟進行。

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a>使用 Microsoft PowerShell 啟用預覽（自願加入）

若要啟用預覽，請使用 Set-SPOTenant Cmdlet：

1. 在 Office 365 中使用具有全域系統管理員或 SharePoint 系統管理員許可權的工作或學校帳戶，連接至 SharePoint。 若要了解如何進行，請參閱[開始使用 SharePoint Online 管理命令介面](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

2. 執行下列命令：

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a>在您建立或變更靈敏度標籤之後排程部署

在 Microsoft 365 規範中心內建立或變更靈敏度標籤之後，請分階段發佈。 如果您發佈尚未完全同步處理的標籤，當使用者將標籤套用至檔案，並將其上傳至 SharePoint 時，就無法在網頁版的 Office 應用程式中開啟檔案。 搜尋和 eDiscovery 也不適用於檔案。

我們建議您遵循下列步驟：

1. 僅將新的或修改過的敏感度標籤發佈給一或兩個人。

2. 在初始出版物過後等候至少24小時。 確認標籤已完全同步處理。

3. 更廣泛地發佈標籤。

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a>使用 Microsoft PowerShell 停用預覽（自願檢出）

如果您停用此預覽，您在預覽期間上傳的檔案會繼續受到標籤的保護。 會繼續強制執行對應的設定。 當您停用預覽後，將標籤套用至新的檔案時，全文搜尋、eDiscovery 和合著功能將不再運作。

若要停用預覽，請使用 Set-SPOTenant Cmdlet：

1. 在 Office 365 中使用具有全域系統管理員或 SharePoint 系統管理員許可權的工作或學校帳戶，連接至 SharePoint。 若要了解如何進行，請參閱[開始使用 SharePoint Online 管理命令介面](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

2. 執行下列命令：

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
