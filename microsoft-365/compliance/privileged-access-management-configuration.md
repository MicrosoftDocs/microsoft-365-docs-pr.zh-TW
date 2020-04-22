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
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: 若要深入瞭解設定特殊許可權存取管理，請使用本主題。
ms.openlocfilehash: 196685eda6818b399c778363ee458f6f2792a33a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626509"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="e3509-103">開始使用 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="e3509-103">Get started with privileged access management</span></span>

<span data-ttu-id="e3509-104">本主題將引導您如何啟用及設定組織中的特殊許可權存取管理。</span><span class="sxs-lookup"><span data-stu-id="e3509-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="e3509-105">您可以使用 Microsoft 365 系統管理中心或 Exchange 管理 PowerShell 來管理和使用特殊許可權存取。</span><span class="sxs-lookup"><span data-stu-id="e3509-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e3509-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="e3509-106">Before you begin</span></span>

<span data-ttu-id="e3509-107">開始使用特殊許可權存取管理之前，您應該先確認您的[Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)及任何附加元件。</span><span class="sxs-lookup"><span data-stu-id="e3509-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="e3509-108">若要存取及使用「特殊的存取管理」，您的組織必須具備下列其中一項訂閱或附加元件：</span><span class="sxs-lookup"><span data-stu-id="e3509-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="e3509-109">Microsoft 365 E5 訂閱（付費或試用版）</span><span class="sxs-lookup"><span data-stu-id="e3509-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="e3509-110">Microsoft 365 E3 訂閱（或 Office 365 E3 訂閱 + Enterprise 可移動性和 Security E3 訂閱） + Microsoft 365 E5 相容性附加元件</span><span class="sxs-lookup"><span data-stu-id="e3509-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="e3509-111">商務訂閱的任何 Microsoft 365、Office 365、Exchange、SharePoint 或 OneDrive + Microsoft 365 E5 內幕人士風險管理附加元件</span><span class="sxs-lookup"><span data-stu-id="e3509-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>  
- <span data-ttu-id="e3509-112">Microsoft 365 A5 訂閱（付費或試用版）</span><span class="sxs-lookup"><span data-stu-id="e3509-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="e3509-113">Microsoft 365 A3 訂閱（或 Office 365 A3 訂閱 + Enterprise 可移動性和安全性 A3 訂閱） + Microsoft A5 符合性附加元件</span><span class="sxs-lookup"><span data-stu-id="e3509-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="e3509-114">教育版訂閱的任何 Microsoft 365、Office 365、Exchange、SharePoint 或 OneDrive，也就是 Microsoft 365 A5 內幕人士風險管理附加元件</span><span class="sxs-lookup"><span data-stu-id="e3509-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="e3509-115">Office 365 企業版 E5 訂閱（付費或試用版）</span><span class="sxs-lookup"><span data-stu-id="e3509-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="e3509-116">Office 365 企業版 E3 訂閱 + Office 365 Advanced 合規性附加元件（已無法再供新訂閱使用，請參閱記事）</span><span class="sxs-lookup"><span data-stu-id="e3509-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="e3509-117">提交及回應特殊許可權存取管理要求的使用者，必須指派上述其中一個授權。</span><span class="sxs-lookup"><span data-stu-id="e3509-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e3509-118">Office 365 Advanced 合規性不再銷售為獨立訂閱。</span><span class="sxs-lookup"><span data-stu-id="e3509-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="e3509-119">當目前的訂閱到期時，客戶應轉換至上述其中一個訂閱，其中包含相同或其他的符合性功能。</span><span class="sxs-lookup"><span data-stu-id="e3509-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="e3509-120">如果您沒有現有的 Office 365 企業版 E5 計畫，且想要嘗試使用許可權存取管理，您可以[將 microsoft 365 新增](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)至現有的 office 365 訂閱，或註冊 Microsoft 365 企業版 e5 的[試用版](https://www.microsoft.com/microsoft-365/enterprise)。</span><span class="sxs-lookup"><span data-stu-id="e3509-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="e3509-121">啟用和設定特殊許可權存取管理</span><span class="sxs-lookup"><span data-stu-id="e3509-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="e3509-122">請遵循下列步驟來設定和使用您組織中的特殊許可權存取：</span><span class="sxs-lookup"><span data-stu-id="e3509-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="e3509-123">步驟1：建立核准者的群組</span><span class="sxs-lookup"><span data-stu-id="e3509-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="e3509-124">在開始使用「許可權存取」之前，請先決定誰需要核准授權，以便存取提升和特權的任務。</span><span class="sxs-lookup"><span data-stu-id="e3509-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="e3509-125">任何屬於核准者群組的使用者都可以核准存取要求。</span><span class="sxs-lookup"><span data-stu-id="e3509-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="e3509-126">您可以在 Office 365 中建立擁有郵件功能的安全性群組，以啟用此群組。</span><span class="sxs-lookup"><span data-stu-id="e3509-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="e3509-127">步驟2：啟用特殊許可權存取</span><span class="sxs-lookup"><span data-stu-id="e3509-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="e3509-128">必須明確啟用具有預設核准者群組的 Office 365 中的許可權存取，包括您想要從特殊許可權存取管理存取控制中排除的一組系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="e3509-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="e3509-129">步驟3：建立存取原則</span><span class="sxs-lookup"><span data-stu-id="e3509-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="e3509-130">建立核准原則可讓您定義個別任務的特定核准需求範圍。</span><span class="sxs-lookup"><span data-stu-id="e3509-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="e3509-131">核准類型選項為**自動**或**手動**。</span><span class="sxs-lookup"><span data-stu-id="e3509-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="e3509-132">步驟4：提交/核准許可權存取要求</span><span class="sxs-lookup"><span data-stu-id="e3509-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="e3509-133">一旦啟用，「特殊許可權存取」會要求任何具有定義相關核准原則的任務的核准。</span><span class="sxs-lookup"><span data-stu-id="e3509-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="e3509-134">對於包含在核准原則中的工作，使用者必須要求並授與「存取權核准」，以具備執行工作所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="e3509-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="e3509-135">授與核准後，要求使用者可以執行預定的工作，而許可權存取將會代表使用者授權並執行工作。</span><span class="sxs-lookup"><span data-stu-id="e3509-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="e3509-136">核准對於要求的持續時間（預設工期為4小時）保持有效，在此期間，申請者可以多次執行預定的工作。</span><span class="sxs-lookup"><span data-stu-id="e3509-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="e3509-137">所有這類執行都會記錄下來，以進行安全性和合規性審核。</span><span class="sxs-lookup"><span data-stu-id="e3509-137">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="e3509-138">如果您想要使用 Exchange 管理 PowerShell 來啟用及設定特殊許可權存取，請依照使用 Multi-Factor 驗證連線至 exchange Online PowerShell 與 Office 365 認證，[使用 [連線至 Exchange online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="e3509-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="e3509-139">您不需要為組織啟用多重要素驗證，就能在連線至 Exchange Online PowerShell 時，使用這些步驟來啟用許可權存取。</span><span class="sxs-lookup"><span data-stu-id="e3509-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="e3509-140">使用多重要素驗證來建立 OAuth 權杖，以供簽署要求的授權存取使用。</span><span class="sxs-lookup"><span data-stu-id="e3509-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="e3509-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="e3509-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="e3509-142">步驟1：建立核准者的群組</span><span class="sxs-lookup"><span data-stu-id="e3509-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="e3509-143">使用組織中的系統管理員帳號憑證，登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="e3509-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="e3509-144">在系統管理中心中，移至 [**群組** > ] [**新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="e3509-145">選取 [擁有**郵件功能的安全性群組**]，然後完成新群組的**名稱**、**群組電子郵件地址**及**描述**欄位。</span><span class="sxs-lookup"><span data-stu-id="e3509-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="e3509-146">儲存群組。</span><span class="sxs-lookup"><span data-stu-id="e3509-146">Save the group.</span></span> <span data-ttu-id="e3509-147">可能需要幾分鐘的時間，才能完整設定群組，並顯示在 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="e3509-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="e3509-148">選取新的核准者群組，然後選取 [**編輯**]，將使用者新增至群組。</span><span class="sxs-lookup"><span data-stu-id="e3509-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="e3509-149">儲存群組。</span><span class="sxs-lookup"><span data-stu-id="e3509-149">Save the group.</span></span>

<span data-ttu-id="e3509-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="e3509-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="e3509-151">步驟2：啟用特殊許可權存取</span><span class="sxs-lookup"><span data-stu-id="e3509-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="e3509-152">在 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="e3509-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="e3509-153">使用組織中的系統管理員帳號憑證，登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="e3509-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="e3509-154">在系統管理中心中，移至 [**設定] > 設定 > 安全性 & 隱私權** > **許可權存取**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-154">In the Admin Center, go to **Settings > Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e3509-155">啟用 [對**特權任務需要核准**] 控制項。</span><span class="sxs-lookup"><span data-stu-id="e3509-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="e3509-156">將您在步驟1中建立的核准者群組指派為預設的 [**核准者] 群組**。</span><span class="sxs-lookup"><span data-stu-id="e3509-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="e3509-157">**儲存**並**關閉**。</span><span class="sxs-lookup"><span data-stu-id="e3509-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="e3509-158">在 Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3509-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="e3509-159">若要啟用特殊許可權存取並指派核准者的群組，請在 Exchange Online 中執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e3509-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="e3509-160">範例：</span><span class="sxs-lookup"><span data-stu-id="e3509-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="e3509-161">系統帳戶功能可供使用，以確保組織內的某些自動化可以運作，而不需要對特殊許可權存取進行相依性存取，但是建議您不要使用，且應該定期核准和審核這些排除專案。</span><span class="sxs-lookup"><span data-stu-id="e3509-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="e3509-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="e3509-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="e3509-163">步驟3：建立存取原則</span><span class="sxs-lookup"><span data-stu-id="e3509-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="e3509-164">您可以為組織建立及設定最多30個許可權存取原則。</span><span class="sxs-lookup"><span data-stu-id="e3509-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="e3509-165">在 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="e3509-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="e3509-166">使用組織中的系統管理員帳號憑證，登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="e3509-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="e3509-167">在系統管理中心中，移至 [**設定** > **安全性 & 隱私權** > 特殊**許可權存取**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e3509-168">選取 [**管理存取原則和要求**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="e3509-169">選取 [**設定原則**]，然後選取 [**新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="e3509-170">從下拉欄位中，為您的組織選取適當的值：</span><span class="sxs-lookup"><span data-stu-id="e3509-170">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="e3509-171">**原則類型**：任務、角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="e3509-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="e3509-172">**原則範圍**： Exchange</span><span class="sxs-lookup"><span data-stu-id="e3509-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="e3509-173">**原則名稱**：從可用原則中選取</span><span class="sxs-lookup"><span data-stu-id="e3509-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="e3509-174">**核准類型**：手動或自動</span><span class="sxs-lookup"><span data-stu-id="e3509-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="e3509-175">**核准群組**：選取步驟1中建立的核准者群組</span><span class="sxs-lookup"><span data-stu-id="e3509-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="e3509-176">選取 [**建立**後**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="e3509-177">可能需要幾分鐘的時間，才能完全設定或啟用原則。</span><span class="sxs-lookup"><span data-stu-id="e3509-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="e3509-178">在 Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3509-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="e3509-179">若要建立及定義核准原則，請在 Exchange Online 中執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e3509-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="e3509-180">範例：</span><span class="sxs-lookup"><span data-stu-id="e3509-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="e3509-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="e3509-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="e3509-182">步驟4：提交/核准許可權存取要求</span><span class="sxs-lookup"><span data-stu-id="e3509-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="e3509-183">要求提升授權以執行特權任務</span><span class="sxs-lookup"><span data-stu-id="e3509-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="e3509-184">在提交要求後，可長達24小時的許可權存取要求是有效的。</span><span class="sxs-lookup"><span data-stu-id="e3509-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="e3509-185">若未核准或拒絕，要求便會到期，而且不會核准存取權。</span><span class="sxs-lookup"><span data-stu-id="e3509-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="e3509-186">在 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="e3509-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="e3509-187">使用您的認證登入[Microsoft 365 Admin Center](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="e3509-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="e3509-188">在系統管理中心中，移至 [**設定** > **安全性 & 隱私權** > 特殊**許可權存取**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-188">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e3509-189">選取 [**管理存取原則和要求**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="e3509-190">選取 [**新增要求**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-190">Select **New request**.</span></span> <span data-ttu-id="e3509-191">從下拉欄位中，為您的組織選取適當的值：</span><span class="sxs-lookup"><span data-stu-id="e3509-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="e3509-192">**要求類型**：任務、角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="e3509-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="e3509-193">**要求範圍**： Exchange</span><span class="sxs-lookup"><span data-stu-id="e3509-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="e3509-194">**要求**：從可用原則選取</span><span class="sxs-lookup"><span data-stu-id="e3509-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="e3509-195">**持續時間（小時）**：要求存取的小時數。</span><span class="sxs-lookup"><span data-stu-id="e3509-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="e3509-196">可要求的小時數沒有限制。</span><span class="sxs-lookup"><span data-stu-id="e3509-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="e3509-197">**批註**：與您的 access 要求相關的註解文字欄位</span><span class="sxs-lookup"><span data-stu-id="e3509-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="e3509-198">選取 [**儲存**並**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="e3509-199">您的要求將透過電子郵件傳送給核准者的群組。</span><span class="sxs-lookup"><span data-stu-id="e3509-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="e3509-200">在 Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3509-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="e3509-201">在 Exchange Online PowerShell 中執行下列命令，以建立並提交核准者群組的核准要求：</span><span class="sxs-lookup"><span data-stu-id="e3509-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="e3509-202">範例：</span><span class="sxs-lookup"><span data-stu-id="e3509-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="e3509-203">查看提升要求狀態</span><span class="sxs-lookup"><span data-stu-id="e3509-203">View status of elevation requests</span></span>

<span data-ttu-id="e3509-204">在建立核准要求之後，可以在系統管理中心或 Exchange Management PowerShell 中，使用與要求識別碼相關聯的方式來複查提升要求狀態。</span><span class="sxs-lookup"><span data-stu-id="e3509-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="e3509-205">在 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="e3509-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="e3509-206">使用您的認證登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="e3509-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="e3509-207">在系統管理中心中，移至 [**設定** > **安全性 & 隱私權** > 特殊**許可權存取**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-207">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e3509-208">選取 [**管理存取原則和要求**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="e3509-209">選取 [ **View** ] （提交）以透過**擱置**、**核准**、**拒絕**或**客戶密碼箱**狀態來篩選送出的要求。</span><span class="sxs-lookup"><span data-stu-id="e3509-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="e3509-210">在 Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3509-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="e3509-211">在 Exchange Online PowerShell 中執行下列命令，以查看特定要求的核准要求狀態 ID:</span><span class="sxs-lookup"><span data-stu-id="e3509-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="e3509-212">範例：</span><span class="sxs-lookup"><span data-stu-id="e3509-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="e3509-213">核准提升授權要求</span><span class="sxs-lookup"><span data-stu-id="e3509-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="e3509-214">建立核准要求時，相關核准者群組的成員會收到電子郵件通知，而且可以核准與要求識別碼相關聯的要求。</span><span class="sxs-lookup"><span data-stu-id="e3509-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="e3509-215">要求核准或透過電子郵件訊息的拒絕通知要求者。</span><span class="sxs-lookup"><span data-stu-id="e3509-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="e3509-216">在 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="e3509-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="e3509-217">使用您的認證登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="e3509-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="e3509-218">在系統管理中心中，移至 [**設定** > **安全性 & 隱私權** > 特殊**許可權存取**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-218">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e3509-219">選取 [**管理存取原則和要求**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="e3509-220">選取列出的要求以查看詳細資料，並對要求採取動作。</span><span class="sxs-lookup"><span data-stu-id="e3509-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="e3509-221">選取 [**核准**] 以核准要求，或選取 [**拒絕**] 以拒絕要求。</span><span class="sxs-lookup"><span data-stu-id="e3509-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="e3509-222">先前核准的要求可以透過選取 **[撤銷]** 來撤銷存取權。</span><span class="sxs-lookup"><span data-stu-id="e3509-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="e3509-223">在 Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3509-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="e3509-224">若要核准提升授權要求，請在 Exchange Online 中執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e3509-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="e3509-225">範例：</span><span class="sxs-lookup"><span data-stu-id="e3509-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="e3509-226">若要拒絕提升授權要求，請在 Exchange Online 中執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e3509-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="e3509-227">範例：</span><span class="sxs-lookup"><span data-stu-id="e3509-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="e3509-228">刪除 Office 365 中的許可權存取原則</span><span class="sxs-lookup"><span data-stu-id="e3509-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="e3509-229">如果您的組織已不再需要該原則，您可以刪除特殊許可權存取原則。</span><span class="sxs-lookup"><span data-stu-id="e3509-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="e3509-230">在 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="e3509-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="e3509-231">使用組織中的系統管理員帳號憑證，登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="e3509-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="e3509-232">在系統管理中心中，移至 [**設定** > **安全性 & 隱私權** > 特殊**許可權存取**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-232">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e3509-233">選取 [**管理存取原則和要求**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="e3509-234">選取 [**設定原則**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="e3509-235">選取您要刪除的原則，然後選取 [**移除原則**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="e3509-236">選取 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="e3509-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="e3509-237">在 Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3509-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="e3509-238">若要刪除特殊許可權存取原則，請在 Exchange Online Powershell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e3509-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="e3509-239">停用 Office 365 的特殊許可權存取</span><span class="sxs-lookup"><span data-stu-id="e3509-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="e3509-240">如有需要，您可以停用組織的特殊許可權存取管理。</span><span class="sxs-lookup"><span data-stu-id="e3509-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="e3509-241">停用特殊許可權存取不會刪除任何關聯的核准原則或核准者群組。</span><span class="sxs-lookup"><span data-stu-id="e3509-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="e3509-242">在 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="e3509-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="e3509-243">使用組織中的系統管理員帳戶的認證登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="e3509-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="e3509-244">在系統管理中心中，移至 [**設定** > **安全性 & 隱私權** > 特殊**許可權存取**]。</span><span class="sxs-lookup"><span data-stu-id="e3509-244">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e3509-245">啟用 [**需要核准存取**許可權] 控制。</span><span class="sxs-lookup"><span data-stu-id="e3509-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="e3509-246">在 Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3509-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="e3509-247">若要停用特殊許可權存取，請在 Exchange Online Powershell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e3509-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
