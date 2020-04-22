---
title: 使用 PST 集合工具，在您的組織中尋找、複製和刪除 PST 檔案
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid: MOE150
ms.assetid: 7a150c84-049c-4a9c-8c91-22355b35f2a7
description: 使用 Microsoft PST 集合工具來搜尋您組織的網路，以取得分散于整個組織中的 PST 檔案清單。 在您找到 PST 檔案之後，您可以使用 PST 集合工具將其複製到一個集中位置，這樣您就可以將它們匯入 Office 365。
ms.openlocfilehash: ee9a657cc0ac44e57e85edc68e80e0a76aa063d4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633328"
---
# <a name="use-the-pst-collection-tool-to-find-copy-and-delete-pst-files-in-your-organization"></a>使用 PST 集合工具，在您的組織中尋找、複製和刪除 PST 檔案

> [!IMPORTANT]
> Microsoft standard support program 或 service 不支援本文所述的 PST 集合工具。 此工具是以不含任何類型擔保的方式提供。 Microsoft 進一步否認所有暗示擔保，包括但不限於任何適售性或特定用途適用性的暗示擔保。 在使用或效能工具及檔的情況中，會繼續產生整個風險。 在任何事件中，Microsoft、其作者、無論使用或無法使用工具或檔，即使已告知 Microsoft 已被告知可能造成這類損害的任何損害（包括（但不限於）使用或無法使用工具或檔時，也會因使用或無法使用工具或檔而引起的任何損害（包括（但不限於）因使用或無法使用工具或檔而造成的任何損害（包括但不限於

您可以使用 Microsoft PST 集合工具來搜尋貴組織的網路中的 PST 檔案。 此工具可協助您取得分散于整個組織中的 PST 檔案清單。 在您找到 PST 檔案之後，您可以使用 PST 集合工具，將其複製到一個集中位置。 在單一位置擁有 Pst，便可將其匯入 Exchange Online 信箱（或單一 Exchange Online 信箱），您可以在其中將一組豐富的規範功能套用至 Office 365。 這包括將 Pst 匯入至使用者的封存信箱、搜尋使用 eDiscovery 搜尋工具匯入的 PST 檔案中的特定郵件、使用 eDiscovery 保留和保留原則來保留郵件，以及使用 Exchange Online 中的通訊記錄管理功能來管理這些郵件的生命週期。 確信您收集的 PST 檔案已成功匯入至 Office 365 之後，您可以使用該工具將其從網路上的原始位置刪除。 
  
您可以使用 PST 集合工具進行的另一件事是，讓使用者無法建立新的 PST 檔案，以及變更您在網路上找到的現有 PST 檔案。 這些「封鎖」功能可讓您尋找、收集和匯入一組已知的 PST 檔案至 Microsoft 365，並避免組織中未來大量增加的 PST 檔案。 
  
## <a name="how-the-pst-collection-tool-works"></a>PST 集合工具的運作方式

以下是使用 PST 集合工具在您的組織中尋找、控制、收集和刪除 PST 檔案的程式的簡介。
  
![PST 集合工具處理常式概述](../media/67a29f27-f83c-4f0a-9df4-7ed92d3086fe.png)
  
