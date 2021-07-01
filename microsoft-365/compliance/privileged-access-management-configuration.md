---
title: 開始使用 Privileged Access Management
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: 請參閱本文，以深入瞭解如何在 Office 365 中啟用和設定特殊許可權存取管理。
ms.openlocfilehash: 13b600c60e1b9c88285ee58efcf80a7ff5ea17fe
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226116"
---
# <a name="get-started-with-privileged-access-management"></a>開始使用 Privileged Access Management

本主題將引導您如何啟用及設定組織中的特殊許可權存取管理。 您可以使用 Microsoft 365 系統管理中心或 Exchange 管理 PowerShell 來管理和使用具有特殊許可權的存取權。

## <a name="before-you-begin"></a>開始之前

開始使用特殊許可權存取管理之前，您應該先確認您的[Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)及任何附加元件。 若要存取及使用「特殊的存取管理」，您的組織必須具備下列其中一項訂閱或附加元件：

- Microsoft 365 E5 訂閱 (付費或試用版) 
- Microsoft 365 E3 訂閱 (或 Office 365 E3 訂閱 + Enterprise 行動性和安全性 E3 訂閱) + Microsoft 365 E5 合規性附加元件
- 任何 Microsoft 365、Office 365、Exchange、SharePoint 或商務用 OneDrive 訂閱 + Microsoft 365 E5 的內部人員風險管理附加元件
- Microsoft 365 A5 訂閱 (付費或試用版) 
- Microsoft 365 A3 訂閱 (或 Office 365 A3 訂閱 + Enterprise 行動性和安全性 A3 訂閱) + Microsoft A5 符合性附加元件
- 教育訂閱的任何 Microsoft 365、Office 365、Exchange、SharePoint 或 OneDrive，以及 Microsoft 365 A5 的有問必答風險管理附加元件
- Office 365 企業版E5 訂閱 (付費或試用版本) 
- Office 365 企業版E3 訂閱 + Office 365 進階合規性附加元件 (無法再供新訂閱使用，請參閱記事) 

提交及回應特殊許可權存取管理要求的使用者，必須指派上述其中一個授權。

> [!IMPORTANT]
> Office 365 進階合規性不再以獨立訂閱銷售。 當目前的訂閱到期時，客戶應轉換至上述其中一個訂閱，其中包含相同或其他的符合性功能。

