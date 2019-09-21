---
title: 疑難排解資訊障礙
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
description: 使用本文做為指南疑難排解資訊障礙。
ms.openlocfilehash: 47549029ffbaa5ead028c18e97850b30f8072011
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076229"
---
# <a name="troubleshooting-information-barriers"></a>疑難排解資訊障礙

[資訊障礙](information-barriers.md)可協助您的組織維持與法務需求和產業規定相容。 例如，與資訊障礙，您可以限制特定群組以避免發生衝突的利益或其他問題的使用者之間的通訊。 （若要深入了解如何設定資訊障礙，請參閱[定義原則的資訊障礙](information-barriers-policies.md)）。

該人員會遇到非預期的問題，資訊障礙已備妥之後，有一些步驟，您可以用來解決這些問題。 使用本文做為指南。

> [!IMPORTANT]
> 若要執行本文所述的工作，您必須獲指派適當的角色，例如下列其中一項：<br/>-Microsoft 365 企業版的全域系統管理員<br/>-Office 365 全域系統管理員<br/>-合規性管理員<br/>-（這是新的角色） ！ IB 相符性管理<p>若要深入了解資訊障礙的必要條件，請參閱[（適用於資訊障礙原則） 的必要條件](information-barriers-policies.md#prerequisites)。<p>確定連接[到 Office 365 安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>問題： 使用者意外系統阻止您與其他人通訊 Microsoft teams 

在此情況下，人員會回報未預期的問題與其他人通訊 Microsoft teams。 範例:
- 使用者搜尋，但找不到，在 Microsoft Teams 中的另一位使用者。
- 使用者可以找到，但不能選取 Microsoft Teams 中的另一位使用者。
- 使用者可以看到另一位使用者，但無法將郵件傳送至 Microsoft Teams 中的其他使用者。

### <a name="what-to-do"></a>要執行的動作

決定使用者是否會受影響資訊障礙原則。 根據原則設定的方式，可能會如預期般運作資訊障礙。 或者，您可能需要調整您的組織原則。

1. 使用**Get-InformationBarrierRecipientStatus** cmdlet 搭配 Identity 參數。 

    |語法  |範例  |
    |---------|---------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p>您可以使用任何可唯一識別每個收件者，例如名稱、 別名、 辨別的名稱 (DN)、 標準 DN、 電子郵件地址或 GUID 的識別值。     |`Get-InformationBarrierRecipientStatus -Identity meganb` <p>在這個範例中，我們會針對 Identity 參數使用別名 (*meganb*)。 此 cmdlet 會傳回指出使用者是否會受到資訊障礙原則的資訊。 (尋找 * ExoPolicyId: \<GUID>。)         |

    **如果使用者不會包含在資訊障礙原則，請連絡支援**。 否則，請繼續進行下一個步驟。

2. 找出哪一個區段會包含在資訊障礙原則。 若要這麼做，請使用`Get-InformationBarrierPolicy`cmdlet 搭配 Identity 參數。 

    |語法  |範例  |
    |---------|---------|
    |`Get-InformationBarrierPolicy` <p>使用詳細資料，例如原則 GUID (ExoPolicyId) 您收到期間前一個步驟中，為 identity 值。     | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p>在這個範例中，我們會取得已 ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*資訊障礙原則的詳細的資訊。         |

    在結果中，執行 cmdlet 時之後, 尋找**AssignedSegment**、 **SegmentsAllowed**和**SegmentsBlocked**值。

    例如之後執行,`Get-InformationBarrierPolicy`指令程式，建議您在我們的結果清單中看到下列：

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    在此情況下，我們可以看到的資訊障礙原則影響處於 「 銷售和參考資料區段的人員。 在此情況下，在 [銷售人員會禁止與研究中的人員進行通訊。 
    
    如果這看似正確，然後資訊障礙都如預期般運作。 如果沒有，請繼續進行下一個步驟。

4. 請確定正確地定義您的區段。 若要這麼做，請使用`Get-OrganizationSegment`指令程式，並檢閱結果清單中的。 

    |語法  |範例  |
    |---------|---------|
    |`Get-OrganizationSegment`<p>使用此 cmdlet 搭配 Identity 參數。     |`Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p>在這個範例中，我們會取得具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*線段的相關資訊。         |

    檢閱詳細資料區段。 如果需要[編輯線段](information-barriers-edit-segments-policies.md.md#edit-a-segment)，，然後重複使用`Start-InformationBarrierPoliciesApplication`指令程式。

    **如果您仍然有問題您資訊障礙的原則，請連絡支援**。

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>問題： 在 Microsoft Teams 中應被封鎖的使用者之間允許通訊

在此情況下，雖然定義資訊障礙，作用中，並套用，人員應禁止與彼此進行通訊是以某種方式能夠與交談，並彼此呼叫 Microsoft teams。

### <a name="what-to-do"></a>要執行的動作

確認資訊障礙原則中包含有問題的使用者。 

1. **取得 InformationBarrierRecipientStatus** cmdlet 搭配 Identity 參數。

    |語法  |範例  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>您可以使用任何可唯一識別每位使用者，例如名稱、 別名、 辨別的名稱、 正式的網域名稱、 電子郵件地址或 GUID 值。     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>在這個範例中，我們將在 Office 365 中的兩個使用者帳戶： *meganb* *謝*，和*alexw*針對*Alex*。          |

    
    > [!TIP]
    > 您也可以使用此 cmdlet 的單一使用者：`Get-InformationBarrierRecipientStatus -Identity <value>`
    
2. 檢閱結果。 **取得 InformationBarrierRecipientStatus** cmdlet 會傳回使用者，例如屬性值和套用的任何資訊障礙原則的相關資訊。 

    檢閱結果，並採取接下來的步驟，如下表所述：
    
    |結果  |要執行的動作下一步]  |
    |---------|---------|
    |沒有區段會列出所選的使用者     |執行下列其中一項動作：<br/>-將使用者指派給現有區段藉由編輯使用者設定檔在 Azure Active Directory 中。 （請參閱[使用 Office 365 PowerShell 的設定使用者帳戶內容](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)）。<br/>-定義使用[支援屬性的資訊障礙](information-barriers-attributes.md)線段。 然後，[定義新的原則](information-barriers-policies.md#part-2-define-information-barrier-policies)，或加入區段的 [[編輯現有的原則](information-barriers-edit-segments-policies.md.md#edit-a-policy)。  |
    |區段會列出，但沒有資訊障礙原則指派給這些線段     |執行下列其中一項動作：<br/>- 每個區段有問題的[定義新的資訊障礙原則](information-barriers-policies.md#part-2-define-information-barrier-policies)<br/>- 若要將其指派給正確的區段的 [[編輯現有的資訊障礙原則](information-barriers-edit-segments-policies.md.md#edit-a-policy)         |
    |區段會列出與每個隨附於資訊障礙原則     |-執行`Get-InformationBarrierPolicy`指令程式來確認資訊障礙原則已啟用<br/>-執行`Get-InformationBarrierPoliciesApplicationStatus`指令程式來確認原則會套用<br/>-執行`Start-InformationBarrierPoliciesApplication`指令程式來套用所有作用中的資訊障礙原則          |
    

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>問題： 我需要移除資訊障礙原則中的單一使用者

在此情況下，資訊障礙原則已生效，並在一或多個使用者意外阻止 Microsoft teams 與其他人通訊。 而不是完全移除資訊障礙原則，您可以從資訊障礙原則移除一或多個個別的使用者。 

### <a name="what-to-do"></a>要執行的動作

資訊障礙原則指派給使用者的區段。 區段定義使用特定[使用者帳戶設定檔中的屬性](information-barriers-attributes.md)。 如果您必須移除單一使用者的原則，請考慮編輯該使用者的 Azure Active Directory 中的設定檔，使得使用者無法再隨附於受到資訊障礙線段。

1. **取得 InformationBarrierRecipientStatus** cmdlet 搭配 Identity 參數。 此 cmdlet 會傳回使用者，例如屬性值和套用的任何資訊障礙原則的相關資訊。

    |語法  |範例  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`<p>您可以使用任何可唯一識別每位使用者，例如名稱、 別名、 辨別的名稱、 正式的網域名稱、 電子郵件地址或 GUID 值。     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>在這個範例中，我們將在 Office 365 中的兩個使用者帳戶： *meganb* *謝*，和*alexw*針對*Alex*。          |
    |`Get-InformationBarrierRecipientStatus -Identity <value>` <p>您可以使用唯一識別使用者，例如名稱、 別名、 辨別的名稱、 正式的網域名稱、 電子郵件地址或 GUID 的任何值。|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p>在這個範例中，我們將在 Office 365 中的單一帳戶： *jeanp*。 |

2. 檢閱結果，以查看指派資訊障礙原則，並從中所屬的一致。 

3. 若要從受影響的資訊障礙，[更新 Azure Active Directory 中的使用者設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)區段中移除使用者。

4. 等候大約 30 分鐘，進行 FwdSync 發生。 或執行`Start-InformationBarrierPoliciesApplication`指令程式來套用所有作用中的資訊障礙原則。

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>問題： 資訊障礙應用程式的處理程序的時間太長

執行**開始 InformationBarrierPoliciesApplication** cmdlet 之後，程序花很長的時間才能完成。

### <a name="what-to-do"></a>要執行的動作

請注意，當您執行原則的應用程式指令程式時，資訊障礙原則已套用 （或已移除），使用者的使用者，針對您的組織中的所有帳戶。 如果您有許多使用者時，它會處理一段時間。 （為一般指導方針，它需要大約等候一個小時處理 5000 的使用者帳戶）。

1. 使用**Get-InformationBarrierPoliciesApplicationStatus**指令程式來驗證最新的原則應用程式的狀態。

    |若要檢視的最新的原則應用程式  |若要檢視所有原則應用程式的狀態  |
    |---------|---------|
    |`Get-InformationBarrierPoliciesApplicationStatus`     |`Get-InformationBarrierPoliciesApplicationStatus -All $true`         |


    這會顯示原則應用程式是否完成、 失敗，或正在進行中的相關資訊。

2. 根據前一個步驟的結果，採取下列其中一個下列步驟：
  
    |狀態  |下一步  |
    |---------|---------|
    |**未開始**     |如果已超過 45 分鐘後已執行**開始 InformationBarrierPoliciesApplication**指令程式，請檢閱您的稽核記錄檔，以查看是否有原則定義中的任何錯誤或其他原因尚未啟動應用程式為何。 |
    |**失敗**     |如果失敗的應用程式，請先檢閱您的稽核記錄檔。 也請先檢閱您的區段和原則。 已指派給多個線段的任何使用者嗎？ 任何區段指派多個 poliicy 嗎？ 如有必要，[編輯線段](information-barriers-edit-segments-policies.md.md#edit-a-segment)及/或[編輯原則](information-barriers-edit-segments-policies.md.md#edit-a-policy)]，然後執行**開始 InformationBarrierPoliciesApplication**指令程式。  |
    |**進行中。**     |如果應用程式仍在進行中，允許更多的時間，才能完成。 如果尚未數天，收集您的稽核記錄，並再連絡客戶支援。 |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>問題： 資訊障礙原則則不會套用所有

在此情況下，您必須定義線段，定義資訊障礙原則，並嘗試將套用這些原則。 不過，當您執行`Get-InformationBarrierPoliciesApplicationStatus`指令程式，您可以看到原則應用程式已失敗。

### <a name="what-to-do"></a>要執行的動作

請確定您的組織不具有[Exchange 通訊錄原則](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)就地。 此類原則會防止資訊障礙原則套用。

1. 連線至[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。 

2. 執行[Get-addressbookpolicy](https://docs.microsoft.com/powershell/module/exchange/email-addresses-and-address-books/get-addressbookpolicy?view=exchange-ps)指令程式，並檢視結果。

    |結果  |下一步  |
    |---------|---------|
    |列出 Exchange 通訊錄原則     |[移除通訊錄原則](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy)         |
    |沒有通訊錄原則存在 |檢閱您的稽核記錄，以找出原則應用程式失敗的原因 |

3. [檢視狀態的使用者帳戶、 區段、 原則或原則應用程式](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)。

## <a name="related-topics"></a>相關主題

[在 Microsoft Teams 中定義的資訊障礙的原則](information-barriers-policies.md)

[資訊障礙](information-barriers.md)



