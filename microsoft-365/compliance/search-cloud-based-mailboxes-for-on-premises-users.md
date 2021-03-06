---
title: 搜尋內部部署使用者的 Teams 聊天資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: 使用 Microsoft 365 中的電子文件探索工具，在 Exchange 混合式部署中搜尋及匯出內部部署使用者的 Teams 聊天資料。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab59c179b62903dd5f1ddd9b718f81a1ac78923a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311795"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a>搜尋內部部署使用者的 Teams 聊天資料

如果貴組織使用 Exchange 混合式部署 (或將內部部署的 Exchange 組織與 Office 365 同步)，且已啟用 Microsoft Teams，則內部部署使用者可以使用 Teams 聊天應用程式傳遞立即訊息。 針對雲端式使用者，Teams 聊天資料 (又稱為 *1 對 1 或 1 對多聊天*) 會儲存到其主要雲端式信箱。 內部部署使用者使用 Teams 聊天應用程式時，其聊天訊息無法儲存在其主要信箱 (位於內部部署)。 為了避免此限制，Microsoft 已發佈新功能，其中建立了雲端式儲存區，以便您可以使用電子文件探索工具來搜尋及匯出內部部署使用者的 Teams 聊天資料。
  
以下是為內部部署使用者啟用雲端式儲存體的要求和限制：
  
- 內部部署目錄服務 (例如 Active Directory) 的使用者帳戶必須與 Azure Active Directory (Microsoft 365 中的目錄服務) 同步。 這表示會在 Microsoft 365 中建立郵件使用者帳戶，並將該帳戶與主要信箱位於內部部署組織中的使用者相關聯。

- 主要信箱位於內部部署組織中的使用者必須受指派 Microsoft Teams 授權和 Exchange Online 方案 1 授權 (最低要求)。

- 如果組織沒有 Exchange 混合式部署，則必須將內部部署 Exchange 結構描述同步處理至 Azure Active Directory。 如果您沒有這樣做，則可能會有為在內部部署 Exchange 組織中擁有信箱的使用者，於 Exchange Online 中建立重複的雲端式信箱的風險。

- 只有與內部部署使用者相關聯的 Teams 聊天資料，才會儲存在雲端式儲存空間。 內部部署使用者無法以任何方式存取此儲存區。

