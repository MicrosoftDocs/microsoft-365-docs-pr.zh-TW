---
title: 管理資訊障礙原則
description: 瞭解如何編輯或移除資訊障礙的原則。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.openlocfilehash: 62e9910a1b94862ba23ecdc63c0fea1ec644043a
ms.sourcegitcommit: c10eb675da725830e9776d2a0566ba3622eb361c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980076"
---
# <a name="manage-information-barrier-policies"></a>管理資訊障礙原則

[定義資訊障礙原則](information-barriers-policies.md)之後，您可能需要變更這些原則或使用者區段，以作為[疑難排解](information-barriers-troubleshooting.md)的一部分，或定期進行維護。 使用本文做為指南。

## <a name="what-do-you-want-to-do"></a>您要執行的工作

|**動作**|**描述**|
|:---------|:--------------|
| [編輯使用者帳戶屬性](#edit-user-account-attributes) | 在 Azure Active Directory 中填入可用於定義區段的屬性。<br/>編輯使用者帳戶屬性時，使用者不會包含在應是的區段中，變更使用者所在的區段，或定義使用不同屬性的區段。 |
| [編輯區段](#edit-a-segment) | 當您想要變更區段定義的方式時，請編輯段落。 <br/>例如，您可能原本使用 *部門* 定義的區段，現在想要使用另一個屬性，例如 *MemberOf*。 |
| [編輯原則](#edit-a-policy) | 當您想要變更原則的運作方式時，請編輯資訊屏障原則。<br/>例如，您可以決定只允許在特定的區段之間進行通訊，而不是封鎖兩個網段間的通訊。 |
| [將原則設定為非使用中狀態](#set-a-policy-to-inactive-status) |當您想要變更原則或不想讓原則生效時，將原則設定為非使用中狀態。 |
| [移除原則](#remove-a-policy) | 當您不再需要特定的原則時，請移除資訊障礙原則。 |
| [停止原則應用程式](#stop-a-policy-application) | 當您想要停止套用資訊障礙原則的程式時，請採取此動作。<br/> 停止原則應用程式不會立即運作，也不會復原已套用至使用者的原則。 |
| [定義資訊障礙的原則](information-barriers-policies.md) | 定義資訊屏障原則時，當您不具備這類原則時，必須限制或限制特定使用者群組之間的通訊。 |
| [疑難排解資訊屏障](information-barriers-troubleshooting.md) | 當您遇到資訊障礙的意外問題時，請參閱本文。 |

> [!IMPORTANT]
> 若要執行本文所述的工作，您必須獲指派適當的角色，例如下列其中一項：<br/>-Microsoft 365 企業版全域系統管理員<br/>-全域管理員<br/>-合規性管理員<br/>-IB 相容性管理 (這是一個新的角色！ ) <br><br>若要深入瞭解資訊障礙的必要條件，請參閱 [資訊屏障原則) 的必要條件 (](information-barriers-policies.md#prerequisites)。<br><br> 請務必 [連接至安全性 & 規範中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。

## <a name="edit-user-account-attributes"></a>編輯使用者帳戶屬性

使用此程式可編輯用於分割使用者的屬性。 例如，如果您使用的是部門屬性，且有一或多個使用者帳戶目前未列出部門的任何值，您必須編輯這些使用者帳戶，以包含部門資訊。 使用者帳戶屬性可用來定義區段，這樣就可以指派資訊屏障原則。

1. 若要查看特定使用者帳戶的詳細資料，例如屬性值和指派的區段 (s) ，請使用 **InformationBarrierRecipientStatus 指令程式** 搭配 Identity 參數。

    |**語法**|**範例**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 您可以使用唯一識別每個使用者的任何值，例如名稱、別名、辨別名稱、正常化功能變數名稱、電子郵件地址或 GUID。 <p>  (您也可以將此 Cmdlet 用於單一使用者： `Get-InformationBarrierRecipientStatus -Identity <value>`)  |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> 在此範例中，我們會參考 Office 365 中的兩個使用者帳戶： *meganb* for *Megan* 和 *alexw* for *Alex*。 |

2. 決定您要編輯使用者帳戶設定檔的哪個屬性 (s) 。 如需詳細資訊，請參閱 [資訊障礙原則的屬性](information-barriers-attributes.md)。 

3. 編輯一或多個使用者帳戶，以包含您在上一個步驟中選取之屬性的值。 若要採取此動作，請使用下列其中一個程式：

    - 若要編輯單一帳戶，請參閱 [使用 Azure Active Directory 新增或更新使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。

    - 若要編輯多個帳戶 (或使用 PowerShell 編輯單一帳戶) ，請參閱 [Configure user account properties With Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)。

## <a name="edit-a-segment"></a>編輯區段

使用此程式來編輯使用者區段的定義。 例如，您可以變更區段的名稱或篩選，用來判斷區段中所包含的人員。

1. 若要查看所有現有的區段，請使用 **OrganizationSegment** Cmdlet。

    語法： `Get-OrganizationSegment`

    您將會看到每個區段和詳細資料的清單，例如區段類型、它的 UserGroupFilter 值、建立或上次修改的人員、GUID 等等。

    > [!TIP]
    > 列印或儲存區段清單以供日後參考。 例如，如果您想要編輯區段，您必須知道其名稱或識別值 (此參數會搭配 Identity 參數) 使用。

2. 若要編輯片段，請使用 **OrganizationSegment 指令程式** 搭配 **Identity** 參數和相關的詳細資料。

    |**語法**|**範例**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p> 在此範例中，針對具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd* 的網段，我們將部門名稱更新為 "HRDept"。 |

完成組織的編輯資料段後，您就可以 [定義](information-barriers-policies.md#part-2-define-information-barrier-policies) 或 [編輯](#edit-a-policy) 資訊障礙原則。

## <a name="edit-a-policy"></a>編輯原則

1. 若要查看目前資訊屏障原則的清單，請使用 **InformationBarrierPolicy** Cmdlet。

    語法： `Get-InformationBarrierPolicy`

    在結果清單中，識別您要變更的原則。 請注意原則的 GUID 和名稱。

2. 使用 **InformationBarrierPolicy** 指令程式搭配 **Identity** 參數，並指定您要進行的變更。

    範例：假設原則定義為封鎖「 *調查* 」區段與「 *銷售* 」和「 *行銷* 」區段的通訊。 原則是使用下列 Cmdlet 來定義的： `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`

    假設我們想要變更它，讓 *調查* 區段中的人員只能與 *HR* 區段中的人員進行通訊。 若要進行此變更，我們使用此 Cmdlet： `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    在此範例中，我們已將 "SegmentsBlocked" 變更為 "SegmentsAllowed"，並指定 *HR* 段。

3. 當您完成編輯原則時，請務必套用您的變更。  (請參閱套用 [資訊屏障原則](information-barriers-policies.md#part-3-apply-information-barrier-policies)。 ) 

## <a name="set-a-policy-to-inactive-status"></a>將原則設定為非使用中狀態

1. 若要查看目前資訊屏障原則的清單，請使用 **InformationBarrierPolicy** Cmdlet。

    語法： `Get-InformationBarrierPolicy`

    在結果清單中，找出您要變更的原則 (或移除) 。 請注意原則的 GUID 和名稱。

2. 若要將原則的狀態設定為非使用中，請使用 **InformationBarrierPolicy** 指令程式搭配 Identity 參數，並將 State 參數設定為非使用中。

    |**語法**|**範例**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p> 在此範例中，我們會將具有 GUID *43c37853-ea10-4b90-a23d-ab8c9377247* 的資訊屏障原則設定為非使用中狀態。 |

3. 若要套用您的變更，請使用 **InformationBarrierPoliciesApplication** Cmdlet。

    語法： `Start-InformationBarrierPoliciesApplication`

    為您的組織套用變更的使用者。 如果您的組織很大，則可能需要24小時的時間，才能完成此程式 (或多個) 。  (一般指導方針，處理5000使用者帳戶大約需要一小時。 ) 

此時，一或多項資訊障礙原則會設定為非使用中狀態。 您可以從這裡執行下列任何動作：

- 將其保持在 (原則設定為非使用中狀態時，不會影響使用者) 
- [編輯原則](#edit-a-policy) 
- [移除原則](#remove-a-policy)

## <a name="remove-a-policy"></a>移除原則

1. 若要查看目前資訊屏障原則的清單，請使用 **InformationBarrierPolicy** Cmdlet。

    語法： `Get-InformationBarrierPolicy`

    在結果清單中，識別您要移除的原則。 請注意原則的 GUID 和名稱。 請確定原則設定為非使用中狀態。

2. 使用具有 Identity 參數的 **InformationBarrierPolicy** Cmdlet。

    |**語法**|**範例**|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p> 在此範例中，我們將移除具有 GUID *43c37853-ea10-4b90-a23d-ab8c93772471* 的原則。 |

    出現提示時，請確認變更。

3. 針對您要移除的每個原則，重複步驟1-2。

4. 當您完成移除原則時，請套用您的變更。 若要採取此動作，請使用 **InformationBarrierPoliciesApplication** Cmdlet。

    語法： `Start-InformationBarrierPoliciesApplication`

    為您的組織套用變更的使用者。 如果您的組織很大，則可能需要24小時的時間，才能完成此程式 (或多個) 。

## <a name="stop-a-policy-application"></a>停止原則應用程式

在您開始套用資訊屏障原則之後，如果您想要停止套用那些原則，請使用下列程式。 這會花費大約30-35 分鐘的時間來開始處理常式。

1. 若要查看最新資訊屏障原則應用程式的狀態，請使用 **InformationBarrierPoliciesApplicationStatus** Cmdlet。

    語法： `Get-InformationBarrierPoliciesApplicationStatus`

    請記下應用程式的 GUID。

2. 使用具有 Identity 參數的 **InformationBarrierPoliciesApplication** Cmdlet。

    |**語法**|**範例**|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> 在此範例中，我們將停止套用資訊屏障原則。 |

## <a name="resources"></a>資源

- [取得資訊障礙的概覽](information-barriers.md)
- [定義資訊障礙的原則](information-barriers-policies.md)
- [深入瞭解 Microsoft 小組中的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [資訊屏障原則的屬性](information-barriers-attributes.md)
- [疑難排解資訊屏障](information-barriers-troubleshooting.md)
