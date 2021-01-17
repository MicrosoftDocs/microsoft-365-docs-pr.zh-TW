---
title: 開始使用通訊合規性
description: 設定通訊相容性原則，以設定使用者的通訊以進行審閱。
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
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: f958a2f6854ca34b0d24a527e2517c848885ad1c
ms.sourcegitcommit: 27cb4591e08f62ba0a08d6dcf224bf2039034fe5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/17/2021
ms.locfileid: "49883682"
---
# <a name="get-started-with-communication-compliance"></a>開始使用通訊合規性

使用通訊相容性原則，識別內部或外部檢閱者進行檢查的使用者通訊。 如需通訊相容性原則如何協助您監視組織中的通訊的詳細資訊，請參閱 [Microsoft 365 中的通訊相容性原則](communication-compliance.md)。 如果您想要查看 Contoso 如何快速設定通訊相容性原則，以監視 Microsoft 小組、Exchange Online 和 Yammer 通訊中的冒犯性語言，請參閱此 [案例研究](communication-compliance-case-study.md)。

## <a name="subscriptions-and-licensing"></a>訂閱與授權

在您開始進行通訊相容性之前，您應該先確認您的 [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 和任何附加元件。 若要存取及使用通訊相容性，您的組織必須具備下列其中一項訂閱或附加元件：

- Microsoft 365 E5 訂閱 (付費或試用版本) 
- Microsoft 365 E3 訂閱 + Microsoft 365 E5 合規性附加元件
- Microsoft 365 E3 訂閱 + Microsoft 365 E5 「內幕人員風險管理附加元件」
- Microsoft 365 A5 訂閱 (付費或試用版本) 
- Microsoft 365 A3 訂閱 + Microsoft 365 A5 合規性附加元件
- Microsoft 365 A3 訂閱 + Microsoft 365 A5 內幕人士風險管理附加元件
- Microsoft 365 G5 訂閱 (付費或試用版本) 
- Microsoft 365 G5 訂閱 + Microsoft 365 G5 合規性附加元件
- Microsoft 365 G5 訂閱 + Microsoft 365 G5 有問必答風險管理附加元件
- Office 365 企業版 E5 訂閱 (付費或試用版本) 
- Office 365 A5 訂閱 (付費或試用版本) 
- Office 365 企業版 E3 訂閱 + Office 365 Advanced 合規性附加元件 (已無法再供新訂閱使用，請參閱記事) 

必須將上述其中一個授權指派給通訊符合性原則中所含的使用者。

>[!IMPORTANT]
>Office 365 Advanced 合規性不再銷售為獨立訂閱。 當目前的訂閱到期時，客戶應轉換至上述其中一個訂閱，其中包含相同或其他的符合性功能。

如果您沒有現有的 Office 365 企業版 E5 計畫，而且想要嘗試通訊相容性，您可以 [將 Microsoft 365 新增](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 至現有的訂閱，或註冊 Office 365 Enterprise E5 的 [試用版](https://www.microsoft.com/microsoft-365/enterprise) 。

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>步驟 1 (必要) ：啟用通訊相容性的許可權

>[!Important]
>根據預設，全域管理員無法存取通訊規範功能。 在此步驟中所指派的角色是必要的通訊相容性功能才能存取。 設定角色群組之後，最多可能需要30分鐘的時間，才能將角色群組許可權套用至組織中指派給指派的使用者。

有五個角色群組可用來設定管理通訊符合性功能的許可權。 若要在 Microsoft 365 規範中心中以功能表選項的方式提供 **通訊相容性** ，並繼續這些設定步驟，您必須指派給 *通訊合規性* 或 *通訊合規性系統管理員* 角色群組。 若要在初始設定之後存取及管理通訊相容性功能，使用者必須是至少一個通訊合規性角色群組的成員。

視您想要管理通訊原則及警示的方式而定，您必須將使用者指派給特定角色群組。 您可以選擇將具有不同規範責任的使用者指派給特定角色群組，以管理不同的通訊相容性功能範圍。 或者，您也可以決定將指定系統管理員、分析員、調查人員和檢視器的所有使用者帳戶指派給 *通訊合規性* 角色群組。 請使用單一角色群組或多個角色群組，盡可能符合您的規範管理需求。

設定通訊相容性時，請從下列角色群組選項中選擇：

| 角色 | 角色權限 |
|:-----|:-----|
| **通訊相容性** | 使用此角色群組來管理單一群組中組織的通訊相容性。 新增指派管理員、分析員、調查人員和檢視器的所有使用者帳戶，您可以在單一群組中設定通訊合規性許可權。 此角色群組包含所有通訊符合性許可權角色。 這項設定是快速開始使用通訊相容性的最簡單方法，而且很適合不需要個別使用者群組定義個別許可權的組織。 |
| **通訊合規性管理** | 使用此角色群組開始設定通訊相容性和更新後，以將通訊合規性管理員隔離成定義的群組。 指派給此角色群組的使用者，可以建立、讀取、更新和刪除通訊符合性原則、全域設定和角色群組指派。 指派給此角色群組的使用者無法查看郵件警示。 |
| **通訊法規遵從性分析師** | 使用此群組可將許可權指派給將充當通訊相容性分析員的使用者。 指派給此角色群組的使用者可以查看其被指派為檢閱者的原則、查看郵件中繼資料 (非郵件內容) 、升級至其他檢閱者，或傳送通知給使用者。 分析員無法解析待處理的警示。 |
| **通訊合規性調查員** | 使用此群組可將許可權指派給將充當通訊合規性調查人員的使用者。 指派給此角色群組的使用者可以查看郵件中繼資料和內容、升級至其他檢閱者、升級至高級 eDiscovery 案例、將通知傳送給使用者，以及解決警示。 |
| **通訊規範檢視器** | 使用此群組可將管理通訊報告的許可權指派給使用者。 指派給此角色群組的使用者，可以存取通訊合規性首頁上的所有報告元件，並可以查看所有的通訊符合性報告。 |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a>選項1：將所有規範使用者指派給通訊合規性角色群組

1. 使用 Microsoft 365 組織中的系統管理員帳戶認證登入[https://protection.office.com/permissions](https://protection.office.com/permissions)。

2. 在安全性與 &amp; 合規性中心，移至 [ **許可權**]。 選取連結，以在 Office 365 中檢視及管理角色。

3. 選取 [ *通訊合規性* ] 角色群組，然後選取 [ **編輯角色群組**]。

4. 在左側瀏覽窗格中選取 **[選擇成員]**，然後選取 **[編輯]**。

5. 選取 [ **新增** ]，然後選取您要新增至 *通訊符合性* 角色群組之所有使用者的核取方塊。

6. 選取 **[新增]**，然後選取 **[完成]**。

7. 選取 **[儲存]** 以將使用者新增至角色群組。 選取 [ **關閉** ] 以完成步驟

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a>選項2：將使用者指派給特定的通訊符合性角色群組

使用此選項可將使用者指派給特定角色群組，以分割組織中不同使用者之間的通訊一致性存取和責任。

1. 使用 Microsoft 365 組織中的系統管理員帳戶認證登入[https://protection.office.com/permissions](https://protection.office.com/permissions)。

2. 在安全性與 &amp; 合規性中心，移至 [ **許可權**]。 選取連結，以在 Office 365 中檢視及管理角色。

3. 選取其中一個通訊符合性角色群組，然後選取 [ **編輯角色群組**]。

4. 在左側瀏覽窗格中選取 **[選擇成員]**，然後選取 **[編輯]**。

5. 選取 **[新增]**，然後針對所有要新增至角色群組的使用者勾選核取方塊。

6. 選取 **[新增]**，然後選取 **[完成]**。

7. 選取 **[儲存]** 以將使用者新增至角色群組。

8. 選取下一個通訊符合性角色群組，然後針對每個必要的角色群組重複步驟4-7。

9. 選取 **[關閉]** 以完成步驟。

如需角色群組和權限的詳細資訊，請參閱[規範中心的權限](../security/office-365-security/protect-against-threats.md)。

## <a name="step-2-required-enable-the-audit-log"></a>步驟 2 (必要) ：啟用審核記錄檔

通訊合規性需要「審核記錄檔」顯示提醒，並追蹤檢閱者採取的修復動作。 「審核記錄檔」會摘要所有與已定義的組織原則相關聯的活動，或在任何時刻的通訊合規性原則變更時。

如需開啟審計的逐步指示，請參閱 [開啟或關閉審計記錄搜尋](turn-audit-log-search-on-or-off.md)。 在您開啟審核後，會顯示一則訊息，指出已準備好審核記錄，而且您可以在準備完成後數小時執行搜尋。 您只需執行這項動作一次。 如需使用審核記錄的詳細資訊，請參閱 [搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>步驟 3 (選用) ：設定通訊相容性群組

 當您建立通訊相容性原則時，您會定義誰會檢查其通訊，以及誰會執行評論。 在原則中，您將使用電子郵件地址來識別個人或人員群組。 若要簡化您的設定，您可以為進行通訊檢查的使用者建立群組，並為審查這些通訊的使用者群組建立群組。 如果您正在使用群組，可能需要數個。 例如，如果您想要監視兩個不同的使用者群組之間的通訊，或是想要指定不會受到監督的群組。

使用下列圖表可協助您設定組織中的通訊遵循原則的群組：

| **原則成員** | **支援的群組** | **不支援的群組** |
|:-----|:-----|:-----|
|監督的使用者 <br> 非監督的使用者 | 通訊群組 <br> Microsoft 365 群組 | 動態通訊群組 <br> 嵌套通訊群組 <br> 擁有郵件功能的安全性群組 |
| 檢閱者 | 無 | 通訊群組 <br> 動態通訊群組 <br> 嵌套通訊群組 <br> 擁有郵件功能的安全性群組 |
  
當您指派原則中的通訊群組時，該原則會監控通訊群組中每個使用者的所有電子郵件和團隊聊天。 當您在原則中指派 Microsoft 365 群組時，原則會監控傳送至該群組的所有電子郵件和團隊聊天，而不是每個群組成員所收到的個別電子郵件和聊天。

如果您是具有 Exchange 內部部署或外部電子郵件提供者的組織，且您想要為使用者監視 Microsoft 團隊聊天，您必須為使用內部部署或外部信箱進行監視的使用者建立通訊群組。 在上述步驟中，您會將此通訊群組指派為 [原則嚮導] 中的 [授與 **群組** ] 選擇。

>[!IMPORTANT]
>您必須向 Microsoft 支援服務提交要求，才能讓組織使用安全性與合規性中心的圖形化使用者介面來搜尋內部部署使用者的 Teams 聊天資料。 如需詳細資訊，請參閱針對 [內部部署使用者搜尋雲端架構信箱](search-cloud-based-mailboxes-for-on-premises-users.md)。

若要管理大型企業組織中的監督使用者，您可能需要跨大型群組監控所有使用者。 您可以使用 PowerShell 為指派的群組設定全域通訊符合性原則的通訊群組。 這可讓您以單一原則監控成千上萬的使用者，並在新員工加入您的組織時，維持通訊相容性原則的更新。

1. 使用下列屬性為您的全域通訊相容性原則建立專用的 [通訊群組](https://docs.microsoft.com/powershell/module/exchange/new-distributiongroup) ：請確定此通訊群組並未用於其他用途或其他 Office 365 服務。

    - **MemberDepartRestriction = 封閉式**。 確保使用者無法從通訊群組中移除自己。
    - **MemberJoinRestriction = 封閉式**。 確保使用者無法將自己新增至通訊群組。
    - **ModerationEnabled = True**。 確定所有傳送至此群組的郵件都會受到核准，而且此群組並未用於通訊相容性原則設定之外的通訊。

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. 選取未使用的 [Exchange 自訂屬性](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes) ，以追蹤新增至組織中通訊合規性原則的使用者。

3. 在週期性排程上執行下列 PowerShell 腳本，以將使用者新增至通訊合規性原則：

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
- [Microsoft 365 群組的概述](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>步驟 4 (選用) ：確認 Yammer 租使用者處於原生模式

在純模式中，所有 Yammer 使用者都在 Azure Active Directory 中 (Azure AD) ，所有群組都是 Office 365 群組，而且所有檔案都儲存在 SharePoint 線上中。 您的 Yammer 租使用者必須採用原生模式，以進行通訊相容性原則，以掃描及識別 Yammer 中的私人郵件和社區交談中有風險的交談。

如需在原生模式中設定 Yammer 的詳細資訊，請參閱：

- [Microsoft 365 中的 Yammer 原生模式概述](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)
- [針對 Microsoft 365 設定您的 Yammer 網路使用原生模式](https://docs.microsoft.com/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>步驟 5 (必要) ：建立通訊相容性原則
  
>[!Important]
>不支援使用 PowerShell 建立及管理通訊相容性原則。 若要建立及管理這些原則，您必須使用 [Microsoft 365 通訊規範解決方案](https://compliance.microsoft.com/supervisoryreview)中的原則管理控制項。

1. 使用 Microsoft 365 組織中的系統管理員帳戶認證登入[https://compliance.microsoft.com](https://compliance.microsoft.com)。

2. 在 [Microsoft 365 規範中心] 中，選取 [ **通訊符合性**]。
  
3. 選取 [原則] 索引標籤。

4. 選取 [ **建立原則** ]，以從範本建立及設定新原則，或建立及設定自訂原則。

    如果您選擇原則範本以建立原則，您可以：

    - 確認或更新原則名稱。 建立原則之後，便無法變更原則名稱。
    
    - 選擇要監督的使用者或群組，包括選擇您想要排除的使用者或群組。 使用利益衝突的範本時，您會選取兩個群組或兩位使用者監視內部通訊。
    
    - 選擇原則的檢閱者。 「檢閱者」是個別的使用者，而且所有檢閱者都必須在 Exchange Online 上主控信箱。 在此新增的檢閱者是在調查和修正工作流程中升級提醒時，可選擇的檢閱者。 當檢閱者新增至原則時，會自動收到一封電子郵件，通知他們對原則的指派，並提供審閱程式相關資訊的連結。
    
    - 選擇 [有限條件] 欄位，通常是要套用至原則的敏感資訊類型或關鍵字字典。

    如果您選擇使用原則嚮導建立自訂原則，您可以：

    - 將原則命名為 [名稱] 和 [描述]。 建立原則之後，便無法變更原則名稱。
    
    - 選擇要監督的使用者或群組，包括您組織中的所有使用者、特定使用者和群組，或是您想要排除的其他使用者和群組。
    
    - 選擇原則的檢閱者。 「檢閱者」是個別的使用者，而且所有檢閱者都必須在 Exchange Online 上主控信箱。 在此新增的檢閱者是在調查和修正工作流程中升級提醒時，可選擇的檢閱者。 當檢閱者新增至原則時，會自動收到一封電子郵件，通知他們對原則的指派，並提供審閱程式相關資訊的連結。
    
    - 選擇要掃描的通訊通道，包括 Exchange、Microsoft 團隊、Yammer 或商務用 Skype。 如果您已在 Microsoft 365 中設定連接器，您也會選擇掃描協力廠商來源。
    
    - 選擇要監視的通訊方向，包括輸入、輸出或內部通訊。
    
    - 定義通訊相容性原則 [條件](communication-compliance-feature-reference.md#ConditionalSettings)。 您可以選擇 [郵寄地址]、[關鍵字]、[檔案類型] 和 [大小相符] 條件。
    
    - 選擇是否要包含機密資訊類型。 在這個步驟中，您可以選取預設和自訂的機密資訊類型。 在 [通訊合規性原則] 中，從現有的自訂敏感資訊類型或自訂關鍵字字典中挑選。 如有需要，您可以在執行該嚮導之前建立這些專案。 您也可以從通訊合規性原則嚮導中建立新的敏感資訊類型。
    
    - 選擇是否要啟用分類器。 分類器可以偵測電子郵件訊息或其他類型的文字內傳送或接收的不適當語言和圖像。 您可以選擇下列內建的分類符： *威脅*、 *猥褻*、 *目標騷擾*、 *成人影像*、 *Racy 影像* 和 *Gory 影像*。

      > [!CAUTION]
      > 我們正在淘汰 **[粗穢言語]** 內建分類器，因為這個分類器產生了大量的誤報。 請勿使用它，如果您目前使用它，您應該將商務程式移出它。 我們建議您改用 **威脅**、 **猥褻** 和 **目標騷擾** 內建的分類符。

    - 定義要複查的通訊百分比。
    
    - 檢查您的原則選擇並建立原則。

5. 使用 [自訂原則] 嚮導時，選取 [使用範本或 **提交** 時 **建立原則**]。

6. **已建立您** 的原則頁面會隨著原則的啟動時間及將捕獲哪些通訊的指導方針來顯示。

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>步驟 6 (選用) ：建立公告範本及設定使用者匿名

如果您想要選擇以傳送提醒通知給關聯的使用者來回應原則警示，您必須在組織中至少建立一個公告範本。 [！注意事項] [通知範本] 欄位是可編輯的，在傳送為警示修復程式的一部分之前，建議您為每個通訊相容性原則建立自訂的通知範本。

您也可以選擇在調查原則符合和對郵件採取動作時，啟用顯示之使用者的匿名。

1. 使用 Microsoft 365 組織中的系統管理員帳戶認證登入[https://compliance.microsoft.com](https://compliance.microsoft.com)。

2. 在 Microsoft 365 規範中心內，移至 [ **通訊符合性**]。

3. 若要設定匿名的使用者名，請選取 [ **隱私權** ] 索引標籤。

4. 若要啟用匿名，請選取 [ **顯示匿名版本的使用者名**]。

5. 選取 [儲存]。

6. 流覽至 [ **公告範本** ] 索引標籤，然後選取 [ **建立公告範本**]。

7. 在 [ **修改公告範本** ] 頁面上，完成下欄欄位：

    - 範本名稱 (必要) 
    -  (必要的傳送) 
    - 抄送和 Bcc (選用) 
    - 主體 (必要) 
    - 需要郵件內文 () 

8. 選取 [ **儲存** ] 以建立及儲存 [公告] 範本。

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>步驟 7 (選用) ：測試通訊合規性原則

在您建立通訊相容性原則之後，建議您加以測試，以確定原則已正確地強制執行您所定義的條件。 您也可以在通訊相容性原則包括敏感資訊類型時， [測試您的資料遺失防護 (DLP) 原則](create-test-tune-dlp-policy.md) 。 請務必提供您的原則啟動時間，以便您想要測試的通訊得以捕獲。

請遵循下列步驟來測試您的通訊合規性原則：

1. 在您要測試之原則中所定義的監督使用者登入時，開啟電子郵件客戶程式、Microsoft 小組或 Yammer。

2. 傳送電子郵件、Microsoft 小組聊天或 Yammer 訊息，其符合您在通訊相容性原則中所定義的準則。 此測試可以是關鍵字、附件大小、網域等等。確定您判斷原則中設定的設定條件設定過於嚴格或太 lenient。

    > [!NOTE]
    > 在原則中，電子郵件訊息最多可能需要24小時才能完全處理。 在 Microsoft 小組、Yammer 和協力廠商平臺中的通訊可能需要長達48小時才能完整處理原則。

3. 以通訊合規性原則中指定的檢閱者身分登入 Microsoft 365。 流覽至 [**通訊相容性**  >  **警示**]，以查看原則的警示。

4. 使用修正控制措施修正警示，並確認已正確解決警示。

## <a name="next-steps"></a>後續步驟

當您完成這些步驟來建立您的第一個通訊符合性原則之後，您將在24-48 小時後開始從活動指示器接收提醒。 根據需要使用本文步驟5的指導方針設定其他原則。

若要深入瞭解如何調查通訊相容性警示，請參閱 [調查和修正通訊相容性警示](communication-compliance-investigate-remediate.md)。
