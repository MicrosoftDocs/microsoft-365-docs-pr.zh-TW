---
title: 了解客戶金鑰的可用性金鑰
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 瞭解用於復原遺失之客戶機碼的可用性金鑰。
ms.openlocfilehash: 4f4dfdff0aa1c7ebe6dd1266c82c6fd290913a3e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345091"
---
# <a name="learn-about-the-availability-key-for-customer-key"></a>了解客戶金鑰的可用性金鑰

可用性機碼是當您建立資料加密原則時，會自動產生及布建的根機碼。 Microsoft 365 儲存及保護可用性金鑰。 可用性機碼的功能類似于您用來提供服務加密的兩個根機碼與客戶金鑰。 可用性金鑰會將金鑰階層中的機碼一個層級向下回繞。 不同于您在 Azure Key Vault 中提供和管理的金鑰，您無法直接存取可用性金鑰。 Microsoft 365 自動化服務以以程式設計方式管理可用性金鑰。 這些服務會啟動永不包括直接存取可用性機碼的自動作業。

可用性機碼的主要用途是從所管理的根機碼的未預期遺失中提供復原功能。 遺失可能是 mismanagement 或惡意動作的結果。 如果您喪失根機碼的控制權，請聯繫 Microsoft 支援人員和 Microsoft，以協助您使用可用性金鑰進行復原。 您將使用可用性金鑰，透過您布建的新根機碼遷移至新的資料加密原則。

根據三個原因，可用性機碼的儲存體和控制會特意不同于 Azure 金鑰保存庫機碼：

- 如果同時控制所有 Azure 金鑰保存庫機碼，可用性金鑰會提供復原「中斷玻璃」功能。
- 邏輯控制項與安全儲存位置的分離，可提供深入防護，並防止所有金鑰和您的資料遺失，也就是從單一攻擊或失敗點。
- 如果 Microsoft 365 服務因暫時性錯誤而無法到達 Azure key Vault 中主控的金鑰，可用性金鑰會提供高可用性的功能。 此規則只適用于 Exchange Online 和商務用 Skype 服務加密。 SharePoint線上、商務用 OneDrive 和 Teams 檔案永遠不會使用可用性金鑰，除非您明確指示 Microsoft 啟動復原程式。

共用責任若要保護您的資料，請使用各種保護和程式進行金鑰管理，最後降低所有按鍵 (的風險，因此您的資料) 會永久遺失或損毀。 當您離開服務時，Microsoft 會為您提供停用或銷毀可用性機碼的唯一授權。 根據設計，Microsoft 沒有任何人能夠存取可用性金鑰：只有 Microsoft 365 服務程式代碼可以存取它。

如需如何保護金鑰的詳細資訊，請參閱 [Microsoft 信任中心](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) 。
  
## <a name="availability-key-uses"></a>可用性金鑰使用

可用性機碼針對主要 vault 的外部 malefactor 或惡意擁有人員竊取控制權，或當不慎 mismanagement 導致根機碼遺失時，提供復原功能。 這項修復功能適用于所有與客戶金鑰相容的 Microsoft 365 服務。 個別服務使用可用性金鑰的方式不同。 Microsoft 365 只會以下文所述的方式使用可用性金鑰。

### <a name="exchange-online-and-skype-for-business-uses"></a>Exchange Online 和商務用 Skype 使用

除了復原能力之外，Exchange Online 和商務用 Skype 使用可用性金鑰，以確保暫時性或間歇運作問題（與存取根機碼的服務相關）中的資料可用性。 當服務因暫時性錯誤而無法到達 Azure Key Vault 中的任何客戶金鑰時，服務會自動使用可用性金鑰。 服務永不直接直接移到可用性金鑰。

Exchange Online 和商務用 Skype 中的自動化系統可能會在暫時性錯誤期間使用可用性金鑰，以支援自動化的後端服務，例如防病毒、電子探索、資料遺失防護、信箱移動和資料索引。

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-uses"></a>SharePoint線上、商務用 OneDrive 和 Teams 檔案使用