1. **[步驟1：在您的網路上尋找 pst](#step-1-find-pst-files-on-your-network)** 檔-當您執行工具以尋找 pst 檔案時，您會指定一個位置，例如包含用戶端和伺服器電腦之 Active Directory 物件的組織單位。 您也可以搜尋特定的機器或網路檔共用。 當您執行工具時，目的電腦上會安裝「輕量」集合代理程式。 這個代理程式會搜尋目的電腦的 PST 檔案，然後將資訊傳回 PST 集合工具，以瞭解它找到的任何 PST 檔案。 工具會建立記錄檔，其中包含在指定位置找到之 PST 檔案的相關資訊。 當您在後續步驟中執行工具時，就會使用這些檔案。 
    
2. **[（選用）步驟2：控制對 PST](#optional-step-2-control-access-to-pst-files)** 檔案的存取-此工具會建立群組原則物件（GPO），其設定可防止使用者建立或變更 PST 檔案。 此 GPO 會套用到您網域中的每位使用者。 此選用步驟可協助您 "鎖定" 步驟1中所找到的 PST 檔案，讓您可以收集、匯入和刪除這些檔案，而不需要建立新的 PST 檔案或變更現有的 PST 檔案。 
    
3. **[步驟3：將 pst 檔案複製到集合位置](#step-3-copy-the-pst-files-to-a-collection-location)**-這可讓您在一個位置收集 pst 檔案，讓您可以在步驟4中使用 Office 365 匯入服務將其匯入 Exchange Online 信箱。 當您在「收集」模式下執行工具時，每個集合代理程式會將該代理程式安裝所在目的電腦上的 PST 檔案複製到該集合位置。 
    
4. **[步驟4：將 pst 檔案匯入 Office 365](#step-4-import-the-pst-files-to-office-365)** -將 pst 檔案複製到一個位置之後，即可將其匯入 Exchange Online 信箱。 
    
5. **[步驟5：刪除在網路上找到的 pst](#step-5-delete-the-pst-files-found-on-your-network)** 檔案-當您找到及收集的 pst 檔案匯入 Office 365 中的 Exchange Online 信箱之後，您可以使用 pst 集合工具，從在步驟1中找到的原始位置刪除 pst 檔案。 

## <a name="before-you-begin"></a>開始之前

- 請遵循下列步驟，將 PST 集合工具下載到您的本機電腦。 
    
    1. [下載 PST 集合工具](https://aka.ms/pstcollectiontool)。
    
    2. 在快顯視窗中，按一下 [**另** \> **存新**檔]，將 PSTCollectionTool 儲存到本機電腦上的資料夾。 
    
    3. 將 PSTCollectionTool .zip 檔案解壓縮至本機電腦上的資料夾;預設的資料夾名稱是 PSTCollectionTool。
    
- 若要在任何模式中執行 PST 集合工具（Find、封鎖、複製或刪除），您必須是 Active Directory 網域中 Domain Administrators 群組的成員。 

## <a name="step-1-find-pst-files-on-your-network"></a>步驟1：在您的網路上尋找 PST 檔

第一步是執行 PST 集合工具，以在您的組織中尋找 PST 檔案。 您可以使用工具來搜尋下列類型的位置。 
  
- 內部部署 Active Directory 網域中的組織單位（Ou）。 工具會搜尋指定 OU 中包含的所有電腦。 
    
- 用戶端和伺服器電腦。 工具會搜尋指定的機器。 
    
- 網路檔共用。 工具會搜尋指定的網路檔共用。 
    
請參閱下列程式中`Locations`的參數的說明，以取得每個位置類型所使用之語法的範例。 
  
> [!IMPORTANT]
> 您必須先在尋找模式中執行 PST 集合工具，才能執行其他動作，例如封鎖、收集或刪除 PST 檔案。 
  
1. 在您的本機電腦上開啟命令提示字元（以系統管理員身分執行）。
    
2. 移至 PSTCollectionTool 資料夾（或您已解壓縮 PSTCollectionTool .zip 檔案的資料夾）。
    
3. 變更為 DataCollectorMaster 目錄。
    
4. 執行下列命令，在指定的位置尋找 PST 檔案。
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName <Name> -Locations <Locations to search for PSTs> -LogLocation <Location to store log files> -ConfigurationLocation <Location to store configuration files>
    ```

    下表說明當您執行 DataCollectorMaster 命令以尋找 PST 檔案時，參數及其必要的值。 
    
    |參數 * * * *|****描述****|範例 * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |會指定要搜尋之資料的類型。 目前，您可以使用 PST 集合工具來搜尋 PST 檔案。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |會指定工具將執行的作業類型。 使用此值`Find`可在指定的位置中尋找 PST 檔案。 請注意，此工具可以尋找並取得 Outlook 和 PST 檔案中已連接至 Outlook 設定檔的 PST 檔案的相關資訊。  <br/> | `-Mode Find` <br/> |
    | `JobName` <br/> |指定 PST 集合工作的名稱。 當您執行 PST 集合工具，以封鎖、收集和刪除在您執行工具以尋找 PST 檔案時所找到的 PST 檔案時，會使用相同的工作名稱。 工作名稱也會新增至記錄檔和設定檔案名。  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> | 指定一或多個要搜尋 PST 檔案的位置。 如果您指定一個以上的位置，請使用分號（;)分隔個別位置。 請務必使用雙引號（""）將此參數的個別值括住。  <br/><br/>   以下是您可以搜尋的位置類型所需的身分識別值格式。  <br/><br/>        **Ou** -使用辨別名稱（DN）來識別 ou;例如：`"OU=NorthAmerica,OU=NWRegion,OU=ITServices,DC=contoso,DC=com"` <br/> > [!IMPORTANT]> 您無法指定內建的電腦容器（例如，CN = 電腦、DC=contoso,DC=com "），因為它不是組織單位。<br/> <br/> **機器**-使用 DN 或完整功能變數名稱（FQDN）來識別網路上的用戶端和伺服器電腦。例如：  <br/>  Dn：`"CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"` <br/>  或  <br/>  Fqdn：`"FILESERVER01.contoso.com"` <br/><br/>  **網路檔案共用**-使用 UNC 名稱來識別網路檔共用;例如，`"\\FILESERVER02\Users"` <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `LogLocation` <br/> |指定將記錄檔複製到的資料夾。 如果資料夾不存在，則會在您執行工具時建立該資料夾。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ConfigurationLocation` <br/> |指定 .xml 設定檔將複製到的資料夾。 此檔案包含您執行工具時所找到之每個 PST 檔案的相關資訊。 當您在步驟3中執行工具，以複製所找到的 PST 檔案時，就會使用此檔案。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `ExcludedLocations` <br/> |此選用參數會指定要在尋找作業期間略過的位置。 您可以排除特定 Ou、電腦及網路檔案共用。 例如，您可以排除機器，例如已設定為 SQL server （或其他類型的應用程式伺服器）的機器，使用者沒有存取權。 如果您指定要排除的位置超過一個位置，請使用分號（;)分隔個別位置。 請務必使用雙引號（""）將此參數的個別值括住。  <br/> | `-ExcludedLocations "SQLSERVER01.contoso.com"` <br/> |
    | `ForceRestart` <br/> |此選用參數可讓您在尋找模式中為現有的 PST 集合工作執行工具。 當您使用此`ForceRestart`參數時，將會捨棄來自先前的「尋找」作業的結果，而且該工具將會重新掃描指定的位置，並建立新的記錄檔和設定檔。  <br/> | `-ForceRestart` <br/> |
   
    以下是針對每個參數使用實際值的 DataCollectorMaster 命令語法範例：
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -LogLocation "c:\users\admin\desktop\PSTCollection" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"
    ```

    在您執行此命令之後，會顯示詳細的狀態訊息，顯示在指定位置尋找 PST 檔案的進度。 經過一段時間後，最後的狀態訊息會顯示找到的 PST 檔案總數、工作是否已完成，以及是否有任何錯誤。 相同的狀態郵件會複製到 .log 檔。
    
### <a name="results-of-running-datacollectormasterexe-in-the-find-mode"></a>在尋找模式中執行 DataCollectorMaster 的結果

在您成功執行 PST 集合工具 [尋找] 模式後，會建立下列檔案，並將其`LogLocation`儲存在由和`ConfigurationLocation`參數指定的資料夾中。 
  
- ** \> _ _JobName Find\<DateTimeStamp\>-記錄檔包含顯示的狀態\<** 訊息。 此檔案會在`LogLocation`參數所指定的資料夾中建立。 
    
- ** \> _ _JobName 尋找\<DateTimeStamp\>-csv 檔案包含每個找到之 PST 檔案的\<** 列。 每個 PST 的資訊包括找到 PST 檔案所在的電腦、pst 檔案的完整檔案路徑位置、PST 檔案的擁有者，以及 PST 檔案的大小（kb，Kb）。 此檔案會在`LogLocation`參數所指定的資料夾中建立。 
    
    > [!TIP]
    > 在 Excel 中使用 AutoSum 工具，計算 CSV 檔案中所列的所有 PST 檔案總大小（以 KB 為單位）。 然後，您可以使用轉換計算機，將總大小轉換成百萬位元組（MB）或千百萬位元組（GB）。 
  
- ** \> _ _JobName find\<DateTimeStamp\>-xml 檔包含您在尋找模式中執行工具時所使用之參數值的相關\<** 資訊。 此檔案也包含每個找到之 PST 檔案的相關資訊。 當您為相同的工作執行重新執行工具以封鎖、收集或刪除所找到的 PST 檔案時，就會使用此檔案中的資料。 此檔案會在`ConfigurationLocation`參數所指定的資料夾中建立。 
    
    > [!IMPORTANT]
    > 請勿重新命名、變更或移動此檔案。 當您在相同工作的封鎖、複製或刪除模式中重新執行工具時，它會由 PST 集合工具使用。 

## <a name="optional-step-2-control-access-to-pst-files"></a>選步驟2：控制 PST 檔案的存取

此選用步驟可讓您 "鎖定" 步驟1中所找到的 PST 檔案，讓您可以將一組已知的 PST 檔收集和匯入至 Office 365。 當您在封鎖模式中執行 PST 集合工具時，會發生下列情況： 
  
- 工具會建立名為*PST Usage Controls*的群組原則物件（GPO）。 此 GPO 會連結到您的網域，並套用至您組織中所有已驗證的使用者。 
    
- PST 使用方式控制 GPO 會在您組織中的機器上建立登錄設定。 根據您使用的參數，您可以建立登錄設定，以防止使用者建立新的 PST 檔案和登錄設定，以防止使用者變更現有的 PST 檔案。
    
> [!NOTE]
> 如果控制對您的組織的存取 PST 檔案的存取過於中斷，您可以考慮略過此步驟，並執行步驟3，將 PST 檔案複製到中央位置。 然後，您可以重複步驟1進行相同的工作（使用`ForceRestart`參數），以尋找將 pst 檔案複製到集合位置之後所建立的其他 pst 檔案。 如果找到新的 PST 檔案，您可以將其複製到集合位置。 當您在 [ `ForceRestart`尋找] 模式中重新執行工具時使用參數時，會捨棄工作先前的尋找作業的結果，而且該工具將會重新掃描指定的位置。 

若要封鎖 PST 檔案的存取：

1. 在您的本機電腦上開啟命令提示字元（以系統管理員身分執行）。
    
2. 移至您下載 PST 集合工具所在的目錄。
    
3. 執行下列命令，以封鎖對步驟1中所找到之 PST 檔案的存取。

    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -BlockChangesToFiles -BlockNewFiles
    ```

    下表說明當您執行 DataCollectorMaster 命令以封鎖 PST 檔案的建立和變更時，參數及其必要的值。 
    
    |參數 * * * *|****描述****|範例 * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |會指定要搜尋之資料的類型。 目前，您可以使用 PST 集合工具來搜尋 PST 檔案。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |會指定工具將執行的作業類型。 使用此值`Block`可防止使用者建立新的 pst 檔案，以及變更現有的 pst 檔案。  <br/> | `-Mode Block` <br/> |
    | `JobName` <br/> |指定現有 PST 集合工作的名稱。 您必須使用這個相同的工作名稱，當您在步驟1的 [尋找] 模式中執行工具時使用。 當您以封鎖模式執行該工具時，此工作名稱也會新增至所建立的記錄檔名稱。  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |指定資料夾包含當您在 [尋找] 模式中執行工具時所建立的 .xml 設定檔。 使用您在步驟1中用於此參數的相同值。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |指定要將封鎖作業的記錄檔複製到其中的資料夾。 這是選用的參數。 若未加入，記錄檔會複製到您下載 PST 集合工具所在的資料夾。 當您在步驟1的尋找模式中執行工具時，請考慮使用與您使用的相同記錄位置，以便將所有記錄檔儲存在相同的資料夾中。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `BlockChangesToFiles` <br/> |使用此參數可防止使用者變更 PST 檔案。 當您使用此參數時，會建立下列登錄專案： `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\PST\PstDisableGrow`並將資料值設為1。 當您在封鎖模式中執行 PST 集合工具時所建立的 GPO，就會在組織中的機器上建立此登錄設定。  <br/> | `-BlockChangesToFiles` <br/> |
    | `BlockNewFiles` <br/> |使用此參數可防止使用者建立新的 PST 檔案、開啟和匯入 PST 檔案至 Outlook，以及從 Outlook 匯出 PST 檔案。 當您使用此參數時，會建立下列登錄專案： `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\DisablePst`並將資料值設為1。 當您在封鎖模式中執行 PST 集合工具時所建立的 GPO，就會在組織中的機器上建立此登錄設定。  <br/> | `-BlockNewFiles` <br/> |
   
    以下是針對每個參數使用實際值的 DataCollectorMaster 命令語法範例：

    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection" -BlockChangesToFiles -BlockNewFiles
    ```

    系統會提示您確認是否要封鎖新的 PST 檔案或現有 PST 檔案的變更。 在您確認要繼續且該命令成功執行後，就會顯示一則訊息，指出已建立新的 GPO （名為「PST 使用控制」）。
    
## <a name="step-3-copy-the-pst-files-to-a-collection-location"></a>步驟3：將 PST 檔案複製到集合位置

下一步是複製您在尋找模式中執行 PST 集合工具時所找到的 PST 檔案。 這可讓您在一個位置收集 PST 檔案，讓您稍後將其匯入 Office 365。 將 PST 檔案複製到集合位置之前，請考慮決定所需的儲存空間總容量。 您可以使用步驟1中建立的 CSV 檔案，計算所有 PST 檔案的總大小。
  
> [!NOTE]
> 將 PST 檔案匯入至 Microsoft 365 並將其從原始位置刪除之後，您可能會想要在此步驟中從複製這些檔案的集合位置中刪除這些檔案。 
  
1. 在您的本機電腦上開啟命令提示字元（以系統管理員身分執行）。
    
2. 移至您下載 PST 集合工具所在的目錄。
    
3. 執行下列命令，將 PST 檔案複製到指定的位置。
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName <Name of job from Step 1> -Locations <same locations from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    下表說明當您執行 DataCollectorMaster 命令以複製 PST 檔案時，參數及其必要的值。 
    
    |參數 * * * *|****描述****|範例 * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |會指定要搜尋之資料的類型。 目前，您可以使用 PST 集合工具來搜尋 PST 檔案。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |會指定工具將執行的作業類型。 使用此值`Collect`可複製您在 [尋找] 模式中執行工具時所找到的 PST 檔案。 請注意，此工具可以複製 Outlook 中開啟的 PST 檔案，並複製連接至 Outlook 設定檔的 PST 檔案。  <br/> | `-Mode Collect` <br/> |
    | `JobName` <br/> |指定現有 PST 集合工作的名稱。 您必須使用這個相同的工作名稱，當您在步驟1的 [尋找] 模式中執行工具時使用。 當您在收集模式中執行工具時，此工作名稱也會新增至所建立的記錄檔名稱。  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> |使用您在步驟1中用於`Locations`參數的相同值。 如果您想要在步驟5中重新執行工具以刪除其來源位置的 PST 檔案，請在收集模式下執行該工具時包含此參數。  <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"; "CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `ConfigurationLocation` <br/> |指定包含您在尋找模式中執行工具時所建立的 .xml 設定檔所在的資料夾。 使用您在步驟1中用於此參數的相同值。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop \PSTCollection\Configuration"` <br/> |
    | `CopyLocation` <br/> |指定您要將 PST 檔案複製到的集合位置。 您可以將檔案複製到檔案伺服器、網路檔共用或硬碟。 在收集模式中執行工具之前，必須已存在位置。 工具不會建立位置，而且會傳回錯誤，指出該位置不存在。  <br/> 此外，您還必須寫入此參數所指定之集合位置的許可權。  <br/> | `-CopyLocation "\\FILESERVER03\PSTs"` <br/> |
    | `LogLocation` <br/> |指定要將收集模式的記錄檔複製到的資料夾。 這是選用的參數。 若未加入，記錄檔會複製到您下載 PST 集合工具所在的資料夾。 當您在步驟1的尋找模式中執行工具時，請考慮使用與您使用的相同記錄位置，以便將所有記錄檔儲存在相同的資料夾中。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |此選用參數可讓您在集合模式中為現有的 PST 集合工作重新執行工具。 如果您先前在收集模式中執行工具，但接著使用`ForceRestart`切換命令重新掃描位置以重新掃描 pst 檔案，您可以使用此參數在集合模式中重新執行該工具，然後在重新掃描位置時，重新複製 pst 檔案。 當您在`ForceRestart`集合模式中使用切換參數時，此工具會略過任何先前的集合作業，並且會嘗試從零開始複製 PST 檔案。  <br/> | `-ForceRestart` <br/> |
   
    以下是 DataCollectorMaster 工具之語法的範例，使用每個參數的實際值：
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -CopyLocation "\\FILESERVER03\PSTs" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    在您執行此命令之後，會顯示詳細的狀態訊息，顯示收集步驟1中所找到之 PST 檔案的進度。 經過一段時間後，會顯示最終狀態訊息是否有任何錯誤和記錄的複製位置。 相同的狀態郵件會複製到 .log 檔。
    
### <a name="results-of-running-datacollectormasterexe-in-the-collect-mode"></a>在收集模式中執行 DataCollectorMaster 的結果

在收集模式中成功執行 DataCollectorMaster 之後，會建立下列檔案，並將其`LogLocation`儲存在由和`ConfigurationLocation`參數指定的資料夾中。 
  
- ** \> _ _JobName 收集\<DateTimeStamp\>-記錄檔包含所顯示的狀態\<** 訊息。 此檔案會在`LogLocation`參數所指定的資料夾中建立。 
    
- ** \> _ _JobName 收集\<DateTimeStamp\>-xml 檔案只會包含在收集模式中執行工具時所使用之參數值的相關\<** 資訊。 當您執行重新執行 DataCollectorMaster 工具以刪除 PST 檔案時，會使用此檔案中的資料;請參閱[步驟 5](#step-5-delete-the-pst-files-found-on-your-network)。
    

## <a name="step-4-import-the-pst-files-to-office-365"></a>步驟4：將 PST 檔案匯入 Office 365

在您收集步驟1中找到的 PST 檔案之後，下一步是將其匯入 Office 365 中的信箱。 在元件或匯入程式中，您必須建立 CSV 對應檔，其中包含您要匯入之每個 PST 檔案的資料列。 每一列中的資訊都會指定 PST 檔的名稱、使用者的電子郵件地址，以及是否要將 PST 檔案匯入至使用者的主要或封存信箱。 使用**JobName\>_尋找_\<DateTimeStamp**檔案中的資訊（在步驟1中建立），以協助您建立 csv 對應檔。 
  
如需將 PST 檔案匯入至 Office 365 的逐步指示，請參閱下列其中一個主題：
  
- [使用網路上傳將 PST 檔案匯入 Office 365](use-network-upload-to-import-pst-files.md)
    
- [使用磁碟機寄送將 PST 檔案匯入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    

## <a name="step-5-delete-the-pst-files-found-on-your-network"></a>步驟5：刪除在您的網路上找到的 PST 檔案

當您找到及收集的 PST 檔案匯入 Office 365 中的 Exchange Online 信箱之後，您可以使用 PST 集合工具，從在步驟1中找到的原始來源位置刪除 PST 檔案。 
  
1. 在您的本機電腦上開啟命令提示字元（以系統管理員身分執行）。
    
2. 移至您下載 PST 集合工具所在的目錄。
    
3. 執行下列命令以刪除 PST 檔案。

    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    下表說明當您執行 DataCollectorMaster 命令以刪除 PST 檔案時，參數及其必要的值。 
    
    |參數 * * * *|****描述****|範例 * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |會指定要搜尋之資料的類型。 目前，您可以使用 PST 集合工具來搜尋 PST 檔案。 ![間隔](../media/b078d05c-3aee-4b9f-8805-6a8a9d8970ee.png)           <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |會指定工具將執行的作業類型。 使用此值`Delete`可刪除您在 [尋找] 模式中執行工具時所找到的 PST 檔案。  <br/> | `-Mode Delete` <br/> |
    | `JobName` <br/> |指定現有 PST 集合工作的名稱。 您必須使用此相同的工作名稱，當您在 [搜尋模式] 和 [步驟 3] 中的收集模式下執行工具時使用。 當您以刪除模式執行工具時，此工作名稱也會新增至所建立的記錄檔名稱。  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |指定在收集模式中執行工具時所建立的 .xml 設定檔所在的資料夾。 使用您在步驟3中用於此參數的相同值。  <br/> | `-ConfigurationLocation "c:\users\admin\ desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |指定要將刪除模式的記錄檔複製到其中的資料夾。 這是選用的參數。 若未加入，記錄檔會複製到您下載 PST 集合工具所在的資料夾。 在 [步驟 1] 和 [步驟 3] 中的 [尋找及收集模式] 中執行工具時，請考慮使用相同的記錄位置，以便將所有記錄檔儲存在相同的資料夾中。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |此選用參數可讓您在現有 PST 集合工作的刪除模式中重新執行工具。 如果您先前已在刪除模式中執行工具，但接著透過`ForceRestart`切換器重新掃描位置以重新掃描 pst 檔案，您可以使用此參數，在刪除模式中重新執行工具，並刪除重新掃描位置時找到的 PST 檔案。 當以刪除`ForceRestart`模式使用切換參數時，此工具會略過任何先前的 Delete 作業，並嘗試再次刪除 PST 檔案。  <br/> | `-ForceRestart` <br/> 

    以下是 DataCollectorMaster 工具之語法的範例，使用每個參數的實際值：
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    在您執行此命令之後，會顯示詳細的狀態訊息，顯示在步驟1中找到的 PST 檔案刪除的進度，並在步驟3中收集。 經過一段時間後，會顯示最終狀態訊息是否有任何錯誤和記錄的複製位置。 相同的狀態郵件會複製到 .log 檔。
    
### <a name="results-of-running-datacollectormasterexe-in-the-delete-mode"></a>在刪除模式中執行 DataCollectorMaster 的結果

在刪除模式中成功執行 DataCollectorMaster 之後，會建立下列檔案，並將其`LogLocation`儲存在由和`ConfigurationLocation`參數指定的資料夾中。 
  
- ** \> _ _JobName 刪除\<DateTimeStamp\>-記錄檔包含顯示的狀態\<** 訊息。 此檔案會在`LogLocation`參數所指定的資料夾中建立。 
    
- ** \> _ _JobName 刪除\<DateTimeStamp\>-xml 檔案只會包含在刪除模式中執行工具時所使用之參數值的相關\<** 資訊。 它也會列出已刪除之每個 PST 檔案的名稱及檔案路徑。 此檔案會在`ConfigurationLocation`參數所指定的資料夾中建立。 
