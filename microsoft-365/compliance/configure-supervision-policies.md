---
title: 設定監督原則
description: 設定 Office 365 的通訊監督原則，以捕獲內部或外部檢閱者進行檢查的員工通訊。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
titleSuffix: Office 365 Compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9cbde149419320495e3848867846322733cb56f9
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033653"
---
# <a name="configure-supervision-policies-in-office-365"></a>在 Office 365 中設定監督原則

>[!IMPORTANT]
>在2月2020中，遵循 Microsoft 365 合規性中的通訊相容性，便會停用 Office 365 中的監督。 監管原則將不再可供建立，而且最終將會在唯讀的唯讀存取之後移除原則。
>
>如果您使用監督，請注意：
>
>- 從2020年6月15日起，承租人將無法建立新的監察原則。
>- 2020年8月31日開始，現有的原則將停止捕獲新的郵件。
>- 從2020年10月26日開始，將會刪除現有的原則。
>
>我們積極鼓勵目前探索或使用 Office 365 內監察的客戶，以使用新的[通訊相容性](communication-compliance.md)解決方案，利用一組更豐富的智慧功能來處理通訊監視或法規需求。

使用監督原則來捕獲員工通訊，以供內部或外部的檢閱者檢查。 如需監督原則如何協助您監視組織中通訊的詳細資訊，請參閱[Office 365 中的監管原則](supervision-policies.md)。