針對 SharePoint 線上、商務用 OneDrive 及 Teams 檔案，可用性機碼永遠不會在復原功能外使用，而且客戶必須明確指示 Microsoft 在復原案例中開始使用可用性金鑰。 自動化服務作業完全依賴您在 Azure Key vault 中的客戶金鑰。 如需有關這些服務之重要階層如何運作的深入資訊，請參閱[SharePoint 線上、商務用 OneDrive 及 Teams 檔案如何使用可用性金鑰](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key)。

## <a name="availability-key-security"></a>可用性金鑰安全性

Microsoft 會以您的方式具現化可用性金鑰並採取大量措施加以保護，分享資料保護的責任。 Microsoft 不會公開對客戶可用性機碼的直接控制權。 例如，您只能 (旋轉) 您在 Azure Key Vault 中擁有的金鑰。 如需詳細資訊，請參閱 [滾或輪替客戶金鑰或可用性金鑰](customer-key-availability-key-roll.md)。

### <a name="availability-key-secret-stores"></a>可用性金鑰密碼存放區

Microsoft 會在存取控制的內部機密存放區中，像客戶對向的 Azure 重要存放庫，保護可用性金鑰。 我們會執行存取控制，以防止 Microsoft 系統管理員直接存取中所含的機密。 機密儲存區作業（包括金鑰輪替和刪除）會透過自動化命令進行，而這些命令永遠不會包含對可用性金鑰的直接存取權。 機密存放區管理作業會限制在特定的工程師，並且需要透過內部工具（密碼箱）進行許可權提升。 許可權提升需要管理員核准和理由才能授與。 密碼箱可確保在時間到期或工程師登出時，存取受限於自動存取撤銷。

**Exchange Online 和商務用 Skype** 可用性機碼儲存于 Exchange Online 的 Active Directory 機密存放區中。 可用性機碼會安全地儲存在 Active Directory 網域控制站內租使用者特定容器內。 這種安全的儲存位置與 SharePoint 線上、商務用 OneDrive 和 Teams 檔案機密存放區分開和隔離。

**SharePoint 線上、商務用 OneDrive 和 Teams** 檔案可用性機碼儲存在由服務小組所管理的內部機密存放區中。 這種安全的機密儲存體服務，具有應用程式端點和 SQL Database 作為後端的前端伺服器。 可用性機碼會儲存在 SQL Database 中，而且會以機密存放區加密金鑰 (加密) ，以使用 AES-256 和 HMAC 的組合來加密靜態的可用性金鑰。 機密儲存區加密機碼會儲存在相同 SQL Database 的邏輯隔離元件中，而且會以 Microsoft 憑證授權單位 (CA) 所管理之憑證中包含的 RSA-2048 機碼進一步加密。 這些憑證會儲存在針對資料庫執行作業的機密存放區前端伺服器中。

### <a name="defense-in-depth"></a>深入防護

Microsoft 採用縱深防禦策略，防止惡意參與者影響儲存在 Microsoft 雲端中的客戶資料的機密性、完整性或可用性。 實施特定的預防和偵探控制措施，以保護機密存放區和可用性機碼，作為總體安全性策略的一部分。

建立 Microsoft 365 以避免濫用可用性金鑰。 應用層是唯一一種方法，可讓您用來加密及解密資料的索引鍵（包括可用性金鑰）。 只有 Microsoft 365 服務程式代碼能夠轉譯及遍歷金鑰階層，以進行加密和解密活動。 客戶金鑰、可用性機碼、其他階層機碼和客戶資料的儲存位置之間存在邏輯隔離。 這項隔離可降低事件中的一個或多個位置遭到破壞時，資料洩密的風險。 階層中的每一層都有內建的「全天候入侵偵測」功能，以保護儲存的資料和機密。

會執行存取控制，以防止對內部系統進行未經授權的存取，包括可用性金鑰機密存放區。 Microsoft 工程師無法直接存取可用性金鑰機密存放區。 如需存取控制的其他詳細資訊，請參閱[Microsoft 365 中的管理存取控制](/Office365/securitycompliance/office-365-administrative-access-controls-overview)。

