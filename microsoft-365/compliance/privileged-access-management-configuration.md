---
title: 開始使用特殊權限存取管理
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
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: 若要深入了解設定特殊權限的存取管理使用本主題。
ms.openlocfilehash: bb1589252ab7a5f7a512db92666827dd9d3cc2d3
ms.sourcegitcommit: 6c7f6ef98c321c80a9254c10bbbb917895b5c156
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/27/2020
ms.locfileid: "42322523"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="ac29f-103">開始使用特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="ac29f-103">Get started with privileged access management</span></span>

>[!IMPORTANT]
><span data-ttu-id="ac29f-104">本主題涵蓋功能目前僅適用於 Office 365 E5 和進階合規性 Sku 的部署和設定指導。</span><span class="sxs-lookup"><span data-stu-id="ac29f-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="ac29f-105">本主題會引導您啟用及設定特殊權限的存取管理 Office 365 組織中。</span><span class="sxs-lookup"><span data-stu-id="ac29f-105">This topic guides you through enabling and configuring privileged access management in your Office 365 organization.</span></span> <span data-ttu-id="ac29f-106">您可以使用 Microsoft 365 系統管理中心或 Exchange Management PowerShell 來管理和使用特殊權限的存取。</span><span class="sxs-lookup"><span data-stu-id="ac29f-106">You can use either the Microsoft 365 Admin Center or Exchange Management PowerShell to manage and use privileged access.</span></span> 

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="ac29f-107">啟用及設定特殊權限的存取管理</span><span class="sxs-lookup"><span data-stu-id="ac29f-107">Enable and configure privileged access management</span></span>

