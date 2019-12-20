---
title: 在 Office 365 中設定特殊權限的存取管理
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
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: 使用此主題以深入了解 Office 365 中設定特殊權限的存取管理
ms.openlocfilehash: 5b7bf33f41bc722c557f2b515c5ab027bd401a2a
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40803760"
---
# <a name="configuring-privileged-access-management-in-office-365"></a>在 Office 365 中設定特殊權限的存取管理

> [!IMPORTANT]
> 本主題涵蓋功能目前僅適用於 Office 365 E5 和進階合規性 Sku 的部署和設定指導。

本主題會引導您啟用及設定特殊權限的存取管理 Office 365 組織中。 您可以使用 Microsoft 365 系統管理中心或 Exchange Management PowerShell 來管理和使用特殊權限的存取。 

## <a name="enable-and-configure-privileged-access-management"></a>啟用及設定特殊權限的存取管理

請遵循下列步驟來設定和使用 Office 365 組織中的特殊權限的存取：

- [步驟 1： 建立核准者群組](privileged-access-management-configuration.md#step1)

    開始使用權限存取之前，請決定誰需要核准授權的傳入要求存取提升權限和特殊權限的工作。 屬於核准者群組的任何使用者都能核准存取要求。 此群組會啟用在 Office 365 中建立擁有郵件功能的安全性群組。

- [步驟 2： 啟用特殊權限的存取](privileged-access-management-configuration.md#step2)

    特殊權限的存取必須是明確啟用 Office 365 中使用預設核准者群組，包括一組您想要排除的特殊權限的存取管理存取控制從系統帳戶之用。

- [步驟 3： 建立存取原則](privileged-access-management-configuration.md#step3)

    建立核准原則可讓您定義的範圍限定在個別工作的特定核准需求。 核准類型選項會**自動**或**手動**。

- [步驟 4： 送出/核准特殊權限的存取要求](privileged-access-management-configuration.md#step4)

    一旦啟用後，特殊權限存取需要核准的任何具有相關聯的核准原則定義的工作。 針對包含在核准原則中的工作，使用者必須要求，並授與存取權核准能夠執行工作所需權限。

授與核准之後，要求使用者可執行預定的工作和特殊權限的存取將授權執行代表使用者工作。 核准保持有效要求的持續期間 （預設時間為 4 小時），在這期間要求者可執行預定的任務多次。 所有這類執行會記錄，並可供安全性和法規遵循稽核。 

> [!NOTE]
> 如果您想要使用 Exchange Management PowerShell 來啟用及設定特殊權限的存取，請依照下列[PowerShell 連線到 Exchange Online 使用多重要素驗證](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)與您的 Office 365 認證連線至 Exchange Online PowerShell 中的步驟。 您不需要啟用若要使用的步驟來連線至 Exchange Online PowerShell 時啟用特殊權限的存取 Office 365 組織的多重要素驗證。 以多重要素驗證連線建立簽署您要求的特殊權限存取使用 OAuth 權杖。

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>步驟 1： 建立核准者群組

1. 登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用您組織中系統管理員帳戶認證。

2. 在系統管理中心，移至 [**群組** > **加入群組**。

3. 選取 [**啟用郵件功能的安全性群組**，然後完成 [新群組的**名稱**、**群組電子郵件地址**，以及**描述**欄位。

4. 儲存群組。 可能需要幾分鐘的完整設定，並出現在 Microsoft 365 系統管理中心中的群組。

5. 選取新的核准者群組，然後選取 [**編輯**] 以將使用者新增至群組。

6. 儲存群組。

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>步驟 2： 啟用特殊權限的存取

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用您組織中系統管理員帳戶認證。

2. 在系統管理中心中，前往 [**設定 > 設定 > 安全性 & 隱私權** > **特殊權限的存取**。

3. 啟用**需要核准的特殊權限的工作，但**控制項。

4. 指派您在做為**預設核准者群組**的步驟 1 建立的核准者群組。

5. **儲存**並**關閉**。

### <a name="in-exchange-management-powershell"></a>在 [Exchange Management PowerShell

若要啟用特殊權限的存取，並將指定的核准者群組，請在 Exchange Online PowerShell 中執行下列命令：
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
範例：
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> 功能便可確保在組織內特定自動化系統帳戶可以處理，而相依性的特殊權限存取，但還是建議這類排除項目是例外並允許這些應該核准及稽核定期。

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>步驟 3： 建立存取原則

您可以建立及設定 Office 365 組織的最多 30 特殊權限的存取原則。

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用您組織中系統管理員帳戶認證。

2. 在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。

3. 選取 [**管理存取原則和要求**。

4. 選取 [**設定原則**，然後選取 [**新增原則**。

5. 從下拉式清單的欄位，選取適當的值為您的組織：
    
    **原則類型**： 任務、 角色或角色群組

    **原則範圍**： Exchange

    **原則名稱**： 選取 [從可用的原則

    **核准類型**： 手動或自動

    **核准群組**： 選取步驟 1 中建立的核准者群組

6. 選取 [**建立**，然後**關閉**。 可能需要幾分鐘的完整設定並啟用原則。

### <a name="in-exchange-management-powershell"></a>在 [Exchange Management PowerShell

若要建立及定義核准原則，請在 Exchange Online PowerShell 中執行下列命令：

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
範例：
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>步驟 4： 送出/核准特殊權限的存取要求

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>要求提高權限的授權，才能執行特殊權限的工作

最多 24 小時之後提交要求的特殊權限存取要求是有效的。 如果未受到核准或拒絕，要求而到期，並且存取未核准。

#### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用您的認證。

2. 在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。

3. 選取 [**管理存取原則和要求**。

4. 選取**新的要求**。 從下拉式清單的欄位，選取適當的值為您的組織：

    **要求類型**： 任務、 角色或角色群組

    **要求範圍**： Exchange

    **要求**： 選取 [從可用的原則

    **持續時間 （小時）**： 存取要求的時數。 您可以要求的時數沒有限制。

    **註解**： 存取要求相關的註解的文字欄位

5. 選取**儲存**，然後**關閉**。 您的要求會傳送至透過電子郵件的核准者群組。

#### <a name="in-exchange-management-powershell"></a>在 [Exchange Management PowerShell

執行下列命令在 Exchange Online PowerShell 來建立及提交核准要求的核准者群組：
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
範例：
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a>檢視提高權限要求的狀態
建立核准要求之後，可以在系統管理中心檢閱提高權限要求的狀態，或在 Exchange Management PowerShell 要求使用相關聯的識別碼。

#### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用您的認證。

2. 在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。

3. 選取 [**管理存取原則和要求**。

4. 選取 [**檢視****擱置中**、**已核准**、 **「 拒絕 」** 或**客戶加密箱**狀態篩選已提交的要求。

#### <a name="in-exchange-management-powershell"></a>在 [Exchange Management PowerShell

執行下列命令在 Exchange Online PowerShell 來檢視特定的要求 ID 核准要求的狀態：
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
範例：
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>核准提高權限授權要求
建立核准要求時，相關的核准者群組的成員接收電子郵件通知，並可核准要求識別碼相關聯的要求 要求者要求核准或拒絕透過電子郵件訊息的通知。

#### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用您的認證。

2. 在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。

3. 選取 [**管理存取原則和要求**。

4. 選取所列的要求來檢視詳細資料，並採取動作的要求。

5. 選取 [核准要求，或選取 [**拒絕**] 拒絕要求**核准**]。 先前核准的要求可以藉由選取**撤銷**撤銷的存取。

#### <a name="in-exchange-management-powershell"></a>在 [Exchange Management PowerShell

若要核准提高權限授權要求，請在 Exchange Online PowerShell 中執行下列命令：

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
範例：
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

若要拒絕提高權限授權要求，請在 Exchange Online PowerShell 中執行下列命令：

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
範例：
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>刪除 Office 365 中的特殊權限的存取原則
如果不再需要您組織中，您可以刪除的特殊權限的存取原則。

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用您組織中系統管理員帳戶認證。

2. 在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。

3. 選取 [**管理存取原則和要求**。

4. 選取 [**設定原則**。

5. 選取您要刪除的原則，然後選取 [**移除原則**。

6. 選取 [**關閉**]。

### <a name="in-exchange-management-powershell"></a>在 [Exchange Management PowerShell

若要刪除的特殊權限的存取原則，請在 Exchange Online Powershell 中執行下列命令：

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>停用 Office 365 中的特殊權限的存取

如有需要您可以停用貴組織的特殊權限的存取管理。 停用權限存取不會刪除任何相關聯的核准原則或核准者群組。

### <a name="in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心

1. 在您的組織中系統管理員帳戶登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用認證。

2. 在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。

3. 啟用**需要核准的特殊權限的存取**控制。

### <a name="in-exchange-management-powershell"></a>在 [Exchange Management PowerShell

若要停用特殊權限的存取，請在 Exchange Online Powershell 中執行下列命令：

```
Disable-ElevatedAccessControl
```