技術控制措施可防止 Microsoft 人員登入高許可權的服務帳戶，攻擊者可能會使用這些帳戶來冒充 Microsoft 服務。 例如，這些控制措施會防止互動式登入。

安全性記錄和監控控制項是另一個防禦防護的防禦措施，可降低 Microsoft 服務和資料的風險。 Microsoft 服務小組已部署使用中監控解決方案，以產生警示和審核記錄。 所有服務小組都會將其記錄上傳至中央存放庫，其中記錄會進行匯總和處理。 內部工具會自動檢查記錄，以確認服務是否以最佳、具彈性且安全的狀態運作。 已標記不尋常的活動以進一步複查。

任何指出可能違反 Microsoft 安全原則的記錄事件，都會立即進入 Microsoft 安全小組的注意力。 Microsoft 365 安全性已設定警示，以偵測嘗試存取可用性金鑰機密存放區。 如果 Microsoft 人員嘗試以互動式方式登入服務帳戶，而這是由存取控制所禁止和保護的，也會產生警示。 Microsoft 365 安全性也會偵測和警示 Microsoft 365 服務與一般基準作業的偏差。 Malefactors 企圖濫用 Microsoft 365 服務會觸發警示，導致罪犯從 Microsoft cloud 環境逐出。

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>使用可用性金鑰從金鑰遺失中復原

如果您喪失客戶機碼的控制權，可用性金鑰可讓您復原和重新加密您的資料。

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Exchange Online 與商務用 Skype 的復原程式

如果您喪失客戶機碼的控制權，可用性金鑰可讓您復原資料，並使受影響的 Microsoft 365 資源回到線上。 當您復原時，可用性機碼會繼續保護您的資料。在高層次上，若要完全從金鑰遺失中復原，您必須建立新的 DEP，並將受影響的資源移至新的原則。

若要使用新的客戶金鑰來加密您的資料，請在 Azure Key Vault 中建立新的金鑰，使用新的客戶機碼建立新的 DEP，然後將新的 DEP 指派給目前使用舊 DEP （金鑰已遺失或損毀）加密的信箱。

這種重新加密處理常式可能需要長達72小時。 當您變更 DEP 時，這是標準持續時間。
  
### <a name="recovery-procedure-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint 線上、商務用 OneDrive 及 Teams 檔案的復原程式

針對 SharePoint 線上、商務用 OneDrive 及 Teams 檔案，可用性機碼永遠不會在復原能力以外使用。 您必須明確指示 Microsoft 在復原案例中開始使用可用性金鑰。 若要啟動修復程式，請與 Microsoft 聯繫以啟用可用性金鑰。 一旦啟用，可用性金鑰即會自動用於解密您的資料，讓您可以使用新建立的 DEP （與新的客戶機碼相關聯）來加密資料。  

此作業與您組織中的網站數目成正比。 一旦您呼叫 Microsoft 使用可用性金鑰，您應該在大約四小時內完全線上。

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>Exchange Online 和商務用 Skype 如何使用可用性金鑰

當您建立具有客戶機碼的 dep 時，Microsoft 365 會產生與該 dep 相關聯 (dep 金鑰) 的資料加密原則機碼。 服務會將 DEP 機碼加密三次：一次使用每個客戶機碼，然後使用可用性金鑰。 只會儲存加密版本的 DEP 機碼，而且 DEP 機碼只能使用客戶機碼或可用性金鑰解密。 然後，使用 DEP 機碼加密個別信箱的信箱金鑰。
  
Microsoft 365 遵循此程式，在客戶使用此服務時，解密及提供資料：
  
1. 使用客戶金鑰解密 DEP 金鑰。

2. 使用解密的 DEP 金鑰來解密信箱金鑰。

3. 使用解密的信箱金鑰來解密信箱本身，讓您可以存取信箱內的資料。

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>SharePoint 線上、商務用 OneDrive 及 Teams 檔案如何使用可用性金鑰

客戶金鑰和可用性機碼的 SharePoint 線上和商務用 OneDrive 架構及實施與 Exchange Online 和商務用 Skype 不同。
  