<span data-ttu-id="ac29f-108">請遵循下列步驟來設定和使用 Office 365 組織中的特殊權限的存取：</span><span class="sxs-lookup"><span data-stu-id="ac29f-108">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="ac29f-109">步驟 1： 建立核准者群組</span><span class="sxs-lookup"><span data-stu-id="ac29f-109">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="ac29f-110">開始使用權限存取之前，請決定誰需要核准授權的傳入要求存取提升權限和特殊權限的工作。</span><span class="sxs-lookup"><span data-stu-id="ac29f-110">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="ac29f-111">屬於核准者群組的任何使用者都能核准存取要求。</span><span class="sxs-lookup"><span data-stu-id="ac29f-111">Any user who is part of the Approvers’ group is able to approve access requests.</span></span> <span data-ttu-id="ac29f-112">此群組會啟用在 Office 365 中建立擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="ac29f-112">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="ac29f-113">步驟 2： 啟用特殊權限的存取</span><span class="sxs-lookup"><span data-stu-id="ac29f-113">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="ac29f-114">特殊權限的存取必須是明確啟用 Office 365 中使用預設核准者群組，包括一組您想要排除的特殊權限的存取管理存取控制從系統帳戶之用。</span><span class="sxs-lookup"><span data-stu-id="ac29f-114">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="ac29f-115">步驟 3： 建立存取原則</span><span class="sxs-lookup"><span data-stu-id="ac29f-115">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="ac29f-116">建立核准原則可讓您定義的範圍限定在個別工作的特定核准需求。</span><span class="sxs-lookup"><span data-stu-id="ac29f-116">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="ac29f-117">核准類型選項會**自動**或**手動**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-117">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="ac29f-118">步驟 4： 送出/核准特殊權限的存取要求</span><span class="sxs-lookup"><span data-stu-id="ac29f-118">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="ac29f-119">一旦啟用後，特殊權限存取需要核准的任何具有相關聯的核准原則定義的工作。</span><span class="sxs-lookup"><span data-stu-id="ac29f-119">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="ac29f-120">針對包含在核准原則中的工作，使用者必須要求，並授與存取權核准能夠執行工作所需權限。</span><span class="sxs-lookup"><span data-stu-id="ac29f-120">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="ac29f-121">授與核准之後，要求使用者可執行預定的工作和特殊權限的存取將授權執行代表使用者工作。</span><span class="sxs-lookup"><span data-stu-id="ac29f-121">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="ac29f-122">核准保持有效要求的持續期間 （預設時間為 4 小時），在這期間要求者可執行預定的任務多次。</span><span class="sxs-lookup"><span data-stu-id="ac29f-122">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="ac29f-123">所有這類執行會記錄，並可供安全性和法規遵循稽核。</span><span class="sxs-lookup"><span data-stu-id="ac29f-123">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="ac29f-124">如果您想要使用 Exchange Management PowerShell 來啟用及設定特殊權限的存取，請依照下列[PowerShell 連線到 Exchange Online 使用多重要素驗證](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)與您的 Office 365 認證連線至 Exchange Online PowerShell 中的步驟。</span><span class="sxs-lookup"><span data-stu-id="ac29f-124">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="ac29f-125">您不需要啟用若要使用的步驟來連線至 Exchange Online PowerShell 時啟用特殊權限的存取 Office 365 組織的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="ac29f-125">You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="ac29f-126">以多重要素驗證連線建立簽署您要求的特殊權限存取使用 OAuth 權杖。</span><span class="sxs-lookup"><span data-stu-id="ac29f-126">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="ac29f-127"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="ac29f-127"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="ac29f-128">步驟 1： 建立核准者群組</span><span class="sxs-lookup"><span data-stu-id="ac29f-128">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="ac29f-129">登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用您組織中系統管理員帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="ac29f-129">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="ac29f-130">在系統管理中心，移至 [**群組** > **加入群組**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-130">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="ac29f-131">選取 [**啟用郵件功能的安全性群組**，然後完成 [新群組的**名稱**、**群組電子郵件地址**，以及**描述**欄位。</span><span class="sxs-lookup"><span data-stu-id="ac29f-131">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="ac29f-132">儲存群組。</span><span class="sxs-lookup"><span data-stu-id="ac29f-132">Save the group.</span></span> <span data-ttu-id="ac29f-133">可能需要幾分鐘的完整設定，並出現在 Microsoft 365 系統管理中心中的群組。</span><span class="sxs-lookup"><span data-stu-id="ac29f-133">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="ac29f-134">選取新的核准者群組，然後選取 [**編輯**] 以將使用者新增至群組。</span><span class="sxs-lookup"><span data-stu-id="ac29f-134">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="ac29f-135">儲存群組。</span><span class="sxs-lookup"><span data-stu-id="ac29f-135">Save the group.</span></span>

<span data-ttu-id="ac29f-136"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="ac29f-136"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="ac29f-137">步驟 2： 啟用特殊權限的存取</span><span class="sxs-lookup"><span data-stu-id="ac29f-137">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="ac29f-138">在 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="ac29f-138">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="ac29f-139">登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用您組織中系統管理員帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="ac29f-139">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="ac29f-140">在系統管理中心中，前往 [**設定 > 設定 > 安全性 & 隱私權** > **特殊權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-140">In the Admin Center, go to **Settings > Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ac29f-141">啟用**需要核准的特殊權限的工作，但**控制項。</span><span class="sxs-lookup"><span data-stu-id="ac29f-141">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="ac29f-142">指派您在做為**預設核准者群組**的步驟 1 建立的核准者群組。</span><span class="sxs-lookup"><span data-stu-id="ac29f-142">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="ac29f-143">**儲存**並**關閉**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-143">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="ac29f-144">在 [Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac29f-144">In Exchange Management PowerShell</span></span>

<span data-ttu-id="ac29f-145">若要啟用特殊權限的存取，並將指定的核准者群組，請在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ac29f-145">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="ac29f-146">範例：</span><span class="sxs-lookup"><span data-stu-id="ac29f-146">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="ac29f-147">功能便可確保在組織內特定自動化系統帳戶可以處理，而相依性的特殊權限存取，但還是建議這類排除項目是例外並允許這些應該核准及稽核定期。</span><span class="sxs-lookup"><span data-stu-id="ac29f-147">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="ac29f-148"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="ac29f-148"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="ac29f-149">步驟 3： 建立存取原則</span><span class="sxs-lookup"><span data-stu-id="ac29f-149">Step 3: Create an access policy</span></span>

<span data-ttu-id="ac29f-150">您可以建立及設定 Office 365 組織的最多 30 特殊權限的存取原則。</span><span class="sxs-lookup"><span data-stu-id="ac29f-150">You can create and configure up to 30 privileged access policies for your Office 365 organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="ac29f-151">在 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="ac29f-151">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="ac29f-152">登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用您組織中系統管理員帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="ac29f-152">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="ac29f-153">在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ac29f-154">選取 [**管理存取原則和要求**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ac29f-155">選取 [**設定原則**，然後選取 [**新增原則**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-155">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="ac29f-156">從下拉式清單的欄位，選取適當的值為您的組織：</span><span class="sxs-lookup"><span data-stu-id="ac29f-156">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="ac29f-157">**原則類型**： 任務、 角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="ac29f-157">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="ac29f-158">**原則範圍**： Exchange</span><span class="sxs-lookup"><span data-stu-id="ac29f-158">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="ac29f-159">**原則名稱**： 選取 [從可用的原則</span><span class="sxs-lookup"><span data-stu-id="ac29f-159">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="ac29f-160">**核准類型**： 手動或自動</span><span class="sxs-lookup"><span data-stu-id="ac29f-160">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="ac29f-161">**核准群組**： 選取步驟 1 中建立的核准者群組</span><span class="sxs-lookup"><span data-stu-id="ac29f-161">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="ac29f-162">選取 [**建立**，然後**關閉**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-162">Select **Create** and then **Close**.</span></span> <span data-ttu-id="ac29f-163">可能需要幾分鐘的完整設定並啟用原則。</span><span class="sxs-lookup"><span data-stu-id="ac29f-163">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="ac29f-164">在 [Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac29f-164">In Exchange Management PowerShell</span></span>

<span data-ttu-id="ac29f-165">若要建立及定義核准原則，請在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ac29f-165">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="ac29f-166">範例：</span><span class="sxs-lookup"><span data-stu-id="ac29f-166">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="ac29f-167"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="ac29f-167"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="ac29f-168">步驟 4： 送出/核准特殊權限的存取要求</span><span class="sxs-lookup"><span data-stu-id="ac29f-168">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="ac29f-169">要求提高權限的授權，才能執行特殊權限的工作</span><span class="sxs-lookup"><span data-stu-id="ac29f-169">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="ac29f-170">最多 24 小時之後提交要求的特殊權限存取要求是有效的。</span><span class="sxs-lookup"><span data-stu-id="ac29f-170">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="ac29f-171">如果未受到核准或拒絕，要求而到期，並且存取未核准。</span><span class="sxs-lookup"><span data-stu-id="ac29f-171">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="ac29f-172">在 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="ac29f-172">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="ac29f-173">登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用您的認證。</span><span class="sxs-lookup"><span data-stu-id="ac29f-173">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="ac29f-174">在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-174">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ac29f-175">選取 [**管理存取原則和要求**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-175">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ac29f-176">選取**新的要求**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-176">Select **New request**.</span></span> <span data-ttu-id="ac29f-177">從下拉式清單的欄位，選取適當的值為您的組織：</span><span class="sxs-lookup"><span data-stu-id="ac29f-177">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="ac29f-178">**要求類型**： 任務、 角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="ac29f-178">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="ac29f-179">**要求範圍**： Exchange</span><span class="sxs-lookup"><span data-stu-id="ac29f-179">**Request scope**: Exchange</span></span>

    <span data-ttu-id="ac29f-180">**要求**： 選取 [從可用的原則</span><span class="sxs-lookup"><span data-stu-id="ac29f-180">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="ac29f-181">**持續時間 （小時）**： 存取要求的時數。</span><span class="sxs-lookup"><span data-stu-id="ac29f-181">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="ac29f-182">您可以要求的時數沒有限制。</span><span class="sxs-lookup"><span data-stu-id="ac29f-182">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="ac29f-183">**註解**： 存取要求相關的註解的文字欄位</span><span class="sxs-lookup"><span data-stu-id="ac29f-183">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="ac29f-184">選取**儲存**，然後**關閉**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-184">Select **Save** and then **Close**.</span></span> <span data-ttu-id="ac29f-185">您的要求會傳送至透過電子郵件的核准者群組。</span><span class="sxs-lookup"><span data-stu-id="ac29f-185">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="ac29f-186">在 [Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac29f-186">In Exchange Management PowerShell</span></span>

<span data-ttu-id="ac29f-187">執行下列命令在 Exchange Online PowerShell 來建立及提交核准要求的核准者群組：</span><span class="sxs-lookup"><span data-stu-id="ac29f-187">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="ac29f-188">範例：</span><span class="sxs-lookup"><span data-stu-id="ac29f-188">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="ac29f-189">檢視提高權限要求的狀態</span><span class="sxs-lookup"><span data-stu-id="ac29f-189">View status of elevation requests</span></span>

<span data-ttu-id="ac29f-190">建立核准要求之後，可以在系統管理中心檢閱提高權限要求的狀態，或在 Exchange Management PowerShell 要求使用相關聯的識別碼。</span><span class="sxs-lookup"><span data-stu-id="ac29f-190">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="ac29f-191">在 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="ac29f-191">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="ac29f-192">登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用您的認證。</span><span class="sxs-lookup"><span data-stu-id="ac29f-192">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="ac29f-193">在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-193">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ac29f-194">選取 [**管理存取原則和要求**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-194">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ac29f-195">選取 [**檢視\*\*\*\*擱置中**、**已核准**、 **「 拒絕 」** 或**客戶加密箱**狀態篩選已提交的要求。</span><span class="sxs-lookup"><span data-stu-id="ac29f-195">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="ac29f-196">在 [Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac29f-196">In Exchange Management PowerShell</span></span>

<span data-ttu-id="ac29f-197">執行下列命令在 Exchange Online PowerShell 來檢視特定的要求 ID 核准要求的狀態：</span><span class="sxs-lookup"><span data-stu-id="ac29f-197">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="ac29f-198">範例：</span><span class="sxs-lookup"><span data-stu-id="ac29f-198">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="ac29f-199">核准提高權限授權要求</span><span class="sxs-lookup"><span data-stu-id="ac29f-199">Approving an elevation authorization request</span></span>

<span data-ttu-id="ac29f-200">建立核准要求時，相關的核准者群組的成員接收電子郵件通知，並可核准要求識別碼相關聯的要求</span><span class="sxs-lookup"><span data-stu-id="ac29f-200">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="ac29f-201">要求者要求核准或拒絕透過電子郵件訊息的通知。</span><span class="sxs-lookup"><span data-stu-id="ac29f-201">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="ac29f-202">在 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="ac29f-202">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="ac29f-203">登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用您的認證。</span><span class="sxs-lookup"><span data-stu-id="ac29f-203">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="ac29f-204">在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-204">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ac29f-205">選取 [**管理存取原則和要求**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-205">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ac29f-206">選取所列的要求來檢視詳細資料，並採取動作的要求。</span><span class="sxs-lookup"><span data-stu-id="ac29f-206">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="ac29f-207">選取 [核准要求，或選取 [**拒絕**] 拒絕要求**核准**]。</span><span class="sxs-lookup"><span data-stu-id="ac29f-207">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="ac29f-208">先前核准的要求可以藉由選取**撤銷**撤銷的存取。</span><span class="sxs-lookup"><span data-stu-id="ac29f-208">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="ac29f-209">在 [Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac29f-209">In Exchange Management PowerShell</span></span>

<span data-ttu-id="ac29f-210">若要核准提高權限授權要求，請在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ac29f-210">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="ac29f-211">範例：</span><span class="sxs-lookup"><span data-stu-id="ac29f-211">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="ac29f-212">若要拒絕提高權限授權要求，請在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ac29f-212">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="ac29f-213">範例：</span><span class="sxs-lookup"><span data-stu-id="ac29f-213">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="ac29f-214">刪除 Office 365 中的特殊權限的存取原則</span><span class="sxs-lookup"><span data-stu-id="ac29f-214">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="ac29f-215">如果不再需要您組織中，您可以刪除的特殊權限的存取原則。</span><span class="sxs-lookup"><span data-stu-id="ac29f-215">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="ac29f-216">在 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="ac29f-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="ac29f-217">登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用您組織中系統管理員帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="ac29f-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="ac29f-218">在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-218">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ac29f-219">選取 [**管理存取原則和要求**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ac29f-220">選取 [**設定原則**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-220">Select **Configure policies**.</span></span>

5. <span data-ttu-id="ac29f-221">選取您要刪除的原則，然後選取 [**移除原則**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-221">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="ac29f-222">選取 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-222">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="ac29f-223">在 [Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac29f-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="ac29f-224">若要刪除的特殊權限的存取原則，請在 Exchange Online Powershell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ac29f-224">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="ac29f-225">停用 Office 365 中的特殊權限的存取</span><span class="sxs-lookup"><span data-stu-id="ac29f-225">Disable privileged access in Office 365</span></span>

<span data-ttu-id="ac29f-226">如有需要您可以停用貴組織的特殊權限的存取管理。</span><span class="sxs-lookup"><span data-stu-id="ac29f-226">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="ac29f-227">停用權限存取不會刪除任何相關聯的核准原則或核准者群組。</span><span class="sxs-lookup"><span data-stu-id="ac29f-227">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="ac29f-228">在 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="ac29f-228">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="ac29f-229">在您的組織中系統管理員帳戶登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用認證。</span><span class="sxs-lookup"><span data-stu-id="ac29f-229">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="ac29f-230">在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="ac29f-230">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ac29f-231">啟用**需要核准的特殊權限的存取**控制。</span><span class="sxs-lookup"><span data-stu-id="ac29f-231">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="ac29f-232">在 [Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac29f-232">In Exchange Management PowerShell</span></span>

<span data-ttu-id="ac29f-233">若要停用特殊權限的存取，請在 Exchange Online Powershell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ac29f-233">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
