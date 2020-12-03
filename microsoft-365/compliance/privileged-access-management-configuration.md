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
ms.openlocfilehash: 6018d3b842dcadb60208e6ab53707a50e26f9d35
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560871"
---
# <a name="get-started-with-privileged-access-management"></a>開始使用 Privileged Access Management

本主題將引導您如何啟用及設定組織中的特殊許可權存取管理。 您可以使用 Microsoft 365 系統管理中心或 Exchange 管理 PowerShell 來管理和使用特殊許可權存取。

## <a name="before-you-begin"></a>在您開始之前

開始使用特殊許可權存取管理之前，您應該先確認您的 [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 及任何附加元件。 若要存取及使用「特殊的存取管理」，您的組織必須具備下列其中一項訂閱或附加元件：

- Microsoft 365 E5 訂閱 (付費或試用版本) 
- Microsoft 365 E3 訂閱 (或 Office 365 E3 訂閱 + Enterprise 可移動性和 Security E3 訂閱) + Microsoft 365 E5 相容性附加元件
- 商務訂閱的任何 Microsoft 365、Office 365、Exchange、SharePoint 或 OneDrive + Microsoft 365 E5 內幕人士風險管理附加元件  
- Microsoft 365 A5 訂閱 (付費或試用版本) 
- Microsoft 365 A3 訂閱 (或 Office 365 A3 訂閱 + 企業行動及安全性 A3 訂閱) + Microsoft A5 規範附加元件
- 教育版訂閱的任何 Microsoft 365、Office 365、Exchange、SharePoint 或 OneDrive，也就是 Microsoft 365 A5 內幕人士風險管理附加元件
- Office 365 企業版 E5 訂閱 (付費或試用版本) 
- Office 365 企業版 E3 訂閱 + Office 365 Advanced 合規性附加元件 (已無法再供新訂閱使用，請參閱記事) 

提交及回應特殊許可權存取管理要求的使用者，必須指派上述其中一個授權。

>[!IMPORTANT]
>Office 365 Advanced 合規性不再銷售為獨立訂閱。 當目前的訂閱到期時，客戶應轉換至上述其中一個訂閱，其中包含相同或其他的符合性功能。

如果您沒有現有的 Office 365 企業版 E5 計畫，且想要嘗試使用許可權存取管理，您可以 [將 microsoft 365 新增](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 至現有的 office 365 訂閱，或註冊 Microsoft 365 企業版 e5 的 [試用版](https://www.microsoft.com/microsoft-365/enterprise) 。

## <a name="enable-and-configure-privileged-access-management"></a>啟用和設定特殊許可權存取管理

請遵循下列步驟來設定和使用您組織中的特殊許可權存取：

- [步驟1：建立核准者的群組](privileged-access-management-configuration.md#step1)

    在開始使用「許可權存取」之前，請先決定誰需要核准授權，以便存取提升和特權的任務。 任何屬於核准者群組的使用者都可以核准存取要求。 您可以在 Office 365 中建立擁有郵件功能的安全性群組，以啟用此群組。

- [步驟2：啟用特殊許可權存取](privileged-access-management-configuration.md#step2)

    必須明確啟用具有預設核准者群組的 Office 365 中的許可權存取，包括您想要從特殊許可權存取管理存取控制中排除的一組系統帳戶。

- [步驟3：建立存取原則](privileged-access-management-configuration.md#step3)

    建立核准原則可讓您定義個別任務的特定核准需求範圍。 核准類型選項為 **自動** 或 **手動**。

- [步驟4：提交/核准許可權存取要求](privileged-access-management-configuration.md#step4)

    一旦啟用，「特殊許可權存取」會要求任何具有定義相關核准原則的任務的核准。 對於包含在核准原則中的工作，使用者必須要求並授與「存取權核准」，以具備執行工作所需的許可權。

授與核准後，要求使用者可以執行預定的工作，而許可權存取將會代表使用者授權並執行工作。 核准對於要求的持續時間保持有效 (預設持續時間為4小時) ，在此期間，申請者可以多次執行預定的工作。 所有這類執行都會記錄下來，以進行安全性和合規性審核。 

>[!NOTE]
>如果您想要使用 Exchange 管理 PowerShell 來啟用及設定特殊許可權存取，請依照使用 Multi-Factor 驗證連線至 exchange Online PowerShell 與 Office 365 認證， [使用 [連線至 Exchange online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) 中的步驟進行。 您不需要為組織啟用多重要素驗證，就能在連線至 Exchange Online PowerShell 時，使用這些步驟來啟用許可權存取。 使用多重要素驗證來建立 OAuth 權杖，以供簽署要求的授權存取使用。

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>步驟1：建立核准者的群組

1. 使用組織中的系統管理員帳號憑證，登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) 。

2. 在系統管理中心中，移至 [**群組**] [  >  **新增群組**]。

3. 選取 [擁有 **郵件功能的安全性群組** ]，然後完成新群組的 **名稱**、 **群組電子郵件地址** 及 **描述** 欄位。

4. 儲存群組。 可能需要幾分鐘的時間，才能完整設定群組，並顯示在 Microsoft 365 系統管理中心。

5. 選取新的核准者群組，然後選取 [ **編輯** ]，將使用者新增至群組。

6. 儲存群組。

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>步驟2：啟用特殊許可權存取

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 使用組織中的系統管理員帳號憑證，登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) 。

2. 在系統管理中心中，移至 [**設定**  >  **組織設定**  >  **安全性 & 隱私權** 特殊  >  **許可權存取**]。

3. 啟用 [對 **特權任務需要核准** ] 控制項。

4. 將您在步驟1中建立的核准者群組指派為預設的 [ **核准者] 群組**。

5. **儲存** 並 **關閉**。

### <a name="in-exchange-management-powershell"></a>在 Exchange 管理 PowerShell

若要啟用特殊許可權存取並指派核准者的群組，請在 Exchange Online 中執行下列命令 PowerShell:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

範例：

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
>系統帳戶功能可供使用，以確保組織內的某些自動化可以運作，而不需要對特殊許可權存取進行相依性存取，但是建議您不要使用，且應該定期核准和審核這些排除專案。

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>步驟3：建立存取原則

您可以為組織建立及設定最多30個許可權存取原則。

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 使用組織中的系統管理員帳號憑證，登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) 。

2. 在系統管理中心中，移至 [**設定**  >  **組織設定**  >  **安全性 & 隱私權** 特殊  >  **許可權存取**]。

3. 選取 [ **管理存取原則和要求**]。

4. 選取 [ **設定原則** ]，然後選取 [ **新增原則**]。

5. 從下拉欄位中，為您的組織選取適當的值：
    
    **原則類型**：任務、角色或角色群組

    **原則範圍**： Exchange

    **原則名稱**：從可用原則中選取

    **核准類型**：手動或自動

    **核准群組**：選取步驟1中建立的核准者群組

6. 選取 [ **建立** 後 **關閉**]。 可能需要幾分鐘的時間，才能完全設定或啟用原則。

### <a name="in-exchange-management-powershell"></a>在 Exchange 管理 PowerShell

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

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>要求提升授權以執行特權任務

在提交要求後，可長達24小時的許可權存取要求是有效的。 若未核准或拒絕，要求便會到期，而且不會核准存取權。

#### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 使用您的認證登入 [Microsoft 365 Admin Center](https://admin.microsoft.com) 。

2. 在系統管理中心中，移至 [**設定**  >  **組織設定**  >  **安全性 & 隱私權** 特殊  >  **許可權存取**]。

3. 選取 [ **管理存取原則和要求**]。

4. 選取 [ **新增要求**]。 從下拉欄位中，為您的組織選取適當的值：

    **要求類型**：任務、角色或角色群組

    **要求範圍**： Exchange

    **要求**：從可用原則選取

    **Duration (小時)**：要求存取的小時數。 可要求的小時數沒有限制。

    **批註**：與您的 access 要求相關的註解文字欄位

5. 選取 [ **儲存** 並 **關閉**]。 您的要求將透過電子郵件傳送給核准者的群組。

#### <a name="in-exchange-management-powershell"></a>在 Exchange 管理 PowerShell

在 Exchange Online PowerShell 中執行下列命令，以建立並提交核准者群組的核准要求：

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

範例：

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>查看提升要求狀態

在建立核准要求之後，可以在系統管理中心或 Exchange Management PowerShell 中，使用與要求識別碼相關聯的方式來複查提升要求狀態。

#### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 使用您的認證登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) 。

2. 在系統管理中心中，移至 [**設定**  >  **組織設定**  >  **安全性 & 隱私權** 特殊  >  **許可權存取**]。

3. 選取 [ **管理存取原則和要求**]。

4. 選取 [ **View** ] （提交）以透過 **擱置**、 **核准**、 **拒絕** 或 **客戶密碼箱** 狀態來篩選送出的要求。

#### <a name="in-exchange-management-powershell"></a>在 Exchange 管理 PowerShell

在 Exchange Online PowerShell 中執行下列命令，以查看特定要求的核准要求狀態 ID:

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

範例：

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>核准提升授權要求

建立核准要求時，相關核准者群組的成員會收到電子郵件通知，而且可以核准與要求識別碼相關聯的要求。 要求核准或透過電子郵件訊息的拒絕通知要求者。

#### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 使用您的認證登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) 。

2. 在系統管理中心中，移至 [**設定**  >  **組織設定**  >  **安全性 & 隱私權** 特殊  >  **許可權存取**]。

3. 選取 [ **管理存取原則和要求**]。

4. 選取列出的要求以查看詳細資料，並對要求採取動作。

5. 選取 [ **核准** ] 以核准要求，或選取 [ **拒絕** ] 以拒絕要求。 先前核准的要求可以透過選取 **[撤銷]** 來撤銷存取權。

#### <a name="in-exchange-management-powershell"></a>在 Exchange 管理 PowerShell

若要核准提升授權要求，請在 Exchange Online 中執行下列命令 PowerShell:

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

範例：

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

若要拒絕提升授權要求，請在 Exchange Online 中執行下列命令 PowerShell:

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

範例：

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>刪除 Office 365 中的許可權存取原則

如果您的組織已不再需要該原則，您可以刪除特殊許可權存取原則。

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 使用組織中的系統管理員帳號憑證，登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) 。

2. 在系統管理中心中，移至 [**設定**  >  **組織設定**  >  **安全性 & 隱私權** 特殊  >  **許可權存取**]。

3. 選取 [ **管理存取原則和要求**]。

4. 選取 [ **設定原則**]。

5. 選取您要刪除的原則，然後選取 [ **移除原則**]。

6. 選取 **[關閉]**。

### <a name="in-exchange-management-powershell"></a>在 Exchange 管理 PowerShell

若要刪除特殊許可權存取原則，請在 Exchange Online Powershell 中執行下列命令：

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>停用 Office 365 的特殊許可權存取

如有需要，您可以停用組織的特殊許可權存取管理。 停用特殊許可權存取不會刪除任何關聯的核准原則或核准者群組。

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 使用組織中的系統管理員帳戶的認證登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) 。

2. 在系統管理中心中，移至 [**設定**  >  **組織設定**  >  **安全性 & 隱私權** 特殊  >  **許可權存取**]。

3. 啟用 [ **需要核准存取** 許可權] 控制。

### <a name="in-exchange-management-powershell"></a>在 Exchange 管理 PowerShell

若要停用特殊許可權存取，請在 Exchange Online Powershell 中執行下列命令：

```PowerShell
Disable-ElevatedAccessControl
```