當組織移至客戶管理的金鑰時，Microsoft 365 會 (TIK) 建立組織特有的中間機碼。 Microsoft 365 會使用每個客戶機碼一次加密 TIK，並儲存兩個加密版本的 TIK。 只會儲存 TIK 的加密版本，且只能使用客戶機碼解密 TIK。 然後使用 TIK 加密網站機碼，然後用來加密 blob 金鑰 (也稱為「檔案區塊金鑰) 。 根據檔案大小，服務可以使用唯一金鑰將檔案分割成多個檔區塊。 blob (檔區塊) 會以 blob 金鑰加密，並儲存在 Microsoft Azure blob 儲存體服務中。
  
Microsoft 365 遵循此程式，在客戶使用服務時，解密及提供客戶檔案：

1. 使用客戶金鑰組 TIK 進行解密。

2. 使用解密的 TIK 來解密網站金鑰。

3. 使用解密的網站金鑰來解密 blob 金鑰。

4. 使用解密的 blob 金鑰來解密 blob。

Microsoft 365 以輕微位移的方式發出兩個解密要求到 Azure Key Vault，以解密 TIK。 Furnishes 結果的第一個，請取消其他要求。
  
若您喪失客戶機碼的存取權，Microsoft 365 也會利用可用性金鑰來加密 TIK，並將它與 TIKs 加密的每個客戶機碼一起儲存。 只有當客戶呼叫 Microsoft 以在存取其機碼失敗時（惡意或無意）存取其金鑰時，才會使用以可用性金鑰加密的 TIK。
  
出於可用性與縮放原因，已解密的 TIKs 會在一個時段有限的記憶體快取中快取。 TIK 快取的兩個小時設定為過期後，Microsoft 365 會嘗試解密每個 TIK。 解密 TIKs 會延伸快取的存留期。 如果 TIK 解密失敗很長一段時間，Microsoft 365 會產生警示，以在快取到期之前通知工程。 只有在客戶撥打 microsoft 時，才會 Microsoft 365 初始化復原作業，此作業會以儲存在 microsoft 機密存放區中的可用性金鑰來解密 TIK，並使用解密的 TIK 及一組新的客戶提供的 Azure key Vault 金鑰來重新加入租使用者。
  
到目前為止，客戶金鑰會包含在 Azure blob 儲存區中儲存的 SharePoint 線上檔案資料的加密和解密鏈，但不會 SharePoint 線上清單專案或 SQL Database 中儲存的中繼資料。 Microsoft 365 不會使用 Exchange Online、商務用 Skype、SharePoint 線上、商務用 OneDrive 和 Teams 等檔案（由客戶發起的案例）以外的可用性金鑰。 客戶資料的人員存取受到客戶資料箱的保護。

## <a name="availability-key-triggers"></a>可用性機碼觸發器

Microsoft 365 會在特定情況下觸發可用性機碼。 這些情況會因服務而有所不同。

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Exchange Online 和商務用 Skype 的觸發器
  
1. Microsoft 365 讀取信箱所指派的 DEP，以決定 Azure Key Vault 中的兩個客戶機碼位置。

2. Microsoft 365 會從 DEP 中隨機播放兩個客戶機碼之一，然後將要求傳送至 Azure 金鑰 Vault，以使用客戶金鑰解對 dep 金鑰。

3. 如果使用客戶金鑰解包 DEP 金鑰的要求失敗，Microsoft 365 會將第二個要求傳送至 Azure key Vault，這次指示它使用備用 (第二個) 客戶金鑰。

4. 如果第二個要求使用客戶機碼解對 DEP 機碼的要求失敗，Microsoft 365 會檢查這兩個要求的結果。

    - 如果檢查會判斷傳回系統錯誤失敗的要求：

       - Microsoft 365 會觸發可用性金鑰來解密 DEP 機碼。

       - Microsoft 365 然後使用 DEP 金鑰來解密信箱機碼，並完成使用者要求。 

       - 在此情況下，Azure Key Vault 可能由於暫時性錯誤而無法回應或無法存取。

    - 如果考試判斷傳回拒絕存取失敗的要求：

       - 這表示有故意、無意或惡意的動作可轉譯客戶機碼 (例如，在將服務) 的情況下，進行資料清除處理常式。

       - 在此情況下，可用性金鑰只會用於系統動作，而不適用於使用者動作，使用者要求會失敗，且使用者會收到錯誤訊息。

