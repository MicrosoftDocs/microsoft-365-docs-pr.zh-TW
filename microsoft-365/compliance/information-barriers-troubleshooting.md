---
title: 疑難排解資訊屏障
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用本文做為疑難排解資訊障礙的指南。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5aa45e3e9dea5ce413b2b0e62d825003bc24e20e
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352322"
---
# <a name="troubleshooting-information-barriers"></a>疑難排解資訊屏障

[資訊障礙](information-barriers.md)可協助您的組織遵守法律需求和行業法規。 例如，利用資訊障礙，您可以限制特定使用者群組之間的通訊，以避免利益衝突或其他問題。 （若要深入瞭解如何設定資訊障礙，請參閱[Define 原則的資訊障礙](information-barriers-policies.md)。）

當有人在資訊壁壘出現之後發生意外問題時，您可以採取一些步驟來解決這些問題。 使用本文做為指南。

> [!IMPORTANT]
> 若要執行本文所述的工作，您必須獲指派適當的角色，例如下列其中一項：<br/>-Microsoft 365 企業版全域系統管理員<br/>-全域管理員<br/>-合規性管理員<br/>-IB 相容性管理（這是新的角色！）<p>若要深入瞭解資訊障礙的必要條件，請參閱[必要條件（適用于資訊障礙原則）](information-barriers-policies.md#prerequisites)。<p>請務必[連接至安全性 & 規範中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>問題：使用者意外封鎖，無法與 Microsoft 小組中的其他使用者通訊 

在此情況下，使用者會在 Microsoft 小組中報告與其他人進行通訊的意外問題。 範例：
- 使用者可搜尋，但找不到 Microsoft 小組中的其他使用者。
- 使用者可以找到，但無法選取 Microsoft 小組中的另一位使用者。
- 使用者可以查看其他使用者，但無法將郵件傳送給 Microsoft 小組中的其他使用者。

### <a name="what-to-do"></a>處理方式

決定使用者是否受到資訊屏障原則的影響。 視原則的設定方式而定，資訊壁壘可能如預期般運作。 或者，您可能需要調整組織的原則。

1. 使用**InformationBarrierRecipientStatus** Cmdlet 搭配 Identity 參數。 

    |語法  |範例  |
    |---------|---------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p>您可以使用唯一識別每個收件者的任何 identity 值，例如 Name、Alias、辨別名稱（DN）、正常化 DN、電子郵件地址或 GUID。     |`Get-InformationBarrierRecipientStatus -Identity meganb` <p>在此範例中，我們使用了 Identity 參數的別名（*meganb*）。 此 Cmdlet 會傳回指出使用者是否受到資訊屏障原則影響的資訊。 （請參閱 * ExoPolicyId： \<GUID>。）         |

    **如果使用者未包含在資訊屏障原則中，請與支援人員聯繫**。 否則，請繼續進行下一個步驟。

2. 瞭解資訊屏障原則中所包含的段落。 若要這麼做，請使用 `Get-InformationBarrierPolicy` Cmdlet 搭配 Identity 參數。 

    |語法  |範例  |
    |---------|---------|
    |`Get-InformationBarrierPolicy` <p>在上一個步驟中，使用詳細資料（如您在上一個步驟中所收到的原則 GUID （ExoPolicyId））做為身分識別值。     | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p>在此範例中，我們取得的資訊屏障原則的詳細資訊 ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*。         |

    在您執行 Cmdlet 後，請在 [結果] 中，尋找 [ **AssignedSegment**]、[ **SegmentsAllowed**] 及 [ **SegmentsBlocked** ] 值。

    例如， `Get-InformationBarrierPolicy` 執行 Cmdlet 後，我們會在結果清單中看到下列專案：

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    在此情況下，我們可以看到資訊障礙原則會影響銷售和研究中心中的人員。 在此情況下，會防止銷售人員與調查中的人員進行通訊。 
    
    如果看起來正確，則資訊壁壘會如預期般運作。 若未完成，請繼續進行下一個步驟。

4. 請確定已正確定義您的區段。 若要這麼做，請使用 `Get-OrganizationSegment` Cmdlet，並複查結果清單。 

    |語法  |範例  |
    |---------|---------|
    |`Get-OrganizationSegment`<p>使用此 Cmdlet 搭配 Identity 參數。     |`Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p>在此範例中，我們會取得 GUID 為*c96e0837-c232-4a8a-841e-ef45787d8fcd*之網段的相關資訊。         |

    查看區段的詳細資料。 如有必要，請[編輯區段](information-barriers-edit-segments-policies.md#edit-a-segment)，然後重新使用 `Start-InformationBarrierPoliciesApplication` Cmdlet。

    **如果您仍有資訊屏障原則的問題，請與支援人員聯繫**。

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>問題：允許在 Microsoft 小組中封鎖的使用者之間進行通訊

在此情況下，雖然資訊壁壘已定義、使用中且已套用，但應禁止彼此進行通訊的人員可以在 Microsoft 小組中互動及呼叫對方。

### <a name="what-to-do"></a>處理方式

確認有問題的使用者已包含在資訊屏障原則中。 

1. 使用具有 Identity 參數的**InformationBarrierRecipientStatus** Cmdlet。

    |語法  |範例  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>您可以使用唯一識別每個使用者的任何值，例如名稱、別名、辨別名稱、正常化功能變數名稱、電子郵件地址或 GUID。     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>在此範例中，我們會參考 Office 365 中的兩個使用者帳戶： *meganb* for *Megan*和*alexw* for *Alex*。          |

    
    > [!TIP]
    > 您也可以將此 Cmdlet 用於單一使用者：`Get-InformationBarrierRecipientStatus -Identity <value>`
    
2. 回顧結果。 **InformationBarrierRecipientStatus 指令程式**會傳回使用者的相關資訊，例如屬性值以及所套用的任何資訊屏障原則。 

    檢查結果，然後採取後續的步驟，如下表所述：
    
    |結果  |接下來要執行的動作  |
    |---------|---------|
    |所選使用者未列出任何區段     |執行下列其中一項動作：<br/>-在 Azure Active Directory 中編輯使用者設定檔，將使用者指派至現有的網段。 （請參閱[使用 Office 365 PowerShell 設定使用者帳戶屬性](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)。）<br/>-使用[支援的資訊障礙屬性](information-barriers-attributes.md)定義區段。 然後，[定義新的原則](information-barriers-policies.md#part-2-define-information-barrier-policies)或[編輯現有的原則](information-barriers-edit-segments-policies.md#edit-a-policy)，以包含該區段。  |
    |會列出網段，但不會將資訊障礙原則指派給那些區段     |執行下列其中一項動作：<br/>- 為相關的每個區段[定義新的資訊屏障原則](information-barriers-policies.md#part-2-define-information-barrier-policies)<br/>- [編輯現有的資訊屏障原則](information-barriers-edit-segments-policies.md#edit-a-policy)，將其指派給正確的區段         |
    |列出各段，且每個區段都包含在資訊屏障原則中     |-執行 `Get-InformationBarrierPolicy` Cmdlet 以確認資訊屏障原則為作用中狀態。<br/>-執行 `Get-InformationBarrierPoliciesApplicationStatus` Cmdlet 以確認已套用原則<br/>-執行 `Start-InformationBarrierPoliciesApplication` Cmdlet 以套用所有作用中的資訊屏障原則          |
    

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>問題：我需要從資訊屏障原則中移除單一使用者

在此情況下，資訊屏障原則會生效，且意外封鎖一或多個使用者與 Microsoft 小組中的其他使用者進行通訊。 您可以移除資訊屏障原則中的一或多個個別使用者，而不是完全移除資訊屏障原則。 

### <a name="what-to-do"></a>處理方式

資訊屏障原則會指派給使用者區段。 區段是以[使用者帳戶設定檔中](information-barriers-attributes.md)的特定屬性定義。 如果您必須從單一使用者移除原則，請考慮在 Azure Active Directory 中編輯該使用者的設定檔，讓使用者不再包含在受到資訊障礙影響的區段中。

1. 使用具有 Identity 參數的**InformationBarrierRecipientStatus** Cmdlet。 此 Cmdlet 會傳回使用者的相關資訊，例如屬性值以及所套用的任何資訊屏障原則。

    |語法  |範例  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`<p>您可以使用唯一識別每個使用者的任何值，例如名稱、別名、辨別名稱、正常化功能變數名稱、電子郵件地址或 GUID。     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>在此範例中，我們會參考 Office 365 中的兩個使用者帳戶： *meganb* for *Megan*和*alexw* for *Alex*。          |
    |`Get-InformationBarrierRecipientStatus -Identity <value>` <p>您可以使用唯一識別使用者的任何值，例如名稱、別名、辨別名稱、正常化功能變數名稱、電子郵件地址或 GUID。|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p>在此範例中，我們參考 Office 365： *jeanp*中的單一帳戶。 |

2. 檢查結果，以查看是否已指派資訊屏障原則，以及使用者屬於哪些網段。 

3. 若要從受資訊障礙影響的區段中移除使用者，請[在 Azure Active Directory 中更新使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。

4. 等候大約30分鐘，以進行 FwdSync。 或者，執行 Cmdlet 以套用所有作用中的 `Start-InformationBarrierPoliciesApplication` 資訊屏障原則。

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>問題：資訊障礙應用程式處理時間過長

在執行**InformationBarrierPoliciesApplication 指令程式**之後，處理常式會花很長的時間才能完成。

### <a name="what-to-do"></a>處理方式

請記住，當您執行 policy application Cmdlet 時，會為組織中的所有帳戶套用（或移除）資訊屏障原則（由使用者移除）。 如果您有許多使用者，需要一些時間才能進行處理。 （一般的指導方針是花一個小時來處理5000使用者帳戶。）

1. 使用**InformationBarrierPoliciesApplicationStatus**指令程式來驗證最近的原則應用程式的狀態。

    |若要查看最新的原則應用程式  |若要查看所有原則應用程式的狀態  |
    |---------|---------|
    |`Get-InformationBarrierPoliciesApplicationStatus`     |`Get-InformationBarrierPoliciesApplicationStatus -All $true`         |


    這會顯示原則應用程式已完成、失敗或進行中的相關資訊。

2. 根據上一個步驟的結果，執行下列其中一個步驟：
  
    |狀態  |後續步驟  |
    |---------|---------|
    |**未開始**     |若**InformationBarrierPoliciesApplication** Cmdlet 已執行超過45分鐘，請複查您的審核記錄檔，以查看原則定義中是否有任何錯誤，或應用程式尚未啟動的其他一些原因。 |
    |**失敗**     |若應用程式失敗，請複查您的審核記錄檔。 另外，請複查您的區段和原則。 是否有任何使用者被指派至多個區段？ 是否有任何區段被指派多個 poliicy？ 如有必要，請[編輯區段](information-barriers-edit-segments-policies.md#edit-a-segment)和/或[編輯原則](information-barriers-edit-segments-policies.md#edit-a-policy)，然後再次執行**InformationBarrierPoliciesApplication** Cmdlet。  |
    |**進行中。**     |若應用程式仍在進行中，請允許更多的時間完成。 如果有好幾天，請收集您的審計記錄檔，然後與支援人員聯繫。 |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>問題：根本沒有套用資訊屏障原則

在此情況下，您已定義區段、定義的資訊關卡原則，並嘗試套用這些原則。 不過，當您執行 `Get-InformationBarrierPoliciesApplicationStatus` Cmdlet 時，您可以看到原則應用程式失敗。

### <a name="what-to-do"></a>處理方式

請確定您的組織沒有適當的[Exchange 通訊錄原則](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)。 這類原則會防止套用資訊屏障原則。

1. 連接至[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。 

2. 執行[Get-AddressBookPolicy](https://docs.microsoft.com/powershell/module/exchange/get-addressbookpolicy?view=exchange-ps) Cmdlet，並檢查結果。

    |結果  |後續步驟  |
    |---------|---------|
    |Exchange 通訊錄原則會列出     |[移除通訊錄原則](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy)         |
    |無通訊錄原則存在 |檢查您的審計記錄檔，以找出原則應用程式失敗的原因 |

3. [查看使用者帳戶、區段、原則或原則應用程式的狀態](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)。

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>問題：資訊屏障原則未套用至所有指定的使用者

定義資料段、定義資訊屏障原則，並嘗試套用這些原則之後，您可能會發現原則套用至某些收件者，而不是其他收件者。
當您執行 `Get-InformationBarrierPoliciesApplicationStatus` Cmdlet 時，請搜尋輸出以取得類似的文字。

> 身份：`<application guid>`
>
> 收件者總數：81527
>
> 失敗的收件者：2
>
> 失敗類別：無
>
> 狀態：完成

### <a name="what-to-do"></a>處理方式

1. 在審核記錄中搜尋 `<application guid>` 。 您可以將此 PowerShell 程式碼和您的變數一起修改。

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. 檢查 [和] 欄位的值之審核記錄中的詳細 `"UserId"` 輸出 `"ErrorDetails"` 。 這可讓您失敗的原因。 您可以將此 PowerShell 程式碼和您的變數一起修改。

```powershell
   $DetailedLogs[1] |fl
```
 例如：

> "UserId"： User1
> 
>"ErrorDetails"： "Status： IBPolicyConflict。 錯誤： IB 區段 "segment id1" 和 IB 線段 "segment id2" 發生衝突，且無法指派給收件者。 

3. 通常，您會發現使用者已包含在一個以上的區段中。 您可以更新中的值以修正此問題 `-UserGroupFilter` `OrganizationSegments` 。

4. 使用這些程式[資訊障礙原則](information-barriers-policies.md#part-3-apply-information-barrier-policies)，重新套用資訊屏障原則。

## <a name="related-topics"></a>相關主題

[在 Microsoft 小組中定義資訊障礙的原則](information-barriers-policies.md)

[資訊屏障](information-barriers.md)
