---
title: Office 365 中使用客戶金鑰的服務加密常見問題集
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/31/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 41ae293a-bd5c-4083-acd8-e1a2b4329da6
description: '[比較基準，透過 BitLocker 與分散式金鑰管理員 (DKM)，而啟用的磁碟區層級加密除了 Office 365 提供多一層的 Office 365，包括資料從 Exchange 中的客戶內容應用程式層級的加密Online、 Skype for Business、 SharePoint Online 和商務用 OneDrive。 這稱為服務加密。'
ms.openlocfilehash: a2285db4bd5ff5594c6b766dcad8909f0442d3ce
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597450"
---
# <a name="service-encryption-with-customer-key-for-office-365-faq"></a>Office 365 中使用客戶金鑰的服務加密常見問題集

[比較基準，透過 BitLocker 與分散式金鑰管理員 (DKM)，而啟用的磁碟區層級加密除了 Office 365 提供多一層的 Office 365，包括資料從 Exchange 中的客戶內容應用程式層級的加密Online、 Skype for Business、 SharePoint Online 和商務用 OneDrive。 這稱為服務加密。
  
客戶金鑰服務加密做為基礎，並可讓您提供和控制機碼是用來加密存放在 Office 365[線上服務條款 (OST)](https://www.microsoft.com/Licensing/product-licensing/products.aspx)中所述。 客戶金鑰可協助您符合規範，因為您可以控制加密金鑰，Office 365 會使用該金鑰來解密資料。
  
客戶金鑰，包括文件中，提供意見反應傳送您的想法、 建議及觀點來看給 customerkeyfeedback@microsoft.com。
  
## <a name="what-is-service-encryption-with-customer-key"></a>使用客戶金鑰服務加密為何？

客戶金鑰可增強組織能夠滿足指定索引鍵的排列方式與雲端服務提供者的符合性需求。 使用客戶金鑰，您可以提供和控制您 Office 365 資料待用應用程式層級的加密金鑰。 如此一來，您可能會演練控制項及撤銷貴組織的機碼，您應該決定結束 「 服務。 藉由撤銷機碼，此資料是服務無法讀取。 索引鍵被撤銷是向資料刪除路徑上的第一個步驟。

## <a name="what-office-365-data-at-rest-is-covered-by-customer-key"></a>客戶金鑰涵蓋靜態哪些 Office 365 資料？
<a name="WhatDataIsCoveredbyCustomerKey"> </a>

涵蓋 SharePoint Online 站台內容和儲存在該站台上的檔案及上傳到商務用 OneDrive 檔案。 涵蓋 Exchange Online 信箱內容 （電子郵件內文、 行事曆項目和電子郵件附件的內容）。 涵蓋從商務用 Skype 的文字交談，但不是包含 Skype 會議廣播錄製和 Skype 會議內容上傳。 Skype 會議廣播和 Skype 會議內容上傳加密以及 Office 365 中的所有其他內容，但我們目前不提供客戶控制項的加密金鑰。
  
## <a name="what-is-the-difference-between-customer-key-and-bring-your-own-key-byok-with-azure-information-protection-for-exchange-online"></a>客戶金鑰和攜帶您自己金鑰 (BYOK) 與 Azure 資訊保護 Exchange online 之間的差異為何？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

這兩個選項可讓您提供和控制加密金鑰。不過，使用客戶金鑰服務加密來加密存放，位於 Office 365 伺服器待用，使用 Azure 資訊保護 Exchange Online 的 BYOK 加密中加密您的資料，以及提供持續性的線上與離線時適用於電子郵件和附件的 Office 365 的保護。 客戶金鑰 BYOK 使用 Azure 資訊保護 Exchange Online 的互補，且不論您選擇使用 Microsoft 的服務管理機碼或您自己的金鑰，加密待用資料及傳輸中可提供從新增的保護惡意攻擊。
  
使用 Azure 資訊保護 Exchange Online 的 BYOK 被提供在 Office 365 郵件加密功能。
  
## <a name="does-office-365-message-encryption-and-bring-your-own-key-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>沒有 Office 365 郵件加密和攜帶您自己的金鑰與 Azure 資訊保護變更 Microsoft 的方法為協力廠商資料要求，例如 subpoenas 嗎？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

否。 Office 365 郵件加密和選項，以提供並控制您自己的加密金鑰的攜帶您自己金鑰 (BYOK) 的 Azure 資訊保護已並非特別設計用來回應法律強制執行 subpoenas。 Office 365 郵件加密與 AIP 的 BYOK 專為合規性焦點的客戶，必須符合其內部或外部合規義務。 Microsoft 會非常重視採用客戶資料的第三方的要求。 為雲端服務提供者，我們一直主張針對客戶資料的隱私權。 事件中我們取得傳票，我們一直嘗試將協力廠商重新導向至客戶取得的資訊。 (請參閱將 Smith 部落格: [ Protecting 客戶資料從政府側錄](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。 我們會定期發行我們收到的要求的詳細的資訊[以下](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data)。
  
請參閱[Microsoft 信任中心](https://www.microsoft.com/trustcenter/default.aspx)有關協力廠商資料要求和 「 外洩的客戶資料 」 的[線上服務條款 (OST)](https://www.microsoft.com/Licensing/product-licensing/products.aspx)如需詳細資訊。
  
## <a name="does-service-encryption-with-customer-key-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>使用客戶金鑰服務加密是否變更 Microsoft 方法協力廠商資料要求，例如 subpoenas？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

否。 客戶金鑰已並非特別設計用來回應法律強制執行 subpoenas。 設計以符合其內部或外部合規義務受管制客戶。 Microsoft 會非常重視採用客戶資料的第三方的要求。 為雲端服務提供者，我們一直主張針對客戶資料的隱私權。 事件中我們取得傳票，我們一直嘗試將協力廠商重新導向至客戶取得的資訊。 (請參閱將 Smith 部落格: [ Protecting 客戶資料從政府側錄](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。 我們會定期發行我們收到的要求的詳細的資訊[以下](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)。
  
請參閱[Microsoft 信任中心](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data)有關協力廠商資料要求和 「 外洩的客戶資料 」 的[線上服務條款 (OST)](https://www.microsoft.com/Licensing/product-licensing/products.aspx)如需詳細資訊。 
  
## <a name="is-fasttrack-support-available-for-implementing-customer-key"></a>是 FastTrack 支援適用於實作客戶金鑰？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

否。 FastTrack 只用來收集租用戶和服務所需為客戶金鑰註冊組態資訊。 客戶金鑰可提供發佈透過 FastTrack，使其便於客戶和合作夥伴送出這個所需的資訊，使用相同的方法，以及簡化封存中提議的客戶提供的資料。
  
如果您需要額外的支援超過文件，請連絡 Microsoft 諮詢服務 (MCS)、 Premier Field Engineering (PFE) 或 Microsoft 合作夥伴以尋求協助。
  
## <a name="if-my-keys-are-destroyed-how-can-i-recover"></a>如果我金鑰已毀損，要如何修復？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性機碼為您提供復原您管理的根機碼未預期遺失的功能。 如果您遺失根機碼，連絡 Microsoft 支援服務與 Microsoft 將協助您完成啟用可用性機碼的程序。 您將使用的可用性機碼來使用佈建您的新金鑰將遷移至新的資料加密原則。 
  
## <a name="what-is-the-availability-key"></a>什麼是可用性金鑰？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性機碼是當您建立的資料加密原則佈建根機碼。 儲存及保護 Office 365 內的可用性機碼並具有相同的作用類似於服務加密搭配使用您所提供，使用客戶金鑰的兩個根機碼。 不同於您提供並管理 Azure 金鑰保存庫中的機碼，您無法直接存取可用性機碼。 儲存區和可用性機碼的控制是刻意不同於 Azure Key Vault 機碼的三個原因： 首先，可用性金鑰提供高可用性功能時，Office 365 服務將無法連線到裝載於 Azure 金鑰的機碼儲藏室;第二，可用性金鑰提供 「 中斷玻璃 」 功能時，便會遺失; 這兩個 Azure Key Vault 機碼和第三邏輯控制項的區隔提供深度防禦提供保護，避免從單一的攻擊的所有索引鍵的遺失或失敗點。 共用保護機碼，同時使用各種不同的保護和處理程序的金鑰管理責任最終可降低風險，所有金鑰 （，因此您的資料） 將會遺失或損毀。 Microsoft 為您提供權力透過損毀的可用性機碼。 根據設計，在 Microsoft 沒有人有權存取可用性金鑰-這不是藉由 Office 365 服務的程式碼。
  
## <a name="how-many-data-encryption-policies-deps-can-i-create"></a>可以建立多少資料加密原則 (DEPs)？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和商務用 Skype:** 您可以建立最多 50 個 DEPs。 
  
 **SharePoint Online 和商務用 OneDrive:** DEP 適用於在一個地理位置，也稱為 「 地理位置的資料。 如果您使用 Office 365 的多地理位置功能，您可以建立一個 DEP 每個地理位置。 如果您不使用多地理位置，您可以建立一個相依性
  
## <a name="can-i-assign-a-data-encryption-policy-before-migrating-a-mailbox-to-the-cloud"></a>可以指派資料加密原則前的信箱移轉至雲端嗎？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可以。 您可以使用資料加密原則 (DEP) 指派的 Windows PowerShell cmdlet Set-mailuser 之前的信箱移轉到 Office 365 使用者。 當您這麼做時，將內容移轉的方式使用指派的 DEP 加密信箱的內容。 這可以是比指派 DEP 已遷移信箱之後，然後再等候才需要耗費數小時或可能是幾天的地方加密更有效率。 
  
## <a name="how-do-i-verify-that-encryption-with-customer-key-is-activated-and-office-365-has-finished-encrypting-with-customer-key"></a>如何確認會在啟動使用客戶金鑰加密和使用客戶金鑰加密完成 Office 365？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和商務用 Skype:** 您可以[使用連線到 Exchange Online 遠端 PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx) ，然後使用 **[Get-mailboxstatistics]** 指令程式，針對您想要檢查每個信箱。 Get-mailboxstatistics 指令程式的輸出，在_IsEncrypted_屬性傳回的值 **，則為 true**如果信箱已加密，值為**false**如果它不是。 如果信箱已加密， _DataEncryptionPolicyID_屬性的傳回值是用來加密信箱 DEP 的 GUID。 如需有關如何執行此 cmdlet 的詳細資訊，請參閱[Get-mailboxstatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx)和使用 PowerShell 與 Exchange Online。 
  
如果信箱未加密之後等待 72 小時的時間您指派 DEP，起始信箱移動。 若要這麼做，請[使用連線到 Exchange Online 遠端 PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)然後使用 New-moverequest 指令程式，並提供信箱的別名，如下所示： 
  
```powershell
New-MoveRequest <alias>
```

 **SharePoint Online 和商務用 OneDrive:** 您可以[連線到 SharePoint Online PowerShell](https://technet.microsoft.com/library/fp161372.aspx)，然後使用 **[Get-SPODataEncryptionPolicy]** 指令程式來檢查您的租用戶的狀態。 * *_狀態_* * 屬性會傳回的**登錄**值，如果啟用客戶金鑰加密和已加密的所有網站中的所有檔案。 仍在進行加密時，此 cmdlet 提供資訊已完成百分比的網站。 
  
## <a name="if-i-want-to-switch-to-a-different-set-of-keys-how-long-does-it-take-for-the-new-set-of-keys-to-protect-my-data"></a>如果我想要切換至一組不同的按鍵，多久多久一組新的金鑰來保護我的資料？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和商務用 Skype:** 可能需要多達 72 小時來保護信箱根據新資料加密原則 (DEP) 從新 DEP 指派給信箱的時間。 
  
 **SharePoint Online 和商務用 OneDrive:** 可能需要最多四個小時後已被指派新的金鑰重新加密整個租用。 
  
## <a name="is-my-existing-data-stored-without-encryption-at-any-time-while-it-is-decrypted-or-encrypted-with-customer-key"></a>我現有的資料儲存沒有任何時候加密時解密，或使用客戶金鑰加密嗎？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

否。 BitLocker 與 DKM 的 Office 365 服務中的靜態永遠加密您的資料。 如需詳細資訊，請參閱 「 安全性、 隱私權和 Office 365 的合規性資訊 」，以及[如何 Exchange Online 保護您電子郵件機密資料](https://support.office.com/article/989BA10C-F73F-4EFB-AD1B-AF3322E5F376)。
  
## <a name="if-i-no-longer-want-to-use-customer-managed-encryption-keys-can-i-switch-to-microsoft-managed-keys"></a>如果我不想再使用客戶管理加密金鑰，可以切換到 Microsoft 受管理的機碼？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和商務用 Skype:** 尚未。 一旦廣泛地使用 Microsoft 受管理的機碼的服務加密 Office 365 中導入，這將會支援。 我們預期會推出此服務中我們使用客戶金鑰發行服務加密之後。 
  
 **SharePoint Online 和商務用 OneDrive:**[是]。 您可以選擇要還原使用 Microsoft 受管理的機碼分別為每個地理位置 （如果您使用多地理位置功能） 或所有資料如果它是在單一地理位置中。 
  
## <a name="if-i-lose-my-keys-how-long-does-it-take-to-recover-service-availability-using-the-recovery-key"></a>如果我遺失我機碼，多久需要復原使用復原金鑰的服務可用性？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和商務用 Skype:** 一旦您呼叫使用可用性鍵時，信箱將會存取在幾分鐘內。 
  
 **SharePoint Online 和商務用 OneDrive:** 這項作業是您所擁有的網站數目調和間距。 一旦您呼叫 Microsoft，以使用可用性機碼，您就可以完全線上約四個小時內。 
  
## <a name="how-is-the-availability-key-used-with-exchange-online"></a>與 Exchange Online 如何使用可用性金鑰？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性索引鍵用三種方式與 Exchange Online:
  
- 服務可用性-的 Azure Key Vault 機碼的代理人連線。
    
- 動作起始由 Office 365 服務的程式碼-例如搜尋索引建立或移動信箱。
    
- 復原從主要遺失-例如遺失與單一相依性關聯這兩個 Azure Key Vault 機碼
    
 **在事件 Azure Key Vault 機碼的代理人連線，則您可以用於服務可用性可用性機碼。**
  
Office 365 會使用可用性金鑰同時適用於服務的可用性和復原從狀況不良的客戶金鑰狀態的 Exchange Online。 沒有使用客戶金鑰的機碼的階層。 這個階層架構，如下圖所示。
  
![圖形顯示金鑰的階層中客戶金鑰](media/a760156b-737f-469a-80ab-c28b7a8b9160.png)
  
如果這兩個 Azure Key Vault 索引鍵的單一資料加密原則 (DEP) 都無法使用，Office 365 可用於可用性金鑰變更為新的相依性 Office 365 會決定是否使用可用性金鑰的服務可用性，以不同方式根據是否使用者起始的活動，例如，當使用者下載電子郵件 Outlook 用戶端，或系統啟動活動，例如編製索引信箱內容，或 eDiscovery 搜尋，觸發程序。
  
Office 365 會遵循此程序，以回應使用者起始動作，以判斷是否可用於使用者信箱的可用性機碼：
  
1. Office 365 會讀取信箱來判斷 Azure 金鑰保存庫中的兩個客戶機碼位置指派 DEP。
    
2. Office 365 隨機選擇下列其中一個兩個客戶金鑰從 DEP，然後將要求傳送至 Azure 金鑰保存庫解除包裝使用客戶金鑰 DEP 機碼。
    
3. 如果要求以解除包裝 DEP 主要使用客戶金鑰失敗，並傳回錯誤，Office 365 第二個將要求傳送至 Azure Key Vault 指示 」，以使用替代這段時間 （秒） 的客戶金鑰。
    
4. 如果第二個要求解除包裝使用客戶金鑰失敗 DEP 機碼，並傳回錯誤，Office 365 會檢查這兩個要求的結果：
    
  - 如果檢查判斷錯誤不會反映由客戶 identity 明確巨集指令，Office 365 會使用可用性金鑰來解密 DEP 金鑰。 DEP 鍵然後用來解密信箱金鑰並完成使用者要求。
    
    在此情況下，Azure 金鑰保存庫是任何原因無法回應或無法連線。 Office 365 鑰決定如果客戶是刻意要撤銷存取的金鑰。
    
  - 如果檢查指出該謹慎地做出巨集指令已採取來轉譯客戶金鑰無法使用，然後將不會使用可用性金鑰、 使用者要求失敗，且使用者會收到錯誤訊息，例如登入失敗。
    
    發生這種情況，客戶可以得知服務會受到影響，以及客戶金鑰的條件為狀況不良。 例如，如果客戶組織中所有信箱都使用單一 DEP，客戶可能會遇到： 使用者無法存取其信箱時遇到的普遍失敗。 這可確保兩個客戶金鑰狀況不良時，客戶會進行更正這個錯誤，並還原至良好的服務需要注意。
    
 **使用可用性金鑰起始由 Office 365 服務的程式碼的動作。**
  
Office 365 服務的程式碼總是具有有效的登入權杖，並無法被封鎖。 因此，直到可用性金鑰已遭刪除，它可以用於起始，或是內部，Office 365 服務的程式碼，例如搜尋索引建立或移動信箱的動作。
  
 **使用可用性金鑰復原金鑰遺失。**
  
您可以使用可用性鍵復原遺失的相關聯的相同 DEP，如所述的答案的常見問題集項目中 「 如果我金鑰已毀損，要如何修復？ 」 這兩個 Azure Key Vault 機碼。
  
## <a name="how-is-the-availability-key-used-with-sharepoint-online-and-onedrive-for-business"></a>如何可用性金鑰搭配使用 SharePoint Online 和 OneDrive for Business？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

SharePoint Online 和 OneDrive for Business 架構、 實作客戶金鑰及可用性的機碼是不同於 Exchange Online 和商務用 Skype。
  
當客戶移至客戶管理機碼時，Office 365 會建立租用戶特定中繼機碼 (TIK)。 Office 365 加密 TIK 兩次，一次使用每個客戶金鑰，並將儲存兩個 TIK 加密的版本。 儲存 TIK 的加密的版本，以及 TIK 只能使用客戶金鑰解密。 TIK 然後用來加密網站金鑰，然後用來加密 blob 機碼。 Blob 本身會加密並儲存在 Microsoft Azure Blob 儲存體服務。
  
Office 365 會遵循此程序來存取 blob 具有客戶檔案資料：
  
1. 解密使用客戶金鑰 TIK。
    
2. 使用解密的 TIK 網站金鑰解密。
    
3. 使用解密的網站金鑰來解密 blob 金鑰。
    
4. 使用解密的 blob 金鑰來解密 blob。
    
當解密 TIK，Office 365 發出，用兩個解密要求來 Azure Key Vault 稍微偏移。 若要完成的第一個提供結果，取消其他要求。
  
萬一客戶會失去存取其客戶機碼，Office 365 也使用可用性金鑰加密 TIK，並將此儲存以及與每個客戶金鑰加密 TIKs。 使用可用性金鑰加密 TIK 只適用於客戶會呼叫 Microsoft 編列復原路徑時遭到惡意或不小心，它們有其機碼，遺失存取。
  
對於可用性和規模原因，已解密的 TIKs 快取時間限制記憶體快取中。 兩個小時才能 TIK 快取設為過期，Office 365 會嘗試解密每個 TIK。 解密 TIKs 延伸的快取的存留期。 如果 TIK 解密失敗相當長的時間，Office 365 就會產生通知的快取到期時間之前工程警示。 只有當客戶會呼叫 Microsoft Office 365 會起始復原作業，其中包括解密 TIK 和一組新的 Microsoft 秘密存放區和上架再次使用 [解密租用戶中儲存與可用性機碼 TIK 嗎客戶提供 Azure Key Vault 鍵。
  
截至今天，客戶金鑰涉及儲存在 Azure blob 存放區，但不是 SharePoint Online 的清單項目或中繼資料儲存在 SQL 資料庫中的 SharePoint Online 檔案資料的加密和解密鏈結。 Office 365 不使用的可用性金鑰 SharePoint Online 或商務用 OneDrive 以外，上面所述的案例也就是起始的客戶。 客戶資料的人性化存取受保護的客戶加密箱。
  
## <a name="how-is-customer-key-licensed"></a>客戶金鑰的授權是？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

客戶金鑰是 Office 365 企業版套件、 「 E5 」 和進階合規性 SKU 中提供。 此外，客戶也必須購買的授權，使用 Azure 金鑰保存庫。
  
從客戶金鑰優點每位使用者需要如果他們想要涵蓋的客戶金鑰的授權。
  
若是 SharePoint Online，會設定客戶金鑰 Office 365 系統管理員也必須授權，才能執行安裝步驟。 此外，優點功能從使用者需要的授權-這包括網站擁有人和任何使用者存取使用客戶金鑰加密的一或多個網站上的檔案。 外部使用者不需要授權存取使用客戶金鑰加密的一或多個網站上的檔案。
  
針對 Exchange Online，就必須授權 「 使用者 」 信箱和 「 郵件使用者 」 的信箱。 所有其他人，例如共用信箱不需要授權的客戶金鑰。 若要檢查您的 Exchange Online 信箱時已取得在適當的授權，請執行下列 cmdlet:
  
```powershell
(Get-Mailbox <alias >).PersistedCapabilities
```

如果字串 BPOS_S_EquivioAnalytics 已存在，則信箱取得適當的授權。 如果不是，您必須套用適當的權限，才能使用客戶金鑰功能，此信箱。
  
## <a name="can-i-enable-customer-key-for-a-trial-subscription"></a>可以啟用試用版訂閱的客戶金鑰嗎？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

否。 根據定義，試用版訂閱可讓您有限的存留期。 裝載在試用版訂閱中的加密金鑰還會遺失的試用版的存留期的結尾。 由於 Microsoft 不能而且不會防止客戶將重要的客戶資料放在試用訂閱，因此禁止的試用訂閱會與使用客戶金鑰。
  
## <a name="how-much-will-using-customer-key-cost"></a>多少會使用客戶金鑰成本嗎？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

除了授權所需的客戶金鑰，客戶將會造成 Key Vault 流量的成本。 [定價的詳細資訊的 azure Key Vault](https://azure.microsoft.com/pricing/details/key-vault/)說明成本模型，並將會協助進行評估。 沒有任何方法可以預測因為使用模式不同，就可能會形成任何客戶的實際成本。 經驗顯示成本是很低，且通常落在範圍的 $0.002 至 $0.005 每位使用者每月加上 HSM 供電機碼的成本。 成本也會因選擇由客戶及用於 Azure Key Vault 記錄檔的 Azure 儲存體數量的記錄設定。 
  
## <a name="for-more-information"></a>相關資訊
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

若要開始使用客戶金鑰，請參閱[控制使用客戶金鑰的 Office 365 中的資料](controlling-your-data-using-customer-key.md)。
  