>[!IMPORTANT]
>Microsoft 365 服務程式代碼永遠都具有有效的登入權杖，以用於透過客戶資料提供增值雲端服務。 因此，在刪除可用性機碼之前，可將其當作 Exchange Online 和商務用 Skype （如搜尋索引建立或移動信箱）所啟動的動作，用作後備。 這同時適用于暫時性錯誤和存取 Azure Key Vault 的拒絕要求。

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint 線上、商務用 OneDrive 及 Teams 檔的觸發器

針對 SharePoint 線上、商務用 OneDrive 及 Teams 檔案，可用性機碼永遠不會在復原功能外使用，而且客戶必須明確指示 Microsoft 在復原案例中開始使用可用性金鑰。

## <a name="audit-logs-and-the-availability-key"></a>審核記錄和可用性金鑰

Microsoft 365 中的自動系統處理所有資料流程過系統以提供雲端服務，例如，反病毒、電子探索、資料遺失防護和資料索引。 Microsoft 365 不會產生此活動的客戶可見記錄。 此外，Microsoft 人員不會在這些一般系統作業中存取您的資料。

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>Exchange Online 和商務用 Skype 可用性機碼記錄

當 Exchange Online 和商務用 Skype 存取可用性機碼以提供服務時，Microsoft 365 會發佈從安全性與合規性中心可存取的客戶可見記錄檔。 每當服務使用可用性金鑰時，就會產生可用性機碼作業的審計記錄記錄。 名為 "Customer Key Service Encryption" 的新記錄類型，其 activity type "Fallback to Availability Key" 可讓系統管理員篩選 [整合的審計記錄](./search-the-audit-log-in-security-and-compliance.md) 搜尋結果，以查看可用性機碼記錄。

記錄檔包含諸如日期、時間、活動、組織識別碼及資料加密原則識別碼等屬性。 記錄可以做為整合的審計記錄檔的一部分，而且可以從安全性 & 合規性中心審核記錄檔搜尋] 索引標籤進行存取。

![可用性機碼事件的審計記錄搜尋](../media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

Exchange Online 和商務用 Skype 可用性機碼記錄使用已新增自訂參數的 Office 365 管理活動[通用架構](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)： Policy Id、範圍鍵版本識別碼和要求識別碼。

![可用性機碼自訂參數](../media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>SharePoint線上、商務用 OneDrive 和 Teams 檔案可用性機碼記錄

可用性機碼記錄尚未提供這些服務。 針對 SharePoint 線上、商務用 OneDrive 及 Teams 檔案，只有在由 Microsoft 所指示時，才會啟動可用性金鑰，以供復原之用。 因此，您已知道每個可用於這些服務之可用性金鑰的事件。

## <a name="availability-key-in-the-customer-key-hierarchy"></a>客戶金鑰階層中的可用性金鑰
  
Microsoft 365 會使用可用性金鑰來包裝為客戶金鑰服務加密所建立之金鑰階層中低的機碼層。 服務之間存在不同的主要階層。 金鑰演算法也會在每個適用服務階層中的可用性機碼和其他機碼之間有所不同。 不同服務使用的可用性金鑰演算法如下：

- Exchange Online 和商務用 Skype 可用性金鑰使用 AES-256。

- SharePoint 線上、商務用 OneDrive 及 Teams 檔案可用性機碼使用 RSA-2048。

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>用來加密 Exchange Online 和商務用 Skype 金鑰的加密密碼

![Exchange Online 客戶機碼的加密密碼](../media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>用於 SharePoint 線上及商務用 OneDrive 加密金鑰的加密密碼

![SharePoint Online 客戶機碼的加密密碼](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>相關文章

- [客戶金鑰服務加密](customer-key-overview.md)

- [設定客戶金鑰](customer-key-set-up.md)

- [管理客戶金鑰](customer-key-manage.md)

- [滾動或旋轉客戶金鑰或可用性金鑰](customer-key-availability-key-roll.md)