---
title: 適用于 Microsoft 365 企業版測試環境的特殊許可權存取管理
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
description: 使用此測試實驗室指南可啟用您的 Microsoft 365 企業版測試環境的特殊許可權存取管理。
ms.openlocfilehash: 28fd27c3059fe25da5da8aaf8700b84c5989b408
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695143"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="2e3c6-103">適用于 Microsoft 365 企業版測試環境的特殊許可權存取管理</span><span class="sxs-lookup"><span data-stu-id="2e3c6-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="2e3c6-104">*此測試實驗室指南可用於 enterprise 和 Office 365 企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="2e3c6-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="2e3c6-105">透過本文中的指示，您可以設定特殊許可權存取管理，以提升 Microsoft 365 for enterprise 測試環境中的安全性。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-105">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
><span data-ttu-id="2e3c6-107">按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，可查看企業用 Microsoft 365 測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="2e3c6-108">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="2e3c6-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="2e3c6-109">如果您只想以輕量的方式設定特殊許可權存取管理，請依照 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-109">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="2e3c6-110">如果您想要在模擬的企業中設定特殊許可權存取管理，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-110">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="2e3c6-111">測試特殊許可權存取管理不需要模擬企業測試環境，包括連接至網際網路的模擬內部網路和 AD DS 樹系的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-111">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="2e3c6-112">這裡是以選項形式提供，讓您可以在代表一般組織的環境中測試特殊許可權存取管理，並進行試驗。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-112">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="2e3c6-113">階段2：設定特殊許可權存取管理</span><span class="sxs-lookup"><span data-stu-id="2e3c6-113">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="2e3c6-114">在此階段中，您會設定核准群組，並為您的 Microsoft 365 for enterprise 測試環境啟用特殊存取權存取管理。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-114">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="2e3c6-115">如需詳細資訊及特殊許可權存取管理的概要資訊，請參閱「特殊許可權 [存取管理](../compliance/privileged-access-management-overview.md)」。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-115">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="2e3c6-116">請遵循下列步驟來設定和使用您組織中的特殊許可權存取：</span><span class="sxs-lookup"><span data-stu-id="2e3c6-116">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="2e3c6-117">步驟1：建立核准者的群組</span><span class="sxs-lookup"><span data-stu-id="2e3c6-117">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

    <span data-ttu-id="2e3c6-118">在您開始使用「許可權存取」之前，請先決定誰有權存取已升高和特權任務的傳入要求。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-118">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="2e3c6-119">任何屬於核准者群組的使用者都可以核准存取要求。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-119">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="2e3c6-120">若要啟用此功能，可在 Microsoft 365 中建立擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-120">This is enabled by creating a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="2e3c6-121">在測試環境中建立名為「特權存取核准者」的新安全性群組，並新增先前在測試實驗室指南步驟中建立的「使用者3」。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-121">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="2e3c6-122">步驟2：啟用特殊許可權存取</span><span class="sxs-lookup"><span data-stu-id="2e3c6-122">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

    <span data-ttu-id="2e3c6-123">必須在 Microsoft 365 中以預設核准者群組明確開啟特殊許可權存取，並包含您想要從「特殊許可權存取管理存取控制」中排除的一組系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-123">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="2e3c6-124">請務必在您的組織中啟用特殊許可權的存取，再開始本指南的第3階段。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-124">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="2e3c6-125">階段3：確認是否需要核准以進行提升和特權工作</span><span class="sxs-lookup"><span data-stu-id="2e3c6-125">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="2e3c6-126">在此階段中，您會驗證特權存取原則是否正常運作，且使用者必須核准，才能執行已定義的高許可權和特權工作。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-126">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="2e3c6-127">測試執行沒有在特權存取原則中定義的工作的能力</span><span class="sxs-lookup"><span data-stu-id="2e3c6-127">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="2e3c6-128">首先，以您的測試環境中設定為全域系統管理員之使用者的認證來連線至 Exchange 管理 PowerShell，並嘗試建立新的日誌規則。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-128">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="2e3c6-129">目前未在組織的特殊許可權存取原則中定義 [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule?view=exchange-ps) 任務。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-129">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="2e3c6-130">在您的本機電腦上， **Microsoft Corporation**  >  使用您測試環境的全域系統管理員帳戶，在 microsoft**exchange online remote PowerShell 模組**中開啟 Exchange online 遠端 PowerShell 模組，並登入。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-130">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2e3c6-131">在 Exchange 管理 PowerShell 中，為您的組織建立新的日誌規則：</span><span class="sxs-lookup"><span data-stu-id="2e3c6-131">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="2e3c6-132">查看已在 Exchange Management PowerShell 中成功建立新的日誌規則。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-132">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="2e3c6-133">為 New-JournalRule 工作建立新的許可權存取原則</span><span class="sxs-lookup"><span data-stu-id="2e3c6-133">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="2e3c6-134">如果您還沒有完成本指南第2階段中的步驟1和2，請確定遵循下列步驟，建立名為「許可權存取核准者」的核准者群組，並在您的測試環境中啟用特殊許可權存取。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-134">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="2e3c6-135">使用認證來登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) 您的測試環境全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-135">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2e3c6-136">在系統管理中心中，移至 [**設定**  >  **安全性 & 隱私權**特殊  >  **許可權存取**]。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-136">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="2e3c6-137">選取 [ **管理存取原則和要求**]。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-137">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="2e3c6-138">選取 [ **設定原則** ]，然後選取 [ **新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-138">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="2e3c6-139">從下拉欄位中，選取或輸入下列值：</span><span class="sxs-lookup"><span data-stu-id="2e3c6-139">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="2e3c6-140">**原則類型**：任務</span><span class="sxs-lookup"><span data-stu-id="2e3c6-140">**Policy type**: Task</span></span>

    <span data-ttu-id="2e3c6-141">**原則範圍**： Exchange</span><span class="sxs-lookup"><span data-stu-id="2e3c6-141">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="2e3c6-142">**原則名稱**：新增日誌規則</span><span class="sxs-lookup"><span data-stu-id="2e3c6-142">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="2e3c6-143">**核准類型**：手動</span><span class="sxs-lookup"><span data-stu-id="2e3c6-143">**Approval type**: Manual</span></span>

    <span data-ttu-id="2e3c6-144">**核准群組**：許可權存取核准者</span><span class="sxs-lookup"><span data-stu-id="2e3c6-144">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="2e3c6-145">選取 [ **建立** 後 **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-145">Select **Create** and then **Close**.</span></span> <span data-ttu-id="2e3c6-146">可能需要幾分鐘的時間，才能完全設定或啟用原則。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-146">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="2e3c6-147">在下一個步驟中測試核准需求之前，請務必允許完整啟用該原則的時間。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-147">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="2e3c6-148">測試許可權存取原則中所定義之 New-JournalRule 工作的核准需求</span><span class="sxs-lookup"><span data-stu-id="2e3c6-148">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="2e3c6-149">在您的本機電腦上， **Microsoft Corporation**  >  使用您測試環境的全域系統管理員帳戶，在 microsoft**exchange online remote PowerShell 模組**中開啟 Exchange online 遠端 PowerShell 模組，並登入。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-149">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2e3c6-150">在 Exchange 管理 PowerShell 中，為您的組織建立新的日誌規則：</span><span class="sxs-lookup"><span data-stu-id="2e3c6-150">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="2e3c6-151">在 Exchange 管理 PowerShell: 中查看「許可權不足」的錯誤</span><span class="sxs-lookup"><span data-stu-id="2e3c6-151">View "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="2e3c6-152">要求存取使用 New-JournalRule 任務建立新的日誌規則</span><span class="sxs-lookup"><span data-stu-id="2e3c6-152">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="2e3c6-153">使用您測試環境的全域系統管理員帳戶登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-153">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2e3c6-154">在系統管理中心中，移至 [**設定**  >  **安全性 & 隱私權**特殊  >  **許可權存取**]。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-154">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="2e3c6-155">選取 [ **管理存取原則和要求**]。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-155">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="2e3c6-156">選取 [ **新增要求**]。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-156">Select **New request**.</span></span> <span data-ttu-id="2e3c6-157">從下拉欄位中，為您的組織選取適當的值：</span><span class="sxs-lookup"><span data-stu-id="2e3c6-157">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="2e3c6-158">**要求類型**：任務</span><span class="sxs-lookup"><span data-stu-id="2e3c6-158">**Request type**: Task</span></span>

    <span data-ttu-id="2e3c6-159">**要求範圍**： Exchange</span><span class="sxs-lookup"><span data-stu-id="2e3c6-159">**Request scope**: Exchange</span></span>

    <span data-ttu-id="2e3c6-160">**要求**：新增日誌規則</span><span class="sxs-lookup"><span data-stu-id="2e3c6-160">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="2e3c6-161">\*\*Duration (小時) \*\*：2</span><span class="sxs-lookup"><span data-stu-id="2e3c6-161">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="2e3c6-162">**批註**：要求許可權以建立新的日誌規則</span><span class="sxs-lookup"><span data-stu-id="2e3c6-162">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="2e3c6-163">選取 [ **儲存** 並 **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-163">Select **Save** and then **Close**.</span></span> <span data-ttu-id="2e3c6-164">您的要求將透過電子郵件傳送給核准者的群組。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-164">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="2e3c6-165">核准建立新的日誌規則的特殊許可權存取要求</span><span class="sxs-lookup"><span data-stu-id="2e3c6-165">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="2e3c6-166">在測試環境中，使用使用者3的認證，登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) 。) 中的「特權存取核准者」安全性群組的成員 (。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-166">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="2e3c6-167">在系統管理中心中，移至 [**設定**  >  **安全性 & 隱私權**特殊  >  **許可權存取**]。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="2e3c6-168">選取 [ **管理存取原則和要求**]。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="2e3c6-169">選取 [擱置的要求]，然後選取 [ **核准** ]，以將存取權授與全域管理員帳戶，以建立新的日誌規則。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-169">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="2e3c6-170">已授與核准的通知電子郵件會傳送至全域管理員帳戶， (要求使用者) 。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-170">A notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="2e3c6-171">測試使用 New-JournalRule 工作核准的特殊存取權來建立新的日誌規則</span><span class="sxs-lookup"><span data-stu-id="2e3c6-171">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="2e3c6-172">在您的本機電腦上， **Microsoft Corporation**  >  使用您測試環境的全域系統管理員帳戶，在 microsoft**exchange online remote PowerShell 模組**中開啟 Exchange online 遠端 PowerShell 模組，並登入。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-172">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2e3c6-173">在 Exchange 管理 PowerShell 中，為您的組織建立新的日誌規則：</span><span class="sxs-lookup"><span data-stu-id="2e3c6-173">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="2e3c6-174">查看已在 Exchange Management PowerShell 中成功建立新的日誌規則。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-174">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="2e3c6-175">下一步</span><span class="sxs-lookup"><span data-stu-id="2e3c6-175">Next step</span></span>

<span data-ttu-id="2e3c6-176">在您的測試環境中探索其他 [資訊保護](m365-enterprise-test-lab-guides.md#information-protection) 功能和功能。</span><span class="sxs-lookup"><span data-stu-id="2e3c6-176">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e3c6-177">請參閱</span><span class="sxs-lookup"><span data-stu-id="2e3c6-177">See also</span></span>

[<span data-ttu-id="2e3c6-178">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="2e3c6-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2e3c6-179">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="2e3c6-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2e3c6-180">適用于企業的 Microsoft 365 檔</span><span class="sxs-lookup"><span data-stu-id="2e3c6-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
