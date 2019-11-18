---
title: 在 Office 365 中搜尋內部部署使用者的雲端式的信箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: 用於安全性 & 合規性中心的內容搜尋工具來搜尋並匯出在 Exchange 混合式部署中的內部部署使用者 MicrosoftTeams 聊天室資料 （稱為 1xN 聊天室）。
ms.openlocfilehash: 97b849e682c0902b6a2d48919c2f2cd1257d8691
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2019
ms.locfileid: "38685647"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users-in-office-365"></a>在 Office 365 中搜尋內部部署使用者的雲端式的信箱

如果您的組織具有 Exchange 混合式部署，且已啟用 Microsoft Teams，使用者可以使用小組聊天應用程式的立即訊息。 雲端型使用者，（也稱為 1xN 聊天） 小組聊天資料會儲存至其主要的雲端式信箱。 當內部部署使用者使用的小組聊天應用程式時，其主要信箱是位於的內部。 若要解決這項限制，Microsoft 已發行位置 （稱為 「 內部部署使用者的基於雲端的信箱） 的雲端式存放裝置區域建立用來儲存內部部署使用者的小組聊天資料的新功能。 這可讓您在安全 & 與規範中心中使用內容搜尋工具來搜尋並匯出內部部署使用者的小組聊天資料。 
  
以下是設定為內部部署使用者的雲端式信箱的限制與需求：
  
- 您在內部部署目錄服務 （例如 Active Directory) 中的使用者帳戶必須與 Azure Active Directory，Office 365 中的目錄服務同步處理。 這表示郵件使用者帳戶在 Office 365 中建立，並為其主要信箱位於內部部署組織中的使用者相關聯。