>[!NOTE]
>監控原則所監控的使用者，必須具備 Microsoft 365 E5 相容性授權、具有高級合規性附加元件的 Office 365 企業版 E3 授權，或是包含在 Office 365 企業版 E5 訂閱中，或包含在 Microsoft 365 E5 訂閱中。
>如果您沒有現有的企業版 E5 計畫，而且想要嘗試監督，您可以[註冊 Office 365 Enterprise e5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。
  
請遵循下列步驟，在您的組織中設定及使用監督：
  
- **步驟1（選用）**：[設定監督群組](#step-1-set-up-groups-for-supervision-optional)

    開始使用監察原則之前，請先決定誰需要檢查通訊，以及誰會執行評論。 如果您想要開始使用少數使用者來查看監管的運作方式，您可以略過設定 [群組] 立即。

- **步驟2（必要）**：[讓監管可用於您的組織](#step-2-make-supervision-available-in-your-organization-required)

    將您本人新增至主管審查角色群組，讓您可以設定原則。 已指派此角色的任何人都可以存取安全性 & 規範中心內的**監管**頁面。 如果 reviewable 電子郵件主控于 Exchange Online，則每個檢閱者都必須有[Exchange online 的遠端 PowerShell 存取權](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。

- **步驟3（選用）**：[建立自訂機密資訊類型及自訂關鍵字字典](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)

    如果您需要監管原則的自訂敏感資訊類型或自訂關鍵字字典，您必須在啟動監管嚮導之前加以建立。

- **步驟4（必要）**：[設定監督原則](#step-4-set-up-a-supervision-policy-required)

    您可以在安全性 & 規範中心建立監督原則。 這些原則定義哪些通訊會在您的組織中進行檢查，並指定誰會執行評論。 通訊包括電子郵件和 Microsoft 小組通訊，以及協力廠商平臺通訊（如 Facebook、Twitter 等）。 Microsoft 365 訂閱中的通訊監督不支援組織中所建立的監督原則。

- **步驟5（選用）**：[測試通訊監督原則](#step-5-test-your-supervision-policy-optional)

    測試您的監督原則，確定其運作正常。 務必確定您的規範策略符合您的標準。

## <a name="step-1-set-up-groups-for-supervision-optional"></a>步驟1：設定監督群組（選用）

 當您建立監督原則時，您會定義哪些人員已掃描其通訊，以及誰會執行評論。 在原則中，您將使用電子郵件地址來識別個人或人員群組。 若要簡化您的設定，您可以為使用者建立群組，讓他們能夠掃描和群組其通訊。 如果您正在使用群組，可能需要數個。 例如，您想要監視兩個不同的使用者群組之間的通訊，或是想要指定不會受到監督的群組。

使用下列圖表可協助您設定組織中的通訊監管原則的群組：

| **原則成員** | **支援的群組** | **不支援的群組** |
|:-----|:-----|:-----|
|監督的使用者 <br> 非監督的使用者 | 通訊群組 <br> Microsoft 365 群組 | 動態通訊群組 |
| 檢閱者 | 擁有郵件功能的安全性群組  | 通訊群組 <br> 動態通訊群組 |
  
當您為監督的使用者選取 Microsoft 365 群組時，該原則會監控共用信箱的內容，以及與群組相關聯的 Microsoft 小組通道。 當您選取通訊群組清單時，該原則會監控個別的使用者信箱。

若要管理大型企業組織中的監督使用者，您可能需要跨大型群組監控所有使用者。 您可以使用 PowerShell 為指派的群組設定全域監督原則的通訊群組。 這可讓您以單一原則監控成千上萬的使用者，並在新員工加入您的組織時，維持監督原則的更新。

1. 使用下列屬性，為全域監督原則建立專屬的[通訊群組](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps)：請確定此通訊群組並未用於其他用途或其他 Office 365 服務。

    - **MemberDepartRestriction = 封閉式**。 確保使用者無法從通訊群組中移除自己。
    - **MemberJoinRestriction = 封閉式**。 確保使用者無法將自己新增至通訊群組。
    - **ModerationEnabled = True**。 確定所有傳送至此群組的郵件都會受到核准，而且此群組並未用來在監督原則設定外進行通訊。

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. 選取未使用的[Exchange 自訂屬性](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww)，追蹤新增至組織中監管原則的使用者。

3. 在週期性排程上執行下列 PowerShell 腳本，將使用者新增至監管原則：

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

如需設定群組的詳細資訊，請參閱：

- [建立並管理通訊群組](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [管理啟用郵件功能的安全性群組](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Microsoft 365 群組的概述](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a>步驟2：讓監管可用於您的組織（必要）

若要讓**監督**成為安全 & 合規性中心的功能表選項，您必須獲指派主管審查系統管理員角色。
  
若要這麼做，您可以將自己新增為主管審查角色群組的成員，也可以建立角色群組。
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>新增成員至主管審查角色群組

1. 登入[https://protection.office.com](https://protection.office.com)在組織中使用管理員帳戶的認證。

2. 在 [安全性 & 規範中心] 中，移至 [**許可權**]。

3. 選取 [**主管審查**] 角色群組，然後按一下 [編輯] 圖示。

4. 在 [**成員**] 區段中，新增您要管理組織之通訊監督的人員。

### <a name="create-a-new-role-group"></a>建立新的角色群組

1. 登入[https://protection.office.com/permissions](https://protection.office.com/permissions)在組織中使用管理員帳戶的認證。

2. 在 [安全性 & 規範中心] 中，移至 [**許可權**]，**+** 然後按一下 [新增] （）。

3. 在 [**角色**] 區段中，按一下**+**[新增] （），然後向下滾動至「**主管審查管理員**」。 將此角色新增至角色群組。

4. 在 [**成員**] 區段中，新增您要管理組織之通訊監督的人員。

如需角色群組和權限的詳細資訊，請參閱[規範中心的權限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>啟用檢閱者的遠端 PowerShell 存取（電子郵件主控于 Exchange Online）

1. 遵循[啟用或停用 Exchange Online PowerShell 存取](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)的指導方針。

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>步驟3：建立自訂機密資訊類型及自訂關鍵字字典（選用）

若要在監督原則嚮導中挑選現有的自訂敏感資訊類型或自訂關鍵字字典，您必須視需要建立這些專案。

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>建立自訂關鍵字字典/詞典（選用）

使用文字編輯器（例如記事本）來建立檔案，該檔案包含您想要在監管原則中監視的關鍵字字詞。 請確定每個字詞都位於個別的一行，並以**Unicode/UTF-16 （小 Endian）** 格式儲存檔案。

### <a name="create-custom-sensitive-information-types"></a>建立自訂機密資訊類型

1. 建立新的敏感資訊類型，並將您的自訂字典加入安全性 & 規範中心。 流覽至 [**分類** \> **機密資訊類型**]，然後依照**新增的敏感資訊類型嚮導**中的步驟進行。 您將在這裡：

    - 定義敏感資訊類型的名稱和描述
    - 定義鄰近性、信賴等級及主要模式元素
    - 將您的自訂字典當作符合元素的需求匯入
    - 檢查您的選擇並建立機密資訊類型

    如需詳細資訊，請參閱[建立自訂機密資訊類型](create-a-custom-sensitive-information-type.md)及[建立關鍵字字典](create-a-keyword-dictionary.md)

    在建立自訂字典/詞典之後，您可以使用[DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary)指令程式來查看已設定的關鍵字，或是使用[DlpKeywordDictionary 指令程式](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary)來新增及移除字詞。

## <a name="step-4-set-up-a-supervision-policy-required"></a>步驟4：設定監督原則（必要）
  
1. 登入[https://protection.office.com](https://protection.office.com)在組織中使用管理員帳戶的認證。

2. 在 [安全性 & 規範中心] 中，選取 [**監督**]。
  
3. 選取 [**建立**]，然後依照嚮導設定原則設定。 使用此嚮導，您可以：

    - 將原則命名為 [名稱] 和 [描述]。
    - 選擇要監督的使用者或群組，包括選擇您想要排除的使用者或群組。
    - 定義監督原則[條件](supervision-policies.md#ConditionalSettings)。 您可以選擇 [郵寄地址]、[關鍵字]、[檔案類型] 和 [大小相符] 條件。
    - 選擇是否要包含機密資訊類型。 您可以在此選擇預設和自訂的機密資訊類型。
    - 選擇是否要啟用冒犯性語言模型。 這會偵測到電子郵件內送出或接收到不適當的語言。
    - 定義要複查的通訊百分比。
    - 選擇原則的檢閱者。 檢閱者可以是個別的使用者或擁有[郵件功能的安全性群組](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。 所有檢閱者都必須在 Exchange Online 上主控信箱。
    - 檢查您的原則選擇並建立原則。

## <a name="step-5-test-your-supervision-policy-optional"></a>步驟5：測試您的監管原則（選用）

在您建立通訊監督原則之後，建議您測試，以確定原則已正確地強制執行您所定義的條件。 您也可以在您的監管原則包括機密資訊類型時，[測試您的資料遺失防護（DLP）原則](create-test-tune-dlp-policy.md)。 請遵循下列步驟來測試您的監管原則：

1. 開啟以您想要測試之原則中所定義之監督使用者的身分登入電子郵件客戶程式或 Microsoft 團隊。
2. 傳送電子郵件或 Microsoft 小組聊天，其符合您在監管原則中所定義的準則。 這可以是關鍵字、附件大小、網域等等。確定您決定原則中設定的設定條件設定過於嚴格，還是過於 lenient。

    >[!NOTE]
    >已定義原則的電子郵件會在近期即時處理，而且在設定原則之後可立即進行測試。 Microsoft 小組中的聊天可能需要長達24小時才能完全處理原則。 

3. 以通訊監督原則中指定的檢閱者身分登入 Microsoft 365。 流覽至 [**監察** > ]*您的自訂原則* > **開啟**以查看原則的報告。