如果您沒有現有的 Office 365 企業版 E5 計畫，且想要嘗試「特殊的存取管理」，您可以[將 Microsoft 365 新增](/office365/admin/try-or-buy-microsoft-365)至現有的 Office 365 訂閱，或註冊 Microsoft 365 企業版 E5 的[試用版](https://www.microsoft.com/microsoft-365/enterprise)。

## <a name="enable-and-configure-privileged-access-management"></a>啟用和設定特殊許可權存取管理

請遵循下列步驟來設定和使用您組織中的特殊許可權存取：

- [步驟1：建立核准者的群組](privileged-access-management-configuration.md#step1)

    開始使用特殊權限存取之前，請決定誰需要傳入要求的核准授權，才能存取提升權限和特殊權限的工作。 任何屬於核准者群組的使用者都能核准存取要求。 您可以在 Office 365 中建立擁有郵件功能的安全性群組，以啟用此群組。

- [步驟2：啟用特殊許可權存取](privileged-access-management-configuration.md#step2)

    必須在 Office 365 中以預設核准者群組明確啟用特殊權限存取，包括您想要從特殊權限存取管理存取控制中排除的一組系統帳戶。

- [步驟3：建立存取原則](privileged-access-management-configuration.md#step3)

    建立核准原則可讓您定義以個別工作為範圍的特定核准需求。 核准類型選項為 **自動** 或 **手動**。

- [步驟4：提交/核准許可權存取要求](privileged-access-management-configuration.md#step4)

    啟用之後，特殊權限存取需要核准已定義相關聯核准原則的任何工作。 對於核准原則中包含的工作，使用者必須要求並取得存取核准，才能擁有執行工作所需的權限。

核准經過授與之後，要求的使用者就可以執行預定的工作，而特殊權限存取會代表使用者授權及執行工作。 核准對於要求持續時間 (預設持續時間為 4 小時) 仍然有效，在此期間要求者可以多次執行預定的工作。 所有此類執行會進行記錄，並可供安全性與合規性稽核使用。

> [!NOTE]
> 如果您想要使用 Exchange 管理 PowerShell 來啟用及設定特殊許可權存取，請依照連線中的步驟， [Exchange Online PowerShell 使用 Multi-Factor 驗證，使用](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)Exchange Online 身分驗證來連線至 PowerShell Office 365。 您不需要為組織啟用多重要素驗證，就能在連線至 Exchange Online PowerShell 時，使用這些步驟來啟用許可權存取。 使用多重要素驗證來建立 OAuth 權杖，以供簽署要求的授權存取使用。

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>步驟1：建立核准者的群組

1. 使用組織中系統管理員帳戶的認證登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。

2. 在系統管理中心中，移至 [**群組**] [  >  **新增群組**]。

3. 選取 [擁有 **郵件功能的安全性群組** ]，然後完成新群組的 **名稱**、 **群組電子郵件地址** 及 **描述** 欄位。

4. 儲存群組。  可能需要幾分鐘才能完整設定群組，並出現在 Microsoft 365 系統管理中心。

5. 選取新的核准者群組，然後選取 [ **編輯** ]，將使用者新增至群組。

6. 儲存群組。

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>步驟2：啟用特殊許可權存取

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 使用組織中系統管理員帳戶的認證，登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。

2. 在系統管理中心中，移至 **設定**  >  **Org 設定**  >  **Security & 隱私權**  >  **許可權**。

3. 啟用 [對 **特權任務需要核准** ] 控制項。

4. 將您在步驟1中建立的核准者群組指派為預設的 [ **核准者] 群組**。

5. **儲存** 並 **關閉**。

### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell

若要啟用特殊許可權存取並指派核准者的群組，請在 Exchange Online 中執行下列命令 PowerShell:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

範例：

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> 系統帳戶功能可供使用，以確保組織內的某些自動化可以運作，而不需要對特殊許可權存取進行相依性存取，但是建議您不要使用，且應該定期核准和審核這些排除專案。

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>步驟3：建立存取原則

您可以為組織建立及設定最多30個許可權存取原則。

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 使用組織中系統管理員帳戶的認證，登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。

2. 在系統管理中心中，移至 **設定**  >  **Org 設定**  >  **Security & 隱私權**  >  **許可權**。

3. 選取 [ **管理存取原則和要求**]。

4. 選取 [ **設定原則** ]，然後選取 [ **新增原則**]。

5. 從下拉欄位中，為您的組織選取適當的值：

    **原則類型**：工作、角色或角色群組

    **原則範圍**：Exchange

    **原則名稱**：從可用的原則中選取

    **核准類型**：手動或自動

    **核准群組**：選取在步驟 1 中建立的核准者群組

6. 選取 [ **建立** 後 **關閉**]。 可能需要幾分鐘的時間，才能完全設定或啟用原則。

### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell

若要建立及定義核准原則，請在 Exchange Online 中執行下列命令 PowerShell:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

範例：

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>步驟4：提交/核准許可權存取要求

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>要求提高權限以執行特殊權限工作

特殊權限存取的要求在提交要求後的 24 小時內有效。 如果未核准或拒絕，要求會過期，且不會核准存取權。

#### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 使用您的認證登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。

2. 在系統管理中心中，移至 **設定**  >  **Org 設定**  >  **Security & 隱私權**  >  **許可權**。

3. 選取 [ **管理存取原則和要求**]。

4. 選取 [ **新增要求**]。 從下拉欄位中，為您的組織選取適當的值：

    **要求類型**：工作、角色或角色群組

    **要求範圍**：Exchange

    **要求項目**：從可用的原則中選取

    **持續時間 (小時)**：要求存取的時數。 可要求的小時數沒有限制。

    **批註**：與您的 access 要求相關的註解文字欄位

5. 選取 [ **儲存** 並 **關閉**]。 您的要求將透過電子郵件傳送給核准者的群組。

#### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell

在 Exchange Online PowerShell 中執行下列命令，以建立並提交核准者群組的核准要求：

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

範例：

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>查看提高權限要求的狀態

在建立核准要求之後，可以在系統管理中心或使用與要求識別碼相關的 Exchange 管理 PowerShell 中查看提升要求狀態。

#### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 使用您的認證登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。

2. 在系統管理中心中，移至 **設定**  >  **Org 設定**  >  **Security & 隱私權**  >  **許可權**。

3. 選取 [ **管理存取原則和要求**]。

4. 選取 [ **View** ] （提交）以透過 **擱置**、 **核准**、 **拒絕** 或 **客戶密碼箱** 狀態來篩選送出的要求。

#### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell

在 Exchange Online PowerShell 中執行下列命令，以查看特定要求的核准要求狀態 ID:

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

範例：

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>核准提升授權要求

建立核准要求時，相關核准者群組的成員會收到電子郵件通知，而且可以核准與要求識別碼相關聯的要求。 要求者會透過電子郵件訊息收到要求核准或拒絕的通知。

#### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 使用您的認證登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。

2. 在系統管理中心中，移至 **設定**  >  **Org 設定**  >  **Security & 隱私權**  >  **許可權**。

3. 選取 [ **管理存取原則和要求**]。

4. 選取列出的要求以查看詳細資料，並對要求採取動作。

5. 選取 [ **核准** ] 以核准要求，或選取 [ **拒絕** ] 以拒絕要求。 先前核准的要求可以透過選取 **[撤銷]** 來撤銷存取權。

#### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell

若要核准提升授權要求，請在 Exchange Online 中執行下列命令 PowerShell:

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

範例：

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

若要拒絕提升許可權的要求，請在 Exchange Online 中執行下列命令 PowerShell:

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

範例：

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>在 Office 365 中刪除特殊許可權存取原則

如果您的組織已不再需要該原則，您可以刪除特殊許可權存取原則。

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 使用組織中系統管理員帳戶的認證登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。

2. 在系統管理中心中，移至 **設定**  >  **Org 設定**  >  **Security & 隱私權**  >  **許可權**。

3. 選取 [ **管理存取原則和要求**]。

4. 選取 [ **設定原則**]。

5. 選取您要刪除的原則，然後選取 [ **移除原則**]。

6. 選取 **[關閉]**。

### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell

若要刪除特殊許可權存取原則，請在 Exchange Online Powershell 中執行下列命令：

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>停用 Office 365 中的特殊許可權存取

如有需要，您可以停用組織的特殊許可權存取管理。 停用特殊許可權存取不會刪除任何關聯的核准原則或核准者群組。

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 使用您組織中的系統管理員帳戶的認證，登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。

2. 在系統管理中心中，移至 **設定**  >  **Org 設定**  >  **Security & 隱私權**  >  **許可權**。

3. 啟用 [ **需要核准存取** 許可權] 控制。

### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell

若要停用特殊許可權存取，請在 Exchange Online Powershell 中執行下列命令：

```PowerShell
Disable-ElevatedAccessControl
```