- Microsoft Teams 授權] 及 [Exchange Online Plan 1 授權必須指派其主要信箱位於內部部署組織中的使用者。
    
- 內部部署使用者的雲端架構信箱是使用唯一的存放區小組聊天資料。 內部部署使用者無法登入的雲端架構信箱或任何的方式存取。 它不能用來傳送或接收電子郵件訊息。 
    
- 您必須將要求提交給 Microsoft 支援服務以啟用您的組織中搜尋的小組聊天資料內部部署使用者的雲端式信箱。 本文中，請參閱[歸檔啟用這項功能的 Microsoft 支援服務要求](#filing-a-request-with-microsoft-support-to-enable-this-feature)。 
    
 **附註：** 小組通道交談一律會儲存在小組與相關聯的雲端式信箱。 這表示您可以使用內容搜尋來搜尋通道交談沒有對支援服務歸檔。 如需關於搜尋小組通道交談，請參閱[搜尋 Microsoft Teams 和 Office 365 群組](content-search.md#searching-microsoft-teams-and-office-365-groups)。
  
## <a name="how-it-works"></a>運作方式

如果 Microsoft Teams 功能的使用者具有內部部署信箱，而且具有 /int/ 其使用者帳戶/身分識別同步處理至雲端，Microsoft 會建立雲端式信箱來存儲 1xN 小組聊天資料。 小組聊天資料會儲存在雲端架構信箱之後，它會編入搜尋索引。 這可讓您使用內容搜尋 （和 eDiscovery 案例相關聯的搜尋） 若要搜尋，預覽，並匯出內部部署使用者的小組聊天資料。 您也可以使用**\*ComplianceSearch**安全性 & 搜尋團隊的合規性中心 PowerShell 中的指令程式聊天室內部部署使用者的資料。 
  
下圖顯示如何小組聊天內部部署使用者的資料的工作流程的可搜尋、 預覽，並匯出。
  
![Microsoft Teams 中的內部部署使用者的雲端儲存空間](media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
除了這項新功能，您仍然可以使用內容搜尋搜尋、 預覽，並匯出雲端型 SharePoint 網站及 Exchange 信箱中的內容相關聯每個 Microsoft 小組及 1xN Teams 中的 Exchange Online 信箱的聊天室資料的小組雲端型使用者。

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a>若要啟用此功能與 Microsoft 支援服務要求歸檔

您必須將歸檔與 Microsoft 支援服務，讓您的組織使用圖形化使用者介面中安全性 & 規範中心搜尋內部部署使用者的雲端式信箱中的小組聊天資料。 在安全性 & 合規性中心 PowerShell 中使用這項功能。 您不需要將支援要求提交給使用 PowerShell 來搜尋內部部署使用者的小組聊天資料。 
  
當您將要求提交給 Microsoft 支援服務時，請包含下列資訊：
  
- Office 365 組織的預設網域名稱。
    
- 租用戶名稱與您的 Office 365 組織租用戶識別碼。 您可以找到這些在 Azure Active Directory 入口網站 (在 [**管理**] 下\>**屬性**)。 請參閱[尋找您的 Office 365 租用戶識別碼](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b)。
    
- 下列的標題或支援要求的用途的描述: [啟用應用程式內容搜尋的內部部署使用者]。 這有助於將要求路由傳送至 Office 365 電子文件探索工程團隊會實作要求者。 
    
工程變更後，Microsoft 支援服務會傳送給您評估的部署的日期。 部署程序通常需要 2 – 3 週後您提交支援要求。 
  
### <a name="what-happens-after-this-feature-is-enabled"></a>啟用此功能後，會發生什麼事？

這項功能在 Office 365 組織中部署之後，在內容搜尋和安全性 & 規範中心的 eDiscovery 案例相關聯的搜尋中，會進行下列變更：
  
- 在內容搜尋的**位置**會新增至**內部部署使用者的加入 Office 應用程式內容**] 核取方塊。 
    
    ![「 新增內部部署使用者的 Office 應用程式內容 」] 核取方塊新增至 「 內容搜尋 UI](media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- 在您用來選取要搜尋的使用者信箱的內容位置選擇器中會顯示內部部署使用者。 
    

  
## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a>搜尋內容的內部部署使用者的雲端式信箱中的小組聊天

啟用此功能之後，您可以使用安全性 & 規範中心的內容搜尋來搜尋內部部署使用者的雲端式信箱中的小組聊天資料。 
  
1. 在 [安全性 & 合規性中心，移至**搜尋** \> **內容搜尋**
    
2. 在 [**搜尋**] 頁面上，按一下 [![加入圖示](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新的搜尋**。
    
    如先前所述，**內部部署使用者的加入 Office 應用程式內容**] 核取方塊會顯示在 [**位置**] 下。 預設會選取它。
    
3. 建立關鍵字查詢，並將條件新增至搜尋查詢，必要時。 只搜尋的小組聊天資料，您可以在 [**關鍵字**] 方塊中新增下列查詢： 
    
    ```text
    kind:im
    ``` 

4. 此時，您可以選擇下列其中一個**位置**] 下的下列選項：
    
    - **所有位置：** 選取此選項可搜尋組織中的所有使用者的信箱。 選取核取方塊時，也可搜尋的內部部署使用者的所有雲端式信箱。 
    
    - **特定位置：** 選取此選項，然後按一下 [**修改**\>選擇使用者、 群組或小組來搜尋特定的信箱。 如先前所述，位置選擇器可讓您搜尋內部部署使用者。 
    
5. 儲存並執行搜尋。 從內部部署使用者的雲端式信箱的任何搜尋結果可以像任何其他的搜尋結果預覽。 您也可以將 （包括任何小組聊天資料） 的搜尋結果匯出至 PST 檔案。 如需詳細資訊，請參閱： 
    
    - [Create a search](content-search.md#create-a-search)
    
    - [Preview search results](content-search.md#preview-search-results)
    
    - [匯出內容搜尋結果](export-search-results.md)
    
## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a>使用 PowerShell 來搜尋小組聊天資料中的內部部署使用者的雲端式信箱

您可以使用**New-compliancesearch**和**Set-compliancesearch** cmdlet 安全性 & 合規性中心 PowerShell 中，搜尋內部部署使用者的雲端式信箱。 如先前所述，您不需要將支援要求提交給使用 PowerShell 來搜尋內部部署使用者的小組聊天資料。 
  
1. [連接到安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。
    
2. 執行下列 PowerShell 命令來建立搜尋內部部署使用者的雲端式信箱的內容搜尋。
    
    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    *IncludeUserAppContent*參數用來指定使用者或*ExchangeLocation*參數所指定的使用者的雲端式信箱。 *AllowNotFoundExchangeLocationsEnabled*允許雲端式信箱的內部部署使用者。 當您使用`$true`值，此參數，請搜尋不會嘗試之前，先執行驗證信箱是否存在。 這是必要搜尋內部部署使用者的基於雲端的信箱，因為這些類型的信箱不解決與一般信箱。 
    
    下列範例會搜尋小組聊天 （也就是立即訊息），包含關鍵字 「 redstone 」 中的雲端架構信箱的 Sara Davis，身為內部部署組織中的使用者 Contoso。
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   建立搜尋之後，請務必使用**Start-compliancesearch** cmdlet 來執行搜尋。 
  
使用這些 cmdlet 的詳細資訊，請參閱：
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)
    
- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)
    

## <a name="known-issues"></a>已知問題

- 目前，您可以僅搜尋、 預覽並在雲端式信箱中的內容匯出內部部署使用者。 將內部部署使用者的雲端架構信箱置於保留 eDiscovery 相關聯情況下，或是將它指派給 Office 365 保留原則不支援。 
    
- 電子文件探索的內容位置選擇器保留顯示內部使用者，並且會讓您選取他們。 不過，如同先前的說明保留不會套用到內部部署使用者。
    
## <a name="frequently-asked-questions"></a>常見問題集

 **內部部署使用者的雲端架構信箱位於何處？**
  
建立並儲存在相同的資料中心，為您的 Office 365 組織中的雲端架構信箱。 
  
 **是否有任何非提交支援要求的其他需求？**
  
 如先前所述，具有內部部署信箱的使用者的身分識別必須同步處理至雲端式組織，讓每個內部部署使用者帳戶在 Office 365 中建立對應的郵件使用者帳戶。 您的組織也必須擁有 Office 365 企業版訂閱，例如 Office 365 企業版 E1、 E3 或 E5 訂閱。 
  
 **是否有遺失小組聊天資料，如果使用者的內部部署信箱移轉到雲端的風險？**
  
否。 當您的內部部署使用者主要信箱遷移至雲端時，該使用者的小組聊天資料會移轉至其新雲端式主要信箱。
  
 **可以我套用 eDiscovery 保留或 Office 365 保留原則至內部部署使用者？**
  
否。
  
 **可以較舊的小組聊天內部部署使用者的時間之前我的組織的內容搜尋尋找提交要求以啟用這項功能嗎？**
  
Microsoft 已啟動的內部部署使用者的小組聊天資料儲存於 2018 年 1 月 31 日。 的話，如果此日期之後，已之間 Active Directory 和 Azure Active Directory 同步內部部署 microsoft Teams 使用者的身分識別，然後其小組聊天資料儲存在雲端式信箱中，而且可搜尋使用內容搜尋。 Microsoft 也將從 2018 年 1 月 31 日之前的小組聊天資料儲存在內部部署使用者的雲端式信箱中運作。 有關此的詳細資訊將會推出。

 **內部部署使用者需要授權才能小組聊天資料儲存在雲端架構信箱嗎？**
  
是。 若要在雲端式信箱中儲存內部部署使用者的小組聊天資料，使用者必須具有 Microsoft Teams 授權和 Exchange Online 計劃授權 Office 365 （或 Microsoft 365） 中。
