---
title: 適用于企業測試環境的 Microsoft 365 的特殊許可權存取管理
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: 使用此測試實驗室指南可啟用企業測試環境的 Microsoft 365 的許可權存取管理。
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126414"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ecc7c-103">適用于企業測試環境的 Microsoft 365 的特殊許可權存取管理</span><span class="sxs-lookup"><span data-stu-id="ecc7c-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ecc7c-104">*此測試實驗室指南可用於 enterprise 和 Office 365 企業版測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="ecc7c-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="ecc7c-105">本文說明如何設定特殊許可權存取管理，以提升企業測試環境中 Microsoft 365 的安全性。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="ecc7c-106">設定 priviledged 存取管理包括三個階段：</span><span class="sxs-lookup"><span data-stu-id="ecc7c-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="ecc7c-107">階段1：組建您的企業測試環境 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ecc7c-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="ecc7c-108">階段2：設定特殊許可權存取管理</span><span class="sxs-lookup"><span data-stu-id="ecc7c-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="ecc7c-109">階段3：確認是否需要核准以進行提升和特權工作</span><span class="sxs-lookup"><span data-stu-id="ecc7c-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="ecc7c-111">如需適用于企業測試實驗室指南堆疊的 Microsoft 365 中的所有文章的視覺對應，請移至[Microsoft 365 for enterprise test lab guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ecc7c-112">階段1：組建您的企業測試環境 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ecc7c-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ecc7c-113">若要以輕量的方式設定特殊許可權存取管理，請遵循 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ecc7c-114">如果您想要在模擬的企業中設定特殊許可權存取管理，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="ecc7c-115">測試特殊許可權存取管理不需要模擬的企業測試環境，包括連接至網際網路的模擬內部網路和 Active Directory 網域服務樹系的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="ecc7c-116">它是以選項形式提供，讓您可以在代表一般組織的環境中測試特殊許可權的存取管理，並進行試驗。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="ecc7c-117">階段2：設定特殊許可權存取管理</span><span class="sxs-lookup"><span data-stu-id="ecc7c-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="ecc7c-118">在這個階段中，設定 [核准者] 群組，並為您的 Microsoft 365 企業測試環境啟用特殊許可權存取管理。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="ecc7c-119">如需詳細資訊及特殊許可權存取管理的概要資訊，請參閱「特殊許可權 [存取管理](../compliance/privileged-access-management-overview.md)」。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="ecc7c-120">若要在組織中設定及使用特殊許可權存取，請執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="ecc7c-121">步驟1：建立核准者的群組</span><span class="sxs-lookup"><span data-stu-id="ecc7c-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="ecc7c-122">在開始使用「特殊許可權存取」之前，請先決定誰將有權存取已升高和特權任務的傳入要求。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="ecc7c-123">所有屬於核准者群組的使用者都可以核准存取要求。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="ecc7c-124">若要使用特殊許可權存取，您必須在 Microsoft 365 中建立擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="ecc7c-125">在測試環境中，將新的安全性群組命名為「特權存取核准者」，並新增先前在先前的測試實驗室指南步驟中所建立的「使用者3」。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="ecc7c-126">步驟2：啟用特殊許可權存取</span><span class="sxs-lookup"><span data-stu-id="ecc7c-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="ecc7c-127">在具有預設核准群組的 Microsoft 365 中，必須明確地開啟特殊許可權存取，而且必須包含您要從特殊許可權存取管理存取控制中排除的一組系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="ecc7c-128">請務必在您的組織中啟用特殊許可權的存取，再開始本指南的第3階段。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="ecc7c-129">階段3：確認是否需要核准以進行提升和特權工作</span><span class="sxs-lookup"><span data-stu-id="ecc7c-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="ecc7c-130">在這個階段中，請確認 [許可權存取原則] 正常運作，且使用者需要核准，才能執行已定義的高許可權和特權工作。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="ecc7c-131">測試執行非特權存取原則中所定義之工作的能力</span><span class="sxs-lookup"><span data-stu-id="ecc7c-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="ecc7c-132">首先，以您的測試環境中已設定為全域系統管理員之使用者的認證，連接至 Exchange 管理 PowerShell，並嘗試建立新的日誌規則。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="ecc7c-133">目前未在組織的特殊許可權存取原則中定義 [New-JournalRule](/powershell/module/exchange/new-journalrule) 任務。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-133">The [New-JournalRule](/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="ecc7c-134">在您的本機電腦上，使用您測試環境的全域系統管理員帳戶，開啟並登入 **Microsoft Corporation**  >  **Microsoft Exchange Online remote PowerShell 模組** 的 Exchange Online remote PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="ecc7c-135">在 Exchange 管理 PowerShell 中，為您的組織建立新的日誌規則：</span><span class="sxs-lookup"><span data-stu-id="ecc7c-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="ecc7c-136">在 Exchange 管理 PowerShell 中，查看是否已成功建立新的日誌規則。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="ecc7c-137">為 New-JournalRule 工作建立新的許可權存取原則</span><span class="sxs-lookup"><span data-stu-id="ecc7c-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="ecc7c-138">如果您還沒有完成本指南第2階段的步驟1和2，請務必遵循下列步驟，建立名為「許可權存取核准者」的核准者群組，以在您的測試環境中啟用特殊許可權存取。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="ecc7c-139">使用認證來登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)您的測試環境全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="ecc7c-140">在系統管理中心，移至 **設定**  >  **安全性 & 隱私權** 的特殊許可權  >  **存取**。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ecc7c-141">選取 [ **管理存取原則和要求**]。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ecc7c-142">選取 [ **設定原則**]，然後選取 [ **新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="ecc7c-143">從下拉欄位中，選取或輸入下列值：</span><span class="sxs-lookup"><span data-stu-id="ecc7c-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="ecc7c-144">**原則類型**：任務</span><span class="sxs-lookup"><span data-stu-id="ecc7c-144">**Policy type**: Task</span></span>

    <span data-ttu-id="ecc7c-145">**原則範圍**：Exchange</span><span class="sxs-lookup"><span data-stu-id="ecc7c-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="ecc7c-146">**原則名稱**：新增日誌規則</span><span class="sxs-lookup"><span data-stu-id="ecc7c-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="ecc7c-147">**核准類型**：手動</span><span class="sxs-lookup"><span data-stu-id="ecc7c-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="ecc7c-148">**核准群組**：許可權存取核准者</span><span class="sxs-lookup"><span data-stu-id="ecc7c-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="ecc7c-149">選取 **[建立]**，然後選取 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="ecc7c-150">可能需要幾分鐘的時間，才能完全設定或啟用原則。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="ecc7c-151">在下一個步驟中測試核准需求之前，請務必允許完整啟用該原則的時間。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="ecc7c-152">測試許可權存取原則中所定義之 New-JournalRule 工作的核准需求</span><span class="sxs-lookup"><span data-stu-id="ecc7c-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="ecc7c-153">在您的本機電腦上，使用為測試環境使用全域系統管理員帳戶，開啟並登入 **Microsoft Corporation** 的 Exchange Online remote PowerShell 模組  >  **Microsoft Exchange Online remote PowerShell Module** 。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="ecc7c-154">在 Exchange 管理 PowerShell 中，為您的組織建立新的日誌規則：</span><span class="sxs-lookup"><span data-stu-id="ecc7c-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="ecc7c-155">在 Exchange 管理 PowerShell: 中查看「許可權不足」的錯誤</span><span class="sxs-lookup"><span data-stu-id="ecc7c-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="ecc7c-156">要求存取使用 New-JournalRule 任務建立新的日誌規則</span><span class="sxs-lookup"><span data-stu-id="ecc7c-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="ecc7c-157">使用測試環境的全域系統管理員帳戶登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="ecc7c-158">在系統管理中心，移至 **設定**  >  **安全性 & 隱私權** 的特殊許可權  >  **存取**。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ecc7c-159">選取 [ **管理存取原則和要求**]。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ecc7c-160">選取 [ **新增要求**]。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-160">Select **New request**.</span></span> <span data-ttu-id="ecc7c-161">從下拉欄位中，為您的組織選取適當的值：</span><span class="sxs-lookup"><span data-stu-id="ecc7c-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="ecc7c-162">**要求類型**：任務</span><span class="sxs-lookup"><span data-stu-id="ecc7c-162">**Request type**: Task</span></span>

    <span data-ttu-id="ecc7c-163">**要求範圍**：Exchange</span><span class="sxs-lookup"><span data-stu-id="ecc7c-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="ecc7c-164">**要求**：新增日誌規則</span><span class="sxs-lookup"><span data-stu-id="ecc7c-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="ecc7c-165">**Duration (小時)**：2</span><span class="sxs-lookup"><span data-stu-id="ecc7c-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="ecc7c-166">**批註**：要求許可權以建立新的日誌規則</span><span class="sxs-lookup"><span data-stu-id="ecc7c-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="ecc7c-167">選取 [ **儲存**]，然後選取 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="ecc7c-168">您的要求將透過電子郵件傳送給核准者的群組。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="ecc7c-169">核准建立新的日誌規則的特殊許可權存取要求</span><span class="sxs-lookup"><span data-stu-id="ecc7c-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="ecc7c-170">在測試環境中，使用使用者3的認證 () 測試環境中的「特權存取核准者」安全性群組的成員，登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="ecc7c-171">在系統管理中心，移至 **設定**  >  **安全性 & 隱私權** 的特殊許可權  >  **存取**。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ecc7c-172">選取 [ **管理存取原則和要求**]。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ecc7c-173">選取 [擱置的要求]，然後選取 [ **核准** ]，以將存取權授與全域管理員帳戶，以建立新的日誌規則。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="ecc7c-174">「全域管理員帳戶」 (要求使用者) 會收到核准已授與的電子郵件確認。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="ecc7c-175">測試使用 New-JournalRule 工作核准的特殊存取權來建立新的日誌規則</span><span class="sxs-lookup"><span data-stu-id="ecc7c-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="ecc7c-176">在您的本機電腦上，使用您測試環境的全域系統管理員帳戶，開啟並登入 **Microsoft Corporation**  >  **Microsoft Exchange Online remote PowerShell 模組** 的 Exchange Online remote PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="ecc7c-177">在 Exchange 管理 PowerShell 中，為您的組織建立新的日誌規則：</span><span class="sxs-lookup"><span data-stu-id="ecc7c-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="ecc7c-178">在 Exchange 管理 PowerShell 中，查看是否已成功建立新的日誌規則。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="ecc7c-179">下一步</span><span class="sxs-lookup"><span data-stu-id="ecc7c-179">Next step</span></span>

<span data-ttu-id="ecc7c-180">在您的測試環境中探索其他 [資訊保護](m365-enterprise-test-lab-guides.md#information-protection) 功能和功能。</span><span class="sxs-lookup"><span data-stu-id="ecc7c-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ecc7c-181">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ecc7c-181">See also</span></span>

[<span data-ttu-id="ecc7c-182">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="ecc7c-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ecc7c-183">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="ecc7c-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ecc7c-184">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="ecc7c-184">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