> [!NOTE]
> Teams 頻道交談一律會儲存在與團隊相關聯的雲端式信箱中，這表示您可以搜尋頻道交談。 如需有關搜尋 Teams 頻道交談的詳細資訊，請參閱[搜尋 Microsoft Teams 和 Microsoft 365 群組](content-search-reference.md#searching-microsoft-teams-and-microsoft-365-groups)。
  
## <a name="how-it-works"></a>運作方式

如果已啟用 Microsoft Teams 的使用者具有內部部署信箱，且其使用者帳戶/身分識別已同步到雲端，Microsoft 會建立雲端式儲存體來與內部部署使用者的 1 對多 Teams 聊天資料產生關聯。 系統會為內部部署使用者的 Teams 聊天資料編製索引，以便搜尋。 這可讓您使用內容搜尋 (以及與核心電子文件探索和進階電子文件探索案例相關聯的搜尋) 來搜尋、預覽及匯出內部部署使用者的 Teams 聊天資料。 您也可以使用安全性與合規性中心 PowerShell 中的 **\*ComplianceSearch** Cmdlet 搜尋內部部署使用者的 Teams 聊天資料。
  
下圖顯示搜尋、預覽及匯出內部部署使用者的 Teams 聊天資料的工作流程。
  
![Microsoft Teams 內部部署使用者的雲端式儲存空間](../media/EHAMShard1.png)
  
除了此功能，您也可以使用電子文件探索工具來搜尋、預覽及匯出小組中與每個 Microsoft Team 相關聯的雲端式 SharePoint 網站和 Exchange 信箱中的 Teams 內容，以及雲端式使用者 Exchange Online 信箱中的 1xN Teams 聊天資料。

### <a name="how-this-feature-is-supported-in-content-search-and-core-ediscovery-search-tools"></a>內容搜尋和核心電子文件探索搜尋工具中如何支援此功能

內容搜尋和 Microsoft 365 合規性中心中與核心電子文件探索案例相關聯的搜尋工具中的下列 UI 元素：
  
- [內容搜尋] 工具的 [位置] 精靈頁面上，預設會顯示和選取 [為內部部署使用者新增 App 內容] 核取方塊。 保持選取此核取方塊，以在內容搜尋中包括內部部署使用者的雲端式儲存空間。

    ![[為內部部署使用者新增 Office App 內容] 核取方塊會新增到內容搜尋 UI](../media/EHAMShardCheckBox.png)
  
- 當您選擇要搜尋的特定使用者時，您可以搜尋內部部署使用者。

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a>搜尋內部部署使用者的 Teams 聊天內容

以下說明如何使用 Microsoft 365 合規性中心的內容搜尋來搜尋內部部署使用者的 Teams 聊天資料。
  
1. 在 Microsoft 365 合規性中心，前往 [內容搜尋 **]**。

2. 在 [搜尋] 索引標籤中，按一下 [新增搜尋]，然後命名新的搜尋。

3. 在 [位置] 頁面上，針對 Exchange 信箱將開關設定為 [開啟]。 請注意，預設會顯示並選取 [為內部部署使用者新增 App 內容]。

4. 若要搜尋特定使用者的 Teams 內容，選取 [選擇使用者、群組或團隊] 並選擇要納入搜尋的特定使用者。 否則，按一下 [下一步] 搜尋所有使用者(包括內部部署使用者) 的 Teams 內容

5. 在 [定義搜尋條件] 頁面上，建立關鍵字查詢，並在必要時將條件新增到搜尋查詢。 若只要搜尋 Team 聊天資料，您可以在 [關鍵字] 方塊中新增下列查詢：

    ```text
    kind:im AND kind:microsoftteams
    ```

6. 儲存並執行搜尋。 任何內部部署使用者的搜尋結果都可以像其他搜尋結果一樣預覽。 您也可以將搜尋結果 (包括任何 Teams 聊天資料) 匯出至 PST 檔案。 如需詳細資訊，請參閱：

    - [建立搜尋](content-search.md)

    - [預覽搜尋結果](preview-ediscovery-search-results.md)

    - [匯出搜尋結果](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a>使用 PowerShell 來搜尋內部部署使用者的 Teams 聊天資料

您可以在安全性與合規性中心 PowerShell 中使用 **New-ComplianceSearch** 和 **Set-ComplianceSearch** Cmdlet 來搜尋內部部署使用者的 Teams 聊天資料。 如先前所述，您不需要提交支援要求，即可使用 PowerShell 來搜尋內部部署使用者的 Teams 聊天資料。
  
1. [連線到安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。

2. 執行下列 PowerShell 命令來建立可搜尋內部部署使用者 Teams 聊天資料的內容搜尋。

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    *IncludeUserAppContent* 參數是用於為 *ExchangeLocation* 參數指定的一位或多位使用者指定雲端式儲存體。 *AllowNotFoundExchangeLocationsEnabled* 能讓您為內部部署使用者搜尋雲端式儲存區。 使用此參數的 `$true` 值時，搜尋在執行前不會嘗試驗證信箱是否存在。 這是搜尋內部部署使用者的雲端式儲存區所需，因為此雲端式儲存區無法解析為一般的雲端式信箱。

    下列範例會在 Sara Davis 的雲端式儲存空間中搜尋包含關鍵字 "redstone" 的 Teams 聊天，Sara Davis 是 Contoso 組織的內部部署使用者。
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND (kind:im AND kind:microsoftteams)" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   建立搜尋後，請務必使用 **Start-ComplianceSearch** Cmdlet 執行搜尋。
  
如需使用這些 Cmdlet 的相關資訊，請參閱：
  
- [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)

- [Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch)

- [Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a>已知問題

- 目前，您可以搜尋、預覽及匯出內部部署使用者的 Teams 聊天資料。 您也可以將內部部署使用者的 Teams 聊天資料置於與核心或進階電子文件探索案例相關聯的保留中，並為內部部署使用者的 Teams 聊天或頻道訊息套用保留原則。 不過，目前無法為內部部署使用者套用其他內容位置 (例如 Exchange 信箱和 SharePoint 網站) 的保留原則。

## <a name="frequently-asked-questions"></a>常見問題集

**我是否必須提交支援要求，才能搜尋內部部署使用者的聊天訊息？**

否。 此功能預設會針對所有組織啟用。 在一個時間點，您確實必須連絡 Microsoft 支援服務，但此情況已不存在。
  
 **電子郵件探索工具可以在針對所有組織預設啟用此功能的時間點之前，尋找內部部署使用者的較舊 Teams 聊天資料嗎？**
  
Microsoft 從 2018 年 1 月 31 日開始為內部部署使用者儲存 Teams 聊天資料。因此，如果內部部署 Teams 使用者的身分識別已在您的內部部署 Active Directory 和 Microsoft 365 中的 Azure Active Directory 之間同步，則自該日起，其 Teams 聊天資料會儲存在雲端，並可使用電子文件探索工具來搜尋。

 **內部部署使用者是否需要授權，才能在雲端中儲存其 Teams 聊天資料？**
  
是。若要在雲端式儲存空間中儲存內部部署使用者的 Teams 聊天資料，必須在 Office 365 (或 Microsoft 365) 中為該使用者指派 Microsoft Teams 授權和 Exchange Online 方案授權。

**內部部署使用者的雲端儲存區位在何處？**
  
Teams 交談資料會儲存在內部部署使用者的慣用資料位置 (PDL)。 PDL 可在單一地理位置和多地理位置環境中採用。 如需詳細資訊，請參閱 [Microsoft 365 多地理位置](../enterprise/microsoft-365-multi-geo.md)。

**如果使用者的內部部署信箱已移轉至雲端，是否有遺失 Teams 聊天資料的風險？**
  
否。將內部部署使用者的主要信箱移轉到雲端時，該使用者的 Teams 聊天資料就會移轉至新的雲端式主要信箱。
  
 **可以將電子文件探索保留或保留原則套用至內部部署使用者嗎？**
  
是。 您可以為內部部署使用者的 Teams 聊天和頻道訊息套用電子文件探索保留或保留原則。 不過，若要保留或保存內部部署使用者的 Teams 內容，則必須為內部部署使用者指派 Exchange Online 方案 2 授權。
